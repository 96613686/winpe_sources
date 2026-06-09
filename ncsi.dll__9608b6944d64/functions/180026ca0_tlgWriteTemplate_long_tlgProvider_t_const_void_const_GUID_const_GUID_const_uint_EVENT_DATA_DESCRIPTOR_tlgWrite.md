# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)

- ea: `0x180026ca0`
- end: `0x180026ea8`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U2@U2@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$00@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@344AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$00@@6@Z`
- size: `520`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64, const size_t **, const size_t **, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18003a500`

## callees

- `0x180026ca0`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180026e4d`
- `ntdll!EtwEventWriteTransfer` at `0x180026e4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        __int64 a9,
        const size_t **a10,
        const size_t **a11,
        __int64 a12,
        __int64 a13)
{
  __int64 v14; // rcx
  const size_t *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  const size_t *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  const unsigned __int16 *v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  const unsigned __int16 *v24; // rdx
  int v25; // ecx
  _DWORD v27[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h]
  char *v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+5Ch] [rbp-A4h]
  unsigned __int8 *v32; // [rsp+60h] [rbp-A0h]
  int v33; // [rsp+68h] [rbp-98h]
  int v34; // [rsp+6Ch] [rbp-94h]
  const unsigned __int16 *v35; // [rsp+70h] [rbp-90h]
  int v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+7Ch] [rbp-84h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+98h] [rbp-68h]
  int v42; // [rsp+9Ch] [rbp-64h]
  __int64 v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  __int64 v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  const size_t *v47; // [rsp+C0h] [rbp-40h]
  int v48; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+CCh] [rbp-34h]
  const size_t *v50; // [rsp+D0h] [rbp-30h]
  int v51; // [rsp+D8h] [rbp-28h]
  int v52; // [rsp+DCh] [rbp-24h]
  __int64 v53; // [rsp+E0h] [rbp-20h]
  __int64 v54; // [rsp+E8h] [rbp-18h]
  __int64 v55; // [rsp+F0h] [rbp-10h]
  __int64 v56; // [rsp+F8h] [rbp-8h]

  v55 = a13;
  v53 = a12;
  v14 = -1;
  v56 = 1;
  v54 = 1;
  v15 = *a11;
  if ( *a11 )
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
  v51 = v17;
  v50 = v15;
  v52 = 0;
  v18 = *a10;
  if ( *a10 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    v20 = 2 * v19 + 2;
  }
  else
  {
    v18 = &pServiceName;
    v20 = 2;
  }
  v48 = v20;
  v45 = a9;
  v43 = a8;
  v47 = v18;
  v49 = 0;
  v46 = 8;
  v21 = *a7;
  v44 = 8;
  if ( v21 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_BYTE *)v21 + v22) );
    v23 = v22 + 1;
  }
  else
  {
    v21 = &qword_18007F760;
    v23 = 1;
  }
  v41 = v23;
  v38 = a6;
  v40 = v21;
  v42 = 0;
  v39 = 8;
  v24 = *a5;
  if ( *a5 )
  {
    do
      ++v14;
    while ( *((_BYTE *)v24 + v14) );
    v25 = v14 + 1;
  }
  else
  {
    v24 = &qword_18007F760;
    v25 = 1;
  }
  v27[0] = *a2 << 24;
  v27[1] = *(unsigned __int16 *)(a2 + 1);
  v28 = *(_QWORD *)(a2 + 3);
  v29 = (char *)off_18009A088;
  v36 = v25;
  v35 = v24;
  v37 = 0;
  v30 = *(unsigned __int16 *)off_18009A088;
  v33 = *(unsigned __int16 *)(a2 + 11);
  v32 = a2 + 11;
  v31 = 2;
  v34 = 1;
  return EtwEventWriteTransfer(qword_18009A0A0, v27, 0, 0, 11, &v29);
}

