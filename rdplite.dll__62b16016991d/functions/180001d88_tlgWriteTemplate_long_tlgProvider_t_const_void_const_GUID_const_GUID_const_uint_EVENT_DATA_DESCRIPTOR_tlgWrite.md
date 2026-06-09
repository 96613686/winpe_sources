# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001d88`
- end: `0x180001ec4`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@@Z`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010cbc`
- `0x180011048`

## callees

- `0x180001448`
- `0x180001d88`
- `0x1800036f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        __int64 **a9)
{
  __int64 v11; // rcx
  __int64 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  int v15; // r8d
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v25; // [rsp+50h] [rbp-31h]
  int v26; // [rsp+58h] [rbp-29h]
  int v27; // [rsp+5Ch] [rbp-25h]
  __int64 v28; // [rsp+60h] [rbp-21h]
  __int64 v29; // [rsp+68h] [rbp-19h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-11h]
  int v31; // [rsp+78h] [rbp-9h]
  int v32; // [rsp+7Ch] [rbp-5h]
  const unsigned __int16 *v33; // [rsp+80h] [rbp-1h]
  int v34; // [rsp+88h] [rbp+7h]
  int v35; // [rsp+8Ch] [rbp+Bh]
  __int64 *v36; // [rsp+90h] [rbp+Fh]
  int v37; // [rsp+98h] [rbp+17h]
  int v38; // [rsp+9Ch] [rbp+1Bh]

  v11 = -1;
  v12 = *a9;
  if ( *a9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &qword_18002E230;
    v14 = 2;
  }
  v37 = v14;
  v15 = 1;
  v36 = v12;
  v38 = 0;
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
    v16 = &qword_18002D6C0;
    v18 = 1;
  }
  v34 = v18;
  v33 = v16;
  v35 = 0;
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
    v19 = &qword_18002D6C0;
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
    v15 = v11 + 1;
  }
  else
  {
    v22 = &qword_18002D6C0;
  }
  v25 = v22;
  v26 = v15;
  v27 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 7u, &v24);
}

```

## disassembly

```asm
0x180001d88  push    rbp
0x180001d8a  lea     rbp, [rsp-2Fh]
0x180001d8f  sub     rsp, 0B0h
0x180001d96  mov     rax, cs:__security_cookie
0x180001d9d  xor     rax, rsp
0x180001da0  mov     [rbp+2Fh+var_10], rax
0x180001da4  mov     rax, [rbp+2Fh+arg_40]
0x180001da8  mov     r11, rdx
0x180001dab  mov     r10, rcx
0x180001dae  xor     r9d, r9d
0x180001db1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001db5  mov     rdx, [rax]
0x180001db8  test    rdx, rdx
0x180001dbb  jz      short loc_180001DD3
0x180001dbd  mov     rax, rcx
0x180001dc0  inc     rax
0x180001dc3  cmp     [rdx+rax*2], r9w
0x180001dc8  jnz     short loc_180001DC0
0x180001dca  lea     eax, ds:2[rax*2]
0x180001dd1  jmp     short loc_180001DDF
0x180001dd3  lea     rdx, qword_18002E230
0x180001dda  mov     eax, 2
0x180001ddf  mov     [rbp+2Fh+var_18], eax
0x180001de2  mov     r8d, 1
0x180001de8  mov     rax, [rbp+2Fh+arg_38]
0x180001dec  mov     [rbp+2Fh+var_20], rdx
0x180001df0  mov     [rbp+2Fh+var_14], r9d
0x180001df4  mov     rdx, [rax]
0x180001df7  test    rdx, rdx
0x180001dfa  jz      short loc_180001E0C
0x180001dfc  mov     rax, rcx
0x180001dff  inc     rax
0x180001e02  cmp     [rdx+rax], r9b
0x180001e06  jnz     short loc_180001DFF
0x180001e08  inc     eax
0x180001e0a  jmp     short loc_180001E16
0x180001e0c  lea     rdx, qword_18002D6C0
0x180001e13  mov     eax, r8d
0x180001e16  mov     [rbp+2Fh+var_28], eax
0x180001e19  mov     rax, [rbp+2Fh+arg_30]
0x180001e1d  mov     [rbp+2Fh+var_30], rdx
0x180001e21  mov     [rbp+2Fh+var_24], r9d
0x180001e25  mov     rdx, [rax]
0x180001e28  test    rdx, rdx
0x180001e2b  jz      short loc_180001E3D
0x180001e2d  mov     rax, rcx
0x180001e30  inc     rax
0x180001e33  cmp     [rdx+rax], r9b
0x180001e37  jnz     short loc_180001E30
0x180001e39  inc     eax
0x180001e3b  jmp     short loc_180001E47
0x180001e3d  lea     rdx, qword_18002D6C0
0x180001e44  mov     eax, r8d
0x180001e47  mov     [rbp+2Fh+var_38], eax
0x180001e4a  mov     rax, [rbp+2Fh+arg_28]
0x180001e4e  mov     [rbp+2Fh+var_50], rax
0x180001e52  mov     rax, [rbp+2Fh+arg_20]
0x180001e56  mov     [rbp+2Fh+var_40], rdx
0x180001e5a  mov     [rbp+2Fh+var_34], r9d
0x180001e5e  mov     [rbp+2Fh+var_48], 4
0x180001e66  mov     rdx, [rax]
0x180001e69  test    rdx, rdx
0x180001e6c  jz      short loc_180001E7D
0x180001e6e  inc     rcx
0x180001e71  cmp     [rdx+rcx], r9b
0x180001e75  jnz     short loc_180001E6E
0x180001e77  lea     r8d, [rcx+1]
0x180001e7b  jmp     short loc_180001E84
0x180001e7d  lea     rdx, qword_18002D6C0
0x180001e84  lea     rax, [rbp+2Fh+var_80]
0x180001e88  mov     [rbp+2Fh+var_60], rdx
0x180001e8c  mov     [rbp+2Fh+var_58], r8d
0x180001e90  mov     rdx, r11
0x180001e93  mov     [rsp+0B0h+var_88], rax
0x180001e98  xor     r8d, r8d
0x180001e9b  mov     rcx, r10
0x180001e9e  mov     [rsp+0B0h+var_90], 7
0x180001ea6  mov     [rbp+2Fh+var_54], r9d
0x180001eaa  call    _tlgWriteTransfer_EventWriteTransfer
0x180001eaf  mov     rcx, [rbp+2Fh+var_10]
0x180001eb3  xor     rcx, rsp; StackCookie
0x180001eb6  call    __security_check_cookie
0x180001ebb  add     rsp, 0B0h
0x180001ec2  pop     rbp
0x180001ec3  retn
```
