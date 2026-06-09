# GetAccessToken(void * *,int,ulong,int)

- ea: `0x18001f3e0`
- end: `0x18001f5b7`
- name: `?GetAccessToken@@YAKPEAPEAXHKH@Z`
- size: `471`
- prototype: `unsigned int __fastcall(PHANDLE TokenHandle, int, unsigned int, int)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18001f5c0`
- `0x18001fa40`
- `0x1800209a8`
- `0x180025eac`
- `0x180028380`
- `0x1800286d0`
- `0x1800287c0`

## callees

- `0x1800049ac`
- `0x18000c39c`
- `0x18001722c`
- `0x18001adf4`
- `0x18001f3e0`
- `0x180028214`
- `0x180031010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x18001f495`
- `ADVAPI32!OpenThreadToken` at `0x18001f495`
- `ADVAPI32!OpenProcessToken` at `0x18001f55a`
- `ADVAPI32!OpenProcessToken` at `0x18001f55a`
- `KERNEL32!GetCurrentThread` at `0x18001f480`
- `KERNEL32!GetCurrentThread` at `0x18001f480`
- `KERNEL32!GetCurrentProcess` at `0x18001f549`
- `KERNEL32!GetCurrentProcess` at `0x18001f549`
- `KERNEL32!GetLastError` at `0x18001f4a3`
- `KERNEL32!GetLastError` at `0x18001f564`
- `KERNEL32!GetLastError` at `0x18001f4a3`
- `KERNEL32!GetLastError` at `0x18001f564`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetAccessToken(PHANDLE TokenHandle, int a2, __int64 a3, int a4)
{
  CImpersonate *v6; // rax
  CImpersonate *v7; // rcx
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HANDLE CurrentProcess; // rax
  _QWORD v14[3]; // [rsp+20h] [rbp-18h] BYREF

  v14[0] = 0;
  if ( a2 )
  {
    v6 = (CImpersonate *)MmAllocate(0x20u);
    v14[1] = v6;
    v7 = v6 ? CImpersonate::CImpersonate(v6, 1, 1) : 0LL;
    v14[0] = v7;
    if ( (*(unsigned int (__fastcall **)(CImpersonate *))(*(_QWORD *)v7 + 8LL))(v7) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 23, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids);
      LastError = 1368;
      goto LABEL_26;
    }
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    goto LABEL_25;
  LastError = GetLastError();
  if ( LastError != 1008 )
  {
    *TokenHandle = 0;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
      goto LABEL_26;
    v11 = 24;
    goto LABEL_15;
  }
  if ( !a4 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    {
      LastError = GetLastError();
      *TokenHandle = 0;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
        goto LABEL_26;
      v11 = 26;
LABEL_15:
      WPP_SF_d(v10[32], v11, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, LastError);
      goto LABEL_26;
    }
LABEL_25:
    LastError = 0;
    goto LABEL_26;
  }
  *TokenHandle = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 25, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, 1008);
  LastError = 1008;
LABEL_26:
  P<CImpersonate>::~P<CImpersonate>(v14);
  return LastError;
}

