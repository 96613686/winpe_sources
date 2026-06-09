# CompareOneXCredentials

- ea: `0x180002f64`
- end: `0x18000311a`
- name: `CompareOneXCredentials`
- size: `438`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ac0`
- `0x180002020`

## callees

- `0x180002f64`
- `0x180005440`
- `0x180007f60`
- `0x18000abc0`
- `0x18000c4c0`
- `0x180010ae0`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180003072`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180003072`

## pseudocode

```c
__int64 __fastcall CompareOneXCredentials(__int64 a1, int a2, PSID *a3, __int64 a4, int *a5)
{
  __int64 v6; // rbx
  __int64 v8; // rbp
  unsigned int v9; // esi
  _BYTE *v10; // r10
  int v11; // eax

  v6 = *(int *)(a1 + 444);
  v8 = a2;
  v9 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  *a5 = 0;
  if ( (_DWORD)v8 != (_DWORD)v6 )
  {
    if ( (_DWORD)v6 == 5 || v10 == (_BYTE *)&WPP_GLOBAL_Control || (v10[68] & 8) == 0 )
      goto LABEL_25;
    WPP_SF_dSS(
      *((_QWORD *)v10 + 7),
      31,
      (unsigned int)WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids,
      v9,
      (__int64)c_AuthIdentityDescription[v6],
      (__int64)c_AuthIdentityDescription[v8]);
LABEL_24:
    v10 = WPP_GLOBAL_Control;
LABEL_25:
    v11 = 1;
    goto LABEL_26;
  }
  if ( (_DWORD)v6 != 2 && (!(unsigned int)SupplicantIsDoingPLAP(a1) || (_DWORD)v6 != 3) )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || (v10[68] & 8) == 0 )
      goto LABEL_20;
    WPP_SF_dd(*((_QWORD *)v10 + 7), 32, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v9, v8);
    goto LABEL_19;
  }
  if ( !EqualSid(*a3, **(PSID **)(a1 + 464)) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_25;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v9);
    goto LABEL_24;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v9);
LABEL_19:
    v10 = WPP_GLOBAL_Control;
  }
LABEL_20:
  v11 = 0;
