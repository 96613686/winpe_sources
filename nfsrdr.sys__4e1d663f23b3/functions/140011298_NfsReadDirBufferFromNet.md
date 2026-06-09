# NfsReadDirBufferFromNet

- ea: `0x140011298`
- end: `0x140011959`
- name: `NfsReadDirBufferFromNet`
- size: `1729`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x140012c40`

## callees

- `0x140001f10`
- `0x140008140`
- `0x14000e4c8`
- `0x14000fa80`
- `0x140011298`
- `0x140011960`
- `0x140011f84`
- `0x140013ac0`
- `0x1400145f0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140022220`
- `0x14002ba00`
- `0x14002ddac`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400113ba`
- `ntoskrnl!KeReleaseMutex` at `0x1400114a8`
- `ntoskrnl!KeReleaseMutex` at `0x140011563`
- `ntoskrnl!KeReleaseMutex` at `0x1400113ba`
- `ntoskrnl!KeReleaseMutex` at `0x1400114a8`
- `ntoskrnl!KeReleaseMutex` at `0x140011563`
- `rpcxdr!OncRpcDestroy` at `0x1400116a1`
- `rpcxdr!OncRpcDestroy` at `0x1400116b7`
- `rpcxdr!OncRpcDestroy` at `0x140011791`
- `rpcxdr!OncRpcDestroy` at `0x140011842`
- `rpcxdr!OncRpcDestroy` at `0x1400118ca`
- `rpcxdr!OncRpcDestroy` at `0x1400116a1`
- `rpcxdr!OncRpcDestroy` at `0x1400116b7`
- `rpcxdr!OncRpcDestroy` at `0x140011791`
- `rpcxdr!OncRpcDestroy` at `0x140011842`
- `rpcxdr!OncRpcDestroy` at `0x1400118ca`

## pseudocode

