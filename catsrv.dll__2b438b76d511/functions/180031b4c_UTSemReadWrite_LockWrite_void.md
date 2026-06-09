# UTSemReadWrite::LockWrite(void)

- ea: `0x180031b4c`
- end: `0x180031cd6`
- name: `?LockWrite@UTSemReadWrite@@QEAAXXZ`
- size: `394`
- prototype: `void __fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `28`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d8c0`
- `0x18000dc28`
- `0x180018620`
- `0x18001a7e0`
- `0x18001b550`
- `0x18001be80`
- `0x18001cd30`
- `0x18001d660`
- `0x18001fd60`
- `0x1800232d0`
- `0x180023460`
- `0x180023610`
- `0x1800237a0`
- `0x180023920`
- `0x1800241f0`
- `0x180024d30`
- `0x180024ee0`
- `0x180025050`
- `0x180025180`
- `0x1800252b0`
- `0x180025390`
- `0x180026170`
- `0x1800262a0`
- `0x180026590`
- `0x1800272d0`
- `0x180028d90`
- `0x180028ec0`
- `0x1800291c0`

## callees

- `0x180009098`
- `0x18000b1e8`
- `0x180031aa8`
- `0x180031b4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031bce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bd8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031b9c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031b9c`

## string_xrefs

- `0x180031bf9`: `com\complus\src\shared\util\utsem.cpp`
- `0x180031c40`: `com\complus\src\shared\util\utsem.cpp`
- `0x180031c95`: `com\complus\src\shared\util\utsem.cpp`
- `0x180031be4`: `WaitForSingleObject failed in UTSemReadWrite:LockWrite`
- `0x180031c28`: `Problem with Reader info in UTSemReadWrite::LockWrite`
- `0x180031c7d`: `Problem with Writer info in UTSemReadWrite::LockWrite`

## pseudocode

```c
void __fastcall UTSemReadWrite::LockWrite(UTSemReadWrite *this)
{
  unsigned int v1; // edi
  signed __int32 v3; // edx
  unsigned int v4; // eax
  void *v5; // rax
  DWORD LastError; // eax
  unsigned __int16 v7; // r8
  unsigned int v8; // r9d
  const void *v9; // [rsp+28h] [rbp-31h]
  unsigned int v10; // [rsp+30h] [rbp-29h]
  int v11; // [rsp+38h] [rbp-21h]
  int v12; // [rsp+40h] [rbp-19h]
  int v13; // [rsp+50h] [rbp-9h] BYREF
  __int16 v14; // [rsp+54h] [rbp-5h]
  int v15; // [rsp+58h] [rbp-1h]
  unsigned __int16 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  __int64 v18; // [rsp+70h] [rbp+17h]
  int v19; // [rsp+78h] [rbp+1Fh]
  int v20; // [rsp+7Ch] [rbp+23h]

  v1 = 0;
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v3 = *((_DWORD *)this + 1);
        if ( v3 )
          break;
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 1, 1024, 0) )
          goto LABEL_11;
      }
      if ( (v3 & 0xFFC00000) != 0xFFC00000 )
        break;
      Sleep(0x3E8u);
    }
    v4 = v1++;
  }
  while ( v4 < *(_DWORD *)this
       || v3 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v3 + 0x400000, v3) );
  v5 = UTSemReadWrite::GetWriteWaiterEvent(this);
  if ( WaitForSingleObject(v5, 0xFFFFFFFF) == -1 )
  {
    LastError = GetLastError();
    CErrorWin32::CErrorWin32(
      (CErrorWin32 *)&v13,
      LastError,
      v7,
      v8,
      L"WaitForSingleObject failed in UTSemReadWrite:LockWrite",
      v9,
      v10,
      v11,
      v12);
    v19 = 1;
    CError::WriteToLog((CError *)&v13, L"com\\complus\\src\\shared\\util\\utsem.cpp", 0x1ADu, v16);
  }
LABEL_11:
  if ( (*((_DWORD *)this + 1) & 0x3FF) != 0 )
  {
    v13 = 0;
    v16 = L"Problem with Reader info in UTSemReadWrite::LockWrite";
    v14 = 21;
    v15 = -1073606063;
    v17 = 0;
    v18 = 0;
    v20 = 1;
    v19 = 1;
    CError::WriteToLog(
      (CError *)&v13,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x1B8u,
      L"Problem with Reader info in UTSemReadWrite::LockWrite");
  }
  if ( (*((_DWORD *)this + 1) & 0xC00) != 0x400 )
  {
    v13 = 0;
    v16 = L"Problem with Writer info in UTSemReadWrite::LockWrite";
    v14 = 21;
    v15 = -1073606063;
    v17 = 0;
    v18 = 0;
    v20 = 1;
    v19 = 1;
    CError::WriteToLog(
      (CError *)&v13,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x1BAu,
      L"Problem with Writer info in UTSemReadWrite::LockWrite");
  }
}

```

## disassembly

