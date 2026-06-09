# NtLmImportSecurityContext

- ea: `0x140021110`
- end: `0x140021159`
- name: `NtLmImportSecurityContext`
- size: `73`
- prototype: `__int64 __fastcall(__int64, __int64, PVOID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140020d50`
- `0x140021110`
- `0x14002fe40`

## pseudocode

```c
__int64 __fastcall NtLmImportSecurityContext(__int64 a1, __int64 a2, PVOID *a3)
{
  int KernelModeContext; // eax
  PVOID v5; // rcx
  unsigned int v6; // ebx
  PVOID P; // [rsp+48h] [rbp+20h] BYREF

  P = 0;
  KernelModeContext = NtLmCreateKernelModeContext(a1, a2, a1, (char **)&P);
  v5 = P;
  v6 = KernelModeContext;
  if ( KernelModeContext >= 0 )
    *a3 = P;
  if ( v5 )
    NtlmDerefContext(v5);
  return v6;
}

```

## disassembly

```asm
0x140021110  mov     [rsp+arg_0], rbx
0x140021115  push    rdi
0x140021116  sub     rsp, 20h
0x14002111a  mov     rdi, r8
0x14002111d  mov     [rsp+28h+P], 0
0x140021126  mov     r8, rcx
0x140021129  lea     r9, [rsp+28h+P]
0x14002112e  call    NtLmCreateKernelModeContext
0x140021133  mov     rcx, [rsp+28h+P]; P
0x140021138  mov     ebx, eax
0x14002113a  test    eax, eax
0x14002113c  js      short loc_140021141
0x14002113e  mov     [rdi], rcx
0x140021141  test    rcx, rcx
0x140021144  jz      short loc_14002114B
0x140021146  call    NtlmDerefContext
0x14002114b  mov     eax, ebx
0x14002114d  mov     rbx, [rsp+28h+arg_0]
0x140021152  add     rsp, 20h
0x140021156  pop     rdi
0x140021157  retn
```
