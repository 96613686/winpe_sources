# Smb2SessionSetup_Start

- ea: `0x140026630`
- end: `0x140026bbd`
- name: `Smb2SessionSetup_Start`
- size: `1421`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14000deb0`
- `0x1400122d0`
- `0x140026630`
- `0x14002ec3c`
- `0x14002edcc`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140026b6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026b85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026b6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026b85`
- `ntoskrnl!ExAllocatePool2` at `0x140026886`
- `ntoskrnl!ExAllocatePool2` at `0x140026921`
- `ntoskrnl!ExAllocatePool2` at `0x140026a38`
- `ntoskrnl!ExAllocatePool2` at `0x140026886`
- `ntoskrnl!ExAllocatePool2` at `0x140026921`
- `ntoskrnl!ExAllocatePool2` at `0x140026a38`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140026a1c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140026a1c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400269aa`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400269aa`
- `rdbss!RxFreeMdl` at `0x140026661`
- `rdbss!RxFreeMdl` at `0x14002681f`
- `rdbss!RxFreeMdl` at `0x1400268ac`
- `rdbss!RxFreeMdl` at `0x140026a0b`
- `rdbss!RxFreeMdl` at `0x140026a54`
- `rdbss!RxFreeMdl` at `0x140026b53`
- `rdbss!RxFreeMdl` at `0x140026661`
- `rdbss!RxFreeMdl` at `0x14002681f`
- `rdbss!RxFreeMdl` at `0x1400268ac`
- `rdbss!RxFreeMdl` at `0x140026a0b`
- `rdbss!RxFreeMdl` at `0x140026a54`
- `rdbss!RxFreeMdl` at `0x140026b53`
- `rdbss!RxAllocateMdl2` at `0x1400269ef`
- `rdbss!RxAllocateMdl2` at `0x1400269ef`
- `ksecdd!SecMakeSPNEx2` at `0x1400267b8`
- `ksecdd!SecMakeSPNEx2` at `0x1400267d5`
- `ksecdd!SecMakeSPNEx2` at `0x1400267b8`
- `ksecdd!SecMakeSPNEx2` at `0x1400267d5`
- `mrxsmb!UninitializeSecurityContextForBindingObject` at `0x1400266e8`
- `mrxsmb!UninitializeSecurityContextForBindingObject` at `0x1400266e8`
- `mrxsmb!SmbCeReferenceBindingObject` at `0x1400266d9`
- `mrxsmb!SmbCeReferenceBindingObject` at `0x1400266d9`
- `mrxsmb!SmbCryptoHashCreate` at `0x1400268f4`
- `mrxsmb!SmbCryptoHashCreate` at `0x1400268f4`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140026adf`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140026b22`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140026adf`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140026b22`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140026ac8`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140026ac8`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140026b35`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140026b35`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140026a93`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140026a93`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140026845`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140026845`

## pseudocode

