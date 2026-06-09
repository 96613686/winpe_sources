# CMsftDiscRecorder2::SendCommandCommonValidation(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)

- ea: `0x18000327c`
- end: `0x180003584`
- name: `?SendCommandCommonValidation@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z`
- size: `776`
- prototype: `int(CMsftDiscRecorder2 *__hidden this, void *const, const union _CDB *, unsigned int, struct _SENSE_DATA *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned __int8)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002750`
- `0x1800030f0`
- `0x18002b300`

## callees

- `0x18000327c`
- `0x18000358c`
- `0x180014134`
- `0x180014180`
- `0x180016778`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::SendCommandCommonValidation(
        CMsftDiscRecorder2 *this,
        void *const a2,
        const union _CDB *a3,
        unsigned int a4,
        struct _SENSE_DATA *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int a8,
        unsigned int *a9,
        unsigned __int8 a10)
{
  unsigned int v10; // ebx
  PVOID *v13; // rcx
  PVOID *v14; // rcx
  __int64 v16; // rdx

  v10 = 0;
  if ( a3 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 13, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2147467261;
  }
  if ( a4 - 6 > 0xA )
  {
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 188) & 4) != 0 && *((_BYTE *)v13 + 185) >= 3u )
      WPP_SF_Dd(v13[22], 14, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, a4, a4);
    v10 = -2147024809;
  }
  if ( CMsftDiscRecorder2::ValidateCdbLength((CMsftDiscRecorder2 *)v13, a3, a4) )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_ddD(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        15,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        a4,
        a4,
        a3->CDB6GENERIC.OperationCode);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2147024809;
  }
  if ( !a5 )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 188) & 4) != 0 && *((_BYTE *)v14 + 185) >= 3u )
    {
      WPP_SF_(v14[22], 16, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2147467261;
  }
  if ( !a8 )
  {
    if ( !a7 )
      goto LABEL_9;
    if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 188) & 4) == 0 || *((_BYTE *)v14 + 185) < 3u )
    {
LABEL_48:
      v10 = -2147024809;
      goto LABEL_9;
    }
    WPP_SF_(v14[22], 18, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
LABEL_47:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  if ( !a7 )
  {
    if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 188) & 4) == 0 || *((_BYTE *)v14 + 185) < 3u )
      goto LABEL_48;
    WPP_SF_Dd(v14[22], 17, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, a8, a8);
    goto LABEL_47;
  }
LABEL_9:
  if ( a10 && !a9 )
  {
    if ( a8 )
    {
      if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 188) & 4) == 0 || *((_BYTE *)v14 + 185) < 3u )
        goto LABEL_54;
      v16 = 20;
    }
    else
    {
      if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 188) & 4) == 0 || *((_BYTE *)v14 + 185) < 3u )
        goto LABEL_54;
      v16 = 19;
    }
    WPP_SF_(v14[22], v16, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_54:
    v10 = -2147024809;
  }
  if ( a6 - 2 > 0xE0E )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 188) & 4) != 0 && *((_BYTE *)v14 + 185) >= 3u )
      WPP_SF_Dd(v14[22], 21, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, a6, a6);
    return (unsigned int)-2147024809;
  }
  return v10;
}

