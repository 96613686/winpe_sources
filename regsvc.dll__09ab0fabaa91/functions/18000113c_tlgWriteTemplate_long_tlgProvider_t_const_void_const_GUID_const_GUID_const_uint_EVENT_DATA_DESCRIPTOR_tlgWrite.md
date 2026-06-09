# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18000113c`
- end: `0x18000120a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@33@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64 **, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b0e8`

## callees

- `0x18000113c`
- `0x18000123c`
- `0x180007740`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-51h] BYREF
  __int64 v14; // [rsp+50h] [rbp-31h]
  __int64 v15; // [rsp+58h] [rbp-29h]
  __int64 *v16; // [rsp+60h] [rbp-21h]
  int v17; // [rsp+68h] [rbp-19h]
  int v18; // [rsp+6Ch] [rbp-15h]
  __int64 v19; // [rsp+70h] [rbp-11h]
  __int64 v20; // [rsp+78h] [rbp-9h]
  __int64 v21; // [rsp+80h] [rbp-1h]
  __int64 v22; // [rsp+88h] [rbp+7h]
  __int64 v23; // [rsp+90h] [rbp+Fh]
  __int64 v24; // [rsp+98h] [rbp+17h]

  v23 = a9;
  v21 = a8;
  v19 = a7;
  v24 = 8;
  v22 = 8;
  v20 = 4;
  v9 = *a6;
  if ( *a6 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &qword_180023510;
    v11 = 2;
  }
  v17 = v11;
  v14 = a5;
  v16 = v9;
  v18 = 0;
  v15 = 8;
  return tlgWriteTransfer_EtwEventWriteTransfer((unsigned int)&dword_18002B048, a2, 0, 0, 7, (__int64)v13);
}

```

## disassembly

```asm
0x18000113c  push    rbp
0x18000113e  lea     rbp, [rsp-2Fh]
0x180001143  sub     rsp, 0B0h
0x18000114a  mov     rax, cs:__security_cookie
0x180001151  xor     rax, rsp
0x180001154  mov     [rbp+2Fh+var_10], rax
0x180001158  mov     rax, [rbp+2Fh+arg_40]
0x18000115c  xor     r8d, r8d
0x18000115f  mov     [rbp+2Fh+var_20], rax
0x180001163  mov     rax, [rbp+2Fh+arg_38]
0x180001167  mov     [rbp+2Fh+var_30], rax
0x18000116b  mov     rax, [rbp+2Fh+arg_30]
0x18000116f  mov     [rbp+2Fh+var_40], rax
0x180001173  mov     rax, [rbp+2Fh+arg_28]
0x180001177  mov     [rbp+2Fh+var_18], 8
0x18000117f  mov     [rbp+2Fh+var_28], 8
0x180001187  mov     [rbp+2Fh+var_38], 4
0x18000118f  mov     rcx, [rax]
0x180001192  test    rcx, rcx
0x180001195  jz      short loc_1800011AE
0x180001197  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000119b  inc     rax
0x18000119e  cmp     [rcx+rax*2], r8w
0x1800011a3  jnz     short loc_18000119B
0x1800011a5  lea     eax, ds:2[rax*2]
0x1800011ac  jmp     short loc_1800011BA
0x1800011ae  lea     rcx, qword_180023510
0x1800011b5  mov     eax, 2
0x1800011ba  mov     [rbp+2Fh+var_48], eax
0x1800011bd  xor     r9d, r9d
0x1800011c0  mov     rax, [rbp+2Fh+arg_20]
0x1800011c4  mov     [rbp+2Fh+var_60], rax
0x1800011c8  lea     rax, [rbp+2Fh+var_80]
0x1800011cc  mov     [rbp+2Fh+var_50], rcx
0x1800011d0  lea     rcx, dword_18002B048
0x1800011d7  mov     [rsp+0B0h+var_88], rax
0x1800011dc  mov     [rsp+0B0h+var_90], 7
0x1800011e4  mov     [rbp+2Fh+var_44], r8d
0x1800011e8  mov     [rbp+2Fh+var_58], 8
0x1800011f0  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800011f5  mov     rcx, [rbp+2Fh+var_10]
0x1800011f9  xor     rcx, rsp; StackCookie
0x1800011fc  call    __security_check_cookie
0x180001201  add     rsp, 0B0h
0x180001208  pop     rbp
0x180001209  retn
```
