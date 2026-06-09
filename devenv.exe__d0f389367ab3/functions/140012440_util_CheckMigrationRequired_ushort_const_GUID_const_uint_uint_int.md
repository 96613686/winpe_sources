# util_CheckMigrationRequired(ushort const *,_GUID const &,uint,uint,int *)

- ea: `0x140012440`
- end: `0x1400128df`
- name: `?util_CheckMigrationRequired@@YAJPEBGAEBU_GUID@@IIPEAH@Z`
- size: `1183`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const struct _GUID *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140001040`
- `0x140004a0c`
- `0x140004a98`
- `0x14000b5f0`
- `0x140012440`
- `0x14001e9e0`
- `0x14002fbd8`
- `0x14002fe10`
- `0x140033ab0`
- `0x140037490`
- `0x140037c08`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140012852`
- `ADVAPI32!RegCloseKey` at `0x140012852`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400125b7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400125b7`
- `KERNEL32!CreateProcessW` at `0x1400127ce`
- `KERNEL32!CreateProcessW` at `0x1400127ce`
- `KERNEL32!CloseHandle` at `0x140012809`
- `KERNEL32!CloseHandle` at `0x140012813`
- `KERNEL32!CloseHandle` at `0x140012809`
- `KERNEL32!CloseHandle` at `0x140012813`
- `USER32!MessageBoxW` at `0x140012763`
- `USER32!MessageBoxW` at `0x140012763`
- `OLEAUT32!__imp_SysAllocString` at `0x140012496`
- `OLEAUT32!__imp_SysAllocString` at `0x140012496`
- `OLEAUT32!__imp_SysFreeString` at `0x140012643`
- `OLEAUT32!__imp_SysFreeString` at `0x14001269c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400127e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400127ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1400127f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400127fd`
- `OLEAUT32!__imp_SysFreeString` at `0x14001281d`
- `OLEAUT32!__imp_SysFreeString` at `0x140012826`
- `OLEAUT32!__imp_SysFreeString` at `0x140012832`
- `OLEAUT32!__imp_SysFreeString` at `0x14001283b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001285c`
- `OLEAUT32!__imp_SysFreeString` at `0x140012643`
- `OLEAUT32!__imp_SysFreeString` at `0x14001269c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400127e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400127ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1400127f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400127fd`
- `OLEAUT32!__imp_SysFreeString` at `0x14001281d`
- `OLEAUT32!__imp_SysFreeString` at `0x140012826`
- `OLEAUT32!__imp_SysFreeString` at `0x140012832`
- `OLEAUT32!__imp_SysFreeString` at `0x14001283b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001285c`
- `OLEAUT32!__imp_SysStringLen` at `0x1400125e7`
- `OLEAUT32!__imp_SysStringLen` at `0x140012617`
- `OLEAUT32!__imp_SysStringLen` at `0x1400126b6`
- `OLEAUT32!__imp_SysStringLen` at `0x1400126ca`
- `OLEAUT32!__imp_SysStringLen` at `0x1400125e7`
- `OLEAUT32!__imp_SysStringLen` at `0x140012617`
- `OLEAUT32!__imp_SysStringLen` at `0x1400126b6`
- `OLEAUT32!__imp_SysStringLen` at `0x1400126ca`
- `OLEAUT32!__imp_VarBstrCat` at `0x140012632`
- `OLEAUT32!__imp_VarBstrCat` at `0x140012632`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall util_CheckMigrationRequired(
        const unsigned __int16 *a1,
        const struct _GUID *a2,
        __int64 a3,
        __int64 a4,
        int *a5)
{
  DWORD v6; // r15d
  unsigned __int16 *v7; // rsi
  HKEY v8; // rbx
  unsigned int v9; // r13d
  __int64 v10; // r8
  int v11; // eax
  unsigned int *v12; // r9
  unsigned __int16 *v13; // r14
  OLECHAR *v14; // rdi
  DWORD v15; // eax
  OLECHAR *v16; // rbx
  int v17; // eax
  HRESULT v18; // edi
  int v19; // eax
  OLECHAR *v20; // r12
  OLECHAR *v21; // r15
  BSTR bstrLeft; // [rsp+68h] [rbp-A0h] BYREF
  BSTR pbstr; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 *v25; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 *v26; // [rsp+80h] [rbp-88h] BYREF
  LPCWSTR lpText; // [rsp+88h] [rbp-80h] BYREF
  BSTR pbstrResult; // [rsp+90h] [rbp-78h] BYREF
  _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-70h] BYREF
  DWORD cValues; // [rsp+B0h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v32; // [rsp+C0h] [rbp-48h] BYREF
  _STARTUPINFOW StartupInfo; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t Buffer[56]; // [rsp+138h] [rbp+30h] BYREF

  v6 = 0;
  if ( !a1 || !a5 )
    return 2147942487LL;
  v7 = SysAllocString(a1);
  v25 = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(-2147024882);
  v8 = 0;
  hKey = 0;
  v32 = 0;
  util_GetPackageResourcesInstance(a1, &CLSID_VSShellMenusPackage, 0, 0, &v32);
  if ( v32 )
  {
    StringCchPrintfW(Buffer, 0x32u, L"\\Setup\\Migration\\%u");
    v10 = -1;
    do
      ++v10;
    while ( Buffer[v10] );
    v11 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v25, Buffer, v10);
    if ( v11 < 0 )
    {
      _mm_lfence();
      ATL::AtlThrowImpl(v11);
    }
    v7 = v25;
    if ( !v25 )
    {
      v9 = -2147024882;
      goto LABEL_42;
    }
    *a5 = 0;
    if ( (int)CVsRegKeyW::Open(&hKey, HKEY_LOCAL_MACHINE, v7, 0x20019u) < 0 )
    {
      v8 = hKey;
    }
    else
    {
      v13 = 0;
      v26 = 0;
      v14 = 0;
      bstrLeft = 0;
      v15 = 0;
      cValues = 0;
      v8 = hKey;
      if ( hKey )
      {
        RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
        v15 = cValues;
      }
      if ( v15 )
      {
        do
        {
          pbstr = 0;
          CVsRegKeyW::EnumValue((CVsRegKeyW *)&hKey, v6, &pbstr, v12);
          v16 = pbstr;
          if ( SysStringLen(pbstr) )
          {
            v17 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrLeft, L"\t", 1);
            if ( v17 < 0 )
            {
              _mm_lfence();
              ATL::AtlThrowImpl(v17);
            }
            if ( SysStringLen(v16) )
            {
              pbstrResult = 0;
              v18 = VarBstrCat(bstrLeft, v16, &pbstrResult);
              if ( v18 < 0 )
              {
                _mm_lfence();
                ATL::AtlThrowImpl(v18);
              }
              SysFreeString(bstrLeft);
              bstrLeft = pbstrResult;
            }
            v19 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrLeft, L"\r\n", 2);
            if ( v19 < 0 )
            {
              _mm_lfence();
              ATL::AtlThrowImpl(v19);
            }
            if ( !v13 )
            {
              CVsRegKeyW::QueryValue((CVsRegKeyW *)&hKey, v16, &v26);
              v13 = v26;
            }
            v14 = bstrLeft;
          }
          SysFreeString(v16);
          ++v6;
        }
        while ( v6 < cValues );
        v8 = hKey;
      }
      if ( SysStringLen(v14) && SysStringLen(v13) )
      {
        *a5 = 1;
        if ( !(unsigned int)util_GetPackageResourcesInstance(
                              a1,
                              &CLSID_VSShellMenusPackage,
                              0,
                              (HINSTANCE *)&pbstrResult,
                              0) )
        {
          v9 = -2147024809;
LABEL_36:
          SysFreeString(v14);
          SysFreeString(v13);
          goto LABEL_42;
        }
        lpText = 0;
        pbstr = 0;
        ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&pbstr, (HINSTANCE)pbstrResult, 0xBB8u);
        util_FormatString((HINSTANCE)pbstrResult, 0x1A36u, v14, (unsigned __int16 **)&lpText);
        v20 = pbstr;
        v21 = (OLECHAR *)lpText;
        if ( !lpText )
        {
          v9 = -2147024882;
LABEL_35:
          SysFreeString(v20);
          SysFreeString(v21);
          goto LABEL_36;
        }
        if ( MessageBoxW(0, lpText, pbstr, 0x11u) == 1 )
        {
          memset_0(&StartupInfo.cb + 1, 0, 0x64u);
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          StartupInfo.cb = 104;
          if ( !CreateProcessW(v13, 0, 0, 0, 1, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
          {
            v9 = -2147024809;
            goto LABEL_35;
          }
          CloseHandle(ProcessInformation.hThread);
          CloseHandle(ProcessInformation.hProcess);
        }
        SysFreeString(v20);
        SysFreeString(v21);
      }
      SysFreeString(v14);
      SysFreeString(v13);
    }
    v9 = 0;
    goto LABEL_42;
  }
  v9 = -2147024809;
LABEL_42:
  if ( v8 )
    RegCloseKey(v8);
  SysFreeString(v7);
  return v9;
}

```

