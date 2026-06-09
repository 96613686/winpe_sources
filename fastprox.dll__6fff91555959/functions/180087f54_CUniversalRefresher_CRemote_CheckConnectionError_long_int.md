# CUniversalRefresher::CRemote::CheckConnectionError(long,int)

- ea: `0x180087f54`
- end: `0x18008816e`
- name: `?CheckConnectionError@CRemote@CUniversalRefresher@@QEAAXJH@Z`
- size: `538`
- prototype: `void __fastcall(CUniversalRefresher::CRemote *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800474d8`
- `0x1800894bc`

## callees

- `0x180037120`
- `0x180086430`
- `0x180086480`
- `0x180087f54`
- `0x180088330`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x1800880b5`
- `msvcrt!_beginthreadex` at `0x1800880b5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800880d8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800880d8`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180088123`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180088123`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180087fd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180087fd1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180087fb6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180087fb6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180087fe1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180087fe1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180087f9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180087f9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088135`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088135`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087fc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008803f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800880fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087fc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008803f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800880fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CUniversalRefresher::CRemote::CheckConnectionError(CUniversalRefresher::CRemote *this, int a2, int a3)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  void *v7; // rax
  void *v8; // rbx
  DWORD v9; // eax
  HANDLE Token; // [rsp+30h] [rbp-50h] BYREF
  HANDLE Thread[2]; // [rsp+38h] [rbp-48h] BYREF
  CUniversalRefresher::CRemote *v12; // [rsp+48h] [rbp-38h] BYREF
  char v13; // [rsp+50h] [rbp-30h]
  HANDLE v14; // [rsp+58h] [rbp-28h] BYREF
  bool v15; // [rsp+60h] [rbp-20h]
  HANDLE v16; // [rsp+68h] [rbp-18h] BYREF
  bool v17; // [rsp+70h] [rbp-10h]
  unsigned int ThrdAddr; // [rsp+98h] [rbp+18h] BYREF
  HANDLE TokenHandle; // [rsp+A8h] [rbp+28h] BYREF

  if ( (unsigned __int16)a2 == 1722 || a2 == -2147417848 || (unsigned __int16)a2 == 1726 )
  {
    if ( a3 )
    {
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle)
        || GetLastError() == 1008
        && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0x2000Eu, &TokenHandle)) )
      {
        v16 = TokenHandle;
        v17 = TokenHandle == 0;
        Token = 0;
        if ( TokenHandle
          && !(unsigned int)DuplicateTokenSameAcl(TokenHandle, &Token)
          && WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, LastError);
        }
        v14 = Token;
        v15 = Token == 0;
        *((_DWORD *)this + 20) = 0;
        _InterlockedIncrement((volatile signed __int32 *)this + 88);
        v12 = this;
        v13 = 0;
        ThrdAddr = 0;
        v7 = (void *)_beginthreadex(0, 0, CUniversalRefresher::CRemote::ThreadProc, this, 4u, &ThrdAddr);
        v8 = v7;
        Thread[0] = v7;
        if ( v7 )
        {
          Thread[1] = v7;
          if ( Token
            && !SetThreadToken(Thread, Token)
            && WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v9 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, v9);
          }
          if ( ResumeThread(Thread[0]) != -1 )
            v13 = 1;
          CloseHandle(v8);
        }
        OnDeleteObjIf0<CUniversalRefresher::CRemote,unsigned long (CUniversalRefresher::CRemote::*)(void),&public: unsigned long CUniversalRefresher::CRemote::Release(void)>::~OnDeleteObjIf0<CUniversalRefresher::CRemote,unsigned long (CUniversalRefresher::CRemote::*)(void),&public: unsigned long CUniversalRefresher::CRemote::Release(void)>((__int64)&v12);
        OnDeleteIf<void *,int (*)(void *),&int CloseHandle(void *)>::~OnDeleteIf<void *,int (*)(void *),&int CloseHandle(void *)>((__int64)&v14);
        OnDeleteIf<void *,int (*)(void *),&int CloseHandle(void *)>::~OnDeleteIf<void *,int (*)(void *),&int CloseHandle(void *)>((__int64)&v16);
      }
    }
  }
}

```

