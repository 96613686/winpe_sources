# UlFastReceiveHttpRequest

- ea: `0x1c00a3c00`
- end: `0x1c00a3f5b`
- name: `UlFastReceiveHttpRequest`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1c00a3800`

## callees

- `0x1c0001760`
- `0x1c000a0d0`
- `0x1c000fc68`
- `0x1c00298a0`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c008f7c0`
- `0x1c008f9bc`
- `0x1c008fb48`
- `0x1c008fc24`
- `0x1c00910e8`
- `0x1c00a3c00`
- `0x1c00b2b20`

## import_xrefs

- `ntoskrnl!ZwYieldExecution` at `0x1c00a3cca`
- `ntoskrnl!ZwYieldExecution` at `0x1c00a3cca`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a3d1c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a3efb`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a3d1c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a3efb`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00a3ceb`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00a3ceb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00a3c7d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00a3c7d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a3eb5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a3ede`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00de748`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00de771`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a3eb5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a3ede`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00de748`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00de771`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a3d8d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a3dba`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a3d8d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a3dba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a3d28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a3ec1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a3eea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a3f07`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00de754`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00de77d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a3d28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a3ec1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a3eea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a3f07`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00de754`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00de77d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a3cd6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a3d70`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a3d99`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a3cd6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a3d70`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a3d99`

## pseudocode

