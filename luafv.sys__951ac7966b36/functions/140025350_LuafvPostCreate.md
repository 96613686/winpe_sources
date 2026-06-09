# LuafvPostCreate

- ea: `0x140025350`
- end: `0x14002588c`
- name: `LuafvPostCreate`
- size: `1340`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140001adc`
- `0x140003fb8`
- `0x140014a90`
- `0x140016238`
- `0x140017e60`
- `0x1400181f4`
- `0x140018530`
- `0x14001860c`
- `0x140018680`
- `0x14001f620`
- `0x1400224ec`
- `0x1400247e0`
- `0x140025350`

## import_xrefs

- `FLTMGR!FltCancelFileOpen` at `0x140025448`
- `FLTMGR!FltCancelFileOpen` at `0x140025511`
- `FLTMGR!FltCancelFileOpen` at `0x1400255a0`
- `FLTMGR!FltCancelFileOpen` at `0x140025448`
- `FLTMGR!FltCancelFileOpen` at `0x140025511`
- `FLTMGR!FltCancelFileOpen` at `0x1400255a0`
- `FLTMGR!FltSetStreamHandleContext` at `0x14002541a`
- `FLTMGR!FltSetStreamHandleContext` at `0x140025572`
- `FLTMGR!FltSetStreamHandleContext` at `0x14002541a`
- `FLTMGR!FltSetStreamHandleContext` at `0x140025572`
- `FLTMGR!FltDeleteContext` at `0x1400253f4`
- `FLTMGR!FltDeleteContext` at `0x14002554c`
- `FLTMGR!FltDeleteContext` at `0x1400253f4`
- `FLTMGR!FltDeleteContext` at `0x14002554c`
- `FLTMGR!FltReleaseContext` at `0x140025866`
- `FLTMGR!FltReleaseContext` at `0x140025866`

## pseudocode

```c
__int64 __fastcall LuafvPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
{
  unsigned __int16 *v3; // rbp
  int IsEnabledDeviceUsageNoInline; // eax
  NTSTATUS Status; // ecx
  bool v9; // zf
  NTSTATUS v10; // ecx
  int v11; // eax
  NTSTATUS v12; // ecx
  char v13; // cl
  NTSTATUS v14; // eax
  __int64 v15; // r8
  NTSTATUS v16; // esi
  char v17; // al
  int v18; // r9d
  int MirrorFile; // esi
  char v20; // al
  NTSTATUS v21; // eax
  NTSTATUS v22; // esi
  char v23; // dl
  int *v24; // r15
  int v25; // r8d
  PFLT_IO_PARAMETER_BLOCK Iopb; // rsi
  int v27; // ecx
  int v28; // r12d
  int FsInformationClass_high; // edx
  int v30; // eax
  bool v31; // cl
  char v32; // al
  NTSTATUS v33; // eax
  int v34; // r9d
  NTSTATUS v35; // eax
  bool v37; // [rsp+30h] [rbp-38h] BYREF
  bool v38; // [rsp+31h] [rbp-37h] BYREF
  char v39; // [rsp+80h] [rbp+18h] BYREF

  v3 = *(unsigned __int16 **)a3;
  v37 = 0;
  IsEnabledDeviceUsageNoInline = Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline();
  if ( !v3 )
  {
    if ( !IsEnabledDeviceUsageNoInline )
    {
      v9 = CallbackData->IoStatus.Status == -1073741790;
      goto LABEL_21;
    }
    Status = CallbackData->IoStatus.Status;
    if ( (*(_BYTE *)(a3 + 53) & 0x10) == 0 )
    {
      v9 = Status == -1073741790;
LABEL_21:
      if ( !v9 )
        goto LABEL_99;
      v18 = *(_DWORD *)(a3 + 48);
      if ( v18 )
        LuafvLogExclusion((__int64)CallbackData, 0, a3, v18);
      goto LABEL_24;
    }
    if ( Status == -1073741790 || (*(_BYTE *)(a3 + 52) & 2) != 0 )
      goto LABEL_99;
  }
  v10 = CallbackData->IoStatus.Status;
  if ( v10 < 0 )
  {
    v23 = *(_BYTE *)(a3 + 52);
    v24 = (int *)(a3 + 48);
    if ( (v23 & 2) != 0 || (v25 = *v24) != 0 && (v23 & 0x10) == 0 && (dword_14000F118 & 8) == 0 )
    {
      if ( (dword_14000F118 & 4) != 0 && (*v24 & 0x400) != 0 && v10 == -1073741790 )
        LuafvLogExclusion((__int64)CallbackData, 0, a3, *v24);
      goto LABEL_99;
    }
    v38 = 0;
    if ( v10 != -1073741790 )
    {
      if ( v10 != -1073741766
        || (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline()
        && ((*(_BYTE *)(a3 + 53) & 0x10) != 0 || !v3)
        || (v3[44] & 2) == 0 )
      {
        goto LABEL_99;
      }
      if ( (dword_14000F118 & 8) != 0 && (*(_DWORD *)(a3 + 48) & 0x400) != 0 )
      {
        CallbackData->IoStatus.Status = -1073741790;
        goto LABEL_99;
      }
      goto LABEL_92;
    }
    Iopb = CallbackData->Iopb;
    v39 = 0;
    v27 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
    v28 = v27 & 0x10000;
    if ( (dword_14000F118 & 8) != 0 )
    {
      if ( (v23 & 1) != 0 )
      {
        if ( (v27 & dword_14000F110) == 0
          && (Iopb->Parameters.Create.Options & 0xFF000000) == 0x1000000
          && (v27 & 0xD0156) != 0 )
        {
          *v24 = v25 | 0x80;
        }
LABEL_53:
        FsInformationClass_high = HIBYTE(Iopb->Parameters.SetVolumeInformation.FsInformationClass);
        if ( (*(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & dword_14000F110) != 0 )
        {
          if ( FsInformationClass_high == 1 )
            goto LABEL_71;
        }
        else if ( FsInformationClass_high == 1 )
        {
          goto LABEL_55;
        }
        if ( FsInformationClass_high != 3 )
        {
          v32 = 0;
LABEL_72:
          v39 = v32;
          goto LABEL_58;
        }
LABEL_71:
        v32 = 1;
        goto LABEL_72;
      }
    }
    else if ( (v23 & 1) != 0 )
    {
      goto LABEL_53;
    }
LABEL_55:
    if ( (dword_14000F118 & 8) == 0
      || (*(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & 0xD0156) == 0
      && (Iopb->Parameters.Create.Options & 0xFF000000) == 0x1000000 )
    {
LABEL_82:
      if ( v28 )
        LuafvLogDeleteFilePCAEvent((int)CallbackData);
LABEL_24:
      if ( (*(_BYTE *)(a3 + 52) & 0x10) != 0 )
        LuafvLogWRPPCAEvent((_DWORD)CallbackData);
      goto LABEL_99;
    }
LABEL_58:
    v30 = LuafvCheckAdminAccess((__int64)CallbackData, *(struct _FLT_INSTANCE **)(a2 + 24), (__int64)v3, &v37);
    if ( v30 < 0 )
    {
      LuafvLogFileError((int)CallbackData, (int)v3, (const EVENT_DESCRIPTOR *)LuafvAdminAccessCheckFailed, v30);
      goto LABEL_78;
    }
    v31 = v37;
    if ( (dword_14000F118 & 8) != 0 )
    {
      if ( v37 )
      {
LABEL_64:
        if ( (v3[20] & 0xC) == 8 && (*(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & 6) != 0 )
        {
          if ( (dword_14000F118 & 8) != 0 )
            *(_DWORD *)(a3 + 48) = *v24 | 0x200;
        }
        else
        {
          v33 = LuafvDelayOrVirtualizeFile(CallbackData, a2, (unsigned __int16 **)a3, &v39, &v38, (_DWORD *)(a3 + 48));
          if ( v33 < 0 )
          {
            CallbackData->IoStatus.Status = v33;
            CallbackData->IoStatus.Information = 0;
          }
          else if ( v39 )
          {
            *(_BYTE *)(a3 + 52) |= 0x80u;
          }
        }
LABEL_78:
        v34 = *(_DWORD *)(a3 + 48);
        if ( v34 && (dword_14000F118 & 8) != 0 )
          LuafvLogExclusion((__int64)CallbackData, (int)v3, a3, v34);
        if ( !v38 )
          goto LABEL_82;
LABEL_92:
        *(_BYTE *)(a3 + 52) |= 2u;
        v35 = LuafvReparse(CallbackData);
        if ( v35 >= 0 )
          goto LABEL_99;
        CallbackData->IoStatus.Status = v35;
        goto LABEL_94;
      }
      *v24 |= 0x20u;
    }
    if ( !v31 && (dword_14000F118 & 8) == 0 )
      goto LABEL_78;
    goto LABEL_64;
  }
  v11 = Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline();
  v12 = CallbackData->IoStatus.Status;
  if ( v11 )
  {
    if ( v12 != 260 )
    {
      v13 = *(_BYTE *)(a3 + 52);
      if ( (v13 & 0xA) == 0 && (*(_BYTE *)(a3 + 53) & 0x10) == 0 )
        goto LABEL_99;
      if ( (v13 & 4) != 0 )
      {
        FltDeleteContext((PFLT_CONTEXT)a3);
        *(_BYTE *)(a3 + 52) &= ~4u;
      }
      v14 = FltSetStreamHandleContext(
              *(PFLT_INSTANCE *)(a2 + 24),
              *(PFILE_OBJECT *)(a2 + 32),
              FLT_SET_CONTEXT_KEEP_IF_EXISTS,
              (PFLT_CONTEXT)a3,
              0);
      v16 = v14;
      if ( v14 < 0 )
      {
        LuafvLogFileError((int)CallbackData, 0, (const EVENT_DESCRIPTOR *)LuafvSetStreamHandleContextFailed, v14);
        FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
        CallbackData->IoStatus.Status = v16;
        CallbackData->IoStatus.Information = 0;
      }
      *(_BYTE *)(a3 + 52) |= 4u;
      v17 = *(_BYTE *)(a3 + 52);
      if ( (v17 & 2) != 0 && CallbackData->IoStatus.Information == 2 )
        goto LABEL_18;
      if ( (*(_BYTE *)(a3 + 53) & 0x10) == 0 )
        goto LABEL_99;
      if ( *(_QWORD *)(a3 + 32) )
        goto LABEL_99;
      if ( *(_QWORD *)(a3 + 24) )
        goto LABEL_99;
      MirrorFile = LuafvCreateMirrorFile(CallbackData, a2, a3);
      if ( MirrorFile >= 0 )
        goto LABEL_99;
      FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
      CallbackData->IoStatus.Status = MirrorFile;
LABEL_94:
      CallbackData->IoStatus.Information = 0;
      goto LABEL_99;
    }
LABEL_32:
    LuafvRemoveEcp(CallbackData);
    goto LABEL_99;
  }
  if ( v12 == 260 )
    goto LABEL_32;
  v20 = *(_BYTE *)(a3 + 52);
  if ( (v20 & 0xA) != 0 )
  {
    if ( (v20 & 4) != 0 )
    {
      FltDeleteContext((PFLT_CONTEXT)a3);
      *(_BYTE *)(a3 + 52) &= ~4u;
    }
    v21 = FltSetStreamHandleContext(
            *(PFLT_INSTANCE *)(a2 + 24),
            *(PFILE_OBJECT *)(a2 + 32),
            FLT_SET_CONTEXT_KEEP_IF_EXISTS,
            (PFLT_CONTEXT)a3,
            0);
    v22 = v21;
    if ( v21 < 0 )
    {
      LuafvLogFileError((int)CallbackData, 0, (const EVENT_DESCRIPTOR *)LuafvSetStreamHandleContextFailed, v21);
      FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
      CallbackData->IoStatus.Status = v22;
      CallbackData->IoStatus.Information = 0;
    }
    *(_BYTE *)(a3 + 52) |= 4u;
    v17 = *(_BYTE *)(a3 + 52);
    if ( (v17 & 2) != 0 && CallbackData->IoStatus.Information == 2 )
    {
LABEL_18:
      *(_BYTE *)(a3 + 52) = v17 | 0x20;
      LuafvUpdateFileTableForFileChange(v3 + 24, *((_QWORD *)v3 + 10), v15);
      if ( (dword_14000F118 & 1) != 0 )
        LuafvLogVirtualCreate((__int64)CallbackData, a3);
    }
  }
LABEL_99:
  FltReleaseContext((PFLT_CONTEXT)a3);
  return 0;
}

```

## disassembly

```asm
0x140025350  mov     [rsp+arg_0], rbx
0x140025355  mov     [rsp+arg_8], rbp
0x14002535a  push    rsi
0x14002535b  push    rdi
0x14002535c  push    r12
0x14002535e  push    r13
0x140025360  push    r15
0x140025362  sub     rsp, 40h
0x140025366  mov     rbp, [r8]
0x140025369  xor     r12d, r12d
0x14002536c  mov     [rsp+68h+var_38], r12b
0x140025371  mov     rbx, r8
0x140025374  mov     r13, rdx
0x140025377  mov     rdi, rcx
0x14002537a  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x14002537f  mov     esi, 0C0000022h
0x140025384  test    rbp, rbp
0x140025387  jnz     short loc_1400253B3
0x140025389  test    eax, eax
0x14002538b  jz      loc_14002549D
0x140025391  test    byte ptr [rbx+35h], 10h
0x140025395  mov     ecx, [rdi+18h]
0x140025398  jnz     short loc_1400253A1
0x14002539a  cmp     ecx, esi
0x14002539c  jmp     loc_1400254A0
0x1400253a1  cmp     ecx, esi
0x1400253a3  jz      loc_140025863
0x1400253a9  test    byte ptr [rbx+34h], 2
0x1400253ad  jnz     loc_140025863
0x1400253b3  mov     ecx, [rdi+18h]
0x1400253b6  test    ecx, ecx
0x1400253b8  js      loc_1400255D2
0x1400253be  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x1400253c3  mov     ecx, [rdi+18h]
0x1400253c6  test    eax, eax
0x1400253c8  jz      loc_140025525
0x1400253ce  cmp     ecx, 104h
0x1400253d4  jz      loc_14002552D
0x1400253da  mov     cl, [rbx+34h]
0x1400253dd  test    cl, 0Ah
0x1400253e0  jnz     short loc_1400253EC
0x1400253e2  test    byte ptr [rbx+35h], 10h
0x1400253e6  jz      loc_140025863
0x1400253ec  test    cl, 4
0x1400253ef  jz      short loc_140025404
0x1400253f1  mov     rcx, rbx; Context
0x1400253f4  call    cs:__imp_FltDeleteContext
0x1400253fb  nop     dword ptr [rax+rax+00h]
0x140025400  and     byte ptr [rbx+34h], 0FBh
0x140025404  mov     rdx, [r13+20h]; FileObject
0x140025408  mov     r9, rbx; NewContext
0x14002540b  mov     rcx, [r13+18h]; Instance
0x14002540f  mov     r8d, 1; Operation
0x140025415  mov     [rsp+68h+OldContext], r12; OldContext
0x14002541a  call    cs:__imp_FltSetStreamHandleContext
0x140025421  nop     dword ptr [rax+rax+00h]
0x140025426  mov     esi, eax
0x140025428  test    eax, eax
0x14002542a  jns     short loc_14002545B
0x14002542c  mov     r9d, eax
0x14002542f  lea     r8, LuafvSetStreamHandleContextFailed
0x140025436  xor     edx, edx
0x140025438  mov     rcx, rdi
0x14002543b  call    LuafvLogFileError
0x140025440  mov     rdx, [r13+20h]; FileObject
0x140025444  mov     rcx, [r13+18h]; Instance
0x140025448  call    cs:__imp_FltCancelFileOpen
0x14002544f  nop     dword ptr [rax+rax+00h]
0x140025454  mov     [rdi+18h], esi
0x140025457  mov     [rdi+20h], r12
0x14002545b  or      byte ptr [rbx+34h], 4
0x14002545f  mov     al, [rbx+34h]
0x140025462  test    al, 2
0x140025464  jz      short loc_1400254D3
0x140025466  cmp     qword ptr [rdi+20h], 2
0x14002546b  jnz     short loc_1400254D3
0x14002546d  or      al, 20h
0x14002546f  lea     rcx, [rbp+30h]
0x140025473  mov     [rbx+34h], al
0x140025476  mov     rdx, [rbp+50h]
0x14002547a  call    LuafvUpdateFileTableForFileChange
0x14002547f  mov     eax, cs:dword_14000F118
0x140025485  test    al, 1
0x140025487  jz      loc_140025863
0x14002548d  mov     rdx, rbx
0x140025490  mov     rcx, rdi
0x140025493  call    LuafvLogVirtualCreate
0x140025498  jmp     loc_140025863
0x14002549d  cmp     [rdi+18h], esi
0x1400254a0  jnz     loc_140025863
0x1400254a6  mov     r9d, [rbx+30h]
0x1400254aa  test    r9d, r9d
0x1400254ad  jz      short loc_1400254BC
0x1400254af  mov     r8, rbx
0x1400254b2  xor     edx, edx
0x1400254b4  mov     rcx, rdi
0x1400254b7  call    LuafvLogExclusion
0x1400254bc  test    byte ptr [rbx+34h], 10h
0x1400254c0  jz      loc_140025863
0x1400254c6  mov     rcx, rdi
0x1400254c9  call    LuafvLogWRPPCAEvent
0x1400254ce  jmp     loc_140025863
0x1400254d3  test    byte ptr [rbx+35h], 10h
0x1400254d7  jz      loc_140025863
0x1400254dd  cmp     [rbx+20h], r12
0x1400254e1  jnz     loc_140025863
0x1400254e7  cmp     [rbx+18h], r12
0x1400254eb  jnz     loc_140025863
0x1400254f1  mov     r8, rbx
0x1400254f4  mov     rdx, r13
0x1400254f7  mov     rcx, rdi
0x1400254fa  call    LuafvCreateMirrorFile
0x1400254ff  mov     esi, eax
0x140025501  test    eax, eax
0x140025503  jns     loc_140025863
0x140025509  mov     rdx, [r13+20h]; FileObject
0x14002550d  mov     rcx, [r13+18h]; Instance
0x140025511  call    cs:__imp_FltCancelFileOpen
0x140025518  nop     dword ptr [rax+rax+00h]
0x14002551d  mov     [rdi+18h], esi
0x140025520  jmp     loc_140025838
0x140025525  cmp     ecx, 104h
0x14002552b  jnz     short loc_14002553A
0x14002552d  mov     rcx, rdi; CallbackData
0x140025530  call    LuafvRemoveEcp
0x140025535  jmp     loc_140025863
0x14002553a  mov     al, [rbx+34h]
0x14002553d  test    al, 0Ah
0x14002553f  jz      loc_140025863
0x140025545  test    al, 4
0x140025547  jz      short loc_14002555C
0x140025549  mov     rcx, rbx; Context
0x14002554c  call    cs:__imp_FltDeleteContext
0x140025553  nop     dword ptr [rax+rax+00h]
0x140025558  and     byte ptr [rbx+34h], 0FBh
0x14002555c  mov     rdx, [r13+20h]; FileObject
0x140025560  mov     r9, rbx; NewContext
0x140025563  mov     rcx, [r13+18h]; Instance
0x140025567  mov     r8d, 1; Operation
0x14002556d  mov     [rsp+68h+OldContext], r12; OldContext
0x140025572  call    cs:__imp_FltSetStreamHandleContext
0x140025579  nop     dword ptr [rax+rax+00h]
0x14002557e  mov     esi, eax
0x140025580  test    eax, eax
0x140025582  jns     short loc_1400255B3
0x140025584  mov     r9d, eax
0x140025587  lea     r8, LuafvSetStreamHandleContextFailed
0x14002558e  xor     edx, edx
0x140025590  mov     rcx, rdi
0x140025593  call    LuafvLogFileError
0x140025598  mov     rdx, [r13+20h]; FileObject
0x14002559c  mov     rcx, [r13+18h]; Instance
0x1400255a0  call    cs:__imp_FltCancelFileOpen
0x1400255a7  nop     dword ptr [rax+rax+00h]
0x1400255ac  mov     [rdi+18h], esi
0x1400255af  mov     [rdi+20h], r12
0x1400255b3  or      byte ptr [rbx+34h], 4
0x1400255b7  mov     al, [rbx+34h]
0x1400255ba  test    al, 2
0x1400255bc  jz      loc_140025863
0x1400255c2  cmp     qword ptr [rdi+20h], 2
0x1400255c7  jnz     loc_140025863
0x1400255cd  jmp     loc_14002546D
0x1400255d2  mov     dl, [rbx+34h]
0x1400255d5  lea     r15, [rbx+30h]
0x1400255d9  test    dl, 2
0x1400255dc  jnz     loc_14002583E
0x1400255e2  mov     r8d, [r15]
0x1400255e5  mov     r9b, 8
0x1400255e8  test    r8d, r8d
0x1400255eb  jz      short loc_140025601
0x1400255ed  test    dl, 10h
0x1400255f0  jnz     short loc_140025601
0x1400255f2  mov     eax, cs:dword_14000F118
0x1400255f8  test    r9b, al
0x1400255fb  jz      loc_14002583E
0x140025601  mov     [rsp+68h+var_37], r12b
0x140025606  cmp     ecx, esi
0x140025608  jnz     loc_1400257E2
0x14002560e  mov     rsi, [rdi+10h]
0x140025612  mov     r11d, 0FF000000h
0x140025618  mov     [rsp+68h+arg_10], r12b
0x140025620  mov     r10d, 0D0156h
0x140025626  mov     rax, [rsi+18h]
0x14002562a  mov     ecx, [rax+10h]
0x14002562d  mov     r12d, ecx
0x140025630  mov     eax, cs:dword_14000F118
0x140025636  and     r12d, 10000h
0x14002563d  test    r9b, al
0x140025640  jz      short loc_14002566B
0x140025642  test    dl, 1
0x140025645  jz      short loc_140025690
0x140025647  test    cs:dword_14000F110, ecx
0x14002564d  jnz     short loc_140025670
0x14002564f  mov     eax, [rsi+20h]
0x140025652  and     eax, r11d
0x140025655  cmp     eax, 1000000h
0x14002565a  jnz     short loc_140025670
0x14002565c  test    r10d, ecx
0x14002565f  jz      short loc_140025670
0x140025661  bts     r8d, 7
0x140025666  mov     [r15], r8d
0x140025669  jmp     short loc_140025670
0x14002566b  test    dl, 1
0x14002566e  jz      short loc_140025690
0x140025670  mov     rax, [rsi+18h]
0x140025674  movzx   edx, byte ptr [rsi+23h]
0x140025678  mov     ecx, [rax+10h]
0x14002567b  test    cs:dword_14000F110, ecx
0x140025681  jnz     loc_14002572D
0x140025687  cmp     edx, 1
0x14002568a  jnz     loc_140025732
0x140025690  mov     eax, cs:dword_14000F118
0x140025696  test    r9b, al
0x140025699  jz      loc_1400257CC
0x14002569f  mov     rax, [rsi+18h]
0x1400256a3  test    [rax+10h], r10d
0x1400256a7  jnz     short loc_1400256BA
0x1400256a9  mov     eax, [rsi+20h]
0x1400256ac  and     eax, r11d
0x1400256af  cmp     eax, 1000000h
0x1400256b4  jz      loc_1400257CC
0x1400256ba  mov     rdx, [r13+18h]
0x1400256be  lea     r9, [rsp+68h+var_38]
0x1400256c3  mov     r8, rbp
0x1400256c6  mov     rcx, rdi
0x1400256c9  call    LuafvCheckAdminAccess
0x1400256ce  test    eax, eax
0x1400256d0  js      loc_14002578F
0x1400256d6  mov     eax, cs:dword_14000F118
0x1400256dc  mov     cl, [rsp+68h+var_38]
0x1400256e0  test    al, 8
0x1400256e2  jz      short loc_1400256EC
0x1400256e4  test    cl, cl
0x1400256e6  jnz     short loc_1400256FE
0x1400256e8  or      dword ptr [r15], 20h
0x1400256ec  test    cl, cl
0x1400256ee  jnz     short loc_1400256FE
0x1400256f0  mov     eax, cs:dword_14000F118
0x1400256f6  test    al, 8
0x1400256f8  jz      loc_1400257A4
0x1400256fe  mov     al, [rbp+28h]
0x140025701  and     al, 0Ch
0x140025703  cmp     al, 8
0x140025705  jnz     short loc_140025749
0x140025707  mov     rax, [rsi+18h]
0x14002570b  mov     ecx, [rax+10h]
0x14002570e  test    cl, 6
0x140025711  jz      short loc_140025749
0x140025713  mov     eax, cs:dword_14000F118
0x140025719  test    al, 8
0x14002571b  jz      loc_1400257A4
0x140025721  mov     eax, [r15]
0x140025724  bts     eax, 9
0x140025728  mov     [rbx+30h], eax
0x14002572b  jmp     short loc_1400257A4
0x14002572d  cmp     edx, 1
0x140025730  jz      short loc_14002573B
0x140025732  cmp     edx, 3
0x140025735  jz      short loc_14002573B
0x140025737  xor     al, al
0x140025739  jmp     short loc_14002573D
0x14002573b  mov     al, 1
0x14002573d  mov     [rsp+68h+arg_10], al
0x140025744  jmp     loc_1400256BA
0x140025749  lea     rax, [rsp+68h+var_37]
0x14002574e  mov     [rsp+68h+var_40], r15
0x140025753  lea     r9, [rsp+68h+arg_10]
0x14002575b  mov     [rsp+68h+OldContext], rax
0x140025760  mov     r8, rbx
0x140025763  mov     rdx, r13
0x140025766  mov     rcx, rdi
0x140025769  call    LuafvDelayOrVirtualizeFile
0x14002576e  test    eax, eax
0x140025770  js      short loc_140025782
0x140025772  cmp     [rsp+68h+arg_10], 0
0x14002577a  jz      short loc_1400257A4
0x14002577c  or      byte ptr [rbx+34h], 80h
0x140025780  jmp     short loc_1400257A4
0x140025782  mov     [rdi+18h], eax
0x140025785  mov     qword ptr [rdi+20h], 0
0x14002578d  jmp     short loc_1400257A4
0x14002578f  mov     r9d, eax
0x140025792  lea     r8, LuafvAdminAccessCheckFailed
0x140025799  mov     rdx, rbp
0x14002579c  mov     rcx, rdi
0x14002579f  call    LuafvLogFileError
0x1400257a4  mov     r9d, [rbx+30h]
0x1400257a8  test    r9d, r9d
0x1400257ab  jz      short loc_1400257C5
0x1400257ad  mov     eax, cs:dword_14000F118
0x1400257b3  test    al, 8
0x1400257b5  jz      short loc_1400257C5
0x1400257b7  mov     r8, rbx
0x1400257ba  mov     rdx, rbp
0x1400257bd  mov     rcx, rdi
0x1400257c0  call    LuafvLogExclusion
0x1400257c5  cmp     [rsp+68h+var_37], 0
0x1400257ca  jnz     short loc_14002581C
0x1400257cc  test    r12d, r12d
  ... truncated ...
```
