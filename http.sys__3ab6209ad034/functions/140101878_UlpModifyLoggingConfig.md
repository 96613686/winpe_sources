# UlpModifyLoggingConfig

- ea: `0x140101878`
- end: `0x140101bcc`
- name: `UlpModifyLoggingConfig`
- size: `852`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400fd240`

## callees

- `0x1400ffd7c`
- `0x1400ffe7c`
- `0x140100800`
- `0x140101878`

## import_xrefs

- `ntoskrnl!SeDeleteClientSecurity` at `0x140101a35`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140101a35`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140101a1b`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140101b8d`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140101a1b`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140101b8d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401019eb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140101b57`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401019eb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140101b57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140101bac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140101bac`
- `ntoskrnl!ExAllocatePool3` at `0x14010190c`
- `ntoskrnl!ExAllocatePool3` at `0x14010190c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401019c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101a4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101a7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401019c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101a4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101a7b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140101ba0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140101ba0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401018cb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401018cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401018b1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401018b1`

## pseudocode

```c
__int64 __fastcall UlpModifyLoggingConfig(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  char v4; // r12
  PSECURITY_DESCRIPTOR v5; // r14
  __int64 v6; // r13
  _OWORD *Pool3; // rsi
  int v10; // ebp
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  ULONG v15; // eax
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rcx
  void *v19; // rcx
  int v20; // edx
  int v21; // ecx
  int v22; // eax
  unsigned int v23; // ecx
  int v24; // r9d
  __int64 v26; // [rsp+90h] [rbp+8h] BYREF
  ULONG v27; // [rsp+98h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR v28; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v29; // [rsp+A8h] [rbp+20h]

  v26 = a1;
  v3 = *(_QWORD *)(a2 + 120);
  v4 = 0;
  v5 = 0;
  v28 = 0;
  v6 = 0;
  v29 = 0;
  LODWORD(v26) = 0;
  Pool3 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v3 + 8, 0);
  if ( (*(_DWORD *)(a3 + 4) & 0x10) != 0 )
  {
    v10 = 0;
    v4 = 1;
  }
  else
  {
    if ( *(_QWORD *)(a3 + 96) )
    {
      Pool3 = (_OWORD *)ExAllocatePool3(66, 72, 1396927573, UxLowPriorityPool, 1);
      if ( !Pool3 )
      {
        v10 = -1073741670;
        goto LABEL_40;
      }
      v11 = *(_QWORD *)(a3 + 96);
      *Pool3 = *(_OWORD *)v11;
      Pool3[1] = *(_OWORD *)(v11 + 16);
      Pool3[2] = *(_OWORD *)(v11 + 32);
      Pool3[3] = *(_OWORD *)(v11 + 48);
      *((_QWORD *)Pool3 + 8) = *(_QWORD *)(v11 + 64);
    }
    v12 = *(_QWORD *)(a3 + 88);
    v10 = 0;
    if ( v12 )
    {
      v13 = UlpCaptureSecurityDescriptor(v12, 0, &v28, &v27);
      v5 = v28;
      v10 = v13;
      if ( v13 < 0 )
        goto LABEL_11;
    }
  }
  v15 = *(unsigned __int16 *)(a3 + 8);
  if ( (_WORD)v15 )
  {
    v10 = UlpCaptureSoftwareDirective(*(PCWCH *)(a3 + 16), v15, (__int64)&v26);
    if ( v10 < 0 )
    {
LABEL_11:
      if ( Pool3 )
        ExFreePoolWithTag(Pool3, 0);
      goto LABEL_38;
    }
    v6 = v29;
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
    SeDeleteClientSecurity(v18);
    ExFreePoolWithTag(*(PVOID *)(v3 + 136), 0);
  }
  v19 = *(void **)(v3 + 16);
  *(_BYTE *)(v3 + 128) = v4;
  *(_QWORD *)(v3 + 120) = v5;
  v5 = 0;
  *(_QWORD *)(v3 + 136) = Pool3;
  if ( v19 )
    ExFreePoolWithTag(v19, 0);
  *(_DWORD *)(v3 + 24) = v26;
  *(_QWORD *)(v3 + 16) = v6;
  v20 = *(_DWORD *)(a3 + 56);
  *(_DWORD *)(v3 + 80) = v20;
  *(_DWORD *)(v3 + 84) = *(_DWORD *)(a3 + 76);
  *(_DWORD *)(v3 + 88) = *(_DWORD *)(a3 + 80);
  *(_DWORD *)(v3 + 92) = *(_DWORD *)(a3 + 60);
  *(_BYTE *)(v3 + 144) = *(_DWORD *)a2 & 1;
  v21 = *(_DWORD *)(v3 + 152)
      ^ ((unsigned __int16)*(_DWORD *)(v3 + 152)
       ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)(a3 + 4) << 9))
      & 0x200;
  *(_DWORD *)(v3 + 152) = v21;
  if ( (*(_DWORD *)(a3 + 4) & 2) == 0 || (v22 = 1024, v20 == 3) )
    v22 = 0;
  v23 = v22 | v21 & 0xFFFFFBFF;
  *(_DWORD *)(v3 + 152) = v23;
  if ( *(_DWORD *)(a3 + 56) != *(_DWORD *)(a2 + 64)
    || *(_DWORD *)(a3 + 76) != *(_DWORD *)(a2 + 84)
    || (v24 = *(_DWORD *)(a3 + 4), (((unsigned __int8)v24 ^ *(_BYTE *)(a2 + 12)) & 1) != 0)
    || (((unsigned __int8)v24 ^ (unsigned __int8)*(_DWORD *)(a2 + 12)) & 2) != 0 )
  {
    v23 |= 6u;
    *(_DWORD *)(v3 + 152) = v23;
  }
  if ( v20 )
  {
    if ( (unsigned int)(v20 - 1) <= 1 )
      *(_DWORD *)(v3 + 152) = v23 | 0x10;
  }
  else if ( *(_DWORD *)(a3 + 60) != *(_DWORD *)(a2 + 68)
         || !RtlEqualUnicodeString((PCUNICODE_STRING)(a3 + 8), (PCUNICODE_STRING)(a2 + 16), 1u) )
  {
    *(_DWORD *)(v3 + 152) &= ~0x10u;
  }
  if ( (*(_DWORD *)(v3 + 152) & 1) != 0 )
  {
    UlpDisableLogFileEntry(v3);
LABEL_38:
    if ( v5 )
    {
      LOBYTE(v14) = 1;
      SeReleaseSecurityDescriptor(v5, 0, v14);
    }
  }
