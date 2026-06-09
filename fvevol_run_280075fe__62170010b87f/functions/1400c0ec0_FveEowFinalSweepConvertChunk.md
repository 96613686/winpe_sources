# FveEowFinalSweepConvertChunk

- ea: `0x1400c0ec0`
- end: `0x1400c1372`
- name: `FveEowFinalSweepConvertChunk`
- size: `1202`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14009677c`
- `0x1400dfa70`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x140029a38`
- `0x14002c500`
- `0x14002cb80`
- `0x14007ccd0`
- `0x1400c0ec0`
- `0x1400c1378`
- `0x1400da590`
- `0x1400da8d4`
- `0x1400db1b8`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400c1140`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400c1140`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400c10ed`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400c10ed`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400c1314`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400c1314`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400c12ff`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400c12ff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400c0fe6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400c0fe6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400c1243`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400c1243`
- `ntoskrnl!KeBugCheckEx` at `0x1400c12d3`
- `ntoskrnl!KeBugCheckEx` at `0x1400c12d3`

## pseudocode

```c
void __fastcall FveEowFinalSweepConvertChunk(__int64 a1, char a2)
{
  char v2; // di
  char v4; // r12
  __int64 v5; // r8
  unsigned int v6; // esi
  char v7; // r14
  __int64 *v8; // rdi
  __int64 v9; // rdi
  char v10; // si
  char v11; // bp
  char v12; // al
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  char v15; // cl
  int v16; // [rsp+30h] [rbp-E8h]
  _BYTE v17[216]; // [rsp+40h] [rbp-D8h] BYREF
  char v18; // [rsp+120h] [rbp+8h] BYREF
  char v19; // [rsp+128h] [rbp+10h]
  char v20; // [rsp+130h] [rbp+18h] BYREF
  char v21; // [rsp+138h] [rbp+20h]

  v19 = a2;
  v2 = a2;
  memset(v17, 0, 0x90u);
  v4 = 0;
  v21 = 0;
  v18 = 0;
  v20 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 262, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
  }
  v16 = FvepAcquireRemoveLock(a1 + 56);
  v6 = v16;
  if ( v16 < 0 )
  {
    v7 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 263, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
    }
    goto LABEL_60;
  }
  v7 = 1;
  if ( !v2 )
  {
    LOBYTE(v5) = 1;
    FvepAcquireDevFveLock(a1, v17, v5);
    v21 = 1;
  }
  if ( (*(_DWORD *)(a1 + 808) & 0x100) != 0 )
  {
    v8 = *(__int64 **)(a1 + 736);
    if ( !v8 || (v9 = *v8) == 0 )
    {
LABEL_59:
      v2 = v19;
      goto LABEL_60;
    }
    v10 = *(_BYTE *)(v9 + 48);
    v11 = 0;
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v9 + 88));
    v12 = *(_BYTE *)(v9 + 144);
    if ( (v12 & 4) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 264, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
      }
      if ( (*(_BYTE *)(v9 + 144) & 0x38) != 8 )
        goto LABEL_56;
      v11 = 1;
      *(_BYTE *)(v9 + 144) &= ~8u;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        goto LABEL_56;
      }
      v14 = 265;
      goto LABEL_55;
    }
    v15 = v12 & 8;
    if ( (v12 & 0x30) == 0 )
    {
      if ( !v15 )
      {
        *(_BYTE *)(v9 + 144) = v12 | 8;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 267, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
        }
      }
      if ( *(_BYTE *)(a1 + 1476) )
      {
        if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 1448)) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
            goto LABEL_56;
          }
          v14 = 268;
