# _lambda_2231b4a0d8078d5c81bf8fecd1a6e66f_::operator()

- ea: `0x180035688`
- end: `0x180035aa9`
- name: `_lambda_2231b4a0d8078d5c81bf8fecd1a6e66f_::operator()`
- size: `1057`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035120`

## callees

- `0x180006780`
- `0x180008ab4`
- `0x18000edb0`
- `0x1800158e0`
- `0x180016538`
- `0x1800176bc`
- `0x1800201f8`
- `0x1800213c4`
- `0x180021a80`
- `0x180029aec`
- `0x18002d518`
- `0x180035688`
- `0x1800368c8`
- `0x180046ce0`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180035a10`
- `ncrypt!NCryptOpenStorageProvider` at `0x180035a10`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_2231b4a0d8078d5c81bf8fecd1a6e66f_::operator()(int **a1)
{
  int *v2; // rbx
  bool *v3; // rdx
  unsigned __int8 *v4; // rdx
  int *v5; // rbx
  struct NgcPolicy *v6; // r8
  enum PolicyManager::PolicyType *v7; // r9
  int *v8; // rbx
  int v9; // ecx
  int *v10; // rax
  int *v11; // rbx
  int *v12; // rcx
  __int64 result; // rax
  int *v14; // rbx
  unsigned int v15; // ebx
  int *v16; // rbx
  char *v17; // rdx
  _QWORD *v18; // rcx
  int *v19; // rbx
  int v20; // [rsp+30h] [rbp-29h] BYREF
  char v21[4]; // [rsp+34h] [rbp-25h] BYREF
  _DWORD *v22; // [rsp+38h] [rbp-21h] BYREF
  void **v23; // [rsp+40h] [rbp-19h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-11h] BYREF
  _QWORD v25[4]; // [rsp+50h] [rbp-9h] BYREF

  v2 = *a1;
  *v2 = PolicyManager::QueryIsNgcEnabled(
          *(const WCHAR **)a1[1],
          *(unsigned __int16 **)a1[2],
          (unsigned __int16 *)a1[3],
          (enum _NGC_ENABLED_STATE *)a1[4],
          (enum _NGC_POLICY_SOURCE *)a1[5]);
  if ( **a1 >= 0 )
  {
    *(_BYTE *)a1[6] = (*a1[5] & 2) != 0;
    *(_BYTE *)a1[7] = (*a1[5] & 8) != 0;
    if ( *(_BYTE *)a1[8] )
      return (unsigned int)**a1;
    v21[0] = 0;
    v5 = *a1;
    *v5 = NgcUtils::IsCurrentSessionRemote((NgcUtils *)v21, v3);
    if ( **a1 >= 0 )
    {
      if ( v21[0] )
      {
        v10 = a1[9];
LABEL_14:
        *v10 = 0;
        return (unsigned int)**a1;
      }
    }
    else
    {
      if ( (unsigned int)dword_18006E000 > 3 )
      {
        v20 = **a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18006E000,
          (unsigned __int8 *)byte_1800605E7,
          0,
          0,
          (__int64)&v20);
      }
      **a1 = 0;
    }
    v8 = *a1;
    *v8 = PolicyManager::GetManagedPolicy(*(PolicyManager **)a1[1], (const unsigned __int16 *)a1[10], v6, v7);
    v9 = **a1;
    if ( v9 == -2146893807 )
    {
      if ( (unsigned int)dword_18006E000 > 3 )
      {
        v20 = **a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18006E000,
          (unsigned __int8 *)byte_1800605AB,
          0,
          0,
          (__int64)&v20);
      }
      v10 = *a1;
      goto LABEL_14;
    }
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_18006E000 <= 2 )
        return (unsigned int)**a1;
      v20 = **a1;
      v4 = (unsigned __int8 *)&dword_180060574;
      goto LABEL_4;
    }
    if ( a1[10][3] != 1 )
      return (unsigned int)**a1;
    *(_BYTE *)a1[11] = 1;
    *(_BYTE *)a1[12] = 1;
    v11 = *a1;
    *v11 = I_IsNgcContainerHardwareCapable(*(const unsigned __int16 **)a1[1], (bool *)a1[13]);
    v12 = *a1;
    result = (unsigned int)**a1;
    if ( (_DWORD)result == -2146893782 )
    {
      *v12 = 0;
      *(_BYTE *)a1[11] = 0;
    }
    else if ( (int)result < 0 )
    {
      return result;
    }
    v22 = 0;
    v14 = *a1;
    *v14 = DsrGetJoinInfo(v12, &v22);
    if ( **a1 < 0 )
    {
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        v20 = **a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18006E000,
          (unsigned __int8 *)&word_18006054E,
          0,
          0,
          (__int64)&v20);
      }
      goto LABEL_32;
    }
    if ( *(_BYTE *)a1[11] && !*(_BYTE *)a1[13] && (!v22 || *v22 != 1) )
    {
      *a1[9] = 0;
      **a1 = 0;
LABEL_32:
      v15 = **a1;
LABEL_43:
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v22);
      return v15;
    }
    *(_BYTE *)a1[14] = 1;
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v25);
    v16 = *a1;
    *v16 = PolicyManager::GetProviderName(a1[10], 1, v25);
    if ( **a1 >= 0 )
    {
      v18 = v25;
      if ( v25[3] > 7u )
        v18 = (_QWORD *)v25[0];
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                              v18,
                              v25[2],
                              L"Microsoft Platform Crypto Provider",
                              34) )
      {
        *(_BYTE *)a1[14] = 0;
        v23 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
        phProvider = 0;
        Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v23);
        v19 = *a1;
        *v19 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
        if ( **a1 >= 0 )
        {
          *(_BYTE *)a1[15] = 1;
        }
        else
        {
          if ( (unsigned int)dword_18006E000 > 3 )
          {
            v20 = **a1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_18006E000,
              (unsigned __int8 *)byte_1800604B9,
              0,
              0,
              (__int64)&v20);
          }
          **a1 = 0;
          *a1[9] = 0;
        }
        v23 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v23);
        std::wstring::~wstring(v25);
        wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v22);
        return (unsigned int)**a1;
      }
      if ( (unsigned int)dword_18006E000 <= 3 )
        goto LABEL_42;
      v17 = byte_1800604F1;
    }
    else
    {
      if ( (unsigned int)dword_18006E000 <= 3 )
      {
LABEL_42:
        **a1 = 0;
        *a1[9] = 0;
        v15 = **a1;
        std::wstring::~wstring(v25);
        goto LABEL_43;
      }
      v17 = byte_180060521;
    }
    v20 = **a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18006E000,
      (unsigned __int8 *)v17,
      0,
      0,
      (__int64)&v20);
    goto LABEL_42;
  }
  if ( (unsigned int)dword_18006E000 > 2 )
  {
    v20 = **a1;
    v4 = (unsigned __int8 *)byte_180060623;
LABEL_4:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18006E000,
      v4,
      0,
      0,
      (__int64)&v20);
  }
  return (unsigned int)**a1;
}

