# RasIsTrustedCustomDll

- ea: `0x18001a4c0`
- end: `0x18001a6b4`
- name: `RasIsTrustedCustomDll`
- size: `500`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800030d0`
- `0x18001a4c0`
- `0x180021b14`
- `0x180021f24`
- `0x180021fd4`
- `0x180025dec`

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
0x18001a4c0  push    rbx
0x18001a4c2  push    rbp
0x18001a4c3  push    rdi
0x18001a4c4  push    r14
0x18001a4c6  push    r15
0x18001a4c8  sub     rsp, 20h
0x18001a4cc  mov     rdi, r8
0x18001a4cf  mov     rbx, rdx
0x18001a4d2  mov     r9, rcx
0x18001a4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4dc  lea     rbp, WPP_GLOBAL_Control
0x18001a4e3  lea     r15, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001a4ea  cmp     rcx, rbp
0x18001a4ed  jz      short loc_18001A513
0x18001a4ef  test    byte ptr [rcx+1Ch], 40h
0x18001a4f3  jz      short loc_18001A513
0x18001a4f5  cmp     byte ptr [rcx+19h], 6
0x18001a4f9  jb      short loc_18001A513
0x18001a4fb  mov     rcx, [rcx+10h]
0x18001a4ff  mov     edx, 27Bh
0x18001a504  mov     r8, r15
0x18001a507  call    WPP_SF_q
0x18001a50c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a513  xor     r14d, r14d
0x18001a516  test    rbx, rbx
0x18001a519  jz      loc_18001A64F
0x18001a51f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a523  inc     rax
0x18001a526  cmp     [rbx+rax*2], r14w
0x18001a52b  jnz     short loc_18001A523
0x18001a52d  cmp     rax, 104h
0x18001a533  ja      loc_18001A64F
0x18001a539  test    rdi, rdi
0x18001a53c  jz      loc_18001A64F
0x18001a542  mov     rcx, rbx; lpSrc
0x18001a545  mov     [rdi], r14d
0x18001a548  call    IsKnownDll
0x18001a54d  test    eax, eax
0x18001a54f  jz      short loc_18001A5B6
0x18001a551  mov     dword ptr [rdi], 1
0x18001a557  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a55e  cmp     rcx, rbp
0x18001a561  jz      short loc_18001A5AF
0x18001a563  test    byte ptr [rcx+1Ch], 40h
0x18001a567  jz      short loc_18001A58A
0x18001a569  cmp     byte ptr [rcx+19h], 5
0x18001a56d  jb      short loc_18001A58A
0x18001a56f  mov     rcx, [rcx+10h]
0x18001a573  mov     edx, 27Eh
0x18001a578  mov     r9b, 1
0x18001a57b  mov     r8, r15
0x18001a57e  call    WPP_SF_c
0x18001a583  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a58a  cmp     rcx, rbp
0x18001a58d  jz      short loc_18001A5AF
0x18001a58f  test    byte ptr [rcx+1Ch], 40h
0x18001a593  jz      short loc_18001A5AF
0x18001a595  cmp     byte ptr [rcx+19h], 6
0x18001a599  jb      short loc_18001A5AF
0x18001a59b  mov     rcx, [rcx+10h]
0x18001a59f  mov     edx, 27Fh
0x18001a5a4  xor     r9d, r9d
0x18001a5a7  mov     r8, r15
0x18001a5aa  call    WPP_SF_d
0x18001a5af  xor     eax, eax
0x18001a5b1  jmp     loc_18001A6A7
0x18001a5b6  mov     ecx, 74h ; 't'
0x18001a5bb  mov     r8, rdi
0x18001a5be  mov     rdx, rbx
0x18001a5c1  call    SubmitLocalRequest
0x18001a5c6  mov     ebx, eax
0x18001a5c8  test    eax, eax
0x18001a5ca  jz      short loc_18001A5FC
0x18001a5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5d3  cmp     rcx, rbp
0x18001a5d6  jz      loc_18001A6A5
0x18001a5dc  test    byte ptr [rcx+1Ch], 40h
0x18001a5e0  jz      short loc_18001A603
0x18001a5e2  cmp     byte ptr [rcx+19h], 2
0x18001a5e6  jb      short loc_18001A603
0x18001a5e8  mov     rcx, [rcx+10h]
0x18001a5ec  mov     edx, 280h
0x18001a5f1  mov     r9d, eax
0x18001a5f4  mov     r8, r15
0x18001a5f7  call    WPP_SF_d
0x18001a5fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a603  cmp     rcx, rbp
0x18001a606  jz      loc_18001A6A5
0x18001a60c  test    byte ptr [rcx+1Ch], 40h
0x18001a610  jz      short loc_18001A637
0x18001a612  cmp     byte ptr [rcx+19h], 5
0x18001a616  jb      short loc_18001A637
0x18001a618  cmp     [rdi], r14d
0x18001a61b  mov     edx, 281h
0x18001a620  mov     rcx, [rcx+10h]
0x18001a624  mov     r8, r15
0x18001a627  setnz   r9b
0x18001a62b  call    WPP_SF_c
0x18001a630  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a637  cmp     rcx, rbp
0x18001a63a  jz      short loc_18001A6A5
0x18001a63c  test    byte ptr [rcx+1Ch], 40h
0x18001a640  jz      short loc_18001A6A5
0x18001a642  cmp     byte ptr [rcx+19h], 6
0x18001a646  jb      short loc_18001A6A5
0x18001a648  mov     edx, 282h
0x18001a64d  jmp     short loc_18001A696
0x18001a64f  mov     ebx, 80070057h
0x18001a654  cmp     rcx, rbp
0x18001a657  jz      short loc_18001A6A5
0x18001a659  test    byte ptr [rcx+1Ch], 40h
0x18001a65d  jz      short loc_18001A680
0x18001a65f  cmp     byte ptr [rcx+19h], 2
0x18001a663  jb      short loc_18001A680
0x18001a665  mov     rcx, [rcx+10h]
0x18001a669  mov     edx, 27Ch
0x18001a66e  mov     r9d, ebx
0x18001a671  mov     r8, r15
0x18001a674  call    WPP_SF_d
0x18001a679  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a680  cmp     rcx, rbp
0x18001a683  jz      short loc_18001A6A5
0x18001a685  test    byte ptr [rcx+1Ch], 40h
0x18001a689  jz      short loc_18001A6A5
0x18001a68b  cmp     byte ptr [rcx+19h], 6
0x18001a68f  jb      short loc_18001A6A5
0x18001a691  mov     edx, 27Dh
0x18001a696  mov     rcx, [rcx+10h]
0x18001a69a  mov     r9d, ebx
0x18001a69d  mov     r8, r15
0x18001a6a0  call    WPP_SF_d
0x18001a6a5  mov     eax, ebx
0x18001a6a7  add     rsp, 20h
0x18001a6ab  pop     r15
0x18001a6ad  pop     r14
0x18001a6af  pop     rdi
0x18001a6b0  pop     rbp
0x18001a6b1  pop     rbx
0x18001a6b2  retn
```
