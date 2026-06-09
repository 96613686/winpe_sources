# HistogramGeneratorMFTTypeHandler::OnInputTypeChanged(void)

- ea: `0x1800bcbe0`
- end: `0x1800bcc98`
- name: `?OnInputTypeChanged@HistogramGeneratorMFTTypeHandler@@MEAAJXZ`
- size: `184`
- prototype: `__int64 __fastcall(HistogramGeneratorMFTTypeHandler *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a09c`
- `0x18001bc24`
- `0x180021d08`
- `0x1800bcbe0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800bcc1e`
- `MFPlat!MFCreateMediaType` at `0x1800bcc37`
- `MFPlat!MFCreateMediaType` at `0x1800bcc1e`
- `MFPlat!MFCreateMediaType` at `0x1800bcc37`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HistogramGeneratorMFTTypeHandler::OnInputTypeChanged(HistogramGeneratorMFTTypeHandler *this)
{
  HRESULT inited; // eax
  unsigned int v3; // ebx
  unsigned int v4; // edx
  IMFMediaType *ppMFType; // [rsp+38h] [rbp+10h] BYREF

  ppMFType = 0;
  if ( (int)CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(this, 1u) >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
    if ( MFCreateMediaType(&ppMFType) >= 0 )
    {
      if ( (*(int (__fastcall **)(_QWORD, IMFMediaType *))(**((_QWORD **)this + 6) + 256LL))(
             *((_QWORD *)this + 6),
             ppMFType) >= 0 )
      {
        CMFTSimpleTypeHandler::SetAvailableOutputType(this, v4, ppMFType);
        v3 = 0;
        goto LABEL_9;
      }
      inited = (*(__int64 (__fastcall **)(_QWORD, IMFMediaType *))(**((_QWORD **)this + 6) + 256LL))(
                 *((_QWORD *)this + 6),
                 ppMFType);
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
      inited = MFCreateMediaType(&ppMFType);
    }
  }
  else
  {
    inited = CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(this, 1u);
  }
  v3 = inited;
LABEL_9:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  return v3;
}

```

## disassembly

```asm
0x1800bcbe0  push    rbx
0x1800bcbe2  sub     rsp, 20h
0x1800bcbe6  mov     rbx, rcx
0x1800bcbe9  mov     [rsp+28h+ppMFType], 0
0x1800bcbf2  mov     edx, 1; unsigned int
0x1800bcbf7  call    ?InitAvailableOutputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(ulong)
0x1800bcbfc  test    eax, eax
0x1800bcbfe  jns     short loc_1800BCC0F
0x1800bcc00  mov     edx, 1; unsigned int
0x1800bcc05  mov     rcx, rbx; this
0x1800bcc08  call    ?InitAvailableOutputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(ulong)
0x1800bcc0d  jmp     short loc_1800BCC3D
0x1800bcc0f  lea     rcx, [rsp+28h+ppMFType]
0x1800bcc14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bcc19  lea     rcx, [rsp+28h+ppMFType]; ppMFType
0x1800bcc1e  call    cs:__imp_MFCreateMediaType
0x1800bcc24  test    eax, eax
0x1800bcc26  jns     short loc_1800BCC41
0x1800bcc28  lea     rcx, [rsp+28h+ppMFType]
0x1800bcc2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bcc32  lea     rcx, [rsp+28h+ppMFType]; ppMFType
0x1800bcc37  call    cs:__imp_MFCreateMediaType
0x1800bcc3d  mov     ebx, eax
0x1800bcc3f  jmp     short loc_1800BCC86
0x1800bcc41  mov     rcx, [rbx+30h]
0x1800bcc45  mov     rax, [rcx]
0x1800bcc48  mov     rdx, [rsp+28h+ppMFType]
0x1800bcc4d  mov     rax, [rax+100h]
0x1800bcc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcc59  test    eax, eax
0x1800bcc5b  jns     short loc_1800BCC77
0x1800bcc5d  mov     rcx, [rbx+30h]
0x1800bcc61  mov     rax, [rcx]
0x1800bcc64  mov     rdx, [rsp+28h+ppMFType]
0x1800bcc69  mov     rax, [rax+100h]
0x1800bcc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcc75  jmp     short loc_1800BCC3D
0x1800bcc77  mov     r8, [rsp+28h+ppMFType]; struct IMFMediaType *
0x1800bcc7c  mov     rcx, rbx; this
0x1800bcc7f  call    ?SetAvailableOutputType@CMFTSimpleTypeHandler@@QEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleTypeHandler::SetAvailableOutputType(ulong,IMFMediaType *)
0x1800bcc84  xor     ebx, ebx
0x1800bcc86  lea     rcx, [rsp+28h+ppMFType]
0x1800bcc8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bcc90  mov     eax, ebx
0x1800bcc92  add     rsp, 20h
0x1800bcc96  pop     rbx
0x1800bcc97  retn
```
