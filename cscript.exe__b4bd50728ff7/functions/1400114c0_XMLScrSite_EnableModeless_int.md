# XMLScrSite::EnableModeless(int)

- ea: `0x1400114c0`
- end: `0x1400114d1`
- name: `?EnableModeless@XMLScrSite@@UEAAJH@Z`
- size: `17`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall XMLScrSite::EnableModeless(XMLScrSite *this)
{
  return *(_BYTE *)(*((_QWORD *)this + 4) + 68LL) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1400114c0  mov     rax, [rcx+20h]
0x1400114c4  mov     cl, [rax+44h]
0x1400114c7  neg     cl
0x1400114c9  sbb     eax, eax
0x1400114cb  and     eax, 80004005h
0x1400114d0  retn
```
