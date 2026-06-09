# ReleaseDomNode(IXMLDOMNode * *)

- ea: `0x18000da60`
- end: `0x18000da8e`
- name: `?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z`
- size: `46`
- prototype: `void __fastcall(struct IXMLDOMNode **)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ad4c`
- `0x18000b000`
- `0x18000b2a4`
- `0x18000b6ec`
- `0x18000ba98`
- `0x18000c1e8`
- `0x18000c870`
- `0x18000d020`
- `0x18000d1bc`
- `0x18000f034`

## callees

- `0x18000da60`
- `0x18002b010`

## pseudocode

```c
void __fastcall ReleaseDomNode(struct IXMLDOMNode **a1)
{
  __int64 v2; // rcx

  if ( a1 )
  {
    v2 = (__int64)*a1;
    if ( v2 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000da60  test    rcx, rcx
0x18000da63  jz      short locret_18000DA8D
0x18000da65  push    rbx
0x18000da66  sub     rsp, 20h
0x18000da6a  mov     rbx, rcx
0x18000da6d  mov     rcx, [rcx]
0x18000da70  test    rcx, rcx
0x18000da73  jz      short loc_18000DA88
0x18000da75  mov     rax, [rcx]
0x18000da78  mov     rax, [rax+10h]
0x18000da7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da81  mov     qword ptr [rbx], 0
0x18000da88  add     rsp, 20h
0x18000da8c  pop     rbx
0x18000da8d  retn
```
