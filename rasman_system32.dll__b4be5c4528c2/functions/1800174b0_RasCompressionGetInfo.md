# RasCompressionGetInfo

- ea: `0x1800174b0`
- end: `0x1800175bc`
- name: `RasCompressionGetInfo`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x1800174b0`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasCompressionGetInfo(__int64 a1, __int64 a2, __int64 a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v7 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 268;
LABEL_20:
      WPP_SF_d(v6[2], v8, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
      return v7;
    }
    return v7;
  }
  v9 = SubmitLocalRequest(0x13u, a1, a2, a3);
  v7 = v9;
  if ( v9 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v8 = 270;
    goto LABEL_20;
  }
  return v7;
}

```

## disassembly

```asm
0x1800174b0  push    rbx
0x1800174b2  push    rsi
0x1800174b3  push    rdi
0x1800174b4  push    r14
0x1800174b6  sub     rsp, 28h
0x1800174ba  mov     rdi, r8
0x1800174bd  mov     rsi, rdx
0x1800174c0  mov     rbx, rcx
0x1800174c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174ca  lea     r14, WPP_GLOBAL_Control
0x1800174d1  cmp     rcx, r14
0x1800174d4  jz      short loc_1800174FA
0x1800174d6  test    byte ptr [rcx+1Ch], 40h
0x1800174da  jz      short loc_1800174FA
0x1800174dc  cmp     byte ptr [rcx+19h], 6
0x1800174e0  jb      short loc_1800174FA
0x1800174e2  mov     rcx, [rcx+10h]
0x1800174e6  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800174ed  mov     edx, 10Bh
0x1800174f2  mov     r9, rbx
0x1800174f5  call    WPP_SF_q
0x1800174fa  mov     rcx, rbx
0x1800174fd  call    ValidatePortHandle
0x180017502  test    eax, eax
0x180017504  jnz     short loc_180017536
0x180017506  mov     rcx, cs:WPP_GLOBAL_Control
0x18001750d  mov     ebx, 259h
0x180017512  cmp     rcx, r14
0x180017515  jz      loc_1800175AF
0x18001751b  test    byte ptr [rcx+1Ch], 40h
0x18001751f  jz      loc_1800175AF
0x180017525  cmp     byte ptr [rcx+19h], 2
0x180017529  jb      loc_1800175AF
0x18001752f  mov     edx, 10Ch
0x180017534  jmp     short loc_18001759C
0x180017536  mov     ecx, 13h
0x18001753b  mov     r9, rdi
0x18001753e  mov     r8, rsi
0x180017541  mov     rdx, rbx
0x180017544  call    SubmitLocalRequest
0x180017549  mov     ebx, eax
0x18001754b  test    eax, eax
0x18001754d  jz      short loc_18001757F
0x18001754f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017556  cmp     rcx, r14
0x180017559  jz      short loc_1800175AF
0x18001755b  test    byte ptr [rcx+1Ch], 40h
0x18001755f  jz      short loc_180017586
0x180017561  cmp     byte ptr [rcx+19h], 2
0x180017565  jb      short loc_180017586
0x180017567  mov     rcx, [rcx+10h]
0x18001756b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180017572  mov     edx, 10Dh
0x180017577  mov     r9d, eax
0x18001757a  call    WPP_SF_d
0x18001757f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017586  cmp     rcx, r14
0x180017589  jz      short loc_1800175AF
0x18001758b  test    byte ptr [rcx+1Ch], 40h
0x18001758f  jz      short loc_1800175AF
0x180017591  cmp     byte ptr [rcx+19h], 6
0x180017595  jb      short loc_1800175AF
0x180017597  mov     edx, 10Eh
0x18001759c  mov     rcx, [rcx+10h]
0x1800175a0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800175a7  mov     r9d, ebx
0x1800175aa  call    WPP_SF_d
0x1800175af  mov     eax, ebx
0x1800175b1  add     rsp, 28h
0x1800175b5  pop     r14
0x1800175b7  pop     rdi
0x1800175b8  pop     rsi
0x1800175b9  pop     rbx
0x1800175ba  retn
```
