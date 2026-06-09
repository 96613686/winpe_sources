# CFLACDecoder::write_callback(FLAC__Frame const *,int const * const * const)

- ea: `0x18001fe00`
- end: `0x18001ff1d`
- name: `?write_callback@CFLACDecoder@@MEAA?AW4FLAC__StreamDecoderWriteStatus@@PEBUFLAC__Frame@@QEBQEBH@Z`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001efc4`
- `0x18001fe00`
- `0x180056010`

## string_xrefs

- `0x18001fe20`: `FLAC__STREAM_DECODER_WRITE_STATUS_ABORT, sample callback is NULL`
- `0x18001fe39`: `CFLACDecoder::write_callback`
- `0x18001fe89`: `CFLACDecoder::write_callback`
- `0x18001feb0`: `CFLACDecoder::write_callback`
- `0x18001fede`: `CFLACDecoder::write_callback`
- `0x18001fe70`: `Failed WriteOutputSample: FLAC__STREAM_DECODER_WRITE_STATUS_ABORT`
- `0x18001fe9a`: `write_callback, write status: %i`

## pseudocode

```c
__int64 __fastcall CFLACDecoder::write_callback(__int64 a1, unsigned int *a2)
{
  __int64 v3; // rcx
  int v4; // edi
  unsigned int v5; // ebx
  int v6; // eax

  v3 = *(_QWORD *)(a1 + 544);
  if ( v3 )
  {
    v5 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 8LL))(v3, *a2);
    v4 = v6;
    if ( v6 )
    {
      v5 = 1;
      if ( v6 == 1 )
        v5 = 0;
      else
        TraceLoggingHelperBase::TraceVA(
          (TraceLoggingHelperBase *)(a1 + 568),
          2u,
          "CFLACDecoder::write_callback",
          0xC1u,
          "Failed WriteOutputSample: FLAC__STREAM_DECODER_WRITE_STATUS_ABORT");
    }
  }
  else
  {
    v4 = 0;
    TraceLoggingHelperBase::TraceVA(
      (TraceLoggingHelperBase *)(a1 + 568),
      2u,
      "CFLACDecoder::write_callback",
      0xB3u,
      "FLAC__STREAM_DECODER_WRITE_STATUS_ABORT, sample callback is NULL");
    v5 = 1;
  }
  TraceLoggingHelperBase::TraceVA(
    (TraceLoggingHelperBase *)(a1 + 568),
    5u,
    "CFLACDecoder::write_callback",
    0xC8u,
    "write_callback, write status: %i",
    v5);
  if ( v4 )
    TraceLoggingHelperBase::TraceVA(
      (TraceLoggingHelperBase *)(a1 + 568),
      2u,
      "CFLACDecoder::write_callback",
      0xC9u,
      "Error %08X returned: File: %s, Line: %d",
      v4,
      "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecoder.cpp",
      201);
  return v5;
}

```

## disassembly

```asm
0x18001fe00  mov     [rsp+arg_0], rbx
0x18001fe05  mov     [rsp+arg_8], rsi
0x18001fe0a  push    rdi
0x18001fe0b  sub     rsp, 40h
0x18001fe0f  mov     rsi, rcx
0x18001fe12  mov     rcx, [rcx+220h]
0x18001fe19  test    rcx, rcx
0x18001fe1c  jnz     short loc_18001FE4D
0x18001fe1e  xor     edi, edi
0x18001fe20  lea     rax, aFlacStreamDeco_23; "FLAC__STREAM_DECODER_WRITE_STATUS_ABORT"...
0x18001fe27  lea     rcx, [rsi+238h]; this
0x18001fe2e  mov     [rsp+48h+Format], rax; Format
0x18001fe33  mov     r9d, 0B3h; unsigned int
0x18001fe39  lea     r8, aCflacdecoderWr; "CFLACDecoder::write_callback"
0x18001fe40  lea     edx, [rdi+2]; unsigned __int8
0x18001fe43  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fe48  lea     ebx, [rdi+1]
0x18001fe4b  jmp     short loc_18001FE9A
0x18001fe4d  mov     rax, [rcx]
0x18001fe50  xor     ebx, ebx
0x18001fe52  mov     edx, [rdx]
0x18001fe54  mov     rax, [rax+8]
0x18001fe58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe5d  mov     edi, eax
0x18001fe5f  test    eax, eax
0x18001fe61  jz      short loc_18001FE9A
0x18001fe63  mov     ebx, 1
0x18001fe68  cmp     eax, ebx
0x18001fe6a  jnz     short loc_18001FE70
0x18001fe6c  xor     ebx, ebx
0x18001fe6e  jmp     short loc_18001FE9A
0x18001fe70  lea     rax, aFailedWriteout; "Failed WriteOutputSample: FLAC__STREAM_"...
0x18001fe77  mov     r9d, 0C1h; unsigned int
0x18001fe7d  lea     rcx, [rsi+238h]; this
0x18001fe84  mov     [rsp+48h+Format], rax; Format
0x18001fe89  lea     r8, aCflacdecoderWr; "CFLACDecoder::write_callback"
0x18001fe90  mov     edx, 2; unsigned __int8
0x18001fe95  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fe9a  lea     rax, aWriteCallbackW; "write_callback, write status: %i"
0x18001fea1  mov     [rsp+48h+var_20], ebx
0x18001fea5  mov     r9d, 0C8h; unsigned int
0x18001feab  mov     [rsp+48h+Format], rax; Format
0x18001feb0  lea     r8, aCflacdecoderWr; "CFLACDecoder::write_callback"
0x18001feb7  mov     edx, 5; unsigned __int8
0x18001febc  lea     rcx, [rsi+238h]; this
0x18001fec3  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fec8  test    edi, edi
0x18001feca  jz      short loc_18001FF0B
0x18001fecc  mov     r9d, 0C9h; unsigned int
0x18001fed2  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001fed9  mov     [rsp+48h+var_10], r9d
0x18001fede  lea     r8, aCflacdecoderWr; "CFLACDecoder::write_callback"
0x18001fee5  mov     [rsp+48h+var_18], rax
0x18001feea  lea     rcx, [rsi+238h]; this
0x18001fef1  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001fef8  mov     [rsp+48h+var_20], edi
0x18001fefc  mov     edx, 2; unsigned __int8
0x18001ff01  mov     [rsp+48h+Format], rax; Format
0x18001ff06  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001ff0b  mov     rsi, [rsp+48h+arg_8]
0x18001ff10  mov     eax, ebx
0x18001ff12  mov     rbx, [rsp+48h+arg_0]
0x18001ff17  add     rsp, 40h
0x18001ff1b  pop     rdi
0x18001ff1c  retn
```
