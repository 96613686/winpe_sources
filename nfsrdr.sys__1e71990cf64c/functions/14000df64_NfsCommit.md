# NfsCommit

- ea: `0x14000df64`
- end: `0x14000e4c2`
- name: `NfsCommit`
- size: `1374`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x140010904`
- `0x14001dba0`
- `0x140030ef0`

## callees

- `0x140001f10`
- `0x140003440`
- `0x140008140`
- `0x14000d99c`
- `0x14000d9f0`
- `0x14000df64`
- `0x14000e4c8`
- `0x14000fa80`
- `0x14000fb40`
- `0x140011960`
- `0x140011f84`
- `0x140011fd4`
- `0x140013ac0`
- `0x1400159cc`
- `0x1400159fc`
- `0x1400173f8`
- `0x140020114`
- `0x140022220`
- `0x14002ddac`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000e059`
- `ntoskrnl!RtlCompareMemory` at `0x14000e411`
- `ntoskrnl!RtlCompareMemory` at `0x14000e059`
- `ntoskrnl!RtlCompareMemory` at `0x14000e411`
- `ntoskrnl!KeReleaseMutex` at `0x14000e0f9`
- `ntoskrnl!KeReleaseMutex` at `0x14000e34a`
- `ntoskrnl!KeReleaseMutex` at `0x14000e3e7`
- `ntoskrnl!KeReleaseMutex` at `0x14000e0f9`
- `ntoskrnl!KeReleaseMutex` at `0x14000e34a`
- `ntoskrnl!KeReleaseMutex` at `0x14000e3e7`
- `rpcxdr!OncRpcDestroy` at `0x14000e45d`
- `rpcxdr!OncRpcDestroy` at `0x14000e46c`
- `rpcxdr!OncRpcDestroy` at `0x14000e480`
- `rpcxdr!OncRpcDestroy` at `0x14000e48f`
- `rpcxdr!OncRpcDestroy` at `0x14000e45d`
- `rpcxdr!OncRpcDestroy` at `0x14000e46c`
- `rpcxdr!OncRpcDestroy` at `0x14000e480`
- `rpcxdr!OncRpcDestroy` at `0x14000e48f`

## pseudocode

```c
__int64 __fastcall NfsCommit(__int64 a1, __int64 a2, __int64 a3, const void *a4, __int64 a5, unsigned int a6)
{
  int v8; // r15d
  _DWORD *v10; // rbx
  bool v11; // r12
  __int64 v13; // rsi
  int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // r8
  unsigned int v19; // eax
  unsigned int v20; // r15d
  unsigned int v21; // r14d
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // [rsp+50h] [rbp-28h] BYREF
  __int64 v25; // [rsp+58h] [rbp-20h]
  _BYTE Source2[8]; // [rsp+60h] [rbp-18h] BYREF

  v25 = *(_QWORD *)(a2 + 80);
  v8 = a2;
  v24 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 244, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  v10 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL);
  v11 = v10[22] == 3;
  if ( !*(_QWORD *)(a1 + 40) || !v10 )
    return 3221225662LL;
  if ( (unsigned __int8)HacIsEntryFake(a3) )
    return 0;
  if ( !(unsigned __int8)HacIsEntryStale(a3) )
  {
    if ( RtlCompareMemory(a4, "NFSDNFSD", 8u) != 8 )
    {
      v13 = NfsRdrBuildCall((int)v10 + 116, v10[20], v10[21], v10[22], 21, 76, a1);
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 246, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        return (unsigned int)-1073741670;
      }
      HacAcquireLock(a3);
      LOBYTE(v15) = v11;
      XdrEncodeNfsFileHandleUnsafe(v13, a3 + 216, v15);
      KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
      XdrEncodeHyperUnsafe(v13, a5);
      XdrEncodeIntUnsafe(v16, a6);
      if ( *(int *)(v13 + 264) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 247, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        v14 = *(_DWORD *)(v13 + 264);
        goto LABEL_65;
      }
      v14 = NfsSendWaitReply(v25, v17, a1, v8, *(_QWORD *)(a1 + 40), (__int64)(v10 + 18), v13, (__int64)&v24, 2);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            248,
            WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
            (unsigned int)v14);
        goto LABEL_65;
      }
      v14 = OncRpcMapRpcStatusToNtStatus(v24);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_64;
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          249,
          WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
          (unsigned int)v14);
LABEL_63:
        v18 = v24;
LABEL_64:
        OncRpcDestroy(v18);
LABEL_65:
        OncRpcDestroy(v13);
        return (unsigned int)v14;
      }
      v19 = XdrDecodeInt(v18);
      v18 = v24;
      v20 = v19;
      if ( *(int *)(v24 + 264) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 250, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
          v18 = v24;
        }
        v14 = *(_DWORD *)(v18 + 264);
        goto LABEL_64;
      }
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 251, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, v19);
          v18 = v24;
        }
        if ( (unsigned __int8)XdrDecodeBool(v18) )
          XdrDecodeSkipBytes(v24, 24);
        if ( (unsigned __int8)XdrDecodeBool(v24) )
        {
          HacAcquireLock(a3);
          v21 = *(_DWORD *)(a3 + 128);
          LOBYTE(v22) = v11;
          XdrDecodeNfsFileAttributes(v24, a3 + 128, v22);
          if ( *(_DWORD *)(a3 + 128) != v21 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_dd(
                WPP_GLOBAL_Control->AttachedDevice,
                252,
                WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
                v21,
                *(_DWORD *)(a3 + 128));
            }
            *(_DWORD *)(a3 + 128) = v21;
          }
          KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
        }
        if ( *(int *)(v24 + 264) < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 253, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        }
        v14 = MapNFSStatusToNtStatus(v20);
        goto LABEL_64;
      }
      if ( (unsigned __int8)XdrDecodeBool(v24) )
        XdrDecodeSkipBytes(v24, 24);
      if ( (unsigned __int8)XdrDecodeBool(v24) )
      {
        HacAcquireLock(a3);
        LOBYTE(v23) = v11;
        XdrDecodeNfsFileAttributes(v24, a3 + 128, v23);
        KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
      }
      XdrDecodeOpaque(v24, 8, Source2);
      if ( RtlCompareMemory(a4, Source2, 8u) != 8 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 254, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        v14 = -1073741614;
        goto LABEL_63;
      }
      OncRpcDestroy(v24);
      OncRpcDestroy(v13);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 245, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return 3221225480LL;
}

```

