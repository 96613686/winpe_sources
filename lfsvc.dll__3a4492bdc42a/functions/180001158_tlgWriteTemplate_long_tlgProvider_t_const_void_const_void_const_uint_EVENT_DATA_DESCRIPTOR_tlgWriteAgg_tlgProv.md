# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001158`
- end: `0x1800012be`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@U4@U4@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@5532@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, char **, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007990`

## callees

- `0x180001158`
- `0x180004310`
- `0x18000b1c4`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char **a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        const unsigned __int16 **a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v12; // rdx
  int v13; // r8d
  const unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rcx
  __int64 v21; // rax
  char *v22; // rcx
  int v23; // edx
  _BYTE v25[32]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v26; // [rsp+50h] [rbp-71h]
  __int64 v27; // [rsp+58h] [rbp-69h]
  __int64 v28; // [rsp+60h] [rbp-61h]
  __int64 v29; // [rsp+68h] [rbp-59h]
  char *v30; // [rsp+70h] [rbp-51h]
  int v31; // [rsp+78h] [rbp-49h]
  int v32; // [rsp+7Ch] [rbp-45h]
  const unsigned __int16 *v33; // [rsp+80h] [rbp-41h]
  int v34; // [rsp+88h] [rbp-39h]
  int v35; // [rsp+8Ch] [rbp-35h]
  const unsigned __int16 *v36; // [rsp+90h] [rbp-31h]
  int v37; // [rsp+98h] [rbp-29h]
  int v38; // [rsp+9Ch] [rbp-25h]
  const unsigned __int16 *v39; // [rsp+A0h] [rbp-21h]
  int v40; // [rsp+A8h] [rbp-19h]
  int v41; // [rsp+ACh] [rbp-15h]
  __int64 v42; // [rsp+B0h] [rbp-11h]
  __int64 v43; // [rsp+B8h] [rbp-9h]
  __int64 v44; // [rsp+C0h] [rbp-1h]
  __int64 v45; // [rsp+C8h] [rbp+7h]

  v44 = a11;
  v12 = -1;
  v42 = a10;
  v13 = 1;
  v45 = 8;
  v43 = 4;
  v14 = *a9;
  if ( *a9 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v14 = &word_18000DA02;
    v16 = 1;
  }
  v40 = v16;
  v39 = v14;
  v41 = 0;
  v17 = *a8;
  if ( *a8 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)v17 + v18) );
    v19 = v18 + 1;
  }
  else
  {
    v17 = &word_18000DA02;
    v19 = 1;
  }
  v37 = v19;
  v36 = v17;
  v38 = 0;
  v20 = *a7;
  if ( *a7 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_BYTE *)v20 + v21) );
    v13 = v21 + 1;
  }
  else
  {
    v20 = &word_18000DA02;
  }
  v33 = v20;
  v34 = v13;
  v35 = 0;
  v22 = *a6;
  if ( *a6 )
  {
    do
      ++v12;
    while ( *(_WORD *)&v22[2 * v12] );
    v23 = 2 * v12 + 2;
  }
  else
  {
    v22 = byte_18000DA00;
    v23 = 2;
  }
  v28 = a5;
  v30 = v22;
  v31 = v23;
  v26 = a4;
  v32 = 0;
  v29 = 4;
  v27 = 8;
  return tlgWriteAgg((unsigned int)&dword_180012038, a2, 0, 10, (__int64)v25);
}

```

## disassembly

