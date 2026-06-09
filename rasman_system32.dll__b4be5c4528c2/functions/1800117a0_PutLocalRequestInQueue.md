# PutLocalRequestInQueue

- ea: `0x1800117a0`
- end: `0x1800119a8`
- name: `PutLocalRequestInQueue`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800030d0`

## callees

- `0x1800117a0`
- `0x1800119b0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011836`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011836`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011855`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011986`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011997`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011986`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001195d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001195d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011869`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011869`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011949`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011949`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001189d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001189d`
- `rtutils!TracePrintfExA` at `0x180011922`
- `rtutils!TracePrintfExA` at `0x180011922`

## string_xrefs

- `0x18001190a`: `PutLocalRequestInQueue: OpenThreadToken Failed 0x%.8x`
- `0x1800118ce`: `PutLocalRequestInQueue: DuplicateToken Failed 0x%.8x`
- `0x180011913`: `PutLocalRequestInQueue: ImpersonateLoggedOnUser failed 0x%.8x`

## pseudocode

```c
__int64 __fastcall PutLocalRequestInQueue(__int64 a1, unsigned int a2)
{
  unsigned int v2; // ebx
  DWORD v5; // eax
  HANDLE CurrentThread; // rax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD LastError; // eax
  void *DuplicateTokenHandle; // [rsp+40h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+20h] BYREF

  v2 = 0;
  TokenHandle = 0;
  DuplicateTokenHandle = 0;
  if ( !g_fRasmanService || !g_fnRasmanServiceInitialized || !g_fnRasmanServiceInitialized() )
  {
    v5 = RemoteSubmitRequestLocal(a1, a2);
    goto LABEL_3;
  }
  if ( !g_fnServiceRequest )
  {
    v2 = 711;
    goto LABEL_4;
  }
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    ((void (__fastcall *)(__int64, _QWORD))g_fnServiceRequest)(a1, a2);
    goto LABEL_4;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    if ( RevertToSelf() )
    {
      ((void (__fastcall *)(__int64, _QWORD))g_fnServiceRequest)(a1, a2);
      if ( DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
      {
        if ( !ImpersonateLoggedOnUser(DuplicateTokenHandle) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "PutLocalRequestInQueue: ImpersonateLoggedOnUser failed 0x%.8x",
              LastError);
        }
      }
      else
      {
        v8 = GetLastError();
        v2 = v8;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "PutLocalRequestInQueue: DuplicateToken Failed 0x%.8x", v8);
      }
      goto LABEL_4;
    }
    v5 = GetLastError();
LABEL_3:
    v2 = v5;
    goto LABEL_4;
  }
  v9 = GetLastError();
  v2 = v9;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "PutLocalRequestInQueue: OpenThreadToken Failed 0x%.8x", v9);
