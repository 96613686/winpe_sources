# Smb2SessionSetup_Finalize

- ea: `0x140053130`
- end: `0x140053879`
- name: `Smb2SessionSetup_Finalize`
- size: `1865`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14000d210`
- `0x14000d4e0`
- `0x14001b4c0`
- `0x14001e520`
- `0x140024ae0`
- `0x140026bd0`
- `0x140029084`
- `0x140029894`
- `0x14002e3ec`
- `0x14002eb78`
- `0x140037120`
- `0x140037240`
- `0x140053130`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140053739`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005377c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400537a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005380d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005382c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053845`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053739`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005377c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400537a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005380d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005382c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053845`
- `mrxsmb!SmbCeDereferenceBindingObject` at `0x140053711`
- `mrxsmb!SmbCeDereferenceBindingObject` at `0x140053711`
- `mrxsmb!SmbCryptoHashDestroy` at `0x140053758`
- `mrxsmb!SmbCryptoHashDestroy` at `0x140053758`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140053376`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140053376`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x1400537f3`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x1400537f3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400532e9`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140053358`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400532e9`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140053358`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x1400533fb`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x1400533fb`
- `mrxsmb!SmbCeDisconnectServerConnections` at `0x1400536c8`
- `mrxsmb!SmbCeDisconnectServerConnections` at `0x1400536c8`

## pseudocode

