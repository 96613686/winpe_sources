# DfscpContainerCleanupNotify

- ea: `0x140019ec0`
- end: `0x14001a02d`
- name: `DfscpContainerCleanupNotify`
- size: `365`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400025f4`
- `0x140011b78`
- `0x140012534`
- `0x140018068`
- `0x140019ec0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019f5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019f5e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019f52`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019f52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140019f12`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140019f12`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019efd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019efd`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001a000`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001a013`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001a000`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001a013`

## pseudocode

```c
NTSTATUS __fastcall DfscpContainerCleanupNotify(__int64 a1)
{
  __int64 v2; // rax
  _QWORD *v3; // rcx
  char *v4; // rcx
  char *v5; // rcx
  void *v6; // rdx
  void *v7; // rdx
  struct _ERESOURCE *v8; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids, a1);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement, 1u);
  v2 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 != a1 )
  {
    if ( *(_QWORD *)(v2 + 8) != a1 || (v3 = *(_QWORD **)(a1 + 8), *v3 != a1) )
      __fastfail(3u);
    *v3 = v2;
    *(_QWORD *)(v2 + 8) = v3;
    *(_QWORD *)(a1 + 8) = a1;
    *(_QWORD *)a1 = a1;
  }
  ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement);
  KeLeaveCriticalRegion();
  v4 = *(char **)(a1 + 128);
  if ( v4 )
  {
    DfscCacheDelete(v4);
    *(_QWORD *)(a1 + 128) = 0;
  }
  v5 = *(char **)(a1 + 136);
  if ( v5 )
  {
    DfscCacheDelete(v5);
    *(_QWORD *)(a1 + 136) = 0;
  }
  v6 = *(void **)(a1 + 256);
  if ( v6 )
  {
    DfscNetUseTableFree(a1, v6);
    *(_QWORD *)(a1 + 256) = 0;
  }
  v7 = *(void **)(a1 + 264);
  if ( v7 )
  {
    DfscNetUseTableFree(a1, v7);
    *(_QWORD *)(a1 + 264) = 0;
  }
  v8 = *(struct _ERESOURCE **)(a1 + 144);
  if ( v8 )
  {
    DfscCredTableFree(v8);
    *(_QWORD *)(a1 + 144) = 0;
  }
  ExDeleteResourceLite((PERESOURCE)(a1 + 16));
  return ExDeleteResourceLite((PERESOURCE)(a1 + 152));
}

```

## disassembly

```asm
0x140019ec0  push    rbx
0x140019ec2  sub     rsp, 20h
0x140019ec6  mov     rbx, rcx
0x140019ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x140019ed0  lea     rax, WPP_GLOBAL_Control
0x140019ed7  cmp     rcx, rax
0x140019eda  jz      short loc_140019EFD
0x140019edc  test    dword ptr [rcx+2Ch], 200000h
0x140019ee3  jz      short loc_140019EFD
0x140019ee5  mov     rcx, [rcx+18h]
0x140019ee9  lea     r8, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids
0x140019ef0  mov     edx, 15h
0x140019ef5  mov     r9, rbx
0x140019ef8  call    WPP_SF_q
0x140019efd  call    cs:__imp_KeEnterCriticalRegion
0x140019f04  nop     dword ptr [rax+rax+00h]
0x140019f09  mov     dl, 1; Wait
0x140019f0b  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x140019f12  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140019f19  nop     dword ptr [rax+rax+00h]
0x140019f1e  mov     rax, [rbx]
0x140019f21  cmp     rax, rbx
0x140019f24  jz      short loc_140019F4B
0x140019f26  cmp     [rax+8], rbx
0x140019f2a  jnz     loc_14001A026
0x140019f30  mov     rcx, [rbx+8]
0x140019f34  cmp     [rcx], rbx
0x140019f37  jnz     loc_14001A026
0x140019f3d  mov     [rcx], rax
0x140019f40  mov     [rax+8], rcx
0x140019f44  mov     [rbx+8], rbx
0x140019f48  mov     [rbx], rbx
0x140019f4b  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x140019f52  call    cs:__imp_ExReleaseResourceLite
0x140019f59  nop     dword ptr [rax+rax+00h]
0x140019f5e  call    cs:__imp_KeLeaveCriticalRegion
0x140019f65  nop     dword ptr [rax+rax+00h]
0x140019f6a  mov     rcx, [rbx+80h]; P
0x140019f71  test    rcx, rcx
0x140019f74  jz      short loc_140019F86
0x140019f76  call    DfscCacheDelete
0x140019f7b  mov     qword ptr [rbx+80h], 0
0x140019f86  mov     rcx, [rbx+88h]; P
0x140019f8d  test    rcx, rcx
0x140019f90  jz      short loc_140019FA2
0x140019f92  call    DfscCacheDelete
0x140019f97  mov     qword ptr [rbx+88h], 0
0x140019fa2  mov     rdx, [rbx+100h]
0x140019fa9  test    rdx, rdx
0x140019fac  jz      short loc_140019FC1
0x140019fae  mov     rcx, rbx
0x140019fb1  call    DfscNetUseTableFree
0x140019fb6  mov     qword ptr [rbx+100h], 0
0x140019fc1  mov     rdx, [rbx+108h]
0x140019fc8  test    rdx, rdx
0x140019fcb  jz      short loc_140019FE0
0x140019fcd  mov     rcx, rbx
0x140019fd0  call    DfscNetUseTableFree
0x140019fd5  mov     qword ptr [rbx+108h], 0
0x140019fe0  mov     rcx, [rbx+90h]; P
0x140019fe7  test    rcx, rcx
0x140019fea  jz      short loc_140019FFC
0x140019fec  call    DfscCredTableFree
0x140019ff1  mov     qword ptr [rbx+90h], 0
0x140019ffc  lea     rcx, [rbx+10h]; Resource
0x14001a000  call    cs:__imp_ExDeleteResourceLite
0x14001a007  nop     dword ptr [rax+rax+00h]
0x14001a00c  lea     rcx, [rbx+98h]; Resource
0x14001a013  call    cs:__imp_ExDeleteResourceLite
0x14001a01a  nop     dword ptr [rax+rax+00h]
0x14001a01f  add     rsp, 20h
0x14001a023  pop     rbx
0x14001a024  retn
0x14001a026  mov     ecx, 3
0x14001a02b  int     29h; Win8: RtlFailFast(ecx)
```
