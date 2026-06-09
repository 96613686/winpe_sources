# AdapterCacheUpdate::GetAdapterKey(DXGI_ADAPTER_DESC1 const &,CachedAdapterInformation &,bool &,bool &,bool &,bool &,bool &)

- ea: `0x14000893c`
- end: `0x140008e63`
- name: `?GetAdapterKey@AdapterCacheUpdate@@QEAAJAEBUDXGI_ADAPTER_DESC1@@AEAUCachedAdapterInformation@@AEA_N2222@Z`
- size: `1319`
- prototype: `unsigned int __fastcall(AdapterCacheUpdate *this, const struct DXGI_ADAPTER_DESC1 *, HKEY *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x14000e174`

## callees

- `0x1400022a0`
- `0x140002d4c`
- `0x140004810`
- `0x140004f00`
- `0x1400050cc`
- `0x140006334`
- `0x140006ec0`
- `0x14000893c`
- `0x14000c8f8`
- `0x1400103b0`
- `0x1400103d0`
- `0x14001113c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008d4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008d4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008c45`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008c77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008cad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008ce6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008c45`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008c77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008cad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008ce6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008d45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008d45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140008dc1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140008dc1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140008c1a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140008c1a`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTCloseAdapter` at `0x140008d0a`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTCloseAdapter` at `0x140008d0a`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008a13`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008a4e`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008a89`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008ac3`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008aff`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008a13`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008a4e`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008a89`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008ac3`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTQueryAdapterInfo` at `0x140008aff`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x140008d99`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x140008d99`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTOpenAdapterFromLuid` at `0x14000899e`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTOpenAdapterFromLuid` at `0x14000899e`

## pseudocode

