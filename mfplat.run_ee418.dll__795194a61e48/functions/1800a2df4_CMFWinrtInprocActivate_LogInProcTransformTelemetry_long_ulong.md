# CMFWinrtInprocActivate::LogInProcTransformTelemetry(long,ulong)

- ea: `0x1800a2df4`
- end: `0x1800a30b6`
- name: `?LogInProcTransformTelemetry@CMFWinrtInprocActivate@@AEAAXJK@Z`
- size: `706`
- prototype: `void __fastcall(CMFWinrtInprocActivate *__hidden this, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d890`

## callees

- `0x1800017a0`
- `0x180004870`
- `0x18003e350`
- `0x180073690`
- `0x180073790`
- `0x1800a0bdc`
- `0x1800a2df4`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a306c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3075`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a307e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a306c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3075`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a307e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3087`

## pseudocode

```c
void __fastcall CMFWinrtInprocActivate::LogInProcTransformTelemetry(CMFWinrtInprocActivate *this, int a2, int a3)
{
  int v3; // r15d
  __int64 v7; // rcx
  void *v8; // rbx
  void *v9; // rdi
  void *v10; // rsi
  void *v11; // r14
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v16; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v17; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v18; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  GUID *v20; // [rsp+A8h] [rbp-58h] BYREF
  void *v21; // [rsp+B0h] [rbp-50h] BYREF
  void *v22; // [rsp+B8h] [rbp-48h] BYREF
  void *v23; // [rsp+C0h] [rbp-40h] BYREF
  void *v24; // [rsp+C8h] [rbp-38h] BYREF
  GUID *v25; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v26[2]; // [rsp+D8h] [rbp-28h] BYREF
  GUID v27; // [rsp+E8h] [rbp-18h] BYREF
  GUID v28; // [rsp+F8h] [rbp-8h] BYREF
  GUID v29; // [rsp+108h] [rbp+8h] BYREF

  v3 = 0;
  v15 = 0;
  v28 = GUID_00000000_0000_0000_0000_000000000000;
  v27 = GUID_00000000_0000_0000_0000_000000000000;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  pv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetUnknown(
    this,
    &MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE,
    &GUID_627d2ca6_e1cd_4898_999d_101308f1d431,
    &v15);
  CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetGUID(this, &MF_TELEMETRY_OBJECT_INSTANCE_ATTRIBUTE, &v28);
  CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(
    this,
    &MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID,
    &v18,
    0);
  CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(
    this,
    &MF_MEDIA_EXTENSION_PACKAGE_FAMILY_NAME,
    &v17,
    0);
  CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(
    this,
    &MF_MEDIA_EXTENSION_PACKAGE_FULL_NAME,
    &v16,
    0);
  CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(this, &MF_MEDIA_EXTENSION_ARCHITECTURE, &pv, 0);
  CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetGUID(this, &MF_TRANSFORM_CATEGORY_Attribute, &v27);
  v7 = v15;
  v8 = v18;
  v9 = v17;
  v10 = v16;
  v11 = pv;
  if ( v15 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 320LL))(
           v15,
           &MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
    {
      goto LABEL_10;
    }
    v7 = v15;
  }
  v29 = GUID_00000000_0000_0000_0000_000000000000;
  if ( !v7
    || (v29 = *(GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 280LL))(v7, v26),
        v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 296LL))(v15),
        !v15)
    || !(*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v15 + 320LL))(
          v15,
          &MF_TELEMETRY_FLAG_THUMBNAIL_GENERATION) )
  {
    if ( (unsigned int)dword_1801F82D8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801F82D8, 0x400000000000LL) )
    {
      pv = (LPVOID)0x1000000;
      v20 = &v27;
      LODWORD(v16) = a3;
      v25 = &v28;
      v26[0] = &v29;
      v21 = v11;
      v22 = v10;
      v23 = v9;
      v24 = v8;
      LODWORD(v17) = a2;
      LODWORD(v18) = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v12,
        (unsigned int)&unk_1801E65F8,
        v13,
        v14,
        (__int64)v26,
        (__int64)&v18,
        (__int64)&v25,
        (__int64)&v17,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v16,
        (__int64)&pv);
    }
  }
LABEL_10:
  CoTaskMemFree(v11);
  CoTaskMemFree(v10);
  CoTaskMemFree(v9);
  CoTaskMemFree(v8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
}