LABEL_4:
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x1800117a0  mov     [rsp+arg_0], rbx
0x1800117a5  mov     [rsp+arg_8], rsi
0x1800117aa  push    rdi
0x1800117ab  sub     rsp, 20h
0x1800117af  xor     ebx, ebx
0x1800117b1  mov     edi, edx
0x1800117b3  cmp     cs:g_fRasmanService, ebx
0x1800117b9  mov     rsi, rcx
0x1800117bc  mov     [rsp+28h+TokenHandle], rbx
0x1800117c1  mov     [rsp+28h+DuplicateTokenHandle], rbx
0x1800117c6  jnz     short loc_180011803
0x1800117c8  mov     edx, edi
0x1800117ca  mov     rcx, rsi
0x1800117cd  call    RemoteSubmitRequestLocal
0x1800117d2  mov     ebx, eax
0x1800117d4  mov     rcx, [rsp+28h+DuplicateTokenHandle]; hObject
0x1800117d9  test    rcx, rcx
0x1800117dc  jnz     loc_180011986
0x1800117e2  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800117e7  test    rcx, rcx
0x1800117ea  jnz     loc_180011997
0x1800117f0  mov     rsi, [rsp+28h+arg_8]
0x1800117f5  mov     eax, ebx
0x1800117f7  mov     rbx, [rsp+28h+arg_0]
0x1800117fc  add     rsp, 20h
0x180011800  pop     rdi
0x180011801  retn
0x180011803  mov     rax, cs:g_fnRasmanServiceInitialized
0x18001180a  test    rax, rax
0x18001180d  jz      short loc_1800117C8
0x18001180f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011814  test    rax, rax
0x180011817  jz      short loc_1800117C8
0x180011819  cmp     cs:g_fnServiceRequest, rbx
0x180011820  jz      loc_18001197C
0x180011826  mov     eax, gs:179Ch
0x18001182e  test    eax, eax
0x180011830  jz      loc_1800118D7
0x180011836  call    cs:__imp_GetCurrentThread
0x18001183d  nop     dword ptr [rax+rax+00h]
0x180011842  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180011847  mov     edx, 0F01FFh; DesiredAccess
0x18001184c  mov     rcx, rax; ThreadHandle
0x18001184f  mov     r8d, 1; OpenAsSelf
0x180011855  call    cs:__imp_OpenThreadToken
0x18001185c  nop     dword ptr [rax+rax+00h]
0x180011861  test    eax, eax
0x180011863  jz      loc_1800118ED
0x180011869  call    cs:__imp_RevertToSelf
0x180011870  nop     dword ptr [rax+rax+00h]
0x180011875  test    eax, eax
0x180011877  jz      loc_180011933
0x18001187d  mov     rax, cs:g_fnServiceRequest
0x180011884  mov     edx, edi
0x180011886  mov     rcx, rsi
0x180011889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001188e  mov     rcx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x180011893  lea     r8, [rsp+28h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180011898  mov     edx, 2; ImpersonationLevel
0x18001189d  call    cs:__imp_DuplicateToken
0x1800118a4  nop     dword ptr [rax+rax+00h]
0x1800118a9  test    eax, eax
0x1800118ab  jnz     loc_180011944
0x1800118b1  call    cs:__imp_GetLastError
0x1800118b8  nop     dword ptr [rax+rax+00h]
0x1800118bd  mov     ecx, cs:g_dwTraceId
0x1800118c3  mov     ebx, eax
0x1800118c5  cmp     ecx, 0FFFFFFFFh
0x1800118c8  jz      loc_1800117D4
0x1800118ce  lea     r8, aPutlocalreques_0; "PutLocalRequestInQueue: DuplicateToken "...
0x1800118d5  jmp     short loc_18001191A
0x1800118d7  mov     rax, cs:g_fnServiceRequest
0x1800118de  mov     edx, edi
0x1800118e0  mov     rcx, rsi
0x1800118e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e8  jmp     loc_1800117D4
0x1800118ed  call    cs:__imp_GetLastError
0x1800118f4  nop     dword ptr [rax+rax+00h]
0x1800118f9  mov     ecx, cs:g_dwTraceId
0x1800118ff  mov     ebx, eax
0x180011901  cmp     ecx, 0FFFFFFFFh
0x180011904  jz      loc_1800117D4
0x18001190a  lea     r8, aPutlocalreques_1; "PutLocalRequestInQueue: OpenThreadToken"...
0x180011911  jmp     short loc_18001191A
0x180011913  lea     r8, aPutlocalreques; "PutLocalRequestInQueue: ImpersonateLogg"...
0x18001191a  mov     r9d, eax
0x18001191d  mov     edx, 0Ch; dwFlags
0x180011922  call    cs:__imp_TracePrintfExA
0x180011929  nop     dword ptr [rax+rax+00h]
0x18001192e  jmp     loc_1800117D4
0x180011933  call    cs:__imp_GetLastError
0x18001193a  nop     dword ptr [rax+rax+00h]
0x18001193f  jmp     loc_1800117D2
0x180011944  mov     rcx, [rsp+28h+DuplicateTokenHandle]; hToken
0x180011949  call    cs:__imp_ImpersonateLoggedOnUser
0x180011950  nop     dword ptr [rax+rax+00h]
0x180011955  test    eax, eax
0x180011957  jnz     loc_1800117D4
0x18001195d  call    cs:__imp_GetLastError
0x180011964  nop     dword ptr [rax+rax+00h]
0x180011969  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001196f  mov     ebx, eax
0x180011971  cmp     ecx, 0FFFFFFFFh
0x180011974  jz      loc_1800117D4
0x18001197a  jmp     short loc_180011913
0x18001197c  mov     ebx, 2C7h
0x180011981  jmp     loc_1800117D4
0x180011986  call    cs:__imp_CloseHandle
0x18001198d  nop     dword ptr [rax+rax+00h]
0x180011992  jmp     loc_1800117E2
0x180011997  call    cs:__imp_CloseHandle
0x18001199e  nop     dword ptr [rax+rax+00h]
0x1800119a3  jmp     loc_1800117F0
```
