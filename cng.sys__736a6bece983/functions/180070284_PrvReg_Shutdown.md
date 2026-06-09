# PrvReg_Shutdown

- ea: `0x180070284`
- end: `0x180070349`
- name: `PrvReg_Shutdown`
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
- `0x180070284`
- `0x1800703f0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x180070331`
- `ntoskrnl!ExDeleteResourceLite` at `0x180070331`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180070292`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180070292`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800702a3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800702a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x180070316`
- `ntoskrnl!ExReleaseResourceLite` at `0x180070316`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180070322`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180070322`

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
0x180070284  push    rbx
0x180070286  push    rbp
0x180070287  push    rsi
0x180070288  push    rdi
0x180070289  push    r14
0x18007028b  sub     rsp, 20h
0x18007028f  mov     rbx, rcx
0x180070292  call    cs:__imp_KeEnterCriticalRegion
0x180070299  nop     dword ptr [rax+rax+00h]
0x18007029e  mov     dl, 1; Wait
0x1800702a0  mov     rcx, rbx; Resource
0x1800702a3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800702aa  nop     dword ptr [rax+rax+00h]
0x1800702af  mov     r14, [rbx+70h]
0x1800702b3  test    r14, r14
0x1800702b6  jz      short loc_180070313
0x1800702b8  mov     ebp, [rbx+68h]
0x1800702bb  xor     esi, esi
0x1800702bd  test    ebp, ebp
0x1800702bf  jz      short loc_1800702FC
0x1800702c1  lea     rdi, [r14+rsi*8]
0x1800702c5  test    rdi, rdi
0x1800702c8  jz      short loc_1800702F6
0x1800702ca  mov     rcx, [rdi]
0x1800702cd  test    rcx, rcx
0x1800702d0  jz      short loc_1800702F6
0x1800702d2  call    _PrvReg_OnFreeProviderNode
0x1800702d7  mov     rax, [rdi]
0x1800702da  mov     rcx, [rax]; P
0x1800702dd  test    rcx, rcx
0x1800702e0  jz      short loc_1800702E7
0x1800702e2  call    DataBlock_Free
0x1800702e7  mov     rcx, [rdi]; P
0x1800702ea  call    BCryptFree
0x1800702ef  mov     qword ptr [rdi], 0
0x1800702f6  inc     esi
0x1800702f8  cmp     esi, ebp
0x1800702fa  jb      short loc_1800702C1
0x1800702fc  mov     rcx, r14; P
0x1800702ff  call    BCryptFree
0x180070304  mov     dword ptr [rbx+68h], 0
0x18007030b  mov     qword ptr [rbx+70h], 0
0x180070313  mov     rcx, rbx; Resource
0x180070316  call    cs:__imp_ExReleaseResourceLite
0x18007031d  nop     dword ptr [rax+rax+00h]
0x180070322  call    cs:__imp_KeLeaveCriticalRegion
0x180070329  nop     dword ptr [rax+rax+00h]
0x18007032e  mov     rcx, rbx; Resource
0x180070331  call    cs:__imp_ExDeleteResourceLite
0x180070338  nop     dword ptr [rax+rax+00h]
0x18007033d  add     rsp, 20h
0x180070341  pop     r14
0x180070343  pop     rdi
0x180070344  pop     rsi
0x180070345  pop     rbp
0x180070346  pop     rbx
0x180070347  retn
```
