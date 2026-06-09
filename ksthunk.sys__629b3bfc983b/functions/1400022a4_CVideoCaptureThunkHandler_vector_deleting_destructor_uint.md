# CVideoCaptureThunkHandler::`vector deleting destructor'(uint)

- ea: `0x1400022a4`
- end: `0x140002305`
- name: `??_ECVideoCaptureThunkHandler@@UEAAPEAXI@Z`
- size: `97`
- prototype: `void *__fastcall(PVOID P, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002250`

## callees

- `0x1400022a4`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x1400022ea`
- `ntoskrnl!ExFreePool` at `0x1400022ea`
- `ks!??1CBaseUnknown@@UEAA@XZ` at `0x1400022d6`
- `ks!??1CBaseUnknown@@UEAA@XZ` at `0x1400022d6`

## pseudocode

```c
_QWORD *__fastcall CVideoCaptureThunkHandler::`vector deleting destructor'(_QWORD *P, char a2)
{
  CBaseUnknown *v4; // rcx

  *P = &CVideoCaptureThunkHandler::`vftable';
  v4 = (CBaseUnknown *)(P + 1);
  *(_QWORD *)v4 = &CVideoCaptureThunkHandler::`vftable'{for `INonDelegatedUnknown'};
  P[2] = &CVideoCaptureThunkHandler::`vftable'{for `IIndirectedUnknown'};
  CBaseUnknown::~CBaseUnknown(v4);
  if ( (a2 & 1) != 0 )
    ExFreePool(P);
  return P;
}

```

## disassembly

```asm
0x1400022a4  mov     [rsp+arg_0], rbx
0x1400022a9  push    rdi
0x1400022aa  sub     rsp, 20h
0x1400022ae  mov     rdi, rcx
0x1400022b1  lea     rax, ??_7CVideoCaptureThunkHandler@@6B@; const CVideoCaptureThunkHandler::`vftable'
0x1400022b8  mov     [rcx], rax
0x1400022bb  mov     ebx, edx
0x1400022bd  add     rcx, 8
0x1400022c1  lea     rax, ??_7CVideoCaptureThunkHandler@@6BINonDelegatedUnknown@@@; const CVideoCaptureThunkHandler::`vftable'{for `INonDelegatedUnknown'}
0x1400022c8  mov     [rcx], rax
0x1400022cb  lea     rax, ??_7CVideoCaptureThunkHandler@@6BIIndirectedUnknown@@@; const CVideoCaptureThunkHandler::`vftable'{for `IIndirectedUnknown'}
0x1400022d2  mov     [rdi+10h], rax
0x1400022d6  call    cs:__imp_??1CBaseUnknown@@UEAA@XZ; CBaseUnknown::~CBaseUnknown(void)
0x1400022dd  nop     dword ptr [rax+rax+00h]
0x1400022e2  test    bl, 1
0x1400022e5  jz      short loc_1400022F6
0x1400022e7  mov     rcx, rdi; P
0x1400022ea  call    cs:__imp_ExFreePool
0x1400022f1  nop     dword ptr [rax+rax+00h]
0x1400022f6  mov     rbx, [rsp+28h+arg_0]
0x1400022fb  mov     rax, rdi
0x1400022fe  add     rsp, 20h
0x140002302  pop     rdi
0x140002303  retn
```
