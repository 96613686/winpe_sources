# ProvSource::GetUserPackageTempDir(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180041e04`
- end: `0x180042016`
- name: `?GetUserPackageTempDir@ProvSource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `530`
- prototype: `_QWORD *__fastcall(_QWORD *, PCWSTR pszMore)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800318a4`

## callees

- `0x18000109c`
- `0x180001168`
- `0x1800011ac`
- `0x1800018ec`
- `0x180002e1c`
- `0x1800071a4`
- `0x18000b030`
- `0x180021cf4`
- `0x18004192c`
- `0x180041e04`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180041e6c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180041e6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041ef4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041f17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041ef4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041f17`
- `ext-ms-win-provisioning-platform-l1-1-0!GetProvisioningTargetUser` at `0x180041e3c`
- `ext-ms-win-provisioning-platform-l1-1-0!GetProvisioningTargetUser` at `0x180041e3c`
- `DMCmnUtils!DmImpersonate` at `0x180041e4e`
- `DMCmnUtils!DmImpersonate` at `0x180041e4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall ProvSource::GetUserPackageTempDir(_QWORD *a1, PCWSTR pszMore)
{
  int v4; // esi
  int v5; // ebx
  __int64 v6; // r9
  char *v7; // rbx
  unsigned __int64 v8; // r8
  int PackageTempDirInternal; // eax
  __int64 v11; // r9
  unsigned __int64 v12; // r8
  unsigned int v13; // eax
  int v14; // [rsp+20h] [rbp-20h]
  __int64 *v15; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HLOCAL hMem; // [rsp+80h] [rbp+40h] BYREF
  HLOCAL Src; // [rsp+88h] [rbp+48h] BYREF

  Src = 0;
  if ( !(unsigned __int8)IsGetProvisioningTargetUserPresent() )
  {
    if ( (unsigned int)dword_18005A000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_18005A000,
        (__int64)byte_180050A1D,
        0,
        0);
    v13 = wil::verify_hresult<long>(0x80004002);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v13,
      v14);
  }
  v4 = 0;
  hMem = 0;
  if ( (int)GetProvisioningTargetUser(&hMem) < 0
    || (v4 = DmImpersonate((const unsigned __int16 *)hMem), v4 < 0)
    || (v5 = GetPackageTempDirInternal(pszMore, &Src), RevertToSelf(), v5 < 0) )
  {
    if ( hMem )
      LocalFree(hMem);
    PackageTempDirInternal = GetPackageTempDirInternal(pszMore, &Src);
    if ( PackageTempDirInternal < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
        (const char *)(unsigned int)PackageTempDirInternal,
        v14);
    v7 = (char *)Src;
    if ( (unsigned int)dword_18005A000 > 4 )
    {
      LODWORD(hMem) = v4;
      v15 = (__int64 *)Src;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)&dword_18005A000,
        (__int64)&dword_1800509AC,
        0,
        v11,
        &v15,
        (__int64)&hMem);
    }
    a1[3] = 7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    if ( *(_WORD *)v7 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)&v7[2 * v12] );
    }
    else
    {
      v12 = 0;
    }
    std::wstring::assign(a1, v7, v12);
  }
  else
  {
    v7 = (char *)Src;
    if ( (unsigned int)dword_18005A000 > 4 )
    {
      v15 = (__int64 *)Src;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)&dword_18005A000,
        (__int64)&byte_1800509E7,
        0,
        v6,
        &v15);
    }
    a1[3] = 7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    if ( *(_WORD *)v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&v7[2 * v8] );
    }
    else
    {
      v8 = 0;
    }
    std::wstring::assign(a1, v7, v8);
    if ( hMem )
      LocalFree(hMem);
  }
  LocalFree(v7);
  return a1;
}

```

## disassembly

