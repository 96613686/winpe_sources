# NfsSetAttributes

- ea: `0x14002a9e0`
- end: `0x14002b130`
- name: `NfsSetAttributes`
- size: `1872`
- prototype: ``
- caller_count: `6`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x140017d40`
- `0x14001add0`
- `0x14001b3e0`
- `0x14001d6b0`
- `0x1400316d0`
- `0x1400374f8`

## callees

- `0x140001f10`
- `0x140003440`
- `0x140008140`
- `0x14000d99c`
- `0x14000d9f0`
- `0x14000fa80`
- `0x14000fb40`
- `0x140011960`
- `0x140011f84`
- `0x140012024`
- `0x140013ac0`
- `0x1400145f0`
- `0x140014970`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x1400173f8`
- `0x14001837c`
- `0x1400186ac`
- `0x1400200d0`
- `0x1400204c0`
- `0x140022220`
- `0x14002a9e0`
- `0x14002ddac`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14002ab5c`
- `ntoskrnl!KeReleaseMutex` at `0x14002adb1`
- `ntoskrnl!KeReleaseMutex` at `0x14002afc3`
- `ntoskrnl!KeReleaseMutex` at `0x14002aff0`
- `ntoskrnl!KeReleaseMutex` at `0x14002ab5c`
- `ntoskrnl!KeReleaseMutex` at `0x14002adb1`
- `ntoskrnl!KeReleaseMutex` at `0x14002afc3`
- `ntoskrnl!KeReleaseMutex` at `0x14002aff0`
- `rpcxdr!OncRpcDestroy` at `0x14002ae71`
- `rpcxdr!OncRpcDestroy` at `0x14002b045`
- `rpcxdr!OncRpcDestroy` at `0x14002b056`
- `rpcxdr!OncRpcDestroy` at `0x14002b0cb`
- `rpcxdr!OncRpcDestroy` at `0x14002ae71`
- `rpcxdr!OncRpcDestroy` at `0x14002b045`
- `rpcxdr!OncRpcDestroy` at `0x14002b056`
- `rpcxdr!OncRpcDestroy` at `0x14002b0cb`

## pseudocode

```c
__int64 __fastcall NfsSetAttributes(__int64 a1, __int64 a2, __int64 *a3, __int64 a4)
{
  int v6; // r14d
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // r15
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r13
  int v15; // ebx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // edx
  struct _DEVICE_OBJECT *v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // r14d
  int v22; // r12d
  unsigned __int8 v23; // al
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rbx
  __int64 v28; // rax
  bool v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  int v31; // [rsp+60h] [rbp-A0h]
  int *v32; // [rsp+68h] [rbp-98h] BYREF
  int v33[2]; // [rsp+70h] [rbp-90h] BYREF
  int v34[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h]
  __int16 v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+94h] [rbp-6Ch]
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  int v41; // [rsp+B0h] [rbp-50h]
  __int64 v42; // [rsp+B8h] [rbp-48h]
  __int64 v43; // [rsp+C0h] [rbp-40h]
  __int64 v44; // [rsp+D0h] [rbp-30h]
  int v45; // [rsp+D8h] [rbp-28h]
  char *v46; // [rsp+180h] [rbp+80h]
  char v47; // [rsp+188h] [rbp+88h] BYREF

  v32 = *(int **)(a2 + 80);
  v6 = a2;
  v30 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      49,
      WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
      *(unsigned int *)(a4 + 4),
      *(_DWORD *)(a4 + 4));
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL);
  v31 = *(_DWORD *)(v8 + 88);
  v29 = v31 == 3;
  if ( !v8 )
    return 3221225662LL;
  *(_QWORD *)v33 = *(_QWORD *)(a1 + 40);
  if ( !*(_QWORD *)v33 )
    return 3221225662LL;
  v9 = a3[1];
  v10 = *a3;
  if ( (unsigned __int8)HacIsEntryFake(v9) )
    return 3221225506LL;
  v14 = NfsRdrBuildCall(v8 + 116, *(_DWORD *)(v8 + 80), *(_DWORD *)(v8 + 84), *(_DWORD *)(v8 + 88), 2, 140, a1);
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = -1073741670;
    goto LABEL_81;
  }
  HacAcquireLock(v9, v12, v13);
  LOBYTE(v16) = v31 == 3;
  XdrEncodeNfsFileHandleUnsafe(v14, v9 + 216, v16);
  LOBYTE(v17) = v31 == 3;
  XdrEncodeNfsSetAttributes(v14, *(unsigned int *)(v9 + 128), a4, v17);
  KeReleaseMutex(*(PRKMUTEX *)(v9 + 40), 0);
  if ( v31 == 3 )
    XdrEncodeIntUnsafe(v14, 0);
  if ( *(int *)(v14 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = *(_DWORD *)(v14 + 264);
    goto LABEL_80;
  }
  v15 = NfsSendWaitReply((_DWORD)v32, v18, a1, v6, *(_QWORD *)(a1 + 40), v8 + 72, v14, (__int64)&v30, 1);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_80;
  }
  v15 = OncRpcMapRpcStatusToNtStatus(v30);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_55;
  }
  v21 = XdrDecodeInt(v30);
  v15 = *(_DWORD *)(v30 + 264);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_55;
  }
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = MapNFSStatusToNtStatus(v21);
    if ( v15 == -1073741816 )
    {
      if ( WPP_GLOBAL_Control != v19 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, v9 + 64);
      HacOrphanStaleEntry(v32, v9);
    }
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL) + 88LL) == 2 )
      goto LABEL_55;
  }
  v22 = 1;
  if ( v31 != 3 )
    goto LABEL_42;
  if ( (unsigned __int8)XdrDecodeBool(v30) )
    XdrDecodeSkipBytes(v30, 24);
  v23 = XdrDecodeBool(v30);
  v22 = v23;
  if ( v23 )
  {
LABEL_42:
    HacAcquireLock(v9, v19, v20);
    LOBYTE(v24) = v29;
    XdrDecodeNfsFileAttributes(v30, v9 + 128, v24);
    KeReleaseMutex(*(PRKMUTEX *)(v9 + 40), 0);
    if ( *(int *)(v30 + 264) >= 0 )
      HacUpdateTimeStamp(v9);
  }
  v15 = *(_DWORD *)(v30 + 264);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    if ( !v21 )
    {
      HacInvalidateAttributes(v9);
LABEL_55:
      OncRpcDestroy(v30);
LABEL_80:
      OncRpcDestroy(v14);
LABEL_81:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      return (unsigned int)v15;
    }
