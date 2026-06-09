# CEtwEventProvHelper::Initialize(void)

- ea: `0x1400f94f4`
- end: `0x1400f977f`
- name: `?Initialize@CEtwEventProvHelper@@QEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(CEtwEventProvHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400f8fc4`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x1400f94f4`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x1400f955d`
- `KERNEL32!LoadLibraryA` at `0x1400f955d`
- `KERNEL32!GetProcAddress` at `0x1400f95d6`
- `KERNEL32!GetProcAddress` at `0x1400f961b`
- `KERNEL32!GetProcAddress` at `0x1400f9670`
- `KERNEL32!GetProcAddress` at `0x1400f96c5`
- `KERNEL32!GetProcAddress` at `0x1400f971a`
- `KERNEL32!GetProcAddress` at `0x1400f95d6`
- `KERNEL32!GetProcAddress` at `0x1400f961b`
- `KERNEL32!GetProcAddress` at `0x1400f9670`
- `KERNEL32!GetProcAddress` at `0x1400f96c5`
- `KERNEL32!GetProcAddress` at `0x1400f971a`
- `KERNEL32!GetLastError` at `0x1400f956c`
- `KERNEL32!GetLastError` at `0x1400f95e4`
- `KERNEL32!GetLastError` at `0x1400f962a`
- `KERNEL32!GetLastError` at `0x1400f967f`
- `KERNEL32!GetLastError` at `0x1400f96d4`
- `KERNEL32!GetLastError` at `0x1400f9729`
- `KERNEL32!GetLastError` at `0x1400f956c`
- `KERNEL32!GetLastError` at `0x1400f95e4`
- `KERNEL32!GetLastError` at `0x1400f962a`
- `KERNEL32!GetLastError` at `0x1400f967f`
- `KERNEL32!GetLastError` at `0x1400f96d4`
- `KERNEL32!GetLastError` at `0x1400f9729`

## string_xrefs

