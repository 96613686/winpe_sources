# RdpDWMDirectWindowContext::CreateCompositionSurface(void *)

- ea: `0x18000d4b4`
- end: `0x18000d563`
- name: `?CreateCompositionSurface@RdpDWMDirectWindowContext@@QEAAJPEAX@Z`
- size: `175`
- prototype: `__int64 __fastcall(RdpDWMDirectWindowContext *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fcdc`

## callees

- `0x180001188`
- `0x18000d4b4`
- `0x18002c010`

## string_xrefs

- `0x18000d4fb`: `CreateCompositionSurface`
- `0x18000d502`: `Failed to send the composition surface creation to the driver`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::CreateCompositionSurface(RdpDWMDirectWindowContext *this, void *a2)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  int v8; // [rsp+60h] [rbp+8h] BYREF
  const char *v9; // [rsp+68h] [rbp+10h] BYREF
  const char *v10; // [rsp+70h] [rbp+18h] BYREF
  const char *v11; // [rsp+78h] [rbp+20h] BYREF

  if ( a2 != *((void **)this + 81) )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 82) + 80LL))(
           *((_QWORD *)this + 82),
           *((_QWORD *)this + 8),
           a2);
    if ( v4 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      v8 = v4;
      v9 = "CreateCompositionSurface";
      v10 = "Failed to send the composition surface creation to the driver";
      v11 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)"CreateCompositionSurface",
        (__int64)byte_18003939D,
        v5,
        v6,
        (const unsigned __int16 **)&v11,
        (const unsigned __int16 **)&v10,
        (__int64)&v8,
        (const unsigned __int16 **)&v9);
    }
    *((_QWORD *)this + 81) = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d4b4  push    rbx
0x18000d4b6  push    rdi
0x18000d4b7  sub     rsp, 48h
0x18000d4bb  mov     rdi, rdx
0x18000d4be  mov     rbx, rcx
0x18000d4c1  cmp     rdx, [rcx+288h]
0x18000d4c8  jz      loc_18000D55A
0x18000d4ce  mov     rcx, [rcx+290h]
0x18000d4d5  mov     r8, rdx
0x18000d4d8  mov     rdx, [rbx+40h]
0x18000d4dc  mov     rax, [rcx]
0x18000d4df  mov     rax, [rax+50h]
0x18000d4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4e8  test    eax, eax
0x18000d4ea  jns     short loc_18000D553
0x18000d4ec  mov     ecx, cs:dword_180044008
0x18000d4f2  cmp     ecx, 3
0x18000d4f5  jbe     short loc_18000D553
0x18000d4f7  mov     [rsp+58h+arg_0], eax
0x18000d4fb  lea     rcx, aCreatecomposit; "CreateCompositionSurface"
0x18000d502  lea     rax, aFailedToSendTh_0; "Failed to send the composition surface "...
0x18000d509  mov     [rsp+58h+arg_8], rcx
0x18000d50e  mov     [rsp+58h+arg_10], rax
0x18000d513  lea     rdx, byte_18003939D
0x18000d51a  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000d521  mov     [rsp+58h+arg_18], rax
0x18000d526  lea     rax, [rsp+58h+arg_8]
0x18000d52b  mov     [rsp+58h+var_20], rax
0x18000d530  lea     rax, [rsp+58h+arg_0]
0x18000d535  mov     [rsp+58h+var_28], rax
0x18000d53a  lea     rax, [rsp+58h+arg_10]
0x18000d53f  mov     [rsp+58h+var_30], rax
0x18000d544  lea     rax, [rsp+58h+arg_18]
0x18000d549  mov     [rsp+58h+var_38], rax
0x18000d54e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000d553  mov     [rbx+288h], rdi
0x18000d55a  xor     eax, eax
0x18000d55c  add     rsp, 48h
0x18000d560  pop     rdi
0x18000d561  pop     rbx
0x18000d562  retn
```
