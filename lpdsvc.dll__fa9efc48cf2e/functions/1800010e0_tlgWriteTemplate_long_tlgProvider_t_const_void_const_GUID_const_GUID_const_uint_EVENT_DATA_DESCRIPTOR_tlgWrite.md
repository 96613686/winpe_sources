# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800010e0`
- end: `0x18000138b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, char **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, char **, __int64, const unsigned __int16 **, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a5cc`

## callees

- `0x1800010e0`
- `0x18000170c`
- `0x180001ce0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        char **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        char **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        char **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  char *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  char *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  char *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  char *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  char *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  char *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  int v87; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v23 = 2;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)&v24[2 * v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = byte_18000FB68;
    v26 = 2;
  }
  v86 = v26;
  v27 = 1;
  v85 = v24;
  v87 = 0;
  v28 = *a19;
  if ( *a19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_18000FB6A;
    v30 = 1;
  }
  v83 = v30;
  v80 = a18;
  v82 = v28;
  v84 = 0;
  v81 = 4;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = byte_18000FB68;
    v33 = 2;
  }
  v78 = v33;
  v77 = v31;
  v79 = 0;
  v34 = *a16;
  if ( *a16 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_18000FB6A;
    v36 = 1;
  }
  v75 = v36;
  v72 = a15;
  v74 = v34;
  v76 = 0;
  v73 = 4;
  v37 = *a14;
  if ( *a14 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_18000FB6A;
    v39 = 1;
  }
  v70 = v39;
  v67 = a13;
  v69 = v37;
  v71 = 0;
  v68 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *(_WORD *)&v40[2 * v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = byte_18000FB68;
  }
  v62 = a11;
  v64 = v40;
  v65 = v23;
  v66 = 0;
  v42 = *a10;
  v63 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &word_18000FB6A;
    v44 = 1;
  }
  v60 = v44;
  v57 = a9;
  v59 = v42;
  v61 = 0;
  v58 = 4;
  v45 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v27 = v22 + 1;
  }
  else
  {
    v45 = &word_18000FB6A;
  }
  v52 = a7;
  v50 = a6;
  v48 = a5;
  v54 = v45;
  v55 = v27;
  v56 = 0;
  v53 = 4;
  v51 = 8;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 18, v47);
}

```

## disassembly

