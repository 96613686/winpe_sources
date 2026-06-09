# XMLScrServProv::XMLScrServProv(void)

- ea: `0x140009728`
- end: `0x140009745`
- name: `??0XMLScrServProv@@AEAA@XZ`
- size: `29`
- prototype: `XMLScrServProv *__fastcall(XMLScrServProv *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1400096bc`

## pseudocode

```c
XMLScrServProv *__fastcall XMLScrServProv::XMLScrServProv(XMLScrServProv *this)
{
  XMLScrServProv *result; // rax

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &XMLScrServProv::`vftable';
  result = this;
  *((_DWORD *)this + 4) = 1;
  return result;
}

```

## disassembly

```asm
0x140009728  lea     rax, ??_7XMLScrServProv@@6B@; const XMLScrServProv::`vftable'
0x14000972f  mov     qword ptr [rcx+8], 0
0x140009737  mov     [rcx], rax
0x14000973a  mov     rax, rcx
0x14000973d  mov     dword ptr [rcx+10h], 1
0x140009744  retn
```
