# SmbCeCompleteSessionEntryInitialization

- ea: `0x140053db0`
- end: `0x1400542bd`
- name: `SmbCeCompleteSessionEntryInitialization`
- size: `1293`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400017a0`
- `0x14004eb70`
- `0x14004f920`

## callees

- `0x140001008`
- `0x140001040`
- `0x140003e20`
- `0x14000ca70`
- `0x14000cda8`
- `0x14000dfa8`
- `0x14000ebd8`
- `0x140016560`
- `0x140028134`
- `0x14003edd4`
- `0x140053db0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400540af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400540af`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400540a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400540a3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053e47`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053e47`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053e2b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053e2b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140053f2e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140053f2e`

## string_xrefs

- `0x1400540f2`: `SmbCeCompleteSessionEntryInitialization`

## pseudocode

```c
__int64 __fastcall SmbCeCompleteSessionEntryInitialization(__int64 a1, unsigned int a2, char a3)
{
  __int64 v3; // rdi
  __int128 *v7; // rdx
  __int64 v8; // r8
  __int128 *v9; // rcx
  __int128 *v10; // rcx
  char v11; // al
  int v12; // ecx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int128 ***v15; // rcx
  __int128 **v16; // rax
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rax
  __int16 v23; // ax
  bool v24; // al
  char v25; // [rsp+30h] [rbp-D0h] BYREF
  char v26; // [rsp+31h] [rbp-CFh] BYREF
  char v27; // [rsp+32h] [rbp-CEh] BYREF
  bool v28; // [rsp+33h] [rbp-CDh] BYREF
  __int16 v29; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v30; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34[18]; // [rsp+70h] [rbp-90h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  v31 = 0;
  v32 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
  *(_QWORD *)(a1 + 72) = 0;
  SmbCeUnblockSerializedSessionSetupRequests(a1);
  v9 = (__int128 *)(a1 + 80);
  if ( *(__int128 **)v9 == v9 )
  {
    *((_QWORD *)&v31 + 1) = &v31;
    *(_QWORD *)&v31 = &v31;
  }
  else
  {
    v31 = *v9;
    *(_QWORD *)(v31 + 8) = &v31;
    v7 = &v31;
    **((_QWORD **)&v31 + 1) = &v31;
    *(_QWORD *)(a1 + 88) = a1 + 80;
    *(_QWORD *)v9 = v9;
  }
  v10 = (__int128 *)(v3 + 744);
  if ( *(__int128 **)v10 == v10 )
  {
    *((_QWORD *)&v32 + 1) = &v32;
    *(_QWORD *)&v32 = &v32;
  }
  else
  {
    v32 = *v10;
    *(_QWORD *)(v32 + 8) = &v32;
    v7 = &v32;
    **((_QWORD **)&v32 + 1) = &v32;
    *(_QWORD *)(v3 + 752) = v3 + 744;
    *(_QWORD *)v10 = v10;
  }
  *(_BYTE *)(v3 + 672) &= ~0x20u;
  v11 = *(_BYTE *)(v3 + 672);
  if ( a2 )
    goto LABEL_37;
  v12 = *(_DWORD *)(a1 + 136);
  if ( (v12 & 0x10) != 0 )
  {
    if ( (MRxSmbSecuritySignaturesRequired || (*(_BYTE *)(v3 + 673) & 1) != 0)
      && !*(_BYTE *)(MRxSmbGetConfigurationBlock() + 229) )
    {
      a2 = -1073741240;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        v14 = 27;
LABEL_23:
        WPP_SF_(v13->AttachedDevice, v14, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids);
      }
    }
  }
  else if ( (v12 & 4) != 0 )
  {
    if ( (*(_BYTE *)(v3 + 673) & 1) != 0 )
    {
      a2 = -1073741240;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        v14 = 28;
        goto LABEL_23;
      }
    }
  }
  else if ( (v11 & 8) == 0 && ((v11 & 0x10) != 0) != a3 )
  {
    a2 = -1073741240;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids);
      goto LABEL_37;
    }
  }
  if ( a2 )
  {
LABEL_37:
    _InterlockedExchange((volatile __int32 *)(a1 + 12), 1);
    goto LABEL_38;
  }
  _InterlockedExchange((volatile __int32 *)(a1 + 12), 0);
  v15 = *(__int128 ****)(a1 + 176);
  if ( v15 && (v15[3] || v15[2]) && (*(_DWORD *)(a1 + 136) & 4) == 0 )
  {
    v16 = (__int128 **)(a1 + 48);
    if ( !*(_QWORD *)(a1 + 48) )
    {
      v15 = (__int128 ***)(v3 + 184);
      v7 = *(__int128 **)(v3 + 184);
      if ( *((_QWORD *)v7 + 1) != v3 + 184 )
        __fastfail(3u);
      *v16 = v7;
      *(_QWORD *)(a1 + 56) = v15;
      *((_QWORD *)v7 + 1) = v16;
      *v15 = v16;
    }
  }
  if ( a3 && (*(_BYTE *)(v3 + 672) & 0x18) == 0x10 )
  {
    if ( *(_DWORD *)(a1 + 128) == 2
      && (SmbInitializeSmbSecuritySignature(v3 + 400, 0, a1 + 188, *(unsigned int *)(a1 + 376)),
          MRxSmbExtendedSignaturesEnabled) )
    {
      *(_DWORD *)(a1 + 136) &= ~0x100u;
      v18 = 1;
    }
    else
    {
      v18 = 2;
    }
    *(_DWORD *)(a1 + 184) = v18;
    *(_BYTE *)(v3 + 672) |= 8u;
    *(_DWORD *)(v3 + 636) = 2;
  }
  else
  {
    *(_DWORD *)(a1 + 184) = 2;
  }
  if ( (unsigned int)dword_14001F0D0 > 5 && (unsigned __int8)tlgKeywordOn(v15, v7, v8) )
  {
    v29 = *(_WORD *)(v3 + 416);
    v34[4] = (__int64)&v29;
    v33 = *(_DWORD *)(a1 + 136);
    v34[6] = (__int64)&v33;
    v25 = *(_BYTE *)(a1 + 381);
    v34[8] = (__int64)&v25;
    v26 = *(_BYTE *)(a1 + 380);
    v34[10] = (__int64)&v26;
    v27 = *(_BYTE *)(a1 + 382);
    v34[12] = (__int64)&v27;
    v22 = *(_QWORD *)(v3 + 344);
    v34[5] = 2;
    v34[7] = 4;
    v34[9] = 1;
    v34[11] = 1;
    v34[13] = 1;
    if ( v22 )
      v23 = *(_WORD *)(v22 + 320);
    else
      v23 = 255;
    v30 = v23;
    v34[15] = 2;
    v34[14] = (__int64)&v30;
    v24 = (*(_BYTE *)(v3 + 672) & 8) != 0;
    v34[17] = 1;
    v28 = v24;
    v34[16] = (__int64)&v28;
    tlgWriteTransfer_EtwWriteTransfer(v19, (int)&unk_14001B430, v20, v21, 9u, (__int64)v34);
  }
LABEL_38:
  *(_WORD *)(a1 + 408) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids, a1);
  ExReleaseResourceLite(&s_SmbCeDbResource);
  KeLeaveCriticalRegion();
  if ( (__int128 *)v31 != &v31 )
    SmbCeResumeOutstandingRequests(&v31, a2);
  if ( (__int128 *)v32 != &v32 )
    SmbCeResumeOutstandingRequests(&v32, 0);
  MRxSmbTrackDerefCount(a1, "SmbCeCompleteSessionEntryInitialization", 1890);
  SmbCepDereferenceSessionEntry(a1);
  return a2;
}

```

