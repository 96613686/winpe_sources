# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180021470`
- end: `0x1800215f6`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@43@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180033e90`

## callees

- `0x180021470`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800215b4`
- `ntdll!EtwEventWriteTransfer` at `0x1800215b4`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 a7,
        __int64 a8,
        const unsigned __int16 **a9)
{
  __int64 v9; // rcx
  const unsigned __int16 *v11; // r8
  __int64 v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // ecx
  _DWORD v20[2]; // [rsp+38h] [rbp-69h] BYREF
  __int64 v21; // [rsp+40h] [rbp-61h]
  char *v22; // [rsp+50h] [rbp-51h] BYREF
  int v23; // [rsp+58h] [rbp-49h]
  int v24; // [rsp+5Ch] [rbp-45h]
  unsigned __int8 *v25; // [rsp+60h] [rbp-41h]
  int v26; // [rsp+68h] [rbp-39h]
  int v27; // [rsp+6Ch] [rbp-35h]
  const unsigned __int16 *v28; // [rsp+70h] [rbp-31h]
  int v29; // [rsp+78h] [rbp-29h]
  int v30; // [rsp+7Ch] [rbp-25h]
  const unsigned __int16 *v31; // [rsp+80h] [rbp-21h]
  int v32; // [rsp+88h] [rbp-19h]
  int v33; // [rsp+8Ch] [rbp-15h]
  __int64 v34; // [rsp+90h] [rbp-11h]
  __int64 v35; // [rsp+98h] [rbp-9h]
  __int64 v36; // [rsp+A0h] [rbp-1h]
  __int64 v37; // [rsp+A8h] [rbp+7h]
  const unsigned __int16 *v38; // [rsp+B0h] [rbp+Fh]
  int v39; // [rsp+B8h] [rbp+17h]
  int v40; // [rsp+BCh] [rbp+1Bh]

  v9 = -1;
  v11 = *a9;
  if ( *a9 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &qword_18007F760;
    v13 = 1;
  }
  v39 = v13;
  v36 = a8;
  v34 = a7;
  v38 = v11;
  v40 = 0;
  v37 = 4;
  v14 = *a6;
  v35 = 4;
  if ( v14 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v14 = &qword_18007F760;
    v16 = 1;
  }
  v32 = v16;
  v31 = v14;
  v33 = 0;
  v17 = *a5;
  if ( *a5 )
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
  v22 = (char *)off_18009A088;
  v29 = v18;
  v28 = v17;
  v30 = 0;
  v23 = *(unsigned __int16 *)off_18009A088;
  v26 = *(unsigned __int16 *)(a2 + 11);
  v25 = a2 + 11;
  v24 = 2;
  v27 = 1;
  return EtwEventWriteTransfer(qword_18009A0A0, v20, 0, 0, 7, &v22);
}

