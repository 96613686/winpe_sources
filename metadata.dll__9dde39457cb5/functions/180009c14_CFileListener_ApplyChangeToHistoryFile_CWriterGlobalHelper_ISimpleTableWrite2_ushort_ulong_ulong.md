# CFileListener::ApplyChangeToHistoryFile(CWriterGlobalHelper *,ISimpleTableWrite2 *,ushort *,ulong,ulong)

- ea: `0x180009c14`
- end: `0x18000a522`
- name: `?ApplyChangeToHistoryFile@CFileListener@@AEAAJPEAVCWriterGlobalHelper@@PEAUISimpleTableWrite2@@PEAGKK@Z`
- size: `2318`
- prototype: `__int64 __fastcall(CFileListener *this, struct CWriterGlobalHelper *, struct ISimpleTableWrite2 *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000d680`

## callees

- `0x1800089c8`
- `0x180008a08`
- `0x180009b80`
- `0x180009c14`
- `0x18000c374`
- `0x18000c4f4`
- `0x18000cb28`
- `0x18001c21c`
- `0x18001c508`
- `0x18002d4fc`
- `0x18002d788`
- `0x18002db80`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a058`
- `msvcrt!_wcsicmp` at `0x18000a0dd`
- `msvcrt!_wcsicmp` at `0x18000a058`
- `msvcrt!_wcsicmp` at `0x18000a0dd`
- `msvcrt!wcsstr` at `0x18000a1ae`
- `msvcrt!wcsstr` at `0x18000a215`
- `msvcrt!wcsstr` at `0x18000a1ae`
- `msvcrt!wcsstr` at `0x18000a215`
- `KERNEL32!MoveFileExW` at `0x18000a40d`
- `KERNEL32!MoveFileExW` at `0x18000a40d`
- `KERNEL32!lstrlenW` at `0x180009ea8`
- `KERNEL32!lstrlenW` at `0x180009ea8`
- `KERNEL32!GetLastError` at `0x18000a483`
- `KERNEL32!GetLastError` at `0x18000a483`
- `IisRTL!PuDbgPrintW` at `0x180009d63`
- `IisRTL!PuDbgPrintW` at `0x180009dab`
- `IisRTL!PuDbgPrintW` at `0x180009e5c`
- `IisRTL!PuDbgPrintW` at `0x180009f52`
- `IisRTL!PuDbgPrintW` at `0x18000a3e0`
- `IisRTL!PuDbgPrintW` at `0x18000a479`
- `IisRTL!PuDbgPrintW` at `0x18000a4dd`
- `IisRTL!PuDbgPrintW` at `0x180009d63`
- `IisRTL!PuDbgPrintW` at `0x180009dab`
- `IisRTL!PuDbgPrintW` at `0x180009e5c`
- `IisRTL!PuDbgPrintW` at `0x180009f52`
- `IisRTL!PuDbgPrintW` at `0x18000a3e0`
- `IisRTL!PuDbgPrintW` at `0x18000a479`
- `IisRTL!PuDbgPrintW` at `0x18000a4dd`

## string_xrefs

- `0x180009d39`: `[CFileListener::ApplyChangeToHistoryFile] Attempting to create a new version of the hisory file %s, %s that contains all the successful updates to the metabase.\n`
- `0x180009d9a`: `[SaveSchema] Initializing writer with write file: %s bin file: %s.\n`
- `0x180009e36`: `[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the hisory file %s. CWriter::Initialize failed with hr = 0x%x.\n`
- `0x180009f41`: `[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the history file %s. GetTable on table %s from file %s failed with hr = 0x%x.\n`
- `0x180009f89`: `[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the hisory file %s. CWriter::BeginWrite failed with hr = 0x%x.\n`
- `0x18000a3ba`: `[CFileListener::ApplyChangeToHistoryFile] Unable to abort write history data file %s. CWriter::EndWriter failed with hr = 0x%x.\n`
- `0x18000a38d`: `[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the history data file %s. CWriter::EndWrite failed with hr = 0x%x.\n`
- `0x18000a462`: `[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the history schema file %s. CopyFile failed with hr = 0x%x.\n`
- `0x18000a4d1`: `[CFileListener::ApplyChangeToHistoryFile] Unable to create a new history file with the changes. MoveFile from %s to %s failed with hr = 0x%x. \n`

## pseudocode

```c
__int64 __fastcall CFileListener::ApplyChangeToHistoryFile(
        CFileListener *this,
        struct CWriterGlobalHelper *a2,
        struct ISimpleTableWrite2 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6)
{
  signed int v9; // ebx
  unsigned __int16 *v10; // r13
  struct CWriter *v11; // rdi
  int v12; // eax
  WCHAR *v13; // r15
  int v14; // eax
  struct CWriter *v15; // rax
  int v16; // eax
  int v17; // r14d
  __int64 v18; // rax
  LPCWSTR v19; // r14
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  unsigned int v24; // r14d
  int v25; // eax
  CFileListener *v26; // rcx
  int v27; // eax
  __int64 (__fastcall **v28)(struct ISimpleTableWrite2 *, GUID *, void **); // rax
  int v29; // eax
  int v30; // ecx
  wchar_t *v31; // rax
  int v32; // eax
  wchar_t *v33; // rax
  __int64 (__fastcall **v34)(struct ISimpleTableWrite2 *, GUID *, void **); // rax
  CFileListener *v35; // rcx
  int v36; // eax
  unsigned int v37; // edx
  int v38; // eax
  unsigned __int16 **v39; // rcx
  int v40; // eax
  signed int LastError; // eax
  unsigned __int16 *v43; // [rsp+30h] [rbp-D0h]
  unsigned int v44[2]; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v45; // [rsp+40h] [rbp-C0h]
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpString; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+68h] [rbp-98h] BYREF
  struct ISimpleTableRead2 *v49; // [rsp+70h] [rbp-90h] BYREF
  int v50; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *SubStr; // [rsp+80h] [rbp-80h]
  wchar_t *v52; // [rsp+88h] [rbp-78h]
  __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  int v54; // [rsp+98h] [rbp-68h]
  int v55; // [rsp+9Ch] [rbp-64h]
  __int64 v56; // [rsp+A0h] [rbp-60h]
  LPCWSTR v57; // [rsp+A8h] [rbp-58h]
  int v58; // [rsp+B0h] [rbp-50h]
  int v59; // [rsp+B4h] [rbp-4Ch]
  int v60; // [rsp+B8h] [rbp-48h]
  int v61; // [rsp+BCh] [rbp-44h]
  _BYTE v62[32]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *String2; // [rsp+E0h] [rbp-20h]
  unsigned int *v64; // [rsp+F8h] [rbp-8h]
  _BYTE v65[32]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t *String1; // [rsp+130h] [rbp+30h]
  unsigned int *v67; // [rsp+148h] [rbp+48h]
  _DWORD *v68; // [rsp+150h] [rbp+50h]

  lpString = a4;
  v50 = 2;
  v49 = 0;
  lpNewFileName = 0;
  Block = 0;
  v9 = 0;
  v10 = 0;
  if ( !a3 )
    return (unsigned int)v9;
  v11 = 0;
  v12 = ConstructHistoryFileName(
          (unsigned __int16 **)&lpNewFileName,
          *((unsigned __int16 **)this + 3),
          *((_DWORD *)this + 8),
          *((unsigned __int16 **)this + 9),
          *((_DWORD *)this + 20),
          *((unsigned __int16 **)this + 11),
          *((_DWORD *)this + 24),
          a5,
          a6);
  v13 = (WCHAR *)lpNewFileName;
  v9 = v12;
  if ( v12 < 0
    || (v14 = ConstructHistoryFileName(
                (unsigned __int16 **)&Block,
                *((unsigned __int16 **)this + 3),
                *((_DWORD *)this + 8),
                *((unsigned __int16 **)this + 17),
                *((_DWORD *)this + 36),
                *((unsigned __int16 **)this + 19),
                *((_DWORD *)this + 40),
                a5,
                a6),
        v10 = (unsigned __int16 *)Block,
        v9 = v14,
        v14 < 0) )
  {
    v17 = 0;
    goto LABEL_53;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      3109,
      "CFileListener::ApplyChangeToHistoryFile",
      L"[CFileListener::ApplyChangeToHistoryFile] Attempting to create a new version of the hisory file %s, %s that contai"
       "ns all the successful updates to the metabase.\n",
      v13,
      Block);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        3114,
        "CFileListener::ApplyChangeToHistoryFile",
        L"[SaveSchema] Initializing writer with write file: %s bin file: %s.\n",
        v13,
        *((_QWORD *)a2 + 31));
  }
  v15 = (struct CWriter *)operator new(0x10050u);
  v11 = v15;
  if ( !v15 )
  {
    v9 = -2147024882;
    v11 = 0;
    v17 = 0;
    goto LABEL_53;
  }
  *(_QWORD *)v15 = 0;
  *((_QWORD *)v15 + 1) = 0;
  *((_QWORD *)v15 + 8200) = 0;
  *((_QWORD *)v15 + 8201) = 0;
  *((_DWORD *)v15 + 4) = 0;
  *((_QWORD *)v15 + 8195) = 0;
  *((_QWORD *)v15 + 8196) = 0;
  *((_QWORD *)v15 + 8197) = 0;
  *((_QWORD *)v15 + 8198) = 0;
  *((_QWORD *)v15 + 8199) = -1;
  v16 = CWriter::Initialize(v15, *((const unsigned __int16 **)this + 31), a2, 0);
  v9 = v16;
  if ( v16 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v43) = v16;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        3131,
        "CFileListener::ApplyChangeToHistoryFile",
        L"[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the hisory file %s. CWriter::Initial"
         "ize failed with hr = 0x%x.\n",
        v13,
        v43);
    }
LABEL_11:
    v17 = 0;
    goto LABEL_53;
  }
  v18 = *((_QWORD *)a2 + 31);
  v19 = lpString;
  v53 = v18;
  v54 = 2;
  v58 = 2;
  v56 = 130;
  v60 = 130;
  v55 = -268435447;
  v57 = lpString;
  v59 = -268435455;
  v20 = lstrlenW(lpString);
  v21 = *((_QWORD *)this + 2);
  v61 = 2 * v20 + 2;
  v22 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, int *, int, _DWORD, struct ISimpleTableRead2 **))(*(_QWORD *)v21 + 24LL))(
          v21,
          L"METABASE",
          L"MBProperty",
          &v53,
          &v50,
          3,
          0,
          &v49);
  v9 = v22;
  if ( v22 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v45) = v22;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        3163,
        "CFileListener::ApplyChangeToHistoryFile",
        L"[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the history file %s. GetTable on tab"
         "le %s from file %s failed with hr = 0x%x.\n",
        v13,
        L"MBProperty",
        v19,
        v45);
    }
    goto LABEL_11;
  }
  v23 = CWriter::BeginWrite(v11, 1, 0);
  v9 = v23;
  if ( v23 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v43) = v23;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        3174,
        "CFileListener::ApplyChangeToHistoryFile",
        L"[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the hisory file %s. CWriter::BeginWr"
         "ite failed with hr = 0x%x.\n",
        v13,
        v43);
    }
    goto LABEL_11;
  }
  v24 = 0;
  LODWORD(lpString) = 0;
  LODWORD(lpNewFileName) = 0;
