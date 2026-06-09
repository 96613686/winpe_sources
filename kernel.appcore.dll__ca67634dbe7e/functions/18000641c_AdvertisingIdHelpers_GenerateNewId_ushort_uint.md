# AdvertisingIdHelpers::GenerateNewId(ushort *,uint)

- ea: `0x18000641c`
- end: `0x1800064c9`
- name: `?GenerateNewId@AdvertisingIdHelpers@@YAJPEAGI@Z`
- size: `173`
- prototype: `__int64 __fastcall(AdvertisingIdHelpers *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006354`

## callees

- `0x1800032c0`
- `0x180006324`
- `0x18000641c`
- `0x180009dd0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180006441`
- `RPCRT4!UuidCreate` at `0x180006441`

## pseudocode

```c
RPC_STATUS __fastcall AdvertisingIdHelpers::GenerateNewId(AdvertisingIdHelpers *this, unsigned __int16 *a2)
{
  RPC_STATUS result; // eax
  int v4; // eax
  int v5; // ebx
  int v6; // [rsp+20h] [rbp-48h]
  int v7; // [rsp+20h] [rbp-48h]
  int v8; // [rsp+28h] [rbp-40h]
  int v9; // [rsp+30h] [rbp-38h]
  UUID Uuid; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  Uuid = 0;
  result = UuidCreate(&Uuid);
  if ( !result || result == 1824 )
  {
    v9 = *(_DWORD *)&Uuid.Data4[4];
    v8 = *(_DWORD *)Uuid.Data4;
    v6 = *(_DWORD *)&Uuid.Data2;
    v4 = StringCchPrintfW((unsigned __int16 *)this, 0x21u, L"%08x%08x%08x%08x", Uuid.Data1, v6, v8, v9);
    v5 = v4;
    if ( v4 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
        (const char *)(unsigned int)v4,
        v7);
      return v5;
    }
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000641c  push    rbx
0x18000641e  sub     rsp, 60h
0x180006422  mov     rax, cs:__security_cookie
0x180006429  xor     rax, rsp
0x18000642c  mov     [rsp+68h+var_18], rax
0x180006431  mov     rbx, rcx
0x180006434  xorps   xmm0, xmm0
0x180006437  lea     rcx, [rsp+68h+Uuid]; Uuid
0x18000643c  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x180006441  call    cs:__imp_UuidCreate
0x180006447  test    eax, eax
0x180006449  jz      short loc_180006460
0x18000644b  cmp     eax, 720h
0x180006450  jz      short loc_180006460
0x180006452  test    eax, eax
0x180006454  jle     short loc_1800064B6
0x180006456  movzx   eax, ax
0x180006459  or      eax, 80070000h
0x18000645e  jmp     short loc_1800064B6
0x180006460  mov     eax, dword ptr [rsp+68h+Uuid.Data4+4]
0x180006464  lea     r8, a08x08x08x08x; "%08x%08x%08x%08x"
0x18000646b  mov     r9d, [rsp+68h+Uuid.Data1]
0x180006470  mov     edx, 21h ; '!'; unsigned __int64
0x180006475  mov     [rsp+68h+var_38], eax
0x180006479  mov     rcx, rbx; unsigned __int16 *
0x18000647c  mov     eax, dword ptr [rsp+68h+Uuid.Data4]
0x180006480  mov     [rsp+68h+var_40], eax
0x180006484  mov     eax, dword ptr [rsp+68h+Uuid.Data2]
0x180006488  mov     [rsp+68h+var_48], eax; int
0x18000648c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006491  mov     ebx, eax
0x180006493  test    eax, eax
0x180006495  jns     short loc_1800064B4
0x180006497  mov     rcx, [rsp+68h]; this
0x18000649c  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800064a3  mov     r9d, eax; char *
0x1800064a6  mov     edx, 5Dh ; ']'; void *
0x1800064ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800064b0  mov     eax, ebx
0x1800064b2  jmp     short loc_1800064B6
0x1800064b4  xor     eax, eax
0x1800064b6  mov     rcx, [rsp+68h+var_18]
0x1800064bb  xor     rcx, rsp; StackCookie
0x1800064be  call    __security_check_cookie
0x1800064c3  add     rsp, 60h
0x1800064c7  pop     rbx
0x1800064c8  retn
```
