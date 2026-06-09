# MupiCheckForMailslotRequest

- ea: `0x14001a0d8`
- end: `0x14001a360`
- name: `MupiCheckForMailslotRequest`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a370`

## callees

- `0x140001040`
- `0x140002614`
- `0x140002e74`
- `0x14000f21c`
- `0x1400120a8`
- `0x140016f88`
- `0x1400194a0`
- `0x14001a0d8`
- `0x14001cb80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001a1a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a265`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a1a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a265`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a1d8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a1d8`

## pseudocode

```c
__int64 __fastcall MupiCheckForMailslotRequest(__int64 a1, __int64 *a2, char a3)
{
  int v3; // r9d
  unsigned int v6; // edi
  unsigned int v7; // r9d
  _WORD *v8; // rdx
  __int64 MatchingChar; // rax
  __int64 v10; // rdx
  int v11; // r9d
  _WORD *v12; // rbx
  unsigned int v13; // r9d
  __int64 v14; // rax
  __int64 v15; // r9
  __int64 v16; // r13
  USHORT v17; // r15
  char v18; // al
  __int16 v19; // r12
  __int64 v20; // r15
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-10h] BYREF
  __int64 v27; // [rsp+90h] [rbp+40h]

  v3 = *(unsigned __int16 *)(a1 + 88) >> 1;
  v6 = -1073741802;
  DestinationString = 0;
  v7 = v3 - 1;
  if ( !v7 )
    goto LABEL_19;
  v8 = (_WORD *)(*(_QWORD *)(a1 + 96) + 2LL);
  if ( *v8 == 92 )
    goto LABEL_19;
  if ( *v8 == 59 )
    goto LABEL_19;
  MatchingChar = MupFindMatchingChar(*(_QWORD *)(a1 + 96) + 2LL, v8, v7);
  if ( !MatchingChar )
    goto LABEL_19;
  v12 = (_WORD *)(MatchingChar + 2);
  v27 = MatchingChar + 2;
  v13 = v11 - ((MatchingChar + 2 - v10) >> 1);
  if ( !v13 || *v12 == 59 )
    goto LABEL_19;
  v14 = MupFindMatchingChar(v12, v10, v13);
  v16 = v14;
  if ( v14 )
    v15 = (v14 - (__int64)v12) >> 1;
  v17 = 2 * v15;
  if ( (unsigned int)(2 * v15) > 0xFFFF )
    goto LABEL_19;
  RtlInitUnicodeString(&DestinationString, 0);
  *(_DWORD *)((char *)&DestinationString.Buffer + 2) = *(_DWORD *)((char *)&v27 + 2);
  HIWORD(DestinationString.Buffer) = HIWORD(v27);
  DestinationString.MaximumLength = v17;
  DestinationString.Length = v17;
  LOWORD(DestinationString.Buffer) = (_WORD)v12;
  if ( RtlCompareUnicodeString(&MupiMailSlotName, &DestinationString, 1u) )
    goto LABEL_19;
  MupiTryStartPoliciesKeyRegistryWatcher();
  v18 = MupEnableMailslotsByPolicy;
  v19 = *(_WORD *)(a1 + 88);
  v20 = *(_QWORD *)(a1 + 96);
  String2 = 0;
  if ( (_BYTE)MupEnableMailslotsByPolicy == 2 )
    v18 = MupEnableMailslots;
  if ( !v18 )
  {
    v6 = -1067646971;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids, 3227320325LL);
    }
    if ( v16 )
    {
      RtlInitUnicodeString(&String2, 0);
      *(_DWORD *)((char *)&String2.Buffer + 2) = (unsigned __int64)(v16 + 2) >> 16;
      HIWORD(String2.Buffer) = (unsigned __int64)(v16 + 2) >> 48;
      String2.Length = v19 + v20 - (v16 + 2);
      String2.MaximumLength = String2.Length;
      LOWORD(String2.Buffer) = v16 + 2;
      MupiWriteTelemetryFailedMailslotName(&String2);
    }
