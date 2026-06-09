# CFLACDecMFT::ConfigInputTypes(void)

- ea: `0x18001cd50`
- end: `0x18001ced2`
- name: `?ConfigInputTypes@CFLACDecMFT@@AEAAJXZ`
- size: `386`
- prototype: `__int64 __fastcall(CFLACDecMFT *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d940`

## callees

- `0x180016e48`
- `0x18001cd50`
- `0x18001efc4`
- `0x18001f56c`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001cdae`
- `MFPlat!MFCreateMediaType` at `0x18001cdae`

## string_xrefs

- `0x18001cd63`: `ConfigInputTypes`
- `0x18001cd75`: `CFLACDecMFT::ConfigInputTypes`
- `0x18001cea8`: `CFLACDecMFT::ConfigInputTypes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACDecMFT::ConfigInputTypes(CFLACDecMFT *this)
{
  TraceLoggingHelperBase *v2; // rbp
  HRESULT inited; // edi
  IMFMediaType *v4; // rsi
  __int64 v5; // rcx
  IMFMediaType *ppMFType; // [rsp+70h] [rbp+8h] BYREF

  v2 = (CFLACDecMFT *)((char *)this + 960);
  TraceLoggingHelperBase::TraceVA(
    (CFLACDecMFT *)((char *)this + 960),
    4u,
    "CFLACDecMFT::ConfigInputTypes",
    0x416u,
    "ConfigInputTypes");
  ppMFType = 0;
  inited = CMFTSimpleBase::_InitAvailableInputTypeArray(this, 1u);
  if ( inited >= 0 )
  {
    inited = MFCreateMediaType(&ppMFType);
    if ( inited >= 0 )
    {
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_MAJOR_TYPE,
                 &MFMediaType_Audio);
      if ( inited >= 0 )
      {
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_SUBTYPE,
                   &MFAudioFormat_FLAC);
        if ( inited >= 0 )
        {
          if ( *((_DWORD *)this + 2) )
          {
            v4 = ppMFType;
            v5 = **((_QWORD **)this + 2);
            if ( v5 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
              **((_QWORD **)this + 2) = 0;
            }
            **((_QWORD **)this + 2) = v4;
            (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 2) + 8LL))(**((_QWORD **)this + 2));
            *(_DWORD *)(*((_QWORD *)this + 2) + 8LL) = 1;
          }
          *((_DWORD *)this + 36) = 0;
          *((_DWORD *)this + 13) = 0x10000;
          *((_DWORD *)this + 23) = 2097120;
        }
      }
    }
  }
  if ( inited )
    TraceLoggingHelperBase::TraceVA(
      v2,
      2u,
      "CFLACDecMFT::ConfigInputTypes",
      0x42Cu,
      "Error %08X returned: File: %s, Line: %d",
      inited,
      "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecmft.cpp",
      1068);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppMFType);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001cd50  push    rbx
