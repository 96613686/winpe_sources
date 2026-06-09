# MQSec_CopySecurityDescriptor(void *,void *,ulong,enumCopyControl)

- ea: `0x180027500`
- end: `0x180027717`
- name: `?MQSec_CopySecurityDescriptor@@YAHPEAX0KW4enumCopyControl@@@Z`
- size: `535`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f5c0`
- `0x180027ca0`
- `0x180027ed0`

## callees

- `0x1800138c0`
- `0x180027398`
- `0x180027500`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorControl` at `0x18002766f`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x1800276ed`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x18002766f`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x1800276ed`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x1800276c4`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x1800276c4`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1800275f1`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1800275f1`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800275d7`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800275d7`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800275b0`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800275b0`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180027596`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180027596`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180027564`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180027564`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800276a4`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800276a4`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180027646`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180027646`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180027626`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180027626`

## pseudocode

```c
__int64 __fastcall MQSec_CopySecurityDescriptor(void *a1, void *a2, char a3, int a4)
{
  unsigned __int16 v9; // cx
  WINBOOL bOwnerDefaulted; // [rsp+20h] [rbp-20h] BYREF
  WINBOOL bDaclPresent; // [rsp+24h] [rbp-1Ch] BYREF
  DWORD dwRevision; // [rsp+28h] [rbp-18h] BYREF
  PSID pOwner; // [rsp+30h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-8h] BYREF
  WORD pControl; // [rsp+68h] [rbp+28h] BYREF

  pDacl = 0;
  pOwner = 0;
  dwRevision = 0;
  if ( !a2 )
  {
    LogIllegalPoint((wchar_t *)L"acssctrl/secdscrp", 0x64u);
    return 0;
  }
  pControl = 0;
  if ( !GetSecurityDescriptorControl(a2, &pControl, &dwRevision) )
  {
    v9 = 102;
    return LogGleAssertReturnFalse(v9);
  }
  if ( (a3 & 1) != 0 )
  {
    bOwnerDefaulted = 0;
    if ( !GetSecurityDescriptorOwner(a2, &pOwner, &bOwnerDefaulted) )
    {
      v9 = 103;
      return LogGleAssertReturnFalse(v9);
    }
    if ( !SetSecurityDescriptorOwner(a1, pOwner, bOwnerDefaulted) )
    {
      v9 = 104;
      return LogGleAssertReturnFalse(v9);
    }
  }
  if ( (a3 & 2) != 0 )
  {
    bOwnerDefaulted = 0;
    if ( !GetSecurityDescriptorGroup(a2, &pOwner, &bOwnerDefaulted) )
    {
      v9 = 105;
      return LogGleAssertReturnFalse(v9);
    }
    if ( !SetSecurityDescriptorGroup(a1, pOwner, bOwnerDefaulted) )
    {
      v9 = 106;
      return LogGleAssertReturnFalse(v9);
    }
  }
  if ( (a3 & 4) != 0 )
  {
    bOwnerDefaulted = 0;
    bDaclPresent = 0;
    if ( !GetSecurityDescriptorDacl(a2, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
    {
      v9 = 107;
      return LogGleAssertReturnFalse(v9);
    }
    if ( !SetSecurityDescriptorDacl(a1, bDaclPresent, pDacl, bOwnerDefaulted) )
    {
      v9 = 108;
      return LogGleAssertReturnFalse(v9);
    }
    if ( a4 == 1 && !SetSecurityDescriptorControl(a1, 0x1500u, pControl & 0x1500) )
    {
      v9 = 109;
      return LogGleAssertReturnFalse(v9);
    }
  }
  if ( (a3 & 8) != 0 )
  {
    bDaclPresent = 0;
    bOwnerDefaulted = 0;
    if ( !GetSecurityDescriptorSacl(a2, &bOwnerDefaulted, &pDacl, &bDaclPresent) )
    {
      v9 = 110;
      return LogGleAssertReturnFalse(v9);
    }
    if ( !SetSecurityDescriptorSacl(a1, bOwnerDefaulted, pDacl, bDaclPresent) )
    {
      v9 = 111;
      return LogGleAssertReturnFalse(v9);
    }
    if ( a4 == 1 && !SetSecurityDescriptorControl(a1, 0x2A00u, pControl & 0x2A00) )
    {
      v9 = 112;
      return LogGleAssertReturnFalse(v9);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180027500  mov     [rsp-18h+arg_0], rbx
0x180027505  mov     [rsp-18h+arg_10], rsi
0x18002750a  push    rbp
0x18002750b  push    rdi
0x18002750c  push    r14
0x18002750e  mov     rbp, rsp
0x180027511  sub     rsp, 40h
0x180027515  mov     [rbp+pDacl], 0
0x18002751d  mov     r14d, r9d
0x180027520  mov     [rbp+pOwner], 0
0x180027528  mov     edi, r8d
0x18002752b  mov     [rbp+dwRevision], 0
0x180027532  mov     rbx, rdx
0x180027535  mov     rsi, rcx
0x180027538  test    rdx, rdx
0x18002753b  jnz     short loc_180027553
0x18002753d  lea     edx, [rbx+64h]; unsigned __int16
0x180027540  lea     rcx, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027547  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18002754c  xor     eax, eax
0x18002754e  jmp     loc_180027704
0x180027553  xor     eax, eax
0x180027555  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180027559  lea     rdx, [rbp+pControl]; pControl
0x18002755d  mov     [rbp+pControl], ax
0x180027561  mov     rcx, rbx; pSecurityDescriptor
0x180027564  call    cs:__imp_GetSecurityDescriptorControl
0x18002756a  test    eax, eax
0x18002756c  jnz     short loc_18002757E
0x18002756e  lea     ecx, [rax+66h]; unsigned __int16
0x180027571  call    ?LogGleAssertReturnFalse@@YA_NG@Z; LogGleAssertReturnFalse(ushort)
0x180027576  movzx   eax, al
0x180027579  jmp     loc_180027704
0x18002757e  test    dil, 1
0x180027582  jz      short loc_1800275BF
0x180027584  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180027588  mov     [rbp+bOwnerDefaulted], 0
0x18002758f  lea     rdx, [rbp+pOwner]; pOwner
0x180027593  mov     rcx, rbx; pSecurityDescriptor
0x180027596  call    cs:__imp_GetSecurityDescriptorOwner
0x18002759c  test    eax, eax
0x18002759e  jnz     short loc_1800275A5
0x1800275a0  lea     ecx, [rax+67h]
0x1800275a3  jmp     short loc_180027571
0x1800275a5  mov     r8d, [rbp+bOwnerDefaulted]; bOwnerDefaulted
0x1800275a9  mov     rcx, rsi; pSecurityDescriptor
0x1800275ac  mov     rdx, [rbp+pOwner]; pOwner
0x1800275b0  call    cs:__imp_SetSecurityDescriptorOwner
0x1800275b6  test    eax, eax
0x1800275b8  jnz     short loc_1800275BF
0x1800275ba  lea     ecx, [rax+68h]
0x1800275bd  jmp     short loc_180027571
0x1800275bf  test    dil, 2
0x1800275c3  jz      short loc_180027603
0x1800275c5  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x1800275c9  mov     [rbp+bOwnerDefaulted], 0
0x1800275d0  lea     rdx, [rbp+pOwner]; pGroup
0x1800275d4  mov     rcx, rbx; pSecurityDescriptor
0x1800275d7  call    cs:__imp_GetSecurityDescriptorGroup
0x1800275dd  test    eax, eax
0x1800275df  jnz     short loc_1800275E6
0x1800275e1  lea     ecx, [rax+69h]
0x1800275e4  jmp     short loc_180027571
0x1800275e6  mov     r8d, [rbp+bOwnerDefaulted]; bGroupDefaulted
0x1800275ea  mov     rcx, rsi; pSecurityDescriptor
0x1800275ed  mov     rdx, [rbp+pOwner]; pGroup
0x1800275f1  call    cs:__imp_SetSecurityDescriptorGroup
0x1800275f7  test    eax, eax
0x1800275f9  jnz     short loc_180027603
0x1800275fb  lea     ecx, [rax+6Ah]
0x1800275fe  jmp     loc_180027571
0x180027603  test    dil, 4
0x180027607  jz      short loc_180027681
0x180027609  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18002760d  mov     [rbp+bOwnerDefaulted], 0
0x180027614  lea     r8, [rbp+pDacl]; pDacl
0x180027618  mov     [rbp+bDaclPresent], 0
0x18002761f  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180027623  mov     rcx, rbx; pSecurityDescriptor
0x180027626  call    cs:__imp_GetSecurityDescriptorDacl
0x18002762c  test    eax, eax
0x18002762e  jnz     short loc_180027638
0x180027630  lea     ecx, [rax+6Bh]
0x180027633  jmp     loc_180027571
0x180027638  mov     r9d, [rbp+bOwnerDefaulted]; bDaclDefaulted
0x18002763c  mov     rcx, rsi; pSecurityDescriptor
0x18002763f  mov     r8, [rbp+pDacl]; pDacl
0x180027643  mov     edx, [rbp+bDaclPresent]; bDaclPresent
0x180027646  call    cs:__imp_SetSecurityDescriptorDacl
0x18002764c  test    eax, eax
0x18002764e  jnz     short loc_180027658
0x180027650  lea     ecx, [rax+6Ch]
0x180027653  jmp     loc_180027571
0x180027658  cmp     r14d, 1
0x18002765c  jnz     short loc_180027681
0x18002765e  movzx   r8d, [rbp+pControl]
0x180027663  mov     edx, 1500h; ControlBitsOfInterest
0x180027668  and     r8w, dx; ControlBitsToSet
0x18002766c  mov     rcx, rsi; pSecurityDescriptor
0x18002766f  call    cs:__imp_SetSecurityDescriptorControl
0x180027675  test    eax, eax
0x180027677  jnz     short loc_180027681
0x180027679  lea     ecx, [rax+6Dh]
0x18002767c  jmp     loc_180027571
0x180027681  test    dil, 8
0x180027685  jz      short loc_1800276FF
0x180027687  lea     r9, [rbp+bDaclPresent]; lpbSaclDefaulted
0x18002768b  mov     [rbp+bDaclPresent], 0
0x180027692  lea     r8, [rbp+pDacl]; pSacl
0x180027696  mov     [rbp+bOwnerDefaulted], 0
0x18002769d  lea     rdx, [rbp+bOwnerDefaulted]; lpbSaclPresent
0x1800276a1  mov     rcx, rbx; pSecurityDescriptor
0x1800276a4  call    cs:__imp_GetSecurityDescriptorSacl
0x1800276aa  test    eax, eax
0x1800276ac  jnz     short loc_1800276B6
0x1800276ae  lea     ecx, [rax+6Eh]
0x1800276b1  jmp     loc_180027571
0x1800276b6  mov     r9d, [rbp+bDaclPresent]; bSaclDefaulted
0x1800276ba  mov     rcx, rsi; pSecurityDescriptor
0x1800276bd  mov     r8, [rbp+pDacl]; pSacl
0x1800276c1  mov     edx, [rbp+bOwnerDefaulted]; bSaclPresent
0x1800276c4  call    cs:__imp_SetSecurityDescriptorSacl
0x1800276ca  test    eax, eax
0x1800276cc  jnz     short loc_1800276D6
0x1800276ce  lea     ecx, [rax+6Fh]
0x1800276d1  jmp     loc_180027571
0x1800276d6  cmp     r14d, 1
0x1800276da  jnz     short loc_1800276FF
0x1800276dc  movzx   r8d, [rbp+pControl]
0x1800276e1  mov     edx, 2A00h; ControlBitsOfInterest
0x1800276e6  and     r8w, dx; ControlBitsToSet
0x1800276ea  mov     rcx, rsi; pSecurityDescriptor
0x1800276ed  call    cs:__imp_SetSecurityDescriptorControl
0x1800276f3  test    eax, eax
0x1800276f5  jnz     short loc_1800276FF
0x1800276f7  lea     ecx, [rax+70h]
0x1800276fa  jmp     loc_180027571
0x1800276ff  mov     eax, 1
0x180027704  mov     rbx, [rsp+40h+arg_0]
0x180027709  mov     rsi, [rsp+40h+arg_10]
0x18002770e  add     rsp, 40h
0x180027712  pop     r14
0x180027714  pop     rdi
0x180027715  pop     rbp
0x180027716  retn
```
