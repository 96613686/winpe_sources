# BitLockerUnenroll::Execute(ActivityContext *)

- ea: `0x18001cfb0`
- end: `0x18001d330`
- name: `?Execute@BitLockerUnenroll@@UEAAJPEAVActivityContext@@@Z`
- size: `896`
- prototype: `int(BitLockerUnenroll *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007120`
- `0x18000dd20`
- `0x18001a86c`
- `0x18001aec8`
- `0x18001ce5c`
- `0x18001cf18`
- `0x18001cfb0`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x1800734e0`
- `0x180075b08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001d1bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001d1bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d301`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d301`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d09b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d0f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d09b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d0f0`
- `FVEAPI!FveCommitChanges` at `0x18001d2ab`
- `FVEAPI!FveCommitChanges` at `0x18001d2ab`
- `FVEAPI!FveCloseVolume` at `0x18001d2f3`
- `FVEAPI!FveCloseVolume` at `0x18001d2f3`
- `FVEAPI!FveOpenVolumeW` at `0x18001d1f8`
- `FVEAPI!FveOpenVolumeW` at `0x18001d1f8`
- `FVEAPI!FveAddAuthMethodInformation` at `0x18001d295`
- `FVEAPI!FveAddAuthMethodInformation` at `0x18001d295`
- `FVEAPI!FveGetStatus` at `0x18001d21f`
- `FVEAPI!FveGetStatus` at `0x18001d21f`

## pseudocode

```c
__int64 __fastcall BitLockerUnenroll::Execute(BitLockerUnenroll *this, struct ActivityContext *a2)
{
  HLOCAL pvData; // rdi
  int KeyAsString; // ebx
  CEnrollmentLogger *v5; // rax
  int v6; // eax
  BitLockerUnenroll *v7; // rcx
  CEnrollmentLogger *Logger; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v11; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v14; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v15; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v16; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+80h] [rbp-80h]
  __int128 v18; // [rsp+90h] [rbp-70h]
  __int64 v19; // [rsp+A0h] [rbp-60h]
  __int128 v20; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v21[3]; // [rsp+C0h] [rbp-40h] BYREF
  char v22; // [rsp+CCh] [rbp-34h]
  __int64 v23; // [rsp+F8h] [rbp-8h]
  _DWORD v24[4]; // [rsp+150h] [rbp+50h] BYREF
  char v25; // [rsp+160h] [rbp+60h]
  int v26; // [rsp+164h] [rbp+64h]
  unsigned __int16 v27[40]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v28[528]; // [rsp+3F0h] [rbp+2F0h] BYREF

  v19 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  memset_0(v24, 0, 0x248u);
  v14 = v24;
  memset_0(v28, 0, 0x208u);
  v12 = 0;
  v20 = 0;
  memset_0(v21, 0, 0x90u);
  pvData = 0;
  memset_0(v27, 0, 0x4Eu);
  pcbData = 0;
  v11 = 0;
  v13 = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\BitLockerCsp\\UserOptions",
         L"LatestEnrollmentId",
         0x20000002u,
         0,
         0,
         &pcbData) )
  {
    goto LABEL_5;
  }
  pvData = LocalAlloc(0x40u, pcbData);
  if ( !pvData )
  {
    KeyAsString = -2147024882;
LABEL_26:
    Logger = CEnrollmentLogger::GetLogger();
    v15 = *(struct _GUID *)((char *)a2 + 8);
    CEnrollmentLogger::LogUnenrollBitLockerUnenrollFailed(Logger, KeyAsString, &v15);
    goto LABEL_27;
  }
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\BitLockerCsp\\UserOptions",
         L"LatestEnrollmentId",
         0x20000002u,
         0,
         pvData,
         &pcbData) )
  {
LABEL_5:
    pcbData = 0;
    v5 = CEnrollmentLogger::GetLogger();
    v15 = *(struct _GUID *)((char *)a2 + 8);
    CEnrollmentLogger::LogUnenrollBitLockerNoEnrollmentID(v5, &v15);
  }
  KeyAsString = ActivityContext::get_KeyAsString(a2, v27);
  if ( KeyAsString < 0 )
    goto LABEL_26;
  KeyAsString = StringCchLengthW(v27, 0x7FFFFFFFu, &v13);
  if ( KeyAsString < 0 )
    goto LABEL_26;
  KeyAsString = ULongLongToULong(v13, &v11);
  if ( KeyAsString < 0 )
    goto LABEL_26;
  KeyAsString = ULongLongToULong(2LL * v11, &v11);
  if ( KeyAsString < 0 )
    goto LABEL_26;
  if ( v11 + 2 < v11 )
  {
    KeyAsString = -2147024362;
    goto LABEL_26;
  }
  KeyAsString = 0;
  if ( pcbData && pcbData == v11 + 2 && !(unsigned int)_o__wcsnicmp(pvData) )
  {
    KeyAsString = NgscbGetOSVolume(v28);
    if ( KeyAsString < 0 )
      goto LABEL_26;
    KeyAsString = FveOpenVolumeW(v28, 1, &v12);
    if ( KeyAsString < 0 )
      goto LABEL_26;
    v21[0] = 144;
    v21[1] = 10;
    KeyAsString = FveGetStatus(v12, v21);
    if ( KeyAsString < 0 )
      goto LABEL_26;
    if ( (v22 & 1) != 0 && (v23 & 0x100) == 0 )
    {
      *(_QWORD *)&v17 = &v14;
      v24[0] = 584;
      v24[1] = 1;
      v24[2] = 1;
      v24[3] = 9;
      v25 = 0;
      v26 = 12;
      *(_QWORD *)&v16 = 0x100000038LL;
      *((_QWORD *)&v16 + 1) = 0x100010000LL;
      v6 = FveAddAuthMethodInformation(v12, &v16, &v20);
      KeyAsString = v6;
      if ( v6 >= 0 && v6 != 1 )
        KeyAsString = FveCommitChanges(v12);
      BitLockerUnenroll::CleanupCspRegistryHive(v7, a2);
      if ( KeyAsString < 0 )
        goto LABEL_26;
    }
    if ( KeyAsString == 1 )
      goto LABEL_26;
  }