```asm
0x180001158  push    rbp
0x18000115a  lea     rbp, [rsp-1Fh]
0x18000115f  sub     rsp, 0E0h
0x180001166  mov     rax, cs:__security_cookie
0x18000116d  xor     rax, rsp
0x180001170  mov     [rbp+1Fh+var_10], rax
0x180001174  mov     rax, [rbp+1Fh+arg_50]
0x180001178  xor     r11d, r11d
0x18000117b  mov     [rbp+1Fh+var_20], rax
0x18000117f  mov     r10, rdx
0x180001182  mov     rax, [rbp+1Fh+arg_48]
0x180001186  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000118a  mov     [rbp+1Fh+var_30], rax
0x18000118e  mov     rax, [rbp+1Fh+arg_40]
0x180001192  lea     r8d, [r11+1]
0x180001196  mov     [rbp+1Fh+var_18], 8
0x18000119e  mov     [rbp+1Fh+var_28], 4
0x1800011a6  mov     rcx, [rax]
0x1800011a9  test    rcx, rcx
0x1800011ac  jz      short loc_1800011BE
0x1800011ae  mov     rax, rdx
0x1800011b1  inc     rax
0x1800011b4  cmp     [rcx+rax], r11b
0x1800011b8  jnz     short loc_1800011B1
0x1800011ba  inc     eax
0x1800011bc  jmp     short loc_1800011C8
0x1800011be  lea     rcx, word_18000DA02
0x1800011c5  mov     eax, r8d
0x1800011c8  mov     [rbp+1Fh+var_38], eax
0x1800011cb  mov     rax, [rbp+1Fh+arg_38]
0x1800011cf  mov     [rbp+1Fh+var_40], rcx
0x1800011d3  mov     [rbp+1Fh+var_34], r11d
0x1800011d7  mov     rcx, [rax]
0x1800011da  test    rcx, rcx
0x1800011dd  jz      short loc_1800011EF
0x1800011df  mov     rax, rdx
0x1800011e2  inc     rax
0x1800011e5  cmp     [rcx+rax], r11b
0x1800011e9  jnz     short loc_1800011E2
0x1800011eb  inc     eax
0x1800011ed  jmp     short loc_1800011F9
0x1800011ef  lea     rcx, word_18000DA02
0x1800011f6  mov     eax, r8d
0x1800011f9  mov     [rbp+1Fh+var_48], eax
0x1800011fc  mov     rax, [rbp+1Fh+arg_30]
0x180001200  mov     [rbp+1Fh+var_50], rcx
0x180001204  mov     [rbp+1Fh+var_44], r11d
0x180001208  mov     rcx, [rax]
0x18000120b  test    rcx, rcx
0x18000120e  jz      short loc_180001222
0x180001210  mov     rax, rdx
0x180001213  inc     rax
0x180001216  cmp     [rcx+rax], r11b
0x18000121a  jnz     short loc_180001213
0x18000121c  lea     r8d, [rax+1]
0x180001220  jmp     short loc_180001229
0x180001222  lea     rcx, word_18000DA02
0x180001229  mov     rax, [rbp+1Fh+arg_28]
0x18000122d  mov     [rbp+1Fh+var_60], rcx
0x180001231  mov     [rbp+1Fh+var_58], r8d
0x180001235  mov     [rbp+1Fh+var_54], r11d
0x180001239  mov     rcx, [rax]
0x18000123c  test    rcx, rcx
0x18000123f  jz      short loc_180001254
0x180001241  inc     rdx
0x180001244  cmp     [rcx+rdx*2], r11w
0x180001249  jnz     short loc_180001241
0x18000124b  lea     edx, ds:2[rdx*2]
0x180001252  jmp     short loc_180001260
0x180001254  lea     rcx, byte_18000DA00
0x18000125b  mov     edx, 2
0x180001260  mov     rax, [rbp+1Fh+arg_20]
0x180001264  xor     r8d, r8d
0x180001267  mov     [rbp+1Fh+var_80], rax
0x18000126b  lea     rax, [rsp+0E0h+var_B0]
0x180001270  mov     [rbp+1Fh+var_70], rcx
0x180001274  lea     rcx, dword_180012038
0x18000127b  mov     [rbp+1Fh+var_68], edx
0x18000127e  mov     rdx, r10
0x180001281  mov     [rbp+1Fh+var_90], r9
0x180001285  mov     r9d, 0Ah
0x18000128b  mov     [rsp+0E0h+var_C0], rax
0x180001290  mov     [rbp+1Fh+var_64], r11d
0x180001294  mov     [rbp+1Fh+var_78], 4
0x18000129c  mov     [rbp+1Fh+var_88], 8
0x1800012a4  call    _tlgWriteAgg
0x1800012a9  mov     rcx, [rbp+1Fh+var_10]
0x1800012ad  xor     rcx, rsp; StackCookie
0x1800012b0  call    __security_check_cookie
0x1800012b5  add     rsp, 0E0h
0x1800012bc  pop     rbp
0x1800012bd  retn
```
