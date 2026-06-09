# GetProcessIntegrityLevel(void *,ulong *)

- ea: `0x180025250`
- end: `0x1800252d9`
- name: `?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z`
- size: `137`
- prototype: `__int64 __fastcall(void *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024b80`

## callees

- `0x180025250`
- `0x1800252e0`
- `0x180025c18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025274`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025274`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025285`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025285`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800252b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800252b6`

## pseudocode

```c
__int64 __fastcall GetProcessIntegrityLevel(void *a1, unsigned int *a2)
{
  void *v3; // rdi
  HANDLE CurrentProcess; // rax
  unsigned int v5; // ebx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  *a2 = 0x2000;
  v3 = a1;
  if ( a1 )
  {
    TokenHandle = a1;
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      return (unsigned int)HRESULTFromLastErrorError();
    a1 = TokenHandle;
  }
  v5 = TokenIntegrityRIDFromToken(a1, a2);
  if ( v5 == -1073741821 )
    v5 = 1;
  if ( !v3 )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x180025250  mov     [rsp+arg_8], rbx
0x180025255  push    rdi
0x180025256  sub     rsp, 20h
0x18002525a  mov     [rsp+28h+TokenHandle], 0
0x180025263  mov     rbx, rdx
0x180025266  mov     dword ptr [rdx], 2000h
0x18002526c  mov     rdi, rcx
0x18002526f  test    rcx, rcx
0x180025272  jnz     short loc_1800252D2
0x180025274  call    cs:__imp_GetCurrentProcess
0x18002527a  mov     rcx, rax; ProcessHandle
0x18002527d  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180025282  lea     edx, [rdi+8]; DesiredAccess
0x180025285  call    cs:__imp_OpenProcessToken
0x18002528b  test    eax, eax
0x18002528d  jz      short loc_1800252C9
0x18002528f  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180025294  mov     rdx, rbx
0x180025297  call    _TokenIntegrityRIDFromToken
0x18002529c  mov     ebx, eax
0x18002529e  mov     eax, 1
0x1800252a3  cmp     ebx, 0C0000003h
0x1800252a9  cmovz   ebx, eax
0x1800252ac  test    rdi, rdi
0x1800252af  jnz     short loc_1800252BC
0x1800252b1  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800252b6  call    cs:__imp_CloseHandle
0x1800252bc  mov     eax, ebx
0x1800252be  mov     rbx, [rsp+28h+arg_8]
0x1800252c3  add     rsp, 20h
0x1800252c7  pop     rdi
0x1800252c8  retn
0x1800252c9  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x1800252ce  mov     ebx, eax
0x1800252d0  jmp     short loc_1800252BC
0x1800252d2  mov     [rsp+28h+TokenHandle], rcx
0x1800252d7  jmp     short loc_180025294
```
