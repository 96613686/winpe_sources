# CVideoCaptureThunkHandler::`vector deleting destructor'(uint)

- ea: `0x140002ba4`
- end: `0x140002c05`
- name: `??_ECVideoCaptureThunkHandler@@UEAAPEAXI@Z`
- size: `97`
- prototype: `_QWORD *__fastcall(_QWORD *P, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002b50`

## callees

- `0x140002ba4`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x140002bea`
- `ntoskrnl!ExFreePool` at `0x140002bea`
- `ks!??1CBaseUnknown@@UEAA@XZ` at `0x140002bd6`
- `ks!??1CBaseUnknown@@UEAA@XZ` at `0x140002bd6`

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
0x140002ba4  mov     [rsp+arg_0], rbx
0x140002ba9  push    rdi
0x140002baa  sub     rsp, 20h
0x140002bae  mov     rdi, rcx
0x140002bb1  lea     rax, ??_7CVideoCaptureThunkHandler@@6B@; const CVideoCaptureThunkHandler::`vftable'
0x140002bb8  mov     [rcx], rax
0x140002bbb  mov     ebx, edx
0x140002bbd  add     rcx, 8
0x140002bc1  lea     rax, ??_7CVideoCaptureThunkHandler@@6BINonDelegatedUnknown@@@; const CVideoCaptureThunkHandler::`vftable'{for `INonDelegatedUnknown'}
0x140002bc8  mov     [rcx], rax
0x140002bcb  lea     rax, ??_7CVideoCaptureThunkHandler@@6BIIndirectedUnknown@@@; const CVideoCaptureThunkHandler::`vftable'{for `IIndirectedUnknown'}
0x140002bd2  mov     [rdi+10h], rax
0x140002bd6  call    cs:__imp_??1CBaseUnknown@@UEAA@XZ; CBaseUnknown::~CBaseUnknown(void)
0x140002bdd  nop     dword ptr [rax+rax+00h]
0x140002be2  test    bl, 1
0x140002be5  jz      short loc_140002BF6
0x140002be7  mov     rcx, rdi; P
0x140002bea  call    cs:__imp_ExFreePool
0x140002bf1  nop     dword ptr [rax+rax+00h]
0x140002bf6  mov     rbx, [rsp+28h+arg_0]
0x140002bfb  mov     rax, rdi
0x140002bfe  add     rsp, 20h
0x140002c02  pop     rdi
0x140002c03  retn
```