```asm
0x180041e04  mov     [rsp-28h+arg_0], rbx
0x180041e09  push    rbp
0x180041e0a  push    rsi
0x180041e0b  push    rdi
0x180041e0c  push    r14
0x180041e0e  push    r15
0x180041e10  mov     rbp, rsp
0x180041e13  sub     rsp, 40h
0x180041e17  mov     r14, rdx
0x180041e1a  mov     rdi, rcx
0x180041e1d  xor     r15d, r15d
0x180041e20  mov     [rbp+Src], r15
0x180041e24  call    IsGetProvisioningTargetUserPresent
0x180041e29  test    al, al
0x180041e2b  jz      loc_180041FBD
0x180041e31  mov     esi, r15d
0x180041e34  mov     [rbp+hMem], r15
0x180041e38  lea     rcx, [rbp+hMem]
0x180041e3c  call    cs:__imp_GetProvisioningTargetUser
0x180041e42  test    eax, eax
0x180041e44  js      loc_180041F0E
0x180041e4a  mov     rcx, [rbp+hMem]
0x180041e4e  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180041e54  mov     esi, eax
0x180041e56  test    eax, eax
0x180041e58  js      loc_180041F0E
0x180041e5e  lea     rdx, [rbp+Src]
0x180041e62  mov     rcx, r14; pszMore
0x180041e65  call    ?GetPackageTempDirInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetPackageTempDirInternal(std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180041e6a  mov     ebx, eax
0x180041e6c  call    cs:__imp_RevertToSelf
0x180041e72  test    ebx, ebx
0x180041e74  js      loc_180041F0E
0x180041e7a  mov     eax, cs:dword_18005A000
0x180041e80  mov     rbx, [rbp+Src]
0x180041e84  cmp     eax, 4
0x180041e87  jbe     short loc_180041EAC
0x180041e89  mov     [rbp+var_8], rbx
0x180041e8d  lea     rax, [rbp+var_8]
0x180041e91  mov     [rsp+40h+var_20], rax
0x180041e96  xor     r8d, r8d
0x180041e99  lea     rdx, byte_1800509E7
0x180041ea0  lea     rcx, dword_18005A000
0x180041ea7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180041eac  mov     qword ptr [rdi+18h], 7
0x180041eb4  mov     [rdi+10h], r15
0x180041eb8  mov     [rdi], r15w
0x180041ebc  cmp     [rbx], r15w
0x180041ec0  jnz     short loc_180041EC7
0x180041ec2  mov     r8, r15
0x180041ec5  jmp     short loc_180041ED5
0x180041ec7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180041ecb  inc     r8
0x180041ece  cmp     [rbx+r8*2], r15w
0x180041ed3  jnz     short loc_180041ECB
0x180041ed5  mov     rdx, rbx; Src
0x180041ed8  mov     rcx, rdi; void *
0x180041edb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180041ee0  nop
0x180041ee1  mov     rcx, [rbp+hMem]; hMem
0x180041ee5  test    rcx, rcx
0x180041ee8  jz      short loc_180041EF1
0x180041eea  call    cs:__imp_LocalFree
0x180041ef0  nop
0x180041ef1  mov     rcx, rbx; hMem
0x180041ef4  call    cs:__imp_LocalFree
0x180041efa  mov     rax, rdi
0x180041efd  mov     rbx, [rsp+40h+arg_0]
0x180041f02  add     rsp, 40h
0x180041f06  pop     r15
0x180041f08  pop     r14
0x180041f0a  pop     rdi
0x180041f0b  pop     rsi
0x180041f0c  pop     rbp
0x180041f0d  retn
0x180041f0e  mov     rcx, [rbp+hMem]; hMem
0x180041f12  test    rcx, rcx
0x180041f15  jz      short loc_180041F1D
0x180041f17  call    cs:__imp_LocalFree
0x180041f1d  lea     rdx, [rbp+Src]
0x180041f21  mov     rcx, r14; pszMore
0x180041f24  call    ?GetPackageTempDirInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetPackageTempDirInternal(std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180041f29  mov     rcx, [rbp+28h]; this
0x180041f2d  test    eax, eax
0x180041f2f  js      short loc_180041FA8
0x180041f31  mov     eax, cs:dword_18005A000
0x180041f37  mov     rbx, [rbp+Src]
0x180041f3b  cmp     eax, 4
0x180041f3e  jbe     short loc_180041F6F
0x180041f40  mov     dword ptr [rbp+hMem], esi
0x180041f43  mov     [rbp+var_8], rbx
0x180041f47  lea     rax, [rbp+hMem]
0x180041f4b  mov     [rsp+40h+var_18], rax
0x180041f50  lea     rax, [rbp+var_8]
0x180041f54  mov     [rsp+40h+var_20], rax
0x180041f59  xor     r8d, r8d
0x180041f5c  lea     rdx, dword_1800509AC
0x180041f63  lea     rcx, dword_18005A000
0x180041f6a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180041f6f  mov     qword ptr [rdi+18h], 7
0x180041f77  mov     [rdi+10h], r15
0x180041f7b  mov     [rdi], r15w
0x180041f7f  cmp     [rbx], r15w
0x180041f83  jnz     short loc_180041F8A
0x180041f85  mov     r8, r15
0x180041f88  jmp     short loc_180041F98
0x180041f8a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180041f8e  inc     r8
0x180041f91  cmp     [rbx+r8*2], r15w
0x180041f96  jnz     short loc_180041F8E
0x180041f98  mov     rdx, rbx; Src
0x180041f9b  mov     rcx, rdi; void *
0x180041f9e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180041fa3  jmp     loc_180041EF1
0x180041fa8  mov     r9d, eax; char *
0x180041fab  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180041fb2  mov     edx, 4Dh ; 'M'; void *
0x180041fb7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041fbd  mov     eax, cs:dword_18005A000
0x180041fc3  cmp     eax, 4
0x180041fc6  jbe     short loc_180041FF3
0x180041fc8  xor     edx, edx
0x180041fca  lea     rcx, dword_18005A000
0x180041fd1  call    _tlgKeywordOn
0x180041fd6  test    al, al
0x180041fd8  jz      short loc_180041FF3
0x180041fda  xor     r9d, r9d
0x180041fdd  xor     r8d, r8d
0x180041fe0  lea     rdx, byte_180050A1D
0x180041fe7  lea     rcx, dword_18005A000
0x180041fee  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180041ff3  mov     ecx, 80004002h
0x180041ff8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180041ffd  mov     r9d, eax; char *
0x180042000  mov     rcx, [rbp+28h]; this
0x180042004  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18004200b  mov     edx, 4Ah ; 'J'; void *
0x180042010  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
