# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180029b5c`
- end: `0x180029cee`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@5@Z`
- size: `402`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180032650`
- `0x180033010`

## callees

- `0x180029b5c`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180029cb2`
- `ntdll!EtwEventWriteTransfer` at `0x180029cb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  int v19; // ecx
  _DWORD v21[2]; // [rsp+38h] [rbp-81h] BYREF
  __int64 v22; // [rsp+40h] [rbp-79h]
  char *v23; // [rsp+50h] [rbp-69h] BYREF
  int v24; // [rsp+58h] [rbp-61h]
  int v25; // [rsp+5Ch] [rbp-5Dh]
  unsigned __int8 *v26; // [rsp+60h] [rbp-59h]
  int v27; // [rsp+68h] [rbp-51h]
  int v28; // [rsp+6Ch] [rbp-4Dh]
  const unsigned __int16 *v29; // [rsp+70h] [rbp-49h]
  int v30; // [rsp+78h] [rbp-41h]
  int v31; // [rsp+7Ch] [rbp-3Dh]
  const unsigned __int16 *v32; // [rsp+80h] [rbp-39h]
  int v33; // [rsp+88h] [rbp-31h]
  int v34; // [rsp+8Ch] [rbp-2Dh]
  __int64 v35; // [rsp+90h] [rbp-29h]
  __int64 v36; // [rsp+98h] [rbp-21h]
  const unsigned __int16 *v37; // [rsp+A0h] [rbp-19h]
  int v38; // [rsp+A8h] [rbp-11h]
  int v39; // [rsp+ACh] [rbp-Dh]
  __int64 v40; // [rsp+B0h] [rbp-9h]
  __int64 v41; // [rsp+B8h] [rbp-1h]
  __int64 v42; // [rsp+C0h] [rbp+7h]
  __int64 v43; // [rsp+C8h] [rbp+Fh]

  v42 = a10;
  v40 = a9;
  v11 = -1;
  v43 = 4;
  v41 = 4;
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
    v12 = &qword_18007F760;
    v14 = 1;
  }
  v38 = v14;
  v35 = a7;
  v37 = v12;
  v39 = 0;
  v36 = 8;
  v15 = *a6;
  if ( *a6 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_BYTE *)v15 + v16) );
    v17 = v16 + 1;
  }
  else
  {
    v15 = &qword_18007F760;
    v17 = 1;
  }
  v33 = v17;
  v32 = v15;
  v34 = 0;
  v18 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v18 + v11) );
    v19 = v11 + 1;
  }
  else
  {
    v18 = &qword_18007F760;
    v19 = 1;
  }
  v21[0] = *a2 << 24;
  v21[1] = *(unsigned __int16 *)(a2 + 1);
  v22 = *(_QWORD *)(a2 + 3);
  v23 = (char *)off_18009A088;
  v30 = v19;
  v29 = v18;
  v31 = 0;
  v24 = *(unsigned __int16 *)off_18009A088;
  v27 = *(unsigned __int16 *)(a2 + 11);
  v26 = a2 + 11;
  v25 = 2;
  v28 = 1;
  return EtwEventWriteTransfer(qword_18009A0A0, v21, 0, 0, 8, &v23);
}

