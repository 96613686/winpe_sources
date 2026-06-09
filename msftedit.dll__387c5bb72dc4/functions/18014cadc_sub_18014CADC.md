# sub_18014CADC

- ea: `0x18014cadc`
- end: `0x18014cb2c`
- name: `sub_18014CADC`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180120a90`

## callees

- `0x18014cadc`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014cb11`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014cb11`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014cb1b`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014cb1b`

## pseudocode

```c
void __fastcall sub_18014CADC(__int64 a1)
{
  void *v2; // rbx
  HDC v3; // rax

  if ( *(_QWORD *)(a1 + 16) )
  {
    v2 = *(void **)(a1 + 8);
    v3 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 24) + 336LL) + 48LL))(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 336LL));
    SelectObject(v3, v2);
    DeleteObject(*(HGDIOBJ *)(a1 + 16));
  }
}

```

## disassembly

```asm
0x18014cadc  mov     [rsp+arg_0], rbx
0x18014cae1  push    rdi
0x18014cae2  sub     rsp, 20h
0x18014cae6  cmp     qword ptr [rcx+10h], 0
0x18014caeb  mov     rdi, rcx
0x18014caee  jz      short loc_18014CB21
0x18014caf0  mov     rax, [rcx+18h]
0x18014caf4  mov     rbx, [rcx+8]
0x18014caf8  mov     rcx, [rax+150h]
0x18014caff  mov     rax, [rcx]
0x18014cb02  mov     rax, [rax+30h]
0x18014cb06  call    j__guard_dispatch_icall
0x18014cb0b  mov     rdx, rbx; h
0x18014cb0e  mov     rcx, rax; hdc
0x18014cb11  call    cs:SelectObject
0x18014cb17  mov     rcx, [rdi+10h]; ho
0x18014cb1b  call    cs:DeleteObject
0x18014cb21  mov     rbx, [rsp+28h+arg_0]
0x18014cb26  add     rsp, 20h
0x18014cb2a  pop     rdi
0x18014cb2b  retn
```