```c
__int64 __fastcall Smb2SessionSetup_Finalize(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // r13
  __int64 v4; // r12
  __int64 v5; // r14
  __int64 LastBufferContext; // rax
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // r15
  int v9; // esi
  unsigned int *v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // eax
  int v18; // r8d
  bool v19; // zf
  int v20; // eax
  int v21; // ecx
  void *v22; // rcx
  void *v23; // rcx
  __int64 v24; // r14
  __int64 v25; // rcx
  _QWORD *v26; // rbx
  __int64 v27; // rcx
  _QWORD *v28; // rdi
  int v29; // eax
  void *v30; // rcx
  void *v31; // rcx
  char v33; // [rsp+40h] [rbp-C0h] BYREF
  char v34; // [rsp+41h] [rbp-BFh] BYREF
  char v35; // [rsp+42h] [rbp-BEh] BYREF
  char v36; // [rsp+43h] [rbp-BDh] BYREF
  bool v37; // [rsp+44h] [rbp-BCh] BYREF
  char v38; // [rsp+45h] [rbp-BBh] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h]
  __int16 v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h]
  __int128 v42; // [rsp+60h] [rbp-A0h] BYREF
  int v43; // [rsp+70h] [rbp-90h] BYREF
  int v44; // [rsp+74h] [rbp-8Ch] BYREF
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+80h] [rbp-80h] BYREF
  __int128 *v46; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h]
  int *v48; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  char *v50; // [rsp+C0h] [rbp-40h]
  __int64 v51; // [rsp+C8h] [rbp-38h]
  char *v52; // [rsp+D0h] [rbp-30h]
  __int64 v53; // [rsp+D8h] [rbp-28h]
  char *v54; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  char *v56; // [rsp+F0h] [rbp-10h]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  bool *v58; // [rsp+100h] [rbp+0h]
  __int64 v59; // [rsp+108h] [rbp+8h]
  int *v60; // [rsp+110h] [rbp+10h]
  __int64 v61; // [rsp+118h] [rbp+18h]
  __int16 *v62; // [rsp+120h] [rbp+20h]
  __int64 v63; // [rsp+128h] [rbp+28h]
  char *v64; // [rsp+130h] [rbp+30h]
  __int64 v65; // [rsp+138h] [rbp+38h]

  v2 = *(_QWORD *)(a1 + 80);
  v3 = *(_QWORD *)(a1 + 1024);
  v4 = *(_QWORD *)(a1 + 1072);
  v39 = *(_QWORD *)(a1 + 16);
  v5 = *(_QWORD *)(v2 + 384);
  LastBufferContext = SmbCeGetLastBufferContext();
  v8 = LastBufferContext;
  if ( SLODWORD(v7->NextDevice) >= 0 && LastBufferContext )
  {
    v7 = *(PDEVICE_OBJECT *)(LastBufferContext + 48);
    v39 = (__int64)v7;
  }
  v9 = v39;
  if ( (int)v39 < 0 )
    goto LABEL_44;
  v10 = *(unsigned int **)(a1 + 1040);
  v11 = *(_QWORD *)(v5 + 24);
  v41 = v11;
  if ( v10 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Dqq(WPP_GLOBAL_Control->AttachedDevice, v11, &WPP_GLOBAL_Control, *v10, v2, *(_QWORD *)(v3 + 392));
      v11 = v41;
    }
  }
  if ( (*(_BYTE *)(v11 + 1314) & 8) == 0 || (*(_DWORD *)(v2 + 4) & 2) == 0 )
  {
    v12 = ValidateSessionSetupSecurityBlob((PVOID)v2);
    v11 = v41;
    v9 = v12;
    v39 = v12;
  }
  if ( v9 )
  {
    if ( v9 >= 0 )
    {
LABEL_32:
      if ( !*(_BYTE *)(v2 + 464) && !*(_BYTE *)(a1 + 1083) )
      {
        if ( !(unsigned __int8)SmbCeCheckServerEntryDialect(v5, 3, 1, 1)
          || (v17 = *(_DWORD *)(v2 + 4), (v17 & 1) != 0)
          || (v17 & 2) != 0 )
        {
LABEL_37:
          *(_QWORD *)(v2 + 600) = *(_QWORD *)(v2 + 440);
          *(_DWORD *)(v5 + 756) = 0;
          if ( (unsigned int)dword_140046050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140046050, 0x400000000000LL, 0) )
          {
            v19 = *(_BYTE *)(a1 + 1083) == (unsigned __int8)v18;
            v46 = &v42;
            v43 = *(_DWORD *)(v2 + 4);
            v37 = v19;
            *(_QWORD *)&v42 = 1;
            v48 = &v43;
            v33 = *(_BYTE *)(v2 + 464);
            v50 = &v33;
            v34 = *(_BYTE *)(v2 + 466);
            v52 = &v34;
            v35 = *(_BYTE *)(v2 + 465);
            v54 = &v35;
            v36 = *(_BYTE *)(v2 + 467);
            v56 = &v36;
            v58 = &v37;
            v44 = *(unsigned __int16 *)(v2 + 572);
            v60 = &v44;
            v40 = *(_WORD *)(v5 + 674);
            v62 = &v40;
            v47 = 8;
            v49 = 4;
            v51 = 1;
            v38 = *(_BYTE *)(v41 + 1312);
            v64 = &v38;
            v53 = 1;
            v55 = 1;
            v57 = 1;
            v59 = 1;
            v61 = 4;
            v63 = 2;
            v65 = 1;
            tlgWriteAgg(1, (int)&unk_140040258, v18, 12, &v45);
          }
          goto LABEL_54;
        }
      }
      v9 = Smb2ComputeIncomingSignatureInitial(v8, v3, *(_QWORD *)(v8 + 712), *(unsigned int *)(v8 + 748));
      if ( v9 >= 0 )
      {
        v20 = Smb2ValidateIncomingSignature(v8, v3, *(unsigned int *)(v8 + 748), *(_QWORD *)(v8 + 712));
        v9 = v20;
        if ( v20 >= 0 )
          goto LABEL_37;
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 )
          McTemplateK0qqq_EtwWriteTransfer(v21, (unsigned int)SessionSetupError, a1 + 312, v20, 162, 14);
      }
    }
LABEL_44:
    if ( (v9 == -2146893022 || v9 == -1073741073)
      && *(_DWORD *)(a1 + 104) == *(_DWORD *)(v5 + 392)
      && _InterlockedIncrement((volatile signed __int32 *)(v5 + 756)) >= 2
      && (((*(_BYTE *)(v5 + 737) & 0xC) - 4) & 0xF7) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qZd(
          WPP_GLOBAL_Control->AttachedDevice,
          43,
          (unsigned int)WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
          v5,
          v5 + 80,
          (*(_BYTE *)(v5 + 737) >> 2) & 3);
      }
      v39 = 0x65C000020CLL;
      SmbCeDisconnectServerConnections(v5, 0, 0, 0, 0x65C000020CLL, 5);
    }
    goto LABEL_54;
  }
  if ( *(_BYTE *)(a1 + 1083) )
    goto LABEL_32;
  *(_BYTE *)(v2 + 467) = *(_BYTE *)(a1 + 1084);
  v13 = *(_DWORD *)(v2 + 4);
  if ( (v13 & 1) != 0 )
    *(_BYTE *)(v2 + 464) = 0;
  if ( (v13 & 2) == 0 )
    goto LABEL_32;
  v14 = *(_QWORD *)(v2 + 128);
  v42 = 0;
  if ( v14 )
  {
    v7 = *(PDEVICE_OBJECT *)(v14 + 16);
    if ( v7 )
      v42 = *(_OWORD *)&v7->Type;
  }
  if ( (*(_BYTE *)(v11 + 1314) & 8) != 0 )
    goto LABEL_22;
  if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(v7) + 228) )
  {
    if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(v15) + 229)
      || *(_BYTE *)(MRxSmbGetInstanceConfigurationBlock(v41) + 56) != 1 )
    {
LABEL_22:
      *(_BYTE *)(v2 + 464) = 0;
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000000) != 0 )
        McTemplateK0hzr0hzr2_EtwWriteTransfer(
          *(_WORD *)(*(_QWORD *)(v2 + 384) + 80LL) >> 1,
          (unsigned int)AllowedInsecureGuestAuth,
          a1 + 312,
          (unsigned __int16)v42 >> 1,
          *((__int64 *)&v42 + 1),
          *(_WORD *)(*(_QWORD *)(v2 + 384) + 80LL) >> 1,
          *(_QWORD *)(*(_QWORD *)(v2 + 384) + 88LL));
      goto LABEL_32;
    }
    v9 = -1067646970;
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(v16, (unsigned int)SessionSetupError, a1 + 312, -1067646970, 90, 14);
  }
  else
  {
    v9 = -1067646974;
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x40000000) != 0 )
      McTemplateK0hzr0hzr2_EtwWriteTransfer(
        *(_WORD *)(*(_QWORD *)(v2 + 384) + 80LL) >> 1,
        (unsigned int)RejectedInsecureGuestAuth,
        a1 + 312,
        (unsigned __int16)v42 >> 1,
        *((__int64 *)&v42 + 1),
        *(_WORD *)(*(_QWORD *)(v2 + 384) + 80LL) >> 1,
        *(_QWORD *)(*(_QWORD *)(v2 + 384) + 88LL));
  }
LABEL_54:
  *(_DWORD *)(v4 + 12) = HIDWORD(v39);
  *(_DWORD *)(v4 + 8) = v9;
  if ( *(_BYTE *)(a1 + 1083) )
    *(_QWORD *)(v4 + 40) = *(unsigned int *)(a1 + 108);
  else
    *(_QWORD *)(v4 + 32) = v3;
  (*(void (__fastcall **)(__int64))v4)(v4);
  if ( v3 )
  {
    SmbCeDereferenceBindingObject(v3);
    *(_QWORD *)(a1 + 1024) = 0;
  }
  if ( *(_BYTE *)(a1 + 1082) )
  {
    ExFreePoolWithTag(*(PVOID *)(a1 + 1056), 0x6D53674Eu);
    *(_QWORD *)(a1 + 1056) = 0;
  }
  if ( *(_QWORD *)(a1 + 1032) )
  {
    SmbCryptoHashDestroy();
    *(_QWORD *)(a1 + 1032) = 0;
  }
  v22 = *(void **)(a1 + 1040);
  if ( v22 )
  {
    ExFreePoolWithTag(v22, 0x6D536850u);
    *(_QWORD *)(a1 + 1040) = 0;
    *(_DWORD *)(a1 + 1048) = 0;
  }
  v23 = *(void **)(a1 + 1096);
  if ( v23 )
  {
    ExFreePoolWithTag(v23, 0);
    *(_QWORD *)(a1 + 1096) = 0;
  }
  v24 = a1 + 160;
  v25 = *(_QWORD *)(a1 + 160);
  v19 = v25 == a1 + 160;
  v26 = (_QWORD *)(v25 - 8);
  if ( v19 )
    v26 = 0;
  while ( v26 )
  {
    v27 = v26[1];
    v28 = v26;
    v26 = 0;
    if ( v27 != v24 )
      v26 = (_QWORD *)(v27 - 8);
    v29 = SmbCseFinalizeBufferContext(v28);
    v30 = (void *)v28[11];
    v9 = v29;
    if ( v30 )
    {
      ExFreePoolWithTag(v30, 0x6D537353u);
      v28[11] = 0;
    }
    v31 = (void *)v28[89];
    if ( v31 )
    {
      ExFreePoolWithTag(v31, 0x6D537353u);
      v28[89] = 0;
    }
    ExFreePoolWithTag(v28, 0x6D537353u);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140053130  push    rbp
0x140053132  push    rbx
0x140053133  push    rsi
0x140053134  push    rdi
0x140053135  push    r12
0x140053137  push    r13
0x140053139  push    r14
0x14005313b  push    r15
0x14005313d  lea     rbp, [rsp-58h]
0x140053142  sub     rsp, 158h
0x140053149  mov     rax, cs:__security_cookie
0x140053150  xor     rax, rsp
0x140053153  mov     [rbp+90h+var_50], rax
0x140053157  mov     rax, [rcx+10h]
0x14005315b  mov     rbx, rcx
0x14005315e  mov     rdi, [rcx+50h]
0x140053162  mov     r13, [rcx+400h]
0x140053169  mov     r12, [rcx+430h]
0x140053170  mov     [rsp+190h+var_148], rax
0x140053175  mov     r14, [rdi+180h]
0x14005317c  call    SmbCeGetLastBufferContext
0x140053181  cmp     dword ptr [rcx+10h], 0
0x140053185  mov     r15, rax
0x140053188  jl      short loc_140053198
0x14005318a  test    rax, rax
0x14005318d  jz      short loc_140053198
0x14005318f  mov     rcx, [rax+30h]
0x140053193  mov     [rsp+190h+var_148], rcx
0x140053198  mov     esi, dword ptr [rsp+190h+var_148]
0x14005319c  lea     r8, WPP_GLOBAL_Control
0x1400531a3  test    esi, esi
0x1400531a5  js      loc_1400535FE
0x1400531ab  mov     r9, [rbx+410h]
0x1400531b2  mov     rdx, [r14+18h]
0x1400531b6  mov     [rsp+190h+var_138], rdx
0x1400531bb  test    r9, r9
0x1400531be  jz      short loc_1400531FD
0x1400531c0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400531c7  cmp     rcx, r8
0x1400531ca  jz      short loc_1400531FD
0x1400531cc  test    dword ptr [rcx+2Ch], 400h
0x1400531d3  jz      short loc_1400531FD
0x1400531d5  cmp     byte ptr [rcx+29h], 2
0x1400531d9  jb      short loc_1400531FD
0x1400531db  mov     rax, [r13+188h]
0x1400531e2  mov     r9d, [r9]
0x1400531e5  mov     rcx, [rcx+18h]
0x1400531e9  mov     [rsp+190h+var_168], rax
0x1400531ee  mov     [rsp+190h+var_170], rdi
0x1400531f3  call    WPP_SF_Dqq
0x1400531f8  mov     rdx, [rsp+190h+var_138]
0x1400531fd  test    byte ptr [rdx+522h], 8
0x140053204  jz      short loc_14005320D
0x140053206  mov     eax, [rdi+4]
0x140053209  test    al, 2
0x14005320b  jnz     short loc_140053227
0x14005320d  mov     r8, rbx
0x140053210  mov     rdx, r13
0x140053213  mov     rcx, rdi; Parameter
0x140053216  call    ValidateSessionSetupSecurityBlob
0x14005321b  mov     rdx, [rsp+190h+var_138]
0x140053220  mov     esi, eax
0x140053222  mov     [rsp+190h+var_148], rax
0x140053227  test    esi, esi
0x140053229  jnz     loc_1400533CC
0x14005322f  cmp     [rbx+43Bh], sil
0x140053236  jnz     loc_1400533D2
0x14005323c  mov     al, [rbx+43Ch]
0x140053242  mov     [rdi+1D3h], al
0x140053248  mov     eax, [rdi+4]
0x14005324b  test    al, 1
0x14005324d  jz      short loc_140053256
0x14005324f  mov     [rdi+1D0h], sil
0x140053256  test    al, 2
0x140053258  jz      loc_1400533D2
0x14005325e  mov     rax, [rdi+80h]
0x140053265  xorps   xmm0, xmm0
0x140053268  movups  [rsp+190h+var_130], xmm0
0x14005326d  test    rax, rax
0x140053270  jz      short loc_140053284
0x140053272  mov     rcx, [rax+10h]
0x140053276  test    rcx, rcx
0x140053279  jz      short loc_140053284
0x14005327b  movups  xmm0, xmmword ptr [rcx]
0x14005327e  movdqu  [rsp+190h+var_130], xmm0
0x140053284  test    byte ptr [rdx+522h], 8
0x14005328b  jz      short loc_1400532E9
0x14005328d  mov     byte ptr [rdi+1D0h], 0
0x140053294  cmp     byte ptr cs:WPP_MAIN_CB.Queue+13h, 0
0x14005329b  jge     loc_1400533D2
0x1400532a1  mov     rax, [rdi+180h]
0x1400532a8  lea     r8, [rbx+138h]
0x1400532af  movzx   r9d, word ptr [rsp+190h+var_130]
0x1400532b5  lea     rdx, AllowedInsecureGuestAuth
0x1400532bc  shr     r9w, 1
0x1400532c0  movzx   ecx, word ptr [rax+50h]
0x1400532c4  mov     rax, [rax+58h]
0x1400532c8  mov     [rsp+190h+var_160], rax
0x1400532cd  mov     rax, qword ptr [rsp+190h+var_130+8]
0x1400532d2  shr     cx, 1
0x1400532d5  mov     word ptr [rsp+190h+var_168], cx
0x1400532da  mov     [rsp+190h+var_170], rax
0x1400532df  call    McTemplateK0hzr0hzr2_EtwWriteTransfer
0x1400532e4  jmp     loc_1400533D2
0x1400532e9  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400532f0  nop     dword ptr [rax+rax+00h]
0x1400532f5  cmp     byte ptr [rax+0E4h], 0
0x1400532fc  jnz     short loc_140053358
0x1400532fe  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 40h
0x140053305  mov     esi, 0C05D0002h
0x14005330a  jz      loc_1400536D4
0x140053310  mov     rax, [rdi+180h]
0x140053317  lea     r8, [rbx+138h]
0x14005331e  movzx   r9d, word ptr [rsp+190h+var_130]
0x140053324  lea     rdx, RejectedInsecureGuestAuth
0x14005332b  shr     r9w, 1
0x14005332f  movzx   ecx, word ptr [rax+50h]
0x140053333  mov     rax, [rax+58h]
0x140053337  mov     [rsp+190h+var_160], rax
0x14005333c  mov     rax, qword ptr [rsp+190h+var_130+8]
0x140053341  shr     cx, 1
0x140053344  mov     word ptr [rsp+190h+var_168], cx
0x140053349  mov     [rsp+190h+var_170], rax
0x14005334e  call    McTemplateK0hzr0hzr2_EtwWriteTransfer
0x140053353  jmp     loc_1400536D4
0x140053358  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14005335f  nop     dword ptr [rax+rax+00h]
0x140053364  cmp     byte ptr [rax+0E5h], 0
0x14005336b  jnz     loc_14005328D
0x140053371  mov     rcx, [rsp+190h+var_138]
0x140053376  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14005337d  nop     dword ptr [rax+rax+00h]
0x140053382  cmp     byte ptr [rax+38h], 1
0x140053386  jnz     loc_14005328D
0x14005338c  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 1
0x140053393  mov     esi, 0C05D0006h
0x140053398  jz      loc_1400536D4
0x14005339e  lea     r8, [rbx+138h]
0x1400533a5  mov     dword ptr [rsp+190h+var_168], 0Eh
0x1400533ad  mov     r9d, 0C05D0006h
0x1400533b3  mov     dword ptr [rsp+190h+var_170], 20100A5Ah
0x1400533bb  lea     rdx, SessionSetupError
0x1400533c2  call    McTemplateK0qqq_EtwWriteTransfer
0x1400533c7  jmp     loc_1400536D4
0x1400533cc  js      loc_1400535F7
0x1400533d2  cmp     byte ptr [rdi+1D0h], 0
0x1400533d9  jnz     loc_140053583
0x1400533df  cmp     byte ptr [rbx+43Bh], 0
0x1400533e6  jnz     loc_140053583
0x1400533ec  mov     edx, 3
0x1400533f1  mov     rcx, r14
0x1400533f4  lea     r9d, [rdx-2]
0x1400533f8  mov     r8d, r9d
0x1400533fb  call    cs:__imp_SmbCeCheckServerEntryDialect
0x140053402  nop     dword ptr [rax+rax+00h]
0x140053407  xor     r8d, r8d
0x14005340a  test    al, al
0x14005340c  jz      short loc_14005341D
0x14005340e  mov     eax, [rdi+4]
0x140053411  test    al, 1
0x140053413  jnz     short loc_14005341D
0x140053415  test    al, 2
0x140053417  jz      loc_140053583
0x14005341d  test    esi, esi
0x14005341f  js      loc_1400535F7
0x140053425  mov     rax, [rdi+1B8h]
0x14005342c  mov     [rdi+258h], rax
0x140053433  mov     [r14+2F4h], r8d
0x14005343a  mov     eax, cs:dword_140046050
0x140053440  cmp     eax, 5
0x140053443  jbe     loc_1400536D4
0x140053449  mov     rdx, 400000000000h
0x140053453  lea     rcx, dword_140046050
0x14005345a  call    _tlgKeywordOn
0x14005345f  test    al, al
0x140053461  jz      loc_1400536D4
0x140053467  cmp     [rbx+43Bh], r8b
0x14005346e  lea     rax, [rsp+190h+var_130]
0x140053473  mov     [rbp+90h+var_F0], rax
0x140053477  lea     rdx, unk_140040258; int
0x14005347e  mov     eax, [rdi+4]
0x140053481  mov     ecx, 1; int
0x140053486  mov     [rsp+190h+var_120], eax
0x14005348a  setz    [rsp+190h+var_14C]
0x14005348f  lea     rax, [rsp+190h+var_120]
0x140053494  mov     qword ptr [rsp+190h+var_130], rcx
0x140053499  mov     [rbp+90h+var_E0], rax
0x14005349d  mov     al, [rdi+1D0h]
0x1400534a3  lea     r9d, [rcx+0Bh]; int
0x1400534a7  mov     [rsp+190h+var_150], al
0x1400534ab  lea     rax, [rsp+190h+var_150]
0x1400534b0  mov     [rbp+90h+var_D0], rax
0x1400534b4  mov     al, [rdi+1D2h]
0x1400534ba  mov     [rsp+190h+var_14F], al
0x1400534be  lea     rax, [rsp+190h+var_14F]
0x1400534c3  mov     [rbp+90h+var_C0], rax
0x1400534c7  mov     al, [rdi+1D1h]
0x1400534cd  mov     [rsp+190h+var_14E], al
0x1400534d1  lea     rax, [rsp+190h+var_14E]
0x1400534d6  mov     [rbp+90h+var_B0], rax
0x1400534da  mov     al, [rdi+1D3h]
0x1400534e0  mov     [rsp+190h+var_14D], al
0x1400534e4  lea     rax, [rsp+190h+var_14D]
0x1400534e9  mov     [rbp+90h+var_A0], rax
0x1400534ed  lea     rax, [rsp+190h+var_14C]
0x1400534f2  mov     [rbp+90h+var_90], rax
0x1400534f6  movzx   eax, word ptr [rdi+23Ch]
0x1400534fd  mov     [rsp+190h+var_11C], eax
0x140053501  lea     rax, [rsp+190h+var_11C]
0x140053506  mov     [rbp+90h+var_80], rax
0x14005350a  movzx   eax, word ptr [r14+2A2h]
0x140053512  mov     [rsp+190h+var_140], ax
0x140053517  lea     rax, [rsp+190h+var_140]
0x14005351c  mov     [rbp+90h+var_70], rax
0x140053520  mov     rax, [rsp+190h+var_138]
0x140053525  mov     [rbp+90h+var_E8], 8
0x14005352d  mov     [rbp+90h+var_D8], 4
0x140053535  mov     [rbp+90h+var_C8], rcx
0x140053539  mov     al, [rax+520h]
0x14005353f  mov     [rsp+190h+var_14B], al
0x140053543  lea     rax, [rsp+190h+var_14B]
0x140053548  mov     [rbp+90h+var_60], rax
0x14005354c  lea     rax, [rbp+90h+var_110]
0x140053550  mov     [rsp+190h+var_170], rax; PEVENT_DATA_DESCRIPTOR
0x140053555  mov     [rbp+90h+var_B8], rcx
0x140053559  mov     [rbp+90h+var_A8], rcx
0x14005355d  mov     [rbp+90h+var_98], rcx
0x140053561  mov     [rbp+90h+var_88], rcx
0x140053565  mov     [rbp+90h+var_78], 4
0x14005356d  mov     [rbp+90h+var_68], 2
0x140053575  mov     [rbp+90h+var_58], rcx
0x140053579  call    _tlgWriteAgg
0x14005357e  jmp     loc_1400536D4
0x140053583  mov     r9d, [r15+2ECh]
0x14005358a  mov     rdx, r13
0x14005358d  mov     r8, [r15+2C8h]
0x140053594  mov     rcx, r15
0x140053597  call    Smb2ComputeIncomingSignatureInitial
0x14005359c  mov     esi, eax
0x14005359e  test    eax, eax
0x1400535a0  js      short loc_1400535F7
0x1400535a2  mov     r9, [r15+2C8h]
0x1400535a9  mov     rdx, r13
0x1400535ac  mov     r8d, [r15+2ECh]
0x1400535b3  mov     rcx, r15
0x1400535b6  call    Smb2ValidateIncomingSignature
0x1400535bb  xor     r8d, r8d
0x1400535be  mov     esi, eax
0x1400535c0  test    eax, eax
0x1400535c2  jns     loc_140053425
0x1400535c8  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 1
0x1400535cf  jz      short loc_1400535F7
0x1400535d1  lea     r8, [rbx+138h]
0x1400535d8  mov     dword ptr [rsp+190h+var_168], 0Eh
0x1400535e0  mov     r9d, eax
0x1400535e3  mov     dword ptr [rsp+190h+var_170], 20100AA2h
0x1400535eb  lea     rdx, SessionSetupError
0x1400535f2  call    McTemplateK0qqq_EtwWriteTransfer
0x1400535f7  lea     r8, WPP_GLOBAL_Control
0x1400535fe  cmp     esi, 80090322h
0x140053604  jz      short loc_140053612
0x140053606  cmp     esi, 0C00002EFh
0x14005360c  jnz     loc_1400536D4
0x140053612  mov     eax, [r14+188h]
0x140053619  cmp     [rbx+68h], eax
0x14005361c  jnz     loc_1400536D4
0x140053622  mov     eax, 1
0x140053627  lock xadd [r14+2F4h], eax
0x140053630  inc     eax
0x140053632  cmp     eax, 2
0x140053635  jl      loc_1400536D4
0x14005363b  movzx   edx, byte ptr [r14+2E1h]
0x140053643  mov     al, dl
0x140053645  and     al, 0Ch
0x140053647  sub     al, 4
0x140053649  test    al, 0F7h
0x14005364b  jnz     loc_1400536D4
0x140053651  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053658  cmp     rcx, r8
0x14005365b  jz      short loc_14005369B
0x14005365d  mov     eax, [rcx+2Ch]
0x140053660  test    al, 1
0x140053662  jz      short loc_14005369B
0x140053664  cmp     byte ptr [rcx+29h], 1
0x140053668  jb      short loc_14005369B
0x14005366a  mov     rcx, [rcx+18h]
0x14005366e  lea     rax, [r14+50h]
0x140053672  mov     r8d, edx
0x140053675  mov     r9, r14
0x140053678  shr     r8d, 2
0x14005367c  mov     edx, 2Bh ; '+'
0x140053681  and     r8d, 3
0x140053685  mov     dword ptr [rsp+190h+var_168], r8d
0x14005368a  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
0x140053691  mov     [rsp+190h+var_170], rax
0x140053696  call    WPP_SF_qZd
0x14005369b  mov     dword ptr [rsp+190h+var_148], 0C000020Ch
0x1400536a3  xor     r9d, r9d
0x1400536a6  mov     dword ptr [rsp+190h+var_148+4], 65h ; 'e'
0x1400536ae  xor     r8d, r8d
  ... truncated ...
```
