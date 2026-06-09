# BCryptRegisterConfigChangeNotify

- ea: `0x18000e6a0`
- end: `0x18000e6cb`
- name: `BCryptRegisterConfigChangeNotify`
- size: `43`
- prototype: `NTSTATUS __stdcall(HANDLE *phEvent)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000e6a0`
- `0x180010980`

## pseudocode

```c
NTSTATUS __stdcall BCryptRegisterConfigChangeNotify(HANDLE *phEvent)
{
  __int64 (__fastcall *v1)(HANDLE *); // rax

  if ( *(_QWORD *)&WPP_MAIN_CB.SectorSize
    && (v1 = *(__int64 (__fastcall **)(HANDLE *))(*(_QWORD *)&WPP_MAIN_CB.SectorSize + 24LL)) != 0 )
  {
    return v1(phEvent);
  }
  else
  {
    return -1073741822;
  }
}

```

## disassembly

```asm
0x18000e6a0  sub     rsp, 28h
0x18000e6a4  mov     rax, qword ptr cs:WPP_MAIN_CB.SectorSize
0x18000e6ab  test    rax, rax
0x18000e6ae  jz      short loc_18000E6C0
0x18000e6b0  mov     rax, [rax+18h]
0x18000e6b4  test    rax, rax
0x18000e6b7  jz      short loc_18000E6C0
0x18000e6b9  call    _guard_dispatch_icall
0x18000e6be  jmp     short loc_18000E6C5
0x18000e6c0  mov     eax, 0C0000002h
0x18000e6c5  add     rsp, 28h
0x18000e6c9  retn
```
