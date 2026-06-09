# NcaSyncedListDestroy

- ea: `0x18000b4f4`
- end: `0x18000b514`
- name: `NcaSyncedListDestroy`
- size: `32`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cfa0`
- `0x18000db90`
- `0x18000e5d0`
- `0x18000e6f8`
- `0x18000f430`
- `0x18000fe20`

## callees

- `0x1800190a0`

## pseudocode

```c
__int64 __fastcall NcaSyncedListDestroy(__int64 a1)
{
  __int64 result; // rax

  NcaCriticalSectionDestroy((LPCRITICAL_SECTION)a1);
  result = a1 + 48;
  *(_QWORD *)(a1 + 56) = a1 + 48;
  *(_QWORD *)(a1 + 48) = a1 + 48;
  return result;
}

```

## disassembly

```asm
0x18000b4f4  push    rbx
0x18000b4f6  sub     rsp, 20h
0x18000b4fa  mov     rbx, rcx
0x18000b4fd  call    NcaCriticalSectionDestroy
0x18000b502  lea     rax, [rbx+30h]
0x18000b506  mov     [rax+8], rax
0x18000b50a  mov     [rax], rax
0x18000b50d  add     rsp, 20h
0x18000b511  pop     rbx
0x18000b512  retn
```
