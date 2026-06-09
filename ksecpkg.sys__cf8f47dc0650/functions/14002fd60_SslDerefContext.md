# SslDerefContext

- ea: `0x14002fd60`
- end: `0x14002fde6`
- name: `SslDerefContext`
- size: `134`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140021bb0`
- `0x1400230a0`
- `0x140023430`
- `0x140028eb0`
- `0x140031100`
- `0x1400311e0`

## callees

- `0x140003e30`
- `0x1400045b0`
- `0x140010240`
- `0x14002fd60`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002fdbf`
- `ntoskrnl!ZwClose` at `0x14002fdbf`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fdd8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fdd8`

## pseudocode

```c
void __fastcall SslDerefContext(char *Entry)
{
  void *v2; // rcx
  void *v3; // rcx
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  GetExternalSchannelAlgorithmsDeferred();
  (*((void (__fastcall **)(char *, char *))SslLsaKernelFunctions + 5))(Entry + 320, &v4);
  if ( v4 )
  {
    v2 = (void *)*((_QWORD *)Entry + 35);
    if ( v2 )
    {
      ZwClose(v2);
      *((_QWORD *)Entry + 35) = 0;
    }
    v3 = (void *)*((_QWORD *)Entry + 37);
    if ( v3 )
      ObfDereferenceObject(v3);
    DeleteUserContext(Entry);
  }
}

```

## disassembly

```asm
0x14002fd60  push    rbx
0x14002fd62  sub     rsp, 20h
0x14002fd66  mov     rbx, rcx
0x14002fd69  mov     [rsp+28h+arg_0], 0
0x14002fd6e  call    GetExternalSchannelAlgorithmsDeferred
0x14002fd73  mov     rax, cs:?SslLsaKernelFunctions@@3PEAU_SECPKG_KERNEL_FUNCTIONS@@EA; _SECPKG_KERNEL_FUNCTIONS * SslLsaKernelFunctions
0x14002fd7a  lea     rcx, [rbx+140h]
0x14002fd81  lea     rdx, [rsp+28h+arg_0]
0x14002fd86  mov     rax, [rax+28h]
0x14002fd8a  call    _guard_dispatch_icall
0x14002fd8f  cmp     [rsp+28h+arg_0], 0
0x14002fd94  jnz     short loc_14002FD9D
0x14002fd96  add     rsp, 20h
0x14002fd9a  pop     rbx
0x14002fd9b  retn
0x14002fd9d  mov     rcx, [rbx+118h]; Handle
0x14002fda4  test    rcx, rcx
0x14002fda7  jnz     short loc_14002FDBF
0x14002fda9  mov     rcx, [rbx+128h]; Object
0x14002fdb0  test    rcx, rcx
0x14002fdb3  jnz     short loc_14002FDD8
0x14002fdb5  mov     rcx, rbx; Entry
0x14002fdb8  call    ?DeleteUserContext@@YAXPEAUCSslUserContext@@@Z; DeleteUserContext(CSslUserContext *)
0x14002fdbd  jmp     short loc_14002FD96
0x14002fdbf  call    cs:__imp_ZwClose
0x14002fdc6  nop     dword ptr [rax+rax+00h]
0x14002fdcb  mov     qword ptr [rbx+118h], 0
0x14002fdd6  jmp     short loc_14002FDA9
0x14002fdd8  call    cs:__imp_ObfDereferenceObject
0x14002fddf  nop     dword ptr [rax+rax+00h]
0x14002fde4  jmp     short loc_14002FDB5
```
