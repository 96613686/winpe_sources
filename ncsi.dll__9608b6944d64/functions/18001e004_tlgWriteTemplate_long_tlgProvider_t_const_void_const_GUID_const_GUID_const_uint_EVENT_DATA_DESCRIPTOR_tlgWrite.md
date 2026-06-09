# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x18001e004`
- end: `0x18001e17a`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@3@Z`
- size: `374`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010230`
- `0x180032650`
- `0x180033010`

## callees

- `0x18001e004`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18001e138`
- `ntdll!EtwEventWriteTransfer` at `0x18001e138`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 a7,
        const unsigned __int16 **a8)
{
  __int64 v8; // rcx
  const unsigned __int16 *v10; // r8
  __int64 v11; // rax
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  int v17; // ecx
  _DWORD v19[2]; // [rsp+38h] [rbp-51h] BYREF
  __int64 v20; // [rsp+40h] [rbp-49h]
  char *v21; // [rsp+50h] [rbp-39h] BYREF
  int v22; // [rsp+58h] [rbp-31h]
  int v23; // [rsp+5Ch] [rbp-2Dh]
  unsigned __int8 *v24; // [rsp+60h] [rbp-29h]
  int v25; // [rsp+68h] [rbp-21h]
  int v26; // [rsp+6Ch] [rbp-1Dh]
  const unsigned __int16 *v27; // [rsp+70h] [rbp-19h]
  int v28; // [rsp+78h] [rbp-11h]
  int v29; // [rsp+7Ch] [rbp-Dh]
  const unsigned __int16 *v30; // [rsp+80h] [rbp-9h]
  int v31; // [rsp+88h] [rbp-1h]
  int v32; // [rsp+8Ch] [rbp+3h]
  __int64 v33; // [rsp+90h] [rbp+7h]
  __int64 v34; // [rsp+98h] [rbp+Fh]
  const unsigned __int16 *v35; // [rsp+A0h] [rbp+17h]
  int v36; // [rsp+A8h] [rbp+1Fh]
  int v37; // [rsp+ACh] [rbp+23h]

  v8 = -1;
  v10 = *a8;
  if ( *a8 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_BYTE *)v10 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v10 = &qword_18007F760;
    v12 = 1;
  }
  v36 = v12;
  v33 = a7;
  v35 = v10;
  v37 = 0;
  v34 = 8;
  v13 = *a6;
  if ( *a6 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &qword_18007F760;
    v15 = 1;
  }
  v31 = v15;
  v30 = v13;
  v32 = 0;
  v16 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_BYTE *)v16 + v8) );
    v17 = v8 + 1;
  }
  else
  {
    v16 = &qword_18007F760;
    v17 = 1;
  }
  v19[0] = *a2 << 24;
  v19[1] = *(unsigned __int16 *)(a2 + 1);
  v20 = *(_QWORD *)(a2 + 3);
  v21 = (char *)off_18009A088;
  v28 = v17;
  v27 = v16;
  v29 = 0;
  v22 = *(unsigned __int16 *)off_18009A088;
  v25 = *(unsigned __int16 *)(a2 + 11);
  v24 = a2 + 11;
  v23 = 2;
  v26 = 1;
  return EtwEventWriteTransfer(qword_18009A0A0, v19, 0, 0, 6, &v21);
}

```

## disassembly

