# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180029dbc`
- end: `0x180029f53`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapSz@G@@5@Z`
- size: `407`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **, __int64, __int64, const size_t **, const size_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000b4a4`

## callees

- `0x180029dbc`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180029f0b`
- `ntdll!EtwEventWriteTransfer` at `0x180029f0b`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        const size_t **a8,
        const size_t **a9)
{
  __int64 v9; // rcx
  const size_t *v11; // r8
  __int64 v12; // rax
  int v13; // eax
  const size_t *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // ecx
  _DWORD v20[2]; // [rsp+38h] [rbp-69h] BYREF
  __int64 v21; // [rsp+40h] [rbp-61h]
  __int16 *v22; // [rsp+50h] [rbp-51h] BYREF
  int v23; // [rsp+58h] [rbp-49h]
  int v24; // [rsp+5Ch] [rbp-45h]
  unsigned __int8 *v25; // [rsp+60h] [rbp-41h]
  int v26; // [rsp+68h] [rbp-39h]
  int v27; // [rsp+6Ch] [rbp-35h]
  const unsigned __int16 *v28; // [rsp+70h] [rbp-31h]
  int v29; // [rsp+78h] [rbp-29h]
  int v30; // [rsp+7Ch] [rbp-25h]
  __int64 v31; // [rsp+80h] [rbp-21h]
  __int64 v32; // [rsp+88h] [rbp-19h]
  __int64 v33; // [rsp+90h] [rbp-11h]
  __int64 v34; // [rsp+98h] [rbp-9h]
  const size_t *v35; // [rsp+A0h] [rbp-1h]
  int v36; // [rsp+A8h] [rbp+7h]
  int v37; // [rsp+ACh] [rbp+Bh]
  const size_t *v38; // [rsp+B0h] [rbp+Fh]
  int v39; // [rsp+B8h] [rbp+17h]
  int v40; // [rsp+BCh] [rbp+1Bh]

  v9 = -1;
  v11 = *a9;
  if ( *a9 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &pServiceName;
    v13 = 2;
  }
  v39 = v13;
  v38 = v11;
  v40 = 0;
  v14 = *a8;
  if ( *a8 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &pServiceName;
    v16 = 2;
  }
  v36 = v16;
  v33 = a7;
  v31 = a6;
  v35 = v14;
  v37 = 0;
  v34 = 8;
  v17 = *a5;
  v32 = 8;
  if ( v17 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v17 + v9) );
    v18 = v9 + 1;
  }
  else
  {
    v17 = &qword_18007F760;
    v18 = 1;
  }
  v20[0] = *a2 << 24;
  v20[1] = *(unsigned __int16 *)(a2 + 1);
  v21 = *(_QWORD *)(a2 + 3);
  v22 = off_18009A050;
  v29 = v18;
  v28 = v17;
  v30 = 0;
  v23 = (unsigned __int16)*off_18009A050;
  v26 = *(unsigned __int16 *)(a2 + 11);
  v25 = a2 + 11;
  v27 = 1;
  v24 = 2;
  return EtwEventWriteTransfer(RegHandle, v20, 0, 0, 7, &v22);
}

```

## disassembly