```

## disassembly

```asm
0x180021470  push    rbp
0x180021472  lea     rbp, [rsp-2Fh]
0x180021477  sub     rsp, 0D0h
0x18002147e  mov     rax, cs:__security_cookie
0x180021485  xor     rax, rsp
0x180021488  mov     [rbp+2Fh+var_10], rax
0x18002148c  mov     rax, [rbp+2Fh+arg_40]
0x180021490  lea     r11, qword_18007F760
0x180021497  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002149b  xor     r10d, r10d
0x18002149e  mov     r9, rdx
0x1800214a1  mov     r8, [rax]
0x1800214a4  test    r8, r8
0x1800214a7  jz      loc_1800215CF
0x1800214ad  mov     rax, rcx
0x1800214b0  inc     rax
0x1800214b3  cmp     [r8+rax], r10b
0x1800214b7  jnz     short loc_1800214B0
0x1800214b9  inc     eax
0x1800214bb  mov     [rbp+2Fh+var_18], eax
0x1800214be  mov     rax, [rbp+2Fh+arg_38]
0x1800214c2  mov     [rbp+2Fh+var_30], rax
0x1800214c6  mov     rax, [rbp+2Fh+arg_30]
0x1800214ca  mov     [rbp+2Fh+var_40], rax
0x1800214ce  mov     rax, [rbp+2Fh+arg_28]
0x1800214d2  mov     [rbp+2Fh+var_20], r8
0x1800214d6  mov     [rbp+2Fh+var_14], r10d
0x1800214da  mov     [rbp+2Fh+var_28], 4
0x1800214e2  mov     rdx, [rax]
0x1800214e5  mov     [rbp+2Fh+var_38], 4
0x1800214ed  test    rdx, rdx
0x1800214f0  jz      loc_1800215DC
0x1800214f6  mov     rax, rcx
0x1800214f9  inc     rax
0x1800214fc  cmp     [rdx+rax], r10b
0x180021500  jnz     short loc_1800214F9
0x180021502  inc     eax
0x180021504  mov     [rbp+2Fh+var_48], eax
0x180021507  mov     rax, [rbp+2Fh+arg_20]
0x18002150b  mov     [rbp+2Fh+var_50], rdx
0x18002150f  mov     [rbp+2Fh+var_44], r10d
0x180021513  mov     rdx, [rax]
0x180021516  test    rdx, rdx
0x180021519  jz      loc_1800215E9
0x18002151f  inc     rcx
0x180021522  cmp     [rdx+rcx], r10b
0x180021526  jnz     short loc_18002151F
0x180021528  inc     ecx
0x18002152a  movzx   eax, byte ptr [r9]
0x18002152e  xor     r8d, r8d
0x180021531  shl     eax, 18h
0x180021534  mov     [rbp+2Fh+var_98], eax
0x180021537  movzx   eax, word ptr [r9+1]
0x18002153c  mov     [rbp+2Fh+var_94], eax
0x18002153f  mov     rax, [r9+3]
0x180021543  mov     [rbp+2Fh+var_90], rax
0x180021547  mov     rax, cs:off_18009A088
0x18002154e  mov     [rbp+2Fh+var_80], rax
0x180021552  mov     [rbp+2Fh+var_58], ecx
0x180021555  lea     rcx, [r9+0Bh]
0x180021559  mov     [rbp+2Fh+var_60], rdx
0x18002155d  xor     r9d, r9d
0x180021560  mov     [rbp+2Fh+var_54], r10d
0x180021564  lea     rdx, [rbp+2Fh+var_98]
0x180021568  movzx   eax, word ptr [rax]
0x18002156b  mov     [rbp+2Fh+var_78], eax
0x18002156e  movzx   eax, word ptr [rcx]
0x180021571  mov     [rbp+2Fh+var_68], eax
0x180021574  lea     rax, _TraceLoggingMetadataEnd
0x18002157b  mov     [rbp+2Fh+var_70], rcx
0x18002157f  lea     rcx, _TraceLoggingMetadata
0x180021586  sub     eax, ecx
0x180021588  mov     [rbp+2Fh+var_74], 2
0x18002158f  mov     [rbp+2Fh+var_64], 1
0x180021596  mov     [rbp+2Fh+var_A0], eax
0x180021599  mov     eax, [rbp+2Fh+var_A0]
0x18002159c  mov     rcx, cs:qword_18009A0A0
0x1800215a3  lea     rax, [rbp+2Fh+var_80]
0x1800215a7  mov     [rsp+0D0h+var_A8], rax
0x1800215ac  mov     [rsp+0D0h+var_B0], 7
0x1800215b4  call    cs:__imp_EtwEventWriteTransfer
0x1800215ba  mov     rcx, [rbp+2Fh+var_10]
0x1800215be  xor     rcx, rsp; StackCookie
0x1800215c1  call    __security_check_cookie
0x1800215c6  add     rsp, 0D0h
0x1800215cd  pop     rbp
0x1800215ce  retn
0x1800215cf  mov     r8, r11
0x1800215d2  mov     eax, 1
0x1800215d7  jmp     loc_1800214BB
0x1800215dc  mov     rdx, r11
0x1800215df  mov     eax, 1
0x1800215e4  jmp     loc_180021504
0x1800215e9  mov     rdx, r11
0x1800215ec  mov     ecx, 1
0x1800215f1  jmp     loc_18002152A
```
