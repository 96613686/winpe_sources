# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x14000f214`
- end: `0x14000f24c`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f620`
- `0x14000f660`

## callees

- `0x1400019bc`
- `0x140001a88`
- `0x14000f214`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // r9

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL, a2);
    if ( (_BYTE)result )
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
               v3,
               &byte_14001B0FF);
  }
  return result;
}

```

## disassembly

```asm
0x14000f214  sub     rsp, 28h
0x14000f218  mov     eax, [rcx]
0x14000f21a  mov     r8, rdx
0x14000f21d  mov     r9, rcx
0x14000f220  cmp     eax, 5
0x14000f223  jbe     short loc_14000F247
0x14000f225  mov     rdx, 400000000000h
0x14000f22f  call    _tlgKeywordOn
0x14000f234  test    al, al
0x14000f236  jz      short loc_14000F247
0x14000f238  lea     rdx, byte_14001B0FF
0x14000f23f  mov     rcx, r9
0x14000f242  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x14000f247  add     rsp, 28h
0x14000f24b  retn
```
