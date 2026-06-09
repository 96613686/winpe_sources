# NetTerminateInternetServices()

- ea: `0x1000e380`
- end: `0x1000e3ac`
- name: `_NetTerminateInternetServices@0`
- size: `44`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x10014ea0`

## callees

- `0x1000e380`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1000e39b`
- `KERNEL32!FreeLibrary` at `0x1000e39b`

## pseudocode

```c
BOOL __stdcall NetTerminateInternetServices()
{
  BOOL result; // eax

  if ( hLibModule )
  {
    InternetCloseHandle((HINTERNET)dword_10040FB8);
    result = FreeLibrary(hLibModule);
    hLibModule = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1000e380  cmp     hLibModule, 0
0x1000e387  jz      short locret_1000E3AB
0x1000e389  push    dword_10040FB8
0x1000e38f  call    InternetCloseHandle
0x1000e395  push    hLibModule; hLibModule
0x1000e39b  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1000e3a1  mov     hLibModule, 0
0x1000e3ab  retn
```
