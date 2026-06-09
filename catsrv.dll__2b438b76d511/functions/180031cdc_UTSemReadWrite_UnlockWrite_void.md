# UTSemReadWrite::UnlockWrite(void)

- ea: `0x180031cdc`
- end: `0x180031f03`
- name: `?UnlockWrite@UTSemReadWrite@@QEAAXXZ`
- size: `551`
- prototype: `void __fastcall(UTSemReadWrite *__hidden this)`
- caller_count: `28`
- callee_count: `5`
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
- `0x1800319f8`
- `0x180031aa8`
- `0x180031cdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031e71`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031e71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180031ed4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180031ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ede`

## string_xrefs

- `0x180031cf4`: `com\complus\src\shared\util\utsem.cpp`
- `0x180031d0e`: `Problem with Reader info in UTSemReadWrite::LockWrite`
- `0x180031d68`: `Problem with Writer info in UTSemReadWrite::LockWrite`
- `0x180031eea`: `ReleaseSemaphore failed in UTSemReadWrite:UnlockWrite`
- `0x180031db2`: `Problem with WriteWatier info in UTSemReadWrite::UnlockWrite`
- `0x180031e87`: `SetEvent failed in UTSemReadWrite:UnlockWrite`

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
0x180031cdc  push    rbp
0x180031cde  push    rbx
0x180031cdf  push    rsi
0x180031ce0  push    rdi
0x180031ce1  push    r12
0x180031ce3  push    r13
0x180031ce5  push    r15
0x180031ce7  mov     rbp, rsp
0x180031cea  sub     rsp, 80h
0x180031cf1  mov     eax, [rcx+4]
0x180031cf4  lea     r12, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x180031cfb  mov     esi, 15h
0x180031d00  mov     rbx, rcx
0x180031d03  lea     r15d, [rsi-14h]
0x180031d07  test    eax, 3FFh
0x180031d0c  jz      short loc_180031D55
0x180031d0e  lea     r9, aProblemWithRea_0; "Problem with Reader info in UTSemReadWr"...
0x180031d15  mov     [rbp+var_30], 0
0x180031d1c  mov     r8d, 235h; unsigned int
0x180031d22  mov     [rbp+var_20], r9
0x180031d26  mov     rdx, r12; unsigned __int16 *
0x180031d29  mov     [rbp+var_2C], si
0x180031d2d  lea     rcx, [rbp+var_30]; this
0x180031d31  mov     [rbp+var_28], 0C0021251h
0x180031d38  mov     [rbp+var_18], 0
0x180031d40  mov     [rbp+var_10], 0
0x180031d48  mov     [rbp+var_4], r15d
0x180031d4c  mov     [rbp+var_8], r15d
0x180031d50  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180031d55  mov     eax, [rbx+4]
0x180031d58  mov     r13d, 400h
0x180031d5e  and     eax, 0C00h
0x180031d63  cmp     eax, r13d
0x180031d66  jz      short loc_180031DAF
0x180031d68  lea     r9, aProblemWithWri_2; "Problem with Writer info in UTSemReadWr"...
0x180031d6f  mov     [rbp+var_30], 0
0x180031d76  mov     r8d, 237h; unsigned int
0x180031d7c  mov     [rbp+var_20], r9
0x180031d80  mov     rdx, r12; unsigned __int16 *
0x180031d83  mov     [rbp+var_2C], si
0x180031d87  lea     rcx, [rbp+var_30]; this
0x180031d8b  mov     [rbp+var_28], 0C0021251h
0x180031d92  mov     [rbp+var_18], 0
0x180031d9a  mov     [rbp+var_10], 0
0x180031da2  mov     [rbp+var_4], r15d
0x180031da6  mov     [rbp+var_8], r15d
0x180031daa  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180031daf  mov     edi, [rbx+4]
0x180031db2  lea     rax, aProblemWithWri_0; "Problem with WriteWatier info in UTSemR"...
0x180031db9  cmp     edi, r13d
0x180031dbc  jnz     short loc_180031DD0
0x180031dbe  xor     ecx, ecx
0x180031dc0  mov     eax, r13d
0x180031dc3  lock cmpxchg [rbx+4], ecx
0x180031dc8  jz      loc_180031EB2
0x180031dce  jmp     short loc_180031DAF
0x180031dd0  test    edi, 3FF000h
0x180031dd6  jz      short loc_180031E06
0x180031dd8  mov     esi, edi
0x180031dda  mov     ecx, edi
0x180031ddc  shr     esi, 0Ch
0x180031ddf  and     esi, 3FFh
0x180031de5  imul    eax, esi, 0FFFh
0x180031deb  sub     ecx, eax
0x180031ded  mov     eax, edi
0x180031def  sub     ecx, r13d
0x180031df2  lock cmpxchg [rbx+4], ecx
0x180031df7  cmp     edi, eax
0x180031df9  jz      loc_180031EC4
0x180031dff  mov     esi, 15h
0x180031e04  jmp     short loc_180031DAF
0x180031e06  test    edi, 0FFC00000h
0x180031e0c  jnz     short loc_180031E51
0x180031e0e  mov     r9, rax; unsigned __int16 *
0x180031e11  mov     [rbp+var_30], 0
0x180031e18  mov     r8d, 253h; unsigned int
0x180031e1e  mov     [rbp+var_2C], si
0x180031e22  mov     rdx, r12; unsigned __int16 *
0x180031e25  mov     [rbp+var_28], 0C0021251h
0x180031e2c  lea     rcx, [rbp+var_30]; this
0x180031e30  mov     [rbp+var_20], rax
0x180031e34  mov     [rbp+var_18], 0
0x180031e3c  mov     [rbp+var_10], 0
0x180031e44  mov     [rbp+var_4], r15d
0x180031e48  mov     [rbp+var_8], r15d
0x180031e4c  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180031e51  lea     ecx, [rdi-400000h]
0x180031e57  mov     eax, edi
0x180031e59  lock cmpxchg [rbx+4], ecx
0x180031e5e  cmp     edi, eax
0x180031e60  jnz     loc_180031DAF
0x180031e66  mov     rcx, rbx; this
0x180031e69  call    ?GetWriteWaiterEvent@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetWriteWaiterEvent(void)
0x180031e6e  mov     rcx, rax; hEvent
0x180031e71  call    cs:__imp_SetEvent
0x180031e77  test    eax, eax
0x180031e79  jnz     short loc_180031EB2
0x180031e7b  call    cs:__imp_GetLastError
0x180031e81  mov     edx, eax; unsigned int
0x180031e83  lea     rcx, [rbp+var_30]; this
0x180031e87  lea     rax, aSeteventFailed_0; "SetEvent failed in UTSemReadWrite:Unloc"...
0x180031e8e  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x180031e93  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x180031e98  mov     r8d, 258h; unsigned int
0x180031e9e  mov     r9, [rbp+var_20]; unsigned __int16 *
0x180031ea2  lea     rcx, [rbp+var_30]; this
0x180031ea6  mov     rdx, r12; unsigned __int16 *
0x180031ea9  mov     [rbp+var_8], r15d
0x180031ead  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180031eb2  add     rsp, 80h
0x180031eb9  pop     r15
0x180031ebb  pop     r13
0x180031ebd  pop     r12
0x180031ebf  pop     rdi
0x180031ec0  pop     rsi
0x180031ec1  pop     rbx
0x180031ec2  pop     rbp
0x180031ec3  retn
0x180031ec4  mov     rcx, rbx; this
0x180031ec7  call    ?GetReadWaiterSemaphore@UTSemReadWrite@@AEAAPEAXXZ; UTSemReadWrite::GetReadWaiterSemaphore(void)
0x180031ecc  mov     rcx, rax; hSemaphore
0x180031ecf  xor     r8d, r8d; lpPreviousCount
0x180031ed2  mov     edx, esi; lReleaseCount
0x180031ed4  call    cs:__imp_ReleaseSemaphore
0x180031eda  test    eax, eax
0x180031edc  jnz     short loc_180031EB2
0x180031ede  call    cs:__imp_GetLastError
0x180031ee4  mov     edx, eax; unsigned int
0x180031ee6  lea     rcx, [rbp+var_30]; this
0x180031eea  lea     rax, aReleasesemapho; "ReleaseSemaphore failed in UTSemReadWri"...
0x180031ef1  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x180031ef6  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x180031efb  mov     r8d, 24Bh
0x180031f01  jmp     short loc_180031E9E
```
