# ValidateConnectionHandle

- ea: `0x180011790`
- end: `0x18001184d`
- name: `ValidateConnectionHandle`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180011860`
- `0x180017460`
- `0x1800186d0`
- `0x180018a80`
- `0x18001a720`
- `0x18001adb0`
- `0x18001f110`

## callees

- `0x180011790`
- `0x180020fd8`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall ValidateConnectionHandle(_QWORD *a1)
{
  PVOID *v2; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 || *a1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      WPP_SF_(v2[2], 15, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    return 1;
  }
  else
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      WPP_SF_(v2[2], 14, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x180011790  mov     [rsp+arg_0], rbx
0x180011795  push    rdi
0x180011796  sub     rsp, 20h
0x18001179a  mov     rbx, rcx
0x18001179d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117a4  lea     rdi, WPP_GLOBAL_Control
0x1800117ab  cmp     rcx, rdi
0x1800117ae  jz      short loc_1800117B6
0x1800117b0  test    byte ptr [rcx+1Ch], 40h
0x1800117b4  jnz     short loc_1800117D6
0x1800117b6  test    rbx, rbx
0x1800117b9  jnz     short loc_1800117FD
0x1800117bb  cmp     rcx, rdi
0x1800117be  jz      short loc_1800117C6
0x1800117c0  test    byte ptr [rcx+1Ch], 40h
0x1800117c4  jnz     short loc_18001182D
0x1800117c6  mov     eax, 1
0x1800117cb  mov     rbx, [rsp+28h+arg_0]
0x1800117d0  add     rsp, 20h
0x1800117d4  pop     rdi
0x1800117d5  retn
0x1800117d6  cmp     byte ptr [rcx+19h], 6
0x1800117da  jb      short loc_1800117B6
0x1800117dc  mov     rcx, [rcx+10h]
0x1800117e0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800117e7  mov     edx, 0Dh
0x1800117ec  mov     r9, rbx
0x1800117ef  call    WPP_SF_q
0x1800117f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117fb  jmp     short loc_1800117B6
0x1800117fd  cmp     qword ptr [rbx], 0
0x180011801  jnz     short loc_1800117BB
0x180011803  cmp     rcx, rdi
0x180011806  jz      short loc_180011829
0x180011808  test    byte ptr [rcx+1Ch], 40h
0x18001180c  jz      short loc_180011829
0x18001180e  cmp     byte ptr [rcx+19h], 6
0x180011812  jb      short loc_180011829
0x180011814  mov     rcx, [rcx+10h]
0x180011818  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001181f  mov     edx, 0Eh
0x180011824  call    WPP_SF_
0x180011829  xor     eax, eax
0x18001182b  jmp     short loc_1800117CB
0x18001182d  cmp     byte ptr [rcx+19h], 6
0x180011831  jb      short loc_1800117C6
0x180011833  mov     rcx, [rcx+10h]
0x180011837  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001183e  mov     edx, 0Fh
0x180011843  call    WPP_SF_
0x180011848  jmp     loc_1800117C6
```
