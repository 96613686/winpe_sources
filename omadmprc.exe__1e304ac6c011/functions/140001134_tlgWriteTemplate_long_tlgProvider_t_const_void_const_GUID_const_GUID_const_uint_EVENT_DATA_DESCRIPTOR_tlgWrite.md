# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001134`
- end: `0x14000130d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@444AEBU?$_tlgWrapperByVal@$03@@5555AEBU?$_tlgWrapSz@D@@@Z`
- size: `473`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c1a4`
- `0x14000c328`

## callees

- `0x140001090`
- `0x140001134`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 **a6,
        __int64 **a7,
        __int64 **a8,
        __int64 **a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        const unsigned __int16 **a15)
{
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  int v20; // r8d
  __int64 *v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  __int64 *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  __int64 *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  __int64 *v30; // rdx
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h]
  __int64 *v35; // [rsp+60h] [rbp-A0h]
  int v36; // [rsp+68h] [rbp-98h]
  int v37; // [rsp+6Ch] [rbp-94h]
  __int64 *v38; // [rsp+70h] [rbp-90h]
  int v39; // [rsp+78h] [rbp-88h]
  int v40; // [rsp+7Ch] [rbp-84h]
  __int64 *v41; // [rsp+80h] [rbp-80h]
  int v42; // [rsp+88h] [rbp-78h]
  int v43; // [rsp+8Ch] [rbp-74h]
  __int64 *v44; // [rsp+90h] [rbp-70h]
  int v45; // [rsp+98h] [rbp-68h]
  int v46; // [rsp+9Ch] [rbp-64h]
  __int64 v47; // [rsp+A0h] [rbp-60h]
  __int64 v48; // [rsp+A8h] [rbp-58h]
  __int64 v49; // [rsp+B0h] [rbp-50h]
  __int64 v50; // [rsp+B8h] [rbp-48h]
  __int64 v51; // [rsp+C0h] [rbp-40h]
  __int64 v52; // [rsp+C8h] [rbp-38h]
  __int64 v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+D8h] [rbp-28h]
  __int64 v55; // [rsp+E0h] [rbp-20h]
  __int64 v56; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v57; // [rsp+F0h] [rbp-10h]
  int v58; // [rsp+F8h] [rbp-8h]
  int v59; // [rsp+FCh] [rbp-4h]

  v16 = -1;
  v17 = *a15;
  if ( *a15 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)v17 + v18) );
    v19 = v18 + 1;
  }
  else
  {
    v17 = &qword_14001A560;
    v19 = 1;
  }
  v58 = v19;
  v20 = 2;
  v55 = a14;
  v53 = a13;
  v51 = a12;
  v49 = a11;
  v47 = a10;
  v57 = v17;
  v59 = 0;
  v56 = 4;
  v21 = *a9;
  v54 = 4;
  v52 = 4;
  v50 = 4;
  v48 = 4;
  if ( v21 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v21 + v22) );
    v23 = 2 * v22 + 2;
  }
  else
  {
    v21 = &qword_14001A798;
    v23 = 2;
  }
  v45 = v23;
  v44 = v21;
  v46 = 0;
  v24 = *a8;
  if ( *a8 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &qword_14001A798;
    v26 = 2;
  }
  v42 = v26;
  v41 = v24;
  v43 = 0;
  v27 = *a7;
  if ( *a7 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v27 + v28) );
    v29 = 2 * v28 + 2;
  }
  else
  {
    v27 = &qword_14001A798;
    v29 = 2;
  }
  v39 = v29;
  v38 = v27;
  v40 = 0;
  v30 = *a6;
  if ( *a6 )
  {
    do
      ++v16;
    while ( *((_WORD *)v30 + v16) );
    v20 = 2 * v16 + 2;
  }
  else
  {
    v30 = &qword_14001A798;
  }
  v33 = a5;
  v35 = v30;
  v36 = v20;
  v37 = 0;
  v34 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, a2, 0, 0, 0xDu, &v32);
}

```

## disassembly

