# CngAdtGetCallerID(_LUID *)

- ea: `0x180075814`
- end: `0x180075a59`
- name: `?CngAdtGetCallerID@@YAJPEAU_LUID@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(struct _LUID *)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180075100`
- `0x180075360`
- `0x180075600`
- `0x1800fb3c0`
- `0x1800fb530`
- `0x1800fb680`

## callees

- `0x180075814`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007589f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800758b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007598c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800759cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800759db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800759ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007589f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800758b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007598c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800759cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800759db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800759ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800759b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800759b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075840`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075840`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007585d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007585d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800759a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800759a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007594c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007594c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075936`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075936`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800758dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800758dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007588b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180075911`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007588b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180075911`

## pseudocode

```c
__int64 __fastcall CngAdtGetCallerID(struct _LUID *a1)
{
  HANDLE CurrentThread; // rax
  struct _LUID *v3; // rdi
  signed int v4; // ebx
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  if ( !a1 )
    return (unsigned int)-1073741811;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        goto LABEL_3;
      if ( (int)GetLastError() <= 0 )
      {
        v4 = GetLastError();
        goto LABEL_12;
      }
      LOWORD(LastError) = GetLastError();
    }
    else if ( LastError <= 0 )
    {
      goto LABEL_12;
    }
    v4 = (unsigned __int16)LastError | 0xC0070000;
    goto LABEL_12;
  }
LABEL_3:
  v3 = 0;
  if ( GetTokenInformation(TokenHandle, TokenStatistics, 0, 0, &TokenInformationLength) )
    goto LABEL_10;
  if ( (int)GetLastError() <= 0 )
    v4 = GetLastError();
  else
    v4 = (unsigned __int16)GetLastError() | 0xC0070000;
  if ( v4 == -1073282950 )
  {
    v3 = (struct _LUID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v3 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenStatistics, v3, TokenInformationLength, &TokenInformationLength) )
      {
        if ( (int)GetLastError() > 0 )
          v4 = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          v4 = GetLastError();
LABEL_11:
        LocalFree(v3);
        goto LABEL_12;
      }
      *a1 = v3[1];
LABEL_10:
      v4 = 0;
      if ( !v3 )
        goto LABEL_12;
      goto LABEL_11;
    }
    v4 = -1073741801;
  }
  else if ( v4 >= 0 )
  {
    goto LABEL_10;
  }
LABEL_12:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180075814  mov     rax, rsp
0x180075817  mov     [rax+18h], rbx
0x18007581b  mov     [rax+20h], rdi
0x18007581f  push    r14
0x180075821  sub     rsp, 30h
0x180075825  mov     dword ptr [rax+8], 0
0x18007582c  mov     r14, rcx
0x18007582f  mov     qword ptr [rax+10h], 0
0x180075837  test    rcx, rcx
0x18007583a  jz      loc_180075985
0x180075840  call    cs:__imp_GetCurrentThread
0x180075847  nop     dword ptr [rax+rax+00h]
0x18007584c  xor     r8d, r8d; OpenAsSelf
0x18007584f  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180075854  mov     rcx, rax; ThreadHandle
0x180075857  lea     edi, [r8+8]
0x18007585b  mov     edx, edi; DesiredAccess
0x18007585d  call    cs:__imp_OpenThreadToken
0x180075864  nop     dword ptr [rax+rax+00h]
0x180075869  test    eax, eax
0x18007586b  jz      loc_18007598C
0x180075871  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180075876  lea     rax, [rsp+38h+TokenInformationLength]
0x18007587b  xor     edi, edi
0x18007587d  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180075882  xor     r9d, r9d; TokenInformationLength
0x180075885  xor     r8d, r8d; TokenInformation
0x180075888  lea     edx, [rdi+0Ah]; TokenInformationClass
0x18007588b  call    cs:__imp_GetTokenInformation
0x180075892  nop     dword ptr [rax+rax+00h]
0x180075897  test    eax, eax
0x180075899  jnz     loc_18007592C
0x18007589f  call    cs:__imp_GetLastError
0x1800758a6  nop     dword ptr [rax+rax+00h]
0x1800758ab  test    eax, eax
0x1800758ad  jle     loc_180075972
0x1800758b3  call    cs:__imp_GetLastError
0x1800758ba  nop     dword ptr [rax+rax+00h]
0x1800758bf  movzx   ebx, ax
0x1800758c2  or      ebx, 0C0070000h
0x1800758c8  cmp     ebx, 0C007007Ah
0x1800758ce  jnz     loc_18007596C
0x1800758d4  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x1800758d8  mov     ecx, 40h ; '@'; uFlags
0x1800758dd  call    cs:__imp_LocalAlloc
0x1800758e4  nop     dword ptr [rax+rax+00h]
0x1800758e9  mov     rdi, rax
0x1800758ec  test    rax, rax
0x1800758ef  jz      loc_180075A12
0x1800758f5  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800758fa  lea     rax, [rsp+38h+TokenInformationLength]
0x1800758ff  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180075904  mov     r8, rdi; TokenInformation
0x180075907  mov     edx, 0Ah; TokenInformationClass
0x18007590c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180075911  call    cs:__imp_GetTokenInformation
0x180075918  nop     dword ptr [rax+rax+00h]
0x18007591d  test    eax, eax
0x18007591f  jz      loc_180075A1C
0x180075925  mov     rax, [rdi+8]
0x180075929  mov     [r14], rax
0x18007592c  xor     ebx, ebx
0x18007592e  test    rdi, rdi
0x180075931  jz      short loc_180075942
0x180075933  mov     rcx, rdi; hMem
0x180075936  call    cs:__imp_LocalFree
0x18007593d  nop     dword ptr [rax+rax+00h]
0x180075942  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180075947  test    rcx, rcx
0x18007594a  jz      short loc_180075958
0x18007594c  call    cs:__imp_CloseHandle
0x180075953  nop     dword ptr [rax+rax+00h]
0x180075958  mov     rdi, [rsp+38h+arg_18]
0x18007595d  mov     eax, ebx
0x18007595f  mov     rbx, [rsp+38h+arg_10]
0x180075964  add     rsp, 30h
0x180075968  pop     r14
0x18007596a  retn
0x18007596c  test    ebx, ebx
0x18007596e  js      short loc_180075942
0x180075970  jmp     short loc_18007592C
0x180075972  call    cs:__imp_GetLastError
0x180075979  nop     dword ptr [rax+rax+00h]
0x18007597e  mov     ebx, eax
0x180075980  jmp     loc_1800758C8
0x180075985  mov     ebx, 0C000000Dh
0x18007598a  jmp     short loc_180075958
0x18007598c  call    cs:__imp_GetLastError
0x180075993  nop     dword ptr [rax+rax+00h]
0x180075998  mov     ebx, eax
0x18007599a  cmp     eax, 3F0h
0x18007599f  jnz     short loc_180075A08
0x1800759a1  call    cs:__imp_GetCurrentProcess
0x1800759a8  nop     dword ptr [rax+rax+00h]
0x1800759ad  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800759b2  mov     edx, edi; DesiredAccess
0x1800759b4  mov     rcx, rax; ProcessHandle
0x1800759b7  call    cs:__imp_OpenProcessToken
0x1800759be  nop     dword ptr [rax+rax+00h]
0x1800759c3  test    eax, eax
0x1800759c5  jnz     loc_180075871
0x1800759cb  call    cs:__imp_GetLastError
0x1800759d2  nop     dword ptr [rax+rax+00h]
0x1800759d7  test    eax, eax
0x1800759d9  jg      short loc_1800759EE
0x1800759db  call    cs:__imp_GetLastError
0x1800759e2  nop     dword ptr [rax+rax+00h]
0x1800759e7  mov     ebx, eax
0x1800759e9  jmp     loc_180075942
0x1800759ee  call    cs:__imp_GetLastError
0x1800759f5  nop     dword ptr [rax+rax+00h]
0x1800759fa  movzx   ebx, ax
0x1800759fd  or      ebx, 0C0070000h
0x180075a03  jmp     loc_180075942
0x180075a08  test    eax, eax
0x180075a0a  jle     loc_180075942
0x180075a10  jmp     short loc_1800759FA
0x180075a12  mov     ebx, 0C0000017h
0x180075a17  jmp     loc_180075942
0x180075a1c  call    cs:__imp_GetLastError
0x180075a23  nop     dword ptr [rax+rax+00h]
0x180075a28  test    eax, eax
0x180075a2a  jg      short loc_180075A3F
0x180075a2c  call    cs:__imp_GetLastError
0x180075a33  nop     dword ptr [rax+rax+00h]
0x180075a38  mov     ebx, eax
0x180075a3a  jmp     loc_180075933
0x180075a3f  call    cs:__imp_GetLastError
0x180075a46  nop     dword ptr [rax+rax+00h]
0x180075a4b  movzx   ebx, ax
0x180075a4e  or      ebx, 0C0070000h
0x180075a54  jmp     loc_180075933
```
