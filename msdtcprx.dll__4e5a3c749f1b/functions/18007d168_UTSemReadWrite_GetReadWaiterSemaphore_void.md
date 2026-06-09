# UTSemReadWrite::GetReadWaiterSemaphore(void)

- ea: `0x18007d168`
- end: `0x18007d212`
- name: `?GetReadWaiterSemaphore@UTSemReadWrite@@AEAAPEAXXZ`
- size: `170`
- prototype: `void *__fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a280`
- `0x18000ef28`

## callees

- `0x18000792c`
- `0x18000fa40`
- `0x18007d168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18007d19a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18007d19a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d1a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d1a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d1f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d1f7`

## string_xrefs

- `0x18007d1cb`: `com\complus\src\shared\util\utsem.cpp`
- `0x18007d1b5`: `CreateSemaphore returned NULL in UTSemReadWrite::GetReadWaiterSemaphore`

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
0x18007d168  mov     [rsp+arg_0], rbx
0x18007d16d  push    rdi
0x18007d16e  sub     rsp, 80h
0x18007d175  mov     rax, [rcx+8]
0x18007d179  mov     rbx, rcx
0x18007d17c  test    rax, rax
0x18007d17f  jnz     short loc_18007D1FD
0x18007d181  mov     dword ptr [rsp+88h+dwDesiredAccess], 1F0003h; void *
0x18007d189  xor     r9d, r9d; lpName
0x18007d18c  xor     edx, edx; lInitialCount
0x18007d18e  mov     [rsp+88h+dwFlags], eax; dwFlags
0x18007d192  xor     ecx, ecx; lpSemaphoreAttributes
0x18007d194  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18007d19a  call    cs:__imp_CreateSemaphoreExW
0x18007d1a0  mov     rdi, rax
0x18007d1a3  test    rax, rax
0x18007d1a6  jnz     short loc_18007D1EA
0x18007d1a8  call    cs:__imp_GetLastError
0x18007d1ae  mov     edx, eax; unsigned int
0x18007d1b0  lea     rcx, [rsp+88h+var_38]; this
0x18007d1b5  lea     rax, aCreatesemaphor; "CreateSemaphore returned NULL in UTSemR"...
0x18007d1bc  mov     qword ptr [rsp+88h+dwFlags], rax; unsigned __int16 *
0x18007d1c1  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x18007d1c6  mov     r9, [rsp+88h+var_28]; unsigned __int16 *
0x18007d1cb  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18007d1d2  mov     r8d, 27Eh; unsigned int
0x18007d1d8  mov     [rsp+88h+var_10], 1
0x18007d1e0  lea     rcx, [rsp+88h+var_38]; this
0x18007d1e5  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18007d1ea  xor     eax, eax
0x18007d1ec  lock cmpxchg [rbx+8], rdi
0x18007d1f2  jz      short loc_18007D1FD
0x18007d1f4  mov     rcx, rdi; hObject
0x18007d1f7  call    cs:__imp_CloseHandle
0x18007d1fd  mov     rax, [rbx+8]
0x18007d201  mov     rbx, [rsp+88h+arg_0]
0x18007d209  add     rsp, 80h
0x18007d210  pop     rdi
0x18007d211  retn
```
