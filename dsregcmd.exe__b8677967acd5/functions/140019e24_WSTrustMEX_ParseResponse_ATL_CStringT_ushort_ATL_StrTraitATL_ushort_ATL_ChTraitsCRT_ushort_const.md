# WSTrustMEX::ParseResponse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140019e24`
- end: `0x14001a285`
- name: `?ParseResponse@WSTrustMEX@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1121`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000b0fc`

## callees

- `0x140001cdc`
- `0x140001d44`
- `0x140005458`
- `0x140007bf8`
- `0x140009818`
- `0x140018a14`
- `0x140018ed8`
- `0x140019090`
- `0x140019500`
- `0x140019e24`
- `0x14001a28c`
- `0x140028040`
- `0x140030010`

## import_xrefs

- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x14001a264`
- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x14001a264`

## string_xrefs

- `0x140019e99`: `xmlns:wsdl='http://schemas.xmlsoap.org/wsdl/' xmlns:sp='http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702' xmlns:sp2005='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' xmlns:wsu='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:wsa10='http://www.w3.org/2005/08/addressing' xmlns:http='http://schemas.microsoft.com/ws/06/2004/policy/http' xmlns:soap12='http://schemas.xmlsoap.org/wsdl/soap12/' xmlns:wsp='http://schemas.xmlsoap.org/ws/2004/09/po`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WSTrustMEX::ParseResponse(_QWORD *a1)
{
  _QWORD *v1; // r12
  const unsigned __int16 **v2; // r9
  unsigned int v3; // edx
  unsigned int v4; // r8d
  __int64 v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rdi
  _QWORD *v10; // rdx
  __int64 v11; // rdi
  __int64 v12; // rcx
  unsigned __int64 j; // rax
  __int64 v14; // rbx
  __int64 v15; // r13
  __int64 v16; // r12
  __int64 v17; // rax
  __int64 v18; // r15
  int v19; // r14d
  int v20; // esi
  _QWORD *v21; // rdx
  signed int k; // ebx
  int v23; // eax
  __int64 v24; // rdx
  _QWORD *v25; // rcx
  unsigned int v27; // eax
  unsigned __int64 i; // r8
  __int128 v29; // [rsp+20h] [rbp-89h] BYREF
  __int64 v30; // [rsp+30h] [rbp-79h]
  __int64 v31; // [rsp+38h] [rbp-71h] BYREF
  __int64 v32; // [rsp+40h] [rbp-69h] BYREF
  int v33; // [rsp+48h] [rbp-61h]
  int v34; // [rsp+4Ch] [rbp-5Dh]
  __int64 v35; // [rsp+50h] [rbp-59h] BYREF
  __int64 v36; // [rsp+58h] [rbp-51h]
  unsigned int v37; // [rsp+60h] [rbp-49h]
  int v38; // [rsp+64h] [rbp-45h]
  int v39; // [rsp+68h] [rbp-41h]
  int v40; // [rsp+6Ch] [rbp-3Dh]
  __int64 v41; // [rsp+70h] [rbp-39h]
  __int64 v42; // [rsp+78h] [rbp-31h]
  int v43; // [rsp+80h] [rbp-29h]
  int v44; // [rsp+84h] [rbp-25h]
  __int64 v45; // [rsp+88h] [rbp-21h]
  __int64 v46; // [rsp+90h] [rbp-19h]
  _QWORD v47[12]; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v49; // [rsp+118h] [rbp+6Fh]
  struct IUnknown *v50; // [rsp+120h] [rbp+77h] BYREF
  __int64 v51; // [rsp+128h] [rbp+7Fh]

  v1 = a1;
  v35 = 0;
  v36 = 0;
  v37 = 17;
  v41 = 0xFFFFFFFFLL;
  v42 = 0;
  v43 = 0;
  v44 = 10;
  v45 = 0;
  v46 = 0;
  v38 = 1061158912;
  v39 = 1048576000;
  v40 = 1074790400;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds(&v35);
  MSXML::Create(
    &v50,
    *v2,
    L"xmlns:wsdl='http://schemas.xmlsoap.org/wsdl/' xmlns:sp='http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702' x"
     "mlns:sp2005='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' xmlns:wsu='http://docs.oasis-open.org/wss/2004/0"
     "1/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:wsa10='http://www.w3.org/2005/08/addressing' xmlns:http='http:"
     "//schemas.microsoft.com/ws/06/2004/policy/http' xmlns:soap12='http://schemas.xmlsoap.org/wsdl/soap12/' xmlns:wsp='h"
     "ttp://schemas.xmlsoap.org/ws/2004/09/policy' ");
  WSTrustMEX::ParseResponsePolicies((__int64)v1, &v50, &v35);
  v29 = 0;
  v30 = 0;
  if ( v36 )
  {
    v3 = 0;
    v4 = v37;
    if ( v37 )
    {
      while ( 1 )
      {
        v5 = *(_QWORD *)(v35 + 8LL * v3);
        if ( v5 )
          break;
        if ( ++v3 >= v37 )
          goto LABEL_17;
      }
      do
      {
        v6 = v5;
        v7 = v5;
        if ( *(_QWORD *)(v5 + 32) )
        {
          v5 = *(_QWORD *)(v5 + 32);
        }
        else
        {
          LODWORD(v8) = *(_DWORD *)(v5 + 40) % v4;
          do
          {
            v8 = (unsigned int)(v8 + 1);
            v5 = 0;
            if ( (unsigned int)v8 >= v4 )
              break;
            v5 = *(_QWORD *)(v35 + 8 * v8);
          }
          while ( !v5 );
        }
        if ( *(_DWORD *)(*(_QWORD *)(v7 + 16) - 16LL) )
        {
          v9 = *((_QWORD *)&v29 + 1);
          if ( *((_QWORD *)&v29 + 1) == v30 )
          {
            std::vector<WSTrustMEX::PolicyInfo>::_Emplace_reallocate<WSTrustMEX::PolicyInfo const &>(
              &v29,
              *((_QWORD *)&v29 + 1),
              v6 + 8);
          }
          else
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              *((_QWORD **)&v29 + 1),
              (__int64 *)(v6 + 8));
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (_QWORD *)(v9 + 8),
              (__int64 *)(v7 + 16));
            *(_DWORD *)(v9 + 16) = *(_DWORD *)(v6 + 24);
            *(_DWORD *)(v9 + 20) = *(_DWORD *)(v6 + 28);
            *((_QWORD *)&v29 + 1) += 24LL;
          }
          v4 = v37;
        }
      }
      while ( v5 );
    }
  }
