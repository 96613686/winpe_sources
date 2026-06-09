# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001408`
- end: `0x1800014d0`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009a80`

## callees

- `0x1800011cc`
- `0x180001408`
- `0x180002270`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        const unsigned __int16 **a9)
{
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-51h] BYREF
  __int64 v14; // [rsp+50h] [rbp-31h]
  __int64 v15; // [rsp+58h] [rbp-29h]
  __int64 v16; // [rsp+60h] [rbp-21h]
  __int64 v17; // [rsp+68h] [rbp-19h]
  __int64 v18; // [rsp+70h] [rbp-11h]
  __int64 v19; // [rsp+78h] [rbp-9h]
  __int64 v20; // [rsp+80h] [rbp-1h]
  __int64 v21; // [rsp+88h] [rbp+7h]
  const unsigned __int16 *v22; // [rsp+90h] [rbp+Fh]
  int v23; // [rsp+98h] [rbp+17h]
  int v24; // [rsp+9Ch] [rbp+1Bh]

  v9 = *a9;
  if ( *a9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_BYTE *)v9 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v9 = &byte_180016B57;
    v11 = 1;
  }
  v23 = v11;
  v20 = a8;
  v18 = a7;
  v16 = a6;
  v14 = a5;
  v22 = v9;
  v24 = 0;
  v21 = 4;
  v19 = 4;
  v17 = 8;
  v15 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001E080, a2, 0, 0, 7, v13);
}

```

## disassembly

```asm
0x180001408  push    rbp
0x18000140a  lea     rbp, [rsp-2Fh]
0x18000140f  sub     rsp, 0B0h
0x180001416  mov     rax, cs:__security_cookie
0x18000141d  xor     rax, rsp
0x180001420  mov     [rbp+2Fh+var_10], rax
0x180001424  mov     rax, [rbp+2Fh+arg_40]
0x180001428  xor     r8d, r8d
0x18000142b  mov     rcx, [rax]
0x18000142e  test    rcx, rcx
0x180001431  jz      short loc_180001444
0x180001433  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001437  inc     rax
0x18000143a  cmp     [rcx+rax], r8b
0x18000143e  jnz     short loc_180001437
0x180001440  inc     eax
0x180001442  jmp     short loc_180001450
0x180001444  lea     rcx, byte_180016B57
0x18000144b  mov     eax, 1
0x180001450  mov     [rbp+2Fh+var_18], eax
0x180001453  xor     r9d, r9d
0x180001456  mov     rax, [rbp+2Fh+arg_38]
0x18000145a  mov     [rbp+2Fh+var_30], rax
0x18000145e  mov     rax, [rbp+2Fh+arg_30]
0x180001462  mov     [rbp+2Fh+var_40], rax
0x180001466  mov     rax, [rbp+2Fh+arg_28]
0x18000146a  mov     [rbp+2Fh+var_50], rax
0x18000146e  mov     rax, [rbp+2Fh+arg_20]
0x180001472  mov     [rbp+2Fh+var_60], rax
0x180001476  lea     rax, [rbp+2Fh+var_80]
0x18000147a  mov     [rbp+2Fh+var_20], rcx
0x18000147e  lea     rcx, dword_18001E080
0x180001485  mov     [rsp+0B0h+var_88], rax
0x18000148a  mov     [rsp+0B0h+var_90], 7
0x180001492  mov     [rbp+2Fh+var_14], r8d
0x180001496  mov     [rbp+2Fh+var_28], 4
0x18000149e  mov     [rbp+2Fh+var_38], 4
0x1800014a6  mov     [rbp+2Fh+var_48], 8
0x1800014ae  mov     [rbp+2Fh+var_58], 8
0x1800014b6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014bb  mov     rcx, [rbp+2Fh+var_10]
0x1800014bf  xor     rcx, rsp; StackCookie
0x1800014c2  call    __security_check_cookie
0x1800014c7  add     rsp, 0B0h
0x1800014ce  pop     rbp
0x1800014cf  retn
```
