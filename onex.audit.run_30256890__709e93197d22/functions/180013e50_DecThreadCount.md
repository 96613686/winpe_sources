# DecThreadCount

- ea: `0x180013e50`
- end: `0x180013ecf`
- name: `DecThreadCount`
- size: `127`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180023d80`
- `0x18002c010`
- `0x18002c1f0`
- `0x18002c8d0`
- `0x18002cae0`
- `0x18002cd10`
- `0x18002d020`

## callees

- `0x180010ae0`
- `0x180013e50`
- `0x18002d9a8`

## pseudocode

```c
__int64 __fastcall DecThreadCount(int a1, unsigned int a2, int a3)
{
  __int64 result; // rax
  __int64 v4; // r9

  result = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    result = WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, a3, a1, a2);
  v4 = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)&qword_18003DD5C);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    return WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v4);
  return result;
}

```

## disassembly

```asm
0x180013e50  push    rbx
0x180013e52  sub     rsp, 30h
0x180013e56  mov     eax, edx
0x180013e58  mov     r9, rcx
0x180013e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e62  lea     rbx, WPP_GLOBAL_Control
0x180013e69  cmp     rcx, rbx
0x180013e6c  jnz     short loc_180013E92
0x180013e6e  mov     r9d, 0FFFFFFFFh
0x180013e74  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x180013e7d  dec     r9d
0x180013e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e87  cmp     rcx, rbx
0x180013e8a  jnz     short loc_180013EAF
0x180013e8c  add     rsp, 30h
0x180013e90  pop     rbx
0x180013e91  retn
0x180013e92  test    dword ptr [rcx+44h], 400h
0x180013e99  jz      short loc_180013E6E
0x180013e9b  mov     rcx, [rcx+38h]
0x180013e9f  mov     edx, 20h ; ' '
0x180013ea4  mov     [rsp+38h+var_18], eax
0x180013ea8  call    WPP_SF_sd
0x180013ead  jmp     short loc_180013E6E
0x180013eaf  test    dword ptr [rcx+44h], 400h
0x180013eb6  jz      short loc_180013E8C
0x180013eb8  mov     rcx, [rcx+38h]
0x180013ebc  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180013ec3  mov     edx, 21h ; '!'
0x180013ec8  call    WPP_SF_d
0x180013ecd  jmp     short loc_180013E8C
```
