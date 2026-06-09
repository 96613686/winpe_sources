# CThreadPoolManager::AssociateHandle(void *,unsigned __int64)

- ea: `0x18001f438`
- end: `0x18001f51b`
- name: `?AssociateHandle@CThreadPoolManager@@QEAAJPEAX_K@Z`
- size: `227`
- prototype: `int(CThreadPoolManager *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b5b84`
- `0x1800b6300`
- `0x1800b6700`

## callees

- `0x1800063b0`
- `0x18001f438`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4b0`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18001f4a5`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18001f4a5`

## string_xrefs

- `0x18001f478`: `com\complus\dtc\dtc\tipgw\commgr\src\threadpoolmanager.cpp`
- `0x18001f4d5`: `com\complus\dtc\dtc\tipgw\commgr\src\threadpoolmanager.cpp`
- `0x18001f4c9`: `Failed to associate a handle to TIP thread pool completion port, hr=%08x`
- `0x18001f44c`: `Associating a handle to TIP thread pool completion port`
- `0x18001f457`: `CThreadPoolManager::AssociateHandle`

## pseudocode

```c
__int64 __fastcall CThreadPoolManager::AssociateHandle(CThreadPoolManager *this, void *a2, ULONG_PTR a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+38h] [rbp-10h]

  TraceStringInline(
    10,
    4,
    L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
    177,
    L"CThreadPoolManager::AssociateHandle",
    0,
    L"Associating a handle to TIP thread pool completion port");
  if ( !CThreadPoolManager::m_fThreadPoolReady || !CThreadPoolManager::m_hCompletionPort )
    return 2147500037LL;
  if ( CreateIoCompletionPort(a2, CThreadPoolManager::m_hCompletionPort, a3, 0) )
    return 0;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  v8 = v6;
  TraceStringInline(
    10,
    1,
    L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
    193,
    L"CThreadPoolManager::AssociateHandle",
    0,
    L"Failed to associate a handle to TIP thread pool completion port, hr=%08x",
    v8);
  return v6;
}

```

## disassembly

```asm
0x18001f438  mov     r11, rsp
0x18001f43b  mov     [r11+8], rbx
0x18001f43f  mov     [r11+10h], rdi
0x18001f443  push    r14
0x18001f445  sub     rsp, 40h
0x18001f449  mov     rdi, rdx
0x18001f44c  lea     rax, aAssociatingAHa; "Associating a handle to TIP thread pool"...
0x18001f453  mov     [r11-18h], rax
0x18001f457  lea     r14, aCthreadpoolman_2; "CThreadPoolManager::AssociateHandle"
0x18001f45e  mov     edx, 4
0x18001f463  mov     qword ptr [r11-20h], 0
0x18001f46b  mov     rbx, r8
0x18001f46e  mov     [r11-28h], r14
0x18001f472  mov     r9d, 0B1h
0x18001f478  lea     r8, aComComplusDtcD_70; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x18001f47f  lea     ecx, [rdx+6]
0x18001f482  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f487  cmp     cs:?m_fThreadPoolReady@CThreadPoolManager@@0HA, 0; int CThreadPoolManager::m_fThreadPoolReady
0x18001f48e  jz      short loc_18001F505
0x18001f490  mov     rdx, cs:?m_hCompletionPort@CThreadPoolManager@@0PEAXEA; ExistingCompletionPort
0x18001f497  test    rdx, rdx
0x18001f49a  jz      short loc_18001F505
0x18001f49c  xor     r9d, r9d; NumberOfConcurrentThreads
0x18001f49f  mov     r8, rbx; CompletionKey
0x18001f4a2  mov     rcx, rdi; FileHandle
0x18001f4a5  call    cs:__imp_CreateIoCompletionPort
0x18001f4ab  test    rax, rax
0x18001f4ae  jnz     short loc_18001F501
0x18001f4b0  call    cs:__imp_GetLastError
0x18001f4b6  mov     ebx, eax
0x18001f4b8  test    eax, eax
0x18001f4ba  jle     short loc_18001F4C5
0x18001f4bc  movzx   ebx, ax
0x18001f4bf  or      ebx, 80070000h
0x18001f4c5  mov     [rsp+48h+var_10], ebx
0x18001f4c9  lea     rax, aFailedToAssoci; "Failed to associate a handle to TIP thr"...
0x18001f4d0  mov     [rsp+48h+var_18], rax
0x18001f4d5  lea     r8, aComComplusDtcD_70; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x18001f4dc  mov     edx, 1
0x18001f4e1  mov     [rsp+48h+var_20], 0
0x18001f4ea  mov     r9d, 0C1h
0x18001f4f0  mov     [rsp+48h+var_28], r14
0x18001f4f5  lea     ecx, [rdx+9]
0x18001f4f8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f4fd  mov     eax, ebx
0x18001f4ff  jmp     short loc_18001F50A
0x18001f501  xor     eax, eax
0x18001f503  jmp     short loc_18001F50A
0x18001f505  mov     eax, 80004005h
0x18001f50a  mov     rbx, [rsp+48h+arg_0]
0x18001f50f  mov     rdi, [rsp+48h+arg_8]
0x18001f514  add     rsp, 40h
0x18001f518  pop     r14
0x18001f51a  retn
```
