# DxgkCreateBundleObjectInternal

- ea: `0x1401bb88c`
- end: `0x1401bc4e6`
- name: `DxgkCreateBundleObjectInternal`
- size: `3162`
- prototype: `__int64 __fastcall(__int64, KPROCESSOR_MODE, __int64, __int64, char *, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14024a770`
- `0x14025f4a4`

## callees

- `0x140012cd4`
- `0x140013a20`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001cd10`
- `0x14001d214`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x1401bb88c`
- `0x1401e7804`
- `0x140249180`
- `0x140249494`
- `0x14032a5c4`
- `0x14036d1f4`
- `0x14036d278`
- `0x14036d848`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401bc147`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401bc147`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401bc284`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401bc284`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bc293`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bc38a`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bc3c2`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bc293`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bc38a`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bc3c2`
- `ntoskrnl!ObfReferenceObject` at `0x1401bc156`
- `ntoskrnl!ObfReferenceObject` at `0x1401bc1c4`
- `ntoskrnl!ObfReferenceObject` at `0x1401bc156`
- `ntoskrnl!ObfReferenceObject` at `0x1401bc1c4`
- `ntoskrnl!ObCloseHandle` at `0x1401bc21f`
- `ntoskrnl!ObCloseHandle` at `0x1401bc367`
- `ntoskrnl!ObCloseHandle` at `0x1401bc21f`
- `ntoskrnl!ObCloseHandle` at `0x1401bc367`
- `ntoskrnl!ObCreateObject` at `0x1401bc01f`
- `ntoskrnl!ObCreateObject` at `0x1401bc01f`
- `ntoskrnl!ObInsertObject` at `0x1401bc186`
- `ntoskrnl!ObInsertObject` at `0x1401bc1f1`
- `ntoskrnl!ObInsertObject` at `0x1401bc186`
- `ntoskrnl!ObInsertObject` at `0x1401bc1f1`
- `ntoskrnl!ObIsKernelHandle` at `0x1401bc209`
- `ntoskrnl!ObIsKernelHandle` at `0x1401bc209`
- `watchdog!WdLogSingleEntry2` at `0x1401bc042`
- `watchdog!WdLogSingleEntry2` at `0x1401bc240`
- `watchdog!WdLogSingleEntry2` at `0x1401bc43c`
- `watchdog!WdLogSingleEntry2` at `0x1401bc042`
- `watchdog!WdLogSingleEntry2` at `0x1401bc240`
- `watchdog!WdLogSingleEntry2` at `0x1401bc43c`
- `watchdog!WdLogSingleEntry3` at `0x1401bbaa0`
- `watchdog!WdLogSingleEntry3` at `0x1401bbf76`
- `watchdog!WdLogSingleEntry3` at `0x1401bc2c2`
- `watchdog!WdLogSingleEntry3` at `0x1401bc332`
- `watchdog!WdLogSingleEntry3` at `0x1401bbaa0`
- `watchdog!WdLogSingleEntry3` at `0x1401bbf76`
- `watchdog!WdLogSingleEntry3` at `0x1401bc2c2`
- `watchdog!WdLogSingleEntry3` at `0x1401bc332`
- `watchdog!WdLogSingleEntry0` at `0x1401bbe1b`
- `watchdog!WdLogSingleEntry0` at `0x1401bbe74`
- `watchdog!WdLogSingleEntry0` at `0x1401bbeee`
- `watchdog!WdLogSingleEntry0` at `0x1401bbf95`
- `watchdog!WdLogSingleEntry0` at `0x1401bc065`
- `watchdog!WdLogSingleEntry0` at `0x1401bbe1b`
- `watchdog!WdLogSingleEntry0` at `0x1401bbe74`
- `watchdog!WdLogSingleEntry0` at `0x1401bbeee`
- `watchdog!WdLogSingleEntry0` at `0x1401bbf95`
- `watchdog!WdLogSingleEntry0` at `0x1401bc065`
- `watchdog!WdLogSingleEntry1` at `0x1401bb955`
- `watchdog!WdLogSingleEntry1` at `0x1401bb9d1`
- `watchdog!WdLogSingleEntry1` at `0x1401bbbb0`
- `watchdog!WdLogSingleEntry1` at `0x1401bb955`
- `watchdog!WdLogSingleEntry1` at `0x1401bb9d1`
- `watchdog!WdLogSingleEntry1` at `0x1401bbbb0`

## string_xrefs

- `0x1401bbad8`: `AccessInheritMask (0x%I64x) is invalid for Input handle count (0x%I64x). Returning 0x%I64x`

## pseudocode

