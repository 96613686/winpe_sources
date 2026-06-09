# PrvReg_Shutdown

- ea: `0x180079a24`
- end: `0x180079ae9`
- name: `PrvReg_Shutdown`
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
- `0x180079a24`
- `0x180079b90`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x180079ad1`
- `ntoskrnl!ExDeleteResourceLite` at `0x180079ad1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180079a32`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180079a32`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180079a43`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180079a43`
- `ntoskrnl!ExReleaseResourceLite` at `0x180079ab6`
- `ntoskrnl!ExReleaseResourceLite` at `0x180079ab6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180079ac2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180079ac2`

## pseudocode

```c
NTSTATUS __fastcall PrvReg_Shutdown(PERESOURCE Resource)
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
        PrvReg_OnFreeProviderNode();
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
0x180079a24  push    rbx
0x180079a26  push    rbp
0x180079a27  push    rsi
0x180079a28  push    rdi
0x180079a29  push    r14
0x180079a2b  sub     rsp, 20h
0x180079a2f  mov     rbx, rcx
0x180079a32  call    cs:__imp_KeEnterCriticalRegion
0x180079a39  nop     dword ptr [rax+rax+00h]
0x180079a3e  mov     dl, 1; Wait
0x180079a40  mov     rcx, rbx; Resource
0x180079a43  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180079a4a  nop     dword ptr [rax+rax+00h]
0x180079a4f  mov     r14, [rbx+70h]
0x180079a53  test    r14, r14
0x180079a56  jz      short loc_180079AB3
0x180079a58  mov     ebp, [rbx+68h]
0x180079a5b  xor     esi, esi
0x180079a5d  test    ebp, ebp
0x180079a5f  jz      short loc_180079A9C
0x180079a61  lea     rdi, [r14+rsi*8]
0x180079a65  test    rdi, rdi
0x180079a68  jz      short loc_180079A96
0x180079a6a  mov     rcx, [rdi]
0x180079a6d  test    rcx, rcx
0x180079a70  jz      short loc_180079A96
0x180079a72  call    _PrvReg_OnFreeProviderNode
0x180079a77  mov     rax, [rdi]
0x180079a7a  mov     rcx, [rax]; P
0x180079a7d  test    rcx, rcx
0x180079a80  jz      short loc_180079A87
0x180079a82  call    DataBlock_Free
0x180079a87  mov     rcx, [rdi]; P
0x180079a8a  call    BCryptFree
0x180079a8f  mov     qword ptr [rdi], 0
0x180079a96  inc     esi
0x180079a98  cmp     esi, ebp
0x180079a9a  jb      short loc_180079A61
0x180079a9c  mov     rcx, r14; P
0x180079a9f  call    BCryptFree
0x180079aa4  mov     dword ptr [rbx+68h], 0
0x180079aab  mov     qword ptr [rbx+70h], 0
0x180079ab3  mov     rcx, rbx; Resource
0x180079ab6  call    cs:__imp_ExReleaseResourceLite
0x180079abd  nop     dword ptr [rax+rax+00h]
0x180079ac2  call    cs:__imp_KeLeaveCriticalRegion
0x180079ac9  nop     dword ptr [rax+rax+00h]
0x180079ace  mov     rcx, rbx; Resource
0x180079ad1  call    cs:__imp_ExDeleteResourceLite
0x180079ad8  nop     dword ptr [rax+rax+00h]
0x180079add  add     rsp, 20h
0x180079ae1  pop     r14
0x180079ae3  pop     rdi
0x180079ae4  pop     rsi
0x180079ae5  pop     rbp
0x180079ae6  pop     rbx
0x180079ae7  retn
```
