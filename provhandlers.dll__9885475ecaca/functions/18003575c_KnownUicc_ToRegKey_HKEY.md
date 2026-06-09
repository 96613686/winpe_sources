# KnownUicc::ToRegKey(HKEY__ *)

- ea: `0x18003575c`
- end: `0x180035baa`
- name: `?ToRegKey@KnownUicc@@QEBAXPEAUHKEY__@@@Z`
- size: `1102`
- prototype: `void __fastcall(LPCWSTR lpSubKey, HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180031100`

## callees

- `0x180007ed4`
- `0x180012390`
- `0x180012d80`
- `0x18003575c`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035aae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035aae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003580c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800358f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035983`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035a82`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003580c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800358f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035983`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035a82`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800357d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035859`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800357d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035859`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall KnownUicc::ToRegKey(LPCWSTR lpSubKey, HKEY hKey)
{
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 *v8; // rdi
  __int64 *v9; // rbx
  unsigned int v10; // eax
  __int64 v11; // r9
  int v12; // eax
  unsigned int v13; // eax
  __int64 *i; // rax
  __int64 *v15; // rcx
  unsigned int v16; // eax
  _WORD *v17; // rdx
  _WORD *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r9
  unsigned __int64 v21; // rax
  DWORD v22; // ecx
  unsigned int v23; // r8d
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-E0h]
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  hKeya = 0;
  if ( *((_QWORD *)lpSubKey + 3) < 8u )
    v4 = lpSubKey;
  else
    v4 = *(const WCHAR **)lpSubKey;
  v5 = RegCreateKeyExW(hKey, v4, 0, 0, 0, 2u, 0, &hKeya, 0);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)v5,
      dwOptions);
  v6 = RegSetValueExW(hKeya, L"Status", 0, 4u, (const BYTE *)lpSubKey + 40, 4u);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)v6,
      dwOptionsa);
  phkResult = 0;
  v7 = RegCreateKeyExW(hKeya, L"Results", 0, 0, 0, 2u, 0, &phkResult, 0);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)v7,
      dwOptionsb);
  v8 = (__int64 *)*((_QWORD *)lpSubKey + 6);
  v9 = (__int64 *)*v8;
  while ( v9 != v8 )
  {
    v10 = 0;
    while ( *((_DWORD *)&off_180040F50 + 4 * v10 + 2) != *((_DWORD *)v9 + 7) )
    {
      if ( ++v10 >= 0x12 )
      {
        v11 = 2147943568LL;
        goto LABEL_15;
      }
    }
    v12 = StringCchCopyW(ValueName, 0x104u, (&off_180040F50)[2 * v10]);
    v11 = (unsigned int)v12;
    if ( v12 >= 0 )
      v11 = 0;
LABEL_15:
    if ( (int)v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v11,
        dwOptionsb);
    v13 = RegSetValueExW(phkResult, ValueName, 0, 4u, (const BYTE *)v9 + 32, 4u);
    if ( v13 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v13,
        dwOptionsb);
    if ( !*((_BYTE *)v9 + 25) )
    {
      i = (__int64 *)v9[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v9 = i;
LABEL_26:
        v9 = i;
      }
      else
      {
        v15 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_26;
        do
        {
          v9 = v15;
          v15 = (__int64 *)*v15;
        }
        while ( !*((_BYTE *)v15 + 25) );
      }
    }
  }
  if ( *((_DWORD *)lpSubKey + 10) == 1 )
  {
    v16 = RegSetValueExW(hKeya, L"UIRequired", 0, 4u, (const BYTE *)lpSubKey + 44, 4u);
    if ( v16 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v16,
        dwOptionsc);
    v17 = (_WORD *)*((_QWORD *)lpSubKey + 4);
    if ( *((_QWORD *)v17 + 3) < 8u )
      v18 = (_WORD *)*((_QWORD *)lpSubKey + 4);
    else
      v18 = *(_WORD **)v17;
    if ( v18 )
    {
      v19 = 0x7FFFFFFF;
      do
      {
        if ( !*v18 )
          break;
        ++v18;
        --v19;
      }
      while ( v19 );
      v20 = v19 == 0 ? 0x80070057 : 0;
      if ( v19 )
      {
        v21 = (2 * (0x7FFFFFFF - v19)) & -(__int64)(v19 != 0);
        goto LABEL_40;
      }
    }
    else
    {
      v20 = 2147942487LL;
    }
    v21 = 0;
LABEL_40:
    if ( (int)v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v20,
        dwOptionsc);
    v22 = -1;
    v23 = v21;
    if ( v21 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        v21 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
        dwOptionsc);
    v24 = v21 + 2;
    if ( v23 + 2 >= v23 )
      v22 = v23 + 2;
    if ( v24 < v23 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        v24 < v23 ? (const char *)0x80070216LL : 0,
        dwOptionsc);
    if ( *((_QWORD *)v17 + 3) >= 8u )
      v17 = *(_WORD **)v17;
    v25 = RegSetValueExW(hKeya, L"IMSI", 0, 1u, (const BYTE *)v17, v22);
    if ( v25 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v25,
        dwOptionsd);
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKeya )
    RegCloseKey(hKeya);
}

