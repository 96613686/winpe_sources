# NsippDeregisterWorker

- ea: `0x1400052a0`
- end: `0x14000530e`
- name: `NsippDeregisterWorker`
- size: `110`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400052fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052fb`
- `ntoskrnl!IoFreeWorkItem` at `0x1400052ea`
- `ntoskrnl!IoFreeWorkItem` at `0x1400052ea`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x1400052da`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x1400052da`

## pseudocode

```c
void __fastcall NsippDeregisterWorker(PDEVICE_OBJECT DeviceObject, char *Context)
{
  __int64 v2; // xmm1_8
  __int128 v4; // xmm0
  __int64 v5; // rax
  _BYTE v6[24]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+40h] [rbp-18h]

  v2 = *((_QWORD *)Context + 5);
  *(_OWORD *)&v6[8] = 0;
  v8 = 0;
  v4 = *(_OWORD *)(Context + 24);
  v5 = *((_QWORD *)Context + 6);
  *(_QWORD *)&v6[16] = v2;
  *(_OWORD *)v6 = v4;
  v7 = v5;
  NsiDeregisterChangeNotificationEx(v6);
  IoFreeWorkItem(*((PIO_WORKITEM *)Context + 14));
  ExFreePoolWithTag(Context, 0);
}

```

## disassembly

```asm
0x1400052a0  push    rbx
0x1400052a2  sub     rsp, 50h
0x1400052a6  movsd   xmm1, qword ptr [rdx+28h]
0x1400052ab  lea     rcx, [rsp+58h+var_38]
0x1400052b0  xorps   xmm0, xmm0
0x1400052b3  xor     eax, eax
0x1400052b5  movdqu  xmmword ptr [rsp+58h+var_38+8], xmm0
0x1400052bb  mov     [rsp+58h+var_18], eax
0x1400052bf  mov     rbx, rdx
0x1400052c2  movups  xmm0, xmmword ptr [rdx+18h]
0x1400052c6  mov     rax, [rdx+30h]
0x1400052ca  movsd   qword ptr [rsp+58h+var_38+10h], xmm1
0x1400052d0  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x1400052d5  mov     [rsp+58h+var_20], rax
0x1400052da  call    cs:__imp_NsiDeregisterChangeNotificationEx
0x1400052e1  nop     dword ptr [rax+rax+00h]
0x1400052e6  mov     rcx, [rbx+70h]; IoWorkItem
0x1400052ea  call    cs:__imp_IoFreeWorkItem
0x1400052f1  nop     dword ptr [rax+rax+00h]
0x1400052f6  xor     edx, edx; Tag
0x1400052f8  mov     rcx, rbx; P
0x1400052fb  call    cs:__imp_ExFreePoolWithTag
0x140005302  nop     dword ptr [rax+rax+00h]
0x140005307  add     rsp, 50h
0x14000530b  pop     rbx
0x14000530c  retn
```