## disassembly

```asm
0x14000df64  push    rbp
0x14000df66  push    rbx
0x14000df67  push    rsi
0x14000df68  push    rdi
0x14000df69  push    r12
0x14000df6b  push    r13
0x14000df6d  push    r14
0x14000df6f  push    r15
0x14000df71  mov     rbp, rsp
0x14000df74  sub     rsp, 78h
0x14000df78  mov     rax, cs:__security_cookie
0x14000df7f  xor     rax, rsp
0x14000df82  mov     [rbp+var_10], rax
0x14000df86  mov     rax, [rdx+50h]
0x14000df8a  mov     r13, r9
0x14000df8d  mov     [rbp+var_20], rax
0x14000df91  mov     rdi, r8
0x14000df94  mov     r15, rdx
0x14000df97  mov     [rbp+var_28], 0
0x14000df9f  mov     r14, rcx
0x14000dfa2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfa9  lea     rsi, WPP_GLOBAL_Control
0x14000dfb0  cmp     rcx, rsi
0x14000dfb3  jz      short loc_14000DFD3
0x14000dfb5  test    dword ptr [rcx+2Ch], 4000h
0x14000dfbc  jz      short loc_14000DFD3
0x14000dfbe  mov     rcx, [rcx+18h]
0x14000dfc2  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000dfc9  mov     edx, 0F4h
0x14000dfce  call    WPP_SF_
0x14000dfd3  mov     rax, [r14+20h]
0x14000dfd7  mov     rcx, [rax+20h]
0x14000dfdb  mov     rbx, [rcx+20h]
0x14000dfdf  cmp     dword ptr [rbx+58h], 3
0x14000dfe3  setz    r12b
0x14000dfe7  cmp     qword ptr [r14+28h], 0
0x14000dfec  jz      loc_14000E49F
0x14000dff2  test    rbx, rbx
0x14000dff5  jz      loc_14000E49F
0x14000dffb  mov     rcx, rdi
0x14000dffe  call    HacIsEntryFake
0x14000e003  test    al, al
0x14000e005  jnz     loc_14000E49B
0x14000e00b  mov     rcx, rdi
0x14000e00e  call    HacIsEntryStale
0x14000e013  test    al, al
0x14000e015  jz      short loc_14000E049
0x14000e017  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e01e  cmp     rcx, rsi
0x14000e021  jz      short loc_14000E03F
0x14000e023  mov     eax, [rcx+2Ch]
0x14000e026  test    al, 1
0x14000e028  jz      short loc_14000E03F
0x14000e02a  mov     rcx, [rcx+18h]
0x14000e02e  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e035  mov     edx, 0F5h
0x14000e03a  call    WPP_SF_
0x14000e03f  mov     eax, 0C0000008h
0x14000e044  jmp     loc_14000E4A4
0x14000e049  mov     r8d, 8; Length
0x14000e04f  lea     rdx, aNfsdnfsd; "NFSDNFSD"
0x14000e056  mov     rcx, r13; Source1
0x14000e059  call    cs:__imp_RtlCompareMemory
0x14000e060  nop     dword ptr [rax+rax+00h]
0x14000e065  cmp     rax, 8
0x14000e069  jz      loc_14000E49B
0x14000e06f  mov     r9d, [rbx+58h]
0x14000e073  lea     rcx, [rbx+74h]
0x14000e077  mov     r8d, [rbx+54h]
0x14000e07b  mov     edx, [rbx+50h]
0x14000e07e  mov     [rsp+78h+var_48], r14
0x14000e083  mov     dword ptr [rsp+78h+var_50], 4Ch ; 'L'
0x14000e08b  mov     dword ptr [rsp+78h+var_58], 15h
0x14000e093  call    NfsRdrBuildCall
0x14000e098  mov     rsi, rax
0x14000e09b  test    rax, rax
0x14000e09e  jnz     short loc_14000E0D9
0x14000e0a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e0a7  lea     r13, WPP_GLOBAL_Control
0x14000e0ae  cmp     rcx, r13
0x14000e0b1  jz      short loc_14000E0CF
0x14000e0b3  mov     eax, [rcx+2Ch]
0x14000e0b6  test    al, 1
0x14000e0b8  jz      short loc_14000E0CF
0x14000e0ba  mov     rcx, [rcx+18h]
0x14000e0be  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e0c5  mov     edx, 0F6h
0x14000e0ca  call    WPP_SF_
0x14000e0cf  mov     ebx, 0C000009Ah
0x14000e0d4  jmp     loc_14000E478
0x14000e0d9  mov     rcx, rdi
0x14000e0dc  call    HacAcquireLock
0x14000e0e1  lea     rdx, [rdi+0D8h]
0x14000e0e8  mov     r8b, r12b
0x14000e0eb  mov     rcx, rsi
0x14000e0ee  call    XdrEncodeNfsFileHandleUnsafe
0x14000e0f3  mov     rcx, [rdi+28h]; Mutex
0x14000e0f7  xor     edx, edx; Wait
0x14000e0f9  call    cs:__imp_KeReleaseMutex
0x14000e100  nop     dword ptr [rax+rax+00h]
0x14000e105  mov     rdx, [rbp+arg_20]
0x14000e109  mov     rcx, rsi
0x14000e10c  call    XdrEncodeHyperUnsafe
0x14000e111  mov     edx, [rbp+arg_28]
0x14000e114  call    XdrEncodeIntUnsafe
0x14000e119  cmp     dword ptr [rsi+108h], 0
0x14000e120  jge     short loc_14000E15C
0x14000e122  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e129  lea     r13, WPP_GLOBAL_Control
0x14000e130  cmp     rcx, r13
0x14000e133  jz      short loc_14000E151
0x14000e135  mov     eax, [rcx+2Ch]
0x14000e138  test    al, 1
0x14000e13a  jz      short loc_14000E151
0x14000e13c  mov     rcx, [rcx+18h]
0x14000e140  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e147  mov     edx, 0F7h
0x14000e14c  call    WPP_SF_
0x14000e151  mov     ebx, [rsi+108h]
0x14000e157  jmp     loc_14000E469
0x14000e15c  mov     [rsp+78h+var_38], 2
0x14000e164  lea     rcx, [rbp+var_28]
0x14000e168  mov     [rsp+78h+var_40], rcx
0x14000e16d  lea     rax, [rbx+48h]
0x14000e171  mov     rcx, [rbp+var_20]
0x14000e175  mov     r9, r15
0x14000e178  mov     [rsp+78h+var_48], rsi
0x14000e17d  mov     r8, r14
0x14000e180  mov     [rsp+78h+var_50], rax
0x14000e185  mov     rax, [r14+28h]
0x14000e189  mov     [rsp+78h+var_58], rax
0x14000e18e  call    NfsSendWaitReply
0x14000e193  mov     ebx, eax
0x14000e195  test    eax, eax
0x14000e197  jns     short loc_14000E1D9
0x14000e199  mov     rax, cs:WPP_GLOBAL_Control
0x14000e1a0  lea     r13, WPP_GLOBAL_Control
0x14000e1a7  cmp     rax, r13
0x14000e1aa  jz      loc_14000E469
0x14000e1b0  mov     ecx, [rax+2Ch]
0x14000e1b3  test    cl, 1
0x14000e1b6  jz      loc_14000E469
0x14000e1bc  mov     rcx, [rax+18h]
0x14000e1c0  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e1c7  mov     edx, 0F8h
0x14000e1cc  mov     r9d, ebx
0x14000e1cf  call    WPP_SF_d
0x14000e1d4  jmp     loc_14000E469
0x14000e1d9  mov     r8, [rbp+var_28]
0x14000e1dd  mov     rcx, r8
0x14000e1e0  call    OncRpcMapRpcStatusToNtStatus
0x14000e1e5  mov     ebx, eax
0x14000e1e7  test    eax, eax
0x14000e1e9  jns     short loc_14000E22A
0x14000e1eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e1f2  lea     r13, WPP_GLOBAL_Control
0x14000e1f9  cmp     rcx, r13
0x14000e1fc  jz      loc_14000E45A
0x14000e202  mov     eax, [rcx+2Ch]
0x14000e205  test    al, 1
0x14000e207  jz      loc_14000E45A
0x14000e20d  mov     rcx, [rcx+18h]
0x14000e211  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e218  mov     edx, 0F9h
0x14000e21d  mov     r9d, ebx
0x14000e220  call    WPP_SF_d
0x14000e225  jmp     loc_14000E456
0x14000e22a  mov     rcx, r8
0x14000e22d  call    XdrDecodeInt
0x14000e232  mov     r8, [rbp+var_28]
0x14000e236  mov     r15d, eax
0x14000e239  cmp     dword ptr [r8+108h], 0
0x14000e241  jge     short loc_14000E282
0x14000e243  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e24a  lea     r13, WPP_GLOBAL_Control
0x14000e251  cmp     rcx, r13
0x14000e254  jz      short loc_14000E276
0x14000e256  mov     eax, [rcx+2Ch]
0x14000e259  test    al, 1
0x14000e25b  jz      short loc_14000E276
0x14000e25d  mov     rcx, [rcx+18h]
0x14000e261  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e268  mov     edx, 0FAh
0x14000e26d  call    WPP_SF_
0x14000e272  mov     r8, [rbp+var_28]
0x14000e276  mov     ebx, [r8+108h]
0x14000e27d  jmp     loc_14000E45A
0x14000e282  test    r15d, r15d
0x14000e285  jz      loc_14000E39F
0x14000e28b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e292  lea     r13, WPP_GLOBAL_Control
0x14000e299  cmp     rcx, r13
0x14000e29c  jz      short loc_14000E2C1
0x14000e29e  mov     eax, [rcx+2Ch]
0x14000e2a1  test    al, 1
0x14000e2a3  jz      short loc_14000E2C1
0x14000e2a5  mov     rcx, [rcx+18h]
0x14000e2a9  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e2b0  mov     edx, 0FBh
0x14000e2b5  mov     r9d, r15d
0x14000e2b8  call    WPP_SF_d
0x14000e2bd  mov     r8, [rbp+var_28]
0x14000e2c1  mov     rcx, r8
0x14000e2c4  call    XdrDecodeBool
0x14000e2c9  test    al, al
0x14000e2cb  jz      short loc_14000E2DB
0x14000e2cd  mov     rcx, [rbp+var_28]
0x14000e2d1  mov     edx, 18h
0x14000e2d6  call    XdrDecodeSkipBytes
0x14000e2db  mov     rcx, [rbp+var_28]
0x14000e2df  call    XdrDecodeBool
0x14000e2e4  test    al, al
0x14000e2e6  jz      short loc_14000E356
0x14000e2e8  mov     rcx, rdi
0x14000e2eb  call    HacAcquireLock
0x14000e2f0  mov     rcx, [rbp+var_28]
0x14000e2f4  lea     rbx, [rdi+80h]
0x14000e2fb  mov     r14d, [rbx]
0x14000e2fe  mov     rdx, rbx
0x14000e301  mov     r8b, r12b
0x14000e304  call    XdrDecodeNfsFileAttributes
0x14000e309  mov     r8d, [rbx]
0x14000e30c  cmp     r8d, r14d
0x14000e30f  jz      short loc_14000E344
0x14000e311  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e318  cmp     rcx, r13
0x14000e31b  jz      short loc_14000E341
0x14000e31d  mov     eax, [rcx+2Ch]
0x14000e320  test    al, 1
0x14000e322  jz      short loc_14000E341
0x14000e324  mov     rcx, [rcx+18h]
0x14000e328  mov     edx, 0FCh
0x14000e32d  mov     dword ptr [rsp+78h+var_58], r8d
0x14000e332  mov     r9d, r14d
0x14000e335  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e33c  call    WPP_SF_dd
0x14000e341  mov     [rbx], r14d
0x14000e344  mov     rcx, [rdi+28h]; Mutex
0x14000e348  xor     edx, edx; Wait
0x14000e34a  call    cs:__imp_KeReleaseMutex
0x14000e351  nop     dword ptr [rax+rax+00h]
0x14000e356  mov     r8, [rbp+var_28]
0x14000e35a  cmp     dword ptr [r8+108h], 0
0x14000e362  jge     short loc_14000E390
0x14000e364  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e36b  cmp     rcx, r13
0x14000e36e  jz      short loc_14000E390
0x14000e370  mov     eax, [rcx+2Ch]
0x14000e373  test    al, 1
0x14000e375  jz      short loc_14000E390
0x14000e377  mov     rcx, [rcx+18h]
0x14000e37b  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000e382  mov     edx, 0FDh
0x14000e387  call    WPP_SF_
0x14000e38c  mov     r8, [rbp+var_28]
0x14000e390  mov     ecx, r15d
0x14000e393  call    MapNFSStatusToNtStatus
0x14000e398  mov     ebx, eax
0x14000e39a  jmp     loc_14000E45A
0x14000e39f  mov     rcx, r8
0x14000e3a2  call    XdrDecodeBool
0x14000e3a7  test    al, al
0x14000e3a9  jz      short loc_14000E3B9
0x14000e3ab  mov     rcx, [rbp+var_28]
0x14000e3af  mov     edx, 18h
0x14000e3b4  call    XdrDecodeSkipBytes
0x14000e3b9  mov     rcx, [rbp+var_28]
0x14000e3bd  call    XdrDecodeBool
0x14000e3c2  test    al, al
0x14000e3c4  jz      short loc_14000E3F3
0x14000e3c6  mov     rcx, rdi
0x14000e3c9  call    HacAcquireLock
0x14000e3ce  mov     rcx, [rbp+var_28]
0x14000e3d2  lea     rdx, [rdi+80h]
0x14000e3d9  mov     r8b, r12b
0x14000e3dc  call    XdrDecodeNfsFileAttributes
0x14000e3e1  mov     rcx, [rdi+28h]; Mutex
0x14000e3e5  xor     edx, edx; Wait
0x14000e3e7  call    cs:__imp_KeReleaseMutex
0x14000e3ee  nop     dword ptr [rax+rax+00h]
0x14000e3f3  mov     rcx, [rbp+var_28]
0x14000e3f7  lea     r8, [rbp+Source2]
0x14000e3fb  mov     ebx, 8
0x14000e400  mov     edx, ebx
0x14000e402  call    XdrDecodeOpaque
0x14000e407  mov     r8d, ebx; Length
0x14000e40a  lea     rdx, [rbp+Source2]; Source2
0x14000e40e  mov     rcx, r13; Source1
0x14000e411  call    cs:__imp_RtlCompareMemory
0x14000e418  nop     dword ptr [rax+rax+00h]
0x14000e41d  cmp     rax, rbx
0x14000e420  jz      short loc_14000E47C
0x14000e422  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e429  lea     r13, WPP_GLOBAL_Control
0x14000e430  cmp     rcx, r13
0x14000e433  jz      short loc_14000E451
0x14000e435  mov     eax, [rcx+2Ch]
0x14000e438  test    al, 2
0x14000e43a  jz      short loc_14000E451
0x14000e43c  mov     rcx, [rcx+18h]
  ... truncated ...
```
