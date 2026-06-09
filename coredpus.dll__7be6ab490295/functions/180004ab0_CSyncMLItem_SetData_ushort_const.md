# CSyncMLItem::SetData(ushort const *)

- ea: `0x180004ab0`
- end: `0x180004af8`
- name: `?SetData@CSyncMLItem@@QEAA?BJPEBG@Z`
- size: `72`
- prototype: `__int64 __fastcall(CSyncMLItem *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a760`
- `0x18001e454`
- `0x1800208f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ac4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ac4`
- `DMCmnUtils!CopyString` at `0x180004aec`

## pseudocode

```c
int __fastcall CSyncMLItem::SetData(HLOCAL *this, const unsigned __int16 *a2)
{
  unsigned __int16 **v2; // rbx

  v2 = (unsigned __int16 **)(this + 10);
  LocalFree(this[10]);
  *v2 = 0;
  return CopyString(a2, 0xFFFFFFFF, v2);
}

```

## disassembly

```asm
0x180004ab0  mov     [rsp+arg_0], rbx
0x180004ab5  push    rdi
0x180004ab6  sub     rsp, 20h
0x180004aba  lea     rbx, [rcx+50h]
0x180004abe  mov     rdi, rdx
0x180004ac1  mov     rcx, [rbx]; hMem
0x180004ac4  call    cs:__imp_LocalFree
0x180004acb  nop     dword ptr [rax+rax+00h]
0x180004ad0  mov     r8, rbx
0x180004ad3  mov     qword ptr [rbx], 0
0x180004ada  mov     edx, 0FFFFFFFFh
0x180004adf  mov     rcx, rdi
0x180004ae2  mov     rbx, [rsp+28h+arg_0]
0x180004ae7  add     rsp, 20h
0x180004aeb  pop     rdi
0x180004aec  jmp     cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
```
