# DfsADBlobStore::RenameBlob(unsigned __int64,DfsRootFolder *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,_BLOB_DATA *,_BLOB_DATA * *,_BLOB_DATA * *,uchar *)

- ea: `0x14000e39c`
- end: `0x14000eddd`
- name: `?RenameBlob@DfsADBlobStore@@QEAAK_KPEAVDfsRootFolder@@PEAU_UNICODE_STRING@@2KPEAU_BLOB_DATA@@PEAPEAU4@4PEAE@Z`
- size: `2625`
- prototype: `unsigned int(DfsADBlobStore *__hidden this, unsigned __int64, struct DfsRootFolder *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, struct _BLOB_DATA *, struct _BLOB_DATA **, struct _BLOB_DATA **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x14000d860`

## callees

- `0x140005a94`
- `0x140005ad8`
- `0x14000851c`
- `0x14000abc4`
- `0x14000d1fc`
- `0x14000dc74`
- `0x14000e39c`
- `0x14000f2d4`
- `0x14000f958`
- `0x14000f9f4`
- `0x14000faf8`
- `0x14000fca8`
- `0x14000fd24`
- `0x1400316bc`
- `0x1400583f4`
- `0x14005864c`
- `0x1400586a8`
- `0x140058708`
- `0x140058ce0`
- `0x140058db8`
- `0x14005ce3a`
- `0x14005ce70`
- `0x14005e010`

## import_xrefs

- `msvcrt!free` at `0x14000ec90`
- `msvcrt!free` at `0x14005d5dc`
- `msvcrt!free` at `0x14000ec90`
- `msvcrt!free` at `0x14005d5dc`
- `msvcrt!malloc` at `0x14000ea5e`
- `msvcrt!malloc` at `0x14000ea5e`
- `RPCRT4!UuidCreate` at `0x14000e983`
- `RPCRT4!UuidCreate` at `0x14000e983`

## pseudocode

