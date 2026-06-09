# DxgkCreateBundleObjectInternal

- ea: `0x1401b8c8c`
- end: `0x1401b98e6`
- name: `DxgkCreateBundleObjectInternal`
- size: `3162`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x140247190`
- `0x14025ae54`

## callees

- `0x140012b14`
- `0x140013860`
- `0x14001ab20`
- `0x14001b890`
- `0x14001cbe0`
- `0x14001d0e4`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a0240`
- `0x1400a0540`
- `0x1401b8c8c`
- `0x1401e5484`
- `0x14024648c`
- `0x1402467a0`
- `0x140323854`
- `0x14036d1b4`
- `0x14036d238`
- `0x14036d808`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401b9547`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401b9547`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401b9684`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401b9684`
- `ntoskrnl!ObfDereferenceObject` at `0x1401b9693`
- `ntoskrnl!ObfDereferenceObject` at `0x1401b978a`
- `ntoskrnl!ObfDereferenceObject` at `0x1401b97c2`
- `ntoskrnl!ObfDereferenceObject` at `0x1401b9693`
- `ntoskrnl!ObfDereferenceObject` at `0x1401b978a`
- `ntoskrnl!ObfDereferenceObject` at `0x1401b97c2`
- `ntoskrnl!ObfReferenceObject` at `0x1401b9556`
- `ntoskrnl!ObfReferenceObject` at `0x1401b95c4`
- `ntoskrnl!ObfReferenceObject` at `0x1401b9556`
- `ntoskrnl!ObfReferenceObject` at `0x1401b95c4`
- `ntoskrnl!ObCloseHandle` at `0x1401b961f`
- `ntoskrnl!ObCloseHandle` at `0x1401b9767`
- `ntoskrnl!ObCloseHandle` at `0x1401b961f`
- `ntoskrnl!ObCloseHandle` at `0x1401b9767`
- `ntoskrnl!ObCreateObject` at `0x1401b941f`
- `ntoskrnl!ObCreateObject` at `0x1401b941f`
- `ntoskrnl!ObInsertObject` at `0x1401b9586`
- `ntoskrnl!ObInsertObject` at `0x1401b95f1`
- `ntoskrnl!ObInsertObject` at `0x1401b9586`
- `ntoskrnl!ObInsertObject` at `0x1401b95f1`
- `ntoskrnl!ObIsKernelHandle` at `0x1401b9609`
- `ntoskrnl!ObIsKernelHandle` at `0x1401b9609`
- `watchdog!WdLogSingleEntry2` at `0x1401b9442`
- `watchdog!WdLogSingleEntry2` at `0x1401b9640`
- `watchdog!WdLogSingleEntry2` at `0x1401b983c`
- `watchdog!WdLogSingleEntry2` at `0x1401b9442`
- `watchdog!WdLogSingleEntry2` at `0x1401b9640`
- `watchdog!WdLogSingleEntry2` at `0x1401b983c`
- `watchdog!WdLogSingleEntry3` at `0x1401b8ea0`
- `watchdog!WdLogSingleEntry3` at `0x1401b9376`
- `watchdog!WdLogSingleEntry3` at `0x1401b96c2`
- `watchdog!WdLogSingleEntry3` at `0x1401b9732`
- `watchdog!WdLogSingleEntry3` at `0x1401b8ea0`
- `watchdog!WdLogSingleEntry3` at `0x1401b9376`
- `watchdog!WdLogSingleEntry3` at `0x1401b96c2`
- `watchdog!WdLogSingleEntry3` at `0x1401b9732`
- `watchdog!WdLogSingleEntry0` at `0x1401b921b`
- `watchdog!WdLogSingleEntry0` at `0x1401b9274`
- `watchdog!WdLogSingleEntry0` at `0x1401b92ee`
- `watchdog!WdLogSingleEntry0` at `0x1401b9395`
- `watchdog!WdLogSingleEntry0` at `0x1401b9465`
- `watchdog!WdLogSingleEntry0` at `0x1401b921b`
- `watchdog!WdLogSingleEntry0` at `0x1401b9274`
- `watchdog!WdLogSingleEntry0` at `0x1401b92ee`
- `watchdog!WdLogSingleEntry0` at `0x1401b9395`
- `watchdog!WdLogSingleEntry0` at `0x1401b9465`
- `watchdog!WdLogSingleEntry1` at `0x1401b8d55`
- `watchdog!WdLogSingleEntry1` at `0x1401b8dd1`
- `watchdog!WdLogSingleEntry1` at `0x1401b8fb0`
- `watchdog!WdLogSingleEntry1` at `0x1401b8d55`
- `watchdog!WdLogSingleEntry1` at `0x1401b8dd1`
- `watchdog!WdLogSingleEntry1` at `0x1401b8fb0`

