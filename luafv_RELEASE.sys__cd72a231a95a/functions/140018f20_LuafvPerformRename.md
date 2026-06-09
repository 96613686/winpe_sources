# LuafvPerformRename

- ea: `0x140018f20`
- end: `0x140019728`
- name: `LuafvPerformRename`
- size: `2056`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x140018220`

## callees

- `0x140002404`
- `0x140005bb0`
- `0x140005d00`
- `0x1400162cc`
- `0x1400175f8`
- `0x140017e10`
- `0x1400184e0`
- `0x1400185bc`
- `0x140018f20`
- `0x140019730`
- `0x140019a24`
- `0x14001a378`
- `0x14001dbd0`
- `0x14001dd40`
- `0x14001f5d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400191ff`
- `ntoskrnl!ExAllocatePool2` at `0x1400191ff`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400192c7`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400192c7`
- `FLTMGR!FltReleaseContext` at `0x140019377`
- `FLTMGR!FltReleaseContext` at `0x140019377`
- `FLTMGR!FltReleasePushLockEx` at `0x140019241`
- `FLTMGR!FltReleasePushLockEx` at `0x140019241`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140019226`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140019226`
- `FLTMGR!FltSetInformationFile` at `0x140019441`
- `FLTMGR!FltSetInformationFile` at `0x1400196d1`
- `FLTMGR!FltSetInformationFile` at `0x140019441`
- `FLTMGR!FltSetInformationFile` at `0x1400196d1`
- `FLTMGR!FltQueryInformationFile` at `0x1400190b7`
- `FLTMGR!FltQueryInformationFile` at `0x140019630`
- `FLTMGR!FltQueryInformationFile` at `0x1400190b7`
- `FLTMGR!FltQueryInformationFile` at `0x140019630`

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
  NTSTATUS NameFileObject; // ebx
  NTSTATUS InformationFile; // eax
  int v17; // ecx
  unsigned int v18; // edi
  __int64 *v20; // r8
  char v21; // dl
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
  char v37; // al
  char v38; // cl
  NTSTATUS v39; // eax
  unsigned __int16 *v40; // rcx
  unsigned int v41; // eax
  int v42; // [rsp+40h] [rbp-89h] BYREF
  char v43; // [rsp+44h] [rbp-85h]
  char v44[3]; // [rsp+45h] [rbp-84h] BYREF
  int v45; // [rsp+48h] [rbp-81h]
  unsigned __int16 *v46; // [rsp+50h] [rbp-79h] BYREF
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
  v44[0] = 0;
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
  v21 = *((_BYTE *)v46 + 40);
  if ( (v21 & 1) != 0 )
  {
    v37 = *((_BYTE *)v46 + 88);
    if ( (v37 & 1) != 0 && (((unsigned __int8)~v21 ^ (unsigned __int8)~v37) & 4) != 0 )
      v42 |= 0x100u;
  }
  v22 = v46[24] + 20;
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
  dword_14000ECBC += v22;
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
  if ( v42 || (v46[44] & 1) == 0 )
  {
    v32 = *v46;
    *(_DWORD *)(v24 + 24) = v32;
    memmove((void *)(v24 + 28), *((const void **)v46 + 1), v32);
    v33 = FltSetInformationFile(*v8, FileObject, v25, Length, FileRenameInformation);
    NameFileObject = v33;
    if ( v33 >= 0 )
    {
      if ( (dword_14000EAD8 & 1) != 0 && v31 )
        LuafvLogVirtualRename(a1, (_DWORD)Context);
      LuafvUpdateFileTableForFileChange(v46, *((_QWORD *)v46 + 4));
    }
    else if ( v33 == -1073741790 )
    {
      v38 = *((_BYTE *)v46 + 40);
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
      if ( (v46[44] & 2) == 0 )
        goto LABEL_68;
    }
    else if ( NameFileObject != -1073741790 )
    {
      goto LABEL_68;
    }
  }
  NameFileObject = LuafvCheckAdminAccess(a1, *v8, v46, v44);
  if ( NameFileObject < 0 )
    goto LABEL_68;
  if ( v44[0] )
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
    if ( (v46[20] & 2) != 0 && (v46[44] & 2) == 0 )
    {
      NameFileObject = LuafvCreateVirtualPath(*v8);
      if ( NameFileObject < 0 )
        goto LABEL_68;
      v40 = v46;
    }
    v41 = v40[24];
    v25[4] = v41;
    memmove(v25 + 5, *((const void **)v46 + 7), v41);
    NameFileObject = FltSetInformationFile(*v8, FileObject, v25, Length, FileRenameInformation);
    if ( NameFileObject >= 0 )
    {
      if ( (dword_14000EAD8 & 1) != 0 )
        LuafvLogVirtualRename(a1, (_DWORD)Context);
      LuafvUpdateFileTableForFileChange(v46 + 24, *((_QWORD *)v46 + 10));
    }
  }
  else
  {
    NameFileObject = -1073741790;
    if ( (dword_14000EAD8 & 8) != 0 )
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
      && ((dword_14000EAD8 & 8) != 0 && v42 || (dword_14000EAD8 & 4) != 0 && (v42 & 0x4400) != 0) )
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
    LuafvFreePool(*((_QWORD *)&v55 + 1));
  return v18;
}

```

