# UTSemReadWrite::GetWriteWaiterEvent(void)

- ea: `0x18007d218`
- end: `0x18007d2b3`
- name: `?GetWriteWaiterEvent@UTSemReadWrite@@AEAAPEAXXZ`
- size: `155`
- prototype: `void *__fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a280`
- `0x180012404`
- `0x18007d2bc`

## callees

- `0x18000792c`
- `0x18000fa40`
- `0x18007d218`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d23b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d23b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d249`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d298`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d298`

## string_xrefs

- `0x18007d26c`: `com\complus\src\shared\util\utsem.cpp`
- `0x18007d256`: `CreateSemaphore returned NULL in UTSemReadWrite::GetReadWaiterSemaphore`

## pseudocode

```c
void *__fastcall UTSemReadWrite::GetWriteWaiterEvent(UTSemReadWrite *this)
{
  HANDLE EventW; // rdi
  DWORD LastError; // eax
  unsigned __int16 v4; // r8
  unsigned int v5; // r9d
  const void *v7; // [rsp+28h] [rbp-60h]
  unsigned int v8; // [rsp+30h] [rbp-58h]
  int v9; // [rsp+38h] [rbp-50h]
  int v10; // [rsp+40h] [rbp-48h]
  _BYTE v11[16]; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int16 *v12; // [rsp+60h] [rbp-28h]
  int v13; // [rsp+78h] [rbp-10h]

  if ( !*((_QWORD *)this + 2) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      CErrorWin32::CErrorWin32(
        (CErrorWin32 *)v11,
        LastError,
        v4,
        v5,
        L"CreateSemaphore returned NULL in UTSemReadWrite::GetReadWaiterSemaphore",
        v7,
        v8,
        v9,
        v10);
      v13 = 1;
      CError::WriteToLog((CError *)v11, L"com\\complus\\src\\shared\\util\\utsem.cpp", 0x2A3u, v12);
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 2, (signed __int64)EventW, 0) )
      CloseHandle(EventW);
  }
  return (void *)*((_QWORD *)this + 2);
}

```

## disassembly

```asm
0x18007d218  mov     [rsp+arg_0], rbx
0x18007d21d  push    rdi
0x18007d21e  sub     rsp, 80h
0x18007d225  mov     rax, [rcx+10h]
0x18007d229  mov     rbx, rcx
0x18007d22c  test    rax, rax
0x18007d22f  jnz     short loc_18007D29E
0x18007d231  xor     r9d, r9d; lpName
0x18007d234  xor     r8d, r8d; bInitialState
0x18007d237  xor     edx, edx; bManualReset
0x18007d239  xor     ecx, ecx; lpEventAttributes
0x18007d23b  call    cs:__imp_CreateEventW
0x18007d241  mov     rdi, rax
0x18007d244  test    rax, rax
0x18007d247  jnz     short loc_18007D28B
0x18007d249  call    cs:__imp_GetLastError
0x18007d24f  mov     edx, eax; unsigned int
0x18007d251  lea     rcx, [rsp+88h+var_38]; this
0x18007d256  lea     rax, aCreatesemaphor; "CreateSemaphore returned NULL in UTSemR"...
0x18007d25d  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18007d262  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x18007d267  mov     r9, [rsp+88h+var_28]; unsigned __int16 *
0x18007d26c  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18007d273  mov     r8d, 2A3h; unsigned int
0x18007d279  mov     [rsp+88h+var_10], 1
0x18007d281  lea     rcx, [rsp+88h+var_38]; this
0x18007d286  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18007d28b  xor     eax, eax
0x18007d28d  lock cmpxchg [rbx+10h], rdi
0x18007d293  jz      short loc_18007D29E
0x18007d295  mov     rcx, rdi; hObject
0x18007d298  call    cs:__imp_CloseHandle
0x18007d29e  mov     rax, [rbx+10h]
0x18007d2a2  mov     rbx, [rsp+88h+arg_0]
0x18007d2aa  add     rsp, 80h
0x18007d2b1  pop     rdi
0x18007d2b2  retn
```
