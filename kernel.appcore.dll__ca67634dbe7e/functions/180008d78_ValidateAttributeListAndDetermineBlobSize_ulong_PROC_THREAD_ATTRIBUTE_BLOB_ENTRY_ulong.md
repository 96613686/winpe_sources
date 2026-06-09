# ValidateAttributeListAndDetermineBlobSize(ulong,_PROC_THREAD_ATTRIBUTE_BLOB_ENTRY *,ulong *)

- ea: `0x180008d78`
- end: `0x180008e2e`
- name: `?ValidateAttributeListAndDetermineBlobSize@@YAJKPEAU_PROC_THREAD_ATTRIBUTE_BLOB_ENTRY@@PEAK@Z`
- size: `182`
- prototype: `__int64 __fastcall(unsigned int, struct _PROC_THREAD_ATTRIBUTE_BLOB_ENTRY *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e40`
- `0x180009050`

## callees

- `0x180008d78`

## pseudocode

```c
__int64 __fastcall ValidateAttributeListAndDetermineBlobSize(
        unsigned int a1,
        struct _PROC_THREAD_ATTRIBUTE_BLOB_ENTRY *a2,
        unsigned int *a3)
{
  int v3; // ebx
  unsigned int v6; // r10d
  unsigned int v7; // r9d
  int v8; // eax
  int v9; // ecx
  unsigned int v10; // edx
  unsigned int v11; // eax

  v3 = 0;
  *a3 = 0;
  v6 = 0;
  v7 = 24;
  while ( v6 < a1 )
  {
    switch ( *((_DWORD *)a2 + 4 * v6) )
    {
      case 0x20007:
        v8 = 8;
        v9 = 16;
        goto LABEL_12;
      case 0x2000E:
        v8 = 1;
        goto LABEL_10;
      case 0x2000F:
        v8 = 2;
LABEL_10:
        v9 = 4;
        goto LABEL_12;
    }
    if ( *((_DWORD *)a2 + 4 * v6) != 131088 )
      return 2147500033LL;
    v8 = 4;
    v9 = 8;
LABEL_12:
    if ( (v8 & v3) != 0 )
      return 2147942487LL;
    v10 = *((_DWORD *)a2 + 4 * v6 + 1);
    if ( v10 != v9 )
      return 2147942487LL;
    v3 |= v8;
    v11 = v7 + 16;
    if ( !v6 )
      v11 = v7;
    v7 = v11;
    if ( v10 > 8 || *((_DWORD *)a2 + 4 * v6) == 131088 )
      v7 = v10 + v11;
    ++v6;
  }
  *a3 = v7;
  return 0;
}

```

## disassembly

```asm
0x180008d78  push    rbx
0x180008d7a  push    rsi
0x180008d7b  push    rdi
0x180008d7c  xor     ebx, ebx
0x180008d7e  mov     dword ptr [r8], 0
0x180008d85  mov     rdi, rdx
0x180008d88  mov     esi, ecx
0x180008d8a  xor     r10d, r10d
0x180008d8d  lea     r9d, [rbx+18h]
0x180008d91  cmp     r10d, esi
0x180008d94  jnb     loc_180008E25
0x180008d9a  mov     edx, r10d
0x180008d9d  add     rdx, rdx
0x180008da0  mov     r11d, [rdi+rdx*8]
0x180008da4  mov     eax, r11d
0x180008da7  sub     eax, 20007h
0x180008dac  jz      short loc_180008DDA
0x180008dae  sub     eax, 7
0x180008db1  jz      short loc_180008DCE
0x180008db3  sub     eax, 1
0x180008db6  jz      short loc_180008DC7
0x180008db8  cmp     eax, 1
0x180008dbb  jnz     short loc_180008E17
0x180008dbd  mov     eax, 4
0x180008dc2  lea     ecx, [rax+4]
0x180008dc5  jmp     short loc_180008DE2
0x180008dc7  mov     eax, 2
0x180008dcc  jmp     short loc_180008DD3
0x180008dce  mov     eax, 1
0x180008dd3  mov     ecx, 4
0x180008dd8  jmp     short loc_180008DE2
0x180008dda  mov     eax, 8
0x180008ddf  lea     ecx, [rax+8]
0x180008de2  test    ebx, eax
0x180008de4  jnz     short loc_180008E1E
0x180008de6  mov     edx, [rdi+rdx*8+4]
0x180008dea  cmp     edx, ecx
0x180008dec  jnz     short loc_180008E1E
0x180008dee  or      ebx, eax
0x180008df0  lea     eax, [r9+10h]
0x180008df4  test    r10d, r10d
0x180008df7  cmovz   eax, r9d
0x180008dfb  mov     r9d, eax
0x180008dfe  cmp     edx, 8
0x180008e01  ja      short loc_180008E0C
0x180008e03  cmp     r11d, 20010h
0x180008e0a  jnz     short loc_180008E0F
0x180008e0c  add     r9d, edx
0x180008e0f  inc     r10d
0x180008e12  jmp     loc_180008D91
0x180008e17  mov     eax, 80004001h
0x180008e1c  jmp     short loc_180008E2A
0x180008e1e  mov     eax, 80070057h
0x180008e23  jmp     short loc_180008E2A
0x180008e25  mov     [r8], r9d
0x180008e28  xor     eax, eax
0x180008e2a  pop     rdi
0x180008e2b  pop     rsi
0x180008e2c  pop     rbx
0x180008e2d  retn
```
