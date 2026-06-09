# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800288d4`
- end: `0x180028aa3`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@6@Z`
- size: `463`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const size_t **, const size_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000b4a4`

## callees

- `0x1800288d4`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180028a4c`
- `ntdll!EtwEventWriteTransfer` at `0x180028a4c`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const size_t **a9,
        const size_t **a10)
{
  __int64 v10; // rcx
  const size_t *v12; // r8
  __int64 v13; // rax
  int v14; // eax
  const size_t *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  const unsigned __int16 *v21; // rdx
  int v22; // ecx
  _DWORD v24[2]; // [rsp+38h] [rbp-81h] BYREF
  __int64 v25; // [rsp+40h] [rbp-79h]
  __int16 *v26; // [rsp+50h] [rbp-69h] BYREF
  int v27; // [rsp+58h] [rbp-61h]
  int v28; // [rsp+5Ch] [rbp-5Dh]
  unsigned __int8 *v29; // [rsp+60h] [rbp-59h]
  int v30; // [rsp+68h] [rbp-51h]
  int v31; // [rsp+6Ch] [rbp-4Dh]
  const unsigned __int16 *v32; // [rsp+70h] [rbp-49h]
  int v33; // [rsp+78h] [rbp-41h]
  int v34; // [rsp+7Ch] [rbp-3Dh]
  __int64 v35; // [rsp+80h] [rbp-39h]
  __int64 v36; // [rsp+88h] [rbp-31h]
  const unsigned __int16 *v37; // [rsp+90h] [rbp-29h]
  int v38; // [rsp+98h] [rbp-21h]
  int v39; // [rsp+9Ch] [rbp-1Dh]
  __int64 v40; // [rsp+A0h] [rbp-19h]
  __int64 v41; // [rsp+A8h] [rbp-11h]
  const size_t *v42; // [rsp+B0h] [rbp-9h]
  int v43; // [rsp+B8h] [rbp-1h]
  int v44; // [rsp+BCh] [rbp+3h]
  const size_t *v45; // [rsp+C0h] [rbp+7h]
  int v46; // [rsp+C8h] [rbp+Fh]
  int v47; // [rsp+CCh] [rbp+13h]

  v10 = -1;
  v12 = *a10;
  if ( *a10 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &pServiceName;
    v14 = 2;
  }
  v46 = v14;
  v45 = v12;
  v47 = 0;
  v15 = *a9;
  if ( *a9 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &pServiceName;
    v17 = 2;
  }
  v43 = v17;
  v40 = a8;
  v42 = v15;
  v44 = 0;
  v41 = 1;
  v18 = *a7;
  if ( *a7 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_BYTE *)v18 + v19) );
    v20 = v19 + 1;
  }
  else
  {
    v18 = &qword_18007F760;
    v20 = 1;
  }
  v38 = v20;
  v35 = a6;
  v37 = v18;
  v39 = 0;
  v36 = 8;
  v21 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( *((_BYTE *)v21 + v10) );
    v22 = v10 + 1;
  }
  else
  {
    v21 = &qword_18007F760;
    v22 = 1;
  }
  v24[0] = *a2 << 24;
  v24[1] = *(unsigned __int16 *)(a2 + 1);
  v25 = *(_QWORD *)(a2 + 3);
  v26 = off_18009A050;
  v33 = v22;
  v32 = v21;
  v34 = 0;
  v27 = (unsigned __int16)*off_18009A050;
  v30 = *(unsigned __int16 *)(a2 + 11);
  v29 = a2 + 11;
  v31 = 1;
  v28 = 2;
  return EtwEventWriteTransfer(RegHandle, v24, 0, 0, 8, &v26);
}

```

## disassembly

