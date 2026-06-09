# RasSetCommSettings

- ea: `0x18001f700`
- end: `0x18001f87d`
- name: `RasSetCommSettings`
- size: `381`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800030d0`
- `0x18001f700`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasSetCommSettings(__int64 a1, _DWORD *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 650, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v5 = -2147024809;
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      {
        WPP_SF_d(v4[2], 651, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 2147942487LL);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 652;
LABEL_33:
        WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
        return v5;
      }
    }
    return v5;
  }
  if ( *a2 != 8 )
  {
    v5 = 632;
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      {
        WPP_SF_d(v4[2], 653, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 632);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 654;
        goto LABEL_33;
      }
    }
    return v5;
  }
  v7 = SubmitLocalRequest(0x77u, a1, a2);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_21;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 655, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_21:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 656;
    goto LABEL_33;
  }
  return v5;
}

```

## disassembly

```asm
0x18001f700  push    rbx
0x18001f702  push    rbp
0x18001f703  push    rdi
0x18001f704  push    r14
0x18001f706  sub     rsp, 28h
0x18001f70a  mov     rbx, rdx
0x18001f70d  mov     rdi, rcx
0x18001f710  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f717  lea     rbp, WPP_GLOBAL_Control
0x18001f71e  lea     r14, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f725  cmp     rcx, rbp
0x18001f728  jz      short loc_18001F751
0x18001f72a  test    byte ptr [rcx+1Ch], 40h
0x18001f72e  jz      short loc_18001F751
0x18001f730  cmp     byte ptr [rcx+19h], 6
0x18001f734  jb      short loc_18001F751
0x18001f736  mov     rcx, [rcx+10h]
0x18001f73a  mov     edx, 28Ah
0x18001f73f  mov     r9, rdi
0x18001f742  mov     r8, r14
0x18001f745  call    WPP_SF_q
0x18001f74a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f751  test    rbx, rbx
0x18001f754  jnz     short loc_18001F7B2
0x18001f756  mov     ebx, 80070057h
0x18001f75b  cmp     rcx, rbp
0x18001f75e  jz      loc_18001F870
0x18001f764  test    byte ptr [rcx+1Ch], 40h
0x18001f768  jz      short loc_18001F78B
0x18001f76a  cmp     byte ptr [rcx+19h], 2
0x18001f76e  jb      short loc_18001F78B
0x18001f770  mov     rcx, [rcx+10h]
0x18001f774  mov     edx, 28Bh
0x18001f779  mov     r9d, ebx
0x18001f77c  mov     r8, r14
0x18001f77f  call    WPP_SF_d
0x18001f784  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f78b  cmp     rcx, rbp
0x18001f78e  jz      loc_18001F870
0x18001f794  test    byte ptr [rcx+1Ch], 40h
0x18001f798  jz      loc_18001F870
0x18001f79e  cmp     byte ptr [rcx+19h], 6
0x18001f7a2  jb      loc_18001F870
0x18001f7a8  mov     edx, 28Ch
0x18001f7ad  jmp     loc_18001F861
0x18001f7b2  cmp     dword ptr [rbx], 8
0x18001f7b5  jnz     short loc_18001F81C
0x18001f7b7  mov     ecx, 77h ; 'w'
0x18001f7bc  mov     r8, rbx
0x18001f7bf  mov     rdx, rdi
0x18001f7c2  call    SubmitLocalRequest
0x18001f7c7  mov     ebx, eax
0x18001f7c9  test    eax, eax
0x18001f7cb  jz      short loc_18001F7FD
0x18001f7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7d4  cmp     rcx, rbp
0x18001f7d7  jz      loc_18001F870
0x18001f7dd  test    byte ptr [rcx+1Ch], 40h
0x18001f7e1  jz      short loc_18001F804
0x18001f7e3  cmp     byte ptr [rcx+19h], 2
0x18001f7e7  jb      short loc_18001F804
0x18001f7e9  mov     rcx, [rcx+10h]
0x18001f7ed  mov     edx, 28Fh
0x18001f7f2  mov     r9d, eax
0x18001f7f5  mov     r8, r14
0x18001f7f8  call    WPP_SF_d
0x18001f7fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f804  cmp     rcx, rbp
0x18001f807  jz      short loc_18001F870
0x18001f809  test    byte ptr [rcx+1Ch], 40h
0x18001f80d  jz      short loc_18001F870
0x18001f80f  cmp     byte ptr [rcx+19h], 6
0x18001f813  jb      short loc_18001F870
0x18001f815  mov     edx, 290h
0x18001f81a  jmp     short loc_18001F861
0x18001f81c  mov     ebx, 278h
0x18001f821  cmp     rcx, rbp
0x18001f824  jz      short loc_18001F870
0x18001f826  test    byte ptr [rcx+1Ch], 40h
0x18001f82a  jz      short loc_18001F84B
0x18001f82c  cmp     byte ptr [rcx+19h], 2
0x18001f830  jb      short loc_18001F84B
0x18001f832  mov     rcx, [rcx+10h]
0x18001f836  lea     edx, [rbx+15h]
0x18001f839  mov     r9d, ebx
0x18001f83c  mov     r8, r14
0x18001f83f  call    WPP_SF_d
0x18001f844  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f84b  cmp     rcx, rbp
0x18001f84e  jz      short loc_18001F870
0x18001f850  test    byte ptr [rcx+1Ch], 40h
0x18001f854  jz      short loc_18001F870
0x18001f856  cmp     byte ptr [rcx+19h], 6
0x18001f85a  jb      short loc_18001F870
0x18001f85c  mov     edx, 28Eh
0x18001f861  mov     rcx, [rcx+10h]
0x18001f865  mov     r9d, ebx
0x18001f868  mov     r8, r14
0x18001f86b  call    WPP_SF_d
0x18001f870  mov     eax, ebx
0x18001f872  add     rsp, 28h
0x18001f876  pop     r14
0x18001f878  pop     rdi
0x18001f879  pop     rbp
0x18001f87a  pop     rbx
0x18001f87b  retn
```