```c
__int64 __fastcall NfsReadDirBufferFromNet(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // r13d
  __int64 v8; // rbx
  bool v9; // r12
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // r8
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 *v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  _QWORD *v29; // r14
  int v30; // ebx
  __int64 v31; // r8
  unsigned int v32; // eax
  unsigned int v33; // ebx
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  struct _DEVICE_OBJECT *v36; // rdx
  unsigned __int8 v37; // r8
  __int64 v39; // [rsp+90h] [rbp+8h]
  __int64 v40; // [rsp+98h] [rbp+10h] BYREF

  v39 = *(_QWORD *)(a2 + 80);
  v6 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 229, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL);
  v9 = *(_DWORD *)(v8 + 88) == 3;
  if ( !v8 )
    return 3221225662LL;
  v10 = 0;
  if ( !*(_QWORD *)(a1 + 40) )
    return 3221225662LL;
  while ( 1 )
  {
    if ( *(_DWORD *)a4 != 1 )
    {
      if ( *(_DWORD *)a4 != 2 )
      {
        if ( *(_DWORD *)a4 != 3 )
          goto LABEL_29;
        v10 = NfsRdrBuildCall(v8 + 116, *(_DWORD *)(v8 + 80), *(_DWORD *)(v8 + 84), *(_DWORD *)(v8 + 88), 17, 92, a1);
        if ( !v10 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v35 = 234;
            goto LABEL_77;
          }
LABEL_78:
          v30 = -1073741670;
LABEL_79:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 243, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
          }
          return (unsigned int)v30;
        }
        HacAcquireLock(a3);
        LOBYTE(v11) = v9;
        XdrEncodeNfsFileHandleUnsafe(v10, a3 + 216, v11);
        XdrEncodeHyperUnsafe(v10, *(_QWORD *)(a4 + 80));
        v13 = *(_QWORD *)(a3 + 32);
        if ( v13 )
          v14 = *(_QWORD *)(*(_QWORD *)(v13 + 8) + 16LL);
        else
          v14 = 0;
        XdrEncodeHyperUnsafe(v12, v14);
        KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
        XdrEncodeIntUnsafe(v10, *(unsigned int *)(a4 + 4), v15);
        XdrEncodeIntUnsafe(v16, *(unsigned int *)(a4 + 4), v17);
        if ( *(int *)(v10 + 264) < 0 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v19 = 235;
            goto LABEL_71;
          }
          goto LABEL_72;
        }
        goto LABEL_29;
      }
      v10 = NfsRdrBuildCall(v8 + 116, *(_DWORD *)(v8 + 80), *(_DWORD *)(v8 + 84), *(_DWORD *)(v8 + 88), 16, 88, a1);
      if ( v10 )
      {
        HacAcquireLock(a3);
        LOBYTE(v20) = v9;
        XdrEncodeNfsFileHandleUnsafe(v10, a3 + 216, v20);
        if ( *(_QWORD *)(a3 + 32) )
        {
          XdrEncodeHyperUnsafe(v10, *(_QWORD *)(a4 + 80));
          v22 = v10;
          v23 = (__int64 *)(*(_QWORD *)(*(_QWORD *)(a3 + 32) + 8LL) + 16LL);
        }
        else
        {
          v40 = 0;
          XdrEncodeHyperUnsafe(v10, 0);
          v23 = &v40;
        }
        XdrEncodeOpaque(v22, v21, v23);
        KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
        XdrEncodeIntUnsafe(v10, *(unsigned int *)(a4 + 4), v24);
        if ( *(int *)(v10 + 264) < 0 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v19 = 233;
            goto LABEL_71;
          }
          goto LABEL_72;
        }
        goto LABEL_29;
      }
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_78;
      v35 = 232;
LABEL_77:
      WPP_SF_(v34->AttachedDevice, v35, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      goto LABEL_78;
    }
    v10 = NfsRdrBuildCall(v8 + 116, *(_DWORD *)(v8 + 80), *(_DWORD *)(v8 + 84), *(_DWORD *)(v8 + 88), 16, 44, a1);
    if ( !v10 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_78;
      v35 = 230;
      goto LABEL_77;
    }
    HacAcquireLock(a3);
    LOBYTE(v25) = v9;
    XdrEncodeNfsFileHandleUnsafe(v10, a3 + 216, v25);
    v27 = 0;
    if ( *(_QWORD *)(a3 + 32) )
      v27 = *(unsigned int *)(a4 + 80);
    XdrEncodeIntUnsafe(v10, v27, v26);
    KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
    XdrEncodeIntUnsafe(v10, *(unsigned int *)(a4 + 4), v28);
    if ( *(int *)(v10 + 264) < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v19 = 231;
LABEL_71:
        WPP_SF_(v18->AttachedDevice, v19, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      }
LABEL_72:
      v30 = *(_DWORD *)(v10 + 264);
LABEL_73:
      OncRpcDestroy(v10);
      goto LABEL_79;
    }
LABEL_29:
    v29 = (_QWORD *)(a4 + 8);
    v30 = NfsSendWaitReply(v39, a2, a1, v6, *(_QWORD *)(a1 + 40), v8 + 72, v10, a4 + 8, 1);
    if ( v30 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 236, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      goto LABEL_73;
    }
    v30 = OncRpcMapRpcStatusToNtStatus(*v29);
    if ( v30 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 237, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      goto LABEL_64;
    }
    v32 = XdrDecodeInt(v31);
    v33 = v32;
    if ( *(int *)(*v29 + 264LL) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 238, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      v30 = *(_DWORD *)(*v29 + 264LL);
      goto LABEL_64;
    }
    if ( !v32 )
      break;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 239, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    if ( v33 != 10004 || *(_DWORD *)a4 != 3 )
    {
      v30 = MapNFSStatusToNtStatus(v33);
      if ( v30 == -1073741816 )
      {
        if ( WPP_GLOBAL_Control != v36 && ((unsigned __int8)HIDWORD(WPP_GLOBAL_Control->Timer) & v37) != 0 )
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 241, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, a3 + 64);
        HacOrphanStaleEntry(v39, a3);
      }
LABEL_64:
      OncRpcDestroy(*v29);
      *v29 = 0;
      goto LABEL_73;
    }
    v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL);
    *(_WORD *)(v8 + 112) |= 1u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 240, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, a3 + 64);
    OncRpcDestroy(*v29);
    *v29 = 0;
    OncRpcDestroy(v10);
    *(_DWORD *)a4 = 2;
  }
  *(_QWORD *)(a4 + 56) = MEMORY[0xFFFFF78000000014];
  OncRpcDestroy(v10);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 242, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140011298  mov     [rsp+arg_10], rbx
0x14001129d  push    rbp
0x14001129e  push    rsi
0x14001129f  push    rdi
0x1400112a0  push    r12
0x1400112a2  push    r13
0x1400112a4  push    r14
0x1400112a6  push    r15
0x1400112a8  sub     rsp, 50h
0x1400112ac  mov     rax, [rdx+50h]
0x1400112b0  mov     r15, r9
0x1400112b3  mov     [rsp+88h+arg_0], rax
0x1400112bb  mov     rsi, r8
0x1400112be  mov     r13, rdx
0x1400112c1  mov     rbp, rcx
0x1400112c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112cb  lea     r14, WPP_GLOBAL_Control
0x1400112d2  cmp     rcx, r14
0x1400112d5  jz      short loc_1400112F3
0x1400112d7  mov     eax, [rcx+2Ch]
0x1400112da  test    al, 40h
0x1400112dc  jz      short loc_1400112F3
0x1400112de  mov     rcx, [rcx+18h]
0x1400112e2  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400112e9  mov     edx, 0E5h
0x1400112ee  call    WPP_SF_
0x1400112f3  mov     rax, [rbp+20h]
0x1400112f7  mov     rcx, [rax+20h]
0x1400112fb  mov     rbx, [rcx+20h]
0x1400112ff  cmp     dword ptr [rbx+58h], 3
0x140011303  setz    r12b
0x140011307  xor     r14d, r14d
0x14001130a  test    rbx, rbx
0x14001130d  jz      loc_14001193B
0x140011313  mov     edi, r14d
0x140011316  cmp     [rbp+28h], r14
0x14001131a  jz      loc_14001193B
0x140011320  mov     ecx, [r15]
0x140011323  sub     ecx, 1
0x140011326  jz      loc_1400114F9
0x14001132c  sub     ecx, 1
0x14001132f  jz      loc_140011414
0x140011335  cmp     ecx, 1
0x140011338  jnz     loc_140011588
0x14001133e  mov     r9d, [rbx+58h]
0x140011342  lea     rcx, [rbx+74h]
0x140011346  mov     r8d, [rbx+54h]
0x14001134a  mov     edx, [rbx+50h]
0x14001134d  mov     [rsp+88h+var_58], rbp
0x140011352  mov     dword ptr [rsp+88h+var_60], 5Ch ; '\'
0x14001135a  mov     dword ptr [rsp+88h+var_68], 11h
0x140011362  call    NfsRdrBuildCall
0x140011367  mov     rdi, rax
0x14001136a  test    rax, rax
0x14001136d  jz      loc_1400116D2
0x140011373  mov     rcx, rsi
0x140011376  call    HacAcquireLock
0x14001137b  lea     rdx, [rsi+0D8h]
0x140011382  mov     r8b, r12b
0x140011385  mov     rcx, rdi
0x140011388  call    XdrEncodeNfsFileHandleUnsafe
0x14001138d  mov     rdx, [r15+50h]
0x140011391  mov     rcx, rdi
0x140011394  call    XdrEncodeHyperUnsafe
0x140011399  mov     rax, [rsi+20h]
0x14001139d  test    rax, rax
0x1400113a0  jnz     short loc_1400113A7
0x1400113a2  mov     rdx, r14
0x1400113a5  jmp     short loc_1400113AF
0x1400113a7  mov     rax, [rax+8]
0x1400113ab  mov     rdx, [rax+10h]
0x1400113af  call    XdrEncodeHyperUnsafe
0x1400113b4  mov     rcx, [rsi+28h]; Mutex
0x1400113b8  xor     edx, edx; Wait
0x1400113ba  call    cs:__imp_KeReleaseMutex
0x1400113c1  nop     dword ptr [rax+rax+00h]
0x1400113c6  mov     edx, [r15+4]
0x1400113ca  mov     rcx, rdi
0x1400113cd  call    XdrEncodeIntUnsafe
0x1400113d2  mov     edx, [r15+4]
0x1400113d6  call    XdrEncodeIntUnsafe
0x1400113db  cmp     [rdi+108h], r14d
0x1400113e2  jge     loc_140011588
0x1400113e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113ef  lea     r14, WPP_GLOBAL_Control
0x1400113f6  cmp     rcx, r14
0x1400113f9  jz      loc_1400118C1
0x1400113ff  mov     eax, [rcx+2Ch]
0x140011402  test    al, 1
0x140011404  jz      loc_1400118C1
0x14001140a  mov     edx, 0EBh
0x14001140f  jmp     loc_1400118B1
0x140011414  mov     r9d, [rbx+58h]
0x140011418  lea     rcx, [rbx+74h]
0x14001141c  mov     r8d, [rbx+54h]
0x140011420  mov     edx, [rbx+50h]
0x140011423  mov     [rsp+88h+var_58], rbp
0x140011428  mov     dword ptr [rsp+88h+var_60], 58h ; 'X'
0x140011430  mov     dword ptr [rsp+88h+var_68], 10h
0x140011438  call    NfsRdrBuildCall
0x14001143d  mov     rdi, rax
0x140011440  test    rax, rax
0x140011443  jz      loc_1400116FE
0x140011449  mov     rcx, rsi
0x14001144c  call    HacAcquireLock
0x140011451  lea     rdx, [rsi+0D8h]
0x140011458  mov     r8b, r12b
0x14001145b  mov     rcx, rdi
0x14001145e  call    XdrEncodeNfsFileHandleUnsafe
0x140011463  mov     rcx, rdi
0x140011466  cmp     [rsi+20h], r14
0x14001146a  jnz     short loc_140011485
0x14001146c  xor     edx, edx
0x14001146e  mov     [rsp+88h+arg_8], r14
0x140011476  call    XdrEncodeHyperUnsafe
0x14001147b  lea     r8, [rsp+88h+arg_8]
0x140011483  jmp     short loc_14001149D
0x140011485  mov     rdx, [r15+50h]
0x140011489  call    XdrEncodeHyperUnsafe
0x14001148e  mov     rcx, [rsi+20h]
0x140011492  mov     r8, [rcx+8]
0x140011496  mov     rcx, rdi
0x140011499  add     r8, 10h
0x14001149d  call    XdrEncodeOpaque
0x1400114a2  mov     rcx, [rsi+28h]; Mutex
0x1400114a6  xor     edx, edx; Wait
0x1400114a8  call    cs:__imp_KeReleaseMutex
0x1400114af  nop     dword ptr [rax+rax+00h]
0x1400114b4  mov     edx, [r15+4]
0x1400114b8  mov     rcx, rdi
0x1400114bb  call    XdrEncodeIntUnsafe
0x1400114c0  cmp     [rdi+108h], r14d
0x1400114c7  jge     loc_140011588
0x1400114cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400114d4  lea     r14, WPP_GLOBAL_Control
0x1400114db  cmp     rcx, r14
0x1400114de  jz      loc_1400118C1
0x1400114e4  mov     eax, [rcx+2Ch]
0x1400114e7  test    al, 1
0x1400114e9  jz      loc_1400118C1
0x1400114ef  mov     edx, 0E9h
0x1400114f4  jmp     loc_1400118B1
0x1400114f9  mov     r9d, [rbx+58h]
0x1400114fd  lea     rcx, [rbx+74h]
0x140011501  mov     r8d, [rbx+54h]
0x140011505  mov     edx, [rbx+50h]
0x140011508  mov     [rsp+88h+var_58], rbp
0x14001150d  mov     dword ptr [rsp+88h+var_60], 2Ch ; ','
0x140011515  mov     dword ptr [rsp+88h+var_68], 10h
0x14001151d  call    NfsRdrBuildCall
0x140011522  mov     rdi, rax
0x140011525  test    rax, rax
0x140011528  jz      loc_1400118D8
0x14001152e  mov     rcx, rsi
0x140011531  call    HacAcquireLock
0x140011536  lea     rdx, [rsi+0D8h]
0x14001153d  mov     r8b, r12b
0x140011540  mov     rcx, rdi
0x140011543  call    XdrEncodeNfsFileHandleUnsafe
0x140011548  mov     edx, r14d
0x14001154b  cmp     [rsi+20h], r14
0x14001154f  jz      short loc_140011555
0x140011551  mov     edx, [r15+50h]
0x140011555  mov     rcx, rdi
0x140011558  call    XdrEncodeIntUnsafe
0x14001155d  mov     rcx, [rsi+28h]; Mutex
0x140011561  xor     edx, edx; Wait
0x140011563  call    cs:__imp_KeReleaseMutex
0x14001156a  nop     dword ptr [rax+rax+00h]
0x14001156f  mov     edx, [r15+4]
0x140011573  mov     rcx, rdi
0x140011576  call    XdrEncodeIntUnsafe
0x14001157b  cmp     [rdi+108h], r14d
0x140011582  jl      loc_140011892
0x140011588  mov     rcx, [rsp+88h+arg_0]
0x140011590  lea     rax, [rbx+48h]
0x140011594  mov     [rsp+88h+var_48], 1
0x14001159c  lea     r14, [r15+8]
0x1400115a0  mov     [rsp+88h+var_50], r14
0x1400115a5  mov     r9, r13
0x1400115a8  mov     [rsp+88h+var_58], rdi
0x1400115ad  mov     r8, rbp
0x1400115b0  mov     [rsp+88h+var_60], rax
0x1400115b5  mov     rax, [rbp+28h]
0x1400115b9  mov     [rsp+88h+var_68], rax
0x1400115be  call    NfsSendWaitReply
0x1400115c3  mov     ebx, eax
0x1400115c5  test    eax, eax
0x1400115c7  js      loc_14001185E
0x1400115cd  mov     r8, [r14]
0x1400115d0  mov     rcx, r8
0x1400115d3  call    OncRpcMapRpcStatusToNtStatus
0x1400115d8  mov     ebx, eax
0x1400115da  test    eax, eax
0x1400115dc  js      loc_14001180D
0x1400115e2  mov     rcx, r8
0x1400115e5  call    XdrDecodeInt
0x1400115ea  mov     rcx, [r14]
0x1400115ed  mov     ebx, eax
0x1400115ef  cmp     dword ptr [rcx+108h], 0
0x1400115f6  jl      loc_1400117D3
0x1400115fc  test    eax, eax
0x1400115fe  jz      loc_140011780
0x140011604  mov     rcx, cs:WPP_GLOBAL_Control
0x14001160b  lea     rdx, WPP_GLOBAL_Control
0x140011612  mov     r8d, 1
0x140011618  cmp     rcx, rdx
0x14001161b  jz      short loc_14001164A
0x14001161d  mov     edx, [rcx+2Ch]
0x140011620  test    r8b, dl
0x140011623  jz      short loc_140011643
0x140011625  mov     rcx, [rcx+18h]
0x140011629  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140011630  mov     edx, 0EFh
0x140011635  mov     r9d, eax
0x140011638  call    WPP_SF_d
0x14001163d  mov     r8d, 1
0x140011643  lea     rdx, WPP_GLOBAL_Control
0x14001164a  cmp     ebx, 2714h
0x140011650  jnz     loc_14001172A
0x140011656  cmp     dword ptr [r15], 3
0x14001165a  jnz     loc_14001172A
0x140011660  mov     rax, [rbp+20h]
0x140011664  mov     rcx, [rax+20h]
0x140011668  mov     rbx, [rcx+20h]
0x14001166c  or      [rbx+70h], r8w
0x140011671  mov     rcx, cs:WPP_GLOBAL_Control
0x140011678  cmp     rcx, rdx
0x14001167b  jz      short loc_14001169E
0x14001167d  mov     eax, [rcx+2Ch]
0x140011680  test    r8b, al
0x140011683  jz      short loc_14001169E
0x140011685  mov     rcx, [rcx+18h]
0x140011689  lea     r9, [rsi+40h]
0x14001168d  mov     edx, 0F0h
0x140011692  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140011699  call    WPP_SF_Z
0x14001169e  mov     rcx, [r14]
0x1400116a1  call    cs:__imp_OncRpcDestroy
0x1400116a8  nop     dword ptr [rax+rax+00h]
0x1400116ad  mov     rcx, rdi
0x1400116b0  mov     qword ptr [r14], 0
0x1400116b7  call    cs:__imp_OncRpcDestroy
0x1400116be  nop     dword ptr [rax+rax+00h]
0x1400116c3  xor     r14d, r14d
0x1400116c6  mov     dword ptr [r15], 2
0x1400116cd  jmp     loc_140011320
0x1400116d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116d9  lea     r14, WPP_GLOBAL_Control
0x1400116e0  cmp     rcx, r14
0x1400116e3  jz      loc_140011907
0x1400116e9  mov     eax, [rcx+2Ch]
0x1400116ec  test    al, 1
0x1400116ee  jz      loc_140011907
0x1400116f4  mov     edx, 0EAh
0x1400116f9  jmp     loc_1400118F7
0x1400116fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140011705  lea     r14, WPP_GLOBAL_Control
0x14001170c  cmp     rcx, r14
0x14001170f  jz      loc_140011907
0x140011715  mov     eax, [rcx+2Ch]
0x140011718  test    al, 1
0x14001171a  jz      loc_140011907
0x140011720  mov     edx, 0E8h
0x140011725  jmp     loc_1400118F7
0x14001172a  mov     ecx, ebx
0x14001172c  call    MapNFSStatusToNtStatus
0x140011731  mov     ebx, eax
0x140011733  cmp     eax, 0C0000008h
0x140011738  jnz     loc_14001183F
0x14001173e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011745  cmp     rcx, rdx
0x140011748  jz      short loc_14001176B
0x14001174a  mov     eax, [rcx+2Ch]
0x14001174d  test    r8b, al
0x140011750  jz      short loc_14001176B
0x140011752  mov     rcx, [rcx+18h]
0x140011756  lea     r9, [rsi+40h]
0x14001175a  mov     edx, 0F1h
0x14001175f  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140011766  call    WPP_SF_Z
0x14001176b  mov     rcx, [rsp+88h+arg_0]
0x140011773  mov     rdx, rsi
0x140011776  call    HacOrphanStaleEntry
0x14001177b  jmp     loc_14001183F
0x140011780  mov     rax, ds:0FFFFF78000000014h
0x14001178a  mov     rcx, rdi
0x14001178d  mov     [r15+38h], rax
0x140011791  call    cs:__imp_OncRpcDestroy
0x140011798  nop     dword ptr [rax+rax+00h]
0x14001179d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117a4  lea     rax, WPP_GLOBAL_Control
0x1400117ab  cmp     rcx, rax
0x1400117ae  jz      short loc_1400117CC
0x1400117b0  mov     eax, [rcx+2Ch]
0x1400117b3  test    al, 40h
0x1400117b5  jz      short loc_1400117CC
0x1400117b7  mov     rcx, [rcx+18h]
0x1400117bb  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400117c2  mov     edx, 0F2h
  ... truncated ...
```
