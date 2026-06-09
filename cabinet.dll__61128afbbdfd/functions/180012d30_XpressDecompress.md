# XpressDecompress

- ea: `0x180012d30`
- end: `0x180012ded`
- name: `XpressDecompress`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012d30`
- `0x18001b625`

## import_xrefs

- `ntdll!RtlDecompressBufferEx` at `0x180012d84`
- `ntdll!RtlDecompressBufferEx` at `0x180012d84`

## pseudocode

```c
__int64 __fastcall XpressDecompress(unsigned __int16 *a1, const void *a2, size_t a3, void *a4, size_t Size, size_t *a6)
{
  size_t v6; // rbx
  int v7; // eax
  unsigned int v8; // edx
  __int64 v9; // rcx
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF

  v6 = Size;
  v11 = 0;
  if ( Size > 0x40000000 )
  {
    v8 = 111;
    *a6 = 0x40000000;
  }
  else if ( a3 )
  {
    if ( a3 > Size )
    {
      return 605;
    }
    else if ( a3 == Size )
    {
      memcpy_0(a4, a2, Size);
      v8 = 0;
      *a6 = v6;
    }
    else
    {
      v7 = RtlDecompressBufferEx(*a1, a4, (unsigned int)Size, a2, a3, &v11, *((_QWORD *)a1 + 4));
      v8 = 605;
      if ( !v7 )
      {
        v9 = v11;
        *a6 = v11;
        return v6 != v9 ? 0x25D : 0;
      }
    }
  }
  else
  {
    v8 = 122;
    *a6 = Size;
  }
  return v8;
}

```

## disassembly

```asm
0x180012d30  push    rbx
0x180012d32  sub     rsp, 40h
0x180012d36  mov     rbx, [rsp+48h+Size]
0x180012d3b  mov     r10, r8
0x180012d3e  mov     r8d, 40000000h
0x180012d44  mov     [rsp+48h+arg_0], 0
0x180012d4c  mov     r11, r9
0x180012d4f  cmp     rbx, r8
0x180012d52  ja      short loc_180012DB1
0x180012d54  test    r10, r10
0x180012d57  jz      short loc_180012DC0
0x180012d59  cmp     r10, rbx
0x180012d5c  ja      short loc_180012DCF
0x180012d5e  jz      short loc_180012DD6
0x180012d60  mov     rax, [rcx+20h]
0x180012d64  mov     r9, rdx
0x180012d67  movzx   ecx, word ptr [rcx]
0x180012d6a  mov     r8d, ebx
0x180012d6d  mov     [rsp+48h+var_18], rax
0x180012d72  mov     rdx, r11
0x180012d75  lea     rax, [rsp+48h+arg_0]
0x180012d7a  mov     [rsp+48h+var_20], rax
0x180012d7f  mov     [rsp+48h+var_28], r10d
0x180012d84  call    cs:__imp_RtlDecompressBufferEx
0x180012d8a  mov     edx, 25Dh
0x180012d8f  test    eax, eax
0x180012d91  jnz     short loc_180012DA9
0x180012d93  mov     ecx, [rsp+48h+arg_0]
0x180012d97  mov     rax, [rsp+48h+arg_28]
0x180012d9c  mov     [rax], rcx
0x180012d9f  sub     rcx, rbx
0x180012da2  neg     rcx
0x180012da5  sbb     ecx, ecx
0x180012da7  and     edx, ecx
0x180012da9  mov     eax, edx
0x180012dab  add     rsp, 40h
0x180012daf  pop     rbx
0x180012db0  retn
0x180012db1  mov     rax, [rsp+48h+arg_28]
0x180012db6  mov     edx, 6Fh ; 'o'
0x180012dbb  mov     [rax], r8
0x180012dbe  jmp     short loc_180012DA9
0x180012dc0  mov     rax, [rsp+48h+arg_28]
0x180012dc5  mov     edx, 7Ah ; 'z'
0x180012dca  mov     [rax], rbx
0x180012dcd  jmp     short loc_180012DA9
0x180012dcf  mov     edx, 25Dh; Src
0x180012dd4  jmp     short loc_180012DA9
0x180012dd6  mov     r8, rbx; Size
0x180012dd9  mov     rcx, r11; void *
0x180012ddc  call    memcpy_0
0x180012de1  mov     rax, [rsp+48h+arg_28]
0x180012de6  xor     edx, edx
0x180012de8  mov     [rax], rbx
0x180012deb  jmp     short loc_180012DA9
```
