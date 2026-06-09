# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180026948`
- end: `0x180026b7a`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U3@U3@U3@U3@U3@U?$_tlgWrapperByVal@$03@@U4@U3@U?$_tlgWrapSz@G@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@55555AEBU?$_tlgWrapperByVal@$03@@65AEBU?$_tlgWrapSz@G@@7@Z`
- size: `562`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, const size_t **, const size_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000b4a4`

## callees

- `0x180026948`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180026b32`
- `ntdll!EtwEventWriteTransfer` at `0x180026b32`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        const size_t **a16,
        const size_t **a17)
{
  __int64 v17; // rcx
  const size_t *v19; // r8
  __int64 v20; // rax
  int v21; // eax
  const size_t *v22; // rdx
  __int64 v23; // rax
  int v24; // eax
  const unsigned __int16 *v25; // rdx
  int v26; // ecx
  _DWORD v28[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h]
  __int16 *v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+5Ch] [rbp-A4h]
  unsigned __int8 *v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  const unsigned __int16 *v36; // [rsp+70h] [rbp-90h]
  int v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+7Ch] [rbp-84h]
  __int64 v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h]
  __int64 v41; // [rsp+90h] [rbp-70h]
  __int64 v42; // [rsp+98h] [rbp-68h]
  __int64 v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  __int64 v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  __int64 v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+D8h] [rbp-28h]
  __int64 v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]
  __int64 v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  __int64 v55; // [rsp+100h] [rbp+0h]
  __int64 v56; // [rsp+108h] [rbp+8h]
  __int64 v57; // [rsp+110h] [rbp+10h]
  __int64 v58; // [rsp+118h] [rbp+18h]
  const size_t *v59; // [rsp+120h] [rbp+20h]
  int v60; // [rsp+128h] [rbp+28h]
  int v61; // [rsp+12Ch] [rbp+2Ch]
  const size_t *v62; // [rsp+130h] [rbp+30h]
  int v63; // [rsp+138h] [rbp+38h]
  int v64; // [rsp+13Ch] [rbp+3Ch]

  v17 = -1;
  v19 = *a17;
  if ( *a17 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v19 + v20) );
    v21 = 2 * v20 + 2;
  }
  else
  {
    v19 = &pServiceName;
    v21 = 2;
  }
  v63 = v21;
  v62 = v19;
  v64 = 0;
  v22 = *a16;
  if ( *a16 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *((_WORD *)v22 + v23) );
    v24 = 2 * v23 + 2;
  }
  else
  {
    v22 = &pServiceName;
    v24 = 2;
  }
  v60 = v24;
  v57 = a15;
  v55 = a14;
  v53 = a13;
  v51 = a12;
  v49 = a11;
  v47 = a10;
  v45 = a9;
  v43 = a8;
  v41 = a7;
  v39 = a6;
  v59 = v22;
  v61 = 0;
  v58 = 1;
  v25 = *a5;
  v56 = 4;
  v54 = 4;
  v52 = 1;
  v50 = 1;
  v48 = 1;
  v46 = 1;
  v44 = 1;
  v42 = 1;
  v40 = 8;
  if ( v25 )
  {
    do
      ++v17;
    while ( *((_BYTE *)v25 + v17) );
    v26 = v17 + 1;
  }
  else
  {
    v25 = &qword_18007F760;
    v26 = 1;
  }
  v28[0] = *a2 << 24;
  v28[1] = *(unsigned __int16 *)(a2 + 1);
  v29 = *(_QWORD *)(a2 + 3);
  v30 = off_18009A050;
  v37 = v26;
  v36 = v25;
  v38 = 0;
  v31 = (unsigned __int16)*off_18009A050;
  v34 = *(unsigned __int16 *)(a2 + 11);
  v33 = a2 + 11;
  v35 = 1;
  v32 = 2;
  return EtwEventWriteTransfer(RegHandle, v28, 0, 0, 15, &v30);
}

```

## disassembly

