# UTSemReadWrite::GetWriteWaiterEvent(void)

- ea: `0x180031aa8`
- end: `0x180031b43`
- name: `?GetWriteWaiterEvent@UTSemReadWrite@@AEAAPEAXXZ`
- size: `155`
- prototype: `void *__fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004f48`
- `0x180031b4c`
- `0x180031cdc`

## callees

- `0x180009098`
- `0x18000b1e8`
- `0x180031aa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031acb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031acb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031b28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ad9`

## string_xrefs

- `0x180031afc`: `com\complus\src\shared\util\utsem.cpp`
- `0x180031ae6`: `CreateSemaphore returned NULL in UTSemReadWrite::GetReadWaiterSemaphore`

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
0x180031aa8  mov     [rsp+arg_0], rbx
0x180031aad  push    rdi
0x180031aae  sub     rsp, 80h
0x180031ab5  mov     rax, [rcx+10h]
0x180031ab9  mov     rbx, rcx
0x180031abc  test    rax, rax
0x180031abf  jnz     short loc_180031B2E
0x180031ac1  xor     r9d, r9d; lpName
0x180031ac4  xor     r8d, r8d; bInitialState
0x180031ac7  xor     edx, edx; bManualReset
0x180031ac9  xor     ecx, ecx; lpEventAttributes
0x180031acb  call    cs:__imp_CreateEventW
0x180031ad1  mov     rdi, rax
0x180031ad4  test    rax, rax
0x180031ad7  jnz     short loc_180031B1B
0x180031ad9  call    cs:__imp_GetLastError
0x180031adf  mov     edx, eax; unsigned int
0x180031ae1  lea     rcx, [rsp+88h+var_38]; this
0x180031ae6  lea     rax, aCreatesemaphor; "CreateSemaphore returned NULL in UTSemR"...
0x180031aed  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x180031af2  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x180031af7  mov     r9, [rsp+88h+var_28]; unsigned __int16 *
0x180031afc  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180031b03  mov     r8d, 2A3h; unsigned int
0x180031b09  mov     [rsp+88h+var_10], 1
0x180031b11  lea     rcx, [rsp+88h+var_38]; this
0x180031b16  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180031b1b  xor     eax, eax
0x180031b1d  lock cmpxchg [rbx+10h], rdi
0x180031b23  jz      short loc_180031B2E
0x180031b25  mov     rcx, rdi; hObject
0x180031b28  call    cs:__imp_CloseHandle
0x180031b2e  mov     rax, [rbx+10h]
0x180031b32  mov     rbx, [rsp+88h+arg_0]
0x180031b3a  add     rsp, 80h
0x180031b41  pop     rdi
0x180031b42  retn
```
