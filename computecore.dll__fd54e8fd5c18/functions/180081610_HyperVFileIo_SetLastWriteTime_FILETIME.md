# HyperVFileIo::SetLastWriteTime(_FILETIME)

- ea: `0x180081610`
- end: `0x180081717`
- name: `?SetLastWriteTime@HyperVFileIo@@UEAAXU_FILETIME@@@Z`
- size: `263`
- prototype: `void __fastcall(HyperVFileIo *__hidden this, struct _FILETIME)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800067c0`
- `0x18001587c`
- `0x18007e39c`
- `0x180080124`
- `0x180081610`
- `0x18008226c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800816cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800816cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800816ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800816ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800816a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800816a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008165f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008165f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800816a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800816a7`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180081651`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180081651`

## string_xrefs

- `0x1800816f7`: `onecore\vm\common\hypervstorage\hypervfileio.cpp`

## pseudocode

```c
void __fastcall HyperVFileIo::SetLastWriteTime(HyperVFileIo *this, FILETIME a2)
{
  DWORD LastError; // ebx
  const unsigned __int16 *v4; // rdx
  void *v5; // r8
  RTL_SRWLOCK *v6; // rcx
  unsigned int v7; // [rsp+20h] [rbp-38h]
  struct _GUID v8; // [rsp+30h] [rbp-28h] BYREF
  FILETIME LastWriteTime; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  LastWriteTime = a2;
  HyperVFileIo::EnsureFileIsConnected(this);
  if ( (*((_BYTE *)this + 144) & 0x20) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x759,
      (unsigned int)"onecore\\vm\\common\\hypervstorage\\hypervfileio.cpp",
      (const char *)0x800710DDLL,
      v7);
  if ( SetFileTime(*((HANDLE *)this + 9), 0, 0, &LastWriteTime) )
    LastError = 0;
  else
    LastError = GetLastError();
  v4 = (const unsigned __int16 *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) > 7u )
    v4 = *(const unsigned __int16 **)v4;
  v5 = (void *)*((_QWORD *)this + 9);
  v8 = *(struct _GUID *)((char *)this + 8);
  HyperVStorageTrace::HyperVFileIo_SetFileTime(&v8, v4, v5, LastWriteTime, LastError);
  if ( LastError )
    HvsThrowWin32Error(LastError);
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  *((_DWORD *)this + 8) = GetCurrentThreadId();
  v6 = (RTL_SRWLOCK *)((char *)this + 24);
  *((FILETIME *)this + 17) = LastWriteTime;
  if ( *((_DWORD *)this + 8) )
  {
    *((_DWORD *)this + 8) = 0;
    ReleaseSRWLockExclusive(v6);
  }
  else
  {
    ReleaseSRWLockShared(v6);
  }
}

```

## disassembly

```asm
0x180081610  mov     [rsp+arg_10], rbx
0x180081615  push    rdi
0x180081616  sub     rsp, 50h
0x18008161a  mov     rax, cs:__security_cookie
0x180081621  xor     rax, rsp
0x180081624  mov     [rsp+58h+var_10], rax
0x180081629  mov     rdi, rcx
0x18008162c  mov     qword ptr [rsp+58h+LastWriteTime.dwLowDateTime], rdx
0x180081631  call    ?EnsureFileIsConnected@HyperVFileIo@@AEAAXXZ; HyperVFileIo::EnsureFileIsConnected(void)
0x180081636  test    byte ptr [rdi+90h], 20h
0x18008163d  jnz     loc_1800816F2
0x180081643  mov     rcx, [rdi+48h]; hFile
0x180081647  lea     r9, [rsp+58h+LastWriteTime]; lpLastWriteTime
0x18008164c  xor     r8d, r8d; lpLastAccessTime
0x18008164f  xor     edx, edx; lpCreationTime
0x180081651  call    cs:__imp_SetFileTime
0x180081657  test    eax, eax
0x180081659  jz      short loc_18008165F
0x18008165b  xor     ebx, ebx
0x18008165d  jmp     short loc_180081667
0x18008165f  call    cs:__imp_GetLastError
0x180081665  mov     ebx, eax
0x180081667  lea     rdx, [rdi+28h]
0x18008166b  cmp     qword ptr [rdx+18h], 7
0x180081670  jbe     short loc_180081675
0x180081672  mov     rdx, [rdx]; unsigned __int16 *
0x180081675  movups  xmm0, xmmword ptr [rdi+8]
0x180081679  mov     r9, qword ptr [rsp+58h+LastWriteTime.dwLowDateTime]; struct _FILETIME
0x18008167e  lea     rcx, [rsp+58h+var_28]; struct _GUID *
0x180081683  mov     r8, [rdi+48h]; void *
0x180081687  movdqu  xmmword ptr [rsp+58h+var_28.Data1], xmm0
0x18008168d  mov     [rsp+58h+var_38], ebx; unsigned int
0x180081691  call    ?HyperVFileIo_SetFileTime@HyperVStorageTrace@@SAXU_GUID@@PEBGPEAXU_FILETIME@@K@Z; HyperVStorageTrace::HyperVFileIo_SetFileTime(_GUID,ushort const *,void *,_FILETIME,ulong)
0x180081696  test    ebx, ebx
0x180081698  jnz     short loc_18008170F
0x18008169a  lea     rbx, [rdi+18h]
0x18008169e  mov     rcx, rbx; SRWLock
0x1800816a1  call    cs:__imp_AcquireSRWLockExclusive
0x1800816a7  call    cs:__imp_GetCurrentThreadId
0x1800816ad  mov     [rbx+8], eax
0x1800816b0  mov     rcx, rbx; SRWLock
0x1800816b3  mov     rax, qword ptr [rsp+58h+LastWriteTime.dwLowDateTime]
0x1800816b8  mov     [rdi+88h], rax
0x1800816bf  cmp     dword ptr [rbx+8], 0
0x1800816c3  jz      short loc_1800816EA
0x1800816c5  mov     dword ptr [rbx+8], 0
0x1800816cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800816d2  mov     rcx, [rsp+58h+var_10]
0x1800816d7  xor     rcx, rsp; StackCookie
0x1800816da  call    __security_check_cookie
0x1800816df  mov     rbx, [rsp+58h+arg_10]
0x1800816e4  add     rsp, 50h
0x1800816e8  pop     rdi
0x1800816e9  retn
0x1800816ea  call    cs:__imp_ReleaseSRWLockShared
0x1800816f0  jmp     short loc_1800816D2
0x1800816f2  mov     rcx, [rsp+58h]; this
0x1800816f7  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\hypervstorage\\hyp"...
0x1800816fe  mov     r9d, 800710DDh; char *
0x180081704  mov     edx, 759h; void *
0x180081709  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008170f  mov     ecx, ebx; unsigned int
0x180081711  call    ?HvsThrowWin32Error@@YAXK@Z; HvsThrowWin32Error(ulong)
```
