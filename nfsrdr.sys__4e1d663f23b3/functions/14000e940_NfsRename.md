# NfsRename

- ea: `0x14000e940`
- end: `0x14000f26e`
- name: `NfsRename`
- size: `2350`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `24`
- tags: `installer_update`

## callers

- `0x14001c694`
- `0x140030ef0`

## callees

- `0x140001f10`
- `0x140003440`
- `0x140008140`
- `0x14000d99c`
- `0x14000d9f0`
- `0x14000e940`
- `0x14000fa80`
- `0x14000fb40`
- `0x14000fb64`
- `0x140011f84`
- `0x140013ac0`
- `0x1400145f0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x14001837c`
- `0x1400200d0`
- `0x1400204c0`
- `0x140022220`
- `0x14002b730`
- `0x14002ba4c`
- `0x14002bf9c`
- `0x14002c764`
- `0x14002ddac`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000edee`
- `ntoskrnl!KeReleaseMutex` at `0x14000ee2b`
- `ntoskrnl!KeReleaseMutex` at `0x14000ef84`
- `ntoskrnl!KeReleaseMutex` at `0x14000eff6`
- `ntoskrnl!KeReleaseMutex` at `0x14000f042`
- `ntoskrnl!KeReleaseMutex` at `0x14000f067`
- `ntoskrnl!KeReleaseMutex` at `0x14000edee`
- `ntoskrnl!KeReleaseMutex` at `0x14000ee2b`
- `ntoskrnl!KeReleaseMutex` at `0x14000ef84`
- `ntoskrnl!KeReleaseMutex` at `0x14000eff6`
- `ntoskrnl!KeReleaseMutex` at `0x14000f042`
- `ntoskrnl!KeReleaseMutex` at `0x14000f067`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f17f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f20b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f17f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f20b`
- `ntoskrnl!ExAllocatePool2` at `0x14000ea4d`
- `ntoskrnl!ExAllocatePool2` at `0x14000ea4d`
- `rpcxdr!OncRpcDestroy` at `0x14000f149`
- `rpcxdr!OncRpcDestroy` at `0x14000f15d`
- `rpcxdr!OncRpcDestroy` at `0x14000f16d`
- `rpcxdr!OncRpcDestroy` at `0x14000f1f9`
- `rpcxdr!OncRpcDestroy` at `0x14000f149`
- `rpcxdr!OncRpcDestroy` at `0x14000f15d`
- `rpcxdr!OncRpcDestroy` at `0x14000f16d`
- `rpcxdr!OncRpcDestroy` at `0x14000f1f9`

## pseudocode

