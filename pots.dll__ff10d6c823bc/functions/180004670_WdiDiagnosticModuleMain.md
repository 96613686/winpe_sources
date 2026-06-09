# WdiDiagnosticModuleMain

- ea: `0x180004670`
- end: `0x1800046f9`
- name: `WdiDiagnosticModuleMain`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x180004670`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x1800046d1`
- `ntdll!EtwEventRegister` at `0x1800046d1`
- `ntdll!EtwEventUnregister` at `0x180004689`
- `ntdll!EtwEventUnregister` at `0x1800046b6`
- `ntdll!EtwEventUnregister` at `0x180004689`
- `ntdll!EtwEventUnregister` at `0x1800046b6`

## pseudocode

```c

```

## disassembly

```asm
0x180004670  sub     rsp, 28h
0x180004674  test    edx, edx
0x180004676  jz      short loc_1800046BE
0x180004678  cmp     edx, 1
0x18000467b  jnz     short loc_1800046F2
0x18000467d  mov     rcx, cs:PoWdiProvHandle
0x180004684  test    rcx, rcx
0x180004687  jz      short loc_18000469A
0x180004689  call    cs:__imp_EtwEventUnregister
0x18000468f  mov     cs:PoWdiProvHandle, 0
0x18000469a  mov     rcx, cs:qword_180009190
0x1800046a1  mov     cs:dword_180009170, 0
0x1800046ab  mov     cs:qword_180009190, 0
0x1800046b6  call    cs:__imp_EtwEventUnregister
0x1800046bc  jmp     short loc_1800046F2
0x1800046be  lea     r9, PoWdiProvHandle
0x1800046c5  xor     r8d, r8d
0x1800046c8  xor     edx, edx
0x1800046ca  lea     rcx, POP_TS_ETW_PROVIDER
0x1800046d1  call    cs:__imp_EtwEventRegister
0x1800046d7  test    eax, eax
0x1800046d9  jz      short loc_1800046E6
0x1800046db  mov     cs:PoWdiProvHandle, 0
0x1800046e6  lea     rcx, dword_180009170
0x1800046ed  call    TraceLoggingRegister_EtwEventRegister_EtwEventSetInformation
0x1800046f2  xor     eax, eax
0x1800046f4  add     rsp, 28h
0x1800046f8  retn
```