## disassembly

```asm
0x180087f54  mov     [rsp-8+arg_0], rbx
0x180087f59  mov     [rsp-8+arg_10], r14
0x180087f5e  push    rbp
0x180087f5f  mov     rbp, rsp
0x180087f62  sub     rsp, 80h
0x180087f69  mov     rbx, rcx
0x180087f6c  movzx   eax, dx
0x180087f6f  cmp     eax, 6BAh
0x180087f74  jz      short loc_180087F89
0x180087f76  cmp     edx, 80010108h
0x180087f7c  jz      short loc_180087F89
0x180087f7e  cmp     eax, 6BEh
0x180087f83  jnz     loc_180088159
0x180087f89  test    r8d, r8d
0x180087f8c  jz      loc_180088159
0x180087f92  mov     [rbp+TokenHandle], 0
0x180087f9a  call    cs:__imp_GetCurrentThread
0x180087fa0  mov     rcx, rax; ThreadHandle
0x180087fa3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180087fa7  mov     r8d, 1; OpenAsSelf
0x180087fad  mov     r14d, 2000Eh
0x180087fb3  mov     edx, r14d; DesiredAccess
0x180087fb6  call    cs:__imp_OpenThreadToken
0x180087fbc  test    eax, eax
0x180087fbe  jnz     short loc_180087FEF
0x180087fc0  call    cs:__imp_GetLastError
0x180087fc6  cmp     eax, 3F0h
0x180087fcb  jnz     loc_180088159
0x180087fd1  call    cs:__imp_GetCurrentProcess
0x180087fd7  mov     rcx, rax; ProcessHandle
0x180087fda  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180087fde  mov     edx, r14d; DesiredAccess
0x180087fe1  call    cs:__imp_OpenProcessToken
0x180087fe7  test    eax, eax
0x180087fe9  jz      loc_180088159
0x180087fef  mov     rax, [rbp+TokenHandle]
0x180087ff3  mov     [rbp+var_18], rax
0x180087ff7  mov     [rbp+var_10], 0
0x180087ffb  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180087fff  test    rcx, rcx
0x180088002  setz    [rbp+var_10]
0x180088006  mov     [rbp+Token], 0
0x18008800e  lea     r14, WPP_GLOBAL_Control
0x180088015  test    rcx, rcx
0x180088018  jz      short loc_180088064
0x18008801a  lea     rdx, [rbp+Token]; phNewToken
0x18008801e  call    ?DuplicateTokenSameAcl@@YAHPEAXPEAPEAX@Z; DuplicateTokenSameAcl(void *,void * *)
0x180088023  test    eax, eax
0x180088025  jnz     short loc_180088064
0x180088027  mov     rax, cs:WPP_GLOBAL_Control
0x18008802e  cmp     rax, r14
0x180088031  jz      short loc_180088064
0x180088033  test    byte ptr [rax+1Ch], 1
0x180088037  jz      short loc_180088064
0x180088039  cmp     byte ptr [rax+19h], 5
0x18008803d  jb      short loc_180088064
0x18008803f  call    cs:__imp_GetLastError
0x180088045  mov     edx, 88h
0x18008804a  mov     r9d, eax
0x18008804d  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180088054  mov     rcx, cs:WPP_GLOBAL_Control
0x18008805b  mov     rcx, [rcx+10h]
0x18008805f  call    WPP_SF_d
0x180088064  mov     rax, [rbp+Token]
0x180088068  mov     [rbp+var_28], rax
0x18008806c  mov     [rbp+var_20], 0
0x180088070  cmp     [rbp+Token], 0
0x180088075  setz    [rbp+var_20]
0x180088079  mov     dword ptr [rbx+50h], 0
0x180088080  lock inc dword ptr [rbx+160h]
0x180088087  mov     [rbp+var_38], rbx
0x18008808b  mov     [rbp+var_30], 0
0x18008808f  mov     [rbp+arg_8], 0
0x180088096  lea     rax, [rbp+arg_8]
0x18008809a  mov     [rsp+80h+ThrdAddr], rax; ThrdAddr
0x18008809f  mov     [rsp+80h+InitFlag], 4; InitFlag
0x1800880a7  mov     r9, rbx; ArgList
0x1800880aa  lea     r8, ?ThreadProc@CRemote@CUniversalRefresher@@KAIPEAX@Z; StartAddress
0x1800880b1  xor     edx, edx; StackSize
0x1800880b3  xor     ecx, ecx; Security
0x1800880b5  call    cs:__imp__beginthreadex
0x1800880bb  mov     rbx, rax
0x1800880be  mov     [rbp+Thread], rax
0x1800880c2  test    rax, rax
0x1800880c5  jz      short loc_18008813C
0x1800880c7  mov     [rbp+var_40], rax
0x1800880cb  mov     rdx, [rbp+Token]; Token
0x1800880cf  test    rdx, rdx
0x1800880d2  jz      short loc_18008811F
0x1800880d4  lea     rcx, [rbp+Thread]; Thread
0x1800880d8  call    cs:__imp_SetThreadToken
0x1800880de  test    eax, eax
0x1800880e0  jnz     short loc_18008811F
0x1800880e2  mov     rax, cs:WPP_GLOBAL_Control
0x1800880e9  cmp     rax, r14
0x1800880ec  jz      short loc_18008811F
0x1800880ee  test    byte ptr [rax+1Ch], 1
0x1800880f2  jz      short loc_18008811F
0x1800880f4  cmp     byte ptr [rax+19h], 5
0x1800880f8  jb      short loc_18008811F
0x1800880fa  call    cs:__imp_GetLastError
0x180088100  mov     edx, 89h
0x180088105  mov     r9d, eax
0x180088108  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18008810f  mov     rcx, cs:WPP_GLOBAL_Control
0x180088116  mov     rcx, [rcx+10h]
0x18008811a  call    WPP_SF_d
0x18008811f  mov     rcx, [rbp+Thread]; hThread
0x180088123  call    cs:__imp_ResumeThread
0x180088129  cmp     eax, 0FFFFFFFFh
0x18008812c  jz      short loc_180088132
0x18008812e  mov     [rbp+var_30], 1
0x180088132  mov     rcx, rbx; hObject
0x180088135  call    cs:__imp_CloseHandle
0x18008813b  nop
0x18008813c  lea     rcx, [rbp+var_38]
0x180088140  call    ??1?$OnDeleteObjIf0@VCRemote@CUniversalRefresher@@P812@EAAKXZ$1?Release@12@QEAAKXZ@@QEAA@XZ; OnDeleteObjIf0<CUniversalRefresher::CRemote,ulong (CUniversalRefresher::CRemote::*)(void),&CUniversalRefresher::CRemote::Release(void)>::~OnDeleteObjIf0<CUniversalRefresher::CRemote,ulong (CUniversalRefresher::CRemote::*)(void),&CUniversalRefresher::CRemote::Release(void)>(void)
0x180088145  nop
0x180088146  lea     rcx, [rbp+var_28]
0x18008814a  call    ??1?$OnDeleteIf@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@QEAA@XZ; OnDeleteIf<void *,int (*)(void *),&CloseHandle(void *)>::~OnDeleteIf<void *,int (*)(void *),&CloseHandle(void *)>(void)
0x18008814f  nop
0x180088150  lea     rcx, [rbp+var_18]
0x180088154  call    ??1?$OnDeleteIf@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@QEAA@XZ; OnDeleteIf<void *,int (*)(void *),&CloseHandle(void *)>::~OnDeleteIf<void *,int (*)(void *),&CloseHandle(void *)>(void)
0x180088159  lea     r11, [rsp+80h+var_s0]
0x180088161  mov     rbx, [r11+10h]
0x180088165  mov     r14, [r11+20h]
0x180088169  mov     rsp, r11
0x18008816c  pop     rbp
0x18008816d  retn
```
