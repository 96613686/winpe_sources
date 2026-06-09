# FTPHOST_CLASS::GetProcessId(ulong *)

- ea: `0x1800037e0`
- end: `0x1800037f9`
- name: `?GetProcessId@FTPHOST_CLASS@@UEAAJPEAK@Z`
- size: `25`
- prototype: `__int64 __fastcall(FTPHOST_CLASS *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800037e9`
- `KERNEL32!GetCurrentProcessId` at `0x1800037e9`

## pseudocode

```c
__int64 __fastcall FTPHOST_CLASS::GetProcessId(FTPHOST_CLASS *this, unsigned int *a2)
{
  *a2 = GetCurrentProcessId();
  return 0;
}

```

## disassembly

```asm
0x1800037e0  push    rbx
0x1800037e2  sub     rsp, 20h
0x1800037e6  mov     rbx, rdx
0x1800037e9  call    cs:__imp_GetCurrentProcessId
0x1800037ef  mov     [rbx], eax
0x1800037f1  xor     eax, eax
0x1800037f3  add     rsp, 20h
0x1800037f7  pop     rbx
0x1800037f8  retn
```
