# CFveApiBase::LibraryCleanup(void)

- ea: `0x180083da0`
- end: `0x180083e22`
- name: `?LibraryCleanup@CFveApiBase@@SAXXZ`
- size: `130`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180049dc0`

## callees

- `0x180042964`
- `0x18004b6ac`
- `0x180083da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180083dff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180083dff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180083e16`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180083daa`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180083daa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180083dc4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180083dc4`

## pseudocode

```c
void CFveApiBase::LibraryCleanup(void)
{
  TlsFree(CFveApiBase::_TlsIndex);
  if ( qword_1801746F8 )
  {
    BCryptCloseAlgorithmProvider(qword_1801746F8, 0);
    qword_1801746F8 = 0;
  }
  TpmApiShaUninitialize(&qword_1801746F0);
  TpmApiShaUninitialize(&qword_1801746E8);
  FveLibCleanup();
  DeleteCriticalSection(&CFveApiBase::_GlobalLock);
  DeleteCriticalSection(&g_TPMAPI_funcFamily_lock);
}

```

## disassembly

```asm
0x180083da0  sub     rsp, 28h
0x180083da4  mov     ecx, cs:?_TlsIndex@CFveApiBase@@1KA; dwTlsIndex
0x180083daa  call    cs:__imp_TlsFree
0x180083db1  nop     dword ptr [rax+rax+00h]
0x180083db6  mov     rcx, cs:qword_1801746F8; hAlgorithm
0x180083dbd  test    rcx, rcx
0x180083dc0  jz      short loc_180083DDB
0x180083dc2  xor     edx, edx; dwFlags
0x180083dc4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180083dcb  nop     dword ptr [rax+rax+00h]
0x180083dd0  mov     cs:qword_1801746F8, 0
0x180083ddb  lea     rcx, qword_1801746F0
0x180083de2  call    TpmApiShaUninitialize
0x180083de7  lea     rcx, qword_1801746E8
0x180083dee  call    TpmApiShaUninitialize
0x180083df3  call    FveLibCleanup
0x180083df8  lea     rcx, ?_GlobalLock@CFveApiBase@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180083dff  call    cs:__imp_DeleteCriticalSection
0x180083e06  nop     dword ptr [rax+rax+00h]
0x180083e0b  lea     rcx, ?g_TPMAPI_funcFamily_lock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_TPMAPI_funcFamily_lock
0x180083e12  add     rsp, 28h
0x180083e16  jmp     cs:__imp_DeleteCriticalSection
```
