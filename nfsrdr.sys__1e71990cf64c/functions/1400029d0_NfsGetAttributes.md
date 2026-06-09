# NfsGetAttributes

- ea: `0x1400029d0`
- end: `0x140003370`
- name: `NfsGetAttributes`
- size: `2464`
- prototype: ``
- caller_count: `10`
- callee_count: `24`
- tags: `installer_update`

## callers

- `0x140001100`
- `0x1400022c0`
- `0x140004530`
- `0x14000be20`
- `0x140014760`
- `0x140018804`
- `0x140019044`
- `0x14001a950`
- `0x14001d6b0`
- `0x140025be0`

## callees

- `0x140001760`
- `0x140001f10`
- `0x1400029d0`
- `0x140003380`
- `0x140005c90`
- `0x140008140`
- `0x14000fb40`
- `0x140010870`
- `0x140011960`
- `0x140011f84`
- `0x1400145f0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x14001837c`
- `0x1400200d0`
- `0x1400204c0`
- `0x140020b64`
- `0x140022220`
- `0x140022270`
- `0x140023dd0`
- `0x14002ddac`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140002a6b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002ae6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002cf3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002ef5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002a6b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002ae6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002cf3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002ef5`
- `ntoskrnl!KeReleaseMutex` at `0x140002b61`
- `ntoskrnl!KeReleaseMutex` at `0x140002be2`
- `ntoskrnl!KeReleaseMutex` at `0x140002c47`
- `ntoskrnl!KeReleaseMutex` at `0x140002e1c`
- `ntoskrnl!KeReleaseMutex` at `0x140002f1d`
- `ntoskrnl!KeReleaseMutex` at `0x140003191`
- `ntoskrnl!KeReleaseMutex` at `0x140003214`
- `ntoskrnl!KeReleaseMutex` at `0x140002b61`
- `ntoskrnl!KeReleaseMutex` at `0x140002be2`
- `ntoskrnl!KeReleaseMutex` at `0x140002c47`
- `ntoskrnl!KeReleaseMutex` at `0x140002e1c`
- `ntoskrnl!KeReleaseMutex` at `0x140002f1d`
- `ntoskrnl!KeReleaseMutex` at `0x140003191`
- `ntoskrnl!KeReleaseMutex` at `0x140003214`
- `rpcxdr!OncRpcDestroy` at `0x140002f33`
- `rpcxdr!OncRpcDestroy` at `0x1400031c1`
- `rpcxdr!OncRpcDestroy` at `0x14000327c`
- `rpcxdr!OncRpcDestroy` at `0x14000328d`
- `rpcxdr!OncRpcDestroy` at `0x140003305`
- `rpcxdr!OncRpcDestroy` at `0x140002f33`
- `rpcxdr!OncRpcDestroy` at `0x1400031c1`
- `rpcxdr!OncRpcDestroy` at `0x14000327c`
- `rpcxdr!OncRpcDestroy` at `0x14000328d`
- `rpcxdr!OncRpcDestroy` at `0x140003305`

## pseudocode

```c
__int64 __fastcall NfsGetAttributes(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  __int64 v7; // rbx
  __int64 v8; // r12
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  struct _KMUTANT *v12; // r8
  struct _LIST_ENTRY *v13; // rax
  __int64 v14; // rcx
  __int16 v15; // di
  __int64 v16; // rdx
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  unsigned int *v19; // rdi
  int v20; // r12d
  __int64 v21; // r13
  int v22; // edi
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  char *v28; // rcx
  __int64 v29; // rax
  char v30; // r8
  char *v31; // r8
  unsigned int v32; // r9d
  unsigned int v33; // r9d
  __int64 v34; // rcx
  union _LARGE_INTEGER v35; // rdx
  _DWORD *v36; // r8
  int v37; // ecx
  int v38; // ecx
  int v39; // eax
  __int64 v40; // rbx
  int v41; // eax
  _DWORD *v42; // r8
  unsigned int v43; // eax
  unsigned int v44; // r12d
  struct _DEVICE_OBJECT *v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rsi
  __int64 v48; // rdi
  __int64 v49; // rdx
  bool v51; // [rsp+50h] [rbp-A8h]
  _DWORD *v52; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v53[10]; // [rsp+60h] [rbp-98h] BYREF

  v3 = *(_QWORD *)(a2 + 80);
  v52 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  v7 = *(_QWORD *)(a1 + 40);
  if ( !v7 )
    return 3221225662LL;
  v8 = MEMORY[0xFFFFF78000000014];
  KeWaitForSingleObject(*(PVOID *)(a3 + 40), Executive, 0, 0, 0);
  v9 = *(_QWORD *)(a3 + 40);
  if ( *(_QWORD *)(v9 + 88) )
  {
    if ( *(_QWORD *)(v9 + 96) == a3 )
      goto LABEL_14;
    v10 = *(_QWORD *)(a3 + 16);
    if ( v10 )
    {
      v11 = *(_QWORD *)(a3 + 24);
      if ( v11 )
      {
        *(_QWORD *)(v11 + 16) = v10;
        *(_QWORD *)(*(_QWORD *)(a3 + 16) + 24LL) = *(_QWORD *)(a3 + 24);
      }
      else
      {
        *(_QWORD *)(v9 + 88) = v10;
        *(_QWORD *)(*(_QWORD *)(a3 + 16) + 24LL) = 0;
      }
    }
    *(_QWORD *)(*(_QWORD *)(v9 + 96) + 16LL) = a3;
    *(_QWORD *)(a3 + 24) = *(_QWORD *)(v9 + 96);
    *(_QWORD *)(a3 + 16) = 0;
  }
  else
  {
    *(_QWORD *)(v9 + 88) = a3;
  }
  *(_QWORD *)(v9 + 96) = a3;
LABEL_14:
  KeWaitForSingleObject(*(PVOID *)(a3 + 40), Executive, 0, 0, 0);
  v12 = *(struct _KMUTANT **)(a3 + 40);
  if ( v12[1].MutantListEntry.Blink )
  {
    if ( v12[1].OwnerThread == (struct _KTHREAD *)a3 )
      goto LABEL_23;
    v13 = *(struct _LIST_ENTRY **)(a3 + 16);
    if ( v13 )
    {
      v14 = *(_QWORD *)(a3 + 24);
      if ( v14 )
      {
        *(_QWORD *)(v14 + 16) = v13;
        *(_QWORD *)(*(_QWORD *)(a3 + 16) + 24LL) = *(_QWORD *)(a3 + 24);
      }
      else
      {
        v12[1].MutantListEntry.Blink = v13;
        *(_QWORD *)(*(_QWORD *)(a3 + 16) + 24LL) = 0;
      }
    }
    *((_QWORD *)v12[1].OwnerThread + 2) = a3;
    *(_QWORD *)(a3 + 24) = v12[1].OwnerThread;
    *(_QWORD *)(a3 + 16) = 0;
  }
  else
  {
    v12[1].MutantListEntry.Blink = (struct _LIST_ENTRY *)a3;
  }
  v12[1].OwnerThread = (struct _KTHREAD *)a3;
  v12 = *(struct _KMUTANT **)(a3 + 40);
LABEL_23:
  v15 = *(_WORD *)(a3 + 48) >> 15;
  KeReleaseMutex(v12, 0);
  if ( (_BYTE)v15 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_Zi(
        WPP_GLOBAL_Control->AttachedDevice,
        38,
        (unsigned int)WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids,
        a3 + 64,
        (v8 - *(_QWORD *)(a3 + 120)) / 600000000);
    goto LABEL_29;
  }
  v16 = *(_QWORD *)(v7 + 144) + *(_QWORD *)(a3 + 120);
  if ( v16 > v8 || v16 < 0 )
  {
LABEL_29:
    KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      return 0;
    v18 = 28;
    goto LABEL_112;
  }
  KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
  v19 = *(unsigned int **)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL);
  if ( !v19 )
    return 3221225662LL;
  v20 = v19[22];
  v51 = v20 == 3;
  v21 = NfsRdrBuildCall((__int64)(v19 + 29), v19[20], v19[21], v20, 1, 68, a1);
  if ( !v21 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v22 = -1073741670;
    goto LABEL_119;
  }
  KeWaitForSingleObject(*(PVOID *)(a3 + 40), Executive, 0, 0, 0);
  v23 = *(_QWORD *)(a3 + 40);
  if ( *(_QWORD *)(v23 + 88) )
  {
    if ( *(_QWORD *)(v23 + 96) == a3 )
      goto LABEL_50;
    v24 = *(_QWORD *)(a3 + 16);
    if ( v24 )
    {
      v25 = *(_QWORD *)(a3 + 24);
      if ( v25 )
      {
        *(_QWORD *)(v25 + 16) = v24;
        *(_QWORD *)(*(_QWORD *)(a3 + 16) + 24LL) = *(_QWORD *)(a3 + 24);
      }
      else
      {
        *(_QWORD *)(v23 + 88) = v24;
        *(_QWORD *)(*(_QWORD *)(a3 + 16) + 24LL) = 0;
      }
    }
    *(_QWORD *)(*(_QWORD *)(v23 + 96) + 16LL) = a3;
    *(_QWORD *)(a3 + 24) = *(_QWORD *)(v23 + 96);
    *(_QWORD *)(a3 + 16) = 0;
  }
  else
  {
    *(_QWORD *)(v23 + 88) = a3;
  }
  *(_QWORD *)(v23 + 96) = a3;
