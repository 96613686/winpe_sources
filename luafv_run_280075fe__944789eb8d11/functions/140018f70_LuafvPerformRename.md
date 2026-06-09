# LuafvPerformRename

- ea: `0x140018f70`
- end: `0x140019778`
- name: `LuafvPerformRename`
- size: `2056`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x140018270`

## callees

- `0x14000217c`
- `0x140005f30`
- `0x140006080`
- `0x1400162cc`
- `0x140017648`
- `0x140017e60`
- `0x140018530`
- `0x14001860c`
- `0x140018f70`
- `0x140019780`
- `0x140019a74`
- `0x14001a3c8`
- `0x14001dc20`
- `0x14001dd90`
- `0x14001f620`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001924f`
- `ntoskrnl!ExAllocatePool2` at `0x14001924f`
- `FLTMGR!FltGetStreamHandleContext` at `0x140019317`
- `FLTMGR!FltGetStreamHandleContext` at `0x140019317`
- `FLTMGR!FltReleaseContext` at `0x1400193c7`
- `FLTMGR!FltReleaseContext` at `0x1400193c7`
- `FLTMGR!FltReleasePushLockEx` at `0x140019291`
- `FLTMGR!FltReleasePushLockEx` at `0x140019291`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140019276`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140019276`
- `FLTMGR!FltSetInformationFile` at `0x140019491`
- `FLTMGR!FltSetInformationFile` at `0x140019721`
- `FLTMGR!FltSetInformationFile` at `0x140019491`
- `FLTMGR!FltSetInformationFile` at `0x140019721`
- `FLTMGR!FltQueryInformationFile` at `0x140019107`
- `FLTMGR!FltQueryInformationFile` at `0x140019680`
- `FLTMGR!FltQueryInformationFile` at `0x140019107`
- `FLTMGR!FltQueryInformationFile` at `0x140019680`

## pseudocode

