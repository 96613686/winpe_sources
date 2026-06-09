# FatPopUpFileCorrupt

- ea: `0x14003958c`
- end: `0x140039604`
- name: `FatPopUpFileCorrupt`
- size: `120`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14002221c`
- `0x1400226b8`
- `0x14002d918`
- `0x14002e0cc`
- `0x14003062c`
- `0x140031e8c`
- `0x14004573c`
- `0x14004af08`

## callees

- `0x14003958c`
- `0x140044bac`

## import_xrefs

- `ntoskrnl!IoIsSystemThread` at `0x1400395c0`
- `ntoskrnl!IoIsSystemThread` at `0x1400395c0`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x1400395ec`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x1400395ec`

## pseudocode

```c
BOOLEAN __fastcall FatPopUpFileCorrupt(__int64 a1, struct _UNICODE_STRING *a2)
{
  BOOLEAN result; // al
  struct _KTHREAD *v5; // r8

  result = 4;
  if ( a2->Length != 1284 )
  {
    if ( !a2[33].Buffer )
      FatSetFullFileNameInFcb(a1);
    if ( IoIsSystemThread(*(PETHREAD *)(*(_QWORD *)(a1 + 40) + 152LL)) )
      v5 = 0;
    else
      v5 = *(struct _KTHREAD **)(*(_QWORD *)(a1 + 40) + 152LL);
    return IoRaiseInformationalHardError(-1073741566, a2 + 33, v5);
  }
  return result;
}

```

## disassembly

```asm
0x14003958c  mov     [rsp+arg_0], rbx
0x140039591  push    rdi
0x140039592  sub     rsp, 20h
0x140039596  mov     eax, 504h
0x14003959b  mov     rbx, rdx
0x14003959e  mov     rdi, rcx
0x1400395a1  cmp     [rdx], ax
0x1400395a4  jz      short loc_1400395F8
0x1400395a6  cmp     qword ptr [rdx+218h], 0
0x1400395ae  jnz     short loc_1400395B5
0x1400395b0  call    FatSetFullFileNameInFcb
0x1400395b5  mov     rcx, [rdi+28h]
0x1400395b9  mov     rcx, [rcx+98h]; Thread
0x1400395c0  call    cs:__imp_IoIsSystemThread
0x1400395c7  nop     dword ptr [rax+rax+00h]
0x1400395cc  test    al, al
0x1400395ce  jz      short loc_1400395D5
0x1400395d0  xor     r8d, r8d
0x1400395d3  jmp     short loc_1400395E0
0x1400395d5  mov     rax, [rdi+28h]
0x1400395d9  mov     r8, [rax+98h]; Thread
0x1400395e0  lea     rdx, [rbx+210h]; String
0x1400395e7  mov     ecx, 0C0000102h; ErrorStatus
0x1400395ec  call    cs:__imp_IoRaiseInformationalHardError
0x1400395f3  nop     dword ptr [rax+rax+00h]
0x1400395f8  mov     rbx, [rsp+28h+arg_0]
0x1400395fd  add     rsp, 20h
0x140039601  pop     rdi
0x140039602  retn
```
