# CEffectRegistry::RegisterParameterizedEffect(_GUID const &,uchar const *,uint,EFFECT_REGISTRATION_TYPE,DebugSink *)

- ea: `0x1801d59d0`
- end: `0x1801d5b26`
- name: `?RegisterParameterizedEffect@CEffectRegistry@@UEAAJAEBU_GUID@@PEBEIW4EFFECT_REGISTRATION_TYPE@@PEAVDebugSink@@@Z`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x1800b067c`
- `0x1800b0b28`
- `0x1801a043c`
- `0x1801d3c04`
- `0x1801d59d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1801d5a8c`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1801d5a8c`

## string_xrefs

- `0x1801d5a74`: `ParameterizedEffect.XML`

## pseudocode

```c
__int64 __fastcall CEffectRegistry::RegisterParameterizedEffect(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rax
  int v12; // ecx
  struct IStream *v14; // rbx
  HRSRC Resource; // rax
  int LastErrorAsFailHr; // eax
  unsigned int v17; // edi
  int v18; // ecx
  int v19; // eax
  __int64 v20; // [rsp+40h] [rbp-28h] BYREF
  int v21; // [rsp+48h] [rbp-20h]
  int v22; // [rsp+4Ch] [rbp-1Ch]
  __int64 v23; // [rsp+50h] [rbp-18h]
  unsigned int v24; // [rsp+58h] [rbp-10h]
  struct IStream *v25; // [rsp+A0h] [rbp+38h] BYREF

  v23 = 0;
  v24 = -1;
  v21 = -1;
  v20 = 0;
  v9 = CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::Find<_GUID,CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::CGenericIterator<CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::CGenericIterator<CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>,CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::CGenericIterator<CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>(
         a1 + 8,
         a2,
         &v20);
  v10 = v9;
  if ( !v9 )
  {
    v11 = *(_QWORD *)(*(_QWORD *)(v23 + 24) + 8LL * v24);
    if ( *(_BYTE *)(v11 + 28) && *(_DWORD *)(v11 + 48) == a4 )
      goto LABEL_6;
    v10 = -2147024809;
    v12 = -2147024809;
LABEL_4:
    DoStackCapture(v12);
LABEL_7:
    DoStackCapture(v10);
    return (unsigned int)v10;
  }
  if ( v9 == -2147023728 )
  {
    v10 = 0;
    goto LABEL_6;
  }
  if ( v9 < 0 )
  {
    v12 = v9;
    goto LABEL_4;
  }
LABEL_6:
  if ( v10 < 0 )
    goto LABEL_7;
  v14 = 0;
  v22 = 0;
  v20 = a3;
  v21 = a4;
  v25 = 0;
  Resource = FindResourceExW(&_ImageBase, (LPCWSTR)0x17, L"ParameterizedEffect.XML", 0);
  if ( Resource )
  {
    LastErrorAsFailHr = CreateStreamFromResourceHandle(&_ImageBase, Resource, &v25);
    v17 = LastErrorAsFailHr;
    if ( LastErrorAsFailHr < 0 )
    {
LABEL_16:
      DoStackCapture(LastErrorAsFailHr);
      v18 = v17;
LABEL_20:
      DoStackCapture(v18);
      goto LABEL_21;
    }
    v14 = v25;
  }
  else
  {
    LastErrorAsFailHr = GetLastErrorAsFailHr();
    v17 = LastErrorAsFailHr;
    if ( LastErrorAsFailHr < 0 )
      goto LABEL_16;
  }
  v19 = CEffectRegistry::RegisterEffectFromStreamInternal(
          a1,
          a2,
          v14,
          0,
          0,
          CEffectBaseT<ID2D1EffectImpl>::Create<CParameterizedEffect>,
          &v20,
          a5);
  v17 = v19;
  if ( v19 < 0 )
  {
    v18 = v19;
    goto LABEL_20;
  }
LABEL_21:
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v25);
  return v17;
}

```

## disassembly

