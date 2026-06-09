# EnumDriverPackageCallback

- ea: `0x180005bd0`
- end: `0x180006487`
- name: `EnumDriverPackageCallback`
- size: `2231`
- prototype: `_BOOL8 __fastcall(__int64, __int64, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005bd0`
- `0x180007370`
- `0x180008de6`
- `0x180008dfe`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `msvcrt!_wcslwr` at `0x180005f54`
- `msvcrt!_wcslwr` at `0x180005f54`
- `msvcrt!wcsstr` at `0x180005f68`
- `msvcrt!wcsstr` at `0x180005f89`
- `msvcrt!wcsstr` at `0x180005faa`
- `msvcrt!wcsstr` at `0x180005f68`
- `msvcrt!wcsstr` at `0x180005f89`
- `msvcrt!wcsstr` at `0x180005faa`
- `KERNEL32!GetLastError` at `0x180005d13`
- `KERNEL32!GetLastError` at `0x180005df0`
- `KERNEL32!GetLastError` at `0x18000605b`
- `KERNEL32!GetLastError` at `0x1800060ea`
- `KERNEL32!GetLastError` at `0x180006198`
- `KERNEL32!GetLastError` at `0x18000622c`
- `KERNEL32!GetLastError` at `0x180006435`
- `KERNEL32!GetLastError` at `0x180005d13`
- `KERNEL32!GetLastError` at `0x180005df0`
- `KERNEL32!GetLastError` at `0x18000605b`
- `KERNEL32!GetLastError` at `0x1800060ea`
- `KERNEL32!GetLastError` at `0x180006198`
- `KERNEL32!GetLastError` at `0x18000622c`
- `KERNEL32!GetLastError` at `0x180006435`
- `SETUPAPI!pSetupStringTableAddStringEx` at `0x18000633a`
- `SETUPAPI!pSetupStringTableAddStringEx` at `0x18000633a`
- `SETUPAPI!pSetupStringFromGuid` at `0x18000610b`
- `SETUPAPI!pSetupStringFromGuid` at `0x18000610b`
- `SETUPAPI!pSetupStringTableLookUpStringEx` at `0x1800061c9`
- `SETUPAPI!pSetupStringTableLookUpStringEx` at `0x1800061c9`
- `drvstore!DriverPackageClose` at `0x18000647c`
- `drvstore!DriverPackageClose` at `0x18000647c`
- `drvstore!DriverPackageEnumDriversW` at `0x18000642b`
- `drvstore!DriverPackageEnumDriversW` at `0x18000642b`
- `drvstore!DriverStoreEnumRelatedDriversW` at `0x180006220`
- `drvstore!DriverStoreEnumRelatedDriversW` at `0x180006220`
- `drvstore!DriverPackageEnumRegKeysW` at `0x180005eb2`
- `drvstore!DriverPackageEnumRegKeysW` at `0x180005eb2`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180005e4d`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180005f33`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180006005`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180006051`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1800060e0`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x18000618e`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180005e4d`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180005f33`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180006005`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180006051`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1800060e0`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x18000618e`
- `drvstore!DriverPackageGetVersionInfoW` at `0x180005de6`
- `drvstore!DriverPackageGetVersionInfoW` at `0x180005de6`
- `drvstore!DriverPackageOpenW` at `0x180005cf7`
- `drvstore!DriverPackageOpenW` at `0x180005cf7`
- `drvstore!DriverStoreDriverPackageResolveCallbackW` at `0x180005cd2`

## string_xrefs

