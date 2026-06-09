# GenGetProcessInfo(ulong,_MINIDUMP_STATE *,_INTERNAL_PROCESS * *,_LIST_ENTRY *)

- ea: `0x18001ad48`
- end: `0x18001b968`
- name: `?GenGetProcessInfo@@YAJKPEAU_MINIDUMP_STATE@@PEAPEAU_INTERNAL_PROCESS@@PEAU_LIST_ENTRY@@@Z`
- size: `3104`
- prototype: `__int64 __fastcall(unsigned int, struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS **, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x18000f8e8`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180003424`
- `0x180016b74`
- `0x180016d9c`
- `0x180017314`
- `0x180017890`
- `0x180017b8c`
- `0x18001832c`
- `0x180018b78`
- `0x18001951c`
- `0x180019620`
- `0x1800196fc`
- `0x180019e3c`
- `0x18001a010`
- `0x18001a598`
- `0x18001ad48`
- `0x18001b970`
- `0x18001ba60`
- `0x18001bb40`
- `0x18001bec8`
- `0x18001f834`
- `0x18001f8f0`
- `0x18002c010`

## string_xrefs

- `0x18001b8e0`: `GenGetProcessInfo.EnumThreads(0x%x) looped`
- `0x18001af98`: `GenGetProcessInfo.EnumThreads(0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall GenGetProcessInfo(
        unsigned int a1,
        struct _MINIDUMP_STATE *a2,
        struct _INTERNAL_PROCESS **a3,
        struct _LIST_ENTRY *a4)
{
  unsigned int v5; // r12d
  struct _LIST_ENTRY *v6; // r15
  __int64 result; // rax
  unsigned int v8; // eax
  unsigned int HandleData; // edi
  struct _INTERNAL_PROCESS *v10; // rax
  __int64 v11; // rax
  int v12; // esi
  unsigned int v13; // eax
  int v14; // eax
  char *v15; // rdx
  _QWORD *v16; // rcx
  unsigned int v17; // esi
  int v18; // r15d
  unsigned int v19; // eax
  unsigned __int16 *v20; // rdi
  struct _INTERNAL_MODULE *v21; // rax
  char *v22; // r8
  _QWORD *v23; // rdx
  char *v24; // rcx
  _DWORD *v25; // rsi
  struct _INTERNAL_PROCESS *v26; // r13
  __int64 **v27; // r14
  struct _LIST_ENTRY *v28; // rsi
  int v29; // r8d
  struct _INTERNAL_PROCESS *v30; // r13
  int v31; // r12d
  __int64 **j; // rsi
  int v33; // r14d
  int v34; // edi
  unsigned int v35; // r12d
  unsigned int v36; // r13d
  unsigned __int16 *v37; // rax
  unsigned __int16 *v38; // r15
  int v39; // eax
  char *v40; // rdx
  _QWORD *v41; // rax
  __int64 **i; // rax
  const unsigned __int16 *v43; // rdx
  int v44; // r15d
  int v45; // edx
  unsigned int v46; // ecx
  unsigned int v47; // r14d
  struct _INTERNAL_MODULE *v48; // r12
  __int64 v49; // r13
  _QWORD *v50; // rsi
  void *v51; // rax
  int v52; // r14d
  char *v53; // rdx
  _QWORD *v54; // rax
  struct _INTERNAL_PROCESS *v55; // rsi
  char *v56; // rax
  char *v57; // r12
  char *v58; // rcx
  char *v59; // r15
  unsigned __int64 *v60; // r14
  unsigned __int64 v61; // rdx
  char *v62; // r13
  __int64 v63; // r14
  int v64; // eax
  int v65; // r15d
  struct _LIST_ENTRY *v66; // [rsp+20h] [rbp-E0h]
  struct _INTERNAL_MODULE **v67; // [rsp+28h] [rbp-D8h]
  struct _INTERNAL_PROCESS *v68; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v69; // [rsp+68h] [rbp-98h] BYREF
  struct _INTERNAL_THREAD *v70; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v71[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v72; // [rsp+80h] [rbp-80h]
  struct _INTERNAL_MODULE *v73; // [rsp+88h] [rbp-78h] BYREF
  __int64 v74; // [rsp+90h] [rbp-70h] BYREF
  __int64 v75; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v76; // [rsp+A0h] [rbp-60h] BYREF
  struct _LIST_ENTRY *v77; // [rsp+A8h] [rbp-58h]
  __int64 v78; // [rsp+B0h] [rbp-50h]
  struct _INTERNAL_PROCESS **v79; // [rsp+B8h] [rbp-48h]
  _QWORD v80[4]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE Src[256]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v82[360]; // [rsp+1E0h] [rbp+E0h] BYREF

  v79 = a3;
  v5 = a1;
  v72 = a1;
  v77 = a4;
  v68 = 0;
  v6 = a4;
  memset_0(v82, 0, sizeof(v82));
  result = GenAllocateProcessObject(a2, &v68);
  if ( (_DWORD)result )
    return result;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a2 + 2) + 272LL))(
         *((_QWORD *)a2 + 2),
         *(_QWORD *)a2,
         *((unsigned int *)a2 + 2));
  HandleData = v8;
  if ( v8 )
  {
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
      *((_QWORD *)a2 + 5),
      4,
      "GenGetProcessInfo.Start(0x%x) failed, 0x%08x",
      *((unsigned int *)a2 + 2),
      v8);
