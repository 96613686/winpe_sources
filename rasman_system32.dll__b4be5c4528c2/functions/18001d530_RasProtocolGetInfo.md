# RasProtocolGetInfo

- ea: `0x18001d530`
- end: `0x18001d63d`
- name: `RasProtocolGetInfo`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001d530`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasProtocolGetInfo(__int64 a1, __int64 a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 442, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 443;
LABEL_20:
      WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  v7 = SubmitLocalRequest(0x43u, a1, a2);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 444, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 445;
    goto LABEL_20;
  }
  return v5;
}

```

## disassembly

```asm
0x18001d530  mov     [rsp+arg_0], rbx
0x18001d535  mov     [rsp+arg_8], rbp
0x18001d53a  push    rdi
0x18001d53b  sub     rsp, 20h
0x18001d53f  mov     rdi, rdx
0x18001d542  mov     rbx, rcx
0x18001d545  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d54c  lea     rbp, WPP_GLOBAL_Control
0x18001d553  cmp     rcx, rbp
0x18001d556  jz      short loc_18001D57C
0x18001d558  test    byte ptr [rcx+1Ch], 40h
0x18001d55c  jz      short loc_18001D57C
0x18001d55e  cmp     byte ptr [rcx+19h], 6
0x18001d562  jb      short loc_18001D57C
0x18001d564  mov     rcx, [rcx+10h]
0x18001d568  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d56f  mov     edx, 1BAh
0x18001d574  mov     r9, rbx
0x18001d577  call    WPP_SF_q
0x18001d57c  mov     rcx, rbx
0x18001d57f  call    ValidatePortHandle
0x18001d584  test    eax, eax
0x18001d586  jnz     short loc_18001D5B4
0x18001d588  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d58f  mov     ebx, 259h
0x18001d594  cmp     rcx, rbp
0x18001d597  jz      loc_18001D62A
0x18001d59d  test    byte ptr [rcx+1Ch], 40h
0x18001d5a1  jz      loc_18001D62A
0x18001d5a7  cmp     byte ptr [rcx+19h], 2
0x18001d5ab  jb      short loc_18001D62A
0x18001d5ad  mov     edx, 1BBh
0x18001d5b2  jmp     short loc_18001D617
0x18001d5b4  mov     ecx, 43h ; 'C'
0x18001d5b9  mov     r8, rdi
0x18001d5bc  mov     rdx, rbx
0x18001d5bf  call    SubmitLocalRequest
0x18001d5c4  mov     ebx, eax
0x18001d5c6  test    eax, eax
0x18001d5c8  jz      short loc_18001D5FA
0x18001d5ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5d1  cmp     rcx, rbp
0x18001d5d4  jz      short loc_18001D62A
0x18001d5d6  test    byte ptr [rcx+1Ch], 40h
0x18001d5da  jz      short loc_18001D601
0x18001d5dc  cmp     byte ptr [rcx+19h], 2
0x18001d5e0  jb      short loc_18001D601
0x18001d5e2  mov     rcx, [rcx+10h]
0x18001d5e6  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d5ed  mov     edx, 1BCh
0x18001d5f2  mov     r9d, eax
0x18001d5f5  call    WPP_SF_d
0x18001d5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d601  cmp     rcx, rbp
0x18001d604  jz      short loc_18001D62A
0x18001d606  test    byte ptr [rcx+1Ch], 40h
0x18001d60a  jz      short loc_18001D62A
0x18001d60c  cmp     byte ptr [rcx+19h], 6
0x18001d610  jb      short loc_18001D62A
0x18001d612  mov     edx, 1BDh
0x18001d617  mov     rcx, [rcx+10h]
0x18001d61b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d622  mov     r9d, ebx
0x18001d625  call    WPP_SF_d
0x18001d62a  mov     rbp, [rsp+28h+arg_8]
0x18001d62f  mov     eax, ebx
0x18001d631  mov     rbx, [rsp+28h+arg_0]
0x18001d636  add     rsp, 20h
0x18001d63a  pop     rdi
0x18001d63b  retn
```
