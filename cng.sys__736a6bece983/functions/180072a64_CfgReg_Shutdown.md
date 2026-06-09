# CfgReg_Shutdown

- ea: `0x180072a64`
- end: `0x180072b29`
- name: `CfgReg_Shutdown`
- size: `197`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006a680`

## callees

- `0x180018e40`
- `0x18004cb68`
- `0x180072a64`
- `0x180072cc0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x180072b11`
- `ntoskrnl!ExDeleteResourceLite` at `0x180072b11`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180072a72`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180072a72`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180072a83`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180072a83`
- `ntoskrnl!ExReleaseResourceLite` at `0x180072af6`
- `ntoskrnl!ExReleaseResourceLite` at `0x180072af6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180072b02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180072b02`

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
0x180072a64  push    rbx
0x180072a66  push    rbp
0x180072a67  push    rsi
0x180072a68  push    rdi
0x180072a69  push    r14
0x180072a6b  sub     rsp, 20h
0x180072a6f  mov     rbx, rcx
0x180072a72  call    cs:__imp_KeEnterCriticalRegion
0x180072a79  nop     dword ptr [rax+rax+00h]
0x180072a7e  mov     dl, 1; Wait
0x180072a80  mov     rcx, rbx; Resource
0x180072a83  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180072a8a  nop     dword ptr [rax+rax+00h]
0x180072a8f  mov     r14, [rbx+70h]
0x180072a93  test    r14, r14
0x180072a96  jz      short loc_180072AF3
0x180072a98  mov     ebp, [rbx+68h]
0x180072a9b  xor     esi, esi
0x180072a9d  test    ebp, ebp
0x180072a9f  jz      short loc_180072ADC
0x180072aa1  lea     rdi, [r14+rsi*8]
0x180072aa5  test    rdi, rdi
0x180072aa8  jz      short loc_180072AD6
0x180072aaa  mov     rcx, [rdi]
0x180072aad  test    rcx, rcx
0x180072ab0  jz      short loc_180072AD6
0x180072ab2  call    _CfgReg_OnFreeTableNode
0x180072ab7  mov     rax, [rdi]
0x180072aba  mov     rcx, [rax]; P
0x180072abd  test    rcx, rcx
0x180072ac0  jz      short loc_180072AC7
0x180072ac2  call    DataBlock_Free
0x180072ac7  mov     rcx, [rdi]; P
0x180072aca  call    BCryptFree
0x180072acf  mov     qword ptr [rdi], 0
0x180072ad6  inc     esi
0x180072ad8  cmp     esi, ebp
0x180072ada  jb      short loc_180072AA1
0x180072adc  mov     rcx, r14; P
0x180072adf  call    BCryptFree
0x180072ae4  mov     dword ptr [rbx+68h], 0
0x180072aeb  mov     qword ptr [rbx+70h], 0
0x180072af3  mov     rcx, rbx; Resource
0x180072af6  call    cs:__imp_ExReleaseResourceLite
0x180072afd  nop     dword ptr [rax+rax+00h]
0x180072b02  call    cs:__imp_KeLeaveCriticalRegion
0x180072b09  nop     dword ptr [rax+rax+00h]
0x180072b0e  mov     rcx, rbx; Resource
0x180072b11  call    cs:__imp_ExDeleteResourceLite
0x180072b18  nop     dword ptr [rax+rax+00h]
0x180072b1d  add     rsp, 20h
0x180072b21  pop     r14
0x180072b23  pop     rdi
0x180072b24  pop     rsi
0x180072b25  pop     rbp
0x180072b26  pop     rbx
0x180072b27  retn
```