LABEL_50:
  if ( v20 == 3 )
  {
    v32 = *(_DWORD *)(a3 + 216);
    if ( v32 > 0x40 )
    {
      *(_DWORD *)(a3 + 216) = 0;
      v32 = 0;
    }
    XdrEncodeIntUnsafe(v21, v32);
    XdrEncodeOpaqueUnsafe(v34, v33);
  }
  else
  {
    v26 = *(_QWORD *)(v21 + 72);
    if ( v26 )
      v26 = *(_QWORD *)(v26 + 64);
    *(_OWORD *)v26 = *(_OWORD *)(a3 + 220);
    *(_OWORD *)(v26 + 16) = *(_OWORD *)(a3 + 236);
    *(_QWORD *)(*(_QWORD *)(v21 + 72) + 64LL) += 32LL;
    v27 = *(_QWORD *)(v21 + 72);
    if ( v27 )
    {
      v29 = *(_QWORD *)(v27 + 56);
      v28 = *(char **)(v27 + 64);
      v30 = (char)v28;
    }
    else
    {
      v28 = 0;
      LOBYTE(v29) = 0;
      v30 = 0;
    }
    *(_QWORD *)(v27 + 64) += ((_BYTE)v29 - v30) & 3;
    v31 = *(char **)(v21 + 72);
    if ( v31 )
      v31 = (char *)*((_QWORD *)v31 + 8);
    if ( v28 != v31 )
      memset(v28, 0, v31 - v28);
  }
  KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
  if ( *(int *)(v21 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v22 = *(_DWORD *)(v21 + 264);
    goto LABEL_118;
  }
  v22 = NfsSendWaitReplyWaitInternal(
          v3,
          v35,
          a2,
          *(unsigned int **)(a1 + 40),
          (__int64)(v19 + 18),
          v21,
          &v52,
          *(_BYTE *)(*(_QWORD *)(a1 + 40) + 16LL) == 2,
          0);
  if ( v22 < 0 )
    goto LABEL_78;
  v36 = v52;
  if ( v52 )
  {
    v37 = v52[68];
    if ( v37 )
    {
      if ( v37 != 1 )
        goto LABEL_81;
      v38 = v52[72];
      if ( v38 )
      {
        if ( v38 == 1 )
          v39 = -1073741790;
        else
          v39 = -1073741823;
      }
      else
      {
        v39 = -1073741628;
      }
    }
    else
    {
      v39 = OncRpcpMapRpcAcceptedStatusToNtStatus((unsigned int)v52[160]);
    }
    if ( v39 == -1073741790 )
    {
      v40 = *(_QWORD *)(a1 + 40);
      KeWaitForSingleObject(*(PVOID *)(v40 + 184), Executive, 0, 0, 0);
      if ( *(_DWORD *)(v40 + 200) != 1 )
        *(_DWORD *)(v40 + 200) = 2;
      KeReleaseMutex(*(PRKMUTEX *)(v40 + 184), 0);
      v22 = -1069481983;
      OncRpcDestroy(v52);
      v52 = 0;
LABEL_78:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          31,
          WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
          (unsigned int)v22);
      goto LABEL_118;
    }
  }