## string_xrefs

- `0x1401b8ed8`: `AccessInheritMask (0x%I64x) is invalid for Input handle count (0x%I64x). Returning 0x%I64x`

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
  int SharedResourceNtObject; // edi
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
  int EntryType; // r14d
  struct DXGPROCESS *v20; // r14
  _QWORD *v21; // r10
  __int64 v22; // rdx
  int v23; // r9d
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  PVOID *v27; // r14
  __int64 v28; // rax
  PVOID *v29; // r14
  __int64 v30; // rcx
  DXGSYNCOBJECT *v31; // r9
  __int64 v32; // r9
  PVOID *v33; // r14
  __int64 v34; // rdx
  KPROCESSOR_MODE v35; // r13
  _DWORD *v36; // r14
  char *v37; // r13
  unsigned int j; // r12d
  BOOLEAN IsKernelHandle; // al
  unsigned int v40; // r14d
  unsigned int i; // eax
  PVOID v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v46; // rcx
  __int64 v47; // r8
  int Handle; // [rsp+28h] [rbp-2C0h]
  __int64 Handlea; // [rsp+28h] [rbp-2C0h]
  __int64 v50; // [rsp+30h] [rbp-2B8h]
  unsigned __int8 v52; // [rsp+51h] [rbp-297h]
  size_t Size; // [rsp+60h] [rbp-288h] BYREF
  PVOID Object; // [rsp+68h] [rbp-280h] BYREF
  unsigned int v55; // [rsp+70h] [rbp-278h] BYREF
  __int64 v56; // [rsp+78h] [rbp-270h]
  char v57; // [rsp+80h] [rbp-268h]
  struct DXGPROCESS *Current; // [rsp+88h] [rbp-260h]
  void *Src[10]; // [rsp+90h] [rbp-258h] BYREF
  PVOID *v60; // [rsp+E0h] [rbp-208h]
  _BYTE v61[24]; // [rsp+E8h] [rbp-200h] BYREF
  __int128 v62; // [rsp+100h] [rbp-1E8h]
  __int128 v63; // [rsp+110h] [rbp-1D8h]
  __int128 v64; // [rsp+120h] [rbp-1C8h]
  _DWORD v65[16]; // [rsp+130h] [rbp-1B8h] BYREF
  ACCESS_MASK v66[16]; // [rsp+170h] [rbp-178h] BYREF
  PVOID v67[16]; // [rsp+1B0h] [rbp-138h] BYREF
  _QWORD v68[16]; // [rsp+230h] [rbp-B8h] BYREF

  v6 = a1;
  v52 = a1;
  v55 = -1;
  v56 = 0;
  if ( (qword_14015C500 & 2) != 0 )
  {
    v57 = 1;
    v55 = 2157;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(a1, EventProfilerEnter, a3, 2157);
  }
  else
  {
    v57 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v55, 2157);
  Current = DXGPROCESS::GetCurrent();
  if ( !Current )
  {
    SharedResourceNtObject = -1073741811;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 2121;
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
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v55);
    if ( v57 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v46, EventProfilerExit, v47, v55);
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
    WdLogSingleEntry2(2, LODWORD(Src[0]));
    WdLogGlobalForLineNumber = 2154;
    v9 = LODWORD(Src[0]);
    v50 = 0;
    Handlea = -1073741811;
    v10 = L"Input handle count (0x%I64x) is out of range. Returning 0x%I64x";
    goto LABEL_99;
  }
  if ( ((-1 << SLOBYTE(Src[0])) & (__int64)Src[8]) != 0 )
  {
    SharedResourceNtObject = -1073741811;
    WdLogSingleEntry3(2, LODWORD(Src[8]), LODWORD(Src[0]), -1073741811);
    WdLogGlobalForLineNumber = 2164;
    v9 = LODWORD(Src[8]);
    v50 = -1073741811;
    Handlea = LODWORD(Src[0]);
    v10 = L"AccessInheritMask (0x%I64x) is invalid for Input handle count (0x%I64x). Returning 0x%I64x";
LABEL_99:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v10, v9, Handlea, v50, 0, 0);
    goto LABEL_100;
  }
  memset(v65, 0, sizeof(v65));
  memset(v68, 0, sizeof(v68));
  memset(v66, 0, sizeof(v66));
  if ( v6 == 1 )
  {
    RtlCopyFromUser(v65, Src[1], 4LL * LODWORD(Src[0]));
    RtlCopyFromUser(v68, Src[2], 8LL * LODWORD(Src[0]));
    v11 = Src[3];
    if ( Src[3] )
    {
      RtlCopyFromUser(v66, Src[3], 4LL * LODWORD(Src[0]));
      v11 = Src[3];
    }
    LODWORD(v8) = Src[0];
LABEL_19:
    if ( v11 )
      goto LABEL_27;
    goto LABEL_20;
  }
  Size = 4LL * LODWORD(Src[0]);
  memmove(v65, Src[1], Size);
  memmove(v68, Src[2], 8 * v8);
  v11 = Src[3];
  if ( Src[3] )
  {
    memmove(v66, Src[3], Size);
    goto LABEL_19;
  }
