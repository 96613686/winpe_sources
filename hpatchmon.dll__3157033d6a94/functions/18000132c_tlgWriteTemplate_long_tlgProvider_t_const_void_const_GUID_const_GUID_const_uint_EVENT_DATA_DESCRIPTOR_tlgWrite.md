# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000132c`
- end: `0x180001402`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64 *, const unsigned __int16 **, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180006f90`
- `0x180009a80`
- `0x18000ed44`
- `0x18000fa50`
- `0x18000ffe0`

## callees

- `0x1800011cc`
- `0x18000132c`
- `0x180002270`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        const unsigned __int16 **a8,
        __int64 a9)
{
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-61h] BYREF
  __int64 v14; // [rsp+50h] [rbp-41h]
  __int64 v15; // [rsp+58h] [rbp-39h]
  __int64 v16; // [rsp+60h] [rbp-31h]
  __int64 v17; // [rsp+68h] [rbp-29h]
  __int64 *v18; // [rsp+70h] [rbp-21h]
  __int64 v19; // [rsp+78h] [rbp-19h]
  __int64 v20; // [rsp+80h] [rbp-11h]
  int v21; // [rsp+88h] [rbp-9h]
  int v22; // [rsp+8Ch] [rbp-5h]
  const unsigned __int16 *v23; // [rsp+90h] [rbp-1h]
  int v24; // [rsp+98h] [rbp+7h]
  int v25; // [rsp+9Ch] [rbp+Bh]
  __int64 v26; // [rsp+A0h] [rbp+Fh]
  __int64 v27; // [rsp+A8h] [rbp+17h]

  v26 = a9;
  v27 = 4;
  v9 = *a8;
  if ( *a8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_BYTE *)v9 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v9 = &byte_180016B57;
    v11 = 1;
  }
  v24 = v11;
  v23 = v9;
  v25 = 0;
  v19 = 2;
  v22 = 0;
  v20 = *a7;
  v21 = *((unsigned __int16 *)a7 + 4);
  v16 = a6;
  v18 = a7 + 1;
  v14 = a5;
  v17 = 8;
  v15 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001E080, a2, 0, 0, 8, v13);
}

```

## disassembly

```asm
0x18000132c  push    rbp
0x18000132e  lea     rbp, [rsp-2Fh]
0x180001333  sub     rsp, 0C0h
0x18000133a  mov     rax, cs:__security_cookie
0x180001341  xor     rax, rsp
0x180001344  mov     [rbp+2Fh+var_10], rax
0x180001348  mov     rax, [rbp+2Fh+arg_40]
0x18000134c  xor     r8d, r8d
0x18000134f  mov     [rbp+2Fh+var_20], rax
0x180001353  mov     rax, [rbp+2Fh+arg_38]
0x180001357  mov     [rbp+2Fh+var_18], 4
0x18000135f  mov     rcx, [rax]
0x180001362  test    rcx, rcx
0x180001365  jz      short loc_180001378
0x180001367  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000136b  inc     rax
0x18000136e  cmp     [rcx+rax], r8b
0x180001372  jnz     short loc_18000136B
0x180001374  inc     eax
0x180001376  jmp     short loc_180001384
0x180001378  lea     rcx, byte_180016B57
0x18000137f  mov     eax, 1
0x180001384  mov     [rbp+2Fh+var_28], eax
0x180001387  xor     r9d, r9d
0x18000138a  mov     rax, [rbp+2Fh+arg_30]
0x18000138e  mov     [rbp+2Fh+var_30], rcx
0x180001392  mov     [rbp+2Fh+var_24], r8d
0x180001396  mov     [rbp+2Fh+var_48], 2
0x18000139e  lea     rcx, [rax+8]
0x1800013a2  mov     [rbp+2Fh+var_34], r8d
0x1800013a6  mov     rax, [rax]
0x1800013a9  mov     [rbp+2Fh+var_40], rax
0x1800013ad  movzx   eax, word ptr [rcx]
0x1800013b0  mov     [rbp+2Fh+var_38], eax
0x1800013b3  mov     rax, [rbp+2Fh+arg_28]
0x1800013b7  mov     [rbp+2Fh+var_60], rax
0x1800013bb  mov     rax, [rbp+2Fh+arg_20]
0x1800013bf  mov     [rbp+2Fh+var_50], rcx
0x1800013c3  mov     ecx, 8
0x1800013c8  mov     [rbp+2Fh+var_70], rax
0x1800013cc  lea     rax, [rbp+2Fh+var_90]
0x1800013d0  mov     [rsp+0C0h+var_98], rax
0x1800013d5  mov     [rsp+0C0h+var_A0], ecx
0x1800013d9  mov     [rbp+2Fh+var_58], rcx
0x1800013dd  mov     [rbp+2Fh+var_68], rcx
0x1800013e1  lea     rcx, dword_18001E080
0x1800013e8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013ed  mov     rcx, [rbp+2Fh+var_10]
0x1800013f1  xor     rcx, rsp; StackCookie
0x1800013f4  call    __security_check_cookie
0x1800013f9  add     rsp, 0C0h
0x180001400  pop     rbp
0x180001401  retn
```