```asm
0x180029dbc  push    rbp
0x180029dbe  lea     rbp, [rsp-2Fh]
0x180029dc3  sub     rsp, 0D0h
0x180029dca  mov     rax, cs:__security_cookie
0x180029dd1  xor     rax, rsp
0x180029dd4  mov     [rbp+2Fh+var_10], rax
0x180029dd8  mov     rax, [rbp+2Fh+arg_40]
0x180029ddc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180029de0  xor     r10d, r10d
0x180029de3  mov     r9, rdx
0x180029de6  mov     r11d, 2
0x180029dec  mov     r8, [rax]
0x180029def  test    r8, r8
0x180029df2  jz      loc_180029F26
0x180029df8  mov     rax, rcx
0x180029dfb  inc     rax
0x180029dfe  cmp     [r8+rax*2], r10w
0x180029e03  jnz     short loc_180029DFB
0x180029e05  lea     eax, ds:2[rax*2]
0x180029e0c  mov     [rbp+2Fh+var_18], eax
0x180029e0f  mov     rax, [rbp+2Fh+arg_38]
0x180029e13  mov     [rbp+2Fh+var_20], r8
0x180029e17  mov     [rbp+2Fh+var_14], r10d
0x180029e1b  mov     rdx, [rax]
0x180029e1e  test    rdx, rdx
0x180029e21  jz      loc_180029F35
0x180029e27  mov     rax, rcx
0x180029e2a  inc     rax
0x180029e2d  cmp     [rdx+rax*2], r10w
0x180029e32  jnz     short loc_180029E2A
0x180029e34  lea     eax, ds:2[rax*2]
0x180029e3b  mov     [rbp+2Fh+var_28], eax
0x180029e3e  mov     r8d, 1
0x180029e44  mov     rax, [rbp+2Fh+arg_30]
0x180029e48  mov     [rbp+2Fh+var_40], rax
0x180029e4c  mov     rax, [rbp+2Fh+arg_28]
0x180029e50  mov     [rbp+2Fh+var_50], rax
0x180029e54  mov     rax, [rbp+2Fh+arg_20]
0x180029e58  mov     [rbp+2Fh+var_30], rdx
0x180029e5c  mov     [rbp+2Fh+var_24], r10d
0x180029e60  mov     [rbp+2Fh+var_38], 8
0x180029e68  mov     rdx, [rax]
0x180029e6b  mov     [rbp+2Fh+var_48], 8
0x180029e73  test    rdx, rdx
0x180029e76  jz      loc_180029F44
0x180029e7c  inc     rcx
0x180029e7f  cmp     [rdx+rcx], r10b
0x180029e83  jnz     short loc_180029E7C
0x180029e85  inc     ecx
0x180029e87  movzx   eax, byte ptr [r9]
0x180029e8b  shl     eax, 18h
0x180029e8e  mov     [rbp+2Fh+var_98], eax
0x180029e91  movzx   eax, word ptr [r9+1]
0x180029e96  mov     [rbp+2Fh+var_94], eax
0x180029e99  mov     rax, [r9+3]
0x180029e9d  mov     [rbp+2Fh+var_90], rax
0x180029ea1  mov     rax, cs:off_18009A050
0x180029ea8  mov     [rbp+2Fh+var_80], rax
0x180029eac  mov     [rbp+2Fh+var_58], ecx
0x180029eaf  lea     rcx, [r9+0Bh]
0x180029eb3  mov     [rbp+2Fh+var_60], rdx
0x180029eb7  xor     r9d, r9d
0x180029eba  mov     [rbp+2Fh+var_54], r10d
0x180029ebe  lea     rdx, [rbp+2Fh+var_98]
0x180029ec2  movzx   eax, word ptr [rax]
0x180029ec5  mov     [rbp+2Fh+var_78], eax
0x180029ec8  movzx   eax, word ptr [rcx]
0x180029ecb  mov     [rbp+2Fh+var_68], eax
0x180029ece  lea     rax, _TraceLoggingMetadataEnd
0x180029ed5  mov     [rbp+2Fh+var_70], rcx
0x180029ed9  lea     rcx, _TraceLoggingMetadata
0x180029ee0  sub     eax, ecx
0x180029ee2  mov     [rbp+2Fh+var_64], r8d
0x180029ee6  mov     [rbp+2Fh+var_74], r11d
0x180029eea  xor     r8d, r8d
0x180029eed  mov     [rbp+2Fh+var_A0], eax
0x180029ef0  mov     eax, [rbp+2Fh+var_A0]
0x180029ef3  mov     rcx, cs:RegHandle
0x180029efa  lea     rax, [rbp+2Fh+var_80]
0x180029efe  mov     [rsp+0D0h+var_A8], rax
0x180029f03  mov     [rsp+0D0h+var_B0], 7
0x180029f0b  call    cs:__imp_EtwEventWriteTransfer
0x180029f11  mov     rcx, [rbp+2Fh+var_10]
0x180029f15  xor     rcx, rsp; StackCookie
0x180029f18  call    __security_check_cookie
0x180029f1d  add     rsp, 0D0h
0x180029f24  pop     rbp
0x180029f25  retn
0x180029f26  lea     r8, pServiceName
0x180029f2d  mov     eax, r11d
0x180029f30  jmp     loc_180029E0C
0x180029f35  lea     rdx, pServiceName
0x180029f3c  mov     eax, r11d
0x180029f3f  jmp     loc_180029E3B
0x180029f44  lea     rdx, qword_18007F760
0x180029f4b  mov     ecx, r8d
0x180029f4e  jmp     loc_180029E87
```