## disassembly

```asm
0x140018f20  mov     [rsp-8+arg_10], rbx
0x140018f25  push    rbp
0x140018f26  push    rsi
0x140018f27  push    rdi
0x140018f28  push    r12
0x140018f2a  push    r13
0x140018f2c  push    r14
0x140018f2e  push    r15
0x140018f30  lea     rbp, [rsp-27h]
0x140018f35  sub     rsp, 0F0h
0x140018f3c  mov     rax, cs:__security_cookie
0x140018f43  xor     rax, rsp
0x140018f46  mov     [rbp+57h+var_38], rax
0x140018f4a  xor     ebx, ebx
0x140018f4c  mov     [rbp+57h+var_A8], rdx
0x140018f50  xor     eax, eax
0x140018f52  mov     qword ptr [rbp+57h+var_70], rbx
0x140018f56  mov     [rbp+57h+var_40], rax
0x140018f5a  xorps   xmm0, xmm0
0x140018f5d  mov     rax, [rcx+10h]
0x140018f61  xorps   xmm1, xmm1
0x140018f64  movups  [rbp+57h+var_C0], xmm1
0x140018f68  mov     [rbp+57h+var_B0], ebx
0x140018f6b  mov     r15, rcx
0x140018f6e  movups  [rbp+57h+FileInformation], xmm0
0x140018f72  mov     [rbp+57h+var_D0], rbx
0x140018f76  movups  [rbp+57h+var_50], xmm0
0x140018f7a  mov     [rsp+120h+var_E0], ebx
0x140018f7e  mov     qword ptr [rbp+57h+var_70+8], rbx
0x140018f82  mov     [rbp+57h+Context], rbx
0x140018f86  mov     rdi, [rax+28h]
0x140018f8a  mov     rcx, [rax+8]
0x140018f8e  mov     r12, [rax+38h]
0x140018f92  mov     [rsp+120h+var_DB], bl
0x140018f96  mov     [rbp+57h+var_A0], rbx
0x140018f9a  mov     [rsp+120h+var_D8], 4
0x140018fa2  mov     [rbp+57h+FileObject], rcx
0x140018fa6  movups  [rbp+57h+var_90], xmm0
0x140018faa  test    rdi, rdi
0x140018fad  jz      loc_1400194A0
0x140018fb3  mov     r14b, bl
0x140018fb6  lea     r13, [rdx+18h]
0x140018fba  test    rdi, rdi
0x140018fbd  jz      loc_1400191B5
0x140018fc3  mov     rcx, [r13+0]
0x140018fc7  mov     rdx, rdi
0x140018fca  call    LuafvIsVirtualFileObject
0x140018fcf  mov     rdx, [rbp+57h+var_A8]
0x140018fd3  mov     [rsp+120h+var_DC], al
0x140018fd7  test    r14b, r14b
0x140018fda  jnz     loc_140019388
0x140018fe0  movzx   ecx, word ptr [r12+10h]
0x140018fe6  lea     r8, [r12+14h]
0x140018feb  mov     qword ptr [rbp+57h+var_90+8], r8
0x140018fef  mov     rsi, r13
0x140018ff2  mov     word ptr [rbp+57h+var_90], cx
0x140018ff6  mov     word ptr [rbp+57h+var_90+2], cx
0x140018ffa  movzx   r9d, cx
0x140018ffe  mov     ecx, r9d
0x140019001  mov     word ptr [rbp+57h+var_C0], bx
0x140019005  shr     ecx, 1
0x140019007  jz      loc_1400194C0
0x14001900d  test    ecx, ecx
0x14001900f  jz      short loc_14001901B
0x140019011  dec     ecx
0x140019013  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x140019019  jnz     short loc_14001900D
0x14001901b  movzx   edx, cx
0x14001901e  lea     rcx, [r8+rcx*2]
0x140019022  add     dx, dx
0x140019025  mov     qword ptr [rbp+57h+var_C0+8], rcx
0x140019029  sub     r9w, dx
0x14001902d  mov     word ptr [rbp+57h+var_90], dx
0x140019031  mov     word ptr [rbp+57h+var_C0], r9w
0x140019036  mov     word ptr [rbp+57h+var_C0+2], r9w
0x14001903b  test    r14b, r14b
0x14001903e  jnz     loc_1400194C8
0x140019044  mov     rcx, [r13+0]; Instance
0x140019048  lea     r8, [rbp+57h+var_70]
0x14001904c  mov     rdx, rdi; FileObject
0x14001904f  call    LuafvGetNameFileObject
0x140019054  mov     ebx, eax
0x140019056  test    eax, eax
0x140019058  js      loc_1400191AC
0x14001905e  movzx   ecx, word ptr [rbp+57h+var_C0]
0x140019062  mov     esi, 2
0x140019067  cmp     cx, si
0x14001906a  jb      short loc_140019089
0x14001906c  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x140019070  cmp     word ptr [rax], 5Ch ; '\'
0x140019074  jnz     short loc_140019089
0x140019076  mov     edx, 0FFFEh
0x14001907b  add     cx, dx
0x14001907e  add     rax, rsi
0x140019081  mov     word ptr [rbp+57h+var_C0], cx
0x140019085  mov     qword ptr [rbp+57h+var_C0+8], rax
0x140019089  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14001908d  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140019091  mov     rcx, [r13+0]; Instance
0x140019095  xor     edi, edi
0x140019097  cmp     [rsp+120h+var_DC], dil
0x14001909c  mov     r9d, 28h ; '('; Length
0x1400190a2  mov     [rsp+120h+LengthReturned], 0; LengthReturned
0x1400190ab  setnz   dil
0x1400190af  mov     [rsp+120h+FileInformationClass], 4; FileInformationClass
0x1400190b7  call    cs:__imp_FltQueryInformationFile
0x1400190be  nop     dword ptr [rax+rax+00h]
0x1400190c3  mov     ebx, eax
0x1400190c5  test    eax, eax
0x1400190c7  js      loc_140019198
0x1400190cd  mov     ecx, edi
0x1400190cf  lea     rax, [rsp+120h+var_E0]
0x1400190d4  mov     [rsp+120h+var_E8], rax
0x1400190d9  lea     r9, [rbp+57h+var_C0]
0x1400190dd  or      ecx, esi
0x1400190df  lea     rax, [rbp+57h+var_B0]
0x1400190e3  test    byte ptr [rbp+57h+var_40], 10h
0x1400190e7  lea     r8, [rbp+57h+var_70]
0x1400190eb  mov     [rsp+120h+var_F0], rax
0x1400190f0  mov     rdx, r15
0x1400190f3  cmovz   ecx, edi
0x1400190f6  lea     rax, [rbp+57h+var_D0]
0x1400190fa  mov     [rsp+120h+LengthReturned], rax
0x1400190ff  mov     [rsp+120h+FileInformationClass], ecx
0x140019103  mov     rcx, [r13+0]
0x140019107  call    LuafvQueryStoreFile
0x14001910c  mov     ebx, eax
0x14001910e  test    eax, eax
0x140019110  js      loc_14001951D
0x140019116  test    byte ptr [rbp+57h+var_B0], sil
0x14001911a  jnz     loc_140019529
0x140019120  cmp     [rbp+57h+var_D0], 0
0x140019125  jnz     loc_1400191BE
0x14001912b  mov     edi, 1
0x140019130  mov     rcx, [rbp+57h+Context]; Context
0x140019134  test    rcx, rcx
0x140019137  jnz     loc_140019377
0x14001913d  cmp     edi, 4
0x140019140  jz      loc_1400192F9
0x140019146  mov     rax, [rbp+57h+var_A0]
0x14001914a  test    rax, rax
0x14001914d  jnz     loc_140019355
0x140019153  mov     rcx, [rbp+57h+var_D0]
0x140019157  test    rcx, rcx
0x14001915a  jnz     loc_14001971E
0x140019160  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x140019164  test    rcx, rcx
0x140019167  jz      short loc_14001916E
0x140019169  call    LuafvFreePool
0x14001916e  mov     eax, edi
0x140019170  mov     rcx, [rbp+57h+var_38]
0x140019174  xor     rcx, rsp; StackCookie
0x140019177  call    __security_check_cookie
0x14001917c  mov     rbx, [rsp+120h+arg_10]
0x140019184  add     rsp, 0F0h
0x14001918b  pop     r15
0x14001918d  pop     r14
0x14001918f  pop     r13
0x140019191  pop     r12
0x140019193  pop     rdi
0x140019194  pop     rsi
0x140019195  pop     rbp
0x140019196  retn
0x140019198  lea     r8, LuafvQueryInformationFailed
0x14001919f  mov     r9d, eax
0x1400191a2  xor     edx, edx
0x1400191a4  mov     rcx, r15
0x1400191a7  call    LuafvLogFileError
0x1400191ac  mov     edi, [rsp+120h+var_D8]
0x1400191b0  jmp     loc_140019130
0x1400191b5  mov     [rsp+120h+var_DC], bl
0x1400191b9  jmp     loc_140018FD7
0x1400191be  mov     rcx, [rbp+57h+var_D0]
0x1400191c2  mov     r8d, 1
0x1400191c8  mov     r9d, 100h
0x1400191ce  mov     dl, [rcx+28h]
0x1400191d1  test    r8b, dl
0x1400191d4  jnz     loc_140019533
0x1400191da  mov     rax, [rbp+57h+var_D0]
0x1400191de  movzx   edi, word ptr [rax+30h]
0x1400191e2  add     edi, 14h
0x1400191e5  mov     [rbp+57h+Length], edi
0x1400191e8  lea     eax, [rdi+8]
0x1400191eb  cmp     eax, 8
0x1400191ee  jb      loc_140019293
0x1400191f4  mov     edx, eax
0x1400191f6  mov     r8d, 6661754Ch
0x1400191fc  mov     rcx, r9
0x1400191ff  call    cs:__imp_ExAllocatePool2
0x140019206  nop     dword ptr [rax+rax+00h]
0x14001920b  mov     rbx, rax
0x14001920e  test    rax, rax
0x140019211  jz      loc_140019557
0x140019217  xor     edx, edx
0x140019219  mov     [rax], edi
0x14001921b  lea     rcx, PoolLock
0x140019222  mov     byte ptr [rax+4], 0FFh
0x140019226  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001922d  nop     dword ptr [rax+rax+00h]
0x140019232  add     cs:dword_14000ECBC, edi
0x140019238  lea     rcx, PoolLock
0x14001923f  xor     edx, edx
0x140019241  call    cs:__imp_FltReleasePushLockEx
0x140019248  nop     dword ptr [rax+rax+00h]
0x14001924d  lea     r14, [rbx+8]
0x140019251  mov     [rbp+57h+var_A0], r14
0x140019255  test    r14, r14
0x140019258  jz      short loc_140019299
0x14001925a  mov     rax, [r15+10h]
0x14001925e  mov     ebx, 1
0x140019263  cmp     dword ptr [rax+20h], 41h ; 'A'
0x140019267  mov     al, [r12]
0x14001926b  jz      loc_140019564
0x140019271  mov     rdx, [rbp+57h+var_A8]
0x140019275  mov     [r14], al
0x140019278  mov     qword ptr [r14+8], 0
0x140019280  mov     rdx, [rdx+20h]; FileObject
0x140019284  test    rdx, rdx
0x140019287  jnz     short loc_1400192A3
0x140019289  xor     esi, esi
0x14001928b  xor     eax, eax
0x14001928d  mov     [rbp+57h+Context], rax
0x140019291  jmp     short loc_1400192DD
0x140019293  xor     eax, eax
0x140019295  mov     [rbp+57h+var_A0], rax
0x140019299  mov     ebx, 0C000009Ah
0x14001929e  jmp     loc_1400191AC
0x1400192a3  mov     rsi, [rdx+18h]
0x1400192a7  test    rsi, rsi
0x1400192aa  jz      short loc_1400192BA
0x1400192ac  mov     eax, 7666h
0x1400192b1  cmp     [rsi], ax
0x1400192b4  jz      loc_1400193B4
0x1400192ba  mov     rcx, [r13+0]; Instance
0x1400192be  test    rcx, rcx
0x1400192c1  jz      short loc_140019289
0x1400192c3  lea     r8, [rbp+57h+Context]; Context
0x1400192c7  call    cs:__imp_FltGetStreamHandleContext
0x1400192ce  nop     dword ptr [rax+rax+00h]
0x1400192d3  test    eax, eax
0x1400192d5  js      short loc_140019289
0x1400192d7  mov     rax, [rbp+57h+Context]
0x1400192db  xor     esi, esi
0x1400192dd  xor     dil, dil
0x1400192e0  test    rax, rax
0x1400192e3  jz      loc_1400193CA
0x1400192e9  test    byte ptr [rax+34h], 2
0x1400192ed  movzx   edi, dil
0x1400192f1  cmovnz  edi, ebx
0x1400192f4  jmp     loc_1400193CA
0x1400192f9  test    ebx, ebx
0x1400192fb  jns     short loc_140019362
0x1400192fd  mov     [r15+18h], ebx
0x140019301  mov     qword ptr [r15+20h], 0
0x140019309  cmp     ebx, 0C0000022h
0x14001930f  jnz     loc_140019146
0x140019315  mov     eax, cs:dword_14000EAD8
0x14001931b  test    al, 8
0x14001931d  jz      short loc_140019326
0x14001931f  cmp     [rsp+120h+var_E0], 0
0x140019324  jnz     short loc_14001933C
0x140019326  test    al, 4
0x140019328  jz      loc_140019146
0x14001932e  test    [rsp+120h+var_E0], 4400h
0x140019336  jz      loc_140019146
0x14001933c  mov     r9d, [rsp+120h+var_E0]
0x140019341  xor     r8d, r8d
0x140019344  mov     rdx, [rbp+57h+var_D0]
0x140019348  mov     rcx, r15
0x14001934b  call    LuafvLogExclusion
0x140019350  jmp     loc_140019146
0x140019355  mov     rcx, rax
0x140019358  call    LuafvFreePool
0x14001935d  jmp     loc_140019153
0x140019362  mov     rax, [rbp+57h+var_A8]
0x140019366  xor     ecx, ecx
0x140019368  mov     r8, [rax+20h]
0x14001936c  mov     rdx, [rax+18h]
0x140019370  call    LuafvUpdateFileTableForFileObject
0x140019375  jmp     short loc_1400192FD
0x140019377  call    cs:__imp_FltReleaseContext
0x14001937e  nop     dword ptr [rax+rax+00h]
0x140019383  jmp     loc_14001913D
0x140019388  lea     rsi, [rdx+18h]
0x14001938c  mov     rdx, rdi; FileObject
0x14001938f  mov     rcx, [rsi]; Instance
0x140019392  lea     r8, [rbp+57h+var_90]
0x140019396  call    LuafvGetNameFileObject
0x14001939b  mov     ebx, eax
0x14001939d  test    eax, eax
0x14001939f  js      loc_1400191AC
0x1400193a5  mov     r8, qword ptr [rbp+57h+var_90+8]
0x1400193a9  xor     ebx, ebx
0x1400193ab  movzx   ecx, word ptr [rbp+57h+var_90]
0x1400193af  jmp     loc_140018FFA
0x1400193b4  mov     rax, [rsi+100h]
0x1400193bb  mov     [rbp+57h+Context], rax
0x1400193bf  cmp     byte ptr [rsi+0FCh], 0
0x1400193c6  setnz   dil
0x1400193ca  cmp     [rsp+120h+var_E0], 0
  ... truncated ...
```
