# CreatePszNode

- ea: `0x180008854`
- end: `0x18000888a`
- name: `CreatePszNode`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0c4`
- `0x18000aca4`

## callees

- `0x180008854`
- `0x180008b94`
- `0x18000ab44`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18000887c`
- `KERNEL32!GlobalFree` at `0x18000887c`

## pseudocode

```c
__int64 __fastcall CreatePszNode(const wchar_t *a1)
{
  wchar_t *v1; // rbx
  __int64 result; // rax

  v1 = StrDup(a1);
  if ( v1 )
  {
    result = DtlCreateSizedNode(0);
    if ( result )
    {
      *(_QWORD *)(result + 16) = v1;
      return result;
    }
    GlobalFree(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x180008854  push    rbx
0x180008856  sub     rsp, 20h
0x18000885a  call    StrDup
0x18000885f  mov     rbx, rax
0x180008862  test    rax, rax
0x180008865  jz      short loc_180008882
0x180008867  xor     ecx, ecx
0x180008869  call    DtlCreateSizedNode
0x18000886e  test    rax, rax
0x180008871  jz      short loc_180008879
0x180008873  mov     [rax+10h], rbx
0x180008877  jmp     short loc_180008884
0x180008879  mov     rcx, rbx; hMem
0x18000887c  call    cs:__imp_GlobalFree
0x180008882  xor     eax, eax
0x180008884  add     rsp, 20h
0x180008888  pop     rbx
0x180008889  retn
```