```asm
0x180031b4c  push    rbp
0x180031b4e  push    rbx
0x180031b4f  push    rdi
0x180031b50  push    r13
0x180031b52  push    r14
0x180031b54  push    r15
0x180031b56  lea     rbp, [rsp-2Fh]
0x180031b5b  sub     rsp, 88h
0x180031b62  xor     edi, edi
0x180031b64  mov     rbx, rcx
0x180031b67  mov     r13d, 400h
0x180031b6d  mov     r15d, 0FFC00000h
0x180031b73  lea     r14d, [rdi+1]
0x180031b77  mov     edx, [rbx+4]
0x180031b7a  test    edx, edx
0x180031b7c  jnz     short loc_180031B8D
0x180031b7e  xor     eax, eax
0x180031b80  lock cmpxchg [rbx+4], r13d
0x180031b86  jnz     short loc_180031B77
0x180031b88  jmp     loc_180031C13
0x180031b8d  mov     eax, edx
0x180031b8f  and     eax, r15d
0x180031b92  cmp     eax, r15d
0x180031b95  jnz     short loc_180031BA4
0x180031b97  mov     ecx, 3E8h; dwMilliseconds
0x180031b9c  call    cs:__imp_Sleep
0x180031ba2  jmp     short loc_180031B77
0x180031ba4  mov     eax, edi
0x180031ba6  add     edi, r14d
0x180031ba9  cmp     eax, [rbx]
0x180031bab  jb      short loc_180031B77
0x180031bad  lea     ecx, [rdx+400000h]
0x180031bb3  mov     eax, edx
0x180031bb5  lock cmpxchg [rbx+4], ecx
0x180031bba  cmp     edx, eax
0x180031bbc  jnz     short loc_180031B77
0x180031bbe  mov     rcx, rbx; this
0x180031bc1  call    ?GetWriteWaiterEvent@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetWriteWaiterEvent(void)
0x180031bc6  or      edi, 0FFFFFFFFh
0x180031bc9  mov     rcx, rax; hHandle
0x180031bcc  mov     edx, edi; dwMilliseconds
0x180031bce  call    cs:__imp_WaitForSingleObject
0x180031bd4  cmp     eax, edi
0x180031bd6  jnz     short loc_180031C13
0x180031bd8  call    cs:__imp_GetLastError
0x180031bde  mov     edx, eax; unsigned int
0x180031be0  lea     rcx, [rbp+57h+var_60]; this
0x180031be4  lea     rax, aWaitforsingleo; "WaitForSingleObject failed in UTSemRead"...
0x180031beb  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x180031bf0  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x180031bf5  mov     r9, [rbp+57h+var_50]; unsigned __int16 *
0x180031bf9  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180031c00  mov     r8d, 1ADh; unsigned int
0x180031c06  mov     [rbp+57h+var_38], r14d
0x180031c0a  lea     rcx, [rbp+57h+var_60]; this
0x180031c0e  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180031c13  mov     eax, [rbx+4]
0x180031c16  mov     edi, 0C0021251h
0x180031c1b  mov     r15d, 15h
0x180031c21  test    eax, 3FFh
0x180031c26  jz      short loc_180031C70
0x180031c28  lea     r9, aProblemWithRea_0; "Problem with Reader info in UTSemReadWr"...
0x180031c2f  mov     [rbp+57h+var_60], 0
0x180031c36  mov     r8d, 1B8h; unsigned int
0x180031c3c  mov     [rbp+57h+var_50], r9
0x180031c40  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180031c47  mov     [rbp+57h+var_5C], r15w
0x180031c4c  lea     rcx, [rbp+57h+var_60]; this
0x180031c50  mov     [rbp+57h+var_58], edi
0x180031c53  mov     [rbp+57h+var_48], 0
0x180031c5b  mov     [rbp+57h+var_40], 0
0x180031c63  mov     [rbp+57h+var_34], r14d
0x180031c67  mov     [rbp+57h+var_38], r14d
0x180031c6b  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180031c70  mov     eax, [rbx+4]
0x180031c73  and     eax, 0C00h
0x180031c78  cmp     eax, r13d
0x180031c7b  jz      short loc_180031CC5
0x180031c7d  lea     r9, aProblemWithWri_2; "Problem with Writer info in UTSemReadWr"...
0x180031c84  mov     [rbp+57h+var_60], 0
0x180031c8b  mov     r8d, 1BAh; unsigned int
0x180031c91  mov     [rbp+57h+var_50], r9
0x180031c95  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180031c9c  mov     [rbp+57h+var_5C], r15w
0x180031ca1  lea     rcx, [rbp+57h+var_60]; this
0x180031ca5  mov     [rbp+57h+var_58], edi
0x180031ca8  mov     [rbp+57h+var_48], 0
0x180031cb0  mov     [rbp+57h+var_40], 0
0x180031cb8  mov     [rbp+57h+var_34], r14d
0x180031cbc  mov     [rbp+57h+var_38], r14d
0x180031cc0  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180031cc5  add     rsp, 88h
0x180031ccc  pop     r15
0x180031cce  pop     r14
0x180031cd0  pop     r13
0x180031cd2  pop     rdi
0x180031cd3  pop     rbx
0x180031cd4  pop     rbp
0x180031cd5  retn
```
