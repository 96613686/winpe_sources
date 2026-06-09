# HyperVFileIo::GetLastWriteTime(void)

- ea: `0x18007e880`
- end: `0x18007ea26`
- name: `?GetLastWriteTime@HyperVFileIo@@UEBA?AU_FILETIME@@XZ`
- size: `422`
- prototype: `struct _FILETIME(HyperVFileIo *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180007dbc`
- `0x180007e24`
- `0x180066284`
- `0x18007e880`
- `0x18007f66c`
- `0x180081f2c`
- `0x180082140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007e9b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007e9b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007e9d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007e9d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e9da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e9da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007e909`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007e909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e8b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e90f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e90f`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18007e8a6`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18007e8a6`

## string_xrefs

- `0x18007e8dc`: `HyperVFileIo::GetLastWriteTime`

## pseudocode

```c
struct _FILETIME __fastcall HyperVFileIo::GetLastWriteTime(HyperVFileIo *this, struct _FILETIME *a2)
{
  DWORD LastError; // r14d
  struct _FILETIME v5; // rcx
  const unsigned __int16 **v6; // rbx
  const unsigned __int16 *v7; // r8
  void *v8; // r9
  char *v9; // rbx
  int IsDebugTraceEnabled; // r15d
  _DWORD *v11; // rcx
  bool v12; // bp
  struct _GUID v14; // [rsp+30h] [rbp-48h] BYREF

  *a2 = 0;
  if ( GetFileTime(*((HANDLE *)this + 9), 0, 0, a2) )
    LastError = 0;
  else
    LastError = GetLastError();
  v5 = *a2;
  v6 = (const unsigned __int16 **)((char *)this + 40);
  if ( *((_QWORD *)this + 8) <= 7u )
    v7 = (const unsigned __int16 *)((char *)this + 40);
  else
    v7 = *v6;
  v8 = (void *)*((_QWORD *)this + 9);
  v14 = *(struct _GUID *)((char *)this + 8);
  HyperVStorageTrace::HyperVFileIo_GetFileTime(&v14, L"HyperVFileIo::GetLastWriteTime", v7, v8, v5, LastError);
  if ( LastError )
  {
    if ( *((_QWORD *)this + 9) != -1 )
    {
      IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0x8000u);
      v11 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
      v12 = v11 && *v11;
      if ( IsDebugTraceEnabled || v12 )
      {
        if ( dword_1800E4860 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                           + (unsigned int)tls_index)
                                         + 16LL) )
        {
          Init_thread_header(&dword_1800E4860);
          if ( dword_1800E4860 == -1 )
          {
            byte_1800E235C = IsDebugTraceEnabled != 0;
            byte_1800E235D = v12;
            Init_thread_footer(&dword_1800E4860);
          }
        }
        if ( *((_QWORD *)this + 8) > 7u )
          v6 = (const unsigned __int16 **)*v6;
        HvsDebugTraceInternal(0x8000u, (const struct HvsDebugTraceParameters *)&off_1800E2348, v6, LastError);
      }
    }
    v9 = (char *)this + 24;
    AcquireSRWLockShared((PSRWLOCK)this + 3);
    *a2 = *(struct _FILETIME *)((char *)this + 136);
  }
  else
  {
    v9 = (char *)this + 24;
    AcquireSRWLockExclusive((PSRWLOCK)this + 3);
    *((_DWORD *)this + 8) = GetCurrentThreadId();
    *((struct _FILETIME *)this + 17) = *a2;
  }
  if ( *((_DWORD *)v9 + 2) )
  {
    *((_DWORD *)v9 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v9);
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v9);
  }
  return (struct _FILETIME)a2;
}