```c
__int64 __fastcall LuafvPerformRename(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rax
  struct _FILE_OBJECT *v4; // rdi
  struct _FILE_OBJECT *v5; // rcx
  char *v6; // r12
  char v7; // r14
  PFLT_INSTANCE *v8; // r13
  char IsVirtualFileObject; // al
  unsigned __int16 v10; // cx
  char *v11; // r8
  PFLT_INSTANCE *v12; // rsi
  unsigned __int16 v13; // r9
  __int64 v14; // rcx
  int NameFileObject; // ebx
  NTSTATUS InformationFile; // eax
  int v17; // ecx
  unsigned int v18; // edi
  __int64 *v20; // r8
  __int8 v21; // dl
  ULONG v22; // edi
  __int64 Pool2; // rax
  __int64 v24; // rbx
  _DWORD *v25; // r14
  char v26; // al
  __int64 v27; // rdx
  struct _FILE_OBJECT *v28; // rdx
  PVOID FsContext; // rsi
  _BYTE *v30; // rax
  bool v31; // di
  unsigned int v32; // ecx
  NTSTATUS v33; // eax
  __int64 v34; // rcx
  unsigned int v35; // edx
  __int16 v36; // r8
  __int8 v37; // al
  __int8 v38; // cl
  NTSTATUS v39; // eax
  __m128i *v40; // rcx
  unsigned int v41; // eax
  int v42; // [rsp+40h] [rbp-89h] BYREF
  char v43; // [rsp+44h] [rbp-85h]
  bool v44; // [rsp+45h] [rbp-84h] BYREF
  int v45; // [rsp+48h] [rbp-81h]
  __m128i *v46; // [rsp+50h] [rbp-79h] BYREF
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-71h] BYREF
  __int128 v48; // [rsp+60h] [rbp-69h] BYREF
  int v49; // [rsp+70h] [rbp-59h] BYREF
  ULONG Length; // [rsp+74h] [rbp-55h]
  __int64 v51; // [rsp+78h] [rbp-51h]
  __int64 v52; // [rsp+80h] [rbp-49h]
  __int128 v53; // [rsp+90h] [rbp-39h]
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-29h]
  __int128 v55; // [rsp+B0h] [rbp-19h] BYREF
  _OWORD FileInformation[2]; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v57; // [rsp+E0h] [rbp+17h]

  v51 = a2;
  v55 = 0u;
  v57 = 0;
  v2 = *(_QWORD **)(a1 + 16);
  v48 = 0;
  v49 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v46 = 0;
  v42 = 0;
  Context = 0;
  v4 = (struct _FILE_OBJECT *)v2[5];
  v5 = (struct _FILE_OBJECT *)v2[1];
  v6 = (char *)v2[7];
  v44 = 0;
  v52 = 0;
  v45 = 4;
  FileObject = v5;
  v53 = 0;
  if ( v4 || *((_DWORD *)v6 + 4) >= 2u && *((_WORD *)v6 + 10) == 92 )
  {
    v7 = 0;
  }
  else
  {
    v4 = v5;
    v7 = 1;
  }
  v8 = (PFLT_INSTANCE *)(a2 + 24);
  if ( v4 )
  {
    IsVirtualFileObject = LuafvIsVirtualFileObject(*v8, v4);
    a2 = v51;
    v43 = IsVirtualFileObject;
  }
  else
  {
    v43 = 0;
  }
  if ( v7 )
  {
    v12 = (PFLT_INSTANCE *)(a2 + 24);
    NameFileObject = LuafvGetNameFileObject(*(PFLT_INSTANCE *)(a2 + 24), v4);
    if ( NameFileObject < 0 )
      goto LABEL_35;
    v11 = (char *)*((_QWORD *)&v53 + 1);
    v10 = v53;
  }
  else
  {
    v10 = *((_WORD *)v6 + 8);
    v11 = v6 + 20;
    *((_QWORD *)&v53 + 1) = v6 + 20;
    v12 = v8;
    LOWORD(v53) = v10;
    WORD1(v53) = v10;
  }
  v13 = v10;
  LOWORD(v48) = 0;
  v14 = v10 >> 1;
  if ( (_DWORD)v14 )
  {
    do
    {
      if ( !(_DWORD)v14 )
        break;
      v14 = (unsigned int)(v14 - 1);
    }
    while ( *(_WORD *)&v11[2 * v14] != 92 );
    *((_QWORD *)&v48 + 1) = &v11[2 * v14];
    LOWORD(v53) = 2 * v14;
    LOWORD(v48) = v13 - 2 * v14;
    WORD1(v48) = v48;
  }
  else
  {
    v8 = v12;
  }
  if ( v7 )
  {
    v55 = v53;
    v34 = 0;
    *((_QWORD *)&v48 + 1) = v6 + 20;
    v35 = *((unsigned __int16 *)v6 + 8);
    LOWORD(v48) = v35;
    WORD1(v48) = v35;
    while ( (unsigned int)v34 < v35 >> 1 )
    {
      v36 = *(_WORD *)&v6[2 * v34 + 20];
      if ( v36 == 92 || v36 == 58 )
      {
        NameFileObject = -1073741773;
        goto LABEL_35;
      }
      v34 = (unsigned int)(v34 + 1);
    }
  }
  else
  {
    NameFileObject = LuafvGetNameFileObject(*v8, v4);
    if ( NameFileObject < 0 )
    {
LABEL_35:
      v18 = v45;
      goto LABEL_23;
    }
    if ( (unsigned __int16)v48 >= 2u && **((_WORD **)&v48 + 1) == 92 )
    {
      LOWORD(v48) = v48 - 2;
      *((_QWORD *)&v48 + 1) += 2LL;
    }
  }
  InformationFile = FltQueryInformationFile(*v8, FileObject, FileInformation, 0x28u, FileBasicInformation, 0);
  NameFileObject = InformationFile;
  if ( InformationFile < 0 )
  {
    v20 = LuafvQueryInformationFailed;
LABEL_34:
    LuafvLogFileError(a1, 0, v20, (unsigned int)InformationFile);
    goto LABEL_35;
  }
  v17 = (v43 != 0) | 2;
  if ( (v57 & 0x10) == 0 )
    v17 = v43 != 0;
  InformationFile = LuafvQueryStoreFile(
                      (unsigned int)*v8,
                      a1,
                      (unsigned int)&v55,
                      (unsigned int)&v48,
                      v17,
                      (__int64)&v46,
                      (__int64)&v49,
                      (__int64)&v42);
  NameFileObject = InformationFile;
  if ( InformationFile < 0 )
  {
    v20 = LuafvQueryStoreFileFailed;
    goto LABEL_34;
  }
  if ( (v49 & 2) != 0 )
  {
    NameFileObject = -1073741790;
    goto LABEL_35;
  }
  if ( !v46 )
  {
    v18 = 1;
    goto LABEL_23;
  }
  v21 = v46[2].m128i_i8[8];
  if ( (v21 & 1) != 0 )
  {
    v37 = v46[5].m128i_i8[8];
    if ( (v37 & 1) != 0 && (((unsigned __int8)~v21 ^ (unsigned __int8)~v37) & 4) != 0 )
      v42 |= 0x100u;
  }
  v22 = v46[3].m128i_u16[0] + 20;
  Length = v22;
  if ( v22 >= 0xFFFFFFF8 )
  {
    v52 = 0;
    goto LABEL_46;
  }
  Pool2 = ExAllocatePool2(256, v22 + 8, 1717663052);
  v24 = Pool2;
  if ( !Pool2 )
  {
    v52 = 0;
    goto LABEL_46;
  }
  *(_DWORD *)Pool2 = v22;
  *(_BYTE *)(Pool2 + 4) = -1;
  FltAcquirePushLockExclusiveEx(&PoolLock, 0);
  dword_14000F2FC += v22;
  FltReleasePushLockEx(&PoolLock, 0);
  v25 = (_DWORD *)(v24 + 8);
  v52 = v24 + 8;
  if ( v24 == -8 )
  {
LABEL_46:
    NameFileObject = -1073741670;
    goto LABEL_35;
  }
  v26 = *v6;
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) == 65 )
    v26 &= 1u;
  v27 = v51;
  *(_BYTE *)v25 = v26;
  *(_QWORD *)(v24 + 16) = 0;
  v28 = *(struct _FILE_OBJECT **)(v27 + 32);
  if ( !v28 )
    goto LABEL_44;
  FsContext = v28->FsContext;
  if ( FsContext && *(_WORD *)FsContext == 30310 )
  {
    Context = (PFLT_CONTEXT)*((_QWORD *)FsContext + 32);
    v31 = *((_BYTE *)FsContext + 252) != 0;
    goto LABEL_65;
  }
  if ( *v8 && FltGetStreamHandleContext(*v8, v28, &Context) >= 0 )
  {
    v30 = Context;
    FsContext = 0;
  }
  else
  {
LABEL_44:
    FsContext = 0;
    v30 = 0;
    Context = 0;
  }
  v31 = 0;
  if ( v30 )
    v31 = (v30[52] & 2) != 0;
LABEL_65:
  if ( v42 || (v46[5].m128i_i8[8] & 1) == 0 )
  {
    v32 = v46->m128i_u16[0];
    *(_DWORD *)(v24 + 24) = v32;
    memmove((void *)(v24 + 28), (const void *)v46->m128i_i64[1], v32);
    v33 = FltSetInformationFile(*v8, FileObject, v25, Length, FileRenameInformation);
    NameFileObject = v33;
    if ( v33 >= 0 )
    {
      if ( (dword_14000F118 & 1) != 0 && v31 )
        LuafvLogVirtualRename(a1, (_DWORD)Context);
      LuafvUpdateFileTableForFileChange(v46, v46[2].m128i_i64[0]);
    }
    else if ( v33 == -1073741790 )
    {
      v38 = v46[2].m128i_i8[8];
      if ( (v38 & 1) != 0 )
      {
        if ( !*v6 )
        {
          NameFileObject = -1073741771;
          goto LABEL_68;
        }
        if ( (v38 & 4) != 0 || (v57 & 0x10) != 0 || (v38 & 8) != 0 )
          goto LABEL_68;
      }
    }
    if ( v42 )
      goto LABEL_68;
    if ( NameFileObject == -1073741766 )
    {
      if ( (v46[5].m128i_i8[8] & 2) == 0 )
        goto LABEL_68;
    }
    else if ( NameFileObject != -1073741790 )
    {
      goto LABEL_68;
    }
  }
  NameFileObject = LuafvCheckAdminAccess(a1, *v8, v46, &v44);
  if ( NameFileObject < 0 )
    goto LABEL_68;
  if ( v44 )
  {
    if ( !v31 )
    {
      v39 = FltQueryInformationFile(*v8, *(PFILE_OBJECT *)(v51 + 32), FileInformation, 0x28u, FileBasicInformation, 0);
      NameFileObject = v39;
      if ( v39 < 0 )
      {
        LuafvLogFileError(a1, 0, LuafvQueryInformationFailed, (unsigned int)v39);
        goto LABEL_68;
      }
      if ( (v57 & 0x10) != 0 )
      {
        v42 |= 0x4000u;
        NameFileObject = -1073741790;
        goto LABEL_68;
      }
    }
    v40 = v46;
    if ( (v46[2].m128i_i8[8] & 2) != 0 && (v46[5].m128i_i8[8] & 2) == 0 )
    {
      NameFileObject = LuafvCreateVirtualPath(*v8);
      if ( NameFileObject < 0 )
        goto LABEL_68;
      v40 = v46;
    }
    v41 = v40[3].m128i_u16[0];
    v25[4] = v41;
    memmove(v25 + 5, (const void *)v46[3].m128i_i64[1], v41);
    NameFileObject = FltSetInformationFile(*v8, FileObject, v25, Length, FileRenameInformation);
    if ( NameFileObject >= 0 )
    {
      if ( (dword_14000F118 & 1) != 0 )
        LuafvLogVirtualRename(a1, (_DWORD)Context);
      LuafvUpdateFileTableForFileChange(&v46[3], v46[5].m128i_i64[0]);
    }
  }
  else
  {
    NameFileObject = -1073741790;
    if ( (dword_14000F118 & 8) != 0 )
      v42 |= 0x20u;
  }
LABEL_68:
  v18 = v45;
  if ( FsContext )
  {
LABEL_54:
    if ( NameFileObject >= 0 )
      LuafvUpdateFileTableForFileObject(0, *(_QWORD *)(v51 + 24), *(_QWORD *)(v51 + 32));
    *(_DWORD *)(a1 + 24) = NameFileObject;
    *(_QWORD *)(a1 + 32) = 0;
    if ( NameFileObject == -1073741790
      && ((dword_14000F118 & 8) != 0 && v42 || (dword_14000F118 & 4) != 0 && (v42 & 0x4400) != 0) )
    {
      LuafvLogExclusion(a1);
    }
    goto LABEL_26;
  }
LABEL_23:
  if ( Context )
    FltReleaseContext(Context);
  if ( v18 == 4 )
    goto LABEL_54;
LABEL_26:
  if ( v52 )
    LuafvFreePool(v52);
  if ( v46 )
    LuafvFreeStoreFile();
  if ( *((_QWORD *)&v55 + 1) )
    LuafvFreePool(*((__int64 *)&v55 + 1));
  return v18;
}

```

