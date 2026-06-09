# BufferWriter::CAsyncIO::Active(void)

- ea: `0x1800a492c`
- end: `0x1800a49a6`
- name: `?Active@CAsyncIO@BufferWriter@@QEAAKXZ`
- size: `122`
- prototype: `unsigned int __fastcall(BufferWriter::CAsyncIO *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800a4c74`
- `0x1800a5a00`

## callees

- `0x1800a492c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a498c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a498c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a4940`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a4940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4977`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800a4962`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800a4962`

## pseudocode

```c
__int64 __fastcall BufferWriter::CAsyncIO::Active(BufferWriter::CAsyncIO *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  HANDLE IoCompletionPort; // rax
  DWORD LastError; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_QWORD *)this + 1)
    || (IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u),
        (*((_QWORD *)this + 1) = IoCompletionPort) != 0) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  LeaveCriticalSection(v1);
  return LastError;
}

```

## disassembly

```asm
0x1800a492c  mov     [rsp+arg_0], rbx
0x1800a4931  push    rdi
0x1800a4932  sub     rsp, 20h
0x1800a4936  lea     rdi, [rcx+10h]
0x1800a493a  mov     rbx, rcx
0x1800a493d  mov     rcx, rdi; lpCriticalSection
0x1800a4940  call    cs:__imp_EnterCriticalSection
0x1800a4947  nop     dword ptr [rax+rax+00h]
0x1800a494c  cmp     qword ptr [rbx+8], 0
0x1800a4951  jnz     short loc_1800A4987
0x1800a4953  mov     r9d, 1; NumberOfConcurrentThreads
0x1800a4959  xor     r8d, r8d; CompletionKey
0x1800a495c  xor     edx, edx; ExistingCompletionPort
0x1800a495e  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1800a4962  call    cs:__imp_CreateIoCompletionPort
0x1800a4969  nop     dword ptr [rax+rax+00h]
0x1800a496e  mov     [rbx+8], rax
0x1800a4972  test    rax, rax
0x1800a4975  jnz     short loc_1800A4987
0x1800a4977  call    cs:__imp_GetLastError
0x1800a497e  nop     dword ptr [rax+rax+00h]
0x1800a4983  mov     ebx, eax
0x1800a4985  jmp     short loc_1800A4989
0x1800a4987  xor     ebx, ebx
0x1800a4989  mov     rcx, rdi; lpCriticalSection
0x1800a498c  call    cs:__imp_LeaveCriticalSection
0x1800a4993  nop     dword ptr [rax+rax+00h]
0x1800a4998  mov     eax, ebx
0x1800a499a  mov     rbx, [rsp+28h+arg_0]
0x1800a499f  add     rsp, 20h
0x1800a49a3  pop     rdi
0x1800a49a4  retn
```
