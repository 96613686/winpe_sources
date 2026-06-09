# HsmFltPostSetRenameInformation

- ea: `0x14005599c`
- end: `0x140055e87`
- name: `HsmFltPostSetRenameInformation`
- size: `1259`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x140054910`

## callees

- `0x140003c50`
- `0x140007ddc`
- `0x14000ac28`
- `0x14001e140`
- `0x14001e280`
- `0x140054a04`
- `0x140055950`
- `0x14005596c`
- `0x14005599c`
- `0x14005c8c0`
- `0x14006def0`
- `0x1400779f4`
- `0x14007f1a0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140055e3b`
- `ntoskrnl!ObfDereferenceObject` at `0x140055e3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055abc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055c1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055c3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055abc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055c1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055c3b`
- `ntoskrnl!ExAllocatePool2` at `0x140055ae4`
- `ntoskrnl!ExAllocatePool2` at `0x140055ae4`
- `FLTMGR!FltSetInformationFile` at `0x140055c96`
- `FLTMGR!FltSetInformationFile` at `0x140055c96`
- `FLTMGR!FltClose` at `0x140055e4f`
- `FLTMGR!FltClose` at `0x140055e4f`
- `FLTMGR!FltQueryInformationFile` at `0x140055bbe`
- `FLTMGR!FltQueryInformationFile` at `0x140055bbe`
- `FLTMGR!FltReleaseContext` at `0x140055c4c`
- `FLTMGR!FltReleaseContext` at `0x140055e68`
- `FLTMGR!FltReleaseContext` at `0x140055c4c`
- `FLTMGR!FltReleaseContext` at `0x140055e68`

## pseudocode

```c
__int64 __fastcall HsmFltPostSetRenameInformation(struct _FLT_CALLBACK_DATA *a1, _QWORD *a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  __int64 v5; // rdi
  ULONG Options; // ecx
  struct _FLT_INSTANCE *TargetInstance; // r12
  struct _FILE_OBJECT *TargetFileObject; // rdx
  struct _FILE_OBJECT *v9; // rdx
  void *v10; // rcx
  _QWORD *v11; // rbx
  _QWORD *v12; // r15
  void *InstanceContext; // r14
  __int64 v15; // rax
  unsigned int v16; // esi
  __int64 Pool2; // rax
  __int64 v18; // rcx
  size_t v19; // r8
  const void *v20; // rdx
  unsigned int v21; // eax
  void *v22; // rcx
  __int64 v23; // rsi
  void *v24; // rcx
  void *v25; // rcx
  int v26; // eax
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // r9d
  char v30; // [rsp+50h] [rbp-59h]
  ULONG v31; // [rsp+54h] [rbp-55h]
  int v32; // [rsp+54h] [rbp-55h]
  int v33; // [rsp+54h] [rbp-55h]
  __int64 v34; // [rsp+58h] [rbp-51h]
  struct _FILE_OBJECT *FileObject; // [rsp+60h] [rbp-49h]
  __int128 v36; // [rsp+78h] [rbp-31h] BYREF
  __int64 v37; // [rsp+88h] [rbp-21h]
  struct _FLT_INSTANCE *v38; // [rsp+90h] [rbp-19h]
  _DWORD *EaBuffer; // [rsp+98h] [rbp-11h]
  __int128 FileInformation; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v41; // [rsp+B0h] [rbp+7h]
  __int64 v42; // [rsp+C0h] [rbp+17h]

  Iopb = a1->Iopb;
  v5 = 0;
  Options = Iopb->Parameters.Create.Options;
  TargetInstance = Iopb->TargetInstance;
  TargetFileObject = Iopb->TargetFileObject;
  EaBuffer = Iopb->Parameters.Create.EaBuffer;
  v31 = Options;
  v42 = 0;
  v37 = 0;
  v38 = TargetInstance;
  FileObject = TargetFileObject;
  FileInformation = 0;
  v41 = 0;
  v36 = 0;
  if ( (unsigned __int8)HsmpIsInstanceContext(a2) )
  {
    v11 = 0;
    v12 = 0;
    HsmpReleaseFileNameLock(v10);
    v9 = FileObject;
    InstanceContext = a2;
LABEL_3:
    v34 = 0;
    goto LABEL_4;
  }
  v12 = (_QWORD *)a2[1];
  InstanceContext = 0;
  v11 = a2;
  if ( !v12 )
    goto LABEL_3;
  v15 = v12[2];
  InstanceContext = *(void **)(v15 + 16);
  v34 = *(_QWORD *)(v15 + 32);
LABEL_4:
  if ( a1->IoStatus.Status < 0 )
  {
    if ( !v11 )
      return 0;
    if ( *((_BYTE *)v11 + 46) )
    {
      *(_QWORD *)&v41 = MEMORY[0xFFFFF78000000014];
      FltSetInformationFile(TargetInstance, v9, &FileInformation, 0x28u, FileBasicInformation);
    }
    goto LABEL_26;
  }
  if ( (unsigned __int8)HsmpCldIsCallbackRequested(5, v12, a1) )
  {
    v16 = *((unsigned __int16 *)v11 + 13) + 24;
    Pool2 = ExAllocatePool2(258, v16, 1666085704);
    v5 = Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)Pool2 = 1666085704;
      *(_DWORD *)(Pool2 + 8) = 24;
      *(_DWORD *)(Pool2 + 12) = 0x10000;
      *(_QWORD *)(Pool2 + 16) = 0;
      if ( v16 >= 0x18 )
      {
        if ( *(_WORD *)(Pool2 + 14) )
        {
          v18 = *(unsigned int *)(Pool2 + 8);
          v19 = *((unsigned __int16 *)v11 + 13);
          if ( v19 + ((v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) <= v16 )
          {
            v20 = (const void *)v11[4];
            v21 = (v18 + 3) & 0xFFFFFFFC;
            *(_DWORD *)(v5 + 8) = v21;
            *(_WORD *)(v5 + 16) = 17;
            *(_WORD *)(v5 + 18) = v19;
            *(_DWORD *)(v5 + 20) = v21;
            if ( v20 )
            {
              v22 = (void *)(v5 + v21);
              if ( v22 != v20 )
                memmove(v22, v20, v19);
            }
            *(_DWORD *)(v5 + 8) += *(unsigned __int16 *)(v5 + 18);
          }
        }
      }
    }
    HsmpCldNotifyPostOperation(5u, a1, 0, 0, v5);
    TargetInstance = v38;
  }
  if ( !v11 )
    goto LABEL_11;
  if ( *((_BYTE *)v11 + 45) && (v31 != 65 || (*EaBuffer & 4) == 0) )
  {
    v23 = (unsigned int)FltQueryInformationFile(
                          TargetInstance,
                          FileObject,
                          &FileInformation,
                          0x28u,
                          FileBasicInformation,
                          0);
    HsmDbgBreakOnStatus(v23);
    if ( (int)v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_qqiqd(
          WPP_GLOBAL_Control->AttachedDevice,
          36,
          WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
          a1,
          InstanceContext,
          v34,
          v12,
          v23);
      }
    }
    else if ( ((*((_DWORD *)v11 + 10) ^ (unsigned int)v42) & 0x180000) == 0 )
    {
      goto LABEL_26;
    }
    v30 = 0;
    if ( !InstanceContext )
    {
      InstanceContext = (void *)HsmpGetInstanceContext(TargetInstance);
      v30 = 1;
    }
    v32 = HsmpOpenFileByPath(InstanceContext, FileObject, 385);
    HsmDbgBreakOnStatus((unsigned int)v32);
    v26 = v32;
    if ( v32 >= 0 )
    {
      v29 = *((_DWORD *)v11 + 10);
      LODWORD(v37) = 0;
      *(_QWORD *)&v36 = 0;
      *((_QWORD *)&v36 + 1) = __PAIR64__(v42, v29);
      v33 = HsmpRecurseDirectory(
              (__int64)InstanceContext,
              0,
              0,
              v29,
              0,
              0,
              (__int64 (__fastcall *)(__int64, struct _FILE_OBJECT *, _QWORD, __int64))HsmiInfoUpdatePlaceholderStatesOnRenamePre,
              (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))HsmiInfoUpdatePlaceholderStatesOnRenamePost,
              (__int64)&v36);
      HsmDbgBreakOnStatus((unsigned int)v33);
      v26 = v33;
      if ( v33 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          v28 = 38;
          goto LABEL_55;
        }
      }
    }
    else
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v28 = 37;
LABEL_55:
        WPP_SF_qqiqd(
          v27->AttachedDevice,
          v28,
          WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
          a1,
          InstanceContext,
          v34,
          v12,
          v26);
      }
    }
    if ( v30 )
      FltReleaseContext(InstanceContext);
  }
