# HidpGetCollectionDescriptor

- ea: `0x1800085d8`
- end: `0x180008647`
- name: `HidpGetCollectionDescriptor`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180006ac8`
- `0x18003b0d0`

## callees

- `0x1800085d8`
- `0x18000cc90`
- `0x180027bd0`
- `0x18003802c`

## pseudocode

```c
__int64 __fastcall HidpGetCollectionDescriptor(__int64 a1, __int64 a2, void *a3, unsigned int *a4, char a5)
{
  __int64 CollectionDesc; // rax
  __int64 v8; // rdi
  unsigned int v9; // ecx
  unsigned int v10; // r10d
  void *v11; // rdx
  unsigned int v12; // ebx

  CollectionDesc = GetCollectionDesc(a1, a2, a3);
  v8 = CollectionDesc;
  if ( CollectionDesc )
  {
    v9 = *a4;
    v10 = *(unsigned __int16 *)(CollectionDesc + 26);
    v11 = *(void **)(CollectionDesc + 32);
    v12 = *a4 < v10 ? 0xC0000206 : 0;
    if ( *a4 >= v10 )
      v9 = *(unsigned __int16 *)(CollectionDesc + 26);
    if ( a5 )
      RtlCopyToUser(a3, v11, v9);
    else
      RtlCopyVolatileMemory(a3, v11, v9);
    *a4 = *(unsigned __int16 *)(v8 + 26);
  }
  else
  {
    return (unsigned int)-1073741762;
  }
  return v12;
}

```

## disassembly

```asm
0x1800085d8  push    rbx
0x1800085da  push    rsi
0x1800085db  push    rdi
0x1800085dc  push    r14
0x1800085de  sub     rsp, 28h
0x1800085e2  mov     r14, r9
0x1800085e5  mov     rsi, r8
0x1800085e8  call    GetCollectionDesc
0x1800085ed  mov     rdi, rax
0x1800085f0  test    rax, rax
0x1800085f3  jz      short loc_180008635
0x1800085f5  mov     ecx, [r14]
0x1800085f8  movzx   r10d, word ptr [rax+1Ah]
0x1800085fd  mov     rdx, [rax+20h]; Src
0x180008601  cmp     ecx, r10d
0x180008604  sbb     ebx, ebx
0x180008606  and     ebx, 0C0000206h
0x18000860c  cmp     ecx, r10d
0x18000860f  cmovnb  ecx, r10d
0x180008613  cmp     [rsp+48h+arg_20], 0
0x180008618  mov     r8d, ecx; Size
0x18000861b  mov     rcx, rsi; void *
0x18000861e  jz      short loc_180008627
0x180008620  call    RtlCopyToUser
0x180008625  jmp     short loc_18000862C
0x180008627  call    RtlCopyVolatileMemory
0x18000862c  movzx   eax, word ptr [rdi+1Ah]
0x180008630  mov     [r14], eax
0x180008633  jmp     short loc_18000863A
0x180008635  mov     ebx, 0C000003Eh
0x18000863a  mov     eax, ebx
0x18000863c  add     rsp, 28h
0x180008640  pop     r14
0x180008642  pop     rdi
0x180008643  pop     rsi
0x180008644  pop     rbx
0x180008645  retn
```
