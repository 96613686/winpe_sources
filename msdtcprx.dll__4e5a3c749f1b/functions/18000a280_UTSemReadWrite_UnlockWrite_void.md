# UTSemReadWrite::UnlockWrite(void)

- ea: `0x18000a280`
- end: `0x18000a4a7`
- name: `?UnlockWrite@UTSemReadWrite@@QEAAXXZ`
- size: `551`
- prototype: `void __fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `26`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a1b4`
- `0x18000b608`
- `0x18000b9d0`
- `0x18003ada0`
- `0x18003c150`
- `0x18004fab0`
- `0x18004fc10`
- `0x18004fed0`
- `0x18004ff20`
- `0x18004ff70`
- `0x18004ffc0`
- `0x180050080`
- `0x18007a350`
- `0x18007a5a8`
- `0x18007b150`
- `0x18007b18c`
- `0x18007b240`
- `0x18007bab0`
- `0x18007bb10`
- `0x18007bb70`
- `0x18007bce0`
- `0x18007bd40`
- `0x18007bea0`
- `0x18007bf00`
- `0x18007bf60`
- `0x1800821cc`

## callees

- `0x18000792c`
- `0x18000a280`
- `0x18000fa40`
- `0x18007d168`
- `0x18007d218`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a478`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a478`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a415`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a482`

## string_xrefs

- `0x18000a298`: `com\complus\src\shared\util\utsem.cpp`
- `0x18000a356`: `Problem with WriteWatier info in UTSemReadWrite::UnlockWrite`
- `0x18000a30c`: `Problem with Writer info in UTSemReadWrite::LockWrite`
- `0x18000a2b2`: `Problem with Reader info in UTSemReadWrite::LockWrite`
- `0x18000a48e`: `ReleaseSemaphore failed in UTSemReadWrite:UnlockWrite`
- `0x18000a42b`: `SetEvent failed in UTSemReadWrite:UnlockWrite`

## pseudocode

```c
void __fastcall UTSemReadWrite::UnlockWrite(UTSemReadWrite *this)
{
  unsigned __int32 v2; // edi
  LONG v3; // esi
  void *v4; // rax
  DWORD LastError; // eax
  unsigned __int16 v6; // r8
  unsigned int v7; // r9d
  unsigned int v8; // r8d
  void *WaiterSemaphore; // rax
  DWORD v10; // eax
  unsigned __int16 v11; // r8
  unsigned int v12; // r9d
  const void *v13; // [rsp+28h] [rbp-58h]
  unsigned int v14; // [rsp+30h] [rbp-50h]
  int v15; // [rsp+38h] [rbp-48h]
  int v16; // [rsp+40h] [rbp-40h]
  int v17; // [rsp+50h] [rbp-30h] BYREF
  __int16 v18; // [rsp+54h] [rbp-2Ch]
  int v19; // [rsp+58h] [rbp-28h]
  unsigned __int16 *v20; // [rsp+60h] [rbp-20h]
  __int64 v21; // [rsp+68h] [rbp-18h]
  __int64 v22; // [rsp+70h] [rbp-10h]
  int v23; // [rsp+78h] [rbp-8h]
  int v24; // [rsp+7Ch] [rbp-4h]

  if ( (*((_DWORD *)this + 1) & 0x3FF) != 0 )
  {
    v17 = 0;
    v20 = L"Problem with Reader info in UTSemReadWrite::LockWrite";
    v18 = 21;
    v19 = -1073606063;
    v21 = 0;
    v22 = 0;
    v24 = 1;
    v23 = 1;
    CError::WriteToLog(
      (CError *)&v17,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x235u,
      L"Problem with Reader info in UTSemReadWrite::LockWrite");
  }
  if ( (*((_DWORD *)this + 1) & 0xC00) != 0x400 )
  {
    v17 = 0;
    v20 = L"Problem with Writer info in UTSemReadWrite::LockWrite";
    v18 = 21;
    v19 = -1073606063;
    v21 = 0;
    v22 = 0;
    v24 = 1;
    v23 = 1;
    CError::WriteToLog(
      (CError *)&v17,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x237u,
      L"Problem with Writer info in UTSemReadWrite::LockWrite");
  }
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v2 = *((_DWORD *)this + 1);
        if ( v2 != 1024 )
          break;
        if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 1, 0, 1024) == 1024 )
          return;
      }
      if ( (v2 & 0x3FF000) != 0 )
        break;
      if ( (v2 & 0xFFC00000) == 0 )
      {
        v17 = 0;
        v18 = 21;
        v19 = -1073606063;
        v20 = L"Problem with WriteWatier info in UTSemReadWrite::UnlockWrite";
        v21 = 0;
        v22 = 0;
        v24 = 1;
        v23 = 1;
        CError::WriteToLog(
          (CError *)&v17,
          L"com\\complus\\src\\shared\\util\\utsem.cpp",
          0x253u,
          L"Problem with WriteWatier info in UTSemReadWrite::UnlockWrite");
      }
      if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 0x400000, v2) )
      {
        v4 = UTSemReadWrite::GetWriteWaiterEvent(this);
        if ( SetEvent(v4) )
          return;
        LastError = GetLastError();
        CErrorWin32::CErrorWin32(
          (CErrorWin32 *)&v17,
          LastError,
          v6,
          v7,
          L"SetEvent failed in UTSemReadWrite:UnlockWrite",
          v13,
          v14,
          v15,
          v16);
        v8 = 600;
        goto LABEL_16;
      }
    }
    v3 = (v2 >> 12) & 0x3FF;
  }
  while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 4095 * v3 - 1024, v2) );
  WaiterSemaphore = UTSemReadWrite::GetReadWaiterSemaphore(this);
  if ( !ReleaseSemaphore(WaiterSemaphore, v3, 0) )
  {
    v10 = GetLastError();
    CErrorWin32::CErrorWin32(
      (CErrorWin32 *)&v17,
      v10,
      v11,
      v12,
      L"ReleaseSemaphore failed in UTSemReadWrite:UnlockWrite",
      v13,
      v14,
      v15,
      v16);
    v8 = 587;
LABEL_16:
    v23 = 1;
    CError::WriteToLog((CError *)&v17, L"com\\complus\\src\\shared\\util\\utsem.cpp", v8, v20);
  }
}

```