## disassembly

```asm
0x140053db0  mov     [rsp-8+arg_10], rbx
0x140053db5  push    rbp
0x140053db6  push    rsi
0x140053db7  push    rdi
0x140053db8  push    r12
0x140053dba  push    r13
0x140053dbc  push    r14
0x140053dbe  push    r15
0x140053dc0  lea     rbp, [rsp-10h]
0x140053dc5  sub     rsp, 110h
0x140053dcc  mov     rax, cs:__security_cookie
0x140053dd3  xor     rax, rsp
0x140053dd6  mov     [rbp+40h+var_40], rax
0x140053dda  mov     rdi, [rcx+40h]
0x140053dde  xorps   xmm0, xmm0
0x140053de1  xorps   xmm1, xmm1
0x140053de4  mov     sil, r8b
0x140053de7  movups  [rsp+140h+var_100], xmm0
0x140053dec  mov     r15d, edx
0x140053def  mov     rbx, rcx
0x140053df2  movups  [rsp+140h+var_F0], xmm1
0x140053df7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053dfe  lea     rax, WPP_GLOBAL_Control
0x140053e05  lea     r13, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x140053e0c  cmp     rcx, rax
0x140053e0f  jz      short loc_140053E2B
0x140053e11  test    dword ptr [rcx+2Ch], 400h
0x140053e18  jz      short loc_140053E2B
0x140053e1a  mov     rcx, [rcx+18h]
0x140053e1e  mov     edx, 1Ah
0x140053e23  mov     r8, r13
0x140053e26  call    WPP_SF_
0x140053e2b  call    cs:__imp_KeEnterCriticalRegion
0x140053e32  nop     dword ptr [rax+rax+00h]
0x140053e37  mov     r14d, 1
0x140053e3d  lea     rcx, s_SmbCeDbResource; Resource
0x140053e44  mov     dl, r14b; Wait
0x140053e47  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140053e4e  nop     dword ptr [rax+rax+00h]
0x140053e53  xor     r12d, r12d
0x140053e56  mov     rcx, rbx
0x140053e59  mov     [rbx+48h], r12
0x140053e5d  call    SmbCeUnblockSerializedSessionSetupRequests
0x140053e62  lea     rcx, [rbx+50h]
0x140053e66  cmp     [rcx], rcx
0x140053e69  jnz     short loc_140053E81
0x140053e6b  lea     rax, [rsp+140h+var_100]
0x140053e70  mov     qword ptr [rsp+140h+var_100+8], rax
0x140053e75  lea     rax, [rsp+140h+var_100]
0x140053e7a  mov     qword ptr [rsp+140h+var_100], rax
0x140053e7f  jmp     short loc_140053EAB
0x140053e81  movups  xmm0, xmmword ptr [rcx]
0x140053e84  lea     rdx, [rsp+140h+var_100]
0x140053e89  movups  [rsp+140h+var_100], xmm0
0x140053e8e  movq    rax, xmm0
0x140053e93  mov     [rax+8], rdx
0x140053e97  lea     rdx, [rsp+140h+var_100]
0x140053e9c  mov     rax, qword ptr [rsp+140h+var_100+8]
0x140053ea1  mov     [rax], rdx
0x140053ea4  mov     [rcx+8], rcx
0x140053ea8  mov     [rcx], rcx
0x140053eab  lea     rcx, [rdi+2E8h]
0x140053eb2  cmp     [rcx], rcx
0x140053eb5  jnz     short loc_140053ECD
0x140053eb7  lea     rax, [rsp+140h+var_F0]
0x140053ebc  mov     qword ptr [rsp+140h+var_F0+8], rax
0x140053ec1  lea     rax, [rsp+140h+var_F0]
0x140053ec6  mov     qword ptr [rsp+140h+var_F0], rax
0x140053ecb  jmp     short loc_140053EF7
0x140053ecd  movups  xmm0, xmmword ptr [rcx]
0x140053ed0  lea     rdx, [rsp+140h+var_F0]
0x140053ed5  movups  [rsp+140h+var_F0], xmm0
0x140053eda  movq    rax, xmm0
0x140053edf  mov     [rax+8], rdx
0x140053ee3  lea     rdx, [rsp+140h+var_F0]
0x140053ee8  mov     rax, qword ptr [rsp+140h+var_F0+8]
0x140053eed  mov     [rax], rdx
0x140053ef0  mov     [rcx+8], rcx
0x140053ef4  mov     [rcx], rcx
0x140053ef7  and     byte ptr [rdi+2A0h], 0DFh
0x140053efe  mov     al, [rdi+2A0h]
0x140053f04  test    r15d, r15d
0x140053f07  jnz     loc_140054060
0x140053f0d  mov     ecx, [rbx+88h]
0x140053f13  test    cl, 10h
0x140053f16  jz      short loc_140053F6C
0x140053f18  cmp     cs:MRxSmbSecuritySignaturesRequired, r12b
0x140053f1f  jnz     short loc_140053F2E
0x140053f21  test    [rdi+2A1h], r14b
0x140053f28  jz      loc_140053FB1
0x140053f2e  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140053f35  nop     dword ptr [rax+rax+00h]
0x140053f3a  cmp     [rax+0E5h], r12b
0x140053f41  jnz     short loc_140053FB1
0x140053f43  mov     r15d, 0C0000248h
0x140053f49  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053f50  lea     rax, WPP_GLOBAL_Control
0x140053f57  cmp     rcx, rax
0x140053f5a  jz      short loc_140053FB1
0x140053f5c  test    dword ptr [rcx+2Ch], 100h
0x140053f63  jz      short loc_140053FB1
0x140053f65  mov     edx, 1Bh
0x140053f6a  jmp     short loc_140053FA5
0x140053f6c  test    cl, 4
0x140053f6f  jz      loc_140054016
0x140053f75  test    [rdi+2A1h], r14b
0x140053f7c  jz      short loc_140053FB1
0x140053f7e  mov     r15d, 0C0000248h
0x140053f84  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053f8b  lea     rax, WPP_GLOBAL_Control
0x140053f92  cmp     rcx, rax
0x140053f95  jz      short loc_140053FB1
0x140053f97  test    dword ptr [rcx+2Ch], 100h
0x140053f9e  jz      short loc_140053FB1
0x140053fa0  mov     edx, 1Ch
0x140053fa5  mov     rcx, [rcx+18h]
0x140053fa9  mov     r8, r13
0x140053fac  call    WPP_SF_
0x140053fb1  test    r15d, r15d
0x140053fb4  jnz     loc_140054060
0x140053fba  mov     eax, r12d
0x140053fbd  xchg    eax, [rbx+0Ch]
0x140053fc0  mov     rcx, [rbx+0B0h]
0x140053fc7  test    rcx, rcx
0x140053fca  jz      loc_140054142
0x140053fd0  cmp     [rcx+18h], r12
0x140053fd4  jnz     short loc_140053FE0
0x140053fd6  cmp     [rcx+10h], r12
0x140053fda  jz      loc_140054142
0x140053fe0  mov     eax, [rbx+88h]
0x140053fe6  test    al, 4
0x140053fe8  jnz     loc_140054142
0x140053fee  lea     rax, [rbx+30h]
0x140053ff2  cmp     [rax], r12
0x140053ff5  jnz     loc_140054142
0x140053ffb  lea     rcx, [rdi+0B8h]
0x140054002  mov     rdx, [rcx]
0x140054005  cmp     [rdx+8], rcx
0x140054009  jz      loc_140054134
0x14005400f  mov     ecx, 3
0x140054014  int     29h; Win8: RtlFailFast(ecx)
0x140054016  test    al, 8
0x140054018  jnz     short loc_140053FB1
0x14005401a  shr     al, 4
0x14005401d  and     al, r14b
0x140054020  cmp     al, sil
0x140054023  jz      short loc_140053FB1
0x140054025  mov     r15d, 0C0000248h
0x14005402b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140054032  lea     rax, WPP_GLOBAL_Control
0x140054039  cmp     rcx, rax
0x14005403c  jz      loc_140053FB1
0x140054042  test    dword ptr [rcx+2Ch], 100h
0x140054049  jz      loc_140053FB1
0x14005404f  mov     rcx, [rcx+18h]
0x140054053  mov     edx, 1Dh
0x140054058  mov     r8, r13
0x14005405b  call    WPP_SF_
0x140054060  xchg    r14d, [rbx+0Ch]
0x140054064  mov     [rbx+198h], r12w
0x14005406c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140054073  lea     rax, WPP_GLOBAL_Control
0x14005407a  cmp     rcx, rax
0x14005407d  jz      short loc_14005409C
0x14005407f  test    dword ptr [rcx+2Ch], 200h
0x140054086  jz      short loc_14005409C
0x140054088  mov     rcx, [rcx+18h]
0x14005408c  mov     edx, 1Eh
0x140054091  mov     r9, rbx
0x140054094  mov     r8, r13
0x140054097  call    WPP_SF_q
0x14005409c  lea     rcx, s_SmbCeDbResource; Resource
0x1400540a3  call    cs:__imp_ExReleaseResourceLite
0x1400540aa  nop     dword ptr [rax+rax+00h]
0x1400540af  call    cs:__imp_KeLeaveCriticalRegion
0x1400540b6  nop     dword ptr [rax+rax+00h]
0x1400540bb  lea     rax, [rsp+140h+var_100]
0x1400540c0  cmp     qword ptr [rsp+140h+var_100], rax
0x1400540c5  jz      short loc_1400540D4
0x1400540c7  mov     edx, r15d
0x1400540ca  lea     rcx, [rsp+140h+var_100]
0x1400540cf  call    SmbCeResumeOutstandingRequests
0x1400540d4  lea     rax, [rsp+140h+var_F0]
0x1400540d9  cmp     qword ptr [rsp+140h+var_F0], rax
0x1400540de  jz      short loc_1400540EC
0x1400540e0  xor     edx, edx
0x1400540e2  lea     rcx, [rsp+140h+var_F0]
0x1400540e7  call    SmbCeResumeOutstandingRequests
0x1400540ec  mov     r8d, 762h
0x1400540f2  lea     rdx, aSmbcecompletes; "SmbCeCompleteSessionEntryInitialization"
0x1400540f9  mov     rcx, rbx
0x1400540fc  call    MRxSmbTrackDerefCount
0x140054101  mov     rcx, rbx
0x140054104  call    SmbCepDereferenceSessionEntry
0x140054109  mov     eax, r15d
0x14005410c  mov     rcx, [rbp+40h+var_40]
0x140054110  xor     rcx, rsp; StackCookie
0x140054113  call    __security_check_cookie
0x140054118  mov     rbx, [rsp+140h+arg_10]
0x140054120  add     rsp, 110h
0x140054127  pop     r15
0x140054129  pop     r14
0x14005412b  pop     r13
0x14005412d  pop     r12
0x14005412f  pop     rdi
0x140054130  pop     rsi
0x140054131  pop     rbp
0x140054132  retn
0x140054134  mov     [rax], rdx
0x140054137  mov     [rax+8], rcx
0x14005413b  mov     [rdx+8], rax
0x14005413f  mov     [rcx], rax
0x140054142  test    sil, sil
0x140054145  jz      short loc_1400541A9
0x140054147  mov     al, [rdi+2A0h]
0x14005414d  and     al, 18h
0x14005414f  cmp     al, 10h
0x140054151  jnz     short loc_1400541A9
0x140054153  mov     esi, 2
0x140054158  cmp     [rbx+80h], esi
0x14005415e  jnz     short loc_140054192
0x140054160  mov     r9d, [rbx+178h]
0x140054167  lea     r8, [rbx+0BCh]
0x14005416e  lea     rcx, [rdi+190h]
0x140054175  xor     edx, edx
0x140054177  call    SmbInitializeSmbSecuritySignature
0x14005417c  cmp     cs:MRxSmbExtendedSignaturesEnabled, r12b
0x140054183  jz      short loc_140054192
0x140054185  btr     dword ptr [rbx+88h], 8
0x14005418d  mov     eax, r14d
0x140054190  jmp     short loc_140054194
0x140054192  mov     eax, esi
0x140054194  mov     [rbx+0B8h], eax
0x14005419a  or      byte ptr [rdi+2A0h], 8
0x1400541a1  mov     [rdi+27Ch], esi
0x1400541a7  jmp     short loc_1400541B4
0x1400541a9  mov     esi, 2
0x1400541ae  mov     [rbx+0B8h], esi
0x1400541b4  mov     eax, cs:dword_14001F0D0
0x1400541ba  cmp     eax, 5
0x1400541bd  jbe     loc_140054064
0x1400541c3  call    _tlgKeywordOn
0x1400541c8  test    al, al
0x1400541ca  jz      loc_140054064
0x1400541d0  movzx   eax, word ptr [rdi+1A0h]
0x1400541d7  mov     [rsp+140h+var_10C], ax
0x1400541dc  lea     rax, [rsp+140h+var_10C]
0x1400541e1  mov     [rbp+40h+var_B0], rax
0x1400541e5  mov     eax, [rbx+88h]
0x1400541eb  mov     [rsp+140h+var_E0], eax
0x1400541ef  lea     rax, [rsp+140h+var_E0]
0x1400541f4  mov     [rbp+40h+var_A0], rax
0x1400541f8  mov     al, [rbx+17Dh]
0x1400541fe  mov     [rsp+140h+var_110], al
0x140054202  lea     rax, [rsp+140h+var_110]
0x140054207  mov     [rbp+40h+var_90], rax
0x14005420b  mov     al, [rbx+17Ch]
0x140054211  mov     [rsp+140h+var_10F], al
0x140054215  lea     rax, [rsp+140h+var_10F]
0x14005421a  mov     [rbp+40h+var_80], rax
0x14005421e  mov     al, [rbx+17Eh]
0x140054224  mov     [rsp+140h+var_10E], al
0x140054228  lea     rax, [rsp+140h+var_10E]
0x14005422d  mov     [rbp+40h+var_70], rax
0x140054231  mov     rax, [rdi+158h]
0x140054238  mov     [rbp+40h+var_A8], 2
0x140054240  mov     [rbp+40h+var_98], 4
0x140054248  mov     [rbp+40h+var_88], r14
0x14005424c  mov     [rbp+40h+var_78], r14
0x140054250  mov     [rbp+40h+var_68], r14
0x140054254  test    rax, rax
0x140054257  jz      short loc_140054262
0x140054259  movzx   eax, word ptr [rax+140h]
0x140054260  jmp     short loc_140054267
0x140054262  mov     eax, 0FFh
0x140054267  mov     [rsp+140h+var_108], ax
0x14005426c  lea     rdx, unk_14001B430; int
0x140054273  lea     rax, [rsp+140h+var_108]
0x140054278  mov     [rbp+40h+var_58], 2
0x140054280  mov     [rbp+40h+var_60], rax
0x140054284  mov     al, [rdi+2A0h]
0x14005428a  shr     al, 3
0x14005428d  and     al, r14b
0x140054290  mov     [rbp+40h+var_48], r14
0x140054294  mov     [rsp+140h+var_10D], al
0x140054298  lea     rax, [rsp+140h+var_10D]
0x14005429d  mov     [rbp+40h+var_50], rax
0x1400542a1  lea     rax, [rsp+140h+var_D0]
0x1400542a6  mov     [rsp+140h+var_118], rax; __int64
0x1400542ab  mov     [rsp+140h+var_120], 9; ULONG
0x1400542b3  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400542b8  jmp     loc_140054064
```
