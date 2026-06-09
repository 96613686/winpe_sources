# RfCommFreeMdlFrame

- ea: `0x1400134f4`
- end: `0x140013546`
- name: `RfCommFreeMdlFrame`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010810`
- `0x140011050`

## callees

- `0x140013480`
- `0x1400134f4`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140013518`
- `ntoskrnl!IoFreeMdl` at `0x140013518`

## pseudocode

```c
void __fastcall RfCommFreeMdlFrame(struct _MDL *a1)
{
  struct _MDL *Next; // rbx
  struct _MDL *i; // rdi

  Next = a1->Next;
  RfCommFreeMdlAndMemory(a1);
  for ( i = Next->Next; i; i = i->Next )
  {
    Next->Next = 0;
    IoFreeMdl(Next);
    Next = i;
  }
  RfCommFreeMdlAndMemory(Next);
}

```

## disassembly

```asm
0x1400134f4  mov     [rsp+arg_0], rbx
0x1400134f9  push    rdi
0x1400134fa  sub     rsp, 20h
0x1400134fe  mov     rbx, [rcx]
0x140013501  call    RfCommFreeMdlAndMemory
0x140013506  mov     rdi, [rbx]
0x140013509  test    rdi, rdi
0x14001350c  jz      short loc_140013532
0x14001350e  mov     rcx, rbx; Mdl
0x140013511  mov     qword ptr [rbx], 0
0x140013518  call    cs:__imp_IoFreeMdl
0x14001351f  nop     dword ptr [rax+rax+00h]
0x140013524  mov     rax, [rdi]
0x140013527  mov     rbx, rdi
0x14001352a  mov     rdi, rax
0x14001352d  test    rax, rax
0x140013530  jnz     short loc_14001350E
0x140013532  mov     rcx, rbx; Mdl
0x140013535  call    RfCommFreeMdlAndMemory
0x14001353a  mov     rbx, [rsp+28h+arg_0]
0x14001353f  add     rsp, 20h
0x140013543  pop     rdi
0x140013544  retn
```