```c
__int64 __fastcall DxgkCreateBundleObjectInternal(
        __int64 a1,
        KPROCESSOR_MODE a2,
        __int64 a3,
        __int64 a4,
        char *a5,
        __int64 a6)
{
  unsigned __int8 v6; // r12
  NTSTATUS SharedResourceNtObject; // edi
  __int64 v8; // r14
  __int64 v9; // rax
  const wchar_t *v10; // r9
  void *v11; // rdi
  unsigned __int64 v12; // rdx
  ACCESS_MASK *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rdi
  unsigned int EntryType; // r14d
  struct DXGPROCESS *v20; // r14
  _QWORD *v21; // r10
  unsigned int v22; // edx
  int v23; // r9d
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  PVOID *v27; // r14
  __int64 v28; // rax
  PVOID *v29; // r14
  PVOID *v30; // rcx
  __int64 v31; // r9
  __int64 v32; // r9
  PVOID *v33; // r14
  __int64 v34; // rdx
  KPROCESSOR_MODE v35; // r13
  int v36; // eax
  _DWORD *v37; // r14
  char *v38; // r13
  unsigned int j; // r12d
  NTSTATUS inserted; // eax
  BOOLEAN IsKernelHandle; // al
  unsigned int v42; // r14d
  unsigned int i; // eax
  PVOID v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v48; // rcx
  __int64 v49; // r8
  PVOID *NewObject; // [rsp+20h] [rbp-2C8h]
  int Handle; // [rsp+28h] [rbp-2C0h]
  __int64 Handlea; // [rsp+28h] [rbp-2C0h]
  __int64 v53; // [rsp+30h] [rbp-2B8h]
  __int64 v54; // [rsp+30h] [rbp-2B8h]
  unsigned __int8 v56; // [rsp+51h] [rbp-297h]
  size_t Size; // [rsp+60h] [rbp-288h] BYREF
  PVOID Object; // [rsp+68h] [rbp-280h] BYREF
  unsigned int v59; // [rsp+70h] [rbp-278h] BYREF
  __int64 v60; // [rsp+78h] [rbp-270h]
  char v61; // [rsp+80h] [rbp-268h]
  struct DXGPROCESS *Current; // [rsp+88h] [rbp-260h]
  void *Src[10]; // [rsp+90h] [rbp-258h] BYREF
  PVOID *v64; // [rsp+E0h] [rbp-208h]
  _BYTE v65[24]; // [rsp+E8h] [rbp-200h] BYREF
  __int128 v66; // [rsp+100h] [rbp-1E8h]
  __int128 v67; // [rsp+110h] [rbp-1D8h]
  __int128 v68; // [rsp+120h] [rbp-1C8h]
  _DWORD v69[16]; // [rsp+130h] [rbp-1B8h] BYREF
  ACCESS_MASK v70[16]; // [rsp+170h] [rbp-178h] BYREF
  PVOID v71[16]; // [rsp+1B0h] [rbp-138h] BYREF
  _QWORD v72[16]; // [rsp+230h] [rbp-B8h] BYREF

  v6 = a1;
  v56 = a1;
  v59 = -1;
  v60 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v61 = 1;
    v59 = 2157;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(a1, EventProfilerEnter, a3, 2157);
  }
  else
  {
    v61 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v59, 2157);
  Current = DXGPROCESS::GetCurrent();
  if ( !Current )
  {
    SharedResourceNtObject = -1073741811;
    WdLogSingleEntry1(2, -1073741811);
    WdLogGlobalForLineNumber = 2165;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid process context, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0,
      0);
LABEL_100:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v59);
    if ( v61 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v48, EventProfilerExit, v49, v59);
    }
    return (unsigned int)SharedResourceNtObject;
  }
  memset(Src, 0, sizeof(Src));
  if ( v6 == 1 )
  {
    RtlCopyFromUser(Src, a5, 0x50u);
  }
  else
  {
    *(_OWORD *)Src = *(_OWORD *)a5;
    *(_OWORD *)&Src[2] = *((_OWORD *)a5 + 1);
    *(_OWORD *)&Src[4] = *((_OWORD *)a5 + 2);
    *(_OWORD *)&Src[6] = *((_OWORD *)a5 + 3);
    *(_OWORD *)&Src[8] = *((_OWORD *)a5 + 4);
  }
  Src[9] = 0;
  v8 = LODWORD(Src[0]);
  if ( (unsigned int)(LODWORD(Src[0]) - 1) > 0xF )
  {
    SharedResourceNtObject = -1073741811;
    WdLogSingleEntry2(2, LODWORD(Src[0]), -1073741811);
    WdLogGlobalForLineNumber = 2198;
    v9 = LODWORD(Src[0]);
    v54 = 0;
    Handlea = -1073741811;
    v10 = L"Input handle count (0x%I64x) is out of range. Returning 0x%I64x";
    goto LABEL_99;
  }
  if ( ((-1 << SLOBYTE(Src[0])) & (__int64)Src[8]) != 0 )
  {
    SharedResourceNtObject = -1073741811;
    WdLogSingleEntry3(2, LODWORD(Src[8]), LODWORD(Src[0]), -1073741811);
    WdLogGlobalForLineNumber = 2208;
    v9 = LODWORD(Src[8]);
    v54 = -1073741811;
    Handlea = LODWORD(Src[0]);
    v10 = L"AccessInheritMask (0x%I64x) is invalid for Input handle count (0x%I64x). Returning 0x%I64x";
LABEL_99:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v10, v9, Handlea, v54, 0, 0);
    goto LABEL_100;
  }
  memset(v69, 0, sizeof(v69));
  memset(v72, 0, sizeof(v72));
  memset(v70, 0, sizeof(v70));
  if ( v6 == 1 )
  {
    RtlCopyFromUser(v69, Src[1], 4LL * LODWORD(Src[0]));
    RtlCopyFromUser(v72, Src[2], 8LL * LODWORD(Src[0]));
    v11 = Src[3];
    if ( Src[3] )
    {
      RtlCopyFromUser(v70, Src[3], 4LL * LODWORD(Src[0]));
      v11 = Src[3];
    }
    LODWORD(v8) = Src[0];
LABEL_19:
    if ( v11 )
      goto LABEL_27;
    goto LABEL_20;
  }
  Size = 4LL * LODWORD(Src[0]);
  memmove(v69, Src[1], Size);
  memmove(v72, Src[2], 8 * v8);
  v11 = Src[3];
  if ( Src[3] )
  {
    memmove(v70, Src[3], Size);
    goto LABEL_19;
  }
LABEL_20:
  v12 = (unsigned int)v8;
  if ( (_DWORD)v8 )
  {
    if ( ((unsigned __int8)v70 & 4) == 0 )
    {
      v13 = v70;
LABEL_25:
      memset64(v13, 0x1000000010000000uLL, v12 >> 1);
      if ( (v12 & 1) != 0 )
        v13[v12 - 1] = 0x10000000;
      goto LABEL_27;
    }
    v70[0] = 0x10000000;
    v12 = (unsigned int)v8 - 1LL;
    if ( (unsigned int)v8 != 1 )
    {
      v13 = &v70[1];
      goto LABEL_25;
    }
  }
LABEL_27:
  Object = 0;
  memset(v71, 0, sizeof(v71));
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v17 = 0;
  while ( 1 )
  {
    LODWORD(Size) = v17;
    if ( v17 >= (unsigned int)v8 )
      break;
    v18 = v17;
    if ( a6 && *(_QWORD *)(a6 + 8LL * v17) )
    {
      EntryType = v69[v17];
    }
    else
    {
      v20 = Current;
      DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v65, Current);
      v21 = (_QWORD *)((char *)v20 + 280);
      v22 = (v69[v18] >> 6) & 0xFFFFFF;
      if ( v22 < *((_DWORD *)v20 + 74)
        && (v23 = *(_DWORD *)(*v21 + 16LL * v22 + 8),
            ((v69[v18] >> 25) & 0x60) == (*(_BYTE *)(*v21 + 16LL * v22 + 8) & 0x60))
        && (v23 & 0x2000) == 0
        && (v23 & 0x1F) != 0 )
      {
        EntryType = HMGRTABLE::GetEntryType((char *)v20 + 280);
      }
      else
      {
        EntryType = 0;
      }
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v65);
    }
    v24 = EntryType - 4;
    if ( EntryType == 4 )
    {
      v32 = 0;
      if ( a6 )
        v32 = *(_QWORD *)(a6 + 8 * v18);
      v33 = &v71[v18];
      LOBYTE(Handle) = 1;
      LOBYTE(v24) = v6;
      SharedResourceNtObject = CreateSharedResourceNtObject(
                                 v24,
                                 v14,
                                 (unsigned int)v69[v18],
                                 v32,
                                 v72[v18],
                                 Handle,
                                 v33);
      if ( SharedResourceNtObject < 0 )
      {
        if ( *v33 )
        {
          WdLogSingleEntry0(1);
          v28 = 2296;
LABEL_62:
          WdLogGlobalForLineNumber = v28;
          DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"Objects[i] == NULL", v28, 0, 0, 0, 0);
        }
LABEL_63:
        v35 = a2;
LABEL_84:
        if ( Src[9] )
        {
          ObCloseHandle(Src[9], v35);
          Src[9] = 0;
        }
        else if ( Object )
        {
          ObfDereferenceObject(Object);
          Object = 0;
        }
        else
        {
          v42 = 0;
          for ( i = (unsigned int)Src[0]; v42 < i; ++v42 )
          {
            v44 = v71[v42];
            if ( v44 )
            {
              ObfDereferenceObject(v44);
              v71[v42] = 0;
              i = (unsigned int)Src[0];
            }
          }
        }
        goto LABEL_100;
      }
    }
    else
    {
      if ( EntryType != 8 )
      {
        v25 = EntryType - 9;
        if ( EntryType == 9 )
        {
          v29 = &v71[v18];
          HIDWORD(v53) = HIDWORD(v29);
          LODWORD(v25) = v6;
          SharedResourceNtObject = CreateSharedKeyedMutexNtObject(v25, v14, (unsigned int)v69[v18]);
          if ( SharedResourceNtObject < 0 )
          {
            if ( *v29 )
            {
              WdLogSingleEntry0(1);
              v28 = 2315;
              goto LABEL_62;
            }
            goto LABEL_63;
          }
          goto LABEL_58;
        }
        v26 = EntryType - 11;
        if ( EntryType != 11 )
        {
          if ( EntryType != 14 )
          {
            v34 = (unsigned int)v69[v18];
            SharedResourceNtObject = -1073741811;
            WdLogSingleEntry3(3, v34, (int)EntryType, -1073741811);
            WdLogGlobalForLineNumber = 2364;
            goto LABEL_63;
          }
          v27 = &v71[v18];
          HIDWORD(v53) = HIDWORD(v27);
          LOBYTE(v26) = v6;
          SharedResourceNtObject = CreateSharedProtectedSessionNtObject(v26, 14, (unsigned int)v69[v18]);
          if ( SharedResourceNtObject < 0 )
          {
            if ( *v27 )
            {
              WdLogSingleEntry0(1);
              v28 = 2354;
              goto LABEL_62;
            }
            goto LABEL_63;
          }
          goto LABEL_58;
        }
      }
      v30 = (PVOID *)v72[v18];
      v31 = 0;
      if ( a6 )
        v31 = *(_QWORD *)(a6 + 8 * v18);
      v64 = &v71[v18];
      LOBYTE(Handle) = 1;
      NewObject = v30;
      LOBYTE(v30) = v6;
      SharedResourceNtObject = CreateSharedSyncNtObject(
                                 v30,
                                 EntryType,
                                 (unsigned int)v69[v18],
                                 v31,
                                 NewObject,
                                 Handle,
                                 v64);
      if ( SharedResourceNtObject < 0 )
      {
        if ( *v64 )
        {
          WdLogSingleEntry0(1);
          v28 = 2335;
          goto LABEL_62;
        }
        goto LABEL_63;
      }
    }
LABEL_58:
    v17 = Size + 1;
    LODWORD(v8) = Src[0];
  }
  LODWORD(v53) = 0;
  v35 = a2;
  LOBYTE(v16) = a2;
  LOBYTE(v15) = v6;
  v36 = ObCreateObject(v15, g_pDxgkSharedBundleObjectType, Src[4], v16, 0, 248, v53, 0, &Object);
  SharedResourceNtObject = v36;
  if ( v36 < 0 )
  {
    WdLogSingleEntry2(3, Current, v36);
    WdLogGlobalForLineNumber = 2387;
    if ( Object )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2389;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pBundleObject == NULL", 2389, 0, 0, 0, 0);
    }
    goto LABEL_84;
  }
  v37 = Object;
  memset(Object, 0, 0xF8u);
  v37[6] = Src[0];
  memmove(v37 + 8, v71, 8LL * LODWORD(Src[0]));
  memmove(v37 + 40, v70, 4LL * LODWORD(Src[0]));
  *(_OWORD *)v37 = *(_OWORD *)((char *)&Src[5] + 4);
  v37[4] = HIDWORD(Src[7]);
  v37[5] = Src[8];
  *((_BYTE *)v37 + 224) = a2;
  v38 = (char *)(v37 + 58);
  *((_QWORD *)v37 + 29) = 0;
  ExAcquirePushLockExclusiveEx(v37 + 58, 0);
  ObfReferenceObject(v37);
  SharedResourceNtObject = ObInsertObject(Object, 0, (ACCESS_MASK)Src[5], 0, 0, &Src[9]);
  if ( SharedResourceNtObject >= 0 && Src[3] )
  {
    for ( j = 0; j < v37[6]; ++j )
    {
      Size = 0;
      ObfReferenceObject(*(PVOID *)&v37[2 * j + 8]);
      inserted = ObInsertObject(*(PVOID *)&v37[2 * j + 8], 0, v70[j], 0, 0, (PHANDLE)&Size);
      SharedResourceNtObject = inserted;
      if ( inserted < 0 )
      {
        WdLogSingleEntry2(3, *(_QWORD *)&v37[2 * j + 8], inserted);
        WdLogGlobalForLineNumber = 2483;
        break;
      }
      IsKernelHandle = ObIsKernelHandle((HANDLE)Size);
      ObCloseHandle((HANDLE)Size, IsKernelHandle == 0);
    }
    v6 = v56;
    v38 = (char *)(v37 + 58);
    if ( SharedResourceNtObject >= 0 )
    {
      *((_BYTE *)v37 + 242) = 1;
      *((_BYTE *)v37 + 240) = 1;
      goto LABEL_76;
    }
  }
  else
  {
LABEL_76:
    if ( SharedResourceNtObject >= 0 )
      *((_BYTE *)v37 + 243) = 1;
  }
  ExReleasePushLockExclusiveEx(v38, 0);
  ObfDereferenceObject(v37);
  if ( SharedResourceNtObject < 0 )
  {
    if ( !Src[9] )
    {
      WdLogSingleEntry3(3, Object, Current, SharedResourceNtObject);
      WdLogGlobalForLineNumber = 2522;
    }
    Object = 0;
    memset(v71, 0, sizeof(v71));
    goto LABEL_63;
  }
  if ( v6 == 1 )
    RtlWriteULong64ToUser(a5 + 72, Src[9]);
  else
    *((void **)a5 + 9) = Src[9];
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v59);
  if ( v61 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v45, EventProfilerExit, v46, v59);
  return 0;
}

```

