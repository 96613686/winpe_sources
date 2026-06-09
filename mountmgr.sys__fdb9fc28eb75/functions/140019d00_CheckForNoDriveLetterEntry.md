# CheckForNoDriveLetterEntry

- ea: `0x140019d00`
- end: `0x140019d8a`
- name: `CheckForNoDriveLetterEntry`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001ae0`
- `0x140019d00`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140019d31`
- `ntoskrnl!RtlCompareMemory` at `0x140019d31`

## pseudocode

```c
__int64 __fastcall CheckForNoDriveLetterEntry(
        _WORD *a1,
        int a2,
        const void *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        _BYTE *a6)
{
  if ( *a1 == 35 && a2 == 3 && a4 == *a5 && RtlCompareMemory(a5 + 1, a3, a4) == a4 )
  {
    *a6 = 1;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 86, a3, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140019d00  sub     rsp, 28h
0x140019d04  cmp     word ptr [rcx], 23h ; '#'
0x140019d08  mov     r10, r8
0x140019d0b  jnz     short loc_140019D51
0x140019d0d  cmp     edx, 3
0x140019d10  jnz     short loc_140019D51
0x140019d12  mov     rcx, [rsp+28h+arg_20]
0x140019d17  movzx   eax, word ptr [rcx]
0x140019d1a  cmp     r9d, eax
0x140019d1d  jnz     short loc_140019D51
0x140019d1f  mov     [rsp+28h+var_8], rbx
0x140019d24  add     rcx, 2; Source1
0x140019d28  mov     r8d, r9d; Length
0x140019d2b  mov     rdx, r10; Source2
0x140019d2e  mov     ebx, r9d
0x140019d31  call    cs:__imp_RtlCompareMemory
0x140019d38  nop     dword ptr [rax+rax+00h]
0x140019d3d  cmp     rax, rbx
0x140019d40  mov     rbx, [rsp+28h+var_8]
0x140019d45  jnz     short loc_140019D51
0x140019d47  mov     rax, [rsp+28h+arg_28]
0x140019d4c  mov     byte ptr [rax], 1
0x140019d4f  jmp     short loc_140019D82
0x140019d51  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d58  lea     rax, WPP_GLOBAL_Control
0x140019d5f  cmp     rcx, rax
0x140019d62  jz      short loc_140019D82
0x140019d64  mov     eax, [rcx+2Ch]
0x140019d67  test    al, 1
0x140019d69  jz      short loc_140019D82
0x140019d6b  cmp     byte ptr [rcx+29h], 1
0x140019d6f  jb      short loc_140019D82
0x140019d71  mov     rcx, [rcx+18h]
0x140019d75  mov     edx, 56h ; 'V'
0x140019d7a  xor     r9d, r9d
0x140019d7d  call    WPP_SF_L
0x140019d82  xor     eax, eax
0x140019d84  add     rsp, 28h
0x140019d88  retn
```
