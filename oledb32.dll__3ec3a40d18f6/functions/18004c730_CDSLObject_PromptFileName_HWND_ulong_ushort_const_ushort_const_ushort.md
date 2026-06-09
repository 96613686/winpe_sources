# CDSLObject::PromptFileName(HWND__ *,ulong,ushort const *,ushort const *,ushort * *)

- ea: `0x18004c730`
- end: `0x18004cf9b`
- name: `?PromptFileName@CDSLObject@@UEAAJPEAUHWND__@@KPEBG1PEAPEAG@Z`
- size: `2155`
- prototype: `__int64 __fastcall(CDSLObject *__hidden this, HWND, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800112b0`
- `0x180013870`
- `0x180029414`
- `0x180029560`
- `0x180029c30`
- `0x18003c270`
- `0x18004b548`
- `0x18004c730`
- `0x18004d664`
- `0x18004d88c`
- `0x18004da48`
- `0x18007e6ca`
- `0x18007e700`
- `0x18007e7c0`
- `0x180087010`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18004cccd`
- `KERNEL32!CreateDirectoryW` at `0x18004cccd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004c7ce`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004c7ce`
- `USER32!LoadStringW` at `0x18004cabc`
- `USER32!LoadStringW` at `0x18004caf8`
- `USER32!LoadStringW` at `0x18004cb52`
- `USER32!LoadStringW` at `0x18004cd1f`
- `USER32!LoadStringW` at `0x18004cabc`
- `USER32!LoadStringW` at `0x18004caf8`
- `USER32!LoadStringW` at `0x18004cb52`
- `USER32!LoadStringW` at `0x18004cd1f`
- `ADVAPI32!RegQueryValueExW` at `0x18004cbf6`
- `ADVAPI32!RegQueryValueExW` at `0x18004cbf6`
- `ADVAPI32!RegOpenKeyExW` at `0x18004cbc3`
- `ADVAPI32!RegOpenKeyExW` at `0x18004cbc3`
- `ADVAPI32!RegCloseKey` at `0x18004cce0`
- `ADVAPI32!RegCloseKey` at `0x18004cce0`
- `ole32!CoTaskMemAlloc` at `0x18004cd79`
- `ole32!CoTaskMemAlloc` at `0x18004cd79`

## string_xrefs

- `0x18004cbe0`: `CommonFilesDir`
- `0x18004cc04`: `\System\OLE DB\Data Links`

## pseudocode

