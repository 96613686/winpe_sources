# Smb2CompleteSrvOpenReconnectionCallback

- ea: `0x1400087c0`
- end: `0x140008ead`
- name: `Smb2CompleteSrvOpenReconnectionCallback`
- size: `1773`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140008480`
- `0x1400108f0`
- `0x140010950`

## callees

- `0x1400087c0`
- `0x14000bd50`
- `0x140017be0`
- `0x140034058`
- `0x1400341a0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140008e31`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140008e31`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140008daa`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140008daa`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140008db9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140008db9`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140008e7e`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140008e7e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008d8f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008d8f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008835`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008835`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140008e94`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140008e94`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140008acd`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140008acd`
- `mrxsmb!SmbCeResumeSuspendedExchangesLite` at `0x140008e11`
- `mrxsmb!SmbCeResumeSuspendedExchangesLite` at `0x140008e11`

## pseudocode

```c
void __fastcall Smb2CompleteSrvOpenReconnectionCallback(PRX_CONTEXT RxContext, __int64 a2, __int64 a3)
{
  PRX_CONTEXT v5; // r13
  char v6; // bp
  __int64 v7; // rsi
  int v8; // edi
  __int64 v9; // rdx
  __int128 *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r9
  int v14; // ebp
  _DWORD *v15; // r14
  int v16; // eax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  bool v19; // zf
  __int64 v20; // r13
  __int64 v21; // rcx
  __int64 v22; // r12
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // rsi
  KIRQL v29; // bl
  unsigned int CurrentThreadId; // eax
  __int64 v31; // r9
  struct _ECP_LIST *v32; // rcx
  unsigned int v33; // [rsp+90h] [rbp-68h]
  __int64 v34; // [rsp+98h] [rbp-60h]
  __int128 v35; // [rsp+A0h] [rbp-58h] BYREF
  unsigned int v37; // [rsp+108h] [rbp+10h]
  char v38; // [rsp+114h] [rbp+1Ch]
  int v39; // [rsp+118h] [rbp+20h]

  v38 = BYTE4(a3);
  v5 = RxContext;
  v35 = 0;
  if ( !a2 )
    goto LABEL_72;
  v6 = 0;
  v7 = *(_QWORD *)(a2 + 48);
  v8 = a3;
  v37 = a3;
  v34 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 40) + 40LL) + 24LL);
  ExAcquirePushLockExclusiveEx(v7 + 16, 0);
  v9 = v7 + 56;
  if ( *(_QWORD *)v9 == v9 )
  {
    *((_QWORD *)&v35 + 1) = &v35;
    v10 = &v35;
    *(_QWORD *)&v35 = &v35;
  }
  else
  {
    *(_QWORD *)&v35 = *(_QWORD *)v9;
    *((_QWORD *)&v35 + 1) = *(_QWORD *)(v7 + 64);
    *(_QWORD *)(v35 + 8) = &v35;
    **((_QWORD **)&v35 + 1) = &v35;
    *(_QWORD *)(v7 + 64) = v7 + 56;
    *(_QWORD *)v9 = v9;
    v10 = (__int128 *)v35;
  }
  v11 = *(unsigned int *)(v7 + 4);
  v33 = *(_DWORD *)(v7 + 44);
  v39 = v11;
  if ( v10 != &v35 )
  {
    while ( 1 )
    {
      v12 = *((_QWORD *)v10 - 10);
      if ( v12 )
      {
        if ( *(_BYTE *)(v12 + 32) == 2 )
          break;
      }
      v10 = *(__int128 **)v10;
      if ( v10 == &v35 )
        goto LABEL_11;
    }
    v6 = 1;
  }
LABEL_11:
  v13 = 9;
  if ( v8 >= 0 )
  {
    *(_DWORD *)(a2 + 72) &= ~0x100000u;
    v14 = v6 != 0 ? 6 : 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqdLdLZ(
        WPP_GLOBAL_Control->AttachedDevice,
        *(_DWORD *)(v7 + 4),
        v11,
        a2,
        v7,
        *(_DWORD *)(v7 + 4),
        *(_DWORD *)(v7 + 4),
        v14,
        v14,
        *(_QWORD *)(a2 + 80));
      v11 = (unsigned int)v39;
    }
    v15 = (_DWORD *)(v7 + 8);
    goto LABEL_43;
  }
  v16 = *(_DWORD *)(v7 + 8);
  v15 = (_DWORD *)(v7 + 8);
  if ( (v16 & 4) == 0 && (v16 & 8) == 0 )
  {
LABEL_34:
    *(_DWORD *)(a2 + 72) &= ~0x100000u;
    v14 = 9;
    v37 = -1073741300;
    goto LABEL_43;
  }
  v17 = (unsigned int)(v8 + 1073741667);
  if ( (unsigned int)v17 > 0x2F || (v9 = 0x900281000001LL, !_bittest64(&v9, v17)) )
  {
    v18 = (unsigned int)(v8 + 1073741309);
    if ( (unsigned int)v18 > 0x3E || (v9 = 0x4208040000000601LL, !_bittest64(&v9, v18)) )
    {
      if ( v8 != -1073740964
        && v8 != -1073741507
        && (unsigned int)(v8 + 1073740698) > 1
        && v8 != -1073740672
        && v8 != -2146893022
        && v8 != -1073741073
        && v8 != -2147483631
        && v8 != -1073741810
        && v8 != -1073741202
        && v8 != -1069481983 )
      {
        if ( v8 != -1073741536 )
          goto LABEL_34;
        v37 = -1073741643;
      }
    }
  }
  if ( (*v15 & 0x40) == 0
    || (*v15 & 0x100) != 0
    || MEMORY[0xFFFFF78000000008] <= *(_QWORD *)(v7 + 248) + *(_QWORD *)(v7 + 256) )
  {
    if ( (_DWORD)v11 == 8 || (v19 = v6 == 0, v14 = 1, !v19) )
      v14 = 7;
  }
  else
  {
    v14 = 9;
  }
LABEL_43:
  if ( (_DWORD)v11 == 4 && !v14 )
  {
    v20 = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 40LL);
    v21 = *(_QWORD *)(v20 + 416);
    v22 = *(_QWORD *)(v21 + 384);
    Smb2IncrementActiveHandleCount(v21, v9, v11, v13);
    if ( (*v15 & 0x40) != 0 )
    {
      v23 = *(_DWORD *)(v22 + 772);
      v24 = 10;
      if ( v23 )
        v24 = v23;
      SmbCeSetConnectionKeepalive(*(_QWORD *)(v20 + 416), v24, 2);
    }
    v5 = RxContext;
  }
  if ( v8 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qqLLdLdLZ(
      WPP_GLOBAL_Control->AttachedDevice,
      *(_DWORD *)(v7 + 4),
      v11,
      a2,
      v7,
      v8,
      v37,
      *(_DWORD *)(v7 + 4),
      *(_DWORD *)(v7 + 4),
      v14,
      v14,
      *(_QWORD *)(a2 + 80));
  }
  if ( v39 >= 6 || v14 != 9 )
    goto LABEL_69;
  if ( (*v15 & 0x20) != 0 )
  {
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
    {
      v25 = *(_QWORD *)(a2 + 80);
      McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
        *(_WORD *)v25 >> 1,
        (unsigned int)PersistentHandleFailure,
        v25,
        v7,
        *(_QWORD *)(v7 + 28),
        *(_QWORD *)(v7 + 36),
        v7 + 264,
        *(_WORD *)(v7 + 4),
        9,
        v8,
        v38,
        **(_WORD **)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 120LL) + 88LL) >> 1,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 120LL) + 88LL) + 8LL),
        *(_WORD *)v25 >> 1,
        *(_QWORD *)(v25 + 8),
        *(_DWORD *)(v7 + 312),
        *(_DWORD *)(v7 + 316));
    }
    if ( !dbgBreakOnPersistentHandleFailure )
      goto LABEL_67;
  }
  else
  {
    if ( (*v15 & 0x40) == 0 )
      goto LABEL_67;
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
    {
      v26 = *(_QWORD *)(a2 + 80);
      McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
        *(_WORD *)v26 >> 1,
        (unsigned int)ResilientHandleFailure,
        v26,
        v7,
        *(_QWORD *)(v7 + 28),
        *(_QWORD *)(v7 + 36),
        v7 + 264,
        *(_WORD *)(v7 + 4),
        9,
        v8,
        v38,
        **(_WORD **)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 120LL) + 88LL) >> 1,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 120LL) + 88LL) + 8LL),
        *(_WORD *)v26 >> 1,
        *(_QWORD *)(v26 + 8),
        *(_DWORD *)(v7 + 312),
        *(_DWORD *)(v7 + 316));
    }
    if ( !dbgBreakOnResilientHandleFailure )
      goto LABEL_67;
  }
  __debugbreak();
LABEL_67:
  if ( dbgBreakOnSrvOpenInvalidation )
    __debugbreak();
LABEL_69:
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400) != 0 )
  {
    v27 = *(_QWORD *)(a2 + 80);
    McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
      *(_WORD *)v27 >> 1,
      (unsigned int)OpenHandleStateTransition,
      v27,
      v7,
      0,
      0,
      v7 + 264,
      *(_WORD *)(v7 + 4),
      v14,
      v8,
      v38,
      **(_WORD **)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 120LL) + 88LL) >> 1,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 120LL) + 88LL) + 8LL),
      *(_WORD *)v27 >> 1,
      *(_QWORD *)(v27 + 8),
      0,
      0);
  }
  *(_DWORD *)(v7 + 4) = v14;
  *(_QWORD *)(v7 + 304) = 0;
  *(_QWORD *)(v7 + 312) = a3;
  ExReleasePushLockExclusiveEx(v7 + 16, 0);
  v28 = v34;
  v29 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v34 + 1920));
  CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
  v31 = v33;
  *(_DWORD *)(v28 + 2352) = CurrentThreadId;
  SmbCeResumeSuspendedExchangesLite(&v35, 1, 3, v31, v37 | 0xE00000000LL, 0);
  *(_DWORD *)(v28 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v28 + 1920), v29);
LABEL_72:
  if ( v5 )
  {
    v32 = *(struct _ECP_LIST **)&v5->TrackerHistory[2].AcquireRelease;
    if ( v32 )
    {
      FsRtlFreeExtraCreateParameterList(v32);
      *(_QWORD *)&v5->TrackerHistory[2].AcquireRelease = 0;
    }
    RxDereferenceAndDeleteRxContext_Real(v5);
  }
}

```

