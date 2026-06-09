# RasCompressionSetInfo

- ea: `0x1800175d0`
- end: `0x1800176dc`
- name: `RasCompressionSetInfo`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x1800175d0`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasCompressionSetInfo(__int64 a1, __int64 a2, __int64 a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v7 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 272;
LABEL_20:
      WPP_SF_d(v6[2], v8, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
      return v7;
    }
    return v7;
  }
  v9 = SubmitLocalRequest(0x14u, a1, a2, a3);
  v7 = v9;
  if ( v9 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 273, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v8 = 274;
    goto LABEL_20;
  }
  return v7;
}

```

## disassembly

```asm
0x1800175d0  push    rbx
0x1800175d2  push    rsi
0x1800175d3  push    rdi
0x1800175d4  push    r14
0x1800175d6  sub     rsp, 28h
0x1800175da  mov     rdi, r8
0x1800175dd  mov     rsi, rdx
0x1800175e0  mov     rbx, rcx
0x1800175e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175ea  lea     r14, WPP_GLOBAL_Control
0x1800175f1  cmp     rcx, r14
0x1800175f4  jz      short loc_18001761A
0x1800175f6  test    byte ptr [rcx+1Ch], 40h
0x1800175fa  jz      short loc_18001761A
0x1800175fc  cmp     byte ptr [rcx+19h], 6
0x180017600  jb      short loc_18001761A
0x180017602  mov     rcx, [rcx+10h]
0x180017606  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001760d  mov     edx, 10Fh
0x180017612  mov     r9, rbx
0x180017615  call    WPP_SF_q
0x18001761a  mov     rcx, rbx
0x18001761d  call    ValidatePortHandle
0x180017622  test    eax, eax
0x180017624  jnz     short loc_180017656
0x180017626  mov     rcx, cs:WPP_GLOBAL_Control
0x18001762d  mov     ebx, 259h
0x180017632  cmp     rcx, r14
0x180017635  jz      loc_1800176CF
0x18001763b  test    byte ptr [rcx+1Ch], 40h
0x18001763f  jz      loc_1800176CF
0x180017645  cmp     byte ptr [rcx+19h], 2
0x180017649  jb      loc_1800176CF
0x18001764f  mov     edx, 110h
0x180017654  jmp     short loc_1800176BC
0x180017656  mov     ecx, 14h
0x18001765b  mov     r9, rdi
0x18001765e  mov     r8, rsi
0x180017661  mov     rdx, rbx
0x180017664  call    SubmitLocalRequest
0x180017669  mov     ebx, eax
0x18001766b  test    eax, eax
0x18001766d  jz      short loc_18001769F
0x18001766f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017676  cmp     rcx, r14
0x180017679  jz      short loc_1800176CF
0x18001767b  test    byte ptr [rcx+1Ch], 40h
0x18001767f  jz      short loc_1800176A6
0x180017681  cmp     byte ptr [rcx+19h], 2
0x180017685  jb      short loc_1800176A6
0x180017687  mov     rcx, [rcx+10h]
0x18001768b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180017692  mov     edx, 111h
0x180017697  mov     r9d, eax
0x18001769a  call    WPP_SF_d
0x18001769f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176a6  cmp     rcx, r14
0x1800176a9  jz      short loc_1800176CF
0x1800176ab  test    byte ptr [rcx+1Ch], 40h
0x1800176af  jz      short loc_1800176CF
0x1800176b1  cmp     byte ptr [rcx+19h], 6
0x1800176b5  jb      short loc_1800176CF
0x1800176b7  mov     edx, 112h
0x1800176bc  mov     rcx, [rcx+10h]
0x1800176c0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800176c7  mov     r9d, ebx
0x1800176ca  call    WPP_SF_d
0x1800176cf  mov     eax, ebx
0x1800176d1  add     rsp, 28h
0x1800176d5  pop     r14
0x1800176d7  pop     rdi
0x1800176d8  pop     rsi
0x1800176d9  pop     rbx
0x1800176da  retn
```
