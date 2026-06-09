# UlpModifyLoggingConfig

- ea: `0x140101848`
- end: `0x140101b9c`
- name: `UlpModifyLoggingConfig`
- size: `852`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400fd210`

## callees

- `0x1400ffd4c`
- `0x1400ffe4c`
- `0x1401007d0`
- `0x140101848`

## import_xrefs

- `ntoskrnl!SeDeleteClientSecurity` at `0x140101a05`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140101a05`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1401019eb`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140101b5d`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1401019eb`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140101b5d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401019bb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140101b27`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1401019bb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140101b27`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140101b7c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140101b7c`
- `ntoskrnl!ExAllocatePool3` at `0x1401018dc`
- `ntoskrnl!ExAllocatePool3` at `0x1401018dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101997`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101a1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101a4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101997`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101a1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140101a4b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140101b70`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140101b70`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010189b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010189b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140101881`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140101881`

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
0x140101848  mov     rax, rsp
0x14010184b  mov     [rax+8], rcx
0x14010184f  push    rbx
0x140101850  push    rbp
0x140101851  push    rsi
0x140101852  push    rdi
0x140101853  push    r12
0x140101855  push    r13
0x140101857  push    r14
0x140101859  push    r15
0x14010185b  sub     rsp, 48h
0x14010185f  mov     rbx, [rdx+78h]
0x140101863  xor     r12d, r12d
0x140101866  mov     r14d, r12d
0x140101869  mov     [rax+18h], r12
0x14010186d  mov     r13d, r12d
0x140101870  mov     [rax+20h], r12
0x140101874  mov     [rax+8], r12d
0x140101878  mov     esi, r12d
0x14010187b  mov     rdi, r8
0x14010187e  mov     r15, rdx
0x140101881  call    cs:__imp_KeEnterCriticalRegion
0x140101888  nop     dword ptr [rax+rax+00h]
0x14010188d  lea     rax, [rbx+8]
0x140101891  xor     edx, edx
0x140101893  mov     rcx, rax
0x140101896  mov     [rsp+88h+var_58], rax
0x14010189b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401018a2  nop     dword ptr [rax+rax+00h]
0x1401018a7  mov     eax, [rdi+4]
0x1401018aa  test    al, 10h
0x1401018ac  jz      short loc_1401018B9
0x1401018ae  mov     ebp, r12d
0x1401018b1  mov     r12b, 1
0x1401018b4  jmp     loc_140101957
0x1401018b9  cmp     [rdi+60h], r12
0x1401018bd  jz      short loc_140101926
0x1401018bf  mov     edx, 48h ; 'H'
0x1401018c4  mov     dword ptr [rsp+88h+var_68], 1
0x1401018cc  lea     r9, UxLowPriorityPool
0x1401018d3  mov     r8d, 53436C55h
0x1401018d9  lea     ecx, [rdx-6]
0x1401018dc  call    cs:__imp_ExAllocatePool3
0x1401018e3  nop     dword ptr [rax+rax+00h]
0x1401018e8  mov     rsi, rax
0x1401018eb  test    rax, rax
0x1401018ee  jnz     short loc_1401018FA
0x1401018f0  mov     ebp, 0C000009Ah
0x1401018f5  jmp     loc_140101B69
0x1401018fa  mov     rax, [rdi+60h]
0x1401018fe  movups  xmm0, xmmword ptr [rax]
0x140101901  movups  xmmword ptr [rsi], xmm0
0x140101904  movups  xmm1, xmmword ptr [rax+10h]
0x140101908  movups  xmmword ptr [rsi+10h], xmm1
0x14010190c  movups  xmm0, xmmword ptr [rax+20h]
0x140101910  movups  xmmword ptr [rsi+20h], xmm0
0x140101914  movups  xmm1, xmmword ptr [rax+30h]
0x140101918  movups  xmmword ptr [rsi+30h], xmm1
0x14010191c  movsd   xmm0, qword ptr [rax+40h]
0x140101921  movsd   qword ptr [rsi+40h], xmm0
0x140101926  mov     rcx, [rdi+58h]
0x14010192a  mov     ebp, r12d
0x14010192d  test    rcx, rcx
0x140101930  jz      short loc_140101957
0x140101932  lea     r9, [rsp+88h+arg_8]
0x14010193a  xor     edx, edx
0x14010193c  lea     r8, [rsp+88h+arg_10]
0x140101944  call    UlpCaptureSecurityDescriptor
0x140101949  mov     r14, [rsp+88h+arg_10]
0x140101951  mov     ebp, eax
0x140101953  test    eax, eax
0x140101955  js      short loc_140101989
0x140101957  movzx   eax, word ptr [rdi+8]
0x14010195b  test    ax, ax
0x14010195e  jz      short loc_1401019B0
0x140101960  mov     rcx, [rdi+10h]; UnicodeString
0x140101964  lea     r9, [rsp+88h+arg_18]
0x14010196c  mov     edx, eax; BytesInUnicodeString
0x14010196e  xor     r8d, r8d
0x140101971  lea     rax, [rsp+88h+arg_0]
0x140101979  mov     [rsp+88h+var_68], rax; __int64
0x14010197e  call    UlpCaptureSoftwareDirective
0x140101983  mov     ebp, eax
0x140101985  test    eax, eax
0x140101987  jns     short loc_1401019A8
0x140101989  test    rsi, rsi
0x14010198c  jz      loc_140101B50
0x140101992  xor     edx, edx; Tag
0x140101994  mov     rcx, rsi; P
0x140101997  call    cs:__imp_ExFreePoolWithTag
0x14010199e  nop     dword ptr [rax+rax+00h]
0x1401019a3  jmp     loc_140101B50
0x1401019a8  mov     r13, [rsp+88h+arg_18]
0x1401019b0  lea     rdx, [r15+28h]; String2
0x1401019b4  mov     r8b, 1; CaseInSensitive
0x1401019b7  lea     rcx, [rdi+20h]; String1
0x1401019bb  call    cs:__imp_RtlEqualUnicodeString
0x1401019c2  nop     dword ptr [rax+rax+00h]
0x1401019c7  xor     edx, edx
0x1401019c9  test    al, al
0x1401019cb  jnz     short loc_1401019DF
0x1401019cd  mov     eax, [rbx+98h]
0x1401019d3  and     eax, 0FFFFFFBFh
0x1401019d6  or      eax, 2
0x1401019d9  mov     [rbx+98h], eax
0x1401019df  mov     rcx, [rbx+78h]
0x1401019e3  test    rcx, rcx
0x1401019e6  jz      short loc_1401019F9
0x1401019e8  mov     r8b, 1
0x1401019eb  call    cs:__imp_SeReleaseSecurityDescriptor
0x1401019f2  nop     dword ptr [rax+rax+00h]
0x1401019f7  xor     edx, edx
0x1401019f9  mov     rcx, [rbx+88h]
0x140101a00  test    rcx, rcx
0x140101a03  jz      short loc_140101A28
0x140101a05  call    cs:__imp_SeDeleteClientSecurity
0x140101a0c  nop     dword ptr [rax+rax+00h]
0x140101a11  mov     rcx, [rbx+88h]; P
0x140101a18  xor     edx, edx; Tag
0x140101a1a  call    cs:__imp_ExFreePoolWithTag
0x140101a21  nop     dword ptr [rax+rax+00h]
0x140101a26  xor     edx, edx
0x140101a28  mov     rcx, [rbx+10h]; P
0x140101a2c  mov     [rbx+80h], r12b
0x140101a33  xor     r12d, r12d
0x140101a36  mov     [rbx+78h], r14
0x140101a3a  mov     r14, rdx
0x140101a3d  mov     [rbx+88h], rsi
0x140101a44  test    rcx, rcx
0x140101a47  jz      short loc_140101A57
0x140101a49  xor     edx, edx; Tag
0x140101a4b  call    cs:__imp_ExFreePoolWithTag
0x140101a52  nop     dword ptr [rax+rax+00h]
0x140101a57  mov     eax, dword ptr [rsp+88h+arg_0]
0x140101a5e  mov     [rbx+18h], eax
0x140101a61  mov     [rbx+10h], r13
0x140101a65  mov     edx, [rdi+38h]
0x140101a68  mov     [rbx+50h], edx
0x140101a6b  mov     eax, [rdi+4Ch]
0x140101a6e  mov     [rbx+54h], eax
0x140101a71  mov     eax, [rdi+50h]
0x140101a74  mov     [rbx+58h], eax
0x140101a77  mov     eax, [rdi+3Ch]
0x140101a7a  mov     [rbx+5Ch], eax
0x140101a7d  mov     eax, [r15]
0x140101a80  and     al, 1
0x140101a82  mov     [rbx+90h], al
0x140101a88  mov     eax, [rbx+98h]
0x140101a8e  mov     ecx, [rdi+4]
0x140101a91  shl     ecx, 9
0x140101a94  xor     ecx, eax
0x140101a96  and     ecx, 200h
0x140101a9c  xor     ecx, eax
0x140101a9e  mov     [rbx+98h], ecx
0x140101aa4  mov     eax, [rdi+4]
0x140101aa7  test    al, 2
0x140101aa9  jz      short loc_140101AB5
0x140101aab  mov     eax, 400h
0x140101ab0  cmp     edx, 3
0x140101ab3  jnz     short loc_140101AB8
0x140101ab5  mov     eax, r12d
0x140101ab8  btr     ecx, 0Ah
0x140101abc  or      ecx, eax
0x140101abe  mov     [rbx+98h], ecx
0x140101ac4  mov     eax, [r15+40h]
0x140101ac8  cmp     [rdi+38h], eax
0x140101acb  jnz     short loc_140101AF1
0x140101acd  mov     eax, [r15+54h]
0x140101ad1  cmp     [rdi+4Ch], eax
0x140101ad4  jnz     short loc_140101AF1
0x140101ad6  mov     r8d, [r15+0Ch]
0x140101ada  mov     eax, r8d
0x140101add  mov     r9d, [rdi+4]
0x140101ae1  xor     eax, r9d
0x140101ae4  test    al, 1
0x140101ae6  jnz     short loc_140101AF1
0x140101ae8  xor     r8d, r9d
0x140101aeb  test    r8b, 2
0x140101aef  jz      short loc_140101AFA
0x140101af1  or      ecx, 6
0x140101af4  mov     [rbx+98h], ecx
0x140101afa  test    edx, edx
0x140101afc  jz      short loc_140101B13
0x140101afe  sub     edx, 1
0x140101b01  jz      short loc_140101B08
0x140101b03  cmp     edx, 1
0x140101b06  jnz     short loc_140101B3E
0x140101b08  or      ecx, 10h
0x140101b0b  mov     [rbx+98h], ecx
0x140101b11  jmp     short loc_140101B3E
0x140101b13  mov     eax, [r15+44h]
0x140101b17  cmp     [rdi+3Ch], eax
0x140101b1a  jnz     short loc_140101B37
0x140101b1c  lea     rdx, [r15+10h]; String2
0x140101b20  mov     r8b, 1; CaseInSensitive
0x140101b23  lea     rcx, [rdi+8]; String1
0x140101b27  call    cs:__imp_RtlEqualUnicodeString
0x140101b2e  nop     dword ptr [rax+rax+00h]
0x140101b33  test    al, al
0x140101b35  jnz     short loc_140101B3E
0x140101b37  and     dword ptr [rbx+98h], 0FFFFFFEFh
0x140101b3e  mov     eax, [rbx+98h]
0x140101b44  test    al, 1
0x140101b46  jz      short loc_140101B69
0x140101b48  mov     rcx, rbx
0x140101b4b  call    UlpDisableLogFileEntry
0x140101b50  test    r14, r14
0x140101b53  jz      short loc_140101B69
0x140101b55  mov     r8b, 1
0x140101b58  xor     edx, edx
0x140101b5a  mov     rcx, r14
0x140101b5d  call    cs:__imp_SeReleaseSecurityDescriptor
0x140101b64  nop     dword ptr [rax+rax+00h]
0x140101b69  mov     rcx, [rsp+88h+var_58]
0x140101b6e  xor     edx, edx
0x140101b70  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140101b77  nop     dword ptr [rax+rax+00h]
0x140101b7c  call    cs:__imp_KeLeaveCriticalRegion
0x140101b83  nop     dword ptr [rax+rax+00h]
0x140101b88  mov     eax, ebp
0x140101b8a  add     rsp, 48h
0x140101b8e  pop     r15
0x140101b90  pop     r14
0x140101b92  pop     r13
0x140101b94  pop     r12
0x140101b96  pop     rdi
0x140101b97  pop     rsi
0x140101b98  pop     rbp
0x140101b99  pop     rbx
0x140101b9a  retn
```