0x18001cd52  push    rbp
0x18001cd53  push    rsi
0x18001cd54  push    rdi
0x18001cd55  sub     rsp, 48h
0x18001cd59  mov     rbx, rcx
0x18001cd5c  lea     rbp, [rcx+3C0h]
0x18001cd63  lea     rax, aConfiginputtyp; "ConfigInputTypes"
0x18001cd6a  mov     [rsp+68h+Format], rax; Format
0x18001cd6f  mov     r9d, 416h; unsigned int
0x18001cd75  lea     r8, aCflacdecmftCon_0; "CFLACDecMFT::ConfigInputTypes"
0x18001cd7c  mov     edx, 4; unsigned __int8
0x18001cd81  mov     rcx, rbp; this
0x18001cd84  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001cd89  mov     [rsp+68h+ppMFType], 0
0x18001cd92  mov     edx, 1; unsigned int
0x18001cd97  mov     rcx, rbx; this
0x18001cd9a  call    ?_InitAvailableInputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableInputTypeArray(ulong)
0x18001cd9f  mov     edi, eax
0x18001cda1  test    eax, eax
0x18001cda3  js      loc_18001CE7D
0x18001cda9  lea     rcx, [rsp+68h+ppMFType]; ppMFType
0x18001cdae  call    cs:__imp_MFCreateMediaType
0x18001cdb4  mov     edi, eax
0x18001cdb6  test    eax, eax
0x18001cdb8  js      loc_18001CE7D
0x18001cdbe  mov     rcx, [rsp+68h+ppMFType]
0x18001cdc3  mov     rax, [rcx]
0x18001cdc6  lea     r8, MFMediaType_Audio
0x18001cdcd  lea     rdx, MF_MT_MAJOR_TYPE
0x18001cdd4  mov     rax, [rax+0C0h]
0x18001cddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cde0  mov     edi, eax
0x18001cde2  test    eax, eax
0x18001cde4  js      loc_18001CE7D
0x18001cdea  mov     rcx, [rsp+68h+ppMFType]
0x18001cdef  mov     rax, [rcx]
0x18001cdf2  lea     r8, MFAudioFormat_FLAC
0x18001cdf9  lea     rdx, MF_MT_SUBTYPE
0x18001ce00  mov     rax, [rax+0C0h]
0x18001ce07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce0c  mov     edi, eax
0x18001ce0e  test    eax, eax
0x18001ce10  js      short loc_18001CE7D
0x18001ce12  cmp     dword ptr [rbx+8], 0
0x18001ce16  jbe     short loc_18001CE65
0x18001ce18  mov     rsi, [rsp+68h+ppMFType]
0x18001ce1d  mov     rax, [rbx+10h]
0x18001ce21  mov     rcx, [rax]
0x18001ce24  test    rcx, rcx
0x18001ce27  jz      short loc_18001CE40
0x18001ce29  mov     rax, [rcx]
0x18001ce2c  mov     rax, [rax+10h]
0x18001ce30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce35  mov     rax, [rbx+10h]
0x18001ce39  mov     qword ptr [rax], 0
0x18001ce40  mov     rax, [rbx+10h]
0x18001ce44  mov     [rax], rsi
0x18001ce47  mov     rax, [rbx+10h]
0x18001ce4b  mov     rcx, [rax]
0x18001ce4e  mov     rax, [rcx]
0x18001ce51  mov     rax, [rax+8]
0x18001ce55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce5a  mov     rax, [rbx+10h]
0x18001ce5e  mov     dword ptr [rax+8], 1
0x18001ce65  mov     dword ptr [rbx+90h], 0
0x18001ce6f  mov     dword ptr [rbx+34h], 10000h
0x18001ce76  mov     dword ptr [rbx+5Ch], 1FFFE0h
0x18001ce7d  test    edi, edi
0x18001ce7f  jz      short loc_18001CEBD
0x18001ce81  mov     r9d, 42Ch; unsigned int
0x18001ce87  mov     [rsp+68h+var_30], r9d
0x18001ce8c  lea     rax, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001ce93  mov     [rsp+68h+var_38], rax
0x18001ce98  mov     [rsp+68h+var_40], edi
0x18001ce9c  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001cea3  mov     [rsp+68h+Format], rax; Format
0x18001cea8  lea     r8, aCflacdecmftCon_0; "CFLACDecMFT::ConfigInputTypes"
0x18001ceaf  mov     edx, 2; unsigned __int8
0x18001ceb4  mov     rcx, rbp; this
0x18001ceb7  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001cebc  nop
0x18001cebd  lea     rcx, [rsp+68h+ppMFType]
0x18001cec2  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001cec7  mov     eax, edi
0x18001cec9  add     rsp, 48h
0x18001cecd  pop     rdi
0x18001cece  pop     rsi
0x18001cecf  pop     rbp
0x18001ced0  pop     rbx
0x18001ced1  retn
```