LABEL_17:
  if ( dword_1400460E0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_1400460E0);
    if ( dword_1400460E0 == -1 )
    {
      v27 = std::_Random_device();
      dword_140047474 = -1;
      dword_1400460F4 = v27;
      for ( i = 1; i < 0x270; ++i )
      {
        v27 = i + 1812433253 * (v27 ^ (v27 >> 30));
        dword_1400460F0[i + 1] = v27;
      }
      dword_1400460F0[0] = 624;
      Init_thread_footer(&dword_1400460E0);
    }
  }
  v10 = (_QWORD *)*((_QWORD *)&v29 + 1);
  v11 = v29;
  v49 = v29;
  v47[0] = dword_1400460F0;
  v12 = 64;
  for ( j = -1; j > 0xFFFFFFFF; j >>= 1 )
    --v12;
  v47[2] = j;
  v47[1] = v12;
  if ( (_QWORD)v29 != *((_QWORD *)&v29 + 1) )
  {
    v14 = 1;
    v15 = v29 + 24;
    if ( (_QWORD)v29 + 24LL != *((_QWORD *)&v29 + 1) )
    {
      v16 = *((_QWORD *)&v29 + 1);
      do
      {
        v51 = v14 + 1;
        v17 = std::_Rng_from_urng<__int64,std::mersenne_twister_engine<unsigned int,32,624,397,31,2567483615,11,4294967295,7,2636928640,15,4022730752,18,1812433253>>::operator()(
                v47,
                v14 + 1);
        if ( v17 != v14 )
        {
          v18 = v11 + 24 * v17;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v31,
            (__int64 *)v15);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v32,
            (__int64 *)(v15 + 8));
          v33 = *(_DWORD *)(v15 + 16);
          v19 = v33;
          v34 = *(_DWORD *)(v15 + 20);
          v20 = v34;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
            (_QWORD *)v15,
            (_QWORD *)v18);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
            (_QWORD *)(v15 + 8),
            (_QWORD *)(v18 + 8));
          *(_DWORD *)(v15 + 16) = *(_DWORD *)(v18 + 16);
          *(_DWORD *)(v15 + 20) = *(_DWORD *)(v18 + 20);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
            (_QWORD *)v18,
            &v31);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
            (_QWORD *)(v18 + 8),
            &v32);
          *(_DWORD *)(v18 + 16) = v19;
          *(_DWORD *)(v18 + 20) = v20;
          v21 = (_QWORD *)(v32 - 24);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32 - 24 + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
          v10 = (_QWORD *)(v31 - 24);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v31 - 24 + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
          v11 = v49;
        }
        v14 = v51;
        v15 += 24;
      }
      while ( v15 != v16 );
      v1 = a1;
    }
  }
  for ( k = 0; k < (int)(-1431655765 * ((__int64)(*((_QWORD *)&v29 + 1) - v29) >> 3)); ++k )
  {
    v10 = (_QWORD *)v29;
    v23 = *(_DWORD *)(v29 + 24LL * k + 16);
    if ( v23 == 1 )
    {
      if ( *(_DWORD *)(v29 + 24LL * k + 20) != 2 )
      {
        if ( *(_DWORD *)(v29 + 24LL * k + 20) != 1 || *(_DWORD *)(v1[1] - 16LL) )
          continue;
        v24 = v29 + 24LL * k;
        v25 = v1 + 1;
        goto LABEL_46;
      }
      if ( !*(_DWORD *)(*v1 - 16LL) )
      {
        v24 = v29 + 24LL * k;
        v25 = v1;
LABEL_46:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          v25,
          (_QWORD *)(v24 + 8));
      }
    }
    else if ( !v23 )
    {
      if ( *(_DWORD *)(v29 + 24LL * k + 20) != 2 )
      {
        if ( *(_DWORD *)(v29 + 24LL * k + 20) != 1 || *(_DWORD *)(v1[3] - 16LL) )
          continue;
        v24 = v29 + 24LL * k;
        v25 = v1 + 3;
        goto LABEL_46;
      }
      if ( !*(_DWORD *)(v1[2] - 16LL) )
      {
        v24 = v29 + 24LL * k;
        v25 = v1 + 2;
        goto LABEL_46;
      }
    }
  }
  std::vector<WSTrustMEX::PolicyInfo>::~vector<WSTrustMEX::PolicyInfo>(&v29, v10);
  if ( v50 )
    ((void (__fastcall *)(struct IUnknown *))v50->lpVtbl->Release)(v50);
  return ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::~CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>(&v35);
}