```c
__int64 __fastcall DfsADBlobStore::RenameBlob(
        DfsADBlobStore *this,
        DfsADBlobCache *a2,
        struct DfsRootFolder *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5,
        char a6,
        struct _BLOB_DATA *a7,
        struct _BLOB_DATA **a8,
        struct _BLOB_DATA **a9,
        unsigned __int8 *a10)
{
  DfsADBlobStore *v12; // r14
  char *v13; // r13
  char v14; // di
  const unsigned __int16 **v15; // r12
  unsigned int v16; // eax
  __int64 v17; // r8
  unsigned int NamedBlob; // ebx
  __int64 v19; // r9
  unsigned int *v20; // rcx
  __int64 v21; // rdx
  unsigned __int8 v22; // r15
  char v23; // al
  __int64 v24; // r8
  unsigned int v25; // eax
  unsigned int *v26; // rcx
  int v27; // edx
  struct _UNICODE_STRING *v28; // r9
  DfsGeneric *v29; // r14
  char *v30; // r12
  DfsADBlobCache *v31; // rdi
  DfsADBlobStore *v32; // rcx
  RPC_STATUS Metadata; // eax
  unsigned int *v34; // rcx
  int v35; // edx
  char *v36; // rax
  int v37; // edx
  DfsADBlobCache *v38; // r14
  DfsADBlobStore *v39; // rsi
  char v41; // [rsp+41h] [rbp-137h]
  char v42; // [rsp+42h] [rbp-136h]
  char v43; // [rsp+43h] [rbp-135h]
  unsigned __int8 v44[8]; // [rsp+48h] [rbp-130h] BYREF
  struct _DFS_NAME_INFORMATION_ *v45; // [rsp+50h] [rbp-128h] BYREF
  unsigned int v46; // [rsp+58h] [rbp-120h] BYREF
  DfsADBlobCache *v47; // [rsp+60h] [rbp-118h]
  DfsGeneric *v48; // [rsp+68h] [rbp-110h] BYREF
  __int128 v49; // [rsp+70h] [rbp-108h] BYREF
  struct _BLOB_DATA *v50; // [rsp+80h] [rbp-F8h] BYREF
  struct _BLOB_DATA *v51; // [rsp+88h] [rbp-F0h] BYREF
  DfsADBlobStore *v52; // [rsp+90h] [rbp-E8h]
  DfsADBlobCache *v53; // [rsp+98h] [rbp-E0h]
  __int128 v54; // [rsp+A0h] [rbp-D8h] BYREF
  unsigned __int8 *v55; // [rsp+B0h] [rbp-C8h]
  char *v56; // [rsp+B8h] [rbp-C0h]
  DfsADBlobStore *v57; // [rsp+C0h] [rbp-B8h]
  struct _UNICODE_STRING v58; // [rsp+C8h] [rbp-B0h] BYREF
  DfsRootFolder *v59; // [rsp+D8h] [rbp-A0h]
  const unsigned __int16 **v60; // [rsp+E0h] [rbp-98h]
  PCUNICODE_STRING v61; // [rsp+E8h] [rbp-90h]
  struct _BLOB_DATA **v62; // [rsp+F0h] [rbp-88h]
  struct _BLOB_DATA **v63; // [rsp+F8h] [rbp-80h]
  __int128 v64; // [rsp+100h] [rbp-78h] BYREF
  UNICODE_STRING Source; // [rsp+110h] [rbp-68h] BYREF
  UUID Uuid; // [rsp+120h] [rbp-58h] BYREF

  v59 = a3;
  v47 = a2;
  v12 = this;
  v52 = this;
  v57 = this;
  v53 = a2;
  v61 = a5;
  v62 = a8;
  v63 = a9;
  v55 = a10;
  v45 = 0;
  v51 = 0;
  v13 = 0;
  v56 = 0;
  v50 = 0;
  v54 = 0;
  Source = 0;
  v64 = 0;
  v58 = 0;
  v49 = 0;
  v48 = 0;
  Uuid = 0;
  v46 = 0;
  v44[0] = 0;
  v14 = 0;
  v42 = 0;
  v43 = 0;
  v41 = 0;
  v15 = (const unsigned __int16 **)((char *)a7 + 56);
  v60 = (const unsigned __int16 **)((char *)a7 + 56);
  DfsRtlInitUnicodeStringEx(&v49, 0);
  v16 = (*(__int64 (__fastcall **)(DfsADBlobStore *, DfsADBlobCache *, _QWORD, struct _DFS_NAME_INFORMATION_ **))(*(_QWORD *)v12 + 96LL))(
          v12,
          a2,
          *((_QWORD *)a7 + 8),
          &v45);
  NamedBlob = v16;
  v19 = 0;
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v20 = pWppControl;
      if ( pWppControl )
      {
        if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) )
        {
          v21 = 36;
LABEL_7:
          WPP_SF_D(*((_QWORD *)v20 + 2), v21, WPP_85082c1995493ee34407538da2d11b51_Traceguids, v16);
LABEL_8:
          v22 = 0;
LABEL_97:
          v19 = 0;
          goto LABEL_98;
        }
      }
    }
    goto LABEL_78;
  }
  DfsGetPathComponents((char *)v45 + 16, &Source, &v64, &v54);
  v19 = 0;
  if ( (_WORD)v54 )
  {
    if ( *((_QWORD *)&v54 + 1) )
    {
      if ( **((_WORD **)&v54 + 1) )
      {
        v23 = DfsPathPrefixUnicodeString(a4, &v54, v17);
        v19 = 0;
        if ( v23 )
        {
          v16 = DfsSubstitutePrefix(&Source, (__int64)a4, a5, (PUNICODE_STRING)v45 + 1);
          NamedBlob = v16;
          v19 = 0;
          if ( v16 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              v20 = pWppControl;
              if ( pWppControl )
              {
                if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) )
                {
                  v21 = 38;
                  goto LABEL_7;
                }
              }
            }
LABEL_78:
            v22 = 0;
            goto LABEL_98;
          }
          v43 = 1;
          DfsGetPathComponents((char *)v45 + 16, 0, 0, &v58);
          if ( (unsigned __int8)DfsPathPrefixUnicodeString(a4, &v58, v24) )
            goto LABEL_37;
          v25 = DfsRootFolder::ValidateLinkName(v59, &v58, v44, 1u, &v48, 0);
          NamedBlob = v25;
          v19 = 0;
          if ( v25 || (v14 = 1, (a6 & 1) == 0) )
            v14 = 0;
          if ( v25 == 1168 )
          {
LABEL_37:
            if ( !v14 )
            {
              v31 = v47;
              goto LABEL_46;
            }
          }
          else if ( !v14 )
          {
            if ( !v25 )
            {
              NamedBlob = 80;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && pWppControl
                && (pWppControl[7] & 0x820) != 0
                && *((_BYTE *)pWppControl + 25) >= 3u )
              {
                WPP_SF_Z(*((_QWORD *)pWppControl + 2), 39, WPP_85082c1995493ee34407538da2d11b51_Traceguids, &v58);
                goto LABEL_8;
              }
              goto LABEL_78;
            }
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_78;
            v26 = pWppControl;
            if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || *((_BYTE *)pWppControl + 25) < 3u )
              goto LABEL_78;
            v27 = 40;
            v28 = &v58;
LABEL_36:
            WPP_SF_ZD(
              *((_QWORD *)v26 + 2),
              v27,
              (unsigned int)WPP_85082c1995493ee34407538da2d11b51_Traceguids,
              (_DWORD)v28,
              v25);
            goto LABEL_8;
          }
          v29 = v48;
          v30 = (char *)v48 + 64;
          v31 = v47;
          NamedBlob = DfsADBlobCache::GetNamedBlob(v47, (struct _UNICODE_STRING *)v48 + 4, &v50);
          DfsGeneric::ReleaseReference(v29);
          v19 = 0;
          v48 = 0;
          if ( NamedBlob )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && pWppControl
              && (pWppControl[7] & 0x820) != 0
              && *((_BYTE *)pWppControl + 25) )
            {
              WPP_SF_DZ(
                *((_QWORD *)pWppControl + 2),
                41,
                (unsigned int)WPP_85082c1995493ee34407538da2d11b51_Traceguids,
                NamedBlob,
                (__int64)v30);
              goto LABEL_8;
            }
            goto LABEL_78;
          }
          v12 = v52;
          v15 = v60;
LABEL_46:
          v16 = DfsSubstitutePrefix(&Source, (__int64)a4, v61, (PUNICODE_STRING)v45 + 2);
          NamedBlob = v16;
          v19 = 0;
          if ( v16 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              v20 = pWppControl;
              if ( pWppControl )
              {
                if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) )
                {
                  v21 = 42;
                  goto LABEL_7;
                }
              }
            }
            goto LABEL_78;
          }
          v42 = 1;
          Metadata = DfsADBlobStore::GetMetadata(v32, v31, v15[1], 0, (void **)&v51, &v46);
          NamedBlob = Metadata;
          v19 = 0;
          if ( Metadata )
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_78;
            v34 = pWppControl;
            if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
              goto LABEL_78;
            v35 = 43;
          }
          else
          {
            Metadata = UuidCreate(&Uuid);
            NamedBlob = Metadata;
            v19 = 0;
            if ( !Metadata )
            {
              NamedBlob = (*(__int64 (__fastcall **)(DfsADBlobStore *, UUID *, __int128 *, _QWORD))(*(_QWORD *)v12 + 80LL))(
                            v12,
                            &Uuid,
                            &v49,
                            0);
              v19 = 0;
              if ( NamedBlob )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && pWppControl
                  && (pWppControl[7] & 0x820) != 0
                  && *((_BYTE *)pWppControl + 25) )
                {
                  WPP_SF_DZZ(*((_QWORD *)pWppControl + 2), 45, v17, NamedBlob, (__int64)a4, (__int64)&v49);
                  goto LABEL_8;
                }
                goto LABEL_78;
              }
              v36 = (char *)malloc(0x60u);
              v13 = v36;
              v56 = v36;
              v19 = 0;
              if ( !v36 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && pWppControl
                  && (pWppControl[7] & 0x820) != 0
                  && *((_BYTE *)pWppControl + 25) )
                {
                  WPP_SF_Z(*((_QWORD *)pWppControl + 2), 46, WPP_85082c1995493ee34407538da2d11b51_Traceguids, a4);
                  v19 = 0;
                }
                NamedBlob = 8;
                goto LABEL_78;
              }
              memset_0(v36, 0, 0x60u);
              v25 = DfsCreateUnicodeString(v13 + 56, &v49);
              NamedBlob = v25;
              v19 = 0;
              if ( !v25 )
              {
                v41 = 1;
                NamedBlob = DfsADBlobStore::SetMetadataNameInformationInBlob(
                              v12,
                              *((void **)v51 + 10),
                              v46,
                              v45,
                              (void **)v13 + 10,
                              (unsigned int *)v13 + 18);
                v19 = 0;
                if ( !NamedBlob )
                {
                  v22 = 1;
                  *v55 = 1;
                  *v62 = (struct _BLOB_DATA *)v13;
                  *v63 = v50;
                  goto LABEL_98;
                }
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && pWppControl
                  && (pWppControl[7] & 0x820) != 0
                  && *((_BYTE *)pWppControl + 25) )
                {
                  WPP_SF_DZZZ(
                    *((_QWORD *)pWppControl + 2),
                    v37,
                    v17,
                    NamedBlob,
                    (__int64)a4,
                    (__int64)v15,
                    (__int64)&v49);
                  goto LABEL_8;
                }
                goto LABEL_78;
              }
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_78;
              v26 = pWppControl;
              if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
                goto LABEL_78;
              v27 = 47;
              v28 = (struct _UNICODE_STRING *)&v49;
              goto LABEL_36;
            }
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_78;
            v34 = pWppControl;
            if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
              goto LABEL_78;
            v35 = 44;
          }
          WPP_SF_DZZ(*((_QWORD *)v34 + 2), v35, v17, Metadata, (__int64)a4, (__int64)v15);
          goto LABEL_8;
        }
      }
    }
  }
  NamedBlob = 0;
  v22 = 0;
  *v55 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_Z(*((_QWORD *)pWppControl + 2), 37, WPP_85082c1995493ee34407538da2d11b51_Traceguids, &v54);
    goto LABEL_97;
  }
LABEL_98:
  if ( v22 )
  {
    v38 = v47;
  }
  else
  {
    if ( v13 )
    {
      if ( v41 )
        DfsFreeUnicodeString(v13 + 56);
      free(v13);
      v19 = 0;
    }
    v38 = v47;
    if ( v50 )
    {
      DfsADBlobCache::ReleaseBlobCacheReference(v47, v50);
      v19 = 0;
    }
  }
  v39 = v52;
  if ( *((_QWORD *)&v49 + 1) )
  {
    (*(void (__fastcall **)(DfsADBlobStore *, __int128 *, __int64, _QWORD))(*(_QWORD *)v52 + 88LL))(v52, &v49, v17, 0);
    v19 = 0;
  }
  if ( v51 )
  {
    DfsADBlobCache::ReleaseBlobCacheReference(v38, v51);
    v19 = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(DfsADBlobStore *, char *, __int64, _QWORD))(*(_QWORD *)v39 + 216LL))(
      v39,
      (char *)v45 + 32,
      v17,
      0);
    v19 = 0;
  }
  if ( v43 )
    (*(void (__fastcall **)(DfsADBlobStore *, char *, __int64, _QWORD))(*(_QWORD *)v39 + 216LL))(
      v39,
      (char *)v45 + 16,
      v17,
      0);
  if ( v45 )
    (*(void (__fastcall **)(DfsADBlobStore *, DfsADBlobCache *, struct _DFS_NAME_INFORMATION_ *, __int64))(*(_QWORD *)v39 + 104LL))(
      v39,
      v38,
      v45,
      v19);
  if ( v48 )
    DfsGeneric::ReleaseReference(v48);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_dD(*((_QWORD *)pWppControl + 2), 49, WPP_85082c1995493ee34407538da2d11b51_Traceguids, NamedBlob, v22);
  }
  return NamedBlob;
}

```

