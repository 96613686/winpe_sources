# pSetupEnableThreadPrivileges

- ea: `0x1800233b8`
- end: `0x1800236c4`
- name: `pSetupEnableThreadPrivileges`
- size: `780`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180022624`

## callees

- `0x1800233b8`
- `0x18007dd10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002368d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800236a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002368d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800236a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023413`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002352f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023413`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002352f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002345d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002349e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800234e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023543`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002358e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023608`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800236ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002345d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002349e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800234e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023543`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002358e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023608`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800236ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023478`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800234a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800234a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800234b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800234b6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023614`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023614`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023676`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800235f2`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800235f2`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800234fc`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18002355f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800234fc`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18002355f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800235b6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800235b6`

## pseudocode

```c
__int64 __fastcall pSetupEnableThreadPrivileges(__int64 a1)
{
  __int64 v2; // r15
  DWORD LastError; // ebx
  void *v4; // r14
  struct _TOKEN_PRIVILEGES *v5; // rax
  struct _TOKEN_PRIVILEGES *v6; // rsi
  __int64 i; // rdx
  __int64 v8; // rcx
  HANDLE CurrentThread; // rax
  DWORD v10; // eax
  HANDLE CurrentProcess; // rax
  void *v12; // rdi
  DWORD v13; // eax
  LUID v15; // [rsp+30h] [rbp-20h]
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+38h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp+40h] BYREF
  DWORD nLengthNeeded; // [rsp+98h] [rbp+48h] BYREF
  HANDLE Token; // [rsp+A0h] [rbp+50h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp+58h] BYREF

  TokenHandle = (void *)-1LL;
  Handle = (HANDLE)-1LL;
  Token = (HANDLE)-1LL;
  v2 = -1;
  nLengthNeeded = 0;
  memset(&TokenAttributes, 0, 20);
  if ( !a1 )
  {
    LastError = 87;
    goto LABEL_44;
  }
  v4 = 0;
  nLengthNeeded = 28;
  v5 = (struct _TOKEN_PRIVILEGES *)HeapAlloc(hHeap, 0, 0x1Cu);
  v6 = v5;
  if ( !v5 )
    goto LABEL_4;
  v5->PrivilegeCount = 2;
  for ( i = 0; i != 2; ++i )
  {
    v8 = i;
    v15 = (LUID)*(unsigned int *)(a1 + 4 * i);
    v5->Privileges[v8].Luid = v15;
    v5->Privileges[v8].Attributes = 2;
  }
  SetLastError(0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20006u, 0, &TokenHandle)
    || (v10 = pSpUtilsGetLastError(), (LastError = v10) == 0) )
  {
    v12 = TokenHandle;
  }
  else
  {
    TokenHandle = (void *)-1LL;
    if ( v10 != 1008 )
      goto LABEL_34;
    SetLastError(0);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20002u, &Handle) )
    {
      LastError = pSpUtilsGetLastError();
      if ( LastError )
      {
        Handle = (HANDLE)-1LL;
        goto LABEL_34;
      }
    }
    v12 = Handle;
  }
  SetLastError(0);
  if ( GetKernelObjectSecurity(v12, 4u, 0, 0, &nLengthNeeded) || (v13 = pSpUtilsGetLastError(), (LastError = v13) == 0) )
  {
LABEL_33:
    LastError = 13;
    goto LABEL_34;
  }
  if ( v13 != 122 )
    goto LABEL_34;
  v4 = HeapAlloc(hHeap, 0, nLengthNeeded);
  if ( !v4 )
  {
LABEL_4:
    LastError = 8;
    goto LABEL_34;
  }
  SetLastError(0);
  if ( !GetKernelObjectSecurity(v12, LastError - 118, v4, nLengthNeeded, &nLengthNeeded) )
  {
    LastError = pSpUtilsGetLastError();
    if ( LastError )
    {
LABEL_34:
      if ( Token != (HANDLE)-1LL )
        CloseHandle(Token);
      goto LABEL_36;
    }
  }
  *(_QWORD *)&TokenAttributes.nLength = 24;
  *(_QWORD *)&TokenAttributes.bInheritHandle = 0;
  TokenAttributes.lpSecurityDescriptor = v4;
  SetLastError(0);
  if ( DuplicateTokenEx(v12, 0x2Cu, &TokenAttributes, SecurityImpersonation, TokenImpersonation, &Token)
    || (LastError = pSpUtilsGetLastError()) == 0 )
  {
    if ( !AdjustTokenPrivileges(Token, 0, v6, 0, 0, 0) )
    {
      LastError = GetLastError();
      goto LABEL_34;
    }
    SetLastError(0);
    if ( SetThreadToken(0, Token) )
    {
      LastError = 0;
    }
    else
    {
      LastError = pSpUtilsGetLastError();
      if ( LastError )
        goto LABEL_34;
    }
    if ( v12 == TokenHandle )
    {
      v2 = (__int64)TokenHandle;
      TokenHandle = (void *)-1LL;
      goto LABEL_34;
    }
    if ( v12 == Handle )
    {
      v2 = 0;
      goto LABEL_34;
    }
    goto LABEL_33;
  }
  Token = (HANDLE)-1LL;
