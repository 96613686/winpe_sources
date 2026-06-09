# RegistryConfig::RegistryConfig(void)

- ea: `0x18000aa28`
- end: `0x18000aa63`
- name: `??0RegistryConfig@@QEAA@XZ`
- size: `59`
- prototype: `RegistryConfig *__fastcall(RegistryConfig *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006e40`
- `0x18000751c`
- `0x1800076ac`
- `0x180008a70`
- `0x1800090e0`
- `0x1800096c0`

## callees

- `0x180007fac`

## string_xrefs

- `0x18000aa35`: `SOFTWARE\Microsoft\Provisioning\Commands`

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
0x18000aa28  push    rbx
0x18000aa2a  sub     rsp, 20h
0x18000aa2e  mov     qword ptr [rcx], 0FFFFFFFF80000002h
0x18000aa35  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Provisioning\\Comm"...
0x18000aa3c  xor     eax, eax
0x18000aa3e  mov     qword ptr [rcx+20h], 7
0x18000aa46  mov     rbx, rcx
0x18000aa49  mov     [rcx+18h], rax
0x18000aa4d  add     rcx, 8; void *
0x18000aa51  mov     [rcx], ax
0x18000aa54  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000aa59  mov     rax, rbx
0x18000aa5c  add     rsp, 20h
0x18000aa60  pop     rbx
0x18000aa61  retn
```
