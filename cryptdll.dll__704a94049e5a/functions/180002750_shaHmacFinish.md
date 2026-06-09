# shaHmacFinish

- ea: `0x180002750`
- end: `0x180002799`
- name: `shaHmacFinish`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001660`
- `0x180001b90`

## callees

- `0x180002750`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002776`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002776`
- `bcrypt!BCryptDestroyHash` at `0x18000276d`
- `bcrypt!BCryptDestroyHash` at `0x18000276d`

## pseudocode

```c
__int64 __fastcall shaHmacFinish(BCRYPT_HASH_HANDLE **a1)
{
  BCRYPT_HASH_HANDLE *v1; // rdi

  v1 = *a1;
  if ( *a1 )
  {
    if ( *v1 )
      BCryptDestroyHash(*v1);
    LocalFree(v1);
    *a1 = 0;
  }
  else
  {
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180002750  mov     [rsp+arg_0], rbx
0x180002755  push    rdi
0x180002756  sub     rsp, 20h
0x18000275a  mov     rdi, [rcx]
0x18000275d  mov     rbx, rcx
0x180002760  test    rdi, rdi
0x180002763  jz      short loc_180002790
0x180002765  mov     rcx, [rdi]; hHash
0x180002768  test    rcx, rcx
0x18000276b  jz      short loc_180002773
0x18000276d  call    cs:__imp_BCryptDestroyHash
0x180002773  mov     rcx, rdi; hMem
0x180002776  call    cs:__imp_LocalFree
0x18000277c  mov     qword ptr [rbx], 0
0x180002783  mov     rbx, [rsp+28h+arg_0]
0x180002788  xor     eax, eax
0x18000278a  add     rsp, 20h
0x18000278e  pop     rdi
0x18000278f  retn
0x180002790  mov     qword ptr [rcx], 0
0x180002797  jmp     short loc_180002783
```
