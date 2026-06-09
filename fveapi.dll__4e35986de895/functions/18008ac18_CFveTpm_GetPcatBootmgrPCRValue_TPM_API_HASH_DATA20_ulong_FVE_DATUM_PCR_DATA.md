# CFveTpm::GetPcatBootmgrPCRValue(_TPM_API_HASH_DATA20 *,ulong *,_FVE_DATUM_PCR_DATA * *)

- ea: `0x18008ac18`
- end: `0x18008b51b`
- name: `?GetPcatBootmgrPCRValue@CFveTpm@@IEAAJPEAU_TPM_API_HASH_DATA20@@PEAKPEAPEAU_FVE_DATUM_PCR_DATA@@@Z`
- size: `2307`
- prototype: `__int64 __fastcall(CFveTpm *__hidden this, struct _TPM_API_HASH_DATA20 *, unsigned int *, struct _FVE_DATUM_PCR_DATA **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update`

## callers

- `0x18008bc3c`

## callees

- `0x180005410`
- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x18000aae0`
- `0x18000ba30`
- `0x180018b10`
- `0x180019128`
- `0x18001b260`
- `0x180039824`
- `0x18003e98c`
- `0x18003f064`
- `0x18004dba8`
- `0x18008ac18`
- `0x180098d68`
- `0x18009befc`
- `0x180119068`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b48d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b4a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180124561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012457f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b48d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b4a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180124561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012457f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008af71`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008af71`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008af00`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008af00`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18008b022`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18008b022`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18008b09f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18008b09f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18008b472`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180124544`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18008b472`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180124544`
- `bcd!BcdCloseObject` at `0x18008b43b`
- `bcd!BcdCloseObject` at `0x18012451b`
- `bcd!BcdCloseObject` at `0x18008b43b`
- `bcd!BcdCloseObject` at `0x18012451b`
- `bcd!BcdOpenObject` at `0x18008add0`
- `bcd!BcdOpenObject` at `0x18008add0`
- `bcd!BcdCloseStore` at `0x18008b452`
- `bcd!BcdCloseStore` at `0x18012452e`
- `bcd!BcdCloseStore` at `0x18008b452`
- `bcd!BcdCloseStore` at `0x18012452e`
- `bcd!BcdOpenSystemStore` at `0x18008ad63`
- `bcd!BcdOpenSystemStore` at `0x18008ad63`

## pseudocode

```c
__int64 __fastcall CFveTpm::GetPcatBootmgrPCRValue(
        CFveTpm *this,
        struct _TPM_API_HASH_DATA20 *a2,
        unsigned int *a3,
        struct _FVE_DATUM_PCR_DATA **a4)
{
  __int64 v7; // rdx
  int v8; // eax
  int BcdElementData; // eax
  __int64 v10; // rdx
  int v11; // ebx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  HANDLE FileW; // rax
  void *v16; // rsi
  unsigned int LastHresultError; // eax
  __int64 v18; // rdx
  HANDLE FileMappingW; // rax
  void *v20; // r15
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int16 v23; // ax
  const WCHAR *v24; // r15
  __int64 v25; // rsi
  unsigned int *v26; // rsi
  int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-3D8h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-3D0h]
  HANDLE v33; // [rsp+58h] [rbp-3A0h]
  __int64 v34; // [rsp+60h] [rbp-398h]
  __int16 v35; // [rsp+68h] [rbp-390h] BYREF
  void *lpMem; // [rsp+70h] [rbp-388h] BYREF
  LPCVOID lpBaseAddress; // [rsp+78h] [rbp-380h]
  struct _FVE_DATUM_PCR_DATA *v38; // [rsp+80h] [rbp-378h] BYREF
  unsigned int v39; // [rsp+88h] [rbp-370h] BYREF
  int v40; // [rsp+8Ch] [rbp-36Ch] BYREF
  unsigned int *v41; // [rsp+90h] [rbp-368h]
  struct _TPM_API_HASH_DATA20 *v42; // [rsp+98h] [rbp-360h]
  CFveTpm *v43; // [rsp+A0h] [rbp-358h]
  struct _TPM_API_HASH_DATA20 *v44; // [rsp+A8h] [rbp-350h] BYREF
  WCHAR *v45; // [rsp+B0h] [rbp-348h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-340h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+C0h] [rbp-338h] BYREF
  void *v48; // [rsp+C8h] [rbp-330h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+D0h] [rbp-328h] BYREF
  _BYTE v50[64]; // [rsp+E0h] [rbp-318h] BYREF
  _BYTE v51[128]; // [rsp+120h] [rbp-2D8h] BYREF
  WCHAR FileName[264]; // [rsp+1A0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  v41 = a3;
  v42 = a2;
  v43 = this;
  phHash[0] = 0;
  memset_0(FileName, 0, 0x208u);
  FileSize.QuadPart = 0;
  memset_0(v50, 0, sizeof(v50));
  memset_0(v51, 0, sizeof(v51));
  v46 = 0;
  v48 = 0;
  v38 = 0;
  v40 = 12;
  v45 = FileName;
  v44 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 292, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
  lpBaseAddress = 0;
  v34 = -1;
  v33 = 0;
  v46 = 0;
  v48 = 0;
  lpMem = 0;
  v39 = 0;
  v35 = 1;
  if ( a4 )
    *a4 = 0;
  v8 = BcdOpenSystemStore(&v46, v7);
  BcdElementData = FromNtStatus(v8);
  v11 = BcdElementData;
  if ( BcdElementData < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_82;
    v13 = 293;
    goto LABEL_10;
  }
  v14 = BcdOpenObject(v46, &GUID_WINDOWS_BOOTMGR, &v48);
  BcdElementData = FromNtStatus(v14);
  v11 = BcdElementData;
  if ( BcdElementData < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_82;
    v13 = 294;
    goto LABEL_10;
  }
  BcdElementData = CFveApiBase::GetBcdElementData(v48, 0x11000001u, &lpMem, &v39);
  v11 = BcdElementData;
  if ( BcdElementData < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_82;
    v13 = 295;
LABEL_10:
    WPP_SF_d(v12[2], v13, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned int)BcdElementData);