LABEL_4:
    GenFreeProcessObject(a2, v68, v6);
    v10 = 0;
    goto LABEL_5;
  }
  if ( (v5 & 0x4000002) == 0 )
  {
    v11 = *((_QWORD *)a2 + 26);
    if ( v11 )
    {
      v66 = (struct _LIST_ENTRY *)(v11 - 984);
      if ( (unsigned int)GenAddMemoryRange(a2, v68, 11) )
        (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a2 + 5) + 8LL))(
          *((_QWORD *)a2 + 5),
          2,
          "Unable to add KUSER_SHARED_DATA memory region to dump\n");
    }
  }
  v12 = 0;
  while ( 1 )
  {
    v70 = 0;
    v69 = 0;
    if ( (unsigned int)GenCheckCancel(a2) )
    {
      HandleData = -2147023673;
      goto LABEL_41;
    }
    if ( (unsigned int)++v12 > 0x100000 )
    {
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
        *((_QWORD *)a2 + 5),
        4,
        "GenGetProcessInfo.EnumThreads(0x%x) looped",
        *((unsigned int *)a2 + 2));
      HandleData = -805305826;
      goto LABEL_41;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a2 + 2) + 280LL))(*((_QWORD *)a2 + 2), &v69);
    HandleData = v13;
    if ( v13 == 1 )
      break;
    if ( v13 )
    {
      LODWORD(v66) = v13;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
        *((_QWORD *)a2 + 5),
        4,
        "GenGetProcessInfo.EnumThreads(0x%x) failed, 0x%08x",
        *((unsigned int *)a2 + 2),
        v66);
      goto LABEL_41;
    }
    v71[0] = 0;
    if ( (unsigned int)GenExecuteIncludeThreadCallback(a2, v69, v71) && (v71[0] & 1) != 0 )
    {
      v14 = GenAllocateThreadObject(a2, v68, v69, v71[0], &v70);
      HandleData = v14;
      if ( v14 < 0 )
        goto LABEL_41;
      if ( !v14 )
      {
        ++*((_DWORD *)v68 + 18);
        v15 = (char *)v68 + 104;
        v16 = (_QWORD *)*((_QWORD *)v68 + 14);
        *((_QWORD *)v70 + 23) = (char *)v68 + 104;
        *((_QWORD *)v70 + 24) = v16;
        *v16 = (char *)v70 + 184;
        *((_QWORD *)v15 + 1) = (char *)v70 + 184;
      }
    }
  }
  v70 = 0;
  v17 = 360;
  v18 = 0;
  while ( 1 )
  {
    v73 = 0;
    v76 = 0;
    if ( (unsigned int)GenCheckCancel(a2) )
    {
      HandleData = -2147023673;
      goto LABEL_39;
    }
    if ( (unsigned int)++v18 > 0x10000 )
    {
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
        *((_QWORD *)a2 + 5),
        4,
        "GenGetProcessInfo.EnumModules(0x%x) looped",
        *((unsigned int *)a2 + 2));
      HandleData = -805305826;
LABEL_39:
      if ( v70 )
        goto LABEL_66;
      goto LABEL_40;
    }
    while ( 1 )
    {
      v70 = (struct _INTERNAL_THREAD *)AllocMemory(a2, 2 * v17);
      if ( !v70 )
      {
        HandleData = -2147024882;
        goto LABEL_40;
      }
      v19 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *, struct _INTERNAL_THREAD *, _QWORD))(**((_QWORD **)a2 + 2) + 288LL))(
              *((_QWORD *)a2 + 2),
              &v76,
              v70,
              v17);
      HandleData = v19;
      if ( v19 != -2147024809 )
        break;
      if ( v17 >= 0x7FFF )
        goto LABEL_55;
      (*(void (__fastcall **)(_QWORD, struct _INTERNAL_THREAD *))(**((_QWORD **)a2 + 4) + 24LL))(
        *((_QWORD *)a2 + 4),
        v70);
      if ( 2 * v17 <= 0x7FFF )
        v17 *= 2;
      else
        v17 = 0x7FFF;
    }
    if ( v19 == 1 )
      break;
    if ( v19 )
    {
LABEL_55:
      LODWORD(v66) = v19;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
        *((_QWORD *)a2 + 5),
        4,
        "GenGetProcessInfo.EnumModules(0x%x) failed, 0x%08x",
        *((unsigned int *)a2 + 2),
        v66);
      goto LABEL_66;
    }
    v20 = (unsigned __int16 *)v70;
    GenAddAuxProvider(a2, v68, v76, (unsigned __int16 *)v70);
    v71[0] = 0;
    if ( (unsigned int)GenExecuteIncludeModuleCallback(a2, v76, v71) && (v71[0] & 1) != 0 )
    {
      HandleData = GenAllocateModuleObject(a2, v68, v20, v76, v71[0], &v73);
      if ( HandleData )
        goto LABEL_66;
      ++*((_DWORD *)v68 + 21);
      v21 = v73;
      v22 = (char *)v68 + 120;
      v23 = (_QWORD *)*((_QWORD *)v68 + 16);
      v24 = (char *)v73 + 144;
      *((_QWORD *)v73 + 18) = (char *)v68 + 120;
      *((_QWORD *)v21 + 19) = v23;
      *v23 = v24;
      *((_QWORD *)v22 + 1) = v24;
    }
  }
  if ( (*((_BYTE *)a2 + 56) & 0x20) != 0 )
  {
    v74 = 0;
    v33 = 0;
    LODWORD(v75) = 0;
    v69 = 0;
    v71[0] = 0;
    while ( 1 )
    {
      v34 = (*(__int64 (__fastcall **)(_QWORD, struct _INTERNAL_THREAD *, _QWORD, __int64 *, __int64 *, unsigned int *, unsigned int *))(**((_QWORD **)a2 + 2) + 320LL))(
              *((_QWORD *)a2 + 2),
              v70,
              v17,
              &v74,
              &v75,
              &v69,
              v71);
      if ( v34 )
        break;
      if ( (unsigned int)GenCheckCancel(a2) )
      {
LABEL_64:
        HandleData = -2147023673;
        goto LABEL_65;
      }
      if ( (unsigned int)++v33 > 0x10000 )
      {
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
          *((_QWORD *)a2 + 5),
          4,
          "GenGetProcessInfo.EnumUnloadedModules(0x%x) looped",
          *((unsigned int *)a2 + 2));
        goto LABEL_70;
      }
      v35 = v71[0];
      v36 = v69;
      LODWORD(v73) = v75;
      v78 = v74;
      v37 = (unsigned __int16 *)AllocMemory(a2, 0x2F8u);
      v38 = v37;
      if ( !v37 )
        goto LABEL_69;
      GenStrCopyNW(v37 + 10, (const unsigned __int16 *)v70, 360);
      v39 = (int)v73;
      *(_QWORD *)v38 = v78;
      *((_DWORD *)v38 + 3) = v36;
      *((_DWORD *)v38 + 2) = v39;
      *((_DWORD *)v38 + 4) = v35;
      ++*((_DWORD *)v68 + 24);
      v40 = (char *)v68 + 136;
      v41 = (_QWORD *)*((_QWORD *)v68 + 18);
      *((_QWORD *)v38 + 93) = (char *)v68 + 136;
      *((_QWORD *)v38 + 94) = v41;
      *v41 = v38 + 372;
      *((_QWORD *)v40 + 1) = v38 + 372;
    }
    if ( v34 != 1 && v34 != -805305826 )
    {
LABEL_69:
      LODWORD(v66) = v34;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
        *((_QWORD *)a2 + 5),
        4,
        "GenGetProcessInfo.EnumUnloadedModules(0x%x) failed, 0x%08x",
        *((unsigned int *)a2 + 2),
        v66);
    }
  }
