# _dynamic_initializer_for__cRegPathBkgndTask__

- ea: `0x180002670`
- end: `0x180002697`
- name: `_dynamic_initializer_for__cRegPathBkgndTask__`
- size: `39`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002ec0`
- `0x18000fffc`

## string_xrefs

- `0x180002674`: `Software\Microsoft\Windows NT\CurrentVersion\Winlogon\IoTShellExtension\CBT`

## pseudocode

```c
int dynamic_initializer_for__cRegPathBkgndTask__()
{
  std::wstring::wstring(
    qword_180026650,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\IoTShellExtension\\CBT");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__cRegPathBkgndTask__);
}

```

## disassembly

```asm
0x180002670  sub     rsp, 28h
0x180002674  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000267b  lea     rcx, qword_180026650
0x180002682  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180002687  lea     rcx, _dynamic_atexit_destructor_for__cRegPathBkgndTask__
0x18000268e  add     rsp, 28h
0x180002692  jmp     atexit
```
