# FveEowFinalSweepConvertChunk

- ea: `0x1400c4930`
- end: `0x1400c4de2`
- name: `FveEowFinalSweepConvertChunk`
- size: `1202`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140098830`
- `0x1400e2390`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x14002aa38`
- `0x14002d500`
- `0x14002db80`
- `0x14007ed70`
- `0x1400c4930`
- `0x1400c4de8`
- `0x1400dce00`
- `0x1400dd144`
- `0x1400de048`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400c4bb0`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400c4bb0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400c4b5d`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400c4b5d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400c4d84`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400c4d84`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400c4d6f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400c4d6f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400c4a56`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400c4a56`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400c4cb3`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400c4cb3`
- `ntoskrnl!KeBugCheckEx` at `0x1400c4d43`
- `ntoskrnl!KeBugCheckEx` at `0x1400c4d43`

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
        if ( *(_DWORD *)(a1 + 2344) == 1 )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 2352) + 4LL));
        else
          _InterlockedIncrement((volatile signed __int32 *)(296LL * HIDWORD(KeGetPcr()[1].LockArray)
                                                          + *(_QWORD *)(a1 + 2352)
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
0x1400c4930  mov     [rsp+arg_8], dl
0x1400c4934  push    rbx
0x1400c4935  push    rbp
0x1400c4936  push    rsi
0x1400c4937  push    rdi
0x1400c4938  push    r12
0x1400c493a  push    r13
0x1400c493c  push    r14
0x1400c493e  push    r15
0x1400c4940  sub     rsp, 0D8h
0x1400c4947  mov     dil, dl
0x1400c494a  mov     rbx, rcx
0x1400c494d  xor     edx, edx; Val
0x1400c494f  lea     rcx, [rsp+118h+var_D8]; void *
0x1400c4954  mov     r8d, 90h; Size
0x1400c495a  call    memset
0x1400c495f  xor     r12b, r12b
0x1400c4962  mov     [rsp+118h+arg_18], 0
0x1400c496a  mov     [rsp+118h+arg_0], r12b
0x1400c4972  mov     [rsp+118h+arg_10], r12b
0x1400c497a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4981  lea     r15, WPP_GLOBAL_Control
0x1400c4988  mov     ebp, 100h
0x1400c498d  cmp     rcx, r15
0x1400c4990  jz      short loc_1400C49B0
0x1400c4992  test    [rcx+2Ch], ebp
0x1400c4995  jz      short loc_1400C49B0
0x1400c4997  cmp     byte ptr [rcx+29h], 5
0x1400c499b  jb      short loc_1400C49B0
0x1400c499d  mov     rcx, [rcx+18h]
0x1400c49a1  lea     edx, [rbp+6]
0x1400c49a4  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c49ab  call    WPP_SF_
0x1400c49b0  lea     rcx, [rbx+38h]; BugCheckParameter2
0x1400c49b4  call    FvepAcquireRemoveLock
0x1400c49b9  mov     [rsp+118h+var_E8], eax
0x1400c49bd  mov     esi, eax
0x1400c49bf  test    eax, eax
0x1400c49c1  jns     short loc_1400C4A03
0x1400c49c3  xor     r14b, r14b
0x1400c49c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c49cd  cmp     rcx, r15
0x1400c49d0  jz      loc_1400C4CEE
0x1400c49d6  test    [rcx+2Ch], ebp
0x1400c49d9  jz      loc_1400C4CEE
0x1400c49df  cmp     byte ptr [rcx+29h], 5
0x1400c49e3  jb      loc_1400C4CEE
0x1400c49e9  mov     rcx, [rcx+18h]
0x1400c49ed  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c49f4  mov     edx, 107h
0x1400c49f9  call    WPP_SF_
0x1400c49fe  jmp     loc_1400C4CEE
0x1400c4a03  mov     r14b, 1
0x1400c4a06  test    dil, dil
0x1400c4a09  jnz     short loc_1400C4A23
0x1400c4a0b  mov     r8b, r14b
0x1400c4a0e  lea     rdx, [rsp+118h+var_D8]
0x1400c4a13  mov     rcx, rbx
0x1400c4a16  call    FvepAcquireDevFveLock
0x1400c4a1b  mov     [rsp+118h+arg_18], r14b
0x1400c4a23  test    [rbx+328h], ebp
0x1400c4a29  jz      loc_1400C4CEE
0x1400c4a2f  mov     rdi, [rbx+2E0h]
0x1400c4a36  test    rdi, rdi
0x1400c4a39  jz      loc_1400C4CE6
0x1400c4a3f  mov     rdi, [rdi]
0x1400c4a42  test    rdi, rdi
0x1400c4a45  jz      loc_1400C4CE6
0x1400c4a4b  mov     sil, [rdi+30h]
0x1400c4a4f  lea     rcx, [rdi+58h]; Mutex
0x1400c4a53  xor     bpl, bpl
0x1400c4a56  call    cs:__imp_KeAcquireGuardedMutex
0x1400c4a5d  nop     dword ptr [rax+rax+00h]
0x1400c4a62  mov     al, [rdi+90h]
0x1400c4a68  test    al, 4
0x1400c4a6a  jnz     loc_1400C4AFD
0x1400c4a70  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4a77  lea     rdx, WPP_GLOBAL_Control
0x1400c4a7e  cmp     rcx, rdx
0x1400c4a81  jz      short loc_1400C4AAE
0x1400c4a83  test    dword ptr [rcx+2Ch], 100h
0x1400c4a8a  jz      short loc_1400C4AAE
0x1400c4a8c  cmp     byte ptr [rcx+29h], 5
0x1400c4a90  jb      short loc_1400C4AAE
0x1400c4a92  mov     rcx, [rcx+18h]
0x1400c4a96  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c4a9d  mov     edx, 108h
0x1400c4aa2  call    WPP_SF_
0x1400c4aa7  lea     rdx, WPP_GLOBAL_Control
0x1400c4aae  mov     cl, [rdi+90h]
0x1400c4ab4  mov     al, cl
0x1400c4ab6  and     al, 38h
0x1400c4ab8  cmp     al, 8
0x1400c4aba  jnz     loc_1400C4CAF
0x1400c4ac0  and     cl, 0F7h
0x1400c4ac3  mov     bpl, r14b
0x1400c4ac6  mov     [rdi+90h], cl
0x1400c4acc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4ad3  cmp     rcx, rdx
0x1400c4ad6  jz      loc_1400C4CAF
0x1400c4adc  test    dword ptr [rcx+2Ch], 100h
0x1400c4ae3  jz      loc_1400C4CAF
0x1400c4ae9  cmp     byte ptr [rcx+29h], 5
0x1400c4aed  jb      loc_1400C4CAF
0x1400c4af3  mov     edx, 109h
0x1400c4af8  jmp     loc_1400C4C9F
0x1400c4afd  mov     cl, al
0x1400c4aff  and     cl, 8
0x1400c4b02  test    al, 30h
0x1400c4b04  jnz     loc_1400C4C70
0x1400c4b0a  test    cl, cl
0x1400c4b0c  jnz     short loc_1400C4B4D
0x1400c4b0e  or      al, 8
0x1400c4b10  mov     [rdi+90h], al
0x1400c4b16  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4b1d  lea     rax, WPP_GLOBAL_Control
0x1400c4b24  cmp     rcx, rax
0x1400c4b27  jz      short loc_1400C4B4D
0x1400c4b29  test    dword ptr [rcx+2Ch], 100h
0x1400c4b30  jz      short loc_1400C4B4D
0x1400c4b32  cmp     byte ptr [rcx+29h], 5
0x1400c4b36  jb      short loc_1400C4B4D
0x1400c4b38  mov     rcx, [rcx+18h]
0x1400c4b3c  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c4b43  mov     edx, 10Bh
0x1400c4b48  call    WPP_SF_
0x1400c4b4d  cmp     [rbx+5C4h], bpl
0x1400c4b54  jz      short loc_1400C4BA9
0x1400c4b56  lea     rcx, [rbx+5A8h]; RunRef
0x1400c4b5d  call    cs:__imp_ExAcquireRundownProtection
0x1400c4b64  nop     dword ptr [rax+rax+00h]
0x1400c4b69  test    al, al
0x1400c4b6b  jnz     loc_1400C4BF8
0x1400c4b71  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4b78  lea     rax, WPP_GLOBAL_Control
0x1400c4b7f  cmp     rcx, rax
0x1400c4b82  jz      loc_1400C4CAF
0x1400c4b88  test    dword ptr [rcx+2Ch], 100h
0x1400c4b8f  jz      loc_1400C4CAF
0x1400c4b95  cmp     byte ptr [rcx+29h], 5
0x1400c4b99  jb      loc_1400C4CAF
0x1400c4b9f  mov     edx, 10Ch
0x1400c4ba4  jmp     loc_1400C4C9F
0x1400c4ba9  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400c4bb0  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400c4bb7  nop     dword ptr [rax+rax+00h]
0x1400c4bbc  test    al, al
0x1400c4bbe  jnz     short loc_1400C4BF8
0x1400c4bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4bc7  lea     rax, WPP_GLOBAL_Control
0x1400c4bce  cmp     rcx, rax
0x1400c4bd1  jz      loc_1400C4CAF
0x1400c4bd7  test    dword ptr [rcx+2Ch], 100h
0x1400c4bde  jz      loc_1400C4CAF
0x1400c4be4  cmp     byte ptr [rcx+29h], 5
0x1400c4be8  jb      loc_1400C4CAF
0x1400c4bee  mov     edx, 10Dh
0x1400c4bf3  jmp     loc_1400C4C9F
0x1400c4bf8  mov     r12b, r14b
0x1400c4bfb  test    sil, 2
0x1400c4bff  jnz     short loc_1400C4C1C
0x1400c4c01  cmp     [rdi+90h], bpl
0x1400c4c08  jl      short loc_1400C4C1C
0x1400c4c0a  lea     rdx, [rsp+118h+arg_10]
0x1400c4c12  mov     rcx, rbx
0x1400c4c15  call    FveEowFinalSweepConvertSpecialRangesChunk
0x1400c4c1a  jmp     short loc_1400C4C2C
0x1400c4c1c  lea     rdx, [rsp+118h+arg_0]
0x1400c4c24  mov     rcx, rbx
0x1400c4c27  call    FveEowFinalSweepSelectAndConvertChunk
0x1400c4c2c  test    byte ptr [rdi+90h], 10h
0x1400c4c33  jz      short loc_1400C4CAF
0x1400c4c35  xor     r14b, r14b
0x1400c4c38  xor     r12b, r12b
0x1400c4c3b  cmp     dword ptr [rbx+928h], 1
0x1400c4c42  jnz     short loc_1400C4C51
0x1400c4c44  mov     rax, [rbx+930h]
0x1400c4c4b  lock inc dword ptr [rax+4]
0x1400c4c4f  jmp     short loc_1400C4CAF
0x1400c4c51  mov     eax, gs:1A4h
0x1400c4c59  mov     ecx, eax
0x1400c4c5b  mov     rax, [rbx+930h]
0x1400c4c62  imul    rdx, rcx, 128h
0x1400c4c69  lock inc dword ptr [rdx+rax+4]
0x1400c4c6e  jmp     short loc_1400C4CAF
0x1400c4c70  test    cl, cl
0x1400c4c72  jz      loc_1400C4D2B
0x1400c4c78  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4c7f  lea     rax, WPP_GLOBAL_Control
0x1400c4c86  cmp     rcx, rax
0x1400c4c89  jz      short loc_1400C4CAF
0x1400c4c8b  test    dword ptr [rcx+2Ch], 100h
0x1400c4c92  jz      short loc_1400C4CAF
0x1400c4c94  cmp     byte ptr [rcx+29h], 5
0x1400c4c98  jb      short loc_1400C4CAF
0x1400c4c9a  mov     edx, 10Ah
0x1400c4c9f  mov     rcx, [rcx+18h]
0x1400c4ca3  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c4caa  call    WPP_SF_
0x1400c4caf  lea     rcx, [rdi+58h]; Mutex
0x1400c4cb3  call    cs:__imp_KeReleaseGuardedMutex
0x1400c4cba  nop     dword ptr [rax+rax+00h]
0x1400c4cbf  test    bpl, bpl
0x1400c4cc2  jz      short loc_1400C4CD6
0x1400c4cc4  mov     r8, rbx
0x1400c4cc7  lea     rdx, FveEowResetConversionLogsWorker
0x1400c4cce  mov     rcx, rbx
0x1400c4cd1  call    FveQueueAutoWorkItem
0x1400c4cd6  mov     esi, [rsp+118h+var_E8]
0x1400c4cda  lea     r15, WPP_GLOBAL_Control
0x1400c4ce1  mov     ebp, 100h
0x1400c4ce6  mov     dil, [rsp+118h+arg_8]
0x1400c4cee  cmp     [rsp+118h+arg_0], 0
0x1400c4cf6  jz      short loc_1400C4D0A
0x1400c4cf8  mov     r8, rbx
0x1400c4cfb  lea     rdx, FveEowFinalSweepComplete
0x1400c4d02  mov     rcx, rbx
0x1400c4d05  call    FveQueueAutoWorkItem
0x1400c4d0a  cmp     [rsp+118h+arg_10], 0
0x1400c4d12  jz      short loc_1400C4D1C
0x1400c4d14  mov     rcx, rbx
0x1400c4d17  call    FveEowFinalSweepUpdate
0x1400c4d1c  cmp     [rsp+118h+arg_18], 0
0x1400c4d24  jz      short loc_1400C4D5A
0x1400c4d26  test    dil, dil
0x1400c4d29  jz      short loc_1400C4D50
0x1400c4d2b  xor     r9d, r9d; BugCheckParameter3
0x1400c4d2e  mov     [rsp+118h+BugCheckParameter4], 0; BugCheckParameter4
0x1400c4d37  xor     r8d, r8d; BugCheckParameter2
0x1400c4d3a  mov     ecx, 120h; BugCheckCode
0x1400c4d3f  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400c4d43  call    cs:__imp_KeBugCheckEx
0x1400c4d50  lea     rcx, [rsp+118h+var_D8]
0x1400c4d55  call    FvepReleaseDevFveLock
0x1400c4d5a  test    r12b, r12b
0x1400c4d5d  jz      short loc_1400C4D90
0x1400c4d5f  cmp     byte ptr [rbx+5C4h], 0
0x1400c4d66  jz      short loc_1400C4D7D
0x1400c4d68  lea     rcx, [rbx+5A8h]; RunRef
0x1400c4d6f  call    cs:__imp_ExReleaseRundownProtection
0x1400c4d76  nop     dword ptr [rax+rax+00h]
0x1400c4d7b  jmp     short loc_1400C4D90
0x1400c4d7d  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400c4d84  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400c4d8b  nop     dword ptr [rax+rax+00h]
0x1400c4d90  test    r14b, r14b
0x1400c4d93  jz      short loc_1400C4D9E
0x1400c4d95  lea     rcx, [rbx+38h]; BugCheckParameter2
0x1400c4d99  call    FvepReleaseRemoveLock
0x1400c4d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4da5  cmp     rcx, r15
0x1400c4da8  jz      short loc_1400C4DCD
0x1400c4daa  test    [rcx+2Ch], ebp
0x1400c4dad  jz      short loc_1400C4DCD
0x1400c4daf  cmp     byte ptr [rcx+29h], 5
0x1400c4db3  jb      short loc_1400C4DCD
0x1400c4db5  mov     rcx, [rcx+18h]
0x1400c4db9  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c4dc0  mov     edx, 10Eh
0x1400c4dc5  mov     r9d, esi
0x1400c4dc8  call    WPP_SF_d
0x1400c4dcd  add     rsp, 0D8h
0x1400c4dd4  pop     r15
0x1400c4dd6  pop     r14
0x1400c4dd8  pop     r13
0x1400c4dda  pop     r12
0x1400c4ddc  pop     rdi
0x1400c4ddd  pop     rsi
0x1400c4dde  pop     rbp
0x1400c4ddf  pop     rbx
0x1400c4de0  retn
```