```c
__int64 __fastcall CDSLObject::PromptFileName(
        CDSLObject *this,
        HWND a2,
        int a3,
        BYTE *a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6)
{
  unsigned int BidID; // eax
  unsigned int v10; // edi
  __int64 v11; // rdx
  HINSTANCE v12; // r15
  int v13; // ebx
  UINT v14; // edx
  int v15; // eax
  __int64 v16; // rax
  unsigned __int64 v17; // rdi
  unsigned __int16 *v18; // rax
  int v19; // eax
  unsigned int v20; // r8d
  int lpcbData; // [rsp+28h] [rbp-D8h]
  int lpcbDataa; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+70h] [rbp-90h] BYREF
  HWND v29; // [rsp+78h] [rbp-88h]
  HINSTANCE v30; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 *v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+B8h] [rbp-48h]
  BYTE *v39; // [rsp+C0h] [rbp-40h]
  WCHAR *v40; // [rsp+C8h] [rbp-38h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  WCHAR *v42; // [rsp+D8h] [rbp-28h]
  __int64 v43; // [rsp+E0h] [rbp-20h]
  unsigned __int64 (__fastcall *v44)(HWND, unsigned int, unsigned __int64, __int64); // [rsp+E8h] [rbp-18h]
  __int64 v45; // [rsp+F0h] [rbp-10h]
  WCHAR Data[260]; // [rsp+110h] [rbp+10h] BYREF
  __int16 v47; // [rsp+318h] [rbp+218h]
  unsigned __int16 v48[264]; // [rsp+350h] [rbp+250h] BYREF
  WCHAR Buffer; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v50[1022]; // [rsp+562h] [rbp+462h] BYREF
  unsigned __int16 v51; // [rsp+960h] [rbp+860h] BYREF
  _BYTE v52[1022]; // [rsp+962h] [rbp+862h] BYREF
  WCHAR v53; // [rsp+D60h] [rbp+C60h] BYREF
  _BYTE v54[1022]; // [rsp+D62h] [rbp+C62h] BYREF
  WCHAR v55; // [rsp+1160h] [rbp+1060h] BYREF
  _BYTE v56[1022]; // [rsp+1162h] [rbp+1062h] BYREF

  v25 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1800C9560[0] )
  {
    BidID = CDSLObject::GetBidID(this);
    v24 = a5;
    bidScopeEnterW(&v25, off_1800C9560[0], BidID, a2, a3, a4);
  }
  SetErrorInfo(0, 0);
  if ( a6 )
  {
    if ( (a3 & 0xFFFFFFF7) == 0 )
    {
      memset_0(v48, 0, 0x208u);
      v12 = hInstance;
      v13 = a3 & 8;
      if ( a5 && *a5 )
      {
        if ( (int)StringCchCopyW(v48, 0x104u, a5) < 0 )
        {
          v10 = -2147287038;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147287038, L"<CDSLObject::PromptFileName|OLEDB|ERR> ", 0x492u);
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_1800C9210[0] )
                bidTraceW(off_1800C83C8[0], 1199104, off_1800C9210[0], 2147680258LL, (_DWORD)a6, lpcbData, v24);
            }
          }
          if ( (bidGblFlags & 4) != 0 && v25 != -1 && bidID != -1 )
            ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v25);
          if ( (bidGblFlags & 2) != 0 )
          {
            v11 = 1200137;
            return (unsigned int)bidTraceHR(off_1800C83C8[0], v11, L"<CDSLObject::PromptFileName|Trace|HR> ", v10);
          }
          return v10;
        }
      }
      else if ( v13 )
      {
        StringCchCopyW(v48, 0x104u, L"*.UDL");
      }
      memset_0(&v28, 0, 0x98u);
      v29 = a2;
      v28 = 152;
      v30 = v12;
      Buffer = 0;
      memset_0(v50, 0, sizeof(v50));
      v51 = 0;
      memset_0(v52, 0, sizeof(v52));
      v53 = 0;
      memset_0(v54, 0, sizeof(v54));
      if ( v13 )
      {
        LoadStringW(v12, 0x60u, &Buffer, 512);
        lpcbDataa = 0;
        StringCchPrintfW(&v51, 0x200u, &Buffer, 0, 0);
        v14 = 98;
      }
      else
      {
        LoadStringW(v12, 0x61u, &Buffer, 512);
        lpcbDataa = 0;
        StringCchPrintfW(&v51, 0x200u, &Buffer, 0, 0);
        v14 = 99;
      }
      v31 = &v51;
      LoadStringW(v12, v14, &v53, 512);
      v32 = 0;
      v40 = &v53;
      v35 = v48;
      v33 = 0;
      v34 = 1;
      v36 = 260;
      v37 = 0;
      v38 = 0;
      hKey = 0;
      cbData = 260;
      if ( a4 )
      {
        v39 = a4;
      }
      else if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion", 0, 0x20019u, &hKey) )
      {
        if ( !RegQueryValueExW(hKey, L"CommonFilesDir", 0, 0, (LPBYTE)Data, &cbData) )
        {
          v47 = 0;
          v15 = StringCchCatW(Data, 0x11Eu, L"\\System\\OLE DB\\Data Links");
          v10 = v15;
          if ( v15 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v15, L"<CDSLObject::PromptFileName|OLEDB|ERR> ", 0x4E9u);
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( off_1800C9208[0] )
                  bidTraceW(off_1800C83C8[0], 1288192, off_1800C9208[0], v10, (_DWORD)a6, lpcbDataa, 0);
              }
            }
            if ( (bidGblFlags & 4) != 0 && v25 != -1 && bidID != -1 )
              ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v25);
            if ( (bidGblFlags & 2) != 0 )
            {
              v11 = 1289225;
              return (unsigned int)bidTraceHR(off_1800C83C8[0], v11, L"<CDSLObject::PromptFileName|Trace|HR> ", v10);
            }
            return v10;
          }
          CreateDirectoryW(Data, 0);
          v39 = (BYTE *)Data;
        }
        RegCloseKey(hKey);
      }
      v41 = 524356;
      v55 = 0;
      memset_0(v56, 0, sizeof(v56));
      LoadStringW(v12, 0x5Du, &v55, 512);
      LODWORD(v41) = v41 | 0x20;
      v42 = &v55;
      v43 = 0;
      v44 = CDSLObject::NonOrganizeHook;
      v45 = 201;
      if ( (unsigned int)IsolationAwareGetOpenFileNameW(&v28) )
      {
        v16 = -1;
        do
          ++v16;
        while ( v35[v16] );
        v17 = (unsigned int)(v16 + 1);
        v18 = (unsigned __int16 *)CoTaskMemAlloc(2 * v17);
        *a6 = v18;
        if ( !v18 )
        {
          v10 = -2147024882;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024882, L"<CDSLObject::PromptFileName|OLEDB|ERR> ", 0x521u);
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_1800C9200[0] )
                bidTraceW(off_1800C83C8[0], 1345536, off_1800C9200[0], 2147942414LL, (_DWORD)a6, lpcbDataa, 0);
            }
          }
          if ( (bidGblFlags & 4) != 0 && v25 != -1 && bidID != -1 )
            ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v25);
          if ( (bidGblFlags & 2) != 0 )
          {
            v11 = 1346569;
            return (unsigned int)bidTraceHR(off_1800C83C8[0], v11, L"<CDSLObject::PromptFileName|Trace|HR> ", v10);
          }
          return v10;
        }
        v10 = StringCchCopyW(v18, v17, v35);
      }
      else
      {
        v19 = IsolationAwareCommDlgExtendedError();
        if ( v19 )
        {
          if ( v19 == 12290 )
          {
            v10 = -2147287038;
            if ( (bidGblFlags & 2) == 0 )
              return v10;
            v20 = 1332;
          }
          else
          {
            v10 = -2147467259;
            if ( (bidGblFlags & 2) == 0 )
              return v10;
            v20 = 1338;
          }
        }
        else
        {
          v10 = -2147217842;
          if ( (bidGblFlags & 2) == 0 )
            return v10;
          v20 = 1326;
        }
        OLEDBTraceErr(v10, L"<CDSLObject::PromptFileName|OLEDB|ERR> ", v20);
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v10, L"<CDSLObject::PromptFileName|OLEDB|ERR> ", 0x53Fu);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (v10 & 0x80000000) != 0 )
          {
            if ( off_1800C91F0[0] )
              bidTraceW(off_1800C83C8[0], 1376256, off_1800C91F0[0], v10, (_DWORD)a6, lpcbDataa, 0);
          }
          else if ( off_1800C91F8[0] )
          {
            bidTraceW(off_1800C83C8[0], 1376256, off_1800C91F8[0], v10, (unsigned int)*a6, lpcbDataa, 0);
          }
          if ( (bidGblFlags & 4) != 0 && v25 != -1 && bidID != -1 )
            ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v25);
          if ( (bidGblFlags & 2) != 0 )
          {
            v11 = 1377289;
            return (unsigned int)bidTraceHR(off_1800C83C8[0], v11, L"<CDSLObject::PromptFileName|Trace|HR> ", v10);
          }
        }
      }
      return v10;
    }
    v10 = -2147024809;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024809, L"<CDSLObject::PromptFileName|OLEDB|ERR> ", 0x481u);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C9218[0] )
          bidTraceW(off_1800C83C8[0], 1181696, off_1800C9218[0], 2147942487LL, (_DWORD)a6, lpcbData, v24);
      }
    }
    if ( (bidGblFlags & 4) != 0 && v25 != -1 && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v25);
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 1182729;
      return (unsigned int)bidTraceHR(off_1800C83C8[0], v11, L"<CDSLObject::PromptFileName|Trace|HR> ", v10);
    }
  }
  else
  {
    v10 = -2147024809;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024809, L"<CDSLObject::PromptFileName|OLEDB|ERR> ", 0x47Bu);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C9220[0] )
          bidTraceW(off_1800C83C8[0], 1175552, off_1800C9220[0], 2147942487LL, 0, lpcbData, v24);
      }
    }
    if ( (bidGblFlags & 4) != 0 && v25 != -1 && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v25);
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 1176585;
      return (unsigned int)bidTraceHR(off_1800C83C8[0], v11, L"<CDSLObject::PromptFileName|Trace|HR> ", v10);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18004c730  push    rbp
0x18004c732  push    rbx
0x18004c733  push    rsi
0x18004c734  push    rdi
0x18004c735  push    r12
0x18004c737  push    r13
0x18004c739  push    r14
0x18004c73b  push    r15
0x18004c73d  lea     rbp, [rsp-1478h]
0x18004c745  mov     eax, 1578h
0x18004c74a  call    _alloca_probe
0x18004c74f  sub     rsp, rax
0x18004c752  mov     rax, cs:__security_cookie
0x18004c759  xor     rax, rsp
0x18004c75c  mov     [rbp+14B0h+var_50], rax
0x18004c763  mov     rdi, [rbp+14B0h+arg_20]
0x18004c76a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004c76e  mov     rsi, [rbp+14B0h+arg_28]
0x18004c775  xor     r13d, r13d
0x18004c778  test    byte ptr cs:_bidGblFlags, 4
0x18004c77f  mov     r14, r9
0x18004c782  mov     ebx, r8d
0x18004c785  mov     [rsp+15B0h+var_1560], r15
0x18004c78a  mov     r12, rdx
0x18004c78d  jz      short loc_18004C7CA
0x18004c78f  mov     rax, cs:off_1800C9560; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004c796  test    rax, rax
0x18004c799  jz      short loc_18004C7CA
0x18004c79b  call    ?GetBidID@CDSLObject@@QEAAHXZ; CDSLObject::GetBidID(void)
0x18004c7a0  mov     rdx, cs:off_1800C9560; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004c7a7  lea     rcx, [rsp+15B0h+var_1560]
0x18004c7ac  mov     [rsp+15B0h+var_1578], rsi
0x18004c7b1  mov     r9, r12
0x18004c7b4  mov     [rsp+15B0h+var_1580], rdi
0x18004c7b9  mov     r8d, eax
0x18004c7bc  mov     [rsp+15B0h+lpcbData], r14
0x18004c7c1  mov     dword ptr [rsp+15B0h+phkResult], ebx
0x18004c7c5  call    _bidScopeEnterW
0x18004c7ca  xor     edx, edx; perrinfo
0x18004c7cc  xor     ecx, ecx; dwReserved
0x18004c7ce  call    cs:__imp_SetErrorInfo
0x18004c7d4  test    rsi, rsi
0x18004c7d7  jnz     loc_18004C87C
0x18004c7dd  mov     bl, 2
0x18004c7df  mov     edi, 80070057h
0x18004c7e4  test    byte ptr cs:_bidGblFlags, bl
0x18004c7ea  jz      short loc_18004C834
0x18004c7ec  mov     r8d, 47Bh; unsigned int
0x18004c7f2  lea     rdx, aCdslobjectProm; "<CDSLObject::PromptFileName|OLEDB|ERR> "
0x18004c7f9  mov     ecx, edi; int
0x18004c7fb  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004c800  test    byte ptr cs:_bidGblFlags, bl
0x18004c806  jz      short loc_18004C834
0x18004c808  mov     rax, cs:off_1800C9220; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004c80f  test    rax, rax
0x18004c812  jz      short loc_18004C834
0x18004c814  mov     r8, cs:off_1800C9220; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004c81b  mov     r9d, edi
0x18004c81e  mov     rcx, cs:off_1800C83C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004c825  mov     edx, 11F000h
0x18004c82a  mov     [rsp+15B0h+phkResult], r13
0x18004c82f  call    _bidTraceW
0x18004c834  test    byte ptr cs:_bidGblFlags, 4
0x18004c83b  jz      short loc_18004C866
0x18004c83d  cmp     [rsp+15B0h+var_1560], r15
0x18004c842  jz      short loc_18004C866
0x18004c844  mov     rcx, cs:_bidID
0x18004c84b  cmp     rcx, r15
0x18004c84e  jz      short loc_18004C866
0x18004c850  mov     rax, cs:off_1800BC0E8
0x18004c857  lea     r9, [rsp+15B0h+var_1560]
0x18004c85c  xor     r8d, r8d
0x18004c85f  xor     edx, edx
0x18004c861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c866  test    byte ptr cs:_bidGblFlags, bl
0x18004c86c  jz      loc_18004CF76
0x18004c872  mov     edx, 11F409h
0x18004c877  jmp     loc_18004CF5E
0x18004c87c  test    ebx, 0FFFFFFF7h
0x18004c882  jz      loc_18004C927
0x18004c888  mov     bl, 2
0x18004c88a  mov     edi, 80070057h
0x18004c88f  test    byte ptr cs:_bidGblFlags, bl
0x18004c895  jz      short loc_18004C8DF
0x18004c897  mov     r8d, 481h; unsigned int
0x18004c89d  lea     rdx, aCdslobjectProm; "<CDSLObject::PromptFileName|OLEDB|ERR> "
0x18004c8a4  mov     ecx, edi; int
0x18004c8a6  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004c8ab  test    byte ptr cs:_bidGblFlags, bl
0x18004c8b1  jz      short loc_18004C8DF
0x18004c8b3  mov     rax, cs:off_1800C9218; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004c8ba  test    rax, rax
0x18004c8bd  jz      short loc_18004C8DF
0x18004c8bf  mov     r8, cs:off_1800C9218; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004c8c6  mov     r9d, edi
0x18004c8c9  mov     rcx, cs:off_1800C83C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004c8d0  mov     edx, 120800h
0x18004c8d5  mov     [rsp+15B0h+phkResult], rsi
0x18004c8da  call    _bidTraceW
0x18004c8df  test    byte ptr cs:_bidGblFlags, 4
0x18004c8e6  jz      short loc_18004C911
0x18004c8e8  cmp     [rsp+15B0h+var_1560], r15
0x18004c8ed  jz      short loc_18004C911
0x18004c8ef  mov     rcx, cs:_bidID
0x18004c8f6  cmp     rcx, r15
0x18004c8f9  jz      short loc_18004C911
0x18004c8fb  mov     rax, cs:off_1800BC0E8
0x18004c902  lea     r9, [rsp+15B0h+var_1560]
0x18004c907  xor     r8d, r8d
0x18004c90a  xor     edx, edx
0x18004c90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c911  test    byte ptr cs:_bidGblFlags, bl
0x18004c917  jz      loc_18004CF76
0x18004c91d  mov     edx, 120C09h
0x18004c922  jmp     loc_18004CF5E
0x18004c927  xor     edx, edx; Val
0x18004c929  lea     rcx, [rbp+14B0h+var_1260]; void *
0x18004c930  mov     r8d, 208h; Size
0x18004c936  call    memset_0
0x18004c93b  mov     r15, cs:hInstance
0x18004c942  and     ebx, 8
0x18004c945  mov     eax, 104h
0x18004c94a  test    rdi, rdi
0x18004c94d  jz      loc_18004CA17
0x18004c953  cmp     [rdi], r13w
0x18004c957  jz      loc_18004CA17
0x18004c95d  mov     r8, rdi; unsigned __int16 *
0x18004c960  lea     rcx, [rbp+14B0h+var_1260]; unsigned __int16 *
0x18004c967  mov     edx, eax; unsigned __int64
0x18004c969  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004c96e  test    eax, eax
0x18004c970  jns     loc_18004CA31
0x18004c976  mov     bl, 2
0x18004c978  mov     edi, 80030002h
0x18004c97d  test    byte ptr cs:_bidGblFlags, bl
0x18004c983  jz      short loc_18004C9CD
0x18004c985  mov     r8d, 492h; unsigned int
0x18004c98b  lea     rdx, aCdslobjectProm; "<CDSLObject::PromptFileName|OLEDB|ERR> "
0x18004c992  mov     ecx, edi; int
0x18004c994  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004c999  test    byte ptr cs:_bidGblFlags, bl
0x18004c99f  jz      short loc_18004C9CD
0x18004c9a1  mov     rax, cs:off_1800C9210; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004c9a8  test    rax, rax
0x18004c9ab  jz      short loc_18004C9CD
0x18004c9ad  mov     r8, cs:off_1800C9210; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004c9b4  mov     r9d, edi
0x18004c9b7  mov     rcx, cs:off_1800C83C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004c9be  mov     edx, 124C00h
0x18004c9c3  mov     [rsp+15B0h+phkResult], rsi
0x18004c9c8  call    _bidTraceW
0x18004c9cd  test    byte ptr cs:_bidGblFlags, 4
0x18004c9d4  jz      short loc_18004CA01
0x18004c9d6  cmp     [rsp+15B0h+var_1560], 0FFFFFFFFFFFFFFFFh
0x18004c9dc  jz      short loc_18004CA01
0x18004c9de  mov     rcx, cs:_bidID
0x18004c9e5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004c9e9  jz      short loc_18004CA01
0x18004c9eb  mov     rax, cs:off_1800BC0E8
0x18004c9f2  lea     r9, [rsp+15B0h+var_1560]
0x18004c9f7  xor     r8d, r8d
0x18004c9fa  xor     edx, edx
0x18004c9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca01  test    byte ptr cs:_bidGblFlags, bl
0x18004ca07  jz      loc_18004CF76
0x18004ca0d  mov     edx, 125009h
0x18004ca12  jmp     loc_18004CF5E
0x18004ca17  test    ebx, ebx
0x18004ca19  jz      short loc_18004CA31
0x18004ca1b  lea     r8, aUdl; "*.UDL"
0x18004ca22  mov     rdx, rax; unsigned __int64
0x18004ca25  lea     rcx, [rbp+14B0h+var_1260]; unsigned __int16 *
0x18004ca2c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004ca31  mov     edi, 98h
0x18004ca36  lea     rcx, [rsp+15B0h+var_1540]; void *
0x18004ca3b  mov     r8d, edi; Size
0x18004ca3e  xor     edx, edx; Val
0x18004ca40  call    memset_0
0x18004ca45  mov     [rsp+15B0h+var_1538], r12
0x18004ca4a  lea     rcx, [rbp+14B0h+var_104E]; void *
0x18004ca51  mov     r12d, 3FEh
0x18004ca57  mov     [rsp+15B0h+var_1540], edi
0x18004ca5b  mov     r8d, r12d; Size
0x18004ca5e  mov     [rbp+14B0h+var_1530], r15
0x18004ca62  xor     edx, edx; Val
0x18004ca64  mov     [rbp+14B0h+Buffer], r13w
0x18004ca6c  call    memset_0
0x18004ca71  mov     r8d, r12d; Size
0x18004ca74  mov     [rbp+14B0h+var_C50], r13w
0x18004ca7c  xor     edx, edx; Val
0x18004ca7e  lea     rcx, [rbp+14B0h+var_C4E]; void *
0x18004ca85  call    memset_0
0x18004ca8a  mov     r8d, r12d; Size
0x18004ca8d  mov     [rbp+14B0h+var_850], r13w
0x18004ca95  xor     edx, edx; Val
0x18004ca97  lea     rcx, [rbp+14B0h+var_84E]; void *
0x18004ca9e  call    memset_0
0x18004caa3  test    ebx, ebx
0x18004caa5  lea     r8, [rbp+14B0h+Buffer]; lpBuffer
0x18004caac  mov     ebx, 200h
0x18004cab1  mov     rcx, r15; hInstance
0x18004cab4  mov     r9d, ebx; cchBufferMax
0x18004cab7  jz      short loc_18004CAF3
0x18004cab9  lea     edx, [rdi-38h]; uID
0x18004cabc  call    cs:__imp_LoadStringW
0x18004cac2  mov     [rsp+15B0h+var_1578], r13
0x18004cac7  lea     r8, [rbp+14B0h+Buffer]; unsigned __int16 *
0x18004cace  mov     [rsp+15B0h+var_1580], r13
0x18004cad3  lea     rcx, [rbp+14B0h+var_C50]; unsigned __int16 *
0x18004cada  mov     [rsp+15B0h+lpcbData], r13
0x18004cadf  xor     r9d, r9d
0x18004cae2  mov     edx, ebx; unsigned __int64
0x18004cae4  mov     [rsp+15B0h+phkResult], r13
0x18004cae9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004caee  lea     edx, [rdi-36h]
0x18004caf1  jmp     short loc_18004CB3A
0x18004caf3  mov     edx, 61h ; 'a'; uID
0x18004caf8  call    cs:__imp_LoadStringW
0x18004cafe  mov     [rsp+15B0h+var_1568], r13
0x18004cb03  lea     r8, [rbp+14B0h+Buffer]; unsigned __int16 *
0x18004cb0a  mov     [rsp+15B0h+var_1570], r13
0x18004cb0f  lea     rcx, [rbp+14B0h+var_C50]; unsigned __int16 *
0x18004cb16  mov     [rsp+15B0h+var_1578], r13
0x18004cb1b  xor     r9d, r9d
0x18004cb1e  mov     [rsp+15B0h+var_1580], r13
0x18004cb23  mov     rdx, rbx; unsigned __int64
0x18004cb26  mov     [rsp+15B0h+lpcbData], r13
0x18004cb2b  mov     [rsp+15B0h+phkResult], r13
0x18004cb30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004cb35  mov     edx, 63h ; 'c'; uID
0x18004cb3a  lea     rax, [rbp+14B0h+var_C50]
0x18004cb41  mov     r9d, ebx; cchBufferMax
0x18004cb44  lea     r8, [rbp+14B0h+var_850]; lpBuffer
0x18004cb4b  mov     [rbp+14B0h+var_1528], rax
0x18004cb4f  mov     rcx, r15; hInstance
0x18004cb52  call    cs:__imp_LoadStringW
0x18004cb58  mov     [rbp+14B0h+var_1520], r13
0x18004cb5c  lea     rax, [rbp+14B0h+var_850]
0x18004cb63  mov     [rbp+14B0h+var_14E8], rax
0x18004cb67  lea     rax, [rbp+14B0h+var_1260]
0x18004cb6e  mov     [rbp+14B0h+var_1510], rax
0x18004cb72  mov     [rbp+14B0h+var_1518], r13d
0x18004cb76  mov     [rbp+14B0h+var_1514], 1
0x18004cb7d  mov     [rbp+14B0h+var_1508], 104h
0x18004cb84  mov     [rbp+14B0h+var_1500], r13
0x18004cb88  mov     [rbp+14B0h+var_14F8], r13d
0x18004cb8c  mov     [rsp+15B0h+hKey], r13
0x18004cb91  mov     [rsp+15B0h+cbData], 104h
0x18004cb99  test    r14, r14
0x18004cb9c  jnz     loc_18004CCE8
0x18004cba2  lea     rax, [rsp+15B0h+hKey]
0x18004cba7  mov     r9d, 20019h; samDesired
0x18004cbad  xor     r8d, r8d; ulOptions
0x18004cbb0  mov     [rsp+15B0h+phkResult], rax; phkResult
0x18004cbb5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004cbbc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004cbc3  call    cs:__imp_RegOpenKeyExW
0x18004cbc9  test    eax, eax
0x18004cbcb  jnz     loc_18004CCEC
0x18004cbd1  mov     rcx, [rsp+15B0h+hKey]; hKey
0x18004cbd6  lea     rax, [rsp+15B0h+cbData]
0x18004cbdb  mov     [rsp+15B0h+lpcbData], rax; lpcbData
0x18004cbe0  lea     rdx, aCommonfilesdir; "CommonFilesDir"
0x18004cbe7  lea     rax, [rbp+14B0h+Data]
0x18004cbeb  xor     r9d, r9d; lpType
0x18004cbee  xor     r8d, r8d; lpReserved
0x18004cbf1  mov     [rsp+15B0h+phkResult], rax; lpData
0x18004cbf6  call    cs:__imp_RegQueryValueExW
0x18004cbfc  test    eax, eax
0x18004cbfe  jnz     loc_18004CCDB
0x18004cc04  lea     r8, aSystemOleDbDat; "\\System\\OLE DB\\Data Links"
0x18004cc0b  mov     [rbp+14B0h+var_1298], r13w
0x18004cc13  mov     edx, 11Eh; unsigned __int64
0x18004cc18  lea     rcx, [rbp+14B0h+Data]; unsigned __int16 *
0x18004cc1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004cc21  mov     edi, eax
0x18004cc23  test    eax, eax
0x18004cc25  jns     loc_18004CCC7
0x18004cc2b  mov     bl, 2
0x18004cc2d  test    byte ptr cs:_bidGblFlags, bl
0x18004cc33  jz      short loc_18004CC7D
0x18004cc35  mov     r8d, 4E9h; unsigned int
0x18004cc3b  lea     rdx, aCdslobjectProm; "<CDSLObject::PromptFileName|OLEDB|ERR> "
0x18004cc42  mov     ecx, eax; int
0x18004cc44  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004cc49  test    byte ptr cs:_bidGblFlags, bl
0x18004cc4f  jz      short loc_18004CC7D
0x18004cc51  mov     rax, cs:off_1800C9208; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004cc58  test    rax, rax
0x18004cc5b  jz      short loc_18004CC7D
0x18004cc5d  mov     r8, cs:off_1800C9208; "<IDBPromptInitialize::PromptFileName|AP"...
0x18004cc64  mov     r9d, edi
0x18004cc67  mov     rcx, cs:off_1800C83C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004cc6e  mov     edx, 13A800h
0x18004cc73  mov     [rsp+15B0h+phkResult], rsi
0x18004cc78  call    _bidTraceW
0x18004cc7d  test    byte ptr cs:_bidGblFlags, 4
0x18004cc84  jz      short loc_18004CCB1
0x18004cc86  cmp     [rsp+15B0h+var_1560], 0FFFFFFFFFFFFFFFFh
0x18004cc8c  jz      short loc_18004CCB1
  ... truncated ...
```
