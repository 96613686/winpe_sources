# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)

- ea: `0x18000208c`
- end: `0x18000218f`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z`
- size: `259`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180014570`
- `0x180017808`
- `0x18001b698`
- `0x18001bb08`
- `0x1800205d4`
- `0x180021640`
- `0x180021b78`

## callees

- `0x180001448`
- `0x18000208c`
- `0x1800036f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8)
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
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-19h]
  int v22; // [rsp+58h] [rbp-11h]
  int v23; // [rsp+5Ch] [rbp-Dh]
  __int64 v24; // [rsp+60h] [rbp-9h]
  __int64 v25; // [rsp+68h] [rbp-1h]
  const unsigned __int16 *v26; // [rsp+70h] [rbp+7h]
  int v27; // [rsp+78h] [rbp+Fh]
  int v28; // [rsp+7Ch] [rbp+13h]
  const unsigned __int16 *v29; // [rsp+80h] [rbp+17h]
  int v30; // [rsp+88h] [rbp+1Fh]
  int v31; // [rsp+8Ch] [rbp+23h]

  v10 = -1;
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
    v12 = &qword_18002D6C0;
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
    v17 = v16 + 1;
  }
  else
  {
    v15 = &qword_18002D6C0;
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
    while ( *((_BYTE *)v18 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v18 = &qword_18002D6C0;
  }
  v21 = v18;
  v22 = v11;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 6u, &v20);
}

```

## disassembly

```asm
0x18000208c  push    rbp
0x18000208e  lea     rbp, [rsp-37h]
0x180002093  sub     rsp, 0A0h
0x18000209a  mov     rax, cs:__security_cookie
0x1800020a1  xor     rax, rsp
0x1800020a4  mov     [rbp+37h+var_10], rax
0x1800020a8  mov     rax, [rbp+37h+arg_38]
0x1800020ac  mov     r11, rdx
0x1800020af  mov     r10, rcx
0x1800020b2  xor     r9d, r9d
0x1800020b5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800020b9  mov     r8d, 1
0x1800020bf  mov     rdx, [rax]
0x1800020c2  test    rdx, rdx
0x1800020c5  jz      short loc_1800020D7
0x1800020c7  mov     rax, rcx
0x1800020ca  inc     rax
0x1800020cd  cmp     [rdx+rax], r9b
0x1800020d1  jnz     short loc_1800020CA
0x1800020d3  inc     eax
0x1800020d5  jmp     short loc_1800020E1
0x1800020d7  lea     rdx, qword_18002D6C0
0x1800020de  mov     eax, r8d
0x1800020e1  mov     [rbp+37h+var_18], eax
0x1800020e4  mov     rax, [rbp+37h+arg_30]
0x1800020e8  mov     [rbp+37h+var_20], rdx
0x1800020ec  mov     [rbp+37h+var_14], r9d
0x1800020f0  mov     rdx, [rax]
0x1800020f3  test    rdx, rdx
0x1800020f6  jz      short loc_180002108
0x1800020f8  mov     rax, rcx
0x1800020fb  inc     rax
0x1800020fe  cmp     [rdx+rax], r9b
0x180002102  jnz     short loc_1800020FB
0x180002104  inc     eax
0x180002106  jmp     short loc_180002112
0x180002108  lea     rdx, qword_18002D6C0
0x18000210f  mov     eax, r8d
0x180002112  mov     [rbp+37h+var_28], eax
0x180002115  mov     rax, [rbp+37h+arg_28]
0x180002119  mov     [rbp+37h+var_40], rax
0x18000211d  mov     rax, [rbp+37h+arg_20]
0x180002121  mov     [rbp+37h+var_30], rdx
0x180002125  mov     [rbp+37h+var_24], r9d
0x180002129  mov     [rbp+37h+var_38], 4
0x180002131  mov     rdx, [rax]
0x180002134  test    rdx, rdx
0x180002137  jz      short loc_180002148
0x180002139  inc     rcx
0x18000213c  cmp     [rdx+rcx], r9b
0x180002140  jnz     short loc_180002139
0x180002142  lea     r8d, [rcx+1]
0x180002146  jmp     short loc_18000214F
0x180002148  lea     rdx, qword_18002D6C0
0x18000214f  lea     rax, [rbp+37h+var_70]
0x180002153  mov     [rbp+37h+var_50], rdx
0x180002157  mov     [rbp+37h+var_48], r8d
0x18000215b  mov     rdx, r11
0x18000215e  mov     [rsp+0A0h+var_78], rax
0x180002163  xor     r8d, r8d
0x180002166  mov     rcx, r10
0x180002169  mov     [rsp+0A0h+var_80], 6
0x180002171  mov     [rbp+37h+var_44], r9d
0x180002175  call    _tlgWriteTransfer_EventWriteTransfer
0x18000217a  mov     rcx, [rbp+37h+var_10]
0x18000217e  xor     rcx, rsp; StackCookie
0x180002181  call    __security_check_cookie
0x180002186  add     rsp, 0A0h
0x18000218d  pop     rbp
0x18000218e  retn
```