LABEL_11:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_82;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      296,
      &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
      (char *)lpMem + 20);
  v11 = StringCchPrintfW(FileName, 0x104u, L"\\\\?\\GLOBALROOT%s\\bootmgr", (char *)lpMem + 20);
  if ( v11 < 0 )
    goto LABEL_11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 297, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, FileName);
  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v16 = FileW;
  v34 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastHresultError = GetLastHresultError();
    v11 = LastHresultError;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v18 = 298;
    goto LABEL_32;
  }
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    LastHresultError = GetLastHresultError();
    v11 = LastHresultError;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v18 = 299;
LABEL_32:
    WPP_SF_d(v12[2], v18, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, LastHresultError);
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_83:
    v20 = v33;
    goto LABEL_84;
  }
  if ( FileSize.HighPart )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_LI(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = -2147418113;
    goto LABEL_83;
  }
  FileMappingW = CreateFileMappingW(v16, 0, 2u, 0, FileSize.LowPart, 0);
  v20 = FileMappingW;
  v33 = FileMappingW;
  if ( !FileMappingW )
  {
    v21 = GetLastHresultError();
    v11 = v21;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v22 = 301;
LABEL_46:
      WPP_SF_d(v12[2], v22, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v21);
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_84;
    }
    goto LABEL_84;
  }
  lpBaseAddress = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  if ( lpBaseAddress )
  {
    v23 = *((_WORD *)this + 832);
    if ( v23 == 4 )
    {
      v24 = L"SHA1";
      v25 = 20;
    }
    else
    {
      if ( v23 != 11 )
      {
        v11 = -2147467263;
        v12 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_84;
      }
      v24 = L"SHA256";
      v25 = 32;
    }
    v11 = TpmApiShaInit(v24, phHash);
    if ( v11 < 0 )
      goto LABEL_11;
    v11 = TpmApiShaUpdate(phHash, lpBaseAddress, FileSize.LowPart);
    if ( v11 < 0 )
      goto LABEL_11;
    v11 = TpmApiShaFinal(phHash, v50, v25);
    if ( v11 < 0 )
      goto LABEL_11;
    v11 = TpmApiShaInit(v24, phHash);
    if ( v11 < 0 )
      goto LABEL_11;
    v11 = TpmApiShaUpdate(phHash, v50, v25);
    if ( v11 < 0 )
      goto LABEL_11;
    v11 = TpmApiShaFinal(phHash, &v51[v25], v25);
    if ( v11 < 0 )
      goto LABEL_11;
    v11 = TpmApiShaInit(v24, phHash);
    if ( v11 < 0 )
      goto LABEL_11;
    v11 = TpmApiShaUpdate(phHash, v51, 2 * v25);
    if ( v11 < 0 )
      goto LABEL_11;
    v11 = TpmApiShaFinal(phHash, (char *)v42 + 4, v25);
    if ( v11 < 0 )
      goto LABEL_11;
    if ( *((_DWORD *)v43 + 15) == 2 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      v26 = v41;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 303, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, *v41);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (*v26 & 0x400) == 0 )
      {
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
          WPP_SF_d(v12[2], 304, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, 10);
        v11 = -1070530280;
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x13C3,
          (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
          (const char *)0xC0310118LL,
          (int)"PPF event log based predicted values do not match PCR values",
          dwFlagsAndAttributes);
        goto LABEL_73;
      }
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !a4 )
      goto LABEL_82;
    v27 = FveDatumPcrDataCreateFromTpmHashData(
            (unsigned int)&v35,
            v10,
            10,
            1,
            dwCreationDisposition,
            (__int64)&v40,
            (__int64)&v45,
            (__int64)&v44,
            (__int64)&v38);
    v28 = FromNtStatus(v27);
    v11 = v28;
    if ( v28 >= 0 )
    {
      v11 = 0;
      *a4 = v38;
      v38 = 0;
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_82;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        305,
        &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
        (unsigned int)v28);
    }
