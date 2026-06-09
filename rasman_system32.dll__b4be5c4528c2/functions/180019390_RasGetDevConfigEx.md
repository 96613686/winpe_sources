# RasGetDevConfigEx

- ea: `0x180019390`
- end: `0x18001946a`
- name: `RasGetDevConfigEx`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800030d0`
- `0x180019390`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasGetDevConfigEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 666, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  v8 = SubmitLocalRequest(0x7Bu, a1, a2, a3, a4);
  v9 = v8;
  if ( !v8 )
    goto LABEL_10;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 667, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
LABEL_10:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 668, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180019390  push    rbx
0x180019392  push    rbp
0x180019393  push    rsi
0x180019394  push    rdi
0x180019395  push    r15
0x180019397  sub     rsp, 30h
0x18001939b  mov     rdi, r9
0x18001939e  mov     rsi, r8
0x1800193a1  mov     rbp, rdx
0x1800193a4  mov     rbx, rcx
0x1800193a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193ae  lea     r15, WPP_GLOBAL_Control
0x1800193b5  cmp     rcx, r15
0x1800193b8  jz      short loc_1800193DE
0x1800193ba  test    byte ptr [rcx+1Ch], 40h
0x1800193be  jz      short loc_1800193DE
0x1800193c0  cmp     byte ptr [rcx+19h], 6
0x1800193c4  jb      short loc_1800193DE
0x1800193c6  mov     rcx, [rcx+10h]
0x1800193ca  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800193d1  mov     edx, 29Ah
0x1800193d6  mov     r9, rbx
0x1800193d9  call    WPP_SF_q
0x1800193de  mov     ecx, 7Bh ; '{'
0x1800193e3  mov     [rsp+58h+var_38], rdi
0x1800193e8  mov     r9, rsi
0x1800193eb  mov     r8, rbp
0x1800193ee  mov     rdx, rbx
0x1800193f1  call    SubmitLocalRequest
0x1800193f6  mov     ebx, eax
0x1800193f8  test    eax, eax
0x1800193fa  jz      short loc_18001942C
0x1800193fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180019403  cmp     rcx, r15
0x180019406  jz      short loc_18001945C
0x180019408  test    byte ptr [rcx+1Ch], 40h
0x18001940c  jz      short loc_180019433
0x18001940e  cmp     byte ptr [rcx+19h], 2
0x180019412  jb      short loc_180019433
0x180019414  mov     rcx, [rcx+10h]
0x180019418  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001941f  mov     edx, 29Bh
0x180019424  mov     r9d, eax
0x180019427  call    WPP_SF_d
0x18001942c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019433  cmp     rcx, r15
0x180019436  jz      short loc_18001945C
0x180019438  test    byte ptr [rcx+1Ch], 40h
0x18001943c  jz      short loc_18001945C
0x18001943e  cmp     byte ptr [rcx+19h], 6
0x180019442  jb      short loc_18001945C
0x180019444  mov     rcx, [rcx+10h]
0x180019448  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001944f  mov     edx, 29Ch
0x180019454  mov     r9d, ebx
0x180019457  call    WPP_SF_d
0x18001945c  mov     eax, ebx
0x18001945e  add     rsp, 30h
0x180019462  pop     r15
0x180019464  pop     rdi
0x180019465  pop     rsi
0x180019466  pop     rbp
0x180019467  pop     rbx
0x180019468  retn
```