```

## disassembly

```asm
0x180029b5c  push    rbp
0x180029b5e  lea     rbp, [rsp-27h]
0x180029b63  sub     rsp, 0E0h
0x180029b6a  mov     rax, cs:__security_cookie
0x180029b71  xor     rax, rsp
0x180029b74  mov     [rbp+27h+var_10], rax
0x180029b78  mov     rax, [rbp+27h+arg_48]
0x180029b7c  lea     r10, qword_18007F760
0x180029b83  mov     [rbp+27h+var_20], rax
0x180029b87  xor     r9d, r9d
0x180029b8a  mov     rax, [rbp+27h+arg_40]
0x180029b8e  mov     r8, rdx
0x180029b91  mov     [rbp+27h+var_30], rax
0x180029b95  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180029b99  mov     rax, [rbp+27h+arg_38]
0x180029b9d  mov     [rbp+27h+var_18], 4
0x180029ba5  lea     r11d, [r9+1]
0x180029ba9  mov     [rbp+27h+var_28], 4
0x180029bb1  mov     rdx, [rax]
0x180029bb4  test    rdx, rdx
0x180029bb7  jz      loc_180029CCD
0x180029bbd  mov     rax, rcx
0x180029bc0  inc     rax
0x180029bc3  cmp     [rdx+rax], r9b
0x180029bc7  jnz     short loc_180029BC0
0x180029bc9  inc     eax
0x180029bcb  mov     [rbp+27h+var_38], eax
0x180029bce  mov     rax, [rbp+27h+arg_30]
0x180029bd2  mov     [rbp+27h+var_50], rax
0x180029bd6  mov     rax, [rbp+27h+arg_28]
0x180029bda  mov     [rbp+27h+var_40], rdx
0x180029bde  mov     [rbp+27h+var_34], r9d
0x180029be2  mov     [rbp+27h+var_48], 8
0x180029bea  mov     rdx, [rax]
0x180029bed  test    rdx, rdx
0x180029bf0  jz      loc_180029CD8
0x180029bf6  mov     rax, rcx
0x180029bf9  inc     rax
0x180029bfc  cmp     [rdx+rax], r9b
0x180029c00  jnz     short loc_180029BF9
0x180029c02  inc     eax
0x180029c04  mov     [rbp+27h+var_58], eax
0x180029c07  mov     rax, [rbp+27h+arg_20]
0x180029c0b  mov     [rbp+27h+var_60], rdx
0x180029c0f  mov     [rbp+27h+var_54], r9d
0x180029c13  mov     rdx, [rax]
0x180029c16  test    rdx, rdx
0x180029c19  jz      loc_180029CE3
0x180029c1f  inc     rcx
0x180029c22  cmp     [rdx+rcx], r9b
0x180029c26  jnz     short loc_180029C1F
0x180029c28  inc     ecx
0x180029c2a  movzx   eax, byte ptr [r8]
0x180029c2e  shl     eax, 18h
0x180029c31  mov     [rsp+0E0h+var_A8], eax
0x180029c35  movzx   eax, word ptr [r8+1]
0x180029c3a  mov     [rbp+27h+var_A4], eax
0x180029c3d  mov     rax, [r8+3]
0x180029c41  mov     [rbp+27h+var_A0], rax
0x180029c45  mov     rax, cs:off_18009A088
0x180029c4c  mov     [rbp+27h+var_90], rax
0x180029c50  mov     [rbp+27h+var_68], ecx
0x180029c53  lea     rcx, [r8+0Bh]
0x180029c57  mov     [rbp+27h+var_70], rdx
0x180029c5b  xor     r8d, r8d
0x180029c5e  mov     [rbp+27h+var_64], r9d
0x180029c62  lea     rdx, [rsp+0E0h+var_A8]
0x180029c67  movzx   eax, word ptr [rax]
0x180029c6a  mov     [rbp+27h+var_88], eax
0x180029c6d  movzx   eax, word ptr [rcx]
0x180029c70  mov     [rbp+27h+var_78], eax
0x180029c73  lea     rax, _TraceLoggingMetadataEnd
0x180029c7a  mov     [rbp+27h+var_80], rcx
0x180029c7e  lea     rcx, _TraceLoggingMetadata
0x180029c85  sub     eax, ecx
0x180029c87  mov     [rbp+27h+var_84], 2
0x180029c8e  mov     [rbp+27h+var_74], r11d
0x180029c92  mov     [rsp+0E0h+var_B0], eax
0x180029c96  mov     eax, [rsp+0E0h+var_B0]
0x180029c9a  mov     rcx, cs:qword_18009A0A0
0x180029ca1  lea     rax, [rbp+27h+var_90]
0x180029ca5  mov     [rsp+0E0h+var_B8], rax
0x180029caa  mov     [rsp+0E0h+var_C0], 8
0x180029cb2  call    cs:__imp_EtwEventWriteTransfer
0x180029cb8  mov     rcx, [rbp+27h+var_10]
0x180029cbc  xor     rcx, rsp; StackCookie
0x180029cbf  call    __security_check_cookie
0x180029cc4  add     rsp, 0E0h
0x180029ccb  pop     rbp
0x180029ccc  retn
0x180029ccd  mov     rdx, r10
0x180029cd0  mov     eax, r11d
0x180029cd3  jmp     loc_180029BCB
0x180029cd8  mov     rdx, r10
0x180029cdb  mov     eax, r11d
0x180029cde  jmp     loc_180029C04
0x180029ce3  mov     rdx, r10
0x180029ce6  mov     ecx, r11d
0x180029ce9  jmp     loc_180029C2A
```
