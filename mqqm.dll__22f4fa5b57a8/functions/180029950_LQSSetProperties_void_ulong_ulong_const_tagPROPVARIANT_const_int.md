# LQSSetProperties(void *,ulong,ulong * const,tagPROPVARIANT * const,int)

- ea: `0x180029950`
- end: `0x18002a231`
- name: `?LQSSetProperties@@YAJPEAXKQEAKQEAUtagPROPVARIANT@@H@Z`
- size: `2273`
- prototype: `__int64 __usercall@<rax>(_HLQS *this@<rcx>, unsigned int@<edx>, unsigned int *const@<r8>, struct tagPROPVARIANT *const@<r9>, int)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001cb34`
- `0x18001d438`
- `0x180027830`
- `0x180050e90`

## callees

- `0x180004d91`
- `0x180009924`
- `0x18000bab8`
- `0x18000cb80`
- `0x18000f7e4`
- `0x180011578`
- `0x180026698`
- `0x180027098`
- `0x180029950`
- `0x18002a6dc`
- `0x18002a91c`
- `0x18002ab44`
- `0x18002af90`
- `0x18002b05c`
- `0x18002c61c`
- `0x18002c6c8`
- `0x18009bd1c`
- `0x1800cffcc`

## import_xrefs

- `msvcrt!free` at `0x180029c01`
- `msvcrt!free` at `0x180029c65`
- `msvcrt!free` at `0x180029c8d`
- `msvcrt!free` at `0x180029c01`
- `msvcrt!free` at `0x180029c65`
- `msvcrt!free` at `0x180029c8d`
- `msvcrt!wcschr` at `0x180029c2a`
- `msvcrt!wcschr` at `0x180029c2a`
- `msvcrt!time` at `0x180029e7f`
- `msvcrt!time` at `0x180029e7f`
- `KERNEL32!GetLastError` at `0x180029a01`
- `KERNEL32!GetLastError` at `0x180029a97`
- `KERNEL32!GetLastError` at `0x180029fb9`
- `KERNEL32!GetLastError` at `0x18002a02b`
- `KERNEL32!GetLastError` at `0x18002a09a`
- `KERNEL32!GetLastError` at `0x18002a193`
- `KERNEL32!GetLastError` at `0x180029a01`
- `KERNEL32!GetLastError` at `0x180029a97`
- `KERNEL32!GetLastError` at `0x180029fb9`
- `KERNEL32!GetLastError` at `0x18002a02b`
- `KERNEL32!GetLastError` at `0x18002a09a`
- `KERNEL32!GetLastError` at `0x18002a193`
- `KERNEL32!LeaveCriticalSection` at `0x180029a77`
- `KERNEL32!LeaveCriticalSection` at `0x180029c0b`
- `KERNEL32!LeaveCriticalSection` at `0x18002a200`
- `KERNEL32!LeaveCriticalSection` at `0x18002a210`
- `KERNEL32!LeaveCriticalSection` at `0x180029a77`
- `KERNEL32!LeaveCriticalSection` at `0x180029c0b`
- `KERNEL32!LeaveCriticalSection` at `0x18002a200`
- `KERNEL32!LeaveCriticalSection` at `0x18002a210`
- `KERNEL32!CopyFileExW` at `0x1800299f3`
- `KERNEL32!CopyFileExW` at `0x1800299f3`
- `KERNEL32!SetFileAttributesW` at `0x180029a8d`
- `KERNEL32!SetFileAttributesW` at `0x18002a090`
- `KERNEL32!SetFileAttributesW` at `0x180029a8d`
- `KERNEL32!SetFileAttributesW` at `0x18002a090`
- `KERNEL32!MoveFileExW` at `0x18002a01e`
- `KERNEL32!MoveFileExW` at `0x18002a01e`
- `KERNEL32!ReplaceFileW` at `0x18002a182`
- `KERNEL32!ReplaceFileW` at `0x18002a182`
- `USER32!CharLowerW` at `0x180029c1c`
- `USER32!CharLowerW` at `0x180029c1c`

## string_xrefs

