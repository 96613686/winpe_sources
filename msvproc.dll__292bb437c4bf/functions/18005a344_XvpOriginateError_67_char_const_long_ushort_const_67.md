# XvpOriginateError<67>(char * const,long,ushort const (&)[67])

- ea: `0x18005a344`
- end: `0x18005a3c3`
- name: `??$XvpOriginateError@$0ED@@@YAJQEADJAEAY0ED@$$CBG@Z`
- size: `127`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007148`

## callees

- `0x180001008`
- `0x18005a344`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005a3b2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005a3b2`

## string_xrefs

- `0x18005a35e`: `Combined rotation and mirroring is not supported for source format`
- `0x18005a376`: `CxCodeVideoProcMFTDataHandler::ConfigureConversions`

## pseudocode

```c
__int64 __fastcall XvpOriginateError<67>(const char *a1, int a2, const wchar_t *a3, __int64 a4)
{
  const char *v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+58h] [rbp+10h] BYREF
  const wchar_t *v7; // [rsp+60h] [rbp+18h] BYREF

  v7 = a3;
  v6 = a2;
  v5 = a1;
  if ( (unsigned int)dword_1801520E8 > 5 )
  {
    v7 = L"Combined rotation and mirroring is not supported for source format";
    v6 = -2147467259;
    v5 = "CxCodeVideoProcMFTDataHandler::ConfigureConversions";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (unsigned int)&v5,
      (unsigned int)&byte_180148027,
      (_DWORD)a3,
      a4,
      (__int64)&v5,
      (__int64)&v6,
      (__int64)&v7);
  }
  RoOriginateErrorW(2147500037LL, 66, L"Combined rotation and mirroring is not supported for source format", a4);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18005a344  mov     r11, rsp
0x18005a347  mov     [r11+18h], r8
0x18005a34b  mov     [rsp+arg_8], edx
0x18005a34f  mov     [r11+8], rcx
0x18005a353  push    rdi
0x18005a354  sub     rsp, 40h
0x18005a358  mov     eax, cs:dword_1801520E8
0x18005a35e  lea     rdi, aCombinedRotati; "Combined rotation and mirroring is not "...
0x18005a365  cmp     eax, 5
0x18005a368  jbe     short loc_18005A3A5
0x18005a36a  lea     rcx, [r11+18h]
0x18005a36e  mov     [r11+18h], rdi
0x18005a372  mov     [r11-18h], rcx
0x18005a376  lea     rax, aCxcodevideopro_127; "CxCodeVideoProcMFTDataHandler::Configur"...
0x18005a37d  lea     rcx, [r11+10h]
0x18005a381  mov     [rsp+48h+arg_8], 80004005h
0x18005a389  mov     [r11-20h], rcx
0x18005a38d  lea     rdx, byte_180148027
0x18005a394  lea     rcx, [r11+8]
0x18005a398  mov     [r11+8], rax
0x18005a39c  mov     [r11-28h], rcx
0x18005a3a0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18005a3a5  mov     r8, rdi
0x18005a3a8  mov     edx, 42h ; 'B'
0x18005a3ad  mov     ecx, 80004005h
0x18005a3b2  call    cs:__imp_RoOriginateErrorW
0x18005a3b8  mov     eax, 80004005h
0x18005a3bd  add     rsp, 40h
0x18005a3c1  pop     rdi
0x18005a3c2  retn
```
