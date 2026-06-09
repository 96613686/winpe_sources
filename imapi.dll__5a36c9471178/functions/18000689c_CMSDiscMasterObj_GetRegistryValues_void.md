# CMSDiscMasterObj::GetRegistryValues(void)

- ea: `0x18000689c`
- end: `0x180006c0d`
- name: `?GetRegistryValues@CMSDiscMasterObj@@AEAAHXZ`
- size: `881`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006e50`

## callees

- `0x180004714`
- `0x180004784`
- `0x18000689c`
- `0x180007bac`
- `0x180007bd4`
- `0x180007ce0`
- `0x1800184ce`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180006a1a`
- `msvcrt!wcsstr` at `0x180006a1a`
- `ADVAPI32!RegQueryValueExW` at `0x1800069a8`
- `ADVAPI32!RegQueryValueExW` at `0x1800069a8`
- `ADVAPI32!RegCloseKey` at `0x180006be5`
- `ADVAPI32!RegCloseKey` at `0x180006be5`
- `ADVAPI32!RegCreateKeyExW` at `0x180006939`
- `ADVAPI32!RegCreateKeyExW` at `0x180006939`

## string_xrefs

- `0x1800069a1`: `TemporaryStashPath`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::GetRegistryValues(CMSDiscMasterObj *this)
{
  unsigned int v2; // ebx
  unsigned int v3; // eax
  __int64 v4; // r9
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v10; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Data[264]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(Data, 0, 0x20Au);
  hKey = 0;
  Type = 0;
  cbData = 0;
  dwDisposition = 0;
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\IMAPI\\StashInfo",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         &dwDisposition) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
    goto LABEL_5;
  }
  cbData = 520;
  v3 = RegQueryValueExW(hKey, L"TemporaryStashPath", 0, &Type, (LPBYTE)Data, &cbData);
  v4 = v3;
  if ( v3 == 2 )
    goto LABEL_36;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_5;
    v6 = 23;
LABEL_35:
    WPP_SF_d(v5[7], v6, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, v4);
    goto LABEL_5;
  }
  v4 = Type;
  if ( cbData == 2 && Type == 1 )
  {
LABEL_36:
    v2 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
  }
  else
  {
    if ( Type != 1 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_5;
      v6 = 24;
      goto LABEL_35;
    }
    v10 = 0;
    if ( wcsstr(Data, L"System Volume Information") )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, Data);
LABEL_18:
      _bstr_t::~_bstr_t((_bstr_t *)&v10);
LABEL_5:
      v2 = 0;
      goto LABEL_39;
    }
    _bstr_t::operator=(&v10, Data);
    if ( !v10 || !*v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
      goto LABEL_18;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 61) + 176LL))(*((_QWORD *)this + 61), *v10);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          26,
          &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
          (unsigned int)v7);
      goto LABEL_18;
    }
    _bstr_t::~_bstr_t((_bstr_t *)&v10);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, Data);
    v2 = 1;
  }
