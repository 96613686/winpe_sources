# Container::Manager::Core::Details::ContainerObject::TransitionToDeployedState(void)

- ea: `0x1800b7900`
- end: `0x1800b7aa6`
- name: `?TransitionToDeployedState@ContainerObject@Details@Core@Manager@Container@@AEAAJXZ`
- size: `422`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ContainerObject *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800a8be0`

## callees

- `0x18000da68`
- `0x1800b7900`
- `0x1800b7b58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7a58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7a58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b7a8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b7a8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7a64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7a64`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b794e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b79c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b7a1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b794e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b79c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b7a1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b79e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7a42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b79e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b7a42`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::TransitionToDeployedState(RTL_SRWLOCK *this)
{
  PVOID Ptr; // rbx
  const WCHAR *v3; // rcx
  HANDLE FileW; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  const WCHAR *v8; // rcx
  HANDLE v9; // rax
  HANDLE v10; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( LODWORD(this[11].Ptr) == 1 )
  {
    Ptr = this[158].Ptr;
    v3 = (const WCHAR *)*((_QWORD *)Ptr + 100);
    if ( *((const WCHAR **)Ptr + 101) != v3 )
    {
      FileW = CreateFileW(v3, 0, 0, 0, 2u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        v6 = 13340;
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)v6,
                 (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                 v5);
      }
      if ( FileW )
        CloseHandle(FileW);
    }
    v8 = (const WCHAR *)*((_QWORD *)Ptr + 104);
    if ( *((const WCHAR **)Ptr + 105) != v8 )
    {
      v9 = CreateFileW(v8, 0, 0, 0, 2u, 0x80u, 0);
      if ( v9 == (HANDLE)-1LL )
      {
        v6 = 13354;
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)v6,
                 (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                 v5);
      }
      if ( v9 )
        CloseHandle(v9);
    }
    if ( *((_BYTE *)Ptr + 896) )
    {
      v10 = CreateFileW(*((LPCWSTR *)Ptr + 108), 0, 0, 0, 2u, 0x80u, 0);
      if ( v10 == (HANDLE)-1LL )
      {
        v6 = 13368;
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)v6,
                 (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                 v5);
      }
      if ( v10 )
        CloseHandle(v10);
    }
  }
  AcquireSRWLockExclusive(this + 57);
  LODWORD(this[58].Ptr) = GetCurrentThreadId();
  Container::Manager::Core::Details::ContainerObject::TransitionToLogicalState((__int64)this, 2, 0);
  LODWORD(this[58].Ptr) = 0;
  ReleaseSRWLockExclusive(this + 57);
  return 0;
}

