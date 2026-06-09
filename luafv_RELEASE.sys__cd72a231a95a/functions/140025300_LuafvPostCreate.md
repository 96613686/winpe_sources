# LuafvPostCreate

- ea: `0x140025300`
- end: `0x140025817`
- name: `LuafvPostCreate`
- size: `1303`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140001adc`
- `0x1400041e8`
- `0x140014a90`
- `0x140016238`
- `0x140017e10`
- `0x1400181a4`
- `0x1400184e0`
- `0x1400185bc`
- `0x140018630`
- `0x14001f5d0`
- `0x14002249c`
- `0x140024790`
- `0x140025300`

## import_xrefs

- `FLTMGR!FltCancelFileOpen` at `0x14002540c`
- `FLTMGR!FltCancelFileOpen` at `0x1400254a0`
- `FLTMGR!FltCancelFileOpen` at `0x14002552f`
- `FLTMGR!FltCancelFileOpen` at `0x14002540c`
- `FLTMGR!FltCancelFileOpen` at `0x1400254a0`
- `FLTMGR!FltCancelFileOpen` at `0x14002552f`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400253dd`
- `FLTMGR!FltSetStreamHandleContext` at `0x140025501`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400253dd`
- `FLTMGR!FltSetStreamHandleContext` at `0x140025501`
- `FLTMGR!FltDeleteContext` at `0x1400253b7`
- `FLTMGR!FltDeleteContext` at `0x1400254db`
- `FLTMGR!FltDeleteContext` at `0x1400253b7`
- `FLTMGR!FltDeleteContext` at `0x1400254db`
- `FLTMGR!FltReleaseContext` at `0x1400257f7`
- `FLTMGR!FltReleaseContext` at `0x1400257f7`

## pseudocode

```c
__int64 __fastcall LuafvPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 *a3)
{
  __int64 v3; // r15
  int IsEnabledDeviceUsageNoInline; // eax
  NTSTATUS Status; // ecx
  int v9; // eax
  NTSTATUS v10; // ecx
  char v11; // cl
  NTSTATUS v12; // eax
  NTSTATUS v13; // r14d
  char v14; // al
  NTSTATUS MirrorFile; // esi
  char v16; // al
  NTSTATUS v17; // eax
  NTSTATUS v18; // esi
  char v19; // dl
  int *v20; // r14
  int v21; // r8d
  PFLT_IO_PARAMETER_BLOCK Iopb; // r13
  int v23; // ecx
  int v24; // r12d
  int FsInformationClass_high; // edx
  int v26; // eax
  char v27; // cl
  char v28; // al
  NTSTATUS v29; // eax
  NTSTATUS v30; // eax
  char v32; // [rsp+30h] [rbp-58h] BYREF
  char v33[87]; // [rsp+31h] [rbp-57h] BYREF
  char v34; // [rsp+A0h] [rbp+18h] BYREF

  v3 = *a3;
  v32 = 0;
  IsEnabledDeviceUsageNoInline = Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline();
  if ( !v3 && (!IsEnabledDeviceUsageNoInline || (*((_BYTE *)a3 + 53) & 0x10) == 0) )
  {
    if ( CallbackData->IoStatus.Status != -1073741790 )
      goto LABEL_93;
    if ( *((_DWORD *)a3 + 12) )
      LuafvLogExclusion((_DWORD)CallbackData);
    goto LABEL_7;
  }
  Status = CallbackData->IoStatus.Status;
  if ( Status < 0 )
  {
    v19 = *((_BYTE *)a3 + 52);
    v20 = (int *)(a3 + 6);
    if ( (v19 & 2) != 0 || (v21 = *v20) != 0 && (v19 & 0x10) == 0 && (dword_14000EAD8 & 8) == 0 )
    {
      if ( (dword_14000EAD8 & 4) != 0 && (*v20 & 0x400) != 0 && Status == -1073741790 )
        LuafvLogExclusion((_DWORD)CallbackData);
      goto LABEL_93;
    }
    v33[0] = 0;
    if ( Status != -1073741790 )
    {
      if ( Status != -1073741766 || (*((_BYTE *)a3 + 53) & 0x10) != 0 || (*(_BYTE *)(v3 + 88) & 2) == 0 )
        goto LABEL_93;
      if ( (dword_14000EAD8 & 8) != 0 && (v21 & 0x400) != 0 )
      {
        CallbackData->IoStatus.Status = -1073741790;
        goto LABEL_93;
      }
      goto LABEL_86;
    }
    Iopb = CallbackData->Iopb;
    v34 = 0;
    v23 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
    v24 = v23 & 0x10000;
    if ( (dword_14000EAD8 & 8) != 0 )
    {
      if ( (v19 & 1) != 0 )
      {
        if ( (v23 & dword_14000EAD0) == 0
          && (Iopb->Parameters.Create.Options & 0xFF000000) == 0x1000000
          && (v23 & 0xD0156) != 0 )
        {
          *v20 = v21 | 0x80;
        }
LABEL_49:
        FsInformationClass_high = HIBYTE(Iopb->Parameters.SetVolumeInformation.FsInformationClass);
        if ( (*(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & dword_14000EAD0) != 0 )
        {
          if ( FsInformationClass_high == 1 )
            goto LABEL_67;
        }
        else if ( FsInformationClass_high == 1 )
        {
          goto LABEL_51;
        }
        if ( FsInformationClass_high != 3 )
        {
          v28 = 0;
LABEL_68:
          v34 = v28;
          goto LABEL_54;
        }
LABEL_67:
        v28 = 1;
        goto LABEL_68;
      }
    }
    else if ( (v19 & 1) != 0 )
    {
      goto LABEL_49;
    }
LABEL_51:
    if ( (dword_14000EAD8 & 8) == 0
      || (*(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & 0xD0156) == 0
      && (Iopb->Parameters.Create.Options & 0xFF000000) == 0x1000000 )
    {
LABEL_78:
      if ( v24 )
        LuafvLogDeleteFilePCAEvent((_DWORD)CallbackData);
LABEL_7:
      if ( (*((_BYTE *)a3 + 52) & 0x10) != 0 )
        LuafvLogWRPPCAEvent((_DWORD)CallbackData);
      goto LABEL_93;
    }
LABEL_54:
    v26 = LuafvCheckAdminAccess(CallbackData, *(_QWORD *)(a2 + 24), v3, &v32);
    if ( v26 < 0 )
    {
      LuafvLogFileError(CallbackData, v3, LuafvAdminAccessCheckFailed, (unsigned int)v26);
      goto LABEL_74;
    }
    v27 = v32;
    if ( (dword_14000EAD8 & 8) != 0 )
    {
      if ( v32 )
      {
LABEL_60:
        if ( (*(_BYTE *)(v3 + 40) & 0xC) == 8 && (*(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & 6) != 0 )
        {
          if ( (dword_14000EAD8 & 8) != 0 )
            *((_DWORD *)a3 + 12) = *v20 | 0x200;
        }
        else
        {
          v29 = LuafvDelayOrVirtualizeFile(
                  (_DWORD)CallbackData,
                  a2,
                  (_DWORD)a3,
                  (unsigned int)&v34,
                  (__int64)v33,
                  (__int64)(a3 + 6));
          if ( v29 < 0 )
          {
            CallbackData->IoStatus.Status = v29;
            CallbackData->IoStatus.Information = 0;
          }
          else if ( v34 )
          {
            *((_BYTE *)a3 + 52) |= 0x80u;
          }
        }
LABEL_74:
        if ( *((_DWORD *)a3 + 12) && (dword_14000EAD8 & 8) != 0 )
          LuafvLogExclusion((_DWORD)CallbackData);
        if ( !v33[0] )
          goto LABEL_78;
LABEL_86:
        *((_BYTE *)a3 + 52) |= 2u;
        v30 = LuafvReparse(CallbackData);
        if ( v30 >= 0 )
          goto LABEL_93;
        CallbackData->IoStatus.Status = v30;
        goto LABEL_88;
      }
      *v20 |= 0x20u;
    }
    if ( !v27 && (dword_14000EAD8 & 8) == 0 )
      goto LABEL_74;
    goto LABEL_60;
  }
  v9 = Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline();
  v10 = CallbackData->IoStatus.Status;
  if ( v9 )
  {
    if ( v10 != 260 )
    {
      v11 = *((_BYTE *)a3 + 52);
      if ( (v11 & 0xA) == 0 && (*((_BYTE *)a3 + 53) & 0x10) == 0 )
        goto LABEL_93;
      if ( (v11 & 4) != 0 )
      {
        FltDeleteContext(a3);
        *((_BYTE *)a3 + 52) &= ~4u;
      }
      v12 = FltSetStreamHandleContext(
              *(PFLT_INSTANCE *)(a2 + 24),
              *(PFILE_OBJECT *)(a2 + 32),
              FLT_SET_CONTEXT_KEEP_IF_EXISTS,
              a3,
              0);
      v13 = v12;
      if ( v12 < 0 )
      {
        LuafvLogFileError(CallbackData, 0, LuafvSetStreamHandleContextFailed, (unsigned int)v12);
        FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
        CallbackData->IoStatus.Status = v13;
        CallbackData->IoStatus.Information = 0;
      }
      *((_BYTE *)a3 + 52) |= 4u;
      v14 = *((_BYTE *)a3 + 52);
      if ( (v14 & 2) != 0 && CallbackData->IoStatus.Information == 2 )
        goto LABEL_20;
      if ( (*((_BYTE *)a3 + 53) & 0x10) == 0 )
        goto LABEL_93;
      if ( a3[4] )
        goto LABEL_93;
      if ( a3[3] )
        goto LABEL_93;
      MirrorFile = LuafvCreateMirrorFile(CallbackData, a2, a3);
      if ( MirrorFile >= 0 )
        goto LABEL_93;
      FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
      CallbackData->IoStatus.Status = MirrorFile;
LABEL_88:
      CallbackData->IoStatus.Information = 0;
      goto LABEL_93;
    }
LABEL_28:
    LuafvRemoveEcp(CallbackData);
    goto LABEL_93;
  }
  if ( v10 == 260 )
    goto LABEL_28;
  v16 = *((_BYTE *)a3 + 52);
  if ( (v16 & 0xA) != 0 )
  {
    if ( (v16 & 4) != 0 )
    {
      FltDeleteContext(a3);
      *((_BYTE *)a3 + 52) &= ~4u;
    }
    v17 = FltSetStreamHandleContext(
            *(PFLT_INSTANCE *)(a2 + 24),
            *(PFILE_OBJECT *)(a2 + 32),
            FLT_SET_CONTEXT_KEEP_IF_EXISTS,
            a3,
            0);
    v18 = v17;
    if ( v17 < 0 )
    {
      LuafvLogFileError(CallbackData, 0, LuafvSetStreamHandleContextFailed, (unsigned int)v17);
      FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
      CallbackData->IoStatus.Status = v18;
      CallbackData->IoStatus.Information = 0;
    }
    *((_BYTE *)a3 + 52) |= 4u;
    v14 = *((_BYTE *)a3 + 52);
    if ( (v14 & 2) != 0 && CallbackData->IoStatus.Information == 2 )
    {
LABEL_20:
      *((_BYTE *)a3 + 52) = v14 | 0x20;
      LuafvUpdateFileTableForFileChange(v3 + 48, *(_QWORD *)(v3 + 80));
      if ( (dword_14000EAD8 & 1) != 0 )
        LuafvLogVirtualCreate(CallbackData, a3);
    }
  }
LABEL_93:
  FltReleaseContext(a3);
  return 0;
}

```

## disassembly

```asm
0x140025300  push    rbx
0x140025302  push    rbp
0x140025303  push    rsi
0x140025304  push    rdi
0x140025305  push    r12
0x140025307  push    r13
0x140025309  push    r14
0x14002530b  push    r15
0x14002530d  sub     rsp, 48h
0x140025311  mov     r15, [r8]
0x140025314  xor     r12d, r12d
0x140025317  mov     [rsp+88h+var_58], r12b
0x14002531c  mov     rbx, r8
0x14002531f  mov     rbp, rdx
0x140025322  mov     rdi, rcx
0x140025325  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x14002532a  mov     sil, 10h
0x14002532d  test    r15, r15
0x140025330  jnz     short loc_140025376
0x140025332  test    eax, eax
0x140025334  jz      short loc_14002533C
0x140025336  test    [rbx+35h], sil
0x14002533a  jnz     short loc_140025376
0x14002533c  cmp     dword ptr [rdi+18h], 0C0000022h
0x140025343  jnz     loc_1400257F4
0x140025349  mov     r9d, [rbx+30h]
0x14002534d  test    r9d, r9d
0x140025350  jz      short loc_14002535F
0x140025352  mov     r8, rbx
0x140025355  xor     edx, edx
0x140025357  mov     rcx, rdi
0x14002535a  call    LuafvLogExclusion
0x14002535f  test    [rbx+34h], sil
0x140025363  jz      loc_1400257F4
0x140025369  mov     rcx, rdi
0x14002536c  call    LuafvLogWRPPCAEvent
0x140025371  jmp     loc_1400257F4
0x140025376  mov     ecx, [rdi+18h]
0x140025379  test    ecx, ecx
0x14002537b  js      loc_140025561
0x140025381  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140025386  mov     ecx, [rdi+18h]
0x140025389  test    eax, eax
0x14002538b  jz      loc_1400254B4
0x140025391  cmp     ecx, 104h
0x140025397  jz      loc_1400254BC
0x14002539d  mov     cl, [rbx+34h]
0x1400253a0  test    cl, 0Ah
0x1400253a3  jnz     short loc_1400253AF
0x1400253a5  test    [rbx+35h], sil
0x1400253a9  jz      loc_1400257F4
0x1400253af  test    cl, 4
0x1400253b2  jz      short loc_1400253C7
0x1400253b4  mov     rcx, rbx; Context
0x1400253b7  call    cs:__imp_FltDeleteContext
0x1400253be  nop     dword ptr [rax+rax+00h]
0x1400253c3  and     byte ptr [rbx+34h], 0FBh
0x1400253c7  mov     rdx, [rbp+20h]; FileObject
0x1400253cb  mov     r9, rbx; NewContext
0x1400253ce  mov     rcx, [rbp+18h]; Instance
0x1400253d2  mov     r8d, 1; Operation
0x1400253d8  mov     [rsp+88h+OldContext], r12; OldContext
0x1400253dd  call    cs:__imp_FltSetStreamHandleContext
0x1400253e4  nop     dword ptr [rax+rax+00h]
0x1400253e9  mov     r14d, eax
0x1400253ec  test    eax, eax
0x1400253ee  jns     short loc_140025420
0x1400253f0  mov     r9d, eax
0x1400253f3  lea     r8, LuafvSetStreamHandleContextFailed
0x1400253fa  xor     edx, edx
0x1400253fc  mov     rcx, rdi
0x1400253ff  call    LuafvLogFileError
0x140025404  mov     rdx, [rbp+20h]; FileObject
0x140025408  mov     rcx, [rbp+18h]; Instance
0x14002540c  call    cs:__imp_FltCancelFileOpen
0x140025413  nop     dword ptr [rax+rax+00h]
0x140025418  mov     [rdi+18h], r14d
0x14002541c  mov     [rdi+20h], r12
0x140025420  or      byte ptr [rbx+34h], 4
0x140025424  mov     al, [rbx+34h]
0x140025427  test    al, 2
0x140025429  jz      short loc_140025462
0x14002542b  cmp     qword ptr [rdi+20h], 2
0x140025430  jnz     short loc_140025462
0x140025432  or      al, 20h
0x140025434  lea     rcx, [r15+30h]
0x140025438  mov     [rbx+34h], al
0x14002543b  mov     rdx, [r15+50h]
0x14002543f  call    LuafvUpdateFileTableForFileChange
0x140025444  mov     eax, cs:dword_14000EAD8
0x14002544a  test    al, 1
0x14002544c  jz      loc_1400257F4
0x140025452  mov     rdx, rbx
0x140025455  mov     rcx, rdi
0x140025458  call    LuafvLogVirtualCreate
0x14002545d  jmp     loc_1400257F4
0x140025462  test    [rbx+35h], sil
0x140025466  jz      loc_1400257F4
0x14002546c  cmp     [rbx+20h], r12
0x140025470  jnz     loc_1400257F4
0x140025476  cmp     [rbx+18h], r12
0x14002547a  jnz     loc_1400257F4
0x140025480  mov     r8, rbx
0x140025483  mov     rdx, rbp
0x140025486  mov     rcx, rdi
0x140025489  call    LuafvCreateMirrorFile
0x14002548e  mov     esi, eax
0x140025490  test    eax, eax
0x140025492  jns     loc_1400257F4
0x140025498  mov     rdx, [rbp+20h]; FileObject
0x14002549c  mov     rcx, [rbp+18h]; Instance
0x1400254a0  call    cs:__imp_FltCancelFileOpen
0x1400254a7  nop     dword ptr [rax+rax+00h]
0x1400254ac  mov     [rdi+18h], esi
0x1400254af  jmp     loc_1400257C5
0x1400254b4  cmp     ecx, 104h
0x1400254ba  jnz     short loc_1400254C9
0x1400254bc  mov     rcx, rdi; CallbackData
0x1400254bf  call    LuafvRemoveEcp
0x1400254c4  jmp     loc_1400257F4
0x1400254c9  mov     al, [rbx+34h]
0x1400254cc  test    al, 0Ah
0x1400254ce  jz      loc_1400257F4
0x1400254d4  test    al, 4
0x1400254d6  jz      short loc_1400254EB
0x1400254d8  mov     rcx, rbx; Context
0x1400254db  call    cs:__imp_FltDeleteContext
0x1400254e2  nop     dword ptr [rax+rax+00h]
0x1400254e7  and     byte ptr [rbx+34h], 0FBh
0x1400254eb  mov     rdx, [rbp+20h]; FileObject
0x1400254ef  mov     r9, rbx; NewContext
0x1400254f2  mov     rcx, [rbp+18h]; Instance
0x1400254f6  mov     r8d, 1; Operation
0x1400254fc  mov     [rsp+88h+OldContext], r12; OldContext
0x140025501  call    cs:__imp_FltSetStreamHandleContext
0x140025508  nop     dword ptr [rax+rax+00h]
0x14002550d  mov     esi, eax
0x14002550f  test    eax, eax
0x140025511  jns     short loc_140025542
0x140025513  mov     r9d, eax
0x140025516  lea     r8, LuafvSetStreamHandleContextFailed
0x14002551d  xor     edx, edx
0x14002551f  mov     rcx, rdi
0x140025522  call    LuafvLogFileError
0x140025527  mov     rdx, [rbp+20h]; FileObject
0x14002552b  mov     rcx, [rbp+18h]; Instance
0x14002552f  call    cs:__imp_FltCancelFileOpen
0x140025536  nop     dword ptr [rax+rax+00h]
0x14002553b  mov     [rdi+18h], esi
0x14002553e  mov     [rdi+20h], r12
0x140025542  or      byte ptr [rbx+34h], 4
0x140025546  mov     al, [rbx+34h]
0x140025549  test    al, 2
0x14002554b  jz      loc_1400257F4
0x140025551  cmp     qword ptr [rdi+20h], 2
0x140025556  jnz     loc_1400257F4
0x14002555c  jmp     loc_140025432
0x140025561  mov     dl, [rbx+34h]
0x140025564  lea     r14, [rbx+30h]
0x140025568  test    dl, 2
0x14002556b  jnz     loc_1400257CB
0x140025571  mov     r8d, [r14]
0x140025574  mov     r9b, 8
0x140025577  test    r8d, r8d
0x14002557a  jz      short loc_140025590
0x14002557c  test    sil, dl
0x14002557f  jnz     short loc_140025590
0x140025581  mov     eax, cs:dword_14000EAD8
0x140025587  test    r9b, al
0x14002558a  jz      loc_1400257CB
0x140025590  mov     [rsp+88h+var_57], r12b
0x140025595  cmp     ecx, 0C0000022h
0x14002559b  jnz     loc_140025779
0x1400255a1  mov     r13, [rdi+10h]
0x1400255a5  mov     r11d, 0FF000000h
0x1400255ab  mov     [rsp+88h+arg_10], r12b
0x1400255b3  mov     r10d, 0D0156h
0x1400255b9  mov     rax, [r13+18h]
0x1400255bd  mov     ecx, [rax+10h]
0x1400255c0  mov     r12d, ecx
0x1400255c3  mov     eax, cs:dword_14000EAD8
0x1400255c9  and     r12d, 10000h
0x1400255d0  test    r9b, al
0x1400255d3  jz      short loc_1400255FF
0x1400255d5  test    dl, 1
0x1400255d8  jz      short loc_140025625
0x1400255da  test    cs:dword_14000EAD0, ecx
0x1400255e0  jnz     short loc_140025604
0x1400255e2  mov     eax, [r13+20h]
0x1400255e6  and     eax, r11d
0x1400255e9  cmp     eax, 1000000h
0x1400255ee  jnz     short loc_140025604
0x1400255f0  test    r10d, ecx
0x1400255f3  jz      short loc_140025604
0x1400255f5  bts     r8d, 7
0x1400255fa  mov     [r14], r8d
0x1400255fd  jmp     short loc_140025604
0x1400255ff  test    dl, 1
0x140025602  jz      short loc_140025625
0x140025604  mov     rax, [r13+18h]
0x140025608  movzx   edx, byte ptr [r13+23h]
0x14002560d  mov     ecx, [rax+10h]
0x140025610  test    cs:dword_14000EAD0, ecx
0x140025616  jnz     loc_1400256C4
0x14002561c  cmp     edx, 1
0x14002561f  jnz     loc_1400256C9
0x140025625  mov     eax, cs:dword_14000EAD8
0x14002562b  test    r9b, al
0x14002562e  jz      loc_140025763
0x140025634  mov     rax, [r13+18h]
0x140025638  test    [rax+10h], r10d
0x14002563c  jnz     short loc_140025650
0x14002563e  mov     eax, [r13+20h]
0x140025642  and     eax, r11d
0x140025645  cmp     eax, 1000000h
0x14002564a  jz      loc_140025763
0x140025650  mov     rdx, [rbp+18h]
0x140025654  lea     r9, [rsp+88h+var_58]
0x140025659  mov     r8, r15
0x14002565c  mov     rcx, rdi
0x14002565f  call    LuafvCheckAdminAccess
0x140025664  test    eax, eax
0x140025666  js      loc_140025726
0x14002566c  mov     eax, cs:dword_14000EAD8
0x140025672  mov     cl, [rsp+88h+var_58]
0x140025676  test    al, 8
0x140025678  jz      short loc_140025682
0x14002567a  test    cl, cl
0x14002567c  jnz     short loc_140025694
0x14002567e  or      dword ptr [r14], 20h
0x140025682  test    cl, cl
0x140025684  jnz     short loc_140025694
0x140025686  mov     eax, cs:dword_14000EAD8
0x14002568c  test    al, 8
0x14002568e  jz      loc_14002573B
0x140025694  mov     al, [r15+28h]
0x140025698  and     al, 0Ch
0x14002569a  cmp     al, 8
0x14002569c  jnz     short loc_1400256E0
0x14002569e  mov     rax, [r13+18h]
0x1400256a2  mov     ecx, [rax+10h]
0x1400256a5  test    cl, 6
0x1400256a8  jz      short loc_1400256E0
0x1400256aa  mov     eax, cs:dword_14000EAD8
0x1400256b0  test    al, 8
0x1400256b2  jz      loc_14002573B
0x1400256b8  mov     eax, [r14]
0x1400256bb  bts     eax, 9
0x1400256bf  mov     [rbx+30h], eax
0x1400256c2  jmp     short loc_14002573B
0x1400256c4  cmp     edx, 1
0x1400256c7  jz      short loc_1400256D2
0x1400256c9  cmp     edx, 3
0x1400256cc  jz      short loc_1400256D2
0x1400256ce  xor     al, al
0x1400256d0  jmp     short loc_1400256D4
0x1400256d2  mov     al, 1
0x1400256d4  mov     [rsp+88h+arg_10], al
0x1400256db  jmp     loc_140025650
0x1400256e0  lea     rax, [rsp+88h+var_57]
0x1400256e5  mov     [rsp+88h+var_60], r14
0x1400256ea  lea     r9, [rsp+88h+arg_10]
0x1400256f2  mov     [rsp+88h+OldContext], rax
0x1400256f7  mov     r8, rbx
0x1400256fa  mov     rdx, rbp
0x1400256fd  mov     rcx, rdi
0x140025700  call    LuafvDelayOrVirtualizeFile
0x140025705  test    eax, eax
0x140025707  js      short loc_140025719
0x140025709  cmp     [rsp+88h+arg_10], 0
0x140025711  jz      short loc_14002573B
0x140025713  or      byte ptr [rbx+34h], 80h
0x140025717  jmp     short loc_14002573B
0x140025719  mov     [rdi+18h], eax
0x14002571c  mov     qword ptr [rdi+20h], 0
0x140025724  jmp     short loc_14002573B
0x140025726  mov     r9d, eax
0x140025729  lea     r8, LuafvAdminAccessCheckFailed
0x140025730  mov     rdx, r15
0x140025733  mov     rcx, rdi
0x140025736  call    LuafvLogFileError
0x14002573b  mov     r9d, [rbx+30h]
0x14002573f  test    r9d, r9d
0x140025742  jz      short loc_14002575C
0x140025744  mov     eax, cs:dword_14000EAD8
0x14002574a  test    al, 8
0x14002574c  jz      short loc_14002575C
0x14002574e  mov     r8, rbx
0x140025751  mov     rdx, r15
0x140025754  mov     rcx, rdi
0x140025757  call    LuafvLogExclusion
0x14002575c  cmp     [rsp+88h+var_57], 0
0x140025761  jnz     short loc_1400257A9
0x140025763  test    r12d, r12d
0x140025766  jz      loc_14002535F
0x14002576c  mov     rcx, rdi
0x14002576f  call    LuafvLogDeleteFilePCAEvent
0x140025774  jmp     loc_14002535F
0x140025779  cmp     ecx, 0C000003Ah
0x14002577f  jnz     short loc_1400257F4
  ... truncated ...
```
