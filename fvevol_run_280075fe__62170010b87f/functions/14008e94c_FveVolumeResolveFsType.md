# FveVolumeResolveFsType

- ea: `0x14008e94c`
- end: `0x14008ea4c`
- name: `FveVolumeResolveFsType`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14008e180`

## callees

- `0x14008e94c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14008e973`
- `ntoskrnl!RtlCompareMemory` at `0x14008e9a3`
- `ntoskrnl!RtlCompareMemory` at `0x14008e9d0`
- `ntoskrnl!RtlCompareMemory` at `0x14008e9ff`
- `ntoskrnl!RtlCompareMemory` at `0x14008ea2b`
- `ntoskrnl!RtlCompareMemory` at `0x14008e973`
- `ntoskrnl!RtlCompareMemory` at `0x14008e9a3`
- `ntoskrnl!RtlCompareMemory` at `0x14008e9d0`
- `ntoskrnl!RtlCompareMemory` at `0x14008e9ff`
- `ntoskrnl!RtlCompareMemory` at `0x14008ea2b`

## pseudocode

```c
__int64 __fastcall FveVolumeResolveFsType(_WORD *a1)
{
  const void **v1; // rsi
  unsigned int v3; // ebx

  v1 = (const void **)(a1 + 4);
  if ( *a1 == 8 && RtlCompareMemory(*v1, L"NTFS", 8u) == 8 )
  {
    return 1;
  }
  else
  {
    if ( *a1 == 10 )
    {
      if ( RtlCompareMemory(*v1, L"exFAT", 0xAu) == 10 )
        return 2;
      if ( *a1 == 10 && RtlCompareMemory(*v1, L"FAT32", 0xAu) == 10 )
        return 3;
    }
    if ( *a1 == 6 && RtlCompareMemory(*v1, L"FAT", 6u) == 6 )
    {
      return 4;
    }
    else
    {
      v3 = 0;
      if ( *a1 == 8 && RtlCompareMemory(*v1, L"ReFS", 8u) == 8 )
        return 5;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14008e94c  push    rbx
0x14008e94e  push    rbp
0x14008e94f  push    rsi
0x14008e950  push    rdi
0x14008e951  sub     rsp, 28h
0x14008e955  mov     ebp, 8
0x14008e95a  lea     rsi, [rcx+8]
0x14008e95e  mov     rdi, rcx
0x14008e961  cmp     [rcx], bp
0x14008e964  jnz     short loc_14008E98C
0x14008e966  mov     rcx, [rsi]; Source1
0x14008e969  lea     rdx, aNtfs; "NTFS"
0x14008e970  mov     r8d, ebp; Length
0x14008e973  call    cs:__imp_RtlCompareMemory
0x14008e97a  nop     dword ptr [rax+rax+00h]
0x14008e97f  cmp     rax, rbp
0x14008e982  jnz     short loc_14008E98C
0x14008e984  lea     ebx, [rbp-7]
0x14008e987  jmp     loc_14008EA40
0x14008e98c  mov     ebx, 0Ah
0x14008e991  cmp     [rdi], bx
0x14008e994  jnz     short loc_14008E9E8
0x14008e996  mov     rcx, [rsi]; Source1
0x14008e999  lea     rdx, aExfat; "exFAT"
0x14008e9a0  mov     r8d, ebx; Length
0x14008e9a3  call    cs:__imp_RtlCompareMemory
0x14008e9aa  nop     dword ptr [rax+rax+00h]
0x14008e9af  cmp     rax, rbx
0x14008e9b2  jnz     short loc_14008E9BE
0x14008e9b4  mov     ebx, 2
0x14008e9b9  jmp     loc_14008EA40
0x14008e9be  cmp     [rdi], bx
0x14008e9c1  jnz     short loc_14008E9E8
0x14008e9c3  mov     rcx, [rsi]; Source1
0x14008e9c6  lea     rdx, aFat32; "FAT32"
0x14008e9cd  mov     r8, rbx; Length
0x14008e9d0  call    cs:__imp_RtlCompareMemory
0x14008e9d7  nop     dword ptr [rax+rax+00h]
0x14008e9dc  cmp     rax, rbx
0x14008e9df  jnz     short loc_14008E9E8
0x14008e9e1  mov     ebx, 3
0x14008e9e6  jmp     short loc_14008EA40
0x14008e9e8  mov     ebx, 6
0x14008e9ed  cmp     [rdi], bx
0x14008e9f0  jnz     short loc_14008EA17
0x14008e9f2  mov     rcx, [rsi]; Source1
0x14008e9f5  lea     rdx, aFat; "FAT"
0x14008e9fc  mov     r8d, ebx; Length
0x14008e9ff  call    cs:__imp_RtlCompareMemory
0x14008ea06  nop     dword ptr [rax+rax+00h]
0x14008ea0b  cmp     rax, rbx
0x14008ea0e  jnz     short loc_14008EA17
0x14008ea10  mov     ebx, 4
0x14008ea15  jmp     short loc_14008EA40
0x14008ea17  xor     ebx, ebx
0x14008ea19  cmp     [rdi], bp
0x14008ea1c  jnz     short loc_14008EA40
0x14008ea1e  mov     rcx, [rsi]; Source1
0x14008ea21  lea     rdx, aRefs; "ReFS"
0x14008ea28  mov     r8, rbp; Length
0x14008ea2b  call    cs:__imp_RtlCompareMemory
0x14008ea32  nop     dword ptr [rax+rax+00h]
0x14008ea37  cmp     rax, rbp
0x14008ea3a  lea     ecx, [rbx+5]
0x14008ea3d  cmovz   ebx, ecx
0x14008ea40  mov     eax, ebx
0x14008ea42  add     rsp, 28h
0x14008ea46  pop     rdi
0x14008ea47  pop     rsi
0x14008ea48  pop     rbp
0x14008ea49  pop     rbx
0x14008ea4a  retn
```