## disassembly

```asm
0x18000a280  push    rbp
0x18000a282  push    rbx
0x18000a283  push    rsi
0x18000a284  push    rdi
0x18000a285  push    r12
0x18000a287  push    r13
0x18000a289  push    r15
0x18000a28b  mov     rbp, rsp
0x18000a28e  sub     rsp, 80h
0x18000a295  mov     eax, [rcx+4]
0x18000a298  lea     r12, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18000a29f  mov     esi, 15h
0x18000a2a4  mov     rbx, rcx
0x18000a2a7  lea     r15d, [rsi-14h]
0x18000a2ab  test    eax, 3FFh
0x18000a2b0  jz      short loc_18000A2F9
0x18000a2b2  lea     r9, aProblemWithRea_0; "Problem with Reader info in UTSemReadWr"...
0x18000a2b9  mov     [rbp+var_30], 0
0x18000a2c0  mov     r8d, 235h; unsigned int
0x18000a2c6  mov     [rbp+var_20], r9
0x18000a2ca  mov     rdx, r12; unsigned __int16 *
0x18000a2cd  mov     [rbp+var_2C], si
0x18000a2d1  lea     rcx, [rbp+var_30]; this
0x18000a2d5  mov     [rbp+var_28], 0C0021251h
0x18000a2dc  mov     [rbp+var_18], 0
0x18000a2e4  mov     [rbp+var_10], 0
0x18000a2ec  mov     [rbp+var_4], r15d
0x18000a2f0  mov     [rbp+var_8], r15d
0x18000a2f4  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000a2f9  mov     eax, [rbx+4]
0x18000a2fc  mov     r13d, 400h
0x18000a302  and     eax, 0C00h
0x18000a307  cmp     eax, r13d
0x18000a30a  jz      short loc_18000A353
0x18000a30c  lea     r9, aProblemWithWri_2; "Problem with Writer info in UTSemReadWr"...
0x18000a313  mov     [rbp+var_30], 0
0x18000a31a  mov     r8d, 237h; unsigned int
0x18000a320  mov     [rbp+var_20], r9
0x18000a324  mov     rdx, r12; unsigned __int16 *
0x18000a327  mov     [rbp+var_2C], si
0x18000a32b  lea     rcx, [rbp+var_30]; this
0x18000a32f  mov     [rbp+var_28], 0C0021251h
0x18000a336  mov     [rbp+var_18], 0
0x18000a33e  mov     [rbp+var_10], 0
0x18000a346  mov     [rbp+var_4], r15d
0x18000a34a  mov     [rbp+var_8], r15d
0x18000a34e  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000a353  mov     edi, [rbx+4]
0x18000a356  lea     rax, aProblemWithWri_0; "Problem with WriteWatier info in UTSemR"...
0x18000a35d  cmp     edi, r13d
0x18000a360  jnz     short loc_18000A374
0x18000a362  xor     ecx, ecx
0x18000a364  mov     eax, r13d
0x18000a367  lock cmpxchg [rbx+4], ecx
0x18000a36c  jz      loc_18000A456
0x18000a372  jmp     short loc_18000A353
0x18000a374  test    edi, 3FF000h
0x18000a37a  jz      short loc_18000A3AA
0x18000a37c  mov     esi, edi
0x18000a37e  mov     ecx, edi
0x18000a380  shr     esi, 0Ch
0x18000a383  and     esi, 3FFh
0x18000a389  imul    eax, esi, 0FFFh
0x18000a38f  sub     ecx, eax
0x18000a391  mov     eax, edi
0x18000a393  sub     ecx, r13d
0x18000a396  lock cmpxchg [rbx+4], ecx
0x18000a39b  cmp     edi, eax
0x18000a39d  jz      loc_18000A468
0x18000a3a3  mov     esi, 15h
0x18000a3a8  jmp     short loc_18000A353
0x18000a3aa  test    edi, 0FFC00000h
0x18000a3b0  jnz     short loc_18000A3F5
0x18000a3b2  mov     r9, rax; unsigned __int16 *
0x18000a3b5  mov     [rbp+var_30], 0
0x18000a3bc  mov     r8d, 253h; unsigned int
0x18000a3c2  mov     [rbp+var_2C], si
0x18000a3c6  mov     rdx, r12; unsigned __int16 *
0x18000a3c9  mov     [rbp+var_28], 0C0021251h
0x18000a3d0  lea     rcx, [rbp+var_30]; this
0x18000a3d4  mov     [rbp+var_20], rax
0x18000a3d8  mov     [rbp+var_18], 0
0x18000a3e0  mov     [rbp+var_10], 0
0x18000a3e8  mov     [rbp+var_4], r15d
0x18000a3ec  mov     [rbp+var_8], r15d
0x18000a3f0  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000a3f5  lea     ecx, [rdi-400000h]
0x18000a3fb  mov     eax, edi
0x18000a3fd  lock cmpxchg [rbx+4], ecx
0x18000a402  cmp     edi, eax
0x18000a404  jnz     loc_18000A353
0x18000a40a  mov     rcx, rbx; this
0x18000a40d  call    ?GetWriteWaiterEvent@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetWriteWaiterEvent(void)
0x18000a412  mov     rcx, rax; hEvent
0x18000a415  call    cs:__imp_SetEvent
0x18000a41b  test    eax, eax
0x18000a41d  jnz     short loc_18000A456
0x18000a41f  call    cs:__imp_GetLastError
0x18000a425  mov     edx, eax; unsigned int
0x18000a427  lea     rcx, [rbp+var_30]; this
0x18000a42b  lea     rax, aSeteventFailed_1; "SetEvent failed in UTSemReadWrite:Unloc"...
0x18000a432  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x18000a437  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x18000a43c  mov     r8d, 258h; unsigned int
0x18000a442  mov     r9, [rbp+var_20]; unsigned __int16 *
0x18000a446  lea     rcx, [rbp+var_30]; this
0x18000a44a  mov     rdx, r12; unsigned __int16 *
0x18000a44d  mov     [rbp+var_8], r15d
0x18000a451  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000a456  add     rsp, 80h
0x18000a45d  pop     r15
0x18000a45f  pop     r13
0x18000a461  pop     r12
0x18000a463  pop     rdi
0x18000a464  pop     rsi
0x18000a465  pop     rbx
0x18000a466  pop     rbp
0x18000a467  retn
0x18000a468  mov     rcx, rbx; this
0x18000a46b  call    ?GetReadWaiterSemaphore@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetReadWaiterSemaphore(void)
0x18000a470  mov     rcx, rax; hSemaphore
0x18000a473  xor     r8d, r8d; lpPreviousCount
0x18000a476  mov     edx, esi; lReleaseCount
0x18000a478  call    cs:__imp_ReleaseSemaphore
0x18000a47e  test    eax, eax
0x18000a480  jnz     short loc_18000A456
0x18000a482  call    cs:__imp_GetLastError
0x18000a488  mov     edx, eax; unsigned int
0x18000a48a  lea     rcx, [rbp+var_30]; this
0x18000a48e  lea     rax, aReleasesemapho; "ReleaseSemaphore failed in UTSemReadWri"...
0x18000a495  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x18000a49a  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x18000a49f  mov     r8d, 24Bh
0x18000a4a5  jmp     short loc_18000A442
```
