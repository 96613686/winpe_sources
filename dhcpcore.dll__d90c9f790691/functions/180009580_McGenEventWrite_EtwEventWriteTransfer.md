# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180009580`
- end: `0x1800095d2`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003544`
- `0x1800089f8`
- `0x180008b04`
- `0x180008c5c`
- `0x180008ce8`
- `0x180008d58`
- `0x180008e6c`
- `0x180008ed0`
- `0x180008f98`
- `0x180009038`
- `0x180009090`
- `0x180009108`
- `0x180009174`
- `0x180009264`
- `0x180009310`
- `0x1800093ac`
- `0x18000941c`
- `0x1800094f0`
- `0x18000e930`
- `0x18001f5f0`
- `0x18001f8e0`
- `0x180020058`
- `0x1800200d0`
- `0x180020154`
- `0x180021420`
- `0x180023684`
- `0x180023928`
- `0x180025350`
- `0x18003214c`
- `0x1800321c0`
- `0x180032228`

## callees

- `0x180009580`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800095b9`
- `ntdll!EtwEventWriteTransfer` at `0x1800095b9`

## pseudocode

```c

```

## disassembly

```asm
0x180009580  sub     rsp, 38h
0x180009584  mov     rcx, cs:qword_180061058
0x18000958b  mov     rax, [rsp+38h+arg_20]
0x180009590  test    rcx, rcx
0x180009593  jnz     short loc_1800095C4
0x180009595  mov     [rax], rcx
0x180009598  xor     r8d, r8d
0x18000959b  mov     [rax+8], ecx
0x18000959e  mov     [rax+0Ch], r8d
0x1800095a2  xor     r8d, r8d
0x1800095a5  mov     rcx, cs:Dhcp_Context
0x1800095ac  mov     [rsp+38h+var_10], rax
0x1800095b1  mov     [rsp+38h+var_18], r9d
0x1800095b6  xor     r9d, r9d
0x1800095b9  call    cs:__imp_EtwEventWriteTransfer
0x1800095bf  add     rsp, 38h
0x1800095c3  retn
0x1800095c4  mov     [rax], rcx
0x1800095c7  mov     r8d, 2
0x1800095cd  movzx   ecx, word ptr [rcx]
0x1800095d0  jmp     short loc_18000959B
```