LABEL_36:
  if ( Handle != (HANDLE)-1LL )
    CloseHandle(Handle);
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  if ( v4 )
    HeapFree(hHeap, 0, v4);
  if ( v6 )
    HeapFree(hHeap, 0, v6);
LABEL_44:
  SetLastError(LastError);
  return v2;
}

```

## disassembly

```asm
0x1800233b8  mov     [rsp-38h+nLengthNeeded], edx
0x1800233bc  push    rbp
0x1800233bd  push    rbx
0x1800233be  push    rsi
0x1800233bf  push    rdi
0x1800233c0  push    r13
0x1800233c2  push    r14
0x1800233c4  push    r15
0x1800233c6  mov     rbp, rsp
0x1800233c9  sub     rsp, 50h
0x1800233cd  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800233d1  xor     eax, eax
0x1800233d3  mov     [rbp+TokenHandle], r13
0x1800233d7  xorps   xmm0, xmm0
0x1800233da  mov     [rbp+Handle], r13
0x1800233de  mov     rbx, rcx
0x1800233e1  mov     [rbp+Token], r13
0x1800233e5  mov     r15, r13
0x1800233e8  mov     [rbp+TokenAttributes.bInheritHandle], eax
0x1800233eb  mov     [rbp+nLengthNeeded], eax
0x1800233ee  movups  xmmword ptr [rbp+TokenAttributes.nLength], xmm0
0x1800233f2  test    rcx, rcx
0x1800233f5  jnz     short loc_1800233FF
0x1800233f7  lea     ebx, [rcx+57h]
0x1800233fa  jmp     loc_1800236AA
0x1800233ff  mov     rcx, cs:hHeap; hHeap
0x180023406  xor     r14d, r14d
0x180023409  xor     edx, edx; dwFlags
0x18002340b  lea     r8d, [r14+1Ch]; dwBytes
0x18002340f  mov     [rbp+nLengthNeeded], r8d
0x180023413  call    cs:__imp_HeapAlloc
0x180023419  mov     rsi, rax
0x18002341c  test    rax, rax
0x18002341f  jnz     short loc_18002342B
0x180023421  mov     ebx, 8
0x180023426  jmp     loc_18002364F
0x18002342b  mov     dword ptr [rax], 2
0x180023431  xor     edx, edx
0x180023433  mov     eax, [rbx+rdx*4]
0x180023436  lea     rcx, [rdx+rdx*2]
0x18002343a  mov     dword ptr [rbp+var_20], eax
0x18002343d  inc     rdx
0x180023440  mov     dword ptr [rbp+var_20+4], r14d
0x180023444  mov     rax, [rbp+var_20]
0x180023448  mov     [rsi+rcx*4+4], rax
0x18002344d  mov     dword ptr [rsi+rcx*4+0Ch], 2
0x180023455  cmp     rdx, 2
0x180023459  jnz     short loc_180023433
0x18002345b  xor     ecx, ecx; dwErrCode
0x18002345d  call    cs:__imp_SetLastError
0x180023463  call    cs:__imp_GetCurrentThread
0x180023469  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002346d  xor     r8d, r8d; OpenAsSelf
0x180023470  mov     rcx, rax; ThreadHandle
0x180023473  mov     edx, 20006h; DesiredAccess
0x180023478  call    cs:__imp_OpenThreadToken
0x18002347e  test    eax, eax
0x180023480  jnz     short loc_1800234DA
0x180023482  call    _pSpUtilsGetLastError
0x180023487  mov     ebx, eax
0x180023489  test    eax, eax
0x18002348b  jz      short loc_1800234DA
0x18002348d  mov     [rbp+TokenHandle], r13
0x180023491  cmp     eax, 3F0h
0x180023496  jnz     loc_18002364F
0x18002349c  xor     ecx, ecx; dwErrCode
0x18002349e  call    cs:__imp_SetLastError
0x1800234a4  call    cs:__imp_GetCurrentProcess
0x1800234aa  lea     r8, [rbp+Handle]; TokenHandle
0x1800234ae  mov     edx, 20002h; DesiredAccess
0x1800234b3  mov     rcx, rax; ProcessHandle
0x1800234b6  call    cs:__imp_OpenProcessToken
0x1800234bc  test    eax, eax
0x1800234be  jnz     short loc_1800234D4
0x1800234c0  call    _pSpUtilsGetLastError
0x1800234c5  mov     ebx, eax
0x1800234c7  test    eax, eax
0x1800234c9  jz      short loc_1800234D4
0x1800234cb  mov     [rbp+Handle], r13
0x1800234cf  jmp     loc_18002364F
0x1800234d4  mov     rdi, [rbp+Handle]
0x1800234d8  jmp     short loc_1800234DE
0x1800234da  mov     rdi, [rbp+TokenHandle]
0x1800234de  xor     ecx, ecx; dwErrCode
0x1800234e0  call    cs:__imp_SetLastError
0x1800234e6  xor     r9d, r9d; nLength
0x1800234e9  lea     rax, [rbp+nLengthNeeded]
0x1800234ed  xor     r8d, r8d; pSecurityDescriptor
0x1800234f0  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800234f5  mov     rcx, rdi; Handle
0x1800234f8  lea     edx, [r9+4]; RequestedInformation
0x1800234fc  call    cs:__imp_GetKernelObjectSecurity
0x180023502  test    eax, eax
0x180023504  jnz     loc_18002364A
0x18002350a  call    _pSpUtilsGetLastError
0x18002350f  mov     ebx, eax
0x180023511  test    eax, eax
0x180023513  jz      loc_18002364A
0x180023519  cmp     eax, 7Ah ; 'z'
0x18002351c  jnz     loc_18002364F
0x180023522  mov     r8d, [rbp+nLengthNeeded]; dwBytes
0x180023526  xor     edx, edx; dwFlags
0x180023528  mov     rcx, cs:hHeap; hHeap
0x18002352f  call    cs:__imp_HeapAlloc
0x180023535  mov     r14, rax
0x180023538  test    rax, rax
0x18002353b  jz      loc_180023421
0x180023541  xor     ecx, ecx; dwErrCode
0x180023543  call    cs:__imp_SetLastError
0x180023549  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18002354d  lea     rax, [rbp+nLengthNeeded]
0x180023551  mov     r8, r14; pSecurityDescriptor
0x180023554  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180023559  lea     edx, [rbx-76h]; RequestedInformation
0x18002355c  mov     rcx, rdi; Handle
0x18002355f  call    cs:__imp_GetKernelObjectSecurity
0x180023565  test    eax, eax
0x180023567  jnz     short loc_180023578
0x180023569  call    _pSpUtilsGetLastError
0x18002356e  mov     ebx, eax
0x180023570  test    eax, eax
0x180023572  jnz     loc_18002364F
0x180023578  xor     ecx, ecx; dwErrCode
0x18002357a  mov     qword ptr [rbp+TokenAttributes.nLength], 18h
0x180023582  mov     qword ptr [rbp+TokenAttributes.bInheritHandle], 0
0x18002358a  mov     [rbp+TokenAttributes.lpSecurityDescriptor], r14
0x18002358e  call    cs:__imp_SetLastError
0x180023594  mov     r9d, 2; ImpersonationLevel
0x18002359a  lea     rax, [rbp+Token]
0x18002359e  mov     [rsp+50h+phNewToken], rax; phNewToken
0x1800235a3  lea     r8, [rbp+TokenAttributes]; lpTokenAttributes
0x1800235a7  mov     rcx, rdi; hExistingToken
0x1800235aa  mov     dword ptr [rsp+50h+lpnLengthNeeded], 2; TokenType
0x1800235b2  lea     edx, [r9+2Ah]; dwDesiredAccess
0x1800235b6  call    cs:__imp_DuplicateTokenEx
0x1800235bc  test    eax, eax
0x1800235be  jnz     short loc_1800235D4
0x1800235c0  call    _pSpUtilsGetLastError
0x1800235c5  mov     ebx, eax
0x1800235c7  test    eax, eax
0x1800235c9  jz      short loc_1800235D4
0x1800235cb  mov     [rbp+Token], r13
0x1800235cf  jmp     loc_18002365E
0x1800235d4  mov     rcx, [rbp+Token]; TokenHandle
0x1800235d8  xor     r9d, r9d; BufferLength
0x1800235db  mov     [rsp+50h+phNewToken], 0; ReturnLength
0x1800235e4  mov     r8, rsi; NewState
0x1800235e7  xor     edx, edx; DisableAllPrivileges
0x1800235e9  mov     [rsp+50h+lpnLengthNeeded], 0; PreviousState
0x1800235f2  call    cs:__imp_AdjustTokenPrivileges
0x1800235f8  test    eax, eax
0x1800235fa  jnz     short loc_180023606
0x1800235fc  call    cs:__imp_GetLastError
0x180023602  mov     ebx, eax
0x180023604  jmp     short loc_18002364F
0x180023606  xor     ecx, ecx; dwErrCode
0x180023608  call    cs:__imp_SetLastError
0x18002360e  mov     rdx, [rbp+Token]; Token
0x180023612  xor     ecx, ecx; Thread
0x180023614  call    cs:__imp_SetThreadToken
0x18002361a  test    eax, eax
0x18002361c  jz      short loc_180023622
0x18002361e  xor     ebx, ebx
0x180023620  jmp     short loc_18002362D
0x180023622  call    _pSpUtilsGetLastError
0x180023627  mov     ebx, eax
0x180023629  test    eax, eax
0x18002362b  jnz     short loc_18002364F
0x18002362d  mov     rcx, [rbp+TokenHandle]
0x180023631  cmp     rdi, rcx
0x180023634  jnz     short loc_18002363F
0x180023636  mov     r15, rcx
0x180023639  mov     [rbp+TokenHandle], r13
0x18002363d  jmp     short loc_18002364F
0x18002363f  cmp     rdi, [rbp+Handle]
0x180023643  jnz     short loc_18002364A
0x180023645  xor     r15d, r15d
0x180023648  jmp     short loc_18002364F
0x18002364a  mov     ebx, 0Dh
0x18002364f  mov     rcx, [rbp+Token]; hObject
0x180023653  cmp     rcx, r13
0x180023656  jz      short loc_18002365E
0x180023658  call    cs:__imp_CloseHandle
0x18002365e  mov     rcx, [rbp+Handle]; hObject
0x180023662  cmp     rcx, r13
0x180023665  jz      short loc_18002366D
0x180023667  call    cs:__imp_CloseHandle
0x18002366d  mov     rcx, [rbp+TokenHandle]; hObject
0x180023671  cmp     rcx, r13
0x180023674  jz      short loc_18002367C
0x180023676  call    cs:__imp_CloseHandle
0x18002367c  test    r14, r14
0x18002367f  jz      short loc_180023693
0x180023681  mov     rcx, cs:hHeap; hHeap
0x180023688  mov     r8, r14; lpMem
0x18002368b  xor     edx, edx; dwFlags
0x18002368d  call    cs:__imp_HeapFree
0x180023693  test    rsi, rsi
0x180023696  jz      short loc_1800236AA
0x180023698  mov     rcx, cs:hHeap; hHeap
0x18002369f  mov     r8, rsi; lpMem
0x1800236a2  xor     edx, edx; dwFlags
0x1800236a4  call    cs:__imp_HeapFree
0x1800236aa  mov     ecx, ebx; dwErrCode
0x1800236ac  call    cs:__imp_SetLastError
0x1800236b2  mov     rax, r15
0x1800236b5  add     rsp, 50h
0x1800236b9  pop     r15
0x1800236bb  pop     r14
0x1800236bd  pop     r13
0x1800236bf  pop     rdi
0x1800236c0  pop     rsi
0x1800236c1  pop     rbx
0x1800236c2  pop     rbp
0x1800236c3  retn
```
