# RciFree(tagRASCON_INFO *)

- ea: `0x180032c08`
- end: `0x180032c34`
- name: `?RciFree@@YAXPEAUtagRASCON_INFO@@@Z`
- size: `44`
- prototype: `void __fastcall(struct tagRASCON_INFO *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002dabc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c1e`

## pseudocode

```c
void __fastcall RciFree(LPVOID *a1)
{
  CoTaskMemFree(*a1);
  CoTaskMemFree(a1[1]);
  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
}

```

## disassembly

```asm
0x180032c08  push    rbx
0x180032c0a  sub     rsp, 20h
0x180032c0e  mov     rbx, rcx
0x180032c11  mov     rcx, [rcx]; pv
0x180032c14  call    cs:__imp_CoTaskMemFree
0x180032c1a  mov     rcx, [rbx+8]; pv
0x180032c1e  call    cs:__imp_CoTaskMemFree
0x180032c24  xorps   xmm0, xmm0
0x180032c27  movups  xmmword ptr [rbx], xmm0
0x180032c2a  movups  xmmword ptr [rbx+10h], xmm0
0x180032c2e  add     rsp, 20h
0x180032c32  pop     rbx
0x180032c33  retn
```