```

## disassembly

```asm
0x18001f3e0  mov     [rsp+arg_0], rbx
0x18001f3e5  mov     [rsp+arg_8], rsi
0x18001f3ea  push    rdi
0x18001f3eb  sub     rsp, 30h
0x18001f3ef  mov     esi, r9d
0x18001f3f2  mov     rdi, rcx
0x18001f3f5  mov     [rsp+38h+var_18], 0
0x18001f3fe  test    edx, edx
0x18001f400  jz      short loc_18001F480
0x18001f402  mov     ecx, 20h ; ' '; unsigned __int64
0x18001f407  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001f40c  mov     [rsp+38h+var_10], rax
0x18001f411  test    rax, rax
0x18001f414  jz      short loc_18001F42B
0x18001f416  mov     edx, 1; int
0x18001f41b  mov     r8d, edx; int
0x18001f41e  mov     rcx, rax; this
0x18001f421  call    ??0CImpersonate@@QEAA@HH@Z; CImpersonate::CImpersonate(int,int)
0x18001f426  mov     rcx, rax
0x18001f429  jmp     short loc_18001F42D
0x18001f42b  xor     ecx, ecx
0x18001f42d  mov     [rsp+38h+var_18], rcx
0x18001f432  mov     rax, [rcx]
0x18001f435  mov     rax, [rax+8]
0x18001f439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f43e  test    eax, eax
0x18001f440  jz      short loc_18001F480
0x18001f442  lea     rax, WPP_GLOBAL_Control
0x18001f449  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f450  cmp     rcx, rax
0x18001f453  jz      short loc_18001F476
0x18001f455  test    byte ptr [rcx+10Ch], 1
0x18001f45c  jz      short loc_18001F476
0x18001f45e  mov     edx, 17h
0x18001f463  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f46a  mov     rcx, [rcx+100h]
0x18001f471  call    WPP_SF_
0x18001f476  mov     ebx, 558h
0x18001f47b  jmp     loc_18001F59B
0x18001f480  call    cs:__imp_GetCurrentThread
0x18001f486  mov     rcx, rax; ThreadHandle
0x18001f489  mov     r9, rdi; TokenHandle
0x18001f48c  mov     edx, 8; DesiredAccess
0x18001f491  lea     r8d, [rdx-7]; OpenAsSelf
0x18001f495  call    cs:__imp_OpenThreadToken
0x18001f49b  test    eax, eax
0x18001f49d  jnz     loc_18001F599
0x18001f4a3  call    cs:__imp_GetLastError
0x18001f4a9  mov     ebx, eax
0x18001f4ab  cmp     eax, 3F0h
0x18001f4b0  jz      short loc_18001F4FD
0x18001f4b2  mov     qword ptr [rdi], 0
0x18001f4b9  lea     rax, WPP_GLOBAL_Control
0x18001f4c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4c7  cmp     rcx, rax
0x18001f4ca  jz      loc_18001F59B
0x18001f4d0  test    byte ptr [rcx+10Ch], 1
0x18001f4d7  jz      loc_18001F59B
0x18001f4dd  mov     edx, 18h
0x18001f4e2  mov     r9d, ebx
0x18001f4e5  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f4ec  mov     rcx, [rcx+100h]
0x18001f4f3  call    WPP_SF_d
0x18001f4f8  jmp     loc_18001F59B
0x18001f4fd  test    esi, esi
0x18001f4ff  jz      short loc_18001F549
0x18001f501  mov     qword ptr [rdi], 0
0x18001f508  lea     rax, WPP_GLOBAL_Control
0x18001f50f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f516  cmp     rcx, rax
0x18001f519  jz      short loc_18001F542
0x18001f51b  test    byte ptr [rcx+10Ch], 1
0x18001f522  jz      short loc_18001F542
0x18001f524  mov     edx, 19h
0x18001f529  mov     r9d, 3F0h
0x18001f52f  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f536  mov     rcx, [rcx+100h]
0x18001f53d  call    WPP_SF_d
0x18001f542  mov     ebx, 3F0h
0x18001f547  jmp     short loc_18001F59B
0x18001f549  call    cs:__imp_GetCurrentProcess
0x18001f54f  mov     rcx, rax; ProcessHandle
0x18001f552  mov     r8, rdi; TokenHandle
0x18001f555  mov     edx, 8; DesiredAccess
0x18001f55a  call    cs:__imp_OpenProcessToken
0x18001f560  test    eax, eax
0x18001f562  jnz     short loc_18001F599
0x18001f564  call    cs:__imp_GetLastError
0x18001f56a  mov     ebx, eax
0x18001f56c  mov     qword ptr [rdi], 0
0x18001f573  lea     rax, WPP_GLOBAL_Control
0x18001f57a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f581  cmp     rcx, rax
0x18001f584  jz      short loc_18001F59B
0x18001f586  test    byte ptr [rcx+10Ch], 1
0x18001f58d  jz      short loc_18001F59B
0x18001f58f  mov     edx, 1Ah
0x18001f594  jmp     loc_18001F4E2
0x18001f599  xor     ebx, ebx
0x18001f59b  lea     rcx, [rsp+38h+var_18]
0x18001f5a0  call    ??1?$P@VCImpersonate@@@@QEAA@XZ; P<CImpersonate>::~P<CImpersonate>(void)
0x18001f5a5  mov     eax, ebx
0x18001f5a7  mov     rbx, [rsp+38h+arg_0]
0x18001f5ac  mov     rsi, [rsp+38h+arg_8]
0x18001f5b1  add     rsp, 30h
0x18001f5b5  pop     rdi
0x18001f5b6  retn
```
