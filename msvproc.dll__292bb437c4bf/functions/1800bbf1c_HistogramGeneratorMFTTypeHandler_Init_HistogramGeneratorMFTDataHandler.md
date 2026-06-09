# HistogramGeneratorMFTTypeHandler::Init(HistogramGeneratorMFTDataHandler *)

- ea: `0x1800bbf1c`
- end: `0x1800bc050`
- name: `?Init@HistogramGeneratorMFTTypeHandler@@QEAAJPEAVHistogramGeneratorMFTDataHandler@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(HistogramGeneratorMFTTypeHandler *__hidden this, struct HistogramGeneratorMFTDataHandler *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bc058`

## callees

- `0x18000a09c`
- `0x18001bcd8`
- `0x18001ca80`
- `0x1800bbf1c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800bbf70`
- `MFPlat!MFCreateMediaType` at `0x1800bc027`
- `MFPlat!MFCreateMediaType` at `0x1800bbf70`
- `MFPlat!MFCreateMediaType` at `0x1800bc027`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HistogramGeneratorMFTTypeHandler::Init(
        HistogramGeneratorMFTTypeHandler *this,
        struct HistogramGeneratorMFTDataHandler *a2)
{
  HRESULT inited; // eax
  signed int i; // edi
  bool v5; // sf
  HRESULT (__stdcall *SetGUID)(IMFMediaType *, const GUID *const, const GUID *const); // rax
  unsigned int v7; // ebx
  IMFMediaType *ppMFType; // [rsp+50h] [rbp+8h] BYREF

  ppMFType = 0;
  *((_QWORD *)this + 1) = a2;
  if ( (int)CMFTSimpleTypeHandler::InitAvailableInputTypeArray(this, 4u) >= 0 )
  {
    for ( i = 0; (unsigned int)i < 4; ++i )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
      if ( MFCreateMediaType(&ppMFType) < 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
        inited = MFCreateMediaType(&ppMFType);
        goto LABEL_13;
      }
      v5 = ((int (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_MAJOR_TYPE,
             &MFMediaType_Video) < 0;
      SetGUID = ppMFType->lpVtbl->SetGUID;
      if ( v5 )
      {
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))SetGUID)(
                   ppMFType,
                   &MF_MT_MAJOR_TYPE,
                   &MFMediaType_Video);
        goto LABEL_13;
      }
      if ( ((int (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))SetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             *((_QWORD *)&HistogramGeneratorMFTTypeHandler::_supportedTypes.Data1 + i)) < 0 )
      {
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_SUBTYPE,
                   *((_QWORD *)&HistogramGeneratorMFTTypeHandler::_supportedTypes.Data1 + i));
        goto LABEL_13;
      }
      CMFTSimpleTypeHandler::SetAvailableInputType(this, i, ppMFType);
    }
    *((_DWORD *)this + 22) = 773;
    v7 = 0;
  }
  else
  {
    inited = CMFTSimpleTypeHandler::InitAvailableInputTypeArray(this, 4u);
LABEL_13:
    v7 = inited;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  return v7;
}

```

## disassembly

```asm
0x1800bbf1c  push    rbx
0x1800bbf1e  push    rsi
0x1800bbf1f  push    rdi
0x1800bbf20  push    r14
0x1800bbf22  sub     rsp, 28h
0x1800bbf26  mov     rbx, rcx
0x1800bbf29  mov     [rsp+48h+ppMFType], 0
0x1800bbf32  mov     [rcx+8], rdx
0x1800bbf36  mov     edx, 4; unsigned int
0x1800bbf3b  call    ?InitAvailableInputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableInputTypeArray(ulong)
0x1800bbf40  test    eax, eax
0x1800bbf42  jns     short loc_1800BBF56
0x1800bbf44  mov     edx, 4; unsigned int
0x1800bbf49  mov     rcx, rbx; this
0x1800bbf4c  call    ?InitAvailableInputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableInputTypeArray(ulong)
0x1800bbf51  jmp     loc_1800BC02D
0x1800bbf56  xor     edi, edi
0x1800bbf58  cmp     edi, 4
0x1800bbf5b  jnb     loc_1800BC031
0x1800bbf61  lea     rcx, [rsp+48h+ppMFType]
0x1800bbf66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bbf6b  lea     rcx, [rsp+48h+ppMFType]; ppMFType
0x1800bbf70  call    cs:__imp_MFCreateMediaType
0x1800bbf76  test    eax, eax
0x1800bbf78  js      loc_1800BC018
0x1800bbf7e  mov     rcx, [rsp+48h+ppMFType]
0x1800bbf83  mov     rax, [rcx]
0x1800bbf86  lea     r8, MFMediaType_Video
0x1800bbf8d  lea     rdx, MF_MT_MAJOR_TYPE
0x1800bbf94  mov     rax, [rax+0C0h]
0x1800bbf9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbfa0  mov     rcx, [rsp+48h+ppMFType]
0x1800bbfa5  test    eax, eax
0x1800bbfa7  mov     rax, [rcx]
0x1800bbfaa  mov     rax, [rax+0C0h]
0x1800bbfb1  js      short loc_1800BC003
0x1800bbfb3  movsxd  rsi, edi
0x1800bbfb6  lea     r14, ?_supportedTypes@HistogramGeneratorMFTTypeHandler@@0PAPEBU_GUID@@A; _GUID const * near * HistogramGeneratorMFTTypeHandler::_supportedTypes
0x1800bbfbd  mov     r8, [r14+rsi*8]
0x1800bbfc1  lea     rdx, MF_MT_SUBTYPE
0x1800bbfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbfcd  test    eax, eax
0x1800bbfcf  js      short loc_1800BBFE7
0x1800bbfd1  mov     r8, [rsp+48h+ppMFType]; struct IMFMediaType *
0x1800bbfd6  mov     edx, edi; unsigned int
0x1800bbfd8  mov     rcx, rbx; this
0x1800bbfdb  call    ?SetAvailableInputType@CMFTSimpleTypeHandler@@QEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleTypeHandler::SetAvailableInputType(ulong,IMFMediaType *)
0x1800bbfe0  inc     edi
0x1800bbfe2  jmp     loc_1800BBF58
0x1800bbfe7  mov     rcx, [rsp+48h+ppMFType]
0x1800bbfec  mov     rax, [rcx]
0x1800bbfef  mov     r8, [r14+rsi*8]
0x1800bbff3  lea     rdx, MF_MT_SUBTYPE
0x1800bbffa  mov     rax, [rax+0C0h]
0x1800bc001  jmp     short loc_1800BC011
0x1800bc003  lea     r8, MFMediaType_Video
0x1800bc00a  lea     rdx, MF_MT_MAJOR_TYPE
0x1800bc011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc016  jmp     short loc_1800BC02D
0x1800bc018  lea     rcx, [rsp+48h+ppMFType]
0x1800bc01d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc022  lea     rcx, [rsp+48h+ppMFType]; ppMFType
0x1800bc027  call    cs:__imp_MFCreateMediaType
0x1800bc02d  mov     ebx, eax
0x1800bc02f  jmp     short loc_1800BC03A
0x1800bc031  mov     dword ptr [rbx+58h], 305h
0x1800bc038  xor     ebx, ebx
0x1800bc03a  lea     rcx, [rsp+48h+ppMFType]
0x1800bc03f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc044  mov     eax, ebx
0x1800bc046  add     rsp, 28h
0x1800bc04a  pop     r14
0x1800bc04c  pop     rdi
0x1800bc04d  pop     rsi
0x1800bc04e  pop     rbx
0x1800bc04f  retn
```
