# WskCloseSocketIrpCompletion

- ea: `0x14001f7d0`
- end: `0x14001f827`
- name: `WskCloseSocketIrpCompletion`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004830`
- `0x14001f454`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001f7dc`
- `ntoskrnl!IoFreeIrp` at `0x14001f7dc`

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
0x14001f7d0  push    rbx
0x14001f7d2  sub     rsp, 20h
0x14001f7d6  mov     rcx, rdx; Irp
0x14001f7d9  mov     rbx, r8
0x14001f7dc  call    cs:__imp_IoFreeIrp
0x14001f7e3  nop     dword ptr [rax+rax+00h]
0x14001f7e8  mov     rax, [rbx+30h]
0x14001f7ec  lea     rcx, aWskclosesocket_3; "WskCloseSocket Done"
0x14001f7f3  mov     qword ptr [rbx+180h], 0
0x14001f7fe  call    _guard_dispatch_icall
0x14001f803  mov     rax, [rbx+30h]
0x14001f807  lea     rcx, aFreeingSockCon; "Freeing Sock Context"
0x14001f80e  call    _guard_dispatch_icall
0x14001f813  mov     rcx, rbx; P
0x14001f816  call    FreeSockContextCommon
0x14001f81b  mov     eax, 0C0000016h
0x14001f820  add     rsp, 20h
0x14001f824  pop     rbx
0x14001f825  retn
```