```c
unsigned int __fastcall AdapterCacheUpdate::GetAdapterKey(
        AdapterCacheUpdate *this,
        const struct DXGI_ADAPTER_DESC1 *a2,
        HKEY *a3,
        bool *a4,
        bool *a5,
        bool *a6,
        bool *a7,
        bool *a8)
{
  unsigned int result; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  int v14; // eax
  unsigned int v15; // r8d
  int v16; // eax
  unsigned int v17; // r8d
  int v18; // eax
  unsigned int v19; // r8d
  int v20; // eax
  unsigned int v21; // r8d
  int v22; // eax
  unsigned int v23; // r8d
  __int64 *v24; // rsi
  __int64 v25; // rbx
  const wchar_t *v26; // rdx
  size_t v27; // r14
  size_t v28; // r15
  const wchar_t *v29; // rcx
  size_t v30; // r8
  int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // r8d
  unsigned int v34; // eax
  unsigned int v35; // r8d
  unsigned int v36; // eax
  unsigned int v37; // r8d
  unsigned int v38; // eax
  unsigned int v39; // r8d
  HKEY v40; // rsi
  DWORD LastError; // ebx
  HKEY v42; // rcx
  unsigned int Key; // eax
  unsigned int v44; // r8d
  int lpData; // [rsp+20h] [rbp-E0h]
  unsigned int lpDataa; // [rsp+20h] [rbp-E0h]
  unsigned int lpDatab; // [rsp+20h] [rbp-E0h]
  unsigned int lpDatac; // [rsp+20h] [rbp-E0h]
  unsigned int lpDatad; // [rsp+20h] [rbp-E0h]
  unsigned int lpDatae; // [rsp+20h] [rbp-E0h]
  BYTE v51[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v52; // [rsp+68h] [rbp-98h] BYREF
  int v53; // [rsp+6Ch] [rbp-94h]
  BYTE *v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  BYTE v56[8]; // [rsp+80h] [rbp-80h] BYREF
  int v57; // [rsp+88h] [rbp-78h] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp-70h] BYREF
  BYTE v59[8]; // [rsp+98h] [rbp-68h] BYREF
  LUID *p_AdapterLuid; // [rsp+A0h] [rbp-60h]
  char v61; // [rsp+A8h] [rbp-58h]
  _BYTE v62[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-40h]
  LUID AdapterLuid; // [rsp+C8h] [rbp-38h] BYREF
  int v65; // [rsp+D0h] [rbp-30h]
  wchar_t *S1[2]; // [rsp+D8h] [rbp-28h] BYREF
  size_t N; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v68; // [rsp+F0h] [rbp-10h]
  WCHAR SubKey[40]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v65 = 0;
  AdapterLuid = a2->AdapterLuid;
  result = D3DKMTOpenAdapterFromLuid(&AdapterLuid);
  if ( result != -1073741811 && result != -1073741130 )
  {
    if ( (result & 0x80000000) != 0 )
      return wil::details::in1diag3::Return_NtStatus(retaddr, v12, v13, (const char *)result, lpData);
    p_AdapterLuid = &AdapterLuid;
    v61 = 1;
    v55 = 80;
    v52 = v65;
    memset_0(SubKey, 0, sizeof(SubKey));
    v54 = (BYTE *)SubKey;
    v53 = 60;
    v14 = D3DKMTQueryAdapterInfo(&v52);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x210, v15, (const char *)(unsigned int)v14, lpData);
    *(_QWORD *)Data = 0;
    v54 = Data;
    LODWORD(v55) = 8;
    v53 = 49;
    v16 = D3DKMTQueryAdapterInfo(&v52);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x217, v17, (const char *)(unsigned int)v16, lpData);
    *(_QWORD *)v59 = 0;
    v54 = v59;
    LODWORD(v55) = 8;
    v53 = 18;
    v18 = D3DKMTQueryAdapterInfo(&v52);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x21D, v19, (const char *)(unsigned int)v18, lpData);
    v57 = 0;
    v54 = (BYTE *)&v57;
    LODWORD(v55) = 4;
    v53 = 22;
    v20 = D3DKMTQueryAdapterInfo(&v52);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x223, v21, (const char *)(unsigned int)v20, lpData);
    *(_DWORD *)v51 = 0;
    v54 = v51;
    LODWORD(v55) = 4;
    v53 = 15;
    v22 = D3DKMTQueryAdapterInfo(&v52);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x229, v23, (const char *)(unsigned int)v22, lpData);
    if ( (v51[0] & 0x20) != 0 )
    {
      *a7 = 1;
    }
    else if ( (*(_WORD *)v51 & 0x400) != 0 && (v57 & 0x20) != 0 )
    {
      *a5 = 1;
    }
    else if ( (v51[0] & 0x10) != 0 )
    {
      *a6 = 1;
    }
    else if ( (*(_WORD *)v51 & 0x8000) != 0 )
    {
      *a8 = 1;
    }
    v24 = (__int64 *)((char *)this + 16);
    std::wstring::wstring(S1, SubKey);
    std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::_Find_lower_bound<std::wstring>(
      (char *)this + 16,
      v62,
      S1);
    v25 = v63;
    if ( *(_BYTE *)(v63 + 25) )
      goto LABEL_28;
    v26 = (const wchar_t *)(v63 + 32);
    v27 = *(_QWORD *)(v63 + 48);
    if ( *(_QWORD *)(v63 + 56) > 7u )
      v26 = *(const wchar_t **)v26;
    v28 = N;
    v29 = (const wchar_t *)S1;
    if ( v68 > 7 )
      v29 = S1[0];
    v30 = *(_QWORD *)(v63 + 48);
    if ( v27 >= N )
      v30 = N;
    v31 = wmemcmp(v29, v26, v30);
    if ( v31 )
    {
      if ( v31 < 0 )
        goto LABEL_28;
    }
    else if ( v28 < v27 )
    {
LABEL_28:
      v25 = *v24;
    }
    std::wstring::~wstring(S1);
    if ( v25 == *v24 )
    {
      v40 = *a3;
      if ( *a3 )
      {
        LastError = GetLastError();
        RegCloseKey(v40);
        SetLastError(LastError);
      }
      *a3 = 0;
      v42 = (HKEY)*((_QWORD *)this + 1);
      if ( (unsigned __int64)(*(_QWORD *)this - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
        Key = RegCreateKeyExW(v42, SubKey, 0, 0, 0, 0x2001Fu, 0, a3, 0);
      else
        Key = RegCreateKeyTransactedW(v42, SubKey, 0, 0, 0, 0x2001Fu, 0, a3, 0, *(HANDLE *)this, 0);
      if ( Key )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x257, v44, (const char *)Key, lpDatae);
    }
    else
    {
      CachedAdapterInformation::operator=(a3, v25 + 64);
      std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>>,0>(
        (char *)this + 16,
        v56,
        v25);
      if ( a3[1] == *(HKEY *)Data && a3[2] == *(HKEY *)v59 && *((_DWORD *)a3 + 24) == 2 )
      {
        *a4 = 0;
LABEL_43:
        *(_DWORD *)v56 = v65;
        D3DKMTCloseAdapter(v56);
        return 0;
      }
      RegDeleteTreeW(*a3, 0);
    }
    v32 = RegSetValueExW(*a3, L"DriverVersion", 0, 0xBu, Data, 8u);
    if ( v32 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v33, (const char *)v32, lpDataa);
    v34 = RegSetValueExW(*a3, L"UMDVersion", 0, 0xBu, v59, 8u);
    if ( v34 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v35, (const char *)v34, lpDatab);
    v36 = RegSetValueExW(*a3, L"AdapterType", 0, 4u, v51, 4u);
    if ( v36 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v37, (const char *)v36, lpDatac);
    *(_DWORD *)v56 = 2;
    v38 = RegSetValueExW(*a3, L"SchemaVersion", 0, 4u, v56, 4u);
    if ( v38 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v39, (const char *)v38, lpDatad);
    *a4 = 1;
    goto LABEL_43;
  }
  return result;
}

```

