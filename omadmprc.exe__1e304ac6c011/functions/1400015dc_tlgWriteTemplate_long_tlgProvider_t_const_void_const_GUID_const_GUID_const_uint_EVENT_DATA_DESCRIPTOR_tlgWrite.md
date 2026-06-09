# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400015dc`
- end: `0x1400016e1`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapSz@D@@@Z`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b774`
- `0x14000bca4`

## callees

- `0x140001090`
- `0x1400015dc`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        const unsigned __int16 **a10)
{
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // rdx
  int v16; // ecx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-69h] BYREF
  __int64 v19; // [rsp+50h] [rbp-49h]
  __int64 v20; // [rsp+58h] [rbp-41h]
  __int64 *v21; // [rsp+60h] [rbp-39h]
  int v22; // [rsp+68h] [rbp-31h]
  int v23; // [rsp+6Ch] [rbp-2Dh]
  __int64 v24; // [rsp+70h] [rbp-29h]
  __int64 v25; // [rsp+78h] [rbp-21h]
  __int64 v26; // [rsp+80h] [rbp-19h]
  __int64 v27; // [rsp+88h] [rbp-11h]
  __int64 v28; // [rsp+90h] [rbp-9h]
  __int64 v29; // [rsp+98h] [rbp-1h]
  const unsigned __int16 *v30; // [rsp+A0h] [rbp+7h]
  int v31; // [rsp+A8h] [rbp+Fh]
  int v32; // [rsp+ACh] [rbp+13h]

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
  v31 = v14;
  v28 = a9;
  v26 = a8;
  v24 = a7;
  v30 = v12;
  v32 = 0;
  v29 = 4;
  v15 = *a6;
  v27 = 4;
  v25 = 4;
  if ( v15 )
  {
    do
      ++v11;
    while ( *((_WORD *)v15 + v11) );
    v16 = 2 * v11 + 2;
  }
  else
  {
    v15 = &qword_14001A798;
    v16 = 2;
  }
  v22 = v16;
  v19 = a5;
  v21 = v15;
  v20 = 8;
  v23 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, a2, 0, 0, 8u, &v18);
}

```

## disassembly

```asm
0x1400015dc  push    rbp
0x1400015de  lea     rbp, [rsp-27h]
0x1400015e3  sub     rsp, 0C0h
0x1400015ea  mov     rax, cs:__security_cookie
0x1400015f1  xor     rax, rsp
0x1400015f4  mov     [rbp+27h+var_10], rax
0x1400015f8  mov     rax, [rbp+27h+arg_48]
0x1400015fc  mov     r10, rdx
0x1400015ff  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001603  xor     r8d, r8d
0x140001606  mov     rdx, [rax]
0x140001609  test    rdx, rdx
0x14000160c  jz      short loc_14000161E
0x14000160e  mov     rax, rcx
0x140001611  inc     rax
0x140001614  cmp     [rdx+rax], r8b
0x140001618  jnz     short loc_140001611
0x14000161a  inc     eax
0x14000161c  jmp     short loc_14000162A
0x14000161e  lea     rdx, qword_14001A560
0x140001625  mov     eax, 1
0x14000162a  mov     [rbp+27h+var_18], eax
0x14000162d  mov     rax, [rbp+27h+arg_40]
0x140001631  mov     [rbp+27h+var_30], rax
0x140001635  mov     rax, [rbp+27h+arg_38]
0x140001639  mov     [rbp+27h+var_40], rax
0x14000163d  mov     rax, [rbp+27h+arg_30]
0x140001641  mov     [rbp+27h+var_50], rax
0x140001645  mov     rax, [rbp+27h+arg_28]
0x140001649  mov     [rbp+27h+var_20], rdx
0x14000164d  mov     [rbp+27h+var_14], r8d
0x140001651  mov     [rbp+27h+var_28], 4
0x140001659  mov     rdx, [rax]
0x14000165c  mov     [rbp+27h+var_38], 4
0x140001664  mov     [rbp+27h+var_48], 4
0x14000166c  test    rdx, rdx
0x14000166f  jz      short loc_140001684
0x140001671  inc     rcx
0x140001674  cmp     [rdx+rcx*2], r8w
0x140001679  jnz     short loc_140001671
0x14000167b  lea     ecx, ds:2[rcx*2]
0x140001682  jmp     short loc_140001690
0x140001684  lea     rdx, qword_14001A798
0x14000168b  mov     ecx, 2
0x140001690  mov     rax, [rbp+27h+arg_20]
0x140001694  xor     r9d, r9d
0x140001697  mov     [rbp+27h+var_58], ecx
0x14000169a  mov     ecx, 8
0x14000169f  mov     [rbp+27h+var_70], rax
0x1400016a3  lea     rax, [rbp+27h+var_90]
0x1400016a7  mov     [rsp+0C0h+var_98], rax
0x1400016ac  mov     [rsp+0C0h+var_A0], ecx
0x1400016b0  mov     [rbp+27h+var_60], rdx
0x1400016b4  mov     rdx, r10
0x1400016b7  mov     [rbp+27h+var_68], rcx
0x1400016bb  lea     rcx, dword_140023000
0x1400016c2  mov     [rbp+27h+var_54], r8d
0x1400016c6  call    _tlgWriteTransfer_EventWriteTransfer
0x1400016cb  mov     rcx, [rbp+27h+var_10]
0x1400016cf  xor     rcx, rsp; StackCookie
0x1400016d2  call    __security_check_cookie
0x1400016d7  add     rsp, 0C0h
0x1400016de  pop     rbp
0x1400016df  retn
```
