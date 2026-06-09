# IsAccessAllowedByEnterpriseDataPolicy(_EFS_DATA_STREAM_HEADER *,uchar *)

- ea: `0x18000e884`
- end: `0x18000eb0e`
- name: `?IsAccessAllowedByEnterpriseDataPolicy@@YAJPEAU_EFS_DATA_STREAM_HEADER@@PEAE@Z`
- size: `650`
- prototype: `__int64 __fastcall(struct _EFS_DATA_STREAM_HEADER *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18000e0fc`

## callees

- `0x1800012b8`
- `0x180001a7c`
- `0x18000dc8c`
- `0x18000e884`
- `0x18000f13c`
- `0x180017570`
- `0x1800470f0`
- `0x1800719b4`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000ea1a`
- `msvcrt!wcsrchr` at `0x18000ea1a`
- `msvcrt!_wcslwr` at `0x18000e987`
- `msvcrt!_wcslwr` at `0x18000e987`
- `msvcrt!wcsstr` at `0x18000e997`
- `msvcrt!wcsstr` at `0x18000ea03`
- `msvcrt!wcsstr` at `0x18000e997`
- `msvcrt!wcsstr` at `0x18000ea03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e9a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e9a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eaeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eaeb`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000e9c5`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000e9c5`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsFileAccessAllowed` at `0x18000e926`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsFileAccessAllowed` at `0x18000e926`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsAccessAllowedByEnterpriseDataPolicy(struct _EFS_DATA_STREAM_HEADER *a1, unsigned __int8 *a2)
{
  unsigned __int8 *v2; // r12
  unsigned int v3; // esi
  signed int IsFileAccessAllowed; // eax
  bool v5; // cc
  wchar_t *v6; // r14
  wchar_t *v7; // rbx
  __int64 v8; // rdx
  wchar_t **AppUniqueId; // r15
  wchar_t *v10; // rax
  __int64 v11; // rdx
  wchar_t *v12; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const wchar_t *v16; // rax
  unsigned int v18; // [rsp+40h] [rbp-78h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-74h] BYREF
  wchar_t *v20; // [rsp+48h] [rbp-70h] BYREF
  HLOCAL v21; // [rsp+50h] [rbp-68h] BYREF
  const wchar_t *v22; // [rsp+58h] [rbp-60h] BYREF
  __int128 v23; // [rsp+60h] [rbp-58h] BYREF
  HLOCAL v24[9]; // [rsp+70h] [rbp-48h] BYREF
  char v25; // [rsp+C0h] [rbp+8h] BYREF
  unsigned __int8 *v26; // [rsp+C8h] [rbp+10h]
  char v27; // [rsp+D0h] [rbp+18h] BYREF
  unsigned int v28; // [rsp+D8h] [rbp+20h]

  v26 = a2;
  v2 = a2;
  v3 = 0;
  v28 = 0;
  v18 = 0;
  v21 = 0;
  v25 = 0;
  v23 = 0;
  memset(v24, 0, 24);
  if ( (unsigned int)(*((_DWORD *)a1 + 2) - 5) > 1 )
  {
    v25 = 1;
    goto LABEL_29;
  }
  IsFileAccessAllowed = QueryProtectorsSrv(a1, &v18, &v21);
  try
  {
    v5 = IsFileAccessAllowed <= 0;
    if ( IsFileAccessAllowed
      || (LODWORD(v23) = v18,
          *((_QWORD *)&v23 + 1) = v21,
          IsFileAccessAllowed = EdpIsFileAccessAllowed(&v23, 0, &v25),
          v5 = IsFileAccessAllowed <= 0,
          IsFileAccessAllowed) )
    {
      if ( v5 )
      {
        v3 = IsFileAccessAllowed;
        v28 = IsFileAccessAllowed;
      }
      else
      {
        v3 = (unsigned __int16)IsFileAccessAllowed | 0xC0070000;
        v28 = v3;
      }
      goto LABEL_9;
    }
    if ( !v25 )
    {
LABEL_9:
      v6 = 0;
      v7 = 0;
      v20 = 0;
      AppUniqueId = (wchar_t **)FetchAppUniqueId(&v27);
      if ( &v20 != AppUniqueId )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v20,
          *AppUniqueId);
        *AppUniqueId = 0;
        v7 = v20;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
        &v27,
        v8);
      v10 = _wcslwr(v7);
      if ( wcsstr(v10, L"svchost.exe") )
      {
        LODWORD(v24[0]) = GetCurrentProcessId();
        HIDWORD(v24[0]) = NtCurrentTeb()->SubProcessTag;
        if ( !(unsigned int)I_QueryTagInformation(0, 1, v24) && v24[2] )
          v6 = (wchar_t *)v24[2];
      }
      else if ( wcsstr(v7, L":\\") && (v12 = wcsrchr(v7, 0x5Cu)) != 0 && *v12 == 92 )
      {
        v6 = v12 + 1;
      }
      else
      {
        v6 = v7;
      }
      if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
      {
        v19 = v3;
        v16 = L"NA";
        if ( v6 )
          v16 = v6;
        v22 = v16;
        v27 = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v13,
          (unsigned int)byte_180101C91,
          v14,
          v15,
          (__int64)&v27,
          (__int64)&v22,
          (__int64)&v19);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
        &v20,
        v11);
    }
  }
  catch ( ... )
  {
    v2 = v26;
    v3 = v28;
  }
  if ( v21 )
    EfspFreeProtectorList(v21, v18);
LABEL_29:
  if ( v24[2] )
    LocalFree(v24[2]);
  *v2 = v25;
  return v3;
}

```

