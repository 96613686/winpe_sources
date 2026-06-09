# SpDeleteUserModeContext(unsigned __int64)

- ea: `0x1800194d0`
- end: `0x18001954c`
- name: `?SpDeleteUserModeContext@@YAJ_K@Z`
- size: `124`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000c5a4`
- `0x18000ebcc`
- `0x18000ec28`
- `0x1800194d0`

## pseudocode

```c
__int64 __fastcall SpDeleteUserModeContext(unsigned __int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids);
  v2 = WSTDeleteUserModeContext(a1);
  v3 = v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids, v2);
  return v3;
}

```

## disassembly

```asm
0x1800194d0  mov     [rsp+arg_0], rbx
0x1800194d5  push    rdi
0x1800194d6  sub     rsp, 20h
0x1800194da  mov     rbx, rcx
0x1800194dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194e4  lea     rdi, WPP_GLOBAL_Control
0x1800194eb  cmp     rcx, rdi
0x1800194ee  jz      short loc_18001950B
0x1800194f0  test    byte ptr [rcx+1Ch], 8
0x1800194f4  jz      short loc_18001950B
0x1800194f6  mov     rcx, [rcx+10h]
0x1800194fa  lea     r8, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids
0x180019501  mov     edx, 13h
0x180019506  call    WPP_SF_
0x18001950b  mov     rcx, rbx; unsigned __int64
0x18001950e  call    ?WSTDeleteUserModeContext@@YAJ_K@Z; WSTDeleteUserModeContext(unsigned __int64)
0x180019513  mov     ebx, eax
0x180019515  mov     rcx, cs:WPP_GLOBAL_Control
0x18001951c  cmp     rcx, rdi
0x18001951f  jz      short loc_18001953F
0x180019521  test    byte ptr [rcx+1Ch], 8
0x180019525  jz      short loc_18001953F
0x180019527  mov     rcx, [rcx+10h]
0x18001952b  lea     r8, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids
0x180019532  mov     edx, 14h
0x180019537  mov     r9d, eax
0x18001953a  call    WPP_SF_d
0x18001953f  mov     eax, ebx
0x180019541  mov     rbx, [rsp+28h+arg_0]
0x180019546  add     rsp, 20h
0x18001954a  pop     rdi
0x18001954b  retn
```
