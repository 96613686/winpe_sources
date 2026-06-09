# FveVolumeResolveFsType

- ea: `0x1400909fc`
- end: `0x140090afc`
- name: `FveVolumeResolveFsType`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140090230`

## callees

- `0x1400909fc`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140090a23`
- `ntoskrnl!RtlCompareMemory` at `0x140090a53`
- `ntoskrnl!RtlCompareMemory` at `0x140090a80`
- `ntoskrnl!RtlCompareMemory` at `0x140090aaf`
- `ntoskrnl!RtlCompareMemory` at `0x140090adb`
- `ntoskrnl!RtlCompareMemory` at `0x140090a23`
- `ntoskrnl!RtlCompareMemory` at `0x140090a53`
- `ntoskrnl!RtlCompareMemory` at `0x140090a80`
- `ntoskrnl!RtlCompareMemory` at `0x140090aaf`
- `ntoskrnl!RtlCompareMemory` at `0x140090adb`

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
0x1400909fc  push    rbx
0x1400909fe  push    rbp
0x1400909ff  push    rsi
0x140090a00  push    rdi
0x140090a01  sub     rsp, 28h
0x140090a05  mov     ebp, 8
0x140090a0a  lea     rsi, [rcx+8]
0x140090a0e  mov     rdi, rcx
0x140090a11  cmp     [rcx], bp
0x140090a14  jnz     short loc_140090A3C
0x140090a16  mov     rcx, [rsi]; Source1
0x140090a19  lea     rdx, aNtfs; "NTFS"
0x140090a20  mov     r8d, ebp; Length
0x140090a23  call    cs:__imp_RtlCompareMemory
0x140090a2a  nop     dword ptr [rax+rax+00h]
0x140090a2f  cmp     rax, rbp
0x140090a32  jnz     short loc_140090A3C
0x140090a34  lea     ebx, [rbp-7]
0x140090a37  jmp     loc_140090AF0
0x140090a3c  mov     ebx, 0Ah
0x140090a41  cmp     [rdi], bx
0x140090a44  jnz     short loc_140090A98
0x140090a46  mov     rcx, [rsi]; Source1
0x140090a49  lea     rdx, aExfat; "exFAT"
0x140090a50  mov     r8d, ebx; Length
0x140090a53  call    cs:__imp_RtlCompareMemory
0x140090a5a  nop     dword ptr [rax+rax+00h]
0x140090a5f  cmp     rax, rbx
0x140090a62  jnz     short loc_140090A6E
0x140090a64  mov     ebx, 2
0x140090a69  jmp     loc_140090AF0
0x140090a6e  cmp     [rdi], bx
0x140090a71  jnz     short loc_140090A98
0x140090a73  mov     rcx, [rsi]; Source1
0x140090a76  lea     rdx, aFat32; "FAT32"
0x140090a7d  mov     r8, rbx; Length
0x140090a80  call    cs:__imp_RtlCompareMemory
0x140090a87  nop     dword ptr [rax+rax+00h]
0x140090a8c  cmp     rax, rbx
0x140090a8f  jnz     short loc_140090A98
0x140090a91  mov     ebx, 3
0x140090a96  jmp     short loc_140090AF0
0x140090a98  mov     ebx, 6
0x140090a9d  cmp     [rdi], bx
0x140090aa0  jnz     short loc_140090AC7
0x140090aa2  mov     rcx, [rsi]; Source1
0x140090aa5  lea     rdx, aFat; "FAT"
0x140090aac  mov     r8d, ebx; Length
0x140090aaf  call    cs:__imp_RtlCompareMemory
0x140090ab6  nop     dword ptr [rax+rax+00h]
0x140090abb  cmp     rax, rbx
0x140090abe  jnz     short loc_140090AC7
0x140090ac0  mov     ebx, 4
0x140090ac5  jmp     short loc_140090AF0
0x140090ac7  xor     ebx, ebx
0x140090ac9  cmp     [rdi], bp
0x140090acc  jnz     short loc_140090AF0
0x140090ace  mov     rcx, [rsi]; Source1
0x140090ad1  lea     rdx, aRefs; "ReFS"
0x140090ad8  mov     r8, rbp; Length
0x140090adb  call    cs:__imp_RtlCompareMemory
0x140090ae2  nop     dword ptr [rax+rax+00h]
0x140090ae7  cmp     rax, rbp
0x140090aea  lea     ecx, [rbx+5]
0x140090aed  cmovz   ebx, ecx
0x140090af0  mov     eax, ebx
0x140090af2  add     rsp, 28h
0x140090af6  pop     rdi
0x140090af7  pop     rsi
0x140090af8  pop     rbp
0x140090af9  pop     rbx
0x140090afa  retn
```