- `0x180005d2c`: `Failed to open driver package %ws (%ws) (Err = 0x%lx)`
- `0x180005f7b`: `\microsoft\windows\devicesoftwareupdates\`
- `0x18000611f`: `Failed to retrieve ExtensionId for %ws (%ws) (Err = 0x%lx), skipping package.`
- `0x18000624c`: `INF %ws (%ws) not installed as primitive, skipping package.`

## pseudocode

```c
_BOOL8 __fastcall EnumDriverPackageCallback(__int64 a1, __int64 a2, unsigned __int16 *a3, __int64 a4)
{
  int v8; // edi
  __int64 v9; // rcx
  void (*v10)(__int64, __int64, _QWORD, const char *, ...); // rax
  unsigned __int16 *v11; // r14
  __int64 v12; // rdx
  __int64 v13; // r13
  DWORD LastError; // eax
  int v16; // r12d
  DWORD v17; // eax
  const char *v18; // r9
  unsigned int v19; // r12d
  int v20; // r13d
  int v21; // r15d
  int v22; // eax
  __int64 v23; // r15
  DWORD v24; // eax
  const char *v25; // r9
  __int64 v26; // rdx
  bool v27; // zf
  int v28; // eax
  __int64 v29; // rcx
  int v30; // r12d
  __int16 *v31; // rdx
  __int64 v32; // rcx
  __int16 *v33; // rax
  __int16 *v34; // rcx
  __int64 v35; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+20h] [rbp-E0h]
  __int64 *v37; // [rsp+30h] [rbp-D0h]
  int v38; // [rsp+50h] [rbp-B0h] BYREF
  char v39[4]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+60h] [rbp-A0h]
  int v42; // [rsp+64h] [rbp-9Ch]
  int v43; // [rsp+68h] [rbp-98h]
  int v44; // [rsp+6Ch] [rbp-94h]
  int v45; // [rsp+70h] [rbp-90h]
  int v46; // [rsp+74h] [rbp-8Ch] BYREF
  int v47; // [rsp+78h] [rbp-88h]
  int v48; // [rsp+7Ch] [rbp-84h]
  int v49; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+98h] [rbp-68h]
  __int128 v53; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v54; // [rsp+B0h] [rbp-50h] BYREF
  int v55; // [rsp+B8h] [rbp-48h]
  __int64 v56; // [rsp+BCh] [rbp-44h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  int v58; // [rsp+D8h] [rbp-28h]
  __int16 v59; // [rsp+DCh] [rbp-24h] BYREF
  __int64 v60; // [rsp+130h] [rbp+30h]
  __int64 v61; // [rsp+140h] [rbp+40h] BYREF
  int v62; // [rsp+148h] [rbp+48h]
  __int128 v63; // [rsp+150h] [rbp+50h] BYREF
  _DWORD v64[8]; // [rsp+160h] [rbp+60h] BYREF
  char v65[80]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v66; // [rsp+1D0h] [rbp+D0h]
  int v67; // [rsp+1D8h] [rbp+D8h]
  int v68; // [rsp+1DCh] [rbp+DCh]
  int v69; // [rsp+1E0h] [rbp+E0h]
  int v70; // [rsp+1E4h] [rbp+E4h]
  int v71; // [rsp+1E8h] [rbp+E8h]
  int v72; // [rsp+1ECh] [rbp+ECh]
  __int128 v73; // [rsp+1F0h] [rbp+F0h]
  int v74; // [rsp+200h] [rbp+100h] BYREF
  char v75[692]; // [rsp+204h] [rbp+104h] BYREF
  __int64 v76; // [rsp+4B8h] [rbp+3B8h]
  __int64 v77; // [rsp+4C0h] [rbp+3C0h]
  _OWORD Buf1[66]; // [rsp+4C8h] [rbp+3C8h] BYREF
  unsigned int v79; // [rsp+8ECh] [rbp+7ECh]
  _WORD v80[40]; // [rsp+8F0h] [rbp+7F0h] BYREF
  wchar_t String[264]; // [rsp+940h] [rbp+840h] BYREF

  v40 = a1;
  memset_0(&v74, 0, 0x6F0u);
  v38 = 0;
  v46 = 0;
  v51 = 0;
  v53 = 0;
  v39[0] = 0;
  memset_0(&v54, 0, 0x88u);
  v50 = 0;
  v61 = 0;
  v62 = 0;
  v49 = 0;
  memset_0(v64, 0, 0xA0u);
  v63 = 0;
  if ( a3 && a4 )
  {
    if ( !(unsigned int)PnpCleanDriversNotifyCallback(a4) )
    {
      v8 = 1223;
LABEL_10:
      *(_DWORD *)a4 = v8;
      return v8 == 0;
    }
    v9 = *(_QWORD *)(a4 + 48);
    v10 = *(void (**)(__int64, __int64, _QWORD, const char *, ...))(a4 + 40);
    v8 = 0;
    v48 = 0;
    v11 = a3 + 86;
    v10(v9, 6, 0, "Processing %ws", a3 + 86);
    v12 = *a3;
    *(_QWORD *)&v53 = DriverStoreDriverPackageResolveCallbackW;
    *((_QWORD *)&v53 + 1) = a1;
    v52 = DriverPackageOpenW(a2, v12, 0, 0, &v53);
    v13 = v52;
    if ( !v52 )
    {
      LastError = GetLastError();
      if ( LastError != -536870909 && LastError - 2 > 1 )
      {
        (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a4 + 40))(
          *(_QWORD *)(a4 + 48),
          1,
          0,
          "Failed to open driver package %ws (%ws) (Err = 0x%lx)",
          a3 + 86,
          a2,
          LastError);
        goto LABEL_10;
      }
      (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a4 + 40))(
        *(_QWORD *)(a4 + 48),
        2,
        0,
        "Driver package %ws (%ws) missing or corrupt (Err = 0x%lx)",
        a3 + 86,
        a2,
        LastError);
      v48 = 1;
    }
    v43 = 0;
    v16 = 0;
    memset_0(v75, 0, 0x6ECu);
    v74 = 1776;
    if ( v52 )
    {
      if ( !(unsigned int)DriverPackageGetVersionInfoW(v52, &v74) )
      {
        v17 = GetLastError();
        v18 = "Failed to get driver package version info for %ws (%ws) (Err = 0x%lx), skipping package.";
LABEL_86:
        LODWORD(v37) = v17;
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const char *, unsigned __int16 *, __int64, __int64 *))(a4 + 40))(
          *(_QWORD *)(a4 + 48),
          1,
          0,
          v18,
          v11,
          a2,
          v37);
        goto LABEL_87;
      }
      v19 = v79;
      if ( (v79 & 1) == 0 )
      {
        if ( !(unsigned int)DriverStoreGetObjectPropertyW(
                              v40,
                              2,
                              a2,
                              DEVPKEY_DriverPackage_Primitive,
                              &v38,
                              v39,
                              1,
                              0,
                              0)
          || v38 != 17
          || v39[0] != -1 )
        {
          (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a4 + 40))(
            *(_QWORD *)(a4 + 48),
            3,
            0,
            "INF %ws (%ws) has no drivers, skipping package.",
            a3 + 86,
            a2);
          goto LABEL_87;
        }
        v19 = v79;
        v43 = 1;
      }
      v16 = (v19 >> 4) & 1;
      if ( !memcmp_0(Buf1, &GUID_DEVCLASS_DISPLAY, 0x10u) )
        DriverPackageEnumRegKeysW(v13, 0, 17, EnumWdfClassExtensionsCallback, &v49);
    }
    if ( (a3[346] & 1) != 0 )
    {
      v20 = 1;
    }
    else if ( (unsigned int)DriverStoreGetObjectPropertyW(
                              v40,
                              2,
                              a2,
                              DEVPKEY_DriverPackage_SourceMediaPath,
                              &v38,
                              String,
                              520,
                              0,
                              0)
           && v38 == 18 )
    {
      String[259] = 0;
      _wcslwr(String);
      if ( wcsstr(String, L"\\softwaredistribution\\download\\") )
      {
        v20 = 3;
      }
      else if ( wcsstr(String, L"\\microsoft\\windows\\devicesoftwareupdates\\") )
      {
        v20 = 4;
      }
      else
      {
        v20 = 6 - (wcsstr(String, L"\\program files") != 0);
      }
    }
    else
    {
      v20 = 0;
    }
    v21 = 0;
    v42 = 0;
    v47 = 0;
    if ( (unsigned int)DriverStoreGetObjectPropertyW(v40, 2, a2, DEVPKEY_DriverPackage_LockLevel, &v38, &v46, 4, 0, 0) )
    {
      v22 = 0;
      if ( v38 == 7 )
        v22 = v46;
      v42 = v22;
    }
    if ( !(unsigned int)DriverStoreGetObjectPropertyW(v40, 2, a2, DEVPKEY_DriverPackage_DriverSetIds, &v38, 0, 0, 0, 0)
      && GetLastError() == 122 )
    {
      if ( v38 == 4109 )
        v21 = 1;
      v47 = v21;
    }
    v80[0] = 0;
    v23 = 39;
    if ( !memcmp_0(Buf1, &GUID_DEVCLASS_EXTENSION, 0x10u) )
    {
      if ( (unsigned int)DriverStoreGetObjectPropertyW(
                           v40,
                           2,
                           a2,
                           DEVPKEY_DriverPackage_ExtensionId,
                           &v38,
                           &v63,
                           16,
                           0,
                           0) )
      {
        v24 = 13;
        if ( v38 != 13 )
        {
LABEL_49:
          v25 = "Failed to retrieve ExtensionId for %ws (%ws) (Err = 0x%lx), skipping package.";
          v26 = 1;
LABEL_50:
          LODWORD(v37) = v24;
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const char *, unsigned __int16 *, __int64, __int64 *))(a4 + 40))(
            *(_QWORD *)(a4 + 48),
            v26,
            0,
            v25,
            v11,
            a2,
            v37);
          goto LABEL_70;
        }
        v24 = pSetupStringFromGuid(&v63, v80, 39);
      }
      else
      {
        v24 = GetLastError();
      }
      v45 = 1;
      if ( v24 )
        goto LABEL_49;
    }
    else
    {
      v45 = 0;
    }
    v44 = 0;
    if ( (unsigned int)DriverStoreGetObjectPropertyW(v40, 2, a2, DEVPKEY_DriverPackage_ImportDate, &v38, &v51, 8, 0, 0) )
      v27 = v38 == 16;
    else
      v27 = GetLastError() == 0;
    if ( !v27 )
      v51 = 0;
    if ( v43 )
    {
      v37 = &v61;
      HIDWORD(v35) = 0;
      if ( !(unsigned int)DriverStoreEnumRelatedDriversW(v40, a2, 1) )
      {
        v24 = GetLastError();
        v25 = "Unable to retrieve Primitive INF family information for %ws (%ws) (Err = 0x%lx), skipping package.";
        v26 = 2;
        goto LABEL_50;
      }
      if ( !v62 )
      {
        (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a4 + 40))(
          *(_QWORD *)(a4 + 48),
          3,
          0,
          "INF %ws (%ws) not installed as primitive, skipping package.",
          v11,
          a2);
LABEL_70:
        v13 = v52;
        if ( !v52 )
          goto LABEL_10;
LABEL_87:
        DriverPackageClose(v13);
        goto LABEL_10;
      }
      v41 = v61;
      v28 = v44;
      LODWORD(v40) = 0;
      if ( HIDWORD(v61) )
        v28 = 1;
      v44 = v28;
    }
    else if ( (unsigned int)pSetupStringTableLookUpStringEx(*(_QWORD *)(a4 + 120), v11, 0, &v50, 8) == -1 )
    {
      v41 = 0;
      LODWORD(v40) = 0;
    }
    else
    {
      LODWORD(v40) = HIDWORD(v50);
      v41 = v50;
    }
    memset_0(v65, 0, sizeof(v65));
    v29 = *(_QWORD *)(a4 + 112);
    v64[1] = v41;
    v64[2] = v40;
    v64[3] = v42;
    v64[4] = v47;
    v70 = v48;
    v64[6] = v43;
    v64[7] = v45;
    v66 = v51;
    v67 = v49;
    v68 = v44;
    v69 = v44;
    v64[0] = v20;
    v64[5] = v16;
    v71 = 0;
    v72 = -1;
    v73 = Buf1[0];
    LODWORD(v35) = 160;
    v30 = pSetupStringTableAddStringEx(v29, v11, 4, v64, v35);
    if ( v30 != -1 )
    {
      v13 = v52;
      if ( !v52 )
        goto LABEL_10;
      memset_0(&v54, 0, 0x88u);
      v31 = v80;
      v56 = v76;
      v32 = 2147483646;
      v57 = v77;
      v58 = v45;
      v33 = &v59;
      v55 = v30;
      v54 = v11;
      do
      {
        if ( !v32 )
          break;
        if ( !*v31 )
          break;
        *v33++ = *v31++;
        --v32;
        --v23;
      }
      while ( v23 );
      v34 = v33 - 1;
      if ( v23 )
        v34 = v33;
      *v34 = 0;
      if ( !v23 )
        v59 = 0;
      v60 = a4;
      if ( (unsigned int)DriverPackageEnumDriversW(v13, 0, EnumDriverNodeCallback, &v54) )
      {
        v17 = *(_DWORD *)a4;
        if ( !*(_DWORD *)a4 )
          goto LABEL_87;
        v18 = "Failed to enumerate devices for driver package %ws (%ws), returned Err = 0x%lx";
      }
      else
      {
        v17 = GetLastError();
        v18 = "Failed to enumerate devices for driver package %ws (%ws), Err = 0x%lx";
      }
      v8 = v17;
      goto LABEL_86;
    }
    v8 = 8;
    LODWORD(v36) = 8;
    (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a4 + 40))(
      *(_QWORD *)(a4 + 48),
      1,
      0,
      "Failed to add INF to StrTabDriverStoreInfs string table, Err = 0x%lx",
      v36);
    goto LABEL_70;
  }
  v8 = 87;
  return v8 == 0;
}