LABEL_73:
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_82:
    v16 = (void *)v34;
    goto LABEL_83;
  }
  v21 = GetLastHresultError();
  v11 = v21;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v22 = 302;
    goto LABEL_46;
  }
LABEL_84:
  if ( lpMem )
  {
    CFveApiBase::FastFree(lpMem);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  v29 = v46;
  if ( v46 )
  {
    if ( v48 )
    {
      BcdCloseObject(v48);
      v29 = v46;
    }
    BcdCloseStore(v29, v10);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpBaseAddress )
  {
    UnmapViewOfFile(lpBaseAddress);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v20 )
  {
    CloseHandle(v20);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v16 != (void *)-1LL )
  {
    CloseHandle(v16);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v38 )
  {
    FveDatumFree(v38);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
    WPP_SF_d(v12[2], 306, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18008ac18  push    rbx
0x18008ac1a  push    rsi
0x18008ac1b  push    rdi
0x18008ac1c  push    r12
0x18008ac1e  push    r13
0x18008ac20  push    r15
0x18008ac22  sub     rsp, 3C8h
0x18008ac29  mov     rax, cs:__security_cookie
0x18008ac30  xor     rax, rsp
0x18008ac33  mov     [rsp+3F8h+var_48], rax
0x18008ac3b  mov     r13, r9
0x18008ac3e  mov     [rsp+3F8h+var_368], r8
0x18008ac46  mov     rbx, rdx
0x18008ac49  mov     [rsp+3F8h+var_360], rdx
0x18008ac51  mov     r12, rcx
0x18008ac54  mov     [rsp+3F8h+var_358], rcx
0x18008ac5c  xor     r15d, r15d
0x18008ac5f  mov     [rsp+3F8h+phHash], r15
0x18008ac67  xor     edx, edx; Val
0x18008ac69  mov     r8d, 208h; Size
0x18008ac6f  lea     rcx, [rsp+3F8h+FileName]; void *
0x18008ac77  call    memset_0
0x18008ac7c  mov     qword ptr [rsp+3F8h+FileSize], r15
0x18008ac84  xor     edx, edx; Val
0x18008ac86  lea     r8d, [r15+40h]; Size
0x18008ac8a  lea     rcx, [rsp+3F8h+var_318]; void *
0x18008ac92  call    memset_0
0x18008ac97  xor     edx, edx; Val
0x18008ac99  mov     r8d, 80h; Size
0x18008ac9f  lea     rcx, [rsp+3F8h+var_2D8]; void *
0x18008aca7  call    memset_0
0x18008acac  mov     [rsp+3F8h+var_340], r15
0x18008acb4  mov     [rsp+3F8h+var_330], r15
0x18008acbc  mov     [rsp+3F8h+var_378], r15
0x18008acc4  mov     [rsp+3F8h+var_36C], 0Ch
0x18008accf  lea     rax, [rsp+3F8h+FileName]
0x18008acd7  mov     [rsp+3F8h+var_348], rax
0x18008acdf  mov     [rsp+3F8h+var_350], rbx
0x18008ace7  lea     rsi, WPP_GLOBAL_Control
0x18008acee  mov     rcx, cs:WPP_GLOBAL_Control
0x18008acf5  lea     rdi, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x18008acfc  cmp     rcx, rsi
0x18008acff  jz      short loc_18008AD18
0x18008ad01  test    byte ptr [rcx+1Ch], 10h
0x18008ad05  jz      short loc_18008AD18
0x18008ad07  mov     edx, 124h
0x18008ad0c  mov     r8, rdi
0x18008ad0f  mov     rcx, [rcx+10h]
0x18008ad13  call    WPP_SF_
0x18008ad18  mov     [rsp+3F8h+lpBaseAddress], r15
0x18008ad1d  mov     [rsp+3F8h+var_398], 0FFFFFFFFFFFFFFFFh
0x18008ad26  mov     [rsp+3F8h+var_3A0], r15
0x18008ad2b  mov     [rsp+3F8h+var_340], r15
0x18008ad33  mov     [rsp+3F8h+var_330], r15
0x18008ad3b  mov     [rsp+3F8h+lpMem], r15
0x18008ad40  mov     [rsp+3F8h+var_370], r15d
0x18008ad48  mov     eax, 1
0x18008ad4d  mov     [rsp+3F8h+var_390], ax
0x18008ad52  test    r13, r13
0x18008ad55  jz      short loc_18008AD5B
0x18008ad57  mov     [r13+0], r15
0x18008ad5b  lea     rcx, [rsp+3F8h+var_340]
0x18008ad63  call    cs:__imp_BcdOpenSystemStore
0x18008ad6a  nop     dword ptr [rax+rax+00h]
0x18008ad6f  mov     ecx, eax; int
0x18008ad71  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18008ad76  mov     ebx, eax
0x18008ad78  mov     [rsp+3F8h+var_3A8], eax
0x18008ad7c  test    eax, eax
0x18008ad7e  jns     short loc_18008ADB9
0x18008ad80  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ad87  cmp     rcx, rsi
0x18008ad8a  jz      short loc_18008ADAD
0x18008ad8c  test    byte ptr [rcx+1Ch], 10h
0x18008ad90  jz      short loc_18008ADAD
0x18008ad92  mov     edx, 125h
0x18008ad97  mov     r9d, eax
0x18008ad9a  mov     r8, rdi
0x18008ad9d  mov     rcx, [rcx+10h]
0x18008ada1  call    WPP_SF_d
0x18008ada6  mov     rcx, cs:WPP_GLOBAL_Control
0x18008adad  lea     r12, WPP_GLOBAL_Control
0x18008adb4  jmp     loc_18008B3FE
0x18008adb9  lea     r8, [rsp+3F8h+var_330]
0x18008adc1  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18008adc8  mov     rcx, [rsp+3F8h+var_340]
0x18008add0  call    cs:__imp_BcdOpenObject
0x18008add7  nop     dword ptr [rax+rax+00h]
0x18008addc  mov     ecx, eax; int
0x18008adde  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18008ade3  mov     ebx, eax
0x18008ade5  mov     [rsp+3F8h+var_3A8], eax
0x18008ade9  test    eax, eax
0x18008adeb  jns     short loc_18008AE06
0x18008aded  mov     rcx, cs:WPP_GLOBAL_Control
0x18008adf4  cmp     rcx, rsi
0x18008adf7  jz      short loc_18008ADAD
0x18008adf9  test    byte ptr [rcx+1Ch], 10h
0x18008adfd  jz      short loc_18008ADAD
0x18008adff  mov     edx, 126h
0x18008ae04  jmp     short loc_18008AD97
0x18008ae06  lea     r9, [rsp+3F8h+var_370]; unsigned int *
0x18008ae0e  lea     r8, [rsp+3F8h+lpMem]; void **
0x18008ae13  mov     edx, 11000001h; unsigned int
0x18008ae18  mov     rcx, [rsp+3F8h+var_330]; void *
0x18008ae20  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18008ae25  mov     ebx, eax
0x18008ae27  mov     [rsp+3F8h+var_3A8], eax
0x18008ae2b  test    eax, eax
0x18008ae2d  jns     short loc_18008AE53
0x18008ae2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ae36  cmp     rcx, rsi
0x18008ae39  jz      loc_18008ADAD
0x18008ae3f  test    byte ptr [rcx+1Ch], 10h
0x18008ae43  jz      loc_18008ADAD
0x18008ae49  mov     edx, 127h
0x18008ae4e  jmp     loc_18008AD97
0x18008ae53  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ae5a  cmp     rcx, rsi
0x18008ae5d  jz      short loc_18008AE7F
0x18008ae5f  test    byte ptr [rcx+1Ch], 8
0x18008ae63  jz      short loc_18008AE7F
0x18008ae65  mov     r9, [rsp+3F8h+lpMem]
0x18008ae6a  add     r9, 14h
0x18008ae6e  mov     edx, 128h
0x18008ae73  mov     r8, rdi
0x18008ae76  mov     rcx, [rcx+10h]
0x18008ae7a  call    WPP_SF_S
0x18008ae7f  mov     r9, [rsp+3F8h+lpMem]
0x18008ae84  add     r9, 14h
0x18008ae88  lea     r8, aGlobalrootSBoo; "\\\\?\\GLOBALROOT%s\\bootmgr"
0x18008ae8f  mov     edx, 104h; unsigned __int64
0x18008ae94  lea     rcx, [rsp+3F8h+FileName]; unsigned __int16 *
0x18008ae9c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008aea1  mov     ebx, eax
0x18008aea3  mov     [rsp+3F8h+var_3A8], eax
0x18008aea7  test    eax, eax
0x18008aea9  js      loc_18008ADA6
0x18008aeaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18008aeb6  cmp     rcx, rsi
0x18008aeb9  jz      short loc_18008AEDA
0x18008aebb  test    byte ptr [rcx+1Ch], 8
0x18008aebf  jz      short loc_18008AEDA
0x18008aec1  mov     edx, 129h
0x18008aec6  lea     r9, [rsp+3F8h+FileName]
0x18008aece  mov     r8, rdi
0x18008aed1  mov     rcx, [rcx+10h]
0x18008aed5  call    WPP_SF_S
0x18008aeda  mov     [rsp+3F8h+hTemplateFile], r15; hTemplateFile
0x18008aedf  mov     [rsp+3F8h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18008aee4  mov     [rsp+3F8h+dwCreationDisposition], 3; dwCreationDisposition
0x18008aeec  xor     r9d, r9d; lpSecurityAttributes
0x18008aeef  mov     edx, 80000000h; dwDesiredAccess
0x18008aef4  lea     r8d, [r9+1]; dwShareMode
0x18008aef8  lea     rcx, [rsp+3F8h+FileName]; lpFileName
0x18008af00  call    cs:__imp_CreateFileW
0x18008af07  nop     dword ptr [rax+rax+00h]
0x18008af0c  mov     rsi, rax
0x18008af0f  mov     [rsp+3F8h+var_398], rax
0x18008af14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008af18  jnz     short loc_18008AF66
0x18008af1a  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18008af1f  mov     ebx, eax
0x18008af21  mov     [rsp+3F8h+var_3A8], eax
0x18008af25  mov     rcx, cs:WPP_GLOBAL_Control
0x18008af2c  lea     r12, WPP_GLOBAL_Control
0x18008af33  cmp     rcx, r12
0x18008af36  jz      loc_18008B403
0x18008af3c  test    byte ptr [rcx+1Ch], 10h
0x18008af40  jz      loc_18008B403
0x18008af46  mov     edx, 12Ah
0x18008af4b  mov     r9d, eax
0x18008af4e  mov     r8, rdi
0x18008af51  mov     rcx, [rcx+10h]
0x18008af55  call    WPP_SF_d
0x18008af5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008af61  jmp     loc_18008B403
0x18008af66  lea     rdx, [rsp+3F8h+FileSize]; lpFileSize
0x18008af6e  mov     rcx, rsi; hFile
0x18008af71  call    cs:__imp_GetFileSizeEx
0x18008af78  nop     dword ptr [rax+rax+00h]
0x18008af7d  test    eax, eax
0x18008af7f  jnz     short loc_18008AFB4
0x18008af81  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18008af86  mov     ebx, eax
0x18008af88  mov     [rsp+3F8h+var_3A8], eax
0x18008af8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008af93  lea     r12, WPP_GLOBAL_Control
0x18008af9a  cmp     rcx, r12
0x18008af9d  jz      loc_18008B403
0x18008afa3  test    byte ptr [rcx+1Ch], 10h
0x18008afa7  jz      loc_18008B403
0x18008afad  mov     edx, 12Bh
0x18008afb2  jmp     short loc_18008AF4B
0x18008afb4  mov     r9d, dword ptr [rsp+3F8h+FileSize+4]
0x18008afbc  test    r9d, r9d
0x18008afbf  jz      short loc_18008B005
0x18008afc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008afc8  lea     r12, WPP_GLOBAL_Control
0x18008afcf  cmp     rcx, r12
0x18008afd2  jz      short loc_18008AFF7
0x18008afd4  test    byte ptr [rcx+1Ch], 2
0x18008afd8  jz      short loc_18008AFF7
0x18008afda  mov     rax, qword ptr [rsp+3F8h+FileSize]
0x18008afe2  mov     qword ptr [rsp+3F8h+dwCreationDisposition], rax
0x18008afe7  mov     rcx, [rcx+10h]
0x18008afeb  call    WPP_SF_LI
0x18008aff0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008aff7  mov     ebx, 8000FFFFh
0x18008affc  mov     [rsp+3F8h+var_3A8], ebx
0x18008b000  jmp     loc_18008B403
0x18008b005  mov     qword ptr [rsp+3F8h+dwFlagsAndAttributes], r15; char *
0x18008b00a  mov     rax, qword ptr [rsp+3F8h+FileSize]
0x18008b012  mov     [rsp+3F8h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18008b016  xor     r9d, r9d; dwMaximumSizeHigh
0x18008b019  xor     edx, edx; lpFileMappingAttributes
0x18008b01b  lea     r8d, [r9+2]; flProtect
0x18008b01f  mov     rcx, rsi; hFile
0x18008b022  call    cs:__imp_CreateFileMappingW
0x18008b029  nop     dword ptr [rax+rax+00h]
0x18008b02e  mov     r15, rax
0x18008b031  mov     [rsp+3F8h+var_3A0], rax
0x18008b036  test    rax, rax
0x18008b039  jnz     short loc_18008B087
0x18008b03b  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18008b040  mov     ebx, eax
0x18008b042  mov     [rsp+3F8h+var_3A8], eax
0x18008b046  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b04d  lea     r12, WPP_GLOBAL_Control
0x18008b054  cmp     rcx, r12
0x18008b057  jz      loc_18008B408
0x18008b05d  test    byte ptr [rcx+1Ch], 10h
0x18008b061  jz      loc_18008B408
0x18008b067  mov     edx, 12Dh
0x18008b06c  mov     r9d, eax
0x18008b06f  mov     r8, rdi
0x18008b072  mov     rcx, [rcx+10h]
0x18008b076  call    WPP_SF_d
0x18008b07b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b082  jmp     loc_18008B408
0x18008b087  mov     qword ptr [rsp+3F8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18008b090  xor     r9d, r9d; dwFileOffsetLow
0x18008b093  xor     r8d, r8d; dwFileOffsetHigh
0x18008b096  lea     ebx, [r9+4]
0x18008b09a  mov     edx, ebx; dwDesiredAccess
0x18008b09c  mov     rcx, rax; hFileMappingObject
0x18008b09f  call    cs:__imp_MapViewOfFile
0x18008b0a6  nop     dword ptr [rax+rax+00h]
0x18008b0ab  mov     [rsp+3F8h+lpBaseAddress], rax
0x18008b0b0  test    rax, rax
0x18008b0b3  jnz     short loc_18008B0E8
0x18008b0b5  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18008b0ba  mov     ebx, eax
0x18008b0bc  mov     [rsp+3F8h+var_3A8], eax
0x18008b0c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b0c7  lea     r12, WPP_GLOBAL_Control
0x18008b0ce  cmp     rcx, r12
0x18008b0d1  jz      loc_18008B408
0x18008b0d7  test    byte ptr [rcx+1Ch], 10h
0x18008b0db  jz      loc_18008B408
0x18008b0e1  mov     edx, 12Eh
0x18008b0e6  jmp     short loc_18008B06C
0x18008b0e8  movzx   eax, word ptr [r12+680h]
0x18008b0f1  cmp     ax, bx
0x18008b0f4  jnz     short loc_18008B104
0x18008b0f6  lea     r15, aSha1_0; "SHA1"
0x18008b0fd  mov     esi, 14h
0x18008b102  jmp     short loc_18008B11A
0x18008b104  cmp     ax, 0Bh
0x18008b108  jnz     loc_18008B3E5
0x18008b10e  lea     r15, pszAlgId; "SHA256"
0x18008b115  mov     esi, 20h ; ' '
0x18008b11a  add     r12, 678h
0x18008b121  mov     r8, r12
0x18008b124  lea     rdx, [rsp+3F8h+phHash]; phHash
0x18008b12c  mov     rcx, r15; pszAlgId
0x18008b12f  call    TpmApiShaInit
0x18008b134  mov     ebx, eax
0x18008b136  mov     [rsp+3F8h+var_3A8], eax
0x18008b13a  test    eax, eax
0x18008b13c  js      loc_18008ADA6
0x18008b142  mov     r8d, dword ptr [rsp+3F8h+FileSize]
0x18008b14a  mov     rdx, [rsp+3F8h+lpBaseAddress]
0x18008b14f  lea     rcx, [rsp+3F8h+phHash]
0x18008b157  call    TpmApiShaUpdate
0x18008b15c  mov     ebx, eax
0x18008b15e  mov     [rsp+3F8h+var_3A8], eax
0x18008b162  test    eax, eax
0x18008b164  js      loc_18008ADA6
0x18008b16a  mov     r8, rsi
0x18008b16d  lea     rdx, [rsp+3F8h+var_318]
0x18008b175  lea     rcx, [rsp+3F8h+phHash]
0x18008b17d  call    TpmApiShaFinal
0x18008b182  mov     ebx, eax
0x18008b184  mov     [rsp+3F8h+var_3A8], eax
0x18008b188  test    eax, eax
0x18008b18a  js      loc_18008ADA6
0x18008b190  mov     r8, r12
0x18008b193  lea     rdx, [rsp+3F8h+phHash]; phHash
0x18008b19b  mov     rcx, r15; pszAlgId
  ... truncated ...
```
