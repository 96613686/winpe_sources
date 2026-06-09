# UlUnlinkRequestFromRequestQueue

- ea: `0x1c00c2ce0`
- end: `0x1c00c2f5c`
- name: `UlUnlinkRequestFromRequestQueue`
- size: `636`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1c000cec0`
- `0x1c001154c`
- `0x1c002cdfc`

## callees

- `0x1c000fc68`
- `0x1c001a5f0`
- `0x1c0029d4c`
- `0x1c008f21c`
- `0x1c008f3ec`
- `0x1c008f680`
- `0x1c00903a4`
- `0x1c00c2ce0`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00c2f04`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00ef348`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00c2f04`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00ef348`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00c2dad`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00c2dad`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c2d7c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c2ec8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c2ee5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00ef329`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00ef3ad`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c2d7c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c2ec8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c2ee5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00ef329`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00ef3ad`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c2d52`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c2dcf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c2e0a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ef38c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c2d52`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c2dcf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c2e0a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ef38c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c2d88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c2ed4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c2ef1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c2f15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ef335`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ef359`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ef3b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c2d88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c2ed4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c2ef1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c2f15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ef335`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ef359`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ef3b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c2d3a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c2d98`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c2dbe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c2df8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ef37b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c2d3a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c2d98`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c2dbe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c2df8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ef37b`

## pseudocode

