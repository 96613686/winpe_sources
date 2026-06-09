# AOMDHandler::UpdateStatsOnExit(void)

- ea: `0x1800157f8`
- end: `0x180015879`
- name: `?UpdateStatsOnExit@AOMDHandler@@AEAAJXZ`
- size: `129`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180007944`

## callees

- `0x180001008`
- `0x18000f144`
- `0x1800157f8`

## string_xrefs

- `0x18001581e`: `UpdateStatsOnExit_Starting`

## pseudocode

```c
__int64 __fastcall AOMDHandler::UpdateStatsOnExit(AOMDHandler *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // r8d
  int v4; // r9d
  int v5; // ecx
  const wchar_t *v7; // [rsp+48h] [rbp+10h] BYREF

  v2 = TlgHelper::Provider();
  if ( *(_DWORD *)v2 > 4u && (*((_BYTE *)v2 + 16) & 2) != 0 && (*((_QWORD *)v2 + 3) & 2LL) == *((_QWORD *)v2 + 3) )
  {
    v7 = L"UpdateStatsOnExit_Starting";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v2,
      (unsigned int)&unk_18002AB01,
      v3,
      v4,
      (__int64)&v7);
  }
  if ( (unsigned int)g_aomdPromptResult <= 0xE )
  {
    v5 = 29952;
    if ( _bittest(&v5, g_aomdPromptResult) )
    {
      *((_QWORD *)this + 12) = *((_QWORD *)this + 13);
      *((_QWORD *)this + 13) = 0;
      *((_DWORD *)this + 28) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800157f8  push    rbx
0x1800157fa  sub     rsp, 30h
0x1800157fe  mov     rbx, rcx
0x180015801  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180015806  cmp     dword ptr [rax], 4
0x180015809  jbe     short loc_180015843
0x18001580b  test    byte ptr [rax+10h], 2
0x18001580f  jz      short loc_180015843
0x180015811  mov     rcx, [rax+18h]
0x180015815  and     ecx, 2
0x180015818  cmp     rcx, [rax+18h]
0x18001581c  jnz     short loc_180015843
0x18001581e  lea     rcx, aUpdatestatsone; "UpdateStatsOnExit_Starting"
0x180015825  mov     [rsp+38h+arg_8], rcx
0x18001582a  lea     rcx, [rsp+38h+arg_8]
0x18001582f  mov     [rsp+38h+var_18], rcx
0x180015834  lea     rdx, byte_18002AB01
0x18001583b  mov     rcx, rax
0x18001583e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180015843  mov     eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180015849  nop
0x18001584a  cmp     eax, 0Eh
0x18001584d  ja      short loc_18001586A
0x18001584f  mov     ecx, 7500h
0x180015854  bt      ecx, eax
0x180015857  jnb     short loc_18001586A
0x180015859  mov     rax, [rbx+68h]
0x18001585d  mov     [rbx+60h], rax
0x180015861  and     qword ptr [rbx+68h], 0
0x180015866  and     dword ptr [rbx+70h], 0
0x18001586a  xor     eax, eax
0x18001586c  jmp     short loc_180015872
0x18001586e  mov     eax, dword ptr [rsp+38h+arg_8]
0x180015872  add     rsp, 30h
0x180015876  pop     rbx
0x180015877  retn
```