LABEL_20:
  v12 = (unsigned int)v8;
  if ( (_DWORD)v8 )
  {
    if ( ((unsigned __int8)v66 & 4) == 0 )
    {
      v13 = v66;
LABEL_25:
      memset64(v13, 0x1000000010000000uLL, v12 >> 1);
      if ( (v12 & 1) != 0 )
        v13[v12 - 1] = 0x10000000;
      goto LABEL_27;
    }
    v66[0] = 0x10000000;
    v12 = (unsigned int)v8 - 1LL;
    if ( (unsigned int)v8 != 1 )
    {
      v13 = &v66[1];
      goto LABEL_25;
    }
  }
LABEL_27:
  Object = 0;
  memset(v67, 0, sizeof(v67));
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v17 = 0;
  while ( 1 )
  {
    LODWORD(Size) = v17;
    if ( v17 >= (unsigned int)v8 )
      break;
    v18 = v17;
    if ( a6 && *(_QWORD *)(a6 + 8LL * v17) )
    {
      EntryType = v65[v17];
    }
    else
    {
      v20 = Current;
      DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v61, Current);
      v21 = (_QWORD *)((char *)v20 + 280);
      v22 = (v65[v18] >> 6) & 0xFFFFFF;
      if ( (unsigned int)v22 < *((_DWORD *)v20 + 74)
        && (v23 = *(_DWORD *)(*v21 + 16LL * (unsigned int)v22 + 8),
            ((v65[v18] >> 25) & 0x60) == (*(_BYTE *)(*v21 + 16LL * (unsigned int)v22 + 8) & 0x60))
        && (v23 & 0x2000) == 0
        && (v23 & 0x1F) != 0 )
      {
        EntryType = HMGRTABLE::GetEntryType((char *)v20 + 280, v22);
      }
      else
      {
        EntryType = 0;
      }
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v61);
    }
    v24 = (unsigned int)(EntryType - 4);
    if ( EntryType == 4 )
    {
      v32 = 0;
      if ( a6 )
        v32 = *(_QWORD *)(a6 + 8 * v18);
      v33 = &v67[v18];
      LOBYTE(Handle) = 1;
      LOBYTE(v24) = v6;
      SharedResourceNtObject = CreateSharedResourceNtObject(
                                 v24,
                                 v14,
                                 (unsigned int)v65[v18],
                                 v32,
                                 v68[v18],
                                 Handle,
                                 v33);
      if ( SharedResourceNtObject < 0 )
      {
        if ( *v33 )
        {
          WdLogSingleEntry0(1);
          v28 = 2252;
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
          v40 = 0;
          for ( i = (unsigned int)Src[0]; v40 < i; ++v40 )
          {
            v42 = v67[v40];
            if ( v42 )
            {
              ObfDereferenceObject(v42);
              v67[v40] = 0;
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
        v25 = (unsigned int)(EntryType - 9);
        if ( EntryType == 9 )
        {
          v29 = &v67[v18];
          LODWORD(v25) = v6;
          SharedResourceNtObject = CreateSharedKeyedMutexNtObject(v25, v14, (unsigned int)v65[v18]);
          if ( SharedResourceNtObject < 0 )
          {
            if ( *v29 )
            {
              WdLogSingleEntry0(1);
              v28 = 2271;
              goto LABEL_62;
            }
            goto LABEL_63;
          }
          goto LABEL_58;
        }
        v26 = (unsigned int)(EntryType - 11);
        if ( EntryType != 11 )
        {
          if ( EntryType != 14 )
          {
            v34 = (unsigned int)v65[v18];
            SharedResourceNtObject = -1073741811;
            WdLogSingleEntry3(3, v34, EntryType, -1073741811);
            WdLogGlobalForLineNumber = 2320;
            goto LABEL_63;
          }
          v27 = &v67[v18];
          LOBYTE(v26) = v6;
          SharedResourceNtObject = CreateSharedProtectedSessionNtObject(v26, 14, (unsigned int)v65[v18]);
          if ( SharedResourceNtObject < 0 )
          {
            if ( *v27 )
            {
              WdLogSingleEntry0(1);
              v28 = 2310;
              goto LABEL_62;
            }
            goto LABEL_63;
          }
          goto LABEL_58;
        }
      }
      v30 = v68[v18];
      v31 = 0;
      if ( a6 )
        v31 = *(DXGSYNCOBJECT **)(a6 + 8 * v18);
      v60 = &v67[v18];
      SharedResourceNtObject = CreateSharedSyncNtObject(v6, EntryType, v65[v18], v31, v30, 1, v60);
      if ( SharedResourceNtObject < 0 )
      {
        if ( *v60 )
        {
          WdLogSingleEntry0(1);
          v28 = 2291;
          goto LABEL_62;
        }
        goto LABEL_63;
      }
    }
LABEL_58:
    v17 = Size + 1;
    LODWORD(v8) = Src[0];
  }
  v35 = a2;
  LOBYTE(v16) = a2;
  LOBYTE(v15) = v6;
  SharedResourceNtObject = ObCreateObject(v15, g_pDxgkSharedBundleObjectType, Src[4], v16, 0, 248, 0, 0, &Object);
  if ( SharedResourceNtObject < 0 )
  {
    WdLogSingleEntry2(3, Current);
    WdLogGlobalForLineNumber = 2343;
    if ( Object )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2345;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pBundleObject == NULL", 2345, 0, 0, 0, 0);
    }
    goto LABEL_84;
  }
  v36 = Object;
  memset(Object, 0, 0xF8u);
  v36[6] = Src[0];
  memmove(v36 + 8, v67, 8LL * LODWORD(Src[0]));
  memmove(v36 + 40, v66, 4LL * LODWORD(Src[0]));
  *(_OWORD *)v36 = *(_OWORD *)((char *)&Src[5] + 4);
  v36[4] = HIDWORD(Src[7]);
  v36[5] = Src[8];
  *((_BYTE *)v36 + 224) = a2;
  v37 = (char *)(v36 + 58);
  *((_QWORD *)v36 + 29) = 0;
  ExAcquirePushLockExclusiveEx(v36 + 58, 0);
  ObfReferenceObject(v36);
  SharedResourceNtObject = ObInsertObject(Object, 0, (ACCESS_MASK)Src[5], 0, 0, &Src[9]);
  if ( SharedResourceNtObject >= 0 && Src[3] )
  {
    for ( j = 0; j < v36[6]; ++j )
    {
      Size = 0;
      ObfReferenceObject(*(PVOID *)&v36[2 * j + 8]);
      SharedResourceNtObject = ObInsertObject(*(PVOID *)&v36[2 * j + 8], 0, v66[j], 0, 0, (PHANDLE)&Size);
      if ( SharedResourceNtObject < 0 )
      {
        WdLogSingleEntry2(3, *(_QWORD *)&v36[2 * j + 8]);
        WdLogGlobalForLineNumber = 2439;
        break;
      }
      IsKernelHandle = ObIsKernelHandle((HANDLE)Size);
      ObCloseHandle((HANDLE)Size, IsKernelHandle == 0);
    }
    v6 = v52;
    v37 = (char *)(v36 + 58);
    if ( SharedResourceNtObject >= 0 )
    {
      *((_BYTE *)v36 + 242) = 1;
      *((_BYTE *)v36 + 240) = 1;
      goto LABEL_76;
    }
  }
  else
  {
LABEL_76:
    if ( SharedResourceNtObject >= 0 )
      *((_BYTE *)v36 + 243) = 1;
  }
  ExReleasePushLockExclusiveEx(v37, 0);
  ObfDereferenceObject(v36);
  if ( SharedResourceNtObject < 0 )
  {
    if ( !Src[9] )
    {
      WdLogSingleEntry3(3, Object, Current, SharedResourceNtObject);
      WdLogGlobalForLineNumber = 2478;
    }
    Object = 0;
    memset(v67, 0, sizeof(v67));
    goto LABEL_63;
  }
  if ( v6 == 1 )
    RtlWriteULong64ToUser(a5 + 72, Src[9]);
  else
    *((void **)a5 + 9) = Src[9];
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v55);
  if ( v57 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v43, EventProfilerExit, v44, v55);
  return 0;
}

