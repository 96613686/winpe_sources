# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800019e4`
- end: `0x180001b03`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@34@Z`
- size: `287`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f5c4`

## callees

- `0x1800013c8`
- `0x1800019e4`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
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
  int v17; // eax
  const unsigned __int16 *v18; // rdx
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
  v11 = 2;
  v12 = *a8;
  if ( *a8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &dword_18002237C;
    v14 = 2;
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
    v17 = v16 + 1;
  }
  else
  {
    v15 = &word_180021D5A;
    v17 = 1;
  }
  v27 = v17;
  v24 = a6;
  v26 = v15;
  v28 = 0;
  v25 = 4;
  v18 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( v18[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v18 = &dword_18002237C;
  }
  v21 = v18;
  v22 = v11;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, a2, 0, 0, 7, v20);
}

```

## disassembly

```asm
0x1800019e4  push    rbp
0x1800019e6  lea     rbp, [rsp-2Fh]
0x1800019eb  sub     rsp, 0B0h
0x1800019f2  mov     rax, cs:__security_cookie
0x1800019f9  xor     rax, rsp
0x1800019fc  mov     [rbp+2Fh+var_10], rax
0x180001a00  mov     rax, [rbp+2Fh+arg_40]
0x180001a04  xor     r9d, r9d
0x180001a07  mov     [rbp+2Fh+var_20], rax
0x180001a0b  mov     r10, rdx
0x180001a0e  mov     rax, [rbp+2Fh+arg_38]
0x180001a12  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001a16  mov     [rbp+2Fh+var_18], 4
0x180001a1e  lea     r8d, [r9+2]
0x180001a22  mov     rdx, [rax]
0x180001a25  test    rdx, rdx
0x180001a28  jz      short loc_180001A40
0x180001a2a  mov     rax, rcx
0x180001a2d  inc     rax
0x180001a30  cmp     [rdx+rax*2], r9w
0x180001a35  jnz     short loc_180001A2D
0x180001a37  lea     eax, ds:2[rax*2]
0x180001a3e  jmp     short loc_180001A4A
0x180001a40  lea     rdx, dword_18002237C
0x180001a47  mov     eax, r8d
0x180001a4a  mov     [rbp+2Fh+var_28], eax
0x180001a4d  mov     rax, [rbp+2Fh+arg_30]
0x180001a51  mov     [rbp+2Fh+var_30], rdx
0x180001a55  mov     [rbp+2Fh+var_24], r9d
0x180001a59  mov     rdx, [rax]
0x180001a5c  test    rdx, rdx
0x180001a5f  jz      short loc_180001A71
0x180001a61  mov     rax, rcx
0x180001a64  inc     rax
0x180001a67  cmp     [rdx+rax], r9b
0x180001a6b  jnz     short loc_180001A64
0x180001a6d  inc     eax
0x180001a6f  jmp     short loc_180001A7D
0x180001a71  lea     rdx, word_180021D5A
0x180001a78  mov     eax, 1
0x180001a7d  mov     [rbp+2Fh+var_38], eax
0x180001a80  mov     rax, [rbp+2Fh+arg_28]
0x180001a84  mov     [rbp+2Fh+var_50], rax
0x180001a88  mov     rax, [rbp+2Fh+arg_20]
0x180001a8c  mov     [rbp+2Fh+var_40], rdx
0x180001a90  mov     [rbp+2Fh+var_34], r9d
0x180001a94  mov     [rbp+2Fh+var_48], 4
0x180001a9c  mov     rdx, [rax]
0x180001a9f  test    rdx, rdx
0x180001aa2  jz      short loc_180001AB8
0x180001aa4  inc     rcx
0x180001aa7  cmp     [rdx+rcx*2], r9w
0x180001aac  jnz     short loc_180001AA4
0x180001aae  lea     r8d, ds:2[rcx*2]
0x180001ab6  jmp     short loc_180001ABF
0x180001ab8  lea     rdx, dword_18002237C
0x180001abf  lea     rax, [rbp+2Fh+var_80]
0x180001ac3  mov     [rbp+2Fh+var_60], rdx
0x180001ac7  mov     [rbp+2Fh+var_58], r8d
0x180001acb  lea     rcx, dword_18002B0C0
0x180001ad2  mov     [rsp+0B0h+var_88], rax
0x180001ad7  xor     r8d, r8d
0x180001ada  mov     rdx, r10
0x180001add  mov     [rsp+0B0h+var_90], 7
0x180001ae5  mov     [rbp+2Fh+var_54], r9d
0x180001ae9  call    _tlgWriteTransfer_EventWriteTransfer
0x180001aee  mov     rcx, [rbp+2Fh+var_10]
0x180001af2  xor     rcx, rsp; StackCookie
0x180001af5  call    __security_check_cookie
0x180001afa  add     rsp, 0B0h
0x180001b01  pop     rbp
0x180001b02  retn
```