## disassembly

```asm
0x140018f70  mov     [rsp-8+arg_10], rbx
0x140018f75  push    rbp
0x140018f76  push    rsi
0x140018f77  push    rdi
0x140018f78  push    r12
0x140018f7a  push    r13
0x140018f7c  push    r14
0x140018f7e  push    r15
0x140018f80  lea     rbp, [rsp-27h]
0x140018f85  sub     rsp, 0F0h
0x140018f8c  mov     rax, cs:__security_cookie
0x140018f93  xor     rax, rsp
0x140018f96  mov     [rbp+57h+var_38], rax
0x140018f9a  xor     ebx, ebx
0x140018f9c  mov     [rbp+57h+var_A8], rdx
0x140018fa0  xor     eax, eax
0x140018fa2  mov     qword ptr [rbp+57h+var_70], rbx
0x140018fa6  mov     [rbp+57h+var_40], rax
0x140018faa  xorps   xmm0, xmm0
0x140018fad  mov     rax, [rcx+10h]
0x140018fb1  xorps   xmm1, xmm1
0x140018fb4  movups  [rbp+57h+var_C0], xmm1
0x140018fb8  mov     [rbp+57h+var_B0], ebx
0x140018fbb  mov     r15, rcx
0x140018fbe  movups  [rbp+57h+FileInformation], xmm0
0x140018fc2  mov     [rbp+57h+var_D0], rbx
0x140018fc6  movups  [rbp+57h+var_50], xmm0
0x140018fca  mov     [rsp+120h+var_E0], ebx
0x140018fce  mov     qword ptr [rbp+57h+var_70+8], rbx
0x140018fd2  mov     [rbp+57h+Context], rbx
0x140018fd6  mov     rdi, [rax+28h]
0x140018fda  mov     rcx, [rax+8]
0x140018fde  mov     r12, [rax+38h]
0x140018fe2  mov     [rsp+120h+var_DB], bl
0x140018fe6  mov     [rbp+57h+var_A0], rbx
0x140018fea  mov     [rsp+120h+var_D8], 4
0x140018ff2  mov     [rbp+57h+FileObject], rcx
0x140018ff6  movups  [rbp+57h+var_90], xmm0
0x140018ffa  test    rdi, rdi
0x140018ffd  jz      loc_1400194F0
0x140019003  mov     r14b, bl
0x140019006  lea     r13, [rdx+18h]
0x14001900a  test    rdi, rdi
0x14001900d  jz      loc_140019205
0x140019013  mov     rcx, [r13+0]
0x140019017  mov     rdx, rdi
0x14001901a  call    LuafvIsVirtualFileObject
0x14001901f  mov     rdx, [rbp+57h+var_A8]
0x140019023  mov     [rsp+120h+var_DC], al
0x140019027  test    r14b, r14b
0x14001902a  jnz     loc_1400193D8
0x140019030  movzx   ecx, word ptr [r12+10h]
0x140019036  lea     r8, [r12+14h]
0x14001903b  mov     qword ptr [rbp+57h+var_90+8], r8
0x14001903f  mov     rsi, r13
0x140019042  mov     word ptr [rbp+57h+var_90], cx
0x140019046  mov     word ptr [rbp+57h+var_90+2], cx
0x14001904a  movzx   r9d, cx
0x14001904e  mov     ecx, r9d
0x140019051  mov     word ptr [rbp+57h+var_C0], bx
0x140019055  shr     ecx, 1
0x140019057  jz      loc_140019510
0x14001905d  test    ecx, ecx
0x14001905f  jz      short loc_14001906B
0x140019061  dec     ecx
0x140019063  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x140019069  jnz     short loc_14001905D
0x14001906b  movzx   edx, cx
0x14001906e  lea     rcx, [r8+rcx*2]
0x140019072  add     dx, dx
0x140019075  mov     qword ptr [rbp+57h+var_C0+8], rcx
0x140019079  sub     r9w, dx
0x14001907d  mov     word ptr [rbp+57h+var_90], dx
0x140019081  mov     word ptr [rbp+57h+var_C0], r9w
0x140019086  mov     word ptr [rbp+57h+var_C0+2], r9w
0x14001908b  test    r14b, r14b
0x14001908e  jnz     loc_140019518
0x140019094  mov     rcx, [r13+0]; Instance
0x140019098  lea     r8, [rbp+57h+var_70]
0x14001909c  mov     rdx, rdi; FileObject
0x14001909f  call    LuafvGetNameFileObject
0x1400190a4  mov     ebx, eax
0x1400190a6  test    eax, eax
0x1400190a8  js      loc_1400191FC
0x1400190ae  movzx   ecx, word ptr [rbp+57h+var_C0]
0x1400190b2  mov     esi, 2
0x1400190b7  cmp     cx, si
0x1400190ba  jb      short loc_1400190D9
0x1400190bc  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x1400190c0  cmp     word ptr [rax], 5Ch ; '\'
0x1400190c4  jnz     short loc_1400190D9
0x1400190c6  mov     edx, 0FFFEh
0x1400190cb  add     cx, dx
0x1400190ce  add     rax, rsi
0x1400190d1  mov     word ptr [rbp+57h+var_C0], cx
0x1400190d5  mov     qword ptr [rbp+57h+var_C0+8], rax
0x1400190d9  mov     rdx, [rbp+57h+FileObject]; FileObject
0x1400190dd  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1400190e1  mov     rcx, [r13+0]; Instance
0x1400190e5  xor     edi, edi
0x1400190e7  cmp     [rsp+120h+var_DC], dil
0x1400190ec  mov     r9d, 28h ; '('; Length
0x1400190f2  mov     [rsp+120h+LengthReturned], 0; LengthReturned
0x1400190fb  setnz   dil
0x1400190ff  mov     [rsp+120h+FileInformationClass], 4; FileInformationClass
0x140019107  call    cs:__imp_FltQueryInformationFile
0x14001910e  nop     dword ptr [rax+rax+00h]
0x140019113  mov     ebx, eax
0x140019115  test    eax, eax
0x140019117  js      loc_1400191E8
0x14001911d  mov     ecx, edi
0x14001911f  lea     rax, [rsp+120h+var_E0]
0x140019124  mov     [rsp+120h+var_E8], rax
0x140019129  lea     r9, [rbp+57h+var_C0]
0x14001912d  or      ecx, esi
0x14001912f  lea     rax, [rbp+57h+var_B0]
0x140019133  test    byte ptr [rbp+57h+var_40], 10h
0x140019137  lea     r8, [rbp+57h+var_70]
0x14001913b  mov     [rsp+120h+var_F0], rax
0x140019140  mov     rdx, r15
0x140019143  cmovz   ecx, edi
0x140019146  lea     rax, [rbp+57h+var_D0]
0x14001914a  mov     [rsp+120h+LengthReturned], rax
0x14001914f  mov     [rsp+120h+FileInformationClass], ecx
0x140019153  mov     rcx, [r13+0]
0x140019157  call    LuafvQueryStoreFile
0x14001915c  mov     ebx, eax
0x14001915e  test    eax, eax
0x140019160  js      loc_14001956D
0x140019166  test    byte ptr [rbp+57h+var_B0], sil
0x14001916a  jnz     loc_140019579
0x140019170  cmp     [rbp+57h+var_D0], 0
0x140019175  jnz     loc_14001920E
0x14001917b  mov     edi, 1
0x140019180  mov     rcx, [rbp+57h+Context]; Context
0x140019184  test    rcx, rcx
0x140019187  jnz     loc_1400193C7
0x14001918d  cmp     edi, 4
0x140019190  jz      loc_140019349
0x140019196  mov     rax, [rbp+57h+var_A0]
0x14001919a  test    rax, rax
0x14001919d  jnz     loc_1400193A5
0x1400191a3  mov     rcx, [rbp+57h+var_D0]
0x1400191a7  test    rcx, rcx
0x1400191aa  jnz     loc_14001976E
0x1400191b0  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x1400191b4  test    rcx, rcx
0x1400191b7  jz      short loc_1400191BE
0x1400191b9  call    LuafvFreePool
0x1400191be  mov     eax, edi
0x1400191c0  mov     rcx, [rbp+57h+var_38]
0x1400191c4  xor     rcx, rsp; StackCookie
0x1400191c7  call    __security_check_cookie
0x1400191cc  mov     rbx, [rsp+120h+arg_10]
0x1400191d4  add     rsp, 0F0h
0x1400191db  pop     r15
0x1400191dd  pop     r14
0x1400191df  pop     r13
0x1400191e1  pop     r12
0x1400191e3  pop     rdi
0x1400191e4  pop     rsi
0x1400191e5  pop     rbp
0x1400191e6  retn
0x1400191e8  lea     r8, LuafvQueryInformationFailed
0x1400191ef  mov     r9d, eax
0x1400191f2  xor     edx, edx
0x1400191f4  mov     rcx, r15
0x1400191f7  call    LuafvLogFileError
0x1400191fc  mov     edi, [rsp+120h+var_D8]
0x140019200  jmp     loc_140019180
0x140019205  mov     [rsp+120h+var_DC], bl
0x140019209  jmp     loc_140019027
0x14001920e  mov     rcx, [rbp+57h+var_D0]
0x140019212  mov     r8d, 1
0x140019218  mov     r9d, 100h
0x14001921e  mov     dl, [rcx+28h]
0x140019221  test    r8b, dl
0x140019224  jnz     loc_140019583
0x14001922a  mov     rax, [rbp+57h+var_D0]
0x14001922e  movzx   edi, word ptr [rax+30h]
0x140019232  add     edi, 14h
0x140019235  mov     [rbp+57h+Length], edi
0x140019238  lea     eax, [rdi+8]
0x14001923b  cmp     eax, 8
0x14001923e  jb      loc_1400192E3
0x140019244  mov     edx, eax
0x140019246  mov     r8d, 6661754Ch
0x14001924c  mov     rcx, r9
0x14001924f  call    cs:__imp_ExAllocatePool2
0x140019256  nop     dword ptr [rax+rax+00h]
0x14001925b  mov     rbx, rax
0x14001925e  test    rax, rax
0x140019261  jz      loc_1400195A7
0x140019267  xor     edx, edx
0x140019269  mov     [rax], edi
0x14001926b  lea     rcx, PoolLock
0x140019272  mov     byte ptr [rax+4], 0FFh
0x140019276  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001927d  nop     dword ptr [rax+rax+00h]
0x140019282  add     cs:dword_14000F2FC, edi
0x140019288  lea     rcx, PoolLock
0x14001928f  xor     edx, edx
0x140019291  call    cs:__imp_FltReleasePushLockEx
0x140019298  nop     dword ptr [rax+rax+00h]
0x14001929d  lea     r14, [rbx+8]
0x1400192a1  mov     [rbp+57h+var_A0], r14
0x1400192a5  test    r14, r14
0x1400192a8  jz      short loc_1400192E9
0x1400192aa  mov     rax, [r15+10h]
0x1400192ae  mov     ebx, 1
0x1400192b3  cmp     dword ptr [rax+20h], 41h ; 'A'
0x1400192b7  mov     al, [r12]
0x1400192bb  jz      loc_1400195B4
0x1400192c1  mov     rdx, [rbp+57h+var_A8]
0x1400192c5  mov     [r14], al
0x1400192c8  mov     qword ptr [r14+8], 0
0x1400192d0  mov     rdx, [rdx+20h]; FileObject
0x1400192d4  test    rdx, rdx
0x1400192d7  jnz     short loc_1400192F3
0x1400192d9  xor     esi, esi
0x1400192db  xor     eax, eax
0x1400192dd  mov     [rbp+57h+Context], rax
0x1400192e1  jmp     short loc_14001932D
0x1400192e3  xor     eax, eax
0x1400192e5  mov     [rbp+57h+var_A0], rax
0x1400192e9  mov     ebx, 0C000009Ah
0x1400192ee  jmp     loc_1400191FC
0x1400192f3  mov     rsi, [rdx+18h]
0x1400192f7  test    rsi, rsi
0x1400192fa  jz      short loc_14001930A
0x1400192fc  mov     eax, 7666h
0x140019301  cmp     [rsi], ax
0x140019304  jz      loc_140019404
0x14001930a  mov     rcx, [r13+0]; Instance
0x14001930e  test    rcx, rcx
0x140019311  jz      short loc_1400192D9
0x140019313  lea     r8, [rbp+57h+Context]; Context
0x140019317  call    cs:__imp_FltGetStreamHandleContext
0x14001931e  nop     dword ptr [rax+rax+00h]
0x140019323  test    eax, eax
0x140019325  js      short loc_1400192D9
0x140019327  mov     rax, [rbp+57h+Context]
0x14001932b  xor     esi, esi
0x14001932d  xor     dil, dil
0x140019330  test    rax, rax
0x140019333  jz      loc_14001941A
0x140019339  test    byte ptr [rax+34h], 2
0x14001933d  movzx   edi, dil
0x140019341  cmovnz  edi, ebx
0x140019344  jmp     loc_14001941A
0x140019349  test    ebx, ebx
0x14001934b  jns     short loc_1400193B2
0x14001934d  mov     [r15+18h], ebx
0x140019351  mov     qword ptr [r15+20h], 0
0x140019359  cmp     ebx, 0C0000022h
0x14001935f  jnz     loc_140019196
0x140019365  mov     eax, cs:dword_14000F118
0x14001936b  test    al, 8
0x14001936d  jz      short loc_140019376
0x14001936f  cmp     [rsp+120h+var_E0], 0
0x140019374  jnz     short loc_14001938C
0x140019376  test    al, 4
0x140019378  jz      loc_140019196
0x14001937e  test    [rsp+120h+var_E0], 4400h
0x140019386  jz      loc_140019196
0x14001938c  mov     r9d, [rsp+120h+var_E0]
0x140019391  xor     r8d, r8d
0x140019394  mov     rdx, [rbp+57h+var_D0]
0x140019398  mov     rcx, r15
0x14001939b  call    LuafvLogExclusion
0x1400193a0  jmp     loc_140019196
0x1400193a5  mov     rcx, rax
0x1400193a8  call    LuafvFreePool
0x1400193ad  jmp     loc_1400191A3
0x1400193b2  mov     rax, [rbp+57h+var_A8]
0x1400193b6  xor     ecx, ecx
0x1400193b8  mov     r8, [rax+20h]
0x1400193bc  mov     rdx, [rax+18h]
0x1400193c0  call    LuafvUpdateFileTableForFileObject
0x1400193c5  jmp     short loc_14001934D
0x1400193c7  call    cs:__imp_FltReleaseContext
0x1400193ce  nop     dword ptr [rax+rax+00h]
0x1400193d3  jmp     loc_14001918D
0x1400193d8  lea     rsi, [rdx+18h]
0x1400193dc  mov     rdx, rdi; FileObject
0x1400193df  mov     rcx, [rsi]; Instance
0x1400193e2  lea     r8, [rbp+57h+var_90]
0x1400193e6  call    LuafvGetNameFileObject
0x1400193eb  mov     ebx, eax
0x1400193ed  test    eax, eax
0x1400193ef  js      loc_1400191FC
0x1400193f5  mov     r8, qword ptr [rbp+57h+var_90+8]
0x1400193f9  xor     ebx, ebx
0x1400193fb  movzx   ecx, word ptr [rbp+57h+var_90]
0x1400193ff  jmp     loc_14001904A
0x140019404  mov     rax, [rsi+100h]
0x14001940b  mov     [rbp+57h+Context], rax
0x14001940f  cmp     byte ptr [rsi+0FCh], 0
0x140019416  setnz   dil
0x14001941a  cmp     [rsp+120h+var_E0], 0
  ... truncated ...
```