- `0x180029dca`: `CreateTime`
- `0x180029e5a`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall LQSSetProperties(
        LPCWSTR *this,
        unsigned int a2,
        unsigned int *const a3,
        struct tagPROPVARIANT *const a4,
        int a5)
{
  int v7; // edi
  const WCHAR *v8; // r12
  const WCHAR *TemporaryFileName; // rsi
  wchar_t *v10; // r14
  DWORD LastError; // eax
  signed int v12; // edi
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  __int64 v16; // r8
  char v17; // al
  unsigned int i; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned __int64 v24; // r12
  unsigned int v25; // edi
  wchar_t *v26; // r14
  int v27; // eax
  unsigned int v28; // edi
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  struct tagPROPVARIANT *v34; // r14
  struct tagPROPVARIANT *v35; // r14
  unsigned int v36; // eax
  unsigned int v37; // eax
  struct tagPROPVARIANT *v38; // r14
  const WCHAR *v39; // r12
  int v40; // eax
  unsigned int v41; // edi
  DWORD v42; // eax
  int v43; // ebx
  signed int v44; // edi
  BOOL v45; // r15d
  DWORD v46; // eax
  DWORD v47; // eax
  char v48; // r12
  bool v49; // sf
  DWORD v50; // eax
  signed int v51; // eax
  int v52; // eax
  char v53; // [rsp+40h] [rbp-F8h]
  char v54; // [rsp+41h] [rbp-F7h]
  char v55; // [rsp+42h] [rbp-F6h]
  WINBOOL pbCancel; // [rsp+44h] [rbp-F4h] BYREF
  int v57; // [rsp+48h] [rbp-F0h]
  wchar_t *v58; // [rsp+50h] [rbp-E8h]
  LPCWSTR lpNewFileName; // [rsp+58h] [rbp-E0h]
  LPCWSTR v60; // [rsp+60h] [rbp-D8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-D0h]
  wchar_t *v62; // [rsp+70h] [rbp-C8h]
  const bad_hresult *v63; // [rsp+78h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+80h] [rbp-B8h] BYREF
  _BYTE v65[32]; // [rsp+A0h] [rbp-98h] BYREF
  _BYTE v66[32]; // [rsp+C0h] [rbp-78h] BYREF
  _BYTE v67[88]; // [rsp+E0h] [rbp-58h] BYREF
  unsigned int v71; // [rsp+160h] [rbp+28h]

  lpCriticalSection = &stru_18013A368;
  CCriticalSection::Lock((CCriticalSection *)&stru_18013A368);
  v7 = 0;
  v57 = 0;
  v8 = *this;
  lpNewFileName = *this;
  TemporaryFileName = _HLQS::GetTemporaryFileName((_HLQS *)this);
  v60 = TemporaryFileName;
  v10 = (wchar_t *)this[2];
  v58 = v10;
  v54 = 0;
  v55 = 0;
  v53 = 0;
  if ( a5 )
  {
    CreateLqsUnicodeFile(TemporaryFileName);
  }
  else
  {
    pbCancel = 0;
    if ( !CopyFileExW(v8, TemporaryFileName, 0, 0, &pbCancel, 0) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SSSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids,
          v8,
          TemporaryFileName,
          v10,
          LastError);
      EvReportWithError(0xC000085D, v12, 3u, v10, v8, TemporaryFileName);
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      LeaveCriticalSection(&stru_18013A368);
      return (unsigned int)v12;
    }
    if ( !SetFileAttributesW(TemporaryFileName, 0x100u) )
    {
      v17 = GetLastError();
      v15 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v17);
    }
  }
  for ( i = 0; ; i = pbCancel + 1 )
  {
    pbCancel = i;
    if ( v7 < 0 )
      goto LABEL_55;
    if ( i >= a2 )
      break;
    v15 = i;
    v19 = a3[i];
    if ( v19 > 0x7D )
    {
      v36 = v19 - 1101;
      if ( !v36 || (v37 = v36 - 3899) == 0 )
      {
LABEL_51:
        v7 = WriteProperyString(TemporaryFileName);
        continue;
      }
      if ( v37 == 1 )
      {
        v38 = &a4[v15];
        v7 = WriteProperyString(TemporaryFileName);
        if ( v38->cVal == 1 )
          v53 = 1;
      }
    }
    else
    {
      if ( v19 == 125 )
        goto LABEL_51;
      if ( v19 > 0x6B )
      {
        v29 = v19 - 108;
        if ( !v29 )
          goto LABEL_51;
        v30 = v29 - 1;
        if ( !v30 )
          goto LABEL_51;
        v31 = v30 - 1;
        if ( !v31 )
        {
          v7 = WriteProperyString(TemporaryFileName);
          v57 = 1;
          continue;
        }
        v32 = v31 - 1;
        if ( v32 )
        {
          v33 = v32 - 1;
          if ( !v33 )
            goto LABEL_51;
          if ( v33 == 1 )
          {
            v34 = &a4[v15];
            v7 = WriteProperyString(TemporaryFileName);
            if ( v34->cVal == 1 )
              v55 = 1;
          }
        }
        else
        {
          v35 = &a4[v15];
          v7 = WriteProperyString(TemporaryFileName);
          if ( v35->cVal == 1 )
            v54 = 1;
        }
      }
      else
      {
        if ( v19 == 107 )
          goto LABEL_51;
        v20 = v19 - 101;
        if ( !v20 )
          goto LABEL_51;
        v21 = v20 - 1;
        if ( !v21 )
          goto LABEL_51;
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( !v23 || v23 - 1 <= 1 )
            goto LABEL_51;
        }
        else
        {
          v24 = v15;
          v25 = mqwcslen(a4[v15].bstrVal) + 1;
          v26 = (wchar_t *)MmAllocate(saturated_mul(v25, 2u));
          v62 = v26;
          v27 = StringCchCopyW(v26, v25, a4[v24].bstrVal);
          v28 = v27;
          if ( v27 < 0 )
          {
            LogMsgHR(v27, (wchar_t *)L"lqs", 0x140Au);
            free(v26);
            LeaveCriticalSection(&stru_18013A368);
            return v28;
          }
          CharLowerW(v26);
          if ( wcschr(v26, 0x5Cu) )
          {
            v7 = WriteProperyString(TemporaryFileName);
            free(v26);
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
            v7 = -1072824314;
            free(v26);
          }
        }
      }
    }
  }
  if ( !v57 )
  {
    v57 = time(0);
    v7 = WriteProperyString(TemporaryFileName);
  }
