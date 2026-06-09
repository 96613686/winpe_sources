# SmbCeCompareInvalidAuthEntry

- ea: `0x140090a00`
- end: `0x140090b0c`
- name: `SmbCeCompareInvalidAuthEntry`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140090530`
- `0x140090700`

## callees

- `0x14003838c`
- `0x140090a00`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140090a68`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140090a68`
- `ksecdd!SspiCompareAuthIdentities` at `0x14009621b`
- `ksecdd!SspiCompareAuthIdentities` at `0x14009621b`

## pseudocode

```c
char __fastcall SmbCeCompareInvalidAuthEntry(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  void *v3; // rbp
  __int64 v4; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rax
  unsigned int v11; // eax
  int v12; // [rsp+24h] [rbp-24h]
  BOOLEAN SameSuppliedUser; // [rsp+50h] [rbp+8h] BYREF
  BOOLEAN SameSuppliedIdentity; // [rsp+58h] [rbp+10h] BYREF
  __int64 v15; // [rsp+68h] [rbp+20h]

  v3 = 0;
  LODWORD(v4) = 0;
  SameSuppliedIdentity = 0;
  SameSuppliedUser = 0;
  v12 = 0;
  v15 = 0;
  if ( a2 )
  {
    v6 = a2[48];
    v7 = a2[16];
    v4 = a2[13];
    v8 = a2[12];
  }
  else
  {
    if ( !a3 )
    {
      v6 = 0;
      LODWORD(v8) = 0;
      goto LABEL_4;
    }
    v4 = a3[10];
    v8 = a3[9];
    v7 = a3[13];
    v6 = *(_QWORD *)(*(_QWORD *)(a3[4] + 32LL) + 32LL);
  }
  v15 = v8;
  v12 = HIDWORD(v4);
  if ( v7 && *(_QWORD *)(v7 + 8) )
    v3 = *(void **)(v7 + 8);
LABEL_4:
  if ( *(_DWORD *)(v6 + 72) != *(_DWORD *)(a1 + 32)
    || RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 16), (PCUNICODE_STRING)(v6 + 80), 1u)
    || *(_QWORD *)(a1 + 64) != __PAIR64__(HIDWORD(v15), v8)
    && (*(_DWORD *)(a1 + 64) != (_DWORD)v4 || *(_DWORD *)(a1 + 68) != v12) )
  {
    return 0;
  }
  v9 = *(_QWORD *)(a1 + 56);
  if ( v3 )
  {
    if ( !v9 )
      return 0;
    v11 = SspiCompareAuthIdentities(
            v3,
            *(PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)(a1 + 56),
            &SameSuppliedUser,
            &SameSuppliedIdentity);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_48980f24b3dc39b8aaca68646dc5bd2a_Traceguids, v11);
      }
      return 0;
    }
    if ( !SameSuppliedUser || !SameSuppliedIdentity )
      return 0;
  }
  else if ( v9 )
  {
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140090a00  mov     [rsp+arg_10], rbx
0x140090a05  push    rbp
0x140090a06  push    rsi
0x140090a07  push    rdi
0x140090a08  sub     rsp, 30h
0x140090a0c  xor     ebp, ebp
0x140090a0e  xor     ebx, ebx
0x140090a10  mov     [rsp+48h+SameSuppliedIdentity], bpl
0x140090a15  mov     rsi, rcx
0x140090a18  mov     [rsp+48h+SameSuppliedUser], bpl
0x140090a1d  mov     qword ptr [rsp+48h+var_28], rbx
0x140090a22  mov     [rsp+48h+arg_18], rbx
0x140090a27  test    rdx, rdx
0x140090a2a  jz      short loc_140090AAA
0x140090a2c  mov     rcx, [rdx+180h]
0x140090a33  mov     rax, [rdx+80h]
0x140090a3a  mov     rbx, [rdx+68h]
0x140090a3e  mov     rdi, [rdx+60h]
0x140090a42  mov     [rsp+48h+arg_18], rdi
0x140090a47  mov     qword ptr [rsp+48h+var_28], rbx
0x140090a4c  test    rax, rax
0x140090a4f  jnz     loc_140090ADC
0x140090a55  mov     eax, [rsi+20h]
0x140090a58  cmp     [rcx+48h], eax
0x140090a5b  jnz     short loc_140090A9A
0x140090a5d  lea     rdx, [rcx+50h]; String2
0x140090a61  mov     r8b, 1; CaseInSensitive
0x140090a64  lea     rcx, [rsi+10h]; String1
0x140090a68  call    cs:__imp_RtlCompareUnicodeString
0x140090a6f  nop     dword ptr [rax+rax+00h]
0x140090a74  test    eax, eax
0x140090a76  jnz     short loc_140090A9A
0x140090a78  mov     ecx, [rsi+40h]
0x140090a7b  cmp     ecx, edi
0x140090a7d  jnz     short loc_140090AFA
0x140090a7f  mov     eax, dword ptr [rsp+48h+arg_18+4]
0x140090a83  cmp     [rsi+44h], eax
0x140090a86  jnz     short loc_140090AFA
0x140090a88  mov     rax, [rsi+38h]
0x140090a8c  test    rbp, rbp
0x140090a8f  jnz     loc_140096202
0x140090a95  test    rax, rax
0x140090a98  jz      short loc_140090ACC
0x140090a9a  xor     al, al
0x140090a9c  mov     rbx, [rsp+48h+arg_10]
0x140090aa1  add     rsp, 30h
0x140090aa5  pop     rdi
0x140090aa6  pop     rsi
0x140090aa7  pop     rbp
0x140090aa8  retn
0x140090aaa  test    r8, r8
0x140090aad  jz      short loc_140090AF1
0x140090aaf  mov     rax, [r8+20h]
0x140090ab3  mov     rbx, [r8+50h]
0x140090ab7  mov     rdi, [r8+48h]
0x140090abb  mov     rcx, [rax+20h]
0x140090abf  mov     rax, [r8+68h]
0x140090ac3  mov     rcx, [rcx+20h]
0x140090ac7  jmp     loc_140090A42
0x140090acc  mov     rbx, [rsp+48h+arg_10]
0x140090ad1  mov     al, 1
0x140090ad3  add     rsp, 30h
0x140090ad7  pop     rdi
0x140090ad8  pop     rsi
0x140090ad9  pop     rbp
0x140090ada  retn
0x140090adc  mov     rdx, [rax+8]
0x140090ae0  test    rdx, rdx
0x140090ae3  jz      loc_140090A55
0x140090ae9  mov     rbp, rdx
0x140090aec  jmp     loc_140090A55
0x140090af1  xor     ecx, ecx
0x140090af3  xor     edi, edi
0x140090af5  jmp     loc_140090A55
0x140090afa  cmp     ecx, ebx
0x140090afc  jnz     short loc_140090A9A
0x140090afe  mov     eax, [rsp+48h+var_28+4]
0x140090b02  cmp     [rsi+44h], eax
0x140090b05  jnz     short loc_140090A9A
0x140090b07  jmp     loc_140090A88
0x140096202  test    rax, rax
0x140096205  jz      loc_140090A9A
0x14009620b  lea     r9, [rsp+48h+SameSuppliedIdentity]; SameSuppliedIdentity
0x140096210  mov     rdx, rax; AuthIdentity2
0x140096213  lea     r8, [rsp+48h+SameSuppliedUser]; SameSuppliedUser
0x140096218  mov     rcx, rbp; AuthIdentity1
0x14009621b  call    cs:__imp_SspiCompareAuthIdentities
0x140096222  nop     dword ptr [rax+rax+00h]
0x140096227  test    eax, eax
0x140096229  jz      short loc_140096276
0x14009622b  mov     rcx, cs:WPP_GLOBAL_Control
0x140096232  lea     rdx, WPP_GLOBAL_Control
0x140096239  cmp     rcx, rdx
0x14009623c  jz      loc_140090A9A
0x140096242  mov     edx, [rcx+2Ch]
0x140096245  test    dl, 2
0x140096248  jz      loc_140090A9A
0x14009624e  cmp     byte ptr [rcx+29h], 2
0x140096252  jb      loc_140090A9A
0x140096258  mov     rcx, [rcx+18h]
0x14009625c  lea     r8, WPP_48980f24b3dc39b8aaca68646dc5bd2a_Traceguids
0x140096263  mov     edx, 0Ah
0x140096268  mov     r9d, eax
0x14009626b  call    WPP_SF_d
0x140096270  nop
0x140096271  jmp     loc_140090A9A
0x140096276  cmp     [rsp+48h+SameSuppliedUser], 0
0x14009627b  jz      loc_140090A9A
0x140096281  cmp     [rsp+48h+SameSuppliedIdentity], 0
0x140096286  jnz     loc_140090ACC
0x14009628c  jmp     loc_140090A9A
```