LABEL_55:
          WPP_SF_(v13->AttachedDevice, v14, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
LABEL_56:
          KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v9 + 88));
          if ( v11 )
            FveQueueAutoWorkItem(a1, FveEowResetConversionLogsWorker, a1);
          v6 = v16;
          goto LABEL_59;
        }
      }
      else if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1456)) )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        {
          goto LABEL_56;
        }
        v14 = 269;
        goto LABEL_55;
      }
      v4 = 1;
      if ( (v10 & 2) != 0 || *(char *)(v9 + 144) < 0 )
        FveEowFinalSweepSelectAndConvertChunk(a1, &v18);
      else
        FveEowFinalSweepConvertSpecialRangesChunk(a1, &v20);
      if ( (*(_BYTE *)(v9 + 144) & 0x10) != 0 )
      {
        v7 = 0;
        v4 = 0;
        if ( *(_DWORD *)(a1 + 2328) == 1 )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2336) + 4LL));
        else
          _InterlockedIncrement((volatile signed __int32 *)(296LL * HIDWORD(KeGetPcr()[1].LockArray)
                                                          + *(_QWORD *)(a1 + 2336)
                                                          + 4));
      }
      goto LABEL_56;
    }
    if ( !v15 )
      goto LABEL_66;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    {
      goto LABEL_56;
    }
    v14 = 266;
    goto LABEL_55;
  }
LABEL_60:
  if ( v18 )
    FveQueueAutoWorkItem(a1, FveEowFinalSweepComplete, a1);
  if ( v20 )
    FveEowFinalSweepUpdate(a1);
  if ( v21 )
  {
    if ( v2 )
LABEL_66:
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
    FvepReleaseDevFveLock(v17);
  }
  if ( v4 )
  {
    if ( *(_BYTE *)(a1 + 1476) )
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 1448));
    else
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1456));
  }
  if ( v7 )
    FvepReleaseRemoveLock(a1 + 56);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 270, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids, v6);
  }
}

