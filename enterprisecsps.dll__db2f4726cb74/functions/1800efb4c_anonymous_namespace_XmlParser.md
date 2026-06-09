# _anonymous_namespace_::XmlParser

- ea: `0x1800efb4c`
- end: `0x1800efef3`
- name: `_anonymous_namespace_::XmlParser`
- size: `935`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ef1a0`
- `0x1800ef640`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x180022e10`
- `0x180055e74`
- `0x18005f668`
- `0x1800d7e58`
- `0x1800efb4c`
- `0x180107010`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800efd7c`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800efd7c`
- `XmlLite!CreateXmlReader` at `0x1800efca6`
- `XmlLite!CreateXmlReader` at `0x1800efca6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800efc59`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800efc59`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800efbaf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800efcf9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800efbaf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800efcf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::XmlParser(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 (__fastcall *a3)(__int64, _QWORD, __int64))
{
  int v6; // eax
  int v7; // edi
  __int64 v9; // rdx
  IStream *v10; // rax
  IUnknown *v11; // rdi
  HRESULT v12; // ebx
  __int64 v13; // rdx
  HRESULT v14; // eax
  int pwszBaseUri; // [rsp+20h] [rbp-50h]
  unsigned int v16; // [rsp+30h] [rbp-40h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-38h] BYREF
  IXmlReaderInput *ppInput; // [rsp+40h] [rbp-30h] BYREF
  IUnknown *v19; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp-18h] BYREF
  UINT cbInit[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v24; // [rsp+A8h] [rbp+38h] BYREF
  int v25; // [rsp+B8h] [rbp+48h] BYREF

  if ( !a2 || !*a2 )
  {
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)0x80070057LL,
      pwszBaseUri);
    return (unsigned int)v12;
  }
  v24 = 0;
  v6 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v24, (unsigned int)a2);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v6,
      pwszBaseUri);
LABEL_5:
    if ( v24 )
      CoUninitialize();
    return (unsigned int)v7;
  }
  ppvObject = 0;
  v19 = 0;
  ppInput = 0;
  v16 = 0;
  v21 = 0;
  *(_QWORD *)cbInit = 0;
  v20 = 0;
  v25 = 0;
  v7 = StringCchLengthW(a2, 0x7FFFFFFFu, &v21);
  if ( v7 < 0 )
  {
    v9 = 107;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v7,
      pwszBaseUri);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppInput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    goto LABEL_5;
  }
  v7 = ULongLongMult(v21, 2u, (unsigned __int64 *)cbInit);
  if ( v7 < 0 )
  {
    v9 = 108;
    goto LABEL_10;
  }
  v10 = SHCreateMemStream((const BYTE *)a2, cbInit[0]);
  v11 = (IUnknown *)v10;
  if ( !v10 )
  {
    v12 = -2147024882;
    v13 = 112;
    goto LABEL_16;
  }
  v21 = (unsigned __int64)v10;
  Microsoft::WRL::ComPtr<IConfigNode>::InternalAddRef(&v21);
  v21 = 0;
  v19 = v11;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
  v12 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v12 < 0 )
  {
    v13 = 115;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)(unsigned int)v12,
      pwszBaseUri);
    goto LABEL_17;
  }
  v12 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
  if ( v12 < 0 )
  {
    v13 = 116;
    goto LABEL_16;
  }
  v12 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  if ( v12 < 0 )
  {
    v13 = 117;
    goto LABEL_16;
  }
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppInput);
  v12 = CreateXmlReaderInputWithEncodingName(v11, 0, L"UTF-16", 0, 0, &ppInput);
  if ( v12 < 0 )
  {
    v13 = 118;
    goto LABEL_16;
  }
  v12 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
  if ( v12 < 0 )
  {
    v13 = 119;
    goto LABEL_16;
  }
  while ( 1 )
  {
    v14 = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v16);
    if ( v14 )
      break;
    switch ( v16 )
    {
      case 1u:
        if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
        {
          v12 = (*(__int64 (__fastcall **)(void *, __int64 *, int *))(*(_QWORD *)ppvObject + 112LL))(
                  ppvObject,
                  &v20,
                  &v25);
          if ( v12 < 0 )
          {
            v13 = 134;
            goto LABEL_16;
          }
          goto LABEL_37;
        }
        break;
      case 3u:
        v12 = (*(__int64 (__fastcall **)(void *, __int64 *, int *))(*(_QWORD *)ppvObject + 128LL))(
                ppvObject,
                &v20,
                &v25);
        if ( v12 < 0 )
        {
          v13 = 144;
          goto LABEL_16;
        }
LABEL_37:
        v12 = a3(a1, v16, v20);
        if ( v12 < 0 )
        {
          v13 = 157;
          goto LABEL_16;
        }
        break;
      case 0xFu:
        v12 = (*(__int64 (__fastcall **)(void *, __int64 *, int *))(*(_QWORD *)ppvObject + 112LL))(
                ppvObject,
                &v20,
                &v25);
        if ( v12 < 0 )
        {
          v13 = 139;
          goto LABEL_16;
        }
        goto LABEL_37;
    }
  }
  v12 = 0;
  if ( v14 != 1 )
    v12 = v14;
LABEL_17:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppInput);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
  if ( v24 )
    CoUninitialize();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800efb4c  mov     [rsp-28h+arg_0], rbx
0x1800efb51  push    rbp
0x1800efb52  push    rsi
0x1800efb53  push    rdi
0x1800efb54  push    r14
0x1800efb56  push    r15
0x1800efb58  mov     rbp, rsp
0x1800efb5b  sub     rsp, 70h
0x1800efb5f  mov     rsi, r8
0x1800efb62  mov     rbx, rdx
0x1800efb65  mov     r14, rcx
0x1800efb68  xor     r15d, r15d
0x1800efb6b  test    rdx, rdx
0x1800efb6e  jz      loc_1800EFEBF
0x1800efb74  cmp     r15w, [rdx]
0x1800efb78  jz      loc_1800EFEBF
0x1800efb7e  mov     [rbp+arg_8], r15d
0x1800efb82  lea     rcx, [rbp+arg_8]; this
0x1800efb86  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800efb8b  mov     edi, eax
0x1800efb8d  test    eax, eax
0x1800efb8f  jns     short loc_1800EFBC2
0x1800efb91  mov     rcx, [rbp+28h]; this
0x1800efb95  mov     r9d, eax; char *
0x1800efb98  lea     r8, aOnecoreuapAdmi_97; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800efb9f  lea     edx, [r15+5Eh]; void *
0x1800efba3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efba8  nop
0x1800efba9  cmp     [rbp+arg_8], r15d
0x1800efbad  jz      short loc_1800EFBBB
0x1800efbaf  call    cs:__imp_CoUninitialize
0x1800efbb6  nop     dword ptr [rax+rax+00h]
0x1800efbbb  mov     eax, edi
0x1800efbbd  jmp     loc_1800EFEDE
0x1800efbc2  mov     [rbp+ppvObject], r15
0x1800efbc6  mov     [rbp+var_28], r15
0x1800efbca  mov     [rbp+var_30], r15
0x1800efbce  mov     [rbp+var_40], r15d
0x1800efbd2  mov     [rbp+var_18], r15
0x1800efbd6  mov     qword ptr [rbp+cbInit], r15
0x1800efbda  mov     [rbp+var_20], r15
0x1800efbde  mov     [rbp+arg_18], r15d
0x1800efbe2  lea     r8, [rbp+var_18]; unsigned __int64 *
0x1800efbe6  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800efbeb  mov     rcx, rbx; unsigned __int16 *
0x1800efbee  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800efbf3  mov     edi, eax
0x1800efbf5  test    eax, eax
0x1800efbf7  jns     short loc_1800EFC34
0x1800efbf9  mov     edx, 6Bh ; 'k'; void *
0x1800efbfe  lea     r8, aOnecoreuapAdmi_97; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800efc05  mov     r9d, edi; char *
0x1800efc08  mov     rcx, [rbp+28h]; this
0x1800efc0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efc11  nop
0x1800efc12  lea     rcx, [rbp+var_30]
0x1800efc16  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800efc1b  nop
0x1800efc1c  lea     rcx, [rbp+var_28]
0x1800efc20  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800efc25  nop
0x1800efc26  lea     rcx, [rbp+ppvObject]
0x1800efc2a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800efc2f  jmp     loc_1800EFBA9
0x1800efc34  lea     r8, [rbp+cbInit]; unsigned __int64 *
0x1800efc38  mov     edx, 2; unsigned __int64
0x1800efc3d  mov     rcx, [rbp+var_18]; unsigned __int64
0x1800efc41  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800efc46  mov     edi, eax
0x1800efc48  test    eax, eax
0x1800efc4a  jns     short loc_1800EFC53
0x1800efc4c  mov     edx, 6Ch ; 'l'
0x1800efc51  jmp     short loc_1800EFBFE
0x1800efc53  mov     edx, [rbp+cbInit]; cbInit
0x1800efc56  mov     rcx, rbx; pInit
0x1800efc59  call    cs:__imp_SHCreateMemStream
0x1800efc60  nop     dword ptr [rax+rax+00h]
0x1800efc65  mov     rdi, rax
0x1800efc68  test    rax, rax
0x1800efc6b  jz      loc_1800EFEB0
0x1800efc71  mov     [rbp+var_18], rax
0x1800efc75  lea     rcx, [rbp+var_18]
0x1800efc79  call    ?InternalAddRef@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalAddRef(void)
0x1800efc7e  mov     [rbp+var_18], r15
0x1800efc82  mov     [rbp+var_28], rdi
0x1800efc86  lea     rcx, [rbp+var_18]
0x1800efc8a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800efc8f  lea     rcx, [rbp+ppvObject]
0x1800efc93  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800efc98  xor     r8d, r8d; pMalloc
0x1800efc9b  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800efc9f  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800efca6  call    cs:__imp_CreateXmlReader
0x1800efcad  nop     dword ptr [rax+rax+00h]
0x1800efcb2  mov     ebx, eax
0x1800efcb4  test    eax, eax
0x1800efcb6  jns     short loc_1800EFD0A
0x1800efcb8  mov     edx, 73h ; 's'; void *
0x1800efcbd  lea     r8, aOnecoreuapAdmi_97; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800efcc4  mov     r9d, ebx; char *
0x1800efcc7  mov     rcx, [rbp+28h]; this
0x1800efccb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efcd0  nop
0x1800efcd1  lea     rcx, [rbp+var_30]
0x1800efcd5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800efcda  nop
0x1800efcdb  lea     rcx, [rbp+var_28]
0x1800efcdf  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800efce4  nop
0x1800efce5  lea     rcx, [rbp+ppvObject]
0x1800efce9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800efcee  nop
0x1800efcef  cmp     [rbp+arg_8], r15d
0x1800efcf3  jz      loc_1800EFEDC
0x1800efcf9  call    cs:__imp_CoUninitialize
0x1800efd00  nop     dword ptr [rax+rax+00h]
0x1800efd05  jmp     loc_1800EFEDC
0x1800efd0a  mov     rcx, [rbp+ppvObject]
0x1800efd0e  mov     rax, [rcx]
0x1800efd11  mov     edx, 1
0x1800efd16  mov     r8d, edx
0x1800efd19  mov     rax, [rax+28h]
0x1800efd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd22  mov     ebx, eax
0x1800efd24  test    eax, eax
0x1800efd26  jns     short loc_1800EFD2F
0x1800efd28  mov     edx, 74h ; 't'
0x1800efd2d  jmp     short loc_1800EFCBD
0x1800efd2f  mov     rcx, [rbp+ppvObject]
0x1800efd33  mov     rax, [rcx]
0x1800efd36  xor     r8d, r8d
0x1800efd39  lea     edx, [r8+4]
0x1800efd3d  mov     rax, [rax+28h]
0x1800efd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd46  mov     ebx, eax
0x1800efd48  test    eax, eax
0x1800efd4a  jns     short loc_1800EFD56
0x1800efd4c  mov     edx, 75h ; 'u'
0x1800efd51  jmp     loc_1800EFCBD
0x1800efd56  lea     rcx, [rbp+var_30]
0x1800efd5a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800efd5f  lea     rax, [rbp+var_30]
0x1800efd63  mov     [rsp+70h+ppInput], rax; ppInput
0x1800efd68  mov     [rsp+70h+pwszBaseUri], r15; pwszBaseUri
0x1800efd6d  xor     r9d, r9d; fEncodingHint
0x1800efd70  lea     r8, pwszEncodingName; "UTF-16"
0x1800efd77  xor     edx, edx; pMalloc
0x1800efd79  mov     rcx, rdi; pInputStream
0x1800efd7c  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x1800efd83  nop     dword ptr [rax+rax+00h]
0x1800efd88  mov     ebx, eax
0x1800efd8a  test    eax, eax
0x1800efd8c  jns     short loc_1800EFD98
0x1800efd8e  mov     edx, 76h ; 'v'
0x1800efd93  jmp     loc_1800EFCBD
0x1800efd98  mov     rcx, [rbp+ppvObject]
0x1800efd9c  mov     rax, [rcx]
0x1800efd9f  mov     rdx, [rbp+var_30]
0x1800efda3  mov     rax, [rax+18h]
0x1800efda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efdac  mov     ebx, eax
0x1800efdae  test    eax, eax
0x1800efdb0  jns     short loc_1800EFDBC
0x1800efdb2  mov     edx, 77h ; 'w'
0x1800efdb7  jmp     loc_1800EFCBD
0x1800efdbc  mov     rcx, [rbp+ppvObject]
0x1800efdc0  mov     rax, [rcx]
0x1800efdc3  lea     rdx, [rbp+var_40]
0x1800efdc7  mov     rax, [rax+30h]
0x1800efdcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efdd0  test    eax, eax
0x1800efdd2  jnz     loc_1800EFEA2
0x1800efdd8  mov     ecx, [rbp+var_40]
0x1800efddb  sub     ecx, 1
0x1800efdde  jnz     short loc_1800EFE1F
0x1800efde0  mov     rcx, [rbp+ppvObject]
0x1800efde4  mov     rax, [rcx]
0x1800efde7  mov     rax, [rax+0A0h]
0x1800efdee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efdf3  test    eax, eax
0x1800efdf5  jnz     short loc_1800EFDBC
0x1800efdf7  mov     rcx, [rbp+ppvObject]
0x1800efdfb  mov     rax, [rcx]
0x1800efdfe  lea     r8, [rbp+arg_18]
0x1800efe02  lea     rdx, [rbp+var_20]
0x1800efe06  mov     rax, [rax+70h]
0x1800efe0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe0f  mov     ebx, eax
0x1800efe11  test    eax, eax
0x1800efe13  jns     short loc_1800EFE72
0x1800efe15  mov     edx, 86h
0x1800efe1a  jmp     loc_1800EFCBD
0x1800efe1f  sub     ecx, 2
0x1800efe22  jz      short loc_1800EFE51
0x1800efe24  cmp     ecx, 0Ch
0x1800efe27  jnz     short loc_1800EFDBC
0x1800efe29  mov     rcx, [rbp+ppvObject]
0x1800efe2d  mov     rax, [rcx]
0x1800efe30  lea     r8, [rbp+arg_18]
0x1800efe34  lea     rdx, [rbp+var_20]
0x1800efe38  mov     rax, [rax+70h]
0x1800efe3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe41  mov     ebx, eax
0x1800efe43  test    eax, eax
0x1800efe45  jns     short loc_1800EFE72
0x1800efe47  mov     edx, 8Bh
0x1800efe4c  jmp     loc_1800EFCBD
0x1800efe51  mov     rcx, [rbp+ppvObject]
0x1800efe55  mov     rax, [rcx]
0x1800efe58  lea     r8, [rbp+arg_18]
0x1800efe5c  lea     rdx, [rbp+var_20]
0x1800efe60  mov     rax, [rax+80h]
0x1800efe67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe6c  mov     ebx, eax
0x1800efe6e  test    eax, eax
0x1800efe70  js      short loc_1800EFE98
0x1800efe72  mov     r8, [rbp+var_20]
0x1800efe76  mov     edx, [rbp+var_40]
0x1800efe79  mov     rcx, r14
0x1800efe7c  mov     rax, rsi
0x1800efe7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe84  mov     ebx, eax
0x1800efe86  test    eax, eax
0x1800efe88  jns     loc_1800EFDBC
0x1800efe8e  mov     edx, 9Dh
0x1800efe93  jmp     loc_1800EFCBD
0x1800efe98  mov     edx, 90h
0x1800efe9d  jmp     loc_1800EFCBD
0x1800efea2  mov     ebx, r15d
0x1800efea5  cmp     eax, 1
0x1800efea8  cmovnz  ebx, eax
0x1800efeab  jmp     loc_1800EFCD1
0x1800efeb0  mov     ebx, 8007000Eh
0x1800efeb5  mov     edx, 70h ; 'p'
0x1800efeba  jmp     loc_1800EFCBD
0x1800efebf  mov     rcx, [rbp+28h]; this
0x1800efec3  mov     ebx, 80070057h
0x1800efec8  mov     r9d, ebx; char *
0x1800efecb  lea     r8, aOnecoreuapAdmi_97; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800efed2  mov     edx, 5Bh ; '['; void *
0x1800efed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efedc  mov     eax, ebx
0x1800efede  mov     rbx, [rsp+70h+arg_0]
0x1800efee6  add     rsp, 70h
0x1800efeea  pop     r15
0x1800efeec  pop     r14
0x1800efeee  pop     rdi
0x1800efeef  pop     rsi
0x1800efef0  pop     rbp
0x1800efef1  retn
```