## disassembly

```asm
0x14000e39c  mov     r11, rsp
0x14000e39f  push    rbx
0x14000e3a0  push    rsi
0x14000e3a1  push    rdi
0x14000e3a2  push    r12
0x14000e3a4  push    r13
0x14000e3a6  push    r14
0x14000e3a8  push    r15
0x14000e3aa  sub     rsp, 140h
0x14000e3b1  mov     rax, cs:__security_cookie
0x14000e3b8  xor     rax, rsp
0x14000e3bb  mov     [rsp+178h+var_48], rax
0x14000e3c3  mov     r15, r9
0x14000e3c6  mov     [rsp+178h+var_A0], r8
0x14000e3ce  mov     rbx, rdx
0x14000e3d1  mov     [rsp+178h+var_118], rdx
0x14000e3d6  mov     r14, rcx
0x14000e3d9  mov     [rsp+178h+var_E8], rcx
0x14000e3e1  mov     [rsp+178h+var_B8], rcx
0x14000e3e9  mov     [rsp+178h+var_E0], rdx
0x14000e3f1  mov     rsi, [rsp+178h+arg_20]
0x14000e3f9  mov     [rsp+178h+var_90], rsi
0x14000e401  mov     rax, [rsp+178h+arg_30]
0x14000e409  mov     rcx, [rsp+178h+arg_38]
0x14000e411  mov     [rsp+178h+var_88], rcx
0x14000e419  mov     rcx, [rsp+178h+arg_40]
0x14000e421  mov     [rsp+178h+var_80], rcx
0x14000e429  mov     rcx, [rsp+178h+arg_48]
0x14000e431  mov     [rsp+178h+var_C8], rcx
0x14000e439  xor     ecx, ecx
0x14000e43b  mov     [rsp+178h+var_128], rcx
0x14000e440  mov     [r11-0F0h], rcx
0x14000e447  mov     r13d, ecx
0x14000e44a  mov     [r11-0C0h], rcx
0x14000e451  mov     [r11-0F8h], rcx
0x14000e458  xorps   xmm0, xmm0
0x14000e45b  movups  [rsp+178h+var_D8], xmm0
0x14000e463  xorps   xmm1, xmm1
0x14000e466  movups  xmmword ptr [r11-68h], xmm1
0x14000e46b  movups  xmmword ptr [r11-78h], xmm0
0x14000e470  movups  xmmword ptr [rsp+178h+var_B0.Length], xmm1
0x14000e478  movups  [rsp+178h+var_108], xmm0
0x14000e47d  mov     [rsp+178h+var_110], rcx
0x14000e482  movups  xmmword ptr [r11-58h], xmm1
0x14000e487  mov     [rsp+178h+var_120], ecx
0x14000e48b  mov     [rsp+178h+var_130], cl
0x14000e48f  mov     [rsp+178h+var_138], cl
0x14000e493  mov     dil, cl
0x14000e496  mov     [rsp+178h+var_136], cl
0x14000e49a  mov     [rsp+178h+var_135], cl
0x14000e49e  mov     [rsp+178h+var_137], cl
0x14000e4a2  lea     r12, [rax+38h]
0x14000e4a6  mov     [rsp+178h+var_98], r12
0x14000e4ae  xor     edx, edx
0x14000e4b0  lea     rcx, [rsp+178h+var_108]
0x14000e4b5  call    DfsRtlInitUnicodeStringEx
0x14000e4ba  nop
0x14000e4bb  mov     rax, [r14]
0x14000e4be  lea     r9, [rsp+178h+var_128]
0x14000e4c3  mov     r8, [r12+8]
0x14000e4c8  mov     rdx, rbx
0x14000e4cb  mov     rcx, r14
0x14000e4ce  mov     rax, [rax+60h]
0x14000e4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4d7  mov     ebx, eax
0x14000e4d9  mov     [rsp+178h+var_134], eax
0x14000e4dd  xor     r9d, r9d
0x14000e4e0  test    eax, eax
0x14000e4e2  jz      short loc_14000E543
0x14000e4e4  lea     rdi, WPP_GLOBAL_Control
0x14000e4eb  cmp     cs:WPP_GLOBAL_Control, rdi
0x14000e4f2  jz      loc_14000EACA
0x14000e4f8  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e4ff  test    rcx, rcx
0x14000e502  jz      loc_14000EACA
0x14000e508  test    dword ptr [rcx+1Ch], 820h
0x14000e50f  jz      loc_14000EACA
0x14000e515  lea     esi, [r13+1]
0x14000e519  cmp     [rcx+19h], sil
0x14000e51d  jb      loc_14000EACA
0x14000e523  lea     edx, [rsi+23h]
0x14000e526  mov     r9d, eax
0x14000e529  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000e530  mov     rcx, [rcx+10h]
0x14000e534  call    WPP_SF_D
0x14000e539  mov     r15b, [rsp+178h+var_138]
0x14000e53e  jmp     loc_14000EC70
0x14000e543  mov     rcx, [rsp+178h+var_128]
0x14000e548  add     rcx, 10h
0x14000e54c  lea     r9, [rsp+178h+var_D8]
0x14000e554  lea     r8, [rsp+178h+var_78]
0x14000e55c  lea     rdx, [rsp+178h+Source]
0x14000e564  call    DfsGetPathComponents
0x14000e569  xor     r9d, r9d
0x14000e56c  cmp     word ptr [rsp+178h+var_D8], r9w
0x14000e575  jz      loc_14000EC11
0x14000e57b  mov     rax, qword ptr [rsp+178h+var_D8+8]
0x14000e583  test    rax, rax
0x14000e586  jz      loc_14000EC11
0x14000e58c  cmp     [rax], r9w
0x14000e590  jz      loc_14000EC11
0x14000e596  lea     rdx, [rsp+178h+var_D8]
0x14000e59e  mov     rcx, r15
0x14000e5a1  call    DfsPathPrefixUnicodeString
0x14000e5a6  xor     r9d, r9d
0x14000e5a9  test    al, al
0x14000e5ab  jz      loc_14000EC11
0x14000e5b1  mov     rax, [rsp+178h+var_128]
0x14000e5b6  add     rax, 10h
0x14000e5ba  mov     [rsp+178h+Destination], rax; Destination
0x14000e5bf  mov     [rsp+178h+var_150], rsi; PCUNICODE_STRING
0x14000e5c4  mov     [rsp+178h+var_158], r15; __int64
0x14000e5c9  lea     r9, [rsp+178h+var_D8]
0x14000e5d1  lea     r8, [rsp+178h+var_78]
0x14000e5d9  mov     esi, 1
0x14000e5de  mov     edx, esi
0x14000e5e0  lea     rcx, [rsp+178h+Source]; Source
0x14000e5e8  call    DfsSubstitutePrefix
0x14000e5ed  mov     ebx, eax
0x14000e5ef  mov     [rsp+178h+var_134], eax
0x14000e5f3  xor     r9d, r9d
0x14000e5f6  test    eax, eax
0x14000e5f8  jz      short loc_14000E63D
0x14000e5fa  lea     rdi, WPP_GLOBAL_Control
0x14000e601  cmp     cs:WPP_GLOBAL_Control, rdi
0x14000e608  jz      loc_14000EACA
0x14000e60e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e615  test    rcx, rcx
0x14000e618  jz      loc_14000EACA
0x14000e61e  test    dword ptr [rcx+1Ch], 820h
0x14000e625  jz      loc_14000EACA
0x14000e62b  cmp     [rcx+19h], sil
0x14000e62f  jb      loc_14000EACA
0x14000e635  lea     edx, [rsi+25h]
0x14000e638  jmp     loc_14000E526
0x14000e63d  mov     [rsp+178h+var_135], sil
0x14000e642  mov     rcx, [rsp+178h+var_128]
0x14000e647  add     rcx, 10h
0x14000e64b  lea     r9, [rsp+178h+var_B0]
0x14000e653  xor     r8d, r8d
0x14000e656  xor     edx, edx
0x14000e658  call    DfsGetPathComponents
0x14000e65d  lea     rdx, [rsp+178h+var_B0]
0x14000e665  mov     rcx, r15
0x14000e668  call    DfsPathPrefixUnicodeString
0x14000e66d  xor     r9d, r9d
0x14000e670  test    al, al
0x14000e672  jnz     loc_14000E79C
0x14000e678  mov     byte ptr [rsp+178h+var_150], r9b; unsigned __int8
0x14000e67d  lea     rax, [rsp+178h+var_110]
0x14000e682  mov     [rsp+178h+var_158], rax; struct DfsFolder **
0x14000e687  mov     r9b, sil; unsigned __int8
0x14000e68a  lea     r8, [rsp+178h+var_130]; unsigned __int8 *
0x14000e68f  lea     rdx, [rsp+178h+var_B0]; struct _UNICODE_STRING *
0x14000e697  mov     rcx, [rsp+178h+var_A0]; this
0x14000e69f  call    ?ValidateLinkName@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@PEAEEPEAPEAVDfsFolder@@E@Z; DfsRootFolder::ValidateLinkName(_UNICODE_STRING *,uchar *,uchar,DfsFolder * *,uchar)
0x14000e6a4  mov     ebx, eax
0x14000e6a6  mov     [rsp+178h+var_134], eax
0x14000e6aa  xor     r9d, r9d
0x14000e6ad  test    eax, eax
0x14000e6af  jnz     short loc_14000E6BE
0x14000e6b1  test    [rsp+178h+arg_28], sil
0x14000e6b9  mov     dil, sil
0x14000e6bc  jnz     short loc_14000E6C1
0x14000e6be  mov     dil, r9b
0x14000e6c1  cmp     eax, 490h
0x14000e6c6  jz      loc_14000E7A4
0x14000e6cc  test    dil, dil
0x14000e6cf  jnz     loc_14000E7AD
0x14000e6d5  test    eax, eax
0x14000e6d7  jnz     short loc_14000E73B
0x14000e6d9  lea     ebx, [rax+50h]
0x14000e6dc  mov     [rsp+178h+var_134], ebx
0x14000e6e0  lea     rdi, WPP_GLOBAL_Control
0x14000e6e7  cmp     cs:WPP_GLOBAL_Control, rdi
0x14000e6ee  jz      loc_14000EACA
0x14000e6f4  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e6fb  test    rcx, rcx
0x14000e6fe  jz      loc_14000EACA
0x14000e704  test    dword ptr [rcx+1Ch], 820h
0x14000e70b  jz      loc_14000EACA
0x14000e711  cmp     byte ptr [rcx+19h], 3
0x14000e715  jb      loc_14000EACA
0x14000e71b  lea     edx, [rax+27h]
0x14000e71e  lea     r9, [rsp+178h+var_B0]
0x14000e726  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000e72d  mov     rcx, [rcx+10h]
0x14000e731  call    WPP_SF_Z
0x14000e736  jmp     loc_14000E539
0x14000e73b  lea     rdi, WPP_GLOBAL_Control
0x14000e742  cmp     cs:WPP_GLOBAL_Control, rdi
0x14000e749  jz      loc_14000EACA
0x14000e74f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e756  test    rcx, rcx
0x14000e759  jz      loc_14000EACA
0x14000e75f  test    dword ptr [rcx+1Ch], 820h
0x14000e766  jz      loc_14000EACA
0x14000e76c  cmp     byte ptr [rcx+19h], 3
0x14000e770  jb      loc_14000EACA
0x14000e776  mov     edx, 28h ; '('
0x14000e77b  lea     r9, [rsp+178h+var_B0]
0x14000e783  mov     dword ptr [rsp+178h+var_158], eax
0x14000e787  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000e78e  mov     rcx, [rcx+10h]
0x14000e792  call    WPP_SF_ZD
0x14000e797  jmp     loc_14000E539
0x14000e79c  mov     [rsp+178h+var_134], 490h
0x14000e7a4  test    dil, dil
0x14000e7a7  jz      loc_14000E856
0x14000e7ad  mov     r14, [rsp+178h+var_110]
0x14000e7b2  lea     r12, [r14+40h]
0x14000e7b6  lea     r8, [rsp+178h+var_F8]; struct _BLOB_DATA **
0x14000e7be  mov     rdx, r12; struct _UNICODE_STRING *
0x14000e7c1  mov     rdi, [rsp+178h+var_118]
0x14000e7c6  mov     rcx, rdi; this
0x14000e7c9  call    ?GetNamedBlob@DfsADBlobCache@@QEAAKPEAU_UNICODE_STRING@@PEAPEAU_BLOB_DATA@@@Z; DfsADBlobCache::GetNamedBlob(_UNICODE_STRING *,_BLOB_DATA * *)
0x14000e7ce  mov     ebx, eax
0x14000e7d0  mov     [rsp+178h+var_134], eax
0x14000e7d4  mov     rcx, r14; this
0x14000e7d7  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14000e7dc  xor     r9d, r9d
0x14000e7df  mov     [rsp+178h+var_110], r9
0x14000e7e4  test    ebx, ebx
0x14000e7e6  jz      short loc_14000E844
0x14000e7e8  lea     rdi, WPP_GLOBAL_Control
0x14000e7ef  cmp     cs:WPP_GLOBAL_Control, rdi
0x14000e7f6  jz      loc_14000EACA
0x14000e7fc  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e803  test    rcx, rcx
0x14000e806  jz      loc_14000EACA
0x14000e80c  test    dword ptr [rcx+1Ch], 820h
0x14000e813  jz      loc_14000EACA
0x14000e819  cmp     [rcx+19h], sil
0x14000e81d  jb      loc_14000EACA
0x14000e823  lea     edx, [r9+29h]
0x14000e827  mov     [rsp+178h+var_158], r12
0x14000e82c  mov     r9d, ebx
0x14000e82f  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000e836  mov     rcx, [rcx+10h]
0x14000e83a  call    WPP_SF_DZ
0x14000e83f  jmp     loc_14000E539
0x14000e844  mov     r14, [rsp+178h+var_E8]
0x14000e84c  mov     r12, [rsp+178h+var_98]
0x14000e854  jmp     short loc_14000E85B
0x14000e856  mov     rdi, [rsp+178h+var_118]
0x14000e85b  mov     rax, [rsp+178h+var_128]
0x14000e860  add     rax, 20h ; ' '
0x14000e864  mov     [rsp+178h+Destination], rax; Destination
0x14000e869  mov     rax, [rsp+178h+var_90]
0x14000e871  mov     [rsp+178h+var_150], rax; PCUNICODE_STRING
0x14000e876  mov     [rsp+178h+var_158], r15; __int64
0x14000e87b  lea     r9, [rsp+178h+var_D8]
0x14000e883  lea     r8, [rsp+178h+var_78]
0x14000e88b  mov     edx, esi
0x14000e88d  lea     rcx, [rsp+178h+Source]; Source
0x14000e895  call    DfsSubstitutePrefix
0x14000e89a  mov     ebx, eax
0x14000e89c  mov     [rsp+178h+var_134], eax
0x14000e8a0  xor     r9d, r9d; unsigned __int16 *
0x14000e8a3  test    eax, eax
0x14000e8a5  jz      short loc_14000E8EB
0x14000e8a7  lea     rdi, WPP_GLOBAL_Control
0x14000e8ae  cmp     cs:WPP_GLOBAL_Control, rdi
0x14000e8b5  jz      loc_14000EACA
0x14000e8bb  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e8c2  test    rcx, rcx
0x14000e8c5  jz      loc_14000EACA
0x14000e8cb  test    dword ptr [rcx+1Ch], 820h
0x14000e8d2  jz      loc_14000EACA
0x14000e8d8  cmp     [rcx+19h], sil
0x14000e8dc  jb      loc_14000EACA
0x14000e8e2  lea     edx, [r9+2Ah]
0x14000e8e6  jmp     loc_14000E526
0x14000e8eb  mov     [rsp+178h+var_136], sil
0x14000e8f0  lea     rax, [rsp+178h+var_120]
0x14000e8f5  mov     [rsp+178h+var_150], rax; unsigned int *
0x14000e8fa  lea     rax, [rsp+178h+var_F0]
0x14000e902  mov     [rsp+178h+var_158], rax; void **
0x14000e907  mov     r8, [r12+8]; unsigned __int16 *
0x14000e90c  mov     rdx, rdi; void *
0x14000e90f  call    ?GetMetadata@DfsADBlobStore@@QEAAKPEAXPEBG1PEAPEAXPEAK@Z; DfsADBlobStore::GetMetadata(void *,ushort const *,ushort const *,void * *,ulong *)
0x14000e914  mov     ebx, eax
0x14000e916  mov     [rsp+178h+var_134], eax
0x14000e91a  xor     r9d, r9d
0x14000e91d  test    eax, eax
0x14000e91f  jz      short loc_14000E97B
0x14000e921  lea     rdi, WPP_GLOBAL_Control
0x14000e928  cmp     cs:WPP_GLOBAL_Control, rdi
0x14000e92f  jz      loc_14000EACA
0x14000e935  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e93c  test    rcx, rcx
0x14000e93f  jz      loc_14000EACA
0x14000e945  test    dword ptr [rcx+1Ch], 820h
0x14000e94c  jz      loc_14000EACA
0x14000e952  cmp     [rcx+19h], sil
0x14000e956  jb      loc_14000EACA
0x14000e95c  lea     edx, [r9+2Bh]
0x14000e960  mov     [rsp+178h+var_150], r12
0x14000e965  mov     r9d, eax
0x14000e968  mov     [rsp+178h+var_158], r15
  ... truncated ...
```
