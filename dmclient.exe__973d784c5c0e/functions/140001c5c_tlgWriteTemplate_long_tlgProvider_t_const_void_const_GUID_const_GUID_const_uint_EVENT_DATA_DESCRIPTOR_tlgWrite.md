# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001c5c`
- end: `0x140001d7a`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4334@Z`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400143cc`

## callees

- `0x140001840`
- `0x140001c5c`
- `0x140019610`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        const unsigned __int16 **a9,
        __int64 a10)
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
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-49h]
  int v23; // [rsp+58h] [rbp-41h]
  int v24; // [rsp+5Ch] [rbp-3Dh]
  __int64 v25; // [rsp+60h] [rbp-39h]
  __int64 v26; // [rsp+68h] [rbp-31h]
  __int64 v27; // [rsp+70h] [rbp-29h]
  __int64 v28; // [rsp+78h] [rbp-21h]
  const unsigned __int16 *v29; // [rsp+80h] [rbp-19h]
  int v30; // [rsp+88h] [rbp-11h]
  int v31; // [rsp+8Ch] [rbp-Dh]
  const unsigned __int16 *v32; // [rsp+90h] [rbp-9h]
  int v33; // [rsp+98h] [rbp-1h]
  int v34; // [rsp+9Ch] [rbp+3h]
  __int64 v35; // [rsp+A0h] [rbp+7h]
  __int64 v36; // [rsp+A8h] [rbp+Fh]

  v35 = a10;
  v11 = -1;
  v36 = 4;
  v12 = 1;
  v13 = *a9;
  if ( *a9 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &word_14001D5D2;
    v15 = 1;
  }
  v33 = v15;
  v32 = v13;
  v34 = 0;
  v16 = *a8;
  if ( *a8 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_BYTE *)v16 + v17) );
    v18 = v17 + 1;
  }
  else
  {
    v16 = &word_14001D5D2;
    v18 = 1;
  }
  v30 = v18;
  v27 = a7;
  v25 = a6;
  v29 = v16;
  v31 = 0;
  v28 = 4;
  v19 = *a5;
  v26 = 4;
  if ( v19 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v19 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v19 = &word_14001D5D2;
  }
  v22 = v19;
  v23 = v12;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140028000, a2, 0, 0, 8u, &v21);
}

```

## disassembly

```asm
0x140001c5c  push    rbp
0x140001c5e  lea     rbp, [rsp-27h]
0x140001c63  sub     rsp, 0C0h
0x140001c6a  mov     rax, cs:__security_cookie
0x140001c71  xor     rax, rsp
0x140001c74  mov     [rbp+27h+var_10], rax
0x140001c78  mov     rax, [rbp+27h+arg_48]
0x140001c7c  lea     r11, word_14001D5D2
0x140001c83  xor     r9d, r9d
0x140001c86  mov     [rbp+27h+var_20], rax
0x140001c8a  mov     rax, [rbp+27h+arg_40]
0x140001c8e  mov     r10, rdx
0x140001c91  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001c95  mov     [rbp+27h+var_18], 4
0x140001c9d  lea     r8d, [r9+1]
0x140001ca1  mov     rdx, [rax]
0x140001ca4  test    rdx, rdx
0x140001ca7  jz      short loc_140001CB9
0x140001ca9  mov     rax, rcx
0x140001cac  inc     rax
0x140001caf  cmp     [rdx+rax], r9b
0x140001cb3  jnz     short loc_140001CAC
0x140001cb5  inc     eax
0x140001cb7  jmp     short loc_140001CBF
0x140001cb9  mov     rdx, r11
0x140001cbc  mov     eax, r8d
0x140001cbf  mov     [rbp+27h+var_28], eax
0x140001cc2  mov     rax, [rbp+27h+arg_38]
0x140001cc6  mov     [rbp+27h+var_30], rdx
0x140001cca  mov     [rbp+27h+var_24], r9d
0x140001cce  mov     rdx, [rax]
0x140001cd1  test    rdx, rdx
0x140001cd4  jz      short loc_140001CE6
0x140001cd6  mov     rax, rcx
0x140001cd9  inc     rax
0x140001cdc  cmp     [rdx+rax], r9b
0x140001ce0  jnz     short loc_140001CD9
0x140001ce2  inc     eax
0x140001ce4  jmp     short loc_140001CEC
0x140001ce6  mov     rdx, r11
0x140001ce9  mov     eax, r8d
0x140001cec  mov     [rbp+27h+var_38], eax
0x140001cef  mov     rax, [rbp+27h+arg_30]
0x140001cf3  mov     [rbp+27h+var_50], rax
0x140001cf7  mov     rax, [rbp+27h+arg_28]
0x140001cfb  mov     [rbp+27h+var_60], rax
0x140001cff  mov     rax, [rbp+27h+arg_20]
0x140001d03  mov     [rbp+27h+var_40], rdx
0x140001d07  mov     [rbp+27h+var_34], r9d
0x140001d0b  mov     [rbp+27h+var_48], 4
0x140001d13  mov     rdx, [rax]
0x140001d16  mov     [rbp+27h+var_58], 4
0x140001d1e  test    rdx, rdx
0x140001d21  jz      short loc_140001D32
0x140001d23  inc     rcx
0x140001d26  cmp     [rdx+rcx], r9b
0x140001d2a  jnz     short loc_140001D23
0x140001d2c  lea     r8d, [rcx+1]
0x140001d30  jmp     short loc_140001D35
0x140001d32  mov     rdx, r11
0x140001d35  lea     rax, [rbp+27h+var_90]
0x140001d39  mov     [rbp+27h+var_70], rdx
0x140001d3d  mov     [rbp+27h+var_68], r8d
0x140001d41  lea     rcx, dword_140028000
0x140001d48  mov     [rsp+0C0h+var_98], rax
0x140001d4d  xor     r8d, r8d
0x140001d50  mov     rdx, r10
0x140001d53  mov     [rsp+0C0h+var_A0], 8
0x140001d5b  mov     [rbp+27h+var_64], r9d
0x140001d5f  call    _tlgWriteTransfer_EventWriteTransfer
0x140001d64  mov     rcx, [rbp+27h+var_10]
0x140001d68  xor     rcx, rsp; StackCookie
0x140001d6b  call    __security_check_cookie
0x140001d70  add     rsp, 0C0h
0x140001d77  pop     rbp
0x140001d78  retn
```
