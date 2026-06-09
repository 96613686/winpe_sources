# _CManagerThread::AddRemoveRegisteredConfig_::_1_::catch$27

- ea: `0x180012590`
- end: `0x180012604`
- name: `_CManagerThread::AddRemoveRegisteredConfig_::_1_::catch$27`
- size: `116`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000d970`
- `0x180012590`

## pseudocode

```c
__int64 __fastcall CManagerThread::AddRemoveRegisteredConfig_::_1_::catch_27(__int64 a1, __int64 a2)
{
  int v2; // eax

  v2 = *(_DWORD *)(a2 + 48);
  *(_DWORD *)(a2 + 144) = v2;
  if ( v2 >= 0 )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      114,
      (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      **(_QWORD **)(a2 + 136),
      v2);
  return 0;
}

```

## disassembly

```asm
0x180012590  mov     [rsp+arg_8], rdx
0x180012595  push    rbp
0x180012596  sub     rsp, 30h
0x18001259a  mov     rbp, rdx
0x18001259d  mov     eax, [rbp+30h]
0x1800125a0  mov     [rbp+90h], eax
0x1800125a6  test    eax, eax
0x1800125a8  jns     short loc_1800125F3
0x1800125aa  lea     rdx, WPP_GLOBAL_Control
0x1800125b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125b8  cmp     rcx, rdx
0x1800125bb  jz      short loc_1800125E7
0x1800125bd  test    byte ptr [rcx+1Ch], 1
0x1800125c1  jz      short loc_1800125E7
0x1800125c3  mov     edx, 72h ; 'r'
0x1800125c8  mov     [rsp+38h+var_18], eax
0x1800125cc  mov     r9, [rbp+88h]
0x1800125d3  mov     r9, [r9]
0x1800125d6  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800125dd  mov     rcx, [rcx+10h]
0x1800125e1  call    WPP_SF_Sd
0x1800125e6  nop
0x1800125e7  mov     rax, 0
0x1800125f1  jmp     short loc_1800125FD
0x1800125f3  mov     rax, 1
0x1800125fd  add     rsp, 30h
0x180012601  pop     rbp
0x180012602  retn
```
