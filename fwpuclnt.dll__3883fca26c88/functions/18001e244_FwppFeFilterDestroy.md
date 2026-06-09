# FwppFeFilterDestroy

- ea: `0x18001e244`
- end: `0x18001e2a2`
- name: `FwppFeFilterDestroy`
- size: `94`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001dfc8`
- `0x18001e074`
- `0x18001e130`
- `0x18001e428`

## callees

- `0x18000438c`
- `0x18001e244`
- `0x18003be30`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18001e284`
- `ntdll!RtlRemoveEntryHashTable` at `0x18001e284`

## pseudocode

```c
__int64 __fastcall FwppFeFilterDestroy(__int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( (*(_BYTE *)(v1 + 52) & 2) != 0 )
      DeleteFilterFromIndex(*(unsigned __int16 *)(v1 + 48), 0, *(_QWORD *)(v1 + 24), 0);
    if ( (*(_BYTE *)(v1 + 52) & 1) != 0 )
      RtlRemoveEntryHashTable((char *)&gFwppFilterEngine + 8, v1, 0);
  }
  return WfpMemFree(a1);
}

```

## disassembly

```asm
0x18001e244  mov     [rsp+arg_0], rbx
0x18001e249  push    rdi
0x18001e24a  sub     rsp, 30h
0x18001e24e  mov     rbx, [rcx]
0x18001e251  mov     rdi, rcx
0x18001e254  test    rbx, rbx
0x18001e257  jz      short loc_18001E290
0x18001e259  test    byte ptr [rbx+34h], 2
0x18001e25d  jz      short loc_18001E271
0x18001e25f  mov     r8, [rbx+18h]
0x18001e263  xor     r9d, r9d
0x18001e266  movzx   ecx, word ptr [rbx+30h]
0x18001e26a  xor     edx, edx
0x18001e26c  call    DeleteFilterFromIndex
0x18001e271  test    byte ptr [rbx+34h], 1
0x18001e275  jz      short loc_18001E290
0x18001e277  xor     r8d, r8d
0x18001e27a  lea     rcx, gFwppFilterEngine+8
0x18001e281  mov     rdx, rbx
0x18001e284  call    cs:__imp_RtlRemoveEntryHashTable
0x18001e28b  nop     dword ptr [rax+rax+00h]
0x18001e290  mov     rcx, rdi
0x18001e293  mov     rbx, [rsp+38h+arg_0]
0x18001e298  add     rsp, 30h
0x18001e29c  pop     rdi
0x18001e29d  jmp     WfpMemFree
```
