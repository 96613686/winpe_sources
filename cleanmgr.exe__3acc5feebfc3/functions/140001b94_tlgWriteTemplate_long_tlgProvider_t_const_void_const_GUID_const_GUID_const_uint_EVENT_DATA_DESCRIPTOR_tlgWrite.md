# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &)

- ea: `0x140001b94`
- end: `0x140001caf`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U1@U1@U_tlgWrapperPtrSize@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5533AEBU_tlgWrapperPtrSize@@6@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const WCHAR **, __int64, __int64, __int64, __int64, __int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013530`

## callees

- `0x1400019e8`
- `0x140001b94`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
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
        __int64 *a12,
        __int64 *a13)
{
  const WCHAR *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  _BYTE v18[32]; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v19; // [rsp+50h] [rbp-91h]
  __int64 v20; // [rsp+58h] [rbp-89h]
  const WCHAR *v21; // [rsp+60h] [rbp-81h]
  int v22; // [rsp+68h] [rbp-79h]
  int v23; // [rsp+6Ch] [rbp-75h]
  __int64 v24; // [rsp+70h] [rbp-71h]
  __int64 v25; // [rsp+78h] [rbp-69h]
  __int64 v26; // [rsp+80h] [rbp-61h]
  __int64 v27; // [rsp+88h] [rbp-59h]
  __int64 v28; // [rsp+90h] [rbp-51h]
  __int64 v29; // [rsp+98h] [rbp-49h]
  __int64 v30; // [rsp+A0h] [rbp-41h]
  __int64 v31; // [rsp+A8h] [rbp-39h]
  __int64 v32; // [rsp+B0h] [rbp-31h]
  __int64 v33; // [rsp+B8h] [rbp-29h]
  __int64 v34; // [rsp+C0h] [rbp-21h]
  int v35; // [rsp+C8h] [rbp-19h]
  int v36; // [rsp+CCh] [rbp-15h]
  __int64 v37; // [rsp+D0h] [rbp-11h]
  int v38; // [rsp+D8h] [rbp-9h]
  int v39; // [rsp+DCh] [rbp-5h]

  v33 = 8;
  v39 = 0;
  v36 = 0;
  v31 = 8;
  v37 = *a13;
  v38 = *((_DWORD *)a13 + 2);
  v29 = 4;
  v27 = 4;
  v34 = *a12;
  v35 = *((_DWORD *)a12 + 2);
  v32 = a11;
  v30 = a10;
  v28 = a9;
  v26 = a8;
  v24 = a7;
  v25 = 4;
  v14 = *a6;
  if ( *a6 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &String;
    v16 = 2;
  }
  v22 = v16;
  v19 = a5;
  v21 = v14;
  v23 = 0;
  v20 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 11, v18);
}

```

## disassembly

```asm
0x140001b94  push    rbp
0x140001b96  lea     rbp, [rsp-0Fh]
0x140001b9b  sub     rsp, 0F0h
0x140001ba2  mov     rax, cs:__security_cookie
0x140001ba9  xor     rax, rsp
0x140001bac  mov     [rbp+0Fh+var_10], rax
0x140001bb0  mov     r10, rcx
0x140001bb3  mov     [rbp+0Fh+var_38], 8
0x140001bbb  mov     rcx, [rbp+0Fh+arg_60]
0x140001bbf  xor     r8d, r8d
0x140001bc2  mov     [rbp+0Fh+var_14], r8d
0x140001bc6  mov     [rbp+0Fh+var_24], r8d
0x140001bca  mov     [rbp+0Fh+var_48], 8
0x140001bd2  mov     rax, [rcx]
0x140001bd5  mov     [rbp+0Fh+var_20], rax
0x140001bd9  mov     eax, [rcx+8]
0x140001bdc  mov     rcx, [rbp+0Fh+arg_58]
0x140001be0  mov     [rbp+0Fh+var_18], eax
0x140001be3  mov     [rbp+0Fh+var_58], 4
0x140001beb  mov     [rbp+0Fh+var_68], 4
0x140001bf3  mov     rax, [rcx]
0x140001bf6  mov     [rbp+0Fh+var_30], rax
0x140001bfa  mov     eax, [rcx+8]
0x140001bfd  mov     [rbp+0Fh+var_28], eax
0x140001c00  mov     rax, [rbp+0Fh+arg_50]
0x140001c04  mov     [rbp+0Fh+var_40], rax
0x140001c08  mov     rax, [rbp+0Fh+arg_48]
0x140001c0c  mov     [rbp+0Fh+var_50], rax
0x140001c10  mov     rax, [rbp+0Fh+arg_40]
0x140001c14  mov     [rbp+0Fh+var_60], rax
0x140001c18  mov     rax, [rbp+0Fh+arg_38]
0x140001c1c  mov     [rbp+0Fh+var_70], rax
0x140001c20  mov     rax, [rbp+0Fh+arg_30]
0x140001c24  mov     [rbp+0Fh+var_80], rax
0x140001c28  mov     rax, [rbp+0Fh+arg_28]
0x140001c2c  mov     [rbp+0Fh+var_78], 4
0x140001c34  mov     rcx, [rax]
0x140001c37  test    rcx, rcx
0x140001c3a  jz      short loc_140001C53
0x140001c3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001c40  inc     rax
0x140001c43  cmp     [rcx+rax*2], r8w
0x140001c48  jnz     short loc_140001C40
0x140001c4a  lea     eax, ds:2[rax*2]
0x140001c51  jmp     short loc_140001C5F
0x140001c53  lea     rcx, String
0x140001c5a  mov     eax, 2
0x140001c5f  mov     [rbp+0Fh+var_88], eax
0x140001c62  xor     r9d, r9d
0x140001c65  mov     rax, [rbp+0Fh+arg_20]
0x140001c69  mov     [rsp+0F0h+var_A0], rax
0x140001c6e  lea     rax, [rsp+0F0h+var_C0]
0x140001c73  mov     [rsp+0F0h+var_90], rcx
0x140001c78  mov     rcx, r10
0x140001c7b  mov     [rsp+0F0h+var_C8], rax
0x140001c80  mov     [rsp+0F0h+var_D0], 0Bh
0x140001c88  mov     [rbp+0Fh+var_84], r8d
0x140001c8c  mov     [rsp+0F0h+var_98], 8
0x140001c95  call    _tlgWriteTransfer_EventWriteTransfer
0x140001c9a  mov     rcx, [rbp+0Fh+var_10]
0x140001c9e  xor     rcx, rsp; StackCookie
0x140001ca1  call    __security_check_cookie
0x140001ca6  add     rsp, 0F0h
0x140001cad  pop     rbp
0x140001cae  retn
```