## disassembly

```asm
0x14000893c  push    rbp
0x14000893e  push    rbx
0x14000893f  push    rsi
0x140008940  push    rdi
0x140008941  push    r12
0x140008943  push    r13
0x140008945  push    r14
0x140008947  push    r15
0x140008949  lea     rbp, [rsp-68h]
0x14000894e  sub     rsp, 168h
0x140008955  mov     rax, cs:__security_cookie
0x14000895c  xor     rax, rsp
0x14000895f  mov     [rbp+0A0h+var_50], rax
0x140008963  mov     r13, r9
0x140008966  mov     rdi, r8
0x140008969  mov     r12, rcx
0x14000896c  mov     rsi, [rbp+0A0h+arg_20]
0x140008973  mov     r14, [rbp+0A0h+arg_28]
0x14000897a  mov     rbx, [rbp+0A0h+arg_30]
0x140008981  mov     r15, [rbp+0A0h+arg_38]
0x140008988  mov     [rbp+0A0h+var_D0], 0
0x14000898f  mov     rax, [rdx+128h]
0x140008996  mov     [rbp+0A0h+var_D8], rax
0x14000899a  lea     rcx, [rbp+0A0h+var_D8]
0x14000899e  call    cs:__imp_D3DKMTOpenAdapterFromLuid
0x1400089a4  cmp     eax, 0C000000Dh
0x1400089a9  jz      loc_140008D12
0x1400089af  cmp     eax, 0C00002B6h
0x1400089b4  jz      loc_140008D12
0x1400089ba  test    eax, eax
0x1400089bc  jns     short loc_1400089D2
0x1400089be  mov     rcx, [rbp+0A8h]; this
0x1400089c5  mov     r9d, eax; char *
0x1400089c8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400089cd  jmp     loc_140008D12
0x1400089d2  lea     rax, [rbp+0A0h+var_D8]
0x1400089d6  mov     [rbp+0A0h+var_100], rax
0x1400089da  mov     [rbp+0A0h+var_F8], 1
0x1400089de  mov     [rsp+1A0h+var_128], 50h ; 'P'
0x1400089e7  mov     eax, [rbp+0A0h+var_D0]
0x1400089ea  mov     [rsp+1A0h+var_138], eax
0x1400089ee  xor     edx, edx; Val
0x1400089f0  lea     r8d, [rdx+50h]; Size
0x1400089f4  lea     rcx, [rbp+0A0h+SubKey]; void *
0x1400089f8  call    memset_0
0x1400089fd  lea     rax, [rbp+0A0h+SubKey]
0x140008a01  mov     [rsp+1A0h+var_130], rax
0x140008a06  mov     [rsp+1A0h+var_134], 3Ch ; '<'
0x140008a0e  lea     rcx, [rsp+1A0h+var_138]
0x140008a13  call    cs:__imp_D3DKMTQueryAdapterInfo
0x140008a19  mov     rcx, [rbp+0A8h]; this
0x140008a20  test    eax, eax
0x140008a22  js      loc_140008DF3
0x140008a28  mov     qword ptr [rbp+0A0h+Data], 0
0x140008a30  lea     rax, [rbp+0A0h+Data]
0x140008a34  mov     [rsp+1A0h+var_130], rax
0x140008a39  mov     dword ptr [rsp+1A0h+var_128], 8
0x140008a41  mov     [rsp+1A0h+var_134], 31h ; '1'
0x140008a49  lea     rcx, [rsp+1A0h+var_138]
0x140008a4e  call    cs:__imp_D3DKMTQueryAdapterInfo
0x140008a54  mov     rcx, [rbp+0A8h]; this
0x140008a5b  test    eax, eax
0x140008a5d  js      loc_140008E01
0x140008a63  mov     qword ptr [rbp+0A0h+var_108], 0
0x140008a6b  lea     rax, [rbp+0A0h+var_108]
0x140008a6f  mov     [rsp+1A0h+var_130], rax
0x140008a74  mov     dword ptr [rsp+1A0h+var_128], 8
0x140008a7c  mov     [rsp+1A0h+var_134], 12h
0x140008a84  lea     rcx, [rsp+1A0h+var_138]
0x140008a89  call    cs:__imp_D3DKMTQueryAdapterInfo
0x140008a8f  mov     rcx, [rbp+0A8h]; this
0x140008a96  test    eax, eax
0x140008a98  js      loc_140008E0F
0x140008a9e  mov     [rbp+0A0h+var_118], 0
0x140008aa5  lea     rax, [rbp+0A0h+var_118]
0x140008aa9  mov     [rsp+1A0h+var_130], rax
0x140008aae  mov     dword ptr [rsp+1A0h+var_128], 4
0x140008ab6  mov     [rsp+1A0h+var_134], 16h
0x140008abe  lea     rcx, [rsp+1A0h+var_138]
0x140008ac3  call    cs:__imp_D3DKMTQueryAdapterInfo
0x140008ac9  mov     rcx, [rbp+0A8h]; this
0x140008ad0  test    eax, eax
0x140008ad2  js      loc_140008E1D
0x140008ad8  mov     dword ptr [rsp+1A0h+var_140], 0
0x140008ae0  lea     rax, [rsp+1A0h+var_140]
0x140008ae5  mov     [rsp+1A0h+var_130], rax
0x140008aea  mov     dword ptr [rsp+1A0h+var_128], 4
0x140008af2  mov     [rsp+1A0h+var_134], 0Fh
0x140008afa  lea     rcx, [rsp+1A0h+var_138]
0x140008aff  call    cs:__imp_D3DKMTQueryAdapterInfo
0x140008b05  mov     rcx, [rbp+0A8h]; this
0x140008b0c  test    eax, eax
0x140008b0e  js      loc_140008E2B
0x140008b14  mov     eax, dword ptr [rsp+1A0h+var_140]
0x140008b18  test    al, 20h
0x140008b1a  jz      short loc_140008B21
0x140008b1c  mov     byte ptr [rbx], 1
0x140008b1f  jmp     short loc_140008B46
0x140008b21  bt      eax, 0Ah
0x140008b25  jnb     short loc_140008B32
0x140008b27  test    byte ptr [rbp+0A0h+var_118], 20h
0x140008b2b  jz      short loc_140008B32
0x140008b2d  mov     byte ptr [rsi], 1
0x140008b30  jmp     short loc_140008B46
0x140008b32  test    al, 10h
0x140008b34  jz      short loc_140008B3C
0x140008b36  mov     byte ptr [r14], 1
0x140008b3a  jmp     short loc_140008B46
0x140008b3c  bt      eax, 0Fh
0x140008b40  jnb     short loc_140008B46
0x140008b42  mov     byte ptr [r15], 1
0x140008b46  lea     rsi, [r12+10h]
0x140008b4b  lea     rdx, [rbp+0A0h+SubKey]
0x140008b4f  lea     rcx, [rbp+0A0h+S1]
0x140008b53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140008b58  lea     r8, [rbp+0A0h+S1]
0x140008b5c  lea     rdx, [rbp+0A0h+var_F0]
0x140008b60  mov     rcx, rsi
0x140008b63  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x140008b68  mov     rbx, [rbp+0A0h+var_E0]
0x140008b6c  xor     r14d, r14d
0x140008b6f  cmp     [rbx+19h], r14b
0x140008b73  jnz     short loc_140008BB4
0x140008b75  lea     rdx, [rbx+20h]
0x140008b79  mov     r14, [rdx+10h]
0x140008b7d  cmp     qword ptr [rdx+18h], 7
0x140008b82  jbe     short loc_140008B87
0x140008b84  mov     rdx, [rdx]; S2
0x140008b87  mov     r15, [rbp+0A0h+N]
0x140008b8b  lea     rcx, [rbp+0A0h+S1]
0x140008b8f  cmp     [rbp+0A0h+var_B0], 7
0x140008b94  cmova   rcx, [rbp+0A0h+S1]; S1
0x140008b99  mov     r8, r14
0x140008b9c  cmp     r14, r15
0x140008b9f  cmovnb  r8, r15; N
0x140008ba3  call    wmemcmp
0x140008ba8  test    eax, eax
0x140008baa  jnz     short loc_140008C07
0x140008bac  cmp     r15, r14
0x140008baf  jnb     short loc_140008C10
0x140008bb1  xor     r14d, r14d
0x140008bb4  mov     rbx, [rsi]
0x140008bb7  lea     rcx, [rbp+0A0h+S1]
0x140008bbb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140008bc0  cmp     rbx, [rsi]
0x140008bc3  jz      loc_140008D32
0x140008bc9  lea     rdx, [rbx+40h]
0x140008bcd  mov     rcx, rdi
0x140008bd0  call    ??4CachedAdapterInformation@@QEAAAEAU0@$$QEAU0@@Z; CachedAdapterInformation::operator=(CachedAdapterInformation &&)
0x140008bd5  mov     r8, rbx
0x140008bd8  lea     rdx, [rbp+0A0h+var_120]
0x140008bdc  mov     rcx, rsi
0x140008bdf  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>>)
0x140008be4  mov     rax, qword ptr [rbp+0A0h+Data]
0x140008be8  cmp     [rdi+8], rax
0x140008bec  jnz     short loc_140008C15
0x140008bee  mov     rax, qword ptr [rbp+0A0h+var_108]
0x140008bf2  cmp     [rdi+10h], rax
0x140008bf6  jnz     short loc_140008C15
0x140008bf8  cmp     dword ptr [rdi+60h], 2
0x140008bfc  jnz     short loc_140008C15
0x140008bfe  mov     [r13+0], r14b
0x140008c02  jmp     loc_140008D00
0x140008c07  xor     r14d, r14d
0x140008c0a  test    eax, eax
0x140008c0c  js      short loc_140008BB4
0x140008c0e  jmp     short loc_140008BB7
0x140008c10  xor     r14d, r14d
0x140008c13  jmp     short loc_140008BB7
0x140008c15  xor     edx, edx; lpSubKey
0x140008c17  mov     rcx, [rdi]; hKey
0x140008c1a  call    cs:__imp_RegDeleteTreeW
0x140008c20  mov     esi, 8
0x140008c25  mov     [rsp+1A0h+cbData], esi; cbData
0x140008c29  lea     rax, [rbp+0A0h+Data]
0x140008c2d  mov     [rsp+1A0h+lpData], rax; unsigned int
0x140008c32  lea     ebx, [rsi+3]
0x140008c35  mov     r9d, ebx; dwType
0x140008c38  xor     r8d, r8d; Reserved
0x140008c3b  lea     rdx, aDriverversion; "DriverVersion"
0x140008c42  mov     rcx, [rdi]; hKey
0x140008c45  call    cs:__imp_RegSetValueExW
0x140008c4b  mov     rcx, [rbp+0A8h]; this
0x140008c52  test    eax, eax
0x140008c54  jnz     loc_140008E39
0x140008c5a  mov     [rsp+1A0h+cbData], esi; cbData
0x140008c5e  lea     rax, [rbp+0A0h+var_108]
0x140008c62  mov     [rsp+1A0h+lpData], rax; unsigned int
0x140008c67  mov     r9d, ebx; dwType
0x140008c6a  xor     r8d, r8d; Reserved
0x140008c6d  lea     rdx, aUmdversion; "UMDVersion"
0x140008c74  mov     rcx, [rdi]; hKey
0x140008c77  call    cs:__imp_RegSetValueExW
0x140008c7d  mov     rcx, [rbp+0A8h]; this
0x140008c84  test    eax, eax
0x140008c86  jnz     loc_140008E47
0x140008c8c  lea     ebx, [rax+4]
0x140008c8f  mov     [rsp+1A0h+cbData], ebx; cbData
0x140008c93  lea     rax, [rsp+1A0h+var_140]
0x140008c98  mov     [rsp+1A0h+lpData], rax; unsigned int
0x140008c9d  mov     r9d, ebx; dwType
0x140008ca0  xor     r8d, r8d; Reserved
0x140008ca3  lea     rdx, aAdaptertype; "AdapterType"
0x140008caa  mov     rcx, [rdi]; hKey
0x140008cad  call    cs:__imp_RegSetValueExW
0x140008cb3  mov     rcx, [rbp+0A8h]; this
0x140008cba  test    eax, eax
0x140008cbc  jnz     loc_140008E55
0x140008cc2  mov     dword ptr [rbp+0A0h+var_120], 2
0x140008cc9  mov     [rsp+1A0h+cbData], ebx; cbData
0x140008ccd  lea     rax, [rbp+0A0h+var_120]
0x140008cd1  mov     [rsp+1A0h+lpData], rax; unsigned int
0x140008cd6  mov     r9d, ebx; dwType
0x140008cd9  xor     r8d, r8d; Reserved
0x140008cdc  lea     rdx, aSchemaversion; "SchemaVersion"
0x140008ce3  mov     rcx, [rdi]; hKey
0x140008ce6  call    cs:__imp_RegSetValueExW
0x140008cec  mov     rcx, [rbp+0A8h]; this
0x140008cf3  test    eax, eax
0x140008cf5  jnz     loc_140008DD7
0x140008cfb  mov     byte ptr [r13+0], 1
0x140008d00  mov     eax, [rbp+0A0h+var_D0]
0x140008d03  mov     dword ptr [rbp+0A0h+var_120], eax
0x140008d06  lea     rcx, [rbp+0A0h+var_120]
0x140008d0a  call    cs:__imp_D3DKMTCloseAdapter
0x140008d10  xor     eax, eax
0x140008d12  mov     rcx, [rbp+0A0h+var_50]
0x140008d16  xor     rcx, rsp; StackCookie
0x140008d19  call    __security_check_cookie
0x140008d1e  add     rsp, 168h
0x140008d25  pop     r15
0x140008d27  pop     r14
0x140008d29  pop     r13
0x140008d2b  pop     r12
0x140008d2d  pop     rdi
0x140008d2e  pop     rsi
0x140008d2f  pop     rbx
0x140008d30  pop     rbp
0x140008d31  retn
0x140008d32  mov     rsi, [rdi]
0x140008d35  test    rsi, rsi
0x140008d38  jz      short loc_140008D53
0x140008d3a  call    cs:__imp_GetLastError
0x140008d40  mov     ebx, eax
0x140008d42  mov     rcx, rsi; hKey
0x140008d45  call    cs:__imp_RegCloseKey
0x140008d4b  mov     ecx, ebx; dwErrCode
0x140008d4d  call    cs:__imp_SetLastError
0x140008d53  mov     [rdi], r14
0x140008d56  mov     rcx, [r12+8]; hKey
0x140008d5b  mov     rdx, [r12]
0x140008d5f  lea     rax, [rdx-1]
0x140008d63  xor     r9d, r9d; lpClass
0x140008d66  xor     r8d, r8d; Reserved
0x140008d69  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140008d6d  ja      short loc_140008DA1
0x140008d6f  mov     [rsp+1A0h+pExtendedParemeter], r14; pExtendedParemeter
0x140008d74  mov     [rsp+1A0h+hTransaction], rdx; hTransaction
0x140008d79  mov     [rsp+1A0h+lpdwDisposition], r14; lpdwDisposition
0x140008d7e  mov     [rsp+1A0h+phkResult], rdi; phkResult
0x140008d83  mov     [rsp+1A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x140008d88  mov     [rsp+1A0h+cbData], 2001Fh; samDesired
0x140008d90  mov     dword ptr [rsp+1A0h+lpData], r14d; dwOptions
0x140008d95  lea     rdx, [rbp+0A0h+SubKey]; lpSubKey
0x140008d99  call    cs:__imp_RegCreateKeyTransactedW
0x140008d9f  jmp     short loc_140008DC7
0x140008da1  mov     [rsp+1A0h+lpdwDisposition], r14; lpdwDisposition
0x140008da6  mov     [rsp+1A0h+phkResult], rdi; phkResult
0x140008dab  mov     [rsp+1A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x140008db0  mov     [rsp+1A0h+cbData], 2001Fh; samDesired
0x140008db8  mov     dword ptr [rsp+1A0h+lpData], r14d; unsigned int
0x140008dbd  lea     rdx, [rbp+0A0h+SubKey]; lpSubKey
0x140008dc1  call    cs:__imp_RegCreateKeyExW
0x140008dc7  mov     rcx, [rbp+0A8h]; this
0x140008dce  test    eax, eax
0x140008dd0  jnz     short loc_140008DE5
0x140008dd2  jmp     loc_140008C20
0x140008dd7  mov     r9d, eax; char *
0x140008dda  mov     edx, 152h; void *
0x140008ddf  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140008de5  mov     r9d, eax; char *
0x140008de8  mov     edx, 257h; void *
0x140008ded  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140008df3  mov     r9d, eax; char *
0x140008df6  mov     edx, 210h; void *
0x140008dfb  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140008e01  mov     r9d, eax; char *
0x140008e04  mov     edx, 217h; void *
0x140008e09  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140008e0f  mov     r9d, eax; char *
0x140008e12  mov     edx, 21Dh; void *
0x140008e17  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140008e1d  mov     r9d, eax; char *
0x140008e20  mov     edx, 223h; void *
0x140008e25  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140008e2b  mov     r9d, eax; char *
0x140008e2e  mov     edx, 229h; void *
0x140008e33  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140008e39  mov     r9d, eax; char *
0x140008e3c  mov     edx, 152h; void *
  ... truncated ...
```