```asm
0x18001e004  push    rbp
0x18001e006  lea     rbp, [rsp-37h]
0x18001e00b  sub     rsp, 0C0h
0x18001e012  mov     rax, cs:__security_cookie
0x18001e019  xor     rax, rsp
0x18001e01c  mov     [rbp+37h+var_10], rax
0x18001e020  mov     rax, [rbp+37h+arg_38]
0x18001e024  lea     r11, qword_18007F760
0x18001e02b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001e02f  xor     r10d, r10d
0x18001e032  mov     r9, rdx
0x18001e035  mov     r8, [rax]
0x18001e038  test    r8, r8
0x18001e03b  jz      loc_18001E153
0x18001e041  mov     rax, rcx
0x18001e044  inc     rax
0x18001e047  cmp     [r8+rax], r10b
0x18001e04b  jnz     short loc_18001E044
0x18001e04d  inc     eax
0x18001e04f  mov     [rbp+37h+var_18], eax
0x18001e052  mov     rax, [rbp+37h+arg_30]
0x18001e056  mov     [rbp+37h+var_30], rax
0x18001e05a  mov     rax, [rbp+37h+arg_28]
0x18001e05e  mov     [rbp+37h+var_20], r8
0x18001e062  mov     [rbp+37h+var_14], r10d
0x18001e066  mov     [rbp+37h+var_28], 8
0x18001e06e  mov     rdx, [rax]
0x18001e071  test    rdx, rdx
0x18001e074  jz      loc_18001E160
0x18001e07a  mov     rax, rcx
0x18001e07d  inc     rax
0x18001e080  cmp     [rdx+rax], r10b
0x18001e084  jnz     short loc_18001E07D
0x18001e086  inc     eax
0x18001e088  mov     [rbp+37h+var_38], eax
0x18001e08b  mov     rax, [rbp+37h+arg_20]
0x18001e08f  mov     [rbp+37h+var_40], rdx
0x18001e093  mov     [rbp+37h+var_34], r10d
0x18001e097  mov     rdx, [rax]
0x18001e09a  test    rdx, rdx
0x18001e09d  jz      loc_18001E16D
0x18001e0a3  inc     rcx
0x18001e0a6  cmp     [rdx+rcx], r10b
0x18001e0aa  jnz     short loc_18001E0A3
0x18001e0ac  inc     ecx
0x18001e0ae  movzx   eax, byte ptr [r9]
0x18001e0b2  xor     r8d, r8d
0x18001e0b5  shl     eax, 18h
0x18001e0b8  mov     [rbp+37h+var_88], eax
0x18001e0bb  movzx   eax, word ptr [r9+1]
0x18001e0c0  mov     [rbp+37h+var_84], eax
0x18001e0c3  mov     rax, [r9+3]
0x18001e0c7  mov     [rbp+37h+var_80], rax
0x18001e0cb  mov     rax, cs:off_18009A088
0x18001e0d2  mov     [rbp+37h+var_70], rax
0x18001e0d6  mov     [rbp+37h+var_48], ecx
0x18001e0d9  lea     rcx, [r9+0Bh]
0x18001e0dd  mov     [rbp+37h+var_50], rdx
0x18001e0e1  xor     r9d, r9d
0x18001e0e4  mov     [rbp+37h+var_44], r10d
0x18001e0e8  lea     rdx, [rbp+37h+var_88]
0x18001e0ec  movzx   eax, word ptr [rax]
0x18001e0ef  mov     [rbp+37h+var_68], eax
0x18001e0f2  movzx   eax, word ptr [rcx]
0x18001e0f5  mov     [rbp+37h+var_58], eax
0x18001e0f8  lea     rax, _TraceLoggingMetadataEnd
0x18001e0ff  mov     [rbp+37h+var_60], rcx
0x18001e103  lea     rcx, _TraceLoggingMetadata
0x18001e10a  sub     eax, ecx
0x18001e10c  mov     [rbp+37h+var_64], 2
0x18001e113  mov     [rbp+37h+var_54], 1
0x18001e11a  mov     [rbp+37h+var_90], eax
0x18001e11d  mov     eax, [rbp+37h+var_90]
0x18001e120  mov     rcx, cs:qword_18009A0A0
0x18001e127  lea     rax, [rbp+37h+var_70]
0x18001e12b  mov     [rsp+0C0h+var_98], rax
0x18001e130  mov     [rsp+0C0h+var_A0], 6
0x18001e138  call    cs:__imp_EtwEventWriteTransfer
0x18001e13e  mov     rcx, [rbp+37h+var_10]
0x18001e142  xor     rcx, rsp; StackCookie
0x18001e145  call    __security_check_cookie
0x18001e14a  add     rsp, 0C0h
0x18001e151  pop     rbp
0x18001e152  retn
0x18001e153  mov     r8, r11
0x18001e156  mov     eax, 1
0x18001e15b  jmp     loc_18001E04F
0x18001e160  mov     rdx, r11
0x18001e163  mov     eax, 1
0x18001e168  jmp     loc_18001E088
0x18001e16d  mov     rdx, r11
0x18001e170  mov     ecx, 1
0x18001e175  jmp     loc_18001E0AE
```
