# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x140001a88`
- end: `0x140001ac7`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `63`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f214`
- `0x14000f788`
- `0x140012a7c`

## callees

- `0x1400019e8`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _BYTE v4[32]; // [rsp+30h] [rbp-38h] BYREF

  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 2, v4);
}

```

## disassembly

```asm
0x140001a88  sub     rsp, 68h
0x140001a8c  mov     rax, cs:__security_cookie
0x140001a93  xor     rax, rsp
0x140001a96  mov     [rsp+68h+var_18], rax
0x140001a9b  lea     rax, [rsp+68h+var_38]
0x140001aa0  xor     r9d, r9d
0x140001aa3  mov     [rsp+68h+var_40], rax
0x140001aa8  mov     [rsp+68h+var_48], 2
0x140001ab0  call    _tlgWriteTransfer_EventWriteTransfer
0x140001ab5  mov     rcx, [rsp+68h+var_18]
0x140001aba  xor     rcx, rsp; StackCookie
0x140001abd  call    __security_check_cookie
0x140001ac2  add     rsp, 68h
0x140001ac6  retn
```
