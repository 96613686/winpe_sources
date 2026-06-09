# RasSetCommSettings

- ea: `0x18001ec70`
- end: `0x18001edec`
- name: `RasSetCommSettings`
- size: `380`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002f80`
- `0x18001ec70`
- `0x180021000`
- `0x180021488`

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
0x18001ec70  push    rbx
0x18001ec72  push    rbp
0x18001ec73  push    rdi
0x18001ec74  push    r14
0x18001ec76  sub     rsp, 28h
0x18001ec7a  mov     rbx, rdx
0x18001ec7d  mov     rdi, rcx
0x18001ec80  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec87  lea     rbp, WPP_GLOBAL_Control
0x18001ec8e  lea     r14, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ec95  cmp     rcx, rbp
0x18001ec98  jz      short loc_18001ECC1
0x18001ec9a  test    byte ptr [rcx+1Ch], 40h
0x18001ec9e  jz      short loc_18001ECC1
0x18001eca0  cmp     byte ptr [rcx+19h], 6
0x18001eca4  jb      short loc_18001ECC1
0x18001eca6  mov     rcx, [rcx+10h]
0x18001ecaa  mov     edx, 28Ah
0x18001ecaf  mov     r9, rdi
0x18001ecb2  mov     r8, r14
0x18001ecb5  call    WPP_SF_q
0x18001ecba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecc1  test    rbx, rbx
0x18001ecc4  jnz     short loc_18001ED22
0x18001ecc6  mov     ebx, 80070057h
0x18001eccb  cmp     rcx, rbp
0x18001ecce  jz      loc_18001EDE0
0x18001ecd4  test    byte ptr [rcx+1Ch], 40h
0x18001ecd8  jz      short loc_18001ECFB
0x18001ecda  cmp     byte ptr [rcx+19h], 2
0x18001ecde  jb      short loc_18001ECFB
0x18001ece0  mov     rcx, [rcx+10h]
0x18001ece4  mov     edx, 28Bh
0x18001ece9  mov     r9d, ebx
0x18001ecec  mov     r8, r14
0x18001ecef  call    WPP_SF_d
0x18001ecf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecfb  cmp     rcx, rbp
0x18001ecfe  jz      loc_18001EDE0
0x18001ed04  test    byte ptr [rcx+1Ch], 40h
0x18001ed08  jz      loc_18001EDE0
0x18001ed0e  cmp     byte ptr [rcx+19h], 6
0x18001ed12  jb      loc_18001EDE0
0x18001ed18  mov     edx, 28Ch
0x18001ed1d  jmp     loc_18001EDD1
0x18001ed22  cmp     dword ptr [rbx], 8
0x18001ed25  jnz     short loc_18001ED8C
0x18001ed27  mov     ecx, 77h ; 'w'
0x18001ed2c  mov     r8, rbx
0x18001ed2f  mov     rdx, rdi
0x18001ed32  call    SubmitLocalRequest
0x18001ed37  mov     ebx, eax
0x18001ed39  test    eax, eax
0x18001ed3b  jz      short loc_18001ED6D
0x18001ed3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed44  cmp     rcx, rbp
0x18001ed47  jz      loc_18001EDE0
0x18001ed4d  test    byte ptr [rcx+1Ch], 40h
0x18001ed51  jz      short loc_18001ED74
0x18001ed53  cmp     byte ptr [rcx+19h], 2
0x18001ed57  jb      short loc_18001ED74
0x18001ed59  mov     rcx, [rcx+10h]
0x18001ed5d  mov     edx, 28Fh
0x18001ed62  mov     r9d, eax
0x18001ed65  mov     r8, r14
0x18001ed68  call    WPP_SF_d
0x18001ed6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed74  cmp     rcx, rbp
0x18001ed77  jz      short loc_18001EDE0
0x18001ed79  test    byte ptr [rcx+1Ch], 40h
0x18001ed7d  jz      short loc_18001EDE0
0x18001ed7f  cmp     byte ptr [rcx+19h], 6
0x18001ed83  jb      short loc_18001EDE0
0x18001ed85  mov     edx, 290h
0x18001ed8a  jmp     short loc_18001EDD1
0x18001ed8c  mov     ebx, 278h
0x18001ed91  cmp     rcx, rbp
0x18001ed94  jz      short loc_18001EDE0
0x18001ed96  test    byte ptr [rcx+1Ch], 40h
0x18001ed9a  jz      short loc_18001EDBB
0x18001ed9c  cmp     byte ptr [rcx+19h], 2
0x18001eda0  jb      short loc_18001EDBB
0x18001eda2  mov     rcx, [rcx+10h]
0x18001eda6  lea     edx, [rbx+15h]
0x18001eda9  mov     r9d, ebx
0x18001edac  mov     r8, r14
0x18001edaf  call    WPP_SF_d
0x18001edb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edbb  cmp     rcx, rbp
0x18001edbe  jz      short loc_18001EDE0
0x18001edc0  test    byte ptr [rcx+1Ch], 40h
0x18001edc4  jz      short loc_18001EDE0
0x18001edc6  cmp     byte ptr [rcx+19h], 6
0x18001edca  jb      short loc_18001EDE0
0x18001edcc  mov     edx, 28Eh
0x18001edd1  mov     rcx, [rcx+10h]
0x18001edd5  mov     r9d, ebx
0x18001edd8  mov     r8, r14
0x18001eddb  call    WPP_SF_d
0x18001ede0  mov     eax, ebx
0x18001ede2  add     rsp, 28h
0x18001ede6  pop     r14
0x18001ede8  pop     rdi
0x18001ede9  pop     rbp
0x18001edea  pop     rbx
0x18001edeb  retn
```
