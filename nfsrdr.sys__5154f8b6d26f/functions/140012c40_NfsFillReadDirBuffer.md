# NfsFillReadDirBuffer

- ea: `0x140012c40`
- end: `0x1400132c5`
- name: `NfsFillReadDirBuffer`
- size: `1669`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x140005de0`
- `0x140013dc0`

## callees

- `0x140003440`
- `0x140008140`
- `0x14000d4cc`
- `0x14000d99c`
- `0x14000fb40`
- `0x140011298`
- `0x140011fd4`
- `0x140012c40`
- `0x1400159cc`
- `0x1400159fc`
- `0x1400184b8`
- `0x140018804`
- `0x14001f860`
- `0x1400204c0`
- `0x1400209b0`
- `0x14002a518`
- `0x14002b650`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140012fbc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012fbc`
- `ntoskrnl!KeReleaseMutex` at `0x140012d8d`
- `ntoskrnl!KeReleaseMutex` at `0x140012df1`
- `ntoskrnl!KeReleaseMutex` at `0x140012f18`
- `ntoskrnl!KeReleaseMutex` at `0x140012fee`
- `ntoskrnl!KeReleaseMutex` at `0x140013000`
- `ntoskrnl!KeReleaseMutex` at `0x140012d8d`
- `ntoskrnl!KeReleaseMutex` at `0x140012df1`
- `ntoskrnl!KeReleaseMutex` at `0x140012f18`
- `ntoskrnl!KeReleaseMutex` at `0x140012fee`
- `ntoskrnl!KeReleaseMutex` at `0x140013000`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131d3`
- `ntoskrnl!ExAllocatePool2` at `0x14001309a`
- `ntoskrnl!ExAllocatePool2` at `0x14001309a`
- `rpcxdr!OncRpcDestroy` at `0x1400131ec`
- `rpcxdr!OncRpcDestroy` at `0x140013261`
- `rpcxdr!OncRpcDestroy` at `0x1400131ec`
- `rpcxdr!OncRpcDestroy` at `0x140013261`

## pseudocode

```c
__int64 __fastcall NfsFillReadDirBuffer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  bool v13; // r15
  int DirBufferFromNet; // esi
  __int64 v15; // rax
  unsigned int v16; // eax
  _QWORD *v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r15
  __int64 v22; // r12
  unsigned __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  __int64 NextBufferDescriptor; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // r8
  unsigned __int64 v33; // r15
  __int64 v34; // r12
  unsigned __int64 v35; // rax
  __int64 v36; // rdx
  __int64 Pool2; // rax
  __int64 v38; // r15
  int v39; // r12d
  unsigned __int64 v40; // rbx
  PDEVICE_OBJECT v41; // rcx
  __int64 v42; // rdx
  char v43; // [rsp+30h] [rbp-41h]
  unsigned int v44; // [rsp+34h] [rbp-3Dh] BYREF
  int v45; // [rsp+38h] [rbp-39h]
  __int64 v46; // [rsp+40h] [rbp-31h]
  __int64 v47; // [rsp+48h] [rbp-29h] BYREF
  int v48; // [rsp+50h] [rbp-21h] BYREF
  __int64 v49; // [rsp+58h] [rbp-19h]
  unsigned __int64 v50; // [rsp+60h] [rbp-11h] BYREF
  __int64 v51; // [rsp+68h] [rbp-9h] BYREF

  v4 = 0;
  v46 = *(_QWORD *)(a2 + 80);
  v51 = 0;
  v49 = a1;
  v48 = 0;
  LODWORD(v47) = 0;
  v44 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 208, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  if ( (unsigned __int8)HacIsEntryFake(a3) )
    return 0;
  v10 = *(_DWORD *)a4;
  v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL);
  v45 = 3;
  v12 = 2;
  v13 = *(_DWORD *)(v11 + 88) == 3;
  if ( v10 == 3 )
  {
    if ( (*(_BYTE *)(v11 + 112) & 1) != 0 )
    {
      *(_DWORD *)a4 = 2;
      v45 = 2;
    }
  }
  else
  {
    v45 = v10;
  }
  if ( (*(_DWORD *)(a4 + 48) & 1) == 0 || !(unsigned int)SearchDirEntryInCache(a1, a2, a3, a4) )
  {
    HacAcquireLock(a3, v11, v12);
    v15 = *(_QWORD *)(a3 + 32);
    if ( v15 )
    {
      v16 = *(unsigned __int16 *)(v15 + 4);
      if ( v16 > *(_DWORD *)a4 )
        *(_DWORD *)a4 = v16;
    }
    KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
    DirBufferFromNet = NfsReadDirBufferFromNet(a1, a2, a3, a4);
    if ( DirBufferFromNet < 0 )
      goto LABEL_87;
    if ( *(_DWORD *)a4 != 2 && *(_DWORD *)a4 != 3 )
      goto LABEL_26;
    v17 = (_QWORD *)(a4 + 8);
    if ( (unsigned __int8)XdrDecodeBool(*(_QWORD *)(a4 + 8)) )
    {
      HacAcquireLock(a3, v18, v19);
      LOBYTE(v20) = v13;
      XdrDecodeNfsFileAttributes(*v17, a3 + 128, v20);
      KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
      if ( *(int *)(*v17 + 264LL) < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_84;
        v27 = 210;
        goto LABEL_83;
      }
      HacUpdateTimeStamp(a3);
    }
    XdrDecodeOpaque(*v17, 8, &v51);
    if ( *(int *)(*v17 + 264LL) >= 0 )
    {
      v4 = v51;
LABEL_26:
      if ( (*(_DWORD *)(a4 + 48) & 1) == 0 )
      {
LABEL_87:
        *(_DWORD *)a4 = v45;
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        {
          return (unsigned int)DirBufferFromNet;
        }
        v42 = 216;
LABEL_90:
        WPP_SF_(v41->AttachedDevice, v42, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        return (unsigned int)DirBufferFromNet;
      }
      v17 = (_QWORD *)(a4 + 8);
      v21 = *(_QWORD *)(a4 + 8);
      v22 = *(_QWORD *)(v21 + 72);
      v50 = *(_QWORD *)(v22 + 64);
      LODWORD(v51) = *(_DWORD *)(v21 + 264);
      DirBufferFromNet = GetNoOfEntriesAndNamesLength(v49, a4, &v44, &v47);
      if ( (int)(DirBufferFromNet + 0x80000000) < 0 || DirBufferFromNet == -2147483642 )
      {
        v23 = v50;
        *(_QWORD *)(v21 + 72) = v22;
        *(_QWORD *)(v22 + 64) = v23;
        *(_DWORD *)(v21 + 264) = v51;
        v24 = *v17;
        v25 = *(_QWORD *)(*v17 + 72LL);
        while ( 1 )
        {
          NextBufferDescriptor = OncRpcBufMgrGetNextBufferDescriptor(v24 + 32, v25);
          if ( !NextBufferDescriptor )
            break;
          v25 = NextBufferDescriptor;
          *(_QWORD *)(NextBufferDescriptor + 64) = *(_QWORD *)(NextBufferDescriptor + 56);
        }
        v29 = v44;
        if ( v44 )
        {
          v32 = 192LL * v44 + (unsigned int)v47 + 232LL;
          v43 = 0;
          v47 = v32;
          v33 = v32 + 48;
          v34 = v46;
          if ( *(_QWORD *)(a3 + 32) )
            v33 = v32;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u) )
          {
            WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, v44, v32, v44, v32, *(_DWORD *)(v46 + 2340));
          }
          while ( 1 )
          {
            HacAcquireLock(a3, v29, v32);
            KeWaitForSingleObject((PVOID)(v34 + 2152), Executive, 0, 0, 0);
            v35 = *(unsigned int *)(v46 + 2340);
            if ( v35 >= v33 )
            {
              v43 = 1;
              *(_DWORD *)(v46 + 2340) = v35 - v33;
            }
            KeReleaseMutex((PRKMUTEX)(v34 + 2152), 0);
            KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
            if ( v43 )
              break;
            v36 = *(_QWORD *)(*(_QWORD *)(v49 + 32) + 40LL);
            if ( !v36 )
            {
              DirBufferFromNet = -1073741634;
              goto LABEL_85;
            }
            if ( !(unsigned int)PruneDirectoryCache(v46, *(_QWORD *)(v36 + 72), v33) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u) )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 213, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
              }
              *(_DWORD *)(a4 + 48) &= ~1u;
              DirBufferFromNet = 0;
              *(_QWORD *)(a4 + 256) = 0;
              goto LABEL_87;
            }
          }
          Pool2 = ExAllocatePool2(258, v47, 1263691342);
          v38 = Pool2;
          if ( !Pool2 )
          {
            DirBufferFromNet = -1073741670;
            goto LABEL_85;
          }
          *(_QWORD *)Pool2 = Pool2;
          v39 = 0;
          *(_DWORD *)(Pool2 + 8) = 0;
          if ( !*(_QWORD *)(a4 + 80) )
            *(_DWORD *)(Pool2 + 8) = 2;
          *(_DWORD *)(Pool2 + 24) = 0;
          if ( (unsigned int)(*(_DWORD *)a4 - 2) <= 1 )
            *(_QWORD *)(Pool2 + 16) = v4;
          v40 = Pool2 + 40;
          v51 = 0;
          while ( v39 <= (int)v44 )
          {
            v50 = v40 + 184;
            DirBufferFromNet = NfsUnPackAnEntry(v49, a4, v40, (unsigned int)&v50, (__int64)&v48, 1);
            if ( (int)(DirBufferFromNet + 0x80000000) >= 0 && DirBufferFromNet != -2147483642 )
              goto LABEL_74;
            if ( v48 )
            {
              *(_DWORD *)(v38 + 8) |= 1u;
              break;
            }
            if ( DirBufferFromNet == 261 )
              break;
            ++v39;
            v51 = *(_QWORD *)(v40 + 8);
            v40 = (*(_DWORD *)(v40 + 16) + 184 + v40 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          }
          *(_QWORD *)(v38 + 32) = v51;
          *(_DWORD *)(v38 + 24) = v39;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 214, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
          }
          DirBufferFromNet = InsertDirBufferIntoDirCache(v46, a3, v38, a4, v47);
          if ( DirBufferFromNet < 0 )
          {
LABEL_74:
            ExFreePoolWithTag((PVOID)v38, 0);
            goto LABEL_85;
          }
          if ( *v17 )
          {
            OncRpcDestroy(*v17);
            *v17 = 0;
          }
          goto LABEL_77;
        }
        HacAcquireLock(a3, v44, v24);
        v30 = *(_QWORD *)(a3 + 32);
        if ( v30 )
        {
          v31 = *(_QWORD *)(v30 + 8);
          if ( v31 )
            *(_DWORD *)(v31 + 8) |= 1u;
        }
        KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
        DirBufferFromNet = -2147483642;
      }
