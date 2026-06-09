# HsmFltPostSetRenameInformation

- ea: `0x140055abc`
- end: `0x140055fa7`
- name: `HsmFltPostSetRenameInformation`
- size: `1259`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x140054a30`

## callees

- `0x140003c50`
- `0x140007ddc`
- `0x14000ac28`
- `0x14001e1c0`
- `0x14001e300`
- `0x140054b24`
- `0x140055a70`
- `0x140055a8c`
- `0x140055abc`
- `0x14005c9e0`
- `0x14006e010`
- `0x140077b34`
- `0x14007f338`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140055f5b`
- `ntoskrnl!ObfDereferenceObject` at `0x140055f5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055bdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055d3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055d5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055bdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055d3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055d5b`
- `ntoskrnl!ExAllocatePool2` at `0x140055c04`
- `ntoskrnl!ExAllocatePool2` at `0x140055c04`
- `FLTMGR!FltSetInformationFile` at `0x140055db6`
- `FLTMGR!FltSetInformationFile` at `0x140055db6`
- `FLTMGR!FltClose` at `0x140055f6f`
- `FLTMGR!FltClose` at `0x140055f6f`
- `FLTMGR!FltQueryInformationFile` at `0x140055cde`
- `FLTMGR!FltQueryInformationFile` at `0x140055cde`
- `FLTMGR!FltReleaseContext` at `0x140055d6c`
- `FLTMGR!FltReleaseContext` at `0x140055f88`
- `FLTMGR!FltReleaseContext` at `0x140055d6c`
- `FLTMGR!FltReleaseContext` at `0x140055f88`

## pseudocode