LABEL_19:
    *a2 = 0;
    goto LABEL_20;
  }
  v23 = MupAllocFileContext(0);
  if ( v23 )
  {
    LOBYTE(v22) = a3;
    v24 = MupAcquireMailslotProvider(v22);
    if ( v24 )
    {
      *(_QWORD *)(v23 + 168) = v24;
      v6 = 0;
      *(_DWORD *)(v23 + 160) = 1;
      *(_DWORD *)(v23 + 216) = 0;
      *(_QWORD *)(v23 + 144) = a1;
      *a2 = v23;
    }
    else
    {
      *a2 = 0;
      MupReleaseFileContext((PVOID)v23);
      v6 = -1073741823;
    }
  }
  else
  {
    v6 = -1073741670;
    *a2 = 0;
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids, a1, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x14001a0d8  mov     [rsp-38h+arg_8], rbx
0x14001a0dd  mov     [rsp-38h+arg_10], r8b
0x14001a0e2  push    rbp
0x14001a0e3  push    rsi
0x14001a0e4  push    rdi
0x14001a0e5  push    r12
0x14001a0e7  push    r13
0x14001a0e9  push    r14
0x14001a0eb  push    r15
0x14001a0ed  mov     rbp, rsp
0x14001a0f0  sub     rsp, 50h
0x14001a0f4  movzx   r9d, word ptr [rcx+58h]
0x14001a0f9  xorps   xmm0, xmm0
0x14001a0fc  shr     r9d, 1
0x14001a0ff  mov     rsi, rdx
0x14001a102  mov     r14, rcx
0x14001a105  mov     edi, 0C0000016h
0x14001a10a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001a10e  sub     r9d, 1
0x14001a112  jz      loc_14001A29E
0x14001a118  mov     rdx, [rcx+60h]
0x14001a11c  add     rdx, 2
0x14001a120  movzx   eax, word ptr [rdx]
0x14001a123  cmp     ax, 5Ch ; '\'
0x14001a127  jz      loc_14001A29E
0x14001a12d  cmp     ax, 3Bh ; ';'
0x14001a131  jz      loc_14001A29E
0x14001a137  mov     r8d, r9d
0x14001a13a  mov     rcx, rdx
0x14001a13d  call    MupFindMatchingChar
0x14001a142  test    rax, rax
0x14001a145  jz      loc_14001A29E
0x14001a14b  lea     rbx, [rax+2]
0x14001a14f  mov     rax, rbx
0x14001a152  mov     [rbp+arg_0], rbx
0x14001a156  sub     rax, rdx
0x14001a159  sar     rax, 1
0x14001a15c  sub     r9d, eax
0x14001a15f  jz      loc_14001A29E
0x14001a165  cmp     word ptr [rbx], 3Bh ; ';'
0x14001a169  jz      loc_14001A29E
0x14001a16f  mov     r8d, r9d
0x14001a172  mov     rcx, rbx
0x14001a175  call    MupFindMatchingChar
0x14001a17a  mov     r13, rax
0x14001a17d  test    rax, rax
0x14001a180  jz      short loc_14001A18B
0x14001a182  mov     r9, rax
0x14001a185  sub     r9, rbx
0x14001a188  sar     r9, 1
0x14001a18b  lea     r15d, [r9+r9]
0x14001a18f  cmp     r15d, 0FFFFh
0x14001a196  ja      loc_14001A29E
0x14001a19c  xor     edx, edx; SourceString
0x14001a19e  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001a1a2  call    cs:__imp_RtlInitUnicodeString
0x14001a1a9  nop     dword ptr [rax+rax+00h]
0x14001a1ae  mov     eax, dword ptr [rbp+arg_0+2]
0x14001a1b1  lea     rdx, [rbp+DestinationString]; String2
0x14001a1b5  mov     dword ptr [rbp+DestinationString.Buffer+2], eax
0x14001a1b8  lea     rcx, MupiMailSlotName; String1
0x14001a1bf  movzx   eax, word ptr [rbp+arg_0+6]
0x14001a1c3  mov     r8b, 1; CaseInSensitive
0x14001a1c6  mov     word ptr [rbp+DestinationString.Buffer+6], ax
0x14001a1ca  mov     [rbp+DestinationString.MaximumLength], r15w
0x14001a1cf  mov     [rbp+DestinationString.Length], r15w
0x14001a1d4  mov     word ptr [rbp+DestinationString.Buffer], bx
0x14001a1d8  call    cs:__imp_RtlCompareUnicodeString
0x14001a1df  nop     dword ptr [rax+rax+00h]
0x14001a1e4  test    eax, eax
0x14001a1e6  jnz     loc_14001A29E
0x14001a1ec  call    MupiTryStartPoliciesKeyRegistryWatcher
0x14001a1f1  mov     al, byte ptr cs:MupEnableMailslotsByPolicy
0x14001a1f7  xorps   xmm0, xmm0
0x14001a1fa  movzx   r12d, word ptr [r14+58h]
0x14001a1ff  mov     r15, [r14+60h]
0x14001a203  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001a207  cmp     al, 2
0x14001a209  jnz     short loc_14001A211
0x14001a20b  mov     al, cs:MupEnableMailslots
0x14001a211  test    al, al
0x14001a213  jnz     loc_14001A2F8
0x14001a219  mov     edi, 0C05D0005h
0x14001a21e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a225  lea     rax, WPP_GLOBAL_Control
0x14001a22c  cmp     rcx, rax
0x14001a22f  jz      short loc_14001A252
0x14001a231  test    dword ptr [rcx+2Ch], 4000000h
0x14001a238  jz      short loc_14001A252
0x14001a23a  mov     rcx, [rcx+18h]
0x14001a23e  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a245  mov     edx, 1Dh
0x14001a24a  mov     r9d, edi
0x14001a24d  call    WPP_SF_d
0x14001a252  test    r13, r13
0x14001a255  jz      short loc_14001A29E
0x14001a257  lea     rbx, [r13+2]
0x14001a25b  xor     edx, edx; SourceString
0x14001a25d  lea     rcx, [rbp+String2]; DestinationString
0x14001a261  mov     [rbp+arg_0], rbx
0x14001a265  call    cs:__imp_RtlInitUnicodeString
0x14001a26c  nop     dword ptr [rax+rax+00h]
0x14001a271  mov     eax, dword ptr [rbp+arg_0+2]
0x14001a274  lea     rcx, [rbp+String2]; String2
0x14001a278  sub     r15w, bx
0x14001a27c  mov     dword ptr [rbp+String2.Buffer+2], eax
0x14001a27f  movzx   eax, word ptr [rbp+arg_0+6]
0x14001a283  add     r15w, r12w
0x14001a287  mov     word ptr [rbp+String2.Buffer+6], ax
0x14001a28b  mov     [rbp+String2.Length], r15w
0x14001a290  mov     [rbp+String2.MaximumLength], r15w
0x14001a295  mov     word ptr [rbp+String2.Buffer], bx
0x14001a299  call    MupiWriteTelemetryFailedMailslotName
0x14001a29e  mov     qword ptr [rsi], 0
0x14001a2a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2ac  lea     rax, WPP_GLOBAL_Control
0x14001a2b3  cmp     rcx, rax
0x14001a2b6  jz      short loc_14001A2DD
0x14001a2b8  test    dword ptr [rcx+2Ch], 4000000h
0x14001a2bf  jz      short loc_14001A2DD
0x14001a2c1  mov     rcx, [rcx+18h]
0x14001a2c5  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a2cc  mov     edx, 1Eh
0x14001a2d1  mov     [rsp+50h+var_30], edi
0x14001a2d5  mov     r9, r14
0x14001a2d8  call    WPP_SF_qD
0x14001a2dd  mov     rbx, [rsp+50h+arg_8]
0x14001a2e5  mov     eax, edi
0x14001a2e7  add     rsp, 50h
0x14001a2eb  pop     r15
0x14001a2ed  pop     r14
0x14001a2ef  pop     r13
0x14001a2f1  pop     r12
0x14001a2f3  pop     rdi
0x14001a2f4  pop     rsi
0x14001a2f5  pop     rbp
0x14001a2f6  retn
0x14001a2f8  xor     ecx, ecx
0x14001a2fa  call    MupAllocFileContext
0x14001a2ff  xor     r15d, r15d
0x14001a302  mov     rbx, rax
0x14001a305  test    rax, rax
0x14001a308  jnz     short loc_14001A314
0x14001a30a  mov     edi, 0C000009Ah
0x14001a30f  mov     [rsi], r15
0x14001a312  jmp     short loc_14001A2A5
0x14001a314  mov     cl, [rbp+arg_10]
0x14001a317  call    MupAcquireMailslotProvider
0x14001a31c  test    rax, rax
0x14001a31f  jnz     short loc_14001A336
0x14001a321  mov     rcx, rbx; P
0x14001a324  mov     [rsi], r15
0x14001a327  call    MupReleaseFileContext
0x14001a32c  mov     edi, 0C0000001h
0x14001a331  jmp     loc_14001A2A5
0x14001a336  mov     [rbx+0A8h], rax
0x14001a33d  mov     edi, r15d
0x14001a340  mov     dword ptr [rbx+0A0h], 1
0x14001a34a  mov     [rbx+0D8h], r15d
0x14001a351  mov     [rbx+90h], r14
0x14001a358  mov     [rsi], rbx
0x14001a35b  jmp     loc_14001A2A5
```