```

## disassembly

```asm
0x1400c0ec0  mov     [rsp+arg_8], dl
0x1400c0ec4  push    rbx
0x1400c0ec5  push    rbp
0x1400c0ec6  push    rsi
0x1400c0ec7  push    rdi
0x1400c0ec8  push    r12
0x1400c0eca  push    r13
0x1400c0ecc  push    r14
0x1400c0ece  push    r15
0x1400c0ed0  sub     rsp, 0D8h
0x1400c0ed7  mov     dil, dl
0x1400c0eda  mov     rbx, rcx
0x1400c0edd  xor     edx, edx; Val
0x1400c0edf  lea     rcx, [rsp+118h+var_D8]; void *
0x1400c0ee4  mov     r8d, 90h; Size
0x1400c0eea  call    memset
0x1400c0eef  xor     r12b, r12b
0x1400c0ef2  mov     [rsp+118h+arg_18], 0
0x1400c0efa  mov     [rsp+118h+arg_0], r12b
0x1400c0f02  mov     [rsp+118h+arg_10], r12b
0x1400c0f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0f11  lea     r15, WPP_GLOBAL_Control
0x1400c0f18  mov     ebp, 100h
0x1400c0f1d  cmp     rcx, r15
0x1400c0f20  jz      short loc_1400C0F40
0x1400c0f22  test    [rcx+2Ch], ebp
0x1400c0f25  jz      short loc_1400C0F40
0x1400c0f27  cmp     byte ptr [rcx+29h], 5
0x1400c0f2b  jb      short loc_1400C0F40
0x1400c0f2d  mov     rcx, [rcx+18h]
0x1400c0f31  lea     edx, [rbp+6]
0x1400c0f34  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c0f3b  call    WPP_SF_
0x1400c0f40  lea     rcx, [rbx+38h]; BugCheckParameter2
0x1400c0f44  call    FvepAcquireRemoveLock
0x1400c0f49  mov     [rsp+118h+var_E8], eax
0x1400c0f4d  mov     esi, eax
0x1400c0f4f  test    eax, eax
0x1400c0f51  jns     short loc_1400C0F93
0x1400c0f53  xor     r14b, r14b
0x1400c0f56  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0f5d  cmp     rcx, r15
0x1400c0f60  jz      loc_1400C127E
0x1400c0f66  test    [rcx+2Ch], ebp
0x1400c0f69  jz      loc_1400C127E
0x1400c0f6f  cmp     byte ptr [rcx+29h], 5
0x1400c0f73  jb      loc_1400C127E
0x1400c0f79  mov     rcx, [rcx+18h]
0x1400c0f7d  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c0f84  mov     edx, 107h
0x1400c0f89  call    WPP_SF_
0x1400c0f8e  jmp     loc_1400C127E
0x1400c0f93  mov     r14b, 1
0x1400c0f96  test    dil, dil
0x1400c0f99  jnz     short loc_1400C0FB3
0x1400c0f9b  mov     r8b, r14b
0x1400c0f9e  lea     rdx, [rsp+118h+var_D8]
0x1400c0fa3  mov     rcx, rbx
0x1400c0fa6  call    FvepAcquireDevFveLock
0x1400c0fab  mov     [rsp+118h+arg_18], r14b
0x1400c0fb3  test    [rbx+328h], ebp
0x1400c0fb9  jz      loc_1400C127E
0x1400c0fbf  mov     rdi, [rbx+2E0h]
0x1400c0fc6  test    rdi, rdi
0x1400c0fc9  jz      loc_1400C1276
0x1400c0fcf  mov     rdi, [rdi]
0x1400c0fd2  test    rdi, rdi
0x1400c0fd5  jz      loc_1400C1276
0x1400c0fdb  mov     sil, [rdi+30h]
0x1400c0fdf  lea     rcx, [rdi+58h]; Mutex
0x1400c0fe3  xor     bpl, bpl
0x1400c0fe6  call    cs:__imp_KeAcquireGuardedMutex
0x1400c0fed  nop     dword ptr [rax+rax+00h]
0x1400c0ff2  mov     al, [rdi+90h]
0x1400c0ff8  test    al, 4
0x1400c0ffa  jnz     loc_1400C108D
0x1400c1000  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1007  lea     rdx, WPP_GLOBAL_Control
0x1400c100e  cmp     rcx, rdx
0x1400c1011  jz      short loc_1400C103E
0x1400c1013  test    dword ptr [rcx+2Ch], 100h
0x1400c101a  jz      short loc_1400C103E
0x1400c101c  cmp     byte ptr [rcx+29h], 5
0x1400c1020  jb      short loc_1400C103E
0x1400c1022  mov     rcx, [rcx+18h]
0x1400c1026  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c102d  mov     edx, 108h
0x1400c1032  call    WPP_SF_
0x1400c1037  lea     rdx, WPP_GLOBAL_Control
0x1400c103e  mov     cl, [rdi+90h]
0x1400c1044  mov     al, cl
0x1400c1046  and     al, 38h
0x1400c1048  cmp     al, 8
0x1400c104a  jnz     loc_1400C123F
0x1400c1050  and     cl, 0F7h
0x1400c1053  mov     bpl, r14b
0x1400c1056  mov     [rdi+90h], cl
0x1400c105c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1063  cmp     rcx, rdx
0x1400c1066  jz      loc_1400C123F
0x1400c106c  test    dword ptr [rcx+2Ch], 100h
0x1400c1073  jz      loc_1400C123F
0x1400c1079  cmp     byte ptr [rcx+29h], 5
0x1400c107d  jb      loc_1400C123F
0x1400c1083  mov     edx, 109h
0x1400c1088  jmp     loc_1400C122F
0x1400c108d  mov     cl, al
0x1400c108f  and     cl, 8
0x1400c1092  test    al, 30h
0x1400c1094  jnz     loc_1400C1200
0x1400c109a  test    cl, cl
0x1400c109c  jnz     short loc_1400C10DD
0x1400c109e  or      al, 8
0x1400c10a0  mov     [rdi+90h], al
0x1400c10a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c10ad  lea     rax, WPP_GLOBAL_Control
0x1400c10b4  cmp     rcx, rax
0x1400c10b7  jz      short loc_1400C10DD
0x1400c10b9  test    dword ptr [rcx+2Ch], 100h
0x1400c10c0  jz      short loc_1400C10DD
0x1400c10c2  cmp     byte ptr [rcx+29h], 5
0x1400c10c6  jb      short loc_1400C10DD
0x1400c10c8  mov     rcx, [rcx+18h]
0x1400c10cc  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c10d3  mov     edx, 10Bh
0x1400c10d8  call    WPP_SF_
0x1400c10dd  cmp     [rbx+5C4h], bpl
0x1400c10e4  jz      short loc_1400C1139
0x1400c10e6  lea     rcx, [rbx+5A8h]; RunRef
0x1400c10ed  call    cs:__imp_ExAcquireRundownProtection
0x1400c10f4  nop     dword ptr [rax+rax+00h]
0x1400c10f9  test    al, al
0x1400c10fb  jnz     loc_1400C1188
0x1400c1101  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1108  lea     rax, WPP_GLOBAL_Control
0x1400c110f  cmp     rcx, rax
0x1400c1112  jz      loc_1400C123F
0x1400c1118  test    dword ptr [rcx+2Ch], 100h
0x1400c111f  jz      loc_1400C123F
0x1400c1125  cmp     byte ptr [rcx+29h], 5
0x1400c1129  jb      loc_1400C123F
0x1400c112f  mov     edx, 10Ch
0x1400c1134  jmp     loc_1400C122F
0x1400c1139  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400c1140  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400c1147  nop     dword ptr [rax+rax+00h]
0x1400c114c  test    al, al
0x1400c114e  jnz     short loc_1400C1188
0x1400c1150  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1157  lea     rax, WPP_GLOBAL_Control
0x1400c115e  cmp     rcx, rax
0x1400c1161  jz      loc_1400C123F
0x1400c1167  test    dword ptr [rcx+2Ch], 100h
0x1400c116e  jz      loc_1400C123F
0x1400c1174  cmp     byte ptr [rcx+29h], 5
0x1400c1178  jb      loc_1400C123F
0x1400c117e  mov     edx, 10Dh
0x1400c1183  jmp     loc_1400C122F
0x1400c1188  mov     r12b, r14b
0x1400c118b  test    sil, 2
0x1400c118f  jnz     short loc_1400C11AC
0x1400c1191  cmp     [rdi+90h], bpl
0x1400c1198  jl      short loc_1400C11AC
0x1400c119a  lea     rdx, [rsp+118h+arg_10]
0x1400c11a2  mov     rcx, rbx
0x1400c11a5  call    FveEowFinalSweepConvertSpecialRangesChunk
0x1400c11aa  jmp     short loc_1400C11BC
0x1400c11ac  lea     rdx, [rsp+118h+arg_0]
0x1400c11b4  mov     rcx, rbx
0x1400c11b7  call    FveEowFinalSweepSelectAndConvertChunk
0x1400c11bc  test    byte ptr [rdi+90h], 10h
0x1400c11c3  jz      short loc_1400C123F
0x1400c11c5  xor     r14b, r14b
0x1400c11c8  xor     r12b, r12b
0x1400c11cb  cmp     dword ptr [rbx+918h], 1
0x1400c11d2  jnz     short loc_1400C11E1
0x1400c11d4  mov     rax, [rbx+920h]
0x1400c11db  lock inc dword ptr [rax+4]
0x1400c11df  jmp     short loc_1400C123F
0x1400c11e1  mov     eax, gs:1A4h
0x1400c11e9  mov     ecx, eax
0x1400c11eb  mov     rax, [rbx+920h]
0x1400c11f2  imul    rdx, rcx, 128h
0x1400c11f9  lock inc dword ptr [rdx+rax+4]
0x1400c11fe  jmp     short loc_1400C123F
0x1400c1200  test    cl, cl
0x1400c1202  jz      loc_1400C12BB
0x1400c1208  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c120f  lea     rax, WPP_GLOBAL_Control
0x1400c1216  cmp     rcx, rax
0x1400c1219  jz      short loc_1400C123F
0x1400c121b  test    dword ptr [rcx+2Ch], 100h
0x1400c1222  jz      short loc_1400C123F
0x1400c1224  cmp     byte ptr [rcx+29h], 5
0x1400c1228  jb      short loc_1400C123F
0x1400c122a  mov     edx, 10Ah
0x1400c122f  mov     rcx, [rcx+18h]
0x1400c1233  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c123a  call    WPP_SF_
0x1400c123f  lea     rcx, [rdi+58h]; Mutex
0x1400c1243  call    cs:__imp_KeReleaseGuardedMutex
0x1400c124a  nop     dword ptr [rax+rax+00h]
0x1400c124f  test    bpl, bpl
0x1400c1252  jz      short loc_1400C1266
0x1400c1254  mov     r8, rbx
0x1400c1257  lea     rdx, FveEowResetConversionLogsWorker
0x1400c125e  mov     rcx, rbx
0x1400c1261  call    FveQueueAutoWorkItem
0x1400c1266  mov     esi, [rsp+118h+var_E8]
0x1400c126a  lea     r15, WPP_GLOBAL_Control
0x1400c1271  mov     ebp, 100h
0x1400c1276  mov     dil, [rsp+118h+arg_8]
0x1400c127e  cmp     [rsp+118h+arg_0], 0
0x1400c1286  jz      short loc_1400C129A
0x1400c1288  mov     r8, rbx
0x1400c128b  lea     rdx, FveEowFinalSweepComplete
0x1400c1292  mov     rcx, rbx
0x1400c1295  call    FveQueueAutoWorkItem
0x1400c129a  cmp     [rsp+118h+arg_10], 0
0x1400c12a2  jz      short loc_1400C12AC
0x1400c12a4  mov     rcx, rbx
0x1400c12a7  call    FveEowFinalSweepUpdate
0x1400c12ac  cmp     [rsp+118h+arg_18], 0
0x1400c12b4  jz      short loc_1400C12EA
0x1400c12b6  test    dil, dil
0x1400c12b9  jz      short loc_1400C12E0
0x1400c12bb  xor     r9d, r9d; BugCheckParameter3
0x1400c12be  mov     [rsp+118h+BugCheckParameter4], 0; BugCheckParameter4
0x1400c12c7  xor     r8d, r8d; BugCheckParameter2
0x1400c12ca  mov     ecx, 120h; BugCheckCode
0x1400c12cf  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400c12d3  call    cs:__imp_KeBugCheckEx
0x1400c12e0  lea     rcx, [rsp+118h+var_D8]
0x1400c12e5  call    FvepReleaseDevFveLock
0x1400c12ea  test    r12b, r12b
0x1400c12ed  jz      short loc_1400C1320
0x1400c12ef  cmp     byte ptr [rbx+5C4h], 0
0x1400c12f6  jz      short loc_1400C130D
0x1400c12f8  lea     rcx, [rbx+5A8h]; RunRef
0x1400c12ff  call    cs:__imp_ExReleaseRundownProtection
0x1400c1306  nop     dword ptr [rax+rax+00h]
0x1400c130b  jmp     short loc_1400C1320
0x1400c130d  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400c1314  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400c131b  nop     dword ptr [rax+rax+00h]
0x1400c1320  test    r14b, r14b
0x1400c1323  jz      short loc_1400C132E
0x1400c1325  lea     rcx, [rbx+38h]; BugCheckParameter2
0x1400c1329  call    FvepReleaseRemoveLock
0x1400c132e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1335  cmp     rcx, r15
0x1400c1338  jz      short loc_1400C135D
0x1400c133a  test    [rcx+2Ch], ebp
0x1400c133d  jz      short loc_1400C135D
0x1400c133f  cmp     byte ptr [rcx+29h], 5
0x1400c1343  jb      short loc_1400C135D
0x1400c1345  mov     rcx, [rcx+18h]
0x1400c1349  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c1350  mov     edx, 10Eh
0x1400c1355  mov     r9d, esi
0x1400c1358  call    WPP_SF_d
0x1400c135d  add     rsp, 0D8h
0x1400c1364  pop     r15
0x1400c1366  pop     r14
0x1400c1368  pop     r13
0x1400c136a  pop     r12
0x1400c136c  pop     rdi
0x1400c136d  pop     rsi
0x1400c136e  pop     rbp
0x1400c136f  pop     rbx
0x1400c1370  retn
```
