# CFLACDecMFT::CreateDecodeEvents(void)

- ea: `0x18001d26c`
- end: `0x18001d330`
- name: `?CreateDecodeEvents@CFLACDecMFT@@AEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(CFLACDecMFT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d940`

## callees

- `0x18001d26c`
- `0x18001efc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d2b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2c6`

## string_xrefs

- `0x18001d27f`: `CreateDecodeEvents`
- `0x18001d293`: `CFLACDecMFT::CreateDecodeEvents`
- `0x18001d2fc`: `CFLACDecMFT::CreateDecodeEvents`

## pseudocode

```c
__int64 __fastcall CFLACDecMFT::CreateDecodeEvents(CFLACDecMFT *this)
{
  TraceLoggingHelperBase *v1; // rsi
  signed int v3; // ebx
  __int64 v4; // rdi
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v7; // zf

  v1 = (CFLACDecMFT *)((char *)this + 960);
  v3 = 0;
  TraceLoggingHelperBase::TraceVA(
    (CFLACDecMFT *)((char *)this + 960),
    5u,
    "CFLACDecMFT::CreateDecodeEvents",
    0x90u,
    "CreateDecodeEvents");
  v4 = 0;
  while ( 1 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + v4 + 113) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v7 = v3 == 0;
      if ( v3 < 0 )
        break;
    }
    v4 = (unsigned int)(v4 + 1);
    if ( (int)v4 >= 7 )
    {
      v7 = v3 == 0;
      break;
    }
  }
  if ( !v7 )
    TraceLoggingHelperBase::TraceVA(
      v1,
      2u,
      "CFLACDecMFT::CreateDecodeEvents",
      0xA0u,
      "Error %08X returned: File: %s, Line: %d",
      v3,
      "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecmft.cpp",
      160);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001d26c  push    rbx
0x18001d26e  push    rbp
0x18001d26f  push    rsi
0x18001d270  push    rdi
0x18001d271  sub     rsp, 48h
0x18001d275  lea     rsi, [rcx+3C0h]
0x18001d27c  mov     rbp, rcx
0x18001d27f  lea     rax, aCreatedecodeev; "CreateDecodeEvents"
0x18001d286  xor     ebx, ebx
0x18001d288  mov     r9d, 90h; unsigned int
0x18001d28e  mov     [rsp+68h+Format], rax; Format
0x18001d293  lea     r8, aCflacdecmftCre_0; "CFLACDecMFT::CreateDecodeEvents"
0x18001d29a  mov     rcx, rsi; this
0x18001d29d  lea     edx, [rbx+5]; unsigned __int8
0x18001d2a0  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001d2a5  xor     edi, edi
0x18001d2a7  xor     r9d, r9d; lpName
0x18001d2aa  xor     r8d, r8d; bInitialState
0x18001d2ad  xor     ecx, ecx; lpEventAttributes
0x18001d2af  lea     edx, [r9+1]; bManualReset
0x18001d2b3  call    cs:__imp_CreateEventW
0x18001d2b9  mov     [rbp+rdi*8+388h], rax
0x18001d2c1  test    rax, rax
0x18001d2c4  jnz     short loc_18001D2DF
0x18001d2c6  call    cs:__imp_GetLastError
0x18001d2cc  mov     ebx, eax
0x18001d2ce  test    eax, eax
0x18001d2d0  jle     short loc_18001D2DB
0x18001d2d2  movzx   ebx, ax
0x18001d2d5  or      ebx, 80070000h
0x18001d2db  test    ebx, ebx
0x18001d2dd  js      short loc_18001D2E8
0x18001d2df  inc     edi
0x18001d2e1  cmp     edi, 7
0x18001d2e4  jl      short loc_18001D2A7
0x18001d2e6  test    ebx, ebx
0x18001d2e8  jz      short loc_18001D325
0x18001d2ea  mov     r9d, 0A0h; unsigned int
0x18001d2f0  lea     rax, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001d2f7  mov     [rsp+68h+var_30], r9d
0x18001d2fc  lea     r8, aCflacdecmftCre_0; "CFLACDecMFT::CreateDecodeEvents"
0x18001d303  mov     [rsp+68h+var_38], rax
0x18001d308  mov     edx, 2; unsigned __int8
0x18001d30d  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001d314  mov     [rsp+68h+var_40], ebx
0x18001d318  mov     rcx, rsi; this
0x18001d31b  mov     [rsp+68h+Format], rax; Format
0x18001d320  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001d325  mov     eax, ebx
0x18001d327  add     rsp, 48h
0x18001d32b  pop     rdi
0x18001d32c  pop     rsi
0x18001d32d  pop     rbp
0x18001d32e  pop     rbx
0x18001d32f  retn
```
