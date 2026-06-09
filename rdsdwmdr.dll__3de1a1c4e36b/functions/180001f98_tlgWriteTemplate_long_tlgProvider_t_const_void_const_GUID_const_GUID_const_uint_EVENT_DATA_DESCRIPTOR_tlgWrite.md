# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001f98`
- end: `0x1800020b5`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z`
- size: `285`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aa80`
- `0x18000bdbc`
- `0x180010a30`
- `0x180011c84`
- `0x1800129e4`
- `0x180013da4`
- `0x1800141d0`
- `0x18001e6c8`
- `0x18001e8e0`
- `0x18001eb5c`
- `0x18001f2d0`
- `0x1800242a0`
- `0x180024bb0`
- `0x180026cd0`
- `0x180027e10`
- `0x180028514`
- `0x180028934`
- `0x180029af0`
- `0x180029c10`
- `0x180029f60`
- `0x18002a608`
- `0x18002a888`
- `0x18002ab18`
- `0x18002b0dc`

## callees

- `0x180001ef8`
- `0x180001f98`
- `0x18002b960`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
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
  _BYTE v21[32]; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-49h]
  int v23; // [rsp+58h] [rbp-41h]
  int v24; // [rsp+5Ch] [rbp-3Dh]
  __int64 v25; // [rsp+60h] [rbp-39h]
  __int64 v26; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v27; // [rsp+70h] [rbp-29h]
  int v28; // [rsp+78h] [rbp-21h]
  int v29; // [rsp+7Ch] [rbp-1Dh]
  __int64 v30; // [rsp+80h] [rbp-19h]
  __int64 v31; // [rsp+88h] [rbp-11h]
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
    v13 = &word_18002F722;
    v15 = 1;
  }
  v33 = v15;
  v30 = a8;
  v32 = v13;
  v34 = 0;
  v31 = 4;
  v16 = *a7;
  if ( *a7 )
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
  v28 = v18;
  v25 = a6;
  v27 = v16;
  v29 = 0;
  v26 = 4;
  v19 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v19 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v19 = &word_18002F722;
  }
  v22 = v19;
  v23 = v12;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180044008, a2, 0, 0, 8, v21);
}

```

## disassembly

```asm
0x180001f98  push    rbp
0x180001f9a  lea     rbp, [rsp-27h]
0x180001f9f  sub     rsp, 0C0h
0x180001fa6  mov     rax, cs:__security_cookie
0x180001fad  xor     rax, rsp
0x180001fb0  mov     [rbp+27h+var_10], rax
0x180001fb4  mov     rax, [rbp+27h+arg_48]
0x180001fb8  lea     r11, word_18002F722
0x180001fbf  xor     r9d, r9d
0x180001fc2  mov     [rbp+27h+var_20], rax
0x180001fc6  mov     rax, [rbp+27h+arg_40]
0x180001fca  mov     r10, rdx
0x180001fcd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001fd1  mov     [rbp+27h+var_18], 4
0x180001fd9  lea     r8d, [r9+1]
0x180001fdd  mov     rdx, [rax]
0x180001fe0  test    rdx, rdx
0x180001fe3  jz      short loc_180001FF5
0x180001fe5  mov     rax, rcx
0x180001fe8  inc     rax
0x180001feb  cmp     [rdx+rax], r9b
0x180001fef  jnz     short loc_180001FE8
0x180001ff1  inc     eax
0x180001ff3  jmp     short loc_180001FFB
0x180001ff5  mov     rdx, r11
0x180001ff8  mov     eax, r8d
0x180001ffb  mov     [rbp+27h+var_28], eax
0x180001ffe  mov     rax, [rbp+27h+arg_38]
0x180002002  mov     [rbp+27h+var_40], rax
0x180002006  mov     rax, [rbp+27h+arg_30]
0x18000200a  mov     [rbp+27h+var_30], rdx
0x18000200e  mov     [rbp+27h+var_24], r9d
0x180002012  mov     [rbp+27h+var_38], 4
0x18000201a  mov     rdx, [rax]
0x18000201d  test    rdx, rdx
0x180002020  jz      short loc_180002032
0x180002022  mov     rax, rcx
0x180002025  inc     rax
0x180002028  cmp     [rdx+rax], r9b
0x18000202c  jnz     short loc_180002025
0x18000202e  inc     eax
0x180002030  jmp     short loc_180002038
0x180002032  mov     rdx, r11
0x180002035  mov     eax, r8d
0x180002038  mov     [rbp+27h+var_48], eax
0x18000203b  mov     rax, [rbp+27h+arg_28]
0x18000203f  mov     [rbp+27h+var_60], rax
0x180002043  mov     rax, [rbp+27h+arg_20]
0x180002047  mov     [rbp+27h+var_50], rdx
0x18000204b  mov     [rbp+27h+var_44], r9d
0x18000204f  mov     [rbp+27h+var_58], 4
0x180002057  mov     rdx, [rax]
0x18000205a  test    rdx, rdx
0x18000205d  jz      short loc_18000206E
0x18000205f  inc     rcx
0x180002062  cmp     [rdx+rcx], r9b
0x180002066  jnz     short loc_18000205F
0x180002068  lea     r8d, [rcx+1]
0x18000206c  jmp     short loc_180002071
0x18000206e  mov     rdx, r11
0x180002071  lea     rax, [rbp+27h+var_90]
0x180002075  mov     [rbp+27h+var_70], rdx
0x180002079  mov     [rbp+27h+var_68], r8d
0x18000207d  lea     rcx, dword_180044008
0x180002084  mov     [rsp+0C0h+var_98], rax
0x180002089  xor     r8d, r8d
0x18000208c  mov     rdx, r10
0x18000208f  mov     [rsp+0C0h+var_A0], 8
0x180002097  mov     [rbp+27h+var_64], r9d
0x18000209b  call    _tlgWriteTransfer_EventWriteTransfer
0x1800020a0  mov     rcx, [rbp+27h+var_10]
0x1800020a4  xor     rcx, rsp; StackCookie
0x1800020a7  call    __security_check_cookie
0x1800020ac  add     rsp, 0C0h
0x1800020b3  pop     rbp
0x1800020b4  retn
```