```

## disassembly

```asm
0x180035688  push    rbp
0x18003568a  push    rbx
0x18003568b  push    rsi
0x18003568c  push    rdi
0x18003568d  push    r12
0x18003568f  push    r14
0x180035691  lea     rbp, [rsp-2Fh]
0x180035696  sub     rsp, 88h
0x18003569d  mov     rax, cs:__security_cookie
0x1800356a4  xor     rax, rsp
0x1800356a7  mov     [rbp+57h+var_40], rax
0x1800356ab  mov     rdi, rcx
0x1800356ae  mov     rbx, [rcx]
0x1800356b1  mov     rdx, [rcx+10h]
0x1800356b5  mov     rcx, [rcx+8]
0x1800356b9  mov     rax, [rdi+28h]
0x1800356bd  mov     [rsp+0B0h+var_90], rax; enum _NGC_POLICY_SOURCE *
0x1800356c2  mov     r9, [rdi+20h]; enum _NGC_ENABLED_STATE *
0x1800356c6  mov     r8, [rdi+18h]; unsigned __int16 *
0x1800356ca  mov     rdx, [rdx]; unsigned __int16 *
0x1800356cd  mov     rcx, [rcx]; this
0x1800356d0  call    ?QueryIsNgcEnabled@PolicyManager@@YAJPEBG0PEAW4_NGC_ENABLED_STATE@@PEAW4_NGC_POLICY_SOURCE@@PEAW4_NgcEnabledModifiers@@@Z; PolicyManager::QueryIsNgcEnabled(ushort const *,ushort const *,_NGC_ENABLED_STATE *,_NGC_POLICY_SOURCE *,_NgcEnabledModifiers *)
0x1800356d5  mov     [rbx], eax
0x1800356d7  mov     rax, [rdi]
0x1800356da  xor     r14d, r14d
0x1800356dd  cmp     [rax], r14d
0x1800356e0  jge     short loc_180035720
0x1800356e2  mov     eax, cs:dword_18006E000
0x1800356e8  cmp     eax, 2
0x1800356eb  jbe     loc_180035A88
0x1800356f1  mov     rax, [rdi]
0x1800356f4  mov     ecx, [rax]
0x1800356f6  mov     [rbp+57h+var_80], ecx
0x1800356f9  lea     rdx, byte_180060623
0x180035700  lea     rcx, dword_18006E000
0x180035707  xor     r9d, r9d
0x18003570a  lea     rax, [rbp+57h+var_80]
0x18003570e  xor     r8d, r8d
0x180035711  mov     [rsp+0B0h+var_90], rax
0x180035716  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003571b  jmp     loc_180035A88
0x180035720  mov     rax, [rdi+28h]
0x180035724  mov     ecx, [rax]
0x180035726  shr     ecx, 1
0x180035728  and     cl, 1
0x18003572b  mov     rax, [rdi+30h]
0x18003572f  mov     [rax], cl
0x180035731  mov     rax, [rdi+28h]
0x180035735  mov     ecx, [rax]
0x180035737  shr     ecx, 3
0x18003573a  and     cl, 1
0x18003573d  mov     rax, [rdi+38h]
0x180035741  mov     [rax], cl
0x180035743  mov     rax, [rdi+40h]
0x180035747  cmp     [rax], r14b
0x18003574a  jnz     loc_180035A88
0x180035750  mov     [rbp+57h+var_7C], r14b
0x180035754  mov     rbx, [rdi]
0x180035757  lea     rcx, [rbp+57h+var_7C]; this
0x18003575b  call    ?IsCurrentSessionRemote@NgcUtils@@YAJPEA_N@Z; NgcUtils::IsCurrentSessionRemote(bool *)
0x180035760  mov     [rbx], eax
0x180035762  mov     rax, [rdi]
0x180035765  lea     rsi, dword_18006E000
0x18003576c  cmp     [rax], r14d
0x18003576f  jge     loc_18003580A
0x180035775  mov     eax, cs:dword_18006E000
0x18003577b  cmp     eax, 3
0x18003577e  jbe     short loc_1800357A6
0x180035780  mov     rax, [rdi]
0x180035783  mov     ecx, [rax]
0x180035785  mov     [rbp+57h+var_80], ecx
0x180035788  lea     rax, [rbp+57h+var_80]
0x18003578c  mov     [rsp+0B0h+var_90], rax
0x180035791  xor     r9d, r9d
0x180035794  xor     r8d, r8d
0x180035797  lea     rdx, byte_1800605E7
0x18003579e  mov     rcx, rsi
0x1800357a1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800357a6  mov     rax, [rdi]
0x1800357a9  mov     [rax], r14d
0x1800357ac  mov     rbx, [rdi]
0x1800357af  mov     rcx, [rdi+8]
0x1800357b3  mov     rdx, [rdi+50h]; unsigned __int16 *
0x1800357b7  mov     rcx, [rcx]; this
0x1800357ba  call    ?GetManagedPolicy@PolicyManager@@YAJPEBGPEAVNgcPolicy@2@PEAW4PolicyType@1@@Z; PolicyManager::GetManagedPolicy(ushort const *,NgcPolicy::NgcPolicy *,PolicyManager::PolicyType *)
0x1800357bf  mov     [rbx], eax
0x1800357c1  mov     rax, [rdi]
0x1800357c4  mov     ecx, [rax]
0x1800357c6  cmp     ecx, 80090011h
0x1800357cc  jnz     short loc_180035816
0x1800357ce  mov     eax, cs:dword_18006E000
0x1800357d4  cmp     eax, 3
0x1800357d7  jbe     short loc_1800357FF
0x1800357d9  mov     rax, [rdi]
0x1800357dc  mov     ecx, [rax]
0x1800357de  mov     [rbp+57h+var_80], ecx
0x1800357e1  lea     rax, [rbp+57h+var_80]
0x1800357e5  mov     [rsp+0B0h+var_90], rax
0x1800357ea  xor     r9d, r9d
0x1800357ed  xor     r8d, r8d
0x1800357f0  lea     rdx, byte_1800605AB
0x1800357f7  mov     rcx, rsi
0x1800357fa  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800357ff  mov     rax, [rdi]
0x180035802  mov     [rax], r14d
0x180035805  jmp     loc_180035A88
0x18003580a  cmp     [rbp+57h+var_7C], r14b
0x18003580e  jz      short loc_1800357AC
0x180035810  mov     rax, [rdi+48h]
0x180035814  jmp     short loc_180035802
0x180035816  test    ecx, ecx
0x180035818  jns     short loc_180035840
0x18003581a  mov     eax, cs:dword_18006E000
0x180035820  cmp     eax, 2
0x180035823  jbe     loc_180035A88
0x180035829  mov     rax, [rdi]
0x18003582c  mov     ecx, [rax]
0x18003582e  mov     [rbp+57h+var_80], ecx
0x180035831  lea     rdx, dword_180060574
0x180035838  mov     rcx, rsi
0x18003583b  jmp     loc_180035707
0x180035840  mov     rax, [rdi+50h]
0x180035844  cmp     dword ptr [rax+0Ch], 1
0x180035848  jnz     loc_180035A88
0x18003584e  mov     rax, [rdi+58h]
0x180035852  mov     byte ptr [rax], 1
0x180035855  mov     rax, [rdi+60h]
0x180035859  mov     byte ptr [rax], 1
0x18003585c  mov     rbx, [rdi]
0x18003585f  mov     rcx, [rdi+8]
0x180035863  mov     rdx, [rdi+68h]; bool *
0x180035867  mov     rcx, [rcx]; unsigned __int16 *
0x18003586a  call    ?I_IsNgcContainerHardwareCapable@@YAJPEBGPEA_N@Z; I_IsNgcContainerHardwareCapable(ushort const *,bool *)
0x18003586f  mov     [rbx], eax
0x180035871  mov     rcx, [rdi]
0x180035874  mov     eax, [rcx]
0x180035876  cmp     eax, 8009002Ah
0x18003587b  jnz     short loc_180035889
0x18003587d  mov     [rcx], r14d
0x180035880  mov     rax, [rdi+58h]
0x180035884  mov     [rax], r14b
0x180035887  jmp     short loc_180035891
0x180035889  test    eax, eax
0x18003588b  js      loc_180035A8D
0x180035891  mov     [rbp+57h+var_78], r14
0x180035895  mov     rbx, [rdi]
0x180035898  lea     rdx, [rbp+57h+var_78]
0x18003589c  call    DsrGetJoinInfo
0x1800358a1  mov     [rbx], eax
0x1800358a3  mov     rax, [rdi]
0x1800358a6  cmp     [rax], r14d
0x1800358a9  jge     short loc_1800358DE
0x1800358ab  mov     eax, cs:dword_18006E000
0x1800358b1  cmp     eax, 2
0x1800358b4  jbe     short loc_18003590B
0x1800358b6  mov     rax, [rdi]
0x1800358b9  mov     ecx, [rax]
0x1800358bb  mov     [rbp+57h+var_80], ecx
0x1800358be  lea     rax, [rbp+57h+var_80]
0x1800358c2  mov     [rsp+0B0h+var_90], rax
0x1800358c7  xor     r9d, r9d
0x1800358ca  xor     r8d, r8d
0x1800358cd  lea     rdx, word_18006054E
0x1800358d4  mov     rcx, rsi
0x1800358d7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800358dc  jmp     short loc_18003590B
0x1800358de  mov     rax, [rdi+58h]
0x1800358e2  cmp     [rax], r14b
0x1800358e5  jz      short loc_180035915
0x1800358e7  mov     rax, [rdi+68h]
0x1800358eb  cmp     [rax], r14b
0x1800358ee  jnz     short loc_180035915
0x1800358f0  mov     rax, [rbp+57h+var_78]
0x1800358f4  test    rax, rax
0x1800358f7  jz      short loc_1800358FE
0x1800358f9  cmp     dword ptr [rax], 1
0x1800358fc  jz      short loc_180035915
0x1800358fe  mov     rax, [rdi+48h]
0x180035902  mov     [rax], r14d
0x180035905  mov     rax, [rdi]
0x180035908  mov     [rax], r14d
0x18003590b  mov     rax, [rdi]
0x18003590e  mov     ebx, [rax]
0x180035910  jmp     loc_1800359D0
0x180035915  mov     rax, [rdi+70h]
0x180035919  mov     byte ptr [rax], 1
0x18003591c  lea     rcx, [rbp+57h+var_60]
0x180035920  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180035925  nop
0x180035926  mov     rbx, [rdi]
0x180035929  xor     r9d, r9d
0x18003592c  lea     r8, [rbp+57h+var_60]
0x180035930  lea     edx, [r9+1]
0x180035934  mov     rcx, [rdi+50h]
0x180035938  call    ?GetProviderName@PolicyManager@@YAJAEBVNgcPolicy@2@W4NgcCtnrTpmSupport@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; PolicyManager::GetProviderName(NgcPolicy::NgcPolicy const &,NgcCtnrTpmSupport,std::wstring *,bool)
0x18003593d  mov     [rbx], eax
0x18003593f  mov     rax, [rdi]
0x180035942  cmp     [rax], r14d
0x180035945  jge     short loc_18003595B
0x180035947  mov     eax, cs:dword_18006E000
0x18003594d  cmp     eax, 3
0x180035950  jbe     short loc_1800359B4
0x180035952  lea     rdx, byte_180060521
0x180035959  jmp     short loc_180035995
0x18003595b  lea     rcx, [rbp+57h+var_60]
0x18003595f  cmp     [rbp+57h+var_48], 7
0x180035964  cmova   rcx, [rbp+57h+var_60]
0x180035969  mov     r9d, 22h ; '"'
0x18003596f  lea     r8, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180035976  mov     rdx, [rbp+57h+var_50]
0x18003597a  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18003597f  test    al, al
0x180035981  jnz     short loc_1800359E0
0x180035983  mov     eax, cs:dword_18006E000
0x180035989  cmp     eax, 3
0x18003598c  jbe     short loc_1800359B4
0x18003598e  lea     rdx, byte_1800604F1
0x180035995  mov     rax, [rdi]
0x180035998  mov     ecx, [rax]
0x18003599a  lea     rax, [rbp+57h+var_80]
0x18003599e  mov     [rbp+57h+var_80], ecx
0x1800359a1  mov     [rsp+0B0h+var_90], rax
0x1800359a6  xor     r9d, r9d
0x1800359a9  xor     r8d, r8d
0x1800359ac  mov     rcx, rsi
0x1800359af  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800359b4  mov     rax, [rdi]
0x1800359b7  mov     [rax], r14d
0x1800359ba  mov     rax, [rdi+48h]
0x1800359be  mov     [rax], r14d
0x1800359c1  mov     rax, [rdi]
0x1800359c4  mov     ebx, [rax]
0x1800359c6  lea     rcx, [rbp+57h+var_60]
0x1800359ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800359cf  nop
0x1800359d0  lea     rcx, [rbp+57h+var_78]
0x1800359d4  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x1800359d9  mov     eax, ebx
0x1800359db  jmp     loc_180035A8D
0x1800359e0  mov     rax, [rdi+70h]
0x1800359e4  mov     [rax], r14b
0x1800359e7  lea     r12, ??_7?$HandleT@UNCryptProvHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable'
0x1800359ee  mov     [rbp+57h+var_70], r12
0x1800359f2  mov     [rbp+57h+phProvider], r14
0x1800359f6  lea     rcx, [rbp+57h+var_70]
0x1800359fa  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x1800359ff  mov     rbx, [rdi]
0x180035a02  xor     r8d, r8d; dwFlags
0x180035a05  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180035a0c  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180035a10  call    cs:__imp_NCryptOpenStorageProvider
0x180035a16  mov     [rbx], eax
0x180035a18  mov     rax, [rdi]
0x180035a1b  cmp     [rax], r14d
0x180035a1e  jge     short loc_180035A60
0x180035a20  mov     eax, cs:dword_18006E000
0x180035a26  cmp     eax, 3
0x180035a29  jbe     short loc_180035A51
0x180035a2b  mov     rax, [rdi]
0x180035a2e  mov     ecx, [rax]
0x180035a30  mov     [rbp+57h+var_80], ecx
0x180035a33  lea     rax, [rbp+57h+var_80]
0x180035a37  mov     [rsp+0B0h+var_90], rax
0x180035a3c  xor     r9d, r9d
0x180035a3f  xor     r8d, r8d
0x180035a42  lea     rdx, byte_1800604B9
0x180035a49  mov     rcx, rsi
0x180035a4c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180035a51  mov     rax, [rdi]
0x180035a54  mov     [rax], r14d
0x180035a57  mov     rax, [rdi+48h]
0x180035a5b  mov     [rax], r14d
0x180035a5e  jmp     short loc_180035A67
0x180035a60  mov     rax, [rdi+78h]
0x180035a64  mov     byte ptr [rax], 1
0x180035a67  mov     [rbp+57h+var_70], r12
0x180035a6b  lea     rcx, [rbp+57h+var_70]
0x180035a6f  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x180035a74  nop
0x180035a75  lea     rcx, [rbp+57h+var_60]
0x180035a79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035a7e  nop
0x180035a7f  lea     rcx, [rbp+57h+var_78]
0x180035a83  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x180035a88  mov     rax, [rdi]
0x180035a8b  mov     eax, [rax]
0x180035a8d  mov     rcx, [rbp+57h+var_40]
0x180035a91  xor     rcx, rsp; StackCookie
0x180035a94  call    __security_check_cookie
0x180035a99  add     rsp, 88h
0x180035aa0  pop     r14
0x180035aa2  pop     r12
0x180035aa4  pop     rdi
0x180035aa5  pop     rsi
0x180035aa6  pop     rbx
0x180035aa7  pop     rbp
0x180035aa8  retn
```