LABEL_26:
  *a5 = v11;
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v10 + 7), 35, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180002f64  push    rbx
0x180002f66  push    rbp
0x180002f67  push    rsi
0x180002f68  push    rdi
0x180002f69  push    r12
0x180002f6b  push    r13
0x180002f6d  push    r14
0x180002f6f  push    r15
0x180002f71  sub     rsp, 38h
0x180002f75  mov     rax, [rcx]
0x180002f78  mov     r15, r8
0x180002f7b  movsxd  rbx, dword ptr [rcx+1BCh]
0x180002f82  mov     rdi, rcx
0x180002f85  movsxd  rbp, edx
0x180002f88  mov     esi, [rax+14h]
0x180002f8b  mov     r10, cs:WPP_GLOBAL_Control
0x180002f92  lea     r12, WPP_GLOBAL_Control
0x180002f99  lea     r13, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180002fa0  cmp     r10, r12
0x180002fa3  jz      short loc_180002FC7
0x180002fa5  test    dword ptr [r10+44h], 800h
0x180002fad  jz      short loc_180002FC7
0x180002faf  mov     rcx, [r10+38h]
0x180002fb3  mov     edx, 1Eh
0x180002fb8  mov     r8, r13
0x180002fbb  call    WPP_SF_
0x180002fc0  mov     r10, cs:WPP_GLOBAL_Control
0x180002fc7  mov     r14, [rsp+78h+arg_20]
0x180002fcf  mov     dword ptr [r14], 0
0x180002fd6  cmp     ebp, ebx
0x180002fd8  jz      short loc_180003029
0x180002fda  cmp     ebx, 5
0x180002fdd  jz      loc_1800030DC
0x180002fe3  cmp     r10, r12
0x180002fe6  jz      loc_1800030DC
0x180002fec  test    byte ptr [r10+44h], 8
0x180002ff1  jz      loc_1800030DC
0x180002ff7  mov     rcx, [r10+38h]
0x180002ffb  lea     r8, c_AuthIdentityDescription
0x180003002  mov     rax, [r8+rbp*8]
0x180003006  mov     edx, 1Fh
0x18000300b  mov     [rsp+78h+var_50], rax
0x180003010  mov     r9d, esi
0x180003013  mov     rax, [r8+rbx*8]
0x180003017  mov     r8, r13
0x18000301a  mov     [rsp+78h+var_58], rax
0x18000301f  call    WPP_SF_dSS
0x180003024  jmp     loc_1800030D5
0x180003029  cmp     ebx, 2
0x18000302c  jz      short loc_180003065
0x18000302e  mov     rcx, rdi
0x180003031  call    SupplicantIsDoingPLAP
0x180003036  test    eax, eax
0x180003038  jz      short loc_18000303F
0x18000303a  cmp     ebx, 3
0x18000303d  jz      short loc_180003065
0x18000303f  cmp     r10, r12
0x180003042  jz      short loc_1800030AA
0x180003044  test    byte ptr [r10+44h], 8
0x180003049  jz      short loc_1800030AA
0x18000304b  mov     rcx, [r10+38h]
0x18000304f  mov     edx, 20h ; ' '
0x180003054  mov     r9d, esi
0x180003057  mov     dword ptr [rsp+78h+var_58], ebp
0x18000305b  mov     r8, r13
0x18000305e  call    WPP_SF_dd
0x180003063  jmp     short loc_1800030A3
0x180003065  mov     rdx, [rdi+1D0h]
0x18000306c  mov     rcx, [r15]; pSid1
0x18000306f  mov     rdx, [rdx]; pSid2
0x180003072  call    cs:__imp_EqualSid
0x180003078  test    eax, eax
0x18000307a  jz      short loc_1800030AE
0x18000307c  mov     r10, cs:WPP_GLOBAL_Control
0x180003083  cmp     r10, r12
0x180003086  jz      short loc_1800030AA
0x180003088  test    byte ptr [r10+44h], 8
0x18000308d  jz      short loc_1800030AA
0x18000308f  mov     rcx, [r10+38h]
0x180003093  mov     edx, 21h ; '!'
0x180003098  mov     r9d, esi
0x18000309b  mov     r8, r13
0x18000309e  call    WPP_SF_d
0x1800030a3  mov     r10, cs:WPP_GLOBAL_Control
0x1800030aa  xor     eax, eax
0x1800030ac  jmp     short loc_1800030E1
0x1800030ae  mov     r10, cs:WPP_GLOBAL_Control
0x1800030b5  cmp     r10, r12
0x1800030b8  jz      short loc_1800030DC
0x1800030ba  test    byte ptr [r10+44h], 8
0x1800030bf  jz      short loc_1800030DC
0x1800030c1  mov     rcx, [r10+38h]
0x1800030c5  mov     edx, 22h ; '"'
0x1800030ca  mov     r9d, esi
0x1800030cd  mov     r8, r13
0x1800030d0  call    WPP_SF_d
0x1800030d5  mov     r10, cs:WPP_GLOBAL_Control
0x1800030dc  mov     eax, 1
0x1800030e1  mov     [r14], eax
0x1800030e4  cmp     r10, r12
0x1800030e7  jz      short loc_180003107
0x1800030e9  test    dword ptr [r10+44h], 800h
0x1800030f1  jz      short loc_180003107
0x1800030f3  mov     rcx, [r10+38h]
0x1800030f7  mov     edx, 23h ; '#'
0x1800030fc  xor     r9d, r9d
0x1800030ff  mov     r8, r13
0x180003102  call    WPP_SF_D
0x180003107  xor     eax, eax
0x180003109  add     rsp, 38h
0x18000310d  pop     r15
0x18000310f  pop     r14
0x180003111  pop     r13
0x180003113  pop     r12
0x180003115  pop     rdi
0x180003116  pop     rsi
0x180003117  pop     rbp
0x180003118  pop     rbx
0x180003119  retn
```
