# std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>::operator=<std::default_delete<D3DCoreModule>,0>(std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> &&)

- ea: `0x18000f574`
- end: `0x18000f5a0`
- name: `??$?4U?$default_delete@VD3DCoreModule@@@std@@$0A@@?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ade0`
- `0x18000fde0`

## callees

- `0x180005de4`
- `0x18000f574`

## pseudocode

```c
D3DCoreModule **__fastcall std::unique_ptr<D3DCoreModule>::operator=<std::default_delete<D3DCoreModule>,0>(
        D3DCoreModule **a1,
        D3DCoreModule **a2)
{
  D3DCoreModule *v2; // rax
  D3DCoreModule *v4; // rdx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    std::default_delete<D3DCoreModule>::operator()((__int64)a1, v4);
  return a1;
}

```

## disassembly

```asm
0x18000f574  push    rbx
0x18000f576  sub     rsp, 20h
0x18000f57a  mov     rax, [rdx]
0x18000f57d  mov     rbx, rcx
0x18000f580  mov     qword ptr [rdx], 0
0x18000f587  mov     rdx, [rcx]
0x18000f58a  mov     [rcx], rax
0x18000f58d  test    rdx, rdx
0x18000f590  jz      short loc_18000F597
0x18000f592  call    ??R?$default_delete@VD3DCoreModule@@@std@@QEBAXPEAVD3DCoreModule@@@Z; std::default_delete<D3DCoreModule>::operator()(D3DCoreModule *)
0x18000f597  mov     rax, rbx
0x18000f59a  add     rsp, 20h
0x18000f59e  pop     rbx
0x18000f59f  retn
```
