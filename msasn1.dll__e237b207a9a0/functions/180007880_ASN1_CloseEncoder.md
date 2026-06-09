# ASN1_CloseEncoder

- ea: `0x180007880`
- end: `0x1800078a5`
- name: `ASN1_CloseEncoder`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800077b0`
- `0x18000a830`

## callees

- `0x180007880`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000789a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000789a`

## pseudocode

```c
void __fastcall ASN1_CloseEncoder(_QWORD *a1)
{
  _QWORD *v1; // rax

  if ( a1 )
  {
    v1 = (_QWORD *)a1[8];
    if ( a1 != v1 )
      v1[9] = 0;
    LocalFree(a1);
  }
}

```

## disassembly

```asm
0x180007880  sub     rsp, 28h
0x180007884  test    rcx, rcx
0x180007887  jz      short loc_1800078A0
0x180007889  mov     rax, [rcx+40h]
0x18000788d  cmp     rcx, rax
0x180007890  jz      short loc_18000789A
0x180007892  mov     qword ptr [rax+48h], 0
0x18000789a  call    cs:__imp_LocalFree
0x1800078a0  add     rsp, 28h
0x1800078a4  retn
```
