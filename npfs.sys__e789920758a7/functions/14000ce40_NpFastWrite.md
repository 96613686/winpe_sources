# NpFastWrite

- ea: `0x14000ce40`
- end: `0x14000ceff`
- name: `NpFastWrite`
- size: `191`
- prototype: `_BOOL8 __fastcall(__int64, __int64, unsigned int, __int64, int, void *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000ce40`
- `0x14000cff8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ce64`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ce64`
- `ntoskrnl!IofCompleteRequest` at `0x14000cecd`
- `ntoskrnl!IofCompleteRequest` at `0x14000cecd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cee3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cee3`

## pseudocode

```c
_BOOL8 __fastcall NpFastWrite(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, int a5, void *a6, __int64 a7)
{
  char v9; // al
  _QWORD *v10; // rbx
  bool v11; // di
  IRP *v12; // rcx
  _QWORD v14[4]; // [rsp+48h] [rbp-20h] BYREF

  v14[1] = v14;
  v14[0] = v14;
  KeEnterCriticalRegion();
  v9 = NpCommonWrite(a1, a6, a3, (__int64)KeGetCurrentThread(), a7, 0, (__int64)v14);
  v10 = (_QWORD *)v14[0];
  v11 = v9 != 0;
  while ( v10 != v14 )
  {
    v12 = (IRP *)(v10 - 21);
    v10 = (_QWORD *)*v10;
    IofCompleteRequest(v12, 2);
  }
  KeLeaveCriticalRegion();
  return v11;
}

```

## disassembly

```asm
0x14000ce40  mov     [rsp+arg_0], rbx
0x14000ce45  push    rdi
0x14000ce46  sub     rsp, 60h
0x14000ce4a  lea     rax, [rsp+68h+var_20]
0x14000ce4f  mov     ebx, r8d
0x14000ce52  mov     [rsp+68h+var_18], rax
0x14000ce57  mov     rdi, rcx
0x14000ce5a  lea     rax, [rsp+68h+var_20]
0x14000ce5f  mov     [rsp+68h+var_20], rax
0x14000ce64  call    cs:__imp_KeEnterCriticalRegion
0x14000ce6b  nop     dword ptr [rax+rax+00h]
0x14000ce70  mov     r9, gs:188h
0x14000ce79  lea     rax, [rsp+68h+var_20]
0x14000ce7e  mov     rdx, [rsp+68h+arg_28]
0x14000ce86  mov     r8d, ebx
0x14000ce89  mov     [rsp+68h+var_38], rax
0x14000ce8e  mov     rcx, rdi
0x14000ce91  mov     rax, [rsp+68h+arg_30]
0x14000ce99  mov     [rsp+68h+var_40], 0
0x14000cea2  mov     [rsp+68h+var_48], rax
0x14000cea7  call    NpCommonWrite
0x14000ceac  mov     rbx, [rsp+68h+var_20]
0x14000ceb1  test    al, al
0x14000ceb3  lea     rax, [rsp+68h+var_20]
0x14000ceb8  setnz   dil
0x14000cebc  cmp     rbx, rax
0x14000cebf  jz      short loc_14000CEE3
0x14000cec1  lea     rcx, [rbx-0A8h]; Irp
0x14000cec8  mov     dl, 2; PriorityBoost
0x14000ceca  mov     rbx, [rbx]
0x14000cecd  call    cs:__imp_IofCompleteRequest
0x14000ced4  nop     dword ptr [rax+rax+00h]
0x14000ced9  lea     rax, [rsp+68h+var_20]
0x14000cede  cmp     rbx, rax
0x14000cee1  jnz     short loc_14000CEC1
0x14000cee3  call    cs:__imp_KeLeaveCriticalRegion
0x14000ceea  nop     dword ptr [rax+rax+00h]
0x14000ceef  mov     rbx, [rsp+68h+arg_0]
0x14000cef4  movzx   eax, dil
0x14000cef8  add     rsp, 60h
0x14000cefc  pop     rdi
0x14000cefd  retn
```
