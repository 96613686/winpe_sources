# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001394`
- end: `0x180001470`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64, __int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025a18`

## callees

- `0x180001278`
- `0x180001394`
- `0x180001bb0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        __int64 *a8,
        __int64 a9,
        __int64 a10)
{
  int v11; // edx
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  _BYTE v16[32]; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v17; // [rsp+50h] [rbp-49h]
  int v18; // [rsp+58h] [rbp-41h]
  int v19; // [rsp+5Ch] [rbp-3Dh]
  __int64 v20; // [rsp+60h] [rbp-39h]
  __int64 v21; // [rsp+68h] [rbp-31h]
  __int64 v22; // [rsp+70h] [rbp-29h]
  __int64 v23; // [rsp+78h] [rbp-21h]
  __int64 v24; // [rsp+80h] [rbp-19h]
  __int64 v25; // [rsp+88h] [rbp-11h]
  __int64 v26; // [rsp+90h] [rbp-9h]
  __int64 v27; // [rsp+98h] [rbp-1h]
  __int64 v28; // [rsp+A0h] [rbp+7h]
  __int64 v29; // [rsp+A8h] [rbp+Fh]

  v28 = a10;
  v26 = a9;
  v11 = 1;
  v29 = 8;
  v27 = 1;
  v25 = 16;
  v12 = *a8;
  v22 = a7;
  v20 = a6;
  v24 = v12;
  v23 = 4;
  v21 = 4;
  v13 = *a5;
  if ( *a5 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v11 = v14 + 1;
  }
  else
  {
    v13 = &word_1800311E2;
  }
  v17 = v13;
  v18 = v11;
  v19 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18003D5C8, a2, 0, 0, 8, v16);
}

```

## disassembly

```asm
0x180001394  push    rbp
0x180001396  lea     rbp, [rsp-27h]
0x18000139b  sub     rsp, 0C0h
0x1800013a2  mov     rax, cs:__security_cookie
0x1800013a9  xor     rax, rsp
0x1800013ac  mov     [rbp+27h+var_10], rax
0x1800013b0  mov     rax, [rbp+27h+arg_48]
0x1800013b4  mov     r9d, 8
0x1800013ba  mov     [rbp+27h+var_20], rax
0x1800013be  mov     r10, rdx
0x1800013c1  mov     rax, [rbp+27h+arg_40]
0x1800013c5  xor     r8d, r8d
0x1800013c8  mov     [rbp+27h+var_30], rax
0x1800013cc  mov     rax, [rbp+27h+arg_38]
0x1800013d0  lea     edx, [r9-7]
0x1800013d4  mov     [rbp+27h+var_18], r9
0x1800013d8  mov     [rbp+27h+var_28], rdx
0x1800013dc  mov     [rbp+27h+var_38], 10h
0x1800013e4  mov     rcx, [rax]
0x1800013e7  mov     rax, [rbp+27h+arg_30]
0x1800013eb  mov     [rbp+27h+var_50], rax
0x1800013ef  mov     rax, [rbp+27h+arg_28]
0x1800013f3  mov     [rbp+27h+var_60], rax
0x1800013f7  mov     rax, [rbp+27h+arg_20]
0x1800013fb  mov     [rbp+27h+var_40], rcx
0x1800013ff  mov     [rbp+27h+var_48], 4
0x180001407  mov     [rbp+27h+var_58], 4
0x18000140f  mov     rcx, [rax]
0x180001412  test    rcx, rcx
0x180001415  jz      short loc_180001429
0x180001417  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000141b  inc     rax
0x18000141e  cmp     [rcx+rax], r8b
0x180001422  jnz     short loc_18000141B
0x180001424  lea     edx, [rax+1]
0x180001427  jmp     short loc_180001430
0x180001429  lea     rcx, word_1800311E2
0x180001430  lea     rax, [rbp+27h+var_90]
0x180001434  mov     [rbp+27h+var_70], rcx
0x180001438  mov     [rsp+0C0h+var_98], rax
0x18000143d  lea     rcx, dword_18003D5C8
0x180001444  mov     [rsp+0C0h+var_A0], r9d
0x180001449  xor     r9d, r9d
0x18000144c  mov     [rbp+27h+var_68], edx
0x18000144f  mov     rdx, r10
0x180001452  mov     [rbp+27h+var_64], r8d
0x180001456  call    _tlgWriteTransfer_EventWriteTransfer
0x18000145b  mov     rcx, [rbp+27h+var_10]
0x18000145f  xor     rcx, rsp; StackCookie
0x180001462  call    __security_check_cookie
0x180001467  add     rsp, 0C0h
0x18000146e  pop     rbp
0x18000146f  retn
```
