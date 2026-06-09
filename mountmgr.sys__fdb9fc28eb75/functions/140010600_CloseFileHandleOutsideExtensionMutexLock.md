# CloseFileHandleOutsideExtensionMutexLock

- ea: `0x140010600`
- end: `0x140010674`
- name: `CloseFileHandleOutsideExtensionMutexLock`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000a96c`
- `0x14000db54`
- `0x14000e340`
- `0x14000ecbc`
- `0x14000f680`
- `0x140010ef0`
- `0x140011500`
- `0x1400119a0`

## callees

- `0x140010600`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140010632`
- `ntoskrnl!KeReleaseMutex` at `0x140010632`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010661`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010661`
- `ntoskrnl!ZwClose` at `0x140010611`
- `ntoskrnl!ZwClose` at `0x140010641`
- `ntoskrnl!ZwClose` at `0x140010611`
- `ntoskrnl!ZwClose` at `0x140010641`

## pseudocode

```c
NTSTATUS __fastcall CloseFileHandleOutsideExtensionMutexLock(struct _KMUTANT *a1, void *a2)
{
  struct _KMUTANT *v4; // rdi

  if ( !a1 )
    return ZwClose(a2);
  v4 = a1 + 1;
  KeReleaseMutex(a1 + 1, 0);
  ZwClose(a2);
  return KeWaitForSingleObject(v4, Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x140010600  push    rbx
0x140010602  sub     rsp, 30h
0x140010606  mov     rbx, rdx
0x140010609  test    rcx, rcx
0x14001060c  jnz     short loc_140010624
0x14001060e  mov     rcx, rdx; Handle
0x140010611  call    cs:__imp_ZwClose
0x140010618  nop     dword ptr [rax+rax+00h]
0x14001061d  add     rsp, 30h
0x140010621  pop     rbx
0x140010622  retn
0x140010624  mov     [rsp+38h+arg_0], rdi
0x140010629  xor     edx, edx; Wait
0x14001062b  lea     rdi, [rcx+38h]
0x14001062f  mov     rcx, rdi; Mutex
0x140010632  call    cs:__imp_KeReleaseMutex
0x140010639  nop     dword ptr [rax+rax+00h]
0x14001063e  mov     rcx, rbx; Handle
0x140010641  call    cs:__imp_ZwClose
0x140010648  nop     dword ptr [rax+rax+00h]
0x14001064d  xor     r9d, r9d; Alertable
0x140010650  mov     [rsp+38h+Timeout], 0; Timeout
0x140010659  xor     r8d, r8d; WaitMode
0x14001065c  xor     edx, edx; WaitReason
0x14001065e  mov     rcx, rdi; Object
0x140010661  call    cs:__imp_KeWaitForSingleObject
0x140010668  nop     dword ptr [rax+rax+00h]
0x14001066d  mov     rdi, [rsp+38h+arg_0]
0x140010672  jmp     short loc_14001061D
```
