# CFLACDecMFT::AddMetadataBlocksToFirstSample(IMFSample *)

- ea: `0x18001c994`
- end: `0x18001cc88`
- name: `?AddMetadataBlocksToFirstSample@CFLACDecMFT@@AEAAJPEAUIMFSample@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(CFLACDecMFT *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d9e0`

## callees

- `0x180016e48`
- `0x18001c638`
- `0x18001c994`
- `0x18001efc4`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc11`
- `MFPlat!MFCreateMemoryBuffer` at `0x18001ca76`
- `MFPlat!MFCreateMemoryBuffer` at `0x18001ca76`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFLACDecMFT::AddMetadataBlocksToFirstSample(CFLACDecMFT *this, struct IMFSample *a2)
{
  HRESULT v4; // ebx
  HRESULT v5; // eax
  DWORD v6; // r14d
  errno_t v7; // eax
  errno_t v8; // eax
  IMFMediaBuffer *ppBuffer; // [rsp+40h] [rbp-30h] BYREF
  __int64 v11; // [rsp+48h] [rbp-28h] BYREF
  void *Destination; // [rsp+50h] [rbp-20h] BYREF
  _DWORD *v13; // [rsp+58h] [rbp-18h] BYREF
  void *Source; // [rsp+60h] [rbp-10h] BYREF
  rsize_t SourceSize; // [rsp+A8h] [rbp+38h] BYREF
  unsigned int v16; // [rsp+B0h] [rbp+40h] BYREF
  int v17; // [rsp+B8h] [rbp+48h] BYREF

  v11 = 0;
  ppBuffer = 0;
  v13 = 0;
  Destination = 0;
  Source = 0;
  v4 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->ConvertToContiguousBuffer)(a2, &v11);
  if ( v4 >= 0 )
  {
    v16 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _DWORD **, _QWORD, unsigned int *))(*(_QWORD *)v11 + 24LL))(
           v11,
           &v13,
           0,
           &v16);
    if ( v4 >= 0 )
    {
      if ( v16 >= 4 && *v13 == 1130450022 )
        goto LABEL_5;
      LODWORD(SourceSize) = 0;
      v5 = (*(__int64 (__fastcall **)(_QWORD, void *, void **, rsize_t *))(**((_QWORD **)this + 5) + 128LL))(
             *((_QWORD *)this + 5),
             &MF_MT_FLAC_METADATA_BLOCKS,
             &Source,
             &SourceSize);
      v4 = v5;
      if ( v5 )
      {
        if ( v5 == -1072875802 )
          v4 = 0;
      }
      else
      {
        v17 = 0;
        v6 = SourceSize + 4;
        if ( (int)SourceSize + 4 < (unsigned int)SourceSize )
        {
          v4 = -2147024362;
        }
        else
        {
          v4 = MFCreateMemoryBuffer(v6, &ppBuffer);
          if ( v4 >= 0 )
          {
            v4 = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, _QWORD, int *))ppBuffer->lpVtbl->Lock)(
                   ppBuffer,
                   &Destination,
                   0,
                   &v17);
            if ( v4 >= 0 )
            {
              v7 = memcpy_s(Destination, 4u, "fLaC", 4u);
              if ( v7 )
              {
                TraceLoggingHelperBase::TraceVA(
                  (CFLACDecMFT *)((char *)this + 960),
                  2u,
                  "CFLACDecMFT::AddMetadataBlocksToFirstSample",
                  0x2F9u,
                  "E_UNEXPECTED - failed in memcpy_s of FLAC code to buffers. Error: (%d)",
                  v7);
LABEL_12:
                v4 = -2147418113;
                goto LABEL_23;
              }
              v8 = memcpy_s((char *)Destination + 4, (unsigned int)SourceSize, Source, (unsigned int)SourceSize);
              if ( v8 )
              {
                TraceLoggingHelperBase::TraceVA(
                  (CFLACDecMFT *)((char *)this + 960),
                  2u,
                  "CFLACDecMFT::AddMetadataBlocksToFirstSample",
                  0x301u,
                  "E_UNEXPECTED - failed in memcpy_s of metadata to buffers. Error: (%d)",
                  v8);
                goto LABEL_12;
              }
              v4 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer, v6);
              if ( v4 >= 0 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11);
                ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                v13 = 0;
                Destination = 0;
                v4 = ((__int64 (__fastcall *)(struct IMFSample *))a2->lpVtbl->RemoveAllBuffers)(a2);
                if ( v4 >= 0 )
                {
                  v4 = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer *))a2->lpVtbl->AddBuffer)(
                         a2,
                         ppBuffer);
                  if ( v4 >= 0 )
                  {
                    v4 = ((__int64 (__fastcall *)(struct IMFSample *, __int64))a2->lpVtbl->AddBuffer)(a2, v11);
                    if ( v4 >= 0 )
LABEL_5:
                      *((_BYTE *)this + 896) = 1;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_23:
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11);
  if ( Destination )
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
  if ( Source )
  {
    CoTaskMemFree(Source);
    Source = 0;
  }
  if ( v4 )
    TraceLoggingHelperBase::TraceVA(
      (CFLACDecMFT *)((char *)this + 960),
      2u,
      "CFLACDecMFT::AddMetadataBlocksToFirstSample",
      0x32Au,
      "Error %08X returned: File: %s, Line: %d",
      v4,
      "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecmft.cpp",
      810);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppBuffer);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c994  mov     [rsp-28h+arg_0], rbx
0x18001c999  push    rbp
0x18001c99a  push    rsi
0x18001c99b  push    rdi
0x18001c99c  push    r14
0x18001c99e  push    r15
0x18001c9a0  mov     rbp, rsp
0x18001c9a3  sub     rsp, 70h
0x18001c9a7  mov     rdi, rdx
0x18001c9aa  mov     rsi, rcx
0x18001c9ad  xor     r15d, r15d
0x18001c9b0  mov     [rbp+var_28], r15
0x18001c9b4  mov     [rbp+ppBuffer], r15
0x18001c9b8  mov     [rbp+var_18], r15
0x18001c9bc  mov     [rbp+Destination], r15
0x18001c9c0  mov     [rbp+Source], r15
0x18001c9c4  mov     rax, [rdx]
0x18001c9c7  lea     rdx, [rbp+var_28]
0x18001c9cb  mov     rcx, rdi
0x18001c9ce  mov     rax, [rax+148h]
0x18001c9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9da  mov     ebx, eax
0x18001c9dc  test    eax, eax
0x18001c9de  js      loc_18001CBDC
0x18001c9e4  mov     [rbp+arg_10], r15d
0x18001c9e8  mov     rcx, [rbp+var_28]
0x18001c9ec  mov     rax, [rcx]
0x18001c9ef  lea     r9, [rbp+arg_10]
0x18001c9f3  xor     r8d, r8d
0x18001c9f6  lea     rdx, [rbp+var_18]
0x18001c9fa  mov     rax, [rax+18h]
0x18001c9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca03  mov     ebx, eax
0x18001ca05  test    eax, eax
0x18001ca07  js      loc_18001CBDC
0x18001ca0d  cmp     [rbp+arg_10], 4
0x18001ca11  jb      short loc_18001CA2B
0x18001ca13  mov     rax, [rbp+var_18]
0x18001ca17  cmp     dword ptr [rax], 43614C66h
0x18001ca1d  jnz     short loc_18001CA2B
0x18001ca1f  mov     byte ptr [rsi+380h], 1
0x18001ca26  jmp     loc_18001CBDC
0x18001ca2b  mov     dword ptr [rbp+SourceSize], r15d
0x18001ca2f  mov     rcx, [rsi+28h]
0x18001ca33  mov     rax, [rcx]
0x18001ca36  lea     r9, [rbp+SourceSize]
0x18001ca3a  lea     r8, [rbp+Source]
0x18001ca3e  lea     rdx, MF_MT_FLAC_METADATA_BLOCKS
0x18001ca45  mov     rax, [rax+80h]
0x18001ca4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca51  mov     ebx, eax
0x18001ca53  test    eax, eax
0x18001ca55  jnz     loc_18001CBD2
0x18001ca5b  mov     [rbp+arg_18], r15d
0x18001ca5f  mov     eax, dword ptr [rbp+SourceSize]
0x18001ca62  lea     r14d, [rax+4]
0x18001ca66  cmp     r14d, eax
0x18001ca69  jb      loc_18001CBCB
0x18001ca6f  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x18001ca73  mov     ecx, r14d; cbMaxLength
0x18001ca76  call    cs:__imp_MFCreateMemoryBuffer
0x18001ca7c  mov     ebx, eax
0x18001ca7e  test    eax, eax
0x18001ca80  js      loc_18001CBDC
0x18001ca86  mov     rcx, [rbp+ppBuffer]
0x18001ca8a  mov     rax, [rcx]
0x18001ca8d  lea     r9, [rbp+arg_18]
0x18001ca91  xor     r8d, r8d
0x18001ca94  lea     rdx, [rbp+Destination]
0x18001ca98  mov     rax, [rax+18h]
0x18001ca9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caa1  mov     ebx, eax
0x18001caa3  test    eax, eax
0x18001caa5  js      loc_18001CBDC
0x18001caab  mov     r9d, 4; SourceSize
0x18001cab1  lea     r8, aFlac_0; "fLaC"
0x18001cab8  mov     edx, r9d; DestinationSize
0x18001cabb  mov     rcx, [rbp+Destination]; Destination
0x18001cabf  call    memcpy_s
0x18001cac4  lea     rbx, [rsi+3C0h]
0x18001cacb  test    eax, eax
0x18001cacd  jz      short loc_18001CB03
0x18001cacf  mov     [rsp+70h+var_48], eax
0x18001cad3  lea     rax, aEUnexpectedFai; "E_UNEXPECTED - failed in memcpy_s of FL"...
0x18001cada  mov     r9d, 2F9h; unsigned int
0x18001cae0  mov     [rsp+70h+Format], rax; Format
0x18001cae5  lea     r8, aCflacdecmftAdd; "CFLACDecMFT::AddMetadataBlocksToFirstSa"...
0x18001caec  mov     edx, 2; unsigned __int8
0x18001caf1  mov     rcx, rbx; this
0x18001caf4  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001caf9  mov     ebx, 8000FFFFh
0x18001cafe  jmp     loc_18001CBDC
0x18001cb03  mov     edx, dword ptr [rbp+SourceSize]; DestinationSize
0x18001cb06  mov     rcx, [rbp+Destination]
0x18001cb0a  add     rcx, 4; Destination
0x18001cb0e  mov     r9d, edx; SourceSize
0x18001cb11  mov     r8, [rbp+Source]; Source
0x18001cb15  call    memcpy_s
0x18001cb1a  test    eax, eax
0x18001cb1c  jz      short loc_18001CB31
0x18001cb1e  mov     [rsp+70h+var_48], eax
0x18001cb22  lea     rax, aEUnexpectedFai_0; "E_UNEXPECTED - failed in memcpy_s of me"...
0x18001cb29  mov     r9d, 301h
0x18001cb2f  jmp     short loc_18001CAE0
0x18001cb31  mov     rcx, [rbp+ppBuffer]
0x18001cb35  mov     rax, [rcx]
0x18001cb38  mov     edx, r14d
0x18001cb3b  mov     rax, [rax+30h]
0x18001cb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb44  mov     ebx, eax
0x18001cb46  test    eax, eax
0x18001cb48  js      loc_18001CBDC
0x18001cb4e  mov     rcx, [rbp+var_28]
0x18001cb52  mov     rax, [rcx]
0x18001cb55  mov     rax, [rax+20h]
0x18001cb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb5e  mov     rcx, [rbp+ppBuffer]
0x18001cb62  mov     rax, [rcx]
0x18001cb65  mov     rax, [rax+20h]
0x18001cb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb6e  mov     [rbp+var_18], r15
0x18001cb72  mov     [rbp+Destination], r15
0x18001cb76  mov     rax, [rdi]
0x18001cb79  mov     rcx, rdi
0x18001cb7c  mov     rax, [rax+160h]
0x18001cb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb88  mov     ebx, eax
0x18001cb8a  test    eax, eax
0x18001cb8c  js      short loc_18001CBDC
0x18001cb8e  mov     rax, [rdi]
0x18001cb91  mov     rdx, [rbp+ppBuffer]
0x18001cb95  mov     rcx, rdi
0x18001cb98  mov     rax, [rax+150h]
0x18001cb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cba4  mov     ebx, eax
0x18001cba6  test    eax, eax
0x18001cba8  js      short loc_18001CBDC
0x18001cbaa  mov     rax, [rdi]
0x18001cbad  mov     rdx, [rbp+var_28]
0x18001cbb1  mov     rcx, rdi
0x18001cbb4  mov     rax, [rax+150h]
0x18001cbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc0  mov     ebx, eax
0x18001cbc2  test    eax, eax
0x18001cbc4  js      short loc_18001CBDC
0x18001cbc6  jmp     loc_18001CA1F
0x18001cbcb  mov     ebx, 80070216h
0x18001cbd0  jmp     short loc_18001CBDC
0x18001cbd2  cmp     eax, 0C00D36E6h
0x18001cbd7  jnz     short loc_18001CBDC
0x18001cbd9  mov     ebx, r15d
0x18001cbdc  cmp     [rbp+var_18], r15
0x18001cbe0  jz      short loc_18001CBF2
0x18001cbe2  mov     rcx, [rbp+var_28]
0x18001cbe6  mov     rax, [rcx]
0x18001cbe9  mov     rax, [rax+20h]
0x18001cbed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbf2  cmp     [rbp+Destination], r15
0x18001cbf6  jz      short loc_18001CC08
0x18001cbf8  mov     rcx, [rbp+ppBuffer]
0x18001cbfc  mov     rax, [rcx]
0x18001cbff  mov     rax, [rax+20h]
0x18001cc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc08  mov     rcx, [rbp+Source]; pv
0x18001cc0c  test    rcx, rcx
0x18001cc0f  jz      short loc_18001CC1B
0x18001cc11  call    cs:__imp_CoTaskMemFree
0x18001cc17  mov     [rbp+Source], r15
0x18001cc1b  test    ebx, ebx
0x18001cc1d  jz      short loc_18001CC5F
0x18001cc1f  lea     rcx, [rsi+3C0h]; this
0x18001cc26  mov     r9d, 32Ah; unsigned int
0x18001cc2c  mov     [rsp+70h+var_38], r9d
0x18001cc31  lea     rax, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001cc38  mov     [rsp+70h+var_40], rax
0x18001cc3d  mov     [rsp+70h+var_48], ebx
0x18001cc41  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001cc48  mov     [rsp+70h+Format], rax; Format
0x18001cc4d  lea     r8, aCflacdecmftAdd; "CFLACDecMFT::AddMetadataBlocksToFirstSa"...
0x18001cc54  mov     edx, 2; unsigned __int8
0x18001cc59  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001cc5e  nop
0x18001cc5f  lea     rcx, [rbp+ppBuffer]
0x18001cc63  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001cc68  nop
0x18001cc69  lea     rcx, [rbp+var_28]
0x18001cc6d  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001cc72  mov     eax, ebx
0x18001cc74  mov     rbx, [rsp+70h+arg_0]
0x18001cc7c  add     rsp, 70h
0x18001cc80  pop     r15
0x18001cc82  pop     r14
0x18001cc84  pop     rdi
0x18001cc85  pop     rsi
0x18001cc86  pop     rbp
0x18001cc87  retn
```
