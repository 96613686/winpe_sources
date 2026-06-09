# CscStorepLowIoRenameFilePoster

- ea: `0x140029cf0`
- end: `0x140029d80`
- name: `CscStorepLowIoRenameFilePoster`
- size: `144`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14002a914`
- `0x140054e88`
- `0x1400570c0`
- `0x1400593dc`
- `0x140059edc`
- `0x14005cac4`
- `0x140081874`

## callees

- `0x14000c460`
- `0x140029cf0`
- `0x14002f440`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x140029d2e`
- `ntoskrnl!IoGetCurrentProcess` at `0x140029d2e`
- `ntoskrnl!PsIsThreadImpersonating` at `0x140029d4c`
- `ntoskrnl!PsIsThreadImpersonating` at `0x140029d4c`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoRenameFilePoster(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v8; // rcx
  _QWORD v10[23]; // [rsp+20h] [rbp-B8h] BYREF

  memset(v10, 0, 0x90u);
  v10[5] = a1;
  v10[6] = a2;
  v10[7] = a3;
  LOBYTE(v10[8]) = a4;
  LOBYTE(v8) = IoGetCurrentProcess() != (PEPROCESS)qword_14003BD08
            && !(unsigned __int8)PsIsThreadImpersonating(KeGetCurrentThread());
  return CscStorepLowIoPost(v8, CscStorepLowIoRenameFilePostedRoutine, v10);
}

```

## disassembly

```asm
0x140029cf0  push    rbx
0x140029cf2  push    rbp
0x140029cf3  push    rsi
0x140029cf4  push    rdi
0x140029cf5  sub     rsp, 0B8h
0x140029cfc  mov     rsi, r8
0x140029cff  mov     rdi, rdx
0x140029d02  mov     rbx, rcx
0x140029d05  xor     edx, edx; Val
0x140029d07  mov     r8d, 90h; Size
0x140029d0d  lea     rcx, [rsp+0D8h+var_B8]; void *
0x140029d12  mov     bpl, r9b
0x140029d15  call    memset
0x140029d1a  mov     [rsp+0D8h+var_90], rbx
0x140029d1f  mov     [rsp+0D8h+var_88], rdi
0x140029d24  mov     [rsp+0D8h+var_80], rsi
0x140029d29  mov     [rsp+0D8h+var_78], bpl
0x140029d2e  call    cs:__imp_IoGetCurrentProcess
0x140029d35  nop     dword ptr [rax+rax+00h]
0x140029d3a  cmp     rax, cs:qword_14003BD08
0x140029d41  jz      short loc_140029D60
0x140029d43  mov     rcx, gs:188h
0x140029d4c  call    cs:__imp_PsIsThreadImpersonating
0x140029d53  nop     dword ptr [rax+rax+00h]
0x140029d58  test    al, al
0x140029d5a  jnz     short loc_140029D60
0x140029d5c  mov     cl, 1
0x140029d5e  jmp     short loc_140029D62
0x140029d60  xor     cl, cl
0x140029d62  lea     r8, [rsp+0D8h+var_B8]
0x140029d67  lea     rdx, CscStorepLowIoRenameFilePostedRoutine
0x140029d6e  call    CscStorepLowIoPost
0x140029d73  add     rsp, 0B8h
0x140029d7a  pop     rdi
0x140029d7b  pop     rsi
0x140029d7c  pop     rbp
0x140029d7d  pop     rbx
0x140029d7e  retn
```
