# FCPreCreate

- ea: `0x14000f9a0`
- end: `0x1400101b2`
- name: `FCPreCreate`
- size: `2066`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002fd0`
- `0x140003098`
- `0x140003b80`
- `0x14000f9a0`
- `0x1400101c0`
- `0x140010500`
- `0x1400111f0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ffa5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ffd3`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140010001`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ffa5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ffd3`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140010001`
- `ntoskrnl!FsRtlIsMobileOS` at `0x14000fc75`
- `ntoskrnl!FsRtlIsMobileOS` at `0x14000fc75`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400101a4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013817`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400101a4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013817`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000fd30`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000fd30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010114`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010137`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010114`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010137`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137e4`
- `ntoskrnl!ExAllocatePool2` at `0x14000faf1`
- `ntoskrnl!ExAllocatePool2` at `0x14000faf1`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000fc01`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000fc01`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400100f9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400137a9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400100f9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400137a9`
- `FLTMGR!FltGetFileNameInformation` at `0x14000fa46`
- `FLTMGR!FltGetFileNameInformation` at `0x14000fa46`
- `FLTMGR!FltReleaseContext` at `0x1400100e3`
- `FLTMGR!FltReleaseContext` at `0x140013793`
- `FLTMGR!FltReleaseContext` at `0x1400100e3`
- `FLTMGR!FltReleaseContext` at `0x140013793`
- `FLTMGR!FltParseFileNameInformation` at `0x14000fa65`
- `FLTMGR!FltParseFileNameInformation` at `0x14000fa65`
- `FLTMGR!FltGetVolumeContext` at `0x14000fa0e`
- `FLTMGR!FltGetVolumeContext` at `0x14000fa0e`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14001008c`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14001008c`

## pseudocode

```c
__int64 __fastcall FCPreCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  PFLT_CALLBACK_DATA v4; // r13
  wchar_t *v5; // rsi
  int v6; // r14d
  char v7; // r15
  NTSTATUS VolumeContext; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  __int64 v10; // rcx
  __int64 v11; // rcx
  PFLT_FILE_NAME_INFORMATION v12; // rdi
  char v13; // r13
  unsigned int Length; // eax
  USHORT v15; // bx
  USHORT v16; // r12
  WCHAR *Pool2; // rax
  WCHAR *v18; // rcx
  WCHAR *v19; // rbx
  wchar_t *v20; // rcx
  char v21; // r12
  void *v22; // rdi
  unsigned int v23; // r14d
  __int64 v24; // r8
  unsigned int v25; // edx
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  ULONG Options; // edx
  BOOLEAN v31; // al
  int v32; // eax
  PVOID v33; // rcx
  int v35; // [rsp+40h] [rbp-B8h] BYREF
  char v36; // [rsp+44h] [rbp-B4h]
  USHORT v37; // [rsp+48h] [rbp-B0h]
  const wchar_t *v38; // [rsp+50h] [rbp-A8h] BYREF
  UNICODE_STRING String2; // [rsp+58h] [rbp-A0h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-90h] BYREF
  PVOID P; // [rsp+70h] [rbp-88h] BYREF
  PFLT_CONTEXT v42; // [rsp+78h] [rbp-80h] BYREF
  WCHAR *v43; // [rsp+80h] [rbp-78h]
  WCHAR *v44; // [rsp+88h] [rbp-70h]
  __int128 Parameter; // [rsp+90h] [rbp-68h] BYREF
  PVOID v46[2]; // [rsp+A0h] [rbp-58h]
  __int64 v47; // [rsp+B0h] [rbp-48h]

  v4 = CallbackData;
  v42 = 0;
  String2 = 0;
  FileNameInformation = 0;
  P = 0;
  v5 = 0;
  v38 = 0;
  v6 = 0;
  v35 = 0;
  v7 = 0;
  VolumeContext = FltGetVolumeContext(*(PFLT_FILTER *)(a2 + 8), *(PFLT_VOLUME *)(a2 + 16), &v42);
  if ( VolumeContext < 0 )
    goto LABEL_43;
  if ( (v4->Iopb->Parameters.Create.Options & 0x2000) == 0 )
  {
    v24 = *(_QWORD *)(a2 + 32);
    v25 = *(unsigned __int16 *)(v24 + 88);
    if ( v25 > 2
      && *(_WORD *)(*(_QWORD *)(v24 + 96) + 2 * ((unsigned __int64)*(unsigned __int16 *)(v24 + 88) >> 1) - 2) == 92 )
    {
      *(_WORD *)(v24 + 88) = v25 - 2;
    }
  }
  VolumeContext = FltGetFileNameInformation(v4, 0x101u, &FileNameInformation);
  if ( VolumeContext < 0 )
  {
    if ( *((_BYTE *)v42 + 49) )
    {
      if ( (Microsoft_Windows_FileCryptEnableBits & 2) != 0 )
        McTemplateK0d_EtwWriteTransfer(v10, &GetFileNameInformationFailure, Iopb, (unsigned int)VolumeContext);
    }
    else
    {
      VolumeContext = 0;
    }
    goto LABEL_43;
  }
  VolumeContext = FltParseFileNameInformation(FileNameInformation);
  if ( VolumeContext < 0 )
  {
    if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
      McTemplateK0d_EtwWriteTransfer(v11, &ParseFileNameInformationFailure, Iopb, (unsigned int)VolumeContext);
    goto LABEL_43;
  }
  if ( !FileNameInformation->ParentDir.Buffer )
  {
    v23 = 1;
    v22 = 0;
    goto LABEL_84;
  }
  v12 = FileNameInformation;
  v43 = 0;
  v37 = 0;
  v13 = 1;
  v36 = 1;
  Length = FileNameInformation->FinalComponent.Length;
  v15 = FileNameInformation->ParentDir.Length + Length + 2;
  v37 = v15;
  if ( (_WORD)Length && FileNameInformation->FinalComponent.Buffer[((unsigned __int64)Length >> 1) - 1] != 92 )
  {
    v15 += 2;
    v37 = v15;
    v13 = 0;
    v36 = 0;
  }
  v16 = v15;
  Pool2 = (WCHAR *)ExAllocatePool2(256, v15, 1718502214);
  v18 = Pool2;
  v44 = Pool2;
  if ( Pool2 )
  {
    String2.Buffer = Pool2;
    String2.Length = 0;
    String2.MaximumLength = v15;
    v43 = Pool2;
    memmove(Pool2, v12->ParentDir.Buffer, v12->ParentDir.Length);
    v19 = &v44[(unsigned __int64)v12->ParentDir.Length >> 1];
    v43 = v19;
    memmove(v19, v12->FinalComponent.Buffer, v12->FinalComponent.Length);
    v18 = &v19[(unsigned __int64)v12->FinalComponent.Length >> 1];
    v43 = v18;
    if ( !v13 )
    {
      *v18++ = 92;
      v43 = v18;
    }
    *v18 = 0;
    String2.Length = v16 - 2;
    VolumeContext = 0;
  }
  else
  {
    VolumeContext = -1073741670;
  }
  if ( VolumeContext < 0 )
  {
    if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
      McTemplateK0d_EtwWriteTransfer(v18, &ConstructFullPathFailure, Iopb, (unsigned int)VolumeContext);
    goto LABEL_55;
  }
  v7 = 1;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  Parameter = (unsigned __int64)&String2;
  if ( KeExpandKernelStackAndCalloutEx(FCpObtainSecurityInfoCallout, &Parameter, 0x3000u, 0, 0) >= 0 )
  {
    P = (PVOID)*((_QWORD *)&Parameter + 1);
    v5 = (wchar_t *)v46[0];
    v38 = (const wchar_t *)v46[0];
    v6 = (int)v46[1];
    v35 = (int)v46[1];
    VolumeContext = v47;
    goto LABEL_16;
  }
  v44 = 0;
  v5 = 0;
  v38 = 0;
  if ( String2.Length )
  {
    VolumeContext = StSecGetSecurityDescriptor(&String2, &P, &v38, &v35);
    v5 = (wchar_t *)v38;
    if ( VolumeContext < 0 || v38 )
    {
      if ( VolumeContext < 0 && (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
        McTemplateK0d_EtwWriteTransfer(v20, &GetSecurityDescriptorFailure, Iopb, (unsigned int)VolumeContext);
      goto LABEL_40;
    }
    if ( (gFCFlags & 4) != 0 )
    {
      v5 = L"{0b7992da-c5e6-41e3-b24f-55419b997a15}";
      v38 = L"{0b7992da-c5e6-41e3-b24f-55419b997a15}";
      v6 = 1;
      v35 = 1;
    }
    else
    {
      if ( (gFCFlags & 2) == 0 )
      {
LABEL_40:
        v6 = v35;
        goto LABEL_16;
      }
      if ( RtlPrefixUnicodeString(&gMusicPath, &String2, 1u) )
      {
        v5 = L"MusicChamber";
        v38 = L"MusicChamber";
      }
      else if ( RtlPrefixUnicodeString(&gPicturesPath, &String2, 1u) )
      {
        v5 = L"PicturesChamber";
        v38 = L"PicturesChamber";
      }
      else
      {
        v31 = RtlPrefixUnicodeString(&gVideosPath, &String2, 1u);
        v20 = L"VideosChamber";
        if ( !v31 )
          v20 = 0;
        v5 = v20;
        v38 = v20;
      }
      v6 = 1;
      v35 = 1;
    }
  }
  else
  {
    VolumeContext = 0;
  }
LABEL_16:
  if ( VolumeContext < 0 )
  {
    if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
    {
      McTemplateK0d_EtwWriteTransfer(v20, &ObtainSdAndChamberIdFailure, Iopb, (unsigned int)VolumeContext);
      v4 = CallbackData;
      goto LABEL_43;
    }
LABEL_55:
    v4 = CallbackData;
    v23 = 0;
    v22 = 0;
    goto LABEL_84;
  }
  if ( !*((_BYTE *)v42 + 49) )
  {
    VolumeContext = 0;
    v4 = CallbackData;
LABEL_19:
    v21 = 0;
    goto LABEL_20;
  }
  v4 = CallbackData;
  v29 = FCpAccessCheck(CallbackData, P, &v35);
  VolumeContext = v29;
  if ( v29 >= 0 )
    goto LABEL_19;
  if ( v29 == -1073741790 )
  {
    Iopb = CallbackData->Iopb;
    Options = Iopb->Parameters.Create.Options;
    v20 = (wchar_t *)HIBYTE(Options);
    if ( (((_DWORD)v20 - 3) & 0xFFFFFFFD) != 0 )
    {
      if ( (_DWORD)v20 == 2 && (Options & 1) != 0 )
      {
        VolumeContext = -1073741771;
LABEL_43:
        v23 = 0;
        v22 = 0;
        goto LABEL_84;
      }
    }
    else
    {
      v32 = 4;
      if ( (_DWORD)v20 != 5 )
        v32 = 1;
      Iopb->Parameters.Create.Options = Options & 0xFFFFFF | (v32 << 24);
      VolumeContext = FCpAccessCheck(CallbackData, P, &v35);
      if ( !VolumeContext )
      {
        v21 = 1;
        FltSetCallbackDataDirty(CallbackData);
        goto LABEL_79;
      }
    }
  }
  v21 = 0;
LABEL_79:
  if ( VolumeContext < 0 )
  {
    if ( (Microsoft_Windows_FileCryptEnableBits & 2) != 0 )
      McTemplateK0zd_EtwWriteTransfer((_DWORD)v20, Options, (_DWORD)Iopb, String2.Buffer, VolumeContext);
    goto LABEL_43;
  }
LABEL_20:
  if ( (unsigned __int8)FsRtlIsMobileOS(v20) )
  {
    if ( !v5 )
    {
LABEL_24:
      v22 = 0;
LABEL_25:
      *a3 = v22;
      v23 = 0;
      goto LABEL_84;
    }
    v26 = ExAllocateFromNPagedLookasideList(&gPre2PostCreateContextList);
    v22 = v26;
    if ( v26 )
    {
      *v26 = v5;
      *((_DWORD *)v26 + 2) = v6;
      *((_BYTE *)v26 + 12) = v21;
      goto LABEL_25;
    }
    VolumeContext = -1073741670;
    if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
      McTemplateK0d_EtwWriteTransfer(v27, &AllocationFailure, Iopb, 3221225626LL);
    v23 = 0;
  }
  else
  {
    if ( (unsigned int)(v6 - 1) <= 1 )
    {
      v28 = *(_QWORD *)(v4->Iopb->Parameters.WMI.ProviderId + 8);
      *(_DWORD *)(v28 + 12) |= 0x40000u;
    }
    if ( !v5 )
      goto LABEL_24;
    FCpFreeChamberId(v5);
    v5 = 0;
    v38 = 0;
    v22 = 0;
    *a3 = 0;
    v23 = 0;
  }
LABEL_84:
  if ( v42 )
    FltReleaseContext(v42);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v7 )
  {
    ExFreePoolWithTag(String2.Buffer, 0x666E4346u);
    *(_DWORD *)&String2.Length = 0;
  }
  v33 = P;
  if ( P )
    ExFreePoolWithTag(P, 0x70537453u);
  if ( VolumeContext < 0 )
  {
    if ( v5 )
      FCpFreeChamberId(v5);
    if ( v22 )
      ExFreeToNPagedLookasideList(&gPre2PostCreateContextList, v22);
    v4->IoStatus.Status = VolumeContext;
    v4->IoStatus.Information = 0;
    v23 = 4;
    if ( (Microsoft_Windows_FileCryptEnableBits & 2) != 0 )
      McTemplateK0d_EtwWriteTransfer(v33, &PreCreateFailure, Iopb, (unsigned int)VolumeContext);
  }
  return v23;
}

