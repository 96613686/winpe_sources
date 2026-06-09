# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x180001450`
- end: `0x1800014ae`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010430`

## callees

- `0x18000123c`
- `0x180007740`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD v6[6]; // [rsp+30h] [rbp-48h] BYREF

  v6[4] = a5;
  v6[5] = 4;
  return tlgWriteTransfer_EtwEventWriteTransfer((unsigned int)&dword_18002B048, a2, 0, 0, 3, (__int64)v6);
}

```

## disassembly

```asm
0x180001450  mov     r11, rsp
0x180001453  sub     rsp, 78h
0x180001457  mov     rax, cs:__security_cookie
0x18000145e  xor     rax, rsp
0x180001461  mov     [rsp+78h+var_18], rax
0x180001466  mov     rax, [rsp+78h+arg_20]
0x18000146e  lea     rcx, dword_18002B048
0x180001475  mov     [r11-28h], rax
0x180001479  xor     r9d, r9d
0x18000147c  lea     rax, [r11-48h]
0x180001480  mov     qword ptr [r11-20h], 4
0x180001488  mov     [r11-50h], rax
0x18000148c  xor     r8d, r8d
0x18000148f  mov     [rsp+78h+var_58], 3
0x180001497  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000149c  mov     rcx, [rsp+78h+var_18]
0x1800014a1  xor     rcx, rsp; StackCookie
0x1800014a4  call    __security_check_cookie
0x1800014a9  add     rsp, 78h
0x1800014ad  retn
```