LABEL_19:
  while ( 1 )
  {
    memset_0(v65, 0, 0x50u);
    memset_0(v62, 0, 0x48u);
    v43 = (unsigned __int16 *)v65;
    v25 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite2 *, _QWORD, __int64))(*(_QWORD *)a3 + 96LL))(a3, v24, 10);
    v9 = v25;
    if ( v25 == -2145318890 )
      break;
    if ( v25 < 0 )
      goto LABEL_11;
    v27 = (*(__int64 (__fastcall **)(struct ISimpleTableRead2 *, _QWORD, __int64))(*(_QWORD *)v49 + 32LL))(
            v49,
            (unsigned int)lpNewFileName,
            9);
    v9 = v27;
    if ( v27 == -2145318890 )
      goto LABEL_46;
    if ( v27 < 0 )
      goto LABEL_11;
    if ( _wcsicmp(String1, String2) < 0 )
    {
      v28 = *(__int64 (__fastcall ***)(struct ISimpleTableWrite2 *, GUID *, void **))a3;
      Block = 0;
      v9 = (*v28)(a3, &IID_ISimpleTableRead2, &Block);
      if ( v9 < 0 )
        goto LABEL_11;
      v9 = CFileListener::MergeLocation(
             (CFileListener *)*v67,
             v11,
             (struct ISimpleTableRead2 *)Block,
             0,
             (unsigned int *)&lpString,
             *v67,
             String1);
      (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
LABEL_43:
      v24 = (unsigned int)lpString;
      goto LABEL_44;
    }
    if ( _wcsicmp(String1, String2) <= 0 )
    {
      if ( *v68 == 4 )
      {
        LODWORD(lpString) = ++v24;
        LODWORD(Block) = *v64;
        SubStr = String2;
        v52 = String1;
        while ( 1 )
        {
          LODWORD(lpNewFileName) = (_DWORD)lpNewFileName + 1;
          v29 = (*(__int64 (__fastcall **)(struct ISimpleTableRead2 *, _QWORD, __int64))(*(_QWORD *)v49 + 32LL))(
                  v49,
                  (unsigned int)lpNewFileName,
                  9);
          v9 = v29;
          if ( v29 == -2145318890 )
            break;
          if ( v29 < 0 )
            goto LABEL_11;
          v30 = (int)Block;
          if ( (_DWORD)Block != *v64 )
          {
            v31 = wcsstr(String2, SubStr);
            if ( v31 == String2 )
              LODWORD(Block) = *v64;
            v43 = (unsigned __int16 *)v65;
            v32 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite2 *, _QWORD, __int64))(*(_QWORD *)a3 + 96LL))(
                    a3,
                    v24,
                    10);
            v9 = v32;
            if ( v32 == -2145318890 )
            {
              v30 = (int)Block;
            }
            else
            {
              if ( v32 < 0 )
                goto LABEL_11;
              v33 = wcsstr(String1, v52);
              v30 = (int)Block;
              if ( v33 == String1 )
                LODWORD(lpString) = ++v24;
            }
          }
          if ( v30 != *v64 )
            goto LABEL_19;
        }
