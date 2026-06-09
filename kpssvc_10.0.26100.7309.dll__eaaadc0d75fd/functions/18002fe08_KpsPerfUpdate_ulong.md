# KpsPerfUpdate(ulong)

- ea: `0x18002fe08`
- end: `0x18002feb5`
- name: `?KpsPerfUpdate@@YAXK@Z`
- size: `173`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001e728`
- `0x1800210f4`
- `0x1800222f0`
- `0x180022708`
- `0x180027af8`
- `0x180028800`
- `0x18002aae8`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x18002fe08`

## pseudocode

```c
void __fastcall KpsPerfUpdate(unsigned int a1)
{
  _QWORD *v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids, a1);
    v2 = WPP_GLOBAL_Control;
  }
  switch ( a1 )
  {
    case 1u:
      _InterlockedIncrement(&dword_18003ADD8);
      break;
    case 2u:
      _InterlockedIncrement(&dword_18003ADDC);
      break;
    case 3u:
      _InterlockedIncrement(&dword_18003ADE0);
      break;
    case 4u:
      _InterlockedIncrement(&dword_18003ADE4);
      break;
    default:
      goto LABEL_13;
  }
  v2 = WPP_GLOBAL_Control;
LABEL_13:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 11, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids);
}

```

## disassembly

```asm
0x18002fe08  mov     [rsp+arg_0], rbx
0x18002fe0d  push    rdi
0x18002fe0e  sub     rsp, 20h
0x18002fe12  mov     ebx, ecx
0x18002fe14  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe1b  lea     rdi, WPP_GLOBAL_Control
0x18002fe22  cmp     rcx, rdi
0x18002fe25  jz      short loc_18002FE4C
0x18002fe27  test    byte ptr [rcx+1Ch], 20h
0x18002fe2b  jz      short loc_18002FE4C
0x18002fe2d  mov     rcx, [rcx+10h]
0x18002fe31  lea     r8, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids
0x18002fe38  mov     edx, 0Ah
0x18002fe3d  mov     r9d, ebx
0x18002fe40  call    WPP_SF_D
0x18002fe45  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe4c  cmp     ebx, 1
0x18002fe4f  jnz     short loc_18002FE5A
0x18002fe51  lock inc cs:dword_18003ADD8
0x18002fe58  jmp     short loc_18002FE82
0x18002fe5a  cmp     ebx, 2
0x18002fe5d  jnz     short loc_18002FE68
0x18002fe5f  lock inc cs:dword_18003ADDC
0x18002fe66  jmp     short loc_18002FE82
0x18002fe68  cmp     ebx, 3
0x18002fe6b  jnz     short loc_18002FE76
0x18002fe6d  lock inc cs:dword_18003ADE0
0x18002fe74  jmp     short loc_18002FE82
0x18002fe76  cmp     ebx, 4
0x18002fe79  jnz     short loc_18002FE89
0x18002fe7b  lock inc cs:dword_18003ADE4
0x18002fe82  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe89  cmp     rcx, rdi
0x18002fe8c  jz      short loc_18002FEA9
0x18002fe8e  test    byte ptr [rcx+1Ch], 20h
0x18002fe92  jz      short loc_18002FEA9
0x18002fe94  mov     rcx, [rcx+10h]
0x18002fe98  lea     r8, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids
0x18002fe9f  mov     edx, 0Bh
0x18002fea4  call    WPP_SF_
0x18002fea9  mov     rbx, [rsp+28h+arg_0]
0x18002feae  add     rsp, 20h
0x18002feb2  pop     rdi
0x18002feb3  retn
```
