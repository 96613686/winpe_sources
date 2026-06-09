# _dynamic_initializer_for__cRegPathShellExtension__

- ea: `0x1800026a0`
- end: `0x1800026c7`
- name: `_dynamic_initializer_for__cRegPathShellExtension__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002ec0`
- `0x18000fffc`

## string_xrefs

- `0x1800026a4`: `Software\Microsoft\Windows NT\CurrentVersion\Winlogon\IoTShellExtension`

## pseudocode

```c
int dynamic_initializer_for__cRegPathShellExtension__()
{
  std::wstring::wstring(
    qword_180026610,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\IoTShellExtension");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__cRegPathShellExtension__);
}

```

## disassembly

```asm
0x1800026a0  sub     rsp, 28h
0x1800026a4  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800026ab  lea     rcx, qword_180026610
0x1800026b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800026b7  lea     rcx, _dynamic_atexit_destructor_for__cRegPathShellExtension__
0x1800026be  add     rsp, 28h
0x1800026c2  jmp     atexit
```