LABEL_70:
  HandleData = GenGetHandleData(a2, v68);
  v80[1] = a2;
  v80[0] = &GenMiniDumpProviderCallbacks::`vftable';
  v80[2] = v68;
  v80[3] = 0;
  if ( v68 )
  {
    for ( i = (__int64 **)*((_QWORD *)v68 + 949); i != (__int64 **)((char *)v68 + 7592); i = (__int64 **)*i )
    {
      if ( i[5] )
      {
        v43 = (const unsigned __int16 *)i[4];
        if ( v43 )
        {
          GenStrCopyNW(v82, v43, 360);
          break;
        }
      }
    }
  }
  v44 = 0;
  while ( 1 )
  {
    *(_QWORD *)v71 = 0;
    v74 = 0;
    v73 = 0;
    v69 = 0;
    v75 = 0;
    if ( (unsigned int)GenCheckCancel(a2) )
      goto LABEL_64;
    if ( (unsigned int)++v44 > 0x10000 )
    {
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
        *((_QWORD *)a2 + 5),
        4,
        "GenGetProcessInfo.EnumFunctionTables(0x%x) looped",
        *((unsigned int *)a2 + 2));
      HandleData = -805305826;
      goto LABEL_100;
    }
    v45 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, __int64 *, struct _INTERNAL_MODULE **, unsigned int *, _BYTE *, _DWORD, __int64 *, _QWORD *, unsigned __int16 *))(**((_QWORD **)a2 + 2) + 296LL))(
            *((_QWORD *)a2 + 2),
            v71,
            &v74,
            &v73,
            &v69,
            Src,
            *((_DWORD *)a2 + 41),
            &v75,
            v80,
            v82);
    if ( v45 )
      break;
    v46 = *((_DWORD *)a2 + 41);
    if ( v46 <= 0x100000 )
    {
      v47 = v69;
      if ( 0xFFFFFFFF / *((_DWORD *)a2 + 42) >= v69 )
      {
        v48 = v73;
        v49 = v74;
        v78 = *(_QWORD *)v71;
        v50 = AllocMemory(a2, v46 + 64);
        if ( v50 )
        {
          v51 = AllocMemory(a2, *((_DWORD *)a2 + 42) * v47);
          v50[5] = v51;
          if ( v51 )
          {
            *v50 = v78;
            v50[4] = v50 + 8;
            v50[1] = v49;
            v50[2] = v48;
            *((_DWORD *)v50 + 6) = v47;
            memcpy_0(v50 + 8, Src, *((unsigned int *)a2 + 41));
            if ( !is_mul_ok(v69, *((_DWORD *)a2 + 42)) )
            {
              HandleData = -2147024362;
              goto LABEL_100;
            }
            v52 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, __int64, _QWORD, unsigned int))(**((_QWORD **)a2 + 2) + 304LL))(
                    *((_QWORD *)a2 + 2),
                    Src,
                    *((unsigned int *)a2 + 41),
                    v75,
                    v50[5],
                    v69 * *((_DWORD *)a2 + 42));
            if ( v52 )
            {
              if ( v50[5] )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 4) + 24LL))(*((_QWORD *)a2 + 4));
              (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)a2 + 4) + 24LL))(*((_QWORD *)a2 + 4), v50);
              LODWORD(v67) = v52;
              LODWORD(v66) = v69;
              (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
                *((_QWORD *)a2 + 5),
                4,
                "GenGetProcessInfo.EnumFunctionTableEntries(0x%I64x, 0x%x) failed, 0x%08x",
                v73,
                v66,
                v67);
            }
            else
            {
              GenIncludeUnwindInfoMemory(a2, v68, (struct _INTERNAL_FUNCTION_TABLE *)v50);
              ++*((_DWORD *)v68 + 25);
              v53 = (char *)v68 + 152;
              v54 = (_QWORD *)*((_QWORD *)v68 + 20);
              v50[6] = (char *)v68 + 152;
              v50[7] = v54;
              *v54 = v50 + 6;
              *((_QWORD *)v53 + 1) = v50 + 6;
            }
          }
          else
          {
            (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)a2 + 4) + 24LL))(*((_QWORD *)a2 + 4), v50);
          }
        }
      }
    }
    if ( v75 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 4) + 24LL))(*((_QWORD *)a2 + 4));
  }
  if ( v45 != 1 )
  {
    LODWORD(v66) = v45;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
      *((_QWORD *)a2 + 5),
      4,
      "GenGetProcessInfo.EnumFunctionTables(0x%x) failed, 0x%08x",
      *((unsigned int *)a2 + 2),
      v66);
  }
LABEL_100:
  v55 = v68;
  v56 = (char *)v68 + 104;
  v57 = (char *)*((_QWORD *)v68 + 13);
  while ( 2 )
  {
    if ( v57 != v56 )
    {
      v58 = v57;
      v59 = v57 - 184;
      v57 = *(char **)v57;
      if ( *((_DWORD *)a2 + 23) == 332 )
      {
        v60 = (unsigned __int64 *)(v59 + 136);
        *((_QWORD *)v59 + 17) -= 4LL;
        v55 = v68;
      }
      else
      {
        v60 = (unsigned __int64 *)(v58 - 48);
      }
      v61 = *((_QWORD *)v59 + 18);
      if ( v61 > *v60 || (v62 = v59 + 128, *v60 >= *((_QWORD *)v59 + 16)) )
      {
        *v60 = v61;
        v62 = v58 - 56;
        v55 = v68;
      }
      GenFilterContext(a2, v55, (struct _INTERNAL_THREAD *)v59, *((void **)v59 + 14), *((_DWORD *)a2 + 35), 0);
      if ( (*((_DWORD *)a2 + 14) & 0x4000002) != 0 )
        goto LABEL_115;
      if ( *((_DWORD *)a2 + 23) == 332 )
      {
        HandleData = GenAddThreadStack(a2, v68, (struct _INTERNAL_THREAD *)v59, *v60, *(_DWORD *)v62 - *(_DWORD *)v60);
        if ( !HandleData )
          goto LABEL_113;
        if ( *v60 > *((_QWORD *)v59 + 18) )
          *v60 += 4LL;
      }
      HandleData = GenAddThreadStack(a2, v68, (struct _INTERNAL_THREAD *)v59, *v60, *(_DWORD *)v62 - *(_DWORD *)v60);
LABEL_113:
      if ( (v72 & 0x200000) != 0 )
        GenAddShadowStack(a2, v68, *((struct _CONTEXT **)v59 + 14), *((_DWORD *)a2 + 35));
LABEL_115:
      v55 = v68;
      v56 = (char *)v68 + 104;
      continue;
    }
    break;
  }
  if ( (*((_DWORD *)a2 + 14) & 0x10200) != 0 )
  {
    v63 = 0;
    v74 = 0;
    do
    {
      HIDWORD(v66) = HIDWORD(v63);
      if ( (unsigned int)GenAddMemoryRegion(a2, v55, 10) == -2147023673 )
        break;
      v63 += v74;
    }
    while ( v74 );
    v55 = v68;
  }
  if ( (*((_DWORD *)a2 + 14) & 0x400000) != 0 )
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)a2 + 2) + 536LL))(
      *((_QWORD *)a2 + 2),
      *((_QWORD *)v55 + 8),
      (__int64)v55 + 73192,
      (__int64)v55 + 73200);
LABEL_65:
  v5 = v72;
LABEL_66:
  (*(void (__fastcall **)(_QWORD, struct _INTERNAL_THREAD *))(**((_QWORD **)a2 + 4) + 24LL))(*((_QWORD *)a2 + 4), v70);
LABEL_40:
  v6 = v77;
LABEL_41:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 2) + 328LL))(*((_QWORD *)a2 + 2));
  if ( HandleData )
    goto LABEL_4;
  v25 = (_DWORD *)((char *)a2 + 56);
  if ( *(_QWORD *)(*((_QWORD *)a2 + 6) + 40LL) )
  {
    if ( (*v25 & 0x4000) == 0 )
    {
      v26 = v68;
      if ( !(unsigned int)GenCheckCancel(a2) )
      {
        v27 = (__int64 **)*((_QWORD *)v26 + 949);
        if ( v27 != (__int64 **)((char *)v26 + 7592) )
        {
          v28 = v77;
          do
          {
            v29 = GenInvokeEnumStackProviders(v5, a2, v26, (const unsigned __int16 *)v27[4], v28);
            if ( v29 < 0 )
            {
              LODWORD(v66) = v29;
              (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
                *((_QWORD *)a2 + 5),
                4,
                "GenInvokeEnumStackProviders(%ws) failed, 0x%08x",
                v27[4],
                v66);
            }
            v27 = (__int64 **)*v27;
          }
          while ( v27 != (__int64 **)((char *)v26 + 7592) );
          v25 = (_DWORD *)((char *)a2 + 56);
        }
      }
    }
  }
  if ( (*v25 & 0x4000002) == 0 && (*v25 & 0x4000) == 0 )
  {
    v30 = v68;
    if ( (unsigned int)GenCheckCancel(a2) )
      goto LABEL_132;
    v31 = 0;
    for ( j = (__int64 **)*((_QWORD *)v30 + 949); j != (__int64 **)((char *)v30 + 7592); j = (__int64 **)*j )
    {
      v64 = GenInvokeAuxEnumMemory(a2, v30, (unsigned __int16 *)j[4], (unsigned __int64)j[2]);
      v65 = v64;
      if ( v64 < 0 )
      {
        LODWORD(v66) = v64;
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a2 + 5) + 8LL))(
          *((_QWORD *)a2 + 5),
          4,
          "GenGetAuxMemory(%ws) failed, 0x%08x",
          j[4],
          v66);
        v31 = v65;
      }
    }
    if ( v31 == -2147023673 )
LABEL_132:
      HandleData = -2147023673;
  }
  v10 = v68;
LABEL_5:
  *v79 = v10;
  return HandleData;
}

```

