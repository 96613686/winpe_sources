# MupiAllocLegacyQueryPathRequest

- ea: `0x1400100c8`
- end: `0x140010131`
- name: `MupiAllocLegacyQueryPathRequest`
- size: `105`
- prototype: `__int64 __fastcall(__int64, const void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001cf8`

## callees

- `0x1400056c0`
- `0x1400100c8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400100ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400100ef`

## pseudocode

```c
__int64 __fastcall MupiAllocLegacyQueryPathRequest(__int64 a1, const void **a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rbx

  Pool2 = ExAllocatePool2(66, *(unsigned __int16 *)a2 + 24LL, 544240973);
  v5 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 8) = a1;
    *(_DWORD *)Pool2 = *(unsigned __int16 *)a2;
    memmove((void *)(Pool2 + 16), a2[1], *(unsigned __int16 *)a2);
  }
  return v5;
}

```

## disassembly

```asm
0x1400100c8  mov     [rsp+arg_0], rbx
0x1400100cd  mov     [rsp+arg_8], rsi
0x1400100d2  push    rdi
0x1400100d3  sub     rsp, 20h
0x1400100d7  mov     rdi, rdx
0x1400100da  mov     rsi, rcx
0x1400100dd  movzx   edx, word ptr [rdx]
0x1400100e0  mov     ecx, 42h ; 'B'
0x1400100e5  add     rdx, 18h
0x1400100e9  mov     r8d, 2070754Dh
0x1400100ef  call    cs:__imp_ExAllocatePool2
0x1400100f6  nop     dword ptr [rax+rax+00h]
0x1400100fb  mov     rbx, rax
0x1400100fe  test    rax, rax
0x140010101  jz      short loc_14001011D
0x140010103  mov     [rax+8], rsi
0x140010107  movzx   ecx, word ptr [rdi]
0x14001010a  mov     [rax], ecx
0x14001010c  lea     rcx, [rax+10h]; void *
0x140010110  movzx   r8d, word ptr [rdi]; Size
0x140010114  mov     rdx, [rdi+8]; Src
0x140010118  call    memmove
0x14001011d  mov     rsi, [rsp+28h+arg_8]
0x140010122  mov     rax, rbx
0x140010125  mov     rbx, [rsp+28h+arg_0]
0x14001012a  add     rsp, 20h
0x14001012e  pop     rdi
0x14001012f  retn
```