LABEL_51:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v15 = MapNFSStatusToNtStatus(v21);
    goto LABEL_55;
  }
  if ( v21 )
    goto LABEL_51;
  HacAcquireLock(v10, v19, v20);
  v27 = *(_QWORD *)(v10 + 32);
  if ( v27 && *(_WORD *)(v27 + 4) == 3 )
  {
    if ( *(_DWORD *)(v10 + 136) == *(_DWORD *)(v27 + 32)
      && *(_DWORD *)(v10 + 200) == *(_DWORD *)(v27 + 36)
      && *(_DWORD *)(v10 + 204) == *(_DWORD *)(v27 + 40) )
    {
      v45 = 0;
      v32 = v34;
      v34[0] = 2;
      v46 = &v47;
      v36 = -1;
      v37 = -1;
      v38 = 0;
      v39 = 0;
      v34[1] = *(_DWORD *)(*(_QWORD *)v33 + 24LL);
      v35 = 0;
      v44 = 0;
      v43 = 0;
      v41 = 7;
      v42 = 0;
      HacAcquireLock(v9, v25, v26);
      *(_QWORD *)v33 = *(_QWORD *)(v9 + 184);
      if ( !(unsigned int)NfsLookupDirCache(v27, (__int64)v34, 1, v33, 0, 0) )
      {
        v28 = v40;
        if ( v40 )
        {
          if ( *(_DWORD *)(v40 + 92) )
          {
            *(_OWORD *)(v40 + 96) = *(_OWORD *)(v9 + 128);
            *(_OWORD *)(v28 + 112) = *(_OWORD *)(v9 + 144);
            *(_OWORD *)(v28 + 128) = *(_OWORD *)(v9 + 160);
            *(_OWORD *)(v28 + 144) = *(_OWORD *)(v9 + 176);
            *(_OWORD *)(v28 + 160) = *(_OWORD *)(v9 + 192);
            *(_QWORD *)(v28 + 176) = *(_QWORD *)(v9 + 208);
          }
        }
      }
      KeReleaseMutex(*(PRKMUTEX *)(v9 + 40), 0);
      NfsReadDirectoryQuit(&v32, 0);
    }
    else
    {
      DeleteDirCache(v32, v10);
    }
  }
  KeReleaseMutex(*(PRKMUTEX *)(v10 + 40), 0);
  if ( !v22 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    HacInvalidateAttributes(v9);
  }
  OncRpcDestroy(v14);
  OncRpcDestroy(v30);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14002a9e0  push    rbp
