# DfsStore::GetStoreApiInformation(unsigned __int64,DfsRootFolder *,_UNICODE_STRING *,ushort *,ulong,uchar *,long *,long *,uchar * *,_HEAP_ALLOCATOR *)

- ea: `0x140037d08`
- end: `0x140038901`
- name: `?GetStoreApiInformation@DfsStore@@QEAAK_KPEAVDfsRootFolder@@PEAU_UNICODE_STRING@@PEAGKPEAEPEAJ5PEAPEAEPEAU_HEAP_ALLOCATOR@@@Z`
- size: `3065`
- prototype: `unsigned int __fastcall(DfsStore *__hidden this, unsigned __int64, struct DfsRootFolder *, struct _UNICODE_STRING *, unsigned __int16 *, unsigned int, unsigned __int8 *, int *, int *, unsigned __int8 **, struct _HEAP_ALLOCATOR *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cc80`
- `0x140022a50`
- `0x14002aa28`
- `0x140046150`

## callees

- `0x140030b48`
- `0x140037d08`
- `0x14003a920`
- `0x14005ce22`
- `0x14005ce3a`
- `0x14005e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140038082`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14003816c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400381b6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140038082`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14003816c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400381b6`

## pseudocode

```c
__int64 __fastcall DfsStore::GetStoreApiInformation(
        DfsStore *this,
        __int64 a2,
        struct DfsRootFolder *a3,
        struct _UNICODE_STRING *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        int *a8,
        int *a9,
        unsigned __int8 **a10,
        struct _HEAP_ALLOCATOR *a11)
{
  int v11; // r14d
  int v14; // esi
  int v15; // r15d
  int v16; // edi
  int v17; // r12d
  unsigned int v18; // ebx
  int v19; // r13d
  unsigned int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r10
  __int64 v23; // r9
  int v24; // r8d
  _WORD *v25; // rax
  int v26; // ecx
  int v27; // eax
  int v28; // r13d
  unsigned int v29; // edi
  __int128 v30; // xmm0
  int v31; // ecx
  __int64 v32; // r9
  int v33; // r8d
  _WORD *v34; // rax
  int v35; // ecx
  void *v36; // rcx
  DWORD v37; // esi
  __int64 v38; // r9
  int v39; // r8d
  _WORD *v40; // rax
  int v41; // ecx
  void *v42; // rcx
  DWORD SecurityDescriptorLength; // esi
  void *v44; // rcx
  int v45; // ecx
  size_t v46; // r12
  unsigned __int8 *v47; // rsi
  size_t v48; // r8
  unsigned __int8 *v49; // r15
  __int64 v50; // r13
  unsigned int v51; // ebx
  unsigned int v52; // ebx
  unsigned int v53; // ebx
  unsigned int v54; // ebx
  unsigned int v55; // ebx
  unsigned int v56; // ecx
  __int64 v57; // rax
  unsigned __int64 v58; // rbx
  __int64 v59; // rdi
  unsigned __int8 v60; // cl
  unsigned __int16 v61; // r9
  size_t v62; // r8
  __int64 v63; // r9
  const void *v64; // r10
  void *v65; // r11
  size_t v66; // r8
  unsigned __int8 *v67; // rbx
  unsigned int v68; // r12d
  __int64 v69; // r8
  unsigned __int64 v70; // rax
  int v71; // ecx
  PWSTR Buffer; // rdx
  __int64 v73; // rdi
  size_t v74; // r8
  __int64 v75; // rbx
  __int64 v76; // r9
  unsigned __int8 *v77; // rcx
  int v78; // eax
  unsigned __int8 *v79; // rcx
  size_t v80; // r8
  size_t v81; // r12
  unsigned __int8 *v82; // r8
  unsigned int v83; // ebx
  unsigned int v84; // ebx
  unsigned int v85; // ebx
  unsigned int v86; // ebx
  DWORD v87; // edi
  unsigned int v88; // ecx
  __int64 v89; // rax
  unsigned __int64 v90; // rbx
  __int64 v91; // rdi
  unsigned __int8 v92; // cl
  unsigned __int16 v93; // r9
  size_t v94; // r8
  __int64 v95; // r9
  const void *v96; // r10
  void *v97; // r11
  int v98; // eax
  size_t v99; // r8
  __int64 v100; // rdi
  size_t v101; // r8
  unsigned __int64 v102; // rbx
  void *v103; // rcx
  __int64 v105; // [rsp+38h] [rbp-91h] BYREF
  int v106; // [rsp+40h] [rbp-89h]
  unsigned int v107; // [rsp+44h] [rbp-85h]
  DWORD v108; // [rsp+48h] [rbp-81h]
  __int64 v109; // [rsp+50h] [rbp-79h] BYREF
  size_t v110; // [rsp+58h] [rbp-71h]
  struct _UNICODE_STRING v111; // [rsp+60h] [rbp-69h] BYREF
  _BYTE Src[16]; // [rsp+78h] [rbp-51h] BYREF
  int v113; // [rsp+88h] [rbp-41h]
  int v114; // [rsp+8Ch] [rbp-3Dh]
  __int128 v115; // [rsp+90h] [rbp-39h]
  int v116; // [rsp+A0h] [rbp-29h]
  unsigned int v117; // [rsp+A8h] [rbp-21h]
  unsigned int v118; // [rsp+B8h] [rbp-11h]
  unsigned int v123; // [rsp+150h] [rbp+87h]
  unsigned int v124; // [rsp+150h] [rbp+87h]

  v11 = 0;
  v105 = 0;
  v109 = 0;
  v14 = *a8;
  v15 = 80;
  v108 = 0;
  *a10 = 0;
  v16 = 0;
  v17 = 0;
  v106 = 0;
  v111 = 0;
  LODWORD(v110) = v14;
  *a9 = 0;
  *a8 = 0;
  memset_0(Src, 0, 0x50u);
  v18 = (*(__int64 (__fastcall **)(DfsStore *, __int64, unsigned __int16 *, __int64 *))(*(_QWORD *)this + 96LL))(
          this,
          a2,
          a5,
          &v105);
  if ( !v18 )
  {
    (*(void (__fastcall **)(DfsStore *, __int64, struct _UNICODE_STRING *))(*(_QWORD *)this + 224LL))(
      this,
      v105 + 16,
      &v111);
    v19 = a4->Length + v111.Length + 8;
    v107 = (*(__int64 (__fastcall **)(DfsStore *, __int64, unsigned __int16 *, __int64 *))(*(_QWORD *)this + 120LL))(
             this,
             a2,
             a5,
             &v109);
    v18 = v107;
    if ( v107 )
    {
LABEL_169:
      (*(void (__fastcall **)(DfsStore *, __int64, __int64))(*(_QWORD *)this + 104LL))(this, a2, v105);
      return v18;
    }
    v20 = a6;
    v21 = 16;
    if ( a6 <= 7 )
    {
      if ( a6 != 7 )
      {
        if ( a6 == 1 )
        {
          v15 = 8;
          v106 = 0;
        }
        else
        {
          v22 = v105;
          if ( a6 == 2 )
          {
            v15 = 24;
            v113 = *(_DWORD *)(v105 + 64);
            v114 = *(_DWORD *)(v109 + 12);
          }
          else
          {
            switch ( a6 )
            {
              case 3u:
                v15 = 32;
                v113 = *(_DWORD *)(v105 + 64);
                v31 = *(_DWORD *)(v109 + 12);
                v114 = v31;
                break;
              case 4u:
                v15 = 56;
                v30 = *(_OWORD *)(v105 + 48);
                v114 = *(_DWORD *)(v105 + 112);
                v113 = *(_DWORD *)(v105 + 64);
                v115 = v30;
                v31 = *(_DWORD *)(v109 + 12);
                v116 = v31;
                break;
              case 5u:
                v15 = 56;
                v16 = v19 + *(unsigned __int16 *)(v105 + 72) + 2;
                v117 = *(_DWORD *)(v109 + 12);
                goto LABEL_23;
              case 6u:
                v15 = 64;
                v117 = *(_DWORD *)(v109 + 12);
                v17 = 32 * v117;
                v106 = 32 * v117;
                if ( v117 )
                {
                  v21 = *(_QWORD *)(v109 + 16) + 48LL;
                  v23 = v117;
                  do
                  {
                    v24 = *(_DWORD *)(v21 - 16);
                    v25 = *(_WORD **)(v21 - 8);
                    if ( (_WORD)v24 == 2 && *v25 == 46 || (_WORD)v24 == 4 && *v25 == 46 && !v25[1] )
                      v24 = *(_DWORD *)&a4->Length;
                    v26 = *(unsigned __int16 *)v21;
                    v21 += 64;
                    v16 += (unsigned __int16)v24 + v26 + 4;
                    --v23;
                  }
                  while ( v23 );
                  v20 = a6;
                  v22 = v105;
                  v14 = v110;
                }
                v27 = v19 + *(unsigned __int16 *)(v22 + 72);
                v28 = 32 * v117;
                v29 = v16 + 2;
                goto LABEL_76;
              default:
LABEL_42:
                v18 = 87;
                goto LABEL_168;
            }
            v17 = 24 * v31;
            v106 = 24 * v31;
            if ( *(_DWORD *)(v109 + 12) )
            {
              v32 = *(unsigned int *)(v109 + 12);
              v21 = *(_QWORD *)(v109 + 16) + 48LL;
              do
              {
                v33 = *(_DWORD *)(v21 - 16);
                v34 = *(_WORD **)(v21 - 8);
                if ( (_WORD)v33 == 2 && *v34 == 46 || (_WORD)v33 == 4 && *v34 == 46 && !v34[1] )
                  v33 = *(_DWORD *)&a4->Length;
                v35 = *(unsigned __int16 *)v21;
                v21 += 64;
                v16 += (unsigned __int16)v33 + v35 + 4;
                --v32;
              }
              while ( v32 );
              v20 = a6;
              v22 = v105;
              v14 = v110;
              v106 = v17;
            }
          }
          v16 += *(unsigned __int16 *)(v22 + 72) + 2;
        }
        v16 += v19;
        v28 = v17;
        goto LABEL_77;
      }
      if ( (*(_DWORD *)(v105 + 64) & 0x300) == 0 )
        goto LABEL_42;
LABEL_41:
      v15 = 16;
LABEL_23:
      v28 = 0;
LABEL_77:
      v45 = v15 + v17 + v16;
      v46 = v45;
      v110 = v45;
      *a9 = v45;
      if ( !a11 )
        goto LABEL_167;
      if ( v45 <= v14 )
      {
        v47 = a7;
        if ( a7 )
        {
          *a8 = v45;
          goto LABEL_81;
        }
      }
      v47 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD, __int64))a11)(v45, v21);
      a7 = v47;
      *a10 = v47;
      *a8 = 0;
      if ( v47 )
      {
LABEL_81:
        memset_0(v47, 0, v46);
        v48 = v15;
        v49 = &v47[v15 + (__int64)v106];
        v50 = (unsigned __int64)&v47[v48] & -(__int64)(v28 != 0);
        memcpy_0(v47, Src, v48);
        if ( v20 > 7 )
        {
          v83 = v20 - 8;
          if ( v83 )
          {
            v84 = v83 - 1;
            if ( v84 )
            {
              v85 = v84 - 41;
              if ( v85 )
              {
                v86 = v85 - 50;
                if ( v86 )
                {
                  if ( v86 == 50 )
                  {
                    v87 = v108;
                    if ( v108 )
                    {
                      *((_QWORD *)v47 + 1) = v49;
                      memcpy_0(v49, *(const void **)(v105 + 128), v87);
                    }
                    else
                    {
                      *((_QWORD *)v47 + 1) = 0;
                    }
                    *(_DWORD *)v47 = v87;
                  }
                }
                else
                {
                  *(_QWORD *)v47 = v49;
                  memcpy_0(v49, *(const void **)(v105 + 80), *(unsigned __int16 *)(v105 + 72));
                }
              }
              else
              {
                *(_DWORD *)v47 = *(_DWORD *)(v105 + 136);
                *((_DWORD *)v47 + 1) = *(_DWORD *)(v105 + 140);
                *((_QWORD *)v47 + 1) = *((_QWORD *)a3 + 29);
              }
              goto LABEL_167;
            }
            *((_QWORD *)v47 + 9) = v50;
            v88 = 0;
            v89 = v109;
            v124 = 0;
            if ( *(_DWORD *)(v109 + 12) )
            {
              do
              {
                v90 = *(_QWORD *)(v89 + 16) + ((unsigned __int64)v88 << 6);
                v91 = 32LL * v88;
                *(_DWORD *)(v91 + v50) = *(_DWORD *)(v90 + 20);
                if ( *(_DWORD *)(v90 + 16) )
                  v92 = 0;
                else
                  v92 = *(_BYTE *)(v90 + 12);
                DfsTargetPriority::UnpackTargetPriority(v92, (struct _DFS_TARGET_PRIORITY *)(v91 + v50 + 24));
                v94 = v93;
                *(_QWORD *)(v91 + v50 + 8) = v49;
                v95 = (__int64)&v49[v93 + 2];
                *(_QWORD *)(v91 + v50 + 16) = v95;
                v49 = (unsigned __int8 *)(v95 + 2 + *(unsigned __int16 *)(v90 + 48));
                memcpy_0(v97, v96, v94);
                memcpy_0(*(void **)(v91 + v50 + 16), *(const void **)(v90 + 56), *(unsigned __int16 *)(v90 + 48));
                v89 = v109;
                v88 = v124 + 1;
                v124 = v88;
              }
              while ( v88 < *(_DWORD *)(v109 + 12) );
              v47 = a7;
              v46 = v110;
            }
          }
          *((_DWORD *)v47 + 5) = *(_DWORD *)(v105 + 112);
          *((_DWORD *)v47 + 4) = *(_DWORD *)(v105 + 64);
          *(_OWORD *)(v47 + 24) = *(_OWORD *)(v105 + 48);
          if ( (*(_BYTE *)(v105 + 68) & 0x20) != 0 )
            *((_DWORD *)v47 + 10) |= 1u;
          if ( (*(_DWORD *)(v105 + 68) & 0x200) != 0 )
            *((_DWORD *)v47 + 10) |= 2u;
          if ( (*(_BYTE *)(v105 + 68) & 0x40) != 0 )
            *((_DWORD *)v47 + 10) |= 4u;
          if ( (*(_DWORD *)(v105 + 68) & 0x8000) != 0 )
            *((_DWORD *)v47 + 10) |= 8u;
          if ( *((_BYTE *)a3 + 450) )
            *((_DWORD *)v47 + 10) |= 0x10u;
          if ( (*(_DWORD *)(v105 + 68) & 0x10000) != 0 )
            *((_DWORD *)v47 + 10) |= 0x20u;
          if ( a5 )
            v98 = 0;
          else
            v98 = (*(__int64 (__fastcall **)(struct DfsRootFolder *))(*(_QWORD *)a3 + 72LL))(a3);
          *((_DWORD *)v47 + 11) = v98;
          *((_QWORD *)v47 + 1) = v49;
          v99 = *(unsigned __int16 *)(v105 + 72);
          v67 = &v49[v99 + 2];
          memcpy_0(v49, *(const void **)(v105 + 80), v99);
          v100 = v108;
          if ( v108 )
          {
            v101 = v108;
            v102 = (unsigned __int64)(v67 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            *((_QWORD *)v47 + 7) = v102;
            v103 = (void *)v102;
            v67 = (unsigned __int8 *)(v100 + v102);
            memcpy_0(v103, *(const void **)(v105 + 128), v101);
          }
          else
          {
            *((_QWORD *)v47 + 7) = 0;
          }
          *((_DWORD *)v47 + 12) = v100;
          goto LABEL_165;
        }
        if ( v20 == 7 )
        {
          (*(void (__fastcall **)(DfsStore *, __int64, unsigned __int8 *))(*(_QWORD *)this + 48LL))(this, a2, v47);
          goto LABEL_167;
        }
        v51 = v20 - 1;
        if ( v51 )
        {
          v52 = v51 - 1;
          if ( v52 )
          {
            v53 = v52 - 1;
            if ( v53 )
            {
              v54 = v53 - 1;
              if ( v54 )
              {
                v55 = v54 - 1;
                if ( !v55 )
                {
LABEL_97:
                  *((_DWORD *)v47 + 5) = *(_DWORD *)(v105 + 112);
                  *((_DWORD *)v47 + 4) = *(_DWORD *)(v105 + 64);
                  *(_OWORD *)(v47 + 24) = *(_OWORD *)(v105 + 48);
                  if ( (*(_BYTE *)(v105 + 68) & 0x20) != 0 )
                    *((_DWORD *)v47 + 10) |= 1u;
                  if ( (*(_DWORD *)(v105 + 68) & 0x200) != 0 )
                    *((_DWORD *)v47 + 10) |= 2u;
                  if ( (*(_BYTE *)(v105 + 68) & 0x40) != 0 )
                    *((_DWORD *)v47 + 10) |= 4u;
                  if ( (*(_DWORD *)(v105 + 68) & 0x8000) != 0 )
                    *((_DWORD *)v47 + 10) |= 8u;
                  if ( *((_BYTE *)a3 + 450) )
                    *((_DWORD *)v47 + 10) |= 0x10u;
                  if ( (*(_DWORD *)(v105 + 68) & 0x10000) != 0 )
                    *((_DWORD *)v47 + 10) |= 0x20u;
                  if ( !a5 )
                    v11 = (*(__int64 (__fastcall **)(struct DfsRootFolder *))(*(_QWORD *)a3 + 72LL))(a3);
                  *((_DWORD *)v47 + 11) = v11;
                  *((_QWORD *)v47 + 1) = v49;
                  v66 = *(unsigned __int16 *)(v105 + 72);
                  v67 = &v49[v66 + 2];
                  memcpy_0(v49, *(const void **)(v105 + 80), v66);
LABEL_165:
                  v82 = v67;
                  *(_QWORD *)v47 = v67;
                  v81 = v46 - (_QWORD)v67;
                  goto LABEL_166;
                }
                if ( v55 == 1 )
                {
                  *((_QWORD *)v47 + 7) = v50;
                  v56 = 0;
                  v57 = v109;
                  v123 = 0;
                  if ( *(_DWORD *)(v109 + 12) )
                  {
                    do
                    {
                      v58 = *(_QWORD *)(v57 + 16) + ((unsigned __int64)v56 << 6);
                      v59 = 32LL * v56;
                      *(_DWORD *)(v59 + v50) = *(_DWORD *)(v58 + 20);
                      if ( *(_DWORD *)(v58 + 16) )
                        v60 = 0;
                      else
                        v60 = *(_BYTE *)(v58 + 12);
                      DfsTargetPriority::UnpackTargetPriority(v60, (struct _DFS_TARGET_PRIORITY *)(v59 + v50 + 24));
                      v62 = v61;
                      *(_QWORD *)(v59 + v50 + 8) = v49;
                      v63 = (__int64)&v49[v61 + 2];
                      *(_QWORD *)(v59 + v50 + 16) = v63;
                      v49 = (unsigned __int8 *)(v63 + 2 + *(unsigned __int16 *)(v58 + 48));
                      memcpy_0(v65, v64, v62);
                      memcpy_0(*(void **)(v59 + v50 + 16), *(const void **)(v58 + 56), *(unsigned __int16 *)(v58 + 48));
                      v57 = v109;
                      v56 = v123 + 1;
                      v123 = v56;
                    }
                    while ( v56 < *(_DWORD *)(v109 + 12) );
                    v47 = a7;
                    v46 = v110;
                  }
                  goto LABEL_97;
                }
LABEL_167:
                v18 = v107;
                goto LABEL_168;
              }
              *((_QWORD *)v47 + 6) = v50;
            }
            else
            {
              *((_QWORD *)v47 + 3) = v50;
            }
            if ( *(_DWORD *)(v109 + 12) )
            {
              v68 = 0;
              do
              {
                v69 = *(_QWORD *)(v109 + 16);
                v70 = (unsigned __int64)v68 << 6;
                v71 = *(_DWORD *)(v70 + v69 + 32);
                Buffer = *(PWSTR *)(v70 + v69 + 40);
                if ( (_WORD)v71 == 2 && *Buffer == 46 || (_WORD)v71 == 4 && *Buffer == 46 && !Buffer[1] )
                {
                  Buffer = a4->Buffer;
                  v71 = *(_DWORD *)&a4->Length;
                }
                v73 = v69 + ((unsigned __int64)v68 << 6);
                v74 = (unsigned __int16)v71;
                v75 = 3LL * v68;
                v76 = (__int64)&v49[(unsigned __int16)v71 + 2];
                v77 = v49;
                v78 = *(_DWORD *)(v73 + 20);
                *(_QWORD *)(v50 + 8 * v75 + 8) = v49;
                *(_QWORD *)(v50 + 8 * v75 + 16) = v76;
                *(_DWORD *)(v50 + 8 * v75) = v78;
                v49 = (unsigned __int8 *)(v76 + 2 + *(unsigned __int16 *)(v73 + 48));
                memcpy_0(v77, Buffer, v74);
                memcpy_0(
                  *(void **)(v50 + 24LL * v68++ + 16),
                  *(const void **)(v73 + 56),
                  *(unsigned __int16 *)(v73 + 48));
              }
              while ( v68 < *(_DWORD *)(v109 + 12) );
              v47 = a7;
              v46 = v110;
            }
          }
          if ( &v47[v46] < &v49[*(unsigned __int16 *)(v105 + 72) + 2] )
          {
            v18 = 111;
            goto LABEL_168;
          }
          *((_QWORD *)v47 + 1) = v49;
          v79 = v49;
          v80 = *(unsigned __int16 *)(v105 + 72);
          v49 += v80 + 2;
          memcpy_0(v79, *(const void **)(v105 + 80), v80);
          *(_WORD *)(*((_QWORD *)v47 + 1) + 2 * ((unsigned __int64)*(unsigned __int16 *)(v105 + 72) >> 1)) = 0;
        }
        *(_QWORD *)v47 = v49;
        v81 = v46 - (_QWORD)v49;
        v82 = v49;
LABEL_166:
        WriteApiPathString(a4, &v111, v82, (unsigned __int64)&v47[v81]);
        goto LABEL_167;
      }
      v18 = 8;
LABEL_168:
      (*(void (__fastcall **)(DfsStore *, __int64, __int64))(*(_QWORD *)this + 128LL))(this, a2, v109);
      goto LABEL_169;
    }
    switch ( a6 )
    {
      case 8u:
        v15 = 72;
        v118 = *(_DWORD *)(v109 + 12);
        v44 = *(void **)(v105 + 128);
        v29 = *(unsigned __int16 *)(v105 + 72) + 2;
        if ( v44 )
        {
          v29 = (*(unsigned __int16 *)(v105 + 72) + 9) & 0xFFFFFFF8;
          SecurityDescriptorLength = GetSecurityDescriptorLength(v44);
        }
        else
        {
          SecurityDescriptorLength = 0;
        }
        v27 = SecurityDescriptorLength + v19;
        v28 = 0;
        break;
      case 9u:
        v118 = *(_DWORD *)(v109 + 12);
        v17 = 32 * v118;
        v106 = 32 * v118;
        if ( v118 )
        {
          v38 = v118;
          v21 = *(_QWORD *)(v109 + 16) + 48LL;
          do
          {
            v39 = *(_DWORD *)(v21 - 16);
            v40 = *(_WORD **)(v21 - 8);
            if ( (_WORD)v39 == 2 && *v40 == 46 || (_WORD)v39 == 4 && *v40 == 46 && !v40[1] )
              v39 = *(_DWORD *)&a4->Length;
            v41 = *(unsigned __int16 *)v21;
            v21 += 64;
            v16 += (unsigned __int16)v39 + v41 + 4;
            --v38;
          }
          while ( v38 );
          v20 = a6;
          v17 = v106;
        }
        v42 = *(void **)(v105 + 128);
        v29 = *(unsigned __int16 *)(v105 + 72) + 2 + v16;
        if ( v42 )
        {
          v29 = (v29 + 7) & 0xFFFFFFF8;
          SecurityDescriptorLength = GetSecurityDescriptorLength(v42);
        }
        else
        {
          SecurityDescriptorLength = 0;
        }
        v27 = SecurityDescriptorLength + v19;
        v28 = v17;
        break;
      case 0x32u:
        if ( a5 )
          goto LABEL_42;
        goto LABEL_41;
      case 0x64u:
        v15 = 8;
        v16 = *(unsigned __int16 *)(v105 + 72) + 2;
        goto LABEL_23;
      case 0x96u:
        if ( !a5 )
        {
          v18 = 50;
          goto LABEL_168;
        }
        v15 = 16;
        v36 = *(void **)(v105 + 128);
        if ( v36 )
          v37 = GetSecurityDescriptorLength(v36);
        else
          v37 = 0;
        v108 = v37;
        v16 = v37;
        v14 = v110;
        v28 = 0;
        goto LABEL_77;
      default:
        goto LABEL_42;
    }
    v108 = SecurityDescriptorLength;
    v14 = v110;
LABEL_76:
    v16 = v27 + v29;
    goto LABEL_77;
  }
  return v18;
}

```

