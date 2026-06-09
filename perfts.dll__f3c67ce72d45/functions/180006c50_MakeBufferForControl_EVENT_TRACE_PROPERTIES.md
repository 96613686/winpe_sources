# MakeBufferForControl(_EVENT_TRACE_PROPERTIES * *)

- ea: `0x180006c50`
- end: `0x180006d05`
- name: `?MakeBufferForControl@@YA_NPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `181`
- prototype: `bool __fastcall(struct _EVENT_TRACE_PROPERTIES **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180004e40`
- `0x18000576c`
- `0x18000823c`

## callees

- `0x180001140`
- `0x180006c50`
- `0x1800098f6`

## import_xrefs

- `msvcrt!malloc` at `0x180006c69`
- `msvcrt!malloc` at `0x180006c69`

## pseudocode

```c
bool __fastcall MakeBufferForControl(struct _EVENT_TRACE_PROPERTIES **a1)
{
  struct _EVENT_TRACE_PROPERTIES *v2; // rax
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  struct _EVENT_TRACE_PROPERTIES *v6; // rbx
  bool result; // al
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF
  const char *v9; // [rsp+50h] [rbp+18h] BYREF

  v2 = (struct _EVENT_TRACE_PROPERTIES *)malloc(0x208u);
  v6 = v2;
  if ( v2 )
  {
    memset_0(v2, 0, 0x208u);
    result = 1;
    v6->Wnode.BufferSize = 520;
    v6->Wnode.Flags = 0x20000;
    v6->Wnode.ClientContext = 2;
    v6->LogFileMode = 258;
    v6->MaximumFileSize = 10;
    v6->LoggerNameOffset = 120;
    v6->LogFileNameOffset = 0;
    *a1 = v6;
  }
  else
  {
    if ( (unsigned int)dword_180012020 > 2 )
    {
      v8 = 520;
      v9 = "Unable to allocate for EVENT_TRACE_PROPERTIES structure";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v3,
        byte_18000F0C2,
        v4,
        v5,
        (const unsigned __int16 **)&v9,
        (__int64)&v8);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006c50  mov     [rsp+arg_0], rbx
0x180006c55  mov     [rsp+arg_18], rsi
0x180006c5a  push    rdi
0x180006c5b  sub     rsp, 30h
0x180006c5f  mov     rdi, rcx
0x180006c62  mov     esi, 208h
0x180006c67  mov     ecx, esi; Size
0x180006c69  call    cs:__imp_malloc
0x180006c6f  mov     rbx, rax
0x180006c72  test    rax, rax
0x180006c75  jnz     short loc_180006CB7
0x180006c77  mov     eax, cs:dword_180012020
0x180006c7d  cmp     eax, 2
0x180006c80  jbe     short loc_180006CB3
0x180006c82  lea     rax, aUnableToAlloca; "Unable to allocate for EVENT_TRACE_PROP"...
0x180006c89  mov     [rsp+38h+arg_8], rsi
0x180006c8e  mov     [rsp+38h+arg_10], rax
0x180006c93  lea     rdx, byte_18000F0C2
0x180006c9a  lea     rax, [rsp+38h+arg_8]
0x180006c9f  mov     [rsp+38h+var_10], rax
0x180006ca4  lea     rax, [rsp+38h+arg_10]
0x180006ca9  mov     [rsp+38h+var_18], rax
0x180006cae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180006cb3  xor     al, al
0x180006cb5  jmp     short loc_180006CF5
0x180006cb7  mov     r8, rsi; Size
0x180006cba  xor     edx, edx; Val
0x180006cbc  mov     rcx, rbx; void *
0x180006cbf  call    memset_0
0x180006cc4  mov     al, 1
0x180006cc6  mov     [rbx], esi
0x180006cc8  mov     dword ptr [rbx+2Ch], 20000h
0x180006ccf  mov     dword ptr [rbx+28h], 2
0x180006cd6  mov     dword ptr [rbx+40h], 102h
0x180006cdd  mov     dword ptr [rbx+3Ch], 0Ah
0x180006ce4  mov     dword ptr [rbx+74h], 78h ; 'x'
0x180006ceb  mov     dword ptr [rbx+70h], 0
0x180006cf2  mov     [rdi], rbx
0x180006cf5  mov     rbx, [rsp+38h+arg_0]
0x180006cfa  mov     rsi, [rsp+38h+arg_18]
0x180006cff  add     rsp, 30h
0x180006d03  pop     rdi
0x180006d04  retn
```
