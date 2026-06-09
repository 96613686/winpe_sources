# CompareUserInfo

- ea: `0x18001e290`
- end: `0x18001e4e2`
- name: `CompareUserInfo`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003120`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000abc0`
- `0x18000c4c0`
- `0x180010ae0`
- `0x180019cd0`
- `0x18001a6cc`
- `0x18001e290`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e42e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e42e`
- `MobileNetworking!FreeMemory` at `0x18001e4a0`
- `MobileNetworking!FreeMemory` at `0x18001e4a0`

## string_xrefs

- `0x18001e491`: `CompareUserInfo`

## pseudocode

```c
__int64 __fastcall CompareUserInfo(__int64 a1, unsigned int a2, __int64 a3, int a4, PSID *a5, int a6)
{
  __int64 v7; // rbp
  __int64 v9; // r14
  int v11; // esi
  _QWORD *v12; // r10
  unsigned int v13; // ebx
  unsigned int v14; // eax
  PSID *v16; // [rsp+90h] [rbp+18h] BYREF

  v7 = *(int *)(a3 + 12);
  v9 = a4;
  if ( (*(_BYTE *)(a3 + 20) & 1) != 0 )
    v11 = *(_DWORD *)(a3 + 24);
  else
    v11 = -1;
  v16 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 36, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( (_DWORD)v9 != (_DWORD)v7 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 8) != 0 )
      WPP_SF_dSS(
        v12[7],
        37,
        (unsigned int)WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids,
        a2,
        (__int64)c_AuthIdentityDescription[v7],
        (__int64)c_AuthIdentityDescription[v9]);
LABEL_33:
    v13 = 5023;
    goto LABEL_34;
  }
  if ( (_DWORD)v7 == 2 || (unsigned int)SupplicantIsDoingPLAP(a1) && (_DWORD)v7 == 3 )
  {
    if ( a6 != v11 )
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 8) != 0 )
        WPP_SF_ddd(v12[7], 39, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, a2, v11, a6);
      goto LABEL_33;
    }
    v14 = OneXGetTokenInformation(*(HANDLE *)(a3 + 32), (LPVOID *)&v16);
    v13 = v14;
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 40, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, a2, v14);
    }
    else
    {
      if ( !EqualSid(*a5, *v16) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 42, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, a2);
        goto LABEL_33;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, a2);
    }
  }
  else
  {
    v13 = 0;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 8) != 0 )
      WPP_SF_dd(v12[7], 38, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, a2, v9);
  }
LABEL_34:
  FreeMemory(&v16, "CompareUserInfo", 423);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 43, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18001e290  push    rbx
