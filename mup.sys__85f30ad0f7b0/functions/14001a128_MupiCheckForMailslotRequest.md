# MupiCheckForMailslotRequest

- ea: `0x14001a128`
- end: `0x14001a3b0`
- name: `MupiCheckForMailslotRequest`
- size: `648`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a3c0`

## callees

- `0x140001040`
- `0x140002614`
- `0x140002e74`
- `0x14000f21c`
- `0x1400120f8`
- `0x140016fd8`
- `0x1400194f0`
- `0x14001a128`
- `0x14001cbd0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001a1f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a2b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a1f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a2b5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a228`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a228`

## pseudocode

```c
__int64 __fastcall MupiCheckForMailslotRequest(__int64 a1, _QWORD *a2, char a3)
{
  int v3; // r9d
  unsigned int v6; // edi
  unsigned int v7; // r9d
  _WORD *v8; // rdx
  _WORD *MatchingChar; // rax
  __int64 v10; // rdx
  int v11; // r9d
  _WORD *v12; // rbx
  unsigned int v13; // r9d
  _WORD *v14; // rax
  __int64 v15; // r9
  _WORD *v16; // r13
  USHORT v17; // r15
  char v18; // al
  __int16 v19; // r12
  __int64 v20; // r15
  __int64 v22; // rcx
  _WORD *v23; // rbx
  __int64 v24; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-10h] BYREF
  _WORD *v27; // [rsp+90h] [rbp+40h]

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
  MatchingChar = MupFindMatchingChar((_WORD *)(*(_QWORD *)(a1 + 96) + 2LL), (__int64)v8, v7);
  if ( !MatchingChar )
    goto LABEL_19;
  v12 = MatchingChar + 1;
  v27 = MatchingChar + 1;
  v13 = v11 - (((__int64)MatchingChar - v10 + 2) >> 1);
  if ( !v13 || *v12 == 59 )
    goto LABEL_19;
  v14 = MupFindMatchingChar(v12, v10, v13);
  v16 = v14;
  if ( v14 )
    v15 = v14 - v12;
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
      *(_DWORD *)((char *)&String2.Buffer + 2) = (unsigned __int64)(v16 + 1) >> 16;
      HIWORD(String2.Buffer) = (unsigned __int64)(v16 + 1) >> 48;
      String2.Length = v19 + v20 - ((_WORD)v16 + 2);
      String2.MaximumLength = String2.Length;
      LOWORD(String2.Buffer) = (_WORD)v16 + 2;
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
      *((_QWORD *)v23 + 21) = v24;
      v6 = 0;
      *((_DWORD *)v23 + 40) = 1;
      *((_DWORD *)v23 + 54) = 0;
      *((_QWORD *)v23 + 18) = a1;
      *a2 = v23;
    }
    else
    {
      *a2 = 0;
      MupReleaseFileContext((char *)v23);
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
0x14001a128  mov     [rsp-38h+arg_8], rbx
0x14001a12d  mov     [rsp-38h+arg_10], r8b
0x14001a132  push    rbp
0x14001a133  push    rsi
0x14001a134  push    rdi
0x14001a135  push    r12
0x14001a137  push    r13
0x14001a139  push    r14
0x14001a13b  push    r15
0x14001a13d  mov     rbp, rsp
0x14001a140  sub     rsp, 50h
0x14001a144  movzx   r9d, word ptr [rcx+58h]
0x14001a149  xorps   xmm0, xmm0
0x14001a14c  shr     r9d, 1
0x14001a14f  mov     rsi, rdx
0x14001a152  mov     r14, rcx
0x14001a155  mov     edi, 0C0000016h
0x14001a15a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001a15e  sub     r9d, 1
0x14001a162  jz      loc_14001A2EE
0x14001a168  mov     rdx, [rcx+60h]
0x14001a16c  add     rdx, 2
0x14001a170  movzx   eax, word ptr [rdx]
0x14001a173  cmp     ax, 5Ch ; '\'
0x14001a177  jz      loc_14001A2EE
0x14001a17d  cmp     ax, 3Bh ; ';'
0x14001a181  jz      loc_14001A2EE
0x14001a187  mov     r8d, r9d
0x14001a18a  mov     rcx, rdx
0x14001a18d  call    MupFindMatchingChar
0x14001a192  test    rax, rax
0x14001a195  jz      loc_14001A2EE
0x14001a19b  lea     rbx, [rax+2]
0x14001a19f  mov     rax, rbx
0x14001a1a2  mov     [rbp+arg_0], rbx
0x14001a1a6  sub     rax, rdx
0x14001a1a9  sar     rax, 1
0x14001a1ac  sub     r9d, eax
0x14001a1af  jz      loc_14001A2EE
0x14001a1b5  cmp     word ptr [rbx], 3Bh ; ';'
0x14001a1b9  jz      loc_14001A2EE
0x14001a1bf  mov     r8d, r9d
0x14001a1c2  mov     rcx, rbx
0x14001a1c5  call    MupFindMatchingChar
0x14001a1ca  mov     r13, rax
0x14001a1cd  test    rax, rax
0x14001a1d0  jz      short loc_14001A1DB
0x14001a1d2  mov     r9, rax
0x14001a1d5  sub     r9, rbx
0x14001a1d8  sar     r9, 1
0x14001a1db  lea     r15d, [r9+r9]
0x14001a1df  cmp     r15d, 0FFFFh
0x14001a1e6  ja      loc_14001A2EE
0x14001a1ec  xor     edx, edx; SourceString
0x14001a1ee  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001a1f2  call    cs:__imp_RtlInitUnicodeString
0x14001a1f9  nop     dword ptr [rax+rax+00h]
0x14001a1fe  mov     eax, dword ptr [rbp+arg_0+2]
0x14001a201  lea     rdx, [rbp+DestinationString]; String2
0x14001a205  mov     dword ptr [rbp+DestinationString.Buffer+2], eax
0x14001a208  lea     rcx, MupiMailSlotName; String1
0x14001a20f  movzx   eax, word ptr [rbp+arg_0+6]
0x14001a213  mov     r8b, 1; CaseInSensitive
0x14001a216  mov     word ptr [rbp+DestinationString.Buffer+6], ax
0x14001a21a  mov     [rbp+DestinationString.MaximumLength], r15w
0x14001a21f  mov     [rbp+DestinationString.Length], r15w
0x14001a224  mov     word ptr [rbp+DestinationString.Buffer], bx
0x14001a228  call    cs:__imp_RtlCompareUnicodeString
0x14001a22f  nop     dword ptr [rax+rax+00h]
0x14001a234  test    eax, eax
0x14001a236  jnz     loc_14001A2EE
0x14001a23c  call    MupiTryStartPoliciesKeyRegistryWatcher
0x14001a241  mov     al, byte ptr cs:MupEnableMailslotsByPolicy
0x14001a247  xorps   xmm0, xmm0
0x14001a24a  movzx   r12d, word ptr [r14+58h]
0x14001a24f  mov     r15, [r14+60h]
0x14001a253  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001a257  cmp     al, 2
0x14001a259  jnz     short loc_14001A261
0x14001a25b  mov     al, cs:MupEnableMailslots
0x14001a261  test    al, al
0x14001a263  jnz     loc_14001A348
0x14001a269  mov     edi, 0C05D0005h
0x14001a26e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a275  lea     rax, WPP_GLOBAL_Control
0x14001a27c  cmp     rcx, rax
0x14001a27f  jz      short loc_14001A2A2
0x14001a281  test    dword ptr [rcx+2Ch], 4000000h
0x14001a288  jz      short loc_14001A2A2
0x14001a28a  mov     rcx, [rcx+18h]
0x14001a28e  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a295  mov     edx, 1Dh
0x14001a29a  mov     r9d, edi
0x14001a29d  call    WPP_SF_d
0x14001a2a2  test    r13, r13
0x14001a2a5  jz      short loc_14001A2EE
0x14001a2a7  lea     rbx, [r13+2]
0x14001a2ab  xor     edx, edx; SourceString
0x14001a2ad  lea     rcx, [rbp+String2]; DestinationString
0x14001a2b1  mov     [rbp+arg_0], rbx
0x14001a2b5  call    cs:__imp_RtlInitUnicodeString
0x14001a2bc  nop     dword ptr [rax+rax+00h]
0x14001a2c1  mov     eax, dword ptr [rbp+arg_0+2]
0x14001a2c4  lea     rcx, [rbp+String2]; String2
0x14001a2c8  sub     r15w, bx
0x14001a2cc  mov     dword ptr [rbp+String2.Buffer+2], eax
0x14001a2cf  movzx   eax, word ptr [rbp+arg_0+6]
0x14001a2d3  add     r15w, r12w
0x14001a2d7  mov     word ptr [rbp+String2.Buffer+6], ax
0x14001a2db  mov     [rbp+String2.Length], r15w
0x14001a2e0  mov     [rbp+String2.MaximumLength], r15w
0x14001a2e5  mov     word ptr [rbp+String2.Buffer], bx
0x14001a2e9  call    MupiWriteTelemetryFailedMailslotName
0x14001a2ee  mov     qword ptr [rsi], 0
0x14001a2f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2fc  lea     rax, WPP_GLOBAL_Control
0x14001a303  cmp     rcx, rax
0x14001a306  jz      short loc_14001A32D
0x14001a308  test    dword ptr [rcx+2Ch], 4000000h
0x14001a30f  jz      short loc_14001A32D
0x14001a311  mov     rcx, [rcx+18h]
0x14001a315  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a31c  mov     edx, 1Eh
0x14001a321  mov     [rsp+50h+var_30], edi
0x14001a325  mov     r9, r14
0x14001a328  call    WPP_SF_qD
0x14001a32d  mov     rbx, [rsp+50h+arg_8]
0x14001a335  mov     eax, edi
0x14001a337  add     rsp, 50h
0x14001a33b  pop     r15
0x14001a33d  pop     r14
0x14001a33f  pop     r13
0x14001a341  pop     r12
0x14001a343  pop     rdi
0x14001a344  pop     rsi
0x14001a345  pop     rbp
0x14001a346  retn
0x14001a348  xor     ecx, ecx
0x14001a34a  call    MupAllocFileContext
0x14001a34f  xor     r15d, r15d
0x14001a352  mov     rbx, rax
0x14001a355  test    rax, rax
0x14001a358  jnz     short loc_14001A364
0x14001a35a  mov     edi, 0C000009Ah
0x14001a35f  mov     [rsi], r15
0x14001a362  jmp     short loc_14001A2F5
0x14001a364  mov     cl, [rbp+arg_10]
0x14001a367  call    MupAcquireMailslotProvider
0x14001a36c  test    rax, rax
0x14001a36f  jnz     short loc_14001A386
0x14001a371  mov     rcx, rbx; P
0x14001a374  mov     [rsi], r15
0x14001a377  call    MupReleaseFileContext
0x14001a37c  mov     edi, 0C0000001h
0x14001a381  jmp     loc_14001A2F5
0x14001a386  mov     [rbx+0A8h], rax
0x14001a38d  mov     edi, r15d
0x14001a390  mov     dword ptr [rbx+0A0h], 1
0x14001a39a  mov     [rbx+0D8h], r15d
0x14001a3a1  mov     [rbx+90h], r14
0x14001a3a8  mov     [rsi], rbx
0x14001a3ab  jmp     loc_14001A2F5
```
