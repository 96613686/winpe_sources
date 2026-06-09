# PrvReg_Shutdown

- ea: `0x18006f884`
- end: `0x18006f949`
- name: `PrvReg_Shutdown`
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
- `0x18006f884`
- `0x18006f9f0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x18006f931`
- `ntoskrnl!ExDeleteResourceLite` at `0x18006f931`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006f892`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006f892`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18006f8a3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18006f8a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006f916`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006f916`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006f922`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006f922`

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
0x18006f884  push    rbx
0x18006f886  push    rbp
0x18006f887  push    rsi
0x18006f888  push    rdi
0x18006f889  push    r14
0x18006f88b  sub     rsp, 20h
0x18006f88f  mov     rbx, rcx
0x18006f892  call    cs:__imp_KeEnterCriticalRegion
0x18006f899  nop     dword ptr [rax+rax+00h]
0x18006f89e  mov     dl, 1; Wait
0x18006f8a0  mov     rcx, rbx; Resource
0x18006f8a3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18006f8aa  nop     dword ptr [rax+rax+00h]
0x18006f8af  mov     r14, [rbx+70h]
0x18006f8b3  test    r14, r14
0x18006f8b6  jz      short loc_18006F913
0x18006f8b8  mov     ebp, [rbx+68h]
0x18006f8bb  xor     esi, esi
0x18006f8bd  test    ebp, ebp
0x18006f8bf  jz      short loc_18006F8FC
0x18006f8c1  lea     rdi, [r14+rsi*8]
0x18006f8c5  test    rdi, rdi
0x18006f8c8  jz      short loc_18006F8F6
0x18006f8ca  mov     rcx, [rdi]
0x18006f8cd  test    rcx, rcx
0x18006f8d0  jz      short loc_18006F8F6
0x18006f8d2  call    _PrvReg_OnFreeProviderNode
0x18006f8d7  mov     rax, [rdi]
0x18006f8da  mov     rcx, [rax]; P
0x18006f8dd  test    rcx, rcx
0x18006f8e0  jz      short loc_18006F8E7
0x18006f8e2  call    DataBlock_Free
0x18006f8e7  mov     rcx, [rdi]; P
0x18006f8ea  call    BCryptFree
0x18006f8ef  mov     qword ptr [rdi], 0
0x18006f8f6  inc     esi
0x18006f8f8  cmp     esi, ebp
0x18006f8fa  jb      short loc_18006F8C1
0x18006f8fc  mov     rcx, r14; P
0x18006f8ff  call    BCryptFree
0x18006f904  mov     dword ptr [rbx+68h], 0
0x18006f90b  mov     qword ptr [rbx+70h], 0
0x18006f913  mov     rcx, rbx; Resource
0x18006f916  call    cs:__imp_ExReleaseResourceLite
0x18006f91d  nop     dword ptr [rax+rax+00h]
0x18006f922  call    cs:__imp_KeLeaveCriticalRegion
0x18006f929  nop     dword ptr [rax+rax+00h]
0x18006f92e  mov     rcx, rbx; Resource
0x18006f931  call    cs:__imp_ExDeleteResourceLite
0x18006f938  nop     dword ptr [rax+rax+00h]
0x18006f93d  add     rsp, 20h
0x18006f941  pop     r14
0x18006f943  pop     rdi
0x18006f944  pop     rsi
0x18006f945  pop     rbp
0x18006f946  pop     rbx
0x18006f947  retn
```