## disassembly

```asm
0x1400087c0  mov     rax, rsp
0x1400087c3  mov     [rax+18h], r8
0x1400087c7  mov     [rax+8], rcx
0x1400087cb  push    r13
0x1400087cd  push    r14
0x1400087cf  sub     rsp, 0E8h
0x1400087d6  mov     [rax-18h], rbx
0x1400087da  xor     r14d, r14d
0x1400087dd  mov     [rax-40h], r15
0x1400087e1  xorps   xmm0, xmm0
0x1400087e4  mov     rbx, r8
0x1400087e7  mov     r15, rdx
0x1400087ea  mov     r13, rcx
0x1400087ed  movups  xmmword ptr [rax-58h], xmm0
0x1400087f1  test    rdx, rdx
0x1400087f4  jz      loc_140008E5D
0x1400087fa  mov     [rax-20h], rbp
0x1400087fe  xor     bpl, bpl
0x140008801  mov     [rax-28h], rsi
0x140008805  mov     rsi, [rdx+30h]
0x140008809  mov     [rax-30h], rdi
0x14000880d  mov     edi, [rax+18h]
0x140008810  mov     [rax-38h], r12
0x140008814  mov     rax, [rdx+28h]
0x140008818  lea     rcx, [rsi+10h]
0x14000881c  xor     edx, edx
0x14000881e  mov     [rsp+0F8h+arg_8], edi
0x140008825  mov     r8, [rax+28h]
0x140008829  mov     rax, [r8+18h]
0x14000882d  mov     [rsp+0F8h+var_60], rax
0x140008835  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000883c  nop     dword ptr [rax+rax+00h]
0x140008841  lea     rdx, [rsi+38h]
0x140008845  cmp     [rdx], rdx
0x140008848  jnz     short loc_14000886C
0x14000884a  lea     rax, [rsp+0F8h+var_58]
0x140008852  mov     [rsp+0F8h+var_50], rax
0x14000885a  lea     rax, [rsp+0F8h+var_58]
0x140008862  mov     [rsp+0F8h+var_58], rax
0x14000886a  jmp     short loc_1400088B1
0x14000886c  mov     rcx, [rdx]
0x14000886f  mov     [rsp+0F8h+var_58], rcx
0x140008877  mov     rax, [rdx+8]
0x14000887b  mov     [rsp+0F8h+var_50], rax
0x140008883  lea     rax, [rsp+0F8h+var_58]
0x14000888b  mov     [rcx+8], rax
0x14000888f  lea     rcx, [rsp+0F8h+var_58]
0x140008897  mov     rax, [rsp+0F8h+var_50]
0x14000889f  mov     [rax], rcx
0x1400088a2  mov     [rdx+8], rdx
0x1400088a6  mov     [rdx], rdx
0x1400088a9  mov     rax, [rsp+0F8h+var_58]
0x1400088b1  mov     ecx, [rsi+2Ch]
0x1400088b4  mov     r8d, [rsi+4]
0x1400088b8  mov     [rsp+0F8h+var_68], ecx
0x1400088bf  lea     rcx, [rsp+0F8h+var_58]
0x1400088c7  mov     [rsp+0F8h+arg_18], r8d
0x1400088cf  cmp     rax, rcx
0x1400088d2  jz      short loc_1400088F8
0x1400088d4  mov     rcx, [rax-50h]
0x1400088d8  test    rcx, rcx
0x1400088db  jz      short loc_1400088E3
0x1400088dd  cmp     byte ptr [rcx+20h], 2
0x1400088e1  jz      short loc_1400088F5
0x1400088e3  mov     rax, [rax]
0x1400088e6  lea     rcx, [rsp+0F8h+var_58]
0x1400088ee  cmp     rax, rcx
0x1400088f1  jnz     short loc_1400088D4
0x1400088f3  jmp     short loc_1400088F8
0x1400088f5  mov     bpl, 1
0x1400088f8  lea     r12, WPP_GLOBAL_Control
0x1400088ff  mov     r9d, 9
0x140008905  test    edi, edi
0x140008907  js      short loc_140008970
0x140008909  and     dword ptr [r15+48h], 0FFEFFFFFh
0x140008911  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008918  neg     bpl
0x14000891b  sbb     ebp, ebp
0x14000891d  and     ebp, 6
0x140008920  cmp     rcx, r12
0x140008923  jz      short loc_140008967
0x140008925  mov     eax, [rcx+2Ch]
0x140008928  test    al, 40h
0x14000892a  jz      short loc_140008967
0x14000892c  cmp     byte ptr [rcx+29h], 2
0x140008930  jb      short loc_140008967
0x140008932  mov     edx, [rsi+4]
0x140008935  mov     r9, r15
0x140008938  mov     rax, [r15+50h]
0x14000893c  mov     rcx, [rcx+18h]
0x140008940  mov     [rsp+0F8h+var_B0], rax
0x140008945  mov     [rsp+0F8h+var_B8], ebp
0x140008949  mov     [rsp+0F8h+var_C0], ebp
0x14000894d  mov     dword ptr [rsp+0F8h+var_C8], edx
0x140008951  mov     dword ptr [rsp+0F8h+var_D0], edx
0x140008955  mov     [rsp+0F8h+var_D8], rsi
0x14000895a  call    WPP_SF_qqdLdLZ
0x14000895f  mov     r8d, [rsp+0F8h+arg_18]
0x140008967  lea     r14, [rsi+8]
0x14000896b  jmp     loc_140008A82
0x140008970  mov     eax, [rsi+8]
0x140008973  lea     r14, [rsi+8]
0x140008977  test    al, 4
0x140008979  jnz     short loc_140008983
0x14000897b  test    al, 8
0x14000897d  jz      loc_140008A25
0x140008983  mov     rcx, 0FFFFF78000000008h
0x14000898d  lea     eax, [rdi+3FFFFF63h]
0x140008993  mov     rcx, [rcx]
0x140008996  cmp     eax, 2Fh ; '/'
0x140008999  ja      short loc_1400089AF
0x14000899b  mov     rdx, 900281000001h
0x1400089a5  bt      rdx, rax
0x1400089a9  jb      loc_140008A48
0x1400089af  lea     eax, [rdi+3FFFFDFDh]
0x1400089b5  cmp     eax, 3Eh ; '>'
0x1400089b8  ja      short loc_1400089CA
0x1400089ba  mov     rdx, 4208040000000601h
0x1400089c4  bt      rdx, rax
0x1400089c8  jb      short loc_140008A48
0x1400089ca  cmp     edi, 0C000035Ch
0x1400089d0  jz      short loc_140008A48
0x1400089d2  cmp     edi, 0C000013Dh
0x1400089d8  jz      short loc_140008A48
0x1400089da  lea     eax, [rdi+3FFFFB9Ah]
0x1400089e0  cmp     eax, 1
0x1400089e3  jbe     short loc_140008A48
0x1400089e5  cmp     edi, 0C0000480h
0x1400089eb  jz      short loc_140008A48
0x1400089ed  cmp     edi, 80090322h
0x1400089f3  jz      short loc_140008A48
0x1400089f5  cmp     edi, 0C00002EFh
0x1400089fb  jz      short loc_140008A48
0x1400089fd  cmp     edi, 80000011h
0x140008a03  jz      short loc_140008A48
0x140008a05  cmp     edi, 0C000000Eh
0x140008a0b  jz      short loc_140008A48
0x140008a0d  cmp     edi, 0C000026Eh
0x140008a13  jz      short loc_140008A48
0x140008a15  cmp     edi, 0C0410001h
0x140008a1b  jz      short loc_140008A48
0x140008a1d  cmp     edi, 0C0000120h
0x140008a23  jz      short loc_140008A3D
0x140008a25  and     dword ptr [r15+48h], 0FFEFFFFFh
0x140008a2d  mov     ebp, r9d
0x140008a30  mov     [rsp+0F8h+arg_8], 0C000020Ch
0x140008a3b  jmp     short loc_140008A82
0x140008a3d  mov     [rsp+0F8h+arg_8], 0C00000B5h
0x140008a48  mov     eax, [r14]
0x140008a4b  test    al, 40h
0x140008a4d  jz      short loc_140008A6D
0x140008a4f  bt      eax, 8
0x140008a53  jb      short loc_140008A6D
0x140008a55  mov     rax, [rsi+100h]
0x140008a5c  add     rax, [rsi+0F8h]
0x140008a63  cmp     rcx, rax
0x140008a66  jbe     short loc_140008A6D
0x140008a68  mov     ebp, r9d
0x140008a6b  jmp     short loc_140008A82
0x140008a6d  cmp     r8d, 8
0x140008a71  jz      short loc_140008A7D
0x140008a73  test    bpl, bpl
0x140008a76  mov     ebp, 1
0x140008a7b  jz      short loc_140008A82
0x140008a7d  mov     ebp, 7
0x140008a82  cmp     r8d, 4
0x140008a86  jnz     short loc_140008AE8
0x140008a88  test    ebp, ebp
0x140008a8a  jnz     short loc_140008AE8
0x140008a8c  mov     rax, [r15+28h]
0x140008a90  mov     r13, [rax+28h]
0x140008a94  mov     rcx, [r13+1A0h]
0x140008a9b  mov     r12, [rcx+180h]
0x140008aa2  call    Smb2IncrementActiveHandleCount
0x140008aa7  mov     eax, [r14]
0x140008aaa  test    al, 40h
0x140008aac  jz      short loc_140008AD9
0x140008aae  mov     eax, [r12+304h]
0x140008ab6  mov     edx, 0Ah
0x140008abb  mov     rcx, [r13+1A0h]
0x140008ac2  test    eax, eax
0x140008ac4  mov     r8d, 2
0x140008aca  cmovnz  edx, eax
0x140008acd  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140008ad4  nop     dword ptr [rax+rax+00h]
0x140008ad9  mov     r13, [rsp+0F8h+arg_0]
0x140008ae1  lea     r12, WPP_GLOBAL_Control
0x140008ae8  test    edi, edi
0x140008aea  jns     short loc_140008B41
0x140008aec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008af3  cmp     rcx, r12
0x140008af6  jz      short loc_140008B41
0x140008af8  mov     eax, [rcx+2Ch]
0x140008afb  test    al, 1
0x140008afd  jz      short loc_140008B41
0x140008aff  cmp     byte ptr [rcx+29h], 1
0x140008b03  jb      short loc_140008B41
0x140008b05  mov     rax, [r15+50h]
0x140008b09  mov     r9, r15
0x140008b0c  mov     edx, [rsi+4]
0x140008b0f  mov     rcx, [rcx+18h]
0x140008b13  mov     [rsp+0F8h+var_A0], rax
0x140008b18  mov     eax, [rsp+0F8h+arg_8]
0x140008b1f  mov     [rsp+0F8h+var_A8], ebp
0x140008b23  mov     dword ptr [rsp+0F8h+var_B0], ebp
0x140008b27  mov     [rsp+0F8h+var_B8], edx
0x140008b2b  mov     [rsp+0F8h+var_C0], edx
0x140008b2f  mov     dword ptr [rsp+0F8h+var_C8], eax
0x140008b33  mov     dword ptr [rsp+0F8h+var_D0], edi
0x140008b37  mov     [rsp+0F8h+var_D8], rsi
0x140008b3c  call    WPP_SF_qqLLdLdLZ
0x140008b41  cmp     [rsp+0F8h+arg_18], 6
0x140008b49  mov     r12d, dword ptr [rsp+0F8h+arg_10+4]
0x140008b51  jge     loc_140008CE5
0x140008b57  cmp     ebp, 9
0x140008b5a  jnz     loc_140008CE5
0x140008b60  mov     eax, [r14]
0x140008b63  test    al, 20h
0x140008b65  jz      loc_140008C21
0x140008b6b  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x140008b72  jz      loc_140008C0D
0x140008b78  mov     rax, [r15+20h]
0x140008b7c  lea     r10, [rsi+108h]
0x140008b83  mov     r8, [r15+50h]
0x140008b87  mov     rcx, [rax+78h]
0x140008b8b  mov     eax, [rsi+13Ch]
0x140008b91  mov     [rsp+0F8h+var_78], eax
0x140008b98  mov     eax, [rsi+138h]
0x140008b9e  mov     r9, [rcx+58h]
0x140008ba2  movzx   ecx, word ptr [r8]
0x140008ba6  mov     [rsp+0F8h+var_80], eax
0x140008baa  mov     rax, [r8+8]
0x140008bae  movzx   edx, word ptr [r9]
0x140008bb2  mov     [rsp+0F8h+var_88], rax
0x140008bb7  mov     rax, [r9+8]
0x140008bbb  mov     r9, rsi
0x140008bbe  shr     dx, 1
0x140008bc1  shr     cx, 1
0x140008bc4  mov     [rsp+0F8h+var_90], cx
0x140008bc9  mov     [rsp+0F8h+var_98], rax
0x140008bce  movzx   eax, word ptr [rsi+4]
0x140008bd2  mov     word ptr [rsp+0F8h+var_A0], dx
0x140008bd7  lea     rdx, PersistentHandleFailure
0x140008bde  mov     [rsp+0F8h+var_A8], r12d
0x140008be3  mov     dword ptr [rsp+0F8h+var_B0], edi
0x140008be7  mov     word ptr [rsp+0F8h+var_B8], bp
0x140008bec  mov     word ptr [rsp+0F8h+var_C0], ax
0x140008bf1  mov     rax, [rsi+24h]
0x140008bf5  mov     [rsp+0F8h+var_C8], r10
0x140008bfa  mov     [rsp+0F8h+var_D0], rax
0x140008bff  mov     rax, [rsi+1Ch]
0x140008c03  mov     [rsp+0F8h+var_D8], rax
0x140008c08  call    McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer
0x140008c0d  movzx   eax, cs:dbgBreakOnPersistentHandleFailure
0x140008c14  test    al, al
0x140008c16  jnz     loc_140008CD8
0x140008c1c  jmp     loc_140008CD9
0x140008c21  test    al, 40h
0x140008c23  jz      loc_140008CD9
0x140008c29  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x140008c30  jz      loc_140008CCD
0x140008c36  mov     rax, [r15+20h]
0x140008c3a  lea     r10, [rsi+108h]
0x140008c41  mov     r8, [r15+50h]
0x140008c45  mov     rcx, [rax+78h]
0x140008c49  mov     eax, [rsi+13Ch]
0x140008c4f  mov     [rsp+0F8h+var_78], eax
0x140008c56  mov     eax, [rsi+138h]
0x140008c5c  mov     r9, [rcx+58h]
0x140008c60  movzx   ecx, word ptr [r8]
0x140008c64  mov     [rsp+0F8h+var_80], eax
0x140008c68  mov     rax, [r8+8]
0x140008c6c  movzx   edx, word ptr [r9]
0x140008c70  mov     [rsp+0F8h+var_88], rax
0x140008c75  mov     rax, [r9+8]
0x140008c79  mov     r9, rsi
0x140008c7c  shr     dx, 1
0x140008c7f  shr     cx, 1
0x140008c82  mov     [rsp+0F8h+var_90], cx
0x140008c87  mov     [rsp+0F8h+var_98], rax
0x140008c8c  movzx   eax, word ptr [rsi+4]
0x140008c90  mov     word ptr [rsp+0F8h+var_A0], dx
0x140008c95  lea     rdx, ResilientHandleFailure
0x140008c9c  mov     [rsp+0F8h+var_A8], r12d
0x140008ca1  mov     dword ptr [rsp+0F8h+var_B0], edi
0x140008ca5  mov     word ptr [rsp+0F8h+var_B8], 9
0x140008cac  mov     word ptr [rsp+0F8h+var_C0], ax
0x140008cb1  mov     rax, [rsi+24h]
0x140008cb5  mov     [rsp+0F8h+var_C8], r10
0x140008cba  mov     [rsp+0F8h+var_D0], rax
0x140008cbf  mov     rax, [rsi+1Ch]
0x140008cc3  mov     [rsp+0F8h+var_D8], rax
0x140008cc8  call    McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer
0x140008ccd  movzx   eax, cs:dbgBreakOnResilientHandleFailure
0x140008cd4  test    al, al
0x140008cd6  jz      short loc_140008CD9
0x140008cd8  int     3; Trap to Debugger
0x140008cd9  movzx   eax, cs:dbgBreakOnSrvOpenInvalidation
0x140008ce0  test    al, al
0x140008ce2  jz      short loc_140008CE5
  ... truncated ...
```
