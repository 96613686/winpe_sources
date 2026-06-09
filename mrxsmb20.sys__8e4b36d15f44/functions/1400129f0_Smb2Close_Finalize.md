# Smb2Close_Finalize

- ea: `0x1400129f0`
- end: `0x140012cfa`
- name: `Smb2Close_Finalize`
- size: `778`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x140007bd0`
- `0x14000b9c0`
- `0x1400129f0`
- `0x140015780`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012c0a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012c0a`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012b8a`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012b8a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012b99`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012b99`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012b77`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012b77`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012b3a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012b3a`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140012adf`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140012af1`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140012adf`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140012af1`
- `mrxsmb!RDR_PERF_ENTER` at `0x140012a15`
- `mrxsmb!RDR_PERF_ENTER` at `0x140012a15`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140012a42`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140012a42`
- `mrxsmb!SmbCeResumeSuspendedExchangesLite` at `0x140012bea`
- `mrxsmb!SmbCeResumeSuspendedExchangesLite` at `0x140012bea`

## pseudocode

```c
__int64 __fastcall Smb2Close_Finalize(__int64 a1, __int64 a2)
{
  int v2; // r14d
  __int64 v4; // rdi
  __int64 v5; // rsi
  __int64 v6; // rdx
  char v7; // al
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rbp
  _OWORD *v15; // rcx
  unsigned int v16; // edi
  KIRQL v17; // bl
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // edx
  __int64 v22; // r9
  void *Src; // rbx
  size_t Size; // [rsp+30h] [rbp-48h]
  _OWORD v25[2]; // [rsp+50h] [rbp-28h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  v4 = *(_QWORD *)(a1 + 48);
  LOBYTE(a2) = 18;
  v5 = *(_QWORD *)(a1 + 88);
  RDR_PERF_ENTER(a1 + 512, a2);
  v6 = *(_QWORD *)(a1 + 160);
  if ( v6 == a1 + 160 || v6 == 8 )
    goto LABEL_6;
  if ( v2 >= 0 )
    v2 = *(_DWORD *)(v6 + 40);
  SmbCseFinalizeBufferContext(v6 - 8);
  if ( !v2 )
  {
LABEL_6:
    if ( !v4 )
      goto LABEL_15;
  }
  else
  {
    if ( !v4 )
      goto LABEL_15;
    v19 = *(_QWORD *)(v4 + 72);
    if ( v19 )
    {
      v20 = *(_QWORD *)(v19 + 48);
      if ( v20 )
      {
        v21 = *(_DWORD *)(v20 + 8);
        if ( ((v21 & 0x20) != 0 || (v21 & 0x40) != 0) && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000) != 0 )
        {
          v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v19 + 32) + 120LL) + 88LL);
          McTemplateK0qqhzr2hzr4_EtwWriteTransfer(
            **(_WORD **)(v19 + 80) >> 1,
            (unsigned int)CloseFailure,
            *(_QWORD *)(v19 + 80),
            0,
            v2,
            *(_WORD *)v22 >> 1,
            *(_QWORD *)(v22 + 8),
            **(_WORD **)(v19 + 80) >> 1,
            *(_QWORD *)(*(_QWORD *)(v19 + 80) + 8LL));
        }
      }
    }
  }
  if ( *(_BYTE *)(a1 + 2409) )
  {
    v7 = *(_BYTE *)(v4 + 504);
    if ( (v7 & 1) != 0 )
    {
      *(_BYTE *)(v4 + 504) = v7 | 2;
      *(_OWORD *)(v4 + 448) = *(_OWORD *)(a1 + 2416);
      *(_OWORD *)(v4 + 464) = *(_OWORD *)(a1 + 2432);
      *(_OWORD *)(v4 + 480) = *(_OWORD *)(a1 + 2448);
      *(_QWORD *)(v4 + 496) = *(_QWORD *)(a1 + 2464);
    }
    v8 = *(_QWORD *)(v4 + 56);
    if ( (*(_DWORD *)(v8 + 156) & 1) == 0 )
    {
      v9 = *(_QWORD *)(v8 + 120);
      v10 = *(_QWORD *)(v9 + 32);
      if ( (*(_DWORD *)(v10 + 96) & 0x80u) != 0
        || (*(_BYTE *)(*(_QWORD *)(v10 + 32) + 764LL) & 2) == 0
        || (*(_DWORD *)(*(_QWORD *)(v8 + 136) + 8LL) & 1) != 0
        || *(_BYTE *)(v9 + 77)
        || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 72) + 40LL) + 40LL) + 424LL) + 184LL)
          & 0x800000) != 0 )
      {
        MRxSmbGetInstanceConfigurationBlock(*(_QWORD *)(v4 + 80));
      }
      else if ( *(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(*(_QWORD *)(v4 + 80)) + 12) )
      {
        Src = (void *)(a1 + 2416);
        Smb2UpdateSingleFileInDirInfoCache(
          (_QWORD *)v4,
          (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v5 + 424) + 1112LL),
          (__int64)Src,
          v11);
        LODWORD(Size) = 56;
        Smb2UpdateFileInfoCacheEntry(
          (_QWORD *)v4,
          (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v5 + 424) + 376LL),
          1,
          0x22u,
          0,
          Src,
          Size);
      }
    }
  }
LABEL_15:
  v12 = *(_QWORD *)(v4 + 72);
  v25[0] = 0;
  if ( v12 )
  {
    v13 = *(_QWORD *)(v12 + 48);
    v14 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 40) + 40LL) + 24LL);
    ExAcquirePushLockExclusiveEx(v13 + 16, 0);
    v15 = (_OWORD *)(v13 + 56);
    if ( *(_OWORD **)v15 == v15 )
    {
      *((_QWORD *)&v25[0] + 1) = v25;
      *(_QWORD *)&v25[0] = v25;
    }
    else
    {
      v25[0] = *v15;
      *(_QWORD *)(*(_QWORD *)&v25[0] + 8LL) = v25;
      **((_QWORD **)&v25[0] + 1) = v25;
      *(_QWORD *)(v13 + 64) = v13 + 56;
      *(_QWORD *)v15 = v15;
    }
    v16 = *(_DWORD *)(v13 + 44);
    *(_DWORD *)(v13 + 4) = 9;
    ExReleasePushLockExclusiveEx(v13 + 16, 0);
    v17 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v14 + 1920));
    *(_DWORD *)(v14 + 2352) = (unsigned int)PsGetCurrentThreadId();
    SmbCeResumeSuspendedExchangesLite(v25, 1, 3, v16, 0x13C0000128LL, 0);
    *(_DWORD *)(v14 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v14 + 1920), v17);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400129f0  mov     [rsp+arg_10], rbx
0x1400129f5  push    rsi
0x1400129f6  push    rdi
0x1400129f7  push    r14
0x1400129f9  sub     rsp, 60h
0x1400129fd  mov     r14d, [rcx+10h]
0x140012a01  mov     rbx, rcx
0x140012a04  mov     rdi, [rcx+30h]
0x140012a08  mov     dl, 12h
0x140012a0a  mov     rsi, [rcx+58h]
0x140012a0e  add     rcx, 200h
0x140012a15  call    cs:__imp_RDR_PERF_ENTER
0x140012a1c  nop     dword ptr [rax+rax+00h]
0x140012a21  lea     rax, [rbx+0A0h]
0x140012a28  mov     rdx, [rax]
0x140012a2b  cmp     rdx, rax
0x140012a2e  jz      short loc_140012A57
0x140012a30  lea     rcx, [rdx-8]
0x140012a34  test    rcx, rcx
0x140012a37  jz      short loc_140012A57
0x140012a39  test    r14d, r14d
0x140012a3c  js      short loc_140012A42
0x140012a3e  mov     r14d, [rdx+28h]
0x140012a42  call    cs:__imp_SmbCseFinalizeBufferContext
0x140012a49  nop     dword ptr [rax+rax+00h]
0x140012a4e  test    r14d, r14d
0x140012a51  jnz     loc_140012CBD
0x140012a57  test    rdi, rdi
0x140012a5a  jz      loc_140012B07
0x140012a60  cmp     byte ptr [rbx+969h], 0
0x140012a67  jz      loc_140012B07
0x140012a6d  movzx   eax, byte ptr [rdi+1F8h]
0x140012a74  test    al, 1
0x140012a76  jz      short loc_140012ABA
0x140012a78  or      al, 2
0x140012a7a  mov     [rdi+1F8h], al
0x140012a80  movups  xmm0, xmmword ptr [rbx+970h]
0x140012a87  movups  xmmword ptr [rdi+1C0h], xmm0
0x140012a8e  movups  xmm1, xmmword ptr [rbx+980h]
0x140012a95  movups  xmmword ptr [rdi+1D0h], xmm1
0x140012a9c  movups  xmm0, xmmword ptr [rbx+990h]
0x140012aa3  movups  xmmword ptr [rdi+1E0h], xmm0
0x140012aaa  movsd   xmm1, qword ptr [rbx+9A0h]
0x140012ab2  movsd   qword ptr [rdi+1F0h], xmm1
0x140012aba  mov     rdx, [rdi+38h]
0x140012abe  mov     eax, [rdx+9Ch]
0x140012ac4  test    al, 1
0x140012ac6  jnz     short loc_140012B07
0x140012ac8  mov     r8, [rdx+78h]
0x140012acc  mov     rcx, [r8+20h]
0x140012ad0  mov     eax, [rcx+60h]
0x140012ad3  test    al, al
0x140012ad5  jns     loc_140012C66
0x140012adb  mov     rcx, [rdi+50h]
0x140012adf  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x140012ae6  nop     dword ptr [rax+rax+00h]
0x140012aeb  jmp     short loc_140012B07
0x140012aed  mov     rcx, [rdi+50h]
0x140012af1  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x140012af8  nop     dword ptr [rax+rax+00h]
0x140012afd  cmp     dword ptr [rax+0Ch], 0
0x140012b01  jnz     loc_14003AD91
0x140012b07  mov     rdx, [rdi+48h]
0x140012b0b  xorps   xmm0, xmm0
0x140012b0e  movups  [rsp+78h+var_28], xmm0
0x140012b13  test    rdx, rdx
0x140012b16  jz      loc_140012C1E
0x140012b1c  mov     rax, [rdx+28h]
0x140012b20  mov     rbx, [rdx+30h]
0x140012b24  xor     edx, edx
0x140012b26  mov     [rsp+78h+arg_8], rbp
0x140012b2e  mov     rcx, [rax+28h]
0x140012b32  mov     rbp, [rcx+18h]
0x140012b36  lea     rcx, [rbx+10h]
0x140012b3a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140012b41  nop     dword ptr [rax+rax+00h]
0x140012b46  lea     rcx, [rbx+38h]
0x140012b4a  cmp     [rcx], rcx
0x140012b4d  jnz     loc_140012C33
0x140012b53  lea     rax, [rsp+78h+var_28]
0x140012b58  mov     qword ptr [rsp+78h+var_28+8], rax
0x140012b5d  lea     rax, [rsp+78h+var_28]
0x140012b62  mov     qword ptr [rsp+78h+var_28], rax
0x140012b67  mov     edi, [rbx+2Ch]
0x140012b6a  lea     rcx, [rbx+10h]
0x140012b6e  xor     edx, edx
0x140012b70  mov     dword ptr [rbx+4], 9
0x140012b77  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140012b7e  nop     dword ptr [rax+rax+00h]
0x140012b83  lea     rcx, [rbp+780h]; SpinLock
0x140012b8a  call    cs:__imp_ExAcquireSpinLockExclusive
0x140012b91  nop     dword ptr [rax+rax+00h]
0x140012b96  movzx   ebx, al
0x140012b99  call    cs:__imp_PsGetCurrentThreadId
0x140012ba0  nop     dword ptr [rax+rax+00h]
0x140012ba5  mov     dword ptr [rsp+78h+arg_0], 0C0000128h
0x140012bb0  lea     rcx, [rsp+78h+var_28]
0x140012bb5  mov     dword ptr [rsp+78h+arg_0+4], 13h
0x140012bc0  mov     r9d, edi
0x140012bc3  mov     r8, [rsp+78h+arg_0]
0x140012bcb  mov     edx, 1
0x140012bd0  mov     [rsp+78h+Src], 0
0x140012bd9  mov     qword ptr [rsp+78h+var_58], r8
0x140012bde  mov     r8d, 3
0x140012be4  mov     [rbp+930h], eax
0x140012bea  call    cs:__imp_SmbCeResumeSuspendedExchangesLite
0x140012bf1  nop     dword ptr [rax+rax+00h]
0x140012bf6  movzx   edx, bl; OldIrql
0x140012bf9  mov     dword ptr [rbp+930h], 0FFFFFFFFh
0x140012c03  lea     rcx, [rbp+780h]; SpinLock
0x140012c0a  call    cs:__imp_ExReleaseSpinLockExclusive
0x140012c11  nop     dword ptr [rax+rax+00h]
0x140012c16  mov     rbp, [rsp+78h+arg_8]
0x140012c1e  mov     rbx, [rsp+78h+arg_10]
0x140012c26  mov     eax, r14d
0x140012c29  add     rsp, 60h
0x140012c2d  pop     r14
0x140012c2f  pop     rdi
0x140012c30  pop     rsi
0x140012c31  retn
0x140012c33  mov     rdx, [rcx]
0x140012c36  mov     qword ptr [rsp+78h+var_28], rdx
0x140012c3b  mov     rax, [rcx+8]
0x140012c3f  mov     qword ptr [rsp+78h+var_28+8], rax
0x140012c44  lea     rax, [rsp+78h+var_28]
0x140012c49  mov     [rdx+8], rax
0x140012c4d  lea     rdx, [rsp+78h+var_28]
0x140012c52  mov     rax, qword ptr [rsp+78h+var_28+8]
0x140012c57  mov     [rax], rdx
0x140012c5a  mov     [rcx+8], rcx
0x140012c5e  mov     [rcx], rcx
0x140012c61  jmp     loc_140012B67
0x140012c66  mov     rax, [rcx+20h]
0x140012c6a  test    byte ptr [rax+2FCh], 2
0x140012c71  jz      loc_140012ADB
0x140012c77  mov     rax, [rdx+88h]
0x140012c7e  mov     ecx, [rax+8]
0x140012c81  test    cl, 1
0x140012c84  jnz     loc_140012ADB
0x140012c8a  cmp     byte ptr [r8+4Dh], 0
0x140012c8f  jnz     loc_140012ADB
0x140012c95  mov     rax, [rdi+48h]
0x140012c99  mov     rcx, [rax+28h]
0x140012c9d  mov     rax, [rcx+28h]
0x140012ca1  mov     rcx, [rax+1A8h]
0x140012ca8  test    dword ptr [rcx+0B8h], 800000h
0x140012cb2  jnz     loc_140012ADB
0x140012cb8  jmp     loc_140012AED
0x140012cbd  test    rdi, rdi
0x140012cc0  jz      loc_140012B07
0x140012cc6  mov     rax, [rdi+48h]
0x140012cca  test    rax, rax
0x140012ccd  jz      loc_140012A60
0x140012cd3  mov     rcx, [rax+30h]
0x140012cd7  test    rcx, rcx
0x140012cda  jz      loc_140012A60
0x140012ce0  mov     edx, [rcx+8]
0x140012ce3  test    dl, 20h
0x140012ce6  jnz     loc_14003AD30
0x140012cec  test    dl, 40h
0x140012cef  jz      loc_140012A60
0x140012cf5  jmp     loc_14003AD30
0x14003ad30  cmp     byte ptr cs:WPP_MAIN_CB.Queue+11h, 0
0x14003ad37  jge     loc_140012A60
0x14003ad3d  mov     r8, [rax+50h]
0x14003ad41  mov     rax, [rax+20h]
0x14003ad45  mov     rcx, [rax+78h]
0x14003ad49  mov     rax, [r8+8]
0x14003ad4d  mov     [rsp+78h+var_38], rax
0x14003ad52  mov     r9, [rcx+58h]
0x14003ad56  movzx   ecx, word ptr [r8]
0x14003ad5a  shr     cx, 1
0x14003ad5d  mov     [rsp+78h+var_40], cx
0x14003ad62  movzx   edx, word ptr [r9]
0x14003ad66  mov     rax, [r9+8]
0x14003ad6a  xor     r9d, r9d
0x14003ad6d  shr     dx, 1
0x14003ad70  mov     [rsp+78h+Size], rax
0x14003ad75  mov     word ptr [rsp+78h+Src], dx
0x14003ad7a  lea     rdx, CloseFailure
0x14003ad81  mov     [rsp+78h+var_58], r14d
0x14003ad86  call    McTemplateK0qqhzr2hzr4_EtwWriteTransfer
0x14003ad8b  nop
0x14003ad8c  jmp     loc_140012A60
0x14003ad91  mov     rdx, [rsi+1A8h]
0x14003ad98  add     rbx, 970h
0x14003ad9f  add     rdx, 458h
0x14003ada6  mov     r8, rbx
0x14003ada9  mov     rcx, rdi
0x14003adac  call    Smb2UpdateSingleFileInDirInfoCache
0x14003adb1  mov     rdx, [rsi+1A8h]
0x14003adb8  mov     r9d, 22h ; '"'; int
0x14003adbe  mov     dword ptr [rsp+78h+Size], 38h ; '8'; Size
0x14003adc6  add     rdx, 178h; int
0x14003adcd  mov     [rsp+78h+Src], rbx; Src
0x14003add2  mov     r8d, 1; int
0x14003add8  mov     rcx, rdi; int
0x14003addb  mov     [rsp+78h+var_58], 0; int
0x14003ade3  call    Smb2UpdateFileInfoCacheEntry
0x14003ade8  nop
0x14003ade9  jmp     loc_140012B07
```