```asm
0x1801d59d0  push    rbp
0x1801d59d2  push    rbx
0x1801d59d3  push    rsi
0x1801d59d4  push    rdi
0x1801d59d5  push    r14
0x1801d59d7  push    r15
0x1801d59d9  mov     rbp, rsp
0x1801d59dc  sub     rsp, 68h
0x1801d59e0  or      eax, 0FFFFFFFFh
0x1801d59e3  mov     [rbp+var_18], 0
0x1801d59eb  mov     rsi, r8
0x1801d59ee  mov     [rbp+var_10], eax
0x1801d59f1  mov     r15, rcx
0x1801d59f4  mov     [rbp+var_20], eax
0x1801d59f7  add     rcx, 8
0x1801d59fb  mov     [rbp+var_28], 0
0x1801d5a03  lea     r8, [rbp+var_28]
0x1801d5a07  mov     edi, r9d
0x1801d5a0a  mov     r14, rdx
0x1801d5a0d  call    ??$Find@U_GUID@@V?$CHash@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@V?$CGenericIterator@V?$CHash@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@V?$CGenericIterator@V?$CMap@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@?$CMap@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@2@V?$CGenericIterator@V?$CMap@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@?$CMap@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@@?$CHash@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@KAJPEAV0@AEBU_GUID@@PEAV?$CGenericIterator@V?$CHash@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@V?$CGenericIterator@V?$CMap@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@?$CMap@U_GUID@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@V?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@@@@V?$CAutoPtr@UD2D1_EFFECT_REGISTRATION@CEffectRegistry@@@@@0@@Z; CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::Find<_GUID,CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::CGenericIterator<CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::CGenericIterator<CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>,CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::CGenericIterator<CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>(CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>> *,_GUID const &,CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::CGenericIterator<CHash<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>::CGenericIterator<CMap<_GUID,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>,CDefaultTraits<_GUID>,CDefaultTraits<CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>>,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>>,CAutoPtr<CEffectRegistry::D2D1_EFFECT_REGISTRATION>> *)
0x1801d5a12  mov     ebx, eax
0x1801d5a14  test    eax, eax
0x1801d5a16  jnz     short loc_1801D5A51
0x1801d5a18  mov     rax, [rbp+var_18]
0x1801d5a1c  mov     edx, [rbp+var_10]
0x1801d5a1f  mov     rcx, [rax+18h]
0x1801d5a23  mov     rax, [rcx+rdx*8]
0x1801d5a27  cmp     [rax+1Ch], bl
0x1801d5a2a  jnz     short loc_1801D5A3A
0x1801d5a2c  mov     ebx, 80070057h
0x1801d5a31  mov     ecx, ebx; int
0x1801d5a33  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801d5a38  jmp     short loc_1801D5A43
0x1801d5a3a  cmp     [rax+30h], edi
0x1801d5a3d  jnz     short loc_1801D5A2C
0x1801d5a3f  test    ebx, ebx
0x1801d5a41  jns     short loc_1801D5A64
0x1801d5a43  mov     ecx, ebx; int
0x1801d5a45  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801d5a4a  mov     eax, ebx
0x1801d5a4c  jmp     loc_1801D5B19
0x1801d5a51  cmp     eax, 80070490h
0x1801d5a56  jnz     short loc_1801D5A5C
0x1801d5a58  xor     ebx, ebx
0x1801d5a5a  jmp     short loc_1801D5A3F
0x1801d5a5c  test    eax, eax
0x1801d5a5e  jns     short loc_1801D5A3F
0x1801d5a60  mov     ecx, eax
0x1801d5a62  jmp     short loc_1801D5A33
0x1801d5a64  xor     ebx, ebx
0x1801d5a66  mov     [rbp+var_1C], 0
0x1801d5a6d  xor     r9d, r9d; wLanguage
0x1801d5a70  mov     [rbp+var_28], rsi
0x1801d5a74  lea     r8, aParameterizede; "ParameterizedEffect.XML"
0x1801d5a7b  mov     [rbp+var_20], edi
0x1801d5a7e  lea     rcx, __ImageBase; hModule
0x1801d5a85  mov     [rbp+arg_0], rbx
0x1801d5a89  lea     edx, [rbx+17h]; lpType
0x1801d5a8c  call    cs:__imp_FindResourceExW
0x1801d5a92  test    rax, rax
0x1801d5a95  jnz     short loc_1801D5AA4
0x1801d5a97  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x1801d5a9c  mov     edi, eax
0x1801d5a9e  test    eax, eax
0x1801d5aa0  jns     short loc_1801D5ACC
0x1801d5aa2  jmp     short loc_1801D5ABD
0x1801d5aa4  lea     r8, [rbp+arg_0]; struct IStream **
0x1801d5aa8  mov     rdx, rax; hResInfo
0x1801d5aab  lea     rcx, __ImageBase; hModule
0x1801d5ab2  call    ?CreateStreamFromResourceHandle@@YAJPEAUHINSTANCE__@@PEAUHRSRC__@@PEAPEAUIStream@@@Z; CreateStreamFromResourceHandle(HINSTANCE__ *,HRSRC__ *,IStream * *)
0x1801d5ab7  mov     edi, eax
0x1801d5ab9  test    eax, eax
0x1801d5abb  jns     short loc_1801D5AC8
0x1801d5abd  mov     ecx, eax; int
0x1801d5abf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801d5ac4  mov     ecx, edi
0x1801d5ac6  jmp     short loc_1801D5B09
0x1801d5ac8  mov     rbx, [rbp+arg_0]
0x1801d5acc  mov     eax, [rbp+arg_20]
0x1801d5acf  xor     r9d, r9d
0x1801d5ad2  mov     [rsp+68h+var_30], eax
0x1801d5ad6  mov     r8, rbx
0x1801d5ad9  lea     rax, [rbp+var_28]
0x1801d5add  mov     rdx, r14
0x1801d5ae0  mov     [rsp+68h+var_38], rax
0x1801d5ae5  mov     rcx, r15
0x1801d5ae8  lea     rax, ??$Create@VCParameterizedEffect@@@?$CEffectBaseT@UID2D1EffectImpl@@@@SAJPEAPEAUIUnknown@@@Z; CEffectBaseT<ID2D1EffectImpl>::Create<CParameterizedEffect>(IUnknown * *)
0x1801d5aef  mov     [rsp+68h+var_40], rax
0x1801d5af4  mov     [rsp+68h+var_48], 0
0x1801d5afc  call    ?RegisterEffectFromStreamInternal@CEffectRegistry@@AEAAJAEBU_GUID@@PEAUIStream@@PEBUD2D1_PROPERTY_BINDING@@IQ6AJPEAPEAUIUnknown@@@ZPEBUD2D1_PARAMETERIZED_EFFECT_REGISTER_PROPERTIES@1@W4EFFECT_REGISTRATION_TYPE@@@Z; CEffectRegistry::RegisterEffectFromStreamInternal(_GUID const &,IStream *,D2D1_PROPERTY_BINDING const *,uint,long (*const)(IUnknown * *),CEffectRegistry::D2D1_PARAMETERIZED_EFFECT_REGISTER_PROPERTIES const *,EFFECT_REGISTRATION_TYPE)
0x1801d5b01  mov     edi, eax
0x1801d5b03  test    eax, eax
0x1801d5b05  jns     short loc_1801D5B0E
0x1801d5b07  mov     ecx, eax; int
0x1801d5b09  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801d5b0e  lea     rcx, [rbp+arg_0]; void *
0x1801d5b12  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1801d5b17  mov     eax, edi
0x1801d5b19  add     rsp, 68h
0x1801d5b1d  pop     r15
0x1801d5b1f  pop     r14
0x1801d5b21  pop     rdi
0x1801d5b22  pop     rsi
0x1801d5b23  pop     rbx
0x1801d5b24  pop     rbp
0x1801d5b25  retn
```