LABEL_26:
  v24 = (void *)v11[2];
  if ( v24 )
    HsmpReleaseFileNameLock(v24);
  if ( *((_BYTE *)v11 + 44) )
    HsmpReleaseUserRequestRundownProtection((PFLT_CONTEXT)v11[1]);
  v25 = (void *)v11[4];
  if ( v25 )
    ExFreePoolWithTag(v25, 0x73557348u);
  if ( v11[1] )
    FltReleaseContext(v12);
  ExFreePoolWithTag(v11, 0x636F7348u);
LABEL_11:
  if ( v5 )
    ExFreePoolWithTag((PVOID)v5, 0x634E7348u);
  return 0;
}

```

## disassembly

```asm
0x14005599c  mov     [rsp-8+arg_10], rbx
0x1400559a1  push    rbp
0x1400559a2  push    rsi
0x1400559a3  push    rdi
0x1400559a4  push    r12
0x1400559a6  push    r13
0x1400559a8  push    r14
0x1400559aa  push    r15
0x1400559ac  lea     rbp, [rsp-27h]
0x1400559b1  sub     rsp, 0D0h
0x1400559b8  mov     rax, cs:__security_cookie
0x1400559bf  xor     rax, rsp
0x1400559c2  mov     [rbp+57h+var_38], rax
0x1400559c6  mov     rax, [rcx+10h]
0x1400559ca  xorps   xmm0, xmm0
0x1400559cd  mov     rsi, rdx
0x1400559d0  mov     [rbp+57h+FileHandle], 0
0x1400559d8  mov     r13, rcx
0x1400559db  xor     edi, edi
0x1400559dd  mov     ecx, [rax+20h]
0x1400559e0  mov     r12, [rax+10h]
0x1400559e4  mov     rdx, [rax+8]
0x1400559e8  mov     rax, [rax+38h]
0x1400559ec  mov     [rbp+57h+var_68], rax
0x1400559f0  xor     eax, eax
0x1400559f2  mov     [rbp+57h+var_AC], ecx
0x1400559f5  mov     rcx, rsi
0x1400559f8  mov     [rbp+57h+var_40], rax
0x1400559fc  mov     [rbp+57h+Object], rax
0x140055a00  mov     [rbp+57h+var_78], rax
0x140055a04  mov     [rbp+57h+var_70], r12
0x140055a08  mov     [rbp+57h+FileObject], rdx
0x140055a0c  movups  [rbp+57h+FileInformation], xmm0
0x140055a10  movups  [rbp+57h+var_50], xmm0
0x140055a14  movups  [rbp+57h+var_88], xmm0
0x140055a18  call    HsmpIsInstanceContext
0x140055a1d  test    al, al
0x140055a1f  jz      short loc_140055A6F
0x140055a21  xor     ebx, ebx
0x140055a23  xor     r15d, r15d
0x140055a26  call    HsmpReleaseFileNameLock
0x140055a2b  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140055a2f  mov     r14, rsi
0x140055a32  mov     [rbp+57h+var_A8], rdi
0x140055a36  cmp     [r13+18h], edi
0x140055a3a  jge     short loc_140055A90
0x140055a3c  test    rbx, rbx
0x140055a3f  jnz     loc_140055C6A
0x140055a45  xor     eax, eax
0x140055a47  mov     rcx, [rbp+57h+var_38]
0x140055a4b  xor     rcx, rsp; StackCookie
0x140055a4e  call    __security_check_cookie
0x140055a53  mov     rbx, [rsp+100h+arg_10]
0x140055a5b  add     rsp, 0D0h
0x140055a62  pop     r15
0x140055a64  pop     r14
0x140055a66  pop     r13
0x140055a68  pop     r12
0x140055a6a  pop     rdi
0x140055a6b  pop     rsi
0x140055a6c  pop     rbp
0x140055a6d  retn
0x140055a6f  mov     r15, [rsi+8]
0x140055a73  xor     r14d, r14d
0x140055a76  mov     rbx, rsi
0x140055a79  test    r15, r15
0x140055a7c  jz      short loc_140055A32
0x140055a7e  mov     rax, [r15+10h]
0x140055a82  mov     r14, [rax+10h]
0x140055a86  mov     rax, [rax+20h]
0x140055a8a  mov     [rbp+57h+var_A8], rax
0x140055a8e  jmp     short loc_140055A36
0x140055a90  xor     r9d, r9d
0x140055a93  mov     r8, r13
0x140055a96  mov     rdx, r15
0x140055a99  lea     ecx, [r9+5]
0x140055a9d  call    HsmpCldIsCallbackRequested
0x140055aa2  test    al, al
0x140055aa4  jnz     short loc_140055ACD
0x140055aa6  test    rbx, rbx
0x140055aa9  jnz     loc_140055B8C
0x140055aaf  test    rdi, rdi
0x140055ab2  jz      short loc_140055A45
0x140055ab4  mov     edx, 634E7348h; Tag
0x140055ab9  mov     rcx, rdi; P
0x140055abc  call    cs:__imp_ExFreePoolWithTag
0x140055ac3  nop     dword ptr [rax+rax+00h]
0x140055ac8  jmp     loc_140055A45
0x140055acd  movzx   esi, word ptr [rbx+1Ah]
0x140055ad1  mov     r8d, 634E7348h
0x140055ad7  add     esi, 18h
0x140055ada  mov     ecx, 102h
0x140055adf  mov     edx, esi
0x140055ae1  mov     r12d, esi
0x140055ae4  call    cs:__imp_ExAllocatePool2
0x140055aeb  nop     dword ptr [rax+rax+00h]
0x140055af0  mov     rdi, rax
0x140055af3  test    rax, rax
0x140055af6  jz      short loc_140055B6C
0x140055af8  mov     qword ptr [rax], 634E7348h
0x140055aff  mov     dword ptr [rax+8], 18h
0x140055b06  mov     dword ptr [rax+0Ch], 10000h
0x140055b0d  xor     eax, eax
0x140055b0f  mov     [rdi+10h], rax
0x140055b13  cmp     esi, 18h
0x140055b16  jb      short loc_140055B6C
0x140055b18  cmp     ax, [rdi+0Eh]
0x140055b1c  jnb     short loc_140055B6C
0x140055b1e  mov     ecx, [rdi+8]
0x140055b21  movzx   r8d, word ptr [rbx+1Ah]; Size
0x140055b26  lea     rax, [rcx+3]
0x140055b2a  and     rax, 0FFFFFFFFFFFFFFFCh
0x140055b2e  add     rax, r8
0x140055b31  cmp     rax, r12
0x140055b34  ja      short loc_140055B6C
0x140055b36  mov     rdx, [rbx+20h]; Src
0x140055b3a  lea     eax, [rcx+3]
0x140055b3d  and     eax, 0FFFFFFFCh
0x140055b40  mov     [rdi+8], eax
0x140055b43  mov     word ptr [rdi+10h], 11h
0x140055b49  mov     [rdi+12h], r8w
0x140055b4e  mov     [rdi+14h], eax
0x140055b51  test    rdx, rdx
0x140055b54  jz      short loc_140055B65
0x140055b56  mov     ecx, eax
0x140055b58  add     rcx, rdi; void *
0x140055b5b  cmp     rcx, rdx
0x140055b5e  jz      short loc_140055B65
0x140055b60  call    memmove
0x140055b65  movzx   eax, word ptr [rdi+12h]
0x140055b69  add     [rdi+8], eax
0x140055b6c  xor     r9d, r9d
0x140055b6f  mov     qword ptr [rsp+100h+FileInformationClass], rdi
0x140055b74  xor     r8d, r8d
0x140055b77  mov     rdx, r13
0x140055b7a  lea     ecx, [r9+5]
0x140055b7e  call    HsmpCldNotifyPostOperation
0x140055b83  mov     r12, [rbp+57h+var_70]
0x140055b87  jmp     loc_140055AA6
0x140055b8c  cmp     byte ptr [rbx+2Dh], 0
0x140055b90  jz      short loc_140055BF3
0x140055b92  cmp     [rbp+57h+var_AC], 41h ; 'A'
0x140055b96  jz      loc_140055C5A
0x140055b9c  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140055ba0  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140055ba4  mov     [rsp+100h+LengthReturned], 0; LengthReturned
0x140055bad  mov     r9d, 28h ; '('; Length
0x140055bb3  mov     rcx, r12; Instance
0x140055bb6  mov     [rsp+100h+FileInformationClass], 4; FileInformationClass
0x140055bbe  call    cs:__imp_FltQueryInformationFile
0x140055bc5  nop     dword ptr [rax+rax+00h]
0x140055bca  mov     ecx, eax
0x140055bcc  mov     esi, eax
0x140055bce  call    HsmDbgBreakOnStatus
0x140055bd3  lea     rax, WPP_GLOBAL_Control
0x140055bda  test    esi, esi
0x140055bdc  js      loc_140055CA7
0x140055be2  mov     eax, dword ptr [rbp+57h+var_40]
0x140055be5  xor     eax, [rbx+28h]
0x140055be8  test    eax, 180000h
0x140055bed  jnz     loc_140055CF0
0x140055bf3  mov     rcx, [rbx+10h]; Context
0x140055bf7  test    rcx, rcx
0x140055bfa  jnz     short loc_140055C2F
0x140055bfc  cmp     byte ptr [rbx+2Ch], 0
0x140055c00  jnz     loc_140055E79
0x140055c06  mov     rcx, [rbx+20h]; P
0x140055c0a  test    rcx, rcx
0x140055c0d  jnz     short loc_140055C36
0x140055c0f  cmp     qword ptr [rbx+8], 0
0x140055c14  jnz     short loc_140055C49
0x140055c16  mov     edx, 636F7348h; Tag
0x140055c1b  mov     rcx, rbx; P
0x140055c1e  call    cs:__imp_ExFreePoolWithTag
0x140055c25  nop     dword ptr [rax+rax+00h]
0x140055c2a  jmp     loc_140055AAF
0x140055c2f  call    HsmpReleaseFileNameLock
0x140055c34  jmp     short loc_140055BFC
0x140055c36  mov     edx, 73557348h; Tag
0x140055c3b  call    cs:__imp_ExFreePoolWithTag
0x140055c42  nop     dword ptr [rax+rax+00h]
0x140055c47  jmp     short loc_140055C0F
0x140055c49  mov     rcx, r15; Context
0x140055c4c  call    cs:__imp_FltReleaseContext
0x140055c53  nop     dword ptr [rax+rax+00h]
0x140055c58  jmp     short loc_140055C16
0x140055c5a  mov     rax, [rbp+57h+var_68]
0x140055c5e  mov     eax, [rax]
0x140055c60  test    al, 4
0x140055c62  jz      loc_140055B9C
0x140055c68  jmp     short loc_140055BF3
0x140055c6a  cmp     [rbx+2Eh], dil
0x140055c6e  jz      short loc_140055BF3
0x140055c70  mov     rax, 0FFFFF78000000014h
0x140055c7a  mov     [rsp+100h+FileInformationClass], 4; FileInformationClass
0x140055c82  mov     r9d, 28h ; '('; Length
0x140055c88  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140055c8c  mov     rcx, r12; Instance
0x140055c8f  mov     rax, [rax]
0x140055c92  mov     qword ptr [rbp+57h+var_50], rax
0x140055c96  call    cs:__imp_FltSetInformationFile
0x140055c9d  nop     dword ptr [rax+rax+00h]
0x140055ca2  jmp     loc_140055BF3
0x140055ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140055cae  cmp     rcx, rax
0x140055cb1  jz      short loc_140055CF0
0x140055cb3  mov     edx, [rcx+2Ch]
0x140055cb6  test    dl, 1
0x140055cb9  jz      short loc_140055CF0
0x140055cbb  cmp     byte ptr [rcx+29h], 3
0x140055cbf  jb      short loc_140055CF0
0x140055cc1  mov     rax, [rbp+57h+var_A8]
0x140055cc5  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140055ccc  mov     rcx, [rcx+18h]
0x140055cd0  mov     edx, 24h ; '$'
0x140055cd5  mov     dword ptr [rsp+100h+var_C8], esi
0x140055cd9  mov     r9, r13
0x140055cdc  mov     [rsp+100h+var_D0], r15
0x140055ce1  mov     [rsp+100h+LengthReturned], rax
0x140055ce6  mov     qword ptr [rsp+100h+FileInformationClass], r14
0x140055ceb  call    WPP_SF_qqiqd
0x140055cf0  mov     [rbp+57h+var_B0], 0
0x140055cf4  test    r14, r14
0x140055cf7  jnz     short loc_140055D08
0x140055cf9  mov     rcx, r12
0x140055cfc  call    HsmpGetInstanceContext
0x140055d01  mov     r14, rax
0x140055d04  mov     [rbp+57h+var_B0], 1
0x140055d08  mov     rdx, [rbp+57h+FileObject]
0x140055d0c  lea     rax, [rbp+57h+Object]
0x140055d10  mov     [rsp+100h+var_C8], rax
0x140055d15  mov     r8d, 181h
0x140055d1b  lea     rax, [rbp+57h+FileHandle]
0x140055d1f  mov     rcx, r14
0x140055d22  mov     [rsp+100h+var_D0], rax
0x140055d27  mov     [rsp+100h+FileInformationClass], 200000h
0x140055d2f  call    HsmpOpenFileByPath
0x140055d34  mov     ecx, eax
0x140055d36  mov     [rbp+57h+var_AC], eax
0x140055d39  call    HsmDbgBreakOnStatus
0x140055d3e  mov     eax, [rbp+57h+var_AC]
0x140055d41  xor     ecx, ecx
0x140055d43  mov     r12, [rbp+57h+FileHandle]
0x140055d47  mov     rsi, [rbp+57h+Object]
0x140055d4b  test    eax, eax
0x140055d4d  jns     short loc_140055D86
0x140055d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d56  lea     rdx, WPP_GLOBAL_Control
0x140055d5d  cmp     rcx, rdx
0x140055d60  jz      loc_140055E33
0x140055d66  mov     edx, [rcx+2Ch]
0x140055d69  test    dl, 1
0x140055d6c  jz      loc_140055E33
0x140055d72  cmp     byte ptr [rcx+29h], 3
0x140055d76  jb      loc_140055E33
0x140055d7c  mov     edx, 25h ; '%'
0x140055d81  jmp     loc_140055E09
0x140055d86  mov     eax, dword ptr [rbp+57h+var_40]
0x140055d89  mov     r8, rsi
0x140055d8c  mov     r9d, [rbx+28h]
0x140055d90  mov     rdx, r12
0x140055d93  mov     dword ptr [rbp+57h+var_88+0Ch], eax
0x140055d96  lea     rax, [rbp+57h+var_88]
0x140055d9a  mov     [rsp+100h+var_C0], rax
0x140055d9f  lea     rax, HsmiInfoUpdatePlaceholderStatesOnRenamePost
0x140055da6  mov     [rsp+100h+var_C8], rax
0x140055dab  lea     rax, HsmiInfoUpdatePlaceholderStatesOnRenamePre
0x140055db2  mov     [rsp+100h+var_D0], rax
0x140055db7  mov     byte ptr [rsp+100h+LengthReturned], cl
0x140055dbb  mov     byte ptr [rsp+100h+FileInformationClass], cl
0x140055dbf  mov     dword ptr [rbp+57h+var_78], ecx
0x140055dc2  mov     rcx, r14
0x140055dc5  mov     qword ptr [rbp+57h+var_88], rsi
0x140055dc9  mov     dword ptr [rbp+57h+var_88+8], r9d
0x140055dcd  call    HsmpRecurseDirectory
0x140055dd2  mov     ecx, eax
0x140055dd4  mov     [rbp+57h+var_AC], eax
0x140055dd7  call    HsmDbgBreakOnStatus
0x140055ddc  mov     eax, [rbp+57h+var_AC]
0x140055ddf  test    eax, eax
0x140055de1  jns     short loc_140055E33
0x140055de3  mov     rcx, cs:WPP_GLOBAL_Control
0x140055dea  lea     rdx, WPP_GLOBAL_Control
0x140055df1  cmp     rcx, rdx
0x140055df4  jz      short loc_140055E33
0x140055df6  mov     edx, [rcx+2Ch]
0x140055df9  test    dl, 1
0x140055dfc  jz      short loc_140055E33
0x140055dfe  cmp     byte ptr [rcx+29h], 3
0x140055e02  jb      short loc_140055E33
0x140055e04  mov     edx, 26h ; '&'
0x140055e09  mov     rcx, [rcx+18h]
0x140055e0d  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140055e14  mov     dword ptr [rsp+100h+var_C8], eax
0x140055e18  mov     r9, r13
0x140055e1b  mov     rax, [rbp+57h+var_A8]
0x140055e1f  mov     [rsp+100h+var_D0], r15
0x140055e24  mov     [rsp+100h+LengthReturned], rax
0x140055e29  mov     qword ptr [rsp+100h+FileInformationClass], r14
0x140055e2e  call    WPP_SF_qqiqd
  ... truncated ...
```
