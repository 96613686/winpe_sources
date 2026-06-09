# DllCanUnloadNow

- ea: `0x18001ee70`
- end: `0x18001eec2`
- name: `DllCanUnloadNow`
- size: `82`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180136810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ee88`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ee88`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_180163AA8 = 1;
  return (*(__int64 (__fastcall **)(__int64 *))(qword_180163AA0 + 24))(&qword_180163AA0) != 0;
}

```

## disassembly

```asm
0x18001ee70  sub     rsp, 28h
0x18001ee74  xor     r9d, r9d; Context
0x18001ee77  lea     rdx, InitFn; InitFn
0x18001ee7e  xor     r8d, r8d; Parameter
0x18001ee81  lea     rcx, InitOnce; InitOnce
0x18001ee88  call    cs:InitOnceExecuteOnce
0x18001ee8f  nop     dword ptr [rax+rax+00h]
0x18001ee94  mov     rax, cs:qword_180163AA0
0x18001ee9b  lea     rcx, qword_180163AA0
0x18001eea2  mov     cs:byte_180163AA8, 1
0x18001eea9  mov     rax, [rax+18h]
0x18001eead  call    cs:__guard_dispatch_icall_fptr
0x18001eeb3  xor     ecx, ecx
0x18001eeb5  test    eax, eax
0x18001eeb7  setnz   cl
0x18001eeba  mov     eax, ecx
0x18001eebc  add     rsp, 28h
0x18001eec0  retn
```
