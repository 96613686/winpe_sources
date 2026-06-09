# CfgReg_Shutdown

- ea: `0x18007c204`
- end: `0x18007c2c9`
- name: `CfgReg_Shutdown`
- size: `197`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180073e20`

## callees

- `0x180025ec0`
- `0x180056428`
- `0x18007c204`
- `0x18007c460`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x18007c2b1`
- `ntoskrnl!ExDeleteResourceLite` at `0x18007c2b1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007c212`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007c212`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007c223`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007c223`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007c296`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007c296`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007c2a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007c2a2`

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
0x18007c204  push    rbx
0x18007c206  push    rbp
0x18007c207  push    rsi
0x18007c208  push    rdi
0x18007c209  push    r14
0x18007c20b  sub     rsp, 20h
0x18007c20f  mov     rbx, rcx
0x18007c212  call    cs:__imp_KeEnterCriticalRegion
0x18007c219  nop     dword ptr [rax+rax+00h]
0x18007c21e  mov     dl, 1; Wait
0x18007c220  mov     rcx, rbx; Resource
0x18007c223  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18007c22a  nop     dword ptr [rax+rax+00h]
0x18007c22f  mov     r14, [rbx+70h]
0x18007c233  test    r14, r14
0x18007c236  jz      short loc_18007C293
0x18007c238  mov     ebp, [rbx+68h]
0x18007c23b  xor     esi, esi
0x18007c23d  test    ebp, ebp
0x18007c23f  jz      short loc_18007C27C
0x18007c241  lea     rdi, [r14+rsi*8]
0x18007c245  test    rdi, rdi
0x18007c248  jz      short loc_18007C276
0x18007c24a  mov     rcx, [rdi]
0x18007c24d  test    rcx, rcx
0x18007c250  jz      short loc_18007C276
0x18007c252  call    _CfgReg_OnFreeTableNode
0x18007c257  mov     rax, [rdi]
0x18007c25a  mov     rcx, [rax]; P
0x18007c25d  test    rcx, rcx
0x18007c260  jz      short loc_18007C267
0x18007c262  call    DataBlock_Free
0x18007c267  mov     rcx, [rdi]; P
0x18007c26a  call    BCryptFree
0x18007c26f  mov     qword ptr [rdi], 0
0x18007c276  inc     esi
0x18007c278  cmp     esi, ebp
0x18007c27a  jb      short loc_18007C241
0x18007c27c  mov     rcx, r14; P
0x18007c27f  call    BCryptFree
0x18007c284  mov     dword ptr [rbx+68h], 0
0x18007c28b  mov     qword ptr [rbx+70h], 0
0x18007c293  mov     rcx, rbx; Resource
0x18007c296  call    cs:__imp_ExReleaseResourceLite
0x18007c29d  nop     dword ptr [rax+rax+00h]
0x18007c2a2  call    cs:__imp_KeLeaveCriticalRegion
0x18007c2a9  nop     dword ptr [rax+rax+00h]
0x18007c2ae  mov     rcx, rbx; Resource
0x18007c2b1  call    cs:__imp_ExDeleteResourceLite
0x18007c2b8  nop     dword ptr [rax+rax+00h]
0x18007c2bd  add     rsp, 20h
0x18007c2c1  pop     r14
0x18007c2c3  pop     rdi
0x18007c2c4  pop     rsi
0x18007c2c5  pop     rbp
0x18007c2c6  pop     rbx
0x18007c2c7  retn
```