LABEL_39:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18000689c  mov     [rsp-8+arg_8], rbx
0x1800068a1  push    rbp
0x1800068a2  lea     rbp, [rsp-190h]
0x1800068aa  sub     rsp, 290h
0x1800068b1  mov     rax, cs:__security_cookie
0x1800068b8  xor     rax, rsp
0x1800068bb  mov     [rbp+190h+var_10], rax
0x1800068c2  mov     rbx, rcx
0x1800068c5  xor     edx, edx; Val
0x1800068c7  lea     rcx, [rsp+290h+Data]; void *
0x1800068cc  mov     r8d, 20Ah; Size
0x1800068d2  call    memset_0
0x1800068d7  lea     rax, [rsp+290h+dwDisposition]
0x1800068dc  mov     [rsp+290h+hKey], 0
0x1800068e5  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x1800068ea  lea     rdx, SubKey; "Software\\Microsoft\\IMAPI\\StashInfo"
0x1800068f1  lea     rax, [rsp+290h+hKey]
0x1800068f6  mov     [rsp+290h+Type], 0
0x1800068fe  mov     [rsp+290h+phkResult], rax; phkResult
0x180006903  xor     r9d, r9d; lpClass
0x180006906  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000690f  xor     r8d, r8d; Reserved
0x180006912  mov     [rsp+290h+samDesired], 2001Fh; samDesired
0x18000691a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180006921  mov     [rsp+290h+dwOptions], 0; dwOptions
0x180006929  mov     [rsp+290h+cbData], 0
0x180006931  mov     [rsp+290h+dwDisposition], 0
0x180006939  call    cs:__imp_RegCreateKeyExW
0x18000693f  test    eax, eax
0x180006941  jz      short loc_180006978
0x180006943  mov     rcx, cs:WPP_GLOBAL_Control
0x18000694a  lea     rax, WPP_GLOBAL_Control
0x180006951  cmp     rcx, rax
0x180006954  jz      short loc_180006971
0x180006956  test    byte ptr [rcx+44h], 1
0x18000695a  jz      short loc_180006971
0x18000695c  mov     rcx, [rcx+38h]
0x180006960  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006967  mov     edx, 15h
0x18000696c  call    WPP_SF_
0x180006971  xor     ebx, ebx
0x180006973  jmp     loc_180006BDB
0x180006978  mov     rcx, [rsp+290h+hKey]; hKey
0x18000697d  lea     rax, [rsp+290h+cbData]
0x180006982  mov     qword ptr [rsp+290h+samDesired], rax; lpcbData
0x180006987  lea     r9, [rsp+290h+Type]; lpType
0x18000698c  lea     rax, [rsp+290h+Data]
0x180006991  mov     [rsp+290h+cbData], 208h
0x180006999  xor     r8d, r8d; lpReserved
0x18000699c  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x1800069a1  lea     rdx, ValueName; "TemporaryStashPath"
0x1800069a8  call    cs:__imp_RegQueryValueExW
0x1800069ae  mov     r9d, eax
0x1800069b1  cmp     eax, 2
0x1800069b4  jz      loc_180006BAD
0x1800069ba  test    eax, eax
0x1800069bc  jnz     loc_180006B72
0x1800069c2  cmp     [rsp+290h+cbData], 2
0x1800069c7  mov     r9d, [rsp+290h+Type]
0x1800069cc  jnz     short loc_1800069D8
0x1800069ce  cmp     r9d, 1
0x1800069d2  jz      loc_180006BAD
0x1800069d8  cmp     r9d, 1
0x1800069dc  jz      short loc_180006A05
0x1800069de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069e5  lea     rax, WPP_GLOBAL_Control
0x1800069ec  cmp     rcx, rax
0x1800069ef  jz      short loc_180006971
0x1800069f1  test    byte ptr [rcx+44h], 1
0x1800069f5  jz      loc_180006971
0x1800069fb  mov     edx, 18h
0x180006a00  jmp     loc_180006B98
0x180006a05  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x180006a0c  mov     [rsp+290h+var_238], 0
0x180006a15  lea     rcx, [rsp+290h+Data]; Str
0x180006a1a  call    cs:__imp_wcsstr
0x180006a20  test    rax, rax
0x180006a23  jz      short loc_180006A67
0x180006a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a2c  lea     rax, WPP_GLOBAL_Control
0x180006a33  cmp     rcx, rax
0x180006a36  jz      short loc_180006A58
0x180006a38  test    byte ptr [rcx+44h], 1
0x180006a3c  jz      short loc_180006A58
0x180006a3e  mov     rcx, [rcx+38h]
0x180006a42  lea     r9, [rsp+290h+Data]
0x180006a47  mov     edx, 19h
0x180006a4c  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006a53  call    WPP_SF_S
0x180006a58  lea     rcx, [rsp+290h+var_238]; this
0x180006a5d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180006a62  jmp     loc_180006971
0x180006a67  lea     rdx, [rsp+290h+Data]
0x180006a6c  lea     rcx, [rsp+290h+var_238]
0x180006a71  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180006a76  mov     rax, [rsp+290h+var_238]
0x180006a7b  test    rax, rax
0x180006a7e  jz      loc_180006B37
0x180006a84  cmp     qword ptr [rax], 0
0x180006a88  jz      loc_180006B37
0x180006a8e  mov     r8, [rbx+1E8h]
0x180006a95  mov     rcx, [r8]
0x180006a98  mov     r9, [rcx+0B0h]
0x180006a9f  test    rax, rax
0x180006aa2  jz      short loc_180006AA9
0x180006aa4  mov     rdx, [rax]
0x180006aa7  jmp     short loc_180006AAB
0x180006aa9  xor     edx, edx
0x180006aab  mov     rcx, r8
0x180006aae  mov     rax, r9
0x180006ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab6  mov     r9d, eax
0x180006ab9  test    eax, eax
0x180006abb  jns     short loc_180006AF0
0x180006abd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ac4  lea     rax, WPP_GLOBAL_Control
0x180006acb  cmp     rcx, rax
0x180006ace  jz      short loc_180006A58
0x180006ad0  test    byte ptr [rcx+44h], 1
0x180006ad4  jz      short loc_180006A58
0x180006ad6  mov     rcx, [rcx+38h]
0x180006ada  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006ae1  mov     edx, 1Ah
0x180006ae6  call    WPP_SF_d
0x180006aeb  jmp     loc_180006A58
0x180006af0  lea     rcx, [rsp+290h+var_238]; this
0x180006af5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180006afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b01  lea     rax, WPP_GLOBAL_Control
0x180006b08  cmp     rcx, rax
0x180006b0b  jz      short loc_180006B2D
0x180006b0d  test    byte ptr [rcx+44h], 1
0x180006b11  jz      short loc_180006B2D
0x180006b13  mov     rcx, [rcx+38h]
0x180006b17  lea     r9, [rsp+290h+Data]
0x180006b1c  mov     edx, 1Ch
0x180006b21  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006b28  call    WPP_SF_S
0x180006b2d  mov     ebx, 1
0x180006b32  jmp     loc_180006BDB
0x180006b37  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b3e  lea     rax, WPP_GLOBAL_Control
0x180006b45  cmp     rcx, rax
0x180006b48  jz      loc_180006A58
0x180006b4e  test    byte ptr [rcx+44h], 1
0x180006b52  jz      loc_180006A58
0x180006b58  mov     rcx, [rcx+38h]
0x180006b5c  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006b63  mov     edx, 1Bh
0x180006b68  call    WPP_SF_
0x180006b6d  jmp     loc_180006A58
0x180006b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b79  lea     rax, WPP_GLOBAL_Control
0x180006b80  cmp     rcx, rax
0x180006b83  jz      loc_180006971
0x180006b89  test    byte ptr [rcx+44h], 1
0x180006b8d  jz      loc_180006971
0x180006b93  mov     edx, 17h
0x180006b98  mov     rcx, [rcx+38h]
0x180006b9c  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006ba3  call    WPP_SF_d
0x180006ba8  jmp     loc_180006971
0x180006bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bb4  lea     rax, WPP_GLOBAL_Control
0x180006bbb  xor     ebx, ebx
0x180006bbd  cmp     rcx, rax
0x180006bc0  jz      short loc_180006BDB
0x180006bc2  test    byte ptr [rcx+44h], 1
0x180006bc6  jz      short loc_180006BDB
0x180006bc8  mov     rcx, [rcx+38h]
0x180006bcc  lea     edx, [rbx+16h]
0x180006bcf  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006bd6  call    WPP_SF_
0x180006bdb  mov     rcx, [rsp+290h+hKey]; hKey
0x180006be0  test    rcx, rcx
0x180006be3  jz      short loc_180006BEB
0x180006be5  call    cs:__imp_RegCloseKey
0x180006beb  mov     eax, ebx
0x180006bed  mov     rcx, [rbp+190h+var_10]
0x180006bf4  xor     rcx, rsp; StackCookie
0x180006bf7  call    __security_check_cookie
0x180006bfc  mov     rbx, [rsp+290h+arg_8]
0x180006c04  add     rsp, 290h
0x180006c0b  pop     rbp
0x180006c0c  retn
```