```asm
0x1800288d4  push    rbp
0x1800288d6  lea     rbp, [rsp-27h]
0x1800288db  sub     rsp, 0E0h
0x1800288e2  mov     rax, cs:__security_cookie
0x1800288e9  xor     rax, rsp
0x1800288ec  mov     [rbp+27h+var_10], rax
0x1800288f0  mov     rax, [rbp+27h+arg_48]
0x1800288f4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800288f8  xor     r10d, r10d
0x1800288fb  mov     r9, rdx
0x1800288fe  mov     r11d, 2
0x180028904  mov     r8, [rax]
0x180028907  test    r8, r8
0x18002890a  jz      loc_180028A67
0x180028910  mov     rax, rcx
0x180028913  inc     rax
0x180028916  cmp     [r8+rax*2], r10w
0x18002891b  jnz     short loc_180028913
0x18002891d  lea     eax, ds:2[rax*2]
0x180028924  mov     [rbp+27h+var_18], eax
0x180028927  mov     rax, [rbp+27h+arg_40]
0x18002892b  mov     [rbp+27h+var_20], r8
0x18002892f  mov     [rbp+27h+var_14], r10d
0x180028933  mov     rdx, [rax]
0x180028936  test    rdx, rdx
0x180028939  jz      loc_180028A76
0x18002893f  mov     rax, rcx
0x180028942  inc     rax
0x180028945  cmp     [rdx+rax*2], r10w
0x18002894a  jnz     short loc_180028942
0x18002894c  lea     eax, ds:2[rax*2]
0x180028953  mov     [rbp+27h+var_28], eax
0x180028956  mov     r8d, 1
0x18002895c  mov     rax, [rbp+27h+arg_38]
0x180028960  mov     [rbp+27h+var_40], rax
0x180028964  mov     rax, [rbp+27h+arg_30]
0x180028968  mov     [rbp+27h+var_30], rdx
0x18002896c  mov     [rbp+27h+var_24], r10d
0x180028970  mov     [rbp+27h+var_38], r8
0x180028974  mov     rdx, [rax]
0x180028977  test    rdx, rdx
0x18002897a  jz      loc_180028A85
0x180028980  mov     rax, rcx
0x180028983  inc     rax
0x180028986  cmp     [rdx+rax], r10b
0x18002898a  jnz     short loc_180028983
0x18002898c  inc     eax
0x18002898e  mov     [rbp+27h+var_48], eax
0x180028991  mov     rax, [rbp+27h+arg_28]
0x180028995  mov     [rbp+27h+var_60], rax
0x180028999  mov     rax, [rbp+27h+arg_20]
0x18002899d  mov     [rbp+27h+var_50], rdx
0x1800289a1  mov     [rbp+27h+var_44], r10d
0x1800289a5  mov     [rbp+27h+var_58], 8
0x1800289ad  mov     rdx, [rax]
0x1800289b0  test    rdx, rdx
0x1800289b3  jz      loc_180028A94
0x1800289b9  inc     rcx
0x1800289bc  cmp     [rdx+rcx], r10b
0x1800289c0  jnz     short loc_1800289B9
0x1800289c2  inc     ecx
0x1800289c4  movzx   eax, byte ptr [r9]
0x1800289c8  shl     eax, 18h
0x1800289cb  mov     [rsp+0E0h+var_A8], eax
0x1800289cf  movzx   eax, word ptr [r9+1]
0x1800289d4  mov     [rbp+27h+var_A4], eax
0x1800289d7  mov     rax, [r9+3]
0x1800289db  mov     [rbp+27h+var_A0], rax
0x1800289df  mov     rax, cs:off_18009A050
0x1800289e6  mov     [rbp+27h+var_90], rax
0x1800289ea  mov     [rbp+27h+var_68], ecx
0x1800289ed  lea     rcx, [r9+0Bh]
0x1800289f1  mov     [rbp+27h+var_70], rdx
0x1800289f5  xor     r9d, r9d
0x1800289f8  mov     [rbp+27h+var_64], r10d
0x1800289fc  lea     rdx, [rsp+0E0h+var_A8]
0x180028a01  movzx   eax, word ptr [rax]
0x180028a04  mov     [rbp+27h+var_88], eax
0x180028a07  movzx   eax, word ptr [rcx]
0x180028a0a  mov     [rbp+27h+var_78], eax
0x180028a0d  lea     rax, _TraceLoggingMetadataEnd
0x180028a14  mov     [rbp+27h+var_80], rcx
0x180028a18  lea     rcx, _TraceLoggingMetadata
0x180028a1f  sub     eax, ecx
0x180028a21  mov     [rbp+27h+var_74], r8d
0x180028a25  mov     [rbp+27h+var_84], r11d
0x180028a29  xor     r8d, r8d
0x180028a2c  mov     [rsp+0E0h+var_B0], eax
0x180028a30  mov     eax, [rsp+0E0h+var_B0]
0x180028a34  mov     rcx, cs:RegHandle
0x180028a3b  lea     rax, [rbp+27h+var_90]
0x180028a3f  mov     [rsp+0E0h+var_B8], rax
0x180028a44  mov     [rsp+0E0h+var_C0], 8
0x180028a4c  call    cs:__imp_EtwEventWriteTransfer
0x180028a52  mov     rcx, [rbp+27h+var_10]
0x180028a56  xor     rcx, rsp; StackCookie
0x180028a59  call    __security_check_cookie
0x180028a5e  add     rsp, 0E0h
0x180028a65  pop     rbp
0x180028a66  retn
0x180028a67  lea     r8, pServiceName
0x180028a6e  mov     eax, r11d
0x180028a71  jmp     loc_180028924
0x180028a76  lea     rdx, pServiceName
0x180028a7d  mov     eax, r11d
0x180028a80  jmp     loc_180028953
0x180028a85  lea     rdx, qword_18007F760
0x180028a8c  mov     eax, r8d
0x180028a8f  jmp     loc_18002898E
0x180028a94  lea     rdx, qword_18007F760
0x180028a9b  mov     ecx, r8d
0x180028a9e  jmp     loc_1800289C4
```
