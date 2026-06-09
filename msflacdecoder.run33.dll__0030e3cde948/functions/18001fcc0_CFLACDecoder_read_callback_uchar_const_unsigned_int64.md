# CFLACDecoder::read_callback(uchar * const,unsigned __int64 *)

- ea: `0x18001fcc0`
- end: `0x18001fdf3`
- name: `?read_callback@CFLACDecoder@@MEAA?AW4FLAC__StreamDecoderReadStatus@@QEAEPEA_K@Z`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001efc4`
- `0x18001fcc0`
- `0x180056010`

## string_xrefs

- `0x18001fccf`: `CFLACDecoder::read_callback`
- `0x18001fd1c`: `Reached FLAC__STREAM_DECODER_READ_STATUS_END_OF_STREAM`
- `0x18001fd3c`: `Failed ReadInputSample: FLAC__STREAM_DECODER_READ_STATUS_ABORT`
- `0x18001fd98`: `read_callback, bytes: %Id, read status: %i`

## pseudocode

```c
__int64 __fastcall CFLACDecoder::read_callback(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v3; // esi
  __int64 (__fastcall ***v6)(_QWORD); // rcx
  int v7; // eax
  TraceLoggingHelperBase *v8; // rdi
  unsigned int v9; // ebx

  v3 = 0;
  if ( a2 && *a3 )
  {
    v6 = *(__int64 (__fastcall ****)(_QWORD))(a1 + 544);
    if ( !v6 || (v7 = (**v6)(v6), (v3 = v7) == 0) )
    {
      v9 = 0;
      v8 = (TraceLoggingHelperBase *)(a1 + 568);
      goto LABEL_11;
    }
    v8 = (TraceLoggingHelperBase *)(a1 + 568);
    v9 = 1;
    if ( v7 == 1 )
    {
      TraceLoggingHelperBase::TraceVA(
        v8,
        2u,
        "CFLACDecoder::read_callback",
        0x98u,
        "Reached FLAC__STREAM_DECODER_READ_STATUS_END_OF_STREAM");
      *a3 = 0;
      goto LABEL_11;
    }
    TraceLoggingHelperBase::TraceVA(
      v8,
      2u,
      "CFLACDecoder::read_callback",
      0x9Eu,
      "Failed ReadInputSample: FLAC__STREAM_DECODER_READ_STATUS_ABORT");
  }
  else
  {
    v8 = (TraceLoggingHelperBase *)(a1 + 568);
    TraceLoggingHelperBase::TraceVA(
      (TraceLoggingHelperBase *)(a1 + 568),
      2u,
      "CFLACDecoder::read_callback",
      0x8Bu,
      "Received buffer pointer is NULL or size is 0");
  }
  v9 = 2;
LABEL_11:
  TraceLoggingHelperBase::TraceVA(
    v8,
    5u,
    "CFLACDecoder::read_callback",
    0xA6u,
    "read_callback, bytes: %Id, read status: %i",
    *a3,
    v9);
  if ( v3 )
    TraceLoggingHelperBase::TraceVA(
      v8,
      2u,
      "CFLACDecoder::read_callback",
      0xA7u,
      "Error %08X returned: File: %s, Line: %d",
      v3,
      "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecoder.cpp",
      167);
  return v9;
}

