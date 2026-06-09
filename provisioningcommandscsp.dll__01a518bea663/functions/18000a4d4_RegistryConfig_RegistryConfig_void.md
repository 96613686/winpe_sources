# RegistryConfig::RegistryConfig(void)

- ea: `0x18000a4d4`
- end: `0x18000a50e`
- name: `??0RegistryConfig@@QEAA@XZ`
- size: `58`
- prototype: `RegistryConfig *__fastcall(RegistryConfig *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006b10`
- `0x1800071d8`
- `0x180007360`
- `0x180008670`
- `0x180008cc0`
- `0x180009290`

## callees

- `0x180007c18`

## string_xrefs

- `0x18000a4e1`: `SOFTWARE\Microsoft\Provisioning\Commands`

## pseudocode

```c
RegistryConfig *__fastcall RegistryConfig::RegistryConfig(RegistryConfig *this)
{
  _WORD *v2; // rcx

  *(_QWORD *)this = -2147483646;
  *((_QWORD *)this + 4) = 7;
  *((_QWORD *)this + 3) = 0;
  v2 = (_WORD *)((char *)this + 8);
  *v2 = 0;
  std::wstring::assign(v2, L"SOFTWARE\\Microsoft\\Provisioning\\Commands");
  return this;
}

```

## disassembly

```asm
0x18000a4d4  push    rbx
0x18000a4d6  sub     rsp, 20h
0x18000a4da  mov     qword ptr [rcx], 0FFFFFFFF80000002h
0x18000a4e1  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Provisioning\\Comm"...
0x18000a4e8  xor     eax, eax
0x18000a4ea  mov     qword ptr [rcx+20h], 7
0x18000a4f2  mov     rbx, rcx
0x18000a4f5  mov     [rcx+18h], rax
0x18000a4f9  add     rcx, 8; void *
0x18000a4fd  mov     [rcx], ax
0x18000a500  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000a505  mov     rax, rbx
0x18000a508  add     rsp, 20h
0x18000a50c  pop     rbx
0x18000a50d  retn
```
