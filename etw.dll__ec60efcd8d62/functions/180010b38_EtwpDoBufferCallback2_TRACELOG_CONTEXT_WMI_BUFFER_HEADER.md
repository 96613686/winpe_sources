# EtwpDoBufferCallback2(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)

- ea: `0x180010b38`
- end: `0x180010b97`
- name: `?EtwpDoBufferCallback2@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z`
- size: `95`
- prototype: `unsigned int __fastcall(struct _TRACELOG_CONTEXT *, struct _WMI_BUFFER_HEADER *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f384`
- `0x18000f90c`
- `0x18000fc74`
- `0x18000ff6c`
- `0x1800108d0`
- `0x180014b10`

## callees

- `0x180016010`

## pseudocode

```c
__int64 __fastcall EtwpDoBufferCallback2(struct _TRACELOG_CONTEXT *a1, struct _WMI_BUFFER_HEADER *a2)
{
  __int64 v2; // rax
  __int64 v3; // r9
  __int64 v5; // rdx
  unsigned int (__fastcall *v6)(struct _WMI_BUFFER_HEADER *, __int64, _QWORD *, __int64); // rax
  _QWORD v8[2]; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+40h] [rbp-18h]
  int v10; // [rsp+44h] [rbp-14h]

  v2 = *((_QWORD *)a1 + 2);
  ++*((_DWORD *)a1 + 26);
  v3 = *((_QWORD *)a1 + 67);
  v5 = *((unsigned int *)a2 + 12);
  v8[0] = v2;
  v8[1] = (char *)a1 + 200;
  v9 = *((_DWORD *)a1 + 26);
  v6 = (unsigned int (__fastcall *)(struct _WMI_BUFFER_HEADER *, __int64, _QWORD *, __int64))*((_QWORD *)a1 + 66);
  v10 = 0;
  return v6(a2, v5, v8, v3) == 0 ? 0x4C7 : 0;
}

```

## disassembly

```asm
0x180010b38  sub     rsp, 58h
0x180010b3c  mov     rax, [rcx+10h]
0x180010b40  lea     r8, [rsp+58h+var_28]
0x180010b45  inc     dword ptr [rcx+68h]
0x180010b48  mov     r10, rcx
0x180010b4b  mov     r9, [rcx+218h]
0x180010b52  mov     r11, rdx
0x180010b55  mov     edx, [rdx+30h]
0x180010b58  mov     [rsp+58h+var_28], rax
0x180010b5d  lea     rax, [rcx+0C8h]
0x180010b64  mov     [rsp+58h+var_20], rax
0x180010b69  mov     eax, [rcx+68h]
0x180010b6c  mov     rcx, r11
0x180010b6f  mov     [rsp+58h+var_18], eax
0x180010b73  mov     rax, [r10+210h]
0x180010b7a  mov     [rsp+58h+var_14], 0
0x180010b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b87  neg     eax
0x180010b89  sbb     eax, eax
0x180010b8b  not     eax
0x180010b8d  and     eax, 4C7h
0x180010b92  add     rsp, 58h
0x180010b96  retn
```
