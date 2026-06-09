# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)

- ea: `0x180001008`
- end: `0x18000120b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U2@U2@U2@U2@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@44444AEBU?$_tlgWrapSz@G@@4@Z`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003560`

## callees

- `0x180001008`
- `0x180001214`
- `0x18000c030`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int **a7,
        int **a8,
        int **a9,
        int **a10,
        int **a11,
        int **a12,
        int **a13,
        int **a14)
{
  __int64 v15; // rcx
  int v16; // r8d
  int *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  int *v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  int *v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  int *v26; // rdx
  __int64 v27; // rax
  int v28; // eax
  int *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  int *v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  int *v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  int *v38; // rdx
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+30h] [rbp-C9h] BYREF
  __int64 v41; // [rsp+50h] [rbp-A9h]
  __int64 v42; // [rsp+58h] [rbp-A1h]
  __int64 v43; // [rsp+60h] [rbp-99h]
  __int64 v44; // [rsp+68h] [rbp-91h]
  int *v45; // [rsp+70h] [rbp-89h]
  int v46; // [rsp+78h] [rbp-81h]
  int v47; // [rsp+7Ch] [rbp-7Dh]
  int *v48; // [rsp+80h] [rbp-79h]
  int v49; // [rsp+88h] [rbp-71h]
  int v50; // [rsp+8Ch] [rbp-6Dh]
  int *v51; // [rsp+90h] [rbp-69h]
  int v52; // [rsp+98h] [rbp-61h]
  int v53; // [rsp+9Ch] [rbp-5Dh]
  int *v54; // [rsp+A0h] [rbp-59h]
  int v55; // [rsp+A8h] [rbp-51h]
  int v56; // [rsp+ACh] [rbp-4Dh]
  int *v57; // [rsp+B0h] [rbp-49h]
  int v58; // [rsp+B8h] [rbp-41h]
  int v59; // [rsp+BCh] [rbp-3Dh]
  int *v60; // [rsp+C0h] [rbp-39h]
  int v61; // [rsp+C8h] [rbp-31h]
  int v62; // [rsp+CCh] [rbp-2Dh]
  int *v63; // [rsp+D0h] [rbp-29h]
  int v64; // [rsp+D8h] [rbp-21h]
  int v65; // [rsp+DCh] [rbp-1Dh]
  int *v66; // [rsp+E0h] [rbp-19h]
  int v67; // [rsp+E8h] [rbp-11h]
  int v68; // [rsp+ECh] [rbp-Dh]

  v15 = -1;
  v16 = 1;
  v17 = *a14;
  if ( *a14 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)v17 + v18) );
    v19 = v18 + 1;
  }
  else
  {
    v17 = &dword_18000F424;
    v19 = 1;
  }
  v67 = v19;
  v66 = v17;
  v68 = 0;
  v20 = *a13;
  if ( *a13 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)v20 + v21) );
    v22 = 2 * v21 + 2;
  }
  else
  {
    v20 = &dword_18000ED9C;
    v22 = 2;
  }
  v64 = v22;
  v63 = v20;
  v65 = 0;
  v23 = *a12;
  if ( *a12 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *((_BYTE *)v23 + v24) );
    v25 = v24 + 1;
  }
  else
  {
    v23 = &dword_18000F424;
    v25 = 1;
  }
  v61 = v25;
  v60 = v23;
  v62 = 0;
  v26 = *a11;
  if ( *a11 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &dword_18000F424;
    v28 = 1;
  }
  v58 = v28;
  v57 = v26;
  v59 = 0;
  v29 = *a10;
  if ( *a10 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &dword_18000F424;
    v31 = 1;
  }
  v55 = v31;
  v54 = v29;
  v56 = 0;
  v32 = *a9;
  if ( *a9 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_BYTE *)v32 + v33) );
    v34 = v33 + 1;
  }
  else
  {
    v32 = &dword_18000F424;
    v34 = 1;
  }
  v52 = v34;
  v51 = v32;
  v53 = 0;
  v35 = *a8;
  if ( *a8 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &dword_18000F424;
    v37 = 1;
  }
  v49 = v37;
  v48 = v35;
  v50 = 0;
  v38 = *a7;
  if ( *a7 )
  {
    do
      ++v15;
    while ( *((_BYTE *)v38 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v38 = &dword_18000F424;
  }
  v43 = a6;
  v41 = a5;
  v45 = v38;
  v46 = v16;
  v47 = 0;
  v44 = 8;
  v42 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014048, a2, 0, 0, 0xCu, &v40);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-7]
0x18000100f  sub     rsp, 100h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+7+var_10], rax
0x180001024  mov     rax, [rbp+7+arg_68]
0x180001028  lea     r11, dword_18000F424
0x18000102f  mov     r10, rdx
0x180001032  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001036  xor     r9d, r9d
0x180001039  mov     r8d, 1
0x18000103f  mov     rdx, [rax]
0x180001042  test    rdx, rdx
0x180001045  jz      short loc_180001057
0x180001047  mov     rax, rcx
0x18000104a  inc     rax
0x18000104d  cmp     [rdx+rax], r9b
0x180001051  jnz     short loc_18000104A
0x180001053  inc     eax
0x180001055  jmp     short loc_18000105D
0x180001057  mov     rdx, r11
0x18000105a  mov     eax, r8d
0x18000105d  mov     [rbp+7+var_18], eax
0x180001060  mov     rax, [rbp+7+arg_60]
0x180001064  mov     [rbp+7+var_20], rdx
0x180001068  mov     [rbp+7+var_14], r9d
0x18000106c  mov     rdx, [rax]
0x18000106f  test    rdx, rdx
0x180001072  jz      short loc_18000108A
0x180001074  mov     rax, rcx
0x180001077  inc     rax
0x18000107a  cmp     [rdx+rax*2], r9w
0x18000107f  jnz     short loc_180001077
0x180001081  lea     eax, ds:2[rax*2]
0x180001088  jmp     short loc_180001096
0x18000108a  lea     rdx, dword_18000ED9C
0x180001091  mov     eax, 2
0x180001096  mov     [rbp+7+var_28], eax
0x180001099  mov     rax, [rbp+7+arg_58]
0x18000109d  mov     [rbp+7+var_30], rdx
0x1800010a1  mov     [rbp+7+var_24], r9d
0x1800010a5  mov     rdx, [rax]
0x1800010a8  test    rdx, rdx
0x1800010ab  jz      short loc_1800010BD
0x1800010ad  mov     rax, rcx
0x1800010b0  inc     rax
0x1800010b3  cmp     [rdx+rax], r9b
0x1800010b7  jnz     short loc_1800010B0
0x1800010b9  inc     eax
0x1800010bb  jmp     short loc_1800010C3
0x1800010bd  mov     rdx, r11
0x1800010c0  mov     eax, r8d
0x1800010c3  mov     [rbp+7+var_38], eax
0x1800010c6  mov     rax, [rbp+7+arg_50]
0x1800010ca  mov     [rbp+7+var_40], rdx
0x1800010ce  mov     [rbp+7+var_34], r9d
0x1800010d2  mov     rdx, [rax]
0x1800010d5  test    rdx, rdx
0x1800010d8  jz      short loc_1800010EA
0x1800010da  mov     rax, rcx
0x1800010dd  inc     rax
0x1800010e0  cmp     [rdx+rax], r9b
0x1800010e4  jnz     short loc_1800010DD
0x1800010e6  inc     eax
0x1800010e8  jmp     short loc_1800010F0
0x1800010ea  mov     rdx, r11
0x1800010ed  mov     eax, r8d
0x1800010f0  mov     [rbp+7+var_48], eax
0x1800010f3  mov     rax, [rbp+7+arg_48]
0x1800010f7  mov     [rbp+7+var_50], rdx
0x1800010fb  mov     [rbp+7+var_44], r9d
0x1800010ff  mov     rdx, [rax]
0x180001102  test    rdx, rdx
0x180001105  jz      short loc_180001117
0x180001107  mov     rax, rcx
0x18000110a  inc     rax
0x18000110d  cmp     [rdx+rax], r9b
0x180001111  jnz     short loc_18000110A
0x180001113  inc     eax
0x180001115  jmp     short loc_18000111D
0x180001117  mov     rdx, r11
0x18000111a  mov     eax, r8d
0x18000111d  mov     [rbp+7+var_58], eax
0x180001120  mov     rax, [rbp+7+arg_40]
0x180001124  mov     [rbp+7+var_60], rdx
0x180001128  mov     [rbp+7+var_54], r9d
0x18000112c  mov     rdx, [rax]
0x18000112f  test    rdx, rdx
0x180001132  jz      short loc_180001144
0x180001134  mov     rax, rcx
0x180001137  inc     rax
0x18000113a  cmp     [rdx+rax], r9b
0x18000113e  jnz     short loc_180001137
0x180001140  inc     eax
0x180001142  jmp     short loc_18000114A
0x180001144  mov     rdx, r11
0x180001147  mov     eax, r8d
0x18000114a  mov     [rbp+7+var_68], eax
0x18000114d  mov     rax, [rbp+7+arg_38]
0x180001151  mov     [rbp+7+var_70], rdx
0x180001155  mov     [rbp+7+var_64], r9d
0x180001159  mov     rdx, [rax]
0x18000115c  test    rdx, rdx
0x18000115f  jz      short loc_180001171
0x180001161  mov     rax, rcx
0x180001164  inc     rax
0x180001167  cmp     [rdx+rax], r9b
0x18000116b  jnz     short loc_180001164
0x18000116d  inc     eax
0x18000116f  jmp     short loc_180001177
0x180001171  mov     rdx, r11
0x180001174  mov     eax, r8d
0x180001177  mov     [rbp+7+var_78], eax
0x18000117a  mov     rax, [rbp+7+arg_30]
0x18000117e  mov     [rbp+7+var_80], rdx
0x180001182  mov     [rbp+7+var_74], r9d
0x180001186  mov     rdx, [rax]
0x180001189  test    rdx, rdx
0x18000118c  jz      short loc_18000119D
0x18000118e  inc     rcx
0x180001191  cmp     [rdx+rcx], r9b
0x180001195  jnz     short loc_18000118E
0x180001197  lea     r8d, [rcx+1]
0x18000119b  jmp     short loc_1800011A0
0x18000119d  mov     rdx, r11
0x1800011a0  mov     rax, [rbp+7+arg_28]
0x1800011a4  lea     rcx, dword_180014048
0x1800011ab  mov     [rsp+100h+var_A0], rax
0x1800011b0  mov     rax, [rbp+7+arg_20]
0x1800011b4  mov     [rsp+100h+var_B0], rax
0x1800011b9  lea     rax, [rsp+100h+var_D0]
0x1800011be  mov     [rsp+100h+var_90], rdx
0x1800011c3  mov     rdx, r10
0x1800011c6  mov     [rsp+100h+var_88], r8d
0x1800011cb  xor     r8d, r8d
0x1800011ce  mov     [rsp+100h+var_D8], rax
0x1800011d3  mov     [rsp+100h+var_E0], 0Ch
0x1800011db  mov     [rbp+7+var_84], r9d
0x1800011df  mov     [rsp+100h+var_98], 8
0x1800011e8  mov     [rsp+100h+var_A8], 8
0x1800011f1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011f6  mov     rcx, [rbp+7+var_10]
0x1800011fa  xor     rcx, rsp; StackCookie
0x1800011fd  call    __security_check_cookie
0x180001202  add     rsp, 100h
0x180001209  pop     rbp
0x18000120a  retn
```
