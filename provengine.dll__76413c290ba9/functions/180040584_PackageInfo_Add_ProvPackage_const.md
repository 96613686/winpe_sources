# PackageInfo::Add(ProvPackage const &)

- ea: `0x180040584`
- end: `0x1800408c0`
- name: `?Add@PackageInfo@@QEAAXAEBVProvPackage@@@Z`
- size: `828`
- prototype: `void __fastcall(HKEY *this, const struct ProvPackage *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180014cf8`

## callees

- `0x180001a14`
- `0x180021cf4`
- `0x18002f9bc`
- `0x180040514`
- `0x180040584`
- `0x180040cb0`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800405dd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040611`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800406b0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040709`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040767`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800407ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040813`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800405dd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040611`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800406b0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040709`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040767`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800407ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040813`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004074a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004074a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040823`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040823`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040693`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040693`

## pseudocode

```c
void __fastcall PackageInfo::Add(HKEY *this, const struct ProvPackage *a2)
{
  __int64 v4; // rax
  unsigned int v5; // eax
  unsigned __int64 v6; // rax
  __int64 v7; // r8
  DWORD v8; // edi
  const char *v9; // r9
  __int64 v10; // rax
  unsigned int v11; // eax
  __int64 *v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int dwOptions; // [rsp+20h] [rbp-59h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-59h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-59h]
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v21; // [rsp+58h] [rbp-21h] BYREF
  __int64 *v22; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v23[2]; // [rsp+68h] [rbp-11h] BYREF
  char v24; // [rsp+78h] [rbp-1h]
  void *v25[3]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 v26; // [rsp+98h] [rbp+1Fh]
  void *v27[4]; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( !*(_QWORD *)((*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)a2 + 16LL))(a2, v25) + 16) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
      (const char *)0x80070057LL,
      dwOptions);
  if ( v26 >= 8 )
    operator delete(v25[0]);
  if ( !*(_QWORD *)((*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)a2 + 24LL))(a2, v25) + 16) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
      (const char *)0x80070057LL,
      dwOptions);
  if ( v26 >= 8 )
    operator delete(v25[0]);
  if ( !PackageInfo::isAdded((PackageInfo *)this, a2) )
  {
    v23[0] = this;
    v23[1] = a2;
    v24 = 1;
    hKey = 0;
    v4 = (*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)a2 + 16LL))(a2, v25);
    if ( *(_QWORD *)(v4 + 24) >= 8u )
      v4 = *(_QWORD *)v4;
    v5 = RegCreateKeyExW(*this, (LPCWSTR)v4, 0, 0, 0, 3u, 0, &hKey, 0);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2A,
        (int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
        (const char *)v5,
        dwOptionsa);
    if ( v26 >= 8 )
      operator delete(v25[0]);
    v6 = 2LL
       * *(_QWORD *)((*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)a2 + 24LL))(a2, v25)
                   + 16)
       + 2;
    v8 = v6;
    if ( v6 > 0xFFFFFFFF )
      v8 = -1;
    v9 = v6 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
    if ( v6 > 0xFFFFFFFF )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2D,
        (int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
        v9,
        dwOptionsa);
    if ( v26 >= 8 )
      operator delete(v25[0]);
    v10 = (*(__int64 (__fastcall **)(const struct ProvPackage *, void **, __int64, const char *))(*(_QWORD *)a2 + 24LL))(
            a2,
            v25,
            v7,
            v9);
    if ( *(_QWORD *)(v10 + 24) >= 8u )
      v10 = *(_QWORD *)v10;
    v11 = RegSetValueExW(hKey, L"PackageVersion", 0, 1u, (const BYTE *)v10, v8);
    if ( v11 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x30,
        (int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
        (const char *)v11,
        dwOptionsb);
    if ( v26 >= 8 )
      operator delete(v25[0]);
    v24 = 0;
    if ( (unsigned int)dword_18005A000 > 5 )
    {
      v12 = (__int64 *)(*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)a2 + 24LL))(a2, v27);
      if ( (unsigned __int64)v12[3] >= 8 )
        v12 = (__int64 *)*v12;
      v21 = v12;
      v13 = (__int64 *)(*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)a2 + 16LL))(a2, v25);
      if ( (unsigned __int64)v13[3] >= 8 )
        v13 = (__int64 *)*v13;
      v22 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v14,
        (__int64)byte_1800506EB,
        v15,
        v16,
        &v22,
        &v21);
      if ( v26 >= 8 )
        operator delete(v25[0]);
      v26 = 7;
      v25[2] = 0;
      LOWORD(v25[0]) = 0;
      if ( v27[3] >= (void *)8 )
        operator delete(v27[0]);
    }
    if ( hKey )
      RegCloseKey(hKey);
    wil::details::ScopeExitFn__lambda_3656d47d6282d429a3b12873ed01b4c6___::_ScopeExitFn__lambda_3656d47d6282d429a3b12873ed01b4c6___(v23);
  }
}

```

## disassembly

