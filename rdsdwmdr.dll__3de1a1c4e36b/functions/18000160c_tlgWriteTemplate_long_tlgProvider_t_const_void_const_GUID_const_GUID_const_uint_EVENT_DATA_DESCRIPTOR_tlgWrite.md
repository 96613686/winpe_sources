# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18000160c`
- end: `0x18000171b`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z`
- size: `271`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **)`
- caller_count: `77`
- callee_count: `3`
- tags: ``

## callers

- `0x180004cbc`
- `0x180005504`
- `0x180005918`
- `0x180005c20`
- `0x180006240`
- `0x18000cde8`
- `0x18000cf04`
- `0x18000d56c`
- `0x18000d788`
- `0x18000dc04`
- `0x18000de24`
- `0x18000e0e8`
- `0x18000e738`
- `0x18000f52c`
- `0x18000f670`
- `0x18000f7cc`
- `0x18000f950`
- `0x180012238`
- `0x180013444`
- `0x1800139a8`
- `0x180013e58`
- `0x180014080`
- `0x1800141d0`
- `0x180014c00`
- `0x180015210`
- `0x180015bc0`
- `0x180016450`
- `0x180016700`
- `0x180016970`
- `0x180016bdc`
- `0x180016e64`
- `0x180017230`
- `0x180017350`
- `0x1800176dc`
- `0x1800181a0`
- `0x1800188bc`
- `0x180018b2c`
- `0x180018e70`
- `0x1800190dc`
- `0x180019340`
- `0x1800195d0`
- `0x18001e40c`
- `0x18001e6c8`
- `0x18001e8e0`
- `0x18001eb5c`
- `0x18001ec90`
- `0x18001f0cc`
- `0x18002164c`
- `0x180021cf0`
- `0x180022490`

## callees

- `0x18000160c`
- `0x180001ef8`
- `0x18002b960`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  _BYTE v20[32]; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-31h]
  int v22; // [rsp+58h] [rbp-29h]
  int v23; // [rsp+5Ch] [rbp-25h]
  __int64 v24; // [rsp+60h] [rbp-21h]
  __int64 v25; // [rsp+68h] [rbp-19h]
  const unsigned __int16 *v26; // [rsp+70h] [rbp-11h]
  int v27; // [rsp+78h] [rbp-9h]
  int v28; // [rsp+7Ch] [rbp-5h]
  __int64 v29; // [rsp+80h] [rbp-1h]
  __int64 v30; // [rsp+88h] [rbp+7h]
  const unsigned __int16 *v31; // [rsp+90h] [rbp+Fh]
  int v32; // [rsp+98h] [rbp+17h]
  int v33; // [rsp+9Ch] [rbp+1Bh]

  v10 = -1;
  v11 = 1;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &word_18002F722;
    v14 = 1;
  }
  v32 = v14;
  v29 = a8;
  v31 = v12;
  v33 = 0;
  v30 = 4;
  v15 = *a7;
  if ( *a7 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_BYTE *)v15 + v16) );
    v17 = v16 + 1;
  }
  else
  {
    v15 = &word_18002F722;
    v17 = 1;
  }
  v27 = v17;
  v24 = a6;
  v26 = v15;
  v28 = 0;
  v25 = 4;
  v18 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( *((_BYTE *)v18 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v18 = &word_18002F722;
  }
  v21 = v18;
  v22 = v11;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180044008, a2, 0, 0, 7, v20);
}

```

## disassembly

```asm
0x18000160c  push    rbp
0x18000160e  lea     rbp, [rsp-2Fh]
0x180001613  sub     rsp, 0B0h
0x18000161a  mov     rax, cs:__security_cookie
0x180001621  xor     rax, rsp
0x180001624  mov     [rbp+2Fh+var_10], rax
0x180001628  mov     rax, [rbp+2Fh+arg_40]
0x18000162c  lea     r11, word_18002F722
0x180001633  mov     r10, rdx
0x180001636  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000163a  xor     r9d, r9d
0x18000163d  mov     r8d, 1
0x180001643  mov     rdx, [rax]
0x180001646  test    rdx, rdx
0x180001649  jz      short loc_18000165B
0x18000164b  mov     rax, rcx
0x18000164e  inc     rax
0x180001651  cmp     [rdx+rax], r9b
0x180001655  jnz     short loc_18000164E
0x180001657  inc     eax
0x180001659  jmp     short loc_180001661
0x18000165b  mov     rdx, r11
0x18000165e  mov     eax, r8d
0x180001661  mov     [rbp+2Fh+var_18], eax
0x180001664  mov     rax, [rbp+2Fh+arg_38]
0x180001668  mov     [rbp+2Fh+var_30], rax
0x18000166c  mov     rax, [rbp+2Fh+arg_30]
0x180001670  mov     [rbp+2Fh+var_20], rdx
0x180001674  mov     [rbp+2Fh+var_14], r9d
0x180001678  mov     [rbp+2Fh+var_28], 4
0x180001680  mov     rdx, [rax]
0x180001683  test    rdx, rdx
0x180001686  jz      short loc_180001698
0x180001688  mov     rax, rcx
0x18000168b  inc     rax
0x18000168e  cmp     [rdx+rax], r9b
0x180001692  jnz     short loc_18000168B
0x180001694  inc     eax
0x180001696  jmp     short loc_18000169E
0x180001698  mov     rdx, r11
0x18000169b  mov     eax, r8d
0x18000169e  mov     [rbp+2Fh+var_38], eax
0x1800016a1  mov     rax, [rbp+2Fh+arg_28]
0x1800016a5  mov     [rbp+2Fh+var_50], rax
0x1800016a9  mov     rax, [rbp+2Fh+arg_20]
0x1800016ad  mov     [rbp+2Fh+var_40], rdx
0x1800016b1  mov     [rbp+2Fh+var_34], r9d
0x1800016b5  mov     [rbp+2Fh+var_48], 4
0x1800016bd  mov     rdx, [rax]
0x1800016c0  test    rdx, rdx
0x1800016c3  jz      short loc_1800016D4
0x1800016c5  inc     rcx
0x1800016c8  cmp     [rdx+rcx], r9b
0x1800016cc  jnz     short loc_1800016C5
0x1800016ce  lea     r8d, [rcx+1]
0x1800016d2  jmp     short loc_1800016D7
0x1800016d4  mov     rdx, r11
0x1800016d7  lea     rax, [rbp+2Fh+var_80]
0x1800016db  mov     [rbp+2Fh+var_60], rdx
0x1800016df  mov     [rbp+2Fh+var_58], r8d
0x1800016e3  lea     rcx, dword_180044008
0x1800016ea  mov     [rsp+0B0h+var_88], rax
0x1800016ef  xor     r8d, r8d
0x1800016f2  mov     rdx, r10
0x1800016f5  mov     [rsp+0B0h+var_90], 7
0x1800016fd  mov     [rbp+2Fh+var_54], r9d
0x180001701  call    _tlgWriteTransfer_EventWriteTransfer
0x180001706  mov     rcx, [rbp+2Fh+var_10]
0x18000170a  xor     rcx, rsp; StackCookie
0x18000170d  call    __security_check_cookie
0x180001712  add     rsp, 0B0h
0x180001719  pop     rbp
0x18000171a  retn
```
