# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800023fc`
- end: `0x1800024ff`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `259`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180018afc`
- `0x180018d7c`
- `0x180018f90`
- `0x180019894`
- `0x18001a974`
- `0x18001aac8`

## callees

- `0x180001448`
- `0x1800023fc`
- `0x1800036f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 *a8,
        __int64 a9,
        __int64 a10)
{
  int v12; // r8d
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v20; // [rsp+50h] [rbp-49h]
  int v21; // [rsp+58h] [rbp-41h]
  int v22; // [rsp+5Ch] [rbp-3Dh]
  __int64 v23; // [rsp+60h] [rbp-39h]
  __int64 v24; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v25; // [rsp+70h] [rbp-29h]
  int v26; // [rsp+78h] [rbp-21h]
  int v27; // [rsp+7Ch] [rbp-1Dh]
  __int64 v28; // [rsp+80h] [rbp-19h]
  __int64 v29; // [rsp+88h] [rbp-11h]
  __int64 v30; // [rsp+90h] [rbp-9h]
  __int64 v31; // [rsp+98h] [rbp-1h]
  __int64 v32; // [rsp+A0h] [rbp+7h]
  __int64 v33; // [rsp+A8h] [rbp+Fh]

  v32 = a10;
  v30 = a9;
  v33 = 8;
  v12 = 1;
  v31 = 4;
  v29 = 16;
  v28 = *a8;
  v13 = -1;
  v14 = *a7;
  if ( *a7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v14 = &qword_18002D6C0;
    v16 = 1;
  }
  v26 = v16;
  v23 = a6;
  v25 = v14;
  v27 = 0;
  v24 = 8;
  v17 = *a5;
  if ( *a5 )
  {
    do
      ++v13;
    while ( *((_BYTE *)v17 + v13) );
    v12 = v13 + 1;
  }
  else
  {
    v17 = &qword_18002D6C0;
  }
  v20 = v17;
  v21 = v12;
  v22 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 8u, &v19);
}

```

## disassembly

```asm
0x1800023fc  push    rbp
0x1800023fe  lea     rbp, [rsp-27h]
0x180002403  sub     rsp, 0C0h
0x18000240a  mov     rax, cs:__security_cookie
0x180002411  xor     rax, rsp
0x180002414  mov     [rbp+27h+var_10], rax
0x180002418  mov     rax, [rbp+27h+arg_48]
0x18000241c  mov     r10, rcx
0x18000241f  mov     [rbp+27h+var_20], rax
0x180002423  xor     r9d, r9d
0x180002426  mov     rax, [rbp+27h+arg_40]
0x18000242a  mov     r11, rdx
0x18000242d  mov     [rbp+27h+var_30], rax
0x180002431  mov     rax, [rbp+27h+arg_38]
0x180002435  mov     [rbp+27h+var_18], 8
0x18000243d  lea     r8d, [r9+1]
0x180002441  mov     [rbp+27h+var_28], 4
0x180002449  mov     [rbp+27h+var_38], 10h
0x180002451  mov     rcx, [rax]
0x180002454  mov     rax, [rbp+27h+arg_30]
0x180002458  mov     [rbp+27h+var_40], rcx
0x18000245c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002460  mov     rdx, [rax]
0x180002463  test    rdx, rdx
0x180002466  jz      short loc_180002478
0x180002468  mov     rax, rcx
0x18000246b  inc     rax
0x18000246e  cmp     [rdx+rax], r9b
0x180002472  jnz     short loc_18000246B
0x180002474  inc     eax
0x180002476  jmp     short loc_180002482
0x180002478  lea     rdx, qword_18002D6C0
0x18000247f  mov     eax, r8d
0x180002482  mov     [rbp+27h+var_48], eax
0x180002485  mov     rax, [rbp+27h+arg_28]
0x180002489  mov     [rbp+27h+var_60], rax
0x18000248d  mov     rax, [rbp+27h+arg_20]
0x180002491  mov     [rbp+27h+var_50], rdx
0x180002495  mov     [rbp+27h+var_44], r9d
0x180002499  mov     [rbp+27h+var_58], 8
0x1800024a1  mov     rdx, [rax]
0x1800024a4  test    rdx, rdx
0x1800024a7  jz      short loc_1800024B8
0x1800024a9  inc     rcx
0x1800024ac  cmp     [rdx+rcx], r9b
0x1800024b0  jnz     short loc_1800024A9
0x1800024b2  lea     r8d, [rcx+1]
0x1800024b6  jmp     short loc_1800024BF
0x1800024b8  lea     rdx, qword_18002D6C0
0x1800024bf  lea     rax, [rbp+27h+var_90]
0x1800024c3  mov     [rbp+27h+var_70], rdx
0x1800024c7  mov     [rbp+27h+var_68], r8d
0x1800024cb  mov     rdx, r11
0x1800024ce  mov     [rsp+0C0h+var_98], rax
0x1800024d3  xor     r8d, r8d
0x1800024d6  mov     rcx, r10
0x1800024d9  mov     [rsp+0C0h+var_A0], 8
0x1800024e1  mov     [rbp+27h+var_64], r9d
0x1800024e5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800024ea  mov     rcx, [rbp+27h+var_10]
0x1800024ee  xor     rcx, rsp; StackCookie
0x1800024f1  call    __security_check_cookie
0x1800024f6  add     rsp, 0C0h
0x1800024fd  pop     rbp
0x1800024fe  retn
```