0x14002a9e2  push    rbx
0x14002a9e3  push    rsi
0x14002a9e4  push    rdi
0x14002a9e5  push    r12
0x14002a9e7  push    r13
0x14002a9e9  push    r14
0x14002a9eb  push    r15
0x14002a9ed  lea     rbp, [rsp-1A8h]
0x14002a9f5  sub     rsp, 2A8h
0x14002a9fc  mov     rax, cs:__security_cookie
0x14002aa03  xor     rax, rsp
0x14002aa06  mov     [rbp+1E0h+var_50], rax
0x14002aa0d  mov     rax, [rdx+50h]
0x14002aa11  mov     rdi, r9
0x14002aa14  mov     [rsp+2E0h+var_278], rax
0x14002aa19  mov     r15, r8
0x14002aa1c  mov     r14, rdx
0x14002aa1f  mov     [rsp+2E0h+var_288], 0
0x14002aa28  mov     r12, rcx
0x14002aa2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa32  lea     rax, WPP_GLOBAL_Control
0x14002aa39  cmp     rcx, rax
0x14002aa3c  jz      short loc_14002AA63
0x14002aa3e  mov     eax, [rcx+2Ch]
0x14002aa41  test    al, 40h
0x14002aa43  jz      short loc_14002AA63
0x14002aa45  mov     r9d, [r9+4]
0x14002aa49  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002aa50  mov     rcx, [rcx+18h]
0x14002aa54  mov     edx, 31h ; '1'
0x14002aa59  mov     dword ptr [rsp+2E0h+String1], r9d
0x14002aa5e  call    WPP_SF_dd
0x14002aa63  mov     rax, [r12+20h]
0x14002aa68  mov     rcx, [rax+20h]
0x14002aa6c  mov     rbx, [rcx+20h]
0x14002aa70  mov     eax, [rbx+58h]
0x14002aa73  cmp     eax, 3
0x14002aa76  mov     [rsp+2E0h+var_280], eax
0x14002aa7a  setz    [rsp+2E0h+var_290]
0x14002aa7f  test    rbx, rbx
0x14002aa82  jz      loc_14002B107
0x14002aa88  mov     rax, [r12+28h]
0x14002aa8d  mov     qword ptr [rsp+2E0h+var_270], rax
0x14002aa92  test    rax, rax
0x14002aa95  jz      loc_14002B107
0x14002aa9b  mov     rsi, [r15+8]
0x14002aa9f  mov     r15, [r15]
0x14002aaa2  mov     rcx, rsi
0x14002aaa5  call    HacIsEntryFake
0x14002aaaa  test    al, al
0x14002aaac  jz      short loc_14002AAB8
0x14002aaae  mov     eax, 0C0000022h
0x14002aab3  jmp     loc_14002B10C
0x14002aab8  mov     r9d, [rbx+58h]
0x14002aabc  lea     rcx, [rbx+74h]
0x14002aac0  mov     r8d, [rbx+54h]
0x14002aac4  mov     edx, [rbx+50h]
0x14002aac7  mov     [rsp+2E0h+var_2B0], r12
0x14002aacc  mov     dword ptr [rsp+2E0h+CaseInSensitive], 8Ch
0x14002aad4  mov     dword ptr [rsp+2E0h+String1], 2
0x14002aadc  call    NfsRdrBuildCall
0x14002aae1  mov     r13, rax
0x14002aae4  test    rax, rax
0x14002aae7  jnz     short loc_14002AB24
0x14002aae9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aaf0  lea     r15, WPP_GLOBAL_Control
0x14002aaf7  lea     edi, [rax+1]
0x14002aafa  cmp     rcx, r15
0x14002aafd  jz      short loc_14002AB1A
0x14002aaff  mov     eax, [rcx+2Ch]
0x14002ab02  test    dil, al
0x14002ab05  jz      short loc_14002AB1A
0x14002ab07  mov     rcx, [rcx+18h]
0x14002ab0b  lea     edx, [rdi+31h]
0x14002ab0e  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002ab15  call    WPP_SF_
0x14002ab1a  mov     ebx, 0C000009Ah
0x14002ab1f  jmp     loc_14002B0D7
0x14002ab24  mov     rcx, rsi
0x14002ab27  call    HacAcquireLock
0x14002ab2c  mov     r8b, [rsp+2E0h+var_290]
0x14002ab31  lea     rdx, [rsi+0D8h]
0x14002ab38  mov     rcx, r13
0x14002ab3b  call    XdrEncodeNfsFileHandleUnsafe
0x14002ab40  mov     r9b, [rsp+2E0h+var_290]
0x14002ab45  mov     r8, rdi
0x14002ab48  mov     edx, [rsi+80h]
0x14002ab4e  mov     rcx, r13
0x14002ab51  call    XdrEncodeNfsSetAttributes
0x14002ab56  mov     rcx, [rsi+28h]; Mutex
0x14002ab5a  xor     edx, edx; Wait
0x14002ab5c  call    cs:__imp_KeReleaseMutex
0x14002ab63  nop     dword ptr [rax+rax+00h]
0x14002ab68  cmp     [rsp+2E0h+var_280], 3
0x14002ab6d  jnz     short loc_14002AB79
0x14002ab6f  xor     edx, edx
0x14002ab71  mov     rcx, r13
0x14002ab74  call    XdrEncodeIntUnsafe
0x14002ab79  cmp     dword ptr [r13+108h], 0
0x14002ab81  jl      loc_14002B08E
0x14002ab87  lea     rcx, [rsp+2E0h+var_288]
0x14002ab8c  mov     edi, 1
0x14002ab91  mov     [rsp+2E0h+var_2A0], edi
0x14002ab95  lea     rax, [rbx+48h]
0x14002ab99  mov     [rsp+2E0h+var_2A8], rcx
0x14002ab9e  mov     r9, r14
0x14002aba1  mov     rcx, [rsp+2E0h+var_278]
0x14002aba6  mov     r8, r12
0x14002aba9  mov     [rsp+2E0h+var_2B0], r13
0x14002abae  mov     qword ptr [rsp+2E0h+CaseInSensitive], rax
0x14002abb3  mov     rax, [r12+28h]
0x14002abb8  mov     [rsp+2E0h+String1], rax
0x14002abbd  call    NfsSendWaitReply
0x14002abc2  mov     ebx, eax
0x14002abc4  test    eax, eax
0x14002abc6  jns     short loc_14002AC06
0x14002abc8  mov     rax, cs:WPP_GLOBAL_Control
0x14002abcf  lea     r15, WPP_GLOBAL_Control
0x14002abd6  cmp     rax, r15
0x14002abd9  jz      loc_14002B0C8
0x14002abdf  mov     ecx, [rax+2Ch]
0x14002abe2  test    dil, cl
0x14002abe5  jz      loc_14002B0C8
0x14002abeb  mov     rcx, [rax+18h]
0x14002abef  lea     edx, [rdi+33h]
0x14002abf2  mov     r9d, ebx
0x14002abf5  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002abfc  call    WPP_SF_d
0x14002ac01  jmp     loc_14002B0C8
0x14002ac06  mov     rcx, [rsp+2E0h+var_288]
0x14002ac0b  call    OncRpcMapRpcStatusToNtStatus
0x14002ac10  mov     ebx, eax
0x14002ac12  test    eax, eax
0x14002ac14  jns     short loc_14002AC56
0x14002ac16  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ac1d  lea     r15, WPP_GLOBAL_Control
0x14002ac24  cmp     rcx, r15
0x14002ac27  jz      loc_14002AE6C
0x14002ac2d  mov     eax, [rcx+2Ch]
0x14002ac30  test    dil, al
0x14002ac33  jz      loc_14002AE6C
0x14002ac39  mov     rcx, [rcx+18h]
0x14002ac3d  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002ac44  mov     edx, 35h ; '5'
0x14002ac49  mov     r9d, ebx
0x14002ac4c  call    WPP_SF_d
0x14002ac51  jmp     loc_14002AE6C
0x14002ac56  mov     rcx, [rsp+2E0h+var_288]
0x14002ac5b  call    XdrDecodeInt
0x14002ac60  mov     rcx, [rsp+2E0h+var_288]
0x14002ac65  mov     r14d, eax
0x14002ac68  mov     ebx, [rcx+108h]
0x14002ac6e  test    ebx, ebx
0x14002ac70  jns     short loc_14002ACAF
0x14002ac72  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ac79  lea     r15, WPP_GLOBAL_Control
0x14002ac80  cmp     rcx, r15
0x14002ac83  jz      loc_14002AE6C
0x14002ac89  mov     eax, [rcx+2Ch]
0x14002ac8c  test    dil, al
0x14002ac8f  jz      loc_14002AE6C
0x14002ac95  mov     rcx, [rcx+18h]
0x14002ac99  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002aca0  mov     edx, 36h ; '6'
0x14002aca5  call    WPP_SF_
0x14002acaa  jmp     loc_14002AE6C
0x14002acaf  test    r14d, r14d
0x14002acb2  jz      loc_14002AD54
0x14002acb8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002acbf  lea     rdx, WPP_GLOBAL_Control
0x14002acc6  cmp     rcx, rdx
0x14002acc9  jz      short loc_14002ACF2
0x14002accb  mov     eax, [rcx+2Ch]
0x14002acce  test    dil, al
0x14002acd1  jz      short loc_14002ACF2
0x14002acd3  mov     rcx, [rcx+18h]
0x14002acd7  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002acde  mov     edx, 37h ; '7'
0x14002ace3  mov     r9d, r14d
0x14002ace6  call    WPP_SF_d
0x14002aceb  lea     rdx, WPP_GLOBAL_Control
0x14002acf2  mov     ecx, r14d
0x14002acf5  call    MapNFSStatusToNtStatus
0x14002acfa  mov     ebx, eax
0x14002acfc  cmp     eax, 0C0000008h
0x14002ad01  jnz     short loc_14002AD3D
0x14002ad03  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ad0a  cmp     rcx, rdx
0x14002ad0d  jz      short loc_14002AD30
0x14002ad0f  mov     eax, [rcx+2Ch]
0x14002ad12  test    dil, al
0x14002ad15  jz      short loc_14002AD30
0x14002ad17  mov     rcx, [rcx+18h]
0x14002ad1b  lea     r9, [rsi+40h]
0x14002ad1f  mov     edx, 38h ; '8'
0x14002ad24  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002ad2b  call    WPP_SF_Z
0x14002ad30  mov     rcx, [rsp+2E0h+var_278]
0x14002ad35  mov     rdx, rsi
0x14002ad38  call    HacOrphanStaleEntry
0x14002ad3d  mov     rax, [r12+20h]
0x14002ad42  mov     rcx, [rax+20h]
0x14002ad46  mov     rax, [rcx+20h]
0x14002ad4a  cmp     dword ptr [rax+58h], 2
0x14002ad4e  jz      loc_14002AE65
0x14002ad54  cmp     [rsp+2E0h+var_280], 3
0x14002ad59  mov     r12d, edi
0x14002ad5c  jnz     short loc_14002AD8D
0x14002ad5e  mov     rcx, [rsp+2E0h+var_288]
0x14002ad63  call    XdrDecodeBool
0x14002ad68  test    al, al
0x14002ad6a  jz      short loc_14002AD7B
0x14002ad6c  mov     rcx, [rsp+2E0h+var_288]
0x14002ad71  mov     edx, 18h
0x14002ad76  call    XdrDecodeSkipBytes
0x14002ad7b  mov     rcx, [rsp+2E0h+var_288]
0x14002ad80  call    XdrDecodeBool
0x14002ad85  movzx   r12d, al
0x14002ad89  test    al, al
0x14002ad8b  jz      short loc_14002ADD3
0x14002ad8d  mov     rcx, rsi
0x14002ad90  call    HacAcquireLock
0x14002ad95  mov     r8b, [rsp+2E0h+var_290]
0x14002ad9a  lea     rdx, [rsi+80h]
0x14002ada1  mov     rcx, [rsp+2E0h+var_288]
0x14002ada6  call    XdrDecodeNfsFileAttributes
0x14002adab  mov     rcx, [rsi+28h]; Mutex
0x14002adaf  xor     edx, edx; Wait
0x14002adb1  call    cs:__imp_KeReleaseMutex
0x14002adb8  nop     dword ptr [rax+rax+00h]
0x14002adbd  mov     rax, [rsp+2E0h+var_288]
0x14002adc2  cmp     dword ptr [rax+108h], 0
0x14002adc9  jl      short loc_14002ADD3
0x14002adcb  mov     rcx, rsi
0x14002adce  call    HacUpdateTimeStamp
0x14002add3  mov     rax, [rsp+2E0h+var_288]
0x14002add8  mov     ebx, [rax+108h]
0x14002adde  test    ebx, ebx
0x14002ade0  jns     short loc_14002AE21
0x14002ade2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ade9  lea     r15, WPP_GLOBAL_Control
0x14002adf0  cmp     rcx, r15
0x14002adf3  jz      short loc_14002AE12
0x14002adf5  mov     eax, [rcx+2Ch]
0x14002adf8  test    dil, al
0x14002adfb  jz      short loc_14002AE12
0x14002adfd  mov     rcx, [rcx+18h]
0x14002ae01  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002ae08  mov     edx, 39h ; '9'
0x14002ae0d  call    WPP_SF_
0x14002ae12  test    r14d, r14d
0x14002ae15  jnz     short loc_14002AE2D
0x14002ae17  mov     rcx, rsi
0x14002ae1a  call    HacInvalidateAttributes
0x14002ae1f  jmp     short loc_14002AE6C
0x14002ae21  test    r14d, r14d
0x14002ae24  jz      short loc_14002AE82
0x14002ae26  lea     r15, WPP_GLOBAL_Control
0x14002ae2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ae34  cmp     rcx, r15
0x14002ae37  jz      short loc_14002AE59
0x14002ae39  mov     eax, [rcx+2Ch]
0x14002ae3c  test    dil, al
0x14002ae3f  jz      short loc_14002AE59
0x14002ae41  mov     rcx, [rcx+18h]
0x14002ae45  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14002ae4c  mov     edx, 3Ah ; ':'
0x14002ae51  mov     r9d, r14d
0x14002ae54  call    WPP_SF_d
0x14002ae59  mov     ecx, r14d
0x14002ae5c  call    MapNFSStatusToNtStatus
0x14002ae61  mov     ebx, eax
0x14002ae63  jmp     short loc_14002AE6C
0x14002ae65  lea     r15, WPP_GLOBAL_Control
0x14002ae6c  mov     rcx, [rsp+2E0h+var_288]
0x14002ae71  call    cs:__imp_OncRpcDestroy
0x14002ae78  nop     dword ptr [rax+rax+00h]
0x14002ae7d  jmp     loc_14002B0C8
0x14002ae82  mov     rcx, r15
0x14002ae85  call    HacAcquireLock
0x14002ae8a  mov     rbx, [r15+20h]
0x14002ae8e  xor     r14d, r14d
0x14002ae91  test    rbx, rbx
0x14002ae94  jz      loc_14002AFEA
0x14002ae9a  lea     eax, [r14+3]
0x14002ae9e  cmp     ax, [rbx+4]
0x14002aea2  jnz     loc_14002AFEA
0x14002aea8  mov     eax, [rbx+20h]
0x14002aeab  cmp     [r15+88h], eax
0x14002aeb2  jnz     loc_14002AFDD
0x14002aeb8  mov     eax, [rbx+24h]
0x14002aebb  cmp     [r15+0C8h], eax
0x14002aec2  jnz     loc_14002AFDD
0x14002aec8  mov     eax, [rbx+28h]
0x14002aecb  cmp     [r15+0CCh], eax
0x14002aed2  jnz     loc_14002AFDD
0x14002aed8  lea     rax, [rbp+1E0h+var_260]
0x14002aedc  mov     [rbp+1E0h+var_208], r14d
0x14002aee0  mov     [rsp+2E0h+var_278], rax
  ... truncated ...
```
