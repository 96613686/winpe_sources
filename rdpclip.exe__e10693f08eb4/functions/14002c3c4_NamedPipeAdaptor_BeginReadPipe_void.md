# NamedPipeAdaptor::BeginReadPipe(void)

- ea: `0x14002c3c4`
- end: `0x14002c469`
- name: `?BeginReadPipe@NamedPipeAdaptor@@AEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(NamedPipeAdaptor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002d770`

## callees

- `0x140008168`
- `0x14002c3c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c409`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002c456`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002c456`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002c442`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002c442`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14002c401`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14002c401`

## string_xrefs

- `0x14002c42b`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::BeginReadPipe(NamedPipeAdaptor *this)
{
  BOOL File; // ebx
  DWORD LastError; // eax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *((_BYTE *)this + 336) )
    ++*((_DWORD *)this + 85);
  File = ReadFile(
           *((HANDLE *)this + 25),
           *((LPVOID *)this + 30),
           *((_DWORD *)this + 62) - *((_QWORD *)this + 30),
           0,
           (LPOVERLAPPED)((char *)this + 208));
  LastError = GetLastError();
  if ( !File && LastError != 997 && LastError != 234 )
  {
    if ( LastError != 109 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1A7,
               (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
               v4);
    AcquireSRWLockExclusive((PSRWLOCK)this + 7);
    *((_DWORD *)this + 48) = 4;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 7);
  }
  return 0;
}

```

## disassembly

```asm
0x14002c3c4  mov     [rsp+arg_0], rbx
0x14002c3c9  push    rdi
0x14002c3ca  sub     rsp, 30h
0x14002c3ce  cmp     byte ptr [rcx+150h], 0
0x14002c3d5  mov     rdi, rcx
0x14002c3d8  jz      short loc_14002C3E0
0x14002c3da  inc     dword ptr [rcx+154h]
0x14002c3e0  lea     rax, [rcx+0D0h]
0x14002c3e7  xor     r9d, r9d; lpNumberOfBytesRead
0x14002c3ea  mov     rdx, [rax+20h]; lpBuffer
0x14002c3ee  mov     r8d, [rax+28h]
0x14002c3f2  mov     rcx, [rcx+0C8h]; hFile
0x14002c3f9  sub     r8d, edx; nNumberOfBytesToRead
0x14002c3fc  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x14002c401  call    cs:__imp_ReadFile
0x14002c407  mov     ebx, eax
0x14002c409  call    cs:__imp_GetLastError
0x14002c40f  test    ebx, ebx
0x14002c411  jnz     short loc_14002C45C
0x14002c413  cmp     eax, 3E5h
0x14002c418  jz      short loc_14002C45C
0x14002c41a  cmp     eax, 0EAh
0x14002c41f  jz      short loc_14002C45C
0x14002c421  cmp     eax, 6Dh ; 'm'
0x14002c424  jz      short loc_14002C43E
0x14002c426  mov     rcx, [rsp+38h]; this
0x14002c42b  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002c432  mov     edx, 1A7h; void *
0x14002c437  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002c43c  jmp     short loc_14002C45E
0x14002c43e  lea     rcx, [rdi+38h]; SRWLock
0x14002c442  call    cs:__imp_AcquireSRWLockExclusive
0x14002c448  lea     rcx, [rdi+38h]; SRWLock
0x14002c44c  mov     dword ptr [rdi+0C0h], 4
0x14002c456  call    cs:__imp_ReleaseSRWLockExclusive
0x14002c45c  xor     eax, eax
0x14002c45e  mov     rbx, [rsp+38h+arg_0]
0x14002c463  add     rsp, 30h
0x14002c467  pop     rdi
0x14002c468  retn
```
