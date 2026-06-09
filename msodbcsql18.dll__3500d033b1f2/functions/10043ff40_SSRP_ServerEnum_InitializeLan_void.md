# SSRP::ServerEnum::InitializeLan(void)

- ea: `0x10043ff40`
- end: `0x1004401cc`
- name: `?InitializeLan@ServerEnum@SSRP@@QEAA_NXZ`
- size: `652`
- prototype: `bool __fastcall(SSRP::ServerEnum *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10043fd20`

## callees

- `0x100417768`
- `0x10043ff40`
- `0x100545d84`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x10044001b`
- `KERNEL32!GetProcAddress` at `0x100440032`
- `KERNEL32!GetProcAddress` at `0x10044001b`
- `KERNEL32!GetProcAddress` at `0x100440032`
- `KERNEL32!FreeLibrary` at `0x1004400ad`
- `KERNEL32!FreeLibrary` at `0x100440155`
- `KERNEL32!FreeLibrary` at `0x1004400ad`
- `KERNEL32!FreeLibrary` at `0x100440155`

## string_xrefs

- `0x10043ffb8`: `netapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall SSRP::ServerEnum::InitializeLan(SSRP::ServerEnum *this)
{
  char v2; // bl
  HMODULE v3; // rax
  HMODULE v4; // rdi
  wchar_t *v5; // r9
  __int64 v6; // r8
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v8)(_QWORD, __int64, char *, __int64, char *, int *, int, _QWORD, _QWORD); // r10
  int v9; // eax
  int v11; // [rsp+78h] [rbp+10h] BYREF
  __int64 v12; // [rsp+80h] [rbp+18h] BYREF

  v12 = -1;
  v2 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004
    && `SSRP::ServerEnum::InitializeLan'::`7'::_bidPtrSA_040_1082[0]
    && bidID != -1 )
  {
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v12,
      `SSRP::ServerEnum::InitializeLan'::`7'::_bidPtrSA_040_1082[0],
      0);
  }
  v3 = SNILoadSystemLibA("netapi32.dll");
  v4 = v3;
  if ( v3 )
  {
    *((_QWORD *)this + 586) = GetProcAddress(v3, "NetServerEnum");
    ProcAddress = GetProcAddress(v4, "NetApiBufferFree");
    *((_QWORD *)this + 587) = ProcAddress;
    v8 = (__int64 (__fastcall *)(_QWORD, __int64, char *, __int64, char *, int *, int, _QWORD, _QWORD))*((_QWORD *)this + 586);
    if ( v8 && ProcAddress )
    {
      v11 = 0;
      v9 = v8(0, 100, (char *)this + 4664, 0xFFFFFFFFLL, (char *)this + 4672, &v11, 4, 0, 0);
      if ( !v9 || v9 == 234 )
      {
        *((_QWORD *)this + 585) = v4;
        if ( (bidGblFlags & 0x20002) == 0x20002
          && `SSRP::ServerEnum::InitializeLan'::`46'::_bidPtrSA_030_1141[0]
          && bidID != -1 )
        {
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
            bidID,
            0,
            1168384,
            `SSRP::ServerEnum::InitializeLan'::`46'::_bidPtrSA_030_1141[0],
            0);
        }
        v2 = 1;
      }
      else
      {
        FreeLibrary(v4);
        if ( (bidGblFlags & 0x20002) == 0x20002
          && `SSRP::ServerEnum::InitializeLan'::`39'::_bidPtrSA_030_1132[0]
          && bidID != -1 )
        {
          v5 = `SSRP::ServerEnum::InitializeLan'::`39'::_bidPtrSA_030_1132[0];
          v6 = 1159168;
          goto LABEL_27;
        }
      }
    }
    else
    {
      FreeLibrary(v4);
      if ( (bidGblFlags & 0x20002) == 0x20002
        && `SSRP::ServerEnum::InitializeLan'::`29'::_bidPtrSA_030_1104[0]
        && bidID != -1 )
      {
        v5 = `SSRP::ServerEnum::InitializeLan'::`29'::_bidPtrSA_030_1104[0];
        v6 = 1130496;
        goto LABEL_27;
      }
    }
  }
  else if ( (bidGblFlags & 0x20002) == 0x20002
         && `SSRP::ServerEnum::InitializeLan'::`19'::_bidPtrSA_030_1090[0]
         && bidID != -1 )
  {
    v5 = `SSRP::ServerEnum::InitializeLan'::`19'::_bidPtrSA_030_1090[0];
    v6 = 1116160;
LABEL_27:
    ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(bidID, 0, v6, v5, 0);
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v12);
  return v2;
}