```c
__int64 __fastcall NfsRename(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 v8; // r14
  __int64 v9; // r12
  _DWORD *v10; // r13
  __int64 v11; // rdi
  CHAR *Pool2; // rax
  int v13; // ebx
  int v14; // edx
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  PCHAR Buffer; // r8
  unsigned __int16 v19; // cx
  int v20; // r14d
  __int64 v21; // r12
  CHAR v22; // r10
  CHAR v23; // dl
  __int64 v24; // r8
  __int64 v25; // r12
  int v26; // r8d
  int v27; // eax
  PCHAR v28; // rdx
  unsigned __int16 v29; // cx
  int v30; // ebx
  __int64 v31; // r12
  CHAR v32; // r9
  CHAR v33; // r8
  int v34; // edx
  __int64 v35; // rdi
  __int64 v36; // r8
  __int64 v37; // r8
  int v38; // edx
  unsigned int v39; // r14d
  bool v40; // bl
  __int64 v41; // r8
  char v42; // al
  __int64 v43; // rcx
  __int64 v44; // r8
  int v46; // [rsp+58h] [rbp-31h]
  __int64 v47; // [rsp+60h] [rbp-29h] BYREF
  __int64 v48; // [rsp+68h] [rbp-21h]
  PVOID P; // [rsp+70h] [rbp-19h]
  STRING SourceString; // [rsp+78h] [rbp-11h] BYREF
  STRING DestinationString; // [rsp+88h] [rbp-1h] BYREF
  int v53; // [rsp+E0h] [rbp+57h]

  v53 = a2;
  v48 = *(_QWORD *)(a2 + 80);
  SourceString = 0;
  DestinationString = 0;
  v8 = a1;
  v47 = 0;
  v9 = a6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
      WPP_SF_SS(WPP_GLOBAL_Control->AttachedDevice, a2, a3, *(_QWORD *)(a5 + 8), *(_QWORD *)(a6 + 8));
  }
  v10 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(v8 + 32) + 32LL) + 32LL);
  v46 = v10[22];
  if ( !v10 )
    return 3221225662LL;
  v11 = *(_QWORD *)(v8 + 40);
  if ( !v11 )
    return 3221225662LL;
  if ( (unsigned __int8)HacIsEntryFake(a3) || (unsigned __int8)HacIsEntryFake(a4) )
    return 3221225506LL;
  Pool2 = (CHAR *)ExAllocatePool2(258, 520, 827483726);
  P = Pool2;
  if ( !Pool2 )
  {
    v13 = -1073741670;
    goto LABEL_125;
  }
  SourceString.Buffer = Pool2;
  *(_DWORD *)&SourceString.Length = 17039360;
  DestinationString.Buffer = Pool2 + 260;
  *(_DWORD *)&DestinationString.Length = 17039360;
  v13 = NfsConvertUnicodeToAnsi(v48, &SourceString, a5);
  if ( v13 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v16 = 137;
      goto LABEL_43;
    }
    goto LABEL_124;
  }
  v17 = *(_DWORD *)(v11 + 32);
  if ( (v17 & 0x40) != 0 )
  {
    DsSjisToEuc(&SourceString, &SourceString);
    goto LABEL_39;
  }
  if ( (v17 & 0x4000) == 0 )
  {
    if ( (v17 & 0x2000) != 0 )
      DsCnsToEuc(SourceString.Buffer, SourceString.Length, SourceString.Buffer, &SourceString);
    goto LABEL_39;
  }
  if ( !SourceString.Length )
    goto LABEL_39;
  Buffer = SourceString.Buffer;
  if ( !SourceString.Buffer )
    goto LABEL_39;
  v19 = 0;
  v20 = SourceString.Length - 1;
  if ( v20 <= 0 )
    goto LABEL_38;
  v21 = 0x3FFFFFF03FFFFFFLL;
  do
  {
    v22 = Buffer[v19];
    if ( (unsigned __int8)(v22 + 127) <= 0x1Fu
      && ((LOBYTE(v14) = Buffer[v19 + 1], (unsigned __int8)(v14 - 65) <= 0x39u)
       && _bittest64(&v21, (unsigned int)(v14 - 65))
       || (unsigned __int8)(v14 + 127) <= 0x1Fu
       || (unsigned __int8)(v14 + 95) <= 0x5Du)
      || (unsigned __int8)(v22 + 95) <= 0x5Du
      && ((v23 = Buffer[v19 + 1], (unsigned __int8)(v23 - 65) <= 0x19u)
       || (unsigned __int8)(v23 - 97) <= 0x19u
       || (unsigned __int8)(v23 + 127) <= 0x1Fu) )
    {
      *(_WORD *)&Buffer[v19] = 16191;
    }
    else if ( (unsigned __int8)(v22 + 127) > 0x7Du )
    {
      goto LABEL_36;
    }
    ++v19;
LABEL_36:
    ++v19;
  }
  while ( v19 < v20 );
  v9 = a6;
LABEL_38:
  v8 = a1;
LABEL_39:
  v24 = v9;
  v25 = v48;
  v13 = NfsConvertUnicodeToAnsi(v48, &DestinationString, v24);
  if ( v13 >= 0 )
  {
    v27 = *(_DWORD *)(v11 + 32);
    if ( (v27 & 0x40) != 0 )
    {
      DsSjisToEuc(&DestinationString, &DestinationString);
      goto LABEL_70;
    }
    if ( (v27 & 0x4000) != 0 )
    {
      if ( DestinationString.Length )
      {
        v28 = DestinationString.Buffer;
        if ( DestinationString.Buffer )
        {
          v29 = 0;
          v30 = DestinationString.Length - 1;
          if ( v30 > 0 )
          {
            v31 = 0x3FFFFFF03FFFFFFLL;
            while ( 1 )
            {
              v32 = v28[v29];
              if ( (unsigned __int8)(v32 + 127) <= 0x1Fu )
              {
                LOBYTE(v26) = v28[v29 + 1];
                if ( (unsigned __int8)(v26 - 65) <= 0x39u )
                {
                  if ( _bittest64(&v31, (unsigned int)(v26 - 65)) )
                    break;
                }
                if ( (unsigned __int8)(v26 + 127) <= 0x1Fu || (unsigned __int8)(v26 + 95) <= 0x5Du )
                  break;
              }
              if ( (unsigned __int8)(v32 + 95) <= 0x5Du )
              {
                v33 = v28[v29 + 1];
                if ( (unsigned __int8)(v33 - 65) <= 0x19u
                  || (unsigned __int8)(v33 - 97) <= 0x19u
                  || (unsigned __int8)(v33 + 127) <= 0x1Fu )
                {
                  v28[v29 + 1] = 63;
                  v28[v29] = 63;
                  goto LABEL_65;
                }
              }
              if ( (unsigned __int8)(v32 + 127) <= 0x7Du )
                goto LABEL_65;
LABEL_66:
              if ( ++v29 >= v30 )
              {
                v25 = v48;
                goto LABEL_70;
              }
            }
            *(_WORD *)&v28[v29] = 16191;
LABEL_65:
            ++v29;
            goto LABEL_66;
          }
        }
      }
    }
    else if ( (v27 & 0x2000) != 0 )
    {
      DsCnsToEuc(DestinationString.Buffer, DestinationString.Length, DestinationString.Buffer, &DestinationString);
    }
LABEL_70:
    v34 = 14;
    if ( v46 != 3 )
      v34 = 11;
    v35 = NfsRdrBuildCall(
            (int)v10 + 116,
            v10[20],
            v10[21],
            v10[22],
            v34,
            DestinationString.Length
          + (-DestinationString.Length & 3)
          + (-SourceString.Length & 3)
          + (unsigned int)SourceString.Length
          + 136,
            v8);
    if ( !v35 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      v13 = -1073741670;
      goto LABEL_124;
    }
    HacAcquireLock(a3);
    LOBYTE(v36) = v46 == 3;
    XdrEncodeNfsFileHandleUnsafe(v35, a3 + 216, v36);
    KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
    XdrEncodeOpaqueAndLength(v35, SourceString.Length, SourceString.Buffer);
    HacAcquireLock(a4);
    LOBYTE(v37) = v46 == 3;
    XdrEncodeNfsFileHandleUnsafe(v35, a4 + 216, v37);
    KeReleaseMutex(*(PRKMUTEX *)(a4 + 40), 0);
    XdrEncodeOpaqueAndLength(v35, DestinationString.Length, DestinationString.Buffer);
    if ( *(int *)(v35 + 264) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      v13 = *(_DWORD *)(v35 + 264);
      goto LABEL_123;
    }
    v13 = NfsSendWaitReply(v25, v38, v8, v53, *(_QWORD *)(v8 + 40), (__int64)(v10 + 18), v35, (__int64)&v47, 2);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      goto LABEL_123;
    }
    v13 = OncRpcMapRpcStatusToNtStatus(v47);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
LABEL_114:
      OncRpcDestroy(v47);
LABEL_123:
      OncRpcDestroy(v35);
      goto LABEL_124;
    }
    v39 = XdrDecodeInt(v47);
    if ( v46 == 3 )
    {
      if ( (unsigned __int8)XdrDecodeBool(v47) )
        XdrDecodeSkipBytes(v47, 24);
      if ( (unsigned __int8)XdrDecodeBool(v47) )
      {
        HacAcquireLock(a3);
        v40 = v46 == 3;
        LOBYTE(v41) = v46 == 3;
        XdrDecodeNfsFileAttributes(v47, a3 + 128, v41);
        KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
        if ( *(int *)(v47 + 264) >= 0 )
          HacUpdateTimeStamp(a3);
      }
      else
      {
        HacInvalidateAttributes(a3);
        v40 = v46 == 3;
      }
      if ( (unsigned __int8)XdrDecodeBool(v47) )
        XdrDecodeSkipBytes(v47, 24);
      v42 = XdrDecodeBool(v47);
      v43 = a4;
      if ( v42 )
      {
        HacAcquireLock(a4);
        LOBYTE(v44) = v40;
        XdrDecodeNfsFileAttributes(v47, a4 + 128, v44);
        KeReleaseMutex(*(PRKMUTEX *)(a4 + 40), 0);
        if ( *(int *)(v47 + 264) >= 0 )
          HacUpdateTimeStamp(a4);
LABEL_100:
        HacAcquireLock(a3);
        DeleteDirCache(v25, a3);
        KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
        HacAcquireLock(a4);
        DeleteDirCache(v25, a4);
        KeReleaseMutex(*(PRKMUTEX *)(a4 + 40), 0);
        v13 = *(_DWORD *)(v47 + 264);
        if ( v13 >= 0 )
        {
          if ( !v39 )
          {
            OncRpcDestroy(v35);
            OncRpcDestroy(v47);
            ExFreePoolWithTag(P, 0);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 146, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
            }
            return 0;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 144, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
          }
          v13 = MapNFSStatusToNtStatus(v39);
          if ( v13 == -1073741816 && a3 == a4 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_Z(
                WPP_GLOBAL_Control->AttachedDevice,
                145,
                WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
                a3 + 64);
            }
            HacOrphanStaleEntry(v25, a3);
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        }
        goto LABEL_114;
      }
    }
    else
    {
      HacInvalidateAttributes(a3);
      v43 = a4;
    }
    HacInvalidateAttributes(v43);
    goto LABEL_100;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v16 = 138;
LABEL_43:
    WPP_SF_d(v15->AttachedDevice, v16, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  }
LABEL_124:
  ExFreePoolWithTag(P, 0);
LABEL_125:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000e940  mov     rax, rsp
0x14000e943  mov     [rax+18h], rbx
0x14000e947  mov     [rax+10h], rdx
0x14000e94b  mov     [rax+8], rcx
0x14000e94f  push    rbp
0x14000e950  push    rsi
0x14000e951  push    rdi
0x14000e952  push    r12
0x14000e954  push    r13
0x14000e956  push    r14
0x14000e958  push    r15
0x14000e95a  lea     rbp, [rax-47h]
0x14000e95e  sub     rsp, 90h
0x14000e965  mov     rax, [rdx+50h]
0x14000e969  xorps   xmm0, xmm0
0x14000e96c  xorps   xmm1, xmm1
0x14000e96f  mov     [rbp+3Fh+var_60], rax
0x14000e973  movups  xmmword ptr [rbp+3Fh+SourceString.Length], xmm0
0x14000e977  mov     r15, r9
0x14000e97a  mov     rsi, r8
0x14000e97d  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm1
0x14000e981  mov     r14, rcx
0x14000e984  mov     [rbp+3Fh+var_68], 0
0x14000e98c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e993  lea     rdi, WPP_GLOBAL_Control
0x14000e99a  mov     r12, [rbp+3Fh+arg_28]
0x14000e99e  mov     rbx, [rbp+3Fh+arg_20]
0x14000e9a2  cmp     rcx, rdi
0x14000e9a5  jz      short loc_14000E9ED
0x14000e9a7  mov     eax, [rcx+2Ch]
0x14000e9aa  test    al, 40h
0x14000e9ac  jz      short loc_14000E9C3
0x14000e9ae  mov     rcx, [rcx+18h]
0x14000e9b2  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e9b9  mov     edx, 87h
0x14000e9be  call    WPP_SF_
0x14000e9c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9ca  cmp     rcx, rdi
0x14000e9cd  jz      short loc_14000E9ED
0x14000e9cf  mov     eax, [rcx+2Ch]
0x14000e9d2  test    al, al
0x14000e9d4  jns     short loc_14000E9ED
0x14000e9d6  mov     rax, [r12+8]
0x14000e9db  mov     r9, [rbx+8]
0x14000e9df  mov     rcx, [rcx+18h]
0x14000e9e3  mov     [rsp+0C0h+var_A0], rax
0x14000e9e8  call    WPP_SF_SS
0x14000e9ed  mov     rax, [r14+20h]
0x14000e9f1  mov     rcx, [rax+20h]
0x14000e9f5  mov     r13, [rcx+20h]
0x14000e9f9  mov     eax, [r13+58h]
0x14000e9fd  cmp     eax, 3
0x14000ea00  mov     [rbp+3Fh+var_70], eax
0x14000ea03  setz    [rbp+3Fh+arg_30]
0x14000ea07  test    r13, r13
0x14000ea0a  jz      loc_14000F24D
0x14000ea10  mov     rdi, [r14+28h]
0x14000ea14  test    rdi, rdi
0x14000ea17  jz      loc_14000F24D
0x14000ea1d  mov     rcx, rsi
0x14000ea20  call    HacIsEntryFake
0x14000ea25  test    al, al
0x14000ea27  jnz     loc_14000F246
0x14000ea2d  mov     rcx, r15
0x14000ea30  call    HacIsEntryFake
0x14000ea35  test    al, al
0x14000ea37  jnz     loc_14000F246
0x14000ea3d  mov     edx, 208h
0x14000ea42  mov     ecx, 102h
0x14000ea47  mov     r8d, 3152664Eh
0x14000ea4d  call    cs:__imp_ExAllocatePool2
0x14000ea54  nop     dword ptr [rax+rax+00h]
0x14000ea59  mov     [rbp+3Fh+P], rax
0x14000ea5d  test    rax, rax
0x14000ea60  jnz     short loc_14000EA73
0x14000ea62  mov     ebx, 0C000009Ah
0x14000ea67  lea     r13, WPP_GLOBAL_Control
0x14000ea6e  jmp     loc_14000F217
0x14000ea73  mov     rcx, [rbp+3Fh+var_60]
0x14000ea77  lea     rdx, [rbp+3Fh+SourceString]
0x14000ea7b  mov     [rbp+3Fh+SourceString.Buffer], rax
0x14000ea7f  mov     r8, rbx
0x14000ea82  add     rax, 104h
0x14000ea88  mov     dword ptr [rbp+3Fh+SourceString.Length], 1040000h
0x14000ea8f  mov     [rbp+3Fh+DestinationString.Buffer], rax
0x14000ea93  mov     dword ptr [rbp+3Fh+DestinationString.Length], 1040000h
0x14000ea9a  mov     eax, [rdi+20h]
0x14000ea9d  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14000eaa1  call    NfsConvertUnicodeToAnsi
0x14000eaa6  mov     ebx, eax
0x14000eaa8  test    eax, eax
0x14000eaaa  jns     short loc_14000EADC
0x14000eaac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eab3  lea     r13, WPP_GLOBAL_Control
0x14000eaba  cmp     rcx, r13
0x14000eabd  jz      loc_14000F205
0x14000eac3  mov     edx, [rcx+2Ch]
0x14000eac6  test    dl, 1
0x14000eac9  jz      loc_14000F205
0x14000eacf  mov     edx, 89h
0x14000ead4  mov     r9d, eax
0x14000ead7  jmp     loc_14000EBFA
0x14000eadc  mov     eax, [rdi+20h]
0x14000eadf  test    al, 40h
0x14000eae1  jz      short loc_14000EAF5
0x14000eae3  lea     rdx, [rbp+3Fh+SourceString]; DestinationString
0x14000eae7  lea     rcx, [rbp+3Fh+SourceString]; SourceString
0x14000eaeb  call    DsSjisToEuc
0x14000eaf0  jmp     loc_14000EBB0
0x14000eaf5  bt      eax, 0Eh
0x14000eaf9  jnb     loc_14000EC0F
0x14000eaff  xor     eax, eax
0x14000eb01  cmp     ax, [rbp+3Fh+SourceString.Length]
0x14000eb05  jz      loc_14000EBB0
0x14000eb0b  mov     r8, [rbp+3Fh+SourceString.Buffer]
0x14000eb0f  test    r8, r8
0x14000eb12  jz      loc_14000EBB0
0x14000eb18  movzx   r14d, [rbp+3Fh+SourceString.Length]
0x14000eb1d  xor     ecx, ecx
0x14000eb1f  dec     r14d
0x14000eb22  test    r14d, r14d
0x14000eb25  jle     loc_14000EBAC
0x14000eb2b  mov     r12, 3FFFFFF03FFFFFFh
0x14000eb35  movzx   r11d, cx
0x14000eb39  mov     r10b, [r8+r11]
0x14000eb3d  lea     ebx, [r10+7Fh]
0x14000eb41  cmp     bl, 1Fh
0x14000eb44  ja      short loc_14000EB70
0x14000eb46  mov     dl, [r8+r11+1]
0x14000eb4b  lea     eax, [rdx-41h]
0x14000eb4e  cmp     al, 39h ; '9'
0x14000eb50  ja      short loc_14000EB58
0x14000eb52  bt      r12, rax
0x14000eb56  jb      short loc_14000EB67
0x14000eb58  lea     eax, [rdx+7Fh]
0x14000eb5b  cmp     al, 1Fh
0x14000eb5d  jbe     short loc_14000EB67
0x14000eb5f  add     dl, 5Fh ; '_'
0x14000eb62  cmp     dl, 5Dh ; ']'
0x14000eb65  ja      short loc_14000EB70
0x14000eb67  mov     word ptr [r8+r11], 3F3Fh
0x14000eb6e  jmp     short loc_14000EB9A
0x14000eb70  add     r10b, 5Fh ; '_'
0x14000eb74  cmp     r10b, 5Dh ; ']'
0x14000eb78  ja      short loc_14000EB95
0x14000eb7a  mov     dl, [r8+r11+1]
0x14000eb7f  lea     eax, [rdx-41h]
0x14000eb82  cmp     al, 19h
0x14000eb84  jbe     short loc_14000EB67
0x14000eb86  lea     eax, [rdx-61h]
0x14000eb89  cmp     al, 19h
0x14000eb8b  jbe     short loc_14000EB67
0x14000eb8d  add     dl, 7Fh
0x14000eb90  cmp     dl, 1Fh
0x14000eb93  jbe     short loc_14000EB67
0x14000eb95  cmp     bl, 7Dh ; '}'
0x14000eb98  ja      short loc_14000EB9D
0x14000eb9a  inc     cx
0x14000eb9d  inc     cx
0x14000eba0  movzx   eax, cx
0x14000eba3  cmp     eax, r14d
0x14000eba6  jl      short loc_14000EB35
0x14000eba8  mov     r12, [rbp+3Fh+arg_28]
0x14000ebac  mov     r14, [rbp+3Fh+arg_0]
0x14000ebb0  mov     eax, [rdi+20h]
0x14000ebb3  lea     rdx, [rbp+3Fh+DestinationString]
0x14000ebb7  mov     r8, r12
0x14000ebba  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14000ebbe  mov     r12, [rbp+3Fh+var_60]
0x14000ebc2  mov     rcx, r12
0x14000ebc5  call    NfsConvertUnicodeToAnsi
0x14000ebca  mov     ebx, eax
0x14000ebcc  test    eax, eax
0x14000ebce  jns     short loc_14000EC2B
0x14000ebd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ebd7  lea     r13, WPP_GLOBAL_Control
0x14000ebde  cmp     rcx, r13
0x14000ebe1  jz      loc_14000F205
0x14000ebe7  mov     eax, [rcx+2Ch]
0x14000ebea  test    al, 1
0x14000ebec  jz      loc_14000F205
0x14000ebf2  mov     edx, 8Ah
0x14000ebf7  mov     r9d, ebx
0x14000ebfa  mov     rcx, [rcx+18h]
0x14000ebfe  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000ec05  call    WPP_SF_d
0x14000ec0a  jmp     loc_14000F205
0x14000ec0f  bt      eax, 0Dh
0x14000ec13  jnb     short loc_14000EBB0
0x14000ec15  mov     r8, [rbp+3Fh+SourceString.Buffer]
0x14000ec19  lea     r9, [rbp+3Fh+SourceString]
0x14000ec1d  movzx   edx, [rbp+3Fh+SourceString.Length]
0x14000ec21  mov     rcx, r8
0x14000ec24  call    DsCnsToEuc
0x14000ec29  jmp     short loc_14000EBB0
0x14000ec2b  mov     eax, [rdi+20h]
0x14000ec2e  test    al, 40h
0x14000ec30  jz      short loc_14000EC44
0x14000ec32  lea     rdx, [rbp+3Fh+DestinationString]; DestinationString
0x14000ec36  lea     rcx, [rbp+3Fh+DestinationString]; SourceString
0x14000ec3a  call    DsSjisToEuc
0x14000ec3f  jmp     loc_14000ED36
0x14000ec44  bt      eax, 0Eh
0x14000ec48  jnb     loc_14000ED1C
0x14000ec4e  xor     eax, eax
0x14000ec50  cmp     ax, [rbp+3Fh+DestinationString.Length]
0x14000ec54  jz      loc_14000ED36
0x14000ec5a  mov     rdx, [rbp+3Fh+DestinationString.Buffer]
0x14000ec5e  test    rdx, rdx
0x14000ec61  jz      loc_14000ED36
0x14000ec67  movzx   ebx, [rbp+3Fh+DestinationString.Length]
0x14000ec6b  xor     ecx, ecx
0x14000ec6d  dec     ebx
0x14000ec6f  test    ebx, ebx
0x14000ec71  jle     loc_14000ED36
0x14000ec77  mov     di, 1
0x14000ec7b  mov     r12, 3FFFFFF03FFFFFFh
0x14000ec85  movzx   r10d, cx
0x14000ec89  mov     r9b, [rdx+r10]
0x14000ec8d  lea     eax, [r9+7Fh]
0x14000ec91  cmp     al, 1Fh
0x14000ec93  ja      short loc_14000ECC3
0x14000ec95  mov     r8b, [rdx+r10+1]
0x14000ec9a  lea     eax, [r8-41h]
0x14000ec9e  cmp     al, 39h ; '9'
0x14000eca0  ja      short loc_14000ECA8
0x14000eca2  bt      r12, rax
0x14000eca6  jb      short loc_14000ECBA
0x14000eca8  lea     eax, [r8+7Fh]
0x14000ecac  cmp     al, 1Fh
0x14000ecae  jbe     short loc_14000ECBA
0x14000ecb0  add     r8b, 5Fh ; '_'
0x14000ecb4  cmp     r8b, 5Dh ; ']'
0x14000ecb8  ja      short loc_14000ECC3
0x14000ecba  mov     word ptr [rdx+r10], 3F3Fh
0x14000ecc1  jmp     short loc_14000ED05
0x14000ecc3  lea     eax, [r9+5Fh]
0x14000ecc7  cmp     al, 5Dh ; ']'
0x14000ecc9  ja      short loc_14000ECFB
0x14000eccb  movzx   r11d, cx
0x14000eccf  mov     r8b, [r11+rdx+1]
0x14000ecd4  lea     eax, [r8-41h]
0x14000ecd8  cmp     al, 19h
0x14000ecda  jbe     short loc_14000ECEE
0x14000ecdc  lea     eax, [r8-61h]
0x14000ece0  cmp     al, 19h
0x14000ece2  jbe     short loc_14000ECEE
0x14000ece4  add     r8b, 7Fh
0x14000ece8  cmp     r8b, 1Fh
0x14000ecec  ja      short loc_14000ECFB
0x14000ecee  mov     byte ptr [r11+rdx+1], 3Fh ; '?'
0x14000ecf4  mov     byte ptr [r10+rdx], 3Fh ; '?'
0x14000ecf9  jmp     short loc_14000ED05
0x14000ecfb  add     r9b, 7Fh
0x14000ecff  cmp     r9b, 7Dh ; '}'
0x14000ed03  ja      short loc_14000ED08
0x14000ed05  add     cx, di
0x14000ed08  add     cx, di
0x14000ed0b  movzx   eax, cx
0x14000ed0e  cmp     eax, ebx
0x14000ed10  jl      loc_14000EC85
0x14000ed16  mov     r12, [rbp+3Fh+var_60]
0x14000ed1a  jmp     short loc_14000ED36
0x14000ed1c  bt      eax, 0Dh
0x14000ed20  jnb     short loc_14000ED36
0x14000ed22  mov     r8, [rbp+3Fh+DestinationString.Buffer]
0x14000ed26  lea     r9, [rbp+3Fh+DestinationString]
0x14000ed2a  movzx   edx, [rbp+3Fh+DestinationString.Length]
0x14000ed2e  mov     rcx, r8
0x14000ed31  call    DsCnsToEuc
0x14000ed36  movzx   edx, [rbp+3Fh+DestinationString.Length]
0x14000ed3a  movzx   r8d, [rbp+3Fh+SourceString.Length]
0x14000ed3f  mov     eax, edx
0x14000ed41  mov     r9d, [r13+58h]
0x14000ed45  neg     eax
0x14000ed47  and     eax, 3
0x14000ed4a  mov     [rsp+0C0h+var_90], r14
0x14000ed4f  add     eax, edx
0x14000ed51  mov     ecx, r8d
0x14000ed54  neg     ecx
0x14000ed56  mov     edx, 0Eh
0x14000ed5b  and     ecx, 3
0x14000ed5e  add     ecx, eax
0x14000ed60  lea     eax, [r8+88h]
0x14000ed67  mov     r8d, [r13+54h]
0x14000ed6b  add     eax, ecx
0x14000ed6d  cmp     [rbp+3Fh+var_70], 3
0x14000ed71  lea     ecx, [rdx-3]
0x14000ed74  mov     dword ptr [rsp+0C0h+var_98], eax
0x14000ed78  cmovnz  edx, ecx
0x14000ed7b  lea     rcx, [r13+74h]
0x14000ed7f  mov     dword ptr [rsp+0C0h+var_A0], edx
0x14000ed83  mov     edx, [r13+50h]
0x14000ed87  call    NfsRdrBuildCall
0x14000ed8c  mov     rdi, rax
0x14000ed8f  test    rax, rax
0x14000ed92  jnz     short loc_14000EDCD
0x14000ed94  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed9b  lea     r13, WPP_GLOBAL_Control
0x14000eda2  cmp     rcx, r13
  ... truncated ...
```
