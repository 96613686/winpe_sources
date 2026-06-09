# CFLACDecMFT::InternalProcessInput(IMFSample *,ulong)

- ea: `0x18001d9e0`
- end: `0x18001dbe3`
- name: `?InternalProcessInput@CFLACDecMFT@@EEAAJPEAUIMFSample@@K@Z`
- size: `515`
- prototype: `__int64 __fastcall(CFLACDecMFT *__hidden this, struct IMFSample *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18001c994`
- `0x18001d9e0`
- `0x18001e834`
- `0x18001ee24`
- `0x18001efc4`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001db5f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001db5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001db8e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001db8e`

## string_xrefs

- `0x18001da30`: `MF_E_NOTACCEPTING - cannot process sample as Input sample already exists`

## pseudocode

```c
__int64 __fastcall CFLACDecMFT::InternalProcessInput(CFLACDecMFT *this, struct IMFSample *a2, int a3)
{
  int v3; // eax
  int Sample; // esi
  unsigned int started; // eax
  int v9; // edx
  struct IMFSampleVtbl *lpVtbl; // rax
  struct IMFSampleVtbl *v12; // rax
  int v13; // [rsp+60h] [rbp+8h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 60);
  if ( v3 && (Sample = 0, v3 != 2)
    || (started = CFLACDecMFT::StartFlacDecoding(this), Sample = MF::OriginateError((MF *)started, v9), Sample >= 0) )
  {
    if ( *((_QWORD *)this + 9) )
    {
      TraceLoggingHelperBase::TraceVA(
        (CFLACDecMFT *)((char *)this + 960),
        2u,
        "CFLACDecMFT::InternalProcessInput",
        0x29Fu,
        "MF_E_NOTACCEPTING - cannot process sample as Input sample already exists");
      Sample = -1072875851;
    }
    else
    {
      if ( !a2 )
      {
        TraceLoggingHelperBase::TraceVA(
          (CFLACDecMFT *)((char *)this + 960),
          2u,
          "CFLACDecMFT::InternalProcessInput",
          0x2A6u,
          "E_INVALIDARG - sample pointer is NULL");
        return 2147942487LL;
      }
      lpVtbl = a2->lpVtbl;
      v14 = 0;
      if ( ((int (__fastcall *)(struct IMFSample *, __int64 *))lpVtbl->GetSampleTime)(a2, &v14) >= 0 )
        *((_QWORD *)this + 33) = v14;
      v12 = a2->lpVtbl;
      v13 = 0;
      if ( ((int (__fastcall *)(struct IMFSample *, const GUID *, int *))v12->GetUINT32)(
             a2,
             &MFSampleExtension_Discontinuity,
             &v13) >= 0 )
        *((_DWORD *)this + 77) = v13;
      if ( *((_BYTE *)this + 896) || (Sample = CFLACDecMFT::AddMetadataBlocksToFirstSample(this, a2), Sample >= 0) )
      {
        *((_QWORD *)this + 9) = a2;
        ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->AddRef)(a2);
        if ( *((_QWORD *)this + 114) )
        {
          TraceLoggingHelperBase::TraceVA(
            (CFLACDecMFT *)((char *)this + 960),
            5u,
            "CFLACDecMFT::InternalProcessInput",
            0x2C2u,
            "ResetEvent(m_hProcessSampleEvents[eSTATE_INPUT_SAMPLE_EMPTY])");
          ResetEvent(*((HANDLE *)this + 113));
          TraceLoggingHelperBase::TraceVA(
            (CFLACDecMFT *)((char *)this + 960),
            5u,
            "CFLACDecMFT::InternalProcessInput",
            0x2C5u,
            "SetEvent(m_hProcessSampleEvents[eSTATE_INPUT_SAMPLE_AVAILABLE])");
          SetEvent(*((HANDLE *)this + 114));
        }
        ++*((_DWORD *)this + 222);
      }
    }
  }
  TraceLoggingHelperBase::TraceVA(
    (CFLACDecMFT *)((char *)this + 960),
    4u,
    "CFLACDecMFT::InternalProcessInput",
    0x2CDu,
    "InternalProcessInput, dwFlags=0x%X, number of samples received: %u",
    a3,
    *((_DWORD *)this + 222));
  return (unsigned int)Sample;
}