```

## disassembly

```asm
0x180026ca0  push    rbp
0x180026ca2  lea     rbp, [rsp-10h]
0x180026ca7  sub     rsp, 110h
0x180026cae  mov     rax, cs:__security_cookie
0x180026cb5  xor     rax, rsp
0x180026cb8  mov     [rbp+10h+var_10], rax
0x180026cbc  mov     rax, [rbp+10h+arg_60]
0x180026cc3  mov     r10d, 1
0x180026cc9  mov     [rbp+10h+var_20], rax
0x180026ccd  mov     r8, rdx
0x180026cd0  mov     rax, [rbp+10h+arg_58]
0x180026cd4  xor     r9d, r9d
0x180026cd7  mov     [rbp+10h+var_30], rax
0x180026cdb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180026cdf  mov     rax, [rbp+10h+arg_50]
0x180026ce3  mov     [rbp+10h+var_18], r10
0x180026ce7  mov     [rbp+10h+var_28], r10
0x180026ceb  mov     rdx, [rax]
0x180026cee  test    rdx, rdx
0x180026cf1  jz      loc_180026E68
0x180026cf7  mov     rax, rcx
0x180026cfa  inc     rax
0x180026cfd  cmp     [rdx+rax*2], r9w
0x180026d02  jnz     short loc_180026CFA
0x180026d04  lea     eax, ds:2[rax*2]
0x180026d0b  mov     [rbp+10h+var_38], eax
0x180026d0e  mov     rax, [rbp+10h+arg_48]
0x180026d12  mov     [rbp+10h+var_40], rdx
0x180026d16  mov     [rbp+10h+var_34], r9d
0x180026d1a  mov     rdx, [rax]
0x180026d1d  test    rdx, rdx
0x180026d20  jz      loc_180026E79
0x180026d26  mov     rax, rcx
0x180026d29  inc     rax
0x180026d2c  cmp     [rdx+rax*2], r9w
0x180026d31  jnz     short loc_180026D29
0x180026d33  lea     eax, ds:2[rax*2]
0x180026d3a  mov     [rbp+10h+var_48], eax
0x180026d3d  mov     rax, [rbp+10h+arg_40]
0x180026d41  mov     [rbp+10h+var_60], rax
0x180026d45  mov     rax, [rbp+10h+arg_38]
0x180026d49  mov     [rbp+10h+var_70], rax
0x180026d4d  mov     rax, [rbp+10h+arg_30]
0x180026d51  mov     [rbp+10h+var_50], rdx
0x180026d55  mov     [rbp+10h+var_44], r9d
0x180026d59  mov     [rbp+10h+var_58], 8
0x180026d61  mov     rdx, [rax]
0x180026d64  mov     [rbp+10h+var_68], 8
0x180026d6c  test    rdx, rdx
0x180026d6f  jz      loc_180026E8A
0x180026d75  mov     rax, rcx
0x180026d78  inc     rax
0x180026d7b  cmp     [rdx+rax], r9b
0x180026d7f  jnz     short loc_180026D78
0x180026d81  inc     eax
0x180026d83  mov     [rbp+10h+var_78], eax
0x180026d86  mov     rax, [rbp+10h+arg_28]
0x180026d8a  mov     [rbp+10h+var_90], rax
0x180026d8e  mov     rax, [rbp+10h+arg_20]
0x180026d92  mov     [rbp+10h+var_80], rdx
0x180026d96  mov     [rbp+10h+var_74], r9d
0x180026d9a  mov     [rbp+10h+var_88], 8
0x180026da2  mov     rdx, [rax]
0x180026da5  test    rdx, rdx
0x180026da8  jz      loc_180026E99
0x180026dae  inc     rcx
0x180026db1  cmp     [rdx+rcx], r9b
0x180026db5  jnz     short loc_180026DAE
0x180026db7  inc     ecx
0x180026db9  movzx   eax, byte ptr [r8]
0x180026dbd  shl     eax, 18h
0x180026dc0  mov     [rsp+110h+var_D8], eax
0x180026dc4  movzx   eax, word ptr [r8+1]
0x180026dc9  mov     [rsp+110h+var_D4], eax
0x180026dcd  mov     rax, [r8+3]
0x180026dd1  mov     [rsp+110h+var_D0], rax
0x180026dd6  mov     rax, cs:off_18009A088
0x180026ddd  mov     [rsp+110h+var_C0], rax
0x180026de2  mov     [rsp+110h+var_98], ecx
0x180026de6  lea     rcx, [r8+0Bh]
0x180026dea  mov     [rsp+110h+var_A0], rdx
0x180026def  xor     r8d, r8d
0x180026df2  mov     [rsp+110h+var_94], r9d
0x180026df7  lea     rdx, [rsp+110h+var_D8]
0x180026dfc  movzx   eax, word ptr [rax]
0x180026dff  mov     [rsp+110h+var_B8], eax
0x180026e03  movzx   eax, word ptr [rcx]
0x180026e06  mov     [rsp+110h+var_A8], eax
0x180026e0a  lea     rax, _TraceLoggingMetadataEnd
0x180026e11  mov     [rsp+110h+var_B0], rcx
0x180026e16  lea     rcx, _TraceLoggingMetadata
0x180026e1d  sub     eax, ecx
0x180026e1f  mov     [rsp+110h+var_B4], 2
0x180026e27  mov     [rsp+110h+var_A4], r10d
0x180026e2c  mov     [rsp+110h+var_E0], eax
0x180026e30  mov     eax, [rsp+110h+var_E0]
0x180026e34  mov     rcx, cs:qword_18009A0A0
0x180026e3b  lea     rax, [rsp+110h+var_C0]
0x180026e40  mov     [rsp+110h+var_E8], rax
0x180026e45  mov     [rsp+110h+var_F0], 0Bh
0x180026e4d  call    cs:__imp_EtwEventWriteTransfer
0x180026e53  mov     rcx, [rbp+10h+var_10]
0x180026e57  xor     rcx, rsp; StackCookie
0x180026e5a  call    __security_check_cookie
0x180026e5f  add     rsp, 110h
0x180026e66  pop     rbp
0x180026e67  retn
0x180026e68  lea     rdx, pServiceName
0x180026e6f  mov     eax, 2
0x180026e74  jmp     loc_180026D0B
0x180026e79  lea     rdx, pServiceName
0x180026e80  mov     eax, 2
0x180026e85  jmp     loc_180026D3A
0x180026e8a  lea     rdx, qword_18007F760
0x180026e91  mov     eax, r10d
0x180026e94  jmp     loc_180026D83
0x180026e99  lea     rdx, qword_18007F760
0x180026ea0  mov     ecx, r10d
0x180026ea3  jmp     loc_180026DB9
```
