# NsiCliDeleteHostRoute

- ea: `0x1400070cc`
- end: `0x1400070e9`
- name: `NsiCliDeleteHostRoute`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c1a0`

## callees

- `0x1400070f0`

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
0x1400070cc  mov     [rsp+arg_0], ecx
0x1400070d0  sub     rsp, 28h
0x1400070d4  mov     ecx, 2
0x1400070d9  lea     rdx, [rsp+28h+arg_0]
0x1400070de  call    NsiCliDeleteHostRouteHelper
0x1400070e3  add     rsp, 28h
0x1400070e7  retn
```