## disassembly

```asm
0x18000e884  mov     r11, rsp
0x18000e887  mov     [r11+10h], rdx
0x18000e88b  push    rbx
0x18000e88c  push    rsi
0x18000e88d  push    r12
0x18000e88f  push    r14
0x18000e891  push    r15
0x18000e893  sub     rsp, 90h
0x18000e89a  mov     r12, rdx
0x18000e89d  xor     esi, esi
0x18000e89f  mov     [rsp+0B8h+arg_18], esi
0x18000e8a6  mov     [rsp+0B8h+var_78], esi
0x18000e8aa  mov     [r11-68h], rsi
0x18000e8ae  mov     [r11+8], sil
0x18000e8b2  xorps   xmm0, xmm0
0x18000e8b5  movups  [rsp+0B8h+var_58], xmm0
0x18000e8ba  mov     [rsp+0B8h+var_48], esi
0x18000e8be  xorps   xmm1, xmm1
0x18000e8c1  xor     eax, eax
0x18000e8c3  movups  xmmword ptr [rsp+0B8h+hMem], xmm1
0x18000e8c8  mov     [r11-34h], eax
0x18000e8cc  mov     eax, [rcx+8]
0x18000e8cf  sub     eax, 5
0x18000e8d2  cmp     eax, 1
0x18000e8d5  jbe     short loc_18000E8E1
0x18000e8d7  mov     byte ptr [r11+8], 1
0x18000e8dc  jmp     loc_18000EADE
0x18000e8e1  lea     r8, [rsp+0B8h+var_68]
0x18000e8e6  lea     rdx, [rsp+0B8h+var_78]
0x18000e8eb  call    QueryProtectorsSrv
0x18000e8f0  test    eax, eax
0x18000e8f2  jz      short loc_18000E905
0x18000e8f4  jg      loc_18000E9E4
0x18000e8fa  mov     esi, eax
0x18000e8fc  mov     [rsp+0B8h+arg_18], eax
0x18000e903  jmp     short loc_18000E93E
0x18000e905  mov     eax, [rsp+0B8h+var_78]
0x18000e909  mov     dword ptr [rsp+0B8h+var_58], eax
0x18000e90d  mov     rax, [rsp+0B8h+var_68]
0x18000e912  mov     qword ptr [rsp+0B8h+var_58+8], rax
0x18000e917  lea     r8, [rsp+0B8h+arg_0]
0x18000e91f  xor     edx, edx
0x18000e921  lea     rcx, [rsp+0B8h+var_58]
0x18000e926  call    cs:__imp_EdpIsFileAccessAllowed
0x18000e92c  test    eax, eax
0x18000e92e  jnz     short loc_18000E8F4
0x18000e930  cmp     [rsp+0B8h+arg_0], sil
0x18000e938  jnz     loc_18000EACB
0x18000e93e  xor     r14d, r14d
0x18000e941  xor     ebx, ebx
0x18000e943  mov     [rsp+0B8h+var_70], rbx
0x18000e948  lea     rcx, [rsp+0B8h+arg_10]
0x18000e950  call    ?FetchAppUniqueId@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@Z; FetchAppUniqueId(void *)
0x18000e955  mov     r15, rax
0x18000e958  lea     rax, [rsp+0B8h+var_70]
0x18000e95d  cmp     rax, r15
0x18000e960  jz      short loc_18000E977
0x18000e962  mov     rdx, [r15]
0x18000e965  lea     rcx, [rsp+0B8h+var_70]
0x18000e96a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000e96f  mov     [r15], rbx
0x18000e972  mov     rbx, [rsp+0B8h+var_70]
0x18000e977  lea     rcx, [rsp+0B8h+arg_10]
0x18000e97f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000e984  mov     rcx, rbx; String
0x18000e987  call    cs:__imp__wcslwr
0x18000e98d  mov     rcx, rax; Str
0x18000e990  lea     rdx, aSvchostExe; "svchost.exe"
0x18000e997  call    cs:__imp_wcsstr
0x18000e99d  test    rax, rax
0x18000e9a0  jz      short loc_18000E9F9
0x18000e9a2  call    cs:__imp_GetCurrentProcessId
0x18000e9a8  mov     [rsp+0B8h+var_48], eax
0x18000e9ac  mov     rax, gs:1720h
0x18000e9b5  mov     dword ptr [rsp+0B8h+hMem], eax
0x18000e9b9  lea     r8, [rsp+0B8h+var_48]
0x18000e9be  mov     edx, 1
0x18000e9c3  xor     ecx, ecx
0x18000e9c5  call    cs:__imp_I_QueryTagInformation
0x18000e9cb  test    eax, eax
0x18000e9cd  jnz     short loc_18000EA37
0x18000e9cf  cmp     qword ptr [rsp+0B8h+hMem+0Ch], 0
0x18000e9d8  jz      short loc_18000EA37
0x18000e9da  mov     r14, qword ptr [rsp+0B8h+hMem+0Ch]
0x18000e9e2  jmp     short loc_18000EA37
0x18000e9e4  movzx   esi, ax
0x18000e9e7  or      esi, 0C0070000h
0x18000e9ed  mov     [rsp+0B8h+arg_18], esi
0x18000e9f4  jmp     loc_18000E93E
0x18000e9f9  lea     rdx, asc_1800F0900; ":\\"
0x18000ea00  mov     rcx, rbx; Str
0x18000ea03  call    cs:__imp_wcsstr
0x18000ea09  test    rax, rax
0x18000ea0c  jz      short loc_18000EA34
0x18000ea0e  mov     r15d, 5Ch ; '\'
0x18000ea14  mov     edx, r15d; Ch
0x18000ea17  mov     rcx, rbx; Str
0x18000ea1a  call    cs:__imp_wcsrchr
0x18000ea20  mov     r14, rax
0x18000ea23  test    rax, rax
0x18000ea26  jz      short loc_18000EA34
0x18000ea28  cmp     [rax], r15w
0x18000ea2c  jnz     short loc_18000EA34
0x18000ea2e  add     r14, 2
0x18000ea32  jmp     short loc_18000EA37
0x18000ea34  mov     r14, rbx
0x18000ea37  mov     eax, cs:dword_180114250
0x18000ea3d  cmp     eax, 5
0x18000ea40  jbe     short loc_18000EAAF
0x18000ea42  mov     rdx, 400000000000h
0x18000ea4c  lea     rcx, dword_180114250
0x18000ea53  call    _tlgKeywordOn
0x18000ea58  test    al, al
0x18000ea5a  jz      short loc_18000EAAF
0x18000ea5c  mov     [rsp+0B8h+var_74], esi
0x18000ea60  lea     rax, aNa; "NA"
0x18000ea67  test    r14, r14
0x18000ea6a  cmovnz  rax, r14
0x18000ea6e  mov     [rsp+0B8h+var_60], rax
0x18000ea73  mov     al, [rsp+0B8h+arg_0]
0x18000ea7a  mov     [rsp+0B8h+arg_10], al
0x18000ea81  lea     rax, [rsp+0B8h+var_74]
0x18000ea86  mov     [rsp+0B8h+var_88], rax
0x18000ea8b  lea     rax, [rsp+0B8h+var_60]
0x18000ea90  mov     [rsp+0B8h+var_90], rax
0x18000ea95  lea     rax, [rsp+0B8h+arg_10]
0x18000ea9d  mov     [rsp+0B8h+var_98], rax
0x18000eaa2  lea     rdx, byte_180101C91
0x18000eaa9  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000eaae  nop
0x18000eaaf  lea     rcx, [rsp+0B8h+var_70]
0x18000eab4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000eab9  nop
0x18000eaba  jmp     short loc_18000EACB
0x18000eabc  mov     r12, [rsp+0B8h+arg_8]
0x18000eac4  mov     esi, [rsp+0B8h+arg_18]
0x18000eacb  mov     rcx, [rsp+0B8h+var_68]; hMem
0x18000ead0  test    rcx, rcx
0x18000ead3  jz      short loc_18000EADE
0x18000ead5  mov     edx, [rsp+0B8h+var_78]; unsigned int
0x18000ead9  call    ?EfspFreeProtectorList@@YAXPEAPEAU_ENCRYPTION_PROTECTOR@@K@Z; EfspFreeProtectorList(_ENCRYPTION_PROTECTOR * *,ulong)
0x18000eade  mov     rcx, qword ptr [rsp+0B8h+hMem+0Ch]; hMem
0x18000eae6  test    rcx, rcx
0x18000eae9  jz      short loc_18000EAF1
0x18000eaeb  call    cs:__imp_LocalFree
0x18000eaf1  mov     cl, [rsp+0B8h+arg_0]
0x18000eaf8  mov     [r12], cl
0x18000eafc  mov     eax, esi
0x18000eafe  add     rsp, 90h
0x18000eb05  pop     r15
0x18000eb07  pop     r14
0x18000eb09  pop     r12
0x18000eb0b  pop     rsi
0x18000eb0c  pop     rbx
0x18000eb0d  retn
```
