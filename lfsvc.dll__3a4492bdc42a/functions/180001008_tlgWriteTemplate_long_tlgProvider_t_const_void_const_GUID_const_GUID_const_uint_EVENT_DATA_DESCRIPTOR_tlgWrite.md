# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x180001152`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@553@Z`
- size: `330`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, char **, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007990`

## callees

- `0x180001008`
- `0x1800012f0`
- `0x180004310`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char **a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        const unsigned __int16 **a9,
        __int64 a10)
{
  __int64 v12; // rdx
  int v13; // r8d
  const unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rcx
  __int64 v21; // rax
  char *v22; // rcx
  int v23; // edx
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+30h] [rbp-69h] BYREF
  __int64 v26; // [rsp+50h] [rbp-49h]
  __int64 v27; // [rsp+58h] [rbp-41h]
  char *v28; // [rsp+60h] [rbp-39h]
  int v29; // [rsp+68h] [rbp-31h]
  int v30; // [rsp+6Ch] [rbp-2Dh]
  const unsigned __int16 *v31; // [rsp+70h] [rbp-29h]
  int v32; // [rsp+78h] [rbp-21h]
  int v33; // [rsp+7Ch] [rbp-1Dh]
  const unsigned __int16 *v34; // [rsp+80h] [rbp-19h]
  int v35; // [rsp+88h] [rbp-11h]
  int v36; // [rsp+8Ch] [rbp-Dh]
  const unsigned __int16 *v37; // [rsp+90h] [rbp-9h]
  int v38; // [rsp+98h] [rbp-1h]
  int v39; // [rsp+9Ch] [rbp+3h]
  __int64 v40; // [rsp+A0h] [rbp+7h]
  __int64 v41; // [rsp+A8h] [rbp+Fh]

  v40 = a10;
  v12 = -1;
  v41 = 4;
  v13 = 1;
  v14 = *a9;
  if ( *a9 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v14 = &word_18000DA02;
    v16 = 1;
  }
  v38 = v16;
  v37 = v14;
  v39 = 0;
  v17 = *a8;
  if ( *a8 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)v17 + v18) );
    v19 = v18 + 1;
  }
  else
  {
    v17 = &word_18000DA02;
    v19 = 1;
  }
  v35 = v19;
  v34 = v17;
  v36 = 0;
  v20 = *a7;
  if ( *a7 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_BYTE *)v20 + v21) );
    v13 = v21 + 1;
  }
  else
  {
    v20 = &word_18000DA02;
  }
  v31 = v20;
  v32 = v13;
  v33 = 0;
  v22 = *a6;
  if ( *a6 )
  {
    do
      ++v12;
    while ( *(_WORD *)&v22[2 * v12] );
    v23 = 2 * v12 + 2;
  }
  else
  {
    v22 = byte_18000DA00;
    v23 = 2;
  }
  v26 = a5;
  v28 = v22;
  v29 = v23;
  v30 = 0;
  v27 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 8u, &v25);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-27h]
0x18000100f  sub     rsp, 0C0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+27h+var_10], rax
0x180001024  mov     rax, [rbp+27h+arg_48]
0x180001028  xor     r9d, r9d; int
0x18000102b  mov     [rbp+27h+var_20], rax
0x18000102f  mov     r11, rdx
0x180001032  mov     rax, [rbp+27h+arg_40]
0x180001036  mov     r10, rcx
0x180001039  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000103d  mov     [rbp+27h+var_18], 4
0x180001045  lea     r8d, [r9+1]
0x180001049  mov     rcx, [rax]
0x18000104c  test    rcx, rcx
0x18000104f  jz      short loc_180001061
0x180001051  mov     rax, rdx
0x180001054  inc     rax
0x180001057  cmp     [rcx+rax], r9b
0x18000105b  jnz     short loc_180001054
0x18000105d  inc     eax
0x18000105f  jmp     short loc_18000106B
0x180001061  lea     rcx, word_18000DA02
0x180001068  mov     eax, r8d
0x18000106b  mov     [rbp+27h+var_28], eax
0x18000106e  mov     rax, [rbp+27h+arg_38]
0x180001072  mov     [rbp+27h+var_30], rcx
0x180001076  mov     [rbp+27h+var_24], r9d
0x18000107a  mov     rcx, [rax]
0x18000107d  test    rcx, rcx
0x180001080  jz      short loc_180001092
0x180001082  mov     rax, rdx
0x180001085  inc     rax
0x180001088  cmp     [rcx+rax], r9b
0x18000108c  jnz     short loc_180001085
0x18000108e  inc     eax
0x180001090  jmp     short loc_18000109C
0x180001092  lea     rcx, word_18000DA02
0x180001099  mov     eax, r8d
0x18000109c  mov     [rbp+27h+var_38], eax
0x18000109f  mov     rax, [rbp+27h+arg_30]
0x1800010a3  mov     [rbp+27h+var_40], rcx
0x1800010a7  mov     [rbp+27h+var_34], r9d
0x1800010ab  mov     rcx, [rax]
0x1800010ae  test    rcx, rcx
0x1800010b1  jz      short loc_1800010C5
0x1800010b3  mov     rax, rdx
0x1800010b6  inc     rax
0x1800010b9  cmp     [rcx+rax], r9b
0x1800010bd  jnz     short loc_1800010B6
0x1800010bf  lea     r8d, [rax+1]
0x1800010c3  jmp     short loc_1800010CC
0x1800010c5  lea     rcx, word_18000DA02
0x1800010cc  mov     rax, [rbp+27h+arg_28]
0x1800010d0  mov     [rbp+27h+var_50], rcx
0x1800010d4  mov     [rbp+27h+var_48], r8d
0x1800010d8  mov     [rbp+27h+var_44], r9d
0x1800010dc  mov     rcx, [rax]
0x1800010df  test    rcx, rcx
0x1800010e2  jz      short loc_1800010F7
0x1800010e4  inc     rdx
0x1800010e7  cmp     [rcx+rdx*2], r9w
0x1800010ec  jnz     short loc_1800010E4
0x1800010ee  lea     edx, ds:2[rdx*2]
0x1800010f5  jmp     short loc_180001103
0x1800010f7  lea     rcx, byte_18000DA00
0x1800010fe  mov     edx, 2
0x180001103  mov     rax, [rbp+27h+arg_20]
0x180001107  xor     r8d, r8d; int
0x18000110a  mov     [rbp+27h+var_70], rax
0x18000110e  lea     rax, [rbp+27h+var_90]
0x180001112  mov     [rbp+27h+var_60], rcx
0x180001116  mov     rcx, r10; int
0x180001119  mov     [rbp+27h+var_58], edx
0x18000111c  mov     rdx, r11; int
0x18000111f  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x180001124  mov     [rsp+0C0h+var_A0], 8; ULONG
0x18000112c  mov     [rbp+27h+var_54], r9d
0x180001130  mov     [rbp+27h+var_68], 4
0x180001138  call    _tlgWriteTransfer_EventWriteTransfer
0x18000113d  mov     rcx, [rbp+27h+var_10]
0x180001141  xor     rcx, rsp; StackCookie
0x180001144  call    __security_check_cookie
0x180001149  add     rsp, 0C0h
0x180001150  pop     rbp
0x180001151  retn
```
