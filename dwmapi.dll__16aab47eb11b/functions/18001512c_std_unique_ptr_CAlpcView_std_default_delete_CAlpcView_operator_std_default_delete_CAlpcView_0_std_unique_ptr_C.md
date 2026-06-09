# std::unique_ptr<CAlpcView,std::default_delete<CAlpcView>>::operator=<std::default_delete<CAlpcView>,0>(std::unique_ptr<CAlpcView,std::default_delete<CAlpcView>> &&)

- ea: `0x18001512c`
- end: `0x180015158`
- name: `??$?4U?$default_delete@VCAlpcView@@@std@@$0A@@?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ad58`
- `0x180015224`

## callees

- `0x18001114c`
- `0x18001512c`

## pseudocode

```c
CAlpcView **__fastcall std::unique_ptr<CAlpcView>::operator=<std::default_delete<CAlpcView>,0>(
        CAlpcView **a1,
        CAlpcView **a2)
{
  CAlpcView *v2; // rax
  CAlpcView *v4; // rdx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    std::default_delete<CAlpcView>::operator()((__int64)a1, v4);
  return a1;
}

```

## disassembly

```asm
0x18001512c  push    rbx
0x18001512e  sub     rsp, 20h
0x180015132  mov     rax, [rdx]
0x180015135  mov     rbx, rcx
0x180015138  mov     qword ptr [rdx], 0
0x18001513f  mov     rdx, [rcx]
0x180015142  mov     [rcx], rax
0x180015145  test    rdx, rdx
0x180015148  jz      short loc_18001514F
0x18001514a  call    ??R?$default_delete@VCAlpcView@@@std@@QEBAXPEAVCAlpcView@@@Z; std::default_delete<CAlpcView>::operator()(CAlpcView *)
0x18001514f  mov     rax, rbx
0x180015152  add     rsp, 20h
0x180015156  pop     rbx
0x180015157  retn
```