```

## disassembly

```asm
0x18007e880  push    rbx
0x18007e882  push    rbp
0x18007e883  push    rsi
0x18007e884  push    rdi
0x18007e885  push    r12
0x18007e887  push    r14
0x18007e889  push    r15
0x18007e88b  sub     rsp, 40h
0x18007e88f  xor     eax, eax
0x18007e891  mov     rsi, rdx
0x18007e894  mov     [rdx], rax
0x18007e897  mov     rdi, rcx
0x18007e89a  mov     rcx, [rcx+48h]; hFile
0x18007e89e  mov     r9, rdx; lpLastWriteTime
0x18007e8a1  xor     edx, edx; lpCreationTime
0x18007e8a3  xor     r8d, r8d; lpLastAccessTime
0x18007e8a6  call    cs:__imp_GetFileTime
0x18007e8ac  test    eax, eax
0x18007e8ae  jz      short loc_18007E8B5
0x18007e8b0  xor     r14d, r14d
0x18007e8b3  jmp     short loc_18007E8BE
0x18007e8b5  call    cs:__imp_GetLastError
0x18007e8bb  mov     r14d, eax
0x18007e8be  mov     rcx, [rsi]
0x18007e8c1  lea     rbx, [rdi+28h]
0x18007e8c5  cmp     qword ptr [rbx+18h], 7
0x18007e8ca  jbe     short loc_18007E8D1
0x18007e8cc  mov     r8, [rbx]
0x18007e8cf  jmp     short loc_18007E8D4
0x18007e8d1  mov     r8, rbx; unsigned __int16 *
0x18007e8d4  movups  xmm0, xmmword ptr [rdi+8]
0x18007e8d8  mov     r9, [rdi+48h]; void *
0x18007e8dc  lea     rdx, aHypervfileioGe; "HyperVFileIo::GetLastWriteTime"
0x18007e8e3  mov     [rsp+78h+var_50], r14d; unsigned int
0x18007e8e8  mov     qword ptr [rsp+78h+var_58.dwLowDateTime], rcx; struct _FILETIME
0x18007e8ed  lea     rcx, [rsp+78h+var_48]; struct _GUID *
0x18007e8f2  movdqu  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x18007e8f8  call    ?HyperVFileIo_GetFileTime@HyperVStorageTrace@@SAXU_GUID@@PEBG1PEAXU_FILETIME@@K@Z; HyperVStorageTrace::HyperVFileIo_GetFileTime(_GUID,ushort const *,ushort const *,void *,_FILETIME,ulong)
0x18007e8fd  test    r14d, r14d
0x18007e900  jnz     short loc_18007E927
0x18007e902  lea     rbx, [rdi+18h]
0x18007e906  mov     rcx, rbx; SRWLock
0x18007e909  call    cs:__imp_AcquireSRWLockExclusive
0x18007e90f  call    cs:__imp_GetCurrentThreadId
0x18007e915  mov     [rbx+8], eax
0x18007e918  mov     rax, [rsi]
0x18007e91b  mov     [rdi+88h], rax
0x18007e922  jmp     loc_18007E9C2
0x18007e927  cmp     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x18007e92c  jz      short loc_18007E9AB
0x18007e92e  mov     ecx, 8000h; unsigned __int16
0x18007e933  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x18007e938  test    eax, eax
0x18007e93a  mov     r15d, eax
0x18007e93d  setnz   r12b
0x18007e941  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18007e946  mov     rcx, [rax+8]
0x18007e94a  test    rcx, rcx
0x18007e94d  jz      short loc_18007E95A
0x18007e94f  mov     ecx, [rcx]
0x18007e951  test    ecx, ecx
0x18007e953  jz      short loc_18007E95A
0x18007e955  mov     bpl, 1
0x18007e958  jmp     short loc_18007E95D
0x18007e95a  xor     bpl, bpl
0x18007e95d  test    r15d, r15d
0x18007e960  jnz     short loc_18007E967
0x18007e962  test    bpl, bpl
0x18007e965  jz      short loc_18007E9AB
0x18007e967  mov     ecx, cs:_tls_index
0x18007e96d  mov     rax, gs:58h
0x18007e976  mov     edx, 10h
0x18007e97b  mov     rax, [rax+rcx*8]
0x18007e97f  mov     eax, [rdx+rax]
0x18007e982  cmp     cs:dword_1800E4860, eax
0x18007e988  jg      short loc_18007E9F2
0x18007e98a  cmp     qword ptr [rbx+18h], 7
0x18007e98f  jbe     short loc_18007E994
0x18007e991  mov     rbx, [rbx]
0x18007e994  mov     r9d, r14d
0x18007e997  lea     rdx, off_1800E2348; struct HvsDebugTraceParameters *
0x18007e99e  mov     r8, rbx
0x18007e9a1  mov     ecx, 8000h; unsigned int
0x18007e9a6  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x18007e9ab  lea     rbx, [rdi+18h]
0x18007e9af  mov     rcx, rbx; SRWLock
0x18007e9b2  call    cs:__imp_AcquireSRWLockShared
0x18007e9b8  mov     rax, [rdi+88h]
0x18007e9bf  mov     [rsi], rax
0x18007e9c2  cmp     dword ptr [rbx+8], 0
0x18007e9c6  mov     rcx, rbx; SRWLock
0x18007e9c9  jz      short loc_18007E9DA
0x18007e9cb  mov     dword ptr [rbx+8], 0
0x18007e9d2  call    cs:__imp_ReleaseSRWLockExclusive
0x18007e9d8  jmp     short loc_18007E9E0
0x18007e9da  call    cs:__imp_ReleaseSRWLockShared
0x18007e9e0  mov     rax, rsi
0x18007e9e3  add     rsp, 40h
0x18007e9e7  pop     r15
0x18007e9e9  pop     r14
0x18007e9eb  pop     r12
0x18007e9ed  pop     rdi
0x18007e9ee  pop     rsi
0x18007e9ef  pop     rbp
0x18007e9f0  pop     rbx
0x18007e9f1  retn
0x18007e9f2  lea     rcx, dword_1800E4860
0x18007e9f9  call    _Init_thread_header
0x18007e9fe  cmp     cs:dword_1800E4860, 0FFFFFFFFh
0x18007ea05  jnz     short loc_18007E98A
0x18007ea07  lea     rcx, dword_1800E4860
0x18007ea0e  mov     cs:byte_1800E235C, r12b
0x18007ea15  mov     cs:byte_1800E235D, bpl
0x18007ea1c  call    _Init_thread_footer
0x18007ea21  jmp     loc_18007E98A
```