```asm
0x1800010e0  mov     [rsp-8+arg_10], rbx
0x1800010e5  push    rbp
0x1800010e6  push    rsi
0x1800010e7  push    rdi
0x1800010e8  lea     rbp, [rsp-60h]
0x1800010ed  sub     rsp, 160h
0x1800010f4  mov     rax, cs:__security_cookie
0x1800010fb  xor     rax, rsp
0x1800010fe  mov     [rbp+70h+var_20], rax
0x180001102  mov     rax, [rbp+70h+arg_98]
0x180001109  mov     r11, rdx
0x18000110c  mov     r10, rcx
0x18000110f  xor     ebx, ebx
0x180001111  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001115  mov     r9d, 2
0x18000111b  mov     rdx, [rax]
0x18000111e  test    rdx, rdx
0x180001121  jz      short loc_180001138
0x180001123  mov     rax, rcx
0x180001126  inc     rax
0x180001129  cmp     [rdx+rax*2], bx
0x18000112d  jnz     short loc_180001126
0x18000112f  lea     eax, ds:2[rax*2]
0x180001136  jmp     short loc_180001142
0x180001138  lea     rdx, byte_18000FB68
0x18000113f  mov     eax, r9d
0x180001142  mov     [rbp+70h+var_28], eax
0x180001145  lea     rdi, word_18000FB6A
0x18000114c  mov     rax, [rbp+70h+arg_90]
0x180001153  mov     r8d, 1
0x180001159  mov     [rbp+70h+var_30], rdx
0x18000115d  mov     [rbp+70h+var_24], ebx
0x180001160  mov     rdx, [rax]
0x180001163  test    rdx, rdx
0x180001166  jz      short loc_180001177
0x180001168  mov     rax, rcx
0x18000116b  inc     rax
0x18000116e  cmp     [rdx+rax], bl
0x180001171  jnz     short loc_18000116B
0x180001173  inc     eax
0x180001175  jmp     short loc_18000117D
0x180001177  mov     rdx, rdi
0x18000117a  mov     eax, r8d
0x18000117d  mov     [rbp+70h+var_38], eax
0x180001180  mov     rax, [rbp+70h+arg_88]
0x180001187  mov     [rbp+70h+var_50], rax
0x18000118b  mov     rax, [rbp+70h+arg_80]
0x180001192  mov     [rbp+70h+var_40], rdx
0x180001196  mov     [rbp+70h+var_34], ebx
0x180001199  mov     [rbp+70h+var_48], 4
0x1800011a1  mov     rdx, [rax]
0x1800011a4  test    rdx, rdx
0x1800011a7  jz      short loc_1800011BE
0x1800011a9  mov     rax, rcx
0x1800011ac  inc     rax
0x1800011af  cmp     [rdx+rax*2], bx
0x1800011b3  jnz     short loc_1800011AC
0x1800011b5  lea     eax, ds:2[rax*2]
0x1800011bc  jmp     short loc_1800011C8
0x1800011be  lea     rdx, byte_18000FB68
0x1800011c5  mov     eax, r9d
0x1800011c8  mov     [rbp+70h+var_58], eax
0x1800011cb  mov     rax, [rbp+70h+arg_78]
0x1800011d2  mov     [rbp+70h+var_60], rdx
0x1800011d6  mov     [rbp+70h+var_54], ebx
0x1800011d9  mov     rdx, [rax]
0x1800011dc  test    rdx, rdx
0x1800011df  jz      short loc_1800011F0
0x1800011e1  mov     rax, rcx
0x1800011e4  inc     rax
0x1800011e7  cmp     [rdx+rax], bl
0x1800011ea  jnz     short loc_1800011E4
0x1800011ec  inc     eax
0x1800011ee  jmp     short loc_1800011F6
0x1800011f0  mov     rdx, rdi
0x1800011f3  mov     eax, r8d
0x1800011f6  mov     [rbp+70h+var_68], eax
0x1800011f9  mov     rax, [rbp+70h+arg_70]
0x180001200  mov     [rbp+70h+var_80], rax
0x180001204  mov     rax, [rbp+70h+arg_68]
0x18000120b  mov     [rbp+70h+var_70], rdx
0x18000120f  mov     [rbp+70h+var_64], ebx
0x180001212  mov     [rbp+70h+var_78], 4
0x18000121a  mov     rdx, [rax]
0x18000121d  test    rdx, rdx
0x180001220  jz      short loc_180001231
0x180001222  mov     rax, rcx
0x180001225  inc     rax
0x180001228  cmp     [rdx+rax], bl
0x18000122b  jnz     short loc_180001225
0x18000122d  inc     eax
0x18000122f  jmp     short loc_180001237
0x180001231  mov     rdx, rdi
0x180001234  mov     eax, r8d
0x180001237  mov     [rbp+70h+var_88], eax
0x18000123a  mov     rax, [rbp+70h+arg_60]
0x180001241  mov     [rbp+70h+var_A0], rax
0x180001245  mov     rax, [rbp+70h+arg_58]
0x18000124c  mov     [rbp+70h+var_90], rdx
0x180001250  mov     [rbp+70h+var_84], ebx
0x180001253  mov     [rbp+70h+var_98], 4
0x18000125b  mov     rdx, [rax]
0x18000125e  test    rdx, rdx
0x180001261  jz      short loc_180001279
0x180001263  mov     rax, rcx
0x180001266  inc     rax
0x180001269  cmp     [rdx+rax*2], bx
0x18000126d  jnz     short loc_180001266
0x18000126f  lea     r9d, ds:2[rax*2]
0x180001277  jmp     short loc_180001280
0x180001279  lea     rdx, byte_18000FB68
0x180001280  mov     rax, [rbp+70h+arg_50]
0x180001287  mov     [rbp+70h+var_C0], rax
0x18000128b  mov     rax, [rbp+70h+arg_48]
0x180001292  mov     [rbp+70h+var_B0], rdx
0x180001296  mov     [rbp+70h+var_A8], r9d
0x18000129a  mov     [rbp+70h+var_A4], ebx
0x18000129d  mov     rdx, [rax]
0x1800012a0  mov     [rbp+70h+var_B8], 4
0x1800012a8  test    rdx, rdx
0x1800012ab  jz      short loc_1800012BC
0x1800012ad  mov     rax, rcx
0x1800012b0  inc     rax
0x1800012b3  cmp     [rdx+rax], bl
0x1800012b6  jnz     short loc_1800012B0
0x1800012b8  inc     eax
0x1800012ba  jmp     short loc_1800012C2
0x1800012bc  mov     rdx, rdi
0x1800012bf  mov     eax, r8d
0x1800012c2  mov     [rbp+70h+var_C8], eax
0x1800012c5  mov     rax, [rbp+70h+arg_40]
0x1800012cc  mov     [rbp+70h+var_E0], rax
0x1800012d0  mov     rax, [rbp+70h+arg_38]
0x1800012d7  mov     [rbp+70h+var_D0], rdx
0x1800012db  mov     [rbp+70h+var_C4], ebx
0x1800012de  mov     [rbp+70h+var_D8], 4
0x1800012e6  mov     rdx, [rax]
0x1800012e9  test    rdx, rdx
0x1800012ec  jz      short loc_1800012FC
0x1800012ee  inc     rcx
0x1800012f1  cmp     [rdx+rcx], bl
0x1800012f4  jnz     short loc_1800012EE
0x1800012f6  lea     r8d, [rcx+1]
0x1800012fa  jmp     short loc_1800012FF
0x1800012fc  mov     rdx, rdi
0x1800012ff  mov     rax, [rbp+70h+arg_30]
0x180001306  xor     r9d, r9d
0x180001309  mov     [rsp+170h+var_100], rax
0x18000130e  mov     rcx, r10
0x180001311  mov     rax, [rbp+70h+arg_28]
0x180001318  mov     [rsp+170h+var_110], rax
0x18000131d  mov     rax, [rbp+70h+arg_20]
0x180001324  mov     [rsp+170h+var_120], rax
0x180001329  lea     rax, [rsp+170h+var_140]
0x18000132e  mov     [rbp+70h+var_F0], rdx
0x180001332  mov     rdx, r11
0x180001335  mov     [rbp+70h+var_E8], r8d
0x180001339  xor     r8d, r8d
0x18000133c  mov     [rsp+170h+var_148], rax
0x180001341  mov     [rsp+170h+var_150], 12h
0x180001349  mov     [rbp+70h+var_E4], ebx
0x18000134c  mov     [rsp+170h+var_F8], 4
0x180001355  mov     [rsp+170h+var_108], 8
0x18000135e  mov     [rsp+170h+var_118], 8
0x180001367  call    _tlgWriteTransfer_EventWriteTransfer
0x18000136c  mov     rcx, [rbp+70h+var_20]
0x180001370  xor     rcx, rsp; StackCookie
0x180001373  call    __security_check_cookie
0x180001378  mov     rbx, [rsp+170h+arg_10]
0x180001380  add     rsp, 160h
0x180001387  pop     rdi
0x180001388  pop     rsi
0x180001389  pop     rbp
0x18000138a  retn
```
