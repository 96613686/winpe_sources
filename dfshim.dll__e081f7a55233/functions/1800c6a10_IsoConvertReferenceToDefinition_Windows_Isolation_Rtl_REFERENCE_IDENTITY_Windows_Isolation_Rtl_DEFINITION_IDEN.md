# IsoConvertReferenceToDefinition(Windows::Isolation::Rtl::_REFERENCE_IDENTITY,Windows::Isolation::Rtl::_DEFINITION_IDENTITY &)

- ea: `0x1800c6a10`
- end: `0x1800c6ebb`
- name: `?IsoConvertReferenceToDefinition@@YAJU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@AEAU_DEFINITION_IDENTITY@234@@Z`
- size: `1195`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800bbf88`
- `0x18010e7a4`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012b1c`
- `0x180013e50`
- `0x180013ed0`
- `0x1800436cc`
- `0x1800448bc`
- `0x18004f2dc`
- `0x1800a5980`
- `0x1800a5a80`
- `0x1800c6a10`
- `0x180107718`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6c43`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6cdf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6e54`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6c43`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6cdf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6e54`

## string_xrefs

- `0x1800c6bf7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c6c97`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c6e0c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall IsoConvertReferenceToDefinition(__int64 a1, _QWORD *a2)
{
  int IdentityAttributeEnumeratorData; // edi
  unsigned __int64 i; // rsi
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // r13
  __int64 v7; // rbx
  HANDLE ProcessHeap_0; // rax
  LPVOID v9; // rax
  void *v10; // rdi
  unsigned __int64 v11; // rdx
  void *v12; // r12
  HANDLE v13; // rax
  unsigned __int64 v14; // rax
  __int64 v15; // r10
  unsigned int *v16; // r11
  signed int v17; // ecx
  __int64 v18; // r10
  unsigned int *v19; // r11
  signed int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned __int64 v25; // r8
  __int64 v26; // r10
  __int64 v27; // r9
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // xmm4_8
  __int128 v32; // xmm1
  __int128 v33; // xmm2
  __int128 v34; // xmm3
  __int64 v35; // r10
  unsigned int *v36; // r11
  signed int v37; // ecx
  unsigned __int64 v38; // rcx
  __int64 v40; // [rsp+30h] [rbp-99h] BYREF
  __int128 v41; // [rsp+38h] [rbp-91h] BYREF
  unsigned __int64 v42; // [rsp+48h] [rbp-81h]
  unsigned __int64 v43; // [rsp+50h] [rbp-79h]
  int v44; // [rsp+58h] [rbp-71h] BYREF
  int v45; // [rsp+5Ch] [rbp-6Dh] BYREF
  __int64 v46; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int64 v47; // [rsp+68h] [rbp-61h] BYREF
  _QWORD *v48; // [rsp+70h] [rbp-59h]
  _BYTE *v49; // [rsp+80h] [rbp-49h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-41h]
  unsigned __int64 v51; // [rsp+90h] [rbp-39h]
  unsigned __int64 v52; // [rsp+98h] [rbp-31h]
  _BYTE v53[80]; // [rsp+A0h] [rbp-29h] BYREF

  v48 = a2;
  *a2 = 0;
  v49 = v53;
  v51 = 10;
  lpMem = v53;
  v52 = 0;
  v40 = 0;
  IdentityAttributeEnumeratorData = RtlCreateReferenceIdentityAttributeEnumerator(a1, &v40);
  if ( IdentityAttributeEnumeratorData < 0 )
  {
LABEL_37:
    if ( v40 )
    {
      LODWORD(v42) = -1073741595;
      *(_QWORD *)&v41 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v40) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v19 + 4))(*v19, v18);
        v20 = 0;
      }
      else
      {
        DWORD2(v41) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v41);
        v20 = v42;
      }
      if ( v20 < 0 )
        RaiseException(v20, 1u, 0, 0);
      v40 = 0;
    }
    if ( v52 < v51 )
      v52 = v51;
  }
  else
  {
    for ( i = 0; ; i += v47 )
    {
      v4 = v51;
      v47 = 0;
      if ( i == v51 )
      {
        v5 = v51 + 10;
        if ( v51 + 10 < v51 || v5 < 0xA )
        {
          IdentityAttributeEnumeratorData = -1073741675;
          goto LABEL_26;
        }
        if ( v5 > v51 )
        {
          v6 = v52;
          v46 = 0;
          BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(&v45, 8, v51 + 10, &v46);
          IdentityAttributeEnumeratorData = v45;
          if ( v45 < 0 )
            goto LABEL_26;
          v7 = v46;
          ProcessHeap_0 = GetProcessHeap_0();
          v9 = HeapAlloc_0(ProcessHeap_0, 0, v7 + 8);
          v4 = v51;
          v10 = v9;
          if ( !v9 )
          {
            IdentityAttributeEnumeratorData = -1073741801;
LABEL_26:
            if ( v40 )
            {
              LODWORD(v42) = -1073741595;
              *(_QWORD *)&v41 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v40) )
              {
                (*((void (__fastcall **)(_QWORD, __int64))v16 + 4))(*v16, v15);
                v4 = v51;
                v17 = 0;
              }
              else
              {
                DWORD2(v41) = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v41);
                v17 = v42;
                v4 = v51;
              }
              if ( v17 < 0 )
              {
                RaiseException(v17, 1u, 0, 0);
                v4 = v51;
              }
              v40 = 0;
            }
            if ( v52 < v4 )
              v52 = v4;
            goto LABEL_69;
          }
          v11 = 0;
          if ( v52 )
          {
            do
            {
              *((_QWORD *)v9 + v11) = *((_QWORD *)lpMem + v11);
              ++v11;
            }
            while ( v11 < v52 );
            v4 = v51;
          }
          v52 = 0;
          v12 = lpMem;
          if ( lpMem )
          {
            if ( lpMem != v49 )
            {
              BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(&v44, v4, 8, &v46);
              if ( v44 >= 0 )
              {
                v13 = GetProcessHeap_0();
                HeapFree_0(v13, 0, v12);
              }
            }
          }
          v4 = v5;
          lpMem = v10;
          v51 = v5;
          v52 = v6;
        }
      }
      v14 = v52;
      if ( v52 < v4 )
        v14 = v4;
      v52 = v14;
      IdentityAttributeEnumeratorData = RtlFetchIdentityAttributeEnumeratorData(
                                          v40,
                                          v4 - i,
                                          (char *)lpMem + 8 * i,
                                          &v47);
      if ( IdentityAttributeEnumeratorData < 0 )
        break;
      if ( !v47 )
      {
        v42 = 0;
        v43 = 0;
        v41 = 0;
        IdentityAttributeEnumeratorData = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(
                                                       &v41,
                                                       &v44,
                                                       i);
        if ( IdentityAttributeEnumeratorData >= 0 )
        {
          v25 = v42;
          v26 = 0;
          v27 = *((_QWORD *)&v41 + 1);
          v28 = v43;
          if ( i )
          {
            do
            {
              v29 = v52;
              if ( v52 < v51 )
                v29 = v51;
              v52 = v29;
              if ( v28 < v25 )
                v28 = v25;
              v22 = *((_QWORD *)lpMem + v26);
              v30 = 9 * v26++;
              v31 = *(_QWORD *)(v22 + 64);
              v32 = *(_OWORD *)(v22 + 16);
              v33 = *(_OWORD *)(v22 + 32);
              v34 = *(_OWORD *)(v22 + 48);
              *(_OWORD *)(v27 + 8 * v30) = *(_OWORD *)v22;
              *(_OWORD *)(v27 + 8 * v30 + 16) = v32;
              *(_OWORD *)(v27 + 8 * v30 + 32) = v33;
              *(_OWORD *)(v27 + 8 * v30 + 48) = v34;
              *(_QWORD *)(v27 + 8 * v30 + 64) = v31;
            }
            while ( v26 != i );
          }
          if ( v28 < v25 )
            v28 = v25;
          v43 = v28;
          IdentityAttributeEnumeratorData = RtlCreateDefinitionIdentity(v22, 0, i, v27, (__int64)v48);
          if ( IdentityAttributeEnumeratorData >= 0 )
            IdentityAttributeEnumeratorData = 0;
        }
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(
          &v41,
          v21,
          v23,
          v24);
        goto LABEL_37;
      }
      if ( v47 + i < i || v47 + i < v47 )
      {
        IdentityAttributeEnumeratorData = -1073741675;
        goto LABEL_37;
      }
    }
    if ( v40 )
    {
      LODWORD(v42) = -1073741595;
      *(_QWORD *)&v41 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v40) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v36 + 4))(*v36, v35);
        v37 = 0;
      }
      else
      {
        DWORD2(v41) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v41);
        v37 = v42;
      }
      if ( v37 < 0 )
        RaiseException(v37, 1u, 0, 0);
      v40 = 0;
    }
    v38 = v52;
    if ( v52 < v51 )
      v38 = v51;
    v52 = v38;
  }
