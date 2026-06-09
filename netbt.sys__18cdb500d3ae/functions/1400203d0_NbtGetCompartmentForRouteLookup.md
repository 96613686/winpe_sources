# NbtGetCompartmentForRouteLookup

- ea: `0x1400203d0`
- end: `0x14002041d`
- name: `NbtGetCompartmentForRouteLookup`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001f7d0`

## callees

- `0x1400203d0`
- `0x1400248f8`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400203ff`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400203ff`

## pseudocode

```c
__int64 __fastcall NbtGetCompartmentForRouteLookup(__int64 a1, int *a2)
{
  int CurrentThreadCompartmentId; // eax

  *a2 = 0;
  if ( !a1 )
  {
    if ( KeGetCurrentIrql() )
    {
      CurrentThreadCompartmentId = 1;
      goto LABEL_4;
    }
LABEL_7:
    CurrentThreadCompartmentId = NdisGetCurrentThreadCompartmentId();
    goto LABEL_4;
  }
  if ( !*(_QWORD *)(a1 + 768) )
    goto LABEL_7;
  CurrentThreadCompartmentId = *(_DWORD *)(a1 + 568);
LABEL_4:
  *a2 = CurrentThreadCompartmentId;
  return 0;
}

```

## disassembly

```asm
0x1400203d0  push    rbx
0x1400203d2  sub     rsp, 20h
0x1400203d6  mov     dword ptr [rdx], 0
0x1400203dc  mov     rbx, rdx
0x1400203df  test    rcx, rcx
0x1400203e2  jz      short loc_1400203FF
0x1400203e4  cmp     qword ptr [rcx+300h], 0
0x1400203ec  jz      short loc_140020416
0x1400203ee  mov     eax, [rcx+238h]
0x1400203f4  mov     [rbx], eax
0x1400203f6  xor     eax, eax
0x1400203f8  add     rsp, 20h
0x1400203fc  pop     rbx
0x1400203fd  retn
0x1400203ff  call    cs:__imp_KeGetCurrentIrql
0x140020406  nop     dword ptr [rax+rax+00h]
0x14002040b  test    al, al
0x14002040d  jz      short loc_140020416
0x14002040f  mov     eax, 1
0x140020414  jmp     short loc_1400203F4
0x140020416  call    NdisGetCurrentThreadCompartmentId
0x14002041b  jmp     short loc_1400203F4
```
