# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)

- ea: `0x180001724`
- end: `0x180001860`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z`
- size: `316`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `67`
- callee_count: `3`
- tags: ``

## callers

- `0x180004cbc`
- `0x180005504`
- `0x180005918`
- `0x180005c20`
- `0x180006a40`
- `0x180007b44`
- `0x1800088c0`
- `0x180008b80`
- `0x180008fa4`
- `0x180009a4c`
- `0x18000a140`
- `0x18000a2d0`
- `0x18000ae80`
- `0x18000bdbc`
- `0x18000cf04`
- `0x18000d788`
- `0x18000e0e8`
- `0x18000e738`
- `0x18000ea10`
- `0x18000f52c`
- `0x18000f950`
- `0x18000fb78`
- `0x18000fcdc`
- `0x18000fe68`
- `0x18000fff0`
- `0x1800103d8`
- `0x18001054c`
- `0x180010724`
- `0x180010a30`
- `0x1800117ac`
- `0x18001196c`
- `0x180011b08`
- `0x180012238`
- `0x180013210`
- `0x180013444`
- `0x180013690`
- `0x1800139a8`
- `0x180013c44`
- `0x1800141d0`
- `0x180014810`
- `0x1800149e0`
- `0x180014c00`
- `0x180015210`
- `0x1800154f0`
- `0x1800157dc`
- `0x180015a60`
- `0x180015bc0`
- `0x180015ff0`
- `0x180016190`
- `0x180016450`

## callees

- `0x180001724`
- `0x180001ef8`
- `0x18002b960`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        const unsigned __int16 **a10)
{
  __int64 v11; // rcx
  int v12; // r8d
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  _BYTE v24[32]; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v25; // [rsp+50h] [rbp-49h]
  int v26; // [rsp+58h] [rbp-41h]
  int v27; // [rsp+5Ch] [rbp-3Dh]
  __int64 v28; // [rsp+60h] [rbp-39h]
  __int64 v29; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-29h]
  int v31; // [rsp+78h] [rbp-21h]
  int v32; // [rsp+7Ch] [rbp-1Dh]
  __int64 v33; // [rsp+80h] [rbp-19h]
  __int64 v34; // [rsp+88h] [rbp-11h]
  const unsigned __int16 *v35; // [rsp+90h] [rbp-9h]
  int v36; // [rsp+98h] [rbp-1h]
  int v37; // [rsp+9Ch] [rbp+3h]
  const unsigned __int16 *v38; // [rsp+A0h] [rbp+7h]
  int v39; // [rsp+A8h] [rbp+Fh]
  int v40; // [rsp+ACh] [rbp+13h]

  v11 = -1;
  v12 = 1;
  v13 = *a10;
  if ( *a10 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &word_18002F722;
    v15 = 1;
  }
  v39 = v15;
  v38 = v13;
  v40 = 0;
  v16 = *a9;
  if ( *a9 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_BYTE *)v16 + v17) );
    v18 = v17 + 1;
  }
  else
  {
    v16 = &word_18002F722;
    v18 = 1;
  }
  v36 = v18;
  v33 = a8;
  v35 = v16;
  v37 = 0;
  v34 = 4;
  v19 = *a7;
  if ( *a7 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *((_BYTE *)v19 + v20) );
    v21 = v20 + 1;
  }
  else
  {
    v19 = &word_18002F722;
    v21 = 1;
  }
  v31 = v21;
  v28 = a6;
  v30 = v19;
  v32 = 0;
  v29 = 4;
  v22 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v22 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v22 = &word_18002F722;
  }
  v25 = v22;
  v26 = v12;
  v27 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180044008, a2, 0, 0, 8, v24);
}

```

## disassembly