```

## disassembly

```asm
0x18000327c  push    rbx
0x18000327e  push    rsi
0x18000327f  push    rdi
0x180003280  push    r12
0x180003282  push    r13
0x180003284  sub     rsp, 30h
0x180003288  xor     ebx, ebx
0x18000328a  lea     r12, WPP_GLOBAL_Control
0x180003291  mov     edi, r9d
0x180003294  mov     rsi, r8
0x180003297  test    r8, r8
0x18000329a  jz      loc_18000336D
0x1800032a0  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800032a7  lea     eax, [rdi-6]
0x1800032aa  mov     r13d, 80070057h
0x1800032b0  cmp     eax, 0Ah
0x1800032b3  ja      loc_1800033B4
0x1800032b9  mov     r8d, edi; unsigned int
0x1800032bc  mov     rdx, rsi; union _CDB *
0x1800032bf  call    ?ValidateCdbLength@CMsftDiscRecorder2@@AEAA?BEPEBT_CDB@@K@Z; CMsftDiscRecorder2::ValidateCdbLength(_CDB const *,ulong)
0x1800032c4  test    al, al
0x1800032c6  jz      loc_1800033F2
0x1800032cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032d3  cmp     [rsp+58h+arg_20], 0
0x1800032dc  jz      loc_180003445
0x1800032e2  mov     edi, [rsp+58h+arg_38]
0x1800032e9  test    edi, edi
0x1800032eb  jz      loc_1800034BD
0x1800032f1  cmp     [rsp+58h+arg_30], 0
0x1800032fa  jz      loc_180003485
0x180003300  cmp     [rsp+58h+arg_48], 0
0x180003308  jnz     short loc_18000332F
0x18000330a  mov     r9d, [rsp+58h+arg_28]
0x180003312  lea     eax, [r9-2]
0x180003316  cmp     eax, 0E0Eh
0x18000331b  ja      loc_180003548
0x180003321  mov     eax, ebx
0x180003323  add     rsp, 30h
0x180003327  pop     r13
0x180003329  pop     r12
0x18000332b  pop     rdi
0x18000332c  pop     rsi
0x18000332d  pop     rbx
0x18000332e  retn
0x18000332f  cmp     [rsp+58h+arg_40], 0
0x180003338  jnz     short loc_18000330A
0x18000333a  test    edi, edi
0x18000333c  jnz     loc_18000350A
0x180003342  cmp     rcx, r12
0x180003345  jz      loc_180003540
0x18000334b  test    byte ptr [rcx+0BCh], 4
0x180003352  jz      loc_180003540
0x180003358  cmp     byte ptr [rcx+0B9h], 3
0x18000335f  jb      loc_180003540
0x180003365  lea     edx, [rdi+13h]
0x180003368  jmp     loc_180003526
0x18000336d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003374  cmp     rcx, r12
0x180003377  jz      short loc_1800033AA
0x180003379  test    byte ptr [rcx+0BCh], 4
0x180003380  jz      short loc_1800033AA
0x180003382  cmp     byte ptr [rcx+0B9h], 3
0x180003389  jb      short loc_1800033AA
0x18000338b  mov     rcx, [rcx+0B0h]
0x180003392  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180003399  mov     edx, 0Dh
0x18000339e  call    WPP_SF_
0x1800033a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033aa  mov     ebx, 80004003h
0x1800033af  jmp     loc_1800032A7
0x1800033b4  cmp     rcx, r12
0x1800033b7  jz      short loc_1800033EA
0x1800033b9  test    byte ptr [rcx+0BCh], 4
0x1800033c0  jz      short loc_1800033EA
0x1800033c2  cmp     byte ptr [rcx+0B9h], 3
0x1800033c9  jb      short loc_1800033EA
0x1800033cb  mov     rcx, [rcx+0B0h]
0x1800033d2  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800033d9  mov     edx, 0Eh
0x1800033de  mov     [rsp+58h+var_38], edi
0x1800033e2  mov     r9d, edi
0x1800033e5  call    WPP_SF_Dd
0x1800033ea  mov     ebx, r13d
0x1800033ed  jmp     loc_1800032B9
0x1800033f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033f9  cmp     rcx, r12
0x1800033fc  jz      short loc_18000343D
0x1800033fe  test    byte ptr [rcx+0BCh], 4
0x180003405  jz      short loc_18000343D
0x180003407  cmp     byte ptr [rcx+0B9h], 3
0x18000340e  jb      short loc_18000343D
0x180003410  movzx   eax, byte ptr [rsi]
0x180003413  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18000341a  mov     rcx, [rcx+0B0h]
0x180003421  mov     edx, 0Fh
0x180003426  mov     [rsp+58h+var_30], eax
0x18000342a  mov     r9d, edi
0x18000342d  mov     [rsp+58h+var_38], edi
0x180003431  call    WPP_SF_ddD
0x180003436  mov     rcx, cs:WPP_GLOBAL_Control
0x18000343d  mov     ebx, r13d
0x180003440  jmp     loc_1800032D3
0x180003445  cmp     rcx, r12
0x180003448  jz      short loc_18000347B
0x18000344a  test    byte ptr [rcx+0BCh], 4
0x180003451  jz      short loc_18000347B
0x180003453  cmp     byte ptr [rcx+0B9h], 3
0x18000345a  jb      short loc_18000347B
0x18000345c  mov     rcx, [rcx+0B0h]
0x180003463  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18000346a  mov     edx, 10h
0x18000346f  call    WPP_SF_
0x180003474  mov     rcx, cs:WPP_GLOBAL_Control
0x18000347b  mov     ebx, 80004003h
0x180003480  jmp     loc_1800032E2
0x180003485  cmp     rcx, r12
0x180003488  jz      short loc_180003502
0x18000348a  test    byte ptr [rcx+0BCh], 4
0x180003491  jz      short loc_180003502
0x180003493  cmp     byte ptr [rcx+0B9h], 3
0x18000349a  jb      short loc_180003502
0x18000349c  mov     rcx, [rcx+0B0h]
0x1800034a3  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800034aa  mov     edx, 11h
0x1800034af  mov     [rsp+58h+var_38], edi
0x1800034b3  mov     r9d, edi
0x1800034b6  call    WPP_SF_Dd
0x1800034bb  jmp     short loc_1800034FB
0x1800034bd  cmp     [rsp+58h+arg_30], 0
0x1800034c6  jz      loc_180003300
0x1800034cc  cmp     rcx, r12
0x1800034cf  jz      short loc_180003502
0x1800034d1  test    byte ptr [rcx+0BCh], 4
0x1800034d8  jz      short loc_180003502
0x1800034da  cmp     byte ptr [rcx+0B9h], 3
0x1800034e1  jb      short loc_180003502
0x1800034e3  mov     rcx, [rcx+0B0h]
0x1800034ea  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800034f1  mov     edx, 12h
0x1800034f6  call    WPP_SF_
0x1800034fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003502  mov     ebx, r13d
0x180003505  jmp     loc_180003300
0x18000350a  cmp     rcx, r12
0x18000350d  jz      short loc_180003540
0x18000350f  test    byte ptr [rcx+0BCh], 4
0x180003516  jz      short loc_180003540
0x180003518  cmp     byte ptr [rcx+0B9h], 3
0x18000351f  jb      short loc_180003540
0x180003521  mov     edx, 14h
0x180003526  mov     rcx, [rcx+0B0h]
0x18000352d  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180003534  call    WPP_SF_
0x180003539  mov     rcx, cs:WPP_GLOBAL_Control
0x180003540  mov     ebx, r13d
0x180003543  jmp     loc_18000330A
0x180003548  cmp     rcx, r12
0x18000354b  jz      short loc_18000357C
0x18000354d  test    byte ptr [rcx+0BCh], 4
0x180003554  jz      short loc_18000357C
0x180003556  cmp     byte ptr [rcx+0B9h], 3
0x18000355d  jb      short loc_18000357C
0x18000355f  mov     rcx, [rcx+0B0h]
0x180003566  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18000356d  mov     edx, 15h
0x180003572  mov     [rsp+58h+var_38], r9d
0x180003577  call    WPP_SF_Dd
0x18000357c  mov     ebx, r13d
0x18000357f  jmp     loc_180003321
```
