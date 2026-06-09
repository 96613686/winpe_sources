# DependentFSDereferenceDependency

- ea: `0x18000d9d0`
- end: `0x18000da91`
- name: `DependentFSDereferenceDependency`
- size: `193`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb48`
- `0x18000e88c`

## callees

- `0x18000d9d0`
- `0x18000f73c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000da56`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000da79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000da56`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000da79`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000da4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000da6d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000da4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000da6d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000da15`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000da15`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000da00`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000da00`

## pseudocode

```c
__int64 __fastcall DependentFSDereferenceDependency(_DWORD *P)
{
  if ( !Driver )
    return 3221225860LL;
  if ( byte_180005196 )
    return 3221225865LL;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( P && *(_WORD *)P == 12336 && P[14] )
  {
    DereferenceDependencyContext(P, 1, 0);
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    return 0;
  }
  else
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x18000d9d0  push    rbx
0x18000d9d2  sub     rsp, 20h
0x18000d9d6  cmp     cs:Driver, 0
0x18000d9de  mov     rbx, rcx
0x18000d9e1  jnz     short loc_18000D9ED
0x18000d9e3  mov     eax, 0C0000184h
0x18000d9e8  jmp     loc_18000DA8A
0x18000d9ed  cmp     cs:byte_180005196, 0
0x18000d9f4  jz      short loc_18000DA00
0x18000d9f6  mov     eax, 0C0000189h
0x18000d9fb  jmp     loc_18000DA8A
0x18000da00  call    cs:__imp_KeEnterCriticalRegion
0x18000da07  nop     dword ptr [rax+rax+00h]
0x18000da0c  mov     dl, 1; Wait
0x18000da0e  lea     rcx, Resource; Resource
0x18000da15  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000da1c  nop     dword ptr [rax+rax+00h]
0x18000da21  test    rbx, rbx
0x18000da24  jz      short loc_18000DA66
0x18000da26  mov     eax, 3030h
0x18000da2b  cmp     [rbx], ax
0x18000da2e  jnz     short loc_18000DA66
0x18000da30  cmp     dword ptr [rbx+38h], 1
0x18000da34  jb      short loc_18000DA66
0x18000da36  xor     r8d, r8d
0x18000da39  mov     dl, 1
0x18000da3b  mov     rcx, rbx; P
0x18000da3e  call    DereferenceDependencyContext
0x18000da43  lea     rcx, Resource; Resource
0x18000da4a  call    cs:__imp_ExReleaseResourceLite
0x18000da51  nop     dword ptr [rax+rax+00h]
0x18000da56  call    cs:__imp_KeLeaveCriticalRegion
0x18000da5d  nop     dword ptr [rax+rax+00h]
0x18000da62  xor     eax, eax
0x18000da64  jmp     short loc_18000DA8A
0x18000da66  lea     rcx, Resource; Resource
0x18000da6d  call    cs:__imp_ExReleaseResourceLite
0x18000da74  nop     dword ptr [rax+rax+00h]
0x18000da79  call    cs:__imp_KeLeaveCriticalRegion
0x18000da80  nop     dword ptr [rax+rax+00h]
0x18000da85  mov     eax, 0C000000Dh
0x18000da8a  add     rsp, 20h
0x18000da8e  pop     rbx
0x18000da8f  retn
```
