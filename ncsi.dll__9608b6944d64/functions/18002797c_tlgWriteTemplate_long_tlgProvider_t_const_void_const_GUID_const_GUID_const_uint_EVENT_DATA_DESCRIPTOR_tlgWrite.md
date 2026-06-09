# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x18002797c`
- end: `0x180027b64`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapSz@G@@U3@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapSz@G@@543@Z`
- size: `488`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **, __int64, __int64, const size_t **, const size_t **, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000b4a4`

## callees

- `0x18002797c`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180027b09`
- `ntdll!EtwEventWriteTransfer` at `0x180027b09`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        const size_t **a8,
        const size_t **a9,
        __int64 a10,
        const unsigned __int16 **a11)
{
  __int64 v11; // rcx
  const unsigned __int16 *v13; // r8
  __int64 v14; // rax
  int v15; // eax
  const size_t *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const size_t *v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  int v23; // ecx
  _DWORD v25[2]; // [rsp+38h] [rbp-99h] BYREF
  __int64 v26; // [rsp+40h] [rbp-91h]
  __int16 *v27; // [rsp+50h] [rbp-81h] BYREF
  int v28; // [rsp+58h] [rbp-79h]
  int v29; // [rsp+5Ch] [rbp-75h]
  unsigned __int8 *v30; // [rsp+60h] [rbp-71h]
  int v31; // [rsp+68h] [rbp-69h]
  int v32; // [rsp+6Ch] [rbp-65h]
  const unsigned __int16 *v33; // [rsp+70h] [rbp-61h]
  int v34; // [rsp+78h] [rbp-59h]
  int v35; // [rsp+7Ch] [rbp-55h]
  __int64 v36; // [rsp+80h] [rbp-51h]
  __int64 v37; // [rsp+88h] [rbp-49h]
  __int64 v38; // [rsp+90h] [rbp-41h]
  __int64 v39; // [rsp+98h] [rbp-39h]
  const size_t *v40; // [rsp+A0h] [rbp-31h]
  int v41; // [rsp+A8h] [rbp-29h]
  int v42; // [rsp+ACh] [rbp-25h]
  const size_t *v43; // [rsp+B0h] [rbp-21h]
  int v44; // [rsp+B8h] [rbp-19h]
  int v45; // [rsp+BCh] [rbp-15h]
  __int64 v46; // [rsp+C0h] [rbp-11h]
  __int64 v47; // [rsp+C8h] [rbp-9h]
  const unsigned __int16 *v48; // [rsp+D0h] [rbp-1h]
  int v49; // [rsp+D8h] [rbp+7h]
  int v50; // [rsp+DCh] [rbp+Bh]

  v11 = -1;
  v13 = *a11;
  if ( *a11 )
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
  v49 = v15;
  v46 = a10;
  v48 = v13;
  v50 = 0;
  v47 = 8;
  v16 = *a9;
  if ( *a9 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v16 + v17) );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v16 = &pServiceName;
    v18 = 2;
  }
  v44 = v18;
  v43 = v16;
  v45 = 0;
  v19 = *a8;
  if ( *a8 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v19 + v20) );
    v21 = 2 * v20 + 2;
  }
  else
  {
    v19 = &pServiceName;
    v21 = 2;
  }
  v41 = v21;
  v38 = a7;
  v36 = a6;
  v40 = v19;
  v42 = 0;
  v39 = 8;
  v22 = *a5;
  v37 = 8;
  if ( v22 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v22 + v11) );
    v23 = v11 + 1;
  }
  else
  {
    v22 = &qword_18007F760;
    v23 = 1;
  }
  v25[0] = *a2 << 24;
  v25[1] = *(unsigned __int16 *)(a2 + 1);
  v26 = *(_QWORD *)(a2 + 3);
  v27 = off_18009A050;
  v34 = v23;
  v33 = v22;
  v35 = 0;
  v28 = (unsigned __int16)*off_18009A050;
  v31 = *(unsigned __int16 *)(a2 + 11);
  v30 = a2 + 11;
  v29 = 2;
  v32 = 1;
  return EtwEventWriteTransfer(RegHandle, v25, 0, 0, 9, &v27);
}

```

## disassembly

