# CEtwEventProvHelper::Initialize(void)

- ea: `0x1400fb664`
- end: `0x1400fb8ef`
- name: `?Initialize@CEtwEventProvHelper@@QEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(CEtwEventProvHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400fb134`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x1400fb664`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x1400fb6cd`
- `KERNEL32!LoadLibraryA` at `0x1400fb6cd`
- `KERNEL32!GetProcAddress` at `0x1400fb746`
- `KERNEL32!GetProcAddress` at `0x1400fb78b`
- `KERNEL32!GetProcAddress` at `0x1400fb7e0`
- `KERNEL32!GetProcAddress` at `0x1400fb835`
- `KERNEL32!GetProcAddress` at `0x1400fb88a`
- `KERNEL32!GetProcAddress` at `0x1400fb746`
- `KERNEL32!GetProcAddress` at `0x1400fb78b`
- `KERNEL32!GetProcAddress` at `0x1400fb7e0`
- `KERNEL32!GetProcAddress` at `0x1400fb835`
- `KERNEL32!GetProcAddress` at `0x1400fb88a`
- `KERNEL32!GetLastError` at `0x1400fb6dc`
- `KERNEL32!GetLastError` at `0x1400fb754`
- `KERNEL32!GetLastError` at `0x1400fb79a`
- `KERNEL32!GetLastError` at `0x1400fb7ef`
- `KERNEL32!GetLastError` at `0x1400fb844`
- `KERNEL32!GetLastError` at `0x1400fb899`
- `KERNEL32!GetLastError` at `0x1400fb6dc`
- `KERNEL32!GetLastError` at `0x1400fb754`
- `KERNEL32!GetLastError` at `0x1400fb79a`
- `KERNEL32!GetLastError` at `0x1400fb7ef`
- `KERNEL32!GetLastError` at `0x1400fb844`
- `KERNEL32!GetLastError` at `0x1400fb899`

## string_xrefs

- `0x1400fb784`: `EventWrite`
- `0x1400fb6c6`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall CEtwEventProvHelper::Initialize(CEtwEventProvHelper *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HMODULE LibraryA; // rax
  signed int LastError; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  FARPROC ProcAddress; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax

  if ( *((_DWORD *)this + 10) )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_d31cb80fda21368ddcab318082abf7ab_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  LibraryA = LoadLibraryA("advapi32.dll");
  *((_QWORD *)this + 6) = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "EventRegister");
    *(_QWORD *)this = ProcAddress;
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_12;
      }
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 17;
      goto LABEL_11;
    }
    v8 = GetProcAddress(*((HMODULE *)this + 6), "EventWrite");
    *((_QWORD *)this + 2) = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_12;
      }
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 18;
      goto LABEL_11;
    }
    v9 = GetProcAddress(*((HMODULE *)this + 6), "EventUnregister");
    *((_QWORD *)this + 1) = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_12;
      }
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 19;
      goto LABEL_11;
    }
    v10 = GetProcAddress(*((HMODULE *)this + 6), "EventEnabled");
    *((_QWORD *)this + 3) = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_12;
      }
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 20;
      goto LABEL_11;
    }
    v11 = GetProcAddress(*((HMODULE *)this + 6), "EventActivityIdControl");
    *((_QWORD *)this + 4) = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_12;
      }
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 21;
      goto LABEL_11;
    }
    *((_DWORD *)this + 10) = 1;
    return 0;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_12;
  }
  v5 = RdpWppGetCurrentThreadActivityIdPrefix();
  v6 = 16;
LABEL_11:
  WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_d31cb80fda21368ddcab318082abf7ab_Traceguids, v5, LastError);