LABEL_55:
  if ( a5 == 1 && !v53 )
  {
    LOBYTE(v16) = v54;
    LOBYTE(v14) = v55;
    MqAddTelemetryQueueInfo(v15, v14, v16, *((unsigned int *)this + 10), g_msmqMode);
  }
  try
  {
    v39 = lpNewFileName;
    if ( v7 < 0 )
    {
      LogMsgHR(v7, (wchar_t *)L"lqs", 0x5DDu);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v7);
      throw (bad_hresult *)pExceptionObject;
    }
    v40 = WriteProperyString(TemporaryFileName);
    v41 = v40;
    if ( v40 < 0 )
    {
      LogMsgHR(v40, (wchar_t *)L"lqs", 0x5DEu);
      bad_win32_error::bad_win32_error((bad_win32_error *)v65, v41);
      throw (bad_hresult *)v65;
    }
    if ( !(unsigned int)LqspFlushFile(TemporaryFileName) )
    {
      v42 = GetLastError();
      v43 = v42;
      if ( v42 )
      {
        LogMsgNTStatus(v42, (wchar_t *)L"lqs", 0x5F1u);
        if ( v43 > 0 )
          v43 = (unsigned __int16)v43 | 0x80070000;
      }
      bad_win32_error::bad_win32_error((bad_win32_error *)v66, v43);
      throw (bad_hresult *)v66;
    }
    v44 = 0;
    if ( !a5 )
    {
      v45 = ReplaceFileW(v39, TemporaryFileName, 0, 1u, 0, 0);
      if ( v45 )
        goto LABEL_81;
      v50 = GetLastError();
      v44 = v50;
      if ( v50 )
        LogMsgNTStatus(v50, (wchar_t *)L"lqs", 0x5F4u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SSSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids,
          v39,
          TemporaryFileName,
          v58,
          v44);
LABEL_82:
      EvReportWithError(0xC000085E, v44, 3u, v58, v39, TemporaryFileName);
      v49 = v44 < 0;
      if ( v44 > 0 )
      {
        v44 = (unsigned __int16)v44 | 0x80070000;
        v49 = v44 < 0;
      }
      if ( v49 )
        LogMsgHR(v44, (wchar_t *)L"lqs", 0x5F5u);
      bad_win32_error::bad_win32_error((bad_win32_error *)v67, v44);
      throw (bad_hresult *)v67;
    }
    v45 = MoveFileExW(TemporaryFileName, v39, 9u);
    if ( !v45 )
    {
      v46 = GetLastError();
      v44 = v46;
      if ( v46 )
        LogMsgNTStatus(v46, (wchar_t *)L"lqs", 0x5F2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SSSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids,
          TemporaryFileName,
          v39,
          v58,
          v44);
    }
    if ( !SetFileAttributesW(v39, 0x20u) )
    {
      v47 = GetLastError();
      v48 = v47;
      if ( v47 )
        LogMsgNTStatus(v47, (wchar_t *)L"lqs", 0x5F3u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v58, v48);
      v39 = lpNewFileName;
    }
