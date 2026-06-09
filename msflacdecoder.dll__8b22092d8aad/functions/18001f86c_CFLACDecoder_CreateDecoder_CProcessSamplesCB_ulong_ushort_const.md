# CFLACDecoder::CreateDecoder(CProcessSamplesCB *,ulong,ushort const *)

- ea: `0x18001f86c`
- end: `0x18001f972`
- name: `?CreateDecoder@CFLACDecoder@@QEAAJPEAVCProcessSamplesCB@@KPEBG@Z`
- size: `262`
- prototype: `int(CFLACDecoder *__hidden this, struct CProcessSamplesCB *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d338`

## callees

- `0x18001ef50`
- `0x18001efc4`
- `0x18001f86c`
- `0x180056010`

## string_xrefs

- `0x18001f889`: `CreateDecoder`
- `0x18001f89b`: `CFLACDecoder::CreateDecoder`
- `0x18001f8d7`: `CFLACDecoder::CreateDecoder`
- `0x18001f913`: `CFLACDecoder::CreateDecoder`
- `0x18001f8e4`: `CreateDecoder failed with FLAC__StreamDecoderInitStatus: %i`

## pseudocode

```c
__int64 __fastcall CFLACDecoder::CreateDecoder(
        CFLACDecoder *this,
        struct CProcessSamplesCB *a2,
        int a3,
        const unsigned __int16 *a4)
{
  TraceLoggingHelperBase *v5; // rbp
  unsigned int v9; // ebx
  int v10; // eax

  v5 = (CFLACDecoder *)((char *)this + 568);
  TraceLoggingHelperBase::TraceVA(
    (CFLACDecoder *)((char *)this + 568),
    4u,
    "CFLACDecoder::CreateDecoder",
    0x2Du,
    "CreateDecoder");
  if ( !a2 )
  {
    v9 = -2147467261;
LABEL_5:
    TraceLoggingHelperBase::TraceVA(
      v5,
      2u,
      "CFLACDecoder::CreateDecoder",
      0x4Du,
      "Error %08X returned: File: %s, Line: %d",
      v9,
      "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecoder.cpp",
      77);
    return v9;
  }
  v10 = (*(__int64 (__fastcall **)(CFLACDecoder *))(*(_QWORD *)this + 176LL))(this);
  if ( v10 )
  {
    TraceLoggingHelperBase::TraceVA(
      v5,
      2u,
      "CFLACDecoder::CreateDecoder",
      0x3Eu,
      "CreateDecoder failed with FLAC__StreamDecoderInitStatus: %i",
      v10);
    v9 = -1072875845;
    goto LABEL_5;
  }
  v9 = 0;
  *((_QWORD *)this + 68) = a2;
  *((_DWORD *)this + 132) = a3;
  if ( a4 )
    StringCchCopyW((unsigned __int16 *)this + 8, 0x100u, a4);
  return v9;
}

```

## disassembly

```asm
0x18001f86c  push    rbx
0x18001f86e  push    rbp
0x18001f86f  push    rsi
0x18001f870  push    rdi
0x18001f871  push    r14
0x18001f873  push    r15
0x18001f875  sub     rsp, 48h
0x18001f879  mov     rsi, r9
0x18001f87c  lea     rbp, [rcx+238h]
0x18001f883  mov     r9d, 2Dh ; '-'; unsigned int
0x18001f889  lea     rax, aCreatedecoder; "CreateDecoder"
0x18001f890  mov     r15d, r8d
0x18001f893  mov     [rsp+78h+Format], rax; Format
0x18001f898  mov     r14, rdx
0x18001f89b  lea     r8, aCflacdecoderCr; "CFLACDecoder::CreateDecoder"
0x18001f8a2  mov     rdi, rcx
0x18001f8a5  mov     rcx, rbp; this
0x18001f8a8  lea     edx, [r9-29h]; unsigned __int8
0x18001f8ac  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f8b1  test    r14, r14
0x18001f8b4  jnz     short loc_18001F8BD
0x18001f8b6  mov     ebx, 80004003h
0x18001f8bb  jmp     short loc_18001F901
0x18001f8bd  mov     rax, [rdi]
0x18001f8c0  mov     rcx, rdi
0x18001f8c3  mov     rax, [rax+0B0h]
0x18001f8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8cf  test    eax, eax
0x18001f8d1  jz      short loc_18001F93D
0x18001f8d3  mov     [rsp+78h+var_50], eax
0x18001f8d7  lea     r8, aCflacdecoderCr; "CFLACDecoder::CreateDecoder"
0x18001f8de  mov     r9d, 3Eh ; '>'; unsigned int
0x18001f8e4  lea     rax, aCreatedecoderF; "CreateDecoder failed with FLAC__StreamD"...
0x18001f8eb  mov     rcx, rbp; this
0x18001f8ee  mov     [rsp+78h+Format], rax; Format
0x18001f8f3  lea     edx, [r9-3Ch]; unsigned __int8
0x18001f8f7  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f8fc  mov     ebx, 0C00D36BBh
0x18001f901  mov     r9d, 4Dh ; 'M'; unsigned int
0x18001f907  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001f90e  mov     [rsp+78h+var_40], r9d
0x18001f913  lea     r8, aCflacdecoderCr; "CFLACDecoder::CreateDecoder"
0x18001f91a  mov     [rsp+78h+var_48], rax
0x18001f91f  mov     rcx, rbp; this
0x18001f922  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001f929  mov     [rsp+78h+var_50], ebx
0x18001f92d  lea     edx, [r9-4Bh]; unsigned __int8
0x18001f931  mov     [rsp+78h+Format], rax; Format
0x18001f936  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f93b  jmp     short loc_18001F963
0x18001f93d  xor     ebx, ebx
0x18001f93f  mov     [rdi+220h], r14
0x18001f946  mov     [rdi+210h], r15d
0x18001f94d  test    rsi, rsi
0x18001f950  jz      short loc_18001F963
0x18001f952  lea     rcx, [rdi+10h]; unsigned __int16 *
0x18001f956  mov     r8, rsi; unsigned __int16 *
0x18001f959  mov     edx, 100h; unsigned __int64
0x18001f95e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f963  mov     eax, ebx
0x18001f965  add     rsp, 48h
0x18001f969  pop     r15
0x18001f96b  pop     r14
0x18001f96d  pop     rdi
0x18001f96e  pop     rsi
0x18001f96f  pop     rbp
0x18001f970  pop     rbx
0x18001f971  retn
```