```c
__int64 __fastcall UlFastReceiveHttpRequest(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  __int64 v6; // rsi
  USHORT CurrentNodeNumber; // bx
  int v8; // r13d
  int v10; // r12d
  unsigned int *v12; // r14
  unsigned __int8 v13; // r15
  _QWORD *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rbx
  __int64 v18; // rdx
  char v19; // cl
  __int64 v20; // rbp
  int v21; // r8d
  _QWORD *v22; // rcx
  _QWORD *v23; // r8
  int v24; // ecx
  __int64 RequestFromId; // rax
  __int64 v26; // [rsp+50h] [rbp-38h]
  __int64 v27; // [rsp+A0h] [rbp+18h] BYREF

  v6 = *(_QWORD *)(a3 + 8);
  CurrentNodeNumber = 0;
  v27 = 0;
  v8 = a4;
  v10 = a2;
  v12 = (unsigned int *)a6;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_iLqqLq(a1, a2, a1, (unsigned int)a2, a3, a4, a5, a6);
  v13 = 0;
  *v12 = 0;
  *((_QWORD *)v12 + 1) = 0;
  if ( *(_DWORD *)(a3 + 40) == 4 && v10 )
    goto LABEL_17;
  if ( !a1 )
  {
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_(16, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
    if ( (unsigned __int16)UlNumberOfLanes > 1u )
      CurrentNodeNumber = KeGetCurrentNodeNumber();
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_D(17, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
    v14 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 8LL * CurrentNodeNumber) + 16LL);
    if ( (_QWORD *)*v14 == v14 )
    {
      v15 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 288) + 8LL * CurrentNodeNumber) + 80LL);
      if ( (_QWORD *)*v15 == v15 )
        ZwYieldExecution();
    }
    KeEnterCriticalRegion();
    v16 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v6 + 280), 0);
    if ( *(_BYTE *)(a3 + 4) || (int)UlpTryRetrieveRequest(v6, a3, &v27) < 0 )
    {
LABEL_16:
      ExReleaseCacheAwarePushLockSharedEx(v16, 0);
      KeLeaveCriticalRegion();
      goto LABEL_17;
    }
    while ( 1 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v27 + 1688, 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(*(_QWORD *)(v27 + 1696) + 56LL, 0);
      v18 = v27;
      v19 = 0;
      v26 = v27;
      LOBYTE(a6) = 0;
      v20 = *(_QWORD *)(v27 + 1696);
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      {
        WPP_SF_qqqL(176, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v27, *(_QWORD *)(v27 + 64), a3, 1);
        v18 = v26;
        v19 = 0;
      }
      if ( *(_BYTE *)(v20 + 64) && (*(_DWORD *)&WPP_MAIN_CB.StackSize & 0x200000) != 0 )
      {
        WPP_SF_qLLqqZq(
          *(_QWORD *)(a3 + 8),
          v18,
          v18,
          *(_DWORD *)(v18 + 1720),
          *(_DWORD *)(v18 + 1724),
          a3,
          *(_QWORD *)(a3 + 8),
          *(_QWORD *)(a3 + 8) + 152LL,
          v20);
        v18 = v26;
        v19 = 0;
      }
      v21 = *(_DWORD *)(v18 + 1720);
      if ( v21 == 1 )
        break;
      if ( (*(_DWORD *)&WPP_MAIN_CB.StackSize & 0x200000) != 0 )
      {
        WPP_SF_qqqZqL(*(_QWORD *)(a3 + 8), v18, v18, a3, *(_QWORD *)(a3 + 8), *(_QWORD *)(a3 + 8) + 152LL, v20, v21);
        v19 = 0;
      }
LABEL_31:
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      {
        WPP_SF_D(179, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
        v19 = a6;
      }
      if ( v19 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v27 + 48));
        ExReleasePushLockExclusiveEx(*(_QWORD *)(v27 + 1696) + 56LL, 0);
        KeLeaveCriticalRegion();
        ExReleasePushLockExclusiveEx(v27 + 1688, 0);
        KeLeaveCriticalRegion();
        ExReleaseCacheAwarePushLockSharedEx(v16, 0);
        KeLeaveCriticalRegion();
        v13 = 1;
        UlCopyRequestToBuffer(v27, v8, v10, (__int64)v12);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 48), 0xFFFFFFFF) == 1 )
          goto LABEL_40;
        goto LABEL_17;
      }
      ExReleasePushLockExclusiveEx(*(_QWORD *)(v27 + 1696) + 56LL, 0);
      KeLeaveCriticalRegion();
      ExReleasePushLockExclusiveEx(v27 + 1688, 0);
      KeLeaveCriticalRegion();
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 48), 0xFFFFFFFF) == 1 )
        UlpQueueFreeHttpRequest(v27);
      if ( (int)UlpTryRetrieveRequest(v6, a3, &v27) < 0 )
        goto LABEL_16;
    }
    UlStopRequestQueueTimer(v18);
    *(_DWORD *)(v26 + 1720) = 2;
    v22 = (_QWORD *)(v26 + 1704);
    v23 = *(_QWORD **)(v20 + 88);
    if ( *v23 != v20 + 80 )
      __fastfail(3u);
    *v22 = v20 + 80;
    *(_QWORD *)(v26 + 1712) = v23;
    *v23 = v22;
    *(_QWORD *)(v20 + 88) = v22;
    v24 = *(_DWORD *)(a3 + 40);
    if ( v24 == 1 )
    {
      if ( *(_QWORD *)(v20 + 72) )
      {
LABEL_30:
        *(_QWORD *)(v26 + 1728) = a3;
        _InterlockedIncrement((volatile signed __int32 *)a3);
        v19 = 1;
        LOBYTE(a6) = 1;
        goto LABEL_31;
      }
      *(_QWORD *)(v20 + 72) = a3;
      _InterlockedIncrement((volatile signed __int32 *)a3);
      v24 = *(_DWORD *)(a3 + 40);
    }
    if ( v24 == 4 )
      *(_BYTE *)(v26 + 1837) = 1;
    goto LABEL_30;
  }
  RequestFromId = UlGetRequestFromId(a1, a3);
  v27 = RequestFromId;
  if ( RequestFromId )
  {
    UlStopRequestQueueTimer(RequestFromId);
    v13 = 1;
    UlCopyRequestToBuffer(v27, v8, v10, (__int64)v12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 48), 0xFFFFFFFF) == 1 )
LABEL_40:
      UlpQueueFreeHttpRequest(v27);
  }
LABEL_17:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_dl(LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink), a2, *v12, v13);
  return v13;
}

```

## disassembly

