# MSMUpdateOneXUserProfile

- ea: `0x18001b360`
- end: `0x18001b49e`
- name: `MSMUpdateOneXUserProfile`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180027ae4`
- `0x180029238`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x18001b360`
- `0x18001c80c`
- `0x18001d838`
- `0x18001e4e8`
- `0x18001f4bc`
- `0x1800214f0`

## pseudocode

```c
__int64 __fastcall MSMUpdateOneXUserProfile(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // edi
  char *v9; // r10
  int v10; // eax

  v4 = *(_DWORD *)(a1 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 70, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
  if ( (unsigned int)PortMgrCanCacheUserData(a1) || (unsigned int)SupplicantIsUsingExplicitCreds(a1 + 2384) )
  {
    if ( v9 != (char *)&WPP_GLOBAL_Control && v9[68] < 0 )
      WPP_SF_dq(*((_QWORD *)v9 + 7), 71, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4, a2);
    v10 = MSMSetOneXUserProfile(a1, a2, a3, a4);
    if ( v10 )
    {
      v9 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_17;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 72, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4, v10);
    }
    goto LABEL_16;
  }
  if ( v9 == (char *)&WPP_GLOBAL_Control )
    return 0;
  if ( v9[68] < 0 )
  {
    WPP_SF_d(*((_QWORD *)v9 + 7), 73, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4);
LABEL_16:
    v9 = (char *)WPP_GLOBAL_Control;
  }
LABEL_17:
  if ( v9 != (char *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v9 + 7), 74, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18001b360  push    rbx
0x18001b362  push    rbp
0x18001b363  push    rsi
0x18001b364  push    rdi
0x18001b365  push    r12
0x18001b367  push    r14
0x18001b369  push    r15
0x18001b36b  sub     rsp, 30h
0x18001b36f  mov     edi, [rcx+14h]
0x18001b372  mov     rbp, r9
0x18001b375  mov     r14d, r8d
0x18001b378  mov     rsi, rdx
0x18001b37b  mov     rbx, rcx
0x18001b37e  mov     r10, cs:WPP_GLOBAL_Control
0x18001b385  lea     r15, WPP_GLOBAL_Control
0x18001b38c  lea     r12, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18001b393  cmp     r10, r15
0x18001b396  jz      short loc_18001B3BA
0x18001b398  test    dword ptr [r10+44h], 800h
0x18001b3a0  jz      short loc_18001B3BA
0x18001b3a2  mov     rcx, [r10+38h]
0x18001b3a6  mov     edx, 46h ; 'F'
0x18001b3ab  mov     r8, r12
0x18001b3ae  call    WPP_SF_
0x18001b3b3  mov     r10, cs:WPP_GLOBAL_Control
0x18001b3ba  mov     rcx, rbx
0x18001b3bd  call    PortMgrCanCacheUserData
0x18001b3c2  test    eax, eax
0x18001b3c4  jnz     short loc_18001B3FE
0x18001b3c6  lea     rcx, [rbx+950h]
0x18001b3cd  call    SupplicantIsUsingExplicitCreds
0x18001b3d2  test    eax, eax
0x18001b3d4  jnz     short loc_18001B3FE
0x18001b3d6  cmp     r10, r15
0x18001b3d9  jz      loc_18001B48D
0x18001b3df  test    byte ptr [r10+44h], 80h
0x18001b3e4  jz      loc_18001B46A
0x18001b3ea  mov     rcx, [r10+38h]
0x18001b3ee  lea     edx, [rax+49h]
0x18001b3f1  mov     r9d, edi
0x18001b3f4  mov     r8, r12
0x18001b3f7  call    WPP_SF_d
0x18001b3fc  jmp     short loc_18001B463
0x18001b3fe  cmp     r10, r15
0x18001b401  jz      short loc_18001B423
0x18001b403  test    byte ptr [r10+44h], 80h
0x18001b408  jz      short loc_18001B423
0x18001b40a  mov     rcx, [r10+38h]
0x18001b40e  mov     edx, 47h ; 'G'
0x18001b413  mov     r9d, edi
0x18001b416  mov     [rsp+68h+var_48], rsi
0x18001b41b  mov     r8, r12
0x18001b41e  call    WPP_SF_dq
0x18001b423  mov     r9, rbp
0x18001b426  mov     r8d, r14d
0x18001b429  mov     rdx, rsi
0x18001b42c  mov     rcx, rbx
0x18001b42f  call    MSMSetOneXUserProfile
0x18001b434  test    eax, eax
0x18001b436  jz      short loc_18001B463
0x18001b438  mov     r10, cs:WPP_GLOBAL_Control
0x18001b43f  cmp     r10, r15
0x18001b442  jz      short loc_18001B48D
0x18001b444  test    byte ptr [r10+44h], 1
0x18001b449  jz      short loc_18001B46A
0x18001b44b  mov     rcx, [r10+38h]
0x18001b44f  mov     edx, 48h ; 'H'
0x18001b454  mov     r9d, edi
0x18001b457  mov     dword ptr [rsp+68h+var_48], eax
0x18001b45b  mov     r8, r12
0x18001b45e  call    WPP_SF_dd
0x18001b463  mov     r10, cs:WPP_GLOBAL_Control
0x18001b46a  cmp     r10, r15
0x18001b46d  jz      short loc_18001B48D
0x18001b46f  test    dword ptr [r10+44h], 800h
0x18001b477  jz      short loc_18001B48D
0x18001b479  mov     rcx, [r10+38h]
0x18001b47d  mov     edx, 4Ah ; 'J'
0x18001b482  xor     r9d, r9d
0x18001b485  mov     r8, r12
0x18001b488  call    WPP_SF_D
0x18001b48d  xor     eax, eax
0x18001b48f  add     rsp, 30h
0x18001b493  pop     r15
0x18001b495  pop     r14
0x18001b497  pop     r12
0x18001b499  pop     rdi
0x18001b49a  pop     rsi
0x18001b49b  pop     rbp
0x18001b49c  pop     rbx
0x18001b49d  retn
```
