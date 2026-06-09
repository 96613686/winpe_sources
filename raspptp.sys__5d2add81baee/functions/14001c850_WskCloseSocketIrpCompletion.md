# WskCloseSocketIrpCompletion

- ea: `0x14001c850`
- end: `0x14001c8a7`
- name: `WskCloseSocketIrpCompletion`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007710`
- `0x14001c2f0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001c85c`
- `ntoskrnl!IoFreeIrp` at `0x14001c85c`

## pseudocode

```c
__int64 __fastcall WskCloseSocketIrpCompletion(__int64 a1, IRP *a2, _QWORD *a3)
{
  void (__fastcall *v4)(const char *); // rax

  IoFreeIrp(a2);
  v4 = (void (__fastcall *)(const char *))a3[6];
  a3[48] = 0;
  v4("WskCloseSocket Done");
  ((void (__fastcall *)(const char *))a3[6])("Freeing Sock Context");
  FreeSockContextCommon(a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001c850  push    rbx
0x14001c852  sub     rsp, 20h
0x14001c856  mov     rcx, rdx; Irp
0x14001c859  mov     rbx, r8
0x14001c85c  call    cs:__imp_IoFreeIrp
0x14001c863  nop     dword ptr [rax+rax+00h]
0x14001c868  mov     rax, [rbx+30h]
0x14001c86c  lea     rcx, aWskclosesocket_3; "WskCloseSocket Done"
0x14001c873  mov     qword ptr [rbx+180h], 0
0x14001c87e  call    _guard_dispatch_icall
0x14001c883  mov     rax, [rbx+30h]
0x14001c887  lea     rcx, aFreeingSockCon; "Freeing Sock Context"
0x14001c88e  call    _guard_dispatch_icall
0x14001c893  mov     rcx, rbx; P
0x14001c896  call    FreeSockContextCommon
0x14001c89b  mov     eax, 0C0000016h
0x14001c8a0  add     rsp, 20h
0x14001c8a4  pop     rbx
0x14001c8a5  retn
```