```asm
0x1c00a3c00  mov     rax, rsp
0x1c00a3c03  mov     [rax+8], rbx
0x1c00a3c07  mov     [rax+10h], rbp
0x1c00a3c0b  mov     [rax+20h], rsi
0x1c00a3c0f  push    rdi
0x1c00a3c10  push    r12
0x1c00a3c12  push    r13
0x1c00a3c14  push    r14
0x1c00a3c16  push    r15
0x1c00a3c18  sub     rsp, 60h
0x1c00a3c1c  mov     rsi, [r8+8]
0x1c00a3c20  xor     ebx, ebx
0x1c00a3c22  mov     [rax+18h], rbx
0x1c00a3c26  mov     r13, r9
0x1c00a3c29  mov     rdi, r8
0x1c00a3c2c  mov     r12d, edx
0x1c00a3c2f  mov     rbp, rcx
0x1c00a3c32  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a3c38  mov     r14, [rsp+88h+arg_28]
0x1c00a3c40  test    al, al
0x1c00a3c42  js      loc_1C00DE55E
0x1c00a3c48  xor     r15b, r15b
0x1c00a3c4b  mov     [r14], ebx
0x1c00a3c4e  mov     [r14+8], rbx
0x1c00a3c52  cmp     dword ptr [rdi+28h], 4
0x1c00a3c56  jz      loc_1C00DE589
0x1c00a3c5c  test    rbp, rbp
0x1c00a3c5f  jnz     loc_1C00DE597
0x1c00a3c65  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a3c6b  test    al, al
0x1c00a3c6d  js      loc_1C00DE611
0x1c00a3c73  cmp     cs:UlNumberOfLanes, 1
0x1c00a3c7b  jbe     short loc_1C00A3C8C
0x1c00a3c7d  call    cs:__imp_KeGetCurrentNodeNumber
0x1c00a3c84  nop     dword ptr [rax+rax+00h]
0x1c00a3c89  movzx   ebx, ax
0x1c00a3c8c  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a3c92  test    al, al
0x1c00a3c94  js      loc_1C00DE628
0x1c00a3c9a  movzx   eax, bx
0x1c00a3c9d  lea     rdx, ds:0[rax*8]
0x1c00a3ca5  mov     rax, [rdi+10h]
0x1c00a3ca9  mov     rcx, [rax+rdx]
0x1c00a3cad  add     rcx, 10h
0x1c00a3cb1  cmp     [rcx], rcx
0x1c00a3cb4  jnz     short loc_1C00A3CD6
0x1c00a3cb6  mov     rax, [rsi+120h]
0x1c00a3cbd  mov     rcx, [rax+rdx]
0x1c00a3cc1  add     rcx, 50h ; 'P'
0x1c00a3cc5  cmp     [rcx], rcx
0x1c00a3cc8  jnz     short loc_1C00A3CD6
0x1c00a3cca  call    cs:__imp_ZwYieldExecution
0x1c00a3cd1  nop     dword ptr [rax+rax+00h]
0x1c00a3cd6  call    cs:__imp_KeEnterCriticalRegion
0x1c00a3cdd  nop     dword ptr [rax+rax+00h]
0x1c00a3ce2  mov     rcx, [rsi+118h]
0x1c00a3ce9  xor     edx, edx
0x1c00a3ceb  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c00a3cf2  nop     dword ptr [rax+rax+00h]
0x1c00a3cf7  mov     rbx, rax
0x1c00a3cfa  cmp     [rdi+4], r15b
0x1c00a3cfe  jnz     short loc_1C00A3D17
0x1c00a3d00  lea     r8, [rsp+88h+arg_10]
0x1c00a3d08  mov     rdx, rdi
0x1c00a3d0b  mov     rcx, rsi
0x1c00a3d0e  call    UlpTryRetrieveRequest
0x1c00a3d13  test    eax, eax
0x1c00a3d15  jns     short loc_1C00A3D70
0x1c00a3d17  xor     edx, edx
0x1c00a3d19  mov     rcx, rbx
0x1c00a3d1c  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00a3d23  nop     dword ptr [rax+rax+00h]
0x1c00a3d28  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a3d2f  nop     dword ptr [rax+rax+00h]
0x1c00a3d34  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a3d3a  test    cl, cl
0x1c00a3d3c  js      loc_1C00DE7E7
0x1c00a3d42  lea     r11, [rsp+88h+var_28]
0x1c00a3d47  movzx   eax, r15b
0x1c00a3d4b  mov     rbx, [r11+30h]
0x1c00a3d4f  mov     rbp, [r11+38h]
0x1c00a3d53  mov     rsi, [r11+48h]
0x1c00a3d57  mov     rsp, r11
0x1c00a3d5a  pop     r15
0x1c00a3d5c  pop     r14
0x1c00a3d5e  pop     r13
0x1c00a3d60  pop     r12
0x1c00a3d62  pop     rdi
0x1c00a3d63  retn
0x1c00a3d70  call    cs:__imp_KeEnterCriticalRegion
0x1c00a3d77  nop     dword ptr [rax+rax+00h]
0x1c00a3d7c  mov     rcx, [rsp+88h+arg_10]
0x1c00a3d84  xor     edx, edx
0x1c00a3d86  add     rcx, 698h
0x1c00a3d8d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00a3d94  nop     dword ptr [rax+rax+00h]
0x1c00a3d99  call    cs:__imp_KeEnterCriticalRegion
0x1c00a3da0  nop     dword ptr [rax+rax+00h]
0x1c00a3da5  mov     rax, [rsp+88h+arg_10]
0x1c00a3dad  xor     edx, edx
0x1c00a3daf  mov     rcx, [rax+6A0h]
0x1c00a3db6  add     rcx, 38h ; '8'
0x1c00a3dba  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00a3dc1  nop     dword ptr [rax+rax+00h]
0x1c00a3dc6  mov     rdx, [rsp+88h+arg_10]
0x1c00a3dce  xor     cl, cl
0x1c00a3dd0  mov     [rsp+88h+var_38], rdx
0x1c00a3dd5  mov     byte ptr [rsp+88h+arg_28], cl
0x1c00a3ddc  mov     rbp, [rdx+6A0h]
0x1c00a3de3  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a3de9  test    al, al
0x1c00a3deb  js      loc_1C00DE643
0x1c00a3df1  cmp     [rbp+40h], r15b
0x1c00a3df5  jnz     loc_1C00DE676
0x1c00a3dfb  mov     r8d, [rdx+6B8h]
0x1c00a3e02  cmp     r8d, 1
0x1c00a3e06  jnz     loc_1C00DE6CC
0x1c00a3e0c  mov     rcx, rdx
0x1c00a3e0f  call    UlStopRequestQueueTimer
0x1c00a3e14  mov     rax, [rsp+88h+var_38]
0x1c00a3e19  lea     rdx, [rbp+50h]
0x1c00a3e1d  mov     dword ptr [rax+6B8h], 2
0x1c00a3e27  lea     rcx, [rax+6A8h]
0x1c00a3e2e  mov     r8, [rdx+8]
0x1c00a3e32  cmp     [r8], rdx
0x1c00a3e35  jnz     loc_1C00DE7E0
0x1c00a3e3b  mov     [rcx], rdx
0x1c00a3e3e  mov     [rcx+8], r8
0x1c00a3e42  mov     [r8], rcx
0x1c00a3e45  mov     [rdx+8], rcx
0x1c00a3e49  mov     ecx, [rdi+28h]
0x1c00a3e4c  cmp     ecx, 1
0x1c00a3e4f  jnz     short loc_1C00A3E62
0x1c00a3e51  cmp     qword ptr [rbp+48h], 0
0x1c00a3e56  jnz     short loc_1C00A3E6B
0x1c00a3e58  mov     [rbp+48h], rdi
0x1c00a3e5c  lock inc dword ptr [rdi]
0x1c00a3e5f  mov     ecx, [rdi+28h]
0x1c00a3e62  cmp     ecx, 4
0x1c00a3e65  jz      loc_1C00DE70F
0x1c00a3e6b  mov     [rax+6C0h], rdi
0x1c00a3e72  lock inc dword ptr [rdi]
0x1c00a3e75  mov     cl, 1
0x1c00a3e77  mov     byte ptr [rsp+88h+arg_28], cl
0x1c00a3e7e  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a3e84  test    al, al
0x1c00a3e86  js      loc_1C00DE71B
0x1c00a3e8c  mov     rax, [rsp+88h+arg_10]
0x1c00a3e94  xor     edx, edx
0x1c00a3e96  test    cl, cl
0x1c00a3e98  jz      loc_1C00DE73D
0x1c00a3e9e  lock inc dword ptr [rax+30h]
0x1c00a3ea2  mov     rax, [rsp+88h+arg_10]
0x1c00a3eaa  mov     rcx, [rax+6A0h]
0x1c00a3eb1  add     rcx, 38h ; '8'
0x1c00a3eb5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00a3ebc  nop     dword ptr [rax+rax+00h]
0x1c00a3ec1  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a3ec8  nop     dword ptr [rax+rax+00h]
0x1c00a3ecd  mov     rcx, [rsp+88h+arg_10]
0x1c00a3ed5  xor     edx, edx
0x1c00a3ed7  add     rcx, 698h
0x1c00a3ede  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00a3ee5  nop     dword ptr [rax+rax+00h]
0x1c00a3eea  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a3ef1  nop     dword ptr [rax+rax+00h]
0x1c00a3ef6  xor     edx, edx
0x1c00a3ef8  mov     rcx, rbx
0x1c00a3efb  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00a3f02  nop     dword ptr [rax+rax+00h]
0x1c00a3f07  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a3f0e  nop     dword ptr [rax+rax+00h]
0x1c00a3f13  mov     r8d, [rsp+88h+arg_20]
0x1c00a3f1b  mov     r9, rdi
0x1c00a3f1e  mov     rcx, [rsp+88h+arg_10]; int
0x1c00a3f26  mov     rdx, r13; int
0x1c00a3f29  mov     [rsp+88h+var_60], r14; __int64
0x1c00a3f2e  mov     r15b, 1
0x1c00a3f31  mov     [rsp+88h+var_68], r12d; int
0x1c00a3f36  call    UlCopyRequestToBuffer
0x1c00a3f3b  mov     rax, [rsp+88h+arg_10]
0x1c00a3f43  mov     ecx, 0FFFFFFFFh
0x1c00a3f48  lock xadd [rax+30h], ecx
0x1c00a3f4d  cmp     ecx, 1
0x1c00a3f50  jnz     loc_1C00A3D34
0x1c00a3f56  jmp     loc_1C00DE7CD
0x1c00de55e  mov     eax, [rsp+88h+arg_20]
0x1c00de565  mov     r9d, r12d
0x1c00de568  mov     [rsp+88h+var_50], r14
0x1c00de56d  mov     r8, rbp
0x1c00de570  mov     dword ptr [rsp+88h+var_58], eax
0x1c00de574  mov     [rsp+88h+var_60], r13
0x1c00de579  mov     qword ptr [rsp+88h+var_68], rdi
0x1c00de57e  call    WPP_SF_iLqqLq
0x1c00de583  nop
0x1c00de584  jmp     loc_1C00A3C48
0x1c00de589  test    r12d, r12d
0x1c00de58c  jnz     loc_1C00A3D34
0x1c00de592  jmp     loc_1C00A3C5C
0x1c00de597  mov     rdx, rdi
0x1c00de59a  mov     rcx, rbp
0x1c00de59d  call    UlGetRequestFromId
0x1c00de5a2  mov     [rsp+88h+arg_10], rax
0x1c00de5aa  test    rax, rax
0x1c00de5ad  jz      loc_1C00A3D34
0x1c00de5b3  mov     rcx, rax
0x1c00de5b6  call    UlStopRequestQueueTimer
0x1c00de5bb  mov     r8d, [rsp+88h+arg_20]
0x1c00de5c3  mov     r9, rdi
0x1c00de5c6  mov     rcx, [rsp+88h+arg_10]; int
0x1c00de5ce  mov     rdx, r13; int
0x1c00de5d1  mov     [rsp+88h+var_60], r14; __int64
0x1c00de5d6  mov     r15b, 1
0x1c00de5d9  mov     [rsp+88h+var_68], r12d; int
0x1c00de5de  call    UlCopyRequestToBuffer
0x1c00de5e3  mov     rax, [rsp+88h+arg_10]
0x1c00de5eb  mov     ecx, 0FFFFFFFFh
0x1c00de5f0  lock xadd [rax+30h], ecx
0x1c00de5f5  cmp     ecx, 1
0x1c00de5f8  jnz     loc_1C00A3D34
0x1c00de5fe  mov     rcx, [rsp+88h+arg_10]
0x1c00de606  call    UlpQueueFreeHttpRequest
0x1c00de60b  nop
0x1c00de60c  jmp     loc_1C00A3D34
0x1c00de611  mov     ecx, 10h
0x1c00de616  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00de61d  call    WPP_SF_
0x1c00de622  nop
0x1c00de623  jmp     loc_1C00A3C73
0x1c00de628  movzx   r8d, bx
0x1c00de62c  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00de633  mov     ecx, 11h
0x1c00de638  call    WPP_SF_D
0x1c00de63d  nop
0x1c00de63e  jmp     loc_1C00A3C9A
0x1c00de643  mov     r9, [rdx+40h]
0x1c00de647  mov     r8, rdx
0x1c00de64a  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00de651  mov     dword ptr [rsp+88h+var_60], 1
0x1c00de659  mov     ecx, 0B0h
0x1c00de65e  mov     qword ptr [rsp+88h+var_68], rdi
0x1c00de663  call    WPP_SF_qqqL
0x1c00de668  mov     rdx, [rsp+88h+var_38]
0x1c00de66d  movzx   ecx, r15b
0x1c00de671  jmp     loc_1C00A3DF1
0x1c00de676  test    dword ptr cs:WPP_MAIN_CB.StackSize, 200000h
0x1c00de680  jz      loc_1C00A3DFB
0x1c00de686  mov     rcx, [rdi+8]
0x1c00de68a  mov     r8, rdx
0x1c00de68d  mov     r9d, [rdx+6B8h]
0x1c00de694  mov     [rsp+88h+var_48], rbp
0x1c00de699  lea     rax, [rcx+98h]
0x1c00de6a0  mov     [rsp+88h+var_50], rax
0x1c00de6a5  mov     eax, [rdx+6BCh]
0x1c00de6ab  mov     [rsp+88h+var_58], rcx
0x1c00de6b0  mov     [rsp+88h+var_60], rdi
0x1c00de6b5  mov     [rsp+88h+var_68], eax
0x1c00de6b9  call    WPP_SF_qLLqqZq
0x1c00de6be  mov     rdx, [rsp+88h+var_38]
0x1c00de6c3  movzx   ecx, r15b
0x1c00de6c7  jmp     loc_1C00A3DFB
0x1c00de6cc  test    dword ptr cs:WPP_MAIN_CB.StackSize, 200000h
0x1c00de6d6  jz      loc_1C00A3E7E
0x1c00de6dc  mov     rcx, [rdi+8]
0x1c00de6e0  mov     r9, rdi
0x1c00de6e3  mov     dword ptr [rsp+88h+var_50], r8d
0x1c00de6e8  mov     r8, rdx
0x1c00de6eb  mov     [rsp+88h+var_58], rbp
0x1c00de6f0  lea     rax, [rcx+98h]
0x1c00de6f7  mov     [rsp+88h+var_60], rax
0x1c00de6fc  mov     qword ptr [rsp+88h+var_68], rcx
0x1c00de701  call    WPP_SF_qqqZqL
0x1c00de706  movzx   ecx, r15b
0x1c00de70a  jmp     loc_1C00A3E7E
0x1c00de70f  mov     byte ptr [rax+72Dh], 1
0x1c00de716  jmp     loc_1C00A3E6B
0x1c00de71b  movzx   r8d, cl
0x1c00de71f  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00de726  mov     ecx, 0B3h
0x1c00de72b  call    WPP_SF_D
0x1c00de730  movzx   ecx, byte ptr [rsp+88h+arg_28]
0x1c00de738  jmp     loc_1C00A3E8C
0x1c00de73d  mov     rcx, [rax+6A0h]
0x1c00de744  add     rcx, 38h ; '8'
0x1c00de748  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00de74f  nop     dword ptr [rax+rax+00h]
0x1c00de754  call    cs:__imp_KeLeaveCriticalRegion
0x1c00de75b  nop     dword ptr [rax+rax+00h]
0x1c00de760  mov     rcx, [rsp+88h+arg_10]
0x1c00de768  xor     edx, edx
0x1c00de76a  add     rcx, 698h
0x1c00de771  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00de778  nop     dword ptr [rax+rax+00h]
0x1c00de77d  call    cs:__imp_KeLeaveCriticalRegion
0x1c00de784  nop     dword ptr [rax+rax+00h]
0x1c00de789  mov     rcx, [rsp+88h+arg_10]
0x1c00de791  mov     eax, 0FFFFFFFFh
0x1c00de796  lock xadd [rcx+30h], eax
0x1c00de79b  cmp     eax, 1
0x1c00de79e  jnz     short loc_1C00DE7AD
  ... truncated ...
```
