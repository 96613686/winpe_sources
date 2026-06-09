# CRWLock::ReleaseReaderLock(void)

- ea: `0x18002e120`
- end: `0x18002e488`
- name: `?ReleaseReaderLock@CRWLock@@QEAAKXZ`
- size: `872`
- prototype: `unsigned int __fastcall(CRWLock *this)`
- caller_count: `10`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ba40`
- `0x18002c0b4`
- `0x18002c684`
- `0x18002cd2c`
- `0x18003aa1c`
- `0x18006fc04`
- `0x1800fd8b0`
- `0x18016f77c`
- `0x180173678`
- `0x18018175c`

## callees

- `0x18002e120`
- `0x1800e7614`
- `0x1800e76b8`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18002e180`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e2da`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e2ff`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e3ba`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e3df`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e429`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e180`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e2da`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e2ff`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e3ba`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e3df`
- `ntdll!RtlDllShutdownInProgress` at `0x18002e429`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e18a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e2e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e309`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e3c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e3e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e437`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e18a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e2e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e309`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e3c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e3e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e132`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e253`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e132`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e253`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e2ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e30f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e3ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e3ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e2ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e30f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e3ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e3ef`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e2f8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e31d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e3d8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e3fd`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e2f8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e31d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e3d8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e3fd`

## pseudocode

```c
__int64 __fastcall CRWLock::ReleaseReaderLock(CRWLock *this)
{
  _QWORD *ReservedForOle; // rcx
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  bool v6; // zf
  signed __int64 lockState; // rcx
  signed __int64 v8; // r8
  signed __int64 v9; // r9
  __int64 v10; // rdx
  _QWORD *v11; // rdx
  _QWORD **v12; // rdx
  signed __int64 v13; // rax
  signed __int64 v14; // rdx
  signed __int64 v15; // r8
  __int64 v16; // rcx
  HANDLE CurrentProcess; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  HANDLE v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // rax

  if ( this->_dwWriterID != GetCurrentThreadId() )
  {
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    if ( !ReservedForOle )
    {
      if ( !RtlDllShutdownInProgress() )
        IsDebuggerPresent();
      CurrentProcess = GetCurrentProcess();
      TerminateProcess(CurrentProcess, 0x8000FFFF);
      __debugbreak();
    }
    v3 = (_QWORD *)ReservedForOle[42];
    if ( !v3 )
    {
      if ( !RtlDllShutdownInProgress() )
        IsDebuggerPresent();
      v19 = GetCurrentProcess();
      TerminateProcess(v19, 0x8000FFFF);
      __debugbreak();
    }
    v4 = (_QWORD *)*v3;
    while ( (CRWLock *)v4[2] != this )
    {
      v4 = (_QWORD *)*v4;
      if ( v4 == (_QWORD *)*v3 )
      {
        if ( !RtlDllShutdownInProgress() )
          IsDebuggerPresent();
        return 288;
      }
    }
    v6 = (*((_WORD *)v4 + 12))-- == 1;
    if ( !v6 )
      return 0;
    lockState = (signed __int64)this->_lockState;
    while ( 1 )
    {
      v8 = lockState - 1;
      v9 = lockState;
      v10 = 0;
      if ( (lockState & 0x6FFFFF) == 1 )
      {
        if ( (lockState & 0xFFFFF00000000000uLL) != 0 )
        {
          v10 = 0x200000;
          goto LABEL_39;
        }
        if ( (lockState & 0xFFFFF000000LL) != 0 )
        {
          v10 = 0x400000;
LABEL_39:
          v8 |= v10;
        }
      }
      lockState = _InterlockedCompareExchange64((volatile signed __int64 *)this, v8, lockState);
      if ( lockState == v9 )
      {
        if ( v10 )
        {
          if ( v10 == 0x200000 )
          {
            CRWLock::RWSetWriterSignal(this);
          }
          else if ( (v9 & 0x800000) == 0 )
          {
            CRWLock::RWSetReaderSignal(this);
          }
        }
        v11 = NtCurrentTeb()->ReservedForOle;
        if ( !v11 )
        {
          if ( !RtlDllShutdownInProgress() )
            IsDebuggerPresent();
          v18 = GetCurrentProcess();
          TerminateProcess(v18, 0x8000FFFF);
          __debugbreak();
        }
        v12 = (_QWORD **)v11[42];
        if ( !v12 )
        {
          if ( !RtlDllShutdownInProgress() )
            IsDebuggerPresent();
          v20 = GetCurrentProcess();
          TerminateProcess(v20, 0x8000FFFF);
          __debugbreak();
        }
        if ( v4 == *v12 )
        {
          *v12 = (_QWORD *)**v12;
        }
        else if ( *(_QWORD *)(*v4 + 16LL) )
        {
          *(_QWORD *)v4[1] = *v4;
          *(_QWORD *)(*v4 + 8LL) = v4[1];
          v21 = *v12;
          *v4 = *v12;
          v22 = (_QWORD *)v21[1];
          v4[1] = v22;
          *v22 = v4;
          v21[1] = v4;
        }
        v4[2] = 0;
        return 0;
      }
    }
  }
  if ( this->_dwWriterID == GetCurrentThreadId() )
  {
    v6 = this->_wWriterLevel-- == 1;
    if ( !v6 )
      return 0;
    this->_dwWriterID = 0;
    v13 = (signed __int64)this->_lockState;
    do
    {
      v14 = v13 - 0x100000;
      v15 = v13;
      v16 = 0;
      if ( (v13 & 0x600000) == 0 )
      {
        if ( (v13 & 0xFFFFF00000000000uLL) != 0 )
        {
          v16 = 0x200000;
          v14 |= 0x200000uLL;
        }
        else if ( (v13 & 0xFFFFF000000LL) != 0 )
        {
          v16 = 0x400000;
          v14 |= 0x400000uLL;
        }
      }
      v13 = _InterlockedCompareExchange64((volatile signed __int64 *)this, v14, v13);
    }
    while ( v13 != v15 );
    if ( v16 )
    {
      if ( v16 == 0x200000 )
      {
        CRWLock::RWSetWriterSignal(this);
        return 0;
      }
      else
      {
        if ( (v15 & 0x800000) != 0 )
          return 0;
        CRWLock::RWSetReaderSignal(this);
        return 0;
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    if ( RtlDllShutdownInProgress() )
      return 0;
    IsDebuggerPresent();
    return 0;
  }
}

```

