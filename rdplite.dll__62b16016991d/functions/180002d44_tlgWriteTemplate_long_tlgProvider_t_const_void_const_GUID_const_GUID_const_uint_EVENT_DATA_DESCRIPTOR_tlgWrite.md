# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180002d44`
- end: `0x180002f62`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@44444444AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `542`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800202a4`
- `0x1800205d4`

## callees

- `0x180001448`
- `0x180002d44`
- `0x1800036f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        __int64 **a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19)
{
  __int64 v21; // rcx
  __int64 *v22; // rdx
  __int64 v23; // rax
  int v24; // eax
  int v25; // r8d
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rax
  int v28; // eax
  const unsigned __int16 *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // rdx
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v35; // [rsp+50h] [rbp-B0h]
  int v36; // [rsp+58h] [rbp-A8h]
  int v37; // [rsp+5Ch] [rbp-A4h]
  __int64 v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+78h] [rbp-88h]
  int v42; // [rsp+7Ch] [rbp-84h]
  const unsigned __int16 *v43; // [rsp+80h] [rbp-80h]
  int v44; // [rsp+88h] [rbp-78h]
  int v45; // [rsp+8Ch] [rbp-74h]
  __int64 *v46; // [rsp+90h] [rbp-70h]
  int v47; // [rsp+98h] [rbp-68h]
  int v48; // [rsp+9Ch] [rbp-64h]
  __int64 v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  __int64 v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+B8h] [rbp-48h]
  __int64 v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  __int64 v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h]
  __int64 v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  __int64 v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  __int64 v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  __int64 v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  __int64 v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  __int64 v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]

  v67 = a19;
  v65 = a18;
  v21 = -1;
  v63 = a17;
  v61 = a16;
  v59 = a15;
  v57 = a14;
  v55 = a13;
  v53 = a12;
  v51 = a11;
  v49 = a10;
  v68 = 4;
  v66 = 8;
  v64 = 4;
  v22 = *a9;
  v62 = 4;
  v60 = 4;
  v58 = 4;
  v56 = 4;
  v54 = 4;
  v52 = 4;
  v50 = 4;
  if ( v22 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *((_WORD *)v22 + v23) );
    v24 = 2 * v23 + 2;
  }
  else
  {
    v22 = &qword_18002E230;
    v24 = 2;
  }
  v47 = v24;
  v25 = 1;
  v46 = v22;
  v48 = 0;
  v26 = *a8;
  if ( *a8 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &qword_18002D6C0;
    v28 = 1;
  }
  v44 = v28;
  v43 = v26;
  v45 = 0;
  v29 = *a7;
  if ( *a7 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &qword_18002D6C0;
    v31 = 1;
  }
  v41 = v31;
  v38 = a6;
  v40 = v29;
  v42 = 0;
  v39 = 4;
  v32 = *a5;
  if ( *a5 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v32 + v21) );
    v25 = v21 + 1;
  }
  else
  {
    v32 = &qword_18002D6C0;
  }
  v35 = v32;
  v36 = v25;
  v37 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x11u, &v34);
}

