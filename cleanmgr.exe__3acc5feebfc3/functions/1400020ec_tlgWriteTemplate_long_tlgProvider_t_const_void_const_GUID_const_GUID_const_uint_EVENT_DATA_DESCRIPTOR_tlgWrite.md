# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &)

- ea: `0x1400020ec`
- end: `0x140002298`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U1@U1@U1@U3@U_tlgWrapperPtrSize@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5555553335AEBU_tlgWrapperPtrSize@@6@Z`
- size: `428`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const WCHAR **, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012a7c`

## callees

- `0x1400019e8`
- `0x1400020ec`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const WCHAR **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 *a18,
        __int64 *a19)
{
  const WCHAR *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  _BYTE v24[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  const WCHAR *v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+6Ch] [rbp-94h]
  __int64 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  __int64 v40; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  __int64 v42; // [rsp+D0h] [rbp-30h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  __int64 v44; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+E8h] [rbp-18h]
  __int64 v46; // [rsp+F0h] [rbp-10h]
  __int64 v47; // [rsp+F8h] [rbp-8h]
  __int64 v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+108h] [rbp+8h]
  __int64 v50; // [rsp+110h] [rbp+10h]
  __int64 v51; // [rsp+118h] [rbp+18h]
  __int64 v52; // [rsp+120h] [rbp+20h]
  int v53; // [rsp+128h] [rbp+28h]
  int v54; // [rsp+12Ch] [rbp+2Ch]
  __int64 v55; // [rsp+130h] [rbp+30h]
  int v56; // [rsp+138h] [rbp+38h]
  int v57; // [rsp+13Ch] [rbp+3Ch]

  v51 = 4;
  v57 = 0;
  v54 = 0;
  v49 = 8;
  v55 = *a19;
  v56 = *((_DWORD *)a19 + 2);
  v47 = 8;
  v45 = 8;
  v52 = *a18;
  v53 = *((_DWORD *)a18 + 2);
  v50 = a17;
  v48 = a16;
  v46 = a15;
  v44 = a14;
  v42 = a13;
  v40 = a12;
  v38 = a11;
  v36 = a10;
  v34 = a9;
  v32 = a8;
  v30 = a7;
  v43 = 4;
  v41 = 4;
  v39 = 4;
  v20 = *a6;
  v37 = 4;
  v35 = 4;
  v33 = 4;
  v31 = 4;
  if ( v20 )
  {
    v21 = -1;
    do
      ++v21;
    while ( v20[v21] );
    v22 = 2 * v21 + 2;
  }
  else
  {
    v20 = &String;
    v22 = 2;
  }
  v28 = v22;
  v25 = a5;
  v27 = v20;
  v29 = 0;
  v26 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 17, v24);
}

```

## disassembly

```asm
0x1400020ec  push    rbp
0x1400020ee  lea     rbp, [rsp-50h]
0x1400020f3  sub     rsp, 150h
0x1400020fa  mov     rax, cs:__security_cookie
0x140002101  xor     rax, rsp
0x140002104  mov     [rbp+50h+var_10], rax
0x140002108  mov     r10, rcx
0x14000210b  mov     [rbp+50h+var_38], 4
0x140002113  mov     rcx, [rbp+50h+arg_90]
0x14000211a  xor     r8d, r8d
0x14000211d  mov     [rbp+50h+var_14], r8d
0x140002121  mov     [rbp+50h+var_24], r8d
0x140002125  mov     [rbp+50h+var_48], 8
0x14000212d  mov     rax, [rcx]
0x140002130  mov     [rbp+50h+var_20], rax
0x140002134  mov     eax, [rcx+8]
0x140002137  mov     rcx, [rbp+50h+arg_88]
0x14000213e  mov     [rbp+50h+var_18], eax
0x140002141  mov     [rbp+50h+var_58], 8
0x140002149  mov     [rbp+50h+var_68], 8
0x140002151  mov     rax, [rcx]
0x140002154  mov     [rbp+50h+var_30], rax
0x140002158  mov     eax, [rcx+8]
0x14000215b  mov     [rbp+50h+var_28], eax
0x14000215e  mov     rax, [rbp+50h+arg_80]
0x140002165  mov     [rbp+50h+var_40], rax
0x140002169  mov     rax, [rbp+50h+arg_78]
0x140002170  mov     [rbp+50h+var_50], rax
0x140002174  mov     rax, [rbp+50h+arg_70]
0x14000217b  mov     [rbp+50h+var_60], rax
0x14000217f  mov     rax, [rbp+50h+arg_68]
0x140002186  mov     [rbp+50h+var_70], rax
0x14000218a  mov     rax, [rbp+50h+arg_60]
0x140002191  mov     [rbp+50h+var_80], rax
0x140002195  mov     rax, [rbp+50h+arg_58]
0x14000219c  mov     [rbp+50h+var_90], rax
0x1400021a0  mov     rax, [rbp+50h+arg_50]
0x1400021a7  mov     [rbp+50h+var_A0], rax
0x1400021ab  mov     rax, [rbp+50h+arg_48]
0x1400021b2  mov     [rbp+50h+var_B0], rax
0x1400021b6  mov     rax, [rbp+50h+arg_40]
0x1400021bd  mov     [rbp+50h+var_C0], rax
0x1400021c1  mov     rax, [rbp+50h+arg_38]
0x1400021c8  mov     [rbp+50h+var_D0], rax
0x1400021cc  mov     rax, [rbp+50h+arg_30]
0x1400021d3  mov     [rsp+150h+var_E0], rax
0x1400021d8  mov     rax, [rbp+50h+arg_28]
0x1400021df  mov     [rbp+50h+var_78], 4
0x1400021e7  mov     [rbp+50h+var_88], 4
0x1400021ef  mov     [rbp+50h+var_98], 4
0x1400021f7  mov     rcx, [rax]
0x1400021fa  mov     [rbp+50h+var_A8], 4
0x140002202  mov     [rbp+50h+var_B8], 4
0x14000220a  mov     [rbp+50h+var_C8], 4
0x140002212  mov     [rsp+150h+var_D8], 4
0x14000221b  test    rcx, rcx
0x14000221e  jz      short loc_140002237
0x140002220  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002224  inc     rax
0x140002227  cmp     [rcx+rax*2], r8w
0x14000222c  jnz     short loc_140002224
0x14000222e  lea     eax, ds:2[rax*2]
0x140002235  jmp     short loc_140002243
0x140002237  lea     rcx, String
0x14000223e  mov     eax, 2
0x140002243  mov     [rsp+150h+var_E8], eax
0x140002247  xor     r9d, r9d
0x14000224a  mov     rax, [rbp+50h+arg_20]
0x140002251  mov     [rsp+150h+var_100], rax
0x140002256  lea     rax, [rsp+150h+var_120]
0x14000225b  mov     [rsp+150h+var_F0], rcx
0x140002260  mov     rcx, r10
0x140002263  mov     [rsp+150h+var_128], rax
0x140002268  mov     [rsp+150h+var_130], 11h
0x140002270  mov     [rsp+150h+var_E4], r8d
0x140002275  mov     [rsp+150h+var_F8], 8
0x14000227e  call    _tlgWriteTransfer_EventWriteTransfer
0x140002283  mov     rcx, [rbp+50h+var_10]
0x140002287  xor     rcx, rsp; StackCookie
0x14000228a  call    __security_check_cookie
0x14000228f  add     rsp, 150h
0x140002296  pop     rbp
0x140002297  retn
```