```

## disassembly

```asm
0x18003575c  mov     [rsp-8+arg_10], rbx
0x180035761  push    rbp
0x180035762  push    rsi
0x180035763  push    rdi
0x180035764  push    r12
0x180035766  push    r13
0x180035768  push    r14
0x18003576a  push    r15
0x18003576c  lea     rbp, [rsp-180h]
0x180035774  sub     rsp, 280h
0x18003577b  mov     rax, cs:__security_cookie
0x180035782  xor     rax, rsp
0x180035785  mov     [rbp+1B0h+var_40], rax
0x18003578c  mov     rax, rdx
0x18003578f  mov     rsi, rcx
0x180035792  xor     r15d, r15d
0x180035795  mov     [rsp+2B0h+hKey], r15
0x18003579a  cmp     qword ptr [rcx+18h], 8
0x18003579f  jb      short loc_1800357A6
0x1800357a1  mov     rdx, [rcx]
0x1800357a4  jmp     short loc_1800357A9
0x1800357a6  mov     rdx, rsi; lpSubKey
0x1800357a9  mov     [rsp+2B0h+lpdwDisposition], r15; lpdwDisposition
0x1800357ae  lea     rcx, [rsp+2B0h+hKey]
0x1800357b3  mov     [rsp+2B0h+phkResult], rcx; phkResult
0x1800357b8  mov     [rsp+2B0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800357bd  mov     [rsp+2B0h+samDesired], 2; samDesired
0x1800357c5  mov     [rsp+2B0h+dwOptions], r15d; unsigned int
0x1800357ca  xor     r9d, r9d; lpClass
0x1800357cd  xor     r8d, r8d; Reserved
0x1800357d0  mov     rcx, rax; hKey
0x1800357d3  call    cs:__imp_RegCreateKeyExW
0x1800357d9  mov     rcx, [rbp+1B8h]; this
0x1800357e0  test    eax, eax
0x1800357e2  jnz     loc_180035AF3
0x1800357e8  lea     r14, [rsi+28h]
0x1800357ec  lea     r12d, [rax+4]
0x1800357f0  mov     [rsp+2B0h+samDesired], r12d; cbData
0x1800357f5  mov     qword ptr [rsp+2B0h+dwOptions], r14; unsigned int
0x1800357fa  mov     r9d, r12d; dwType
0x1800357fd  xor     r8d, r8d; Reserved
0x180035800  lea     rdx, ?c_status@@3QBGB; "Status"
0x180035807  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003580c  call    cs:__imp_RegSetValueExW
0x180035812  mov     rcx, [rbp+1B8h]; this
0x180035819  test    eax, eax
0x18003581b  jnz     loc_180035B08
0x180035821  mov     [rsp+2B0h+var_258], r15
0x180035826  mov     [rsp+2B0h+lpdwDisposition], r15; lpdwDisposition
0x18003582b  lea     rax, [rsp+2B0h+var_258]
0x180035830  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180035835  mov     [rsp+2B0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003583a  mov     [rsp+2B0h+samDesired], 2; samDesired
0x180035842  mov     [rsp+2B0h+dwOptions], r15d; int
0x180035847  xor     r9d, r9d; lpClass
0x18003584a  xor     r8d, r8d; Reserved
0x18003584d  lea     rdx, ?c_results@@3QBGB; "Results"
0x180035854  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180035859  call    cs:__imp_RegCreateKeyExW
0x18003585f  mov     rcx, [rbp+1B8h]; this
0x180035866  test    eax, eax
0x180035868  jnz     loc_180035B1D
0x18003586e  mov     rdi, [rsi+30h]
0x180035872  mov     rbx, [rdi]
0x180035875  lea     r13, off_180040F50; "Uicc_Language"
0x18003587c  cmp     rbx, rdi
0x18003587f  jz      loc_180035959
0x180035885  mov     ecx, [rbx+1Ch]
0x180035888  mov     eax, r15d
0x18003588b  mov     r8d, eax
0x18003588e  add     r8, r8
0x180035891  cmp     [r13+r8*8+8], ecx
0x180035896  jz      short loc_1800358A7
0x180035898  inc     eax
0x18003589a  cmp     eax, 12h
0x18003589d  jb      short loc_18003588B
0x18003589f  mov     r9d, 80070490h
0x1800358a5  jmp     short loc_1800358C4
0x1800358a7  mov     r8, [r13+r8*8+0]; unsigned __int16 *
0x1800358ac  mov     edx, 104h; unsigned __int64
0x1800358b1  lea     rcx, [rsp+2B0h+ValueName]; unsigned __int16 *
0x1800358b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800358bb  mov     r9d, eax
0x1800358be  test    eax, eax
0x1800358c0  cmovns  r9d, r15d; char *
0x1800358c4  mov     rcx, [rbp+1B8h]; this
0x1800358cb  test    r9d, r9d
0x1800358ce  js      loc_180035B47
0x1800358d4  lea     rax, [rbx+20h]
0x1800358d8  mov     [rsp+2B0h+samDesired], r12d; cbData
0x1800358dd  mov     qword ptr [rsp+2B0h+dwOptions], rax; unsigned int
0x1800358e2  mov     r9d, r12d; dwType
0x1800358e5  xor     r8d, r8d; Reserved
0x1800358e8  lea     rdx, [rsp+2B0h+ValueName]; lpValueName
0x1800358ed  mov     rcx, [rsp+2B0h+var_258]; hKey
0x1800358f2  call    cs:__imp_RegSetValueExW
0x1800358f8  mov     rcx, [rbp+1B8h]; this
0x1800358ff  test    eax, eax
0x180035901  jnz     loc_180035B32
0x180035907  cmp     [rbx+19h], r15b
0x18003590b  jnz     loc_18003587C
0x180035911  mov     rax, [rbx+10h]
0x180035915  cmp     [rax+19h], r15b
0x180035919  jnz     short loc_180035938
0x18003591b  mov     rcx, [rax]
0x18003591e  cmp     [rcx+19h], r15b
0x180035922  jnz     short loc_180035951
0x180035924  mov     rbx, rcx
0x180035927  mov     rax, [rcx]
0x18003592a  mov     rcx, rax
0x18003592d  cmp     [rax+19h], r15b
0x180035931  jz      short loc_180035924
0x180035933  jmp     loc_18003587C
0x180035938  mov     rax, [rbx+8]
0x18003593c  jmp     short loc_18003594B
0x18003593e  cmp     rbx, [rax+10h]
0x180035942  jnz     short loc_180035951
0x180035944  mov     rbx, rax
0x180035947  mov     rax, [rax+8]
0x18003594b  cmp     [rax+19h], r15b
0x18003594f  jz      short loc_18003593E
0x180035951  mov     rbx, rax
0x180035954  jmp     loc_18003587C
0x180035959  cmp     dword ptr [r14], 1
0x18003595d  jnz     loc_180035A93
0x180035963  lea     rax, [rsi+2Ch]
0x180035967  mov     [rsp+2B0h+samDesired], r12d; cbData
0x18003596c  mov     qword ptr [rsp+2B0h+dwOptions], rax; int
0x180035971  mov     r9d, r12d; dwType
0x180035974  xor     r8d, r8d; Reserved
0x180035977  lea     rdx, ?gc_wszUIRequired@@3QBGB; "UIRequired"
0x18003597e  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180035983  call    cs:__imp_RegSetValueExW
0x180035989  mov     rcx, [rbp+1B8h]; this
0x180035990  test    eax, eax
0x180035992  jnz     loc_180035B59
0x180035998  mov     rdx, [rsi+20h]
0x18003599c  cmp     qword ptr [rdx+18h], 8
0x1800359a1  jb      short loc_1800359A8
0x1800359a3  mov     rax, [rdx]
0x1800359a6  jmp     short loc_1800359AB
0x1800359a8  mov     rax, rdx
0x1800359ab  test    rax, rax
0x1800359ae  jz      short loc_1800359F2
0x1800359b0  mov     r8d, 7FFFFFFFh
0x1800359b6  mov     ecx, r8d
0x1800359b9  cmp     [rax], r15w
0x1800359bd  jz      short loc_1800359C9
0x1800359bf  add     rax, 2
0x1800359c3  sub     rcx, 1
0x1800359c7  jnz     short loc_1800359B9
0x1800359c9  mov     rax, rcx
0x1800359cc  neg     rax
0x1800359cf  sbb     r9d, r9d
0x1800359d2  not     r9d
0x1800359d5  and     r9d, 80070057h
0x1800359dc  test    rcx, rcx
0x1800359df  jz      short loc_1800359F8
0x1800359e1  sub     r8, rcx
0x1800359e4  add     r8, r8
0x1800359e7  neg     rcx
0x1800359ea  sbb     rax, rax
0x1800359ed  and     rax, r8
0x1800359f0  jmp     short loc_1800359FB
0x1800359f2  mov     r9d, 80070057h; char *
0x1800359f8  mov     rax, r15
0x1800359fb  mov     rcx, [rbp+1B8h]; this
0x180035a02  test    r9d, r9d
0x180035a05  js      loc_180035B6E
0x180035a0b  mov     ecx, 0FFFFFFFFh
0x180035a10  cmp     rax, rcx
0x180035a13  mov     r8d, eax
0x180035a16  jbe     short loc_180035A1B
0x180035a18  mov     r8d, ecx
0x180035a1b  cmp     rcx, rax
0x180035a1e  sbb     r9d, r9d
0x180035a21  mov     r11d, 80070216h
0x180035a27  and     r9d, r11d; char *
0x180035a2a  mov     r10, [rbp+1B8h]
0x180035a31  cmp     rax, rcx
0x180035a34  ja      loc_180035B80
0x180035a3a  lea     eax, [r8+2]
0x180035a3e  cmp     eax, r8d
0x180035a41  cmovnb  ecx, eax
0x180035a44  sbb     r9d, r9d
0x180035a47  and     r9d, r11d; char *
0x180035a4a  mov     r10, [rbp+1B8h]
0x180035a51  cmp     eax, r8d
0x180035a54  jb      loc_180035B95
0x180035a5a  cmp     qword ptr [rdx+18h], 8
0x180035a5f  jb      short loc_180035A64
0x180035a61  mov     rdx, [rdx]
0x180035a64  mov     [rsp+2B0h+samDesired], ecx; cbData
0x180035a68  mov     qword ptr [rsp+2B0h+dwOptions], rdx; unsigned int
0x180035a6d  mov     r9d, 1; dwType
0x180035a73  xor     r8d, r8d; Reserved
0x180035a76  lea     rdx, c_wszIMSIAttribute; "IMSI"
0x180035a7d  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180035a82  call    cs:__imp_RegSetValueExW
0x180035a88  mov     rcx, [rbp+1B8h]; this
0x180035a8f  test    eax, eax
0x180035a91  jnz     short loc_180035ADE
0x180035a93  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180035a98  test    rcx, rcx
0x180035a9b  jz      short loc_180035AA4
0x180035a9d  call    cs:__imp_RegCloseKey
0x180035aa3  nop
0x180035aa4  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180035aa9  test    rcx, rcx
0x180035aac  jz      short loc_180035AB4
0x180035aae  call    cs:__imp_RegCloseKey
0x180035ab4  mov     rcx, [rbp+1B0h+var_40]
0x180035abb  xor     rcx, rsp; StackCookie
0x180035abe  call    __security_check_cookie
0x180035ac3  mov     rbx, [rsp+2B0h+arg_10]
0x180035acb  add     rsp, 280h
0x180035ad2  pop     r15
0x180035ad4  pop     r14
0x180035ad6  pop     r13
0x180035ad8  pop     r12
0x180035ada  pop     rdi
0x180035adb  pop     rsi
0x180035adc  pop     rbp
0x180035add  retn
0x180035ade  mov     r9d, eax; char *
0x180035ae1  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035ae8  mov     edx, 7Eh ; '~'; void *
0x180035aed  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035af3  mov     r9d, eax; char *
0x180035af6  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035afd  mov     edx, 5Dh ; ']'; void *
0x180035b02  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035b08  mov     r9d, eax; char *
0x180035b0b  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035b12  mov     edx, 61h ; 'a'; void *
0x180035b17  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035b1d  mov     r9d, eax; char *
0x180035b20  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035b27  mov     edx, 66h ; 'f'; void *
0x180035b2c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035b32  mov     r9d, eax; char *
0x180035b35  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035b3c  mov     edx, 6Ch ; 'l'; void *
0x180035b41  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035b47  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035b4e  mov     edx, 6Ah ; 'j'; void *
0x180035b53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035b59  mov     r9d, eax; char *
0x180035b5c  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035b63  mov     edx, 75h ; 'u'; void *
0x180035b68  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035b6e  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035b75  mov     edx, 79h ; 'y'; void *
0x180035b7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035b80  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035b87  mov     edx, 7Bh ; '{'; void *
0x180035b8c  mov     rcx, r10; this
0x180035b8f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035b95  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035b9c  mov     edx, 7Ch ; '|'; void *
0x180035ba1  mov     rcx, r10; this
0x180035ba4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
