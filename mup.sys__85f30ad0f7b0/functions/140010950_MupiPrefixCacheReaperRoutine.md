# MupiPrefixCacheReaperRoutine

- ea: `0x140010950`
- end: `0x140010a78`
- name: `MupiPrefixCacheReaperRoutine`
- size: `296`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140002a14`
- `0x1400036c8`
- `0x140010950`
- `0x140010bb8`
- `0x140010e48`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400109a0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400109a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010a2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010a2b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001098b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001098b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010a37`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010a37`

## pseudocode

```c
void __fastcall MupiPrefixCacheReaperRoutine(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  __int64 *v2; // rbx
  __int64 *v3; // rdi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_ea0133f9b224365980f4880a222ef939_Traceguids);
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v2 = (__int64 *)qword_14000A9E0;
  while ( v2 != &qword_14000A9E0 )
  {
    v3 = v2 - 15;
    v2 = (__int64 *)*v2;
    if ( !*((_DWORD *)v3 + 34) && MEMORY[0xFFFFF78000000320] >= v3[12] )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
      {
        WPP_SF_Zq(
          WPP_GLOBAL_Control->AttachedDevice,
          28,
          (unsigned int)WPP_ea0133f9b224365980f4880a222ef939_Traceguids,
          (_DWORD)v3 + 80,
          (char)v3);
      }
      MupiRemoveKnownPrefixEntry((char *)v3);
    }
  }
  MupiPrefixScheduleGarbageCollectionTimeout();
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_ea0133f9b224365980f4880a222ef939_Traceguids);
  }
}

```

## disassembly

```asm
0x140010950  push    rbx
0x140010952  push    rsi
0x140010953  push    rdi
0x140010954  push    r15
0x140010956  sub     rsp, 38h
0x14001095a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010961  lea     rsi, WPP_GLOBAL_Control
0x140010968  cmp     rcx, rsi
0x14001096b  jz      short loc_14001098B
0x14001096d  test    dword ptr [rcx+2Ch], 2000000h
0x140010974  jz      short loc_14001098B
0x140010976  mov     rcx, [rcx+18h]
0x14001097a  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x140010981  mov     edx, 1Bh
0x140010986  call    WPP_SF_
0x14001098b  call    cs:__imp_KeEnterCriticalRegion
0x140010992  nop     dword ptr [rax+rax+00h]
0x140010997  mov     dl, 1; Wait
0x140010999  lea     rcx, Resource; Resource
0x1400109a0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400109a7  nop     dword ptr [rax+rax+00h]
0x1400109ac  mov     rbx, cs:qword_14000A9E0
0x1400109b3  lea     r15, qword_14000A9E0
0x1400109ba  jmp     short loc_140010A1A
0x1400109bc  lea     rdi, [rbx-78h]
0x1400109c0  mov     rbx, [rbx]
0x1400109c3  cmp     dword ptr [rdi+88h], 0
0x1400109ca  jnz     short loc_140010A1A
0x1400109cc  mov     rax, 0FFFFF78000000320h
0x1400109d6  mov     rax, [rax]
0x1400109d9  cmp     rax, [rdi+60h]
0x1400109dd  jl      short loc_140010A1A
0x1400109df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400109e6  cmp     rcx, rsi
0x1400109e9  jz      short loc_140010A12
0x1400109eb  test    dword ptr [rcx+2Ch], 4000000h
0x1400109f2  jz      short loc_140010A12
0x1400109f4  mov     rcx, [rcx+18h]
0x1400109f8  lea     r9, [rdi+50h]
0x1400109fc  mov     edx, 1Ch
0x140010a01  mov     [rsp+58h+var_38], rdi
0x140010a06  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x140010a0d  call    WPP_SF_Zq
0x140010a12  mov     rcx, rdi; P
0x140010a15  call    MupiRemoveKnownPrefixEntry
0x140010a1a  cmp     rbx, r15
0x140010a1d  jnz     short loc_1400109BC
0x140010a1f  call    MupiPrefixScheduleGarbageCollectionTimeout
0x140010a24  lea     rcx, Resource; Resource
0x140010a2b  call    cs:__imp_ExReleaseResourceLite
0x140010a32  nop     dword ptr [rax+rax+00h]
0x140010a37  call    cs:__imp_KeLeaveCriticalRegion
0x140010a3e  nop     dword ptr [rax+rax+00h]
0x140010a43  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a4a  cmp     rcx, rsi
0x140010a4d  jz      short loc_140010A6D
0x140010a4f  test    dword ptr [rcx+2Ch], 2000000h
0x140010a56  jz      short loc_140010A6D
0x140010a58  mov     rcx, [rcx+18h]
0x140010a5c  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x140010a63  mov     edx, 1Dh
0x140010a68  call    WPP_SF_
0x140010a6d  add     rsp, 38h
0x140010a71  pop     r15
0x140010a73  pop     rdi
0x140010a74  pop     rsi
0x140010a75  pop     rbx
0x140010a76  retn
```
