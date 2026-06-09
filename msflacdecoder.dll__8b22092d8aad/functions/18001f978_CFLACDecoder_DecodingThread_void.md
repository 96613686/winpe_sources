# CFLACDecoder::DecodingThread(void)

- ea: `0x18001f978`
- end: `0x18001fa86`
- name: `?DecodingThread@CFLACDecoder@@QEAAJXZ`
- size: `270`
- prototype: `__int64 __fastcall(CFLACDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001fa90`

## callees

- `0x180002d30`
- `0x18001efc4`
- `0x18001f978`
- `0x180056010`

## string_xrefs

- `0x18001f991`: `DecodingThread`
- `0x18001f9a6`: `CFLACDecoder::DecodingThread`
- `0x18001fa46`: `CFLACDecoder::DecodingThread`

## pseudocode

```c
__int64 __fastcall CFLACDecoder::DecodingThread(CFLACDecoder *this)
{
  TraceLoggingHelperBase *v1; // rdi
  int v3; // ecx
  __int64 v4; // rax
  char v5; // si
  unsigned int v6; // ebx
  char v8; // [rsp+50h] [rbp+8h] BYREF

  v1 = (CFLACDecoder *)((char *)this + 568);
  TraceLoggingHelperBase::TraceVA(
    (CFLACDecoder *)((char *)this + 568),
    5u,
    "CFLACDecoder::DecodingThread",
    0x10Du,
    "DecodingThread");
  v3 = 0;
  if ( *((_DWORD *)this + 140) == -1 )
    goto LABEL_6;
  do
  {
    v4 = *(_QWORD *)this;
    if ( v3 )
      (*(void (__fastcall **)(CFLACDecoder *))(v4 + 208))(this);
    else
      (*(void (__fastcall **)(CFLACDecoder *))(v4 + 216))(this);
    *((_DWORD *)this + 140) = -1;
LABEL_6:
    v5 = (*(__int64 (__fastcall **)(CFLACDecoder *))(*(_QWORD *)this + 248LL))(this);
    v3 = *(_DWORD *)FLAC::Decoder::Stream::get_state(this, &v8);
  }
  while ( *((_DWORD *)this + 140) != -1 );
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 68) + 24LL))(*((_QWORD *)this + 68));
  if ( v5 )
  {
    return 0;
  }
  else
  {
    v6 = -1072875845;
    TraceLoggingHelperBase::TraceVA(
      v1,
      2u,
      "CFLACDecoder::DecodingThread",
      0x13Bu,
      "Error %08X returned: File: %s, Line: %d",
      -1072875845,
      "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecoder.cpp",
      315);
  }
  return v6;
}

```

## disassembly

```asm
0x18001f978  mov     [rsp+arg_8], rbx
0x18001f97d  mov     [rsp+arg_10], rsi
0x18001f982  push    rdi
0x18001f983  sub     rsp, 40h
0x18001f987  lea     rdi, [rcx+238h]
0x18001f98e  mov     rbx, rcx
0x18001f991  lea     rax, aDecodingthread; "DecodingThread"
0x18001f998  mov     rcx, rdi; this
0x18001f99b  mov     r9d, 10Dh; unsigned int
0x18001f9a1  mov     [rsp+48h+Format], rax; Format
0x18001f9a6  lea     r8, aCflacdecoderDe; "CFLACDecoder::DecodingThread"
0x18001f9ad  mov     edx, 5; unsigned __int8
0x18001f9b2  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f9b7  xor     ecx, ecx
0x18001f9b9  cmp     dword ptr [rbx+230h], 0FFFFFFFFh
0x18001f9c0  jz      short loc_18001F9EB
0x18001f9c2  mov     rax, [rbx]
0x18001f9c5  test    ecx, ecx
0x18001f9c7  mov     rcx, rbx
0x18001f9ca  jnz     short loc_18001F9D5
0x18001f9cc  mov     rax, [rax+0D8h]
0x18001f9d3  jmp     short loc_18001F9DC
0x18001f9d5  mov     rax, [rax+0D0h]
0x18001f9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9e1  mov     dword ptr [rbx+230h], 0FFFFFFFFh
0x18001f9eb  mov     rax, [rbx]
0x18001f9ee  mov     rcx, rbx
0x18001f9f1  mov     rax, [rax+0F8h]
0x18001f9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9fd  lea     rdx, [rsp+48h+arg_0]
0x18001fa02  mov     rcx, rbx
0x18001fa05  mov     sil, al
0x18001fa08  call    ?get_state@Stream@Decoder@FLAC@@QEBA?AVState@123@XZ; FLAC::Decoder::Stream::get_state(void)
0x18001fa0d  cmp     dword ptr [rbx+230h], 0FFFFFFFFh
0x18001fa14  mov     ecx, [rax]
0x18001fa16  jnz     short loc_18001F9C2
0x18001fa18  mov     rcx, [rbx+220h]
0x18001fa1f  mov     rdx, [rcx]
0x18001fa22  mov     rax, [rdx+18h]
0x18001fa26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa2b  test    sil, sil
0x18001fa2e  jz      short loc_18001FA34
0x18001fa30  xor     ebx, ebx
0x18001fa32  jmp     short loc_18001FA74
0x18001fa34  mov     r9d, 13Bh; unsigned int
0x18001fa3a  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001fa41  mov     [rsp+48h+var_10], r9d
0x18001fa46  lea     r8, aCflacdecoderDe; "CFLACDecoder::DecodingThread"
0x18001fa4d  mov     [rsp+48h+var_18], rax
0x18001fa52  mov     ebx, 0C00D36BBh
0x18001fa57  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001fa5e  mov     [rsp+48h+var_20], ebx
0x18001fa62  mov     edx, 2; unsigned __int8
0x18001fa67  mov     [rsp+48h+Format], rax; Format
0x18001fa6c  mov     rcx, rdi; this
0x18001fa6f  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fa74  mov     rsi, [rsp+48h+arg_10]
0x18001fa79  mov     eax, ebx
0x18001fa7b  mov     rbx, [rsp+48h+arg_8]
0x18001fa80  add     rsp, 40h
0x18001fa84  pop     rdi
0x18001fa85  retn
```
