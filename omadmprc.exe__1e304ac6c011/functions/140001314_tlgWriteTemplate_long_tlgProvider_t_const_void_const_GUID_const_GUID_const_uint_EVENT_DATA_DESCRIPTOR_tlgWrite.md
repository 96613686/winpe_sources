# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001314`
- end: `0x14000149c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@444AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bd90`
- `0x14000c084`

## callees

- `0x140001090`
- `0x140001314`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
        const unsigned __int16 **a11)
{
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  int v16; // r8d
  __int64 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  __int64 *v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  __int64 *v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  __int64 *v26; // rdx
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+30h] [rbp-81h] BYREF
  __int64 v29; // [rsp+50h] [rbp-61h]
  __int64 v30; // [rsp+58h] [rbp-59h]
  __int64 *v31; // [rsp+60h] [rbp-51h]
  int v32; // [rsp+68h] [rbp-49h]
  int v33; // [rsp+6Ch] [rbp-45h]
  __int64 *v34; // [rsp+70h] [rbp-41h]
  int v35; // [rsp+78h] [rbp-39h]
  int v36; // [rsp+7Ch] [rbp-35h]
  __int64 *v37; // [rsp+80h] [rbp-31h]
  int v38; // [rsp+88h] [rbp-29h]
  int v39; // [rsp+8Ch] [rbp-25h]
  __int64 *v40; // [rsp+90h] [rbp-21h]
  int v41; // [rsp+98h] [rbp-19h]
  int v42; // [rsp+9Ch] [rbp-15h]
  __int64 v43; // [rsp+A0h] [rbp-11h]
  __int64 v44; // [rsp+A8h] [rbp-9h]
  const unsigned __int16 *v45; // [rsp+B0h] [rbp-1h]
  int v46; // [rsp+B8h] [rbp+7h]
  int v47; // [rsp+BCh] [rbp+Bh]

  v12 = -1;
  v13 = *a11;
  if ( *a11 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &qword_14001A560;
    v15 = 1;
  }
  v46 = v15;
  v16 = 2;
  v43 = a10;
  v45 = v13;
  v47 = 0;
  v44 = 4;
  v17 = *a9;
  if ( *a9 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = &qword_14001A798;
    v19 = 2;
  }
  v41 = v19;
  v40 = v17;
  v42 = 0;
  v20 = *a8;
  if ( *a8 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)v20 + v21) );
    v22 = 2 * v21 + 2;
  }
  else
  {
    v20 = &qword_14001A798;
    v22 = 2;
  }
  v38 = v22;
  v37 = v20;
  v39 = 0;
  v23 = *a7;
  if ( *a7 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *((_WORD *)v23 + v24) );
    v25 = 2 * v24 + 2;
  }
  else
  {
    v23 = &qword_14001A798;
    v25 = 2;
  }
  v35 = v25;
  v34 = v23;
  v36 = 0;
  v26 = *a6;
  if ( *a6 )
  {
    do
      ++v12;
    while ( *((_WORD *)v26 + v12) );
    v16 = 2 * v12 + 2;
  }
  else
  {
    v26 = &qword_14001A798;
  }
  v29 = a5;
  v31 = v26;
  v32 = v16;
  v33 = 0;
  v30 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, a2, 0, 0, 9u, &v28);
}