LABEL_81:
  v41 = OncRpcMapRpcStatusToNtStatus(v36);
  v22 = v41;
  if ( v41 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
        (unsigned int)v41);
      v42 = v52;
    }
    goto LABEL_102;
  }
  v43 = XdrDecodeInt(v42);
  v42 = v52;
  v44 = v43;
  v22 = v52[66];
  if ( v22 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      v42 = v52;
    }
    goto LABEL_102;
  }
  if ( !v43 )
  {
    HacAcquireLock(a3);
    XdrDecodeNfsFileAttributes(v52, a3 + 128, v51);
    KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
    v42 = v52;
    v22 = v52[66];
    if ( v22 >= 0 )
    {
      HacUpdateTimeStamp(a3);
      OncRpcDestroy(v21);
      OncRpcDestroy(v52);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        return 0;
      v18 = 37;
LABEL_112:
      WPP_SF_(v17->AttachedDevice, v18, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      v42 = v52;
    }
    goto LABEL_102;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, v43);
  v22 = MapNFSStatusToNtStatus(v44);
  if ( v22 == -1073741816 )
  {
    if ( WPP_GLOBAL_Control != v45 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, a3 + 64);
    if ( !*(_WORD *)(a3 + 64) )
    {
      memset(v53, 0, 0x44u);
      v46 = *(_QWORD *)(a1 + 32);
      v47 = *(_QWORD *)(v46 + 40);
      if ( v47 )
      {
        v48 = *(_QWORD *)(v46 + 32);
        HacReference(*(_QWORD *)(v47 + 40));
        v22 = MntMount(v48, a2, v47, v7, (PCUNICODE_STRING)(v47 + 24), (unsigned int *)v53);
        if ( v22 >= 0 )
        {
          HacAcquireLock(*(_QWORD *)(v47 + 40));
          v49 = *(_QWORD *)(v47 + 40);
          *(_OWORD *)(v49 + 216) = *(_OWORD *)v53;
          *(_OWORD *)(v49 + 232) = *(_OWORD *)&v53[2];
          *(_OWORD *)(v49 + 248) = *(_OWORD *)&v53[4];
          *(_OWORD *)(v49 + 264) = *(_OWORD *)&v53[6];
          *(_DWORD *)(v49 + 280) = v53[8];
          DeleteDirCache(v3, *(_QWORD *)(v47 + 40));
          KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v47 + 40) + 40LL), 0);
          HacUpdateTimeStamp(*(_QWORD *)(v47 + 40));
          HacDereference(v3, *(_QWORD *)(v47 + 40));
LABEL_101:
          v42 = v52;
          goto LABEL_102;
        }
        HacDereference(v3, *(_QWORD *)(v47 + 40));
      }
    }
    HacOrphanStaleEntry(v3, a3);
    HacInvalidateAttributes(a3);
    goto LABEL_101;
  }