LABEL_46:
        v34 = *(__int64 (__fastcall ***)(struct ISimpleTableWrite2 *, GUID *, void **))a3;
        Block = 0;
        v9 = (*v34)(a3, &IID_ISimpleTableRead2, &Block);
        if ( v9 >= 0 )
        {
          v9 = CFileListener::MergeRemainingLocations(
                 v35,
                 v11,
                 (struct ISimpleTableRead2 *)Block,
                 0,
                 (unsigned int *)&lpString);
          (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
        }
        goto LABEL_11;
      }
      v9 = CFileListener::MergeLocation(
             (CFileListener *)*v64,
             v11,
             v49,
             (unsigned int *)&lpNewFileName,
             *v64,
             a3,
             (unsigned int *)&lpString,
             *v67,
             String1);
      goto LABEL_43;
    }
    v9 = CFileListener::MergeLocation((CFileListener *)*v64, v11, v49, 1, (unsigned int *)&lpNewFileName, *v64, String2);
LABEL_44:
    if ( v9 < 0 )
      goto LABEL_11;
  }
  if ( v24 )
  {
    v9 = CFileListener::MergeRemainingLocations(v26, v11, v49, 1, (unsigned int *)&lpNewFileName);
    goto LABEL_11;
  }
  v9 = 0;
  v17 = 1;