```c
__int64 __fastcall UlUnlinkRequestFromRequestQueue(__int64 a1)
{
  char v1; // r14
  __int64 v3; // rbp
  __int64 v4; // rdi
  _QWORD *v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  char v8; // al
  _QWORD *v9; // r8
  _QWORD *v10; // rdx
  __int64 v11; // rbp
  __int64 result; // rax
  __int64 v13; // r9
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  v14 = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
  {
    if ( a1 )
      v13 = *(_QWORD *)(a1 + 64);
    else
      v13 = 0;
    WPP_SF_qq(229, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, v13);
  }
  if ( *(_BYTE *)(a1 + 1836) )
  {
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_qqq(38, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, *(_QWORD *)(a1 + 64), &v14);
    v14 = 0;
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 1688, 0);
    v3 = *(_QWORD *)(a1 + 1696);
    if ( v3 )
    {
      while ( 1 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v3);
        ExReleasePushLockExclusiveEx(a1 + 1688, 0);
        KeLeaveCriticalRegion();
        v4 = *(_QWORD *)(v3 + 48);
        KeEnterCriticalRegion();
        v14 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v4 + 280), 0);
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(a1 + 1688, 0);
        if ( *(_QWORD *)(a1 + 1696) == v3 )
          break;
        ExReleasePushLockExclusiveEx(a1 + 1688, 0);
        KeLeaveCriticalRegion();
        ExReleaseCacheAwarePushLockSharedEx(v14, 0);
        v14 = 0;
        KeLeaveCriticalRegion();
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
          UlpFreeCoupling((PVOID)v3);
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(a1 + 1688, 0);
        v3 = *(_QWORD *)(a1 + 1696);
        if ( !v3 )
          goto LABEL_35;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
        UlpFreeCoupling((PVOID)v3);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v3 + 56, 0);
    }
    else
    {
LABEL_35:
      ExReleasePushLockExclusiveEx(a1 + 1688, 0);
      KeLeaveCriticalRegion();
    }
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_q(39, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v3);
    if ( v3 )
    {
      if ( *(_DWORD *)(a1 + 1720) == 1 )
      {
        v8 = UlpRemoveRequestFromLane(a1);
        *(_DWORD *)(a1 + 1720) = 3;
        v1 = v8;
        if ( v8 )
          goto LABEL_20;
      }
      else if ( *(_DWORD *)(a1 + 1720) == 2 )
      {
        v5 = (_QWORD *)(a1 + 1704);
        v6 = *(_QWORD *)(a1 + 1704);
        if ( *(_QWORD *)(v6 + 8) != a1 + 1704 )
          goto LABEL_16;
        v7 = *(_QWORD **)(a1 + 1712);
        if ( (_QWORD *)*v7 != v5 )
          goto LABEL_16;
        *v7 = v6;
        v1 = 1;
        *(_QWORD *)(v6 + 8) = v7;
        *v5 = 0;
        *(_QWORD *)(a1 + 1712) = 0;
        *(_DWORD *)(a1 + 1720) = 3;
LABEL_20:
        v9 = *(_QWORD **)(v3 + 104);
        v10 = (_QWORD *)(a1 + 1800);
        v11 = v3 + 96;
        if ( *v9 == v11 )
        {
          *v10 = v11;
          *(_QWORD *)(a1 + 1808) = v9;
          *v9 = v10;
          *(_QWORD *)(v11 + 8) = v10;
          goto LABEL_22;
        }
LABEL_16:
        __fastfail(3u);
      }
LABEL_22:
      ExReleasePushLockExclusiveEx(*(_QWORD *)(a1 + 1696) + 56LL, 0);
      KeLeaveCriticalRegion();
      ExReleasePushLockExclusiveEx(a1 + 1688, 0);
      KeLeaveCriticalRegion();
      ExReleaseCacheAwarePushLockSharedEx(v14, 0);
      v14 = 0;
      KeLeaveCriticalRegion();
      if ( v1 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 48), 0xFFFFFFFF) == 1 )
        UlpQueueFreeHttpRequest(a1);
    }
  }
  result = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    return WPP_SF_(230, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1c00c2ce0  push    rbx
0x1c00c2ce2  push    r12
0x1c00c2ce4  push    r14
0x1c00c2ce6  sub     rsp, 40h
0x1c00c2cea  xor     r14b, r14b
0x1c00c2ced  mov     rbx, rcx
0x1c00c2cf0  xor     r12d, r12d
0x1c00c2cf3  mov     [rsp+58h+arg_8], r12
0x1c00c2cf8  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00c2cfe  test    al, al
0x1c00c2d00  js      loc_1C00EF2D4
0x1c00c2d06  mov     [rsp+58h+arg_10], rbp
0x1c00c2d0b  mov     [rsp+58h+arg_18], rsi
0x1c00c2d10  mov     [rsp+58h+var_28], r15
0x1c00c2d15  cmp     [rbx+72Ch], r12b
0x1c00c2d1c  jz      loc_1C00C2F34
0x1c00c2d22  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00c2d28  test    al, al
0x1c00c2d2a  js      loc_1C00EF2FC
0x1c00c2d30  mov     [rsp+58h+var_20], rdi
0x1c00c2d35  mov     [rsp+58h+arg_8], r12
0x1c00c2d3a  call    cs:__imp_KeEnterCriticalRegion
0x1c00c2d41  nop     dword ptr [rax+rax+00h]
0x1c00c2d46  lea     r15, [rbx+698h]
0x1c00c2d4d  xor     edx, edx
0x1c00c2d4f  mov     rcx, r15
0x1c00c2d52  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00c2d59  nop     dword ptr [rax+rax+00h]
0x1c00c2d5e  mov     rbp, [rbx+6A0h]
0x1c00c2d65  mov     esi, 0FFFFFFFFh
0x1c00c2d6a  test    rbp, rbp
0x1c00c2d6d  jz      loc_1C00EF3A8
0x1c00c2d73  lock inc dword ptr [rbp+0]
0x1c00c2d77  xor     edx, edx
0x1c00c2d79  mov     rcx, r15
0x1c00c2d7c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00c2d83  nop     dword ptr [rax+rax+00h]
0x1c00c2d88  call    cs:__imp_KeLeaveCriticalRegion
0x1c00c2d8f  nop     dword ptr [rax+rax+00h]
0x1c00c2d94  mov     rdi, [rbp+30h]
0x1c00c2d98  call    cs:__imp_KeEnterCriticalRegion
0x1c00c2d9f  nop     dword ptr [rax+rax+00h]
0x1c00c2da4  mov     rcx, [rdi+118h]
0x1c00c2dab  xor     edx, edx
0x1c00c2dad  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c00c2db4  nop     dword ptr [rax+rax+00h]
0x1c00c2db9  mov     [rsp+58h+arg_8], rax
0x1c00c2dbe  call    cs:__imp_KeEnterCriticalRegion
0x1c00c2dc5  nop     dword ptr [rax+rax+00h]
0x1c00c2dca  xor     edx, edx
0x1c00c2dcc  mov     rcx, r15
0x1c00c2dcf  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00c2dd6  nop     dword ptr [rax+rax+00h]
0x1c00c2ddb  cmp     [rbx+6A0h], rbp
0x1c00c2de2  jnz     loc_1C00EF324
0x1c00c2de8  mov     eax, esi
0x1c00c2dea  lock xadd [rbp+0], eax
0x1c00c2def  cmp     eax, 1
0x1c00c2df2  jz      loc_1C00EF3CB
0x1c00c2df8  call    cs:__imp_KeEnterCriticalRegion
0x1c00c2dff  nop     dword ptr [rax+rax+00h]
0x1c00c2e04  lea     rcx, [rbp+38h]
0x1c00c2e08  xor     edx, edx
0x1c00c2e0a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00c2e11  nop     dword ptr [rax+rax+00h]
0x1c00c2e16  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00c2e1c  mov     rdi, [rsp+58h+var_20]
0x1c00c2e21  test    al, al
0x1c00c2e23  js      loc_1C00EF3DB
0x1c00c2e29  test    rbp, rbp
0x1c00c2e2c  jz      loc_1C00C2F34
0x1c00c2e32  mov     ecx, [rbx+6B8h]
0x1c00c2e38  sub     ecx, 1
0x1c00c2e3b  jz      short loc_1C00C2E7F
0x1c00c2e3d  cmp     ecx, 1
0x1c00c2e40  jnz     short loc_1C00C2EBB
0x1c00c2e42  lea     rax, [rbx+6A8h]
0x1c00c2e49  mov     rcx, [rax]
0x1c00c2e4c  cmp     [rcx+8], rax
0x1c00c2e50  jz      short loc_1C00C2E59
0x1c00c2e52  mov     ecx, 3
0x1c00c2e57  int     29h; Win8: RtlFailFast(ecx)
0x1c00c2e59  mov     rdx, [rax+8]
0x1c00c2e5d  cmp     [rdx], rax
0x1c00c2e60  jnz     short loc_1C00C2E52
0x1c00c2e62  mov     [rdx], rcx
0x1c00c2e65  mov     r14b, 1
0x1c00c2e68  mov     [rcx+8], rdx
0x1c00c2e6c  mov     [rax], r12
0x1c00c2e6f  mov     [rax+8], r12
0x1c00c2e73  mov     dword ptr [rbx+6B8h], 3
0x1c00c2e7d  jmp     short loc_1C00C2E99
0x1c00c2e7f  mov     rcx, rbx
0x1c00c2e82  call    UlpRemoveRequestFromLane
0x1c00c2e87  mov     dword ptr [rbx+6B8h], 3
0x1c00c2e91  movzx   r14d, al
0x1c00c2e95  test    al, al
0x1c00c2e97  jz      short loc_1C00C2EBB
0x1c00c2e99  mov     r8, [rbp+68h]
0x1c00c2e9d  lea     rdx, [rbx+708h]
0x1c00c2ea4  add     rbp, 60h ; '`'
0x1c00c2ea8  cmp     [r8], rbp
0x1c00c2eab  jnz     short loc_1C00C2E52
0x1c00c2ead  mov     [rdx], rbp
0x1c00c2eb0  mov     [rdx+8], r8
0x1c00c2eb4  mov     [r8], rdx
0x1c00c2eb7  mov     [rbp+8], rdx
0x1c00c2ebb  mov     rcx, [rbx+6A0h]
0x1c00c2ec2  xor     edx, edx
0x1c00c2ec4  add     rcx, 38h ; '8'
0x1c00c2ec8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00c2ecf  nop     dword ptr [rax+rax+00h]
0x1c00c2ed4  call    cs:__imp_KeLeaveCriticalRegion
0x1c00c2edb  nop     dword ptr [rax+rax+00h]
0x1c00c2ee0  xor     edx, edx
0x1c00c2ee2  mov     rcx, r15
0x1c00c2ee5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00c2eec  nop     dword ptr [rax+rax+00h]
0x1c00c2ef1  call    cs:__imp_KeLeaveCriticalRegion
0x1c00c2ef8  nop     dword ptr [rax+rax+00h]
0x1c00c2efd  mov     rcx, [rsp+58h+arg_8]
0x1c00c2f02  xor     edx, edx
0x1c00c2f04  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00c2f0b  nop     dword ptr [rax+rax+00h]
0x1c00c2f10  mov     [rsp+58h+arg_8], r12
0x1c00c2f15  call    cs:__imp_KeLeaveCriticalRegion
0x1c00c2f1c  nop     dword ptr [rax+rax+00h]
0x1c00c2f21  test    r14b, r14b
0x1c00c2f24  jz      short loc_1C00C2F34
0x1c00c2f26  lock xadd [rbx+30h], esi
0x1c00c2f2b  cmp     esi, 1
0x1c00c2f2e  jz      loc_1C00EF3F5
0x1c00c2f34  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00c2f3a  test    al, al
0x1c00c2f3c  js      loc_1C00EF403
0x1c00c2f42  mov     r15, [rsp+58h+var_28]
0x1c00c2f47  mov     rsi, [rsp+58h+arg_18]
0x1c00c2f4c  mov     rbp, [rsp+58h+arg_10]
0x1c00c2f51  add     rsp, 40h
0x1c00c2f55  pop     r14
0x1c00c2f57  pop     r12
0x1c00c2f59  pop     rbx
0x1c00c2f5a  retn
0x1c00ef2d4  test    rbx, rbx
0x1c00ef2d7  jz      short loc_1C00EF2DF
0x1c00ef2d9  mov     r9, [rcx+40h]
0x1c00ef2dd  jmp     short loc_1C00EF2E2
0x1c00ef2df  mov     r9, r12
0x1c00ef2e2  mov     ecx, 0E5h
0x1c00ef2e7  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00ef2ee  mov     r8, rbx
0x1c00ef2f1  call    WPP_SF_qq
0x1c00ef2f6  nop
0x1c00ef2f7  jmp     loc_1C00C2D06
0x1c00ef2fc  mov     r9, [rbx+40h]
0x1c00ef300  lea     rax, [rsp+58h+arg_8]
0x1c00ef305  mov     ecx, 26h ; '&'
0x1c00ef30a  mov     [rsp+58h+var_38], rax
0x1c00ef30f  mov     r8, rbx
0x1c00ef312  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00ef319  call    WPP_SF_qqq
0x1c00ef31e  nop
0x1c00ef31f  jmp     loc_1C00C2D30
0x1c00ef324  xor     edx, edx
0x1c00ef326  mov     rcx, r15
0x1c00ef329  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00ef330  nop     dword ptr [rax+rax+00h]
0x1c00ef335  call    cs:__imp_KeLeaveCriticalRegion
0x1c00ef33c  nop     dword ptr [rax+rax+00h]
0x1c00ef341  mov     rcx, [rsp+58h+arg_8]
0x1c00ef346  xor     edx, edx
0x1c00ef348  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00ef34f  nop     dword ptr [rax+rax+00h]
0x1c00ef354  mov     [rsp+58h+arg_8], r12
0x1c00ef359  call    cs:__imp_KeLeaveCriticalRegion
0x1c00ef360  nop     dword ptr [rax+rax+00h]
0x1c00ef365  mov     eax, esi
0x1c00ef367  lock xadd [rbp+0], eax
0x1c00ef36c  cmp     eax, 1
0x1c00ef36f  jnz     short loc_1C00EF37B
0x1c00ef371  xor     edx, edx
0x1c00ef373  mov     rcx, rbp; P
0x1c00ef376  call    UlpFreeCoupling
0x1c00ef37b  call    cs:__imp_KeEnterCriticalRegion
0x1c00ef382  nop     dword ptr [rax+rax+00h]
0x1c00ef387  xor     edx, edx
0x1c00ef389  mov     rcx, r15
0x1c00ef38c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00ef393  nop     dword ptr [rax+rax+00h]
0x1c00ef398  mov     rbp, [rbx+6A0h]
0x1c00ef39f  test    rbp, rbp
0x1c00ef3a2  jnz     loc_1C00C2D73
0x1c00ef3a8  xor     edx, edx
0x1c00ef3aa  mov     rcx, r15
0x1c00ef3ad  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00ef3b4  nop     dword ptr [rax+rax+00h]
0x1c00ef3b9  call    cs:__imp_KeLeaveCriticalRegion
0x1c00ef3c0  nop     dword ptr [rax+rax+00h]
0x1c00ef3c5  nop
0x1c00ef3c6  jmp     loc_1C00C2E16
0x1c00ef3cb  xor     edx, edx
0x1c00ef3cd  mov     rcx, rbp; P
0x1c00ef3d0  call    UlpFreeCoupling
0x1c00ef3d5  nop
0x1c00ef3d6  jmp     loc_1C00C2DF8
0x1c00ef3db  mov     ecx, 27h ; '''
0x1c00ef3e0  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00ef3e7  mov     r8, rbp
0x1c00ef3ea  call    WPP_SF_q
0x1c00ef3ef  nop
0x1c00ef3f0  jmp     loc_1C00C2E29
0x1c00ef3f5  mov     rcx, rbx
0x1c00ef3f8  call    UlpQueueFreeHttpRequest
0x1c00ef3fd  nop
0x1c00ef3fe  jmp     loc_1C00C2F34
0x1c00ef403  mov     ecx, 0E6h
0x1c00ef408  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00ef40f  call    WPP_SF_
0x1c00ef414  nop
0x1c00ef415  jmp     loc_1C00C2F42
```
