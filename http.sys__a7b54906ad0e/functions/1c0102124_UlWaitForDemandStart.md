# UlWaitForDemandStart

- ea: `0x1c0102124`
- end: `0x1c0102281`
- name: `UlWaitForDemandStart`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1c011d530`

## callees

- `0x1c0016860`
- `0x1c002a02c`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c0102124`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c010222d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c010222d`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c010217d`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c010217d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c01021e1`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c01021e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0102239`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0102239`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102168`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102168`

## pseudocode

```c
__int64 __fastcall UlWaitForDemandStart(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v3; // rbp
  USHORT CurrentNodeNumber; // di
  __int64 v5; // r14
  int v6; // ebx
  __int64 v7; // r8

  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qq(194, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, a2);
  v3 = *(KSPIN_LOCK **)(a1 + 8);
  KeEnterCriticalRegion();
  CurrentNodeNumber = 0;
  v5 = ExAcquireCacheAwarePushLockSharedEx(v3[35], 0);
  if ( *(_BYTE *)(a1 + 4) )
  {
    v6 = -1073741816;
  }
  else
  {
    v6 = UlSiqEnqueueIrp(v3 + 8);
    if ( v6 >= 0 )
    {
      v6 = 259;
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_(16, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
      if ( (unsigned __int16)UlNumberOfLanes > 1u )
        CurrentNodeNumber = KeGetCurrentNodeNumber();
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_D(17, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
      LOBYTE(v7) = 1;
      UlpSynchronizeLanes(v3, *(_QWORD *)(v3[36] + 8LL * CurrentNodeNumber), v7);
    }
  }
  ExReleaseCacheAwarePushLockSharedEx(v5, 0);
  KeLeaveCriticalRegion();
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(195, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1c0102124  mov     rax, rsp
0x1c0102127  mov     [rax+8], rbx
0x1c010212b  mov     [rax+10h], rbp
0x1c010212f  mov     [rax+18h], rsi
0x1c0102133  mov     [rax+20h], rdi
0x1c0102137  push    r14
0x1c0102139  sub     rsp, 20h
0x1c010213d  mov     rsi, rdx
0x1c0102140  mov     rbx, rcx
0x1c0102143  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0102149  test    al, al
0x1c010214b  jns     short loc_1C0102164
0x1c010214d  mov     r9, rdx
0x1c0102150  mov     ecx, 0C2h
0x1c0102155  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c010215c  mov     r8, rbx
0x1c010215f  call    WPP_SF_qq
0x1c0102164  mov     rbp, [rbx+8]
0x1c0102168  call    cs:__imp_KeEnterCriticalRegion
0x1c010216f  nop     dword ptr [rax+rax+00h]
0x1c0102174  mov     rcx, [rbp+118h]
0x1c010217b  xor     edx, edx
0x1c010217d  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c0102184  nop     dword ptr [rax+rax+00h]
0x1c0102189  xor     edi, edi
0x1c010218b  mov     r14, rax
0x1c010218e  cmp     [rbx+4], dil
0x1c0102192  jz      short loc_1C010219E
0x1c0102194  mov     ebx, 0C0000008h
0x1c0102199  jmp     loc_1C0102228
0x1c010219e  lea     rcx, [rbp+40h]; SpinLock
0x1c01021a2  mov     rdx, rsi
0x1c01021a5  lea     r8, UlpCancelDemandStartIrp
0x1c01021ac  call    UlSiqEnqueueIrp
0x1c01021b1  mov     ebx, eax
0x1c01021b3  test    eax, eax
0x1c01021b5  js      short loc_1C0102228
0x1c01021b7  mov     ebx, 103h
0x1c01021bc  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c01021c2  test    al, al
0x1c01021c4  jns     short loc_1C01021D7
0x1c01021c6  mov     ecx, 10h
0x1c01021cb  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c01021d2  call    WPP_SF_
0x1c01021d7  cmp     cs:UlNumberOfLanes, 1
0x1c01021df  jbe     short loc_1C01021F0
0x1c01021e1  call    cs:__imp_KeGetCurrentNodeNumber
0x1c01021e8  nop     dword ptr [rax+rax+00h]
0x1c01021ed  movzx   edi, ax
0x1c01021f0  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c01021f6  test    al, al
0x1c01021f8  jns     short loc_1C010220F
0x1c01021fa  movzx   r8d, di
0x1c01021fe  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0102205  mov     ecx, 11h
0x1c010220a  call    WPP_SF_D
0x1c010220f  mov     rdx, [rbp+120h]
0x1c0102216  mov     r8b, 1
0x1c0102219  movzx   eax, di
0x1c010221c  mov     rcx, rbp
0x1c010221f  mov     rdx, [rdx+rax*8]
0x1c0102223  call    UlpSynchronizeLanes
0x1c0102228  xor     edx, edx
0x1c010222a  mov     rcx, r14
0x1c010222d  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c0102234  nop     dword ptr [rax+rax+00h]
0x1c0102239  call    cs:__imp_KeLeaveCriticalRegion
0x1c0102240  nop     dword ptr [rax+rax+00h]
0x1c0102245  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c010224b  test    al, al
0x1c010224d  jns     short loc_1C0102263
0x1c010224f  mov     ecx, 0C3h
0x1c0102254  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c010225b  mov     r8d, ebx
0x1c010225e  call    WPP_SF_D
0x1c0102263  mov     rbp, [rsp+28h+arg_8]
0x1c0102268  mov     eax, ebx
0x1c010226a  mov     rbx, [rsp+28h+arg_0]
0x1c010226f  mov     rsi, [rsp+28h+arg_10]
0x1c0102274  mov     rdi, [rsp+28h+arg_18]
0x1c0102279  add     rsp, 20h
0x1c010227d  pop     r14
0x1c010227f  retn
```