```

## disassembly

```asm
0x180002d44  mov     [rsp-8+arg_10], rdi
0x180002d49  push    rbp
0x180002d4a  lea     rbp, [rsp-50h]
0x180002d4f  sub     rsp, 150h
0x180002d56  mov     rax, cs:__security_cookie
0x180002d5d  xor     rax, rsp
0x180002d60  mov     [rbp+50h+var_10], rax
0x180002d64  mov     rax, [rbp+50h+arg_90]
0x180002d6b  mov     r11, rdx
0x180002d6e  mov     [rbp+50h+var_20], rax
0x180002d72  mov     r10, rcx
0x180002d75  mov     rax, [rbp+50h+arg_88]
0x180002d7c  xor     r9d, r9d
0x180002d7f  mov     [rbp+50h+var_30], rax
0x180002d83  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002d87  mov     rax, [rbp+50h+arg_80]
0x180002d8e  mov     [rbp+50h+var_40], rax
0x180002d92  mov     rax, [rbp+50h+arg_78]
0x180002d99  mov     [rbp+50h+var_50], rax
0x180002d9d  mov     rax, [rbp+50h+arg_70]
0x180002da4  mov     [rbp+50h+var_60], rax
0x180002da8  mov     rax, [rbp+50h+arg_68]
0x180002daf  mov     [rbp+50h+var_70], rax
0x180002db3  mov     rax, [rbp+50h+arg_60]
0x180002dba  mov     [rbp+50h+var_80], rax
0x180002dbe  mov     rax, [rbp+50h+arg_58]
0x180002dc5  mov     [rbp+50h+var_90], rax
0x180002dc9  mov     rax, [rbp+50h+arg_50]
0x180002dd0  mov     [rbp+50h+var_A0], rax
0x180002dd4  mov     rax, [rbp+50h+arg_48]
0x180002ddb  mov     [rbp+50h+var_B0], rax
0x180002ddf  mov     rax, [rbp+50h+arg_40]
0x180002de6  mov     [rbp+50h+var_18], 4
0x180002dee  mov     [rbp+50h+var_28], 8
0x180002df6  mov     [rbp+50h+var_38], 4
0x180002dfe  mov     rdx, [rax]
0x180002e01  mov     [rbp+50h+var_48], 4
0x180002e09  mov     [rbp+50h+var_58], 4
0x180002e11  mov     [rbp+50h+var_68], 4
0x180002e19  mov     [rbp+50h+var_78], 4
0x180002e21  mov     [rbp+50h+var_88], 4
0x180002e29  mov     [rbp+50h+var_98], 4
0x180002e31  mov     [rbp+50h+var_A8], 4
0x180002e39  test    rdx, rdx
0x180002e3c  jz      short loc_180002E54
0x180002e3e  mov     rax, rcx
0x180002e41  inc     rax
0x180002e44  cmp     [rdx+rax*2], r9w
0x180002e49  jnz     short loc_180002E41
0x180002e4b  lea     eax, ds:2[rax*2]
0x180002e52  jmp     short loc_180002E60
0x180002e54  lea     rdx, qword_18002E230
0x180002e5b  mov     eax, 2
0x180002e60  mov     [rbp+50h+var_B8], eax
0x180002e63  mov     r8d, 1
0x180002e69  mov     rax, [rbp+50h+arg_38]
0x180002e70  mov     [rbp+50h+var_C0], rdx
0x180002e74  mov     [rbp+50h+var_B4], r9d
0x180002e78  mov     rdx, [rax]
0x180002e7b  test    rdx, rdx
0x180002e7e  jz      short loc_180002E90
0x180002e80  mov     rax, rcx
0x180002e83  inc     rax
0x180002e86  cmp     [rdx+rax], r9b
0x180002e8a  jnz     short loc_180002E83
0x180002e8c  inc     eax
0x180002e8e  jmp     short loc_180002E9A
0x180002e90  lea     rdx, qword_18002D6C0
0x180002e97  mov     eax, r8d
0x180002e9a  mov     [rbp+50h+var_C8], eax
0x180002e9d  mov     rax, [rbp+50h+arg_30]
0x180002ea4  mov     [rbp+50h+var_D0], rdx
0x180002ea8  mov     [rbp+50h+var_C4], r9d
0x180002eac  mov     rdx, [rax]
0x180002eaf  test    rdx, rdx
0x180002eb2  jz      short loc_180002EC4
0x180002eb4  mov     rax, rcx
0x180002eb7  inc     rax
0x180002eba  cmp     [rdx+rax], r9b
0x180002ebe  jnz     short loc_180002EB7
0x180002ec0  inc     eax
0x180002ec2  jmp     short loc_180002ECE
0x180002ec4  lea     rdx, qword_18002D6C0
0x180002ecb  mov     eax, r8d
0x180002ece  mov     [rsp+150h+var_D8], eax
0x180002ed2  mov     rax, [rbp+50h+arg_28]
0x180002ed9  mov     [rsp+150h+var_F0], rax
0x180002ede  mov     rax, [rbp+50h+arg_20]
0x180002ee5  mov     [rsp+150h+var_E0], rdx
0x180002eea  mov     [rsp+150h+var_D4], r9d
0x180002eef  mov     [rsp+150h+var_E8], 4
0x180002ef8  mov     rdx, [rax]
0x180002efb  test    rdx, rdx
0x180002efe  jz      short loc_180002F0F
0x180002f00  inc     rcx
0x180002f03  cmp     [rdx+rcx], r9b
0x180002f07  jnz     short loc_180002F00
0x180002f09  lea     r8d, [rcx+1]
0x180002f0d  jmp     short loc_180002F16
0x180002f0f  lea     rdx, qword_18002D6C0
0x180002f16  lea     rax, [rsp+150h+var_120]
0x180002f1b  mov     [rsp+150h+var_100], rdx
0x180002f20  mov     [rsp+150h+var_F8], r8d
0x180002f25  mov     rdx, r11
0x180002f28  mov     [rsp+150h+var_128], rax
0x180002f2d  xor     r8d, r8d
0x180002f30  mov     rcx, r10
0x180002f33  mov     [rsp+150h+var_130], 11h
0x180002f3b  mov     [rsp+150h+var_F4], r9d
0x180002f40  call    _tlgWriteTransfer_EventWriteTransfer
0x180002f45  mov     rcx, [rbp+50h+var_10]
0x180002f49  xor     rcx, rsp; StackCookie
0x180002f4c  call    __security_check_cookie
0x180002f51  mov     rdi, [rsp+150h+arg_10]
0x180002f59  add     rsp, 150h
0x180002f60  pop     rbp
0x180002f61  retn
```