LABEL_102:
  OncRpcDestroy(v42);
LABEL_118:
  OncRpcDestroy(v21);
LABEL_119:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, (unsigned int)v22);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1400029d0  push    rbx
0x1400029d2  push    rbp
0x1400029d3  push    rsi
0x1400029d4  push    rdi
0x1400029d5  push    r13
0x1400029d7  push    r14
0x1400029d9  push    r15
0x1400029db  sub     rsp, 0C0h
0x1400029e2  mov     rax, cs:__security_cookie
0x1400029e9  xor     rax, rsp
0x1400029ec  mov     [rsp+0F8h+var_48], rax
0x1400029f4  mov     r15, [rdx+50h]
0x1400029f8  xor     edi, edi
0x1400029fa  mov     [rsp+0F8h+var_A0], rdi
0x1400029ff  mov     rbp, r8
0x140002a02  mov     r14, rdx
0x140002a05  mov     rsi, rcx
0x140002a08  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a0f  lea     r13, WPP_GLOBAL_Control
0x140002a16  cmp     rcx, r13
0x140002a19  jz      short loc_140002A37
0x140002a1b  mov     eax, [rcx+2Ch]
0x140002a1e  test    al, 40h
0x140002a20  jz      short loc_140002A37
0x140002a22  mov     rcx, [rcx+18h]
0x140002a26  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140002a2d  mov     edx, 1Ah
0x140002a32  call    WPP_SF_
0x140002a37  mov     rbx, [rsi+28h]
0x140002a3b  mov     [rsp+0F8h+arg_18], r12
0x140002a43  test    rbx, rbx
0x140002a46  jz      loc_140003340
0x140002a4c  mov     r12, 0FFFFF78000000014h
0x140002a56  mov     [rsp+0F8h+Timeout], rdi; Timeout
0x140002a5b  xor     r9d, r9d; Alertable
0x140002a5e  xor     r8d, r8d; WaitMode
0x140002a61  xor     edx, edx; WaitReason
0x140002a63  mov     r12, [r12]
0x140002a67  mov     rcx, [rbp+28h]; Object
0x140002a6b  call    cs:__imp_KeWaitForSingleObject
0x140002a72  nop     dword ptr [rax+rax+00h]
0x140002a77  mov     rdx, [rbp+28h]
0x140002a7b  cmp     [rdx+58h], rdi
0x140002a7f  jz      short loc_140002ACD
0x140002a81  cmp     [rdx+60h], rbp
0x140002a85  jz      short loc_140002AD5
0x140002a87  mov     rax, [rbp+10h]
0x140002a8b  test    rax, rax
0x140002a8e  jz      short loc_140002AB7
0x140002a90  mov     rcx, [rbp+18h]
0x140002a94  test    rcx, rcx
0x140002a97  jz      short loc_140002AAB
0x140002a99  mov     [rcx+10h], rax
0x140002a9d  mov     rcx, [rbp+10h]
0x140002aa1  mov     rax, [rbp+18h]
0x140002aa5  mov     [rcx+18h], rax
0x140002aa9  jmp     short loc_140002AB7
0x140002aab  mov     [rdx+58h], rax
0x140002aaf  mov     rax, [rbp+10h]
0x140002ab3  mov     [rax+18h], rdi
0x140002ab7  mov     rax, [rdx+60h]
0x140002abb  mov     [rax+10h], rbp
0x140002abf  mov     rax, [rdx+60h]
0x140002ac3  mov     [rbp+18h], rax
0x140002ac7  mov     [rbp+10h], rdi
0x140002acb  jmp     short loc_140002AD1
0x140002acd  mov     [rdx+58h], rbp
0x140002ad1  mov     [rdx+60h], rbp
0x140002ad5  mov     rcx, [rbp+28h]; Object
0x140002ad9  xor     r9d, r9d; Alertable
0x140002adc  xor     r8d, r8d; WaitMode
0x140002adf  mov     [rsp+0F8h+Timeout], rdi; Timeout
0x140002ae4  xor     edx, edx; WaitReason
0x140002ae6  call    cs:__imp_KeWaitForSingleObject
0x140002aed  nop     dword ptr [rax+rax+00h]
0x140002af2  mov     r8, [rbp+28h]
0x140002af6  cmp     [r8+58h], rdi
0x140002afa  jz      short loc_140002B48
0x140002afc  cmp     [r8+60h], rbp
0x140002b00  jz      short loc_140002B54
0x140002b02  mov     rax, [rbp+10h]
0x140002b06  test    rax, rax
0x140002b09  jz      short loc_140002B32
0x140002b0b  mov     rcx, [rbp+18h]
0x140002b0f  test    rcx, rcx
0x140002b12  jz      short loc_140002B26
0x140002b14  mov     [rcx+10h], rax
0x140002b18  mov     rcx, [rbp+10h]
0x140002b1c  mov     rax, [rbp+18h]
0x140002b20  mov     [rcx+18h], rax
0x140002b24  jmp     short loc_140002B32
0x140002b26  mov     [r8+58h], rax
0x140002b2a  mov     rax, [rbp+10h]
0x140002b2e  mov     [rax+18h], rdi
0x140002b32  mov     rax, [r8+60h]
0x140002b36  mov     [rax+10h], rbp
0x140002b3a  mov     rax, [r8+60h]
0x140002b3e  mov     [rbp+18h], rax
0x140002b42  mov     [rbp+10h], rdi
0x140002b46  jmp     short loc_140002B4C
0x140002b48  mov     [r8+58h], rbp
0x140002b4c  mov     [r8+60h], rbp
0x140002b50  mov     r8, [rbp+28h]
0x140002b54  movzx   edi, word ptr [rbp+30h]
0x140002b58  xor     edx, edx; Wait
0x140002b5a  mov     rcx, r8; Mutex
0x140002b5d  shr     di, 0Fh
0x140002b61  call    cs:__imp_KeReleaseMutex
0x140002b68  nop     dword ptr [rax+rax+00h]
0x140002b6d  test    dil, dil
0x140002b70  jz      short loc_140002BC7
0x140002b72  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b79  cmp     rcx, r13
0x140002b7c  jz      short loc_140002BDC
0x140002b7e  mov     eax, [rcx+2Ch]
0x140002b81  test    al, 2
0x140002b83  jz      short loc_140002BDC
0x140002b85  sub     r12, [rbp+78h]
0x140002b89  lea     r9, [rbp+40h]
0x140002b8d  mov     rcx, [rcx+18h]
0x140002b91  mov     rax, 1CA213D840BAF7D5h
0x140002b9b  imul    r12
0x140002b9e  mov     r8, rdx
0x140002ba1  mov     edx, 26h ; '&'
0x140002ba6  sar     r8, 1Ah
0x140002baa  mov     rax, r8
0x140002bad  shr     rax, 3Fh
0x140002bb1  add     r8, rax
0x140002bb4  mov     [rsp+0F8h+Timeout], r8
0x140002bb9  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140002bc0  call    WPP_SF_Zi
0x140002bc5  jmp     short loc_140002BDC
0x140002bc7  mov     rdx, [rbp+78h]
0x140002bcb  add     rdx, [rbx+90h]
0x140002bd2  cmp     rdx, r12
0x140002bd5  jg      short loc_140002BDC
0x140002bd7  test    rdx, rdx
0x140002bda  jns     short loc_140002C41
0x140002bdc  mov     rcx, [rbp+28h]; Mutex
0x140002be0  xor     edx, edx; Wait
0x140002be2  call    cs:__imp_KeReleaseMutex
0x140002be9  nop     dword ptr [rax+rax+00h]
0x140002bee  mov     rcx, cs:WPP_GLOBAL_Control
0x140002bf5  cmp     rcx, r13
0x140002bf8  jz      loc_1400032C8
0x140002bfe  test    dword ptr [rcx+2Ch], 2000h
0x140002c05  jz      short loc_140002C1C
0x140002c07  mov     rcx, [rcx+18h]
0x140002c0b  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140002c12  mov     edx, 1Bh
0x140002c17  call    WPP_SF_
0x140002c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c23  cmp     rcx, r13
0x140002c26  jz      loc_1400032C8
0x140002c2c  mov     eax, [rcx+2Ch]
0x140002c2f  test    al, 40h
0x140002c31  jz      loc_1400032C8
0x140002c37  mov     edx, 1Ch
0x140002c3c  jmp     loc_1400032B8
0x140002c41  mov     rcx, [rbp+28h]; Mutex
0x140002c45  xor     edx, edx; Wait
0x140002c47  call    cs:__imp_KeReleaseMutex
0x140002c4e  nop     dword ptr [rax+rax+00h]
0x140002c53  mov     rax, [rsi+20h]
0x140002c57  mov     rcx, [rax+20h]
0x140002c5b  mov     rdi, [rcx+20h]
0x140002c5f  test    rdi, rdi
0x140002c62  jz      loc_140003340
0x140002c68  mov     r12d, [rdi+58h]
0x140002c6c  lea     rcx, [rdi+74h]
0x140002c70  mov     r8d, [rdi+54h]
0x140002c74  cmp     r12d, 3
0x140002c78  mov     edx, [rdi+50h]
0x140002c7b  mov     r9d, r12d
0x140002c7e  mov     [rsp+0F8h+var_C8], rsi
0x140002c83  setz    [rsp+0F8h+var_A8]
0x140002c88  mov     dword ptr [rsp+0F8h+var_D0], 44h ; 'D'
0x140002c90  mov     dword ptr [rsp+0F8h+Timeout], 1
0x140002c98  call    NfsRdrBuildCall
0x140002c9d  mov     r13, rax
0x140002ca0  test    rax, rax
0x140002ca3  jnz     short loc_140002CDE
0x140002ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x140002cac  lea     rbx, WPP_GLOBAL_Control
0x140002cb3  cmp     rcx, rbx
0x140002cb6  jz      short loc_140002CD4
0x140002cb8  mov     eax, [rcx+2Ch]
0x140002cbb  test    al, 1
0x140002cbd  jz      short loc_140002CD4
0x140002cbf  mov     rcx, [rcx+18h]
0x140002cc3  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140002cca  mov     edx, 1Dh
0x140002ccf  call    WPP_SF_
0x140002cd4  mov     edi, 0C000009Ah
0x140002cd9  jmp     loc_140003311
0x140002cde  mov     rcx, [rbp+28h]; Object
0x140002ce2  xor     r9d, r9d; Alertable
0x140002ce5  xor     r8d, r8d; WaitMode
0x140002ce8  mov     [rsp+0F8h+Timeout], 0; Timeout
0x140002cf1  xor     edx, edx; WaitReason
0x140002cf3  call    cs:__imp_KeWaitForSingleObject
0x140002cfa  nop     dword ptr [rax+rax+00h]
0x140002cff  mov     rdx, [rbp+28h]
0x140002d03  cmp     qword ptr [rdx+58h], 0
0x140002d08  jz      short loc_140002D5E
0x140002d0a  cmp     [rdx+60h], rbp
0x140002d0e  jz      short loc_140002D66
0x140002d10  mov     rax, [rbp+10h]
0x140002d14  test    rax, rax
0x140002d17  jz      short loc_140002D44
0x140002d19  mov     rcx, [rbp+18h]
0x140002d1d  test    rcx, rcx
0x140002d20  jz      short loc_140002D34
0x140002d22  mov     [rcx+10h], rax
0x140002d26  mov     rcx, [rbp+10h]
0x140002d2a  mov     rax, [rbp+18h]
0x140002d2e  mov     [rcx+18h], rax
0x140002d32  jmp     short loc_140002D44
0x140002d34  mov     [rdx+58h], rax
0x140002d38  mov     rax, [rbp+10h]
0x140002d3c  mov     qword ptr [rax+18h], 0
0x140002d44  mov     rax, [rdx+60h]
0x140002d48  mov     [rax+10h], rbp
0x140002d4c  mov     rax, [rdx+60h]
0x140002d50  mov     [rbp+18h], rax
0x140002d54  mov     qword ptr [rbp+10h], 0
0x140002d5c  jmp     short loc_140002D62
0x140002d5e  mov     [rdx+58h], rbp
0x140002d62  mov     [rdx+60h], rbp
0x140002d66  cmp     r12d, 3
0x140002d6a  jz      short loc_140002DE2
0x140002d6c  mov     rax, [r13+48h]
0x140002d70  test    rax, rax
0x140002d73  jz      short loc_140002D79
0x140002d75  mov     rax, [rax+40h]
0x140002d79  movups  xmm0, xmmword ptr [rbp+0DCh]
0x140002d80  movups  xmmword ptr [rax], xmm0
0x140002d83  movups  xmm1, xmmword ptr [rbp+0ECh]
0x140002d8a  movups  xmmword ptr [rax+10h], xmm1
0x140002d8e  mov     rax, [r13+48h]
0x140002d92  add     qword ptr [rax+40h], 20h ; ' '
0x140002d97  mov     rdx, [r13+48h]
0x140002d9b  mov     r9, [rdx+40h]
0x140002d9f  test    rdx, rdx
0x140002da2  jnz     short loc_140002DAD
0x140002da4  xor     ecx, ecx
0x140002da6  xor     eax, eax
0x140002da8  xor     r8d, r8d
0x140002dab  jmp     short loc_140002DB7
0x140002dad  mov     rax, [rdx+38h]
0x140002db1  mov     rcx, r9; void *
0x140002db4  mov     r8, r9
0x140002db7  sub     rax, r8
0x140002dba  and     eax, 3
0x140002dbd  add     rax, r9
0x140002dc0  mov     [rdx+40h], rax
0x140002dc4  mov     r8, [r13+48h]
0x140002dc8  test    r8, r8
0x140002dcb  jz      short loc_140002DD1
0x140002dcd  mov     r8, [r8+40h]
0x140002dd1  cmp     rcx, r8
0x140002dd4  jz      short loc_140002E16
0x140002dd6  sub     r8, rcx; Size
0x140002dd9  xor     edx, edx; Val
0x140002ddb  call    memset
0x140002de0  jmp     short loc_140002E16
0x140002de2  mov     r9d, [rbp+0D8h]
0x140002de9  cmp     r9d, 40h ; '@'
0x140002ded  jbe     short loc_140002DFC
0x140002def  mov     dword ptr [rbp+0D8h], 0
0x140002df9  xor     r9d, r9d
0x140002dfc  mov     edx, r9d
0x140002dff  mov     rcx, r13
0x140002e02  call    XdrEncodeIntUnsafe
0x140002e07  mov     edx, r9d
0x140002e0a  lea     r8, [rbp+0DCh]
0x140002e11  call    XdrEncodeOpaqueUnsafe
0x140002e16  mov     rcx, [rbp+28h]; Mutex
0x140002e1a  xor     edx, edx; Wait
0x140002e1c  call    cs:__imp_KeReleaseMutex
0x140002e23  nop     dword ptr [rax+rax+00h]
0x140002e28  cmp     dword ptr [r13+108h], 0
0x140002e30  jl      loc_1400032CC
0x140002e36  mov     r9, [rsi+28h]
0x140002e3a  lea     rcx, [rdi+48h]
0x140002e3e  mov     [rsp+0F8h+var_B8], 0
0x140002e46  mov     r8, r14
0x140002e49  cmp     byte ptr [r9+10h], 2
0x140002e4e  setz    al
0x140002e51  mov     [rsp+0F8h+var_C0], al
0x140002e55  lea     rax, [rsp+0F8h+var_A0]
0x140002e5a  mov     [rsp+0F8h+var_C8], rax
0x140002e5f  mov     [rsp+0F8h+var_D0], r13
0x140002e64  mov     [rsp+0F8h+Timeout], rcx
0x140002e69  mov     rcx, r15
0x140002e6c  call    NfsSendWaitReplyWaitInternal
0x140002e71  mov     edi, eax
0x140002e73  test    eax, eax
0x140002e75  js      loc_140002F48
0x140002e7b  mov     r8, [rsp+0F8h+var_A0]
  ... truncated ...
```
