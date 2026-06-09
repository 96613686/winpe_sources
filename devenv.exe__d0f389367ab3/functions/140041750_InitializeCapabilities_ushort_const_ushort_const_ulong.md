# InitializeCapabilities(ushort const *,ushort const *,ulong)

- ea: `0x140041750`
- end: `0x140041d8c`
- name: `?InitializeCapabilities@@YAJPEBG0K@Z`
- size: `1596`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002e30`
- `0x140003160`
- `0x140007740`
- `0x140009b10`
- `0x14001e390`
- `0x140027c20`
- `0x140033ab0`
- `0x140041648`
- `0x140041750`
- `0x140041d8c`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x140041a63`
- `ADVAPI32!RegDeleteKeyW` at `0x140041a63`
- `ADVAPI32!RegCloseKey` at `0x140041c5a`
- `ADVAPI32!RegCloseKey` at `0x140041d1e`
- `ADVAPI32!RegCloseKey` at `0x140041d2d`
- `ADVAPI32!RegCloseKey` at `0x140041d3c`
- `ADVAPI32!RegCloseKey` at `0x140041c5a`
- `ADVAPI32!RegCloseKey` at `0x140041d1e`
- `ADVAPI32!RegCloseKey` at `0x140041d2d`
- `ADVAPI32!RegCloseKey` at `0x140041d3c`
- `ADVAPI32!RegCreateKeyExW` at `0x14004189c`
- `ADVAPI32!RegCreateKeyExW` at `0x140041aa4`
- `ADVAPI32!RegCreateKeyExW` at `0x14004189c`
- `ADVAPI32!RegCreateKeyExW` at `0x140041aa4`
- `ADVAPI32!RegOpenKeyExW` at `0x14004184c`
- `ADVAPI32!RegOpenKeyExW` at `0x1400418f2`
- `ADVAPI32!RegOpenKeyExW` at `0x140041b91`
- `ADVAPI32!RegOpenKeyExW` at `0x14004184c`
- `ADVAPI32!RegOpenKeyExW` at `0x1400418f2`
- `ADVAPI32!RegOpenKeyExW` at `0x140041b91`
- `ADVAPI32!RegSetValueExW` at `0x1400419e3`
- `ADVAPI32!RegSetValueExW` at `0x140041c1a`
- `ADVAPI32!RegSetValueExW` at `0x1400419e3`
- `ADVAPI32!RegSetValueExW` at `0x140041c1a`
- `ADVAPI32!RegEnumKeyExW` at `0x140041b37`
- `ADVAPI32!RegEnumKeyExW` at `0x140041b37`
- `KERNEL32!GetModuleHandleW` at `0x140041a0f`
- `KERNEL32!GetModuleHandleW` at `0x140041a0f`
- `KERNEL32!GetProcAddress` at `0x140041a24`
- `KERNEL32!GetProcAddress` at `0x140041a24`

## string_xrefs

