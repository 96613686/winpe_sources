# CallBackRegistered

- ea: `0x18000b494`
- end: `0x18000b4df`
- name: `CallBackRegistered`
- size: `75`
- prototype: `_BOOL8()`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b8dc`
- `0x18000bda0`
- `0x18000da5c`
- `0x18000e034`
- `0x18000e2b0`

## callees

- `0x18000b494`
- `0x180010be8`

## pseudocode

```c
_BOOL8 CallBackRegistered()
{
  BOOL v0; // ebx

  v0 = qword_18001A6E0 != 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      345,
      WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
      qword_18001A6E0 != 0);
  return v0;
}

```

## disassembly

```asm
0x18000b494  push    rbx
0x18000b496  sub     rsp, 20h
0x18000b49a  xor     ebx, ebx
0x18000b49c  cmp     cs:qword_18001A6E0, rbx
0x18000b4a3  setnz   bl
0x18000b4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4ad  lea     rax, WPP_GLOBAL_Control
0x18000b4b4  cmp     rcx, rax
0x18000b4b7  jz      short loc_18000B4D7
0x18000b4b9  test    byte ptr [rcx+1Ch], 20h
0x18000b4bd  jz      short loc_18000B4D7
0x18000b4bf  mov     rcx, [rcx+10h]
0x18000b4c3  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000b4ca  mov     edx, 159h
0x18000b4cf  mov     r9d, ebx
0x18000b4d2  call    WPP_SF_d
0x18000b4d7  mov     eax, ebx
0x18000b4d9  add     rsp, 20h
0x18000b4dd  pop     rbx
0x18000b4de  retn
```