LABEL_12:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400fb664  mov     [rsp+arg_0], rbx
0x1400fb669  mov     [rsp+arg_8], rsi
0x1400fb66e  push    rdi
0x1400fb66f  sub     rsp, 30h
0x1400fb673  cmp     dword ptr [rcx+28h], 0
0x1400fb677  mov     rbx, rcx
0x1400fb67a  jnz     loc_1400FB8DB
0x1400fb680  mov     rax, cs:WPP_GLOBAL_Control
0x1400fb687  lea     rdi, WPP_GLOBAL_Control
0x1400fb68e  lea     rsi, WPP_d31cb80fda21368ddcab318082abf7ab_Traceguids
0x1400fb695  cmp     rax, rdi
0x1400fb698  jz      short loc_1400FB6C6
0x1400fb69a  test    byte ptr [rax+1Ch], 1
0x1400fb69e  jz      short loc_1400FB6C6
0x1400fb6a0  cmp     byte ptr [rax+19h], 4
0x1400fb6a4  jb      short loc_1400FB6C6
0x1400fb6a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400fb6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fb6b2  mov     edx, 0Fh
0x1400fb6b7  mov     r9d, eax
0x1400fb6ba  mov     r8, rsi
0x1400fb6bd  mov     rcx, [rcx+10h]
0x1400fb6c1  call    WPP_SF_d
0x1400fb6c6  lea     rcx, aAdvapi32Dll_1; "advapi32.dll"
0x1400fb6cd  call    cs:__imp_LoadLibraryA
0x1400fb6d3  mov     [rbx+30h], rax
0x1400fb6d7  test    rax, rax
0x1400fb6da  jnz     short loc_1400FB73C
0x1400fb6dc  call    cs:__imp_GetLastError
0x1400fb6e2  mov     ebx, eax
0x1400fb6e4  mov     rax, cs:WPP_GLOBAL_Control
0x1400fb6eb  cmp     rax, rdi
0x1400fb6ee  jz      short loc_1400FB720
0x1400fb6f0  test    byte ptr [rax+1Ch], 8
0x1400fb6f4  jz      short loc_1400FB720
0x1400fb6f6  cmp     byte ptr [rax+19h], 2
0x1400fb6fa  jb      short loc_1400FB720
0x1400fb6fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400fb701  mov     edx, 10h
0x1400fb706  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fb70d  mov     r9d, eax
0x1400fb710  mov     r8, rsi
0x1400fb713  mov     [rsp+38h+var_18], ebx
0x1400fb717  mov     rcx, [rcx+10h]
0x1400fb71b  call    WPP_SF_Dd
0x1400fb720  test    ebx, ebx
0x1400fb722  jle     short loc_1400FB72D
0x1400fb724  movzx   ebx, bx
0x1400fb727  or      ebx, 80070000h
0x1400fb72d  test    ebx, ebx
0x1400fb72f  mov     eax, 80004005h
0x1400fb734  cmovns  ebx, eax
0x1400fb737  jmp     loc_1400FB8DD
0x1400fb73c  lea     rdx, aEventregister_0; "EventRegister"
0x1400fb743  mov     rcx, rax; hModule
0x1400fb746  call    cs:__imp_GetProcAddress
0x1400fb74c  mov     [rbx], rax
0x1400fb74f  test    rax, rax
0x1400fb752  jnz     short loc_1400FB780
0x1400fb754  call    cs:__imp_GetLastError
0x1400fb75a  mov     ebx, eax
0x1400fb75c  mov     rax, cs:WPP_GLOBAL_Control
0x1400fb763  cmp     rax, rdi
0x1400fb766  jz      short loc_1400FB720
0x1400fb768  test    byte ptr [rax+1Ch], 8
0x1400fb76c  jz      short loc_1400FB720
0x1400fb76e  cmp     byte ptr [rax+19h], 2
0x1400fb772  jb      short loc_1400FB720
0x1400fb774  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400fb779  mov     edx, 11h
0x1400fb77e  jmp     short loc_1400FB706
0x1400fb780  mov     rcx, [rbx+30h]; hModule
0x1400fb784  lea     rdx, aEventwrite; "EventWrite"
0x1400fb78b  call    cs:__imp_GetProcAddress
0x1400fb791  mov     [rbx+10h], rax
0x1400fb795  test    rax, rax
0x1400fb798  jnz     short loc_1400FB7D5
0x1400fb79a  call    cs:__imp_GetLastError
0x1400fb7a0  mov     ebx, eax
0x1400fb7a2  mov     rax, cs:WPP_GLOBAL_Control
0x1400fb7a9  cmp     rax, rdi
0x1400fb7ac  jz      loc_1400FB720
0x1400fb7b2  test    byte ptr [rax+1Ch], 8
0x1400fb7b6  jz      loc_1400FB720
0x1400fb7bc  cmp     byte ptr [rax+19h], 2
0x1400fb7c0  jb      loc_1400FB720
0x1400fb7c6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400fb7cb  mov     edx, 12h
0x1400fb7d0  jmp     loc_1400FB706
0x1400fb7d5  mov     rcx, [rbx+30h]; hModule
0x1400fb7d9  lea     rdx, aEventunregiste_0; "EventUnregister"
0x1400fb7e0  call    cs:__imp_GetProcAddress
0x1400fb7e6  mov     [rbx+8], rax
0x1400fb7ea  test    rax, rax
0x1400fb7ed  jnz     short loc_1400FB82A
0x1400fb7ef  call    cs:__imp_GetLastError
0x1400fb7f5  mov     ebx, eax
0x1400fb7f7  mov     rax, cs:WPP_GLOBAL_Control
0x1400fb7fe  cmp     rax, rdi
0x1400fb801  jz      loc_1400FB720
0x1400fb807  test    byte ptr [rax+1Ch], 8
0x1400fb80b  jz      loc_1400FB720
0x1400fb811  cmp     byte ptr [rax+19h], 2
0x1400fb815  jb      loc_1400FB720
0x1400fb81b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400fb820  mov     edx, 13h
0x1400fb825  jmp     loc_1400FB706
0x1400fb82a  mov     rcx, [rbx+30h]; hModule
0x1400fb82e  lea     rdx, aEventenabled; "EventEnabled"
0x1400fb835  call    cs:__imp_GetProcAddress
0x1400fb83b  mov     [rbx+18h], rax
0x1400fb83f  test    rax, rax
0x1400fb842  jnz     short loc_1400FB87F
0x1400fb844  call    cs:__imp_GetLastError
0x1400fb84a  mov     ebx, eax
0x1400fb84c  mov     rax, cs:WPP_GLOBAL_Control
0x1400fb853  cmp     rax, rdi
0x1400fb856  jz      loc_1400FB720
0x1400fb85c  test    byte ptr [rax+1Ch], 8
0x1400fb860  jz      loc_1400FB720
0x1400fb866  cmp     byte ptr [rax+19h], 2
0x1400fb86a  jb      loc_1400FB720
0x1400fb870  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400fb875  mov     edx, 14h
0x1400fb87a  jmp     loc_1400FB706
0x1400fb87f  mov     rcx, [rbx+30h]; hModule
0x1400fb883  lea     rdx, aEventactivityi_0; "EventActivityIdControl"
0x1400fb88a  call    cs:__imp_GetProcAddress
0x1400fb890  mov     [rbx+20h], rax
0x1400fb894  test    rax, rax
0x1400fb897  jnz     short loc_1400FB8D4
0x1400fb899  call    cs:__imp_GetLastError
0x1400fb89f  mov     ebx, eax
0x1400fb8a1  mov     rax, cs:WPP_GLOBAL_Control
0x1400fb8a8  cmp     rax, rdi
0x1400fb8ab  jz      loc_1400FB720
0x1400fb8b1  test    byte ptr [rax+1Ch], 8
0x1400fb8b5  jz      loc_1400FB720
0x1400fb8bb  cmp     byte ptr [rax+19h], 2
0x1400fb8bf  jb      loc_1400FB720
0x1400fb8c5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400fb8ca  mov     edx, 15h
0x1400fb8cf  jmp     loc_1400FB706
0x1400fb8d4  mov     dword ptr [rbx+28h], 1
0x1400fb8db  xor     ebx, ebx
0x1400fb8dd  mov     rsi, [rsp+38h+arg_8]
0x1400fb8e2  mov     eax, ebx
0x1400fb8e4  mov     rbx, [rsp+38h+arg_0]
0x1400fb8e9  add     rsp, 30h
0x1400fb8ed  pop     rdi
0x1400fb8ee  retn
```
