# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001628`
- end: `0x180001744`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@45@Z`
- size: `284`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a2a4`
- `0x18000a6f4`
- `0x18000a8a8`
- `0x18000be00`

## callees

- `0x1800013c8`
- `0x180001628`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  const unsigned __int16 *v17; // rdx
  int v18; // ecx
  _BYTE v20[32]; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-31h]
  int v22; // [rsp+58h] [rbp-29h]
  int v23; // [rsp+5Ch] [rbp-25h]
  __int64 v24; // [rsp+60h] [rbp-21h]
  __int64 v25; // [rsp+68h] [rbp-19h]
  const unsigned __int16 *v26; // [rsp+70h] [rbp-11h]
  int v27; // [rsp+78h] [rbp-9h]
  int v28; // [rsp+7Ch] [rbp-5h]
  __int64 v29; // [rsp+80h] [rbp-1h]
  __int64 v30; // [rsp+88h] [rbp+7h]
  const unsigned __int16 *v31; // [rsp+90h] [rbp+Fh]
  int v32; // [rsp+98h] [rbp+17h]
  int v33; // [rsp+9Ch] [rbp+1Bh]

  v10 = -1;
  v11 = 1;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &word_180021D5A;
    v14 = 1;
  }
  v32 = v14;
  v29 = a8;
  v31 = v12;
  v33 = 0;
  v30 = 4;
  v15 = *a7;
  if ( *a7 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_BYTE *)v15 + v16) );
    v11 = v16 + 1;
  }
  else
  {
    v15 = &word_180021D5A;
  }
  v24 = a6;
  v26 = v15;
  v27 = v11;
  v28 = 0;
  v17 = *a5;
  v25 = 4;
  if ( v17 )
  {
    do
      ++v10;
    while ( v17[v10] );
    v18 = 2 * v10 + 2;
  }
  else
  {
    v17 = &dword_18002237C;
    v18 = 2;
  }
  v21 = v17;
  v22 = v18;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, a2, 0, 0, 7, v20);
}

```

## disassembly

```asm
0x180001628  push    rbp
0x18000162a  lea     rbp, [rsp-2Fh]
0x18000162f  sub     rsp, 0B0h
0x180001636  mov     rax, cs:__security_cookie
0x18000163d  xor     rax, rsp
0x180001640  mov     [rbp+2Fh+var_10], rax
0x180001644  mov     rax, [rbp+2Fh+arg_40]
0x180001648  mov     r10, rdx
0x18000164b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000164f  xor     r9d, r9d
0x180001652  mov     r8d, 1
0x180001658  mov     rdx, [rax]
0x18000165b  test    rdx, rdx
0x18000165e  jz      short loc_180001670
0x180001660  mov     rax, rcx
0x180001663  inc     rax
0x180001666  cmp     [rdx+rax], r9b
0x18000166a  jnz     short loc_180001663
0x18000166c  inc     eax
0x18000166e  jmp     short loc_18000167A
0x180001670  lea     rdx, word_180021D5A
0x180001677  mov     eax, r8d
0x18000167a  mov     [rbp+2Fh+var_18], eax
0x18000167d  mov     rax, [rbp+2Fh+arg_38]
0x180001681  mov     [rbp+2Fh+var_30], rax
0x180001685  mov     rax, [rbp+2Fh+arg_30]
0x180001689  mov     [rbp+2Fh+var_20], rdx
0x18000168d  mov     [rbp+2Fh+var_14], r9d
0x180001691  mov     [rbp+2Fh+var_28], 4
0x180001699  mov     rdx, [rax]
0x18000169c  test    rdx, rdx
0x18000169f  jz      short loc_1800016B3
0x1800016a1  mov     rax, rcx
0x1800016a4  inc     rax
0x1800016a7  cmp     [rdx+rax], r9b
0x1800016ab  jnz     short loc_1800016A4
0x1800016ad  lea     r8d, [rax+1]
0x1800016b1  jmp     short loc_1800016BA
0x1800016b3  lea     rdx, word_180021D5A
0x1800016ba  mov     rax, [rbp+2Fh+arg_28]
0x1800016be  mov     [rbp+2Fh+var_50], rax
0x1800016c2  mov     rax, [rbp+2Fh+arg_20]
0x1800016c6  mov     [rbp+2Fh+var_40], rdx
0x1800016ca  mov     [rbp+2Fh+var_38], r8d
0x1800016ce  mov     [rbp+2Fh+var_34], r9d
0x1800016d2  mov     rdx, [rax]
0x1800016d5  mov     [rbp+2Fh+var_48], 4
0x1800016dd  test    rdx, rdx
0x1800016e0  jz      short loc_1800016F5
0x1800016e2  inc     rcx
0x1800016e5  cmp     [rdx+rcx*2], r9w
0x1800016ea  jnz     short loc_1800016E2
0x1800016ec  lea     ecx, ds:2[rcx*2]
0x1800016f3  jmp     short loc_180001701
0x1800016f5  lea     rdx, dword_18002237C
0x1800016fc  mov     ecx, 2
0x180001701  lea     rax, [rbp+2Fh+var_80]
0x180001705  mov     [rbp+2Fh+var_60], rdx
0x180001709  mov     [rbp+2Fh+var_58], ecx
0x18000170c  xor     r8d, r8d
0x18000170f  mov     [rsp+0B0h+var_88], rax
0x180001714  lea     rcx, dword_18002B0C0
0x18000171b  mov     rdx, r10
0x18000171e  mov     [rsp+0B0h+var_90], 7
0x180001726  mov     [rbp+2Fh+var_54], r9d
0x18000172a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000172f  mov     rcx, [rbp+2Fh+var_10]
0x180001733  xor     rcx, rsp; StackCookie
0x180001736  call    __security_check_cookie
0x18000173b  add     rsp, 0B0h
0x180001742  pop     rbp
0x180001743  retn
```
