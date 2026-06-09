# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800013ac`
- end: `0x180001449`
- name: `??$Write@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `157`
- prototype: ``
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
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 **a5,
        __int64 a6,
        __int64 a7)
{
  int v7; // ecx
  _BYTE v9[32]; // [rsp+30h] [rbp-31h] BYREF
  _DWORD *v10; // [rsp+50h] [rbp-11h]
  __int64 v11; // [rsp+58h] [rbp-9h]
  __int64 v12; // [rsp+60h] [rbp-1h]
  _DWORD v13[2]; // [rsp+68h] [rbp+7h] BYREF
  __int64 v14; // [rsp+70h] [rbp+Fh]
  __int64 v15; // [rsp+78h] [rbp+17h]
  __int64 v16; // [rsp+80h] [rbp+1Fh]
  __int64 v17; // [rsp+88h] [rbp+27h]

  v16 = a7;
  v14 = a6;
  v10 = v13;
  v17 = 8;
  v15 = 4;
  v11 = 2;
  v7 = **a5;
  v12 = *((_QWORD *)*a5 + 1);
  v13[0] = v7;
  v13[1] = 0;
  return tlgWriteTransfer_EtwEventWriteTransfer((__int64)&dword_18002B048, a2, 0, 0, 6, (__int64)v9);
}

```

## disassembly

```asm
0x1800013ac  push    rbp
0x1800013ae  lea     rbp, [rsp-3Fh]
0x1800013b3  sub     rsp, 0A0h
0x1800013ba  mov     rax, cs:__security_cookie
0x1800013c1  xor     rax, rsp
0x1800013c4  mov     [rbp+3Fh+var_10], rax
0x1800013c8  mov     rax, [rbp+3Fh+arg_30]
0x1800013cc  xor     r8d, r8d
0x1800013cf  mov     [rbp+3Fh+var_20], rax
0x1800013d3  xor     r9d, r9d
0x1800013d6  mov     rax, [rbp+3Fh+arg_28]
0x1800013da  mov     [rbp+3Fh+var_30], rax
0x1800013de  lea     rax, [rbp+3Fh+var_38]
0x1800013e2  mov     [rbp+3Fh+var_50], rax
0x1800013e6  mov     rax, [rbp+3Fh+arg_20]
0x1800013ea  mov     [rbp+3Fh+var_18], 8
0x1800013f2  mov     [rbp+3Fh+var_28], 4
0x1800013fa  mov     [rbp+3Fh+var_48], 2
0x180001402  mov     rax, [rax]
0x180001405  movzx   ecx, word ptr [rax]
0x180001408  mov     rax, [rax+8]
0x18000140c  mov     [rbp+3Fh+var_40], rax
0x180001410  lea     rax, [rbp+3Fh+var_70]
0x180001414  mov     [rbp+3Fh+var_38], ecx
0x180001417  lea     rcx, dword_18002B048
0x18000141e  mov     [rsp+0A0h+var_78], rax
0x180001423  mov     [rsp+0A0h+var_80], 6
0x18000142b  mov     [rbp+3Fh+var_34], r8d
0x18000142f  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180001434  mov     rcx, [rbp+3Fh+var_10]
0x180001438  xor     rcx, rsp; StackCookie
0x18000143b  call    __security_check_cookie
0x180001440  add     rsp, 0A0h
0x180001447  pop     rbp
0x180001448  retn
```