## disassembly

```asm
0x18002e120  mov     [rsp+arg_8], rbx
0x18002e125  mov     [rsp+arg_10], rsi
0x18002e12a  push    rdi
0x18002e12b  sub     rsp, 20h
0x18002e12f  mov     rdi, this
0x18002e132  call    cs:__imp_GetCurrentThreadId
0x18002e138  mov     edx, [rdi+0Ch]
0x18002e13b  cmp     edx, eax
0x18002e13d  jz      loc_18002E253
0x18002e143  mov     rax, gs:30h
0x18002e14c  mov     this, [rax+1758h]
0x18002e153  test    this, this
0x18002e156  jz      loc_18002E2DA
0x18002e15c  mov     rax, [this+150h]
0x18002e163  test    rax, rax
0x18002e166  jz      loc_18002E3BA
0x18002e16c  mov     this, [rax]
0x18002e16f  mov     rbx, this
0x18002e172  cmp     [rbx+10h], rdi
0x18002e176  jz      short loc_18002E1A5
0x18002e178  mov     rbx, [rbx]
0x18002e17b  cmp     rbx, this
0x18002e17e  jnz     short loc_18002E172
0x18002e180  call    cs:__imp_RtlDllShutdownInProgress
0x18002e186  test    al, al
0x18002e188  jnz     short loc_18002E190
0x18002e18a  call    cs:__imp_IsDebuggerPresent
0x18002e190  mov     eax, 120h
0x18002e195  mov     rbx, [rsp+28h+arg_8]
0x18002e19a  mov     rsi, [rsp+28h+arg_10]
0x18002e19f  add     rsp, 20h
0x18002e1a3  pop     rdi
0x18002e1a4  retn
0x18002e1a5  mov     eax, 0FFFFh
0x18002e1aa  add     [rbx+18h], ax
0x18002e1ae  jnz     loc_18002E241
0x18002e1b4  mov     this, [rdi]
0x18002e1b7  xor     esi, esi
0x18002e1b9  mov     r11, 0FFFFF00000000000h
0x18002e1c3  mov     r10, 0FFFFF000000h
0x18002e1cd  mov     rax, this
0x18002e1d0  lea     r8, [this-1]
0x18002e1d4  and     eax, 6FFFFFh
0x18002e1d9  mov     r9, this
0x18002e1dc  mov     rdx, rsi
0x18002e1df  cmp     rax, 1
0x18002e1e3  jz      loc_18002E324
0x18002e1e9  mov     rax, this
0x18002e1ec  lock cmpxchg [rdi], r8
0x18002e1f1  mov     this, rax
0x18002e1f4  cmp     rax, r9
0x18002e1f7  jnz     short loc_18002E1CD
0x18002e1f9  test    rdx, rdx
0x18002e1fc  jnz     loc_18002E36E
0x18002e202  mov     rax, gs:30h
0x18002e20b  mov     rdx, [rax+1758h]
0x18002e212  test    rdx, rdx
0x18002e215  jz      loc_18002E2FF
0x18002e21b  mov     rdx, [rdx+150h]
0x18002e222  test    rdx, rdx
0x18002e225  jz      loc_18002E3DF
0x18002e22b  mov     rax, [rdx]
0x18002e22e  cmp     rbx, rax
0x18002e231  jnz     loc_18002E44F
0x18002e237  mov     rax, [rax]
0x18002e23a  mov     [rdx], rax
0x18002e23d  mov     [rbx+10h], rsi
0x18002e241  xor     eax, eax
0x18002e243  mov     rbx, [rsp+28h+arg_8]
0x18002e248  mov     rsi, [rsp+28h+arg_10]
0x18002e24d  add     rsp, 20h
0x18002e251  pop     rdi
0x18002e252  retn
0x18002e253  call    cs:__imp_GetCurrentThreadId
0x18002e259  mov     edx, [rdi+0Ch]
0x18002e25c  cmp     edx, eax
0x18002e25e  jnz     loc_18002E429
0x18002e264  mov     eax, 0FFFFh
0x18002e269  add     [rdi+12h], ax
0x18002e26d  jnz     short loc_18002E241
0x18002e26f  xor     esi, esi
0x18002e271  mov     r11, 0FFFFF00000000000h
0x18002e27b  mov     [rdi+0Ch], esi
0x18002e27e  mov     r10, 0FFFFF000000h
0x18002e288  mov     rax, [rdi]
0x18002e28b  lea     rdx, [rax-100000h]
0x18002e292  mov     r8, rax
0x18002e295  mov     this, rsi
0x18002e298  test    rax, 600000h
0x18002e29e  jz      loc_18002E346
0x18002e2a4  lock cmpxchg [rdi], rdx
0x18002e2a9  cmp     rax, r8
0x18002e2ac  jnz     short loc_18002E28B
0x18002e2ae  test    this, this
0x18002e2b1  jz      short loc_18002E241
0x18002e2b3  cmp     this, 200000h
0x18002e2ba  jnz     loc_18002E388
0x18002e2c0  mov     this, rdi; this
0x18002e2c3  call    ?RWSetWriterSignal@CRWLock@@AEAAXXZ; CRWLock::RWSetWriterSignal(void)
0x18002e2c8  xor     eax, eax
0x18002e2ca  mov     rbx, [rsp+28h+arg_8]
0x18002e2cf  mov     rsi, [rsp+28h+arg_10]
0x18002e2d4  add     rsp, 20h
0x18002e2d8  pop     rdi
0x18002e2d9  retn
0x18002e2da  call    cs:__imp_RtlDllShutdownInProgress
0x18002e2e0  test    al, al
0x18002e2e2  jnz     short loc_18002E2EA
0x18002e2e4  call    cs:__imp_IsDebuggerPresent
0x18002e2ea  call    cs:__imp_GetCurrentProcess
0x18002e2f0  mov     this, rax; hProcess
0x18002e2f3  mov     edx, 8000FFFFh; uExitCode
0x18002e2f8  call    cs:__imp_TerminateProcess
0x18002e2fe  int     3; Trap to Debugger
0x18002e2ff  call    cs:__imp_RtlDllShutdownInProgress
0x18002e305  test    al, al
0x18002e307  jnz     short loc_18002E30F
0x18002e309  call    cs:__imp_IsDebuggerPresent
0x18002e30f  call    cs:__imp_GetCurrentProcess
0x18002e315  mov     this, rax; hProcess
0x18002e318  mov     edx, 8000FFFFh; uExitCode
0x18002e31d  call    cs:__imp_TerminateProcess
0x18002e323  int     3; Trap to Debugger
0x18002e324  test    r11, this
0x18002e327  jnz     short loc_18002E339
0x18002e329  test    r10, this
0x18002e32c  jz      loc_18002E1E9
0x18002e332  mov     edx, 400000h
0x18002e337  jmp     short loc_18002E33E
0x18002e339  mov     edx, 200000h
0x18002e33e  or      r8, rdx
0x18002e341  jmp     loc_18002E1E9
0x18002e346  test    r11, rax
0x18002e349  jnz     short loc_18002E361
0x18002e34b  test    r10, rax
0x18002e34e  jz      loc_18002E2A4
0x18002e354  mov     ecx, 400000h
0x18002e359  or      rdx, this
0x18002e35c  jmp     loc_18002E2A4
0x18002e361  mov     ecx, 200000h
0x18002e366  or      rdx, this
0x18002e369  jmp     loc_18002E2A4
0x18002e36e  cmp     rdx, 200000h
0x18002e375  jnz     loc_18002E404
0x18002e37b  mov     this, rdi; this
0x18002e37e  call    ?RWSetWriterSignal@CRWLock@@AEAAXXZ; CRWLock::RWSetWriterSignal(void)
0x18002e383  jmp     loc_18002E202
0x18002e388  cmp     this, 400000h
0x18002e38f  jnz     loc_18002E241
0x18002e395  bt      r8, 17h
0x18002e39a  jb      loc_18002E241
0x18002e3a0  mov     this, rdi; this
0x18002e3a3  call    ?RWSetReaderSignal@CRWLock@@AEAAXXZ; CRWLock::RWSetReaderSignal(void)
0x18002e3a8  xor     eax, eax
0x18002e3aa  mov     rbx, [rsp+28h+arg_8]
0x18002e3af  mov     rsi, [rsp+28h+arg_10]
0x18002e3b4  add     rsp, 20h
0x18002e3b8  pop     rdi
0x18002e3b9  retn
0x18002e3ba  call    cs:__imp_RtlDllShutdownInProgress
0x18002e3c0  test    al, al
0x18002e3c2  jnz     short loc_18002E3CA
0x18002e3c4  call    cs:__imp_IsDebuggerPresent
0x18002e3ca  call    cs:__imp_GetCurrentProcess
0x18002e3d0  mov     this, rax; hProcess
0x18002e3d3  mov     edx, 8000FFFFh; uExitCode
0x18002e3d8  call    cs:__imp_TerminateProcess
0x18002e3de  int     3; Trap to Debugger
0x18002e3df  call    cs:__imp_RtlDllShutdownInProgress
0x18002e3e5  test    al, al
0x18002e3e7  jnz     short loc_18002E3EF
0x18002e3e9  call    cs:__imp_IsDebuggerPresent
0x18002e3ef  call    cs:__imp_GetCurrentProcess
0x18002e3f5  mov     this, rax; hProcess
0x18002e3f8  mov     edx, 8000FFFFh; uExitCode
0x18002e3fd  call    cs:__imp_TerminateProcess
0x18002e403  int     3; Trap to Debugger
0x18002e404  cmp     rdx, 400000h
0x18002e40b  jnz     loc_18002E202
0x18002e411  bt      r9, 17h
0x18002e416  jb      loc_18002E202
0x18002e41c  mov     this, rdi; this
0x18002e41f  call    ?RWSetReaderSignal@CRWLock@@AEAAXXZ; CRWLock::RWSetReaderSignal(void)
0x18002e424  jmp     loc_18002E202
0x18002e429  call    cs:__imp_RtlDllShutdownInProgress
0x18002e42f  test    al, al
0x18002e431  jnz     loc_18002E241
0x18002e437  call    cs:__imp_IsDebuggerPresent
0x18002e43d  mov     rbx, [rsp+28h+arg_8]
0x18002e442  xor     eax, eax
0x18002e444  mov     rsi, [rsp+28h+arg_10]
0x18002e449  add     rsp, 20h
0x18002e44d  pop     rdi
0x18002e44e  retn
0x18002e44f  mov     this, [rbx]
0x18002e452  cmp     [this+10h], rsi
0x18002e456  jz      loc_18002E23D
0x18002e45c  mov     rax, [rbx+8]
0x18002e460  mov     [rax], this
0x18002e463  mov     this, [rbx]
0x18002e466  mov     rax, [rbx+8]
0x18002e46a  mov     [this+8], rax
0x18002e46e  mov     this, [rdx]
0x18002e471  mov     [rbx], this
0x18002e474  mov     rax, [this+8]
0x18002e478  mov     [rbx+8], rax
0x18002e47c  mov     [rax], rbx
0x18002e47f  mov     [this+8], rbx
0x18002e483  jmp     loc_18002E23D
```