- `0x140041a1a`: `RegDeleteKeyExW`
- `0x140041a08`: `Advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall InitializeCapabilities(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int a3)
{
  HKEY v6; // r14
  HKEY v7; // r13
  HKEY v8; // r15
  LSTATUS v9; // eax
  signed int ExeLocation; // esi
  LSTATUS v11; // eax
  struct ATL::IAtlStringMgr *Instance; // rax
  BYTE *v13; // rbx
  struct ATL::IAtlStringMgr *v14; // rax
  HKEY v15; // rdi
  DWORD v16; // r12d
  LSTATUS v17; // eax
  __int64 v18; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  LSTATUS v21; // eax
  __int64 v22; // rdx
  WCHAR *v23; // r8
  __int64 v24; // rdx
  unsigned __int16 *v25; // r8
  bool v26; // zf
  HKEY v27; // rax
  __int64 v28; // rcx
  LPWSTR v29; // rdx
  int v30; // eax
  LPCWSTR v31; // rdx
  LPCWSTR v32; // rdx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v35; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR lpName; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR v39; // [rsp+78h] [rbp-88h] BYREF
  BYTE *lpData; // [rsp+80h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-78h] BYREF
  __int128 v42; // [rsp+90h] [rbp-70h]
  __int64 v43; // [rsp+A0h] [rbp-60h]
  HKEY v44[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-48h]
  __int128 v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+D0h] [rbp-30h]
  __int128 v48; // [rsp+D8h] [rbp-28h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  DWORD cchName; // [rsp+F0h] [rbp-10h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+F8h] [rbp-8h] BYREF

  if ( !a1 || !a2 )
    return 2147500035LL;
  v6 = 0;
  v42 = 0u;
  v43 = 0;
  v7 = 0;
  v48 = 0u;
  v49 = 0;
  v8 = 0;
  v46 = 0u;
  v47 = 0;
  lpSubKey = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpSubKey,
    a1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpSubKey,
    L"\\%s",
    L"Capabilities");
  v39 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v39,
    a1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v39,
    L"\\%s",
    L"ShellFileAssociations");
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2000Eu, &hKey) )
  {
    v6 = hKey;
    *(_QWORD *)&v42 = hKey;
    DWORD2(v42) = 0;
    goto LABEL_10;
  }
  hKey = 0;
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
  if ( !v9 )
  {
    v6 = hKey;
    *(_QWORD *)&v42 = hKey;
    DWORD2(v42) = 0;
  }
  ExeLocation = (unsigned __int16)(v9 != 0 ? v9 : 0) | 0x80070000;
  if ( (v9 != 0 ? v9 : 0) <= 0 )
    ExeLocation = v9 != 0 ? v9 : 0;
  if ( ExeLocation >= 0 )
  {
LABEL_10:
    hKey = 0;
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v39, 0, 0x20019u, &hKey);
    if ( !v11 )
    {
      v8 = hKey;
      *(_QWORD *)&v46 = hKey;
      DWORD2(v46) = 0;
    }
    ExeLocation = (unsigned __int16)(v11 != 0 ? v11 : 0) | 0x80070000;
    if ( (v11 != 0 ? v11 : 0) <= 0 )
      ExeLocation = v11 != 0 ? v11 : 0;
    if ( ExeLocation >= 0 )
    {
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      v13 = (BYTE *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
      lpData = v13;
      v14 = ATL::CAtlStringMgr::GetInstance();
      if ( !v14 )
        ATL::AtlThrowImpl(-2147467259);
      hKey = (HKEY)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v14 + 24LL))(v14) + 24);
      ExeLocation = anonymous_namespace_::GetExeLocation(&hKey);
      if ( ExeLocation < 0 )
      {
        v15 = hKey;
        goto LABEL_60;
      }
      ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
        &hKey,
        a2);
      v15 = hKey;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &lpData,
        L"@%s,-%d",
        hKey,
        a3);
      v13 = lpData;
      v16 = 0;
      if ( lpData )
      {
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)&lpData[2 * v18] );
        v17 = RegSetValueExW(v6, L"ApplicationDescription", 0, 1u, lpData, 2 * v18 + 2);
      }
      else
      {
        v17 = 13;
      }
      ExeLocation = (unsigned __int16)v17 | 0x80070000;
      if ( v17 <= 0 )
        ExeLocation = v17;
      if ( ExeLocation >= 0 )
      {
        if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
        {
          ProcAddress = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
        }
        else
        {
          ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
          if ( ModuleHandleW )
          {
            ProcAddress = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
            `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)ProcAddress;
          }
          else
          {
            ProcAddress = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
          }
          `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
        }
        if ( ProcAddress )
          ((void (__fastcall *)(HKEY, const WCHAR *, _QWORD, _QWORD))ProcAddress)(v6, L"FileAssociations", 0, 0);
        else
          RegDeleteKeyW(v6, L"FileAssociations");
        v35 = 0;
        v21 = RegCreateKeyExW(v6, L"FileAssociations", 0, 0, 0, 0x20006u, 0, &v35, &dwDisposition);
        if ( !v21 )
        {
          v7 = v35;
          *(_QWORD *)&v48 = v35;
          DWORD2(v48) = 0;
        }
        v22 = v21 & (unsigned int)-(v21 != 0);
        ExeLocation = (unsigned __int16)(v21 != 0 ? v21 : 0) | 0x80070000;
        if ( (int)v22 <= 0 )
          ExeLocation = v21 != 0 ? v21 : 0;
        if ( ExeLocation >= 0 )
        {
          cchName = 260;
          lpName = 0;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &lpName,
            v22,
            260);
          while ( 1 )
          {
            v23 = lpName;
            if ( *((int *)lpName - 2) > 1 )
            {
              ATL::CSimpleStringT<unsigned short,0>::Fork(&lpName, *((unsigned int *)lpName - 4));
              v23 = lpName;
            }
            if ( RegEnumKeyExW(v8, v16, v23, &cchName, 0, 0, 0, &ftLastWriteTime) )
            {
              v29 = lpName - 12;
              v30 = _InterlockedExchangeAdd((volatile signed __int32 *)lpName - 2, 0xFFFFFFFF);
              v15 = hKey;
              if ( v30 <= 1 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
              }
              goto LABEL_60;
            }
            dwDisposition = 260;
            v44[0] = 0;
            v44[1] = 0;
            v45 = 0;
            v35 = 0;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v35,
              v24,
              260);
            phkResult = 0;
            if ( RegOpenKeyExW(v8, lpName, 0, 0x20019u, &phkResult) )
              goto LABEL_52;
            v44[0] = phkResult;
            LODWORD(v44[1]) = 0;
            v25 = (unsigned __int16 *)v35;
            if ( *((int *)v35 - 2) > 1 )
            {
              ATL::CSimpleStringT<unsigned short,0>::Fork(&v35, *((unsigned int *)v35 - 4));
              v25 = (unsigned __int16 *)v35;
            }
            v26 = (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v44, &WindowName, v25, &dwDisposition) == 0;
            v27 = v35;
            if ( v26 )
            {
              if ( v35 )
                break;
            }
LABEL_53:
            cchName = 260;
            ++v16;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 - 3) + 8LL))(*((_QWORD *)v27 - 3));
            }
            if ( v44[0] )
              RegCloseKey(v44[0]);
          }
          v28 = -1;
          do
            ++v28;
          while ( *((_WORD *)v35 + v28) );
          RegSetValueExW(v7, lpName, 0, 1u, (const BYTE *)v35, 2 * v28 + 2);
LABEL_52:
          v27 = v35;
          goto LABEL_53;
        }
      }
LABEL_60:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3) + 8LL))(*((_QWORD *)v13 - 3));
      }
    }
  }
  v31 = v39 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v39 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 8LL))(*(_QWORD *)v31);
  }
  v32 = lpSubKey - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpSubKey - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v32 + 8LL))(*(_QWORD *)v32);
  }
  if ( v8 )
    RegCloseKey(v8);
  if ( v7 )
    RegCloseKey(v7);
  if ( v6 )
    RegCloseKey(v6);
  return (unsigned int)ExeLocation;
}

```