```

## disassembly

```asm
0x18001d9e0  mov     [rsp+arg_8], rbx
0x18001d9e5  mov     [rsp+arg_10], rbp
0x18001d9ea  push    rsi
0x18001d9eb  push    rdi
0x18001d9ec  push    r12
0x18001d9ee  sub     rsp, 40h
0x18001d9f2  mov     eax, [rcx+0F0h]
0x18001d9f8  lea     r12, aCflacdecmftInt; "CFLACDecMFT::InternalProcessInput"
0x18001d9ff  mov     ebp, r8d
0x18001da02  mov     rbx, rdx
0x18001da05  mov     rdi, rcx
0x18001da08  test    eax, eax
0x18001da0a  jz      short loc_18001DA13
0x18001da0c  xor     esi, esi
0x18001da0e  cmp     eax, 2
0x18001da11  jnz     short loc_18001DA29
0x18001da13  call    ?StartFlacDecoding@CFLACDecMFT@@AEAAJXZ; CFLACDecMFT::StartFlacDecoding(void)
0x18001da18  mov     ecx, eax; this
0x18001da1a  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x18001da1f  mov     esi, eax
0x18001da21  test    eax, eax
0x18001da23  js      loc_18001DB9A
0x18001da29  cmp     qword ptr [rdi+48h], 0
0x18001da2e  jz      short loc_18001DA60
0x18001da30  lea     rax, aMfENotacceptin; "MF_E_NOTACCEPTING - cannot process samp"...
0x18001da37  mov     r9d, 29Fh; unsigned int
0x18001da3d  lea     rcx, [rdi+3C0h]; this
0x18001da44  mov     [rsp+58h+Format], rax; Format
0x18001da49  mov     r8, r12; char *
0x18001da4c  mov     edx, 2; unsigned __int8
0x18001da51  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001da56  mov     esi, 0C00D36B5h
0x18001da5b  jmp     loc_18001DB9A
0x18001da60  test    rbx, rbx
0x18001da63  jnz     short loc_18001DA93
0x18001da65  lea     rax, aEInvalidargSam; "E_INVALIDARG - sample pointer is NULL"
0x18001da6c  mov     r9d, 2A6h; unsigned int
0x18001da72  lea     rcx, [rdi+3C0h]; this
0x18001da79  mov     [rsp+58h+Format], rax; Format
0x18001da7e  mov     r8, r12; char *
0x18001da81  lea     edx, [rbx+2]; unsigned __int8
0x18001da84  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001da89  mov     eax, 80070057h
0x18001da8e  jmp     loc_18001DBD0
0x18001da93  mov     rax, [rbx]
0x18001da96  lea     rdx, [rsp+58h+arg_18]
0x18001da9b  mov     rcx, rbx
0x18001da9e  mov     [rsp+58h+arg_18], 0
0x18001daa7  mov     rax, [rax+118h]
0x18001daae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dab3  test    eax, eax
0x18001dab5  js      short loc_18001DAC3
0x18001dab7  mov     rax, [rsp+58h+arg_18]
0x18001dabc  mov     [rdi+108h], rax
0x18001dac3  mov     rax, [rbx]
0x18001dac6  lea     r8, [rsp+58h+arg_0]
0x18001dacb  lea     rdx, MFSampleExtension_Discontinuity
0x18001dad2  mov     [rsp+58h+arg_0], 0
0x18001dada  mov     rcx, rbx
0x18001dadd  mov     rax, [rax+38h]
0x18001dae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae6  test    eax, eax
0x18001dae8  js      short loc_18001DAF4
0x18001daea  mov     eax, [rsp+58h+arg_0]
0x18001daee  mov     [rdi+134h], eax
0x18001daf4  cmp     byte ptr [rdi+380h], 0
0x18001dafb  jnz     short loc_18001DB12
0x18001dafd  mov     rdx, rbx; struct IMFSample *
0x18001db00  mov     rcx, rdi; this
0x18001db03  call    ?AddMetadataBlocksToFirstSample@CFLACDecMFT@@AEAAJPEAUIMFSample@@@Z; CFLACDecMFT::AddMetadataBlocksToFirstSample(IMFSample *)
0x18001db08  mov     esi, eax
0x18001db0a  test    eax, eax
0x18001db0c  js      loc_18001DB9A
0x18001db12  mov     [rdi+48h], rbx
0x18001db16  mov     rcx, rbx
0x18001db19  mov     rax, [rbx]
0x18001db1c  mov     rax, [rax+8]
0x18001db20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db25  cmp     qword ptr [rdi+390h], 0
0x18001db2d  jz      short loc_18001DB94
0x18001db2f  lea     rax, aReseteventMHpr; "ResetEvent(m_hProcessSampleEvents[eSTAT"...
0x18001db36  mov     r9d, 2C2h; unsigned int
0x18001db3c  lea     rbx, [rdi+3C0h]
0x18001db43  mov     [rsp+58h+Format], rax; Format
0x18001db48  mov     rcx, rbx; this
0x18001db4b  mov     r8, r12; char *
0x18001db4e  mov     edx, 5; unsigned __int8
0x18001db53  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001db58  mov     rcx, [rdi+388h]; hEvent
0x18001db5f  call    cs:__imp_ResetEvent
0x18001db65  lea     rax, aSeteventMHproc; "SetEvent(m_hProcessSampleEvents[eSTATE_"...
0x18001db6c  mov     r9d, 2C5h; unsigned int
0x18001db72  mov     r8, r12; char *
0x18001db75  mov     [rsp+58h+Format], rax; Format
0x18001db7a  mov     edx, 5; unsigned __int8
0x18001db7f  mov     rcx, rbx; this
0x18001db82  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001db87  mov     rcx, [rdi+390h]; hEvent
0x18001db8e  call    cs:__imp_SetEvent
0x18001db94  inc     dword ptr [rdi+378h]
0x18001db9a  mov     eax, [rdi+378h]
0x18001dba0  lea     rcx, [rdi+3C0h]; this
0x18001dba7  mov     [rsp+58h+var_28], eax
0x18001dbab  mov     r9d, 2CDh; unsigned int
0x18001dbb1  lea     rax, aInternalproces_0; "InternalProcessInput, dwFlags=0x%X, num"...
0x18001dbb8  mov     [rsp+58h+var_30], ebp
0x18001dbbc  mov     r8, r12; char *
0x18001dbbf  mov     [rsp+58h+Format], rax; Format
0x18001dbc4  mov     edx, 4; unsigned __int8
0x18001dbc9  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001dbce  mov     eax, esi
0x18001dbd0  mov     rbx, [rsp+58h+arg_8]
0x18001dbd5  mov     rbp, [rsp+58h+arg_10]
0x18001dbda  add     rsp, 40h
0x18001dbde  pop     r12
0x18001dbe0  pop     rdi
0x18001dbe1  pop     rsi
0x18001dbe2  retn
```
