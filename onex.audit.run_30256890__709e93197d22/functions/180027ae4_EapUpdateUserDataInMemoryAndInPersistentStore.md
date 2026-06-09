# EapUpdateUserDataInMemoryAndInPersistentStore

- ea: `0x180027ae4`
- end: `0x180027c9c`
- name: `EapUpdateUserDataInMemoryAndInPersistentStore`
- size: `440`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180009540`
- `0x180015f90`
- `0x180024860`
- `0x180027158`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000abc0`
- `0x180010ae0`
- `0x180017840`
- `0x18001b360`
- `0x18001ce44`
- `0x1800214f0`
- `0x180027ae4`
- `0x18002eec8`

## pseudocode

```c
__int64 __fastcall EapUpdateUserDataInMemoryAndInPersistentStore(
        __int64 *a1,
        unsigned int a2,
        void *a3,
        unsigned int a4)
{
  __int64 v4; // r15
  unsigned int v9; // r14d
  unsigned int v10; // ebx
  unsigned int updated; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx

  v4 = *a1;
  v9 = *(_DWORD *)(*a1 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 100, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  if ( a3 || a2 )
  {
    updated = EapSetWorkingSetUserData(a1, a2, a3);
    v10 = updated;
    if ( updated )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v10;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_25;
      v13 = 101;
      goto LABEL_16;
    }
    updated = EapUpdateMasterUserData(a1, a2, a3, a4);
    v10 = updated;
    if ( updated )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v10;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_25;
      v13 = 102;
      goto LABEL_16;
    }
  }
  else
  {
    v10 = 0;
    OneXSetEapUserDataFlag(*(_QWORD *)(*a1 + 2760), a4);
  }
  if ( (unsigned int)SupplicantIsDoingPLAP(v4 + 2384) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
      goto LABEL_25;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 104, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9);
    goto LABEL_24;
  }
  updated = MSMUpdateOneXUserProfile(
              v4,
              *(_QWORD *)(*a1 + 2840),
              *(unsigned int *)(*a1 + 2752),
              *(_QWORD *)(*a1 + 2760));
  v10 = updated;
  if ( !updated )
  {
LABEL_24:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v13 = 103;
LABEL_16:
    WPP_SF_dd(v12[7], v13, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9, updated);
    goto LABEL_24;
  }
LABEL_25:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
    WPP_SF_D(v12[7], 105, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180027ae4  push    rbx
0x180027ae6  push    rbp
0x180027ae7  push    rsi
0x180027ae8  push    rdi
0x180027ae9  push    r12
0x180027aeb  push    r13
0x180027aed  push    r14
0x180027aef  push    r15
0x180027af1  sub     rsp, 38h
0x180027af5  mov     r15, [rcx]
0x180027af8  mov     r12d, r9d
0x180027afb  mov     rsi, r8
0x180027afe  mov     ebp, edx
0x180027b00  mov     rdi, rcx
0x180027b03  mov     r14d, [r15+14h]
0x180027b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b0e  lea     r13, WPP_GLOBAL_Control
0x180027b15  cmp     rcx, r13
0x180027b18  jz      short loc_180027B38
0x180027b1a  test    dword ptr [rcx+44h], 800h
0x180027b21  jz      short loc_180027B38
0x180027b23  mov     rcx, [rcx+38h]
0x180027b27  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180027b2e  mov     edx, 64h ; 'd'
0x180027b33  call    WPP_SF_
0x180027b38  test    rsi, rsi
0x180027b3b  jnz     short loc_180027BB4
0x180027b3d  test    ebp, ebp
0x180027b3f  jnz     short loc_180027BB4
0x180027b41  mov     rcx, [rdi]
0x180027b44  xor     ebx, ebx
0x180027b46  mov     edx, r12d
0x180027b49  mov     rcx, [rcx+0AC8h]
0x180027b50  call    OneXSetEapUserDataFlag
0x180027b55  lea     rcx, [r15+950h]
0x180027b5c  call    SupplicantIsDoingPLAP
0x180027b61  test    eax, eax
0x180027b63  jnz     loc_180027C32
0x180027b69  mov     rdx, [rdi]
0x180027b6c  mov     rcx, r15
0x180027b6f  mov     r9, [rdx+0AC8h]
0x180027b76  mov     r8d, [rdx+0AC0h]
0x180027b7d  mov     rdx, [rdx+0B18h]
0x180027b84  call    MSMUpdateOneXUserProfile
0x180027b89  mov     ebx, eax
0x180027b8b  test    eax, eax
0x180027b8d  jz      loc_180027C5C
0x180027b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b9a  cmp     rcx, r13
0x180027b9d  jz      loc_180027C89
0x180027ba3  test    byte ptr [rcx+44h], 1
0x180027ba7  jz      loc_180027C63
0x180027bad  mov     edx, 67h ; 'g'
0x180027bb2  jmp     short loc_180027BE6
0x180027bb4  mov     r8, rsi
0x180027bb7  mov     edx, ebp
0x180027bb9  mov     rcx, rdi
0x180027bbc  call    EapSetWorkingSetUserData
0x180027bc1  mov     ebx, eax
0x180027bc3  test    eax, eax
0x180027bc5  jz      short loc_180027BFF
0x180027bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bce  cmp     rcx, r13
0x180027bd1  jz      loc_180027C89
0x180027bd7  test    byte ptr [rcx+44h], 1
0x180027bdb  jz      loc_180027C63
0x180027be1  mov     edx, 65h ; 'e'
0x180027be6  mov     rcx, [rcx+38h]
0x180027bea  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180027bf1  mov     r9d, r14d
0x180027bf4  mov     [rsp+78h+var_58], eax
0x180027bf8  call    WPP_SF_dd
0x180027bfd  jmp     short loc_180027C5C
0x180027bff  mov     r9d, r12d
0x180027c02  mov     r8, rsi
0x180027c05  mov     edx, ebp
0x180027c07  mov     rcx, rdi
0x180027c0a  call    EapUpdateMasterUserData
0x180027c0f  mov     ebx, eax
0x180027c11  test    eax, eax
0x180027c13  jz      loc_180027B55
0x180027c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c20  cmp     rcx, r13
0x180027c23  jz      short loc_180027C89
0x180027c25  test    byte ptr [rcx+44h], 1
0x180027c29  jz      short loc_180027C63
0x180027c2b  mov     edx, 66h ; 'f'
0x180027c30  jmp     short loc_180027BE6
0x180027c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c39  cmp     rcx, r13
0x180027c3c  jz      short loc_180027C89
0x180027c3e  test    byte ptr [rcx+44h], 4
0x180027c42  jz      short loc_180027C63
0x180027c44  mov     rcx, [rcx+38h]
0x180027c48  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180027c4f  mov     edx, 68h ; 'h'
0x180027c54  mov     r9d, r14d
0x180027c57  call    WPP_SF_d
0x180027c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c63  cmp     rcx, r13
0x180027c66  jz      short loc_180027C89
0x180027c68  test    dword ptr [rcx+44h], 800h
0x180027c6f  jz      short loc_180027C89
0x180027c71  mov     rcx, [rcx+38h]
0x180027c75  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180027c7c  mov     edx, 69h ; 'i'
0x180027c81  mov     r9d, ebx
0x180027c84  call    WPP_SF_D
0x180027c89  mov     eax, ebx
0x180027c8b  add     rsp, 38h
0x180027c8f  pop     r15
0x180027c91  pop     r14
0x180027c93  pop     r13
0x180027c95  pop     r12
0x180027c97  pop     rdi
0x180027c98  pop     rsi
0x180027c99  pop     rbp
0x180027c9a  pop     rbx
0x180027c9b  retn
```