## disassembly

```asm
0x18001ad48  push    rbp
0x18001ad4a  push    rbx
0x18001ad4b  push    rsi
0x18001ad4c  push    rdi
0x18001ad4d  push    r12
0x18001ad4f  push    r13
0x18001ad51  push    r14
0x18001ad53  push    r15
0x18001ad55  lea     rbp, [rsp-3C8h]
0x18001ad5d  sub     rsp, 4C8h
0x18001ad64  mov     rax, cs:__security_cookie
0x18001ad6b  xor     rax, rsp
0x18001ad6e  mov     [rbp+400h+var_50], rax
0x18001ad75  mov     [rbp+400h+var_448], r8
0x18001ad79  mov     rbx, rdx
0x18001ad7c  mov     r12d, ecx
0x18001ad7f  mov     [rbp+400h+var_480], ecx
0x18001ad82  xor     r13d, r13d
0x18001ad85  mov     [rbp+400h+var_458], r9
0x18001ad89  xor     edx, edx; Val
0x18001ad8b  mov     [rsp+500h+var_4A0], r13
0x18001ad90  mov     r8d, 2D0h; Size
0x18001ad96  lea     rcx, [rbp+400h+var_320]; void *
0x18001ad9d  mov     r15, r9
0x18001ada0  call    memset_0
0x18001ada5  lea     rdx, [rsp+500h+var_4A0]; struct _INTERNAL_PROCESS **
0x18001adaa  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001adad  call    ?GenAllocateProcessObject@@YAJPEAU_MINIDUMP_STATE@@PEAPEAU_INTERNAL_PROCESS@@@Z; GenAllocateProcessObject(_MINIDUMP_STATE *,_INTERNAL_PROCESS * *)
0x18001adb2  test    eax, eax
0x18001adb4  jnz     short loc_18001AE15
0x18001adb6  mov     rcx, [rbx+10h]
0x18001adba  mov     r8d, [rbx+8]
0x18001adbe  mov     rdx, [rbx]
0x18001adc1  mov     rax, [rcx]
0x18001adc4  mov     rax, [rax+110h]
0x18001adcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001add0  mov     edi, eax
0x18001add2  test    eax, eax
0x18001add4  jz      short loc_18001AE38
0x18001add6  mov     rcx, [rbx+28h]
0x18001adda  lea     r8, aGengetprocessi_5; "GenGetProcessInfo.Start(0x%x) failed, 0"...
0x18001ade1  mov     r9d, [rbx+8]
0x18001ade5  mov     dword ptr [rsp+500h+var_4E0], edi
0x18001ade9  mov     rdx, [rcx]
0x18001adec  mov     rax, [rdx+8]
0x18001adf0  lea     edx, [r13+4]
0x18001adf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adf9  mov     rdx, [rsp+500h+var_4A0]; struct _INTERNAL_PROCESS *
0x18001adfe  mov     r8, r15; struct _LIST_ENTRY *
0x18001ae01  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001ae04  call    ?GenFreeProcessObject@@YAXPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_LIST_ENTRY@@@Z; GenFreeProcessObject(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_LIST_ENTRY *)
0x18001ae09  mov     rax, r13
0x18001ae0c  mov     rcx, [rbp+400h+var_448]
0x18001ae10  mov     [rcx], rax
0x18001ae13  mov     eax, edi
0x18001ae15  mov     rcx, [rbp+400h+var_50]
0x18001ae1c  xor     rcx, rsp; StackCookie
0x18001ae1f  call    __security_check_cookie
0x18001ae24  add     rsp, 4C8h
0x18001ae2b  pop     r15
0x18001ae2d  pop     r14
0x18001ae2f  pop     r13
0x18001ae31  pop     r12
0x18001ae33  pop     rdi
0x18001ae34  pop     rsi
0x18001ae35  pop     rbx
0x18001ae36  pop     rbp
0x18001ae37  retn
0x18001ae38  test    r12d, 4000002h
0x18001ae3f  jnz     short loc_18001AE98
0x18001ae41  mov     rax, [rbx+0D0h]
0x18001ae48  test    rax, rax
0x18001ae4b  jz      short loc_18001AE98
0x18001ae4d  mov     rdx, [rsp+500h+var_4A0]
0x18001ae52  mov     r9d, 1
0x18001ae58  add     rax, 0FFFFFFFFFFFFFC28h
0x18001ae5e  mov     [rsp+500h+var_4D8], 0AA0h
0x18001ae67  mov     rcx, rbx
0x18001ae6a  mov     [rsp+500h+var_4E0], rax
0x18001ae6f  lea     r8d, [r9+0Ah]
0x18001ae73  call    ?GenAddMemoryRange@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_K4@Z; GenAddMemoryRange(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,unsigned __int64)
0x18001ae78  test    eax, eax
0x18001ae7a  jz      short loc_18001AE98
0x18001ae7c  mov     rcx, [rbx+28h]
0x18001ae80  lea     r8, aUnableToAddKus; "Unable to add KUSER_SHARED_DATA memory "...
0x18001ae87  mov     edx, 2
0x18001ae8c  mov     rax, [rcx]
0x18001ae8f  mov     rax, [rax+8]
0x18001ae93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae98  mov     esi, r13d
0x18001ae9b  jmp     loc_18001AF70
0x18001aea0  inc     esi
0x18001aea2  cmp     esi, 100000h
0x18001aea8  ja      loc_18001B8DC
0x18001aeae  mov     rcx, [rbx+10h]
0x18001aeb2  lea     rdx, [rsp+500h+var_498]
0x18001aeb7  mov     rax, [rcx]
0x18001aeba  mov     rax, [rax+118h]
0x18001aec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aec6  mov     edi, eax
0x18001aec8  cmp     eax, 1
0x18001aecb  jz      loc_18001AFBD
0x18001aed1  test    eax, eax
0x18001aed3  jnz     loc_18001AF94
0x18001aed9  mov     edx, [rsp+500h+var_498]; unsigned int
0x18001aedd  lea     r8, [rsp+500h+var_488]; unsigned int *
0x18001aee2  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001aee5  mov     [rsp+500h+var_488], r13d
0x18001aeea  call    ?GenExecuteIncludeThreadCallback@@YAHPEAU_MINIDUMP_STATE@@KPEAK@Z; GenExecuteIncludeThreadCallback(_MINIDUMP_STATE *,ulong,ulong *)
0x18001aeef  test    eax, eax
0x18001aef1  jz      short loc_18001AF70
0x18001aef3  mov     r9d, [rsp+500h+var_488]; unsigned int
0x18001aef8  test    r9b, 1
0x18001aefc  jz      short loc_18001AF70
0x18001aefe  mov     r8d, [rsp+500h+var_498]; unsigned int
0x18001af03  lea     rax, [rsp+500h+var_490]
0x18001af08  mov     rdx, [rsp+500h+var_4A0]; struct _INTERNAL_PROCESS *
0x18001af0d  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001af10  mov     [rsp+500h+var_4E0], rax; struct _INTERNAL_THREAD **
0x18001af15  call    ?GenAllocateThreadObject@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@KKPEAPEAU_INTERNAL_THREAD@@@Z; GenAllocateThreadObject(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,ulong,ulong,_INTERNAL_THREAD * *)
0x18001af1a  mov     edi, eax
0x18001af1c  test    eax, eax
0x18001af1e  js      loc_18001B12C
0x18001af24  jnz     short loc_18001AF70
0x18001af26  mov     rax, [rsp+500h+var_4A0]
0x18001af2b  inc     dword ptr [rax+48h]
0x18001af2e  mov     rdx, [rsp+500h+var_4A0]
0x18001af33  mov     rax, [rsp+500h+var_490]
0x18001af38  add     rdx, 68h ; 'h'
0x18001af3c  mov     rcx, [rdx+8]
0x18001af40  mov     [rax+0B8h], rdx
0x18001af47  mov     rax, [rsp+500h+var_490]
0x18001af4c  mov     [rax+0C0h], rcx
0x18001af53  mov     rax, [rsp+500h+var_490]
0x18001af58  add     rax, 0B8h
0x18001af5e  mov     [rcx], rax
0x18001af61  mov     rax, [rsp+500h+var_490]
0x18001af66  add     rax, 0B8h
0x18001af6c  mov     [rdx+8], rax
0x18001af70  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001af73  mov     [rsp+500h+var_490], r13
0x18001af78  mov     [rsp+500h+var_498], r13d
0x18001af7d  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18001af82  test    eax, eax
0x18001af84  jz      loc_18001AEA0
0x18001af8a  mov     edi, 800704C7h
0x18001af8f  jmp     loc_18001B12C
0x18001af94  mov     rcx, [rbx+28h]
0x18001af98  lea     r8, aGengetprocessi_7; "GenGetProcessInfo.EnumThreads(0x%x) fai"...
0x18001af9f  mov     r9d, [rbx+8]
0x18001afa3  mov     edx, 4
0x18001afa8  mov     dword ptr [rsp+500h+var_4E0], edi
0x18001afac  mov     rax, [rcx]
0x18001afaf  mov     rax, [rax+8]
0x18001afb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afb8  jmp     loc_18001B12C
0x18001afbd  mov     [rsp+500h+var_490], r13
0x18001afc2  mov     esi, 168h
0x18001afc7  mov     r15d, r13d
0x18001afca  jmp     loc_18001B100
0x18001afcf  inc     r15d
0x18001afd2  cmp     r15d, 10000h
0x18001afd9  ja      loc_18001B8B2
0x18001afdf  lea     r14d, [rsi+rsi]
0x18001afe3  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001afe6  mov     edx, r14d; unsigned int
0x18001afe9  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x18001afee  mov     [rsp+500h+var_490], rax
0x18001aff3  mov     r8, rax
0x18001aff6  test    rax, rax
0x18001aff9  jz      loc_18001B8A8
0x18001afff  mov     rcx, [rbx+10h]
0x18001b003  mov     r9d, esi
0x18001b006  mov     rdx, [rcx]
0x18001b009  mov     rax, [rdx+120h]
0x18001b010  lea     rdx, [rbp+400h+var_460]
0x18001b014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b019  mov     edi, eax
0x18001b01b  cmp     eax, 80070057h
0x18001b020  jnz     short loc_18001B058
0x18001b022  cmp     esi, 7FFFh
0x18001b028  jnb     loc_18001B20F
0x18001b02e  mov     rcx, [rbx+20h]
0x18001b032  mov     rdx, [rsp+500h+var_490]
0x18001b037  mov     rax, [rcx]
0x18001b03a  mov     rax, [rax+18h]
0x18001b03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b043  cmp     r14d, 7FFFh
0x18001b04a  jbe     short loc_18001B053
0x18001b04c  mov     esi, 7FFFh
0x18001b051  jmp     short loc_18001AFDF
0x18001b053  mov     esi, r14d
0x18001b056  jmp     short loc_18001AFDF
0x18001b058  cmp     edi, 1
0x18001b05b  jz      loc_18001B238
0x18001b061  test    edi, edi
0x18001b063  jnz     loc_18001B20F
0x18001b069  mov     rdi, [rsp+500h+var_490]
0x18001b06e  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001b071  mov     r8, [rbp+400h+var_460]; unsigned __int64
0x18001b075  mov     r9, rdi; unsigned __int16 *
0x18001b078  mov     rdx, [rsp+500h+var_4A0]; struct _INTERNAL_PROCESS *
0x18001b07d  call    ?GenAddAuxProvider@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@_KPEAG@Z; GenAddAuxProvider(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,unsigned __int64,ushort *)
0x18001b082  mov     rdx, [rbp+400h+var_460]; unsigned __int64
0x18001b086  lea     r8, [rsp+500h+var_488]; unsigned int *
0x18001b08b  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001b08e  mov     [rsp+500h+var_488], r13d
0x18001b093  call    ?GenExecuteIncludeModuleCallback@@YAHPEAU_MINIDUMP_STATE@@_KPEAK@Z; GenExecuteIncludeModuleCallback(_MINIDUMP_STATE *,unsigned __int64,ulong *)
0x18001b098  test    eax, eax
0x18001b09a  jz      short loc_18001B100
0x18001b09c  mov     eax, [rsp+500h+var_488]
0x18001b0a0  test    al, 1
0x18001b0a2  jz      short loc_18001B100
0x18001b0a4  mov     r9, [rbp+400h+var_460]; unsigned __int64
0x18001b0a8  lea     rcx, [rbp+400h+var_478]
0x18001b0ac  mov     rdx, [rsp+500h+var_4A0]; struct _INTERNAL_PROCESS *
0x18001b0b1  mov     r8, rdi; unsigned __int16 *
0x18001b0b4  mov     [rsp+500h+var_4D8], rcx; struct _INTERNAL_MODULE **
0x18001b0b9  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001b0bc  mov     dword ptr [rsp+500h+var_4E0], eax; unsigned int
0x18001b0c0  call    ?GenAllocateModuleObject@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAG_KKPEAPEAU_INTERNAL_MODULE@@@Z; GenAllocateModuleObject(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,ushort *,unsigned __int64,ulong,_INTERNAL_MODULE * *)
0x18001b0c5  mov     edi, eax
0x18001b0c7  test    eax, eax
0x18001b0c9  jnz     loc_18001B37B
0x18001b0cf  mov     rax, [rsp+500h+var_4A0]
0x18001b0d4  inc     dword ptr [rax+54h]
0x18001b0d7  mov     r8, [rsp+500h+var_4A0]
0x18001b0dc  mov     rax, [rbp+400h+var_478]
0x18001b0e0  add     r8, 78h ; 'x'
0x18001b0e4  mov     rdx, [r8+8]
0x18001b0e8  lea     rcx, [rax+90h]
0x18001b0ef  mov     [rcx], r8
0x18001b0f2  mov     [rax+98h], rdx
0x18001b0f9  mov     [rdx], rcx
0x18001b0fc  mov     [r8+8], rcx
0x18001b100  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001b103  mov     [rbp+400h+var_478], r13
0x18001b107  mov     [rbp+400h+var_460], r13
0x18001b10b  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18001b110  test    eax, eax
0x18001b112  jz      loc_18001AFCF
0x18001b118  mov     edi, 800704C7h
0x18001b11d  cmp     [rsp+500h+var_490], r13
0x18001b122  jnz     loc_18001B37B
0x18001b128  mov     r15, [rbp+400h+var_458]
0x18001b12c  mov     rcx, [rbx+10h]
0x18001b130  mov     rax, [rcx]
0x18001b133  mov     rax, [rax+148h]
0x18001b13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b13f  test    edi, edi
0x18001b141  jnz     loc_18001ADF9
0x18001b147  mov     rax, [rbx+30h]
0x18001b14b  lea     rsi, [rbx+38h]
0x18001b14f  cmp     [rax+28h], r13
0x18001b153  jz      short loc_18001B1D0
0x18001b155  test    dword ptr [rsi], 4000h
0x18001b15b  jnz     short loc_18001B1D0
0x18001b15d  mov     r13, [rsp+500h+var_4A0]
0x18001b162  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001b165  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18001b16a  test    eax, eax
0x18001b16c  jnz     short loc_18001B1D0
0x18001b16e  lea     r15, [r13+1DA8h]
0x18001b175  mov     r14, [r15]
0x18001b178  cmp     r14, r15
0x18001b17b  jz      short loc_18001B1D0
0x18001b17d  mov     rsi, [rbp+400h+var_458]
0x18001b181  mov     r9, [r14+20h]; unsigned __int16 *
0x18001b185  mov     r8, r13; struct _INTERNAL_PROCESS *
0x18001b188  mov     rdx, rbx; struct _MINIDUMP_STATE *
0x18001b18b  mov     [rsp+500h+var_4E0], rsi; struct _LIST_ENTRY *
0x18001b190  mov     ecx, r12d; unsigned int
0x18001b193  call    ?GenInvokeEnumStackProviders@@YAJKPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEBGPEAU_LIST_ENTRY@@@Z; GenInvokeEnumStackProviders(ulong,_MINIDUMP_STATE *,_INTERNAL_PROCESS *,ushort const *,_LIST_ENTRY *)
0x18001b198  mov     r8d, eax
0x18001b19b  test    eax, eax
0x18001b19d  jns     short loc_18001B1C4
0x18001b19f  mov     rcx, [rbx+28h]
0x18001b1a3  mov     r9, [r14+20h]
0x18001b1a7  mov     dword ptr [rsp+500h+var_4E0], r8d
0x18001b1ac  lea     r8, aGeninvokeenums; "GenInvokeEnumStackProviders(%ws) failed"...
0x18001b1b3  mov     rdx, [rcx]
0x18001b1b6  mov     rax, [rdx+8]
0x18001b1ba  mov     edx, 4
0x18001b1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1c4  mov     r14, [r14]
0x18001b1c7  cmp     r14, r15
0x18001b1ca  jnz     short loc_18001B181
0x18001b1cc  lea     rsi, [rbx+38h]
0x18001b1d0  test    dword ptr [rsi], 4000002h
0x18001b1d6  jnz     loc_18001B95E
0x18001b1dc  test    dword ptr [rsi], 4000h
0x18001b1e2  jnz     loc_18001B95E
0x18001b1e8  mov     r13, [rsp+500h+var_4A0]
0x18001b1ed  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18001b1f0  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18001b1f5  test    eax, eax
0x18001b1f7  jnz     loc_18001B959
0x18001b1fd  lea     r14, [r13+1DA8h]
0x18001b204  xor     r12d, r12d
0x18001b207  mov     rsi, [r14]
  ... truncated ...
```