```

## disassembly

```asm
0x180005bd0  push    rbp
0x180005bd2  push    rbx
0x180005bd3  push    rsi
0x180005bd4  push    rdi
0x180005bd5  push    r12
0x180005bd7  push    r13
0x180005bd9  push    r14
0x180005bdb  push    r15
0x180005bdd  lea     rbp, [rsp-0A68h]
0x180005be5  sub     rsp, 0B68h
0x180005bec  mov     rax, cs:__security_cookie
0x180005bf3  xor     rax, rsp
0x180005bf6  mov     [rbp+0AA0h+var_50], rax
0x180005bfd  mov     r15, r8
0x180005c00  mov     [rsp+0BA0h+var_B48], rcx
0x180005c05  mov     rsi, rdx
0x180005c08  mov     r12, rcx
0x180005c0b  xor     edx, edx; Val
0x180005c0d  lea     rcx, [rbp+0AA0h+var_9A0]; void *
0x180005c14  mov     r8d, 6F0h; Size
0x180005c1a  mov     rbx, r9
0x180005c1d  call    memset_0
0x180005c22  xor     r14d, r14d
0x180005c25  lea     rcx, [rbp+0AA0h+var_AF0]; void *
0x180005c29  xorps   xmm0, xmm0
0x180005c2c  mov     [rsp+0BA0h+var_B50], r14d
0x180005c31  xor     edx, edx; Val
0x180005c33  mov     [rsp+0BA0h+var_B2C], r14d
0x180005c38  mov     r8d, 88h; Size
0x180005c3e  mov     [rbp+0AA0h+var_B10], r14
0x180005c42  movups  [rbp+0AA0h+var_B00], xmm0
0x180005c46  mov     [rsp+0BA0h+var_B4C], r14b
0x180005c4b  call    memset_0
0x180005c50  xor     eax, eax
0x180005c52  mov     [rbp+0AA0h+var_B18], r14
0x180005c56  xor     edx, edx; Val
0x180005c58  mov     [rbp+0AA0h+var_A60], rax
0x180005c5c  mov     r8d, 0A0h; Size
0x180005c62  mov     [rbp+0AA0h+var_A58], eax
0x180005c65  lea     rcx, [rbp+0AA0h+var_A40]; void *
0x180005c69  mov     [rbp+0AA0h+var_B20], r14d
0x180005c6d  call    memset_0
0x180005c72  xorps   xmm0, xmm0
0x180005c75  movups  [rbp+0AA0h+var_A50], xmm0
0x180005c79  test    r15, r15
0x180005c7c  jnz     short loc_180005C88
0x180005c7e  mov     edi, 57h ; 'W'
0x180005c83  jmp     loc_180005D55
0x180005c88  test    rbx, rbx
0x180005c8b  jz      short loc_180005C7E
0x180005c8d  mov     rcx, rbx
0x180005c90  call    PnpCleanDriversNotifyCallback
0x180005c95  test    eax, eax
0x180005c97  jnz     short loc_180005CA3
0x180005c99  mov     edi, 4C7h
0x180005c9e  jmp     loc_180005D53
0x180005ca3  mov     rcx, [rbx+30h]
0x180005ca7  lea     r9, aProcessingWs; "Processing %ws"
0x180005cae  mov     rax, [rbx+28h]
0x180005cb2  xor     r8d, r8d
0x180005cb5  mov     edi, r14d
0x180005cb8  mov     [rsp+0BA0h+var_B24], r14d
0x180005cbd  lea     r14, [r15+0ACh]
0x180005cc4  mov     [rsp+0BA0h+var_B80], r14
0x180005cc9  lea     edx, [r8+6]
0x180005ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd2  mov     rax, cs:__imp_DriverStoreDriverPackageResolveCallbackW
0x180005cd9  xor     r9d, r9d
0x180005cdc  movzx   edx, word ptr [r15]
0x180005ce0  xor     r8d, r8d
0x180005ce3  mov     qword ptr [rbp+0AA0h+var_B00], rax
0x180005ce7  mov     rcx, rsi
0x180005cea  lea     rax, [rbp+0AA0h+var_B00]
0x180005cee  mov     qword ptr [rbp+0AA0h+var_B00+8], r12
0x180005cf2  mov     [rsp+0BA0h+var_B80], rax
0x180005cf7  call    cs:__imp_DriverPackageOpenW
0x180005cfd  mov     [rbp+0AA0h+var_B08], rax
0x180005d01  mov     r13, rax
0x180005d04  mov     r12d, 1
0x180005d0a  test    rax, rax
0x180005d0d  jnz     loc_180005DAE
0x180005d13  call    cs:__imp_GetLastError
0x180005d19  cmp     eax, 0E0000003h
0x180005d1e  jz      short loc_180005D80
0x180005d20  lea     ecx, [rax-2]
0x180005d23  cmp     ecx, r12d
0x180005d26  jbe     short loc_180005D80
0x180005d28  mov     rcx, [rbx+30h]
0x180005d2c  lea     r9, aFailedToOpenDr; "Failed to open driver package %ws (%ws)"...
0x180005d33  mov     dword ptr [rsp+0BA0h+var_B70], eax
0x180005d37  xor     r8d, r8d
0x180005d3a  mov     rax, [rbx+28h]
0x180005d3e  mov     edx, r12d
0x180005d41  mov     [rsp+0BA0h+var_B78], rsi
0x180005d46  mov     [rsp+0BA0h+var_B80], r14
0x180005d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d50  xor     r14d, r14d
0x180005d53  mov     [rbx], edi
0x180005d55  test    edi, edi
0x180005d57  mov     eax, r14d
0x180005d5a  setz    al
0x180005d5d  mov     rcx, [rbp+0AA0h+var_50]
0x180005d64  xor     rcx, rsp; StackCookie
0x180005d67  call    __security_check_cookie
0x180005d6c  add     rsp, 0B68h
0x180005d73  pop     r15
0x180005d75  pop     r14
0x180005d77  pop     r13
0x180005d79  pop     r12
0x180005d7b  pop     rdi
0x180005d7c  pop     rsi
0x180005d7d  pop     rbx
0x180005d7e  pop     rbp
0x180005d7f  retn
0x180005d80  mov     rcx, [rbx+30h]
0x180005d84  lea     r9, aDriverPackageW; "Driver package %ws (%ws) missing or cor"...
0x180005d8b  mov     dword ptr [rsp+0BA0h+var_B70], eax
0x180005d8f  xor     r8d, r8d
0x180005d92  mov     rax, [rbx+28h]
0x180005d96  mov     [rsp+0BA0h+var_B78], rsi
0x180005d9b  mov     [rsp+0BA0h+var_B80], r14
0x180005da0  lea     edx, [r8+2]
0x180005da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da9  mov     [rsp+0BA0h+var_B24], r12d
0x180005dae  xor     edx, edx; Val
0x180005db0  mov     [rsp+0BA0h+var_B38], edi
0x180005db4  mov     r8d, 6ECh; Size
0x180005dba  lea     rcx, [rbp+0AA0h+var_99C]; void *
0x180005dc1  xor     r12d, r12d
0x180005dc4  call    memset_0
0x180005dc9  mov     [rbp+0AA0h+var_9A0], 6F0h
0x180005dd3  test    r13, r13
0x180005dd6  jz      loc_180005EB8
0x180005ddc  lea     rdx, [rbp+0AA0h+var_9A0]
0x180005de3  mov     rcx, r13
0x180005de6  call    cs:__imp_DriverPackageGetVersionInfoW
0x180005dec  test    eax, eax
0x180005dee  jnz     short loc_180005E07
0x180005df0  call    cs:__imp_GetLastError
0x180005df6  lea     r9, aFailedToGetDri; "Failed to get driver package version in"...
0x180005dfd  lea     edx, [r12+1]
0x180005e02  jmp     loc_180006458
0x180005e07  mov     r12d, [rbp+0AA0h+var_2B4]
0x180005e0e  mov     eax, 1
0x180005e13  test    al, r12b
0x180005e16  jnz     short loc_180005E75
0x180005e18  mov     rcx, [rsp+0BA0h+var_B48]
0x180005e1d  lea     r9, DEVPKEY_DriverPackage_Primitive
0x180005e24  mov     [rsp+0BA0h+var_B60], edi
0x180005e28  mov     r8, rsi
0x180005e2b  mov     [rsp+0BA0h+var_B68], rdi
0x180005e30  mov     edx, 2
0x180005e35  mov     dword ptr [rsp+0BA0h+var_B70], eax
0x180005e39  lea     rax, [rsp+0BA0h+var_B4C]
0x180005e3e  mov     [rsp+0BA0h+var_B78], rax
0x180005e43  lea     rax, [rsp+0BA0h+var_B50]
0x180005e48  mov     [rsp+0BA0h+var_B80], rax
0x180005e4d  call    cs:__imp_DriverStoreGetObjectPropertyW
0x180005e53  test    eax, eax
0x180005e55  jz      short loc_180005ECE
0x180005e57  cmp     [rsp+0BA0h+var_B50], 11h
0x180005e5c  jnz     short loc_180005ECE
0x180005e5e  cmp     [rsp+0BA0h+var_B4C], 0FFh
0x180005e63  jnz     short loc_180005ECE
0x180005e65  mov     r12d, [rbp+0AA0h+var_2B4]
0x180005e6c  mov     eax, 1
0x180005e71  mov     [rsp+0BA0h+var_B38], eax
0x180005e75  shr     r12d, 4
0x180005e79  lea     rdx, GUID_DEVCLASS_DISPLAY; Buf2
0x180005e80  mov     r8d, 10h; Size
0x180005e86  lea     rcx, [rbp+0AA0h+Buf1]; Buf1
0x180005e8d  and     r12d, eax
0x180005e90  call    memcmp_0
0x180005e95  test    eax, eax
0x180005e97  jnz     short loc_180005EB8
0x180005e99  xor     edx, edx
0x180005e9b  lea     rax, [rbp+0AA0h+var_B20]
0x180005e9f  lea     r9, EnumWdfClassExtensionsCallback
0x180005ea6  mov     [rsp+0BA0h+var_B80], rax
0x180005eab  mov     rcx, r13
0x180005eae  lea     r8d, [rdx+11h]
0x180005eb2  call    cs:__imp_DriverPackageEnumRegKeysW
0x180005eb8  mov     eax, 1
0x180005ebd  test    [r15+2B4h], al
0x180005ec4  jz      short loc_180005EF8
0x180005ec6  mov     r13d, eax
0x180005ec9  jmp     loc_180005FBF
0x180005ece  mov     rcx, [rbx+30h]
0x180005ed2  lea     r9, aInfWsWsHasNoDr; "INF %ws (%ws) has no drivers, skipping "...
0x180005ed9  mov     rax, [rbx+28h]
0x180005edd  xor     r8d, r8d
0x180005ee0  mov     [rsp+0BA0h+var_B78], rsi
0x180005ee5  mov     [rsp+0BA0h+var_B80], r14
0x180005eea  lea     edx, [r8+3]
0x180005eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef3  jmp     loc_180006476
0x180005ef8  mov     rcx, [rsp+0BA0h+var_B48]
0x180005efd  lea     rax, [rbp+0AA0h+String]
0x180005f04  mov     [rsp+0BA0h+var_B60], edi
0x180005f08  lea     r9, DEVPKEY_DriverPackage_SourceMediaPath
0x180005f0f  mov     [rsp+0BA0h+var_B68], rdi
0x180005f14  mov     r8, rsi
0x180005f17  mov     dword ptr [rsp+0BA0h+var_B70], 208h
0x180005f1f  mov     edx, 2
0x180005f24  mov     [rsp+0BA0h+var_B78], rax
0x180005f29  lea     rax, [rsp+0BA0h+var_B50]
0x180005f2e  mov     [rsp+0BA0h+var_B80], rax
0x180005f33  call    cs:__imp_DriverStoreGetObjectPropertyW
0x180005f39  test    eax, eax
0x180005f3b  jz      short loc_180005FBC
0x180005f3d  cmp     [rsp+0BA0h+var_B50], 12h
0x180005f42  jnz     short loc_180005FBC
0x180005f44  xor     eax, eax
0x180005f46  lea     rcx, [rbp+0AA0h+String]; String
0x180005f4d  mov     [rbp+0AA0h+var_5A], ax
0x180005f54  call    cs:__imp__wcslwr
0x180005f5a  lea     rdx, aSoftwaredistri; "\\softwaredistribution\\download\\"
0x180005f61  lea     rcx, [rbp+0AA0h+String]; Str
0x180005f68  call    cs:__imp_wcsstr
0x180005f6e  test    rax, rax
0x180005f71  jz      short loc_180005F7B
0x180005f73  mov     r13d, 3
0x180005f79  jmp     short loc_180005FBF
0x180005f7b  lea     rdx, aMicrosoftWindo; "\\microsoft\\windows\\devicesoftwareupd"...
0x180005f82  lea     rcx, [rbp+0AA0h+String]; Str
0x180005f89  call    cs:__imp_wcsstr
0x180005f8f  test    rax, rax
0x180005f92  jz      short loc_180005F9C
0x180005f94  mov     r13d, 4
0x180005f9a  jmp     short loc_180005FBF
0x180005f9c  lea     rdx, aProgramFiles; "\\program files"
0x180005fa3  lea     rcx, [rbp+0AA0h+String]; Str
0x180005faa  call    cs:__imp_wcsstr
0x180005fb0  neg     rax
0x180005fb3  sbb     r13d, r13d
0x180005fb6  add     r13d, 6
0x180005fba  jmp     short loc_180005FBF
0x180005fbc  xor     r13d, r13d
0x180005fbf  mov     rcx, [rsp+0BA0h+var_B48]
0x180005fc4  lea     r9, DEVPKEY_DriverPackage_LockLevel
0x180005fcb  xor     eax, eax
0x180005fcd  xor     r15d, r15d
0x180005fd0  mov     [rsp+0BA0h+var_B60], eax
0x180005fd4  mov     r8, rsi
0x180005fd7  mov     [rsp+0BA0h+var_B68], rax
0x180005fdc  mov     [rsp+0BA0h+var_B3C], eax
0x180005fe0  lea     rax, [rsp+0BA0h+var_B2C]
0x180005fe5  mov     dword ptr [rsp+0BA0h+var_B70], 4
0x180005fed  lea     edx, [r15+2]
0x180005ff1  mov     [rsp+0BA0h+var_B78], rax
0x180005ff6  lea     rax, [rsp+0BA0h+var_B50]
0x180005ffb  mov     [rsp+0BA0h+var_B80], rax
0x180006000  mov     [rsp+0BA0h+var_B28], r15d
0x180006005  call    cs:__imp_DriverStoreGetObjectPropertyW
0x18000600b  xor     ecx, ecx
0x18000600d  test    eax, eax
0x18000600f  jz      short loc_180006021
0x180006011  cmp     [rsp+0BA0h+var_B50], 7
0x180006016  mov     eax, ecx
0x180006018  cmovz   eax, [rsp+0BA0h+var_B2C]
0x18000601d  mov     [rsp+0BA0h+var_B3C], eax
0x180006021  mov     [rsp+0BA0h+var_B60], ecx
0x180006025  lea     rax, [rsp+0BA0h+var_B50]
0x18000602a  mov     [rsp+0BA0h+var_B68], rcx
0x18000602f  lea     r9, DEVPKEY_DriverPackage_DriverSetIds
0x180006036  mov     dword ptr [rsp+0BA0h+var_B70], ecx
0x18000603a  mov     r8, rsi
0x18000603d  mov     [rsp+0BA0h+var_B78], rcx
0x180006042  mov     edx, 2
0x180006047  mov     rcx, [rsp+0BA0h+var_B48]
0x18000604c  mov     [rsp+0BA0h+var_B80], rax
0x180006051  call    cs:__imp_DriverStoreGetObjectPropertyW
0x180006057  test    eax, eax
0x180006059  jnz     short loc_18000607C
0x18000605b  call    cs:__imp_GetLastError
0x180006061  cmp     eax, 7Ah ; 'z'
0x180006064  jnz     short loc_18000607C
0x180006066  cmp     [rsp+0BA0h+var_B50], 100Dh
0x18000606e  mov     eax, 1
0x180006073  cmovz   r15d, eax
0x180006077  mov     [rsp+0BA0h+var_B28], r15d
0x18000607c  xor     eax, eax
0x18000607e  lea     rdx, GUID_DEVCLASS_EXTENSION; Buf2
0x180006085  lea     rcx, [rbp+0AA0h+Buf1]; Buf1
0x18000608c  mov     [rbp+0AA0h+var_2B0], ax
0x180006093  lea     r8d, [rax+10h]; Size
0x180006097  call    memcmp_0
0x18000609c  xor     ecx, ecx
0x18000609e  lea     r15d, [rcx+27h]
0x1800060a2  test    eax, eax
0x1800060a4  jnz     loc_18000614E
0x1800060aa  mov     [rsp+0BA0h+var_B60], ecx
0x1800060ae  lea     rax, [rbp+0AA0h+var_A50]
0x1800060b2  mov     [rsp+0BA0h+var_B68], rcx
0x1800060b7  lea     edx, [rcx+2]
0x1800060ba  mov     rcx, [rsp+0BA0h+var_B48]
0x1800060bf  lea     r9, DEVPKEY_DriverPackage_ExtensionId
0x1800060c6  mov     dword ptr [rsp+0BA0h+var_B70], 10h
0x1800060ce  mov     r8, rsi
0x1800060d1  mov     [rsp+0BA0h+var_B78], rax
  ... truncated ...
```