```

## disassembly

```asm
0x140001314  push    rbp
0x140001316  lea     rbp, [rsp-1Fh]
0x14000131b  sub     rsp, 0D0h
0x140001322  mov     rax, cs:__security_cookie
0x140001329  xor     rax, rsp
0x14000132c  mov     [rbp+1Fh+var_10], rax
0x140001330  mov     rax, [rbp+1Fh+arg_50]
0x140001334  mov     r10, rdx
0x140001337  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000133b  xor     r9d, r9d
0x14000133e  mov     rdx, [rax]
0x140001341  test    rdx, rdx
0x140001344  jz      short loc_140001356
0x140001346  mov     rax, rcx
0x140001349  inc     rax
0x14000134c  cmp     [rdx+rax], r9b
0x140001350  jnz     short loc_140001349
0x140001352  inc     eax
0x140001354  jmp     short loc_140001362
0x140001356  lea     rdx, qword_14001A560
0x14000135d  mov     eax, 1
0x140001362  mov     [rbp+1Fh+var_18], eax
0x140001365  lea     r11, qword_14001A798
0x14000136c  mov     rax, [rbp+1Fh+arg_48]
0x140001370  mov     r8d, 2
0x140001376  mov     [rbp+1Fh+var_30], rax
0x14000137a  mov     rax, [rbp+1Fh+arg_40]
0x14000137e  mov     [rbp+1Fh+var_20], rdx
0x140001382  mov     [rbp+1Fh+var_14], r9d
0x140001386  mov     [rbp+1Fh+var_28], 4
0x14000138e  mov     rdx, [rax]
0x140001391  test    rdx, rdx
0x140001394  jz      short loc_1400013AC
0x140001396  mov     rax, rcx
0x140001399  inc     rax
0x14000139c  cmp     [rdx+rax*2], r9w
0x1400013a1  jnz     short loc_140001399
0x1400013a3  lea     eax, ds:2[rax*2]
0x1400013aa  jmp     short loc_1400013B2
0x1400013ac  mov     rdx, r11
0x1400013af  mov     eax, r8d
0x1400013b2  mov     [rbp+1Fh+var_38], eax
0x1400013b5  mov     rax, [rbp+1Fh+arg_38]
0x1400013b9  mov     [rbp+1Fh+var_40], rdx
0x1400013bd  mov     [rbp+1Fh+var_34], r9d
0x1400013c1  mov     rdx, [rax]
0x1400013c4  test    rdx, rdx
0x1400013c7  jz      short loc_1400013DF
0x1400013c9  mov     rax, rcx
0x1400013cc  inc     rax
0x1400013cf  cmp     [rdx+rax*2], r9w
0x1400013d4  jnz     short loc_1400013CC
0x1400013d6  lea     eax, ds:2[rax*2]
0x1400013dd  jmp     short loc_1400013E5
0x1400013df  mov     rdx, r11
0x1400013e2  mov     eax, r8d
0x1400013e5  mov     [rbp+1Fh+var_48], eax
0x1400013e8  mov     rax, [rbp+1Fh+arg_30]
0x1400013ec  mov     [rbp+1Fh+var_50], rdx
0x1400013f0  mov     [rbp+1Fh+var_44], r9d
0x1400013f4  mov     rdx, [rax]
0x1400013f7  test    rdx, rdx
0x1400013fa  jz      short loc_140001412
0x1400013fc  mov     rax, rcx
0x1400013ff  inc     rax
0x140001402  cmp     [rdx+rax*2], r9w
0x140001407  jnz     short loc_1400013FF
0x140001409  lea     eax, ds:2[rax*2]
0x140001410  jmp     short loc_140001418
0x140001412  mov     rdx, r11
0x140001415  mov     eax, r8d
0x140001418  mov     [rbp+1Fh+var_58], eax
0x14000141b  mov     rax, [rbp+1Fh+arg_28]
0x14000141f  mov     [rbp+1Fh+var_60], rdx
0x140001423  mov     [rbp+1Fh+var_54], r9d
0x140001427  mov     rdx, [rax]
0x14000142a  test    rdx, rdx
0x14000142d  jz      short loc_140001443
0x14000142f  inc     rcx
0x140001432  cmp     [rdx+rcx*2], r9w
0x140001437  jnz     short loc_14000142F
0x140001439  lea     r8d, ds:2[rcx*2]
0x140001441  jmp     short loc_140001446
0x140001443  mov     rdx, r11
0x140001446  mov     rax, [rbp+1Fh+arg_20]
0x14000144a  lea     rcx, dword_140023000
0x140001451  mov     [rbp+1Fh+var_80], rax
0x140001455  lea     rax, [rsp+0D0h+var_A0]
0x14000145a  mov     [rbp+1Fh+var_70], rdx
0x14000145e  mov     rdx, r10
0x140001461  mov     [rbp+1Fh+var_68], r8d
0x140001465  xor     r8d, r8d
0x140001468  mov     [rsp+0D0h+var_A8], rax
0x14000146d  mov     [rsp+0D0h+var_B0], 9
0x140001475  mov     [rbp+1Fh+var_64], r9d
0x140001479  mov     [rbp+1Fh+var_78], 8
0x140001481  call    _tlgWriteTransfer_EventWriteTransfer
0x140001486  mov     rcx, [rbp+1Fh+var_10]
0x14000148a  xor     rcx, rsp; StackCookie
0x14000148d  call    __security_check_cookie
0x140001492  add     rsp, 0D0h
0x140001499  pop     rbp
0x14000149a  retn
```