LABEL_40:
  ExReleasePushLockExclusiveEx(v3 + 8, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140101878  mov     rax, rsp
0x14010187b  mov     [rax+8], rcx
0x14010187f  push    rbx
0x140101880  push    rbp
0x140101881  push    rsi
0x140101882  push    rdi
0x140101883  push    r12
0x140101885  push    r13
0x140101887  push    r14
0x140101889  push    r15
0x14010188b  sub     rsp, 48h
0x14010188f  mov     rbx, [rdx+78h]
0x140101893  xor     r12d, r12d
0x140101896  mov     r14d, r12d
0x140101899  mov     [rax+18h], r12
0x14010189d  mov     r13d, r12d
0x1401018a0  mov     [rax+20h], r12
0x1401018a4  mov     [rax+8], r12d
0x1401018a8  mov     esi, r12d
0x1401018ab  mov     rdi, r8
0x1401018ae  mov     r15, rdx
0x1401018b1  call    cs:__imp_KeEnterCriticalRegion
0x1401018b8  nop     dword ptr [rax+rax+00h]
0x1401018bd  lea     rax, [rbx+8]
0x1401018c1  xor     edx, edx
0x1401018c3  mov     rcx, rax
0x1401018c6  mov     [rsp+88h+var_58], rax
0x1401018cb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401018d2  nop     dword ptr [rax+rax+00h]
0x1401018d7  mov     eax, [rdi+4]
0x1401018da  test    al, 10h
0x1401018dc  jz      short loc_1401018E9
0x1401018de  mov     ebp, r12d
0x1401018e1  mov     r12b, 1
0x1401018e4  jmp     loc_140101987
0x1401018e9  cmp     [rdi+60h], r12
0x1401018ed  jz      short loc_140101956
0x1401018ef  mov     edx, 48h ; 'H'
0x1401018f4  mov     dword ptr [rsp+88h+var_68], 1
0x1401018fc  lea     r9, UxLowPriorityPool
0x140101903  mov     r8d, 53436C55h
0x140101909  lea     ecx, [rdx-6]
0x14010190c  call    cs:__imp_ExAllocatePool3
0x140101913  nop     dword ptr [rax+rax+00h]
0x140101918  mov     rsi, rax
0x14010191b  test    rax, rax
0x14010191e  jnz     short loc_14010192A
0x140101920  mov     ebp, 0C000009Ah
0x140101925  jmp     loc_140101B99
0x14010192a  mov     rax, [rdi+60h]
0x14010192e  movups  xmm0, xmmword ptr [rax]
0x140101931  movups  xmmword ptr [rsi], xmm0
0x140101934  movups  xmm1, xmmword ptr [rax+10h]
0x140101938  movups  xmmword ptr [rsi+10h], xmm1
0x14010193c  movups  xmm0, xmmword ptr [rax+20h]
0x140101940  movups  xmmword ptr [rsi+20h], xmm0
0x140101944  movups  xmm1, xmmword ptr [rax+30h]
0x140101948  movups  xmmword ptr [rsi+30h], xmm1
0x14010194c  movsd   xmm0, qword ptr [rax+40h]
0x140101951  movsd   qword ptr [rsi+40h], xmm0
0x140101956  mov     rcx, [rdi+58h]
0x14010195a  mov     ebp, r12d
0x14010195d  test    rcx, rcx
0x140101960  jz      short loc_140101987
0x140101962  lea     r9, [rsp+88h+arg_8]
0x14010196a  xor     edx, edx
0x14010196c  lea     r8, [rsp+88h+arg_10]
0x140101974  call    UlpCaptureSecurityDescriptor
0x140101979  mov     r14, [rsp+88h+arg_10]
0x140101981  mov     ebp, eax
0x140101983  test    eax, eax
0x140101985  js      short loc_1401019B9
0x140101987  movzx   eax, word ptr [rdi+8]
0x14010198b  test    ax, ax
0x14010198e  jz      short loc_1401019E0
0x140101990  mov     rcx, [rdi+10h]; UnicodeString
0x140101994  lea     r9, [rsp+88h+arg_18]
0x14010199c  mov     edx, eax; BytesInUnicodeString
0x14010199e  xor     r8d, r8d
0x1401019a1  lea     rax, [rsp+88h+arg_0]
0x1401019a9  mov     [rsp+88h+var_68], rax; __int64
0x1401019ae  call    UlpCaptureSoftwareDirective
0x1401019b3  mov     ebp, eax
0x1401019b5  test    eax, eax
0x1401019b7  jns     short loc_1401019D8
0x1401019b9  test    rsi, rsi
0x1401019bc  jz      loc_140101B80
0x1401019c2  xor     edx, edx; Tag
0x1401019c4  mov     rcx, rsi; P
0x1401019c7  call    cs:__imp_ExFreePoolWithTag
0x1401019ce  nop     dword ptr [rax+rax+00h]
0x1401019d3  jmp     loc_140101B80
0x1401019d8  mov     r13, [rsp+88h+arg_18]
0x1401019e0  lea     rdx, [r15+28h]; String2
0x1401019e4  mov     r8b, 1; CaseInSensitive
0x1401019e7  lea     rcx, [rdi+20h]; String1
0x1401019eb  call    cs:__imp_RtlEqualUnicodeString
0x1401019f2  nop     dword ptr [rax+rax+00h]
0x1401019f7  xor     edx, edx
0x1401019f9  test    al, al
0x1401019fb  jnz     short loc_140101A0F
0x1401019fd  mov     eax, [rbx+98h]
0x140101a03  and     eax, 0FFFFFFBFh
0x140101a06  or      eax, 2
0x140101a09  mov     [rbx+98h], eax
0x140101a0f  mov     rcx, [rbx+78h]
0x140101a13  test    rcx, rcx
0x140101a16  jz      short loc_140101A29
0x140101a18  mov     r8b, 1
0x140101a1b  call    cs:__imp_SeReleaseSecurityDescriptor
0x140101a22  nop     dword ptr [rax+rax+00h]
0x140101a27  xor     edx, edx
0x140101a29  mov     rcx, [rbx+88h]
0x140101a30  test    rcx, rcx
0x140101a33  jz      short loc_140101A58
0x140101a35  call    cs:__imp_SeDeleteClientSecurity
0x140101a3c  nop     dword ptr [rax+rax+00h]
0x140101a41  mov     rcx, [rbx+88h]; P
0x140101a48  xor     edx, edx; Tag
0x140101a4a  call    cs:__imp_ExFreePoolWithTag
0x140101a51  nop     dword ptr [rax+rax+00h]
0x140101a56  xor     edx, edx
0x140101a58  mov     rcx, [rbx+10h]; P
0x140101a5c  mov     [rbx+80h], r12b
0x140101a63  xor     r12d, r12d
0x140101a66  mov     [rbx+78h], r14
0x140101a6a  mov     r14, rdx
0x140101a6d  mov     [rbx+88h], rsi
0x140101a74  test    rcx, rcx
0x140101a77  jz      short loc_140101A87
0x140101a79  xor     edx, edx; Tag
0x140101a7b  call    cs:__imp_ExFreePoolWithTag
0x140101a82  nop     dword ptr [rax+rax+00h]
0x140101a87  mov     eax, dword ptr [rsp+88h+arg_0]
0x140101a8e  mov     [rbx+18h], eax
0x140101a91  mov     [rbx+10h], r13
0x140101a95  mov     edx, [rdi+38h]
0x140101a98  mov     [rbx+50h], edx
0x140101a9b  mov     eax, [rdi+4Ch]
0x140101a9e  mov     [rbx+54h], eax
0x140101aa1  mov     eax, [rdi+50h]
0x140101aa4  mov     [rbx+58h], eax
0x140101aa7  mov     eax, [rdi+3Ch]
0x140101aaa  mov     [rbx+5Ch], eax
0x140101aad  mov     eax, [r15]
0x140101ab0  and     al, 1
0x140101ab2  mov     [rbx+90h], al
0x140101ab8  mov     eax, [rbx+98h]
0x140101abe  mov     ecx, [rdi+4]
0x140101ac1  shl     ecx, 9
0x140101ac4  xor     ecx, eax
0x140101ac6  and     ecx, 200h
0x140101acc  xor     ecx, eax
0x140101ace  mov     [rbx+98h], ecx
0x140101ad4  mov     eax, [rdi+4]
0x140101ad7  test    al, 2
0x140101ad9  jz      short loc_140101AE5
0x140101adb  mov     eax, 400h
0x140101ae0  cmp     edx, 3
0x140101ae3  jnz     short loc_140101AE8
0x140101ae5  mov     eax, r12d
0x140101ae8  btr     ecx, 0Ah
0x140101aec  or      ecx, eax
0x140101aee  mov     [rbx+98h], ecx
0x140101af4  mov     eax, [r15+40h]
0x140101af8  cmp     [rdi+38h], eax
0x140101afb  jnz     short loc_140101B21
0x140101afd  mov     eax, [r15+54h]
0x140101b01  cmp     [rdi+4Ch], eax
0x140101b04  jnz     short loc_140101B21
0x140101b06  mov     r8d, [r15+0Ch]
0x140101b0a  mov     eax, r8d
0x140101b0d  mov     r9d, [rdi+4]
0x140101b11  xor     eax, r9d
0x140101b14  test    al, 1
0x140101b16  jnz     short loc_140101B21
0x140101b18  xor     r8d, r9d
0x140101b1b  test    r8b, 2
0x140101b1f  jz      short loc_140101B2A
0x140101b21  or      ecx, 6
0x140101b24  mov     [rbx+98h], ecx
0x140101b2a  test    edx, edx
0x140101b2c  jz      short loc_140101B43
0x140101b2e  sub     edx, 1
0x140101b31  jz      short loc_140101B38
0x140101b33  cmp     edx, 1
0x140101b36  jnz     short loc_140101B6E
0x140101b38  or      ecx, 10h
0x140101b3b  mov     [rbx+98h], ecx
0x140101b41  jmp     short loc_140101B6E
0x140101b43  mov     eax, [r15+44h]
0x140101b47  cmp     [rdi+3Ch], eax
0x140101b4a  jnz     short loc_140101B67
0x140101b4c  lea     rdx, [r15+10h]; String2
0x140101b50  mov     r8b, 1; CaseInSensitive
0x140101b53  lea     rcx, [rdi+8]; String1
0x140101b57  call    cs:__imp_RtlEqualUnicodeString
0x140101b5e  nop     dword ptr [rax+rax+00h]
0x140101b63  test    al, al
0x140101b65  jnz     short loc_140101B6E
0x140101b67  and     dword ptr [rbx+98h], 0FFFFFFEFh
0x140101b6e  mov     eax, [rbx+98h]
0x140101b74  test    al, 1
0x140101b76  jz      short loc_140101B99
0x140101b78  mov     rcx, rbx
0x140101b7b  call    UlpDisableLogFileEntry
0x140101b80  test    r14, r14
0x140101b83  jz      short loc_140101B99
0x140101b85  mov     r8b, 1
0x140101b88  xor     edx, edx
0x140101b8a  mov     rcx, r14
0x140101b8d  call    cs:__imp_SeReleaseSecurityDescriptor
0x140101b94  nop     dword ptr [rax+rax+00h]
0x140101b99  mov     rcx, [rsp+88h+var_58]
0x140101b9e  xor     edx, edx
0x140101ba0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140101ba7  nop     dword ptr [rax+rax+00h]
0x140101bac  call    cs:__imp_KeLeaveCriticalRegion
0x140101bb3  nop     dword ptr [rax+rax+00h]
0x140101bb8  mov     eax, ebp
0x140101bba  add     rsp, 48h
0x140101bbe  pop     r15
0x140101bc0  pop     r14
0x140101bc2  pop     r13
0x140101bc4  pop     r12
0x140101bc6  pop     rdi
0x140101bc7  pop     rsi
0x140101bc8  pop     rbp
0x140101bc9  pop     rbx
0x140101bca  retn
```