```asm
0x180040584  mov     [rsp-8+arg_10], rbx
0x180040589  mov     [rsp-8+arg_18], rdi
0x18004058e  push    rbp
0x18004058f  lea     rbp, [rsp-57h]
0x180040594  sub     rsp, 0D0h
0x18004059b  mov     rax, cs:__security_cookie
0x1800405a2  xor     rax, rsp
0x1800405a5  mov     [rbp+57h+var_10], rax
0x1800405a9  mov     rbx, rdx
0x1800405ac  mov     rdi, rcx
0x1800405af  mov     rax, [rdx]
0x1800405b2  lea     rdx, [rbp+57h+var_50]
0x1800405b6  mov     rcx, rbx
0x1800405b9  mov     rax, [rax+10h]
0x1800405bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405c2  nop
0x1800405c3  mov     rcx, [rbp+5Fh]; this
0x1800405c7  cmp     qword ptr [rax+10h], 0
0x1800405cc  jz      loc_180040869
0x1800405d2  cmp     [rbp+57h+var_38], 8
0x1800405d7  jb      short loc_1800405E3
0x1800405d9  mov     rcx, [rbp+57h+var_50]
0x1800405dd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800405e3  mov     rax, [rbx]
0x1800405e6  lea     rdx, [rbp+57h+var_50]
0x1800405ea  mov     rcx, rbx
0x1800405ed  mov     rax, [rax+18h]
0x1800405f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405f6  nop
0x1800405f7  mov     rcx, [rbp+5Fh]; this
0x1800405fb  cmp     qword ptr [rax+10h], 0
0x180040600  jz      loc_180040881
0x180040606  cmp     [rbp+57h+var_38], 8
0x18004060b  jb      short loc_180040617
0x18004060d  mov     rcx, [rbp+57h+var_50]
0x180040611  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180040617  mov     rdx, rbx; struct ProvPackage *
0x18004061a  mov     rcx, rdi; this
0x18004061d  call    ?isAdded@PackageInfo@@QEAA_NAEBVProvPackage@@@Z; PackageInfo::isAdded(ProvPackage const &)
0x180040622  test    al, al
0x180040624  jnz     loc_180040833
0x18004062a  mov     [rbp+57h+var_68], rdi
0x18004062e  mov     [rbp+57h+var_60], rbx
0x180040632  mov     [rbp+57h+var_58], 1
0x180040636  mov     [rbp+57h+hKey], 0
0x18004063e  mov     rax, [rbx]
0x180040641  lea     rdx, [rbp+57h+var_50]
0x180040645  mov     rcx, rbx
0x180040648  mov     rax, [rax+10h]
0x18004064c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040651  nop
0x180040652  cmp     qword ptr [rax+18h], 8
0x180040657  jb      short loc_18004065C
0x180040659  mov     rax, [rax]
0x18004065c  mov     [rsp+0D0h+lpdwDisposition], 0; lpdwDisposition
0x180040665  lea     rcx, [rbp+57h+hKey]
0x180040669  mov     [rsp+0D0h+phkResult], rcx; phkResult
0x18004066e  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180040677  mov     [rsp+0D0h+samDesired], 3; samDesired
0x18004067f  mov     [rsp+0D0h+dwOptions], 0; unsigned int
0x180040687  xor     r9d, r9d; lpClass
0x18004068a  xor     r8d, r8d; Reserved
0x18004068d  mov     rdx, rax; lpSubKey
0x180040690  mov     rcx, [rdi]; hKey
0x180040693  call    cs:__imp_RegCreateKeyExW
0x180040699  mov     rcx, [rbp+5Fh]; this
0x18004069d  test    eax, eax
0x18004069f  jnz     loc_180040899
0x1800406a5  cmp     [rbp+57h+var_38], 8
0x1800406aa  jb      short loc_1800406B6
0x1800406ac  mov     rcx, [rbp+57h+var_50]
0x1800406b0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800406b6  mov     rax, [rbx]
0x1800406b9  lea     rdx, [rbp+57h+var_50]
0x1800406bd  mov     rcx, rbx
0x1800406c0  mov     rax, [rax+18h]
0x1800406c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406c9  nop
0x1800406ca  mov     rax, [rax+10h]
0x1800406ce  lea     rax, ds:2[rax*2]
0x1800406d6  mov     edx, 0FFFFFFFFh
0x1800406db  cmp     rax, rdx
0x1800406de  mov     edi, eax
0x1800406e0  jbe     short loc_1800406E4
0x1800406e2  mov     edi, edx
0x1800406e4  cmp     rdx, rax
0x1800406e7  sbb     r9d, r9d
0x1800406ea  and     r9d, 80070216h; char *
0x1800406f1  mov     rcx, [rbp+5Fh]; this
0x1800406f5  cmp     rax, rdx
0x1800406f8  ja      loc_1800408AE
0x1800406fe  cmp     [rbp+57h+var_38], 8
0x180040703  jb      short loc_18004070F
0x180040705  mov     rcx, [rbp+57h+var_50]
0x180040709  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004070f  mov     rax, [rbx]
0x180040712  lea     rdx, [rbp+57h+var_50]
0x180040716  mov     rcx, rbx
0x180040719  mov     rax, [rax+18h]
0x18004071d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040722  nop
0x180040723  cmp     qword ptr [rax+18h], 8
0x180040728  jb      short loc_18004072D
0x18004072a  mov     rax, [rax]
0x18004072d  mov     [rsp+0D0h+samDesired], edi; cbData
0x180040731  mov     qword ptr [rsp+0D0h+dwOptions], rax; unsigned int
0x180040736  mov     r9d, 1; dwType
0x18004073c  xor     r8d, r8d; Reserved
0x18004073f  lea     rdx, aPackageversion; "PackageVersion"
0x180040746  mov     rcx, [rbp+57h+hKey]; hKey
0x18004074a  call    cs:__imp_RegSetValueExW
0x180040750  mov     rcx, [rbp+5Fh]; this
0x180040754  test    eax, eax
0x180040756  jnz     loc_180040854
0x18004075c  cmp     [rbp+57h+var_38], 8
0x180040761  jb      short loc_18004076D
0x180040763  mov     rcx, [rbp+57h+var_50]
0x180040767  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004076d  mov     [rbp+57h+var_58], 0
0x180040771  mov     eax, cs:dword_18005A000
0x180040777  cmp     eax, 5
0x18004077a  jbe     loc_18004081A
0x180040780  mov     rax, [rbx]
0x180040783  lea     rdx, [rbp+57h+var_30]
0x180040787  mov     rcx, rbx
0x18004078a  mov     rax, [rax+18h]
0x18004078e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040793  nop
0x180040794  cmp     qword ptr [rax+18h], 8
0x180040799  jb      short loc_18004079E
0x18004079b  mov     rax, [rax]
0x18004079e  mov     [rbp+57h+var_78], rax
0x1800407a2  mov     rax, [rbx]
0x1800407a5  lea     rdx, [rbp+57h+var_50]
0x1800407a9  mov     rcx, rbx
0x1800407ac  mov     rax, [rax+10h]
0x1800407b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407b5  cmp     qword ptr [rax+18h], 8
0x1800407ba  jb      short loc_1800407BF
0x1800407bc  mov     rax, [rax]
0x1800407bf  mov     [rbp+57h+var_70], rax
0x1800407c3  lea     rax, [rbp+57h+var_78]
0x1800407c7  mov     qword ptr [rsp+0D0h+samDesired], rax
0x1800407cc  lea     rax, [rbp+57h+var_70]
0x1800407d0  mov     qword ptr [rsp+0D0h+dwOptions], rax
0x1800407d5  lea     rdx, byte_1800506EB
0x1800407dc  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800407e1  cmp     [rbp+57h+var_38], 8
0x1800407e6  jb      short loc_1800407F2
0x1800407e8  mov     rcx, [rbp+57h+var_50]
0x1800407ec  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800407f2  mov     [rbp+57h+var_38], 7
0x1800407fa  mov     [rbp+57h+var_40], 0
0x180040802  xor     eax, eax
0x180040804  mov     word ptr [rbp+57h+var_50], ax
0x180040808  cmp     [rbp+57h+var_18], 8
0x18004080d  jb      short loc_18004081A
0x18004080f  mov     rcx, [rbp+57h+var_30]
0x180040813  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180040819  nop
0x18004081a  mov     rcx, [rbp+57h+hKey]; hKey
0x18004081e  test    rcx, rcx
0x180040821  jz      short loc_18004082A
0x180040823  call    cs:__imp_RegCloseKey
0x180040829  nop
0x18004082a  lea     rcx, [rbp+57h+var_68]
0x18004082e  call    wil__details__ScopeExitFn__lambda_3656d47d6282d429a3b12873ed01b4c6______ScopeExitFn__lambda_3656d47d6282d429a3b12873ed01b4c6___
0x180040833  mov     rcx, [rbp+57h+var_10]
0x180040837  xor     rcx, rsp; StackCookie
0x18004083a  call    __security_check_cookie
0x18004083f  lea     r11, [rsp+0D0h+var_s0]
0x180040847  mov     rbx, [r11+20h]
0x18004084b  mov     rdi, [r11+28h]
0x18004084f  mov     rsp, r11
0x180040852  pop     rbp
0x180040853  retn
0x180040854  mov     r9d, eax; char *
0x180040857  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x18004085e  mov     edx, 30h ; '0'; void *
0x180040863  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180040869  mov     r9d, 80070057h; char *
0x18004086f  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x180040876  mov     edx, 18h; void *
0x18004087b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040881  mov     r9d, 80070057h; char *
0x180040887  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x18004088e  mov     edx, 19h; void *
0x180040893  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040899  mov     r9d, eax; char *
0x18004089c  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x1800408a3  mov     edx, 2Ah ; '*'; void *
0x1800408a8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800408ae  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x1800408b5  mov     edx, 2Dh ; '-'; void *
0x1800408ba  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
