# ComPtr<DockingProviders>::~ComPtr<DockingProviders>(void)

- ea: `0x1800086f0`
- end: `0x180008713`
- name: `??1?$ComPtr@VDockingProviders@@@@QEAA@XZ`
- size: `35`
- prototype: `unsigned int __fastcall(DockingProviders **)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d082`
- `0x18001d0e3`
- `0x18001d10f`
- `0x18001dc91`

## callees

- `0x1800086f0`
- `0x180016e2c`

## pseudocode

```c
unsigned int __fastcall ComPtr<DockingProviders>::~ComPtr<DockingProviders>(DockingProviders **a1)
{
  DockingProviders *v2; // rcx
  unsigned int result; // eax

  v2 = *a1;
  if ( v2 )
  {
    result = DockingProviders::Release(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800086f0  push    rbx
0x1800086f2  sub     rsp, 20h
0x1800086f6  mov     rbx, rcx
0x1800086f9  mov     rcx, [rcx]; this
0x1800086fc  test    rcx, rcx
0x1800086ff  jz      short loc_18000870D
0x180008701  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x180008706  mov     qword ptr [rbx], 0
0x18000870d  add     rsp, 20h
0x180008711  pop     rbx
0x180008712  retn
```
