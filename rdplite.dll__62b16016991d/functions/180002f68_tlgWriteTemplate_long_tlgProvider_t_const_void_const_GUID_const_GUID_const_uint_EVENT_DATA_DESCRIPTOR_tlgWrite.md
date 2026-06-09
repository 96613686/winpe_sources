# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180002f68`
- end: `0x180003079`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180021640`
- `0x180021b78`

## callees

- `0x180001448`
- `0x180002f68`
- `0x1800036f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        __int64 a9)
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
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-31h]
  int v23; // [rsp+58h] [rbp-29h]
  int v24; // [rsp+5Ch] [rbp-25h]
  __int64 v25; // [rsp+60h] [rbp-21h]
  __int64 v26; // [rsp+68h] [rbp-19h]
  const unsigned __int16 *v27; // [rsp+70h] [rbp-11h]
  int v28; // [rsp+78h] [rbp-9h]
  int v29; // [rsp+7Ch] [rbp-5h]
  const unsigned __int16 *v30; // [rsp+80h] [rbp-1h]
  int v31; // [rsp+88h] [rbp+7h]
  int v32; // [rsp+8Ch] [rbp+Bh]
  __int64 v33; // [rsp+90h] [rbp+Fh]
  __int64 v34; // [rsp+98h] [rbp+17h]

  v33 = a9;
  v11 = -1;
  v34 = 8;
  v12 = 1;
  v13 = *a8;
  if ( *a8 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &qword_18002D6C0;
    v15 = 1;
  }
  v31 = v15;
  v30 = v13;
  v32 = 0;
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
    v16 = &qword_18002D6C0;
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
    v19 = &qword_18002D6C0;
  }
  v22 = v19;
  v23 = v12;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 7u, &v21);
}

```

## disassembly

```asm
0x180002f68  push    rbp
0x180002f6a  lea     rbp, [rsp-2Fh]
0x180002f6f  sub     rsp, 0B0h
0x180002f76  mov     rax, cs:__security_cookie
0x180002f7d  xor     rax, rsp
0x180002f80  mov     [rbp+2Fh+var_10], rax
0x180002f84  mov     rax, [rbp+2Fh+arg_40]
0x180002f88  xor     r9d, r9d
0x180002f8b  mov     [rbp+2Fh+var_20], rax
0x180002f8f  mov     r11, rdx
0x180002f92  mov     rax, [rbp+2Fh+arg_38]
0x180002f96  mov     r10, rcx
0x180002f99  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002f9d  mov     [rbp+2Fh+var_18], 8
0x180002fa5  lea     r8d, [r9+1]
0x180002fa9  mov     rdx, [rax]
0x180002fac  test    rdx, rdx
0x180002faf  jz      short loc_180002FC1
0x180002fb1  mov     rax, rcx
0x180002fb4  inc     rax
0x180002fb7  cmp     [rdx+rax], r9b
0x180002fbb  jnz     short loc_180002FB4
0x180002fbd  inc     eax
0x180002fbf  jmp     short loc_180002FCB
0x180002fc1  lea     rdx, qword_18002D6C0
0x180002fc8  mov     eax, r8d
0x180002fcb  mov     [rbp+2Fh+var_28], eax
0x180002fce  mov     rax, [rbp+2Fh+arg_30]
0x180002fd2  mov     [rbp+2Fh+var_30], rdx
0x180002fd6  mov     [rbp+2Fh+var_24], r9d
0x180002fda  mov     rdx, [rax]
0x180002fdd  test    rdx, rdx
0x180002fe0  jz      short loc_180002FF2
0x180002fe2  mov     rax, rcx
0x180002fe5  inc     rax
0x180002fe8  cmp     [rdx+rax], r9b
0x180002fec  jnz     short loc_180002FE5
0x180002fee  inc     eax
0x180002ff0  jmp     short loc_180002FFC
0x180002ff2  lea     rdx, qword_18002D6C0
0x180002ff9  mov     eax, r8d
0x180002ffc  mov     [rbp+2Fh+var_38], eax
0x180002fff  mov     rax, [rbp+2Fh+arg_28]
0x180003003  mov     [rbp+2Fh+var_50], rax
0x180003007  mov     rax, [rbp+2Fh+arg_20]
0x18000300b  mov     [rbp+2Fh+var_40], rdx
0x18000300f  mov     [rbp+2Fh+var_34], r9d
0x180003013  mov     [rbp+2Fh+var_48], 4
0x18000301b  mov     rdx, [rax]
0x18000301e  test    rdx, rdx
0x180003021  jz      short loc_180003032
0x180003023  inc     rcx
0x180003026  cmp     [rdx+rcx], r9b
0x18000302a  jnz     short loc_180003023
0x18000302c  lea     r8d, [rcx+1]
0x180003030  jmp     short loc_180003039
0x180003032  lea     rdx, qword_18002D6C0
0x180003039  lea     rax, [rbp+2Fh+var_80]
0x18000303d  mov     [rbp+2Fh+var_60], rdx
0x180003041  mov     [rbp+2Fh+var_58], r8d
0x180003045  mov     rdx, r11
0x180003048  mov     [rsp+0B0h+var_88], rax
0x18000304d  xor     r8d, r8d
0x180003050  mov     rcx, r10
0x180003053  mov     [rsp+0B0h+var_90], 7
0x18000305b  mov     [rbp+2Fh+var_54], r9d
0x18000305f  call    _tlgWriteTransfer_EventWriteTransfer
0x180003064  mov     rcx, [rbp+2Fh+var_10]
0x180003068  xor     rcx, rsp; StackCookie
0x18000306b  call    __security_check_cookie
0x180003070  add     rsp, 0B0h
0x180003077  pop     rbp
0x180003078  retn
```
