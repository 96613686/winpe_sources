# BCryptUnregisterConfigChangeNotify

- ea: `0x18000e790`
- end: `0x18000e7bb`
- name: `BCryptUnregisterConfigChangeNotify`
- size: `43`
- prototype: `NTSTATUS __stdcall(HANDLE hEvent)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000e790`
- `0x180010980`

## pseudocode

```c
NTSTATUS __stdcall BCryptUnregisterConfigChangeNotify(HANDLE hEvent)
{
  __int64 (__fastcall *v1)(HANDLE); // rax

  if ( *(_QWORD *)&WPP_MAIN_CB.SectorSize
    && (v1 = *(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)&WPP_MAIN_CB.SectorSize + 32LL)) != 0 )
  {
    return v1(hEvent);
  }
  else
  {
    return -1073741822;
  }
}

```

## disassembly

```asm
0x18000e790  sub     rsp, 28h
0x18000e794  mov     rax, qword ptr cs:WPP_MAIN_CB.SectorSize
0x18000e79b  test    rax, rax
0x18000e79e  jz      short loc_18000E7B0
0x18000e7a0  mov     rax, [rax+20h]
0x18000e7a4  test    rax, rax
0x18000e7a7  jz      short loc_18000E7B0
0x18000e7a9  call    _guard_dispatch_icall
0x18000e7ae  jmp     short loc_18000E7B5
0x18000e7b0  mov     eax, 0C0000002h
0x18000e7b5  add     rsp, 28h
0x18000e7b9  retn
```
