# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &)

- ea: `0x140001fb4`
- end: `0x1400020e3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U1@U1@U_tlgWrapperPtrSize@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55533AEBU_tlgWrapperPtrSize@@6@Z`
- size: `303`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const WCHAR **, __int64, __int64, __int64, __int64, __int64, __int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013530`

## callees

- `0x1400019e8`
- `0x140001fb4`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const WCHAR **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 *a13,
        __int64 *a14)
{
  const WCHAR *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  _BYTE v19[32]; // [rsp+30h] [rbp-C9h] BYREF
  __int64 v20; // [rsp+50h] [rbp-A9h]
  __int64 v21; // [rsp+58h] [rbp-A1h]
  const WCHAR *v22; // [rsp+60h] [rbp-99h]
  int v23; // [rsp+68h] [rbp-91h]
  int v24; // [rsp+6Ch] [rbp-8Dh]
  __int64 v25; // [rsp+70h] [rbp-89h]
  __int64 v26; // [rsp+78h] [rbp-81h]
  __int64 v27; // [rsp+80h] [rbp-79h]
  __int64 v28; // [rsp+88h] [rbp-71h]
  __int64 v29; // [rsp+90h] [rbp-69h]
  __int64 v30; // [rsp+98h] [rbp-61h]
  __int64 v31; // [rsp+A0h] [rbp-59h]
  __int64 v32; // [rsp+A8h] [rbp-51h]
  __int64 v33; // [rsp+B0h] [rbp-49h]
  __int64 v34; // [rsp+B8h] [rbp-41h]
  __int64 v35; // [rsp+C0h] [rbp-39h]
  __int64 v36; // [rsp+C8h] [rbp-31h]
  __int64 v37; // [rsp+D0h] [rbp-29h]
  int v38; // [rsp+D8h] [rbp-21h]
  int v39; // [rsp+DCh] [rbp-1Dh]
  __int64 v40; // [rsp+E0h] [rbp-19h]
  int v41; // [rsp+E8h] [rbp-11h]
  int v42; // [rsp+ECh] [rbp-Dh]

  v36 = 8;
  v42 = 0;
  v39 = 0;
  v34 = 8;
  v40 = *a14;
  v41 = *((_DWORD *)a14 + 2);
  v32 = 4;
  v30 = 4;
  v37 = *a13;
  v38 = *((_DWORD *)a13 + 2);
  v35 = a12;
  v33 = a11;
  v31 = a10;
  v29 = a9;
  v27 = a8;
  v25 = a7;
  v28 = 4;
  v26 = 4;
  v15 = *a6;
  if ( *a6 )
  {
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &String;
    v17 = 2;
  }
  v23 = v17;
  v20 = a5;
  v22 = v15;
  v24 = 0;
  v21 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 12, v19);
}

```

## disassembly

```asm
0x140001fb4  push    rbp
0x140001fb6  lea     rbp, [rsp-7]
0x140001fbb  sub     rsp, 100h
0x140001fc2  mov     rax, cs:__security_cookie
0x140001fc9  xor     rax, rsp
0x140001fcc  mov     [rbp+7+var_10], rax
0x140001fd0  mov     r10, rcx
0x140001fd3  mov     [rbp+7+var_38], 8
0x140001fdb  mov     rcx, [rbp+7+arg_68]
0x140001fdf  xor     r8d, r8d
0x140001fe2  mov     [rbp+7+var_14], r8d
0x140001fe6  mov     [rbp+7+var_24], r8d
0x140001fea  mov     [rbp+7+var_48], 8
0x140001ff2  mov     rax, [rcx]
0x140001ff5  mov     [rbp+7+var_20], rax
0x140001ff9  mov     eax, [rcx+8]
0x140001ffc  mov     rcx, [rbp+7+arg_60]
0x140002000  mov     [rbp+7+var_18], eax
0x140002003  mov     [rbp+7+var_58], 4
0x14000200b  mov     [rbp+7+var_68], 4
0x140002013  mov     rax, [rcx]
0x140002016  mov     [rbp+7+var_30], rax
0x14000201a  mov     eax, [rcx+8]
0x14000201d  mov     [rbp+7+var_28], eax
0x140002020  mov     rax, [rbp+7+arg_58]
0x140002024  mov     [rbp+7+var_40], rax
0x140002028  mov     rax, [rbp+7+arg_50]
0x14000202c  mov     [rbp+7+var_50], rax
0x140002030  mov     rax, [rbp+7+arg_48]
0x140002034  mov     [rbp+7+var_60], rax
0x140002038  mov     rax, [rbp+7+arg_40]
0x14000203c  mov     [rbp+7+var_70], rax
0x140002040  mov     rax, [rbp+7+arg_38]
0x140002044  mov     [rbp+7+var_80], rax
0x140002048  mov     rax, [rbp+7+arg_30]
0x14000204c  mov     [rsp+100h+var_90], rax
0x140002051  mov     rax, [rbp+7+arg_28]
0x140002055  mov     [rbp+7+var_78], 4
0x14000205d  mov     [rsp+100h+var_88], 4
0x140002066  mov     rcx, [rax]
0x140002069  test    rcx, rcx
0x14000206c  jz      short loc_140002085
0x14000206e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002072  inc     rax
0x140002075  cmp     [rcx+rax*2], r8w
0x14000207a  jnz     short loc_140002072
0x14000207c  lea     eax, ds:2[rax*2]
0x140002083  jmp     short loc_140002091
0x140002085  lea     rcx, String
0x14000208c  mov     eax, 2
0x140002091  mov     [rsp+100h+var_98], eax
0x140002095  xor     r9d, r9d
0x140002098  mov     rax, [rbp+7+arg_20]
0x14000209c  mov     [rsp+100h+var_B0], rax
0x1400020a1  lea     rax, [rsp+100h+var_D0]
0x1400020a6  mov     [rsp+100h+var_A0], rcx
0x1400020ab  mov     rcx, r10
0x1400020ae  mov     [rsp+100h+var_D8], rax
0x1400020b3  mov     [rsp+100h+var_E0], 0Ch
0x1400020bb  mov     [rsp+100h+var_94], r8d
0x1400020c0  mov     [rsp+100h+var_A8], 8
0x1400020c9  call    _tlgWriteTransfer_EventWriteTransfer
0x1400020ce  mov     rcx, [rbp+7+var_10]
0x1400020d2  xor     rcx, rsp; StackCookie
0x1400020d5  call    __security_check_cookie
0x1400020da  add     rsp, 100h
0x1400020e1  pop     rbp
0x1400020e2  retn
```
