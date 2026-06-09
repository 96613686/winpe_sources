# RciFree(tagRASCON_INFO *)

- ea: `0x180061db0`
- end: `0x180061ddc`
- name: `?RciFree@@YAXPEAUtagRASCON_INFO@@@Z`
- size: `44`
- prototype: `void __fastcall(struct tagRASCON_INFO *)`
- caller_count: `6`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18005ccfc`
- `0x18005d2d8`
- `0x18005d308`
- `0x18005d3f4`
- `0x18005d55c`
- `0x180061824`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180061dbc`
- `ole32!CoTaskMemFree` at `0x180061dc6`
- `ole32!CoTaskMemFree` at `0x180061dbc`
- `ole32!CoTaskMemFree` at `0x180061dc6`

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
0x180061db0  push    rbx
0x180061db2  sub     rsp, 20h
0x180061db6  mov     rbx, rcx
0x180061db9  mov     rcx, [rcx]; pv
0x180061dbc  call    cs:__imp_CoTaskMemFree
0x180061dc2  mov     rcx, [rbx+8]; pv
0x180061dc6  call    cs:__imp_CoTaskMemFree
0x180061dcc  xorps   xmm0, xmm0
0x180061dcf  movups  xmmword ptr [rbx], xmm0
0x180061dd2  movups  xmmword ptr [rbx+10h], xmm0
0x180061dd6  add     rsp, 20h
0x180061dda  pop     rbx
0x180061ddb  retn
```
