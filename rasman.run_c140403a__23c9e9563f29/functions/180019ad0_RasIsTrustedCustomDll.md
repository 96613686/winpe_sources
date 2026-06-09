# RasIsTrustedCustomDll

- ea: `0x180019ad0`
- end: `0x180019cc3`
- name: `RasIsTrustedCustomDll`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180002f80`
- `0x180019ad0`
- `0x180021000`
- `0x1800213e4`
- `0x180021488`
- `0x180024f6c`

## pseudocode

```c
__int64 __fastcall RasIsTrustedCustomDll(__int64 a1, const WCHAR *a2, _DWORD *a3)
{
  PVOID *v6; // rcx
  unsigned __int64 v7; // rax
  __int64 v8; // r9
  PVOID *v9; // rcx
  unsigned int v11; // eax
  __int64 v12; // r9
  unsigned int v13; // ebx
  __int64 v14; // rdx

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 635, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_34;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( v7 > 0x104 || !a3 )
  {
LABEL_34:
    v13 = -2147024809;
    if ( v6 == &WPP_GLOBAL_Control )
      return v13;
    if ( (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    {
      WPP_SF_d(v6[2], 636, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 2147942487LL);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 || *((_BYTE *)v6 + 25) < 6u )
      return v13;
    v14 = 637;
LABEL_42:
    WPP_SF_d(v6[2], v14, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v13);
    return v13;
  }
  *a3 = 0;
  if ( !(unsigned int)IsKnownDll(a2) )
  {
    v11 = SubmitLocalRequest(0x74u, a2, a3);
    v13 = v11;
    if ( v11 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v13;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_26;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 640, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_26:
    if ( v6 == &WPP_GLOBAL_Control )
      return v13;
    if ( (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    {
      LOBYTE(v12) = *a3 != 0;
      WPP_SF_c(v6[2], 641, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v12);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 || *((_BYTE *)v6 + 25) < 6u )
      return v13;
    v14 = 642;
    goto LABEL_42;
  }
  *a3 = 1;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      LOBYTE(v8) = 1;
      WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 638, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 6u )
      WPP_SF_d(v9[2], 639, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180019ad0  push    rbx
0x180019ad2  push    rbp
0x180019ad3  push    rdi
0x180019ad4  push    r14
0x180019ad6  push    r15
0x180019ad8  sub     rsp, 20h
0x180019adc  mov     rdi, r8
0x180019adf  mov     rbx, rdx
0x180019ae2  mov     r9, rcx
0x180019ae5  mov     rcx, cs:WPP_GLOBAL_Control
0x180019aec  lea     rbp, WPP_GLOBAL_Control
0x180019af3  lea     r15, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019afa  cmp     rcx, rbp
0x180019afd  jz      short loc_180019B23
0x180019aff  test    byte ptr [rcx+1Ch], 40h
0x180019b03  jz      short loc_180019B23
0x180019b05  cmp     byte ptr [rcx+19h], 6
0x180019b09  jb      short loc_180019B23
0x180019b0b  mov     rcx, [rcx+10h]
0x180019b0f  mov     edx, 27Bh
0x180019b14  mov     r8, r15
0x180019b17  call    WPP_SF_q
0x180019b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b23  xor     r14d, r14d
0x180019b26  test    rbx, rbx
0x180019b29  jz      loc_180019C5F
0x180019b2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019b33  inc     rax
0x180019b36  cmp     [rbx+rax*2], r14w
0x180019b3b  jnz     short loc_180019B33
0x180019b3d  cmp     rax, 104h
0x180019b43  ja      loc_180019C5F
0x180019b49  test    rdi, rdi
0x180019b4c  jz      loc_180019C5F
0x180019b52  mov     rcx, rbx; lpSrc
0x180019b55  mov     [rdi], r14d
0x180019b58  call    IsKnownDll
0x180019b5d  test    eax, eax
0x180019b5f  jz      short loc_180019BC6
0x180019b61  mov     dword ptr [rdi], 1
0x180019b67  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b6e  cmp     rcx, rbp
0x180019b71  jz      short loc_180019BBF
0x180019b73  test    byte ptr [rcx+1Ch], 40h
0x180019b77  jz      short loc_180019B9A
0x180019b79  cmp     byte ptr [rcx+19h], 5
0x180019b7d  jb      short loc_180019B9A
0x180019b7f  mov     rcx, [rcx+10h]
0x180019b83  mov     edx, 27Eh
0x180019b88  mov     r9b, 1
0x180019b8b  mov     r8, r15
0x180019b8e  call    WPP_SF_c
0x180019b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b9a  cmp     rcx, rbp
0x180019b9d  jz      short loc_180019BBF
0x180019b9f  test    byte ptr [rcx+1Ch], 40h
0x180019ba3  jz      short loc_180019BBF
0x180019ba5  cmp     byte ptr [rcx+19h], 6
0x180019ba9  jb      short loc_180019BBF
0x180019bab  mov     rcx, [rcx+10h]
0x180019baf  mov     edx, 27Fh
0x180019bb4  xor     r9d, r9d
0x180019bb7  mov     r8, r15
0x180019bba  call    WPP_SF_d
0x180019bbf  xor     eax, eax
0x180019bc1  jmp     loc_180019CB7
0x180019bc6  mov     ecx, 74h ; 't'
0x180019bcb  mov     r8, rdi
0x180019bce  mov     rdx, rbx
0x180019bd1  call    SubmitLocalRequest
0x180019bd6  mov     ebx, eax
0x180019bd8  test    eax, eax
0x180019bda  jz      short loc_180019C0C
0x180019bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180019be3  cmp     rcx, rbp
0x180019be6  jz      loc_180019CB5
0x180019bec  test    byte ptr [rcx+1Ch], 40h
0x180019bf0  jz      short loc_180019C13
0x180019bf2  cmp     byte ptr [rcx+19h], 2
0x180019bf6  jb      short loc_180019C13
0x180019bf8  mov     rcx, [rcx+10h]
0x180019bfc  mov     edx, 280h
0x180019c01  mov     r9d, eax
0x180019c04  mov     r8, r15
0x180019c07  call    WPP_SF_d
0x180019c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c13  cmp     rcx, rbp
0x180019c16  jz      loc_180019CB5
0x180019c1c  test    byte ptr [rcx+1Ch], 40h
0x180019c20  jz      short loc_180019C47
0x180019c22  cmp     byte ptr [rcx+19h], 5
0x180019c26  jb      short loc_180019C47
0x180019c28  cmp     [rdi], r14d
0x180019c2b  mov     edx, 281h
0x180019c30  mov     rcx, [rcx+10h]
0x180019c34  mov     r8, r15
0x180019c37  setnz   r9b
0x180019c3b  call    WPP_SF_c
0x180019c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c47  cmp     rcx, rbp
0x180019c4a  jz      short loc_180019CB5
0x180019c4c  test    byte ptr [rcx+1Ch], 40h
0x180019c50  jz      short loc_180019CB5
0x180019c52  cmp     byte ptr [rcx+19h], 6
0x180019c56  jb      short loc_180019CB5
0x180019c58  mov     edx, 282h
0x180019c5d  jmp     short loc_180019CA6
0x180019c5f  mov     ebx, 80070057h
0x180019c64  cmp     rcx, rbp
0x180019c67  jz      short loc_180019CB5
0x180019c69  test    byte ptr [rcx+1Ch], 40h
0x180019c6d  jz      short loc_180019C90
0x180019c6f  cmp     byte ptr [rcx+19h], 2
0x180019c73  jb      short loc_180019C90
0x180019c75  mov     rcx, [rcx+10h]
0x180019c79  mov     edx, 27Ch
0x180019c7e  mov     r9d, ebx
0x180019c81  mov     r8, r15
0x180019c84  call    WPP_SF_d
0x180019c89  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c90  cmp     rcx, rbp
0x180019c93  jz      short loc_180019CB5
0x180019c95  test    byte ptr [rcx+1Ch], 40h
0x180019c99  jz      short loc_180019CB5
0x180019c9b  cmp     byte ptr [rcx+19h], 6
0x180019c9f  jb      short loc_180019CB5
0x180019ca1  mov     edx, 27Dh
0x180019ca6  mov     rcx, [rcx+10h]
0x180019caa  mov     r9d, ebx
0x180019cad  mov     r8, r15
0x180019cb0  call    WPP_SF_d
0x180019cb5  mov     eax, ebx
0x180019cb7  add     rsp, 20h
0x180019cbb  pop     r15
0x180019cbd  pop     r14
0x180019cbf  pop     rdi
0x180019cc0  pop     rbp
0x180019cc1  pop     rbx
0x180019cc2  retn
```