```asm
0x180026948  push    rbp
0x18002694a  lea     rbp, [rsp-50h]
0x18002694f  sub     rsp, 150h
0x180026956  mov     rax, cs:__security_cookie
0x18002695d  xor     rax, rsp
0x180026960  mov     [rbp+50h+var_10], rax
0x180026964  mov     rax, [rbp+50h+arg_80]
0x18002696b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002696f  xor     r10d, r10d
0x180026972  mov     r9, rdx
0x180026975  mov     r11d, 2
0x18002697b  mov     r8, [rax]
0x18002697e  test    r8, r8
0x180026981  jz      loc_180026B4D
0x180026987  mov     rax, rcx
0x18002698a  inc     rax
0x18002698d  cmp     [r8+rax*2], r10w
0x180026992  jnz     short loc_18002698A
0x180026994  lea     eax, ds:2[rax*2]
0x18002699b  mov     [rbp+50h+var_18], eax
0x18002699e  mov     rax, [rbp+50h+arg_78]
0x1800269a5  mov     [rbp+50h+var_20], r8
0x1800269a9  mov     [rbp+50h+var_14], r10d
0x1800269ad  mov     rdx, [rax]
0x1800269b0  test    rdx, rdx
0x1800269b3  jz      loc_180026B5C
0x1800269b9  mov     rax, rcx
0x1800269bc  inc     rax
0x1800269bf  cmp     [rdx+rax*2], r10w
0x1800269c4  jnz     short loc_1800269BC
0x1800269c6  lea     eax, ds:2[rax*2]
0x1800269cd  mov     [rbp+50h+var_28], eax
0x1800269d0  mov     r8d, 1
0x1800269d6  mov     rax, [rbp+50h+arg_70]
0x1800269dd  mov     [rbp+50h+var_40], rax
0x1800269e1  mov     rax, [rbp+50h+arg_68]
0x1800269e8  mov     [rbp+50h+var_50], rax
0x1800269ec  mov     rax, [rbp+50h+arg_60]
0x1800269f3  mov     [rbp+50h+var_60], rax
0x1800269f7  mov     rax, [rbp+50h+arg_58]
0x1800269fe  mov     [rbp+50h+var_70], rax
0x180026a02  mov     rax, [rbp+50h+arg_50]
0x180026a09  mov     [rbp+50h+var_80], rax
0x180026a0d  mov     rax, [rbp+50h+arg_48]
0x180026a14  mov     [rbp+50h+var_90], rax
0x180026a18  mov     rax, [rbp+50h+arg_40]
0x180026a1f  mov     [rbp+50h+var_A0], rax
0x180026a23  mov     rax, [rbp+50h+arg_38]
0x180026a2a  mov     [rbp+50h+var_B0], rax
0x180026a2e  mov     rax, [rbp+50h+arg_30]
0x180026a35  mov     [rbp+50h+var_C0], rax
0x180026a39  mov     rax, [rbp+50h+arg_28]
0x180026a40  mov     [rbp+50h+var_D0], rax
0x180026a44  mov     rax, [rbp+50h+arg_20]
0x180026a4b  mov     [rbp+50h+var_30], rdx
0x180026a4f  mov     [rbp+50h+var_24], r10d
0x180026a53  mov     [rbp+50h+var_38], r8
0x180026a57  mov     rdx, [rax]
0x180026a5a  mov     [rbp+50h+var_48], 4
0x180026a62  mov     [rbp+50h+var_58], 4
0x180026a6a  mov     [rbp+50h+var_68], r8
0x180026a6e  mov     [rbp+50h+var_78], r8
0x180026a72  mov     [rbp+50h+var_88], r8
0x180026a76  mov     [rbp+50h+var_98], r8
0x180026a7a  mov     [rbp+50h+var_A8], r8
0x180026a7e  mov     [rbp+50h+var_B8], r8
0x180026a82  mov     [rbp+50h+var_C8], 8
0x180026a8a  test    rdx, rdx
0x180026a8d  jz      loc_180026B6B
0x180026a93  inc     rcx
0x180026a96  cmp     [rdx+rcx], r10b
0x180026a9a  jnz     short loc_180026A93
0x180026a9c  inc     ecx
0x180026a9e  movzx   eax, byte ptr [r9]
0x180026aa2  shl     eax, 18h
0x180026aa5  mov     [rsp+150h+var_118], eax
0x180026aa9  movzx   eax, word ptr [r9+1]
0x180026aae  mov     [rsp+150h+var_114], eax
0x180026ab2  mov     rax, [r9+3]
0x180026ab6  mov     [rsp+150h+var_110], rax
0x180026abb  mov     rax, cs:off_18009A050
0x180026ac2  mov     [rsp+150h+var_100], rax
0x180026ac7  mov     [rsp+150h+var_D8], ecx
0x180026acb  lea     rcx, [r9+0Bh]
0x180026acf  mov     [rsp+150h+var_E0], rdx
0x180026ad4  xor     r9d, r9d
0x180026ad7  mov     [rsp+150h+var_D4], r10d
0x180026adc  lea     rdx, [rsp+150h+var_118]
0x180026ae1  movzx   eax, word ptr [rax]
0x180026ae4  mov     [rsp+150h+var_F8], eax
0x180026ae8  movzx   eax, word ptr [rcx]
0x180026aeb  mov     [rsp+150h+var_E8], eax
0x180026aef  lea     rax, _TraceLoggingMetadataEnd
0x180026af6  mov     [rsp+150h+var_F0], rcx
0x180026afb  lea     rcx, _TraceLoggingMetadata
0x180026b02  sub     eax, ecx
0x180026b04  mov     [rsp+150h+var_E4], r8d
0x180026b09  mov     [rsp+150h+var_F4], r11d
0x180026b0e  xor     r8d, r8d
0x180026b11  mov     [rsp+150h+var_120], eax
0x180026b15  mov     eax, [rsp+150h+var_120]
0x180026b19  mov     rcx, cs:RegHandle
0x180026b20  lea     rax, [rsp+150h+var_100]
0x180026b25  mov     [rsp+150h+var_128], rax
0x180026b2a  mov     [rsp+150h+var_130], 0Fh
0x180026b32  call    cs:__imp_EtwEventWriteTransfer
0x180026b38  mov     rcx, [rbp+50h+var_10]
0x180026b3c  xor     rcx, rsp; StackCookie
0x180026b3f  call    __security_check_cookie
0x180026b44  add     rsp, 150h
0x180026b4b  pop     rbp
0x180026b4c  retn
0x180026b4d  lea     r8, pServiceName
0x180026b54  mov     eax, r11d
0x180026b57  jmp     loc_18002699B
0x180026b5c  lea     rdx, pServiceName
0x180026b63  mov     eax, r11d
0x180026b66  jmp     loc_1800269CD
0x180026b6b  lea     rdx, qword_18007F760
0x180026b72  mov     ecx, r8d
0x180026b75  jmp     loc_180026A9E
```
