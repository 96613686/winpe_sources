# GenImageDirectoryEntryToData(void *,uchar,ushort,ulong *)

- ea: `0x180026b18`
- end: `0x180026bb5`
- name: `?GenImageDirectoryEntryToData@@YAPEAXPEAXEGPEAK@Z`
- size: `157`
- prototype: `char *__fastcall(unsigned __int64, __int64, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180016f50`
- `0x18001a3f0`

## callees

- `0x180026abc`
- `0x180026b18`
- `0x180026cb4`

## pseudocode

```c
char *__fastcall GenImageDirectoryEntryToData(unsigned __int64 a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  char *v5; // rbx
  struct _IMAGE_NT_HEADERS64 *v6; // rcx
  __int64 VirtualAddress; // r8
  unsigned int Size; // eax

  v5 = (char *)(a1 & 0xFFFFFFFFFFFFFFFEuLL);
  if ( (a1 & 1) == 0 )
    v5 = (char *)a1;
  v6 = GenImageNtHeader(v5, 0);
  if ( !v6 )
    return 0;
  if ( v6->OptionalHeader.Magic == 267 )
  {
    if ( HIDWORD(v6->OptionalHeader.SizeOfHeapReserve) > 6 )
    {
      VirtualAddress = v6->OptionalHeader.DataDirectory[4].VirtualAddress;
      if ( (_DWORD)VirtualAddress )
      {
        Size = v6->OptionalHeader.DataDirectory[4].Size;
        goto LABEL_8;
      }
    }
    return 0;
  }
  if ( v6->OptionalHeader.Magic != 523 )
    return 0;
  if ( v6->OptionalHeader.NumberOfRvaAndSizes <= 6 )
    return 0;
  VirtualAddress = v6->OptionalHeader.DataDirectory[6].VirtualAddress;
  if ( !(_DWORD)VirtualAddress )
    return 0;
  Size = v6->OptionalHeader.DataDirectory[6].Size;
LABEL_8:
  *a4 = Size;
  if ( (unsigned int)VirtualAddress < v6->OptionalHeader.SizeOfHeaders )
    return &v5[VirtualAddress];
  else
    return (char *)GenAddressInSectionTable(v6, v5, VirtualAddress);
}

```

## disassembly

```asm
0x180026b18  mov     [rsp+arg_0], rbx
0x180026b1d  push    rdi
0x180026b1e  sub     rsp, 20h
0x180026b22  mov     rbx, rcx
0x180026b25  mov     rdi, r9
0x180026b28  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180026b2c  test    cl, 1
0x180026b2f  cmovz   rbx, rcx
0x180026b33  xor     edx, edx; struct _IMAGE_NT_HEADERS64 *
0x180026b35  mov     rcx, rbx; void *
0x180026b38  call    ?GenImageNtHeader@@YAPEAU_IMAGE_NT_HEADERS64@@PEAXPEAU1@@Z; GenImageNtHeader(void *,_IMAGE_NT_HEADERS64 *)
0x180026b3d  mov     rcx, rax; struct _IMAGE_NT_HEADERS64 *
0x180026b40  test    rax, rax
0x180026b43  jz      short loc_180026BA8
0x180026b45  mov     eax, 10Bh
0x180026b4a  cmp     [rcx+18h], ax
0x180026b4e  jnz     short loc_180026B80
0x180026b50  cmp     dword ptr [rcx+74h], 6
0x180026b54  jbe     short loc_180026BA8
0x180026b56  mov     r8d, [rcx+0A8h]; unsigned int
0x180026b5d  test    r8d, r8d
0x180026b60  jz      short loc_180026BA8
0x180026b62  mov     eax, [rcx+0ACh]
0x180026b68  mov     [rdi], eax
0x180026b6a  cmp     r8d, [rcx+54h]
0x180026b6e  jb      short loc_180026B7A
0x180026b70  mov     rdx, rbx; void *
0x180026b73  call    ?GenAddressInSectionTable@@YAPEAXPEAU_IMAGE_NT_HEADERS64@@PEAXK@Z; GenAddressInSectionTable(_IMAGE_NT_HEADERS64 *,void *,ulong)
0x180026b78  jmp     short loc_180026BAA
0x180026b7a  lea     rax, [rbx+r8]
0x180026b7e  jmp     short loc_180026BAA
0x180026b80  mov     eax, 20Bh
0x180026b85  cmp     [rcx+18h], ax
0x180026b89  jnz     short loc_180026BA8
0x180026b8b  cmp     dword ptr [rcx+84h], 6
0x180026b92  jbe     short loc_180026BA8
0x180026b94  mov     r8d, [rcx+0B8h]
0x180026b9b  test    r8d, r8d
0x180026b9e  jz      short loc_180026BA8
0x180026ba0  mov     eax, [rcx+0BCh]
0x180026ba6  jmp     short loc_180026B68
0x180026ba8  xor     eax, eax
0x180026baa  mov     rbx, [rsp+28h+arg_0]
0x180026baf  add     rsp, 20h
0x180026bb3  pop     rdi
0x180026bb4  retn
```
