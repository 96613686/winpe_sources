# Coerce_MiInstance_ToBool

- ea: `0x1800440f0`
- end: `0x1800441ff`
- name: `Coerce_MiInstance_ToBool`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180044208`

## callees

- `0x180006ef8`
- `0x1800076d0`
- `0x180007c80`
- `0x1800440f0`
- `0x180044208`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18004414a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18004414a`

## string_xrefs

- `0x18004413f`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall Coerce_MiInstance_ToBool(__int64 a1, _BYTE *a2)
{
  unsigned int v2; // edi
  HMODULE ModuleHandleA; // rax
  _DWORD v7[4]; // [rsp+30h] [rbp-19h] BYREF
  __int128 v8; // [rsp+40h] [rbp-9h]
  _OWORD v9[3]; // [rsp+50h] [rbp+7h] BYREF

  v2 = 0;
  if ( a1 )
  {
    if ( Observable_FromInstance() )
    {
      v8 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      BYTE8(v8) = 0;
      *(_QWORD *)&v8 = Intlstr_GetString_LoadString(ModuleHandleA, 2000);
      v2 = 7;
      MI_ReportErrorDetails_ForCustomError(7, (int)L"MI", 0, 0);
    }
    else
    {
      v7[0] = 0;
      memset(v9, 0, sizeof(v9));
      Unbox(a1, v7, v9);
      if ( v7[0] )
      {
        if ( (DWORD1(v9[0]) & 0x20000000) != 0 )
          *a2 = 0;
        else
          return (unsigned int)Coerce_MiValue_ToBool(LODWORD(v9[0]), (char *)v9 + 8, a2);
      }
      else
      {
        *a2 = 1;
      }
    }
  }
  else
  {
    *a2 = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800440f0  mov     [rsp-8+arg_10], rbx
0x1800440f5  push    rbp
0x1800440f6  push    rsi
0x1800440f7  push    rdi
0x1800440f8  lea     rbp, [rsp-47h]
0x1800440fd  sub     rsp, 90h
0x180044104  mov     rax, cs:__security_cookie
0x18004410b  xor     rax, rsp
0x18004410e  mov     [rbp+57h+var_20], rax
0x180044112  xor     edi, edi
0x180044114  mov     rbx, rdx
0x180044117  mov     rsi, rcx
0x18004411a  test    rcx, rcx
0x18004411d  jnz     short loc_180044127
0x18004411f  mov     [rdx], dil
0x180044122  jmp     loc_1800441DE
0x180044127  mov     rax, cs:off_180047B90
0x18004412e  mov     rax, [rax+8]
0x180044132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044137  xorps   xmm0, xmm0
0x18004413a  test    rax, rax
0x18004413d  jz      short loc_180044196
0x18004413f  lea     rcx, ModuleName; "mpunits.dll"
0x180044146  movups  [rbp+57h+var_60], xmm0
0x18004414a  call    cs:__imp_GetModuleHandleA
0x180044150  mov     rcx, rax
0x180044153  mov     edx, 7D0h
0x180044158  call    _Intlstr_GetString_LoadString
0x18004415d  mov     byte ptr [rbp+57h+var_60+8], dil
0x180044161  lea     r9, [rbp+57h+var_60]
0x180044165  mov     qword ptr [rbp+57h+var_60], rax
0x180044169  lea     rdx, aMi; "MI"
0x180044170  movaps  xmm0, [rbp+57h+var_60]
0x180044174  mov     r8d, 0Bh
0x18004417a  mov     [rsp+0A0h+var_78], rdi; __int64
0x18004417f  mov     [rsp+0A0h+var_80], rdi; __int64
0x180044184  movdqa  [rbp+57h+var_60], xmm0
0x180044189  lea     edi, [r8-4]
0x18004418d  mov     ecx, edi; int
0x18004418f  call    MI_ReportErrorDetails_ForCustomError
0x180044194  jmp     short loc_1800441DE
0x180044196  lea     r8, [rbp+57h+var_50]
0x18004419a  mov     [rbp+57h+var_70], edi
0x18004419d  lea     rdx, [rbp+57h+var_70]
0x1800441a1  mov     rcx, rsi
0x1800441a4  movups  [rbp+57h+var_50], xmm0
0x1800441a8  movups  [rbp+57h+var_40], xmm0
0x1800441ac  movups  [rbp+57h+var_30], xmm0
0x1800441b0  call    Unbox
0x1800441b5  cmp     [rbp+57h+var_70], edi
0x1800441b8  jnz     short loc_1800441BF
0x1800441ba  mov     byte ptr [rbx], 1
0x1800441bd  jmp     short loc_1800441DE
0x1800441bf  test    dword ptr [rbp+57h+var_50+4], 20000000h
0x1800441c6  jz      short loc_1800441CD
0x1800441c8  mov     [rbx], dil
0x1800441cb  jmp     short loc_1800441DE
0x1800441cd  mov     ecx, dword ptr [rbp+57h+var_50]
0x1800441d0  lea     rdx, [rbp+57h+var_50+8]
0x1800441d4  mov     r8, rbx
0x1800441d7  call    Coerce_MiValue_ToBool
0x1800441dc  mov     edi, eax
0x1800441de  mov     eax, edi
0x1800441e0  mov     rcx, [rbp+57h+var_20]
0x1800441e4  xor     rcx, rsp; StackCookie
0x1800441e7  call    __security_check_cookie
0x1800441ec  mov     rbx, [rsp+0A0h+arg_10]
0x1800441f4  add     rsp, 90h
0x1800441fb  pop     rdi
0x1800441fc  pop     rsi
0x1800441fd  pop     rbp
0x1800441fe  retn
```
