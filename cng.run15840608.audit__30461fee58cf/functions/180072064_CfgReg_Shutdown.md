# CfgReg_Shutdown

- ea: `0x180072064`
- end: `0x180072129`
- name: `CfgReg_Shutdown`
- size: `197`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180069c80`

## callees

- `0x18001bd90`
- `0x18004c328`
- `0x180072064`
- `0x1800722c0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x180072111`
- `ntoskrnl!ExDeleteResourceLite` at `0x180072111`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180072072`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180072072`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180072083`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180072083`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800720f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800720f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180072102`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180072102`

## pseudocode

```c
NTSTATUS __fastcall CfgReg_Shutdown(PERESOURCE Resource)
{
  struct _LIST_ENTRY *Blink; // r14
  unsigned int Flink; // ebp
  __int64 i; // rsi
  PVOID *v5; // rdi
  void *v6; // rcx

  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(Resource, 1u);
  Blink = Resource[1].SystemResourcesList.Blink;
  if ( Blink )
  {
    Flink = (unsigned int)Resource[1].SystemResourcesList.Flink;
    for ( i = 0; (unsigned int)i < Flink; i = (unsigned int)(i + 1) )
    {
      v5 = (PVOID *)(&Blink->Flink + i);
      if ( v5 && *v5 )
      {
        CfgReg_OnFreeTableNode();
        v6 = *(void **)*v5;
        if ( v6 )
          DataBlock_Free(v6);
        BCryptFree(*v5);
        *v5 = 0;
      }
    }
    BCryptFree(Blink);
    LODWORD(Resource[1].SystemResourcesList.Flink) = 0;
    Resource[1].SystemResourcesList.Blink = 0;
  }
  ExReleaseResourceLite(Resource);
  KeLeaveCriticalRegion();
  return ExDeleteResourceLite(Resource);
}

```

## disassembly

```asm
0x180072064  push    rbx
0x180072066  push    rbp
0x180072067  push    rsi
0x180072068  push    rdi
0x180072069  push    r14
0x18007206b  sub     rsp, 20h
0x18007206f  mov     rbx, rcx
0x180072072  call    cs:__imp_KeEnterCriticalRegion
0x180072079  nop     dword ptr [rax+rax+00h]
0x18007207e  mov     dl, 1; Wait
0x180072080  mov     rcx, rbx; Resource
0x180072083  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18007208a  nop     dword ptr [rax+rax+00h]
0x18007208f  mov     r14, [rbx+70h]
0x180072093  test    r14, r14
0x180072096  jz      short loc_1800720F3
0x180072098  mov     ebp, [rbx+68h]
0x18007209b  xor     esi, esi
0x18007209d  test    ebp, ebp
0x18007209f  jz      short loc_1800720DC
0x1800720a1  lea     rdi, [r14+rsi*8]
0x1800720a5  test    rdi, rdi
0x1800720a8  jz      short loc_1800720D6
0x1800720aa  mov     rcx, [rdi]
0x1800720ad  test    rcx, rcx
0x1800720b0  jz      short loc_1800720D6
0x1800720b2  call    _CfgReg_OnFreeTableNode
0x1800720b7  mov     rax, [rdi]
0x1800720ba  mov     rcx, [rax]; P
0x1800720bd  test    rcx, rcx
0x1800720c0  jz      short loc_1800720C7
0x1800720c2  call    DataBlock_Free
0x1800720c7  mov     rcx, [rdi]; P
0x1800720ca  call    BCryptFree
0x1800720cf  mov     qword ptr [rdi], 0
0x1800720d6  inc     esi
0x1800720d8  cmp     esi, ebp
0x1800720da  jb      short loc_1800720A1
0x1800720dc  mov     rcx, r14; P
0x1800720df  call    BCryptFree
0x1800720e4  mov     dword ptr [rbx+68h], 0
0x1800720eb  mov     qword ptr [rbx+70h], 0
0x1800720f3  mov     rcx, rbx; Resource
0x1800720f6  call    cs:__imp_ExReleaseResourceLite
0x1800720fd  nop     dword ptr [rax+rax+00h]
0x180072102  call    cs:__imp_KeLeaveCriticalRegion
0x180072109  nop     dword ptr [rax+rax+00h]
0x18007210e  mov     rcx, rbx; Resource
0x180072111  call    cs:__imp_ExDeleteResourceLite
0x180072118  nop     dword ptr [rax+rax+00h]
0x18007211d  add     rsp, 20h
0x180072121  pop     r14
0x180072123  pop     rdi
0x180072124  pop     rsi
0x180072125  pop     rbp
0x180072126  pop     rbx
0x180072127  retn
```