LABEL_53:
  if ( v49 )
  {
    (*(void (__fastcall **)(struct ISimpleTableRead2 *))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( v11 )
  {
    if ( v9 < 0 || v17 )
    {
      v38 = CWriter::EndWrite(v11, 2);
      if ( v38 < 0 && (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v43) = v38;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          3476,
          "CFileListener::ApplyChangeToHistoryFile",
          L"[CFileListener::ApplyChangeToHistoryFile] Unable to abort write history data file %s. CWriter::EndWriter faile"
           "d with hr = 0x%x.\n",
          v13,
          v43);
      }
    }
    else
    {
      v36 = CWriter::EndWrite(v11, 1);
      v9 = v36;
      if ( v36 < 0 && (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v43) = v36;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          3488,
          "CFileListener::ApplyChangeToHistoryFile",
          L"[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the history data file %s. CWriter:"
           ":EndWrite failed with hr = 0x%x.\n",
          v13,
          v43);
      }
    }
    CWriter::`scalar deleting destructor'(v11, v37);
    if ( v9 >= 0 && !v17 )
    {
      if ( MoveFileExW(*((LPCWSTR *)this + 31), v13, 1u) )
      {
        v39 = (unsigned __int16 **)((char *)this + 104);
        if ( *((_DWORD *)this + 138) )
          v39 = (unsigned __int16 **)((char *)this + 232);
        v40 = CopyFileWithSecurityDescriptor(*v39, v10);
        v9 = v40;
        if ( v40 < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            LODWORD(v43) = v40;
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\listener.cpp",
              3522,
              "CFileListener::ApplyChangeToHistoryFile",
              L"[CFileListener::ApplyChangeToHistoryFile] Unable to write to new version of the history schema file %s. Co"
               "pyFile failed with hr = 0x%x.\n",
              v10,
              v43);
          }
          v9 = 0;
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v44[0] = v9;
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\listener.cpp",
            3536,
            "CFileListener::ApplyChangeToHistoryFile",
            L"[CFileListener::ApplyChangeToHistoryFile] Unable to create a new history file with the changes. MoveFile fro"
             "m %s to %s failed with hr = 0x%x. \n",
            *((_QWORD *)this + 31),
            v13,
            *(_QWORD *)v44);
        }
      }
    }
  }
  if ( v13 )
    operator delete(v13);
  if ( v10 )
    operator delete(v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009c14  push    rbp
0x180009c16  push    rbx
0x180009c17  push    rsi
0x180009c18  push    rdi
0x180009c19  push    r12
0x180009c1b  push    r13
0x180009c1d  push    r14
0x180009c1f  push    r15
0x180009c21  lea     rbp, [rsp-0C8h]
0x180009c29  sub     rsp, 1C8h
0x180009c30  mov     rax, cs:__security_cookie
0x180009c37  xor     rax, rsp
0x180009c3a  mov     [rbp+100h+var_50], rax
0x180009c41  xor     eax, eax
0x180009c43  mov     [rsp+200h+lpString], r9
0x180009c48  mov     [rsp+200h+var_188], 2
0x180009c50  mov     r12, r8
0x180009c53  mov     [rsp+200h+var_190], rax
0x180009c58  mov     r14, rdx
0x180009c5b  mov     [rsp+200h+lpNewFileName], rax
0x180009c60  mov     rsi, rcx
0x180009c63  mov     [rsp+200h+Block], rax
0x180009c68  mov     ebx, eax
0x180009c6a  mov     r13d, eax
0x180009c6d  test    r8, r8
0x180009c70  jz      loc_18000A4FD
0x180009c76  mov     r9, [rcx+48h]; unsigned __int16 *
0x180009c7a  mov     edi, eax
0x180009c7c  mov     r8d, [rcx+20h]; unsigned int
0x180009c80  mov     rdx, [rcx+18h]; unsigned __int16 *
0x180009c84  mov     [rsp+200h+var_1B0], eax
0x180009c88  mov     eax, [rbp+100h+arg_28]
0x180009c8e  mov     dword ptr [rsp+200h+var_1C0], eax; unsigned int
0x180009c92  mov     eax, [rbp+100h+arg_20]
0x180009c98  mov     [rsp+200h+var_1C8], eax; unsigned int
0x180009c9c  mov     eax, [rcx+60h]
0x180009c9f  mov     dword ptr [rsp+200h+var_1D0], eax; unsigned int
0x180009ca3  mov     rax, [rcx+58h]
0x180009ca7  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x180009cac  mov     eax, [rcx+50h]
0x180009caf  lea     rcx, [rsp+200h+lpNewFileName]; unsigned __int16 **
0x180009cb4  mov     dword ptr [rsp+200h+var_1E0], eax; unsigned int
0x180009cb8  call    ?ConstructHistoryFileName@@YAJPEAPEAGPEAGK1K1KKK@Z; ConstructHistoryFileName(ushort * *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong,ulong)
0x180009cbd  mov     r15, [rsp+200h+lpNewFileName]
0x180009cc2  mov     ebx, eax
0x180009cc4  test    eax, eax
0x180009cc6  js      loc_18000A334
0x180009ccc  mov     eax, [rbp+100h+arg_28]
0x180009cd2  lea     rcx, [rsp+200h+Block]; unsigned __int16 **
0x180009cd7  mov     r9, [rsi+88h]; unsigned __int16 *
0x180009cde  mov     r8d, [rsi+20h]; unsigned int
0x180009ce2  mov     rdx, [rsi+18h]; unsigned __int16 *
0x180009ce6  mov     dword ptr [rsp+200h+var_1C0], eax; unsigned int
0x180009cea  mov     eax, [rbp+100h+arg_20]
0x180009cf0  mov     [rsp+200h+var_1C8], eax; unsigned int
0x180009cf4  mov     eax, [rsi+0A0h]
0x180009cfa  mov     dword ptr [rsp+200h+var_1D0], eax; unsigned int
0x180009cfe  mov     rax, [rsi+98h]
0x180009d05  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x180009d0a  mov     eax, [rsi+90h]
0x180009d10  mov     dword ptr [rsp+200h+var_1E0], eax; unsigned int
0x180009d14  call    ?ConstructHistoryFileName@@YAJPEAPEAGPEAGK1K1KKK@Z; ConstructHistoryFileName(ushort * *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong,ulong)
0x180009d19  mov     r13, [rsp+200h+Block]
0x180009d1e  mov     ebx, eax
0x180009d20  test    eax, eax
0x180009d22  js      loc_18000A334
0x180009d28  mov     eax, cs:g_dwDebugFlags
0x180009d2e  test    al, 3
0x180009d30  jz      short loc_180009DB1
0x180009d32  mov     rcx, cs:g_pDebug
0x180009d39  lea     rax, aCfilelistenerA_7; "[CFileListener::ApplyChangeToHistoryFil"...
0x180009d40  mov     [rsp+200h+var_1D0], r13
0x180009d45  lea     r9, aCfilelistenerA_0; "CFileListener::ApplyChangeToHistoryFile"
0x180009d4c  mov     [rsp+200h+var_1D8], r15
0x180009d51  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x180009d58  mov     r8d, 0C25h
0x180009d5e  mov     [rsp+200h+var_1E0], rax
0x180009d63  call    cs:__imp_PuDbgPrintW
0x180009d69  mov     eax, cs:g_dwDebugFlags
0x180009d6f  test    al, 3
0x180009d71  jz      short loc_180009DB1
0x180009d73  mov     rax, [r14+0F8h]
0x180009d7a  lea     r9, aCfilelistenerA_0; "CFileListener::ApplyChangeToHistoryFile"
0x180009d81  mov     rcx, cs:g_pDebug
0x180009d88  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x180009d8f  mov     [rsp+200h+var_1D0], rax
0x180009d94  mov     r8d, 0C2Ah
0x180009d9a  lea     rax, aSaveschemaInit; "[SaveSchema] Initializing writer with w"...
0x180009da1  mov     [rsp+200h+var_1D8], r15
0x180009da6  mov     [rsp+200h+var_1E0], rax
0x180009dab  call    cs:__imp_PuDbgPrintW
0x180009db1  mov     ecx, 10050h; Size
0x180009db6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009dbb  xor     ecx, ecx
0x180009dbd  mov     rdi, rax
0x180009dc0  test    rax, rax
0x180009dc3  jz      loc_18000A327
0x180009dc9  mov     [rax], rcx
0x180009dcc  xor     r9d, r9d; void *
0x180009dcf  mov     [rax+8], rcx
0x180009dd3  mov     r8, r14; struct CWriterGlobalHelper *
0x180009dd6  mov     [rax+10040h], rcx
0x180009ddd  mov     [rax+10048h], rcx
0x180009de4  mov     [rax+10h], ecx
0x180009de7  mov     [rax+10018h], rcx
0x180009dee  mov     [rax+10020h], rcx
0x180009df5  mov     [rax+10028h], rcx
0x180009dfc  mov     [rax+10030h], rcx
0x180009e03  mov     rcx, rax; this
0x180009e06  mov     qword ptr [rax+10038h], 0FFFFFFFFFFFFFFFFh
0x180009e11  mov     rdx, [rsi+0F8h]; unsigned __int16 *
0x180009e18  call    ?Initialize@CWriter@@QEAAJPEBGPEAVCWriterGlobalHelper@@PEAX@Z; CWriter::Initialize(ushort const *,CWriterGlobalHelper *,void *)
0x180009e1d  mov     ebx, eax
0x180009e1f  test    eax, eax
0x180009e21  jns     short loc_180009E6C
0x180009e23  test    byte ptr cs:g_dwDebugFlags, 3
0x180009e2a  jz      short loc_180009E62
0x180009e2c  mov     dword ptr [rsp+200h+var_1D0], eax
0x180009e30  mov     r8d, 0C3Bh
0x180009e36  lea     rax, aCfilelistenerA_4; "[CFileListener::ApplyChangeToHistoryFil"...
0x180009e3d  mov     rcx, cs:g_pDebug
0x180009e44  lea     r9, aCfilelistenerA_0; "CFileListener::ApplyChangeToHistoryFile"
0x180009e4b  mov     [rsp+200h+var_1D8], r15
0x180009e50  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x180009e57  mov     [rsp+200h+var_1E0], rax
0x180009e5c  call    cs:__imp_PuDbgPrintW
0x180009e62  mov     r14d, [rsp+200h+var_1B0]
0x180009e67  jmp     loc_18000A337
0x180009e6c  mov     rax, [r14+0F8h]
0x180009e73  mov     ecx, 2
0x180009e78  mov     r14, [rsp+200h+lpString]
0x180009e7d  mov     [rbp+100h+var_170], rax
0x180009e81  mov     eax, 82h
0x180009e86  mov     [rbp+100h+var_168], ecx
0x180009e89  mov     [rbp+100h+var_150], ecx
0x180009e8c  mov     rcx, r14; lpString
0x180009e8f  mov     [rbp+100h+var_160], rax
0x180009e93  mov     [rbp+100h+var_148], eax
0x180009e96  mov     [rbp+100h+var_164], 0F0000009h
0x180009e9d  mov     [rbp+100h+var_158], r14
0x180009ea1  mov     [rbp+100h+var_14C], 0F0000001h
0x180009ea8  call    cs:__imp_lstrlenW
0x180009eae  mov     rcx, [rsi+10h]
0x180009eb2  lea     rdx, [rsp+200h+var_190]
0x180009eb7  mov     qword ptr [rsp+200h+var_1C8], rdx
0x180009ebc  lea     r9, [rbp+100h+var_170]
0x180009ec0  mov     dword ptr [rsp+200h+var_1D0], 0
0x180009ec8  lea     rdx, [rsp+200h+var_188]
0x180009ecd  lea     eax, ds:2[rax*2]
0x180009ed4  mov     dword ptr [rsp+200h+var_1D8], 3
0x180009edc  mov     [rbp+100h+var_144], eax
0x180009edf  lea     r8, aMbproperty_0; "MBProperty"
0x180009ee6  mov     rax, [rcx]
0x180009ee9  mov     [rsp+200h+var_1E0], rdx
0x180009eee  lea     rdx, aMetabase; "METABASE"
0x180009ef5  mov     rax, [rax+18h]
0x180009ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009efe  mov     ebx, eax
0x180009f00  test    eax, eax
0x180009f02  jns     short loc_180009F5D
0x180009f04  test    byte ptr cs:g_dwDebugFlags, 3
0x180009f0b  jz      loc_180009E62
0x180009f11  mov     rcx, cs:g_pDebug
0x180009f18  lea     r9, aCfilelistenerA_0; "CFileListener::ApplyChangeToHistoryFile"
0x180009f1f  mov     dword ptr [rsp+200h+var_1C0], eax
0x180009f23  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x180009f2a  mov     qword ptr [rsp+200h+var_1C8], r14
0x180009f2f  lea     rax, aMbproperty_0; "MBProperty"
0x180009f36  mov     [rsp+200h+var_1D0], rax
0x180009f3b  mov     r8d, 0C5Bh
0x180009f41  lea     rax, aCfilelistenerA_1; "[CFileListener::ApplyChangeToHistoryFil"...
0x180009f48  mov     [rsp+200h+var_1D8], r15
0x180009f4d  mov     [rsp+200h+var_1E0], rax
0x180009f52  call    cs:__imp_PuDbgPrintW
0x180009f58  jmp     loc_180009E62
0x180009f5d  xor     r8d, r8d
0x180009f60  mov     rcx, rdi
0x180009f63  lea     edx, [r8+1]
0x180009f67  call    ?BeginWrite@CWriter@@QEAAJW4eWriter@@PEAU_SECURITY_ATTRIBUTES@@@Z; CWriter::BeginWrite(eWriter,_SECURITY_ATTRIBUTES *)
0x180009f6c  mov     ebx, eax
0x180009f6e  test    eax, eax
0x180009f70  jns     short loc_180009F95
0x180009f72  test    byte ptr cs:g_dwDebugFlags, 3
0x180009f79  jz      loc_180009E62
0x180009f7f  mov     dword ptr [rsp+200h+var_1D0], eax
0x180009f83  mov     r8d, 0C66h
0x180009f89  lea     rax, aCfilelistenerA; "[CFileListener::ApplyChangeToHistoryFil"...
0x180009f90  jmp     loc_180009E3D
0x180009f95  xor     r14d, r14d
0x180009f98  mov     dword ptr [rsp+200h+lpString], r14d
0x180009f9d  mov     dword ptr [rsp+200h+lpNewFileName], r14d
0x180009fa2  xor     edx, edx; Val
0x180009fa4  lea     rcx, [rbp+100h+var_F0]; void *
0x180009fa8  lea     r8d, [rdx+50h]; Size
0x180009fac  call    memset_0
0x180009fb1  xor     edx, edx; Val
0x180009fb3  lea     rcx, [rbp+100h+var_140]; void *
0x180009fb7  lea     r8d, [rdx+48h]; Size
0x180009fbb  call    memset_0
0x180009fc0  mov     rax, [r12]
0x180009fc4  lea     rcx, [rbp+100h+var_F0]
0x180009fc8  mov     [rsp+200h+var_1D0], rcx
0x180009fcd  xor     r9d, r9d
0x180009fd0  lea     rcx, [rbp+100h+var_78]
0x180009fd7  mov     edx, r14d
0x180009fda  mov     [rsp+200h+var_1D8], rcx
0x180009fdf  mov     rcx, r12
0x180009fe2  mov     rax, [rax+60h]
0x180009fe6  lea     r8d, [r9+0Ah]
0x180009fea  mov     [rsp+200h+var_1E0], 0
0x180009ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff8  mov     ebx, eax
0x180009ffa  cmp     eax, 80210816h
0x180009fff  jz      loc_18000A2F6
0x18000a005  test    eax, eax
0x18000a007  js      loc_180009E62
0x18000a00d  mov     rcx, [rsp+200h+var_190]
0x18000a012  lea     rdx, [rbp+100h+var_140]
0x18000a016  mov     [rsp+200h+var_1D8], rdx
0x18000a01b  xor     r9d, r9d
0x18000a01e  lea     rdx, [rbp+100h+var_A0]
0x18000a022  mov     [rsp+200h+var_1E0], rdx
0x18000a027  mov     rax, [rcx]
0x18000a02a  mov     edx, dword ptr [rsp+200h+lpNewFileName]
0x18000a02e  lea     r8d, [r9+9]
0x18000a032  mov     rax, [rax+20h]
0x18000a036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a03b  mov     ebx, eax
0x18000a03d  cmp     eax, 80210816h
0x18000a042  jz      loc_18000A296
0x18000a048  test    eax, eax
0x18000a04a  js      loc_180009E62
0x18000a050  mov     rdx, [rbp+100h+String2]; String2
0x18000a054  mov     rcx, [rbp+100h+String1]; String1
0x18000a058  call    cs:__imp__wcsicmp
0x18000a05e  test    eax, eax
0x18000a060  jns     short loc_18000A0D5
0x18000a062  mov     rax, [r12]
0x18000a066  lea     r8, [rsp+200h+Block]
0x18000a06b  lea     rdx, IID_ISimpleTableRead2
0x18000a072  mov     [rsp+200h+Block], 0
0x18000a07b  mov     rcx, r12
0x18000a07e  mov     rax, [rax]
0x18000a081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a086  mov     ebx, eax
0x18000a088  test    eax, eax
0x18000a08a  js      loc_180009E62
0x18000a090  mov     rax, [rbp+100h+String1]
0x18000a094  xor     r9d, r9d; int
0x18000a097  mov     r8, [rsp+200h+Block]; struct ISimpleTableRead2 *
0x18000a09c  mov     rdx, rdi; struct CWriter *
0x18000a09f  mov     [rsp+200h+var_1D0], rax; unsigned __int16 *
0x18000a0a4  mov     rax, [rbp+100h+var_B8]
0x18000a0a8  mov     ecx, [rax]; this
0x18000a0aa  lea     rax, [rsp+200h+lpString]
0x18000a0af  mov     dword ptr [rsp+200h+var_1D8], ecx; unsigned int
0x18000a0b3  mov     [rsp+200h+var_1E0], rax; unsigned int *
0x18000a0b8  call    ?MergeLocation@CFileListener@@AEAAJPEAVCWriter@@PEAUISimpleTableRead2@@HPEAKKPEBG@Z; CFileListener::MergeLocation(CWriter *,ISimpleTableRead2 *,int,ulong *,ulong,ushort const *)
0x18000a0bd  mov     rcx, [rsp+200h+Block]
0x18000a0c2  mov     ebx, eax
0x18000a0c4  mov     rax, [rcx]
0x18000a0c7  mov     rax, [rax+10h]
0x18000a0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0d0  jmp     loc_18000A284
0x18000a0d5  mov     rdx, [rbp+100h+String2]; String2
0x18000a0d9  mov     rcx, [rbp+100h+String1]; String1
0x18000a0dd  call    cs:__imp__wcsicmp
0x18000a0e3  test    eax, eax
0x18000a0e5  jle     short loc_18000A11E
0x18000a0e7  mov     rax, [rbp+100h+String2]
0x18000a0eb  mov     r9d, 1; int
0x18000a0f1  mov     r8, [rsp+200h+var_190]; struct ISimpleTableRead2 *
0x18000a0f6  mov     rdx, rdi; struct CWriter *
0x18000a0f9  mov     [rsp+200h+var_1D0], rax; unsigned __int16 *
0x18000a0fe  mov     rax, [rbp+100h+var_108]
0x18000a102  mov     ecx, [rax]; this
0x18000a104  lea     rax, [rsp+200h+lpNewFileName]
0x18000a109  mov     dword ptr [rsp+200h+var_1D8], ecx; unsigned int
0x18000a10d  mov     [rsp+200h+var_1E0], rax; unsigned int *
0x18000a112  call    ?MergeLocation@CFileListener@@AEAAJPEAVCWriter@@PEAUISimpleTableRead2@@HPEAKKPEBG@Z; CFileListener::MergeLocation(CWriter *,ISimpleTableRead2 *,int,ulong *,ulong,ushort const *)
0x18000a117  mov     ebx, eax
0x18000a119  jmp     loc_18000A289
0x18000a11e  mov     rax, [rbp+100h+var_B0]
0x18000a122  cmp     dword ptr [rax], 4
0x18000a125  jnz     loc_18000A244
0x18000a12b  mov     rax, [rbp+100h+var_108]
0x18000a12f  inc     r14d
0x18000a132  mov     dword ptr [rsp+200h+lpString], r14d
0x18000a137  mov     eax, [rax]
0x18000a139  mov     dword ptr [rsp+200h+Block], eax
0x18000a13d  mov     rax, [rbp+100h+String2]
0x18000a141  mov     [rbp+100h+SubStr], rax
0x18000a145  mov     rax, [rbp+100h+String1]
0x18000a149  mov     [rbp+100h+var_178], rax
0x18000a14d  mov     edx, dword ptr [rsp+200h+lpNewFileName]
0x18000a151  lea     r8, [rbp+100h+var_140]
0x18000a155  mov     rcx, [rsp+200h+var_190]
0x18000a15a  xor     r9d, r9d
0x18000a15d  mov     [rsp+200h+var_1D8], r8
0x18000a162  inc     edx
  ... truncated ...
```