```

## disassembly

```asm
0x1800b7900  mov     rax, rsp
0x1800b7903  mov     [rax+8], rbx
0x1800b7907  push    rdi
0x1800b7908  sub     rsp, 40h
0x1800b790c  cmp     dword ptr [rcx+58h], 1
0x1800b7910  mov     rdi, rcx
0x1800b7913  jnz     loc_1800B7A4E
0x1800b7919  mov     rbx, [rcx+4F0h]
0x1800b7920  mov     rcx, [rbx+320h]; lpFileName
0x1800b7927  cmp     [rbx+328h], rcx
0x1800b792e  jz      short loc_1800B798F
0x1800b7930  mov     qword ptr [rax-18h], 0
0x1800b7938  xor     r9d, r9d; lpSecurityAttributes
0x1800b793b  mov     dword ptr [rax-20h], 80h
0x1800b7942  xor     r8d, r8d; dwShareMode
0x1800b7945  xor     edx, edx; dwDesiredAccess
0x1800b7947  mov     dword ptr [rax-28h], 2
0x1800b794e  call    cs:__imp_CreateFileW
0x1800b7955  nop     dword ptr [rax+rax+00h]
0x1800b795a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b795e  jnz     short loc_1800B797B
0x1800b7960  mov     edx, 341Ch; void *
0x1800b7965  mov     rcx, [rsp+48h]; this
0x1800b796a  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b7971  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b7976  jmp     loc_1800B7A9A
0x1800b797b  test    rax, rax
0x1800b797e  jz      short loc_1800B798F
0x1800b7980  mov     rcx, rax; hObject
0x1800b7983  call    cs:__imp_CloseHandle
0x1800b798a  nop     dword ptr [rax+rax+00h]
0x1800b798f  mov     rcx, [rbx+340h]; lpFileName
0x1800b7996  cmp     [rbx+348h], rcx
0x1800b799d  jz      short loc_1800B79ED
0x1800b799f  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800b79a8  xor     r9d, r9d; lpSecurityAttributes
0x1800b79ab  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b79b3  xor     r8d, r8d; dwShareMode
0x1800b79b6  xor     edx, edx; dwDesiredAccess
0x1800b79b8  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x1800b79c0  call    cs:__imp_CreateFileW
0x1800b79c7  nop     dword ptr [rax+rax+00h]
0x1800b79cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b79d0  jnz     short loc_1800B79D9
0x1800b79d2  mov     edx, 342Ah
0x1800b79d7  jmp     short loc_1800B7965
0x1800b79d9  test    rax, rax
0x1800b79dc  jz      short loc_1800B79ED
0x1800b79de  mov     rcx, rax; hObject
0x1800b79e1  call    cs:__imp_CloseHandle
0x1800b79e8  nop     dword ptr [rax+rax+00h]
0x1800b79ed  cmp     byte ptr [rbx+380h], 0
0x1800b79f4  jz      short loc_1800B7A4E
0x1800b79f6  mov     rcx, [rbx+360h]; lpFileName
0x1800b79fd  xor     r9d, r9d; lpSecurityAttributes
0x1800b7a00  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800b7a09  xor     r8d, r8d; dwShareMode
0x1800b7a0c  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b7a14  xor     edx, edx; dwDesiredAccess
0x1800b7a16  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x1800b7a1e  call    cs:__imp_CreateFileW
0x1800b7a25  nop     dword ptr [rax+rax+00h]
0x1800b7a2a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b7a2e  jnz     short loc_1800B7A3A
0x1800b7a30  mov     edx, 3438h
0x1800b7a35  jmp     loc_1800B7965
0x1800b7a3a  test    rax, rax
0x1800b7a3d  jz      short loc_1800B7A4E
0x1800b7a3f  mov     rcx, rax; hObject
0x1800b7a42  call    cs:__imp_CloseHandle
0x1800b7a49  nop     dword ptr [rax+rax+00h]
0x1800b7a4e  lea     rbx, [rdi+1C8h]
0x1800b7a55  mov     rcx, rbx; SRWLock
0x1800b7a58  call    cs:__imp_AcquireSRWLockExclusive
0x1800b7a5f  nop     dword ptr [rax+rax+00h]
0x1800b7a64  call    cs:__imp_GetCurrentThreadId
0x1800b7a6b  nop     dword ptr [rax+rax+00h]
0x1800b7a70  xor     r8d, r8d
0x1800b7a73  mov     rcx, rdi
0x1800b7a76  mov     [rbx+8], eax
0x1800b7a79  lea     edx, [r8+2]
0x1800b7a7d  call    ?TransitionToLogicalState@ContainerObject@Details@Core@Manager@Container@@AEAAXW4ContainerLogicalState@2345@W4TransitionToLogicalStateFlags@12345@@Z; Container::Manager::Core::Details::ContainerObject::TransitionToLogicalState(Container::Manager::Core::Details::ContainerLogicalState,Container::Manager::Core::Details::ContainerObject::TransitionToLogicalStateFlags)
0x1800b7a82  mov     rcx, rbx; SRWLock
0x1800b7a85  mov     dword ptr [rbx+8], 0
0x1800b7a8c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b7a93  nop     dword ptr [rax+rax+00h]
0x1800b7a98  xor     eax, eax
0x1800b7a9a  mov     rbx, [rsp+48h+arg_0]
0x1800b7a9f  add     rsp, 40h
0x1800b7aa3  pop     rdi
0x1800b7aa4  retn
```
