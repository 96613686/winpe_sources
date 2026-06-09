# EapUpdateConnectionDataInMemoryAndInPersistentStore

- ea: `0x180027598`
- end: `0x1800277b3`
- name: `EapUpdateConnectionDataInMemoryAndInPersistentStore`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180015f90`

## callees

- `0x180005440`
- `0x180007e50`
- `0x180007f60`
- `0x180010ae0`
- `0x1800214f0`
- `0x1800258c8`
- `0x180027598`
- `0x1800277bc`
- `0x180028724`

## pseudocode

```c
__int64 __fastcall EapUpdateConnectionDataInMemoryAndInPersistentStore(__int64 a1, unsigned int a2, const void *a3)
{
  __int64 v3; // r15
  unsigned int v7; // esi
  unsigned int updated; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  int v14; // [rsp+80h] [rbp+8h] BYREF

  v3 = *(_QWORD *)a1;
  v14 = 0;
  v7 = *(_DWORD *)(v3 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 91, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  updated = EapSetWorkingSetConnectionData(a1, a2, a3);
  v9 = updated;
  if ( !updated )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 93, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v7, a2);
      v12 = WPP_GLOBAL_Control;
    }
    if ( *(_DWORD *)(a1 + 172) )
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 0x10) != 0 )
        WPP_SF_d(v12[7], 94, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v7);
      updated = EapChangeUseWinlogonCreds(a1, 1, &v14);
      v9 = updated;
      if ( updated )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v9;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_30;
        v11 = 95;
        goto LABEL_28;
      }
      if ( v14
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 96, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v7);
      }
      *(_DWORD *)(a1 + 172) = 0;
    }
    else
    {
      updated = EapUpdateMasterConnectionData((__int64 *)a1, a2, a3);
      v9 = updated;
      if ( updated )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v9;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_30;
        v11 = 97;
        goto LABEL_28;
      }
    }
    updated = MSMSetOneXConnectionProfile(v3, *(_DWORD *)(*(_QWORD *)a1 + 2736LL), *(_QWORD *)(*(_QWORD *)a1 + 2744LL));
    v9 = updated;
    if ( !updated )
    {
LABEL_29:
      v10 = WPP_GLOBAL_Control;
      goto LABEL_30;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_30;
    v11 = 98;
LABEL_28:
    WPP_SF_dd(v10[7], v11, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v7, updated);
    goto LABEL_29;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v11 = 92;
    goto LABEL_28;
  }
