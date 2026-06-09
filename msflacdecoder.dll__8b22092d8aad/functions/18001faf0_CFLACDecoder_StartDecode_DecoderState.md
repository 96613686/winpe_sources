# CFLACDecoder::StartDecode(DecoderState)

- ea: `0x18001faf0`
- end: `0x18001fc07`
- name: `?StartDecode@CFLACDecoder@@QEAAJW4DecoderState@@@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ee24`

## callees

- `0x18001efc4`
- `0x18001faf0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fba0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fba0`

## pseudocode

```c
__int64 __fastcall CFLACDecoder::StartDecode(_QWORD *a1, int a2)
{
  TraceLoggingHelperBase *v2; // rsi
  unsigned int v5; // ebx
  char v6; // al
  HANDLE Thread; // rax

  v2 = (TraceLoggingHelperBase *)(a1 + 71);
  TraceLoggingHelperBase::TraceVA(
    (TraceLoggingHelperBase *)(a1 + 71),
    4u,
    "CFLACDecoder::StartDecode",
    0x54u,
    "StartDecode (state: %i)",
    a2);
  if ( a1[69] )
  {
    v5 = -1072875854;
    goto LABEL_11;
  }
  *((_DWORD *)a1 + 140) = -1;
  if ( !a2 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 216LL))(a1);
    goto LABEL_7;
  }
  if ( a2 == 2 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 208LL))(a1);
LABEL_7:
    if ( !v6 )
    {
      v5 = -1072875845;
      goto LABEL_11;
    }
  }
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DecodingThreadProc, a1, 0, 0);
  a1[69] = Thread;
  if ( Thread )
    return 0;
  v5 = -2147024882;
LABEL_11:
  TraceLoggingHelperBase::TraceVA(
    v2,
    2u,
    "CFLACDecoder::StartDecode",
    0x7Fu,
    "Error %08X returned: File: %s, Line: %d",
    v5,
    "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecoder.cpp",
    127);
  return v5;
}

```

## disassembly

```asm
0x18001faf0  mov     [rsp+arg_0], rbx
0x18001faf5  mov     [rsp+arg_8], rsi
0x18001fafa  push    rdi
0x18001fafb  sub     rsp, 40h
0x18001faff  mov     dword ptr [rsp+48h+lpThreadId], edx
0x18001fb03  lea     rsi, [rcx+238h]
0x18001fb0a  mov     r9d, 54h ; 'T'; unsigned int
0x18001fb10  lea     rax, aStartdecodeSta; "StartDecode (state: %i)"
0x18001fb17  mov     edi, edx
0x18001fb19  mov     qword ptr [rsp+48h+dwCreationFlags], rax; Format
0x18001fb1e  mov     rbx, rcx
0x18001fb21  lea     r8, aCflacdecoderSt; "CFLACDecoder::StartDecode"
0x18001fb28  mov     rcx, rsi; this
0x18001fb2b  lea     edx, [r9-50h]; unsigned __int8
0x18001fb2f  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fb34  cmp     qword ptr [rbx+228h], 0
0x18001fb3c  jz      short loc_18001FB45
0x18001fb3e  mov     ebx, 0C00D36B2h
0x18001fb43  jmp     short loc_18001FBB7
0x18001fb45  mov     dword ptr [rbx+230h], 0FFFFFFFFh
0x18001fb4f  test    edi, edi
0x18001fb51  jnz     short loc_18001FB5F
0x18001fb53  mov     rax, [rbx]
0x18001fb56  mov     rax, [rax+0D8h]
0x18001fb5d  jmp     short loc_18001FB6E
0x18001fb5f  cmp     edi, 2
0x18001fb62  jnz     short loc_18001FB81
0x18001fb64  mov     rax, [rbx]
0x18001fb67  mov     rax, [rax+0D0h]
0x18001fb6e  mov     rcx, rbx
0x18001fb71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb76  test    al, al
0x18001fb78  jnz     short loc_18001FB81
0x18001fb7a  mov     ebx, 0C00D36BBh
0x18001fb7f  jmp     short loc_18001FBB7
0x18001fb81  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x18001fb8a  lea     r8, ?DecodingThreadProc@@YAKPEAX@Z; lpStartAddress
0x18001fb91  mov     r9, rbx; lpParameter
0x18001fb94  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18001fb9c  xor     edx, edx; dwStackSize
0x18001fb9e  xor     ecx, ecx; lpThreadAttributes
0x18001fba0  call    cs:__imp_CreateThread
0x18001fba6  mov     [rbx+228h], rax
0x18001fbad  test    rax, rax
0x18001fbb0  jnz     short loc_18001FBF3
0x18001fbb2  mov     ebx, 8007000Eh
0x18001fbb7  mov     r9d, 7Fh; unsigned int
0x18001fbbd  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001fbc4  mov     [rsp+48h+var_10], r9d
0x18001fbc9  lea     r8, aCflacdecoderSt; "CFLACDecoder::StartDecode"
0x18001fbd0  mov     [rsp+48h+var_18], rax
0x18001fbd5  mov     rcx, rsi; this
0x18001fbd8  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001fbdf  mov     dword ptr [rsp+48h+lpThreadId], ebx
0x18001fbe3  lea     edx, [r9-7Dh]; unsigned __int8
0x18001fbe7  mov     qword ptr [rsp+48h+dwCreationFlags], rax; Format
0x18001fbec  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001fbf1  jmp     short loc_18001FBF5
0x18001fbf3  xor     ebx, ebx
0x18001fbf5  mov     rsi, [rsp+48h+arg_8]
0x18001fbfa  mov     eax, ebx
0x18001fbfc  mov     rbx, [rsp+48h+arg_0]
0x18001fc01  add     rsp, 40h
0x18001fc05  pop     rdi
0x18001fc06  retn
```
