# EncodePasswordW

- ea: `0x1800086d4`
- end: `0x18000878f`
- name: `EncodePasswordW`
- size: `187`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180002250`
- `0x1800040f0`
- `0x1800047f0`
- `0x180004e74`
- `0x180005068`
- `0x180005d70`

## callees

- `0x180008518`
- `0x1800086d4`
- `0x180008798`

## pseudocode

```c
void __fastcall EncodePasswordW(__int16 *a1)
{
  _UNKNOWN **v2; // rcx
  __int16 i; // ax

  v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x10u, (const GUID *)WPP_017db3e43f20315255b30dbb12198294_Traceguids);
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    ReverseSzW(a1);
    for ( i = *a1; *a1; i = *a1 )
    {
      if ( i != 165 )
        *a1 = i ^ 0xA5;
      ++a1;
    }
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_((TRACEHANDLE)v2[2], 0x11u, (const GUID *)WPP_017db3e43f20315255b30dbb12198294_Traceguids);
}

```

## disassembly

```asm
0x1800086d4  mov     [rsp+arg_0], rbx
0x1800086d9  mov     [rsp+arg_8], rsi
0x1800086de  push    rdi
0x1800086df  sub     rsp, 20h
0x1800086e3  mov     rbx, rcx
0x1800086e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ed  lea     rsi, WPP_GLOBAL_Control
0x1800086f4  cmp     rcx, rsi
0x1800086f7  jz      short loc_180008721
0x1800086f9  test    byte ptr [rcx+1Ch], 4
0x1800086fd  jz      short loc_180008721
0x1800086ff  cmp     byte ptr [rcx+19h], 6
0x180008703  jb      short loc_180008721
0x180008705  mov     rcx, [rcx+10h]
0x180008709  lea     r8, WPP_017db3e43f20315255b30dbb12198294_Traceguids
0x180008710  mov     edx, 10h
0x180008715  call    WPP_SF_
0x18000871a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008721  test    rbx, rbx
0x180008724  jz      short loc_180008759
0x180008726  mov     rcx, rbx
0x180008729  call    ReverseSzW
0x18000872e  movzx   eax, word ptr [rbx]
0x180008731  test    ax, ax
0x180008734  jz      short loc_180008752
0x180008736  mov     ecx, 0A5h
0x18000873b  cmp     ax, cx
0x18000873e  jz      short loc_180008746
0x180008740  xor     ax, cx
0x180008743  mov     [rbx], ax
0x180008746  add     rbx, 2
0x18000874a  movzx   eax, word ptr [rbx]
0x18000874d  test    ax, ax
0x180008750  jnz     short loc_18000873B
0x180008752  mov     rcx, cs:WPP_GLOBAL_Control
0x180008759  cmp     rcx, rsi
0x18000875c  jz      short loc_18000877F
0x18000875e  test    byte ptr [rcx+1Ch], 4
0x180008762  jz      short loc_18000877F
0x180008764  cmp     byte ptr [rcx+19h], 6
0x180008768  jb      short loc_18000877F
0x18000876a  mov     rcx, [rcx+10h]
0x18000876e  lea     r8, WPP_017db3e43f20315255b30dbb12198294_Traceguids
0x180008775  mov     edx, 11h
0x18000877a  call    WPP_SF_
0x18000877f  mov     rbx, [rsp+28h+arg_0]
0x180008784  mov     rsi, [rsp+28h+arg_8]
0x180008789  add     rsp, 20h
0x18000878d  pop     rdi
0x18000878e  retn
```