## disassembly

```asm
0x140037d08  mov     rax, rsp
0x140037d0b  mov     [rax+20h], r9
0x140037d0f  mov     [rax+18h], r8
0x140037d13  mov     [rax+10h], rdx
0x140037d17  mov     [rax+8], rcx
0x140037d1b  push    rbp
0x140037d1c  push    rbx
0x140037d1d  push    rsi
0x140037d1e  push    rdi
0x140037d1f  push    r12
0x140037d21  push    r13
0x140037d23  push    r14
0x140037d25  push    r15
0x140037d27  lea     rbp, [rax-47h]
0x140037d2b  sub     rsp, 0C8h
0x140037d32  mov     rax, [rbp+3Fh+arg_38]
0x140037d39  xor     r14d, r14d
0x140037d3c  mov     r13, rcx
0x140037d3f  mov     qword ptr [rsp+100h+var_D0], r14
0x140037d44  mov     rcx, [rbp+3Fh+arg_48]
0x140037d4b  mov     rbx, rdx
0x140037d4e  xorps   xmm0, xmm0
0x140037d51  mov     [rbp+3Fh+var_B8], r14
0x140037d55  mov     esi, [rax]
0x140037d57  lea     r15d, [r14+50h]
0x140037d5b  mov     r8d, r15d; Size
0x140037d5e  mov     [rsp+100h+var_C0], r14d
0x140037d63  mov     [rcx], r14
0x140037d66  xor     edx, edx; Val
0x140037d68  mov     rcx, [rbp+3Fh+arg_40]
0x140037d6f  mov     edi, r14d
0x140037d72  mov     r12d, r14d
0x140037d75  mov     [rsp+100h+var_C8], r14d
0x140037d7a  movups  xmmword ptr [rbp+3Fh+var_A8.Length], xmm0
0x140037d7e  mov     dword ptr [rbp+3Fh+var_B0], esi
0x140037d81  mov     [rcx], r14d
0x140037d84  lea     rcx, [rbp+3Fh+Src]; void *
0x140037d88  mov     [rax], r14d
0x140037d8b  call    memset_0
0x140037d90  mov     rax, [r13+0]
0x140037d94  lea     r9, [rsp+100h+var_D0]
0x140037d99  mov     r8, [rbp+3Fh+arg_20]
0x140037d9d  mov     rdx, rbx
0x140037da0  mov     rcx, r13
0x140037da3  mov     rax, [rax+60h]
0x140037da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037dac  mov     ebx, eax
0x140037dae  test    eax, eax
0x140037db0  jnz     loc_1400388EA
0x140037db6  mov     rax, [r13+0]
0x140037dba  lea     r8, [rbp+3Fh+var_A8]
0x140037dbe  mov     rdx, qword ptr [rsp+100h+var_D0]
0x140037dc3  mov     rcx, r13
0x140037dc6  add     rdx, 10h
0x140037dca  mov     rax, [rax+0E0h]
0x140037dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037dd6  mov     rax, [rbp+3Fh+arg_18]
0x140037dda  lea     r9, [rbp+3Fh+var_B8]
0x140037dde  movzx   r13d, [rbp+3Fh+var_A8.Length]
0x140037de3  mov     r8, [rbp+3Fh+arg_20]
0x140037de7  add     r13d, 8
0x140037deb  mov     rdx, [rbp+3Fh+arg_8]
0x140037def  movzx   ecx, word ptr [rax]
0x140037df2  add     r13d, ecx
0x140037df5  mov     rcx, [rbp+3Fh+arg_0]
0x140037df9  mov     rax, [rcx]
0x140037dfc  mov     rax, [rax+78h]
0x140037e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e05  mov     [rsp+100h+var_C4], eax
0x140037e09  mov     ebx, eax
0x140037e0b  test    eax, eax
0x140037e0d  jnz     loc_1400388D1
0x140037e13  mov     ebx, [rbp+3Fh+arg_28]
0x140037e16  lea     ecx, [rax+8]
0x140037e19  lea     edx, [rax+10h]
0x140037e1c  mov     r11w, 2Eh ; '.'
0x140037e21  lea     r10d, [r14+2]
0x140037e25  cmp     ebx, 7
0x140037e28  ja      loc_14003804A
0x140037e2e  jz      loc_14003802A
0x140037e34  mov     eax, ebx
0x140037e36  sub     eax, 1
0x140037e39  jz      loc_140038017
0x140037e3f  mov     r10, qword ptr [rsp+100h+var_D0]
0x140037e44  sub     eax, 1
0x140037e47  jz      loc_140037FF4
0x140037e4d  sub     eax, 1
0x140037e50  jz      loc_140037F52
0x140037e56  sub     eax, 1
0x140037e59  jz      loc_140037F28
0x140037e5f  sub     eax, 1
0x140037e62  jz      loc_140037F05
0x140037e68  cmp     eax, 1
0x140037e6b  jnz     loc_140038040
0x140037e71  mov     rax, [rbp+3Fh+var_B8]
0x140037e75  lea     r15d, [r14+40h]
0x140037e79  mov     ecx, [rax+0Ch]
0x140037e7c  mov     r12d, ecx
0x140037e7f  mov     [rbp+3Fh+var_60], ecx
0x140037e82  shl     r12d, 5
0x140037e86  mov     [rsp+100h+var_C8], r12d
0x140037e8b  test    ecx, ecx
0x140037e8d  jz      short loc_140037EF2
0x140037e8f  mov     rdx, [rax+10h]
0x140037e93  lea     esi, [r14+2]
0x140037e97  mov     rbx, [rbp+3Fh+arg_18]
0x140037e9b  lea     r10d, [r14+4]
0x140037e9f  add     rdx, 30h ; '0'
0x140037ea3  mov     r9d, ecx
0x140037ea6  mov     r8d, [rdx-10h]
0x140037eaa  mov     rax, [rdx-8]
0x140037eae  cmp     r8w, si
0x140037eb2  jnz     short loc_140037EBA
0x140037eb4  cmp     [rax], r11w
0x140037eb8  jz      short loc_140037ECD
0x140037eba  cmp     r8w, r10w
0x140037ebe  jnz     short loc_140037ED0
0x140037ec0  cmp     [rax], r11w
0x140037ec4  jnz     short loc_140037ED0
0x140037ec6  cmp     [rax+2], r14w
0x140037ecb  jnz     short loc_140037ED0
0x140037ecd  mov     r8d, [rbx]
0x140037ed0  movzx   ecx, word ptr [rdx]
0x140037ed3  add     rdx, r15
0x140037ed6  movzx   eax, r8w
0x140037eda  add     eax, edi
0x140037edc  lea     edi, [rcx+4]
0x140037edf  add     edi, eax
0x140037ee1  sub     r9, 1
0x140037ee5  jnz     short loc_140037EA6
0x140037ee7  mov     ebx, [rbp+3Fh+arg_28]
0x140037eea  mov     r10, qword ptr [rsp+100h+var_D0]
0x140037eef  mov     esi, dword ptr [rbp+3Fh+var_B0]
0x140037ef2  movzx   eax, word ptr [r10+48h]
0x140037ef7  add     eax, r13d
0x140037efa  mov     r13d, r12d
0x140037efd  add     edi, 2
0x140037f00  jmp     loc_1400381D7
0x140037f05  mov     rax, [rbp+3Fh+var_B8]
0x140037f09  mov     r15d, 38h ; '8'
0x140037f0f  movzx   edi, word ptr [r10+48h]
0x140037f14  add     edi, 2
0x140037f17  add     edi, r13d
0x140037f1a  mov     ecx, [rax+0Ch]
0x140037f1d  mov     [rbp+3Fh+var_60], ecx
0x140037f20  mov     r13d, r14d
0x140037f23  jmp     loc_1400381D9
0x140037f28  mov     eax, [r10+70h]
0x140037f2c  mov     r15d, 38h ; '8'
0x140037f32  movups  xmm0, xmmword ptr [r10+30h]
0x140037f37  mov     [rbp+3Fh+var_7C], eax
0x140037f3a  mov     eax, [r10+40h]
0x140037f3e  mov     [rbp+3Fh+var_80], eax
0x140037f41  mov     rax, [rbp+3Fh+var_B8]
0x140037f45  movdqu  [rbp+3Fh+var_78], xmm0
0x140037f4a  mov     ecx, [rax+0Ch]
0x140037f4d  mov     [rbp+3Fh+var_68], ecx
0x140037f50  jmp     short loc_140037F69
0x140037f52  mov     eax, [r10+40h]
0x140037f56  mov     r15d, 20h ; ' '
0x140037f5c  mov     [rbp+3Fh+var_80], eax
0x140037f5f  mov     rax, [rbp+3Fh+var_B8]
0x140037f63  mov     ecx, [rax+0Ch]
0x140037f66  mov     [rbp+3Fh+var_7C], ecx
0x140037f69  mov     rax, [rbp+3Fh+var_B8]
0x140037f6d  lea     r12d, [rcx+rcx*2]
0x140037f71  shl     r12d, 3
0x140037f75  mov     [rsp+100h+var_C8], r12d
0x140037f7a  cmp     [rax+0Ch], r14d
0x140037f7e  jbe     loc_14003800B
0x140037f84  mov     rdx, [rax+10h]
0x140037f88  mov     ebx, 2
0x140037f8d  mov     r9d, [rax+0Ch]
0x140037f91  add     rdx, 30h ; '0'
0x140037f95  mov     rsi, [rbp+3Fh+arg_18]
0x140037f99  lea     r10d, [rbx+2]
0x140037f9d  mov     r8d, [rdx-10h]
0x140037fa1  mov     rax, [rdx-8]
0x140037fa5  cmp     r8w, bx
0x140037fa9  jnz     short loc_140037FB1
0x140037fab  cmp     [rax], r11w
0x140037faf  jz      short loc_140037FC4
0x140037fb1  cmp     r8w, r10w
0x140037fb5  jnz     short loc_140037FC7
0x140037fb7  cmp     [rax], r11w
0x140037fbb  jnz     short loc_140037FC7
0x140037fbd  cmp     [rax+2], r14w
0x140037fc2  jnz     short loc_140037FC7
0x140037fc4  mov     r8d, [rsi]
0x140037fc7  movzx   ecx, word ptr [rdx]
0x140037fca  add     rdx, 40h ; '@'
0x140037fce  movzx   eax, r8w
0x140037fd2  add     eax, edi
0x140037fd4  lea     edi, [rcx+4]
0x140037fd7  add     edi, eax
0x140037fd9  sub     r9, 1
0x140037fdd  jnz     short loc_140037F9D
0x140037fdf  mov     ebx, [rbp+3Fh+arg_28]
0x140037fe2  mov     r10, qword ptr [rsp+100h+var_D0]
0x140037fe7  mov     esi, dword ptr [rbp+3Fh+var_B0]
0x140037fea  mov     [rsp+100h+var_C8], r12d
0x140037fef  test    r15d, r15d
0x140037ff2  jnz     short loc_14003800B
0x140037ff4  mov     eax, [r10+40h]
0x140037ff8  mov     r15d, 18h
0x140037ffe  mov     [rbp+3Fh+var_80], eax
0x140038001  mov     rax, [rbp+3Fh+var_B8]
0x140038005  mov     ecx, [rax+0Ch]
0x140038008  mov     [rbp+3Fh+var_7C], ecx
0x14003800b  movzx   eax, word ptr [r10+48h]
0x140038010  add     edi, 2
0x140038013  add     edi, eax
0x140038015  jmp     short loc_14003801F
0x140038017  mov     r15d, ecx
0x14003801a  mov     [rsp+100h+var_C8], r14d
0x14003801f  add     edi, r13d
0x140038022  mov     r13d, r12d
0x140038025  jmp     loc_1400381D9
0x14003802a  mov     rax, qword ptr [rsp+100h+var_D0]
0x14003802f  test    dword ptr [rax+40h], 300h
0x140038036  jz      short loc_140038040
0x140038038  mov     r15d, edx
0x14003803b  jmp     loc_140037F20
0x140038040  mov     ebx, 57h ; 'W'
0x140038045  jmp     loc_1400388B6
0x14003804a  mov     eax, ebx
0x14003804c  sub     eax, ecx
0x14003804e  jz      loc_140038188
0x140038054  sub     eax, 1
0x140038057  jz      short loc_1400380D3
0x140038059  sub     eax, 29h ; ')'
0x14003805c  jz      short loc_1400380C4
0x14003805e  sub     eax, 32h ; '2'
0x140038061  jz      short loc_1400380B0
0x140038063  cmp     eax, 32h ; '2'
0x140038066  jnz     short loc_140038040
0x140038068  cmp     [rbp+3Fh+arg_20], r14
0x14003806c  jz      short loc_1400380A6
0x14003806e  mov     rax, qword ptr [rsp+100h+var_D0]
0x140038073  mov     r15d, edx
0x140038076  mov     rcx, [rax+80h]; pSecurityDescriptor
0x14003807d  test    rcx, rcx
0x140038080  jz      short loc_140038092
0x140038082  call    cs:__imp_GetSecurityDescriptorLength
0x140038089  nop     dword ptr [rax+rax+00h]
0x14003808e  mov     esi, eax
0x140038090  jmp     short loc_140038095
0x140038092  mov     esi, r14d
0x140038095  mov     [rsp+100h+var_C0], esi
0x140038099  mov     edi, esi
0x14003809b  mov     esi, dword ptr [rbp+3Fh+var_B0]
0x14003809e  mov     r13d, r14d
0x1400380a1  jmp     loc_1400381D9
0x1400380a6  mov     ebx, 32h ; '2'
0x1400380ab  jmp     loc_1400388B6
0x1400380b0  mov     rax, qword ptr [rsp+100h+var_D0]
0x1400380b5  mov     r15d, ecx
0x1400380b8  movzx   edi, word ptr [rax+48h]
0x1400380bc  add     edi, r10d
0x1400380bf  jmp     loc_140037F20
0x1400380c4  cmp     [rbp+3Fh+arg_20], r14
0x1400380c8  jnz     loc_140038040
0x1400380ce  jmp     loc_140038038
0x1400380d3  mov     rax, [rbp+3Fh+var_B8]
0x1400380d7  mov     ecx, [rax+0Ch]
0x1400380da  mov     r12d, ecx
0x1400380dd  mov     [rbp+3Fh+var_50], ecx
0x1400380e0  shl     r12d, 5
0x1400380e4  mov     [rsp+100h+var_C8], r12d
0x1400380e9  test    ecx, ecx
0x1400380eb  jz      short loc_14003814C
0x1400380ed  mov     rdx, [rax+10h]
0x1400380f1  mov     r9d, ecx
0x1400380f4  mov     rbx, [rbp+3Fh+arg_18]
0x1400380f8  add     rdx, 30h ; '0'
0x1400380fc  mov     r12d, 4
0x140038102  mov     r8d, [rdx-10h]
0x140038106  mov     rax, [rdx-8]
0x14003810a  cmp     r8w, r10w
0x14003810e  jnz     short loc_140038116
0x140038110  cmp     [rax], r11w
0x140038114  jz      short loc_140038129
0x140038116  cmp     r8w, r12w
0x14003811a  jnz     short loc_14003812C
0x14003811c  cmp     [rax], r11w
0x140038120  jnz     short loc_14003812C
0x140038122  cmp     [rax+2], r14w
0x140038127  jnz     short loc_14003812C
0x140038129  mov     r8d, [rbx]
0x14003812c  movzx   ecx, word ptr [rdx]
0x14003812f  add     rdx, 40h ; '@'
0x140038133  movzx   eax, r8w
0x140038137  add     eax, edi
0x140038139  lea     edi, [rcx+4]
0x14003813c  add     edi, eax
0x14003813e  sub     r9, 1
0x140038142  jnz     short loc_140038102
0x140038144  mov     ebx, [rbp+3Fh+arg_28]
0x140038147  mov     r12d, [rsp+100h+var_C8]
0x14003814c  mov     rcx, qword ptr [rsp+100h+var_D0]
  ... truncated ...
```