## disassembly

```asm
0x1401bb88c  mov     [rsp+arg_10], rbx
0x1401bb891  mov     [rsp+arg_18], rsi
0x1401bb896  push    rdi
0x1401bb897  push    r12
0x1401bb899  push    r13
0x1401bb89b  push    r14
0x1401bb89d  push    r15
0x1401bb89f  sub     rsp, 2C0h
0x1401bb8a6  mov     rax, cs:__security_cookie
0x1401bb8ad  xor     rax, rsp
0x1401bb8b0  mov     [rsp+2E8h+var_38], rax
0x1401bb8b8  mov     [rsp+2E8h+PreviousMode], dl
0x1401bb8bc  mov     r12b, cl
0x1401bb8bf  mov     [rsp+2E8h+var_297], cl
0x1401bb8c3  mov     [rsp+2E8h+var_290], dl
0x1401bb8c7  mov     r15, [rsp+2E8h+arg_20]
0x1401bb8cf  mov     r13, [rsp+2E8h+arg_28]
0x1401bb8d7  or      edi, 0FFFFFFFFh
0x1401bb8da  mov     [rsp+2E8h+var_278], edi
0x1401bb8de  xor     ebx, ebx
0x1401bb8e0  mov     [rsp+2E8h+var_270], rbx
0x1401bb8e5  mov     rax, cs:qword_1401604F0
0x1401bb8ec  lea     esi, [rdi+2]
0x1401bb8ef  test    al, 2
0x1401bb8f1  jz      short loc_1401BB920
0x1401bb8f3  mov     [rsp+2E8h+var_268], sil
0x1401bb8fb  mov     [rsp+2E8h+var_278], 86Dh
0x1401bb903  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x1401bb90a  jz      short loc_1401BB927
0x1401bb90c  mov     r9d, 86Dh
0x1401bb912  lea     rdx, EventProfilerEnter
0x1401bb919  call    McTemplateK0q_EtwWriteTransfer
0x1401bb91e  jmp     short loc_1401BB927
0x1401bb920  mov     [rsp+2E8h+var_268], bl
0x1401bb927  mov     edx, 86Dh
0x1401bb92c  lea     rcx, [rsp+2E8h+var_278]
0x1401bb931  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1401bb936  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1401bb93b  mov     [rsp+2E8h+var_260], rax
0x1401bb943  test    rax, rax
0x1401bb946  jnz     short loc_1401BB990
0x1401bb948  mov     rdi, 0FFFFFFFFC000000Dh
0x1401bb94f  mov     rdx, rdi
0x1401bb952  lea     ecx, [rax+2]
0x1401bb955  call    cs:__imp_WdLogSingleEntry1
0x1401bb95c  nop     dword ptr [rax+rax+00h]
0x1401bb961  mov     cs:WdLogGlobalForLineNumber, 875h
0x1401bb96b  mov     [rsp+2E8h+var_2A8], rbx
0x1401bb970  mov     [rsp+2E8h+var_2B0], rbx
0x1401bb975  mov     [rsp+2E8h+var_2B8], rbx
0x1401bb97a  mov     [rsp+2E8h+Handle], rbx
0x1401bb97f  mov     [rsp+2E8h+NewObject], rdi
0x1401bb984  lea     r9, aInvalidProcess_4; "Invalid process context, returning 0x%I"...
0x1401bb98b  jmp     loc_1401BC479
0x1401bb990  mov     r14d, 50h ; 'P'
0x1401bb996  mov     r8d, r14d; Size
0x1401bb999  xor     edx, edx; Val
0x1401bb99b  lea     rcx, [rsp+2E8h+Src]; void *
0x1401bb9a3  call    memset
0x1401bb9a8  cmp     r12b, sil
0x1401bb9ab  jnz     short loc_1401BBA1F
0x1401bb9ad  mov     r8d, r14d; Size
0x1401bb9b0  mov     rdx, r15; Src
0x1401bb9b3  lea     rcx, [rsp+2E8h+Src]; void *
0x1401bb9bb  call    RtlCopyFromUser
0x1401bb9c0  jmp     loc_1401BBA5F
0x1401bb9c5  mov     rdx, 0FFFFFFFFC000000Dh
0x1401bb9cc  mov     ecx, 3
0x1401bb9d1  call    cs:__imp_WdLogSingleEntry1
0x1401bb9d8  nop     dword ptr [rax+rax+00h]
0x1401bb9dd  mov     cs:WdLogGlobalForLineNumber, 885h
0x1401bb9e7  lea     rcx, [rsp+2E8h+var_278]; this
0x1401bb9ec  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1401bb9f1  cmp     [rsp+2E8h+var_268], 0
0x1401bb9f9  jz      short loc_1401BBA15
0x1401bb9fb  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401bba02  jz      short loc_1401BBA15
0x1401bba04  mov     r9d, [rsp+2E8h+var_278]
0x1401bba09  lea     rdx, EventProfilerExit
0x1401bba10  call    McTemplateK0q_EtwWriteTransfer
0x1401bba15  mov     eax, 0C000000Dh
0x1401bba1a  jmp     loc_1401BC4B8
0x1401bba1f  movups  xmm0, xmmword ptr [r15]
0x1401bba23  movaps  xmmword ptr [rsp+2E8h+Src], xmm0
0x1401bba2b  movups  xmm1, xmmword ptr [r15+10h]
0x1401bba30  movaps  xmmword ptr [rsp+2E8h+var_248], xmm1
0x1401bba38  movups  xmm0, xmmword ptr [r15+20h]
0x1401bba3d  movaps  xmmword ptr [rsp+2E8h+DesiredAccess], xmm0
0x1401bba45  movups  xmm1, xmmword ptr [r15+30h]
0x1401bba4a  movaps  [rsp+2E8h+var_228], xmm1
0x1401bba52  movups  xmm0, xmmword ptr [r15+40h]
0x1401bba57  movaps  xmmword ptr [rsp+2E8h+var_218], xmm0
0x1401bba5f  mov     [rsp+2E8h+var_218+8], rbx
0x1401bba67  mov     r14d, dword ptr [rsp+2E8h+Src]
0x1401bba6f  lea     eax, [r14-1]
0x1401bba73  cmp     eax, 0Fh
0x1401bba76  ja      loc_1401BC42A
0x1401bba7c  mov     ecx, r14d
0x1401bba7f  shl     edi, cl
0x1401bba81  mov     eax, dword ptr [rsp+2E8h+var_218]
0x1401bba88  test    eax, edi
0x1401bba8a  jz      short loc_1401BBAE4
0x1401bba8c  mov     r8d, r14d
0x1401bba8f  mov     edx, eax
0x1401bba91  mov     rdi, 0FFFFFFFFC000000Dh
0x1401bba98  mov     r9, rdi
0x1401bba9b  mov     ecx, 2
0x1401bbaa0  call    cs:__imp_WdLogSingleEntry3
0x1401bbaa7  nop     dword ptr [rax+rax+00h]
0x1401bbaac  mov     cs:WdLogGlobalForLineNumber, 8A0h
0x1401bbab6  mov     ecx, dword ptr [rsp+2E8h+Src]
0x1401bbabd  mov     eax, dword ptr [rsp+2E8h+var_218]
0x1401bbac4  mov     [rsp+2E8h+var_2A8], rbx
0x1401bbac9  mov     [rsp+2E8h+var_2B0], rbx
0x1401bbace  mov     [rsp+2E8h+var_2B8], rdi
0x1401bbad3  mov     [rsp+2E8h+Handle], rcx
0x1401bbad8  lea     r9, aAccessinheritm; "AccessInheritMask (0x%I64x) is invalid "...
0x1401bbadf  jmp     loc_1401BC474
0x1401bbae4  mov     edi, 40h ; '@'
0x1401bbae9  mov     r8d, edi; Size
0x1401bbaec  xor     edx, edx; Val
0x1401bbaee  lea     rcx, [rsp+2E8h+var_1B8]; void *
0x1401bbaf6  call    memset
0x1401bbafb  xor     edx, edx; Val
0x1401bbafd  lea     r8d, [rdi+40h]; Size
0x1401bbb01  lea     rcx, [rsp+2E8h+var_B8]; void *
0x1401bbb09  call    memset
0x1401bbb0e  mov     r8d, edi; Size
0x1401bbb11  xor     edx, edx; Val
0x1401bbb13  lea     rcx, [rsp+2E8h+var_178]; void *
0x1401bbb1b  call    memset
0x1401bbb20  cmp     r12b, sil
0x1401bbb23  jnz     loc_1401BBBFE
0x1401bbb29  mov     r8, r14
0x1401bbb2c  shl     r8, 2; Size
0x1401bbb30  mov     rdx, [rsp+2E8h+Src+8]; Src
0x1401bbb38  lea     rcx, [rsp+2E8h+var_1B8]; void *
0x1401bbb40  call    RtlCopyFromUser
0x1401bbb45  mov     r8d, dword ptr [rsp+2E8h+Src]
0x1401bbb4d  shl     r8, 3; Size
0x1401bbb51  mov     rdx, [rsp+2E8h+var_248]; Src
0x1401bbb59  lea     rcx, [rsp+2E8h+var_B8]; void *
0x1401bbb61  call    RtlCopyFromUser
0x1401bbb66  mov     rdi, [rsp+2E8h+var_248+8]
0x1401bbb6e  test    rdi, rdi
0x1401bbb71  jz      short loc_1401BBB97
0x1401bbb73  mov     r8d, dword ptr [rsp+2E8h+Src]
0x1401bbb7b  shl     r8, 2; Size
0x1401bbb7f  mov     rdx, rdi; Src
0x1401bbb82  lea     rcx, [rsp+2E8h+var_178]; void *
0x1401bbb8a  call    RtlCopyFromUser
0x1401bbb8f  mov     rdi, [rsp+2E8h+var_248+8]
0x1401bbb97  mov     r14d, dword ptr [rsp+2E8h+Src]
0x1401bbb9f  jmp     loc_1401BBC62
0x1401bbba4  mov     rdx, 0FFFFFFFFC000000Dh
0x1401bbbab  mov     ecx, 3
0x1401bbbb0  call    cs:__imp_WdLogSingleEntry1
0x1401bbbb7  nop     dword ptr [rax+rax+00h]
0x1401bbbbc  mov     cs:WdLogGlobalForLineNumber, 8B7h
0x1401bbbc6  lea     rcx, [rsp+2E8h+var_278]; this
0x1401bbbcb  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1401bbbd0  cmp     [rsp+2E8h+var_268], 0
0x1401bbbd8  jz      short loc_1401BBBF4
0x1401bbbda  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401bbbe1  jz      short loc_1401BBBF4
0x1401bbbe3  mov     r9d, [rsp+2E8h+var_278]
0x1401bbbe8  lea     rdx, EventProfilerExit
0x1401bbbef  call    McTemplateK0q_EtwWriteTransfer
0x1401bbbf4  mov     eax, 0C000000Dh
0x1401bbbf9  jmp     loc_1401BC4B8
0x1401bbbfe  lea     rax, ds:0[r14*4]
0x1401bbc06  mov     [rsp+2E8h+Size], rax
0x1401bbc0b  mov     r8, rax; Size
0x1401bbc0e  mov     rdx, [rsp+2E8h+Src+8]; Src
0x1401bbc16  lea     rcx, [rsp+2E8h+var_1B8]; void *
0x1401bbc1e  call    memmove
0x1401bbc23  lea     r8, ds:0[r14*8]; Size
0x1401bbc2b  mov     rdx, [rsp+2E8h+var_248]; Src
0x1401bbc33  lea     rcx, [rsp+2E8h+var_B8]; void *
0x1401bbc3b  call    memmove
0x1401bbc40  mov     rdi, [rsp+2E8h+var_248+8]
0x1401bbc48  test    rdi, rdi
0x1401bbc4b  jz      short loc_1401BBC67
0x1401bbc4d  mov     r8, [rsp+2E8h+Size]; Size
0x1401bbc52  mov     rdx, rdi; Src
0x1401bbc55  lea     rcx, [rsp+2E8h+var_178]; void *
0x1401bbc5d  call    memmove
0x1401bbc62  test    rdi, rdi
0x1401bbc65  jnz     short loc_1401BBCC2
0x1401bbc67  mov     edx, r14d
0x1401bbc6a  test    r14d, r14d
0x1401bbc6d  jz      short loc_1401BBCC2
0x1401bbc6f  lea     rax, [rsp+2E8h+var_178]
0x1401bbc77  test    al, 4
0x1401bbc79  jz      short loc_1401BBC96
0x1401bbc7b  mov     [rsp+2E8h+var_178], 10000000h
0x1401bbc86  sub     rdx, 1
0x1401bbc8a  jz      short loc_1401BBCC2
0x1401bbc8c  lea     r8, [rsp+2E8h+var_174]
0x1401bbc94  jmp     short loc_1401BBC9E
0x1401bbc96  lea     r8, [rsp+2E8h+var_178]
0x1401bbc9e  mov     rcx, rdx
0x1401bbca1  shr     rcx, 1
0x1401bbca4  mov     rax, 1000000010000000h
0x1401bbcae  mov     rdi, r8
0x1401bbcb1  rep stosq
0x1401bbcb4  test    sil, dl
0x1401bbcb7  jz      short loc_1401BBCC2
0x1401bbcb9  mov     dword ptr [r8+rdx*4-4], 10000000h
0x1401bbcc2  mov     [rsp+2E8h+Object], rbx
0x1401bbcc7  xor     edx, edx; Val
0x1401bbcc9  mov     r8d, 80h; Size
0x1401bbccf  lea     rcx, [rsp+2E8h+var_138]; void *
0x1401bbcd7  call    memset
0x1401bbcdc  xorps   xmm0, xmm0
0x1401bbcdf  movups  [rsp+2E8h+var_1E8], xmm0
0x1401bbce7  movups  [rsp+2E8h+var_1D8], xmm0
0x1401bbcef  movups  [rsp+2E8h+var_1C8], xmm0
0x1401bbcf7  mov     eax, ebx
0x1401bbcf9  mov     dword ptr [rsp+2E8h+Size], eax
0x1401bbcfd  cmp     eax, r14d
0x1401bbd00  jnb     loc_1401BBFE6
0x1401bbd06  mov     edi, eax
0x1401bbd08  test    r13, r13
0x1401bbd0b  jz      short loc_1401BBD21
0x1401bbd0d  cmp     [r13+rdi*8+0], rbx
0x1401bbd12  jz      short loc_1401BBD21
0x1401bbd14  mov     r14d, [rsp+rdi*4+2E8h+var_1B8]
0x1401bbd1c  jmp     loc_1401BBDA4
0x1401bbd21  mov     r14, [rsp+2E8h+var_260]
0x1401bbd29  mov     rdx, r14; struct DXGPROCESS *
0x1401bbd2c  lea     rcx, [rsp+2E8h+var_200]; this
0x1401bbd34  call    ??0DXGHANDLETABLELOCKSHARED@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED(DXGPROCESS *)
0x1401bbd39  mov     r8d, [rsp+rdi*4+2E8h+var_1B8]
0x1401bbd41  lea     r10, [r14+118h]
0x1401bbd48  mov     edx, r8d
0x1401bbd4b  shr     edx, 6
0x1401bbd4e  and     edx, 0FFFFFFh
0x1401bbd54  cmp     edx, [r10+10h]
0x1401bbd58  jnb     short loc_1401BBD94
0x1401bbd5a  mov     ecx, edx
0x1401bbd5c  add     rcx, rcx
0x1401bbd5f  mov     rax, [r10]
0x1401bbd62  mov     r9d, [rax+rcx*8+8]
0x1401bbd67  shr     r8d, 19h
0x1401bbd6b  and     r8d, 60h
0x1401bbd6f  mov     eax, r9d
0x1401bbd72  and     eax, 60h
0x1401bbd75  cmp     r8b, al
0x1401bbd78  jnz     short loc_1401BBD94
0x1401bbd7a  bt      r9d, 0Dh
0x1401bbd7f  jb      short loc_1401BBD94
0x1401bbd81  test    r9b, 1Fh
0x1401bbd85  jz      short loc_1401BBD94
0x1401bbd87  mov     rcx, r10
0x1401bbd8a  call    ?GetEntryType@HMGRTABLE@@QEAA?AW4_HMGRENTRY_TYPE@@I@Z; HMGRTABLE::GetEntryType(uint)
0x1401bbd8f  mov     r14d, eax
0x1401bbd92  jmp     short loc_1401BBD97
0x1401bbd94  mov     r14d, ebx
0x1401bbd97  lea     rcx, [rsp+2E8h+var_200]; this
0x1401bbd9f  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401bbda4  mov     ecx, r14d
0x1401bbda7  sub     ecx, 4
0x1401bbdaa  jz      loc_1401BBF04
0x1401bbdb0  sub     ecx, 4
0x1401bbdb3  jz      loc_1401BBE8A
0x1401bbdb9  sub     ecx, 1
0x1401bbdbc  jz      short loc_1401BBE31
0x1401bbdbe  sub     ecx, 2
0x1401bbdc1  jz      loc_1401BBE8A
0x1401bbdc7  cmp     ecx, 3
0x1401bbdca  jnz     loc_1401BBF5D
0x1401bbdd0  lea     r14, [rsp+2E8h+var_138]
0x1401bbdd8  lea     r14, [r14+rdi*8]
0x1401bbddc  mov     [rsp+2E8h+var_2B8], r14
0x1401bbde1  mov     byte ptr [rsp+2E8h+Handle], sil
0x1401bbde6  mov     rax, [rsp+rdi*8+2E8h+var_B8]
0x1401bbdee  mov     [rsp+2E8h+NewObject], rax
0x1401bbdf3  mov     r8d, [rsp+rdi*4+2E8h+var_1B8]
0x1401bbdfb  lea     edx, [rcx+0Bh]
0x1401bbdfe  mov     cl, r12b
0x1401bbe01  call    ?CreateSharedProtectedSessionNtObject@@YAJDW4_HMGRENTRY_TYPE@@IPEAXPEAU_OBJECT_ATTRIBUTES@@DPEAPEAX@Z; CreateSharedProtectedSessionNtObject(char,_HMGRENTRY_TYPE,uint,void *,_OBJECT_ATTRIBUTES *,char,void * *)
0x1401bbe06  mov     edi, eax
0x1401bbe08  test    eax, eax
0x1401bbe0a  jns     loc_1401BBF4A
0x1401bbe10  cmp     [r14], rbx
0x1401bbe13  jz      loc_1401BBFDC
0x1401bbe19  mov     ecx, esi
0x1401bbe1b  call    cs:__imp_WdLogSingleEntry0
0x1401bbe22  nop     dword ptr [rax+rax+00h]
0x1401bbe27  mov     eax, 932h
0x1401bbe2c  jmp     loc_1401BBFA6
0x1401bbe31  lea     r14, [rsp+2E8h+var_138]
0x1401bbe39  lea     r14, [r14+rdi*8]
0x1401bbe3d  mov     [rsp+2E8h+var_2B8], r14
0x1401bbe42  mov     rax, [rsp+rdi*8+2E8h+var_B8]
0x1401bbe4a  mov     [rsp+2E8h+NewObject], rax
0x1401bbe4f  mov     r8d, [rsp+rdi*4+2E8h+var_1B8]
0x1401bbe57  mov     cl, r12b
0x1401bbe5a  call    ?CreateSharedKeyedMutexNtObject@@YAJDW4_HMGRENTRY_TYPE@@IPEAXPEAU_OBJECT_ATTRIBUTES@@DPEAPEAX@Z; CreateSharedKeyedMutexNtObject(char,_HMGRENTRY_TYPE,uint,void *,_OBJECT_ATTRIBUTES *,char,void * *)
  ... truncated ...
```