```c
__int64 __fastcall Smb2SessionSetup_Start(__int64 a1)
{
  __int64 v1; // r15
  __int64 v4; // rbp
  struct _MDL *Mdl2; // rsi
  _QWORD *v6; // r14
  unsigned int v7; // r13d
  int v8; // r8d
  __int64 v9; // rbx
  struct _UNICODE_STRING v10; // xmm0
  struct _UNICODE_STRING *v11; // rbx
  NTSTATUS SPNEx2; // eax
  int v13; // edx
  int v14; // r8d
  int v15; // ebx
  unsigned int v16; // ecx
  void *v17; // rax
  char *Pool2; // rbp
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rbx
  __int64 v24; // r15
  KIRQL v25; // al
  __int64 v26; // rcx
  unsigned int v27; // ebx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rbx
  __int64 v31; // rsi
  __int64 v32; // rdx
  PUNICODE_STRING InTargetInfo; // [rsp+28h] [rbp-70h]
  struct _UNICODE_STRING *Spn; // [rsp+30h] [rbp-68h]
  PULONG TotalSize; // [rsp+38h] [rbp-60h]
  int Allocate; // [rsp+40h] [rbp-58h]
  struct _UNICODE_STRING InstanceName; // [rsp+50h] [rbp-48h] BYREF
  ULONG v38; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v39; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v40; // [rsp+B0h] [rbp+18h]

  v1 = *(_QWORD *)(a1 + 96);
  v39 = 0;
  if ( !*(_DWORD *)(*(_QWORD *)(v1 + 392) + 320LL) )
  {
    RxFreeMdl(0);
    return 3221225701LL;
  }
  v4 = *(_QWORD *)(a1 + 80);
  Mdl2 = 0;
  v6 = 0;
  v40 = *(_QWORD *)(a1 + 72);
  if ( !*(_BYTE *)(a1 + 1081) )
    _InterlockedAnd((volatile signed __int32 *)(a1 + 68), 0xFEFFFFFF);
  v7 = 10;
  if ( !*(_BYTE *)(a1 + 1080) )
    goto LABEL_28;
  SmbCeReferenceBindingObject(v1);
  UninitializeSecurityContextForBindingObject(v1);
  v9 = *(_QWORD *)(v4 + 128);
  v10 = *(struct _UNICODE_STRING *)(*(_QWORD *)(v4 + 384) + 128LL);
  v38 = 0;
  *(_OWORD *)(a1 + 1088) = 0;
  *(_BYTE *)(a1 + 1084) = 0;
  InstanceName = v10;
  if ( v9 )
    v11 = *(struct _UNICODE_STRING **)(v9 + 40);
  else
    v11 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 10, v8, (unsigned int)&InstanceName, (__int64)v11);
  }
  Spn = (struct _UNICODE_STRING *)(a1 + 1088);
  if ( *(_QWORD *)(v4 + 592) )
  {
    SPNEx2 = SecMakeSPNEx2(&CifsServiceName, (PUNICODE_STRING)(v4 + 584), &InstanceName, 0, 0, v11, Spn, &v38, 1u, 0);
    *(_BYTE *)(a1 + 1084) = 1;
  }
  else
  {
    SPNEx2 = SecMakeSPNEx2(&CifsServiceName, &InstanceName, 0, 0, 0, v11, Spn, &v38, 1u, 0);
  }
  v15 = SPNEx2;
  if ( SPNEx2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_LZ(WPP_GLOBAL_Control->AttachedDevice, v13, v14, SPNEx2, (__int64)&InstanceName);
    }
    RxFreeMdl(0);
    return (unsigned int)v15;
  }
  if ( !(unsigned __int8)SmbCeCheckServerEntryDialect(*(_QWORD *)(v4 + 384), 3, 1, 1) || *(_BYTE *)(a1 + 1081) )
  {
LABEL_28:
    *(_QWORD *)(a1 + 1024) = v1;
    Pool2 = (char *)ExAllocatePool2(66, 0x4000, 1834185555);
    if ( !Pool2 )
      goto LABEL_26;
    if ( *(_BYTE *)(a1 + 1080) )
    {
      v23 = *(_QWORD *)(v1 + 392);
      v24 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL);
      *(_BYTE *)(a1 + 1080) = 0;
      v25 = SmbCeAcquireSpinLock(v24, v20, v21, v22);
      v26 = *(_QWORD *)(v23 + 552);
      if ( v26 )
      {
        *(_QWORD *)(a1 + 1056) = v26;
        *(_DWORD *)(a1 + 1064) = *(_DWORD *)(v23 + 560);
        *(_BYTE *)(a1 + 1082) = 1;
        *(_QWORD *)(v23 + 552) = 0;
        *(_DWORD *)(v23 + 560) = 0;
      }
      *(_DWORD *)(v24 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v24 + 1920), v25);
    }
    v15 = BuildSessionSetupSmb(a1, Pool2 + 32, v21, &v39);
    if ( v15 >= 0 )
    {
      v27 = v39;
      Mdl2 = (struct _MDL *)RxAllocateMdl2(Pool2 + 32, v39, 0, 0, 0);
      if ( !Mdl2 )
      {
        v15 = -1073741670;
        RxFreeMdl(0);
LABEL_51:
        ExFreePoolWithTag(Pool2, 0x6D537353u);
LABEL_52:
        if ( v6 )
          ExFreePoolWithTag(v6, 0x6D537353u);
        return (unsigned int)v15;
      }
      MmBuildMdlForNonPagedPool(Mdl2);
      v28 = ExAllocatePool2(66, 1384, 1834185555);
      v6 = (_QWORD *)v28;
      if ( !v28 )
      {
        v15 = -1073741670;
        RxFreeMdl(Mdl2);
        goto LABEL_51;
      }
      LOWORD(Allocate) = 0;
      LODWORD(TotalSize) = 0;
      LODWORD(InTargetInfo) = 0;
      v15 = SmbCseInitializeBufferContextWithMemoryRegistration(
              v28,
              a1,
              Mdl2,
              v27,
              0,
              InTargetInfo,
              0,
              TotalSize,
              Allocate,
              4);
      if ( !v15 )
      {
        v30 = *(_QWORD *)(a1 + 80);
        v31 = v40;
        if ( *(_DWORD *)(v30 + 432) )
        {
          v32 = *(unsigned int *)(v40 + 776);
          if ( !(_DWORD)v32 )
            v32 = *(_DWORD *)(MRxSmbGetConfigurationBlock(v29) + 12) >> 1;
          SmbCeSetConnectionKeepalive(v30, v32, 0);
        }
        if ( *(_DWORD *)(v30 + 704) || (*(_BYTE *)(*(_QWORD *)(a1 + 72) + 737LL) & 3) == 3 )
        {
          if ( *(_DWORD *)(v31 + 772) )
            v7 = *(_DWORD *)(v31 + 772);
          SmbCeSetConnectionKeepalive(v30, v7, 2);
        }
        v6[11] = Pool2;
        Pool2 = 0;
        Mdl2 = 0;
        v15 = SmbCseSubmitBufferContext(v6);
        v6 = 0;
      }
      if ( v15 >= 0 )
        return (unsigned int)v15;
    }
LABEL_50:
    RxFreeMdl(Mdl2);
    if ( !Pool2 )
      goto LABEL_52;
    goto LABEL_51;
  }
  v16 = *(_DWORD *)(*(_QWORD *)(v1 + 392) + 572LL);
  *(_DWORD *)(a1 + 1048) = v16;
  v17 = (void *)ExAllocatePool2(66, v16, 1834182736);
  *(_QWORD *)(a1 + 1040) = v17;
  if ( v17 )
  {
    Pool2 = 0;
    memmove(v17, *(const void **)(*(_QWORD *)(v1 + 392) + 576LL), *(unsigned int *)(a1 + 1048));
    LOBYTE(v19) = 1;
    v15 = SmbCryptoHashCreate(a1 + 1032, *(unsigned int *)(*(_QWORD *)(v1 + 392) + 568LL), v19);
    if ( v15 < 0 )
      goto LABEL_50;
    goto LABEL_28;
  }
  *(_DWORD *)(a1 + 1048) = 0;
LABEL_26:
  v15 = -1073741670;
  RxFreeMdl(0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140026630  push    rdi
0x140026632  push    r12
0x140026634  push    r15
0x140026636  sub     rsp, 80h
0x14002663d  mov     r15, [rcx+60h]
0x140026641  xor     r12d, r12d
0x140026644  mov     rdi, rcx
0x140026647  mov     [rsp+98h+arg_8], r12d
0x14002664f  mov     rax, [r15+188h]
0x140026656  cmp     [rax+140h], r12d
0x14002665d  jnz     short loc_140026680
0x14002665f  xor     ecx, ecx
0x140026661  call    cs:__imp_RxFreeMdl
0x140026668  nop     dword ptr [rax+rax+00h]
0x14002666d  mov     eax, 0C00000E5h
0x140026672  add     rsp, 80h
0x140026679  pop     r15
0x14002667b  pop     r12
0x14002667d  pop     rdi
0x14002667e  retn
0x140026680  mov     rax, [rcx+48h]
0x140026684  mov     [rsp+98h+var_20], rbp
0x140026689  mov     rbp, [rcx+50h]
0x14002668d  mov     [rsp+98h+var_28], rsi
0x140026692  mov     rsi, r12
0x140026695  mov     [rsp+98h+var_30], r13
0x14002669a  mov     [rsp+98h+var_38], r14
0x14002669f  mov     r14, r12
0x1400266a2  mov     [rsp+98h+arg_10], rax
0x1400266aa  cmp     [rcx+439h], sil
0x1400266b1  jnz     short loc_1400266BB
0x1400266b3  lock and dword ptr [rcx+44h], 0FEFFFFFFh
0x1400266bb  mov     r13d, 0Ah
0x1400266c1  mov     [rsp+98h+arg_18], rbx
0x1400266c9  cmp     [rcx+438h], sil
0x1400266d0  jz      loc_14002690A
0x1400266d6  mov     rcx, r15
0x1400266d9  call    cs:__imp_SmbCeReferenceBindingObject
0x1400266e0  nop     dword ptr [rax+rax+00h]
0x1400266e5  mov     rcx, r15
0x1400266e8  call    cs:__imp_UninitializeSecurityContextForBindingObject
0x1400266ef  nop     dword ptr [rax+rax+00h]
0x1400266f4  mov     rax, [rbp+180h]
0x1400266fb  lea     r12, [rdi+440h]
0x140026702  mov     rbx, [rbp+80h]
0x140026709  xor     ecx, ecx
0x14002670b  xorps   xmm1, xmm1
0x14002670e  movups  xmm0, xmmword ptr [rax+80h]
0x140026715  mov     [rsp+98h+arg_0], ecx
0x14002671c  movups  xmmword ptr [r12], xmm1
0x140026721  mov     [rdi+43Ch], cl
0x140026727  movups  xmmword ptr [rsp+98h+InstanceName.Length], xmm0
0x14002672c  test    rbx, rbx
0x14002672f  jz      short loc_140026737
0x140026731  mov     rbx, [rbx+28h]
0x140026735  jmp     short loc_14002673A
0x140026737  mov     rbx, rcx
0x14002673a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140026741  lea     rax, WPP_GLOBAL_Control
0x140026748  cmp     rcx, rax
0x14002674b  jz      short loc_140026770
0x14002674d  mov     eax, [rcx+2Ch]
0x140026750  test    al, 8
0x140026752  jz      short loc_140026770
0x140026754  cmp     byte ptr [rcx+29h], 2
0x140026758  jb      short loc_140026770
0x14002675a  mov     rcx, [rcx+18h]
0x14002675e  lea     r9, [rsp+98h+InstanceName]
0x140026763  mov     edx, r13d
0x140026766  mov     [rsp+98h+Referrer], rbx
0x14002676b  call    WPP_SF_ZZ
0x140026770  mov     [rsp+98h+IsTargetInfoMarshaled], sil; IsTargetInfoMarshaled
0x140026775  lea     rax, [rsp+98h+arg_0]
0x14002677d  mov     [rsp+98h+Allocate], 1; Allocate
0x140026782  lea     rcx, CifsServiceName; ServiceClass
0x140026789  mov     [rsp+98h+TotalSize], rax; TotalSize
0x14002678e  xor     r9d, r9d; InstancePort
0x140026791  mov     [rsp+98h+Spn], r12; Spn
0x140026796  xor     r12d, r12d
0x140026799  mov     [rsp+98h+InTargetInfo], rbx; InTargetInfo
0x14002679e  mov     [rsp+98h+Referrer], r12; Referrer
0x1400267a3  cmp     [rbp+250h], rsi
0x1400267aa  jz      short loc_1400267CD
0x1400267ac  lea     rdx, [rbp+248h]; ServiceName
0x1400267b3  lea     r8, [rsp+98h+InstanceName]; InstanceName
0x1400267b8  call    cs:__imp_SecMakeSPNEx2
0x1400267bf  nop     dword ptr [rax+rax+00h]
0x1400267c4  mov     byte ptr [rdi+43Ch], 1
0x1400267cb  jmp     short loc_1400267E1
0x1400267cd  xor     r8d, r8d; InstanceName
0x1400267d0  lea     rdx, [rsp+98h+InstanceName]; ServiceName
0x1400267d5  call    cs:__imp_SecMakeSPNEx2
0x1400267dc  nop     dword ptr [rax+rax+00h]
0x1400267e1  mov     ebx, eax
0x1400267e3  test    eax, eax
0x1400267e5  jns     short loc_140026830
0x1400267e7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400267ee  lea     rax, WPP_GLOBAL_Control
0x1400267f5  cmp     rcx, rax
0x1400267f8  jz      short loc_14002681D
0x1400267fa  mov     eax, [rcx+2Ch]
0x1400267fd  test    al, 1
0x1400267ff  jz      short loc_14002681D
0x140026801  cmp     byte ptr [rcx+29h], 1
0x140026805  jb      short loc_14002681D
0x140026807  mov     rcx, [rcx+18h]
0x14002680b  lea     rax, [rsp+98h+InstanceName]
0x140026810  mov     r9d, ebx
0x140026813  mov     [rsp+98h+Referrer], rax
0x140026818  call    WPP_SF_LZ
0x14002681d  xor     ecx, ecx
0x14002681f  call    cs:__imp_RxFreeMdl
0x140026826  nop     dword ptr [rax+rax+00h]
0x14002682b  jmp     loc_140026B91
0x140026830  mov     rcx, [rbp+180h]
0x140026837  mov     r9d, 1
0x14002683d  mov     r8d, r9d
0x140026840  mov     edx, 3
0x140026845  call    cs:__imp_SmbCeCheckServerEntryDialect
0x14002684c  nop     dword ptr [rax+rax+00h]
0x140026851  test    al, al
0x140026853  jz      loc_14002690A
0x140026859  cmp     [rdi+439h], sil
0x140026860  jnz     loc_14002690A
0x140026866  mov     rax, [r15+188h]
0x14002686d  mov     r8d, 6D536850h
0x140026873  mov     ecx, [rax+23Ch]
0x140026879  mov     [rdi+418h], ecx
0x14002687f  mov     edx, ecx
0x140026881  mov     ecx, 42h ; 'B'
0x140026886  call    cs:__imp_ExAllocatePool2
0x14002688d  nop     dword ptr [rax+rax+00h]
0x140026892  mov     [rdi+410h], rax
0x140026899  test    rax, rax
0x14002689c  jnz     short loc_1400268BD
0x14002689e  mov     [rdi+418h], r12d
0x1400268a5  xor     ecx, ecx
0x1400268a7  mov     ebx, 0C000009Ah
0x1400268ac  call    cs:__imp_RxFreeMdl
0x1400268b3  nop     dword ptr [rax+rax+00h]
0x1400268b8  jmp     loc_140026B91
0x1400268bd  mov     rdx, [r15+188h]
0x1400268c4  mov     rcx, rax; void *
0x1400268c7  mov     r8d, [rdi+418h]; Size
0x1400268ce  mov     rbp, r12
0x1400268d1  mov     rdx, [rdx+240h]; Src
0x1400268d8  call    memmove
0x1400268dd  mov     rdx, [r15+188h]
0x1400268e4  lea     rcx, [rdi+408h]
0x1400268eb  mov     r8b, 1
0x1400268ee  mov     edx, [rdx+238h]
0x1400268f4  call    cs:__imp_SmbCryptoHashCreate
0x1400268fb  nop     dword ptr [rax+rax+00h]
0x140026900  mov     ebx, eax
0x140026902  test    eax, eax
0x140026904  js      loc_140026B50
0x14002690a  mov     edx, 4000h
0x14002690f  mov     [rdi+400h], r15
0x140026916  mov     ecx, 42h ; 'B'
0x14002691b  mov     r8d, 6D537353h
0x140026921  call    cs:__imp_ExAllocatePool2
0x140026928  nop     dword ptr [rax+rax+00h]
0x14002692d  mov     rbp, rax
0x140026930  test    rax, rax
0x140026933  jz      loc_1400268A5
0x140026939  cmp     [rdi+438h], sil
0x140026940  jz      short loc_1400269B6
0x140026942  mov     rbx, [r15+188h]
0x140026949  mov     rax, [rdi+48h]
0x14002694d  mov     r15, [rax+18h]
0x140026951  mov     rcx, r15
0x140026954  mov     [rdi+438h], sil
0x14002695b  call    SmbCeAcquireSpinLock
0x140026960  mov     rcx, [rbx+228h]
0x140026967  test    rcx, rcx
0x14002696a  jz      short loc_140026995
0x14002696c  mov     [rdi+420h], rcx
0x140026973  mov     ecx, [rbx+230h]
0x140026979  mov     [rdi+428h], ecx
0x14002697f  xor     ecx, ecx
0x140026981  mov     byte ptr [rdi+43Ah], 1
0x140026988  mov     [rbx+228h], rcx
0x14002698f  mov     [rbx+230h], ecx
0x140026995  lea     rcx, [r15+780h]; SpinLock
0x14002699c  mov     dword ptr [r15+930h], 0FFFFFFFFh
0x1400269a7  movzx   edx, al; OldIrql
0x1400269aa  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400269b1  nop     dword ptr [rax+rax+00h]
0x1400269b6  lea     r9, [rsp+98h+arg_8]
0x1400269be  mov     rcx, rdi
0x1400269c1  lea     rdx, [rbp+20h]
0x1400269c5  call    BuildSessionSetupSmb
0x1400269ca  mov     ebx, eax
0x1400269cc  test    eax, eax
0x1400269ce  js      loc_140026B50
0x1400269d4  mov     ebx, [rsp+98h+arg_8]
0x1400269db  lea     rcx, [rbp+20h]
0x1400269df  xor     r15d, r15d
0x1400269e2  mov     edx, ebx
0x1400269e4  xor     r9d, r9d
0x1400269e7  mov     [rsp+98h+Referrer], r15
0x1400269ec  xor     r8d, r8d
0x1400269ef  call    cs:__imp_RxAllocateMdl2
0x1400269f6  nop     dword ptr [rax+rax+00h]
0x1400269fb  mov     rsi, rax
0x1400269fe  mov     rcx, rax; MemoryDescriptorList
0x140026a01  test    rax, rax
0x140026a04  jnz     short loc_140026A1C
0x140026a06  mov     ebx, 0C000009Ah
0x140026a0b  call    cs:__imp_RxFreeMdl
0x140026a12  nop     dword ptr [rax+rax+00h]
0x140026a17  jmp     loc_140026B64
0x140026a1c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140026a23  nop     dword ptr [rax+rax+00h]
0x140026a28  mov     edx, 568h
0x140026a2d  mov     ecx, 42h ; 'B'
0x140026a32  mov     r8d, 6D537353h
0x140026a38  call    cs:__imp_ExAllocatePool2
0x140026a3f  nop     dword ptr [rax+rax+00h]
0x140026a44  mov     r14, rax
0x140026a47  test    rax, rax
0x140026a4a  jnz     short loc_140026A65
0x140026a4c  mov     rcx, rsi
0x140026a4f  mov     ebx, 0C000009Ah
0x140026a54  call    cs:__imp_RxFreeMdl
0x140026a5b  nop     dword ptr [rax+rax+00h]
0x140026a60  jmp     loc_140026B64
0x140026a65  mov     dword ptr [rsp+98h+IsTargetInfoMarshaled], 4
0x140026a6d  mov     r9d, ebx
0x140026a70  mov     word ptr [rsp+98h+Allocate], r15w
0x140026a76  mov     r8, rsi
0x140026a79  mov     dword ptr [rsp+98h+TotalSize], r15d
0x140026a7e  mov     rdx, rdi
0x140026a81  mov     [rsp+98h+Spn], r15
0x140026a86  mov     rcx, r14
0x140026a89  mov     dword ptr [rsp+98h+InTargetInfo], r15d
0x140026a8e  mov     [rsp+98h+Referrer], r15
0x140026a93  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x140026a9a  nop     dword ptr [rax+rax+00h]
0x140026a9f  mov     ebx, eax
0x140026aa1  test    eax, eax
0x140026aa3  jnz     loc_140026B4C
0x140026aa9  mov     rbx, [rdi+50h]
0x140026aad  mov     rsi, [rsp+98h+arg_10]
0x140026ab5  cmp     [rbx+1B0h], r15d
0x140026abc  jbe     short loc_140026AEB
0x140026abe  mov     edx, [rsi+308h]
0x140026ac4  test    edx, edx
0x140026ac6  jnz     short loc_140026AD9
0x140026ac8  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140026acf  nop     dword ptr [rax+rax+00h]
0x140026ad4  mov     edx, [rax+0Ch]
0x140026ad7  shr     edx, 1
0x140026ad9  xor     r8d, r8d
0x140026adc  mov     rcx, rbx
0x140026adf  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140026ae6  nop     dword ptr [rax+rax+00h]
0x140026aeb  cmp     [rbx+2C0h], r15d
0x140026af2  ja      short loc_140026B0A
0x140026af4  mov     rax, [rdi+48h]
0x140026af8  movzx   r8d, byte ptr [rax+2E1h]
0x140026b00  and     r8b, 3
0x140026b04  cmp     r8b, 3
0x140026b08  jnz     short loc_140026B2E
0x140026b0a  mov     eax, [rsi+304h]
0x140026b10  mov     r8d, 2
0x140026b16  test    eax, eax
0x140026b18  mov     rcx, rbx
0x140026b1b  cmovnz  r13d, eax
0x140026b1f  mov     edx, r13d
0x140026b22  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140026b29  nop     dword ptr [rax+rax+00h]
0x140026b2e  mov     rcx, r14
0x140026b31  mov     [r14+58h], rbp
0x140026b35  call    cs:__imp_SmbCseSubmitBufferContext
0x140026b3c  nop     dword ptr [rax+rax+00h]
0x140026b41  mov     rbp, r15
0x140026b44  mov     rsi, r15
0x140026b47  mov     ebx, eax
0x140026b49  mov     r14, r15
0x140026b4c  test    ebx, ebx
0x140026b4e  jns     short loc_140026B91
0x140026b50  mov     rcx, rsi
0x140026b53  call    cs:__imp_RxFreeMdl
0x140026b5a  nop     dword ptr [rax+rax+00h]
0x140026b5f  test    rbp, rbp
0x140026b62  jz      short loc_140026B78
0x140026b64  mov     edx, 6D537353h; Tag
0x140026b69  mov     rcx, rbp; P
0x140026b6c  call    cs:__imp_ExFreePoolWithTag
0x140026b73  nop     dword ptr [rax+rax+00h]
0x140026b78  test    r14, r14
0x140026b7b  jz      short loc_140026B91
0x140026b7d  mov     edx, 6D537353h; Tag
0x140026b82  mov     rcx, r14; P
0x140026b85  call    cs:__imp_ExFreePoolWithTag
0x140026b8c  nop     dword ptr [rax+rax+00h]
0x140026b91  mov     rsi, [rsp+98h+var_28]
0x140026b96  mov     eax, ebx
0x140026b98  mov     rbx, [rsp+98h+arg_18]
  ... truncated ...
```
