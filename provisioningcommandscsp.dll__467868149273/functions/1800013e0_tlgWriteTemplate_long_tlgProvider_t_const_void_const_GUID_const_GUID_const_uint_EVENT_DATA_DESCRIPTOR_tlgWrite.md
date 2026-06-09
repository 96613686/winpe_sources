# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013e0`
- end: `0x180001514`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z`
- size: `308`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ad90`
- `0x18000b2c0`

## callees

- `0x180001090`
- `0x1800013e0`
- `0x18000ccc0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6,
        __int64 **a7,
        __int64 **a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  __int64 *v20; // rdx
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v23; // [rsp+50h] [rbp-19h]
  int v24; // [rsp+58h] [rbp-11h]
  int v25; // [rsp+5Ch] [rbp-Dh]
  __int64 *v26; // [rsp+60h] [rbp-9h]
  int v27; // [rsp+68h] [rbp-1h]
  int v28; // [rsp+6Ch] [rbp+3h]
  __int64 *v29; // [rsp+70h] [rbp+7h]
  int v30; // [rsp+78h] [rbp+Fh]
  int v31; // [rsp+7Ch] [rbp+13h]
  __int64 *v32; // [rsp+80h] [rbp+17h]
  int v33; // [rsp+88h] [rbp+1Fh]
  int v34; // [rsp+8Ch] [rbp+23h]

  v9 = -1;
  v10 = 2;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &qword_180010000;
    v13 = 2;
  }
  v33 = v13;
  v32 = v11;
  v34 = 0;
  v14 = *a7;
  if ( *a7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &qword_180010000;
    v16 = 2;
  }
  v30 = v16;
  v29 = v14;
  v31 = 0;
  v17 = *a6;
  if ( *a6 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = &qword_180010000;
    v19 = 2;
  }
  v27 = v19;
  v26 = v17;
  v28 = 0;
  v20 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_WORD *)v20 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v20 = &qword_180010000;
  }
  v23 = v20;
  v24 = v10;
  v25 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014230, a2, 0, 0, 6u, &v22);
}

```

## disassembly

```asm
0x1800013e0  push    rbp
0x1800013e2  lea     rbp, [rsp-37h]
0x1800013e7  sub     rsp, 0A0h
0x1800013ee  mov     rax, cs:__security_cookie
0x1800013f5  xor     rax, rsp
0x1800013f8  mov     [rbp+37h+var_10], rax
0x1800013fc  mov     rax, [rbp+37h+arg_38]
0x180001400  lea     r11, qword_180010000
0x180001407  mov     r10, rdx
0x18000140a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000140e  xor     r9d, r9d
0x180001411  mov     r8d, 2
0x180001417  mov     rdx, [rax]
0x18000141a  test    rdx, rdx
0x18000141d  jz      short loc_180001435
0x18000141f  mov     rax, rcx
0x180001422  inc     rax
0x180001425  cmp     [rdx+rax*2], r9w
0x18000142a  jnz     short loc_180001422
0x18000142c  lea     eax, ds:2[rax*2]
0x180001433  jmp     short loc_18000143B
0x180001435  mov     rdx, r11
0x180001438  mov     eax, r8d
0x18000143b  mov     [rbp+37h+var_18], eax
0x18000143e  mov     rax, [rbp+37h+arg_30]
0x180001442  mov     [rbp+37h+var_20], rdx
0x180001446  mov     [rbp+37h+var_14], r9d
0x18000144a  mov     rdx, [rax]
0x18000144d  test    rdx, rdx
0x180001450  jz      short loc_180001468
0x180001452  mov     rax, rcx
0x180001455  inc     rax
0x180001458  cmp     [rdx+rax*2], r9w
0x18000145d  jnz     short loc_180001455
0x18000145f  lea     eax, ds:2[rax*2]
0x180001466  jmp     short loc_18000146E
0x180001468  mov     rdx, r11
0x18000146b  mov     eax, r8d
0x18000146e  mov     [rbp+37h+var_28], eax
0x180001471  mov     rax, [rbp+37h+arg_28]
0x180001475  mov     [rbp+37h+var_30], rdx
0x180001479  mov     [rbp+37h+var_24], r9d
0x18000147d  mov     rdx, [rax]
0x180001480  test    rdx, rdx
0x180001483  jz      short loc_18000149B
0x180001485  mov     rax, rcx
0x180001488  inc     rax
0x18000148b  cmp     [rdx+rax*2], r9w
0x180001490  jnz     short loc_180001488
0x180001492  lea     eax, ds:2[rax*2]
0x180001499  jmp     short loc_1800014A1
0x18000149b  mov     rdx, r11
0x18000149e  mov     eax, r8d
0x1800014a1  mov     [rbp+37h+var_38], eax
0x1800014a4  mov     rax, [rbp+37h+arg_20]
0x1800014a8  mov     [rbp+37h+var_40], rdx
0x1800014ac  mov     [rbp+37h+var_34], r9d
0x1800014b0  mov     rdx, [rax]
0x1800014b3  test    rdx, rdx
0x1800014b6  jz      short loc_1800014CC
0x1800014b8  inc     rcx
0x1800014bb  cmp     [rdx+rcx*2], r9w
0x1800014c0  jnz     short loc_1800014B8
0x1800014c2  lea     r8d, ds:2[rcx*2]
0x1800014ca  jmp     short loc_1800014CF
0x1800014cc  mov     rdx, r11
0x1800014cf  lea     rax, [rbp+37h+var_70]
0x1800014d3  mov     [rbp+37h+var_50], rdx
0x1800014d7  mov     [rbp+37h+var_48], r8d
0x1800014db  lea     rcx, dword_180014230
0x1800014e2  mov     [rsp+0A0h+var_78], rax
0x1800014e7  xor     r8d, r8d
0x1800014ea  mov     rdx, r10
0x1800014ed  mov     [rsp+0A0h+var_80], 6
0x1800014f5  mov     [rbp+37h+var_44], r9d
0x1800014f9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014fe  mov     rcx, [rbp+37h+var_10]
0x180001502  xor     rcx, rsp; StackCookie
0x180001505  call    __security_check_cookie
0x18000150a  add     rsp, 0A0h
0x180001511  pop     rbp
0x180001512  retn
```