## disassembly

```asm
0x140012440  mov     rax, rsp
0x140012443  mov     [rax+10h], rbx
0x140012447  mov     [rax+18h], rsi
0x14001244b  mov     [rax+20h], rdi
0x14001244f  push    rbp
0x140012450  push    r12
0x140012452  push    r13
0x140012454  push    r14
0x140012456  push    r15
0x140012458  lea     rbp, [rax-0D8h]
0x14001245f  sub     rsp, 1B0h
0x140012466  mov     rax, cs:__security_cookie
0x14001246d  xor     rax, rsp
0x140012470  mov     [rbp+0D0h+var_30], rax
0x140012477  mov     r12, rcx
0x14001247a  mov     r13, [rbp+0D0h+arg_20]
0x140012481  xor     r15d, r15d
0x140012484  test    rcx, rcx
0x140012487  jz      loc_140012867
0x14001248d  test    r13, r13
0x140012490  jz      loc_140012867
0x140012496  call    cs:__imp_SysAllocString
0x14001249c  mov     rsi, rax
0x14001249f  mov     [rsp+1D0h+var_160], rax
0x1400124a4  test    rax, rax
0x1400124a7  jz      loc_1400128AB
0x1400124ad  mov     ebx, r15d
0x1400124b0  mov     [rbp+0D0h+hKey], rbx
0x1400124b4  mov     [rbp+0D0h+var_118], r15d
0x1400124b8  lea     rax, [rbp+0D0h+var_118]
0x1400124bc  mov     [rsp+1D0h+lpcSubKeys], rax; unsigned int *
0x1400124c1  xor     r9d, r9d; HINSTANCE *
0x1400124c4  xor     r8d, r8d; bool
0x1400124c7  lea     rdx, CLSID_VSShellMenusPackage; rguid
0x1400124ce  mov     rcx, r12; unsigned __int16 *
0x1400124d1  call    ?util_GetPackageResourcesInstance@@YAHPEBGAEBU_GUID@@_NPEAPEAUHINSTANCE__@@PEAK@Z; util_GetPackageResourcesInstance(ushort const *,_GUID const &,bool,HINSTANCE__ * *,ulong *)
0x1400124d6  mov     r9d, [rbp+0D0h+var_118]
0x1400124da  test    r9d, r9d
0x1400124dd  jnz     short loc_1400124EA
0x1400124df  mov     r13d, 80070057h
0x1400124e5  jmp     loc_14001284A
0x1400124ea  lea     r8, aSetupMigration; "\\Setup\\Migration\\%u"
0x1400124f1  mov     edx, 32h ; '2'; unsigned __int64
0x1400124f6  lea     rcx, [rbp+0D0h+Buffer]; Buffer
0x1400124fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400124ff  lea     rax, [rbp+0D0h+Buffer]
0x140012503  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012507  inc     r8; int
0x14001250a  cmp     [rax+r8*2], r15w
0x14001250f  jnz     short loc_140012507
0x140012511  lea     rdx, [rbp+0D0h+Buffer]; unsigned __int16 *
0x140012515  lea     rcx, [rsp+1D0h+var_160]; this
0x14001251a  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14001251f  test    eax, eax
0x140012521  js      loc_1400128B9
0x140012527  mov     rsi, [rsp+1D0h+var_160]
0x14001252c  test    rsi, rsi
0x14001252f  jnz     short loc_14001253C
0x140012531  mov     r13d, 8007000Eh
0x140012537  jmp     loc_14001284A
0x14001253c  mov     [r13+0], r15d
0x140012540  mov     r9d, 20019h; unsigned int
0x140012546  mov     r8, rsi; unsigned __int16 *
0x140012549  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140012550  lea     rcx, [rbp+0D0h+hKey]; this
0x140012554  call    ?Open@CVsRegKeyW@@QEAAJPEAUHKEY__@@PEBGK@Z; CVsRegKeyW::Open(HKEY__ *,ushort const *,ulong)
0x140012559  test    eax, eax
0x14001255b  js      loc_140012843
0x140012561  mov     r14, r15
0x140012564  mov     [rsp+1D0h+var_158], r15
0x140012569  mov     rdi, r15
0x14001256c  mov     [rsp+1D0h+bstrLeft], r15
0x140012571  mov     eax, r15d
0x140012574  mov     [rbp+0D0h+cValues], eax
0x140012577  mov     rbx, [rbp+0D0h+hKey]
0x14001257b  test    rbx, rbx
0x14001257e  jz      short loc_1400125C0
0x140012580  mov     [rsp+1D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x140012585  mov     [rsp+1D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14001258a  mov     [rsp+1D0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x14001258f  mov     [rsp+1D0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x140012594  lea     rax, [rbp+0D0h+cValues]
0x140012598  mov     [rsp+1D0h+lpcValues], rax; lpCurrentDirectory
0x14001259d  mov     [rsp+1D0h+lpcbMaxClassLen], r15; lpEnvironment
0x1400125a2  mov     [rsp+1D0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1400125a7  mov     [rsp+1D0h+lpcSubKeys], r15; lpcSubKeys
0x1400125ac  xor     r9d, r9d; lpReserved
0x1400125af  xor     r8d, r8d; lpcchClass
0x1400125b2  xor     edx, edx; lpClass
0x1400125b4  mov     rcx, rbx; hKey
0x1400125b7  call    cs:__imp_RegQueryInfoKeyW
0x1400125bd  mov     eax, [rbp+0D0h+cValues]
0x1400125c0  test    eax, eax
0x1400125c2  jz      loc_1400126B3
0x1400125c8  and     [rsp+1D0h+pbstr], 0
0x1400125ce  lea     r8, [rsp+1D0h+pbstr]; unsigned __int16 **
0x1400125d3  mov     edx, r15d; unsigned int
0x1400125d6  lea     rcx, [rbp+0D0h+hKey]; this
0x1400125da  call    ?EnumValue@CVsRegKeyW@@QEBAJKPEAPEAGPEAK@Z; CVsRegKeyW::EnumValue(ulong,ushort * *,ulong *)
0x1400125df  mov     rbx, [rsp+1D0h+pbstr]
0x1400125e4  mov     rcx, rbx; pbstr
0x1400125e7  call    cs:__imp_SysStringLen
0x1400125ed  test    eax, eax
0x1400125ef  jz      loc_140012699
0x1400125f5  mov     r8d, 1; int
0x1400125fb  lea     rdx, asc_140080978; "\t"
0x140012602  lea     rcx, [rsp+1D0h+bstrLeft]; this
0x140012607  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14001260c  test    eax, eax
0x14001260e  js      loc_14001289C
0x140012614  mov     rcx, rbx; pbstr
0x140012617  call    cs:__imp_SysStringLen
0x14001261d  test    eax, eax
0x14001261f  jz      short loc_14001265A
0x140012621  and     [rbp+0D0h+pbstrResult], 0
0x140012626  lea     r8, [rbp+0D0h+pbstrResult]; pbstrResult
0x14001262a  mov     rdx, rbx; bstrRight
0x14001262d  mov     rcx, [rsp+1D0h+bstrLeft]; bstrLeft
0x140012632  call    cs:__imp_VarBstrCat
0x140012638  mov     edi, eax
0x14001263a  test    eax, eax
0x14001263c  js      short loc_140012652
0x14001263e  mov     rcx, [rsp+1D0h+bstrLeft]; bstrString
0x140012643  call    cs:__imp_SysFreeString
0x140012649  mov     rcx, [rbp+0D0h+pbstrResult]
0x14001264d  mov     [rsp+1D0h+bstrLeft], rcx
0x140012652  test    edi, edi
0x140012654  js      loc_1400128C9
0x14001265a  mov     r8d, 2; int
0x140012660  lea     rdx, asc_1400805C0; "\r\n"
0x140012667  lea     rcx, [rsp+1D0h+bstrLeft]; this
0x14001266c  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x140012671  test    eax, eax
0x140012673  js      loc_1400128D4
0x140012679  test    r14, r14
0x14001267c  jnz     short loc_140012694
0x14001267e  lea     r8, [rsp+1D0h+var_158]; unsigned __int16 **
0x140012683  mov     rdx, rbx; unsigned __int16 *
0x140012686  lea     rcx, [rbp+0D0h+hKey]; this
0x14001268a  call    ?QueryValue@CVsRegKeyW@@QEBAJPEBGPEAPEAG@Z; CVsRegKeyW::QueryValue(ushort const *,ushort * *)
0x14001268f  mov     r14, [rsp+1D0h+var_158]
0x140012694  mov     rdi, [rsp+1D0h+bstrLeft]
0x140012699  mov     rcx, rbx; bstrString
0x14001269c  call    cs:__imp_SysFreeString
0x1400126a2  inc     r15d
0x1400126a5  cmp     r15d, [rbp+0D0h+cValues]
0x1400126a9  jb      loc_1400125C8
0x1400126af  mov     rbx, [rbp+0D0h+hKey]
0x1400126b3  mov     rcx, rdi; pbstr
0x1400126b6  call    cs:__imp_SysStringLen
0x1400126bc  xor     r15d, r15d
0x1400126bf  test    eax, eax
0x1400126c1  jz      loc_14001282F
0x1400126c7  mov     rcx, r14; pbstr
0x1400126ca  call    cs:__imp_SysStringLen
0x1400126d0  test    eax, eax
0x1400126d2  jz      loc_14001282F
0x1400126d8  mov     dword ptr [r13+0], 1
0x1400126e0  mov     [rsp+1D0h+lpcSubKeys], r15; unsigned int *
0x1400126e5  lea     r9, [rbp+0D0h+pbstrResult]; HINSTANCE *
0x1400126e9  xor     r8d, r8d; bool
0x1400126ec  lea     rdx, CLSID_VSShellMenusPackage; rguid
0x1400126f3  mov     rcx, r12; unsigned __int16 *
0x1400126f6  call    ?util_GetPackageResourcesInstance@@YAHPEBGAEBU_GUID@@_NPEAPEAUHINSTANCE__@@PEAK@Z; util_GetPackageResourcesInstance(ushort const *,_GUID const &,bool,HINSTANCE__ * *,ulong *)
0x1400126fb  test    eax, eax
0x1400126fd  jnz     short loc_14001270A
0x1400126ff  mov     r13d, 80070057h
0x140012705  jmp     loc_1400127F1
0x14001270a  mov     [rbp+0D0h+lpText], r15
0x14001270e  mov     [rsp+1D0h+pbstr], r15
0x140012713  mov     r8d, 0BB8h; unsigned int
0x140012719  mov     rdx, [rbp+0D0h+pbstrResult]; HINSTANCE
0x14001271d  lea     rcx, [rsp+1D0h+pbstr]; this
0x140012722  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x140012727  lea     r9, [rbp+0D0h+lpText]; unsigned __int16 **
0x14001272b  mov     r8, rdi; unsigned __int16 *
0x14001272e  mov     edx, 1A36h; unsigned int
0x140012733  mov     rcx, [rbp+0D0h+pbstrResult]; HINSTANCE
0x140012737  call    ?util_FormatString@@YAHPEAUHINSTANCE__@@IPEBGPEAPEAG@Z; util_FormatString(HINSTANCE__ *,uint,ushort const *,ushort * *)
0x14001273c  mov     r12, [rsp+1D0h+pbstr]
0x140012741  mov     r15, [rbp+0D0h+lpText]
0x140012745  test    r15, r15
0x140012748  jnz     short loc_140012755
0x14001274a  mov     r13d, 8007000Eh
0x140012750  jmp     loc_1400127DE
0x140012755  mov     r9d, 11h; uType
0x14001275b  mov     r8, r12; lpCaption
0x14001275e  mov     rdx, r15; lpText
0x140012761  xor     ecx, ecx; hWnd
0x140012763  call    cs:__imp_MessageBoxW
0x140012769  cmp     eax, 1
0x14001276c  jnz     loc_14001281A
0x140012772  xor     edx, edx; Val
0x140012774  lea     r8d, [rax+63h]; Size
0x140012778  lea     rcx, [rbp+0D0h+StartupInfo+4]; void *
0x14001277c  call    memset_0
0x140012781  xorps   xmm0, xmm0
0x140012784  xor     eax, eax
0x140012786  movups  xmmword ptr [rbp+0D0h+ProcessInformation.hProcess], xmm0
0x14001278a  mov     qword ptr [rbp+0D0h+ProcessInformation.dwProcessId], rax
0x14001278e  mov     [rbp+0D0h+StartupInfo.cb], 68h ; 'h'
0x140012795  lea     rax, [rbp+0D0h+ProcessInformation]
0x140012799  mov     [rsp+1D0h+lpcbMaxValueLen], rax; lpProcessInformation
0x14001279e  lea     rax, [rbp+0D0h+StartupInfo]
0x1400127a2  mov     [rsp+1D0h+lpcbMaxValueNameLen], rax; lpStartupInfo
0x1400127a7  and     [rsp+1D0h+lpcValues], 0
0x1400127ad  and     [rsp+1D0h+lpcbMaxClassLen], 0
0x1400127b3  mov     dword ptr [rsp+1D0h+lpcbMaxSubKeyLen], 8; dwCreationFlags
0x1400127bb  mov     dword ptr [rsp+1D0h+lpcSubKeys], 1; bInheritHandles
0x1400127c3  xor     r9d, r9d; lpThreadAttributes
0x1400127c6  xor     r8d, r8d; lpProcessAttributes
0x1400127c9  xor     edx, edx; lpCommandLine
0x1400127cb  mov     rcx, r14; lpApplicationName
0x1400127ce  call    cs:__imp_CreateProcessW
0x1400127d4  test    eax, eax
0x1400127d6  jnz     short loc_140012805
0x1400127d8  mov     r13d, 80070057h
0x1400127de  mov     rcx, r12; bstrString
0x1400127e1  call    cs:__imp_SysFreeString
0x1400127e7  mov     rcx, r15; bstrString
0x1400127ea  call    cs:__imp_SysFreeString
0x1400127f0  nop
0x1400127f1  mov     rcx, rdi; bstrString
0x1400127f4  call    cs:__imp_SysFreeString
0x1400127fa  mov     rcx, r14; bstrString
0x1400127fd  call    cs:__imp_SysFreeString
0x140012803  jmp     short loc_14001284A
0x140012805  mov     rcx, [rbp+0D0h+ProcessInformation.hThread]; hObject
0x140012809  call    cs:__imp_CloseHandle
0x14001280f  mov     rcx, [rbp+0D0h+ProcessInformation.hProcess]; hObject
0x140012813  call    cs:__imp_CloseHandle
0x140012819  nop
0x14001281a  mov     rcx, r12; bstrString
0x14001281d  call    cs:__imp_SysFreeString
0x140012823  mov     rcx, r15; bstrString
0x140012826  call    cs:__imp_SysFreeString
0x14001282c  xor     r15d, r15d
0x14001282f  mov     rcx, rdi; bstrString
0x140012832  call    cs:__imp_SysFreeString
0x140012838  mov     rcx, r14; bstrString
0x14001283b  call    cs:__imp_SysFreeString
0x140012841  jmp     short loc_140012847
0x140012843  mov     rbx, [rbp+0D0h+hKey]
0x140012847  mov     r13d, r15d
0x14001284a  test    rbx, rbx
0x14001284d  jz      short loc_140012859
0x14001284f  mov     rcx, rbx; hKey
0x140012852  call    cs:__imp_RegCloseKey
0x140012858  nop
0x140012859  mov     rcx, rsi; bstrString
0x14001285c  call    cs:__imp_SysFreeString
0x140012862  mov     eax, r13d
0x140012865  jmp     short loc_14001286C
0x140012867  mov     eax, 80070057h
0x14001286c  mov     rcx, [rbp+0D0h+var_30]
0x140012873  xor     rcx, rsp; StackCookie
0x140012876  call    __security_check_cookie
0x14001287b  lea     r11, [rsp+1D0h+var_20]
0x140012883  mov     rbx, [r11+38h]
0x140012887  mov     rsi, [r11+40h]
0x14001288b  mov     rdi, [r11+48h]
0x14001288f  mov     rsp, r11
0x140012892  pop     r15
0x140012894  pop     r14
0x140012896  pop     r13
0x140012898  pop     r12
0x14001289a  pop     rbp
0x14001289b  retn
0x14001289c  lfence
0x14001289f  mov     ecx, eax; int
0x1400128a1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400128a7  jmp     short loc_1400128AA
0x1400128aa  nop
0x1400128ab  mov     ecx, 8007000Eh; int
0x1400128b0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400128b6  jmp     short $+2
0x1400128b8  nop
0x1400128b9  lfence
0x1400128bc  mov     ecx, eax; int
0x1400128be  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400128c4  jmp     short loc_1400128C8
0x1400128c8  nop
0x1400128c9  lfence
0x1400128cc  mov     ecx, edi; int
0x1400128ce  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400128d4  lfence
0x1400128d7  mov     ecx, eax; int
0x1400128d9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