```

## disassembly

```asm
0x18001fcc0  push    rbx
0x18001fcc2  push    rbp
0x18001fcc3  push    rsi
0x18001fcc4  push    rdi
0x18001fcc5  push    r14
0x18001fcc7  push    r15
0x18001fcc9  sub     rsp, 48h
0x18001fccd  xor     esi, esi
0x18001fccf  lea     r15, aCflacdecoderRe; "CFLACDecoder::read_callback"
0x18001fcd6  mov     r14, r8
0x18001fcd9  mov     rdi, rcx
0x18001fcdc  lea     ebp, [rsi+2]
0x18001fcdf  test    rdx, rdx
0x18001fce2  jz      short loc_18001FD56
0x18001fce4  cmp     [r8], rsi
0x18001fce7  jz      short loc_18001FD56
0x18001fce9  mov     rcx, [rcx+220h]
0x18001fcf0  test    rcx, rcx
0x18001fcf3  jz      short loc_18001FD4B
0x18001fcf5  mov     rax, [rcx]
0x18001fcf8  mov     rax, [rax]
0x18001fcfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd00  mov     esi, eax
0x18001fd02  test    eax, eax
0x18001fd04  jz      short loc_18001FD4B
0x18001fd06  add     rdi, 238h
0x18001fd0d  lea     ebx, [rbp-1]
0x18001fd10  mov     r8, r15; char *
0x18001fd13  mov     edx, ebp; unsigned __int8
0x18001fd15  mov     rcx, rdi; this
0x18001fd18  cmp     eax, ebx
0x18001fd1a  jnz     short loc_18001FD3C
0x18001fd1c  lea     rax, aReachedFlacStr; "Reached FLAC__STREAM_DECODER_READ_STATU"...
0x18001fd23  mov     r9d, 98h; unsigned int
0x18001fd29  mov     [rsp+78h+Format], rax; Format
0x18001fd2e  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fd33  mov     qword ptr [r14], 0
0x18001fd3a  jmp     short loc_18001FD7E
0x18001fd3c  lea     rax, aFailedReadinpu; "Failed ReadInputSample: FLAC__STREAM_DE"...
0x18001fd43  mov     r9d, 9Eh
0x18001fd49  jmp     short loc_18001FD72
0x18001fd4b  xor     ebx, ebx
0x18001fd4d  add     rdi, 238h
0x18001fd54  jmp     short loc_18001FD7E
0x18001fd56  add     rdi, 238h
0x18001fd5d  lea     rax, aReceivedBuffer; "Received buffer pointer is NULL or size"...
0x18001fd64  mov     rcx, rdi; this
0x18001fd67  mov     r9d, 8Bh; unsigned int
0x18001fd6d  mov     r8, r15; char *
0x18001fd70  mov     edx, ebp; unsigned __int8
0x18001fd72  mov     [rsp+78h+Format], rax; Format
0x18001fd77  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fd7c  mov     ebx, ebp
0x18001fd7e  mov     rax, [r14]
0x18001fd81  mov     r9d, 0A6h; unsigned int
0x18001fd87  mov     dword ptr [rsp+78h+var_48], ebx
0x18001fd8b  mov     r8, r15; char *
0x18001fd8e  mov     [rsp+78h+var_50], rax
0x18001fd93  mov     edx, 5; unsigned __int8
0x18001fd98  lea     rax, aReadCallbackBy; "read_callback, bytes: %Id, read status:"...
0x18001fd9f  mov     rcx, rdi; this
0x18001fda2  mov     [rsp+78h+Format], rax; Format
0x18001fda7  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fdac  test    esi, esi
0x18001fdae  jz      short loc_18001FDE4
0x18001fdb0  mov     r9d, 0A7h; unsigned int
0x18001fdb6  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001fdbd  mov     [rsp+78h+var_40], r9d
0x18001fdc2  mov     r8, r15; char *
0x18001fdc5  mov     [rsp+78h+var_48], rax
0x18001fdca  mov     edx, ebp; unsigned __int8
0x18001fdcc  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001fdd3  mov     dword ptr [rsp+78h+var_50], esi
0x18001fdd7  mov     rcx, rdi; this
0x18001fdda  mov     [rsp+78h+Format], rax; Format
0x18001fddf  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fde4  mov     eax, ebx
0x18001fde6  add     rsp, 48h
0x18001fdea  pop     r15
0x18001fdec  pop     r14
0x18001fdee  pop     rdi
0x18001fdef  pop     rsi
0x18001fdf0  pop     rbp
0x18001fdf1  pop     rbx
0x18001fdf2  retn
```
