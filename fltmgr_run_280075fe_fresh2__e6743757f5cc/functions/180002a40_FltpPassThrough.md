# FltpPassThrough

- ea: `0x180002a40`
- end: `0x1800031d8`
- name: `FltpPassThrough`
- size: `1944`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002880`
- `0x18006ee20`

## callees

- `0x180002a40`
- `0x1800031e0`
- `0x180003380`
- `0x180007d80`
- `0x180009f20`
- `0x18000a360`
- `0x180016f40`
- `0x18005cfe0`
- `0x180060520`
- `0x180060930`
- `0x1800614b0`
- `0x180065d30`
- `0x18006ba60`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x180002d76`
- `ntoskrnl!KeDelayExecutionThread` at `0x180002d76`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180002f4a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800252e8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180002f4a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800252e8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800030b4`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800030b4`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180002ee2`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180002ee2`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180002e68`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180002e68`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x180002e1b`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x180002e1b`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x180002e98`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x180002e98`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x180002b91`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x180002fe9`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x1800030d3`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x180002b91`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x180002fe9`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x1800030d3`

## pseudocode

```c
__int64 __fastcall FltpPassThrough(LARGE_INTEGER **a1)
{
  LARGE_INTEGER *v1; // rax
  char *QuadPart; // r14
  ULONG LowPart; // r11d
  struct _FILE_OBJECT *v5; // rdi
  __int64 v6; // r8
  int v7; // r10d
  LARGE_INTEGER v8; // rax
  _BYTE *FsContext; // rax
  unsigned int v11; // ebp
  int v12; // eax
  char v13; // si
  PFSRTL_PER_FILEOBJECT_CONTEXT v14; // rax
  _BYTE *v15; // r15
  LARGE_INTEGER *v16; // rdx
  int v17; // ecx
  LARGE_INTEGER v18; // r12
  __int64 v19; // r13
  __int64 v20; // rax
  unsigned int v21; // ecx
  bool v22; // zf
  __int16 v23; // ax
  LARGE_INTEGER *v24; // r12
  unsigned __int8 v25; // cl
  char v26; // cl
  LARGE_INTEGER *v27; // rax
  LARGE_INTEGER *v28; // rdi
  LARGE_INTEGER v29; // r14
  unsigned int IrpCtrlInternal; // eax
  LARGE_INTEGER *v31; // rax
  unsigned int EcpListFromIrp; // eax
  unsigned int ExtraCreateParameter; // eax
  char v34; // al
  int v35; // eax
  PVOID v36; // r8
  int v37; // ecx
  PFSRTL_PER_FILEOBJECT_CONTEXT v38; // rax
  __int64 v39; // rax
  LARGE_INTEGER *v40; // rcx
  PFSRTL_PER_FILEOBJECT_CONTEXT v41; // rax
  int v42; // edx
  _BYTE *v43; // r8
  int v44; // eax
  unsigned int v45; // eax
  unsigned __int64 v46; // rax
  __int64 v47; // rcx
  unsigned int v48; // esi
  PVOID v49; // rdx
  LARGE_INTEGER v50; // rcx
  LARGE_INTEGER v51; // rdx
  LARGE_INTEGER v52; // rcx
  _DWORD *v53; // rax
  LARGE_INTEGER Interval; // [rsp+70h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+78h] [rbp+10h] BYREF
  PECP_LIST EcpList; // [rsp+80h] [rbp+18h] BYREF

  v1 = a1[1];
  QuadPart = (char *)v1[23].QuadPart;
  LowPart = v1[2].LowPart;
  v5 = (struct _FILE_OBJECT *)*((_QWORD *)QuadPart + 6);
  v6 = (unsigned __int8)(*QuadPart + 22);
  if ( (LARGE_INTEGER *)(*a1)[2 * v6 + 40].QuadPart != &(*a1)[2 * v6 + 40] )
  {
    v7 = *(&(*a1)[140].LowPart + v6);
    if ( !v5 || (v7 & 8) == 0 || (v5->Flags & 0x400000) != 0 )
    {
      if ( (unsigned __int8)(*QuadPart - 3) <= 1u )
      {
        if ( (LowPart & 2) != 0 && (v7 & 1) != 0 )
          goto LABEL_7;
        if ( (LowPart & 1) != 0 )
        {
          if ( (LowPart & 2) == 0 && (v7 & 0x10) != 0 )
            goto LABEL_7;
        }
        else if ( (v7 & 2) != 0 )
        {
          goto LABEL_7;
        }
      }
      if ( v5 )
      {
        FsContext = v5->FsContext;
        if ( (!FsContext || (FsContext[6] & 2) == 0)
          && (((*a1)[7].LowPart & 1) != 0 && (*a1)[7].HighPart != 11
           || (v5->Flags & 0x100) != 0 && !v5->FsContext && *QuadPart == 18) )
        {
          goto LABEL_11;
        }
      }
      *((_DWORD *)a1 + 10) |= 0x200u;
      v11 = 0;
      v12 = *((_DWORD *)a1 + 10);
      EcpContext = 0;
      if ( (v12 & 0x400) != 0 )
      {
        *((_DWORD *)a1 + 10) = v12 & 0xFFFFFBFF;
        goto LABEL_26;
      }
      v13 = *QuadPart;
      if ( *QuadPart == -14 || v13 == -7 )
      {
        v31 = a1[2];
        EcpList = 0;
        Interval.LowPart = 0;
        EcpListFromIrp = FsRtlGetEcpListFromIrp(*(PIRP *)(v31[31].QuadPart + 24), &EcpList);
        if ( (int)FltpDbgStatus(EcpListFromIrp, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 933, 0) < 0 )
          goto LABEL_26;
        if ( !EcpList )
          goto LABEL_26;
        ExtraCreateParameter = FsRtlFindExtraCreateParameter(
                                 EcpList,
                                 &FLTMGR_TIOCTRL_ECP_GUID,
                                 &EcpContext,
                                 (ULONG *)&Interval);
        if ( (int)FltpDbgStatus(ExtraCreateParameter, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 949, 0) < 0
          || FsRtlIsEcpFromUserMode(EcpContext) )
        {
          goto LABEL_26;
        }
      }
      else
      {
        if ( !v5 )
          goto LABEL_26;
        v14 = FsRtlLookupPerFileObjectContext(v5, DriverObject, 0);
        if ( !v14 )
          goto LABEL_26;
        EcpContext = &v14[-1];
      }
      v15 = EcpContext;
      v16 = *a1;
      v17 = *((unsigned __int16 *)EcpContext + 2);
      v18 = (*a1)[13];
      Interval = v18;
      if ( !v17 )
      {
        v19 = *((_QWORD *)EcpContext + 9);
        if ( !v19 )
          goto LABEL_41;
        if ( *(_QWORD *)(*(_QWORD *)(v19 + 64) + 88LL) != v16[11].QuadPart )
        {
          if ( (*((_BYTE *)EcpContext + 6) & 2) != 0 )
            *((_DWORD *)a1 + 10) |= 0x10u;
          goto LABEL_41;
        }
        v20 = *((_QWORD *)EcpContext + 1);
        v21 = *(_DWORD *)(v18.QuadPart + 24);
        v22 = v21 == *(_DWORD *)(v20 + 24);
        if ( v21 <= *(_DWORD *)(v20 + 24) )
        {
          v23 = *((_WORD *)EcpContext + 3);
          if ( v22 )
          {
            if ( (v23 & 0x20) != 0 )
            {
              EcpList = (PECP_LIST)(unsigned __int8)(v13 + 22);
              v24 = *(LARGE_INTEGER **)(v19 + 8LL * (_QWORD)EcpList + 304);
              if ( !v24
                || (*(_DWORD *)(v19 + 80) & 6) != 0
                || !ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v19 + 56), 1u) )
              {
                v24 = 0;
              }
              v25 = (unsigned __int8)EcpList;
              a1[3] = v24;
              v18 = Interval;
            }
            else
            {
              v25 = v13 + 22;
            }
            if ( (v15[6] & 0x20) == 0 || !a1[3] )
              a1[3] = (LARGE_INTEGER *)FltpGetNextCallbackNodeForInstance(v19, v25, 0);
            if ( (v15[6] & 2) == 0 )
              goto LABEL_41;
          }
          else if ( (v23 & 2) == 0 )
          {
            goto LABEL_41;
          }
          goto LABEL_97;
        }
LABEL_84:
        a1[3] = 0;
        goto LABEL_41;
      }
      v37 = v17 - 1;
      if ( !v37 )
        goto LABEL_84;
      if ( v37 == 1 )
      {
        v39 = *((_QWORD *)EcpContext + 8);
        if ( v39 && v39 != v16[11].QuadPart )
        {
          if ( (*((_BYTE *)EcpContext + 6) & 2) == 0 )
            goto LABEL_41;
          goto LABEL_97;
        }
        if ( *(_DWORD *)(v18.QuadPart + 24) > *(_DWORD *)(*((_QWORD *)EcpContext + 1) + 24LL) )
          goto LABEL_84;
        if ( (*((_BYTE *)EcpContext + 6) & 2) != 0 )
LABEL_97:
          *((_DWORD *)a1 + 10) |= 0x10u;
      }
LABEL_41:
      if ( ((_DWORD)a1[5] & 0x200) != 0 )
      {
        if ( v13 == 18 )
        {
          ((void (__fastcall *)(_QWORD, _QWORD))FltpCleanupFileObjectContextForCleanup)(
            (LARGE_INTEGER)v18.QuadPart,
            EcpContext);
        }
        else if ( v13 == 2 )
        {
          ((void (__fastcall *)(_QWORD, _QWORD))FltpCleanupFileObjectContextForClose)(
            (LARGE_INTEGER)v18.QuadPart,
            EcpContext);
          if ( !a1[3] )
            FltpCleanupStreamListCtrlForFileObjectClose(*a1, v5);
        }
      }
LABEL_26:
      if ( !a1[3] )
      {
        *((_DWORD *)a1 + 10) |= 8u;
        return 0;
      }
      v26 = *QuadPart;
      if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*QuadPart + 22)) & 4) != 0 )
      {
        if ( v26 == 17 )
        {
          if ( QuadPart[1] == 3 )
            goto LABEL_51;
        }
        else if ( v26 != 13
               || *((_DWORD *)QuadPart + 6) == 590448
               && !QuadPart[1]
               && *((_DWORD *)QuadPart + 4) >= 4u
               && (*(_DWORD *)a1[1][3].QuadPart & 2) != 0 )
        {
LABEL_51:
          v27 = *a1;
          v28 = a1[1];
          Interval.QuadPart = -100000;
          v29 = v27[8];
          IrpCtrlInternal = FltpAllocateIrpCtrlInternal(v29.LowPart, 1, (_DWORD)v28, (int)a1 + 16);
          if ( (int)FltpDbgStatus(IrpCtrlInternal, "minkernel\\fs\\filtermgr\\filter\\allocateirpctrlsup.c", 951, 0) < 0 )
          {
            do
            {
              if ( (v28[8].QuadPart & 0x2000000000000000LL) == 0 )
                KeDelayExecutionThread(0, 0, &Interval);
              v45 = FltpAllocateIrpCtrlInternal(v29.LowPart, 1, (_DWORD)v28, (int)a1 + 16);
            }
            while ( (int)FltpDbgStatus(v45, "minkernel\\fs\\filtermgr\\filter\\allocateirpctrlsup.c", 951, 0) < 0 );
          }
          goto LABEL_56;
        }
      }
      v11 = FltpAllocateIrpCtrlInternal((*a1)[8].QuadPart, 1, (unsigned int)a1[1], (int)a1 + 16);
LABEL_56:
      if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 2740, 0) >= 0 )
        return FltpPassThroughInternal(a1, 0);
      v40 = a1[3];
      if ( v40 != (LARGE_INTEGER *)-1LL )
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v40[2].QuadPart + 56), 1u);
      FltpCompleteRequest(a1[1], v11);
      return v11;
    }
  }
LABEL_7:
  if ( *QuadPart == 18 )
  {
    v41 = FsRtlLookupPerFileObjectContext(*((PFILE_OBJECT *)QuadPart + 6), DriverObject, 0);
    if ( v41 )
      ((void (__fastcall *)(_QWORD, _QWORD))FltpCleanupFileObjectContextForCleanup)(
        (LARGE_INTEGER)(*a1)[13].QuadPart,
        &v41[-1]);
    goto LABEL_11;
  }
  if ( *QuadPart == 2 )
  {
    v38 = FsRtlLookupPerFileObjectContext(*((PFILE_OBJECT *)QuadPart + 6), DriverObject, 0);
    if ( v38 )
      ((void (__fastcall *)(_QWORD, _QWORD))FltpCleanupFileObjectContextForClose)(
        (LARGE_INTEGER)(*a1)[13].QuadPart,
        &v38[-1]);
    FltpCleanupStreamListCtrlForFileObjectClose(*a1, v5);
    goto LABEL_11;
  }
  v8 = a1[1][23];
  if ( *(_BYTE *)v8.QuadPart != 6
    || (v46 = (unsigned int)(*(_DWORD *)(v8.QuadPart + 16) - 10), (unsigned int)v46 > 0x3E)
    || (v47 = 0x4080000040000003LL, !_bittest64(&v47, v46)) )
  {
    if ( ((*a1)[7].LowPart & 0x100) == 0 )
      goto LABEL_11;
    if ( *QuadPart != 6 )
      goto LABEL_71;
    v42 = *((_DWORD *)QuadPart + 4);
    if ( (unsigned int)(v42 - 19) <= 1 || v42 == 39 )
      goto LABEL_77;
    if ( v42 == 13 )
    {
      v43 = (_BYTE *)a1[1][3].QuadPart;
      if ( !v43 )
        goto LABEL_72;
      if ( *v43 )
        goto LABEL_77;
    }
    if ( v42 == 64 )
    {
      v53 = (_DWORD *)a1[1][3].QuadPart;
      if ( v53 )
      {
        if ( (*v53 & 1) != 0 )
          goto LABEL_77;
LABEL_71:
        if ( *QuadPart == 4
          && ((a1[1][2].LowPart & 1) != 0 || ((*a1)[7].LowPart & 1) != 0 || (*a1)[7].HighPart == 27)
          && (a1[1][2].LowPart & 0x42) == 0 )
        {
          goto LABEL_77;
        }
      }
    }
LABEL_72:
    v34 = *QuadPart;
    if ( *QuadPart || *((_DWORD *)QuadPart + 4) >= 0x1000000u )
    {
      if ( v34 == 13 )
      {
        v44 = *((_DWORD *)QuadPart + 6);
        if ( v44 != 622792 && v44 != 623208 && v44 != 1327346 && v44 != 1343730 && v44 != 590047 )
          goto LABEL_11;
      }
      else
      {
        if ( v34 != 14 )
          goto LABEL_11;
        v35 = *((_DWORD *)QuadPart + 6);
        if ( v35 != 1328152 && v35 != 1344540 )
          goto LABEL_11;
      }
    }
LABEL_77:
    v36 = ExAllocateFromNPagedLookasideList(&stru_18003ED40);
    if ( v36 )
    {
      v51 = a1[1][23];
      *(_OWORD *)(v51.QuadPart - 72) = *(_OWORD *)v51.QuadPart;
      *(_OWORD *)(v51.QuadPart - 56) = *(_OWORD *)(v51.QuadPart + 16);
      *(_OWORD *)(v51.QuadPart - 40) = *(_OWORD *)(v51.QuadPart + 32);
      *(_QWORD *)(v51.QuadPart - 24) = *(_QWORD *)(v51.QuadPart + 48);
      *(_BYTE *)(v51.QuadPart - 69) = 0;
      v52 = a1[1][23];
      *(_QWORD *)(v52.QuadPart - 8) = v36;
LABEL_139:
      *(_QWORD *)(v52.QuadPart - 16) = FltpNoFilterCallbackCompletion;
      *(_BYTE *)(v52.QuadPart - 69) = -32;
      *(_BYTE *)(a1[1][23].QuadPart + 3) |= 1u;
      FltpCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)((*a1)[8].QuadPart + 64) + 8LL), (PIRP)a1[1]);
      return 259;
    }
LABEL_11:
    *((_DWORD *)a1 + 10) |= 8u;
    return 0;
  }
  v48 = FltpInvalidateNameCachingAllFrames(*a1);
  if ( (int)FltpDbgStatus(v48, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 2506, 0) >= 0 )
  {
    v49 = ExAllocateFromNPagedLookasideList(&stru_18003ED40);
    if ( !v49 )
    {
      FltpReinstateNameCachingAllFrames(*a1, 0);
      FltpPurgeVolumeNameCache(*a1, 0, 0);
      goto LABEL_11;
    }
    v50 = a1[1][23];
    *(_OWORD *)(v50.QuadPart - 72) = *(_OWORD *)v50.QuadPart;
    *(_OWORD *)(v50.QuadPart - 56) = *(_OWORD *)(v50.QuadPart + 16);
    *(_OWORD *)(v50.QuadPart - 40) = *(_OWORD *)(v50.QuadPart + 32);
    *(_QWORD *)(v50.QuadPart - 24) = *(_QWORD *)(v50.QuadPart + 48);
    *(_BYTE *)(v50.QuadPart - 69) = 0;
    v52 = a1[1][23];
    *(_QWORD *)(v52.QuadPart - 8) = v49;
    goto LABEL_139;
  }
  FltpCompleteRequest(a1[1], v48);
  return v48;
}

```