LABEL_27:
  if ( v12 )
    FveCloseVolume();
  if ( pvData )
    LocalFree(pvData);
  return (unsigned int)KeyAsString;
}

```

## disassembly

```asm
0x18001cfb0  mov     [rsp-8+arg_0], rbx
0x18001cfb5  mov     [rsp-8+arg_10], rsi
0x18001cfba  push    rbp
0x18001cfbb  push    rdi
0x18001cfbc  push    r15
0x18001cfbe  lea     rbp, [rsp-510h]
0x18001cfc6  sub     rsp, 610h
0x18001cfcd  mov     rax, cs:__security_cookie
0x18001cfd4  xor     rax, rsp
0x18001cfd7  mov     [rbp+520h+var_20], rax
0x18001cfde  xorps   xmm0, xmm0
0x18001cfe1  lea     rcx, [rbp+520h+var_4D0]; void *
0x18001cfe5  mov     rsi, rdx
0x18001cfe8  xor     eax, eax
0x18001cfea  xor     edx, edx; Val
0x18001cfec  mov     [rbp+520h+var_580], rax
0x18001cff0  mov     r8d, 248h; Size
0x18001cff6  movups  [rsp+620h+var_5B0], xmm0
0x18001cffb  movups  [rbp+520h+var_5A0], xmm0
0x18001cfff  movups  [rbp+520h+var_590], xmm0
0x18001d003  call    memset_0
0x18001d008  lea     rax, [rbp+520h+var_4D0]
0x18001d00c  xor     edx, edx; Val
0x18001d00e  mov     r8d, 208h; Size
0x18001d014  mov     [rsp+620h+var_5C8], rax
0x18001d019  lea     rcx, [rbp+520h+var_230]; void *
0x18001d020  call    memset_0
0x18001d025  xorps   xmm0, xmm0
0x18001d028  mov     [rsp+620h+var_5D8], 0
0x18001d031  xor     edx, edx; Val
0x18001d033  lea     rcx, [rbp+520h+var_560]; void *
0x18001d037  mov     r8d, 90h; Size
0x18001d03d  movups  [rbp+520h+var_578], xmm0
0x18001d041  call    memset_0
0x18001d046  xor     edi, edi
0x18001d048  lea     rcx, [rbp+520h+var_280]; void *
0x18001d04f  xor     edx, edx; Val
0x18001d051  lea     r8d, [rdi+4Eh]; Size
0x18001d055  call    memset_0
0x18001d05a  lea     rax, [rsp+620h+var_5E0]
0x18001d05f  mov     [rsp+620h+var_5E0], edi
0x18001d063  mov     [rsp+620h+pcbData], rax; pcbData
0x18001d068  lea     r8, aLatestenrollme; "LatestEnrollmentId"
0x18001d06f  mov     ebx, 20000002h
0x18001d074  mov     [rsp+620h+pvData], rdi; pvData
0x18001d079  mov     r15, 0FFFFFFFF80000002h
0x18001d080  mov     [rsp+620h+pdwType], rdi; pdwType
0x18001d085  mov     r9d, ebx; dwFlags
0x18001d088  mov     [rsp+620h+var_5DC], edi
0x18001d08c  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\BitLockerCsp\\User"...
0x18001d093  mov     [rsp+620h+var_5D0], rdi
0x18001d098  mov     rcx, r15; hkey
0x18001d09b  call    cs:__imp_RegGetValueW
0x18001d0a1  test    eax, eax
0x18001d0a3  jnz     short loc_18001D0FA
0x18001d0a5  mov     edx, [rsp+620h+var_5E0]; uBytes
0x18001d0a9  lea     ecx, [rdi+40h]; uFlags
0x18001d0ac  call    cs:__imp_LocalAlloc
0x18001d0b2  mov     rdi, rax
0x18001d0b5  test    rax, rax
0x18001d0b8  jnz     short loc_18001D0C4
0x18001d0ba  mov     ebx, 8007000Eh
0x18001d0bf  jmp     loc_18001D2CB
0x18001d0c4  lea     rax, [rsp+620h+var_5E0]
0x18001d0c9  mov     r9d, ebx; dwFlags
0x18001d0cc  mov     [rsp+620h+pcbData], rax; pcbData
0x18001d0d1  lea     r8, aLatestenrollme; "LatestEnrollmentId"
0x18001d0d8  mov     [rsp+620h+pvData], rdi; pvData
0x18001d0dd  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\BitLockerCsp\\User"...
0x18001d0e4  mov     rcx, r15; hkey
0x18001d0e7  mov     [rsp+620h+pdwType], 0; pdwType
0x18001d0f0  call    cs:__imp_RegGetValueW
0x18001d0f6  test    eax, eax
0x18001d0f8  jz      short loc_18001D11E
0x18001d0fa  mov     [rsp+620h+var_5E0], 0
0x18001d102  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001d107  movups  xmm0, xmmword ptr [rsi+8]
0x18001d10b  lea     rdx, [rsp+620h+var_5C0]; struct _GUID
0x18001d110  mov     rcx, rax; this
0x18001d113  movdqu  xmmword ptr [rsp+620h+var_5C0.Data1], xmm0
0x18001d119  call    ?LogUnenrollBitLockerNoEnrollmentID@CEnrollmentLogger@@QEAAXU_GUID@@@Z; CEnrollmentLogger::LogUnenrollBitLockerNoEnrollmentID(_GUID)
0x18001d11e  lea     rdx, [rbp+520h+var_280]; unsigned __int16 *
0x18001d125  mov     rcx, rsi; this
0x18001d128  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x18001d12d  mov     ebx, eax
0x18001d12f  test    eax, eax
0x18001d131  js      loc_18001D2CB
0x18001d137  lea     r8, [rsp+620h+var_5D0]; unsigned __int64 *
0x18001d13c  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001d141  lea     rcx, [rbp+520h+var_280]; unsigned __int16 *
0x18001d148  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001d14d  mov     ebx, eax
0x18001d14f  test    eax, eax
0x18001d151  js      loc_18001D2CB
0x18001d157  mov     rcx, [rsp+620h+var_5D0]; unsigned __int64
0x18001d15c  lea     rdx, [rsp+620h+var_5DC]; unsigned int *
0x18001d161  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001d166  mov     ebx, eax
0x18001d168  test    eax, eax
0x18001d16a  js      loc_18001D2CB
0x18001d170  mov     ecx, [rsp+620h+var_5DC]
0x18001d174  lea     rdx, [rsp+620h+var_5DC]; unsigned int *
0x18001d179  add     rcx, rcx; unsigned __int64
0x18001d17c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001d181  mov     ebx, eax
0x18001d183  test    eax, eax
0x18001d185  js      loc_18001D2CB
0x18001d18b  mov     eax, [rsp+620h+var_5DC]
0x18001d18f  lea     ecx, [rax+2]
0x18001d192  cmp     ecx, eax
0x18001d194  jb      loc_18001D2C6
0x18001d19a  mov     eax, [rsp+620h+var_5E0]
0x18001d19e  xor     ebx, ebx
0x18001d1a0  test    eax, eax
0x18001d1a2  jz      loc_18001D2E9
0x18001d1a8  cmp     eax, ecx
0x18001d1aa  jnz     loc_18001D2E9
0x18001d1b0  mov     r8, [rsp+620h+var_5D0]
0x18001d1b5  lea     rdx, [rbp+520h+var_280]
0x18001d1bc  mov     rcx, rdi
0x18001d1bf  call    cs:__imp__o__wcsnicmp
0x18001d1c5  test    eax, eax
0x18001d1c7  jnz     loc_18001D2E9
0x18001d1cd  lea     rcx, [rbp+520h+var_230]
0x18001d1d4  call    NgscbGetOSVolume
0x18001d1d9  mov     ebx, eax
0x18001d1db  test    eax, eax
0x18001d1dd  js      loc_18001D2CB
0x18001d1e3  mov     r15d, 1
0x18001d1e9  lea     r8, [rsp+620h+var_5D8]
0x18001d1ee  mov     edx, r15d
0x18001d1f1  lea     rcx, [rbp+520h+var_230]
0x18001d1f8  call    cs:__imp_FveOpenVolumeW
0x18001d1fe  mov     ebx, eax
0x18001d200  test    eax, eax
0x18001d202  js      loc_18001D2CB
0x18001d208  mov     rcx, [rsp+620h+var_5D8]
0x18001d20d  lea     rdx, [rbp+520h+var_560]
0x18001d211  mov     [rbp+520h+var_560], 90h
0x18001d218  mov     [rbp+520h+var_55C], 0Ah
0x18001d21f  call    cs:__imp_FveGetStatus
0x18001d225  mov     ebx, eax
0x18001d227  test    eax, eax
0x18001d229  js      loc_18001D2CB
0x18001d22f  test    [rbp+520h+var_554], r15b
0x18001d233  jz      loc_18001D2BF
0x18001d239  test    [rbp+520h+var_528], 100h
0x18001d241  jnz     short loc_18001D2BF
0x18001d243  mov     rcx, [rsp+620h+var_5D8]
0x18001d248  lea     rax, [rsp+620h+var_5C8]
0x18001d24d  lea     r8, [rbp+520h+var_578]
0x18001d251  mov     qword ptr [rbp+520h+var_5A0], rax
0x18001d255  lea     rdx, [rsp+620h+var_5B0]
0x18001d25a  mov     [rbp+520h+var_4D0], 248h
0x18001d261  mov     [rbp+520h+var_4CC], r15d
0x18001d265  mov     [rbp+520h+var_4C8], r15d
0x18001d269  mov     [rbp+520h+var_4C4], 9
0x18001d270  mov     [rbp+520h+var_4C0], 0
0x18001d274  mov     [rbp+520h+var_4BC], 0Ch
0x18001d27b  mov     dword ptr [rsp+620h+var_5B0], 38h ; '8'
0x18001d283  mov     dword ptr [rsp+620h+var_5B0+4], r15d
0x18001d288  mov     dword ptr [rsp+620h+var_5B0+8], 10000h
0x18001d290  mov     dword ptr [rsp+620h+var_5B0+0Ch], r15d
0x18001d295  call    cs:__imp_FveAddAuthMethodInformation
0x18001d29b  mov     ebx, eax
0x18001d29d  test    eax, eax
0x18001d29f  js      short loc_18001D2B3
0x18001d2a1  cmp     eax, r15d
0x18001d2a4  jz      short loc_18001D2B3
0x18001d2a6  mov     rcx, [rsp+620h+var_5D8]
0x18001d2ab  call    cs:__imp_FveCommitChanges
0x18001d2b1  mov     ebx, eax
0x18001d2b3  mov     rdx, rsi; struct ActivityContext *
0x18001d2b6  call    ?CleanupCspRegistryHive@BitLockerUnenroll@@AEAAXPEAVActivityContext@@@Z; BitLockerUnenroll::CleanupCspRegistryHive(ActivityContext *)
0x18001d2bb  test    ebx, ebx
0x18001d2bd  js      short loc_18001D2CB
0x18001d2bf  cmp     ebx, r15d
0x18001d2c2  jnz     short loc_18001D2E9
0x18001d2c4  jmp     short loc_18001D2CB
0x18001d2c6  mov     ebx, 80070216h
0x18001d2cb  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001d2d0  movups  xmm0, xmmword ptr [rsi+8]
0x18001d2d4  lea     r8, [rsp+620h+var_5C0]; struct _GUID
0x18001d2d9  mov     edx, ebx; int
0x18001d2db  mov     rcx, rax; this
0x18001d2de  movdqu  xmmword ptr [rsp+620h+var_5C0.Data1], xmm0
0x18001d2e4  call    ?LogUnenrollBitLockerUnenrollFailed@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollBitLockerUnenrollFailed(long,_GUID)
0x18001d2e9  mov     rcx, [rsp+620h+var_5D8]
0x18001d2ee  test    rcx, rcx
0x18001d2f1  jz      short loc_18001D2F9
0x18001d2f3  call    cs:__imp_FveCloseVolume
0x18001d2f9  test    rdi, rdi
0x18001d2fc  jz      short loc_18001D307
0x18001d2fe  mov     rcx, rdi; hMem
0x18001d301  call    cs:__imp_LocalFree
0x18001d307  mov     eax, ebx
0x18001d309  mov     rcx, [rbp+520h+var_20]
0x18001d310  xor     rcx, rsp; StackCookie
0x18001d313  call    __security_check_cookie
0x18001d318  lea     r11, [rsp+620h+var_10]
0x18001d320  mov     rbx, [r11+20h]
0x18001d324  mov     rsi, [r11+30h]
0x18001d328  mov     rsp, r11
0x18001d32b  pop     r15
0x18001d32d  pop     rdi
0x18001d32e  pop     rbp
0x18001d32f  retn
```