## disassembly

```asm
0x140041750  mov     [rsp-8+arg_18], rbx
0x140041755  push    rbp
0x140041756  push    rsi
0x140041757  push    rdi
0x140041758  push    r12
0x14004175a  push    r13
0x14004175c  push    r14
0x14004175e  push    r15
0x140041760  lea     rbp, [rsp-10h]
0x140041765  sub     rsp, 110h
0x14004176c  mov     rax, cs:__security_cookie
0x140041773  xor     rax, rsp
0x140041776  mov     [rbp+40h+var_40], rax
0x14004177a  mov     r12d, r8d
0x14004177d  mov     rdi, rdx
0x140041780  mov     rbx, rcx
0x140041783  xor     esi, esi
0x140041785  test    rcx, rcx
0x140041788  jz      loc_140041D46
0x14004178e  test    rdx, rdx
0x140041791  jz      loc_140041D46
0x140041797  xorps   xmm0, xmm0
0x14004179a  movups  [rbp+40h+var_B0], xmm0
0x14004179e  mov     r14d, esi
0x1400417a1  mov     qword ptr [rbp+40h+var_B0], rsi
0x1400417a5  mov     dword ptr [rbp+40h+var_B0+8], esi
0x1400417a8  mov     [rbp+40h+var_A0], rsi
0x1400417ac  movups  [rbp+40h+var_68], xmm0
0x1400417b0  mov     r13d, esi
0x1400417b3  mov     qword ptr [rbp+40h+var_68], rsi
0x1400417b7  mov     dword ptr [rbp+40h+var_68+8], esi
0x1400417ba  mov     [rbp+40h+var_58], rsi
0x1400417be  movups  [rbp+40h+var_80], xmm0
0x1400417c2  mov     r15d, esi
0x1400417c5  mov     qword ptr [rbp+40h+var_80], rsi
0x1400417c9  mov     dword ptr [rbp+40h+var_80+8], esi
0x1400417cc  mov     [rbp+40h+var_70], rsi
0x1400417d0  mov     [rsp+140h+lpSubKey], rsi
0x1400417d5  mov     rdx, rcx
0x1400417d8  lea     rcx, [rsp+140h+lpSubKey]
0x1400417dd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400417e2  lea     r8, aCapabilities; "Capabilities"
0x1400417e9  lea     rdx, aS_4; "\\%s"
0x1400417f0  lea     rcx, [rsp+140h+lpSubKey]
0x1400417f5  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1400417fa  mov     [rsp+140h+var_C8], rsi
0x1400417ff  mov     rdx, rbx
0x140041802  lea     rcx, [rsp+140h+var_C8]
0x140041807  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004180c  nop
0x14004180d  lea     r8, aShellfileassoc; "ShellFileAssociations"
0x140041814  lea     rdx, aS_4; "\\%s"
0x14004181b  lea     rcx, [rsp+140h+var_C8]
0x140041820  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x140041825  mov     [rsp+140h+hKey], rsi
0x14004182a  lea     rax, [rsp+140h+hKey]
0x14004182f  mov     [rsp+140h+phkResult], rax; phkResult
0x140041834  mov     r9d, 2000Eh; samDesired
0x14004183a  xor     r8d, r8d; ulOptions
0x14004183d  mov     rdx, [rsp+140h+lpSubKey]; lpSubKey
0x140041842  mov     rbx, 0FFFFFFFF80000002h
0x140041849  mov     rcx, rbx; hKey
0x14004184c  call    cs:__imp_RegOpenKeyExW
0x140041852  test    eax, eax
0x140041854  jnz     short loc_140041864
0x140041856  mov     r14, [rsp+140h+hKey]
0x14004185b  mov     qword ptr [rbp+40h+var_B0], r14
0x14004185f  mov     dword ptr [rbp+40h+var_B0+8], esi
0x140041862  jmp     short loc_1400418D2
0x140041864  mov     [rsp+140h+hKey], rsi
0x140041869  lea     rax, [rsp+140h+dwDisposition]
0x14004186e  mov     [rsp+140h+lpdwDisposition], rax; lpdwDisposition
0x140041873  lea     rax, [rsp+140h+hKey]
0x140041878  mov     [rsp+140h+var_108], rax; phkResult
0x14004187d  mov     [rsp+140h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x140041882  mov     [rsp+140h+samDesired], 20006h; samDesired
0x14004188a  mov     dword ptr [rsp+140h+phkResult], esi; dwOptions
0x14004188e  xor     r9d, r9d; lpClass
0x140041891  xor     r8d, r8d; Reserved
0x140041894  mov     rdx, [rsp+140h+lpSubKey]; lpSubKey
0x140041899  mov     rcx, rbx; hKey
0x14004189c  call    cs:__imp_RegCreateKeyExW
0x1400418a2  test    eax, eax
0x1400418a4  jnz     short loc_1400418B2
0x1400418a6  mov     r14, [rsp+140h+hKey]
0x1400418ab  mov     qword ptr [rbp+40h+var_B0], r14
0x1400418af  mov     dword ptr [rbp+40h+var_B0+8], esi
0x1400418b2  mov     ecx, eax
0x1400418b4  neg     ecx
0x1400418b6  sbb     edx, edx
0x1400418b8  and     edx, eax
0x1400418ba  movzx   esi, dx
0x1400418bd  or      esi, 80070000h
0x1400418c3  test    edx, edx
0x1400418c5  cmovle  esi, edx
0x1400418c8  test    esi, esi
0x1400418ca  js      loc_140041CD0
0x1400418d0  xor     esi, esi
0x1400418d2  mov     [rsp+140h+hKey], rsi
0x1400418d7  lea     rax, [rsp+140h+hKey]
0x1400418dc  mov     [rsp+140h+phkResult], rax; phkResult
0x1400418e1  mov     r9d, 20019h; samDesired
0x1400418e7  xor     r8d, r8d; ulOptions
0x1400418ea  mov     rdx, [rsp+140h+var_C8]; lpSubKey
0x1400418ef  mov     rcx, rbx; hKey
0x1400418f2  call    cs:__imp_RegOpenKeyExW
0x1400418f8  test    eax, eax
0x1400418fa  jnz     short loc_140041908
0x1400418fc  mov     r15, [rsp+140h+hKey]
0x140041901  mov     qword ptr [rbp+40h+var_80], r15
0x140041905  mov     dword ptr [rbp+40h+var_80+8], esi
0x140041908  mov     ecx, eax
0x14004190a  neg     ecx
0x14004190c  sbb     edx, edx
0x14004190e  and     edx, eax
0x140041910  movzx   esi, dx
0x140041913  or      esi, 80070000h
0x140041919  test    edx, edx
0x14004191b  cmovle  esi, edx
0x14004191e  test    esi, esi
0x140041920  js      loc_140041CD0
0x140041926  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004192b  mov     rcx, rax
0x14004192e  test    rax, rax
0x140041931  jz      loc_140041D81
0x140041937  mov     rax, [rax]
0x14004193a  call    qword ptr [rax+18h]
0x14004193d  lea     rbx, [rax+18h]
0x140041941  mov     [rbp+40h+lpData], rbx
0x140041945  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004194a  mov     rcx, rax
0x14004194d  test    rax, rax
0x140041950  jz      loc_140041D72
0x140041956  mov     rax, [rax]
0x140041959  call    qword ptr [rax+18h]
0x14004195c  add     rax, 18h
0x140041960  mov     [rsp+140h+hKey], rax
0x140041965  lea     rcx, [rsp+140h+hKey]
0x14004196a  call    _anonymous_namespace___GetExeLocation
0x14004196f  mov     esi, eax
0x140041971  test    eax, eax
0x140041973  js      loc_140041C8E
0x140041979  mov     rdx, rdi
0x14004197c  lea     rcx, [rsp+140h+hKey]
0x140041981  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x140041986  mov     r9d, r12d
0x140041989  mov     rdi, [rsp+140h+hKey]
0x14004198e  mov     r8, rdi
0x140041991  lea     rdx, aSD_0; "@%s,-%d"
0x140041998  lea     rcx, [rbp+40h+lpData]
0x14004199c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1400419a1  mov     rbx, [rbp+40h+lpData]
0x1400419a5  xor     r12d, r12d
0x1400419a8  test    rbx, rbx
0x1400419ab  jnz     short loc_1400419B2
0x1400419ad  lea     eax, [rbx+0Dh]
0x1400419b0  jmp     short loc_1400419E9
0x1400419b2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400419b6  inc     rax
0x1400419b9  cmp     [rbx+rax*2], r12w
0x1400419be  jnz     short loc_1400419B6
0x1400419c0  lea     eax, ds:2[rax*2]
0x1400419c7  mov     [rsp+140h+samDesired], eax; cbData
0x1400419cb  mov     [rsp+140h+phkResult], rbx; lpData
0x1400419d0  mov     r9d, 1; dwType
0x1400419d6  xor     r8d, r8d; Reserved
0x1400419d9  lea     rdx, aApplicationdes; "ApplicationDescription"
0x1400419e0  mov     rcx, r14; hKey
0x1400419e3  call    cs:__imp_RegSetValueExW
0x1400419e9  movzx   esi, ax
0x1400419ec  or      esi, 80070000h
0x1400419f2  test    eax, eax
0x1400419f4  cmovle  esi, eax
0x1400419f7  test    esi, esi
0x1400419f9  js      loc_140041C93
0x1400419ff  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, r12b; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x140041a06  jnz     short loc_140041A43
0x140041a08  lea     rcx, aAdvapi32Dll_1; "Advapi32.dll"
0x140041a0f  call    cs:__imp_GetModuleHandleW
0x140041a15  test    rax, rax
0x140041a18  jz      short loc_140041A33
0x140041a1a  lea     rdx, aRegdeletekeyex_0; "RegDeleteKeyExW"
0x140041a21  mov     rcx, rax; hModule
0x140041a24  call    cs:__imp_GetProcAddress
0x140041a2a  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x140041a31  jmp     short loc_140041A3A
0x140041a33  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x140041a3a  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, 1; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x140041a41  jmp     short loc_140041A4A
0x140041a43  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x140041a4a  lea     rdx, aFileassociatio; "FileAssociations"
0x140041a51  mov     rcx, r14; hKey
0x140041a54  test    rax, rax
0x140041a57  jz      short loc_140041A63
0x140041a59  xor     r9d, r9d
0x140041a5c  xor     r8d, r8d
0x140041a5f  call    rax
0x140041a61  jmp     short loc_140041A69
0x140041a63  call    cs:__imp_RegDeleteKeyW
0x140041a69  mov     [rsp+140h+var_E8], r12
0x140041a6e  lea     rax, [rsp+140h+dwDisposition]
0x140041a73  mov     [rsp+140h+lpdwDisposition], rax; lpdwDisposition
0x140041a78  lea     rax, [rsp+140h+var_E8]
0x140041a7d  mov     [rsp+140h+var_108], rax; phkResult
0x140041a82  mov     [rsp+140h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140041a87  mov     [rsp+140h+samDesired], 20006h; samDesired
0x140041a8f  mov     dword ptr [rsp+140h+phkResult], r12d; dwOptions
0x140041a94  xor     r9d, r9d; lpClass
0x140041a97  xor     r8d, r8d; Reserved
0x140041a9a  lea     rdx, aFileassociatio; "FileAssociations"
0x140041aa1  mov     rcx, r14; hKey
0x140041aa4  call    cs:__imp_RegCreateKeyExW
0x140041aaa  test    eax, eax
0x140041aac  jnz     short loc_140041ABB
0x140041aae  mov     r13, [rsp+140h+var_E8]
0x140041ab3  mov     qword ptr [rbp+40h+var_68], r13
0x140041ab7  mov     dword ptr [rbp+40h+var_68+8], r12d
0x140041abb  mov     ecx, eax
0x140041abd  neg     ecx
0x140041abf  sbb     edx, edx
0x140041ac1  and     edx, eax
0x140041ac3  movzx   esi, dx
0x140041ac6  or      esi, 80070000h
0x140041acc  test    edx, edx
0x140041ace  cmovle  esi, edx
0x140041ad1  test    esi, esi
0x140041ad3  js      loc_140041C93
0x140041ad9  mov     eax, 104h
0x140041ade  mov     [rbp+40h+cchName], eax
0x140041ae1  xor     edi, edi
0x140041ae3  mov     [rsp+140h+lpName], rdi
0x140041ae8  mov     r8d, eax
0x140041aeb  lea     rcx, [rsp+140h+lpName]
0x140041af0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@GH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort,int)
0x140041af5  nop
0x140041af6  mov     r8, [rsp+140h+lpName]
0x140041afb  cmp     dword ptr [r8-8], 1
0x140041b00  jle     short loc_140041B15
0x140041b02  mov     edx, [r8-10h]
0x140041b06  lea     rcx, [rsp+140h+lpName]
0x140041b0b  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x140041b10  mov     r8, [rsp+140h+lpName]; lpName
0x140041b15  lea     rax, [rbp+40h+ftLastWriteTime]
0x140041b19  mov     [rsp+140h+var_108], rax; lpftLastWriteTime
0x140041b1e  mov     [rsp+140h+lpSecurityAttributes], rdi; lpcchClass
0x140041b23  mov     qword ptr [rsp+140h+samDesired], rdi; lpClass
0x140041b28  mov     [rsp+140h+phkResult], rdi; lpReserved
0x140041b2d  lea     r9, [rbp+40h+cchName]; lpcchName
0x140041b31  mov     edx, r12d; dwIndex
0x140041b34  mov     rcx, r15; hKey
0x140041b37  call    cs:__imp_RegEnumKeyExW
0x140041b3d  test    eax, eax
0x140041b3f  jnz     loc_140041C65
0x140041b45  mov     ecx, 104h
0x140041b4a  mov     [rsp+140h+dwDisposition], ecx
0x140041b4e  xorps   xmm0, xmm0
0x140041b51  movups  xmmword ptr [rbp+40h+var_98], xmm0
0x140041b55  mov     [rbp+40h+var_98], rdi
0x140041b59  mov     dword ptr [rbp+40h+var_98+8], edi
0x140041b5c  mov     [rbp+40h+var_88], rdi
0x140041b60  mov     [rsp+140h+var_E8], rdi
0x140041b65  mov     r8d, ecx
0x140041b68  lea     rcx, [rsp+140h+var_E8]
0x140041b6d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@GH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort,int)
0x140041b72  nop
0x140041b73  mov     [rbp+40h+var_B8], rdi
0x140041b77  lea     rax, [rbp+40h+var_B8]
0x140041b7b  mov     [rsp+140h+phkResult], rax; phkResult
0x140041b80  mov     r9d, 20019h; samDesired
0x140041b86  xor     r8d, r8d; ulOptions
0x140041b89  mov     rdx, [rsp+140h+lpName]; lpSubKey
0x140041b8e  mov     rcx, r15; hKey
0x140041b91  call    cs:__imp_RegOpenKeyExW
0x140041b97  test    eax, eax
0x140041b99  jnz     loc_140041C20
0x140041b9f  mov     rax, [rbp+40h+var_B8]
0x140041ba3  mov     [rbp+40h+var_98], rax
0x140041ba7  mov     dword ptr [rbp+40h+var_98+8], edi
0x140041baa  mov     r8, [rsp+140h+var_E8]
0x140041baf  cmp     dword ptr [r8-8], 1
0x140041bb4  jle     short loc_140041BC9
0x140041bb6  mov     edx, [r8-10h]
0x140041bba  lea     rcx, [rsp+140h+var_E8]
0x140041bbf  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x140041bc4  mov     r8, [rsp+140h+var_E8]; unsigned __int16 *
0x140041bc9  lea     r9, [rsp+140h+dwDisposition]; unsigned int *
0x140041bce  lea     rdx, WindowName; unsigned __int16 *
0x140041bd5  lea     rcx, [rbp+40h+var_98]; this
0x140041bd9  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140041bde  test    eax, eax
0x140041be0  mov     rax, [rsp+140h+var_E8]
0x140041be5  jnz     short loc_140041C25
0x140041be7  test    rax, rax
0x140041bea  jz      short loc_140041C25
0x140041bec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140041bf0  inc     rcx
0x140041bf3  cmp     [rax+rcx*2], di
0x140041bf7  jnz     short loc_140041BF0
0x140041bf9  lea     ecx, ds:2[rcx*2]
0x140041c00  mov     [rsp+140h+samDesired], ecx; cbData
  ... truncated ...
```
