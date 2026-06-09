# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400016e8`
- end: `0x1400017e0`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapSz@D@@@Z`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000baec`

## callees

- `0x140001090`
- `0x1400016e8`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 **a6,
        __int64 a7,
        __int64 a8,
        const unsigned __int16 **a9)
{
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rdx
  int v15; // ecx
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+30h] [rbp-51h] BYREF
  __int64 v18; // [rsp+50h] [rbp-31h]
  __int64 v19; // [rsp+58h] [rbp-29h]
  __int64 *v20; // [rsp+60h] [rbp-21h]
  int v21; // [rsp+68h] [rbp-19h]
  int v22; // [rsp+6Ch] [rbp-15h]
  __int64 v23; // [rsp+70h] [rbp-11h]
  __int64 v24; // [rsp+78h] [rbp-9h]
  __int64 v25; // [rsp+80h] [rbp-1h]
  __int64 v26; // [rsp+88h] [rbp+7h]
  const unsigned __int16 *v27; // [rsp+90h] [rbp+Fh]
  int v28; // [rsp+98h] [rbp+17h]
  int v29; // [rsp+9Ch] [rbp+1Bh]

  v10 = -1;
  v11 = *a9;
  if ( *a9 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &qword_14001A560;
    v13 = 1;
  }
  v28 = v13;
  v25 = a8;
  v23 = a7;
  v27 = v11;
  v29 = 0;
  v26 = 4;
  v14 = *a6;
  v24 = 4;
  if ( v14 )
  {
    do
      ++v10;
    while ( *((_WORD *)v14 + v10) );
    v15 = 2 * v10 + 2;
  }
  else
  {
    v14 = &qword_14001A798;
    v15 = 2;
  }
  v18 = a5;
  v20 = v14;
  v21 = v15;
  v22 = 0;
  v19 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, a2, 0, 0, 7u, &v17);
}

```

## disassembly

```asm
0x1400016e8  push    rbp
0x1400016ea  lea     rbp, [rsp-2Fh]
0x1400016ef  sub     rsp, 0B0h
0x1400016f6  mov     rax, cs:__security_cookie
0x1400016fd  xor     rax, rsp
0x140001700  mov     [rbp+2Fh+var_10], rax
0x140001704  mov     rax, [rbp+2Fh+arg_40]
0x140001708  mov     r10, rdx
0x14000170b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000170f  xor     r8d, r8d
0x140001712  mov     rdx, [rax]
0x140001715  test    rdx, rdx
0x140001718  jz      short loc_14000172A
0x14000171a  mov     rax, rcx
0x14000171d  inc     rax
0x140001720  cmp     [rdx+rax], r8b
0x140001724  jnz     short loc_14000171D
0x140001726  inc     eax
0x140001728  jmp     short loc_140001736
0x14000172a  lea     rdx, qword_14001A560
0x140001731  mov     eax, 1
0x140001736  mov     [rbp+2Fh+var_18], eax
0x140001739  mov     rax, [rbp+2Fh+arg_38]
0x14000173d  mov     [rbp+2Fh+var_30], rax
0x140001741  mov     rax, [rbp+2Fh+arg_30]
0x140001745  mov     [rbp+2Fh+var_40], rax
0x140001749  mov     rax, [rbp+2Fh+arg_28]
0x14000174d  mov     [rbp+2Fh+var_20], rdx
0x140001751  mov     [rbp+2Fh+var_14], r8d
0x140001755  mov     [rbp+2Fh+var_28], 4
0x14000175d  mov     rdx, [rax]
0x140001760  mov     [rbp+2Fh+var_38], 4
0x140001768  test    rdx, rdx
0x14000176b  jz      short loc_140001780
0x14000176d  inc     rcx
0x140001770  cmp     [rdx+rcx*2], r8w
0x140001775  jnz     short loc_14000176D
0x140001777  lea     ecx, ds:2[rcx*2]
0x14000177e  jmp     short loc_14000178C
0x140001780  lea     rdx, qword_14001A798
0x140001787  mov     ecx, 2
0x14000178c  mov     rax, [rbp+2Fh+arg_20]
0x140001790  xor     r9d, r9d
0x140001793  mov     [rbp+2Fh+var_60], rax
0x140001797  lea     rax, [rbp+2Fh+var_80]
0x14000179b  mov     [rbp+2Fh+var_50], rdx
0x14000179f  mov     rdx, r10
0x1400017a2  mov     [rbp+2Fh+var_48], ecx
0x1400017a5  lea     rcx, dword_140023000
0x1400017ac  mov     [rsp+0B0h+var_88], rax
0x1400017b1  mov     [rsp+0B0h+var_90], 7
0x1400017b9  mov     [rbp+2Fh+var_44], r8d
0x1400017bd  mov     [rbp+2Fh+var_58], 8
0x1400017c5  call    _tlgWriteTransfer_EventWriteTransfer
0x1400017ca  mov     rcx, [rbp+2Fh+var_10]
0x1400017ce  xor     rcx, rsp; StackCookie
0x1400017d1  call    __security_check_cookie
0x1400017d6  add     rsp, 0B0h
0x1400017dd  pop     rbp
0x1400017de  retn
```
