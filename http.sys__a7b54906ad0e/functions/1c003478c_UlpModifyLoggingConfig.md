# UlpModifyLoggingConfig

- ea: `0x1c003478c`
- end: `0x1c0034b05`
- name: `UlpModifyLoggingConfig`
- size: `889`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1c00325a8`

## callees

- `0x1c0033ed0`
- `0x1c003478c`
- `0x1c011f454`
- `0x1c011f548`

## import_xrefs

- `ntoskrnl!SeTokenType` at `0x1c0034928`
- `ntoskrnl!SeTokenType` at `0x1c0034928`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1c0034944`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1c0034944`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1c0034952`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1c0034952`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c003490a`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c0034ac6`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c003490a`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c0034ac6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1c00348da`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1c0034a7a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1c00348da`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1c0034a7a`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0034815`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0034815`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0034967`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c003499b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0034aad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0034967`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c003499b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0034aad`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0034ad9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0034ad9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00347e2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00347e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0034ae5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0034ae5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00347c8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00347c8`

## pseudocode

```c
__int64 __fastcall UlpModifyLoggingConfig(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  char v4; // r12
  __int64 v5; // r14
  int v6; // ebp
  __int64 v7; // r13
  _OWORD *PoolWithTagPriority; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  ULONG v15; // eax
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rcx
  TOKEN_TYPE v19; // eax
  void *v20; // rcx
  void *v21; // rcx
  int v22; // r8d
  int v23; // ecx
  int v24; // eax
  unsigned int v25; // ecx
  int v26; // r9d
  __int64 v28; // [rsp+90h] [rbp+8h] BYREF
  char v29; // [rsp+98h] [rbp+10h] BYREF
  __int64 v30; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v31; // [rsp+A8h] [rbp+20h]

  v28 = a1;
  v3 = *(_QWORD *)(a2 + 120);
  v4 = 0;
  v5 = 0;
  v30 = 0;
  v6 = 0;
  v31 = 0;
  v7 = 0;
  LODWORD(v28) = 0;
  PoolWithTagPriority = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v3 + 8, 0);
  if ( (*(_DWORD *)(a3 + 4) & 0x10) != 0 )
  {
    v4 = 1;
  }
  else
  {
    if ( *(_QWORD *)(a3 + 96) )
    {
      PoolWithTagPriority = ExAllocatePoolWithTagPriority((POOL_TYPE)512, 0x48u, 0x53436C55u, LowPoolPriority);
      if ( !PoolWithTagPriority )
      {
        v6 = -1073741670;
        goto LABEL_43;
      }
      v11 = *(_QWORD *)(a3 + 96);
      *PoolWithTagPriority = *(_OWORD *)v11;
      PoolWithTagPriority[1] = *(_OWORD *)(v11 + 16);
      PoolWithTagPriority[2] = *(_OWORD *)(v11 + 32);
      PoolWithTagPriority[3] = *(_OWORD *)(v11 + 48);
      *((_QWORD *)PoolWithTagPriority + 8) = *(_QWORD *)(v11 + 64);
    }
    v12 = *(_QWORD *)(a3 + 88);
    if ( v12 )
    {
      v13 = UlpCaptureSecurityDescriptor(v12, 0, &v30, &v29);
      v5 = v30;
      v6 = v13;
      if ( v13 < 0 )
        goto LABEL_39;
    }
  }
  v15 = *(unsigned __int16 *)(a3 + 8);
  if ( (_WORD)v15 )
  {
    v6 = UlpCaptureSoftwareDirective(*(PCWCH *)(a3 + 16), v15, (__int64)&v28);
    if ( v6 < 0 )
    {
LABEL_39:
      if ( PoolWithTagPriority )
        ExFreePoolWithTag(PoolWithTagPriority, 0);
      if ( v5 )
      {
        LOBYTE(v14) = 1;
        SeReleaseSecurityDescriptor(v5, 0, v14);
      }
      goto LABEL_43;
    }
    v7 = v31;
  }
  if ( !RtlEqualUnicodeString((PCUNICODE_STRING)(a3 + 32), (PCUNICODE_STRING)(a2 + 40), 1u) )
    *(_DWORD *)(v3 + 152) = *(_DWORD *)(v3 + 152) & 0xFFFFFFBD | 2;
  v17 = *(_QWORD *)(v3 + 120);
  if ( v17 )
  {
    LOBYTE(v16) = 1;
    SeReleaseSecurityDescriptor(v17, 0, v16);
  }
  v18 = *(_QWORD *)(v3 + 136);
  if ( v18 )
  {
    v19 = SeTokenType(*(PACCESS_TOKEN *)(v18 + 16));
    v20 = *(void **)(*(_QWORD *)(v3 + 136) + 16LL);
    if ( v19 == TokenPrimary )
      PsDereferencePrimaryToken(v20);
    else
      PsDereferenceImpersonationToken(v20);
    ExFreePoolWithTag(*(PVOID *)(v3 + 136), 0);
  }
  v21 = *(void **)(v3 + 16);
  *(_BYTE *)(v3 + 128) = v4;
  *(_QWORD *)(v3 + 120) = v5;
  v5 = 0;
  *(_QWORD *)(v3 + 136) = PoolWithTagPriority;
  PoolWithTagPriority = 0;
  if ( v21 )
    ExFreePoolWithTag(v21, 0);
  *(_DWORD *)(v3 + 24) = v28;
  *(_QWORD *)(v3 + 16) = v7;
  v22 = *(_DWORD *)(a3 + 56);
  *(_DWORD *)(v3 + 80) = v22;
  *(_DWORD *)(v3 + 84) = *(_DWORD *)(a3 + 76);
  *(_DWORD *)(v3 + 88) = *(_DWORD *)(a3 + 80);
  *(_DWORD *)(v3 + 92) = *(_DWORD *)(a3 + 60);
  *(_BYTE *)(v3 + 144) = *(_BYTE *)a2 & 1;
  v23 = *(_DWORD *)(v3 + 152) ^ (*(_DWORD *)(v3 + 152) ^ (*(_DWORD *)(a3 + 4) << 9)) & 0x200;
  *(_DWORD *)(v3 + 152) = v23;
  if ( (*(_DWORD *)(a3 + 4) & 2) == 0 || (v24 = 1024, v22 == 3) )
    v24 = 0;
  v25 = v24 | v23 & 0xFFFFFBFF;
  *(_DWORD *)(v3 + 152) = v25;
  if ( *(_DWORD *)(a3 + 56) != *(_DWORD *)(a2 + 64)
    || *(_DWORD *)(a3 + 76) != *(_DWORD *)(a2 + 84)
    || (v26 = *(_DWORD *)(a3 + 4), (((unsigned __int8)v26 ^ *(_BYTE *)(a2 + 12)) & 1) != 0)
    || (((unsigned __int8)v26 ^ (unsigned __int8)*(_DWORD *)(a2 + 12)) & 2) != 0 )
  {
    v25 |= 6u;
    *(_DWORD *)(v3 + 152) = v25;
  }
  if ( v22 )
  {
    if ( (unsigned int)(v22 - 1) <= 1 )
      *(_DWORD *)(v3 + 152) = v25 | 0x10;
  }
  else if ( *(_DWORD *)(a3 + 60) != *(_DWORD *)(a2 + 68)
         || !RtlEqualUnicodeString((PCUNICODE_STRING)(a3 + 8), (PCUNICODE_STRING)(a2 + 16), 1u) )
  {
    *(_DWORD *)(v3 + 152) &= ~0x10u;
  }
  if ( (*(_DWORD *)(v3 + 152) & 1) != 0 )
  {
    UlpDisableLogFileEntry(v3);
    goto LABEL_39;
  }