```asm
0x140001134  push    rbp
0x140001136  lea     rbp, [rsp-10h]
0x14000113b  sub     rsp, 110h
0x140001142  mov     rax, cs:__security_cookie
0x140001149  xor     rax, rsp
0x14000114c  mov     [rbp+10h+var_10], rax
0x140001150  mov     rax, [rbp+10h+arg_70]
0x140001157  mov     r10, rdx
0x14000115a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000115e  xor     r9d, r9d
0x140001161  mov     rdx, [rax]
0x140001164  test    rdx, rdx
0x140001167  jz      short loc_140001179
0x140001169  mov     rax, rcx
0x14000116c  inc     rax
0x14000116f  cmp     [rdx+rax], r9b
0x140001173  jnz     short loc_14000116C
0x140001175  inc     eax
0x140001177  jmp     short loc_140001185
0x140001179  lea     rdx, qword_14001A560
0x140001180  mov     eax, 1
0x140001185  mov     [rbp+10h+var_18], eax
0x140001188  lea     r11, qword_14001A798
0x14000118f  mov     rax, [rbp+10h+arg_68]
0x140001196  mov     r8d, 2
0x14000119c  mov     [rbp+10h+var_30], rax
0x1400011a0  mov     rax, [rbp+10h+arg_60]
0x1400011a7  mov     [rbp+10h+var_40], rax
0x1400011ab  mov     rax, [rbp+10h+arg_58]
0x1400011af  mov     [rbp+10h+var_50], rax
0x1400011b3  mov     rax, [rbp+10h+arg_50]
0x1400011b7  mov     [rbp+10h+var_60], rax
0x1400011bb  mov     rax, [rbp+10h+arg_48]
0x1400011bf  mov     [rbp+10h+var_70], rax
0x1400011c3  mov     rax, [rbp+10h+arg_40]
0x1400011c7  mov     [rbp+10h+var_20], rdx
0x1400011cb  mov     [rbp+10h+var_14], r9d
0x1400011cf  mov     [rbp+10h+var_28], 4
0x1400011d7  mov     rdx, [rax]
0x1400011da  mov     [rbp+10h+var_38], 4
0x1400011e2  mov     [rbp+10h+var_48], 4
0x1400011ea  mov     [rbp+10h+var_58], 4
0x1400011f2  mov     [rbp+10h+var_68], 4
0x1400011fa  test    rdx, rdx
0x1400011fd  jz      short loc_140001215
0x1400011ff  mov     rax, rcx
0x140001202  inc     rax
0x140001205  cmp     [rdx+rax*2], r9w
0x14000120a  jnz     short loc_140001202
0x14000120c  lea     eax, ds:2[rax*2]
0x140001213  jmp     short loc_14000121B
0x140001215  mov     rdx, r11
0x140001218  mov     eax, r8d
0x14000121b  mov     [rbp+10h+var_78], eax
0x14000121e  mov     rax, [rbp+10h+arg_38]
0x140001222  mov     [rbp+10h+var_80], rdx
0x140001226  mov     [rbp+10h+var_74], r9d
0x14000122a  mov     rdx, [rax]
0x14000122d  test    rdx, rdx
0x140001230  jz      short loc_140001248
0x140001232  mov     rax, rcx
0x140001235  inc     rax
0x140001238  cmp     [rdx+rax*2], r9w
0x14000123d  jnz     short loc_140001235
0x14000123f  lea     eax, ds:2[rax*2]
0x140001246  jmp     short loc_14000124E
0x140001248  mov     rdx, r11
0x14000124b  mov     eax, r8d
0x14000124e  mov     [rbp+10h+var_88], eax
0x140001251  mov     rax, [rbp+10h+arg_30]
0x140001255  mov     [rbp+10h+var_90], rdx
0x140001259  mov     [rbp+10h+var_84], r9d
0x14000125d  mov     rdx, [rax]
0x140001260  test    rdx, rdx
0x140001263  jz      short loc_14000127B
0x140001265  mov     rax, rcx
0x140001268  inc     rax
0x14000126b  cmp     [rdx+rax*2], r9w
0x140001270  jnz     short loc_140001268
0x140001272  lea     eax, ds:2[rax*2]
0x140001279  jmp     short loc_140001281
0x14000127b  mov     rdx, r11
0x14000127e  mov     eax, r8d
0x140001281  mov     [rsp+110h+var_98], eax
0x140001285  mov     rax, [rbp+10h+arg_28]
0x140001289  mov     [rsp+110h+var_A0], rdx
0x14000128e  mov     [rsp+110h+var_94], r9d
0x140001293  mov     rdx, [rax]
0x140001296  test    rdx, rdx
0x140001299  jz      short loc_1400012AF
0x14000129b  inc     rcx
0x14000129e  cmp     [rdx+rcx*2], r9w
0x1400012a3  jnz     short loc_14000129B
0x1400012a5  lea     r8d, ds:2[rcx*2]
0x1400012ad  jmp     short loc_1400012B2
0x1400012af  mov     rdx, r11
0x1400012b2  mov     rax, [rbp+10h+arg_20]
0x1400012b6  lea     rcx, dword_140023000
0x1400012bd  mov     [rsp+110h+var_C0], rax
0x1400012c2  lea     rax, [rsp+110h+var_E0]
0x1400012c7  mov     [rsp+110h+var_B0], rdx
0x1400012cc  mov     rdx, r10
0x1400012cf  mov     [rsp+110h+var_A8], r8d
0x1400012d4  xor     r8d, r8d
0x1400012d7  mov     [rsp+110h+var_E8], rax
0x1400012dc  mov     [rsp+110h+var_F0], 0Dh
0x1400012e4  mov     [rsp+110h+var_A4], r9d
0x1400012e9  mov     [rsp+110h+var_B8], 8
0x1400012f2  call    _tlgWriteTransfer_EventWriteTransfer
0x1400012f7  mov     rcx, [rbp+10h+var_10]
0x1400012fb  xor     rcx, rsp; StackCookie
0x1400012fe  call    __security_check_cookie
0x140001303  add     rsp, 110h
0x14000130a  pop     rbp
0x14000130b  retn
```