```

## disassembly

```asm
0x1800a2df4  push    rbp
0x1800a2df6  push    rbx
0x1800a2df7  push    rsi
0x1800a2df8  push    rdi
0x1800a2df9  push    r12
0x1800a2dfb  push    r13
0x1800a2dfd  push    r14
0x1800a2dff  push    r15
0x1800a2e01  lea     rbp, [rsp-28h]
0x1800a2e06  sub     rsp, 128h
0x1800a2e0d  mov     rax, cs:__security_cookie
0x1800a2e14  xor     rax, rsp
0x1800a2e17  mov     [rbp+60h+var_48], rax
0x1800a2e1b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800a2e22  xor     r15d, r15d
0x1800a2e25  mov     rbx, rcx
0x1800a2e28  lea     rcx, [rbp+60h+var_E0]
0x1800a2e2c  mov     [rbp+60h+var_E0], r15
0x1800a2e30  movdqu  [rbp+60h+var_68], xmm0
0x1800a2e35  mov     r12d, r8d
0x1800a2e38  mov     r13d, edx
0x1800a2e3b  movdqu  [rbp+60h+var_78], xmm0
0x1800a2e40  mov     [rbp+60h+var_C8], r15
0x1800a2e44  mov     [rbp+60h+var_D0], r15
0x1800a2e48  mov     [rbp+60h+var_D8], r15
0x1800a2e4c  mov     [rbp+60h+pv], r15
0x1800a2e50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a2e55  lea     r9, [rbp+60h+var_E0]
0x1800a2e59  mov     rcx, rbx
0x1800a2e5c  lea     r8, _GUID_627d2ca6_e1cd_4898_999d_101308f1d431
0x1800a2e63  lea     rdx, MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE
0x1800a2e6a  call    ?GetUnknown@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@0PEAPEAX@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetUnknown(_GUID const &,_GUID const &,void * *)
0x1800a2e6f  lea     r8, [rbp+60h+var_68]
0x1800a2e73  mov     rcx, rbx
0x1800a2e76  lea     rdx, MF_TELEMETRY_OBJECT_INSTANCE_ATTRIBUTE
0x1800a2e7d  call    ?GetGUID@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAU2@@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetGUID(_GUID const &,_GUID *)
0x1800a2e82  xor     r9d, r9d
0x1800a2e85  lea     r8, [rbp+60h+var_C8]
0x1800a2e89  lea     rdx, MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID
0x1800a2e90  mov     rcx, rbx
0x1800a2e93  call    ?GetAllocatedString@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)
0x1800a2e98  xor     r9d, r9d
0x1800a2e9b  lea     r8, [rbp+60h+var_D0]
0x1800a2e9f  lea     rdx, MF_MEDIA_EXTENSION_PACKAGE_FAMILY_NAME
0x1800a2ea6  mov     rcx, rbx
0x1800a2ea9  call    ?GetAllocatedString@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)
0x1800a2eae  xor     r9d, r9d
0x1800a2eb1  lea     r8, [rbp+60h+var_D8]
0x1800a2eb5  lea     rdx, MF_MEDIA_EXTENSION_PACKAGE_FULL_NAME
0x1800a2ebc  mov     rcx, rbx
0x1800a2ebf  call    ?GetAllocatedString@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)
0x1800a2ec4  xor     r9d, r9d
0x1800a2ec7  lea     r8, [rbp+60h+pv]
0x1800a2ecb  lea     rdx, MF_MEDIA_EXTENSION_ARCHITECTURE
0x1800a2ed2  mov     rcx, rbx
0x1800a2ed5  call    ?GetAllocatedString@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)
0x1800a2eda  lea     r8, [rbp+60h+var_78]
0x1800a2ede  mov     rcx, rbx
0x1800a2ee1  lea     rdx, MF_TRANSFORM_CATEGORY_Attribute
0x1800a2ee8  call    ?GetGUID@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAU2@@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::GetGUID(_GUID const &,_GUID *)
0x1800a2eed  mov     rcx, [rbp+60h+var_E0]
0x1800a2ef1  mov     rbx, [rbp+60h+var_C8]
0x1800a2ef5  mov     rdi, [rbp+60h+var_D0]
0x1800a2ef9  mov     rsi, [rbp+60h+var_D8]
0x1800a2efd  mov     r14, [rbp+60h+pv]
0x1800a2f01  test    rcx, rcx
0x1800a2f04  jz      short loc_1800A2F28
0x1800a2f06  mov     rax, [rcx]
0x1800a2f09  lea     rdx, MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT
0x1800a2f10  mov     rax, [rax+140h]
0x1800a2f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f1c  test    eax, eax
0x1800a2f1e  jnz     loc_1800A3069
0x1800a2f24  mov     rcx, [rbp+60h+var_E0]
0x1800a2f28  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800a2f2f  movdqu  [rbp+60h+var_58], xmm0
0x1800a2f34  test    rcx, rcx
0x1800a2f37  jz      short loc_1800A2F91
0x1800a2f39  mov     rax, [rcx]
0x1800a2f3c  lea     rdx, [rbp+60h+var_88]
0x1800a2f40  mov     rax, [rax+118h]
0x1800a2f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f4c  mov     rcx, [rbp+60h+var_E0]
0x1800a2f50  movups  xmm0, xmmword ptr [rax]
0x1800a2f53  movdqu  [rbp+60h+var_58], xmm0
0x1800a2f58  mov     rax, [rcx]
0x1800a2f5b  mov     rax, [rax+128h]
0x1800a2f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f67  mov     rcx, [rbp+60h+var_E0]
0x1800a2f6b  mov     r15d, eax
0x1800a2f6e  test    rcx, rcx
0x1800a2f71  jz      short loc_1800A2F91
0x1800a2f73  mov     rdx, [rcx]
0x1800a2f76  mov     rax, [rdx+140h]
0x1800a2f7d  lea     rdx, MF_TELEMETRY_FLAG_THUMBNAIL_GENERATION
0x1800a2f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f89  test    eax, eax
0x1800a2f8b  jnz     loc_1800A3069
0x1800a2f91  mov     eax, cs:dword_1801F82D8
0x1800a2f97  cmp     eax, 4
0x1800a2f9a  jbe     loc_1800A3069
0x1800a2fa0  mov     rdx, 400000000000h
0x1800a2faa  lea     rcx, dword_1801F82D8
0x1800a2fb1  call    _tlgKeywordOn
0x1800a2fb6  test    al, al
0x1800a2fb8  jz      loc_1800A3069
0x1800a2fbe  lea     rax, [rbp+60h+var_78]
0x1800a2fc2  mov     [rbp+60h+pv], 1000000h
0x1800a2fca  mov     [rbp+60h+var_B8], rax
0x1800a2fce  lea     rdx, unk_1801E65F8
0x1800a2fd5  lea     rax, [rbp+60h+var_68]
0x1800a2fd9  mov     dword ptr [rbp+60h+var_D8], r12d
0x1800a2fdd  mov     [rbp+60h+var_90], rax
0x1800a2fe1  lea     rax, [rbp+60h+var_58]
0x1800a2fe5  mov     [rbp+60h+var_88], rax
0x1800a2fe9  lea     rax, [rbp+60h+pv]
0x1800a2fed  mov     [rsp+160h+var_F0], rax
0x1800a2ff2  lea     rax, [rbp+60h+var_D8]
0x1800a2ff6  mov     [rsp+160h+var_F8], rax
0x1800a2ffb  lea     rax, [rbp+60h+var_B8]
0x1800a2fff  mov     [rsp+160h+var_100], rax
0x1800a3004  lea     rax, [rbp+60h+var_B0]
0x1800a3008  mov     [rsp+160h+var_108], rax
0x1800a300d  lea     rax, [rbp+60h+var_A8]
0x1800a3011  mov     [rsp+160h+var_110], rax
0x1800a3016  lea     rax, [rbp+60h+var_A0]
0x1800a301a  mov     [rsp+160h+var_118], rax
0x1800a301f  lea     rax, [rbp+60h+var_98]
0x1800a3023  mov     [rsp+160h+var_120], rax
0x1800a3028  lea     rax, [rbp+60h+var_D0]
0x1800a302c  mov     [rsp+160h+var_128], rax
0x1800a3031  lea     rax, [rbp+60h+var_90]
0x1800a3035  mov     [rsp+160h+var_130], rax
0x1800a303a  lea     rax, [rbp+60h+var_C8]
0x1800a303e  mov     [rsp+160h+var_138], rax
0x1800a3043  lea     rax, [rbp+60h+var_88]
0x1800a3047  mov     [rsp+160h+var_140], rax
0x1800a304c  mov     [rbp+60h+var_B0], r14
0x1800a3050  mov     [rbp+60h+var_A8], rsi
0x1800a3054  mov     [rbp+60h+var_A0], rdi
0x1800a3058  mov     [rbp+60h+var_98], rbx
0x1800a305c  mov     dword ptr [rbp+60h+var_D0], r13d
0x1800a3060  mov     dword ptr [rbp+60h+var_C8], r15d
0x1800a3064  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapSz@G@@U3@U3@U3@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapSz@G@@55534AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800a3069  mov     rcx, r14; pv
0x1800a306c  call    cs:__imp_CoTaskMemFree
0x1800a3072  mov     rcx, rsi; pv
0x1800a3075  call    cs:__imp_CoTaskMemFree
0x1800a307b  mov     rcx, rdi; pv
0x1800a307e  call    cs:__imp_CoTaskMemFree
0x1800a3084  mov     rcx, rbx; pv
0x1800a3087  call    cs:__imp_CoTaskMemFree
0x1800a308d  lea     rcx, [rbp+60h+var_E0]
0x1800a3091  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a3096  mov     rcx, [rbp+60h+var_48]
0x1800a309a  xor     rcx, rsp; StackCookie
0x1800a309d  call    __security_check_cookie
0x1800a30a2  add     rsp, 128h
0x1800a30a9  pop     r15
0x1800a30ab  pop     r14
0x1800a30ad  pop     r13
0x1800a30af  pop     r12
0x1800a30b1  pop     rdi
0x1800a30b2  pop     rsi
0x1800a30b3  pop     rbx
0x1800a30b4  pop     rbp
0x1800a30b5  retn
```