LABEL_43:
  ExReleasePushLockExclusiveEx(v3 + 8, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1c003478c  mov     rax, rsp
0x1c003478f  mov     [rax+8], rcx
0x1c0034793  push    rbx
0x1c0034794  push    rbp
0x1c0034795  push    rsi
0x1c0034796  push    rdi
0x1c0034797  push    r12
0x1c0034799  push    r13
0x1c003479b  push    r14
0x1c003479d  push    r15
0x1c003479f  sub     rsp, 48h
0x1c00347a3  mov     rbx, [rdx+78h]
0x1c00347a7  xor     r12d, r12d
0x1c00347aa  mov     r14d, r12d
0x1c00347ad  mov     [rax+18h], r12
0x1c00347b1  mov     ebp, r12d
0x1c00347b4  mov     [rax+20h], r12
0x1c00347b8  mov     r13d, r12d
0x1c00347bb  mov     [rax+8], r12d
0x1c00347bf  mov     esi, r12d
0x1c00347c2  mov     rdi, r8
0x1c00347c5  mov     r15, rdx
0x1c00347c8  call    cs:__imp_KeEnterCriticalRegion
0x1c00347cf  nop     dword ptr [rax+rax+00h]
0x1c00347d4  lea     rax, [rbx+8]
0x1c00347d8  xor     edx, edx
0x1c00347da  mov     rcx, rax
0x1c00347dd  mov     [rsp+88h+var_58], rax
0x1c00347e2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00347e9  nop     dword ptr [rax+rax+00h]
0x1c00347ee  mov     eax, [rdi+4]
0x1c00347f1  test    al, 10h
0x1c00347f3  jz      short loc_1C00347FD
0x1c00347f5  mov     r12b, 1
0x1c00347f8  jmp     loc_1C0034891
0x1c00347fd  cmp     [rdi+60h], r12
0x1c0034801  jz      short loc_1C003485F
0x1c0034803  xor     r9d, r9d; Priority
0x1c0034806  mov     ecx, 200h; PoolType
0x1c003480b  mov     r8d, 53436C55h; Tag
0x1c0034811  lea     edx, [r9+48h]; NumberOfBytes
0x1c0034815  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c003481c  nop     dword ptr [rax+rax+00h]
0x1c0034821  mov     rsi, rax
0x1c0034824  test    rax, rax
0x1c0034827  jnz     short loc_1C0034833
0x1c0034829  mov     ebp, 0C000009Ah
0x1c003482e  jmp     loc_1C0034AD2
0x1c0034833  mov     rax, [rdi+60h]
0x1c0034837  movups  xmm0, xmmword ptr [rax]
0x1c003483a  movups  xmmword ptr [rsi], xmm0
0x1c003483d  movups  xmm1, xmmword ptr [rax+10h]
0x1c0034841  movups  xmmword ptr [rsi+10h], xmm1
0x1c0034845  movups  xmm0, xmmword ptr [rax+20h]
0x1c0034849  movups  xmmword ptr [rsi+20h], xmm0
0x1c003484d  movups  xmm1, xmmword ptr [rax+30h]
0x1c0034851  movups  xmmword ptr [rsi+30h], xmm1
0x1c0034855  movsd   xmm0, qword ptr [rax+40h]
0x1c003485a  movsd   qword ptr [rsi+40h], xmm0
0x1c003485f  mov     rcx, [rdi+58h]
0x1c0034863  test    rcx, rcx
0x1c0034866  jz      short loc_1C0034891
0x1c0034868  lea     r9, [rsp+88h+arg_8]
0x1c0034870  xor     edx, edx
0x1c0034872  lea     r8, [rsp+88h+arg_10]
0x1c003487a  call    UlpCaptureSecurityDescriptor
0x1c003487f  mov     r14, [rsp+88h+arg_10]
0x1c0034887  mov     ebp, eax
0x1c0034889  test    eax, eax
0x1c003488b  js      loc_1C0034AA3
0x1c0034891  movzx   eax, word ptr [rdi+8]
0x1c0034895  test    ax, ax
0x1c0034898  jz      short loc_1C00348CF
0x1c003489a  mov     rcx, [rdi+10h]; UnicodeString
0x1c003489e  lea     r9, [rsp+88h+arg_18]
0x1c00348a6  mov     edx, eax; BytesInUnicodeString
0x1c00348a8  xor     r8d, r8d
0x1c00348ab  lea     rax, [rsp+88h+arg_0]
0x1c00348b3  mov     [rsp+88h+var_68], rax; __int64
0x1c00348b8  call    UlpCaptureSoftwareDirective
0x1c00348bd  mov     ebp, eax
0x1c00348bf  test    eax, eax
0x1c00348c1  js      loc_1C0034AA3
0x1c00348c7  mov     r13, [rsp+88h+arg_18]
0x1c00348cf  lea     rdx, [r15+28h]; String2
0x1c00348d3  mov     r8b, 1; CaseInSensitive
0x1c00348d6  lea     rcx, [rdi+20h]; String1
0x1c00348da  call    cs:__imp_RtlEqualUnicodeString
0x1c00348e1  nop     dword ptr [rax+rax+00h]
0x1c00348e6  xor     edx, edx
0x1c00348e8  test    al, al
0x1c00348ea  jnz     short loc_1C00348FE
0x1c00348ec  mov     eax, [rbx+98h]
0x1c00348f2  and     eax, 0FFFFFFBFh
0x1c00348f5  or      eax, 2
0x1c00348f8  mov     [rbx+98h], eax
0x1c00348fe  mov     rcx, [rbx+78h]
0x1c0034902  test    rcx, rcx
0x1c0034905  jz      short loc_1C0034918
0x1c0034907  mov     r8b, 1
0x1c003490a  call    cs:__imp_SeReleaseSecurityDescriptor
0x1c0034911  nop     dword ptr [rax+rax+00h]
0x1c0034916  xor     edx, edx
0x1c0034918  mov     rcx, [rbx+88h]
0x1c003491f  test    rcx, rcx
0x1c0034922  jz      short loc_1C0034975
0x1c0034924  mov     rcx, [rcx+10h]; Token
0x1c0034928  call    cs:__imp_SeTokenType
0x1c003492f  nop     dword ptr [rax+rax+00h]
0x1c0034934  mov     rcx, [rbx+88h]
0x1c003493b  mov     rcx, [rcx+10h]; ImpersonationToken
0x1c003493f  cmp     eax, 1
0x1c0034942  jnz     short loc_1C0034952
0x1c0034944  call    cs:__imp_PsDereferencePrimaryToken
0x1c003494b  nop     dword ptr [rax+rax+00h]
0x1c0034950  jmp     short loc_1C003495E
0x1c0034952  call    cs:__imp_PsDereferenceImpersonationToken
0x1c0034959  nop     dword ptr [rax+rax+00h]
0x1c003495e  mov     rcx, [rbx+88h]; P
0x1c0034965  xor     edx, edx; Tag
0x1c0034967  call    cs:__imp_ExFreePoolWithTag
0x1c003496e  nop     dword ptr [rax+rax+00h]
0x1c0034973  xor     edx, edx
0x1c0034975  mov     rcx, [rbx+10h]; P
0x1c0034979  mov     [rbx+80h], r12b
0x1c0034980  xor     r12d, r12d
0x1c0034983  mov     [rbx+78h], r14
0x1c0034987  mov     r14, rdx
0x1c003498a  mov     [rbx+88h], rsi
0x1c0034991  mov     esi, r12d
0x1c0034994  test    rcx, rcx
0x1c0034997  jz      short loc_1C00349A7
0x1c0034999  xor     edx, edx; Tag
0x1c003499b  call    cs:__imp_ExFreePoolWithTag
0x1c00349a2  nop     dword ptr [rax+rax+00h]
0x1c00349a7  mov     eax, dword ptr [rsp+88h+arg_0]
0x1c00349ae  mov     [rbx+18h], eax
0x1c00349b1  mov     [rbx+10h], r13
0x1c00349b5  mov     r8d, [rdi+38h]
0x1c00349b9  mov     [rbx+50h], r8d
0x1c00349bd  mov     eax, [rdi+4Ch]
0x1c00349c0  mov     [rbx+54h], eax
0x1c00349c3  mov     eax, [rdi+50h]
0x1c00349c6  mov     [rbx+58h], eax
0x1c00349c9  mov     eax, [rdi+3Ch]
0x1c00349cc  mov     [rbx+5Ch], eax
0x1c00349cf  mov     al, [r15]
0x1c00349d2  and     al, 1
0x1c00349d4  mov     [rbx+90h], al
0x1c00349da  mov     ecx, [rdi+4]
0x1c00349dd  shl     ecx, 9
0x1c00349e0  xor     ecx, [rbx+98h]
0x1c00349e6  and     ecx, 200h
0x1c00349ec  xor     ecx, [rbx+98h]
0x1c00349f2  mov     [rbx+98h], ecx
0x1c00349f8  mov     eax, [rdi+4]
0x1c00349fb  test    al, 2
0x1c00349fd  jz      short loc_1C0034A0A
0x1c00349ff  mov     eax, 400h
0x1c0034a04  cmp     r8d, 3
0x1c0034a08  jnz     short loc_1C0034A0D
0x1c0034a0a  mov     eax, r12d
0x1c0034a0d  btr     ecx, 0Ah
0x1c0034a11  or      ecx, eax
0x1c0034a13  mov     [rbx+98h], ecx
0x1c0034a19  mov     eax, [r15+40h]
0x1c0034a1d  cmp     [rdi+38h], eax
0x1c0034a20  jnz     short loc_1C0034A44
0x1c0034a22  mov     eax, [r15+54h]
0x1c0034a26  cmp     [rdi+4Ch], eax
0x1c0034a29  jnz     short loc_1C0034A44
0x1c0034a2b  mov     edx, [r15+0Ch]
0x1c0034a2f  mov     eax, edx
0x1c0034a31  mov     r9d, [rdi+4]
0x1c0034a35  xor     eax, r9d
0x1c0034a38  test    al, 1
0x1c0034a3a  jnz     short loc_1C0034A44
0x1c0034a3c  xor     edx, r9d
0x1c0034a3f  test    dl, 2
0x1c0034a42  jz      short loc_1C0034A4D
0x1c0034a44  or      ecx, 6
0x1c0034a47  mov     [rbx+98h], ecx
0x1c0034a4d  test    r8d, r8d
0x1c0034a50  jz      short loc_1C0034A66
0x1c0034a52  lea     eax, [r8-1]
0x1c0034a56  cmp     eax, 1
0x1c0034a59  ja      short loc_1C0034A91
0x1c0034a5b  or      ecx, 10h
0x1c0034a5e  mov     [rbx+98h], ecx
0x1c0034a64  jmp     short loc_1C0034A91
0x1c0034a66  mov     eax, [r15+44h]
0x1c0034a6a  cmp     [rdi+3Ch], eax
0x1c0034a6d  jnz     short loc_1C0034A8A
0x1c0034a6f  lea     rdx, [r15+10h]; String2
0x1c0034a73  mov     r8b, 1; CaseInSensitive
0x1c0034a76  lea     rcx, [rdi+8]; String1
0x1c0034a7a  call    cs:__imp_RtlEqualUnicodeString
0x1c0034a81  nop     dword ptr [rax+rax+00h]
0x1c0034a86  test    al, al
0x1c0034a88  jnz     short loc_1C0034A91
0x1c0034a8a  and     dword ptr [rbx+98h], 0FFFFFFEFh
0x1c0034a91  mov     eax, [rbx+98h]
0x1c0034a97  test    al, 1
0x1c0034a99  jz      short loc_1C0034AD2
0x1c0034a9b  mov     rcx, rbx
0x1c0034a9e  call    UlpDisableLogFileEntry
0x1c0034aa3  test    rsi, rsi
0x1c0034aa6  jz      short loc_1C0034AB9
0x1c0034aa8  xor     edx, edx; Tag
0x1c0034aaa  mov     rcx, rsi; P
0x1c0034aad  call    cs:__imp_ExFreePoolWithTag
0x1c0034ab4  nop     dword ptr [rax+rax+00h]
0x1c0034ab9  test    r14, r14
0x1c0034abc  jz      short loc_1C0034AD2
0x1c0034abe  mov     r8b, 1
0x1c0034ac1  xor     edx, edx
0x1c0034ac3  mov     rcx, r14
0x1c0034ac6  call    cs:__imp_SeReleaseSecurityDescriptor
0x1c0034acd  nop     dword ptr [rax+rax+00h]
0x1c0034ad2  mov     rcx, [rsp+88h+var_58]
0x1c0034ad7  xor     edx, edx
0x1c0034ad9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0034ae0  nop     dword ptr [rax+rax+00h]
0x1c0034ae5  call    cs:__imp_KeLeaveCriticalRegion
0x1c0034aec  nop     dword ptr [rax+rax+00h]
0x1c0034af1  mov     eax, ebp
0x1c0034af3  add     rsp, 48h
0x1c0034af7  pop     r15
0x1c0034af9  pop     r14
0x1c0034afb  pop     r13
0x1c0034afd  pop     r12
0x1c0034aff  pop     rdi
0x1c0034b00  pop     rsi
0x1c0034b01  pop     rbp
0x1c0034b02  pop     rbx
0x1c0034b03  retn
```