LABEL_69:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v49);
  return (unsigned int)IdentityAttributeEnumeratorData;
}

```

## disassembly

```asm
0x1800c6a10  mov     [rsp-8+arg_10], rbx
0x1800c6a15  mov     [rsp-8+arg_18], rsi
0x1800c6a1a  push    rbp
0x1800c6a1b  push    rdi
0x1800c6a1c  push    r12
0x1800c6a1e  push    r13
0x1800c6a20  push    r15
0x1800c6a22  lea     rbp, [rsp-37h]
0x1800c6a27  sub     rsp, 100h
0x1800c6a2e  mov     rax, cs:__security_cookie
0x1800c6a35  xor     rax, rsp
0x1800c6a38  mov     [rbp+57h+var_30], rax
0x1800c6a3c  xor     r12d, r12d
0x1800c6a3f  mov     [rbp+57h+var_B0], rdx
0x1800c6a43  lea     rax, [rbp+57h+var_80]
0x1800c6a47  mov     [rdx], r12
0x1800c6a4a  mov     [rbp+57h+var_A0], rax
0x1800c6a4e  lea     rdx, [rsp+120h+var_F0]
0x1800c6a53  lea     rax, [rbp+57h+var_80]
0x1800c6a57  mov     [rbp+57h+var_90], 0Ah
0x1800c6a5f  mov     [rbp+57h+lpMem], rax
0x1800c6a63  mov     [rbp+57h+var_88], r12
0x1800c6a67  mov     [rsp+120h+var_F0], r12
0x1800c6a6c  call    RtlCreateReferenceIdentityAttributeEnumerator
0x1800c6a71  mov     edi, eax
0x1800c6a73  test    eax, eax
0x1800c6a75  js      loc_1800C6C86
0x1800c6a7b  mov     esi, r12d
0x1800c6a7e  mov     rbx, [rbp+57h+var_90]
0x1800c6a82  mov     [rbp+57h+var_B8], r12
0x1800c6a86  cmp     rsi, rbx
0x1800c6a89  jnz     loc_1800C6B81
0x1800c6a8f  lea     r15, [rbx+0Ah]
0x1800c6a93  cmp     r15, rbx
0x1800c6a96  jb      loc_1800C6BE1
0x1800c6a9c  cmp     r15, 0Ah
0x1800c6aa0  jb      loc_1800C6BE1
0x1800c6aa6  cmp     r15, rbx
0x1800c6aa9  jbe     loc_1800C6B81
0x1800c6aaf  mov     r13, [rbp+57h+var_88]
0x1800c6ab3  lea     r9, [rbp+57h+var_C0]
0x1800c6ab7  mov     r8, r15
0x1800c6aba  mov     [rbp+57h+var_C0], r12
0x1800c6abe  mov     edx, 8
0x1800c6ac3  lea     rcx, [rbp+57h+var_C4]
0x1800c6ac7  call    ??$MultiplyWithOverflowCheck@VCCallDisposition@Rtl@BUCL@@_K@BUCL@@YA?AVCCallDisposition@Rtl@0@_K0AEA_K@Z; BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x1800c6acc  mov     edi, [rbp+57h+var_C4]
0x1800c6acf  test    edi, edi
0x1800c6ad1  js      loc_1800C6BE6
0x1800c6ad7  mov     rbx, [rbp+57h+var_C0]
0x1800c6adb  call    GetProcessHeap_0
0x1800c6ae0  mov     rcx, rax; hHeap
0x1800c6ae3  lea     r8, [rbx+8]; dwBytes
0x1800c6ae7  xor     edx, edx; dwFlags
0x1800c6ae9  call    HeapAlloc_0
0x1800c6aee  mov     rbx, [rbp+57h+var_90]
0x1800c6af2  mov     rdi, rax
0x1800c6af5  test    rax, rax
0x1800c6af8  jnz     short loc_1800C6B09
0x1800c6afa  mov     edi, 0C0000017h
0x1800c6aff  test    edi, edi
0x1800c6b01  js      loc_1800C6BE6
0x1800c6b07  jmp     short loc_1800C6B81
0x1800c6b09  mov     r8, rax
0x1800c6b0c  mov     rdx, r12
0x1800c6b0f  cmp     [rbp+57h+var_88], r12
0x1800c6b13  jbe     short loc_1800C6B2E
0x1800c6b15  mov     rax, [rbp+57h+lpMem]
0x1800c6b19  mov     rcx, [rax+rdx*8]
0x1800c6b1d  mov     [r8+rdx*8], rcx
0x1800c6b21  inc     rdx
0x1800c6b24  cmp     rdx, [rbp+57h+var_88]
0x1800c6b28  jb      short loc_1800C6B15
0x1800c6b2a  mov     rbx, [rbp+57h+var_90]
0x1800c6b2e  mov     [rbp+57h+var_88], r12
0x1800c6b32  mov     r12, [rbp+57h+lpMem]
0x1800c6b36  test    r12, r12
0x1800c6b39  jz      short loc_1800C6B6F
0x1800c6b3b  cmp     r12, [rbp+57h+var_A0]
0x1800c6b3f  jz      short loc_1800C6B6F
0x1800c6b41  lea     r9, [rbp+57h+var_C0]
0x1800c6b45  mov     r8d, 8
0x1800c6b4b  mov     rdx, rbx
0x1800c6b4e  lea     rcx, [rbp+57h+var_C8]
0x1800c6b52  call    ??$MultiplyWithOverflowCheck@VCCallDisposition@Rtl@BUCL@@_K@BUCL@@YA?AVCCallDisposition@Rtl@0@_K0AEA_K@Z; BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x1800c6b57  cmp     [rbp+57h+var_C8], 0
0x1800c6b5b  jl      short loc_1800C6B6F
0x1800c6b5d  call    GetProcessHeap_0
0x1800c6b62  mov     r8, r12; lpMem
0x1800c6b65  xor     edx, edx; dwFlags
0x1800c6b67  mov     rcx, rax; hHeap
0x1800c6b6a  call    HeapFree_0
0x1800c6b6f  mov     rbx, r15
0x1800c6b72  mov     [rbp+57h+lpMem], rdi
0x1800c6b76  mov     [rbp+57h+var_90], rbx
0x1800c6b7a  xor     r12d, r12d
0x1800c6b7d  mov     [rbp+57h+var_88], r13
0x1800c6b81  mov     rax, [rbp+57h+var_88]
0x1800c6b85  lea     r9, [rbp+57h+var_B8]
0x1800c6b89  mov     rcx, [rsp+120h+var_F0]
0x1800c6b8e  cmp     rax, rbx
0x1800c6b91  cmovb   rax, rbx
0x1800c6b95  sub     rbx, rsi
0x1800c6b98  mov     [rbp+57h+var_88], rax
0x1800c6b9c  mov     rdx, rbx
0x1800c6b9f  mov     rax, [rbp+57h+lpMem]
0x1800c6ba3  lea     r8, [rax+rsi*8]
0x1800c6ba7  call    RtlFetchIdentityAttributeEnumeratorData
0x1800c6bac  mov     edi, eax
0x1800c6bae  test    eax, eax
0x1800c6bb0  js      loc_1800C6DFB
0x1800c6bb6  mov     rax, [rbp+57h+var_B8]
0x1800c6bba  test    rax, rax
0x1800c6bbd  jz      loc_1800C6D19
0x1800c6bc3  lea     rcx, [rax+rsi]
0x1800c6bc7  cmp     rcx, rsi
0x1800c6bca  jb      loc_1800C6C81
0x1800c6bd0  cmp     rcx, rax
0x1800c6bd3  jb      loc_1800C6C81
0x1800c6bd9  mov     rsi, rcx
0x1800c6bdc  jmp     loc_1800C6A7E
0x1800c6be1  mov     edi, 0C0000095h
0x1800c6be6  mov     r10, [rsp+120h+var_F0]
0x1800c6beb  test    r10, r10
0x1800c6bee  jz      short loc_1800C6C52
0x1800c6bf0  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800c6bf7  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c6bfe  mov     dword ptr [rsp+120h+var_D8], 0C00000E5h
0x1800c6c06  mov     qword ptr [rsp+120h+var_E8], rax
0x1800c6c0b  test    r11, r11
0x1800c6c0e  jz      short loc_1800C6C65
0x1800c6c10  mov     rdx, r11
0x1800c6c13  mov     rcx, r10
0x1800c6c16  call    RtlIsTypeSafeHandleValid
0x1800c6c1b  test    al, al
0x1800c6c1d  jz      short loc_1800C6C65
0x1800c6c1f  mov     ecx, [r11]
0x1800c6c22  mov     rdx, r10
0x1800c6c25  mov     rax, [r11+20h]
0x1800c6c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c2e  mov     rbx, [rbp+57h+var_90]
0x1800c6c32  mov     ecx, r12d; dwExceptionCode
0x1800c6c35  test    ecx, ecx
0x1800c6c37  jns     short loc_1800C6C4D
0x1800c6c39  xor     r9d, r9d; lpArguments
0x1800c6c3c  xor     r8d, r8d; nNumberOfArguments
0x1800c6c3f  lea     edx, [r9+1]; dwExceptionFlags
0x1800c6c43  call    cs:__imp_RaiseException
0x1800c6c49  mov     rbx, [rbp+57h+var_90]
0x1800c6c4d  mov     [rsp+120h+var_F0], r12
0x1800c6c52  cmp     [rbp+57h+var_88], rbx
0x1800c6c56  jnb     loc_1800C6E70
0x1800c6c5c  mov     [rbp+57h+var_88], rbx
0x1800c6c60  jmp     loc_1800C6E70
0x1800c6c65  mov     dword ptr [rsp+120h+var_E8+8], 124h
0x1800c6c6d  lea     rcx, [rsp+120h+var_E8]
0x1800c6c72  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c6c77  mov     ecx, dword ptr [rsp+120h+var_D8]
0x1800c6c7b  mov     rbx, [rbp+57h+var_90]
0x1800c6c7f  jmp     short loc_1800C6C35
0x1800c6c81  mov     edi, 0C0000095h
0x1800c6c86  mov     r10, [rsp+120h+var_F0]
0x1800c6c8b  test    r10, r10
0x1800c6c8e  jz      short loc_1800C6CEA
0x1800c6c90  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800c6c97  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c6c9e  mov     dword ptr [rsp+120h+var_D8], 0C00000E5h
0x1800c6ca6  mov     qword ptr [rsp+120h+var_E8], rax
0x1800c6cab  test    r11, r11
0x1800c6cae  jz      short loc_1800C6D01
0x1800c6cb0  mov     rdx, r11
0x1800c6cb3  mov     rcx, r10
0x1800c6cb6  call    RtlIsTypeSafeHandleValid
0x1800c6cbb  test    al, al
0x1800c6cbd  jz      short loc_1800C6D01
0x1800c6cbf  mov     ecx, [r11]
0x1800c6cc2  mov     rdx, r10
0x1800c6cc5  mov     rax, [r11+20h]
0x1800c6cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6cce  mov     ecx, r12d; dwExceptionCode
0x1800c6cd1  test    ecx, ecx
0x1800c6cd3  jns     short loc_1800C6CE5
0x1800c6cd5  xor     r9d, r9d; lpArguments
0x1800c6cd8  xor     r8d, r8d; nNumberOfArguments
0x1800c6cdb  lea     edx, [r9+1]; dwExceptionFlags
0x1800c6cdf  call    cs:__imp_RaiseException
0x1800c6ce5  mov     [rsp+120h+var_F0], r12
0x1800c6cea  mov     rax, [rbp+57h+var_90]
0x1800c6cee  cmp     [rbp+57h+var_88], rax
0x1800c6cf2  jnb     loc_1800C6E70
0x1800c6cf8  mov     [rbp+57h+var_88], rax
0x1800c6cfc  jmp     loc_1800C6E70
0x1800c6d01  mov     dword ptr [rsp+120h+var_E8+8], 124h
0x1800c6d09  lea     rcx, [rsp+120h+var_E8]
0x1800c6d0e  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c6d13  mov     ecx, dword ptr [rsp+120h+var_D8]
0x1800c6d17  jmp     short loc_1800C6CD1
0x1800c6d19  xorps   xmm0, xmm0
0x1800c6d1c  mov     [rsp+120h+var_D8], r12
0x1800c6d21  mov     r8, rsi
0x1800c6d24  mov     [rbp+57h+var_D0], r12
0x1800c6d28  lea     rdx, [rbp+57h+var_C8]
0x1800c6d2c  lea     rcx, [rsp+120h+var_E8]
0x1800c6d31  movdqu  [rsp+120h+var_E8], xmm0
0x1800c6d37  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@_KU_IDENTITY_ATTRIBUTE@Rtl@Isolation@Windows@@V?$CDefaultObjectTraits@U_IDENTITY_ATTRIBUTE@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(unsigned __int64)
0x1800c6d3c  mov     edi, [rax]
0x1800c6d3e  test    edi, edi
0x1800c6d40  jns     short loc_1800C6D51
0x1800c6d42  lea     rcx, [rsp+120h+var_E8]
0x1800c6d47  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_IDENTITY_UTF8_ATTRIBUTE@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CSmartInlineArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800c6d4c  jmp     loc_1800C6C86
0x1800c6d51  mov     r8, [rsp+120h+var_D8]
0x1800c6d56  mov     r10, r12
0x1800c6d59  mov     r9, qword ptr [rsp+120h+var_E8+8]
0x1800c6d5e  mov     rdx, [rbp+57h+var_D0]
0x1800c6d62  test    rsi, rsi
0x1800c6d65  jz      short loc_1800C6DC5
0x1800c6d67  mov     rax, [rbp+57h+var_88]
0x1800c6d6b  cmp     rax, [rbp+57h+var_90]
0x1800c6d6f  cmovb   rax, [rbp+57h+var_90]
0x1800c6d74  cmp     rdx, r8
0x1800c6d77  mov     [rbp+57h+var_88], rax
0x1800c6d7b  mov     rax, [rbp+57h+lpMem]
0x1800c6d7f  cmovb   rdx, r8
0x1800c6d83  mov     rcx, [rax+r10*8]
0x1800c6d87  lea     rax, [r10+r10*8]
0x1800c6d8b  inc     r10
0x1800c6d8e  movsd   xmm4, qword ptr [rcx+40h]
0x1800c6d93  movups  xmm0, xmmword ptr [rcx]
0x1800c6d96  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c6d9a  movups  xmm2, xmmword ptr [rcx+20h]
0x1800c6d9e  movups  xmm3, xmmword ptr [rcx+30h]
0x1800c6da2  movups  xmmword ptr [r9+rax*8], xmm0
0x1800c6da7  movups  xmmword ptr [r9+rax*8+10h], xmm1
0x1800c6dad  movups  xmmword ptr [r9+rax*8+20h], xmm2
0x1800c6db3  movups  xmmword ptr [r9+rax*8+30h], xmm3
0x1800c6db9  movsd   qword ptr [r9+rax*8+40h], xmm4
0x1800c6dc0  cmp     r10, rsi
0x1800c6dc3  jnz     short loc_1800C6D67
0x1800c6dc5  mov     rax, [rbp+57h+var_B0]
0x1800c6dc9  cmp     rdx, r8
0x1800c6dcc  mov     [rsp+120h+var_100], rax
0x1800c6dd1  cmovb   rdx, r8
0x1800c6dd5  mov     r8, rsi
0x1800c6dd8  mov     [rbp+57h+var_D0], rdx
0x1800c6ddc  mov     rdx, r12
0x1800c6ddf  call    RtlCreateDefinitionIdentity
0x1800c6de4  lea     rcx, [rsp+120h+var_E8]
0x1800c6de9  mov     edi, eax
0x1800c6deb  test    eax, eax
0x1800c6ded  js      loc_1800C6D47
0x1800c6df3  mov     edi, r12d
0x1800c6df6  jmp     loc_1800C6D47
0x1800c6dfb  mov     r10, [rsp+120h+var_F0]
0x1800c6e00  test    r10, r10
0x1800c6e03  jz      short loc_1800C6E5F
0x1800c6e05  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800c6e0c  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c6e13  mov     dword ptr [rsp+120h+var_D8], 0C00000E5h
0x1800c6e1b  mov     qword ptr [rsp+120h+var_E8], rax
0x1800c6e20  test    r11, r11
0x1800c6e23  jz      short loc_1800C6EA3
0x1800c6e25  mov     rdx, r11
0x1800c6e28  mov     rcx, r10
0x1800c6e2b  call    RtlIsTypeSafeHandleValid
0x1800c6e30  test    al, al
0x1800c6e32  jz      short loc_1800C6EA3
0x1800c6e34  mov     ecx, [r11]
0x1800c6e37  mov     rdx, r10
0x1800c6e3a  mov     rax, [r11+20h]
0x1800c6e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e43  mov     ecx, r12d; dwExceptionCode
0x1800c6e46  test    ecx, ecx
0x1800c6e48  jns     short loc_1800C6E5A
0x1800c6e4a  xor     r9d, r9d; lpArguments
0x1800c6e4d  xor     r8d, r8d; nNumberOfArguments
0x1800c6e50  lea     edx, [r9+1]; dwExceptionFlags
0x1800c6e54  call    cs:__imp_RaiseException
0x1800c6e5a  mov     [rsp+120h+var_F0], r12
0x1800c6e5f  mov     rcx, [rbp+57h+var_88]
0x1800c6e63  cmp     rcx, [rbp+57h+var_90]
0x1800c6e67  cmovb   rcx, [rbp+57h+var_90]
0x1800c6e6c  mov     [rbp+57h+var_88], rcx
0x1800c6e70  lea     rcx, [rbp+57h+var_A0]
0x1800c6e74  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_DEFINITION_APPID@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800c6e79  mov     eax, edi
0x1800c6e7b  mov     rcx, [rbp+57h+var_30]
0x1800c6e7f  xor     rcx, rsp; StackCookie
0x1800c6e82  call    __security_check_cookie
0x1800c6e87  lea     r11, [rsp+120h+var_20]
0x1800c6e8f  mov     rbx, [r11+40h]
0x1800c6e93  mov     rsi, [r11+48h]
0x1800c6e97  mov     rsp, r11
0x1800c6e9a  pop     r15
0x1800c6e9c  pop     r13
0x1800c6e9e  pop     r12
0x1800c6ea0  pop     rdi
0x1800c6ea1  pop     rbp
0x1800c6ea2  retn
0x1800c6ea3  mov     dword ptr [rsp+120h+var_E8+8], 124h
  ... truncated ...
```
