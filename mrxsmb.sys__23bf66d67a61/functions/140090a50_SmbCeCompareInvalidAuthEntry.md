# SmbCeCompareInvalidAuthEntry

- ea: `0x140090a50`
- end: `0x140090b5c`
- name: `SmbCeCompareInvalidAuthEntry`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140090580`
- `0x140090750`

## callees

- `0x14003838c`
- `0x140090a50`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140090ab8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140090ab8`
- `ksecdd!SspiCompareAuthIdentities` at `0x14009626b`
- `ksecdd!SspiCompareAuthIdentities` at `0x14009626b`

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
0x140090a50  mov     [rsp+arg_10], rbx
0x140090a55  push    rbp
0x140090a56  push    rsi
0x140090a57  push    rdi
0x140090a58  sub     rsp, 30h
0x140090a5c  xor     ebp, ebp
0x140090a5e  xor     ebx, ebx
0x140090a60  mov     [rsp+48h+SameSuppliedIdentity], bpl
0x140090a65  mov     rsi, rcx
0x140090a68  mov     [rsp+48h+SameSuppliedUser], bpl
0x140090a6d  mov     qword ptr [rsp+48h+var_28], rbx
0x140090a72  mov     [rsp+48h+arg_18], rbx
0x140090a77  test    rdx, rdx
0x140090a7a  jz      short loc_140090AFA
0x140090a7c  mov     rcx, [rdx+180h]
0x140090a83  mov     rax, [rdx+80h]
0x140090a8a  mov     rbx, [rdx+68h]
0x140090a8e  mov     rdi, [rdx+60h]
0x140090a92  mov     [rsp+48h+arg_18], rdi
0x140090a97  mov     qword ptr [rsp+48h+var_28], rbx
0x140090a9c  test    rax, rax
0x140090a9f  jnz     loc_140090B2C
0x140090aa5  mov     eax, [rsi+20h]
0x140090aa8  cmp     [rcx+48h], eax
0x140090aab  jnz     short loc_140090AEA
0x140090aad  lea     rdx, [rcx+50h]; String2
0x140090ab1  mov     r8b, 1; CaseInSensitive
0x140090ab4  lea     rcx, [rsi+10h]; String1
0x140090ab8  call    cs:__imp_RtlCompareUnicodeString
0x140090abf  nop     dword ptr [rax+rax+00h]
0x140090ac4  test    eax, eax
0x140090ac6  jnz     short loc_140090AEA
0x140090ac8  mov     ecx, [rsi+40h]
0x140090acb  cmp     ecx, edi
0x140090acd  jnz     short loc_140090B4A
0x140090acf  mov     eax, dword ptr [rsp+48h+arg_18+4]
0x140090ad3  cmp     [rsi+44h], eax
0x140090ad6  jnz     short loc_140090B4A
0x140090ad8  mov     rax, [rsi+38h]
0x140090adc  test    rbp, rbp
0x140090adf  jnz     loc_140096252
0x140090ae5  test    rax, rax
0x140090ae8  jz      short loc_140090B1C
0x140090aea  xor     al, al
0x140090aec  mov     rbx, [rsp+48h+arg_10]
0x140090af1  add     rsp, 30h
0x140090af5  pop     rdi
0x140090af6  pop     rsi
0x140090af7  pop     rbp
0x140090af8  retn
0x140090afa  test    r8, r8
0x140090afd  jz      short loc_140090B41
0x140090aff  mov     rax, [r8+20h]
0x140090b03  mov     rbx, [r8+50h]
0x140090b07  mov     rdi, [r8+48h]
0x140090b0b  mov     rcx, [rax+20h]
0x140090b0f  mov     rax, [r8+68h]
0x140090b13  mov     rcx, [rcx+20h]
0x140090b17  jmp     loc_140090A92
0x140090b1c  mov     rbx, [rsp+48h+arg_10]
0x140090b21  mov     al, 1
0x140090b23  add     rsp, 30h
0x140090b27  pop     rdi
0x140090b28  pop     rsi
0x140090b29  pop     rbp
0x140090b2a  retn
0x140090b2c  mov     rdx, [rax+8]
0x140090b30  test    rdx, rdx
0x140090b33  jz      loc_140090AA5
0x140090b39  mov     rbp, rdx
0x140090b3c  jmp     loc_140090AA5
0x140090b41  xor     ecx, ecx
0x140090b43  xor     edi, edi
0x140090b45  jmp     loc_140090AA5
0x140090b4a  cmp     ecx, ebx
0x140090b4c  jnz     short loc_140090AEA
0x140090b4e  mov     eax, [rsp+48h+var_28+4]
0x140090b52  cmp     [rsi+44h], eax
0x140090b55  jnz     short loc_140090AEA
0x140090b57  jmp     loc_140090AD8
0x140096252  test    rax, rax
0x140096255  jz      loc_140090AEA
0x14009625b  lea     r9, [rsp+48h+SameSuppliedIdentity]; SameSuppliedIdentity
0x140096260  mov     rdx, rax; AuthIdentity2
0x140096263  lea     r8, [rsp+48h+SameSuppliedUser]; SameSuppliedUser
0x140096268  mov     rcx, rbp; AuthIdentity1
0x14009626b  call    cs:__imp_SspiCompareAuthIdentities
0x140096272  nop     dword ptr [rax+rax+00h]
0x140096277  test    eax, eax
0x140096279  jz      short loc_1400962C6
0x14009627b  mov     rcx, cs:WPP_GLOBAL_Control
0x140096282  lea     rdx, WPP_GLOBAL_Control
0x140096289  cmp     rcx, rdx
0x14009628c  jz      loc_140090AEA
0x140096292  mov     edx, [rcx+2Ch]
0x140096295  test    dl, 2
0x140096298  jz      loc_140090AEA
0x14009629e  cmp     byte ptr [rcx+29h], 2
0x1400962a2  jb      loc_140090AEA
0x1400962a8  mov     rcx, [rcx+18h]
0x1400962ac  lea     r8, WPP_48980f24b3dc39b8aaca68646dc5bd2a_Traceguids
0x1400962b3  mov     edx, 0Ah
0x1400962b8  mov     r9d, eax
0x1400962bb  call    WPP_SF_d
0x1400962c0  nop
0x1400962c1  jmp     loc_140090AEA
0x1400962c6  cmp     [rsp+48h+SameSuppliedUser], 0
0x1400962cb  jz      loc_140090AEA
0x1400962d1  cmp     [rsp+48h+SameSuppliedIdentity], 0
0x1400962d6  jnz     loc_140090B1C
0x1400962dc  jmp     loc_140090AEA
```