LABEL_85:
      if ( *v17 )
      {
        OncRpcDestroy(*v17);
        *v17 = 0;
      }
      goto LABEL_87;
    }
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    {
LABEL_84:
      DirBufferFromNet = *(_DWORD *)(*v17 + 264LL);
      goto LABEL_85;
    }
    v27 = 211;
LABEL_83:
    WPP_SF_(v26->AttachedDevice, v27, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_84;
  }
  DirBufferFromNet = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 209, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
LABEL_77:
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      return (unsigned int)DirBufferFromNet;
    v42 = 215;
    goto LABEL_90;
  }
  return (unsigned int)DirBufferFromNet;
}

```

## disassembly

```asm
0x140012c40  push    rbp
0x140012c42  push    rbx
0x140012c43  push    rsi
0x140012c44  push    rdi
0x140012c45  push    r12
0x140012c47  push    r13
0x140012c49  push    r14
0x140012c4b  push    r15
0x140012c4d  lea     rbp, [rsp-17h]
0x140012c52  sub     rsp, 88h
0x140012c59  mov     rax, cs:__security_cookie
0x140012c60  xor     rax, rsp
0x140012c63  mov     [rbp+4Fh+var_50], rax
0x140012c67  mov     rax, [rdx+50h]
0x140012c6b  xor     ebx, ebx
0x140012c6d  mov     [rbp+4Fh+var_80], rax
0x140012c71  mov     r14, r9
0x140012c74  mov     [rbp+4Fh+var_58], rbx
0x140012c78  mov     r13, r8
0x140012c7b  mov     rdi, rdx
0x140012c7e  mov     [rbp+4Fh+var_68], rcx
0x140012c82  mov     rsi, rcx
0x140012c85  mov     [rbp+4Fh+var_70], 0
0x140012c8c  mov     dword ptr [rbp+4Fh+var_78], 0
0x140012c93  mov     [rbp+4Fh+var_8C], 0
0x140012c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ca1  lea     r12, WPP_GLOBAL_Control
0x140012ca8  cmp     rcx, r12
0x140012cab  jz      short loc_140012CC9
0x140012cad  mov     eax, [rcx+2Ch]
0x140012cb0  test    al, 40h
0x140012cb2  jz      short loc_140012CC9
0x140012cb4  mov     rcx, [rcx+18h]
0x140012cb8  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140012cbf  mov     edx, 0D0h
0x140012cc4  call    WPP_SF_
0x140012cc9  mov     rcx, r13
0x140012ccc  call    HacIsEntryFake
0x140012cd1  test    al, al
0x140012cd3  jz      short loc_140012CDC
0x140012cd5  xor     eax, eax
0x140012cd7  jmp     loc_1400132A4
0x140012cdc  mov     rax, [rsi+20h]
0x140012ce0  mov     rcx, [rax+20h]
0x140012ce4  mov     eax, [r14]
0x140012ce7  mov     rdx, [rcx+20h]
0x140012ceb  mov     ecx, 3
0x140012cf0  mov     [rbp+4Fh+var_88], ecx
0x140012cf3  cmp     [rdx+58h], ecx
0x140012cf6  lea     r8d, [rcx-1]
0x140012cfa  setz    r15b
0x140012cfe  cmp     eax, ecx
0x140012d00  jnz     short loc_140012D11
0x140012d02  test    byte ptr [rdx+70h], 1
0x140012d06  jz      short loc_140012D14
0x140012d08  mov     [r14], r8d
0x140012d0b  mov     [rbp+4Fh+var_88], r8d
0x140012d0f  jmp     short loc_140012D14
0x140012d11  mov     [rbp+4Fh+var_88], eax
0x140012d14  mov     eax, [r14+30h]
0x140012d18  test    al, 1
0x140012d1a  jz      short loc_140012D6A
0x140012d1c  mov     r9, r14
0x140012d1f  mov     r8, r13
0x140012d22  mov     rdx, rdi
0x140012d25  mov     rcx, rsi
0x140012d28  call    SearchDirEntryInCache
0x140012d2d  test    eax, eax
0x140012d2f  jz      short loc_140012D6A
0x140012d31  xor     esi, esi
0x140012d33  mov     rcx, cs:WPP_GLOBAL_Control
0x140012d3a  cmp     rcx, r12
0x140012d3d  jz      loc_1400132A2
0x140012d43  test    dword ptr [rcx+2Ch], 100h
0x140012d4a  jz      loc_140013206
0x140012d50  mov     rcx, [rcx+18h]
0x140012d54  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140012d5b  mov     edx, 0D1h
0x140012d60  call    WPP_SF_
0x140012d65  jmp     loc_140013206
0x140012d6a  mov     rcx, r13
0x140012d6d  call    HacAcquireLock
0x140012d72  mov     rax, [r13+20h]
0x140012d76  test    rax, rax
0x140012d79  jz      short loc_140012D87
0x140012d7b  movzx   eax, word ptr [rax+4]
0x140012d7f  cmp     eax, [r14]
0x140012d82  jbe     short loc_140012D87
0x140012d84  mov     [r14], eax
0x140012d87  mov     rcx, [r13+28h]; Mutex
0x140012d8b  xor     edx, edx; Wait
0x140012d8d  call    cs:__imp_KeReleaseMutex
0x140012d94  nop     dword ptr [rax+rax+00h]
0x140012d99  mov     r9, r14
0x140012d9c  mov     r8, r13
0x140012d9f  mov     rdx, rdi
0x140012da2  mov     rcx, rsi
0x140012da5  call    NfsReadDirBufferFromNet
0x140012daa  mov     esi, eax
0x140012dac  test    eax, eax
0x140012dae  js      loc_140013274
0x140012db4  mov     eax, [r14]
0x140012db7  sub     eax, 2
0x140012dba  jz      short loc_140012DC1
0x140012dbc  cmp     eax, 1
0x140012dbf  jnz     short loc_140012E38
0x140012dc1  lea     rdi, [r14+8]
0x140012dc5  mov     rcx, [rdi]
0x140012dc8  call    XdrDecodeBool
0x140012dcd  test    al, al
0x140012dcf  jz      short loc_140012E14
0x140012dd1  mov     rcx, r13
0x140012dd4  call    HacAcquireLock
0x140012dd9  mov     rcx, [rdi]
0x140012ddc  lea     rdx, [r13+80h]
0x140012de3  mov     r8b, r15b
0x140012de6  call    XdrDecodeNfsFileAttributes
0x140012deb  mov     rcx, [r13+28h]; Mutex
0x140012def  xor     edx, edx; Wait
0x140012df1  call    cs:__imp_KeReleaseMutex
0x140012df8  nop     dword ptr [rax+rax+00h]
0x140012dfd  mov     rax, [rdi]
0x140012e00  cmp     [rax+108h], ebx
0x140012e06  jl      loc_140012EAF
0x140012e0c  mov     rcx, r13
0x140012e0f  call    HacUpdateTimeStamp
0x140012e14  mov     rcx, [rdi]
0x140012e17  lea     r8, [rbp+4Fh+var_58]
0x140012e1b  mov     edx, 8
0x140012e20  call    XdrDecodeOpaque
0x140012e25  mov     rax, [rdi]
0x140012e28  cmp     [rax+108h], ebx
0x140012e2e  jl      loc_140013228
0x140012e34  mov     rbx, [rbp+4Fh+var_58]
0x140012e38  mov     eax, [r14+30h]
0x140012e3c  test    al, 1
0x140012e3e  jz      loc_140013274
0x140012e44  mov     rcx, [rbp+4Fh+var_68]
0x140012e48  lea     rdi, [r14+8]
0x140012e4c  mov     r15, [rdi]
0x140012e4f  lea     r9, [rbp+4Fh+var_78]
0x140012e53  lea     r8, [rbp+4Fh+var_8C]
0x140012e57  mov     rdx, r14
0x140012e5a  mov     r12, [r15+48h]
0x140012e5e  mov     rax, [r12+40h]
0x140012e63  mov     [rbp+4Fh+var_60], rax
0x140012e67  mov     eax, [r15+108h]
0x140012e6e  mov     dword ptr [rbp+4Fh+var_58], eax
0x140012e71  call    GetNoOfEntriesAndNamesLength
0x140012e76  mov     ecx, 80000000h
0x140012e7b  mov     esi, eax
0x140012e7d  add     eax, ecx
0x140012e7f  test    ecx, eax
0x140012e81  jnz     short loc_140012E8F
0x140012e83  cmp     esi, 80000006h
0x140012e89  jnz     loc_140012F29
0x140012e8f  mov     rax, [rbp+4Fh+var_60]
0x140012e93  mov     [r15+48h], r12
0x140012e97  mov     [r12+40h], rax
0x140012e9c  mov     eax, dword ptr [rbp+4Fh+var_58]
0x140012e9f  mov     [r15+108h], eax
0x140012ea6  mov     r8, [rdi]
0x140012ea9  mov     rdx, [r8+48h]
0x140012ead  jmp     short loc_140012EDF
0x140012eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140012eb6  cmp     rcx, r12
0x140012eb9  jz      loc_140013250
0x140012ebf  mov     eax, [rcx+2Ch]
0x140012ec2  test    al, 1
0x140012ec4  jz      loc_140013250
0x140012eca  mov     edx, 0D2h
0x140012ecf  jmp     loc_140013240
0x140012ed4  mov     rcx, [rax+38h]
0x140012ed8  mov     rdx, rax
0x140012edb  mov     [rax+40h], rcx
0x140012edf  lea     rcx, [r8+20h]
0x140012ee3  call    OncRpcBufMgrGetNextBufferDescriptor
0x140012ee8  test    rax, rax
0x140012eeb  jnz     short loc_140012ED4
0x140012eed  mov     edx, [rbp+4Fh+var_8C]
0x140012ef0  test    edx, edx
0x140012ef2  jnz     short loc_140012F35
0x140012ef4  mov     rcx, r13
0x140012ef7  call    HacAcquireLock
0x140012efc  mov     rax, [r13+20h]
0x140012f00  test    rax, rax
0x140012f03  jz      short loc_140012F12
0x140012f05  mov     rax, [rax+8]
0x140012f09  test    rax, rax
0x140012f0c  jz      short loc_140012F12
0x140012f0e  or      dword ptr [rax+8], 1
0x140012f12  mov     rcx, [r13+28h]; Mutex
0x140012f16  xor     edx, edx; Wait
0x140012f18  call    cs:__imp_KeReleaseMutex
0x140012f1f  nop     dword ptr [rax+rax+00h]
0x140012f24  mov     esi, 80000006h
0x140012f29  lea     r12, WPP_GLOBAL_Control
0x140012f30  jmp     loc_140013259
0x140012f35  mov     r8d, dword ptr [rbp+4Fh+var_78]
0x140012f39  lea     rcx, [rdx+rdx*2]
0x140012f3d  shl     rcx, 6
0x140012f41  add     r8, 0E8h
0x140012f48  add     r8, rcx
0x140012f4b  mov     [rbp+4Fh+var_90], 0
0x140012f4f  mov     [rbp+4Fh+var_78], r8
0x140012f53  cmp     qword ptr [r13+20h], 0
0x140012f58  lea     r15, [r8+30h]
0x140012f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f63  lea     rax, WPP_GLOBAL_Control
0x140012f6a  mov     r12, [rbp+4Fh+var_80]
0x140012f6e  cmovnz  r15, r8
0x140012f72  cmp     rcx, rax
0x140012f75  jz      short loc_140012F9B
0x140012f77  bt      dword ptr [rcx+2Ch], 8
0x140012f7c  jnb     short loc_140012F9B
0x140012f7e  mov     eax, [r12+924h]
0x140012f86  mov     r9d, edx
0x140012f89  mov     rcx, [rcx+18h]
0x140012f8d  mov     [rsp+0C0h+var_98], eax
0x140012f91  mov     dword ptr [rsp+0C0h+Timeout], r8d
0x140012f96  call    WPP_SF_DDD
0x140012f9b  mov     rcx, r13
0x140012f9e  call    HacAcquireLock
0x140012fa3  xor     r9d, r9d; Alertable
0x140012fa6  mov     [rsp+0C0h+Timeout], 0; Timeout
0x140012faf  xor     r8d, r8d; WaitMode
0x140012fb2  lea     rcx, [r12+868h]; Object
0x140012fba  xor     edx, edx; WaitReason
0x140012fbc  call    cs:__imp_KeWaitForSingleObject
0x140012fc3  nop     dword ptr [rax+rax+00h]
0x140012fc8  mov     rcx, [rbp+4Fh+var_80]
0x140012fcc  mov     eax, [rcx+924h]
0x140012fd2  cmp     rax, r15
0x140012fd5  jb      short loc_140012FE4
0x140012fd7  sub     eax, r15d
0x140012fda  mov     [rbp+4Fh+var_90], 1
0x140012fde  mov     [rcx+924h], eax
0x140012fe4  xor     edx, edx; Wait
0x140012fe6  lea     rcx, [r12+868h]; Mutex
0x140012fee  call    cs:__imp_KeReleaseMutex
0x140012ff5  nop     dword ptr [rax+rax+00h]
0x140012ffa  mov     rcx, [r13+28h]; Mutex
0x140012ffe  xor     edx, edx; Wait
0x140013000  call    cs:__imp_KeReleaseMutex
0x140013007  nop     dword ptr [rax+rax+00h]
0x14001300c  cmp     [rbp+4Fh+var_90], 0
0x140013010  jnz     short loc_14001308B
0x140013012  mov     rax, [rbp+4Fh+var_68]
0x140013016  mov     rax, [rax+20h]
0x14001301a  mov     rdx, [rax+28h]
0x14001301e  test    rdx, rdx
0x140013021  jz      short loc_140013081
0x140013023  mov     rdx, [rdx+48h]
0x140013027  mov     r8, r15
0x14001302a  mov     rcx, [rbp+4Fh+var_80]
0x14001302e  call    PruneDirectoryCache
0x140013033  test    eax, eax
0x140013035  jnz     loc_140012F9B
0x14001303b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013042  lea     r12, WPP_GLOBAL_Control
0x140013049  cmp     rcx, r12
0x14001304c  jz      short loc_14001306A
0x14001304e  bt      dword ptr [rcx+2Ch], 8
0x140013053  jnb     short loc_14001306A
0x140013055  mov     rcx, [rcx+18h]
0x140013059  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140013060  mov     edx, 0D5h
0x140013065  call    WPP_SF_
0x14001306a  and     dword ptr [r14+30h], 0FFFFFFFEh
0x14001306f  xor     esi, esi
0x140013071  mov     qword ptr [r14+100h], 0
0x14001307c  jmp     loc_140013274
0x140013081  mov     esi, 0C00000BEh
0x140013086  jmp     loc_140012F29
0x14001308b  mov     rdx, [rbp+4Fh+var_78]
0x14001308f  mov     r8d, 4B52664Eh
0x140013095  mov     ecx, 102h
0x14001309a  call    cs:__imp_ExAllocatePool2
0x1400130a1  nop     dword ptr [rax+rax+00h]
0x1400130a6  mov     r15, rax
0x1400130a9  test    rax, rax
0x1400130ac  jnz     short loc_1400130B8
0x1400130ae  mov     esi, 0C000009Ah
0x1400130b3  jmp     loc_140012F29
0x1400130b8  xor     ecx, ecx
0x1400130ba  mov     [rax], r15
0x1400130bd  xor     r12d, r12d
0x1400130c0  mov     [rax+8], ecx
0x1400130c3  cmp     [r14+50h], rcx
0x1400130c7  jnz     short loc_1400130D0
0x1400130c9  mov     dword ptr [rax+8], 2
0x1400130d0  mov     [rax+18h], ecx
0x1400130d3  mov     eax, [r14]
0x1400130d6  sub     eax, 2
0x1400130d9  cmp     eax, 1
0x1400130dc  ja      short loc_1400130E2
0x1400130de  mov     [r15+10h], rbx
0x1400130e2  lea     rbx, [r15+28h]
0x1400130e6  mov     [rbp+4Fh+var_58], rcx
0x1400130ea  cmp     r12d, [rbp+4Fh+var_8C]
  ... truncated ...
```
