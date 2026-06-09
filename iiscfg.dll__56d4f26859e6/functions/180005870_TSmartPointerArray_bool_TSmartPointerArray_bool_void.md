# TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)

- ea: `0x180005870`
- end: `0x18000589e`
- name: `??1?$TSmartPointerArray@_N@@QEAA@XZ`
- size: `46`
- prototype: `void(void *)`
- caller_count: `39`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180005930`
- `0x18000593c`
- `0x180006310`
- `0x180009e84`
- `0x18000a1c8`
- `0x18000a9b4`
- `0x180010f14`
- `0x18001560c`
- `0x18001565c`
- `0x180015f34`
- `0x180016a18`
- `0x1800176b8`
- `0x180017814`
- `0x180017b70`
- `0x180019f9c`
- `0x18001b188`
- `0x18001c86c`
- `0x18001da08`
- `0x18001dd08`
- `0x180025bb4`
- `0x18002e5ae`
- `0x18002e68f`
- `0x18002e7e3`
- `0x18002e7f5`
- `0x18002e819`
- `0x18002e9b7`
- `0x18002e9c9`
- `0x18002e9db`
- `0x18002ea11`
- `0x18002eb88`
- `0x18002eb9a`
- `0x18002ebac`
- `0x18002ebbe`
- `0x18002ece6`
- `0x18002edb9`
- `0x18002edcb`
- `0x18002eddd`
- `0x18002edef`
- `0x18002efe0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000587c`
- `ole32!CoTaskMemFree` at `0x18000588b`
- `ole32!CoTaskMemFree` at `0x18000587c`
- `ole32!CoTaskMemFree` at `0x18000588b`

## pseudocode

```c
void __fastcall TSmartPointerArray<bool>::~TSmartPointerArray<bool>(LPVOID *a1)
{
  CoTaskMemFree(*a1);
  *a1 = 0;
  CoTaskMemFree(0);
  *a1 = 0;
}

```

## disassembly

```asm
0x180005870  push    rbx
0x180005872  sub     rsp, 20h
0x180005876  mov     rbx, rcx
0x180005879  mov     rcx, [rcx]; pv
0x18000587c  call    cs:__imp_CoTaskMemFree
0x180005882  mov     qword ptr [rbx], 0
0x180005889  xor     ecx, ecx; pv
0x18000588b  call    cs:__imp_CoTaskMemFree
0x180005891  mov     qword ptr [rbx], 0
0x180005898  add     rsp, 20h
0x18000589c  pop     rbx
0x18000589d  retn
```