```

## disassembly

```asm
0x14000f9a0  mov     rax, rsp
0x14000f9a3  mov     [rax+18h], r8
0x14000f9a7  mov     [rax+8], rcx
0x14000f9ab  push    rbx
0x14000f9ac  push    rsi
0x14000f9ad  push    rdi
0x14000f9ae  push    r12
0x14000f9b0  push    r13
0x14000f9b2  push    r14
0x14000f9b4  push    r15
0x14000f9b6  sub     rsp, 0C0h
0x14000f9bd  mov     rdi, rdx
0x14000f9c0  mov     r13, rcx
0x14000f9c3  xor     r12d, r12d
0x14000f9c6  mov     [rax-80h], r12
0x14000f9ca  xorps   xmm0, xmm0
0x14000f9cd  movups  xmmword ptr [rsp+0F8h+String2.Length], xmm0
0x14000f9d2  mov     [rsp+0F8h+FileNameInformation], r12
0x14000f9d7  mov     [rax+20h], r12d
0x14000f9db  mov     [rsp+0F8h+var_C8], r12d
0x14000f9e0  mov     [rsp+0F8h+P], r12
0x14000f9e5  mov     esi, r12d
0x14000f9e8  mov     [rsp+0F8h+var_A8], r12
0x14000f9ed  mov     r14d, r12d
0x14000f9f0  mov     [rsp+0F8h+var_B8], r12d
0x14000f9f5  mov     [rsp+0F8h+Entry], r12
0x14000f9fa  xor     r15b, r15b
0x14000f9fd  mov     [rsp+0F8h+var_C4], r15b
0x14000fa02  lea     r8, [rax-80h]; Context
0x14000fa06  mov     rdx, [rdx+10h]; Volume
0x14000fa0a  mov     rcx, [rdi+8]; Filter
0x14000fa0e  call    cs:__imp_FltGetVolumeContext
0x14000fa15  nop     dword ptr [rax+rax+00h]
0x14000fa1a  mov     ebx, eax
0x14000fa1c  mov     [rsp+0F8h+var_C8], eax
0x14000fa20  test    eax, eax
0x14000fa22  js      loc_14000FE04
0x14000fa28  mov     rax, [r13+10h]
0x14000fa2c  test    dword ptr [rax+20h], 2000h
0x14000fa33  jz      loc_14000FCBB
0x14000fa39  lea     r8, [rsp+0F8h+FileNameInformation]; FileNameInformation
0x14000fa3e  mov     edx, 101h; NameOptions
0x14000fa43  mov     rcx, r13; CallbackData
0x14000fa46  call    cs:__imp_FltGetFileNameInformation
0x14000fa4d  nop     dword ptr [rax+rax+00h]
0x14000fa52  mov     ebx, eax
0x14000fa54  mov     [rsp+0F8h+var_C8], eax
0x14000fa58  test    eax, eax
0x14000fa5a  js      loc_14000FDEE
0x14000fa60  mov     rcx, [rsp+0F8h+FileNameInformation]; FileNameInformation
0x14000fa65  call    cs:__imp_FltParseFileNameInformation
0x14000fa6c  nop     dword ptr [rax+rax+00h]
0x14000fa71  mov     ebx, eax
0x14000fa73  mov     [rsp+0F8h+var_C8], eax
0x14000fa77  test    eax, eax
0x14000fa79  js      loc_14000FF21
0x14000fa7f  mov     rax, [rsp+0F8h+FileNameInformation]
0x14000fa84  cmp     qword ptr [rax+70h], 0
0x14000fa89  jz      loc_14000FEC4
0x14000fa8f  mov     rdi, rax
0x14000fa92  mov     [rsp+0F8h+var_78], r12
0x14000fa9a  mov     [rsp+0F8h+var_B0], r12w
0x14000faa0  mov     r13b, 1
0x14000faa3  mov     [rsp+0F8h+var_B4], r13b
0x14000faa8  movzx   eax, word ptr [rax+58h]
0x14000faac  lea     ebx, [rax+2]
0x14000faaf  add     bx, [rdi+68h]
0x14000fab3  mov     [rsp+0F8h+var_B0], bx
0x14000fab8  test    ax, ax
0x14000fabb  jz      short loc_14000FADF
0x14000fabd  mov     ecx, eax
0x14000fabf  shr     rcx, 1
0x14000fac2  mov     rax, [rdi+60h]
0x14000fac6  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14000facc  jz      short loc_14000FADF
0x14000face  add     bx, 2
0x14000fad2  mov     [rsp+0F8h+var_B0], bx
0x14000fad7  xor     r13b, r13b
0x14000fada  mov     [rsp+0F8h+var_B4], r13b
0x14000fadf  movzx   r12d, bx
0x14000fae3  mov     r8d, 666E4346h
0x14000fae9  mov     edx, r12d
0x14000faec  mov     ecx, 100h
0x14000faf1  call    cs:__imp_ExAllocatePool2
0x14000faf8  nop     dword ptr [rax+rax+00h]
0x14000fafd  mov     rcx, rax; void *
0x14000fb00  mov     [rsp+0F8h+var_70], rax
0x14000fb08  test    rax, rax
0x14000fb0b  jz      loc_14000FF44
0x14000fb11  mov     [rsp+0F8h+String2.Buffer], rax
0x14000fb16  xor     eax, eax
0x14000fb18  mov     [rsp+0F8h+String2.Length], ax
0x14000fb1d  mov     [rsp+0F8h+String2.MaximumLength], bx
0x14000fb22  mov     [rsp+0F8h+var_78], rcx
0x14000fb2a  movzx   r8d, word ptr [rdi+68h]; Size
0x14000fb2f  mov     rdx, [rdi+70h]; Src
0x14000fb33  call    memmove
0x14000fb38  movzx   eax, word ptr [rdi+68h]
0x14000fb3c  shr     rax, 1
0x14000fb3f  mov     rcx, [rsp+0F8h+var_70]
0x14000fb47  lea     rbx, [rcx+rax*2]
0x14000fb4b  mov     [rsp+0F8h+var_78], rbx
0x14000fb53  movzx   r8d, word ptr [rdi+58h]; Size
0x14000fb58  mov     rdx, [rdi+60h]; Src
0x14000fb5c  mov     rcx, rbx; void *
0x14000fb5f  call    memmove
0x14000fb64  movzx   eax, word ptr [rdi+58h]
0x14000fb68  shr     rax, 1
0x14000fb6b  lea     rcx, [rbx+rax*2]
0x14000fb6f  mov     [rsp+0F8h+var_78], rcx
0x14000fb77  test    r13b, r13b
0x14000fb7a  jnz     short loc_14000FB90
0x14000fb7c  mov     eax, 5Ch ; '\'
0x14000fb81  mov     [rcx], ax
0x14000fb84  add     rcx, 2
0x14000fb88  mov     [rsp+0F8h+var_78], rcx
0x14000fb90  xor     eax, eax
0x14000fb92  mov     [rcx], ax
0x14000fb95  sub     r12w, 2
0x14000fb9a  mov     [rsp+0F8h+String2.Length], r12w
0x14000fba0  xor     r12d, r12d
0x14000fba3  mov     ebx, r12d
0x14000fba6  mov     [rsp+0F8h+var_C8], ebx
0x14000fbaa  test    ebx, ebx
0x14000fbac  js      loc_14000FF51
0x14000fbb2  mov     r15b, 1
0x14000fbb5  mov     [rsp+0F8h+var_C4], r15b
0x14000fbba  xorps   xmm0, xmm0
0x14000fbbd  xor     eax, eax
0x14000fbbf  movups  [rsp+0F8h+Parameter], xmm0
0x14000fbc7  movups  xmmword ptr [rsp+0F8h+var_58], xmm0
0x14000fbcf  mov     [rsp+0F8h+var_48], rax
0x14000fbd7  lea     rax, [rsp+0F8h+String2]
0x14000fbdc  mov     qword ptr [rsp+0F8h+Parameter], rax
0x14000fbe4  mov     [rsp+0F8h+Context], r12; Context
0x14000fbe9  xor     r9d, r9d; Wait
0x14000fbec  mov     r8d, 3000h; Size
0x14000fbf2  lea     rdx, [rsp+0F8h+Parameter]; Parameter
0x14000fbfa  lea     rcx, FCpObtainSecurityInfoCallout; Callout
0x14000fc01  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000fc08  nop     dword ptr [rax+rax+00h]
0x14000fc0d  test    eax, eax
0x14000fc0f  js      loc_14000FD81
0x14000fc15  mov     rax, qword ptr [rsp+0F8h+Parameter+8]
0x14000fc1d  mov     [rsp+0F8h+P], rax
0x14000fc22  mov     rsi, [rsp+0F8h+var_58]
0x14000fc2a  mov     [rsp+0F8h+var_A8], rsi
0x14000fc2f  mov     r14d, dword ptr [rsp+0F8h+var_58+8]
0x14000fc37  mov     [rsp+0F8h+var_B8], r14d
0x14000fc3c  mov     ebx, dword ptr [rsp+0F8h+var_48]
0x14000fc43  mov     edi, 1
0x14000fc48  mov     [rsp+0F8h+var_C8], ebx
0x14000fc4c  test    ebx, ebx
0x14000fc4e  js      loc_14000FED4
0x14000fc54  mov     rax, [rsp+0F8h+var_80]
0x14000fc59  cmp     byte ptr [rax+31h], 0
0x14000fc5d  jnz     loc_14000FE2E
0x14000fc63  mov     ebx, r12d
0x14000fc66  mov     [rsp+0F8h+var_C8], ebx
0x14000fc6a  mov     r13, [rsp+0F8h+Data]
0x14000fc72  xor     r12b, r12b
0x14000fc75  call    cs:__imp_FsRtlIsMobileOS
0x14000fc7c  nop     dword ptr [rax+rax+00h]
0x14000fc81  test    al, al
0x14000fc83  jnz     loc_14000FD20
0x14000fc89  lea     eax, [r14-1]
0x14000fc8d  cmp     eax, 1
0x14000fc90  jbe     loc_14000FE16
0x14000fc96  test    rsi, rsi
0x14000fc99  jnz     short loc_14000FCF0
0x14000fc9b  xor     r12d, r12d
0x14000fc9e  mov     rdi, [rsp+0F8h+Entry]
0x14000fca3  mov     rax, [rsp+0F8h+arg_10]
0x14000fcab  mov     [rax], rdi
0x14000fcae  mov     r14d, [rsp+0F8h+arg_18]
0x14000fcb6  jmp     loc_1400100D9
0x14000fcbb  mov     r8, [rdi+20h]
0x14000fcbf  movzx   edx, word ptr [r8+58h]
0x14000fcc4  cmp     edx, 2
0x14000fcc7  jbe     loc_14000FA39
0x14000fccd  mov     ecx, edx
0x14000fccf  shr     rcx, 1
0x14000fcd2  mov     rax, [r8+60h]
0x14000fcd6  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14000fcdc  jnz     loc_14000FA39
0x14000fce2  sub     dx, 2
0x14000fce6  mov     [r8+58h], dx
0x14000fceb  jmp     loc_14000FA39
0x14000fcf0  mov     rcx, rsi; P
0x14000fcf3  call    FCpFreeChamberId
0x14000fcf8  xor     r12d, r12d
0x14000fcfb  mov     esi, r12d
0x14000fcfe  mov     [rsp+0F8h+var_A8], r12
0x14000fd03  mov     rdi, [rsp+0F8h+Entry]
0x14000fd08  mov     rax, [rsp+0F8h+arg_10]
0x14000fd10  mov     [rax], rdi
0x14000fd13  mov     r14d, [rsp+0F8h+arg_18]
0x14000fd1b  jmp     loc_1400100D9
0x14000fd20  test    rsi, rsi
0x14000fd23  jz      loc_14000FC9B
0x14000fd29  lea     rcx, gPre2PostCreateContextList; Lookaside
0x14000fd30  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000fd37  nop     dword ptr [rax+rax+00h]
0x14000fd3c  mov     rdi, rax
0x14000fd3f  mov     [rsp+0F8h+Entry], rax
0x14000fd44  test    rax, rax
0x14000fd47  jnz     loc_1400100C6
0x14000fd4d  mov     ebx, 0C000009Ah
0x14000fd52  mov     [rsp+0F8h+var_C8], ebx
0x14000fd56  movzx   eax, byte ptr cs:Microsoft_Windows_FileCryptEnableBits
0x14000fd5d  test    r15b, al
0x14000fd60  jz      short loc_14000FD71
0x14000fd62  mov     r9d, ebx
0x14000fd65  lea     rdx, AllocationFailure
0x14000fd6c  call    McTemplateK0d_EtwWriteTransfer
0x14000fd71  mov     r14d, [rsp+0F8h+arg_18]
0x14000fd79  xor     r12d, r12d
0x14000fd7c  jmp     loc_1400100D9
0x14000fd81  mov     [rsp+0F8h+var_70], r12
0x14000fd89  mov     rsi, r12
0x14000fd8c  mov     [rsp+0F8h+var_A8], r12
0x14000fd91  cmp     [rsp+0F8h+String2.Length], 0
0x14000fd97  jz      loc_14000FF70
0x14000fd9d  lea     r9, [rsp+0F8h+var_B8]
0x14000fda2  lea     r8, [rsp+0F8h+var_A8]
0x14000fda7  lea     rdx, [rsp+0F8h+P]
0x14000fdac  lea     rcx, [rsp+0F8h+String2]
0x14000fdb1  call    StSecGetSecurityDescriptor
0x14000fdb6  mov     ebx, eax
0x14000fdb8  mov     rsi, [rsp+0F8h+var_A8]
0x14000fdbd  test    eax, eax
0x14000fdbf  js      loc_14000FE98
0x14000fdc5  test    rsi, rsi
0x14000fdc8  jnz     loc_14000FE98
0x14000fdce  mov     eax, cs:gFCFlags
0x14000fdd4  test    al, 4
0x14000fdd6  jnz     loc_14000FF78
0x14000fddc  test    al, 2
0x14000fdde  jnz     loc_14000FF95
0x14000fde4  mov     r14d, [rsp+0F8h+var_B8]
0x14000fde9  jmp     loc_14000FC43
0x14000fdee  mov     rax, [rsp+0F8h+var_80]
0x14000fdf3  cmp     byte ptr [rax+31h], 0
0x14000fdf7  jnz     loc_14000FEFE
0x14000fdfd  mov     ebx, r12d
0x14000fe00  mov     [rsp+0F8h+var_C8], ebx
0x14000fe04  mov     r14d, [rsp+0F8h+arg_18]
0x14000fe0c  mov     rdi, [rsp+0F8h+Entry]
0x14000fe11  jmp     loc_1400100D9
0x14000fe16  mov     rax, [r13+10h]
0x14000fe1a  mov     rdx, [rax+18h]
0x14000fe1e  mov     rax, [rdx+8]
0x14000fe22  or      dword ptr [rax+0Ch], 40000h
0x14000fe29  jmp     loc_14000FC96
0x14000fe2e  lea     r8, [rsp+0F8h+var_B8]
0x14000fe33  mov     rdx, [rsp+0F8h+P]
0x14000fe38  mov     r13, [rsp+0F8h+Data]
0x14000fe40  mov     rcx, r13
0x14000fe43  call    FCpAccessCheck
0x14000fe48  mov     ebx, eax
0x14000fe4a  mov     [rsp+0F8h+var_C8], eax
0x14000fe4e  test    eax, eax
0x14000fe50  jns     loc_14000FC72
0x14000fe56  cmp     eax, 0C0000022h
0x14000fe5b  jnz     loc_14001009A
0x14000fe61  mov     r8, [r13+10h]
0x14000fe65  mov     edx, [r8+20h]
0x14000fe69  mov     ecx, edx
0x14000fe6b  shr     ecx, 18h
0x14000fe6e  lea     eax, [rcx-3]
0x14000fe71  test    eax, 0FFFFFFFDh
0x14000fe76  jz      loc_14001004F
0x14000fe7c  cmp     ecx, 2
0x14000fe7f  jnz     loc_14001009A
0x14000fe85  test    r15b, dl
0x14000fe88  jz      loc_14001009A
0x14000fe8e  mov     ebx, 0C0000035h
0x14000fe93  jmp     loc_14000FE00
0x14000fe98  test    ebx, ebx
0x14000fe9a  jns     loc_14000FDE4
0x14000fea0  movzx   eax, byte ptr cs:Microsoft_Windows_FileCryptEnableBits
0x14000fea7  test    r15b, al
0x14000feaa  jz      loc_14000FDE4
0x14000feb0  mov     r9d, ebx
0x14000feb3  lea     rdx, GetSecurityDescriptorFailure
0x14000feba  call    McTemplateK0d_EtwWriteTransfer
0x14000febf  jmp     loc_14000FDE4
0x14000fec4  mov     r14d, 1
0x14000feca  mov     rdi, [rsp+0F8h+Entry]
0x14000fecf  jmp     loc_1400100D9
0x14000fed4  movzx   eax, byte ptr cs:Microsoft_Windows_FileCryptEnableBits
0x14000fedb  test    r15b, al
0x14000fede  jnz     loc_140010033
0x14000fee4  mov     r13, [rsp+0F8h+Data]
0x14000feec  mov     r14d, [rsp+0F8h+arg_18]
0x14000fef4  mov     rdi, [rsp+0F8h+Entry]
0x14000fef9  jmp     loc_1400100D9
0x14000fefe  movzx   eax, byte ptr cs:Microsoft_Windows_FileCryptEnableBits
0x14000ff05  test    al, 2
0x14000ff07  jz      loc_14000FE04
  ... truncated ...
```