## disassembly

```asm
0x180002a40  push    rbx
0x180002a42  push    rbp
0x180002a43  push    rsi
0x180002a44  push    rdi
0x180002a45  push    r14
0x180002a47  sub     rsp, 40h
0x180002a4b  mov     rax, [rcx+8]
0x180002a4f  mov     rbx, rcx
0x180002a52  mov     rdx, [rcx]
0x180002a55  mov     r14, [rax+0B8h]
0x180002a5c  mov     r11d, [rax+10h]
0x180002a60  movzx   r9d, byte ptr [r14]
0x180002a64  mov     rdi, [r14+30h]
0x180002a68  lea     eax, [r9+16h]
0x180002a6c  movzx   r8d, al
0x180002a70  lea     rcx, [r8+14h]
0x180002a74  shl     rcx, 4
0x180002a78  add     rcx, rdx
0x180002a7b  mov     rax, [rcx]
0x180002a7e  cmp     rax, rcx
0x180002a81  jz      short loc_180002AB2
0x180002a83  mov     r10d, [rdx+r8*4+460h]
0x180002a8b  test    rdi, rdi
0x180002a8e  jnz     short loc_180002AFC
0x180002a90  sub     r9b, 3
0x180002a94  cmp     r9b, 1
0x180002a98  ja      loc_180002B29
0x180002a9e  mov     eax, r11d
0x180002aa1  and     eax, 2
0x180002aa4  jnz     short loc_180002B17
0x180002aa6  test    r11b, 1
0x180002aaa  jnz     short loc_180002B1F
0x180002aac  test    r10b, 2
0x180002ab0  jz      short loc_180002B29
0x180002ab2  movzx   eax, byte ptr [r14]
0x180002ab6  cmp     al, 12h
0x180002ab8  jz      loc_1800030C6
0x180002abe  cmp     al, 2
0x180002ac0  jz      loc_180002FDC
0x180002ac6  mov     r8, [rbx+8]
0x180002aca  mov     rax, [r8+0B8h]
0x180002ad1  cmp     byte ptr [rax], 6
0x180002ad4  jz      loc_18002528F
0x180002ada  mov     rax, [rbx]
0x180002add  mov     ecx, [rax+38h]
0x180002ae0  bt      ecx, 8
0x180002ae4  jb      loc_180002EFB
0x180002aea  or      dword ptr [rbx+28h], 8
0x180002aee  xor     eax, eax
0x180002af0  add     rsp, 40h
0x180002af4  pop     r14
0x180002af6  pop     rdi
0x180002af7  pop     rsi
0x180002af8  pop     rbp
0x180002af9  pop     rbx
0x180002afa  retn
0x180002afc  mov     eax, [rdi+50h]
0x180002aff  test    r10b, 8
0x180002b03  setnz   cl
0x180002b06  bt      eax, 16h
0x180002b0a  setnb   al
0x180002b0d  test    al, cl
0x180002b0f  jz      loc_180002A90
0x180002b15  jmp     short loc_180002AB2
0x180002b17  test    r10b, 1
0x180002b1b  jz      short loc_180002AA6
0x180002b1d  jmp     short loc_180002AB2
0x180002b1f  test    eax, eax
0x180002b21  jnz     short loc_180002B29
0x180002b23  test    r10b, 10h
0x180002b27  jnz     short loc_180002AB2
0x180002b29  test    rdi, rdi
0x180002b2c  jz      short loc_180002B47
0x180002b2e  mov     rax, [rdi+18h]
0x180002b32  test    rax, rax
0x180002b35  jz      loc_180002F9D
0x180002b3b  movzx   eax, byte ptr [rax+6]
0x180002b3f  test    al, 2
0x180002b41  jz      loc_180002F9D
0x180002b47  or      dword ptr [rbx+28h], 200h
0x180002b4e  xor     ebp, ebp
0x180002b50  mov     eax, [rbx+28h]
0x180002b53  mov     [rsp+68h+var_38], r15
0x180002b58  mov     [rsp+68h+EcpContext], rbp
0x180002b5d  bt      eax, 0Ah
0x180002b61  jb      loc_180002F67
0x180002b67  movzx   esi, byte ptr [r14]
0x180002b6b  cmp     sil, 0F2h
0x180002b6f  jz      loc_180002DF8
0x180002b75  cmp     sil, 0F9h
0x180002b79  jz      loc_180002DF8
0x180002b7f  test    rdi, rdi
0x180002b82  jz      short loc_180002BA2
0x180002b84  mov     rdx, cs:DriverObject; OwnerId
0x180002b8b  xor     r8d, r8d; InstanceId
0x180002b8e  mov     rcx, rdi; FileObject
0x180002b91  call    cs:__imp_FsRtlLookupPerFileObjectContext
0x180002b98  nop     dword ptr [rax+rax+00h]
0x180002b9d  test    rax, rax
0x180002ba0  jnz     short loc_180002BC3
0x180002ba2  cmp     [rbx+18h], rbp
0x180002ba6  jnz     loc_180002CEA
0x180002bac  or      dword ptr [rbx+28h], 8
0x180002bb0  xor     eax, eax
0x180002bb2  mov     r15, [rsp+68h+var_38]
0x180002bb7  add     rsp, 40h
0x180002bbb  pop     r14
0x180002bbd  pop     rdi
0x180002bbe  pop     rsi
0x180002bbf  pop     rbp
0x180002bc0  pop     rbx
0x180002bc1  retn
0x180002bc3  add     rax, 0FFFFFFFFFFFFFFE0h
0x180002bc7  mov     [rsp+68h+EcpContext], rax
0x180002bcc  mov     r15, [rsp+68h+EcpContext]
0x180002bd1  mov     rdx, [rbx]
0x180002bd4  mov     [rsp+68h+arg_18], r12
0x180002bdc  mov     [rsp+68h+var_30], r13
0x180002be1  movzx   ecx, word ptr [r15+4]
0x180002be6  mov     r12, [rdx+68h]
0x180002bea  mov     qword ptr [rsp+68h+Interval], r12
0x180002bef  test    ecx, ecx
0x180002bf1  jnz     loc_180002F8B
0x180002bf7  mov     r13, [r15+48h]
0x180002bfb  test    r13, r13
0x180002bfe  jz      loc_180002C96
0x180002c04  mov     rcx, [r13+40h]
0x180002c08  mov     rax, [rdx+58h]
0x180002c0c  cmp     [rcx+58h], rax
0x180002c10  jnz     loc_18000300E
0x180002c16  mov     rax, [r15+8]
0x180002c1a  mov     ecx, [r12+18h]
0x180002c1f  cmp     ecx, [rax+18h]
0x180002c22  ja      loc_180002F94
0x180002c28  movzx   eax, word ptr [r15+6]
0x180002c2d  jnz     loc_180002EB1
0x180002c33  test    al, 20h
0x180002c35  jz      loc_180002F83
0x180002c3b  lea     eax, [rsi+16h]
0x180002c3e  movzx   eax, al
0x180002c41  mov     [rsp+68h+EcpList], rax
0x180002c49  mov     r12, [r13+rax*8+130h]
0x180002c51  test    r12, r12
0x180002c54  jnz     loc_180002ECD
0x180002c5a  mov     r12, rbp
0x180002c5d  mov     rcx, [rsp+68h+EcpList]
0x180002c65  mov     [rbx+18h], r12
0x180002c69  mov     r12, qword ptr [rsp+68h+Interval]
0x180002c6e  test    byte ptr [r15+6], 20h
0x180002c73  jnz     loc_180002EBE
0x180002c79  movzx   edx, cl
0x180002c7c  xor     r8d, r8d
0x180002c7f  mov     rcx, r13
0x180002c82  call    FltpGetNextCallbackNodeForInstance
0x180002c87  mov     [rbx+18h], rax
0x180002c8b  test    byte ptr [r15+6], 2
0x180002c90  jnz     loc_18000302D
0x180002c96  test    dword ptr [rbx+28h], 200h
0x180002c9d  mov     r13, [rsp+68h+var_30]
0x180002ca2  jz      short loc_180002CDD
0x180002ca4  cmp     sil, 12h
0x180002ca8  jz      short loc_180002CD0
0x180002caa  cmp     sil, 2
0x180002cae  jnz     short loc_180002CDD
0x180002cb0  mov     rdx, [rsp+68h+EcpContext]
0x180002cb5  mov     rcx, r12
0x180002cb8  call    FltpCleanupFileObjectContextForClose
0x180002cbd  cmp     [rbx+18h], rbp
0x180002cc1  jnz     short loc_180002CDD
0x180002cc3  mov     rcx, [rbx]
0x180002cc6  mov     rdx, rdi
0x180002cc9  call    FltpCleanupStreamListCtrlForFileObjectClose
0x180002cce  jmp     short loc_180002CDD
0x180002cd0  mov     rdx, [rsp+68h+EcpContext]
0x180002cd5  mov     rcx, r12
0x180002cd8  call    FltpCleanupFileObjectContextForCleanup
0x180002cdd  mov     r12, [rsp+68h+arg_18]
0x180002ce5  jmp     loc_180002BA2
0x180002cea  movzx   ecx, byte ptr [r14]
0x180002cee  lea     rdx, FltpOperationFlags
0x180002cf5  lea     eax, [rcx+16h]
0x180002cf8  movzx   eax, al
0x180002cfb  test    byte ptr [rax+rdx], 4
0x180002cff  jz      loc_180002D96
0x180002d05  cmp     cl, 11h
0x180002d08  jz      loc_180002F73
0x180002d0e  cmp     cl, 0Dh
0x180002d11  jz      short loc_180002D88
0x180002d13  mov     rax, [rbx]
0x180002d16  lea     r9, [rbx+10h]
0x180002d1a  mov     rdi, [rbx+8]
0x180002d1e  mov     edx, 1
0x180002d23  mov     r8, rdi
0x180002d26  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFFE7960h
0x180002d2f  mov     r14, [rax+40h]
0x180002d33  lea     rax, [rsp+68h+Interval]
0x180002d38  mov     rcx, r14
0x180002d3b  mov     [rsp+68h+var_40], rax
0x180002d40  call    FltpAllocateIrpCtrlInternal
0x180002d45  mov     r15d, 3B7h
0x180002d4b  lea     rdx, aMinkernelFsFil_1; "minkernel\\fs\\filtermgr\\filter\\alloc"...
0x180002d52  mov     r8d, r15d
0x180002d55  xor     r9d, r9d
0x180002d58  mov     ecx, eax
0x180002d5a  call    FltpDbgStatus
0x180002d5f  test    eax, eax
0x180002d61  jns     short loc_180002DBE
0x180002d63  test    byte ptr [rdi+47h], 20h
0x180002d67  jnz     loc_18002523E
0x180002d6d  lea     r8, [rsp+68h+Interval]; Interval
0x180002d72  xor     edx, edx; Alertable
0x180002d74  xor     ecx, ecx; WaitMode
0x180002d76  call    cs:__imp_KeDelayExecutionThread
0x180002d7d  nop     dword ptr [rax+rax+00h]
0x180002d82  nop
0x180002d83  jmp     loc_18002523E
0x180002d88  cmp     dword ptr [r14+18h], 90270h
0x180002d90  jz      loc_18000306D
0x180002d96  test    rdi, rdi
0x180002d99  jz      short loc_180002D9E
0x180002d9b  mov     eax, [rdi+50h]
0x180002d9e  mov     rcx, [rbx]
0x180002da1  lea     r9, [rbx+10h]
0x180002da5  mov     r8, [rbx+8]
0x180002da9  mov     edx, 1
0x180002dae  mov     [rsp+68h+var_40], rbp
0x180002db3  mov     rcx, [rcx+40h]
0x180002db7  call    FltpAllocateIrpCtrlInternal
0x180002dbc  mov     ebp, eax
0x180002dbe  mov     r8d, 0AB4h
0x180002dc4  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x180002dcb  xor     r9d, r9d
0x180002dce  mov     ecx, ebp
0x180002dd0  call    FltpDbgStatus
0x180002dd5  test    eax, eax
0x180002dd7  js      loc_180003099
0x180002ddd  xor     edx, edx
0x180002ddf  mov     rcx, rbx
0x180002de2  call    FltpPassThroughInternal
0x180002de7  mov     r15, [rsp+68h+var_38]
0x180002dec  add     rsp, 40h
0x180002df0  pop     r14
0x180002df2  pop     rdi
0x180002df3  pop     rsi
0x180002df4  pop     rbp
0x180002df5  pop     rbx
0x180002df6  retn
0x180002df8  mov     rax, [rbx+10h]
0x180002dfc  lea     rdx, [rsp+68h+EcpList]; EcpList
0x180002e04  mov     [rsp+68h+EcpList], rbp
0x180002e0c  mov     dword ptr [rsp+68h+Interval], ebp
0x180002e10  mov     rcx, [rax+0F8h]
0x180002e17  mov     rcx, [rcx+18h]; Irp
0x180002e1b  call    cs:__imp_FsRtlGetEcpListFromIrp
0x180002e22  nop     dword ptr [rax+rax+00h]
0x180002e27  mov     r8d, 3A5h
0x180002e2d  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x180002e34  mov     ecx, eax
0x180002e36  xor     r9d, r9d
0x180002e39  call    FltpDbgStatus
0x180002e3e  test    eax, eax
0x180002e40  js      loc_180002BA2
0x180002e46  mov     rcx, [rsp+68h+EcpList]; EcpList
0x180002e4e  test    rcx, rcx
0x180002e51  jz      loc_180002BA2
0x180002e57  lea     r9, [rsp+68h+Interval]; EcpContextSize
0x180002e5c  lea     r8, [rsp+68h+EcpContext]; EcpContext
0x180002e61  lea     rdx, FLTMGR_TIOCTRL_ECP_GUID; EcpType
0x180002e68  call    cs:__imp_FsRtlFindExtraCreateParameter
0x180002e6f  nop     dword ptr [rax+rax+00h]
0x180002e74  mov     r8d, 3B5h
0x180002e7a  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x180002e81  mov     ecx, eax
0x180002e83  xor     r9d, r9d
0x180002e86  call    FltpDbgStatus
0x180002e8b  test    eax, eax
0x180002e8d  js      loc_180002BA2
0x180002e93  mov     rcx, [rsp+68h+EcpContext]; EcpContext
0x180002e98  call    cs:__imp_FsRtlIsEcpFromUserMode
0x180002e9f  nop     dword ptr [rax+rax+00h]
0x180002ea4  test    al, al
0x180002ea6  jnz     loc_180002BA2
0x180002eac  jmp     loc_180002BCC
0x180002eb1  test    al, 2
0x180002eb3  jz      loc_180002C96
0x180002eb9  jmp     loc_18000302D
0x180002ebe  cmp     [rbx+18h], rbp
0x180002ec2  jnz     loc_180002C8B
0x180002ec8  jmp     loc_180002C79
0x180002ecd  mov     eax, [r13+50h]
0x180002ed1  test    al, 6
0x180002ed3  jnz     loc_180002C5A
0x180002ed9  mov     rcx, [r13+38h]; RunRefCacheAware
0x180002edd  mov     edx, 1; Count
0x180002ee2  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x180002ee9  nop     dword ptr [rax+rax+00h]
0x180002eee  test    al, al
0x180002ef0  jnz     loc_180002C5D
0x180002ef6  jmp     loc_180002C5A
0x180002efb  movzx   ecx, byte ptr [r14]
  ... truncated ...
```