LABEL_30:
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
    WPP_SF_D(v10[7], 99, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180027598  mov     rax, rsp
0x18002759b  push    rbx
0x18002759c  push    rbp
0x18002759d  push    rsi
0x18002759e  push    rdi
0x18002759f  push    r12
0x1800275a1  push    r13
0x1800275a3  push    r14
0x1800275a5  push    r15
0x1800275a7  sub     rsp, 38h
0x1800275ab  mov     r15, [rcx]
0x1800275ae  mov     r14, r8
0x1800275b1  mov     ebp, edx
0x1800275b3  mov     dword ptr [rax+8], 0
0x1800275ba  mov     rdi, rcx
0x1800275bd  mov     esi, [r15+14h]
0x1800275c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275c8  lea     r12, WPP_GLOBAL_Control
0x1800275cf  lea     r13, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800275d6  cmp     rcx, r12
0x1800275d9  jz      short loc_1800275F5
0x1800275db  test    dword ptr [rcx+44h], 800h
0x1800275e2  jz      short loc_1800275F5
0x1800275e4  mov     rcx, [rcx+38h]
0x1800275e8  mov     edx, 5Bh ; '['
0x1800275ed  mov     r8, r13
0x1800275f0  call    WPP_SF_
0x1800275f5  mov     r8, r14
0x1800275f8  mov     edx, ebp
0x1800275fa  mov     rcx, rdi
0x1800275fd  call    EapSetWorkingSetConnectionData
0x180027602  mov     ebx, eax
0x180027604  test    eax, eax
0x180027606  jz      short loc_18002762C
0x180027608  mov     rcx, cs:WPP_GLOBAL_Control
0x18002760f  cmp     rcx, r12
0x180027612  jz      loc_180027770
0x180027618  test    byte ptr [rcx+44h], 1
0x18002761c  jz      loc_18002774E
0x180027622  mov     edx, 5Ch ; '\'
0x180027627  jmp     loc_180027734
0x18002762c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027633  cmp     rcx, r12
0x180027636  jz      short loc_18002765D
0x180027638  test    byte ptr [rcx+44h], 10h
0x18002763c  jz      short loc_18002765D
0x18002763e  mov     rcx, [rcx+38h]
0x180027642  mov     edx, 5Dh ; ']'
0x180027647  mov     r9d, esi
0x18002764a  mov     [rsp+78h+var_58], ebp
0x18002764e  mov     r8, r13
0x180027651  call    WPP_SF_dd
0x180027656  mov     rcx, cs:WPP_GLOBAL_Control
0x18002765d  cmp     dword ptr [rdi+0ACh], 0
0x180027664  jz      loc_180027783
0x18002766a  cmp     rcx, r12
0x18002766d  jz      short loc_180027689
0x18002766f  test    byte ptr [rcx+44h], 10h
0x180027673  jz      short loc_180027689
0x180027675  mov     rcx, [rcx+38h]
0x180027679  mov     edx, 5Eh ; '^'
0x18002767e  mov     r9d, esi
0x180027681  mov     r8, r13
0x180027684  call    WPP_SF_d
0x180027689  lea     r8, [rsp+78h+arg_0]
0x180027691  mov     edx, 1
0x180027696  mov     rcx, rdi
0x180027699  call    EapChangeUseWinlogonCreds
0x18002769e  mov     ebx, eax
0x1800276a0  test    eax, eax
0x1800276a2  jz      short loc_1800276C5
0x1800276a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276ab  cmp     rcx, r12
0x1800276ae  jz      loc_180027770
0x1800276b4  test    byte ptr [rcx+44h], 1
0x1800276b8  jz      loc_18002774E
0x1800276be  mov     edx, 5Fh ; '_'
0x1800276c3  jmp     short loc_180027734
0x1800276c5  cmp     [rsp+78h+arg_0], 0
0x1800276cd  jz      short loc_1800276F5
0x1800276cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276d6  cmp     rcx, r12
0x1800276d9  jz      short loc_1800276F5
0x1800276db  test    byte ptr [rcx+44h], 4
0x1800276df  jz      short loc_1800276F5
0x1800276e1  mov     rcx, [rcx+38h]
0x1800276e5  mov     edx, 60h ; '`'
0x1800276ea  mov     r9d, esi
0x1800276ed  mov     r8, r13
0x1800276f0  call    WPP_SF_d
0x1800276f5  mov     dword ptr [rdi+0ACh], 0
0x1800276ff  mov     rdx, [rdi]
0x180027702  mov     rcx, r15
0x180027705  mov     r8, [rdx+0AB8h]
0x18002770c  mov     edx, [rdx+0AB0h]
0x180027712  call    MSMSetOneXConnectionProfile
0x180027717  mov     ebx, eax
0x180027719  test    eax, eax
0x18002771b  jz      short loc_180027747
0x18002771d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027724  cmp     rcx, r12
0x180027727  jz      short loc_180027770
0x180027729  test    byte ptr [rcx+44h], 1
0x18002772d  jz      short loc_18002774E
0x18002772f  mov     edx, 62h ; 'b'
0x180027734  mov     rcx, [rcx+38h]
0x180027738  mov     r9d, esi
0x18002773b  mov     r8, r13
0x18002773e  mov     [rsp+78h+var_58], eax
0x180027742  call    WPP_SF_dd
0x180027747  mov     rcx, cs:WPP_GLOBAL_Control
0x18002774e  cmp     rcx, r12
0x180027751  jz      short loc_180027770
0x180027753  test    dword ptr [rcx+44h], 800h
0x18002775a  jz      short loc_180027770
0x18002775c  mov     rcx, [rcx+38h]
0x180027760  mov     edx, 63h ; 'c'
0x180027765  mov     r9d, ebx
0x180027768  mov     r8, r13
0x18002776b  call    WPP_SF_D
0x180027770  mov     eax, ebx
0x180027772  add     rsp, 38h
0x180027776  pop     r15
0x180027778  pop     r14
0x18002777a  pop     r13
0x18002777c  pop     r12
0x18002777e  pop     rdi
0x18002777f  pop     rsi
0x180027780  pop     rbp
0x180027781  pop     rbx
0x180027782  retn
0x180027783  mov     r8, r14
0x180027786  mov     edx, ebp
0x180027788  mov     rcx, rdi
0x18002778b  call    EapUpdateMasterConnectionData
0x180027790  mov     ebx, eax
0x180027792  test    eax, eax
0x180027794  jz      loc_1800276FF
0x18002779a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277a1  cmp     rcx, r12
0x1800277a4  jz      short loc_180027770
0x1800277a6  test    byte ptr [rcx+44h], 1
0x1800277aa  jz      short loc_18002774E
0x1800277ac  mov     edx, 61h ; 'a'
0x1800277b1  jmp     short loc_180027734
```
