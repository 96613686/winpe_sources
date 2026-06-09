# NfsUpCallCreateRequestQueue

- ea: `0x140039328`
- end: `0x1400393ef`
- name: `NfsUpCallCreateRequestQueue`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d428`

## callees

- `0x140039328`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1400393b1`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400393b1`
- `ntoskrnl!KeInitializeEvent` at `0x1400393c6`
- `ntoskrnl!KeInitializeEvent` at `0x1400393c6`
- `ntoskrnl!ExAllocatePool2` at `0x14003935b`
- `ntoskrnl!ExAllocatePool2` at `0x14003935b`

## pseudocode

```c
__int64 __fastcall NfsUpCallCreateRequestQueue(_QWORD *a1)
{
  char *Pool2; // rax
  char *v3; // rbx
  unsigned int v4; // edi

  if ( !a1 || *a1 )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    Pool2 = (char *)ExAllocatePool2(66, 160, 1433626190);
    v3 = Pool2;
    if ( Pool2 )
    {
      v4 = 0;
      memset(Pool2, 0, 0xA0u);
      *((_DWORD *)v3 + 35) = 0;
      *((_DWORD *)v3 + 36) = 0;
      *((_DWORD *)v3 + 37) = 0;
      *((_DWORD *)v3 + 38) = 0;
      *(_QWORD *)v3 = 0;
      *((_DWORD *)v3 + 34) = 3;
      ExInitializeResourceLite((PERESOURCE)(v3 + 8));
      KeInitializeEvent((PRKEVENT)(v3 + 112), NotificationEvent, 0);
      *a1 = v3;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140039328  mov     [rsp+arg_0], rbx
0x14003932d  mov     [rsp+arg_8], rsi
0x140039332  push    rdi
0x140039333  sub     rsp, 20h
0x140039337  mov     rsi, rcx
0x14003933a  test    rcx, rcx
0x14003933d  jz      loc_1400393D7
0x140039343  cmp     qword ptr [rcx], 0
0x140039347  jnz     loc_1400393D7
0x14003934d  mov     edx, 0A0h
0x140039352  mov     r8d, 5573664Eh
0x140039358  lea     ecx, [rdx-5Eh]
0x14003935b  call    cs:__imp_ExAllocatePool2
0x140039362  nop     dword ptr [rax+rax+00h]
0x140039367  mov     rbx, rax
0x14003936a  test    rax, rax
0x14003936d  jnz     short loc_140039376
0x14003936f  mov     edi, 0C000009Ah
0x140039374  jmp     short loc_1400393DC
0x140039376  xor     edx, edx; Val
0x140039378  mov     r8d, 0A0h; Size
0x14003937e  mov     rcx, rbx; void *
0x140039381  xor     edi, edi
0x140039383  call    memset
0x140039388  mov     [rbx+8Ch], edi
0x14003938e  lea     rcx, [rbx+8]; Resource
0x140039392  mov     [rbx+90h], edi
0x140039398  mov     [rbx+94h], edi
0x14003939e  mov     [rbx+98h], edi
0x1400393a4  mov     [rbx], rdi
0x1400393a7  mov     dword ptr [rbx+88h], 3
0x1400393b1  call    cs:__imp_ExInitializeResourceLite
0x1400393b8  nop     dword ptr [rax+rax+00h]
0x1400393bd  lea     rcx, [rbx+70h]; Event
0x1400393c1  xor     r8d, r8d; State
0x1400393c4  xor     edx, edx; Type
0x1400393c6  call    cs:__imp_KeInitializeEvent
0x1400393cd  nop     dword ptr [rax+rax+00h]
0x1400393d2  mov     [rsi], rbx
0x1400393d5  jmp     short loc_1400393DC
0x1400393d7  mov     edi, 0C000000Dh
0x1400393dc  mov     rbx, [rsp+28h+arg_0]
0x1400393e1  mov     eax, edi
0x1400393e3  mov     rsi, [rsp+28h+arg_8]
0x1400393e8  add     rsp, 20h
0x1400393ec  pop     rdi
0x1400393ed  retn
```
