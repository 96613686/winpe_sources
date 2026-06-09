# ACpValidAllocatorHeader(CAccessibleBlock *,ulong,ulong)

- ea: `0x14000f44c`
- end: `0x14000f4c2`
- name: `?ACpValidAllocatorHeader@@YAJPEAVCAccessibleBlock@@KK@Z`
- size: `118`
- prototype: `__int64 __fastcall(struct CAccessibleBlock *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400107b4`

## callees

- `0x140001c34`
- `0x14000f44c`

## pseudocode

```c
__int64 __fastcall ACpValidAllocatorHeader(struct CAccessibleBlock *a1, int a2, int a3)
{
  unsigned int v3; // eax

  v3 = *(_DWORD *)a1;
  if ( !*(_DWORD *)a1 )
    return 3221225700LL;
  if ( (v3 & 0x1FF) != 0 )
    return 3221225700LL;
  if ( v3 <= (a3 - a2) << 9 )
    return 0;
  return 3221225700LL;
}

```

## disassembly

```asm
0x14000f44c  push    rbx
0x14000f44e  sub     rsp, 20h
0x14000f452  mov     eax, [rcx]
0x14000f454  test    eax, eax
0x14000f456  jnz     short loc_14000F45F
0x14000f458  mov     eax, 0C00000E4h
0x14000f45d  jmp     short loc_14000F4BB
0x14000f45f  test    eax, 1FFh
0x14000f464  jz      short loc_14000F46D
0x14000f466  mov     eax, 0C00000E4h
0x14000f46b  jmp     short loc_14000F4BB
0x14000f46d  sub     r8d, edx
0x14000f470  shl     r8d, 9
0x14000f474  cmp     eax, r8d
0x14000f477  jbe     short loc_14000F480
0x14000f479  mov     eax, 0C00000E4h
0x14000f47e  jmp     short loc_14000F4BB
0x14000f480  xor     eax, eax
0x14000f482  jmp     short loc_14000F4BB
0x14000f484  mov     ebx, eax
0x14000f486  lea     rax, WPP_GLOBAL_Control
0x14000f48d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f494  cmp     rcx, rax
0x14000f497  jz      short loc_14000F4B9
0x14000f499  mov     edx, [rcx+6Ch]
0x14000f49c  test    dl, 1
0x14000f49f  jz      short loc_14000F4B9
0x14000f4a1  mov     edx, 0Dh
0x14000f4a6  mov     r9d, ebx
0x14000f4a9  lea     r8, WPP_664e97eed756311217f592c2f10907d7_Traceguids
0x14000f4b0  mov     rcx, [rcx+58h]
0x14000f4b4  call    WPP_SF_d
0x14000f4b9  mov     eax, ebx
0x14000f4bb  add     rsp, 20h
0x14000f4bf  pop     rbx
0x14000f4c0  retn
```
