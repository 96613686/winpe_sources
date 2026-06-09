# NsiCliDeleteHostRoute

- ea: `0x140004350`
- end: `0x14000436d`
- name: `NsiCliDeleteHostRoute`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f304`

## callees

- `0x140004374`

## pseudocode

```c
__int64 __fastcall NsiCliDeleteHostRoute(int a1)
{
  int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  return NsiCliDeleteHostRouteHelper(2u, (__int64)&v2);
}

```

## disassembly

```asm
0x140004350  mov     [rsp+arg_0], ecx
0x140004354  sub     rsp, 28h
0x140004358  mov     ecx, 2
0x14000435d  lea     rdx, [rsp+28h+arg_0]
0x140004362  call    NsiCliDeleteHostRouteHelper
0x140004367  add     rsp, 28h
0x14000436b  retn
```
