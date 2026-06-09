# UTSemReadWrite::GetReadWaiterSemaphore(void)

- ea: `0x1800319f8`
- end: `0x180031aa2`
- name: `?GetReadWaiterSemaphore@UTSemReadWrite@@AEAAPEAXXZ`
- size: `170`
- prototype: `void *__fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004d60`
- `0x180031cdc`

## callees

- `0x180009098`
- `0x18000b1e8`
- `0x1800319f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180031a2a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180031a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a38`

## string_xrefs

- `0x180031a5b`: `com\complus\src\shared\util\utsem.cpp`
- `0x180031a45`: `CreateSemaphore returned NULL in UTSemReadWrite::GetReadWaiterSemaphore`

## pseudocode

```c
void *__fastcall UTSemReadWrite::GetReadWaiterSemaphore(UTSemReadWrite *this)
{
  HANDLE Semaphore; // rdi
  DWORD LastError; // eax
  unsigned __int16 v4; // r8
  unsigned int v5; // r9d
  const void *dwDesiredAccess; // [rsp+28h] [rbp-60h]
  unsigned int v8; // [rsp+30h] [rbp-58h]
  int v9; // [rsp+38h] [rbp-50h]
  int v10; // [rsp+40h] [rbp-48h]
  _BYTE v11[16]; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int16 *v12; // [rsp+60h] [rbp-28h]
  int v13; // [rsp+78h] [rbp-10h]

  if ( !*((_QWORD *)this + 1) )
  {
    Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
    if ( !Semaphore )
    {
      LastError = GetLastError();
      CErrorWin32::CErrorWin32(
        (CErrorWin32 *)v11,
        LastError,
        v4,
        v5,
        L"CreateSemaphore returned NULL in UTSemReadWrite::GetReadWaiterSemaphore",
        dwDesiredAccess,
        v8,
        v9,
        v10);
      v13 = 1;
      CError::WriteToLog((CError *)v11, L"com\\complus\\src\\shared\\util\\utsem.cpp", 0x27Eu, v12);
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, (signed __int64)Semaphore, 0) )
      CloseHandle(Semaphore);
  }
  return (void *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x1800319f8  mov     [rsp+arg_0], rbx
0x1800319fd  push    rdi
0x1800319fe  sub     rsp, 80h
0x180031a05  mov     rax, [rcx+8]
0x180031a09  mov     rbx, rcx
0x180031a0c  test    rax, rax
0x180031a0f  jnz     short loc_180031A8D
0x180031a11  mov     dword ptr [rsp+88h+dwDesiredAccess], 1F0003h; void *
0x180031a19  xor     r9d, r9d; lpName
0x180031a1c  xor     edx, edx; lInitialCount
0x180031a1e  mov     [rsp+88h+dwFlags], eax; dwFlags
0x180031a22  xor     ecx, ecx; lpSemaphoreAttributes
0x180031a24  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180031a2a  call    cs:__imp_CreateSemaphoreExW
0x180031a30  mov     rdi, rax
0x180031a33  test    rax, rax
0x180031a36  jnz     short loc_180031A7A
0x180031a38  call    cs:__imp_GetLastError
0x180031a3e  mov     edx, eax; unsigned int
0x180031a40  lea     rcx, [rsp+88h+var_38]; this
0x180031a45  lea     rax, aCreatesemaphor; "CreateSemaphore returned NULL in UTSemR"...
0x180031a4c  mov     qword ptr [rsp+88h+dwFlags], rax; unsigned __int16 *
0x180031a51  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x180031a56  mov     r9, [rsp+88h+var_28]; unsigned __int16 *
0x180031a5b  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180031a62  mov     r8d, 27Eh; unsigned int
0x180031a68  mov     [rsp+88h+var_10], 1
0x180031a70  lea     rcx, [rsp+88h+var_38]; this
0x180031a75  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180031a7a  xor     eax, eax
0x180031a7c  lock cmpxchg [rbx+8], rdi
0x180031a82  jz      short loc_180031A8D
0x180031a84  mov     rcx, rdi; hObject
0x180031a87  call    cs:__imp_CloseHandle
0x180031a8d  mov     rax, [rbx+8]
0x180031a91  mov     rbx, [rsp+88h+arg_0]
0x180031a99  add     rsp, 80h
0x180031aa0  pop     rdi
0x180031aa1  retn
```