```

## disassembly

```asm
0x1401b8c8c  mov     [rsp+arg_10], rbx
0x1401b8c91  mov     [rsp+arg_18], rsi
0x1401b8c96  push    rdi
0x1401b8c97  push    r12
0x1401b8c99  push    r13
0x1401b8c9b  push    r14
0x1401b8c9d  push    r15
0x1401b8c9f  sub     rsp, 2C0h
0x1401b8ca6  mov     rax, cs:__security_cookie
0x1401b8cad  xor     rax, rsp
0x1401b8cb0  mov     [rsp+2E8h+var_38], rax
0x1401b8cb8  mov     [rsp+2E8h+PreviousMode], dl
0x1401b8cbc  mov     r12b, cl
0x1401b8cbf  mov     [rsp+2E8h+var_297], cl
0x1401b8cc3  mov     [rsp+2E8h+var_290], dl
0x1401b8cc7  mov     r15, [rsp+2E8h+arg_20]
0x1401b8ccf  mov     r13, [rsp+2E8h+arg_28]
0x1401b8cd7  or      edi, 0FFFFFFFFh
0x1401b8cda  mov     [rsp+2E8h+var_278], edi
0x1401b8cde  xor     ebx, ebx
0x1401b8ce0  mov     [rsp+2E8h+var_270], rbx
0x1401b8ce5  mov     rax, cs:qword_14015C500
0x1401b8cec  lea     esi, [rdi+2]
0x1401b8cef  test    al, 2
0x1401b8cf1  jz      short loc_1401B8D20
0x1401b8cf3  mov     [rsp+2E8h+var_268], sil
0x1401b8cfb  mov     [rsp+2E8h+var_278], 86Dh
0x1401b8d03  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x1401b8d0a  jz      short loc_1401B8D27
0x1401b8d0c  mov     r9d, 86Dh
0x1401b8d12  lea     rdx, EventProfilerEnter
0x1401b8d19  call    McTemplateK0q_EtwWriteTransfer
0x1401b8d1e  jmp     short loc_1401B8D27
0x1401b8d20  mov     [rsp+2E8h+var_268], bl
0x1401b8d27  mov     edx, 86Dh
0x1401b8d2c  lea     rcx, [rsp+2E8h+var_278]
0x1401b8d31  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1401b8d36  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1401b8d3b  mov     [rsp+2E8h+var_260], rax
0x1401b8d43  test    rax, rax
0x1401b8d46  jnz     short loc_1401B8D90
0x1401b8d48  mov     rdi, 0FFFFFFFFC000000Dh
0x1401b8d4f  mov     rdx, rdi
0x1401b8d52  lea     ecx, [rax+2]
0x1401b8d55  call    cs:__imp_WdLogSingleEntry1
0x1401b8d5c  nop     dword ptr [rax+rax+00h]
0x1401b8d61  mov     cs:WdLogGlobalForLineNumber, 849h
0x1401b8d6b  mov     [rsp+2E8h+var_2A8], rbx
0x1401b8d70  mov     [rsp+2E8h+var_2B0], rbx
0x1401b8d75  mov     [rsp+2E8h+var_2B8], rbx
0x1401b8d7a  mov     [rsp+2E8h+Handle], rbx
0x1401b8d7f  mov     [rsp+2E8h+NewObject], rdi
0x1401b8d84  lea     r9, aInvalidProcess_4; "Invalid process context, returning 0x%I"...
0x1401b8d8b  jmp     loc_1401B9879
0x1401b8d90  mov     r14d, 50h ; 'P'
0x1401b8d96  mov     r8d, r14d; Size
0x1401b8d99  xor     edx, edx; Val
0x1401b8d9b  lea     rcx, [rsp+2E8h+Src]; void *
0x1401b8da3  call    memset
0x1401b8da8  cmp     r12b, sil
0x1401b8dab  jnz     short loc_1401B8E1F
0x1401b8dad  mov     r8d, r14d; Size
0x1401b8db0  mov     rdx, r15; Src
0x1401b8db3  lea     rcx, [rsp+2E8h+Src]; void *
0x1401b8dbb  call    RtlCopyFromUser
0x1401b8dc0  jmp     loc_1401B8E5F
0x1401b8dc5  mov     rdx, 0FFFFFFFFC000000Dh
0x1401b8dcc  mov     ecx, 3
0x1401b8dd1  call    cs:__imp_WdLogSingleEntry1
0x1401b8dd8  nop     dword ptr [rax+rax+00h]
0x1401b8ddd  mov     cs:WdLogGlobalForLineNumber, 859h
0x1401b8de7  lea     rcx, [rsp+2E8h+var_278]; this
0x1401b8dec  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1401b8df1  cmp     [rsp+2E8h+var_268], 0
0x1401b8df9  jz      short loc_1401B8E15
0x1401b8dfb  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401b8e02  jz      short loc_1401B8E15
0x1401b8e04  mov     r9d, [rsp+2E8h+var_278]
0x1401b8e09  lea     rdx, EventProfilerExit
0x1401b8e10  call    McTemplateK0q_EtwWriteTransfer
0x1401b8e15  mov     eax, 0C000000Dh
0x1401b8e1a  jmp     loc_1401B98B8
0x1401b8e1f  movups  xmm0, xmmword ptr [r15]
0x1401b8e23  movaps  xmmword ptr [rsp+2E8h+Src], xmm0
0x1401b8e2b  movups  xmm1, xmmword ptr [r15+10h]
0x1401b8e30  movaps  xmmword ptr [rsp+2E8h+var_248], xmm1
0x1401b8e38  movups  xmm0, xmmword ptr [r15+20h]
0x1401b8e3d  movaps  xmmword ptr [rsp+2E8h+DesiredAccess], xmm0
0x1401b8e45  movups  xmm1, xmmword ptr [r15+30h]
0x1401b8e4a  movaps  [rsp+2E8h+var_228], xmm1
0x1401b8e52  movups  xmm0, xmmword ptr [r15+40h]
0x1401b8e57  movaps  xmmword ptr [rsp+2E8h+var_218], xmm0
0x1401b8e5f  mov     [rsp+2E8h+var_218+8], rbx
0x1401b8e67  mov     r14d, dword ptr [rsp+2E8h+Src]
0x1401b8e6f  lea     eax, [r14-1]
0x1401b8e73  cmp     eax, 0Fh
0x1401b8e76  ja      loc_1401B982A
0x1401b8e7c  mov     ecx, r14d
0x1401b8e7f  shl     edi, cl
0x1401b8e81  mov     eax, dword ptr [rsp+2E8h+var_218]
0x1401b8e88  test    eax, edi
0x1401b8e8a  jz      short loc_1401B8EE4
0x1401b8e8c  mov     r8d, r14d
0x1401b8e8f  mov     edx, eax
0x1401b8e91  mov     rdi, 0FFFFFFFFC000000Dh
0x1401b8e98  mov     r9, rdi
0x1401b8e9b  mov     ecx, 2
0x1401b8ea0  call    cs:__imp_WdLogSingleEntry3
0x1401b8ea7  nop     dword ptr [rax+rax+00h]
0x1401b8eac  mov     cs:WdLogGlobalForLineNumber, 874h
0x1401b8eb6  mov     ecx, dword ptr [rsp+2E8h+Src]
0x1401b8ebd  mov     eax, dword ptr [rsp+2E8h+var_218]
0x1401b8ec4  mov     [rsp+2E8h+var_2A8], rbx
0x1401b8ec9  mov     [rsp+2E8h+var_2B0], rbx
0x1401b8ece  mov     [rsp+2E8h+var_2B8], rdi
0x1401b8ed3  mov     [rsp+2E8h+Handle], rcx
0x1401b8ed8  lea     r9, aAccessinheritm; "AccessInheritMask (0x%I64x) is invalid "...
0x1401b8edf  jmp     loc_1401B9874
0x1401b8ee4  mov     edi, 40h ; '@'
0x1401b8ee9  mov     r8d, edi; Size
0x1401b8eec  xor     edx, edx; Val
0x1401b8eee  lea     rcx, [rsp+2E8h+var_1B8]; void *
0x1401b8ef6  call    memset
0x1401b8efb  xor     edx, edx; Val
0x1401b8efd  lea     r8d, [rdi+40h]; Size
0x1401b8f01  lea     rcx, [rsp+2E8h+var_B8]; void *
0x1401b8f09  call    memset
0x1401b8f0e  mov     r8d, edi; Size
0x1401b8f11  xor     edx, edx; Val
0x1401b8f13  lea     rcx, [rsp+2E8h+var_178]; void *
0x1401b8f1b  call    memset
0x1401b8f20  cmp     r12b, sil
0x1401b8f23  jnz     loc_1401B8FFE
0x1401b8f29  mov     r8, r14
0x1401b8f2c  shl     r8, 2; Size
0x1401b8f30  mov     rdx, [rsp+2E8h+Src+8]; Src
0x1401b8f38  lea     rcx, [rsp+2E8h+var_1B8]; void *
0x1401b8f40  call    RtlCopyFromUser
0x1401b8f45  mov     r8d, dword ptr [rsp+2E8h+Src]
0x1401b8f4d  shl     r8, 3; Size
0x1401b8f51  mov     rdx, [rsp+2E8h+var_248]; Src
0x1401b8f59  lea     rcx, [rsp+2E8h+var_B8]; void *
0x1401b8f61  call    RtlCopyFromUser
0x1401b8f66  mov     rdi, [rsp+2E8h+var_248+8]
0x1401b8f6e  test    rdi, rdi
0x1401b8f71  jz      short loc_1401B8F97
0x1401b8f73  mov     r8d, dword ptr [rsp+2E8h+Src]
0x1401b8f7b  shl     r8, 2; Size
0x1401b8f7f  mov     rdx, rdi; Src
0x1401b8f82  lea     rcx, [rsp+2E8h+var_178]; void *
0x1401b8f8a  call    RtlCopyFromUser
0x1401b8f8f  mov     rdi, [rsp+2E8h+var_248+8]
0x1401b8f97  mov     r14d, dword ptr [rsp+2E8h+Src]
0x1401b8f9f  jmp     loc_1401B9062
0x1401b8fa4  mov     rdx, 0FFFFFFFFC000000Dh
0x1401b8fab  mov     ecx, 3
0x1401b8fb0  call    cs:__imp_WdLogSingleEntry1
0x1401b8fb7  nop     dword ptr [rax+rax+00h]
0x1401b8fbc  mov     cs:WdLogGlobalForLineNumber, 88Bh
0x1401b8fc6  lea     rcx, [rsp+2E8h+var_278]; this
0x1401b8fcb  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1401b8fd0  cmp     [rsp+2E8h+var_268], 0
0x1401b8fd8  jz      short loc_1401B8FF4
0x1401b8fda  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401b8fe1  jz      short loc_1401B8FF4
0x1401b8fe3  mov     r9d, [rsp+2E8h+var_278]
0x1401b8fe8  lea     rdx, EventProfilerExit
0x1401b8fef  call    McTemplateK0q_EtwWriteTransfer
0x1401b8ff4  mov     eax, 0C000000Dh
0x1401b8ff9  jmp     loc_1401B98B8
0x1401b8ffe  lea     rax, ds:0[r14*4]
0x1401b9006  mov     [rsp+2E8h+Size], rax
0x1401b900b  mov     r8, rax; Size
0x1401b900e  mov     rdx, [rsp+2E8h+Src+8]; Src
0x1401b9016  lea     rcx, [rsp+2E8h+var_1B8]; void *
0x1401b901e  call    memmove
0x1401b9023  lea     r8, ds:0[r14*8]; Size
0x1401b902b  mov     rdx, [rsp+2E8h+var_248]; Src
0x1401b9033  lea     rcx, [rsp+2E8h+var_B8]; void *
0x1401b903b  call    memmove
0x1401b9040  mov     rdi, [rsp+2E8h+var_248+8]
0x1401b9048  test    rdi, rdi
0x1401b904b  jz      short loc_1401B9067
0x1401b904d  mov     r8, [rsp+2E8h+Size]; Size
0x1401b9052  mov     rdx, rdi; Src
0x1401b9055  lea     rcx, [rsp+2E8h+var_178]; void *
0x1401b905d  call    memmove
0x1401b9062  test    rdi, rdi
0x1401b9065  jnz     short loc_1401B90C2
0x1401b9067  mov     edx, r14d
0x1401b906a  test    r14d, r14d
0x1401b906d  jz      short loc_1401B90C2
0x1401b906f  lea     rax, [rsp+2E8h+var_178]
0x1401b9077  test    al, 4
0x1401b9079  jz      short loc_1401B9096
0x1401b907b  mov     [rsp+2E8h+var_178], 10000000h
0x1401b9086  sub     rdx, 1
0x1401b908a  jz      short loc_1401B90C2
0x1401b908c  lea     r8, [rsp+2E8h+var_174]
0x1401b9094  jmp     short loc_1401B909E
0x1401b9096  lea     r8, [rsp+2E8h+var_178]
0x1401b909e  mov     rcx, rdx
0x1401b90a1  shr     rcx, 1
0x1401b90a4  mov     rax, 1000000010000000h
0x1401b90ae  mov     rdi, r8
0x1401b90b1  rep stosq
0x1401b90b4  test    sil, dl
0x1401b90b7  jz      short loc_1401B90C2
0x1401b90b9  mov     dword ptr [r8+rdx*4-4], 10000000h
0x1401b90c2  mov     [rsp+2E8h+Object], rbx
0x1401b90c7  xor     edx, edx; Val
0x1401b90c9  mov     r8d, 80h; Size
0x1401b90cf  lea     rcx, [rsp+2E8h+var_138]; void *
0x1401b90d7  call    memset
0x1401b90dc  xorps   xmm0, xmm0
0x1401b90df  movups  [rsp+2E8h+var_1E8], xmm0
0x1401b90e7  movups  [rsp+2E8h+var_1D8], xmm0
0x1401b90ef  movups  [rsp+2E8h+var_1C8], xmm0
0x1401b90f7  mov     eax, ebx
0x1401b90f9  mov     dword ptr [rsp+2E8h+Size], eax
0x1401b90fd  cmp     eax, r14d
0x1401b9100  jnb     loc_1401B93E6
0x1401b9106  mov     edi, eax
0x1401b9108  test    r13, r13
0x1401b910b  jz      short loc_1401B9121
0x1401b910d  cmp     [r13+rdi*8+0], rbx
0x1401b9112  jz      short loc_1401B9121
0x1401b9114  mov     r14d, [rsp+rdi*4+2E8h+var_1B8]
0x1401b911c  jmp     loc_1401B91A4
0x1401b9121  mov     r14, [rsp+2E8h+var_260]
0x1401b9129  mov     rdx, r14; struct DXGPROCESS *
0x1401b912c  lea     rcx, [rsp+2E8h+var_200]; this
0x1401b9134  call    ??0DXGHANDLETABLELOCKSHARED@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED(DXGPROCESS *)
0x1401b9139  mov     r8d, [rsp+rdi*4+2E8h+var_1B8]
0x1401b9141  lea     r10, [r14+118h]
0x1401b9148  mov     edx, r8d
0x1401b914b  shr     edx, 6
0x1401b914e  and     edx, 0FFFFFFh
0x1401b9154  cmp     edx, [r10+10h]
0x1401b9158  jnb     short loc_1401B9194
0x1401b915a  mov     ecx, edx
0x1401b915c  add     rcx, rcx
0x1401b915f  mov     rax, [r10]
0x1401b9162  mov     r9d, [rax+rcx*8+8]
0x1401b9167  shr     r8d, 19h
0x1401b916b  and     r8d, 60h
0x1401b916f  mov     eax, r9d
0x1401b9172  and     eax, 60h
0x1401b9175  cmp     r8b, al
0x1401b9178  jnz     short loc_1401B9194
0x1401b917a  bt      r9d, 0Dh
0x1401b917f  jb      short loc_1401B9194
0x1401b9181  test    r9b, 1Fh
0x1401b9185  jz      short loc_1401B9194
0x1401b9187  mov     rcx, r10
0x1401b918a  call    ?GetEntryType@HMGRTABLE@@QEAA?AW4_HMGRENTRY_TYPE@@I@Z; HMGRTABLE::GetEntryType(uint)
0x1401b918f  mov     r14d, eax
0x1401b9192  jmp     short loc_1401B9197
0x1401b9194  mov     r14d, ebx
0x1401b9197  lea     rcx, [rsp+2E8h+var_200]; this
0x1401b919f  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401b91a4  mov     ecx, r14d
0x1401b91a7  sub     ecx, 4
0x1401b91aa  jz      loc_1401B9304
0x1401b91b0  sub     ecx, 4
0x1401b91b3  jz      loc_1401B928A
0x1401b91b9  sub     ecx, 1
0x1401b91bc  jz      short loc_1401B9231
0x1401b91be  sub     ecx, 2
0x1401b91c1  jz      loc_1401B928A
0x1401b91c7  cmp     ecx, 3
0x1401b91ca  jnz     loc_1401B935D
0x1401b91d0  lea     r14, [rsp+2E8h+var_138]
0x1401b91d8  lea     r14, [r14+rdi*8]
0x1401b91dc  mov     [rsp+2E8h+var_2B8], r14
0x1401b91e1  mov     byte ptr [rsp+2E8h+Handle], sil
0x1401b91e6  mov     rax, [rsp+rdi*8+2E8h+var_B8]
0x1401b91ee  mov     [rsp+2E8h+NewObject], rax
0x1401b91f3  mov     r8d, [rsp+rdi*4+2E8h+var_1B8]
0x1401b91fb  lea     edx, [rcx+0Bh]
0x1401b91fe  mov     cl, r12b
0x1401b9201  call    ?CreateSharedProtectedSessionNtObject@@YAJDW4_HMGRENTRY_TYPE@@IPEAXPEAU_OBJECT_ATTRIBUTES@@DPEAPEAX@Z; CreateSharedProtectedSessionNtObject(char,_HMGRENTRY_TYPE,uint,void *,_OBJECT_ATTRIBUTES *,char,void * *)
0x1401b9206  mov     edi, eax
0x1401b9208  test    eax, eax
0x1401b920a  jns     loc_1401B934A
0x1401b9210  cmp     [r14], rbx
0x1401b9213  jz      loc_1401B93DC
0x1401b9219  mov     ecx, esi
0x1401b921b  call    cs:__imp_WdLogSingleEntry0
0x1401b9222  nop     dword ptr [rax+rax+00h]
0x1401b9227  mov     eax, 906h
0x1401b922c  jmp     loc_1401B93A6
0x1401b9231  lea     r14, [rsp+2E8h+var_138]
0x1401b9239  lea     r14, [r14+rdi*8]
0x1401b923d  mov     [rsp+2E8h+var_2B8], r14
0x1401b9242  mov     rax, [rsp+rdi*8+2E8h+var_B8]
0x1401b924a  mov     [rsp+2E8h+NewObject], rax
0x1401b924f  mov     r8d, [rsp+rdi*4+2E8h+var_1B8]
0x1401b9257  mov     cl, r12b
0x1401b925a  call    ?CreateSharedKeyedMutexNtObject@@YAJDW4_HMGRENTRY_TYPE@@IPEAXPEAU_OBJECT_ATTRIBUTES@@DPEAPEAX@Z; CreateSharedKeyedMutexNtObject(char,_HMGRENTRY_TYPE,uint,void *,_OBJECT_ATTRIBUTES *,char,void * *)
  ... truncated ...
```
