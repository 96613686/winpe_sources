# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000125c`
- end: `0x180001386`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@544@Z`
- size: `298`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ef62`

## callees

- `0x18000125c`
- `0x1800013c8`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v11; // rcx
  int v12; // r8d
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  const unsigned __int16 *v18; // rdx
  int v19; // ecx
  _BYTE v21[32]; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-49h]
  int v23; // [rsp+58h] [rbp-41h]
  int v24; // [rsp+5Ch] [rbp-3Dh]
  __int64 v25; // [rsp+60h] [rbp-39h]
  __int64 v26; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v27; // [rsp+70h] [rbp-29h]
  int v28; // [rsp+78h] [rbp-21h]
  int v29; // [rsp+7Ch] [rbp-1Dh]
  const unsigned __int16 *v30; // [rsp+80h] [rbp-19h]
  int v31; // [rsp+88h] [rbp-11h]
  int v32; // [rsp+8Ch] [rbp-Dh]
  __int64 v33; // [rsp+90h] [rbp-9h]
  __int64 v34; // [rsp+98h] [rbp-1h]
  __int64 v35; // [rsp+A0h] [rbp+7h]
  __int64 v36; // [rsp+A8h] [rbp+Fh]

  v35 = a10;
  v11 = -1;
  v33 = a9;
  v12 = 1;
  v36 = 4;
  v34 = 4;
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
    v13 = &word_180021D5A;
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
    v12 = v17 + 1;
  }
  else
  {
    v16 = &word_180021D5A;
  }
  v25 = a6;
  v27 = v16;
  v28 = v12;
  v29 = 0;
  v18 = *a5;
  v26 = 4;
  if ( v18 )
  {
    do
      ++v11;
    while ( v18[v11] );
    v19 = 2 * v11 + 2;
  }
  else
  {
    v18 = &dword_18002237C;
    v19 = 2;
  }
  v22 = v18;
  v23 = v19;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, a2, 0, 0, 8, v21);
}

```

## disassembly

```asm
0x18000125c  push    rbp
0x18000125e  lea     rbp, [rsp-27h]
0x180001263  sub     rsp, 0C0h
0x18000126a  mov     rax, cs:__security_cookie
0x180001271  xor     rax, rsp
0x180001274  mov     [rbp+27h+var_10], rax
0x180001278  mov     rax, [rbp+27h+arg_48]
0x18000127c  xor     r9d, r9d
0x18000127f  mov     [rbp+27h+var_20], rax
0x180001283  mov     r10, rdx
0x180001286  mov     rax, [rbp+27h+arg_40]
0x18000128a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000128e  mov     [rbp+27h+var_30], rax
0x180001292  mov     rax, [rbp+27h+arg_38]
0x180001296  lea     r8d, [r9+1]
0x18000129a  mov     [rbp+27h+var_18], 4
0x1800012a2  mov     [rbp+27h+var_28], 4
0x1800012aa  mov     rdx, [rax]
0x1800012ad  test    rdx, rdx
0x1800012b0  jz      short loc_1800012C2
0x1800012b2  mov     rax, rcx
0x1800012b5  inc     rax
0x1800012b8  cmp     [rdx+rax], r9b
0x1800012bc  jnz     short loc_1800012B5
0x1800012be  inc     eax
0x1800012c0  jmp     short loc_1800012CC
0x1800012c2  lea     rdx, word_180021D5A
0x1800012c9  mov     eax, r8d
0x1800012cc  mov     [rbp+27h+var_38], eax
0x1800012cf  mov     rax, [rbp+27h+arg_30]
0x1800012d3  mov     [rbp+27h+var_40], rdx
0x1800012d7  mov     [rbp+27h+var_34], r9d
0x1800012db  mov     rdx, [rax]
0x1800012de  test    rdx, rdx
0x1800012e1  jz      short loc_1800012F5
0x1800012e3  mov     rax, rcx
0x1800012e6  inc     rax
0x1800012e9  cmp     [rdx+rax], r9b
0x1800012ed  jnz     short loc_1800012E6
0x1800012ef  lea     r8d, [rax+1]
0x1800012f3  jmp     short loc_1800012FC
0x1800012f5  lea     rdx, word_180021D5A
0x1800012fc  mov     rax, [rbp+27h+arg_28]
0x180001300  mov     [rbp+27h+var_60], rax
0x180001304  mov     rax, [rbp+27h+arg_20]
0x180001308  mov     [rbp+27h+var_50], rdx
0x18000130c  mov     [rbp+27h+var_48], r8d
0x180001310  mov     [rbp+27h+var_44], r9d
0x180001314  mov     rdx, [rax]
0x180001317  mov     [rbp+27h+var_58], 4
0x18000131f  test    rdx, rdx
0x180001322  jz      short loc_180001337
0x180001324  inc     rcx
0x180001327  cmp     [rdx+rcx*2], r9w
0x18000132c  jnz     short loc_180001324
0x18000132e  lea     ecx, ds:2[rcx*2]
0x180001335  jmp     short loc_180001343
0x180001337  lea     rdx, dword_18002237C
0x18000133e  mov     ecx, 2
0x180001343  lea     rax, [rbp+27h+var_90]
0x180001347  mov     [rbp+27h+var_70], rdx
0x18000134b  mov     [rbp+27h+var_68], ecx
0x18000134e  xor     r8d, r8d
0x180001351  mov     [rsp+0C0h+var_98], rax
0x180001356  lea     rcx, dword_18002B0C0
0x18000135d  mov     rdx, r10
0x180001360  mov     [rsp+0C0h+var_A0], 8
0x180001368  mov     [rbp+27h+var_64], r9d
0x18000136c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001371  mov     rcx, [rbp+27h+var_10]
0x180001375  xor     rcx, rsp; StackCookie
0x180001378  call    __security_check_cookie
0x18000137d  add     rsp, 0C0h
0x180001384  pop     rbp
0x180001385  retn
```
