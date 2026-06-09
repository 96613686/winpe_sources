# CreatePszNode

- ea: `0x180025480`
- end: `0x1800254bd`
- name: `CreatePszNode`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180026cf8`

## callees

- `0x180025480`
- `0x180025ed0`
- `0x18002700c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800254a8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800254a8`

## pseudocode

```c
_QWORD *__fastcall CreatePszNode(const wchar_t *a1)
{
  wchar_t *v1; // rbx
  _QWORD *result; // rax

  v1 = StrDup(a1);
  if ( v1 )
  {
    result = DtlCreateSizedNode(0);
    if ( result )
    {
      result[2] = v1;
      return result;
    }
    GlobalFree(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x180025480  push    rbx
0x180025482  sub     rsp, 20h
0x180025486  call    StrDup
0x18002548b  mov     rbx, rax
0x18002548e  test    rax, rax
0x180025491  jz      short loc_1800254B4
0x180025493  xor     ecx, ecx
0x180025495  call    DtlCreateSizedNode
0x18002549a  test    rax, rax
0x18002549d  jz      short loc_1800254A5
0x18002549f  mov     [rax+10h], rbx
0x1800254a3  jmp     short loc_1800254B6
0x1800254a5  mov     rcx, rbx; hMem
0x1800254a8  call    cs:__imp_GlobalFree
0x1800254af  nop     dword ptr [rax+rax+00h]
0x1800254b4  xor     eax, eax
0x1800254b6  add     rsp, 20h
0x1800254ba  pop     rbx
0x1800254bb  retn
```
