# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x180001106`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U3@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@545@Z`
- size: `254`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004518`

## callees

- `0x180001008`
- `0x1800012a8`
- `0x180001a50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  __int64 v9; // rcx
  __int64 v10; // rax

  v9 = -1;
  if ( *a9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_BYTE *)(*a9 + v10) );
  }
  if ( *a6 )
  {
    do
      ++v9;
    while ( *(_BYTE *)(*a6 + v9) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_180019048, a2, 0);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-27h]
0x18000100f  sub     rsp, 0C0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+27h+var_10], rax
0x180001024  mov     rax, [rbp+27h+arg_48]
0x180001028  xor     r9d, r9d
0x18000102b  mov     [rbp+27h+var_20], rax
0x18000102f  mov     r10, rdx
0x180001032  mov     rax, [rbp+27h+arg_40]
0x180001036  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000103a  mov     [rbp+27h+var_18], 4
0x180001042  lea     r8d, [r9+1]
0x180001046  mov     rdx, [rax]
0x180001049  test    rdx, rdx
0x18000104c  jz      short loc_18000105E
0x18000104e  mov     rax, rcx
0x180001051  inc     rax
0x180001054  cmp     [rdx+rax], r9b
0x180001058  jnz     short loc_180001051
0x18000105a  inc     eax
0x18000105c  jmp     short loc_180001068
0x18000105e  lea     rdx, word_180013F7A
0x180001065  mov     eax, r8d
0x180001068  mov     [rbp+27h+var_28], eax
0x18000106b  mov     rax, [rbp+27h+arg_38]
0x18000106f  mov     [rbp+27h+var_40], rax
0x180001073  mov     rax, [rbp+27h+arg_30]
0x180001077  mov     [rbp+27h+var_50], rax
0x18000107b  mov     rax, [rbp+27h+arg_28]
0x18000107f  mov     [rbp+27h+var_30], rdx
0x180001083  mov     [rbp+27h+var_24], r9d
0x180001087  mov     [rbp+27h+var_38], 4
0x18000108f  mov     rdx, [rax]
0x180001092  mov     [rbp+27h+var_48], 4
0x18000109a  test    rdx, rdx
0x18000109d  jz      short loc_1800010AE
0x18000109f  inc     rcx
0x1800010a2  cmp     [rdx+rcx], r9b
0x1800010a6  jnz     short loc_18000109F
0x1800010a8  lea     r8d, [rcx+1]
0x1800010ac  jmp     short loc_1800010B5
0x1800010ae  lea     rdx, word_180013F7A
0x1800010b5  mov     rax, [rbp+27h+arg_20]
0x1800010b9  mov     ecx, 8
0x1800010be  mov     [rbp+27h+var_70], rax
0x1800010c2  lea     rax, [rbp+27h+var_90]
0x1800010c6  mov     [rsp+0C0h+var_98], rax
0x1800010cb  mov     [rsp+0C0h+var_A0], ecx
0x1800010cf  mov     [rbp+27h+var_60], rdx
0x1800010d3  mov     rdx, r10
0x1800010d6  mov     [rbp+27h+var_58], r8d
0x1800010da  xor     r8d, r8d
0x1800010dd  mov     [rbp+27h+var_68], rcx
0x1800010e1  lea     rcx, dword_180019048
0x1800010e8  mov     [rbp+27h+var_54], r9d
0x1800010ec  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010f1  mov     rcx, [rbp+27h+var_10]
0x1800010f5  xor     rcx, rsp; StackCookie
0x1800010f8  call    __security_check_cookie
0x1800010fd  add     rsp, 0C0h
0x180001104  pop     rbp
0x180001105  retn
```