```asm
0x18002797c  push    rbp
0x18002797e  lea     rbp, [rsp-1Fh]
0x180027983  sub     rsp, 0F0h
0x18002798a  mov     rax, cs:__security_cookie
0x180027991  xor     rax, rsp
0x180027994  mov     [rbp+1Fh+var_10], rax
0x180027998  mov     rax, [rbp+1Fh+arg_50]
0x18002799c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800279a0  xor     r10d, r10d
0x1800279a3  mov     r9, rdx
0x1800279a6  mov     r8, [rax]
0x1800279a9  test    r8, r8
0x1800279ac  jz      loc_180027B24
0x1800279b2  mov     rax, rcx
0x1800279b5  inc     rax
0x1800279b8  cmp     [r8+rax], r10b
0x1800279bc  jnz     short loc_1800279B5
0x1800279be  inc     eax
0x1800279c0  mov     [rbp+1Fh+var_18], eax
0x1800279c3  mov     r11d, 2
0x1800279c9  mov     rax, [rbp+1Fh+arg_48]
0x1800279cd  mov     [rbp+1Fh+var_30], rax
0x1800279d1  mov     rax, [rbp+1Fh+arg_40]
0x1800279d5  mov     [rbp+1Fh+var_20], r8
0x1800279d9  mov     [rbp+1Fh+var_14], r10d
0x1800279dd  mov     [rbp+1Fh+var_28], 8
0x1800279e5  mov     rdx, [rax]
0x1800279e8  test    rdx, rdx
0x1800279eb  jz      loc_180027B35
0x1800279f1  mov     rax, rcx
0x1800279f4  inc     rax
0x1800279f7  cmp     [rdx+rax*2], r10w
0x1800279fc  jnz     short loc_1800279F4
0x1800279fe  lea     eax, ds:2[rax*2]
0x180027a05  mov     [rbp+1Fh+var_38], eax
0x180027a08  mov     rax, [rbp+1Fh+arg_38]
0x180027a0c  mov     [rbp+1Fh+var_40], rdx
0x180027a10  mov     [rbp+1Fh+var_34], r10d
0x180027a14  mov     rdx, [rax]
0x180027a17  test    rdx, rdx
0x180027a1a  jz      loc_180027B44
0x180027a20  mov     rax, rcx
0x180027a23  inc     rax
0x180027a26  cmp     [rdx+rax*2], r10w
0x180027a2b  jnz     short loc_180027A23
0x180027a2d  lea     eax, ds:2[rax*2]
0x180027a34  mov     [rbp+1Fh+var_48], eax
0x180027a37  mov     rax, [rbp+1Fh+arg_30]
0x180027a3b  mov     [rbp+1Fh+var_60], rax
0x180027a3f  mov     rax, [rbp+1Fh+arg_28]
0x180027a43  mov     [rbp+1Fh+var_70], rax
0x180027a47  mov     rax, [rbp+1Fh+arg_20]
0x180027a4b  mov     [rbp+1Fh+var_50], rdx
0x180027a4f  mov     [rbp+1Fh+var_44], r10d
0x180027a53  mov     [rbp+1Fh+var_58], 8
0x180027a5b  mov     rdx, [rax]
0x180027a5e  mov     [rbp+1Fh+var_68], 8
0x180027a66  test    rdx, rdx
0x180027a69  jz      loc_180027B53
0x180027a6f  inc     rcx
0x180027a72  cmp     [rdx+rcx], r10b
0x180027a76  jnz     short loc_180027A6F
0x180027a78  inc     ecx
0x180027a7a  movzx   eax, byte ptr [r9]
0x180027a7e  xor     r8d, r8d
0x180027a81  shl     eax, 18h
0x180027a84  mov     [rsp+0F0h+var_B8], eax
0x180027a88  movzx   eax, word ptr [r9+1]
0x180027a8d  mov     [rsp+0F0h+var_B4], eax
0x180027a91  mov     rax, [r9+3]
0x180027a95  mov     [rsp+0F0h+var_B0], rax
0x180027a9a  mov     rax, cs:off_18009A050
0x180027aa1  mov     [rsp+0F0h+var_A0], rax
0x180027aa6  mov     [rbp+1Fh+var_78], ecx
0x180027aa9  lea     rcx, [r9+0Bh]
0x180027aad  mov     [rbp+1Fh+var_80], rdx
0x180027ab1  xor     r9d, r9d
0x180027ab4  mov     [rbp+1Fh+var_74], r10d
0x180027ab8  lea     rdx, [rsp+0F0h+var_B8]
0x180027abd  movzx   eax, word ptr [rax]
0x180027ac0  mov     [rbp+1Fh+var_98], eax
0x180027ac3  movzx   eax, word ptr [rcx]
0x180027ac6  mov     [rbp+1Fh+var_88], eax
0x180027ac9  lea     rax, _TraceLoggingMetadataEnd
0x180027ad0  mov     [rbp+1Fh+var_90], rcx
0x180027ad4  lea     rcx, _TraceLoggingMetadata
0x180027adb  sub     eax, ecx
0x180027add  mov     [rbp+1Fh+var_94], r11d
0x180027ae1  mov     [rbp+1Fh+var_84], 1
0x180027ae8  mov     [rsp+0F0h+var_C0], eax
0x180027aec  mov     eax, [rsp+0F0h+var_C0]
0x180027af0  mov     rcx, cs:RegHandle
0x180027af7  lea     rax, [rsp+0F0h+var_A0]
0x180027afc  mov     [rsp+0F0h+var_C8], rax
0x180027b01  mov     [rsp+0F0h+var_D0], 9
0x180027b09  call    cs:__imp_EtwEventWriteTransfer
0x180027b0f  mov     rcx, [rbp+1Fh+var_10]
0x180027b13  xor     rcx, rsp; StackCookie
0x180027b16  call    __security_check_cookie
0x180027b1b  add     rsp, 0F0h
0x180027b22  pop     rbp
0x180027b23  retn
0x180027b24  lea     r8, qword_18007F760
0x180027b2b  mov     eax, 1
0x180027b30  jmp     loc_1800279C0
0x180027b35  lea     rdx, pServiceName
0x180027b3c  mov     eax, r11d
0x180027b3f  jmp     loc_180027A05
0x180027b44  lea     rdx, pServiceName
0x180027b4b  mov     eax, r11d
0x180027b4e  jmp     loc_180027A34
0x180027b53  lea     rdx, qword_18007F760
0x180027b5a  mov     ecx, 1
0x180027b5f  jmp     loc_180027A7A
```
