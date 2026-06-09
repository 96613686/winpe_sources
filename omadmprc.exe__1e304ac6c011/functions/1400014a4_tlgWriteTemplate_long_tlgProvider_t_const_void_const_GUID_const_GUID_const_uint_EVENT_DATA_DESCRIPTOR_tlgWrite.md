# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400014a4`
- end: `0x1400015d3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapSz@D@@@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bbbc`

## callees

- `0x140001090`
- `0x1400014a4`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 **a6,
        __int64 **a7,
        __int64 a8,
        __int64 a9,
        const unsigned __int16 **a10)
{
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  int v15; // r8d
  __int64 *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  __int64 *v19; // rdx
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-69h] BYREF
  __int64 v22; // [rsp+50h] [rbp-49h]
  __int64 v23; // [rsp+58h] [rbp-41h]
  __int64 *v24; // [rsp+60h] [rbp-39h]
  int v25; // [rsp+68h] [rbp-31h]
  int v26; // [rsp+6Ch] [rbp-2Dh]
  __int64 *v27; // [rsp+70h] [rbp-29h]
  int v28; // [rsp+78h] [rbp-21h]
  int v29; // [rsp+7Ch] [rbp-1Dh]
  __int64 v30; // [rsp+80h] [rbp-19h]
  __int64 v31; // [rsp+88h] [rbp-11h]
  __int64 v32; // [rsp+90h] [rbp-9h]
  __int64 v33; // [rsp+98h] [rbp-1h]
  const unsigned __int16 *v34; // [rsp+A0h] [rbp+7h]
  int v35; // [rsp+A8h] [rbp+Fh]
  int v36; // [rsp+ACh] [rbp+13h]

  v11 = -1;
  v12 = *a10;
  if ( *a10 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &qword_14001A560;
    v14 = 1;
  }
  v35 = v14;
  v15 = 2;
  v32 = a9;
  v30 = a8;
  v34 = v12;
  v36 = 0;
  v33 = 4;
  v16 = *a7;
  v31 = 4;
  if ( v16 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v16 + v17) );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v16 = &qword_14001A798;
    v18 = 2;
  }
  v28 = v18;
  v27 = v16;
  v29 = 0;
  v19 = *a6;
  if ( *a6 )
  {
    do
      ++v11;
    while ( *((_WORD *)v19 + v11) );
    v15 = 2 * v11 + 2;
  }
  else
  {
    v19 = &qword_14001A798;
  }
  v22 = a5;
  v24 = v19;
  v25 = v15;
  v23 = 8;
  v26 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, a2, 0, 0, 8u, &v21);
}

```

## disassembly

```asm
0x1400014a4  push    rbp
0x1400014a6  lea     rbp, [rsp-27h]
0x1400014ab  sub     rsp, 0C0h
0x1400014b2  mov     rax, cs:__security_cookie
0x1400014b9  xor     rax, rsp
0x1400014bc  mov     [rbp+27h+var_10], rax
0x1400014c0  mov     rax, [rbp+27h+arg_48]
0x1400014c4  mov     r10, rdx
0x1400014c7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400014cb  xor     r9d, r9d
0x1400014ce  mov     rdx, [rax]
0x1400014d1  test    rdx, rdx
0x1400014d4  jz      short loc_1400014E6
0x1400014d6  mov     rax, rcx
0x1400014d9  inc     rax
0x1400014dc  cmp     [rdx+rax], r9b
0x1400014e0  jnz     short loc_1400014D9
0x1400014e2  inc     eax
0x1400014e4  jmp     short loc_1400014F2
0x1400014e6  lea     rdx, qword_14001A560
0x1400014ed  mov     eax, 1
0x1400014f2  mov     [rbp+27h+var_18], eax
0x1400014f5  mov     r8d, 2
0x1400014fb  mov     rax, [rbp+27h+arg_40]
0x1400014ff  mov     [rbp+27h+var_30], rax
0x140001503  mov     rax, [rbp+27h+arg_38]
0x140001507  mov     [rbp+27h+var_40], rax
0x14000150b  mov     rax, [rbp+27h+arg_30]
0x14000150f  mov     [rbp+27h+var_20], rdx
0x140001513  mov     [rbp+27h+var_14], r9d
0x140001517  mov     [rbp+27h+var_28], 4
0x14000151f  mov     rdx, [rax]
0x140001522  mov     [rbp+27h+var_38], 4
0x14000152a  test    rdx, rdx
0x14000152d  jz      short loc_140001545
0x14000152f  mov     rax, rcx
0x140001532  inc     rax
0x140001535  cmp     [rdx+rax*2], r9w
0x14000153a  jnz     short loc_140001532
0x14000153c  lea     eax, ds:2[rax*2]
0x140001543  jmp     short loc_14000154F
0x140001545  lea     rdx, qword_14001A798
0x14000154c  mov     eax, r8d
0x14000154f  mov     [rbp+27h+var_48], eax
0x140001552  mov     rax, [rbp+27h+arg_28]
0x140001556  mov     [rbp+27h+var_50], rdx
0x14000155a  mov     [rbp+27h+var_44], r9d
0x14000155e  mov     rdx, [rax]
0x140001561  test    rdx, rdx
0x140001564  jz      short loc_14000157A
0x140001566  inc     rcx
0x140001569  cmp     [rdx+rcx*2], r9w
0x14000156e  jnz     short loc_140001566
0x140001570  lea     r8d, ds:2[rcx*2]
0x140001578  jmp     short loc_140001581
0x14000157a  lea     rdx, qword_14001A798
0x140001581  mov     rax, [rbp+27h+arg_20]
0x140001585  mov     ecx, 8
0x14000158a  mov     [rbp+27h+var_70], rax
0x14000158e  lea     rax, [rbp+27h+var_90]
0x140001592  mov     [rsp+0C0h+var_98], rax
0x140001597  mov     [rsp+0C0h+var_A0], ecx
0x14000159b  mov     [rbp+27h+var_60], rdx
0x14000159f  mov     rdx, r10
0x1400015a2  mov     [rbp+27h+var_58], r8d
0x1400015a6  xor     r8d, r8d
0x1400015a9  mov     [rbp+27h+var_68], rcx
0x1400015ad  lea     rcx, dword_140023000
0x1400015b4  mov     [rbp+27h+var_54], r9d
0x1400015b8  call    _tlgWriteTransfer_EventWriteTransfer
0x1400015bd  mov     rcx, [rbp+27h+var_10]
0x1400015c1  xor     rcx, rsp; StackCookie
0x1400015c4  call    __security_check_cookie
0x1400015c9  add     rsp, 0C0h
0x1400015d0  pop     rbp
0x1400015d1  retn
```