LABEL_81:
    if ( !v45 )
      goto LABEL_82;
  }
  catch ( const bad_hresult *v63 )
  {
    if ( !DeleteFileW(v60) )
    {
      v51 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( v51 > 0 )
          v51 = (unsigned __int16)v51 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids,
          (unsigned int)v51);
      }
    }
    v52 = (*(__int64 (__fastcall **)(const bad_hresult *))(*(_QWORD *)v63 + 16LL))(v63);
    v71 = v52;
    if ( v52 < 0 )
      LogMsgHR(v52, (wchar_t *)L"lqs", 0x482u);
    LeaveCriticalSection(lpCriticalSection);
    return v71;
  }
  LeaveCriticalSection(&stru_18013A368);
  return 0;
}

```

## disassembly

```asm
0x180029950  mov     [rsp+arg_10], r8
0x180029955  mov     [rsp+arg_8], edx
0x180029959  mov     [rsp+arg_0], rcx
0x18002995e  push    rbx
0x18002995f  push    rsi
0x180029960  push    rdi
0x180029961  push    r12
0x180029963  push    r13
0x180029965  push    r14
0x180029967  push    r15
0x180029969  sub     rsp, 100h
0x180029970  mov     r15, r9
0x180029973  mov     r14, rcx
0x180029976  lea     rbx, stru_18013A368
0x18002997d  mov     [rsp+138h+lpCriticalSection], rbx
0x180029982  mov     rcx, rbx; this
0x180029985  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18002998a  nop
0x18002998b  xor     edi, edi
0x18002998d  xor     eax, eax
0x18002998f  mov     [rsp+138h+var_F0], eax
0x180029993  mov     r12, [r14]
0x180029996  mov     [rsp+138h+lpNewFileName], r12
0x18002999b  mov     rcx, r14; this
0x18002999e  call    ?GetTemporaryFileName@_HLQS@@QEAAPEB_WXZ; _HLQS::GetTemporaryFileName(void)
0x1800299a3  mov     rsi, rax
0x1800299a6  mov     [rsp+138h+var_D8], rax
0x1800299ab  mov     r14, [r14+10h]
0x1800299af  mov     [rsp+138h+var_E8], r14
0x1800299b4  xor     r8b, r8b
0x1800299b7  mov     [rsp+138h+var_F7], r8b
0x1800299bc  xor     dl, dl
0x1800299be  mov     [rsp+138h+var_F6], dl
0x1800299c2  xor     al, al
0x1800299c4  mov     [rsp+138h+var_F8], al
0x1800299c8  cmp     [rsp+138h+arg_20], edi
0x1800299cf  jnz     loc_180029AD9
0x1800299d5  mov     [rsp+138h+var_F4], edi
0x1800299d9  mov     [rsp+138h+dwCopyFlags], edi; dwCopyFlags
0x1800299dd  lea     rax, [rsp+138h+var_F4]
0x1800299e2  mov     [rsp+138h+pbCancel], rax; pbCancel
0x1800299e7  xor     r9d, r9d; lpData
0x1800299ea  xor     r8d, r8d; lpProgressRoutine
0x1800299ed  mov     rdx, rsi; lpNewFileName
0x1800299f0  mov     rcx, r12; lpExistingFileName
0x1800299f3  call    cs:__imp_CopyFileExW
0x1800299f9  test    eax, eax
0x1800299fb  jnz     loc_180029A85
0x180029a01  call    cs:__imp_GetLastError
0x180029a07  mov     edi, eax
0x180029a09  lea     r13, WPP_GLOBAL_Control
0x180029a10  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a17  cmp     rcx, r13
0x180029a1a  jz      short loc_180029A48
0x180029a1c  test    byte ptr [rcx+1Ch], 1
0x180029a20  jz      short loc_180029A48
0x180029a22  mov     edx, 16h
0x180029a27  mov     [rsp+138h+var_108], eax
0x180029a2b  mov     qword ptr [rsp+138h+dwCopyFlags], r14
0x180029a30  mov     [rsp+138h+pbCancel], rsi
0x180029a35  mov     r9, r12
0x180029a38  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x180029a3f  mov     rcx, [rcx+10h]
0x180029a43  call    WPP_SF_SSSD
0x180029a48  mov     r8d, 3; unsigned __int16
0x180029a4e  mov     qword ptr [rsp+138h+dwCopyFlags], rsi
0x180029a53  mov     [rsp+138h+pbCancel], r12
0x180029a58  mov     r9, r14
0x180029a5b  mov     edx, edi; dwMessageId
0x180029a5d  mov     ecx, 0C000085Dh; unsigned int
0x180029a62  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x180029a67  test    edi, edi
0x180029a69  jle     short loc_180029A74
0x180029a6b  movzx   edi, di
0x180029a6e  or      edi, 80070000h
0x180029a74  mov     rcx, rbx; lpCriticalSection
0x180029a77  call    cs:__imp_LeaveCriticalSection
0x180029a7d  nop
0x180029a7e  mov     eax, edi
0x180029a80  jmp     loc_18002A21E
0x180029a85  mov     edx, 100h; dwFileAttributes
0x180029a8a  mov     rcx, rsi; lpFileName
0x180029a8d  call    cs:__imp_SetFileAttributesW
0x180029a93  test    eax, eax
0x180029a95  jnz     short loc_180029AE1
0x180029a97  call    cs:__imp_GetLastError
0x180029a9d  lea     r13, WPP_GLOBAL_Control
0x180029aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180029aab  cmp     rcx, r13
0x180029aae  jz      short loc_180029AE8
0x180029ab0  test    byte ptr [rcx+1Ch], 1
0x180029ab4  jz      short loc_180029AE8
0x180029ab6  mov     edx, 17h
0x180029abb  mov     [rsp+138h+dwCopyFlags], eax; char
0x180029abf  mov     [rsp+138h+pbCancel], r14; wchar_t *
0x180029ac4  mov     r9, rsi
0x180029ac7  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x180029ace  mov     rcx, [rcx+10h]; LoggerHandle
0x180029ad2  call    WPP_SF_SSD
0x180029ad7  jmp     short loc_180029AE8
0x180029ad9  mov     rcx, rsi; wchar_t *
0x180029adc  call    ?CreateLqsUnicodeFile@@YAJPEB_W@Z; CreateLqsUnicodeFile(wchar_t const *)
0x180029ae1  lea     r13, WPP_GLOBAL_Control
0x180029ae8  xor     eax, eax
0x180029aea  mov     [rsp+138h+var_F4], eax
0x180029aee  test    edi, edi
0x180029af0  js      loc_180029EAA
0x180029af6  cmp     eax, [rsp+138h+arg_8]
0x180029afd  jnb     loc_180029E76
0x180029b03  mov     ecx, eax
0x180029b05  mov     rax, [rsp+138h+arg_10]
0x180029b0d  mov     eax, [rax+rcx*4]
0x180029b10  cmp     eax, 7Dh ; '}'
0x180029b13  ja      loc_180029DEE
0x180029b19  jz      loc_180029DE2
0x180029b1f  cmp     eax, 6Bh ; 'k'
0x180029b22  ja      loc_180029CDB
0x180029b28  jz      loc_180029CC6
0x180029b2e  sub     eax, 65h ; 'e'
0x180029b31  jz      loc_180029CBD
0x180029b37  sub     eax, 1
0x180029b3a  jz      loc_180029C99
0x180029b40  sub     eax, 1
0x180029b43  jz      short loc_180029BA0
0x180029b45  sub     eax, 1
0x180029b48  jz      short loc_180029B88
0x180029b4a  sub     eax, 1
0x180029b4d  jz      short loc_180029B70
0x180029b4f  cmp     eax, 1
0x180029b52  jnz     loc_180029E6B
0x180029b58  lea     r8, [rcx+rcx*2]
0x180029b5c  lea     r9, [r15+8]
0x180029b60  lea     r9, [r9+r8*8]
0x180029b64  lea     rdx, aBasepriority; "BasePriority"
0x180029b6b  jmp     loc_180029CA9
0x180029b70  lea     r8, [rcx+rcx*2]
0x180029b74  lea     r9, [r15+8]
0x180029b78  lea     r9, [r9+r8*8]
0x180029b7c  lea     rdx, aQuota; "Quota"
0x180029b83  jmp     loc_180029CA9
0x180029b88  lea     r8, [rcx+rcx*2]
0x180029b8c  lea     r9, [r15+8]
0x180029b90  lea     r9, [r9+r8*8]
0x180029b94  lea     rdx, aJournal; "Journal"
0x180029b9b  jmp     loc_180029CA9
0x180029ba0  lea     r12, [rcx+rcx*2]
0x180029ba4  mov     rcx, [r15+r12*8+8]; wchar_t *
0x180029ba9  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180029bae  lea     edi, [rax+1]
0x180029bb1  mov     eax, 2
0x180029bb6  mul     rdi
0x180029bb9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180029bc0  cmovb   rax, rcx
0x180029bc4  mov     rcx, rax; unsigned __int64
0x180029bc7  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180029bcc  mov     r14, rax
0x180029bcf  mov     [rsp+138h+var_C8], rax
0x180029bd4  mov     r8, [r15+r12*8+8]; wchar_t *
0x180029bd9  mov     edx, edi; unsigned __int64
0x180029bdb  mov     rcx, rax; wchar_t *
0x180029bde  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180029be3  mov     edi, eax
0x180029be5  test    eax, eax
0x180029be7  jns     short loc_180029C19
0x180029be9  mov     r8d, 140Ah; unsigned __int16
0x180029bef  lea     rdx, aLqs_0; "lqs"
0x180029bf6  mov     ecx, eax; int
0x180029bf8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029bfd  nop
0x180029bfe  mov     rcx, r14; Block
0x180029c01  call    cs:__imp_free
0x180029c07  nop
0x180029c08  mov     rcx, rbx; lpCriticalSection
0x180029c0b  call    cs:__imp_LeaveCriticalSection
0x180029c11  nop
0x180029c12  mov     eax, edi
0x180029c14  jmp     loc_18002A21E
0x180029c19  mov     rcx, r14; lpsz
0x180029c1c  call    cs:__imp_CharLowerW
0x180029c22  mov     edx, 5Ch ; '\'; Ch
0x180029c27  mov     rcx, r14; Str
0x180029c2a  call    cs:__imp_wcschr
0x180029c30  test    rax, rax
0x180029c33  jnz     short loc_180029C71
0x180029c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c3c  cmp     rcx, r13
0x180029c3f  jz      short loc_180029C5D
0x180029c41  test    byte ptr [rcx+1Ch], 1
0x180029c45  jz      short loc_180029C5D
0x180029c47  lea     edx, [rax+18h]
0x180029c4a  mov     r9, r14
0x180029c4d  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x180029c54  mov     rcx, [rcx+10h]; LoggerHandle
0x180029c58  call    WPP_SF_S
0x180029c5d  mov     edi, 0C00E0006h
0x180029c62  mov     rcx, r14; Block
0x180029c65  call    cs:__imp_free
0x180029c6b  nop
0x180029c6c  jmp     loc_180029E6B
0x180029c71  mov     r9, rax
0x180029c74  movzx   r8d, word ptr [r15+r12*8]
0x180029c79  lea     rdx, aQueuename; "QueueName"
0x180029c80  mov     rcx, rsi; lpFileName
0x180029c83  call    WriteProperyString
0x180029c88  mov     edi, eax
0x180029c8a  mov     rcx, r14; Block
0x180029c8d  call    cs:__imp_free
0x180029c93  nop
0x180029c94  jmp     loc_180029E6B
0x180029c99  lea     rdx, aType; "Type"
0x180029ca0  lea     r8, [rcx+rcx*2]
0x180029ca4  mov     r9, [r15+r8*8+8]
0x180029ca9  movzx   r8d, word ptr [r15+r8*8]
0x180029cae  mov     rcx, rsi; lpFileName
0x180029cb1  call    WriteProperyString
0x180029cb6  mov     edi, eax
0x180029cb8  jmp     loc_180029E6B
0x180029cbd  lea     rdx, aInstance; "Instance"
0x180029cc4  jmp     short loc_180029CA0
0x180029cc6  lea     r8, [rcx+rcx*2]
0x180029cca  lea     r9, [r15+8]
0x180029cce  lea     r9, [r9+r8*8]
0x180029cd2  lea     rdx, aJournalquota; "JournalQuota"
0x180029cd9  jmp     short loc_180029CA9
0x180029cdb  sub     eax, 6Ch ; 'l'
0x180029cde  jz      loc_180029DD6
0x180029ce4  sub     eax, 1
0x180029ce7  jz      loc_180029DBE
0x180029ced  sub     eax, 1
0x180029cf0  jz      loc_180029D8F
0x180029cf6  sub     eax, 1
0x180029cf9  jz      short loc_180029D58
0x180029cfb  sub     eax, 1
0x180029cfe  jz      short loc_180029D40
0x180029d00  cmp     eax, 1
0x180029d03  jnz     loc_180029E6B
0x180029d09  lea     r8, [rcx+rcx*2]
0x180029d0d  lea     r14, [r15+r8*8]
0x180029d11  lea     r9, [r14+8]
0x180029d15  movzx   r8d, word ptr [r15+r8*8]
0x180029d1a  lea     rdx, aTransaction; "Transaction"
0x180029d21  mov     rcx, rsi; lpFileName
0x180029d24  call    WriteProperyString
0x180029d29  mov     edi, eax
0x180029d2b  cmp     byte ptr [r14+8], 1
0x180029d30  jnz     loc_180029E6B
0x180029d36  mov     [rsp+138h+var_F6], 1
0x180029d3b  jmp     loc_180029E6B
0x180029d40  lea     r8, [rcx+rcx*2]
0x180029d44  lea     r9, [r15+8]
0x180029d48  lea     r9, [r9+r8*8]
0x180029d4c  lea     rdx, aPrivlevel; "PrivLevel"
0x180029d53  jmp     loc_180029CA9
0x180029d58  lea     r8, [rcx+rcx*2]
0x180029d5c  lea     r14, [r15+r8*8]
0x180029d60  lea     r9, [r14+8]
0x180029d64  movzx   r8d, word ptr [r15+r8*8]
0x180029d69  lea     rdx, aAuthenticate; "Authenticate"
0x180029d70  mov     rcx, rsi; lpFileName
0x180029d73  call    WriteProperyString
0x180029d78  mov     edi, eax
0x180029d7a  cmp     byte ptr [r14+8], 1
0x180029d7f  jnz     loc_180029E6B
0x180029d85  mov     [rsp+138h+var_F7], 1
0x180029d8a  jmp     loc_180029E6B
0x180029d8f  lea     r8, [rcx+rcx*2]
0x180029d93  lea     r9, [r15+8]
0x180029d97  lea     r9, [r9+r8*8]
0x180029d9b  movzx   r8d, word ptr [r15+r8*8]
0x180029da0  lea     rdx, aModifytime; "ModifyTime"
0x180029da7  mov     rcx, rsi; lpFileName
0x180029daa  call    WriteProperyString
0x180029daf  mov     edi, eax
0x180029db1  mov     [rsp+138h+var_F0], 1
0x180029db9  jmp     loc_180029E6B
0x180029dbe  lea     r8, [rcx+rcx*2]
0x180029dc2  lea     r9, [r15+8]
0x180029dc6  lea     r9, [r9+r8*8]
0x180029dca  lea     rdx, aCreatetime; "CreateTime"
0x180029dd1  jmp     loc_180029CA9
0x180029dd6  lea     rdx, aLabel; "Label"
0x180029ddd  jmp     loc_180029CA0
0x180029de2  lea     rdx, aMulticastaddre; "MulticastAddress"
0x180029de9  jmp     loc_180029CA0
0x180029dee  sub     eax, 44Dh
0x180029df3  jz      short loc_180029E49
0x180029df5  sub     eax, 0F3Bh
0x180029dfa  jz      short loc_180029E31
0x180029dfc  cmp     eax, 1
0x180029dff  jnz     short loc_180029E6B
0x180029e01  lea     r8, [rcx+rcx*2]
0x180029e05  lea     r14, [r15+r8*8]
0x180029e09  lea     r9, [r14+8]
0x180029e0d  movzx   r8d, word ptr [r15+r8*8]
0x180029e12  lea     rdx, aSystemqueue; "SystemQueue"
0x180029e19  mov     rcx, rsi; lpFileName
0x180029e1c  call    WriteProperyString
0x180029e21  mov     edi, eax
0x180029e23  cmp     byte ptr [r14+8], 1
0x180029e28  jnz     short loc_180029E6B
  ... truncated ...
```
