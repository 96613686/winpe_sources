# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000113c`
- end: `0x180001256`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@54@Z`
- size: `282`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ef62`
- `0x18001f146`
- `0x18001f8b3`

## callees

- `0x18000113c`
- `0x1800013c8`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        __int64 a9)
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
  const unsigned __int16 *v29; // [rsp+80h] [rbp-1h]
  int v30; // [rsp+88h] [rbp+7h]
  int v31; // [rsp+8Ch] [rbp+Bh]
  __int64 v32; // [rsp+90h] [rbp+Fh]
  __int64 v33; // [rsp+98h] [rbp+17h]

  v32 = a9;
  v10 = -1;
  v33 = 4;
  v11 = 1;
  v12 = *a8;
  if ( *a8 )
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
  v30 = v14;
  v29 = v12;
  v31 = 0;
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
0x18000113c  push    rbp
0x18000113e  lea     rbp, [rsp-2Fh]
0x180001143  sub     rsp, 0B0h
0x18000114a  mov     rax, cs:__security_cookie
0x180001151  xor     rax, rsp
0x180001154  mov     [rbp+2Fh+var_10], rax
0x180001158  mov     rax, [rbp+2Fh+arg_40]
0x18000115c  xor     r9d, r9d
0x18000115f  mov     [rbp+2Fh+var_20], rax
0x180001163  mov     r10, rdx
0x180001166  mov     rax, [rbp+2Fh+arg_38]
0x18000116a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000116e  mov     [rbp+2Fh+var_18], 4
0x180001176  lea     r8d, [r9+1]
0x18000117a  mov     rdx, [rax]
0x18000117d  test    rdx, rdx
0x180001180  jz      short loc_180001192
0x180001182  mov     rax, rcx
0x180001185  inc     rax
0x180001188  cmp     [rdx+rax], r9b
0x18000118c  jnz     short loc_180001185
0x18000118e  inc     eax
0x180001190  jmp     short loc_18000119C
0x180001192  lea     rdx, word_180021D5A
0x180001199  mov     eax, r8d
0x18000119c  mov     [rbp+2Fh+var_28], eax
0x18000119f  mov     rax, [rbp+2Fh+arg_30]
0x1800011a3  mov     [rbp+2Fh+var_30], rdx
0x1800011a7  mov     [rbp+2Fh+var_24], r9d
0x1800011ab  mov     rdx, [rax]
0x1800011ae  test    rdx, rdx
0x1800011b1  jz      short loc_1800011C5
0x1800011b3  mov     rax, rcx
0x1800011b6  inc     rax
0x1800011b9  cmp     [rdx+rax], r9b
0x1800011bd  jnz     short loc_1800011B6
0x1800011bf  lea     r8d, [rax+1]
0x1800011c3  jmp     short loc_1800011CC
0x1800011c5  lea     rdx, word_180021D5A
0x1800011cc  mov     rax, [rbp+2Fh+arg_28]
0x1800011d0  mov     [rbp+2Fh+var_50], rax
0x1800011d4  mov     rax, [rbp+2Fh+arg_20]
0x1800011d8  mov     [rbp+2Fh+var_40], rdx
0x1800011dc  mov     [rbp+2Fh+var_38], r8d
0x1800011e0  mov     [rbp+2Fh+var_34], r9d
0x1800011e4  mov     rdx, [rax]
0x1800011e7  mov     [rbp+2Fh+var_48], 4
0x1800011ef  test    rdx, rdx
0x1800011f2  jz      short loc_180001207
0x1800011f4  inc     rcx
0x1800011f7  cmp     [rdx+rcx*2], r9w
0x1800011fc  jnz     short loc_1800011F4
0x1800011fe  lea     ecx, ds:2[rcx*2]
0x180001205  jmp     short loc_180001213
0x180001207  lea     rdx, dword_18002237C
0x18000120e  mov     ecx, 2
0x180001213  lea     rax, [rbp+2Fh+var_80]
0x180001217  mov     [rbp+2Fh+var_60], rdx
0x18000121b  mov     [rbp+2Fh+var_58], ecx
0x18000121e  xor     r8d, r8d
0x180001221  mov     [rsp+0B0h+var_88], rax
0x180001226  lea     rcx, dword_18002B0C0
0x18000122d  mov     rdx, r10
0x180001230  mov     [rsp+0B0h+var_90], 7
0x180001238  mov     [rbp+2Fh+var_54], r9d
0x18000123c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001241  mov     rcx, [rbp+2Fh+var_10]
0x180001245  xor     rcx, rsp; StackCookie
0x180001248  call    __security_check_cookie
0x18000124d  add     rsp, 0B0h
0x180001254  pop     rbp
0x180001255  retn
```