- `0x1400f9556`: `advapi32.dll`
- `0x1400f9614`: `EventWrite`

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
0x1400f94f4  mov     [rsp+arg_0], rbx
0x1400f94f9  mov     [rsp+arg_8], rsi
0x1400f94fe  push    rdi
0x1400f94ff  sub     rsp, 30h
0x1400f9503  cmp     dword ptr [rcx+28h], 0
0x1400f9507  mov     rbx, rcx
0x1400f950a  jnz     loc_1400F976B
0x1400f9510  mov     rax, cs:WPP_GLOBAL_Control
0x1400f9517  lea     rdi, WPP_GLOBAL_Control
0x1400f951e  lea     rsi, WPP_d31cb80fda21368ddcab318082abf7ab_Traceguids
0x1400f9525  cmp     rax, rdi
0x1400f9528  jz      short loc_1400F9556
0x1400f952a  test    byte ptr [rax+1Ch], 1
0x1400f952e  jz      short loc_1400F9556
0x1400f9530  cmp     byte ptr [rax+19h], 4
0x1400f9534  jb      short loc_1400F9556
0x1400f9536  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400f953b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f9542  mov     edx, 0Fh
0x1400f9547  mov     r9d, eax
0x1400f954a  mov     r8, rsi
0x1400f954d  mov     rcx, [rcx+10h]
0x1400f9551  call    WPP_SF_d
0x1400f9556  lea     rcx, aAdvapi32Dll_1; "advapi32.dll"
0x1400f955d  call    cs:__imp_LoadLibraryA
0x1400f9563  mov     [rbx+30h], rax
0x1400f9567  test    rax, rax
0x1400f956a  jnz     short loc_1400F95CC
0x1400f956c  call    cs:__imp_GetLastError
0x1400f9572  mov     ebx, eax
0x1400f9574  mov     rax, cs:WPP_GLOBAL_Control
0x1400f957b  cmp     rax, rdi
0x1400f957e  jz      short loc_1400F95B0
0x1400f9580  test    byte ptr [rax+1Ch], 8
0x1400f9584  jz      short loc_1400F95B0
0x1400f9586  cmp     byte ptr [rax+19h], 2
0x1400f958a  jb      short loc_1400F95B0
0x1400f958c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400f9591  mov     edx, 10h
0x1400f9596  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f959d  mov     r9d, eax
0x1400f95a0  mov     r8, rsi
0x1400f95a3  mov     [rsp+38h+var_18], ebx
0x1400f95a7  mov     rcx, [rcx+10h]
0x1400f95ab  call    WPP_SF_Dd
0x1400f95b0  test    ebx, ebx
0x1400f95b2  jle     short loc_1400F95BD
0x1400f95b4  movzx   ebx, bx
0x1400f95b7  or      ebx, 80070000h
0x1400f95bd  test    ebx, ebx
0x1400f95bf  mov     eax, 80004005h
0x1400f95c4  cmovns  ebx, eax
0x1400f95c7  jmp     loc_1400F976D
0x1400f95cc  lea     rdx, aEventregister_0; "EventRegister"
0x1400f95d3  mov     rcx, rax; hModule
0x1400f95d6  call    cs:__imp_GetProcAddress
0x1400f95dc  mov     [rbx], rax
0x1400f95df  test    rax, rax
0x1400f95e2  jnz     short loc_1400F9610
0x1400f95e4  call    cs:__imp_GetLastError
0x1400f95ea  mov     ebx, eax
0x1400f95ec  mov     rax, cs:WPP_GLOBAL_Control
0x1400f95f3  cmp     rax, rdi
0x1400f95f6  jz      short loc_1400F95B0
0x1400f95f8  test    byte ptr [rax+1Ch], 8
0x1400f95fc  jz      short loc_1400F95B0
0x1400f95fe  cmp     byte ptr [rax+19h], 2
0x1400f9602  jb      short loc_1400F95B0
0x1400f9604  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400f9609  mov     edx, 11h
0x1400f960e  jmp     short loc_1400F9596
0x1400f9610  mov     rcx, [rbx+30h]; hModule
0x1400f9614  lea     rdx, aEventwrite; "EventWrite"
0x1400f961b  call    cs:__imp_GetProcAddress
0x1400f9621  mov     [rbx+10h], rax
0x1400f9625  test    rax, rax
0x1400f9628  jnz     short loc_1400F9665
0x1400f962a  call    cs:__imp_GetLastError
0x1400f9630  mov     ebx, eax
0x1400f9632  mov     rax, cs:WPP_GLOBAL_Control
0x1400f9639  cmp     rax, rdi
0x1400f963c  jz      loc_1400F95B0
0x1400f9642  test    byte ptr [rax+1Ch], 8
0x1400f9646  jz      loc_1400F95B0
0x1400f964c  cmp     byte ptr [rax+19h], 2
0x1400f9650  jb      loc_1400F95B0
0x1400f9656  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400f965b  mov     edx, 12h
0x1400f9660  jmp     loc_1400F9596
0x1400f9665  mov     rcx, [rbx+30h]; hModule
0x1400f9669  lea     rdx, aEventunregiste_0; "EventUnregister"
0x1400f9670  call    cs:__imp_GetProcAddress
0x1400f9676  mov     [rbx+8], rax
0x1400f967a  test    rax, rax
0x1400f967d  jnz     short loc_1400F96BA
0x1400f967f  call    cs:__imp_GetLastError
0x1400f9685  mov     ebx, eax
0x1400f9687  mov     rax, cs:WPP_GLOBAL_Control
0x1400f968e  cmp     rax, rdi
0x1400f9691  jz      loc_1400F95B0
0x1400f9697  test    byte ptr [rax+1Ch], 8
0x1400f969b  jz      loc_1400F95B0
0x1400f96a1  cmp     byte ptr [rax+19h], 2
0x1400f96a5  jb      loc_1400F95B0
0x1400f96ab  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400f96b0  mov     edx, 13h
0x1400f96b5  jmp     loc_1400F9596
0x1400f96ba  mov     rcx, [rbx+30h]; hModule
0x1400f96be  lea     rdx, aEventenabled; "EventEnabled"
0x1400f96c5  call    cs:__imp_GetProcAddress
0x1400f96cb  mov     [rbx+18h], rax
0x1400f96cf  test    rax, rax
0x1400f96d2  jnz     short loc_1400F970F
0x1400f96d4  call    cs:__imp_GetLastError
0x1400f96da  mov     ebx, eax
0x1400f96dc  mov     rax, cs:WPP_GLOBAL_Control
0x1400f96e3  cmp     rax, rdi
0x1400f96e6  jz      loc_1400F95B0
0x1400f96ec  test    byte ptr [rax+1Ch], 8
0x1400f96f0  jz      loc_1400F95B0
0x1400f96f6  cmp     byte ptr [rax+19h], 2
0x1400f96fa  jb      loc_1400F95B0
0x1400f9700  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400f9705  mov     edx, 14h
0x1400f970a  jmp     loc_1400F9596
0x1400f970f  mov     rcx, [rbx+30h]; hModule
0x1400f9713  lea     rdx, aEventactivityi_0; "EventActivityIdControl"
0x1400f971a  call    cs:__imp_GetProcAddress
0x1400f9720  mov     [rbx+20h], rax
0x1400f9724  test    rax, rax
0x1400f9727  jnz     short loc_1400F9764
0x1400f9729  call    cs:__imp_GetLastError
0x1400f972f  mov     ebx, eax
0x1400f9731  mov     rax, cs:WPP_GLOBAL_Control
0x1400f9738  cmp     rax, rdi
0x1400f973b  jz      loc_1400F95B0
0x1400f9741  test    byte ptr [rax+1Ch], 8
0x1400f9745  jz      loc_1400F95B0
0x1400f974b  cmp     byte ptr [rax+19h], 2
0x1400f974f  jb      loc_1400F95B0
0x1400f9755  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400f975a  mov     edx, 15h
0x1400f975f  jmp     loc_1400F9596
0x1400f9764  mov     dword ptr [rbx+28h], 1
0x1400f976b  xor     ebx, ebx
0x1400f976d  mov     rsi, [rsp+38h+arg_8]
0x1400f9772  mov     eax, ebx
0x1400f9774  mov     rbx, [rsp+38h+arg_0]
0x1400f9779  add     rsp, 30h
0x1400f977d  pop     rdi
0x1400f977e  retn
```