```c
__int64 __fastcall HsmFltPostSetRenameInformation(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  __int64 v5; // rdi
  int v6; // ecx
  struct _FLT_INSTANCE *v7; // r12
  struct _FILE_OBJECT *v8; // rdx
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
  NTSTATUS v23; // esi
  void *v24; // rcx
  void *v25; // rcx
  int v26; // eax
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // r9d
  char v30; // [rsp+50h] [rbp-59h]
  int v31; // [rsp+54h] [rbp-55h]
  int v32; // [rsp+54h] [rbp-55h]
  int v33; // [rsp+54h] [rbp-55h]
  __int64 v34; // [rsp+58h] [rbp-51h]
  struct _FILE_OBJECT *FileObject; // [rsp+60h] [rbp-49h]
  __int128 v36; // [rsp+78h] [rbp-31h] BYREF
  __int64 v37; // [rsp+88h] [rbp-21h]
  struct _FLT_INSTANCE *v38; // [rsp+90h] [rbp-19h]
  _DWORD *v39; // [rsp+98h] [rbp-11h]
  __int128 FileInformation; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v41; // [rsp+B0h] [rbp+7h]
  __int64 v42; // [rsp+C0h] [rbp+17h]

  v2 = *(_QWORD *)(a1 + 16);
  v5 = 0;
  v6 = *(_DWORD *)(v2 + 32);
  v7 = *(struct _FLT_INSTANCE **)(v2 + 16);
  v8 = *(struct _FILE_OBJECT **)(v2 + 8);
  v39 = *(_DWORD **)(v2 + 56);
  v31 = v6;
  v42 = 0;
  v37 = 0;
  v38 = v7;
  FileObject = v8;
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
  if ( *(int *)(a1 + 24) < 0 )
  {
    if ( !v11 )
      return 0;
    if ( *((_BYTE *)v11 + 46) )
    {
      *(_QWORD *)&v41 = MEMORY[0xFFFFF78000000014];
      FltSetInformationFile(v7, v9, &FileInformation, 0x28u, FileBasicInformation);
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
    HsmpCldNotifyPostOperation(5, a1, 0, 0, v5);
    v7 = v38;
  }
  if ( !v11 )
    goto LABEL_11;
  if ( *((_BYTE *)v11 + 45) && (v31 != 65 || (*v39 & 4) == 0) )
  {
    v23 = FltQueryInformationFile(v7, FileObject, &FileInformation, 0x28u, FileBasicInformation, 0);
    HsmDbgBreakOnStatus(v23);
    if ( v23 < 0 )
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
      InstanceContext = (void *)HsmpGetInstanceContext(v7);
      v30 = 1;
    }
    v32 = HsmpOpenFileByPath(InstanceContext, FileObject, 385);
    HsmDbgBreakOnStatus(v32);
    v26 = v32;
    if ( v32 >= 0 )
    {
      v29 = *((_DWORD *)v11 + 10);
      LODWORD(v37) = 0;
      *(_QWORD *)&v36 = 0;
      *((_QWORD *)&v36 + 1) = __PAIR64__(v42, v29);
      v33 = HsmpRecurseDirectory(
              (_DWORD)InstanceContext,
              0,
              0,
              v29,
              0,
              0,
              (__int64)HsmiInfoUpdatePlaceholderStatesOnRenamePre,
              (__int64)HsmiInfoUpdatePlaceholderStatesOnRenamePost,
              (__int64)&v36);
      HsmDbgBreakOnStatus(v33);
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
0x140055abc  mov     [rsp-8+arg_10], rbx
0x140055ac1  push    rbp
0x140055ac2  push    rsi
0x140055ac3  push    rdi
0x140055ac4  push    r12
0x140055ac6  push    r13
0x140055ac8  push    r14
0x140055aca  push    r15
0x140055acc  lea     rbp, [rsp-27h]
0x140055ad1  sub     rsp, 0D0h
0x140055ad8  mov     rax, cs:__security_cookie
0x140055adf  xor     rax, rsp
0x140055ae2  mov     [rbp+57h+var_38], rax
0x140055ae6  mov     rax, [rcx+10h]
0x140055aea  xorps   xmm0, xmm0
0x140055aed  mov     rsi, rdx
0x140055af0  mov     [rbp+57h+FileHandle], 0
0x140055af8  mov     r13, rcx
0x140055afb  xor     edi, edi
0x140055afd  mov     ecx, [rax+20h]
0x140055b00  mov     r12, [rax+10h]
0x140055b04  mov     rdx, [rax+8]
0x140055b08  mov     rax, [rax+38h]
0x140055b0c  mov     [rbp+57h+var_68], rax
0x140055b10  xor     eax, eax
0x140055b12  mov     [rbp+57h+var_AC], ecx
0x140055b15  mov     rcx, rsi
0x140055b18  mov     [rbp+57h+var_40], rax
0x140055b1c  mov     [rbp+57h+Object], rax
0x140055b20  mov     [rbp+57h+var_78], rax
0x140055b24  mov     [rbp+57h+var_70], r12
0x140055b28  mov     [rbp+57h+FileObject], rdx
0x140055b2c  movups  [rbp+57h+FileInformation], xmm0
0x140055b30  movups  [rbp+57h+var_50], xmm0
0x140055b34  movups  [rbp+57h+var_88], xmm0
0x140055b38  call    HsmpIsInstanceContext
0x140055b3d  test    al, al
0x140055b3f  jz      short loc_140055B8F
0x140055b41  xor     ebx, ebx
0x140055b43  xor     r15d, r15d
0x140055b46  call    HsmpReleaseFileNameLock
0x140055b4b  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140055b4f  mov     r14, rsi
0x140055b52  mov     [rbp+57h+var_A8], rdi
0x140055b56  cmp     [r13+18h], edi
0x140055b5a  jge     short loc_140055BB0
0x140055b5c  test    rbx, rbx
0x140055b5f  jnz     loc_140055D8A
0x140055b65  xor     eax, eax
0x140055b67  mov     rcx, [rbp+57h+var_38]
0x140055b6b  xor     rcx, rsp; StackCookie
0x140055b6e  call    __security_check_cookie
0x140055b73  mov     rbx, [rsp+100h+arg_10]
0x140055b7b  add     rsp, 0D0h
0x140055b82  pop     r15
0x140055b84  pop     r14
0x140055b86  pop     r13
0x140055b88  pop     r12
0x140055b8a  pop     rdi
0x140055b8b  pop     rsi
0x140055b8c  pop     rbp
0x140055b8d  retn
0x140055b8f  mov     r15, [rsi+8]
0x140055b93  xor     r14d, r14d
0x140055b96  mov     rbx, rsi
0x140055b99  test    r15, r15
0x140055b9c  jz      short loc_140055B52
0x140055b9e  mov     rax, [r15+10h]
0x140055ba2  mov     r14, [rax+10h]
0x140055ba6  mov     rax, [rax+20h]
0x140055baa  mov     [rbp+57h+var_A8], rax
0x140055bae  jmp     short loc_140055B56
0x140055bb0  xor     r9d, r9d
0x140055bb3  mov     r8, r13
0x140055bb6  mov     rdx, r15
0x140055bb9  lea     ecx, [r9+5]
0x140055bbd  call    HsmpCldIsCallbackRequested
0x140055bc2  test    al, al
0x140055bc4  jnz     short loc_140055BED
0x140055bc6  test    rbx, rbx
0x140055bc9  jnz     loc_140055CAC
0x140055bcf  test    rdi, rdi
0x140055bd2  jz      short loc_140055B65
0x140055bd4  mov     edx, 634E7348h; Tag
0x140055bd9  mov     rcx, rdi; P
0x140055bdc  call    cs:__imp_ExFreePoolWithTag
0x140055be3  nop     dword ptr [rax+rax+00h]
0x140055be8  jmp     loc_140055B65
0x140055bed  movzx   esi, word ptr [rbx+1Ah]
0x140055bf1  mov     r8d, 634E7348h
0x140055bf7  add     esi, 18h
0x140055bfa  mov     ecx, 102h
0x140055bff  mov     edx, esi
0x140055c01  mov     r12d, esi
0x140055c04  call    cs:__imp_ExAllocatePool2
0x140055c0b  nop     dword ptr [rax+rax+00h]
0x140055c10  mov     rdi, rax
0x140055c13  test    rax, rax
0x140055c16  jz      short loc_140055C8C
0x140055c18  mov     qword ptr [rax], 634E7348h
0x140055c1f  mov     dword ptr [rax+8], 18h
0x140055c26  mov     dword ptr [rax+0Ch], 10000h
0x140055c2d  xor     eax, eax
0x140055c2f  mov     [rdi+10h], rax
0x140055c33  cmp     esi, 18h
0x140055c36  jb      short loc_140055C8C
0x140055c38  cmp     ax, [rdi+0Eh]
0x140055c3c  jnb     short loc_140055C8C
0x140055c3e  mov     ecx, [rdi+8]
0x140055c41  movzx   r8d, word ptr [rbx+1Ah]; Size
0x140055c46  lea     rax, [rcx+3]
0x140055c4a  and     rax, 0FFFFFFFFFFFFFFFCh
0x140055c4e  add     rax, r8
0x140055c51  cmp     rax, r12
0x140055c54  ja      short loc_140055C8C
0x140055c56  mov     rdx, [rbx+20h]; Src
0x140055c5a  lea     eax, [rcx+3]
0x140055c5d  and     eax, 0FFFFFFFCh
0x140055c60  mov     [rdi+8], eax
0x140055c63  mov     word ptr [rdi+10h], 11h
0x140055c69  mov     [rdi+12h], r8w
0x140055c6e  mov     [rdi+14h], eax
0x140055c71  test    rdx, rdx
0x140055c74  jz      short loc_140055C85
0x140055c76  mov     ecx, eax
0x140055c78  add     rcx, rdi; void *
0x140055c7b  cmp     rcx, rdx
0x140055c7e  jz      short loc_140055C85
0x140055c80  call    memmove
0x140055c85  movzx   eax, word ptr [rdi+12h]
0x140055c89  add     [rdi+8], eax
0x140055c8c  xor     r9d, r9d
0x140055c8f  mov     qword ptr [rsp+100h+FileInformationClass], rdi
0x140055c94  xor     r8d, r8d
0x140055c97  mov     rdx, r13
0x140055c9a  lea     ecx, [r9+5]
0x140055c9e  call    HsmpCldNotifyPostOperation
0x140055ca3  mov     r12, [rbp+57h+var_70]
0x140055ca7  jmp     loc_140055BC6
0x140055cac  cmp     byte ptr [rbx+2Dh], 0
0x140055cb0  jz      short loc_140055D13
0x140055cb2  cmp     [rbp+57h+var_AC], 41h ; 'A'
0x140055cb6  jz      loc_140055D7A
0x140055cbc  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140055cc0  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140055cc4  mov     [rsp+100h+LengthReturned], 0; LengthReturned
0x140055ccd  mov     r9d, 28h ; '('; Length
0x140055cd3  mov     rcx, r12; Instance
0x140055cd6  mov     [rsp+100h+FileInformationClass], 4; FileInformationClass
0x140055cde  call    cs:__imp_FltQueryInformationFile
0x140055ce5  nop     dword ptr [rax+rax+00h]
0x140055cea  mov     ecx, eax
0x140055cec  mov     esi, eax
0x140055cee  call    HsmDbgBreakOnStatus
0x140055cf3  lea     rax, WPP_GLOBAL_Control
0x140055cfa  test    esi, esi
0x140055cfc  js      loc_140055DC7
0x140055d02  mov     eax, dword ptr [rbp+57h+var_40]
0x140055d05  xor     eax, [rbx+28h]
0x140055d08  test    eax, 180000h
0x140055d0d  jnz     loc_140055E10
0x140055d13  mov     rcx, [rbx+10h]; Context
0x140055d17  test    rcx, rcx
0x140055d1a  jnz     short loc_140055D4F
0x140055d1c  cmp     byte ptr [rbx+2Ch], 0
0x140055d20  jnz     loc_140055F99
0x140055d26  mov     rcx, [rbx+20h]; P
0x140055d2a  test    rcx, rcx
0x140055d2d  jnz     short loc_140055D56
0x140055d2f  cmp     qword ptr [rbx+8], 0
0x140055d34  jnz     short loc_140055D69
0x140055d36  mov     edx, 636F7348h; Tag
0x140055d3b  mov     rcx, rbx; P
0x140055d3e  call    cs:__imp_ExFreePoolWithTag
0x140055d45  nop     dword ptr [rax+rax+00h]
0x140055d4a  jmp     loc_140055BCF
0x140055d4f  call    HsmpReleaseFileNameLock
0x140055d54  jmp     short loc_140055D1C
0x140055d56  mov     edx, 73557348h; Tag
0x140055d5b  call    cs:__imp_ExFreePoolWithTag
0x140055d62  nop     dword ptr [rax+rax+00h]
0x140055d67  jmp     short loc_140055D2F
0x140055d69  mov     rcx, r15; Context
0x140055d6c  call    cs:__imp_FltReleaseContext
0x140055d73  nop     dword ptr [rax+rax+00h]
0x140055d78  jmp     short loc_140055D36
0x140055d7a  mov     rax, [rbp+57h+var_68]
0x140055d7e  mov     eax, [rax]
0x140055d80  test    al, 4
0x140055d82  jz      loc_140055CBC
0x140055d88  jmp     short loc_140055D13
0x140055d8a  cmp     [rbx+2Eh], dil
0x140055d8e  jz      short loc_140055D13
0x140055d90  mov     rax, 0FFFFF78000000014h
0x140055d9a  mov     [rsp+100h+FileInformationClass], 4; FileInformationClass
0x140055da2  mov     r9d, 28h ; '('; Length
0x140055da8  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140055dac  mov     rcx, r12; Instance
0x140055daf  mov     rax, [rax]
0x140055db2  mov     qword ptr [rbp+57h+var_50], rax
0x140055db6  call    cs:__imp_FltSetInformationFile
0x140055dbd  nop     dword ptr [rax+rax+00h]
0x140055dc2  jmp     loc_140055D13
0x140055dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140055dce  cmp     rcx, rax
0x140055dd1  jz      short loc_140055E10
0x140055dd3  mov     edx, [rcx+2Ch]
0x140055dd6  test    dl, 1
0x140055dd9  jz      short loc_140055E10
0x140055ddb  cmp     byte ptr [rcx+29h], 3
0x140055ddf  jb      short loc_140055E10
0x140055de1  mov     rax, [rbp+57h+var_A8]
0x140055de5  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140055dec  mov     rcx, [rcx+18h]
0x140055df0  mov     edx, 24h ; '$'
0x140055df5  mov     dword ptr [rsp+100h+var_C8], esi
0x140055df9  mov     r9, r13
0x140055dfc  mov     [rsp+100h+var_D0], r15
0x140055e01  mov     [rsp+100h+LengthReturned], rax
0x140055e06  mov     qword ptr [rsp+100h+FileInformationClass], r14
0x140055e0b  call    WPP_SF_qqiqd
0x140055e10  mov     [rbp+57h+var_B0], 0
0x140055e14  test    r14, r14
0x140055e17  jnz     short loc_140055E28
0x140055e19  mov     rcx, r12
0x140055e1c  call    HsmpGetInstanceContext
0x140055e21  mov     r14, rax
0x140055e24  mov     [rbp+57h+var_B0], 1
0x140055e28  mov     rdx, [rbp+57h+FileObject]
0x140055e2c  lea     rax, [rbp+57h+Object]
0x140055e30  mov     [rsp+100h+var_C8], rax
0x140055e35  mov     r8d, 181h
0x140055e3b  lea     rax, [rbp+57h+FileHandle]
0x140055e3f  mov     rcx, r14
0x140055e42  mov     [rsp+100h+var_D0], rax
0x140055e47  mov     [rsp+100h+FileInformationClass], 200000h
0x140055e4f  call    HsmpOpenFileByPath
0x140055e54  mov     ecx, eax
0x140055e56  mov     [rbp+57h+var_AC], eax
0x140055e59  call    HsmDbgBreakOnStatus
0x140055e5e  mov     eax, [rbp+57h+var_AC]
0x140055e61  xor     ecx, ecx
0x140055e63  mov     r12, [rbp+57h+FileHandle]
0x140055e67  mov     rsi, [rbp+57h+Object]
0x140055e6b  test    eax, eax
0x140055e6d  jns     short loc_140055EA6
0x140055e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e76  lea     rdx, WPP_GLOBAL_Control
0x140055e7d  cmp     rcx, rdx
0x140055e80  jz      loc_140055F53
0x140055e86  mov     edx, [rcx+2Ch]
0x140055e89  test    dl, 1
0x140055e8c  jz      loc_140055F53
0x140055e92  cmp     byte ptr [rcx+29h], 3
0x140055e96  jb      loc_140055F53
0x140055e9c  mov     edx, 25h ; '%'
0x140055ea1  jmp     loc_140055F29
0x140055ea6  mov     eax, dword ptr [rbp+57h+var_40]
0x140055ea9  mov     r8, rsi
0x140055eac  mov     r9d, [rbx+28h]
0x140055eb0  mov     rdx, r12
0x140055eb3  mov     dword ptr [rbp+57h+var_88+0Ch], eax
0x140055eb6  lea     rax, [rbp+57h+var_88]
0x140055eba  mov     [rsp+100h+var_C0], rax
0x140055ebf  lea     rax, HsmiInfoUpdatePlaceholderStatesOnRenamePost
0x140055ec6  mov     [rsp+100h+var_C8], rax
0x140055ecb  lea     rax, HsmiInfoUpdatePlaceholderStatesOnRenamePre
0x140055ed2  mov     [rsp+100h+var_D0], rax
0x140055ed7  mov     byte ptr [rsp+100h+LengthReturned], cl
0x140055edb  mov     byte ptr [rsp+100h+FileInformationClass], cl
0x140055edf  mov     dword ptr [rbp+57h+var_78], ecx
0x140055ee2  mov     rcx, r14
0x140055ee5  mov     qword ptr [rbp+57h+var_88], rsi
0x140055ee9  mov     dword ptr [rbp+57h+var_88+8], r9d
0x140055eed  call    HsmpRecurseDirectory
0x140055ef2  mov     ecx, eax
0x140055ef4  mov     [rbp+57h+var_AC], eax
0x140055ef7  call    HsmDbgBreakOnStatus
0x140055efc  mov     eax, [rbp+57h+var_AC]
0x140055eff  test    eax, eax
0x140055f01  jns     short loc_140055F53
0x140055f03  mov     rcx, cs:WPP_GLOBAL_Control
0x140055f0a  lea     rdx, WPP_GLOBAL_Control
0x140055f11  cmp     rcx, rdx
0x140055f14  jz      short loc_140055F53
0x140055f16  mov     edx, [rcx+2Ch]
0x140055f19  test    dl, 1
0x140055f1c  jz      short loc_140055F53
0x140055f1e  cmp     byte ptr [rcx+29h], 3
0x140055f22  jb      short loc_140055F53
0x140055f24  mov     edx, 26h ; '&'
0x140055f29  mov     rcx, [rcx+18h]
0x140055f2d  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140055f34  mov     dword ptr [rsp+100h+var_C8], eax
0x140055f38  mov     r9, r13
0x140055f3b  mov     rax, [rbp+57h+var_A8]
0x140055f3f  mov     [rsp+100h+var_D0], r15
0x140055f44  mov     [rsp+100h+LengthReturned], rax
0x140055f49  mov     qword ptr [rsp+100h+FileInformationClass], r14
0x140055f4e  call    WPP_SF_qqiqd
  ... truncated ...
```