```asm
0x180001724  push    rbp
0x180001726  lea     rbp, [rsp-27h]
0x18000172b  sub     rsp, 0C0h
0x180001732  mov     rax, cs:__security_cookie
0x180001739  xor     rax, rsp
0x18000173c  mov     [rbp+27h+var_10], rax
0x180001740  mov     rax, [rbp+27h+arg_48]
0x180001744  lea     r11, word_18002F722
0x18000174b  mov     r10, rdx
0x18000174e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001752  xor     r9d, r9d
0x180001755  mov     r8d, 1
0x18000175b  mov     rdx, [rax]
0x18000175e  test    rdx, rdx
0x180001761  jz      short loc_180001773
0x180001763  mov     rax, rcx
0x180001766  inc     rax
0x180001769  cmp     [rdx+rax], r9b
0x18000176d  jnz     short loc_180001766
0x18000176f  inc     eax
0x180001771  jmp     short loc_180001779
0x180001773  mov     rdx, r11
0x180001776  mov     eax, r8d
0x180001779  mov     [rbp+27h+var_18], eax
0x18000177c  mov     rax, [rbp+27h+arg_40]
0x180001780  mov     [rbp+27h+var_20], rdx
0x180001784  mov     [rbp+27h+var_14], r9d
0x180001788  mov     rdx, [rax]
0x18000178b  test    rdx, rdx
0x18000178e  jz      short loc_1800017A0
0x180001790  mov     rax, rcx
0x180001793  inc     rax
0x180001796  cmp     [rdx+rax], r9b
0x18000179a  jnz     short loc_180001793
0x18000179c  inc     eax
0x18000179e  jmp     short loc_1800017A6
0x1800017a0  mov     rdx, r11
0x1800017a3  mov     eax, r8d
0x1800017a6  mov     [rbp+27h+var_28], eax
0x1800017a9  mov     rax, [rbp+27h+arg_38]
0x1800017ad  mov     [rbp+27h+var_40], rax
0x1800017b1  mov     rax, [rbp+27h+arg_30]
0x1800017b5  mov     [rbp+27h+var_30], rdx
0x1800017b9  mov     [rbp+27h+var_24], r9d
0x1800017bd  mov     [rbp+27h+var_38], 4
0x1800017c5  mov     rdx, [rax]
0x1800017c8  test    rdx, rdx
0x1800017cb  jz      short loc_1800017DD
0x1800017cd  mov     rax, rcx
0x1800017d0  inc     rax
0x1800017d3  cmp     [rdx+rax], r9b
0x1800017d7  jnz     short loc_1800017D0
0x1800017d9  inc     eax
0x1800017db  jmp     short loc_1800017E3
0x1800017dd  mov     rdx, r11
0x1800017e0  mov     eax, r8d
0x1800017e3  mov     [rbp+27h+var_48], eax
0x1800017e6  mov     rax, [rbp+27h+arg_28]
0x1800017ea  mov     [rbp+27h+var_60], rax
0x1800017ee  mov     rax, [rbp+27h+arg_20]
0x1800017f2  mov     [rbp+27h+var_50], rdx
0x1800017f6  mov     [rbp+27h+var_44], r9d
0x1800017fa  mov     [rbp+27h+var_58], 4
0x180001802  mov     rdx, [rax]
0x180001805  test    rdx, rdx
0x180001808  jz      short loc_180001819
0x18000180a  inc     rcx
0x18000180d  cmp     [rdx+rcx], r9b
0x180001811  jnz     short loc_18000180A
0x180001813  lea     r8d, [rcx+1]
0x180001817  jmp     short loc_18000181C
0x180001819  mov     rdx, r11
0x18000181c  lea     rax, [rbp+27h+var_90]
0x180001820  mov     [rbp+27h+var_70], rdx
0x180001824  mov     [rbp+27h+var_68], r8d
0x180001828  lea     rcx, dword_180044008
0x18000182f  mov     [rsp+0C0h+var_98], rax
0x180001834  xor     r8d, r8d
0x180001837  mov     rdx, r10
0x18000183a  mov     [rsp+0C0h+var_A0], 8
0x180001842  mov     [rbp+27h+var_64], r9d
0x180001846  call    _tlgWriteTransfer_EventWriteTransfer
0x18000184b  mov     rcx, [rbp+27h+var_10]
0x18000184f  xor     rcx, rsp; StackCookie
0x180001852  call    __security_check_cookie
0x180001857  add     rsp, 0C0h
0x18000185e  pop     rbp
0x18000185f  retn
```