```

## disassembly

```asm
0x140019e24  mov     [rsp-8+arg_0], rcx
0x140019e29  push    rbp
0x140019e2a  push    rbx
0x140019e2b  push    rsi
0x140019e2c  push    rdi
0x140019e2d  push    r12
0x140019e2f  push    r13
0x140019e31  push    r14
0x140019e33  push    r15
0x140019e35  lea     rbp, [rsp-1Fh]
0x140019e3a  sub     rsp, 0C8h
0x140019e41  mov     r9, rdx
0x140019e44  mov     r12, rcx
0x140019e47  xor     r15d, r15d
0x140019e4a  mov     [rbp+57h+var_B0], r15
0x140019e4e  mov     [rbp+57h+var_A8], r15
0x140019e52  mov     [rbp+57h+var_A0], 11h
0x140019e59  mov     r13d, 0FFFFFFFFh
0x140019e5f  mov     [rbp+57h+var_90], r13
0x140019e63  mov     [rbp+57h+var_88], r15
0x140019e67  mov     [rbp+57h+var_80], r15d
0x140019e6b  mov     [rbp+57h+var_7C], 0Ah
0x140019e72  mov     [rbp+57h+var_78], r15
0x140019e76  mov     [rbp+57h+var_70], r15
0x140019e7a  mov     [rbp+57h+var_9C], 3F400000h
0x140019e81  mov     [rbp+57h+var_98], 3E800000h
0x140019e88  mov     [rbp+57h+var_94], 40100000h
0x140019e8f  lea     rcx, [rbp+57h+var_B0]
0x140019e93  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds(void)
0x140019e98  nop
0x140019e99  lea     r8, aXmlnsWsdlHttpS; "xmlns:wsdl='http://schemas.xmlsoap.org/"...
0x140019ea0  mov     rdx, [r9]
0x140019ea3  lea     rcx, [rbp+57h+arg_10]
0x140019ea7  call    ?Create@MSXML@@YA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG0@Z; MSXML::Create(ushort const *,ushort const *)
0x140019eac  nop
0x140019ead  lea     r8, [rbp+57h+var_B0]
0x140019eb1  lea     rdx, [rbp+57h+arg_10]
0x140019eb5  mov     rcx, r12
0x140019eb8  call    ?ParseResponsePolicies@WSTrustMEX@@AEAAXAEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@@Z; WSTrustMEX::ParseResponsePolicies(_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> const &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>> &)
0x140019ebd  xorps   xmm0, xmm0
0x140019ec0  movdqu  [rsp+100h+var_E0], xmm0
0x140019ec6  mov     [rbp+57h+var_D0], r15
0x140019eca  cmp     [rbp+57h+var_A8], r15
0x140019ece  jz      loc_140019F97
0x140019ed4  mov     edx, r15d
0x140019ed7  mov     r8d, [rbp+57h+var_A0]
0x140019edb  test    r8d, r8d
0x140019ede  jz      loc_140019F97
0x140019ee4  mov     ecx, edx
0x140019ee6  mov     rax, [rbp+57h+var_B0]
0x140019eea  mov     rbx, [rax+rcx*8]
0x140019eee  test    rbx, rbx
0x140019ef1  jnz     short loc_140019EFF
0x140019ef3  inc     edx
0x140019ef5  cmp     edx, r8d
0x140019ef8  jb      short loc_140019EE4
0x140019efa  jmp     loc_140019F97
0x140019eff  mov     rsi, rbx
0x140019f02  mov     r14, rbx
0x140019f05  mov     rax, [rbx+20h]
0x140019f09  test    rax, rax
0x140019f0c  jz      short loc_140019F13
0x140019f0e  mov     rbx, rax
0x140019f11  jmp     short loc_140019F32
0x140019f13  xor     edx, edx
0x140019f15  mov     eax, [rbx+28h]
0x140019f18  div     r8d
0x140019f1b  inc     edx
0x140019f1d  mov     rbx, r15
0x140019f20  cmp     edx, r8d
0x140019f23  jnb     short loc_140019F32
0x140019f25  mov     rax, [rbp+57h+var_B0]
0x140019f29  mov     rbx, [rax+rdx*8]
0x140019f2d  test    rbx, rbx
0x140019f30  jz      short loc_140019F1B
0x140019f32  mov     rax, [r14+10h]
0x140019f36  cmp     [rax-10h], r15d
0x140019f3a  jz      short loc_140019F8E
0x140019f3c  mov     rdi, qword ptr [rsp+100h+var_E0+8]
0x140019f41  cmp     rdi, [rbp+57h+var_D0]
0x140019f45  jz      short loc_140019F79
0x140019f47  mov     [rbp+57h+arg_8], rdi
0x140019f4b  lea     rdx, [rsi+8]
0x140019f4f  mov     rcx, rdi
0x140019f52  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140019f57  nop
0x140019f58  lea     rcx, [rdi+8]
0x140019f5c  lea     rdx, [r14+10h]
0x140019f60  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140019f65  mov     eax, [rsi+18h]
0x140019f68  mov     [rdi+10h], eax
0x140019f6b  mov     eax, [rsi+1Ch]
0x140019f6e  mov     [rdi+14h], eax
0x140019f71  add     qword ptr [rsp+100h+var_E0+8], 18h
0x140019f77  jmp     short loc_140019F8A
0x140019f79  lea     r8, [rsi+8]
0x140019f7d  mov     rdx, rdi
0x140019f80  lea     rcx, [rsp+100h+var_E0]
0x140019f85  call    ??$_Emplace_reallocate@AEBUPolicyInfo@WSTrustMEX@@@?$vector@UPolicyInfo@WSTrustMEX@@V?$allocator@UPolicyInfo@WSTrustMEX@@@std@@@std@@AEAAPEAUPolicyInfo@WSTrustMEX@@QEAU23@AEBU23@@Z; std::vector<WSTrustMEX::PolicyInfo>::_Emplace_reallocate<WSTrustMEX::PolicyInfo const &>(WSTrustMEX::PolicyInfo * const,WSTrustMEX::PolicyInfo const &)
0x140019f8a  mov     r8d, [rbp+57h+var_A0]
0x140019f8e  test    rbx, rbx
0x140019f91  jnz     loc_140019EFF
0x140019f97  mov     ecx, 4
0x140019f9c  mov     rax, gs:58h
0x140019fa5  mov     rax, [rax]
0x140019fa8  lea     rbx, dword_1400460F0
0x140019faf  mov     eax, [rcx+rax]
0x140019fb2  cmp     cs:dword_1400460E0, eax
0x140019fb8  jg      loc_14001A24B
0x140019fbe  mov     rdx, qword ptr [rsp+100h+var_E0+8]
0x140019fc3  mov     rdi, qword ptr [rsp+100h+var_E0]
0x140019fc8  mov     [rbp+57h+arg_8], rdi
0x140019fcc  mov     [rbp+57h+var_60], rbx
0x140019fd0  mov     ecx, 40h ; '@'
0x140019fd5  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019fd9  dec     rcx
0x140019fdc  shr     rax, 1
0x140019fdf  cmp     rax, r13
0x140019fe2  ja      short loc_140019FD9
0x140019fe4  mov     [rbp+57h+var_50], rax
0x140019fe8  mov     [rbp+57h+var_58], rcx
0x140019fec  cmp     rdi, rdx
0x140019fef  jz      loc_14001A105
0x140019ff5  mov     ebx, 1
0x140019ffa  lea     r13, [rdi+18h]
0x140019ffe  cmp     r13, rdx
0x14001a001  jz      loc_14001A105
0x14001a007  mov     r12, rdx
0x14001a00a  lea     rax, [rbx+1]
0x14001a00e  mov     [rbp+57h+arg_18], rax
0x14001a012  mov     rdx, rax
0x14001a015  lea     rcx, [rbp+57h+var_60]
0x14001a019  call    ??R?$_Rng_from_urng@_JV?$mersenne_twister_engine@I$0CA@$0CHA@$0BIN@$0BP@$0JJAILANP@$0L@$0PPPPPPPP@$06$0JNCMFGIA@$0P@$0OPMGAAAA@$0BC@$0GMAHIJGF@@std@@@std@@QEAA_J_J@Z; std::_Rng_from_urng<__int64,std::mersenne_twister_engine<uint,32,624,397,31,2567483615,11,4294967295,7,2636928640,15,4022730752,18,1812433253>>::operator()(__int64)
0x14001a01e  cmp     rax, rbx
0x14001a021  jz      loc_14001A0F0
0x14001a027  lea     rax, [rax+rax*2]
0x14001a02b  lea     r15, [rdi+rax*8]
0x14001a02f  mov     rdx, r13
0x14001a032  lea     rcx, [rbp+57h+var_C8]
0x14001a036  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001a03b  nop
0x14001a03c  lea     rdx, [r13+8]
0x14001a040  lea     rcx, [rbp+57h+var_C0]
0x14001a044  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001a049  mov     r14d, [r13+10h]
0x14001a04d  mov     [rbp+57h+var_B8], r14d
0x14001a051  mov     esi, [r13+14h]
0x14001a055  mov     [rbp+57h+var_B4], esi
0x14001a058  mov     rdx, r15
0x14001a05b  mov     rcx, r13
0x14001a05e  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001a063  lea     rdx, [r15+8]
0x14001a067  lea     rcx, [r13+8]
0x14001a06b  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001a070  mov     eax, [r15+10h]
0x14001a074  mov     [r13+10h], eax
0x14001a078  mov     eax, [r15+14h]
0x14001a07c  mov     [r13+14h], eax
0x14001a080  lea     rdx, [rbp+57h+var_C8]
0x14001a084  mov     rcx, r15
0x14001a087  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001a08c  lea     rdx, [rbp+57h+var_C0]
0x14001a090  lea     rcx, [r15+8]
0x14001a094  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001a099  mov     [r15+10h], r14d
0x14001a09d  mov     [r15+14h], esi
0x14001a0a1  mov     rdx, [rbp+57h+var_C0]
0x14001a0a5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a0a9  or      eax, 0FFFFFFFFh
0x14001a0ac  lock xadd [rdx+10h], eax
0x14001a0b1  xor     r15d, r15d
0x14001a0b4  sub     eax, 1
0x14001a0b7  jg      short loc_14001A0C8
0x14001a0b9  mov     rcx, [rdx]
0x14001a0bc  mov     rax, [rcx]
0x14001a0bf  mov     rax, [rax+8]
0x14001a0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a0c8  mov     rdx, [rbp+57h+var_C8]
0x14001a0cc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a0d0  or      eax, 0FFFFFFFFh
0x14001a0d3  lock xadd [rdx+10h], eax
0x14001a0d8  sub     eax, 1
0x14001a0db  jg      short loc_14001A0EC
0x14001a0dd  mov     rcx, [rdx]
0x14001a0e0  mov     rax, [rcx]
0x14001a0e3  mov     rax, [rax+8]
0x14001a0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a0ec  mov     rdi, [rbp+57h+arg_8]
0x14001a0f0  mov     rbx, [rbp+57h+arg_18]
0x14001a0f4  add     r13, 18h
0x14001a0f8  cmp     r13, r12
0x14001a0fb  jnz     loc_14001A00A
0x14001a101  mov     r12, [rbp+57h+arg_0]
0x14001a105  mov     ebx, r15d
0x14001a108  mov     rax, qword ptr [rsp+100h+var_E0+8]
0x14001a10d  sub     rax, qword ptr [rsp+100h+var_E0]
0x14001a112  sar     rax, 3
0x14001a116  mov     rdi, 0AAAAAAAAAAAAAAABh
0x14001a120  imul    rax, rdi
0x14001a124  test    eax, eax
0x14001a126  jle     loc_14001A1D9
0x14001a12c  movsxd  rax, ebx
0x14001a12f  lea     rcx, [rax+rax*2]
0x14001a133  mov     rdx, qword ptr [rsp+100h+var_E0]
0x14001a138  mov     eax, [rdx+rcx*8+10h]
0x14001a13c  cmp     eax, 1
0x14001a13f  jnz     short loc_14001A178
0x14001a141  cmp     dword ptr [rdx+rcx*8+14h], 2
0x14001a146  jnz     short loc_14001A15B
0x14001a148  mov     rax, [r12]
0x14001a14c  cmp     [rax-10h], r15d
0x14001a150  jnz     short loc_14001A1BD
0x14001a152  lea     rdx, [rdx+rcx*8]
0x14001a156  mov     rcx, r12
0x14001a159  jmp     short loc_14001A1B4
0x14001a15b  cmp     dword ptr [rdx+rcx*8+14h], 1
0x14001a160  jnz     short loc_14001A1BD
0x14001a162  mov     rax, [r12+8]
0x14001a167  cmp     [rax-10h], r15d
0x14001a16b  jnz     short loc_14001A1BD
0x14001a16d  lea     rdx, [rdx+rcx*8]
0x14001a171  lea     rcx, [r12+8]
0x14001a176  jmp     short loc_14001A1B4
0x14001a178  test    eax, eax
0x14001a17a  jnz     short loc_14001A1BD
0x14001a17c  cmp     dword ptr [rdx+rcx*8+14h], 2
0x14001a181  jnz     short loc_14001A199
0x14001a183  mov     rax, [r12+10h]
0x14001a188  cmp     [rax-10h], r15d
0x14001a18c  jnz     short loc_14001A1BD
0x14001a18e  lea     rdx, [rdx+rcx*8]
0x14001a192  lea     rcx, [r12+10h]
0x14001a197  jmp     short loc_14001A1B4
0x14001a199  cmp     dword ptr [rdx+rcx*8+14h], 1
0x14001a19e  jnz     short loc_14001A1BD
0x14001a1a0  mov     rax, [r12+18h]
0x14001a1a5  cmp     [rax-10h], r15d
0x14001a1a9  jnz     short loc_14001A1BD
0x14001a1ab  lea     rdx, [rdx+rcx*8]
0x14001a1af  lea     rcx, [r12+18h]
0x14001a1b4  add     rdx, 8
0x14001a1b8  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001a1bd  inc     ebx
0x14001a1bf  mov     rax, qword ptr [rsp+100h+var_E0+8]
0x14001a1c4  sub     rax, qword ptr [rsp+100h+var_E0]
0x14001a1c9  sar     rax, 3
0x14001a1cd  imul    rax, rdi
0x14001a1d1  cmp     ebx, eax
0x14001a1d3  jl      loc_14001A12C
0x14001a1d9  lea     rcx, [rsp+100h+var_E0]
0x14001a1de  call    ??1?$vector@UPolicyInfo@WSTrustMEX@@V?$allocator@UPolicyInfo@WSTrustMEX@@@std@@@std@@QEAA@XZ; std::vector<WSTrustMEX::PolicyInfo>::~vector<WSTrustMEX::PolicyInfo>(void)
0x14001a1e3  nop
0x14001a1e4  mov     rcx, [rbp+57h+arg_10]
0x14001a1e8  test    rcx, rcx
0x14001a1eb  jz      short loc_14001A1FA
0x14001a1ed  mov     rax, [rcx]
0x14001a1f0  mov     rax, [rax+10h]
0x14001a1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a1f9  nop
0x14001a1fa  lea     rcx, [rbp+57h+var_B0]
0x14001a1fe  call    ??1?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@QEAA@XZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::~CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>(void)
0x14001a203  add     rsp, 0C8h
0x14001a20a  pop     r15
0x14001a20c  pop     r14
0x14001a20e  pop     r13
0x14001a210  pop     r12
0x14001a212  pop     rdi
0x14001a213  pop     rsi
0x14001a214  pop     rbx
0x14001a215  pop     rbp
0x14001a216  retn
0x14001a217  mov     edx, eax
0x14001a219  shr     edx, 1Eh
0x14001a21c  xor     edx, eax
0x14001a21e  imul    eax, edx, 6C078965h
0x14001a224  add     eax, r8d
0x14001a227  mov     [rbx+r8*4+4], eax
0x14001a22c  inc     r8
0x14001a22f  cmp     r8, rcx
0x14001a232  jb      short loc_14001A217
0x14001a234  mov     cs:dword_1400460F0, ecx
0x14001a23a  lea     rcx, dword_1400460E0
0x14001a241  call    _Init_thread_footer
0x14001a246  jmp     loc_140019FBE
0x14001a24b  lea     rcx, dword_1400460E0
0x14001a252  call    _Init_thread_header
0x14001a257  cmp     cs:dword_1400460E0, 0FFFFFFFFh
0x14001a25e  jnz     loc_140019FBE
0x14001a264  call    cs:__imp_?_Random_device@std@@YAIXZ; std::_Random_device(void)
0x14001a26a  mov     cs:dword_140047474, r13d
0x14001a271  mov     cs:dword_1400460F4, eax
0x14001a277  mov     ecx, 270h
0x14001a27c  mov     r8d, 1
0x14001a282  jmp     short loc_14001A217
```