0x18001e292  push    rbp
0x18001e293  push    rsi
0x18001e294  push    rdi
0x18001e295  push    r12
0x18001e297  push    r13
0x18001e299  push    r14
0x18001e29b  push    r15
0x18001e29d  sub     rsp, 38h
0x18001e2a1  test    byte ptr [r8+14h], 1
0x18001e2a6  mov     rbx, r8
0x18001e2a9  movsxd  rbp, dword ptr [r8+0Ch]
0x18001e2ad  mov     edi, edx
0x18001e2af  movsxd  r14, r9d
0x18001e2b2  mov     r15, rcx
0x18001e2b5  jz      short loc_18001E2BD
0x18001e2b7  mov     esi, [r8+18h]
0x18001e2bb  jmp     short loc_18001E2C0
0x18001e2bd  or      esi, 0FFFFFFFFh
0x18001e2c0  mov     [rsp+78h+arg_10], 0
0x18001e2cc  mov     r10, cs:WPP_GLOBAL_Control
0x18001e2d3  lea     r12, WPP_GLOBAL_Control
0x18001e2da  lea     r13, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x18001e2e1  cmp     r10, r12
0x18001e2e4  jz      short loc_18001E308
0x18001e2e6  test    dword ptr [r10+44h], 800h
0x18001e2ee  jz      short loc_18001E308
0x18001e2f0  mov     rcx, [r10+38h]
0x18001e2f4  mov     edx, 24h ; '$'
0x18001e2f9  mov     r8, r13
0x18001e2fc  call    WPP_SF_
0x18001e301  mov     r10, cs:WPP_GLOBAL_Control
0x18001e308  cmp     r14d, ebp
0x18001e30b  jz      short loc_18001E353
0x18001e30d  cmp     r10, r12
0x18001e310  jz      loc_18001E486
0x18001e316  test    byte ptr [r10+44h], 8
0x18001e31b  jz      loc_18001E486
0x18001e321  mov     rcx, [r10+38h]
0x18001e325  lea     r8, c_AuthIdentityDescription
0x18001e32c  mov     rax, [r8+r14*8]
0x18001e330  mov     edx, 25h ; '%'
0x18001e335  mov     [rsp+78h+var_50], rax
0x18001e33a  mov     r9d, edi
0x18001e33d  mov     rax, [r8+rbp*8]
0x18001e341  mov     r8, r13
0x18001e344  mov     [rsp+78h+var_58], rax
0x18001e349  call    WPP_SF_dSS
0x18001e34e  jmp     loc_18001E486
0x18001e353  cmp     ebp, 2
0x18001e356  jz      short loc_18001E38D
0x18001e358  mov     rcx, r15
0x18001e35b  call    SupplicantIsDoingPLAP
0x18001e360  test    eax, eax
0x18001e362  jz      short loc_18001E369
0x18001e364  cmp     ebp, 3
0x18001e367  jz      short loc_18001E38D
0x18001e369  xor     ebx, ebx
0x18001e36b  cmp     r10, r12
0x18001e36e  jz      loc_18001E48B
0x18001e374  test    byte ptr [r10+44h], 8
0x18001e379  jz      loc_18001E48B
0x18001e37f  mov     rcx, [r10+38h]
0x18001e383  lea     edx, [rbx+26h]
0x18001e386  mov     dword ptr [rsp+78h+var_58], r14d
0x18001e38b  jmp     short loc_18001E40B
0x18001e38d  mov     eax, [rsp+78h+arg_28]
0x18001e394  cmp     eax, esi
0x18001e396  jz      short loc_18001E3CD
0x18001e398  cmp     r10, r12
0x18001e39b  jz      loc_18001E486
0x18001e3a1  test    byte ptr [r10+44h], 8
0x18001e3a6  jz      loc_18001E486
0x18001e3ac  mov     rcx, [r10+38h]
0x18001e3b0  mov     edx, 27h ; '''
0x18001e3b5  mov     dword ptr [rsp+78h+var_50], eax
0x18001e3b9  mov     r9d, edi
0x18001e3bc  mov     r8, r13
0x18001e3bf  mov     dword ptr [rsp+78h+var_58], esi
0x18001e3c3  call    WPP_SF_ddd
0x18001e3c8  jmp     loc_18001E486
0x18001e3cd  mov     rcx, [rbx+20h]; TokenHandle
0x18001e3d1  lea     rdx, [rsp+78h+arg_10]
0x18001e3d9  call    OneXGetTokenInformation
0x18001e3de  mov     ebx, eax
0x18001e3e0  test    eax, eax
0x18001e3e2  jz      short loc_18001E418
0x18001e3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3eb  cmp     rcx, r12
0x18001e3ee  jz      loc_18001E48B
0x18001e3f4  test    byte ptr [rcx+44h], 1
0x18001e3f8  jz      loc_18001E48B
0x18001e3fe  mov     rcx, [rcx+38h]
0x18001e402  mov     edx, 28h ; '('
0x18001e407  mov     dword ptr [rsp+78h+var_58], eax
0x18001e40b  mov     r8, r13
0x18001e40e  mov     r9d, edi
0x18001e411  call    WPP_SF_dd
0x18001e416  jmp     short loc_18001E48B
0x18001e418  mov     rdx, [rsp+78h+arg_10]
0x18001e420  mov     rcx, [rsp+78h+arg_20]
0x18001e428  mov     rdx, [rdx]; pSid2
0x18001e42b  mov     rcx, [rcx]; pSid1
0x18001e42e  call    cs:__imp_EqualSid
0x18001e434  test    eax, eax
0x18001e436  jz      short loc_18001E460
0x18001e438  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e43f  cmp     rcx, r12
0x18001e442  jz      short loc_18001E48B
0x18001e444  test    byte ptr [rcx+44h], 8
0x18001e448  jz      short loc_18001E48B
0x18001e44a  mov     rcx, [rcx+38h]
0x18001e44e  mov     edx, 29h ; ')'
0x18001e453  mov     r9d, edi
0x18001e456  mov     r8, r13
0x18001e459  call    WPP_SF_d
0x18001e45e  jmp     short loc_18001E48B
0x18001e460  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e467  cmp     rcx, r12
0x18001e46a  jz      short loc_18001E486
0x18001e46c  test    byte ptr [rcx+44h], 8
0x18001e470  jz      short loc_18001E486
0x18001e472  mov     rcx, [rcx+38h]
0x18001e476  mov     edx, 2Ah ; '*'
0x18001e47b  mov     r9d, edi
0x18001e47e  mov     r8, r13
0x18001e481  call    WPP_SF_d
0x18001e486  mov     ebx, 139Fh
0x18001e48b  mov     r8d, 1A7h
0x18001e491  lea     rdx, aCompareuserinf; "CompareUserInfo"
0x18001e498  lea     rcx, [rsp+78h+arg_10]
0x18001e4a0  call    cs:__imp_FreeMemory
0x18001e4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4ad  cmp     rcx, r12
0x18001e4b0  jz      short loc_18001E4CF
0x18001e4b2  test    dword ptr [rcx+44h], 800h
0x18001e4b9  jz      short loc_18001E4CF
0x18001e4bb  mov     rcx, [rcx+38h]
0x18001e4bf  mov     edx, 2Bh ; '+'
0x18001e4c4  mov     r9d, ebx
0x18001e4c7  mov     r8, r13
0x18001e4ca  call    WPP_SF_D
0x18001e4cf  mov     eax, ebx
0x18001e4d1  add     rsp, 38h
0x18001e4d5  pop     r15
0x18001e4d7  pop     r14
0x18001e4d9  pop     r13
0x18001e4db  pop     r12
0x18001e4dd  pop     rdi
0x18001e4de  pop     rsi
0x18001e4df  pop     rbp
0x18001e4e0  pop     rbx
0x18001e4e1  retn
```
