# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001008`
- end: `0x140001135`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z`
- size: `301`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64 **, __int64 **, __int64, __int64)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x140003738`
- `0x140003828`
- `0x140003918`
- `0x140003a08`
- `0x140003af8`
- `0x140003be8`
- `0x140003cdc`
- `0x140003dcc`
- `0x140003ebc`
- `0x140003fac`
- `0x14000409c`
- `0x14000418c`
- `0x140004280`
- `0x140004370`
- `0x140004460`
- `0x140004550`
- `0x140004640`
- `0x140004730`
- `0x140004824`
- `0x140004914`
- `0x140004a04`
- `0x140004af4`
- `0x140004be4`
- `0x140004cd4`

## callees

- `0x140001008`
- `0x1400011bc`
- `0x140001c50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 **a9,
        __int64 **a10,
        __int64 a11,
        __int64 a12)
{
  __int64 v13; // rcx
  int v14; // r8d
  __int64 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  __int64 *v18; // rdx
  _BYTE v20[32]; // [rsp+30h] [rbp-99h] BYREF
  __int64 v21; // [rsp+50h] [rbp-79h]
  __int64 v22; // [rsp+58h] [rbp-71h]
  __int64 v23; // [rsp+60h] [rbp-69h]
  __int64 v24; // [rsp+68h] [rbp-61h]
  __int64 v25; // [rsp+70h] [rbp-59h]
  __int64 v26; // [rsp+78h] [rbp-51h]
  __int64 v27; // [rsp+80h] [rbp-49h]
  __int64 v28; // [rsp+88h] [rbp-41h]
  __int64 *v29; // [rsp+90h] [rbp-39h]
  int v30; // [rsp+98h] [rbp-31h]
  int v31; // [rsp+9Ch] [rbp-2Dh]
  __int64 *v32; // [rsp+A0h] [rbp-29h]
  int v33; // [rsp+A8h] [rbp-21h]
  int v34; // [rsp+ACh] [rbp-1Dh]
  __int64 v35; // [rsp+B0h] [rbp-19h]
  __int64 v36; // [rsp+B8h] [rbp-11h]
  __int64 v37; // [rsp+C0h] [rbp-9h]
  __int64 v38; // [rsp+C8h] [rbp-1h]

  v37 = a12;
  v13 = -1;
  v35 = a11;
  v14 = 2;
  v38 = 8;
  v36 = 4;
  v15 = *a10;
  if ( *a10 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &qword_14000E928;
    v17 = 2;
  }
  v33 = v17;
  v32 = v15;
  v34 = 0;
  v18 = *a9;
  if ( *a9 )
  {
    do
      ++v13;
    while ( *((_WORD *)v18 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v18 = &qword_14000E928;
  }
  v27 = a8;
  v25 = a7;
  v23 = a6;
  v21 = a5;
  v29 = v18;
  v30 = v14;
  v31 = 0;
  v28 = 8;
  v26 = 8;
  v24 = 8;
  v22 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140014000, a2, 0, 0, 10, v20);
}

```

## disassembly

```asm
0x140001008  push    rbp
0x14000100a  lea     rbp, [rsp-17h]
0x14000100f  sub     rsp, 0E0h
0x140001016  mov     rax, cs:__security_cookie
0x14000101d  xor     rax, rsp
0x140001020  mov     [rbp+17h+var_10], rax
0x140001024  mov     rax, [rbp+17h+arg_58]
0x140001028  xor     r9d, r9d
0x14000102b  mov     [rbp+17h+var_20], rax
0x14000102f  mov     r10, rdx
0x140001032  mov     rax, [rbp+17h+arg_50]
0x140001036  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000103a  mov     [rbp+17h+var_30], rax
0x14000103e  mov     rax, [rbp+17h+arg_48]
0x140001042  lea     r8d, [r9+2]
0x140001046  mov     [rbp+17h+var_18], 8
0x14000104e  mov     [rbp+17h+var_28], 4
0x140001056  mov     rdx, [rax]
0x140001059  test    rdx, rdx
0x14000105c  jz      short loc_140001074
0x14000105e  mov     rax, rcx
0x140001061  inc     rax
0x140001064  cmp     [rdx+rax*2], r9w
0x140001069  jnz     short loc_140001061
0x14000106b  lea     eax, ds:2[rax*2]
0x140001072  jmp     short loc_14000107E
0x140001074  lea     rdx, qword_14000E928
0x14000107b  mov     eax, r8d
0x14000107e  mov     [rbp+17h+var_38], eax
0x140001081  mov     rax, [rbp+17h+arg_40]
0x140001085  mov     [rbp+17h+var_40], rdx
0x140001089  mov     [rbp+17h+var_34], r9d
0x14000108d  mov     rdx, [rax]
0x140001090  test    rdx, rdx
0x140001093  jz      short loc_1400010A9
0x140001095  inc     rcx
0x140001098  cmp     [rdx+rcx*2], r9w
0x14000109d  jnz     short loc_140001095
0x14000109f  lea     r8d, ds:2[rcx*2]
0x1400010a7  jmp     short loc_1400010B0
0x1400010a9  lea     rdx, qword_14000E928
0x1400010b0  mov     rax, [rbp+17h+arg_38]
0x1400010b4  lea     rcx, dword_140014000
0x1400010bb  mov     [rbp+17h+var_60], rax
0x1400010bf  mov     rax, [rbp+17h+arg_30]
0x1400010c3  mov     [rbp+17h+var_70], rax
0x1400010c7  mov     rax, [rbp+17h+arg_28]
0x1400010cb  mov     [rbp+17h+var_80], rax
0x1400010cf  mov     rax, [rbp+17h+arg_20]
0x1400010d3  mov     [rbp+17h+var_90], rax
0x1400010d7  lea     rax, [rsp+0E0h+var_B0]
0x1400010dc  mov     [rbp+17h+var_50], rdx
0x1400010e0  mov     rdx, r10
0x1400010e3  mov     [rbp+17h+var_48], r8d
0x1400010e7  xor     r8d, r8d
0x1400010ea  mov     [rsp+0E0h+var_B8], rax
0x1400010ef  mov     [rsp+0E0h+var_C0], 0Ah
0x1400010f7  mov     [rbp+17h+var_44], r9d
0x1400010fb  mov     [rbp+17h+var_58], 8
0x140001103  mov     [rbp+17h+var_68], 8
0x14000110b  mov     [rbp+17h+var_78], 8
0x140001113  mov     [rbp+17h+var_88], 4
0x14000111b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001120  mov     rcx, [rbp+17h+var_10]
0x140001124  xor     rcx, rsp; StackCookie
0x140001127  call    __security_check_cookie
0x14000112c  add     rsp, 0E0h
0x140001133  pop     rbp
0x140001134  retn
```