```

## disassembly

```asm
0x10043ff40  mov     r11, rsp
0x10043ff43  push    rdi
0x10043ff44  sub     rsp, 60h
0x10043ff48  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x10043ff50  mov     [r11+8], rbx
0x10043ff54  mov     [r11+20h], rsi
0x10043ff58  mov     rsi, rcx
0x10043ff5b  or      qword ptr [r11+18h], 0FFFFFFFFFFFFFFFFh
0x10043ff60  mov     eax, cs:_bidGblFlags
0x10043ff66  mov     ecx, 20004h
0x10043ff6b  and     eax, ecx
0x10043ff6d  xor     ebx, ebx
0x10043ff6f  cmp     eax, ecx
0x10043ff71  jnz     short loc_10043FFB8
0x10043ff73  mov     rax, cs:?_bidPtrSA_040_1082@?6??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`7'::_bidPtrSA_040_1082
0x10043ff7a  test    rax, rax
0x10043ff7d  jz      short loc_10043FFB8
0x10043ff7f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10043ff87  jz      short loc_10043FFB8
0x10043ff89  mov     r10, cs:off_1005D39F0
0x10043ff90  mov     [r11-40h], rbx
0x10043ff94  mov     rax, cs:?_bidPtrSA_040_1082@?6??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`7'::_bidPtrSA_040_1082
0x10043ff9b  mov     [r11-48h], rax
0x10043ff9f  lea     r9, [r11+18h]
0x10043ffa3  xor     r8d, r8d
0x10043ffa6  xor     edx, edx
0x10043ffa8  mov     rcx, cs:_bidID
0x10043ffaf  mov     rax, r10
0x10043ffb2  call    cs:__guard_dispatch_icall_fptr
0x10043ffb8  lea     rcx, aNetapi32Dll_0; "netapi32.dll"
0x10043ffbf  call    SNILoadSystemLibA
0x10043ffc4  mov     rdi, rax
0x10043ffc7  test    rax, rax
0x10043ffca  jnz     short loc_100440011
0x10043ffcc  mov     eax, cs:_bidGblFlags
0x10043ffd2  mov     ecx, 20002h
0x10043ffd7  and     eax, ecx
0x10043ffd9  cmp     eax, ecx
0x10043ffdb  jnz     loc_1004401AB
0x10043ffe1  mov     rax, cs:?_bidPtrSA_030_1090@?BD@??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`19'::_bidPtrSA_030_1090
0x10043ffe8  test    rax, rax
0x10043ffeb  jz      loc_1004401AB
0x10043fff1  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10043fff9  jz      loc_1004401AB
0x10043ffff  mov     r9, cs:?_bidPtrSA_030_1090@?BD@??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`19'::_bidPtrSA_030_1090
0x100440006  mov     r8d, 110800h
0x10044000c  jmp     loc_10044018F
0x100440011  lea     rdx, aNetserverenum; "NetServerEnum"
0x100440018  mov     rcx, rdi; hModule
0x10044001b  call    cs:__imp_GetProcAddress
0x100440021  mov     [rsi+1250h], rax
0x100440028  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x10044002f  mov     rcx, rdi; hModule
0x100440032  call    cs:__imp_GetProcAddress
0x100440038  mov     [rsi+1258h], rax
0x10044003f  mov     r10, [rsi+1250h]
0x100440046  test    r10, r10
0x100440049  jz      loc_100440152
0x10044004f  test    rax, rax
0x100440052  jz      loc_100440152
0x100440058  mov     [rsp+68h+arg_8], ebx
0x10044005c  lea     rcx, [rsi+1240h]
0x100440063  lea     r8, [rsi+1238h]
0x10044006a  mov     [rsp+68h+var_28], rbx
0x10044006f  mov     [rsp+68h+var_30], rbx
0x100440074  mov     [rsp+68h+var_38], 4
0x10044007c  lea     rax, [rsp+68h+arg_8]
0x100440081  mov     [rsp+68h+var_40], rax
0x100440086  mov     [rsp+68h+var_48], rcx
0x10044008b  or      r9d, 0FFFFFFFFh
0x10044008f  mov     edx, 64h ; 'd'
0x100440094  xor     ecx, ecx
0x100440096  mov     rax, r10
0x100440099  call    cs:__guard_dispatch_icall_fptr
0x10044009f  test    eax, eax
0x1004400a1  jz      short loc_1004400F8
0x1004400a3  cmp     eax, 0EAh
0x1004400a8  jz      short loc_1004400F8
0x1004400aa  mov     rcx, rdi; hLibModule
0x1004400ad  call    cs:__imp_FreeLibrary
0x1004400b3  mov     eax, cs:_bidGblFlags
0x1004400b9  mov     ecx, 20002h
0x1004400be  and     eax, ecx
0x1004400c0  cmp     eax, ecx
0x1004400c2  jnz     loc_1004401AB
0x1004400c8  mov     rax, cs:?_bidPtrSA_030_1132@?CH@??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`39'::_bidPtrSA_030_1132
0x1004400cf  test    rax, rax
0x1004400d2  jz      loc_1004401AB
0x1004400d8  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1004400e0  jz      loc_1004401AB
0x1004400e6  mov     r9, cs:?_bidPtrSA_030_1132@?CH@??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`39'::_bidPtrSA_030_1132
0x1004400ed  mov     r8d, 11B000h
0x1004400f3  jmp     loc_10044018F
0x1004400f8  mov     [rsi+1248h], rdi
0x1004400ff  mov     eax, cs:_bidGblFlags
0x100440105  mov     ecx, 20002h
0x10044010a  and     eax, ecx
0x10044010c  cmp     eax, ecx
0x10044010e  jnz     short loc_10044014E
0x100440110  mov     rax, cs:?_bidPtrSA_030_1141@?CO@??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`46'::_bidPtrSA_030_1141
0x100440117  test    rax, rax
0x10044011a  jz      short loc_10044014E
0x10044011c  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100440124  jz      short loc_10044014E
0x100440126  mov     rax, cs:off_1005D39E0
0x10044012d  mov     [rsp+68h+var_48], rbx
0x100440132  mov     r9, cs:?_bidPtrSA_030_1141@?CO@??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`46'::_bidPtrSA_030_1141
0x100440139  xor     edx, edx
0x10044013b  mov     r8d, 11D400h
0x100440141  mov     rcx, cs:_bidID
0x100440148  call    cs:__guard_dispatch_icall_fptr
0x10044014e  mov     bl, 1
0x100440150  jmp     short loc_1004401AB
0x100440152  mov     rcx, rdi; hLibModule
0x100440155  call    cs:__imp_FreeLibrary
0x10044015b  mov     eax, cs:_bidGblFlags
0x100440161  mov     ecx, 20002h
0x100440166  and     eax, ecx
0x100440168  cmp     eax, ecx
0x10044016a  jnz     short loc_1004401AB
0x10044016c  mov     rax, cs:?_bidPtrSA_030_1104@?BN@??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`29'::_bidPtrSA_030_1104
0x100440173  test    rax, rax
0x100440176  jz      short loc_1004401AB
0x100440178  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100440180  jz      short loc_1004401AB
0x100440182  mov     r9, cs:?_bidPtrSA_030_1104@?BN@??InitializeLan@ServerEnum@SSRP@@QEAA_NXZ@4REBGEB; ushort const * const `SSRP::ServerEnum::InitializeLan(void)'::`29'::_bidPtrSA_030_1104
0x100440189  mov     r8d, 114000h
0x10044018f  mov     [rsp+68h+var_48], rbx
0x100440194  xor     edx, edx
0x100440196  mov     rcx, cs:_bidID
0x10044019d  mov     rax, cs:off_1005D39E0
0x1004401a4  call    cs:__guard_dispatch_icall_fptr
0x1004401aa  nop
0x1004401ab  lea     rcx, [rsp+68h+arg_10]; this
0x1004401b3  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1004401b8  mov     al, bl
0x1004401ba  lea     r11, [rsp+68h+var_8]
0x1004401bf  mov     rbx, [r11+10h]
0x1004401c3  mov     rsi, [r11+28h]
0x1004401c7  mov     rsp, r11
0x1004401ca  pop     rdi
0x1004401cb  retn
```
