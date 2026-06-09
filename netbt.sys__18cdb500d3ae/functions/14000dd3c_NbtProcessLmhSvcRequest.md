# NbtProcessLmhSvcRequest

- ea: `0x14000dd3c`
- end: `0x14000e261`
- name: `NbtProcessLmhSvcRequest`
- size: `1317`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000efd4`
- `0x140017214`
- `0x14001ba80`
- `0x14004d740`
- `0x14004f224`

## callees

- `0x140004880`
- `0x14000dccc`
- `0x14000dd3c`
- `0x140031140`
- `0x1400400a4`
- `0x140040294`
- `0x1400402b4`
- `0x140043b4c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e015`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e015`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dd78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dd78`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000de86`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000df4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000df88`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e037`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000de86`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000df4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000df88`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e037`

## pseudocode

```c
__int64 __fastcall NbtProcessLmhSvcRequest(__int64 a1, int a2, int a3)
{
  __int64 *v6; // r14
  KIRQL v7; // al
  __int64 v8; // rcx
  KIRQL v9; // r13
  _DWORD *v10; // r15
  __int64 v11; // r13
  __int64 v12; // rdx
  const void *v13; // r9
  unsigned int v14; // edi
  char *v15; // rdx
  unsigned int v16; // ecx
  int v17; // ebx
  KIRQL v18; // dl
  signed int v20; // edi
  __int64 v21; // rcx
  __int64 v22; // rsi
  __int64 v23; // rcx
  __int64 *v24; // r14
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rbx
  const char *v29; // r9
  const char *v30; // r9
  const char *v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rcx
  KIRQL NewIrql; // [rsp+88h] [rbp+10h]

  if ( a2 )
  {
    if ( a2 != 1 )
      return 3221225473LL;
    v6 = &DnsQueries;
  }
  else
  {
    v6 = &CheckAddr;
  }
  v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v8 = *(_QWORD *)(a1 + 40);
  v9 = v7;
  NewIrql = v7;
  *(_DWORD *)(a1 + 56) = 0;
  if ( !v8 || *(_DWORD *)(v8 + 360) != 1131832644 || !*v6 )
  {
    if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    {
      v31 = "NBT_RESOLVE_WITH_DNS";
      if ( a2 != 1 )
        v31 = "NBT_PING_IP_ADDRS";
      WPP_SF_s(1049, 24, WPP_e595452688c43ce128ab41f39d85d938_Traceguids, v31);
    }
    KeReleaseSpinLock(&SpinLock, v9);
    if ( *v6 )
    {
      if ( (BYTE3(xmmword_140038420) & 2) == 0 )
        return 3221225662LL;
      v32 = 25;
      v33 = 1049;
    }
    else
    {
      if ( (byte_140038413 & 2) == 0 )
        return 3221225662LL;
      v32 = 26;
      v33 = 537;
    }
    WPP_SF_(v33, v32, WPP_e595452688c43ce128ab41f39d85d938_Traceguids);
    return 3221225662LL;
  }
  if ( *((_BYTE *)v6 + 40) )
  {
    v22 = *(_QWORD *)(a1 + 24);
    v17 = 0;
    v23 = *(_QWORD *)(v22 + 24);
    if ( v23 && (v17 = NTCheckSetCancelRoutine(v23, NbtCancelWaitForLmhSvcIrp), v17 < 0) )
    {
      if ( (BYTE3(xmmword_140038420) & 2) != 0 )
      {
        v30 = "NBT_RESOLVE_WITH_DNS";
        if ( a2 != 1 )
          v30 = "NBT_PING_IP_ADDRS";
        WPP_SF_sD(1049, 31, (unsigned int)WPP_e595452688c43ce128ab41f39d85d938_Traceguids, (_DWORD)v30, v17);
        if ( (BYTE3(xmmword_140038420) & 2) != 0 )
          WPP_SF_d(1049, 32, WPP_e595452688c43ce128ab41f39d85d938_Traceguids, (unsigned int)v17);
      }
    }
    else
    {
      v24 = v6 + 1;
      *(_DWORD *)(v22 + 112) = a3;
      v25 = (__int64 *)v24[1];
      if ( (__int64 *)*v25 != v24 )
        __fastfail(3u);
      *(_QWORD *)a1 = v24;
      *(_QWORD *)(a1 + 8) = v25;
      *v25 = a1;
      v24[1] = a1;
    }
    v18 = v9;
    goto LABEL_23;
  }
  v10 = (_DWORD *)v6[4];
  if ( !v10 )
  {
    v26 = *(_QWORD *)(*v6 + 8);
    v10 = (*(_BYTE *)(v26 + 10) & 5) != 0
        ? *(_DWORD **)(v26 + 24)
        : MmMapLockedPagesSpecifyCache((PMDL)v26, 0, MmCached, 0, 0, 0x40000020u);
    v6[4] = (__int64)v10;
    if ( !v10 )
    {
      KeReleaseSpinLock(&SpinLock, v9);
      if ( (byte_14003841B & 2) != 0 )
        WPP_SF_(793, 27, WPP_e595452688c43ce128ab41f39d85d938_Traceguids);
      return 3221225473LL;
    }
  }
  *((_BYTE *)v6 + 40) = 1;
  v6[3] = a1;
  v10[131] = a3;
  v11 = *(_QWORD *)(a1 + 24);
  if ( !a2 )
  {
    v27 = *(unsigned int *)(v11 + 228);
    if ( (unsigned int)v27 > 0x1A )
      v27 = 26;
    v28 = (unsigned int)v27;
    memmove(v10 + 132, *(const void **)(v11 + 232), 4 * v27);
    v10[v28 + 132] = 0;
LABEL_33:
    v21 = *(_QWORD *)(v11 + 24);
    if ( !v21 || (v17 = NTCheckSetCancelRoutine(v21, NbtCancelWaitForLmhSvcIrp), v17 >= 0) )
    {
      v6[4] = 0;
      KeReleaseSpinLock(&SpinLock, NewIrql);
      NTIoComplete((PIRP)*v6, 0, 0);
      return 259;
    }
    goto LABEL_19;
  }
  if ( a2 != 1 )
    goto LABEL_33;
  v12 = *(_QWORD *)(a1 + 16);
  if ( v11 )
    v13 = *(const void **)(v11 + 312);
  else
    v13 = 0;
  if ( v12 )
  {
    v14 = 16;
    v15 = (char *)(*(_QWORD *)(v12 + 48) + 164LL);
  }
  else
  {
    v14 = *(_DWORD *)(v11 + 212);
    v15 = *(char **)(v11 + 40);
    if ( v14 != 16 )
    {
      if ( v14 > 0xFF )
        v14 = 255;
      goto LABEL_29;
    }
  }
  v16 = v15[15];
  if ( v15[15] != 1 && (unsigned __int8)(v16 - 27) > 3u )
  {
    if ( (unsigned __int8)(v16 - 33) > 0x5Du )
      v14 = 15;
LABEL_29:
    if ( v13 )
    {
      v20 = *(_DWORD *)(v11 + 280);
      if ( (unsigned int)v20 > 0x1FE )
        v20 = 510;
      memmove(v10, v13, v20);
      *((_WORD *)v10 + ((unsigned __int64)v20 >> 1)) = 0;
      v10[128] = v20;
      v10[129] = 1;
    }
    else
    {
      v10[129] = 0;
      memmove(v10, v15, v14);
      *((_BYTE *)v10 + v14) = 0;
      v10[128] = v14;
    }
    goto LABEL_33;
  }
  if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    WPP_SF_d(1049, 28, WPP_e595452688c43ce128ab41f39d85d938_Traceguids, v16);
  v17 = -1073741634;
LABEL_19:
  if ( (BYTE11(xmmword_140038420) & 2) != 0 )
    WPP_SF_d(1305, 29, WPP_e595452688c43ce128ab41f39d85d938_Traceguids, (unsigned int)v17);
  if ( (BYTE3(xmmword_140038420) & 2) != 0 )
  {
    v29 = "NBT_RESOLVE_WITH_DNS";
    if ( a2 != 1 )
      v29 = "NBT_PING_IP_ADDRS";
    WPP_SF_sD(1049, 30, (unsigned int)WPP_e595452688c43ce128ab41f39d85d938_Traceguids, (_DWORD)v29, v17);
  }
  v18 = NewIrql;
  *((_BYTE *)v6 + 40) = 0;
  v6[3] = 0;
LABEL_23:
  KeReleaseSpinLock(&SpinLock, v18);
  if ( v17 >= 0 )
    return 259;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14000dd3c  push    rbx
0x14000dd3e  push    rbp
0x14000dd3f  push    rsi
0x14000dd40  push    rdi
0x14000dd41  push    r12
0x14000dd43  push    r13
0x14000dd45  push    r14
0x14000dd47  push    r15
0x14000dd49  sub     rsp, 38h
0x14000dd4d  mov     ebp, r8d
0x14000dd50  mov     r12d, edx
0x14000dd53  mov     rdi, rcx
0x14000dd56  test    edx, edx
0x14000dd58  jz      loc_14000E099
0x14000dd5e  cmp     edx, 1
0x14000dd61  jnz     loc_14000E064
0x14000dd67  lea     r14, DnsQueries
0x14000dd6e  lea     rbx, SpinLock
0x14000dd75  mov     rcx, rbx; SpinLock
0x14000dd78  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000dd7f  nop     dword ptr [rax+rax+00h]
0x14000dd84  mov     rcx, [rdi+28h]
0x14000dd88  mov     r13b, al
0x14000dd8b  mov     [rsp+78h+NewIrql], al
0x14000dd92  mov     dword ptr [rdi+38h], 0
0x14000dd99  test    rcx, rcx
0x14000dd9c  jz      loc_14000DF6D
0x14000dda2  cmp     dword ptr [rcx+168h], 43766544h
0x14000ddac  jnz     loc_14000DF6D
0x14000ddb2  mov     rcx, [r14]
0x14000ddb5  test    rcx, rcx
0x14000ddb8  jz      loc_14000DF6D
0x14000ddbe  cmp     byte ptr [r14+28h], 0
0x14000ddc3  jnz     loc_14000DFB5
0x14000ddc9  mov     r15, [r14+20h]
0x14000ddcd  test    r15, r15
0x14000ddd0  jz      loc_14000DFF2
0x14000ddd6  mov     byte ptr [r14+28h], 1
0x14000dddb  mov     sil, 2
0x14000ddde  mov     [r14+18h], rdi
0x14000dde2  mov     [r15+20Ch], ebp
0x14000dde9  mov     ebp, 419h
0x14000ddee  mov     r13, [rdi+18h]
0x14000ddf2  test    r12d, r12d
0x14000ddf5  jz      loc_14000E0F3
0x14000ddfb  cmp     r12d, 1
0x14000ddff  jnz     loc_14000DF15
0x14000de05  mov     rdx, [rdi+10h]
0x14000de09  test    r13, r13
0x14000de0c  jz      loc_14000E06E
0x14000de12  mov     r9, [r13+138h]
0x14000de19  test    rdx, rdx
0x14000de1c  jz      loc_14000DEB0
0x14000de22  mov     rdx, [rdx+30h]
0x14000de26  mov     edi, 10h
0x14000de2b  add     rdx, 0A4h
0x14000de32  movsx   ecx, byte ptr [rdx+0Fh]
0x14000de36  cmp     cl, 1
0x14000de39  jnz     loc_14000E0A5
0x14000de3f  test    byte ptr cs:xmmword_140038420+3, sil
0x14000de46  jnz     loc_14000E0B2
0x14000de4c  mov     ebx, 0C00000BEh
0x14000de51  test    byte ptr cs:xmmword_140038420+0Bh, sil
0x14000de58  jnz     loc_14000E132
0x14000de5e  test    byte ptr cs:xmmword_140038420+3, sil
0x14000de65  jnz     loc_14000E150
0x14000de6b  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x14000de72  mov     byte ptr [r14+28h], 0
0x14000de77  mov     qword ptr [r14+18h], 0
0x14000de7f  lea     rcx, SpinLock; SpinLock
0x14000de86  call    cs:__imp_KeReleaseSpinLock
0x14000de8d  nop     dword ptr [rax+rax+00h]
0x14000de92  mov     eax, 103h
0x14000de97  test    ebx, ebx
0x14000de99  cmovns  ebx, eax
0x14000de9c  mov     eax, ebx
0x14000de9e  add     rsp, 38h
0x14000dea2  pop     r15
0x14000dea4  pop     r14
0x14000dea6  pop     r13
0x14000dea8  pop     r12
0x14000deaa  pop     rdi
0x14000deab  pop     rsi
0x14000deac  pop     rbp
0x14000dead  pop     rbx
0x14000deae  retn
0x14000deb0  mov     edi, [r13+0D4h]
0x14000deb7  mov     rdx, [r13+28h]; Src
0x14000debb  cmp     edi, 10h
0x14000debe  jz      loc_14000DE32
0x14000dec4  mov     eax, 0FFh
0x14000dec9  cmp     edi, eax
0x14000decb  cmova   edi, eax
0x14000dece  mov     rcx, r15; void *
0x14000ded1  test    r9, r9
0x14000ded4  jz      loc_14000E0CD
0x14000deda  mov     edi, [r13+118h]
0x14000dee1  mov     eax, 1FEh
0x14000dee6  cmp     edi, eax
0x14000dee8  mov     rdx, r9; Src
0x14000deeb  cmova   edi, eax
0x14000deee  movsxd  rbx, edi
0x14000def1  mov     r8, rbx; Size
0x14000def4  call    memmove
0x14000def9  shr     rbx, 1
0x14000defc  xor     eax, eax
0x14000defe  mov     [r15+rbx*2], ax
0x14000df03  mov     [r15+200h], edi
0x14000df0a  mov     dword ptr [r15+204h], 1
0x14000df15  mov     rcx, [r13+18h]
0x14000df19  test    rcx, rcx
0x14000df1c  jz      short loc_14000DF34
0x14000df1e  lea     rdx, NbtCancelWaitForLmhSvcIrp
0x14000df25  call    NTCheckSetCancelRoutine
0x14000df2a  mov     ebx, eax
0x14000df2c  test    eax, eax
0x14000df2e  js      loc_14000DE51
0x14000df34  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x14000df3b  lea     rcx, SpinLock; SpinLock
0x14000df42  mov     qword ptr [r14+20h], 0
0x14000df4a  call    cs:__imp_KeReleaseSpinLock
0x14000df51  nop     dword ptr [rax+rax+00h]
0x14000df56  mov     rcx, [r14]; Irp
0x14000df59  xor     r8d, r8d
0x14000df5c  xor     edx, edx
0x14000df5e  call    NTIoComplete
0x14000df63  mov     eax, 103h
0x14000df68  jmp     loc_14000DE9E
0x14000df6d  mov     sil, 2
0x14000df70  mov     ebp, 419h
0x14000df75  test    byte ptr cs:xmmword_140038420+3, sil
0x14000df7c  jnz     loc_14000E202
0x14000df82  mov     dl, r13b; NewIrql
0x14000df85  mov     rcx, rbx; SpinLock
0x14000df88  call    cs:__imp_KeReleaseSpinLock
0x14000df8f  nop     dword ptr [rax+rax+00h]
0x14000df94  cmp     qword ptr [r14], 0
0x14000df98  jnz     loc_14000E230
0x14000df9e  test    cs:byte_140038413, sil
0x14000dfa5  jnz     loc_14000E246
0x14000dfab  mov     eax, 0C00000BEh
0x14000dfb0  jmp     loc_14000DE9E
0x14000dfb5  mov     rsi, [rdi+18h]
0x14000dfb9  xor     ebx, ebx
0x14000dfbb  mov     rcx, [rsi+18h]
0x14000dfbf  test    rcx, rcx
0x14000dfc2  jnz     loc_14000E182
0x14000dfc8  add     r14, 8
0x14000dfcc  mov     [rsi+70h], ebp
0x14000dfcf  mov     rax, [r14+8]
0x14000dfd3  cmp     [rax], r14
0x14000dfd6  jnz     loc_14000E07C
0x14000dfdc  mov     [rdi], r14
0x14000dfdf  mov     [rdi+8], rax
0x14000dfe3  mov     [rax], rdi
0x14000dfe6  mov     [r14+8], rdi
0x14000dfea  mov     dl, r13b
0x14000dfed  jmp     loc_14000DE7F
0x14000dff2  mov     rcx, [rcx+8]; MemoryDescriptorList
0x14000dff6  test    byte ptr [rcx+0Ah], 5
0x14000dffa  jnz     short loc_14000E076
0x14000dffc  xor     r9d, r9d; RequestedAddress
0x14000dfff  mov     [rsp+78h+Priority], 40000020h; Priority
0x14000e007  xor     edx, edx; AccessMode
0x14000e009  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000e011  lea     r8d, [r9+1]; CacheType
0x14000e015  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000e01c  nop     dword ptr [rax+rax+00h]
0x14000e021  mov     r15, rax
0x14000e024  mov     [r14+20h], r15
0x14000e028  test    r15, r15
0x14000e02b  jnz     loc_14000DDD6
0x14000e031  mov     dl, r13b; NewIrql
0x14000e034  mov     rcx, rbx; SpinLock
0x14000e037  call    cs:__imp_KeReleaseSpinLock
0x14000e03e  nop     dword ptr [rax+rax+00h]
0x14000e043  mov     sil, 2
0x14000e046  test    cs:byte_14003841B, sil
0x14000e04d  jz      short loc_14000E064
0x14000e04f  lea     edx, [r15+1Bh]
0x14000e053  mov     ecx, 319h
0x14000e058  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14000e05f  call    WPP_SF_
0x14000e064  mov     eax, 0C0000001h
0x14000e069  jmp     loc_14000DE9E
0x14000e06e  xor     r9d, r9d
0x14000e071  jmp     loc_14000DE19
0x14000e076  mov     r15, [rcx+18h]
0x14000e07a  jmp     short loc_14000E024
0x14000e07c  mov     ecx, 3
0x14000e081  int     29h; Win8: RtlFailFast(ecx)
0x14000e083  sub     cl, 21h ; '!'
0x14000e086  cmp     cl, 5Dh ; ']'
0x14000e089  jbe     loc_14000DECE
0x14000e08f  mov     edi, 0Fh
0x14000e094  jmp     loc_14000DECE
0x14000e099  lea     r14, CheckAddr
0x14000e0a0  jmp     loc_14000DD6E
0x14000e0a5  lea     eax, [rcx-1Bh]
0x14000e0a8  cmp     al, 3
0x14000e0aa  jbe     loc_14000DE3F
0x14000e0b0  jmp     short loc_14000E083
0x14000e0b2  mov     r9d, ecx
0x14000e0b5  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14000e0bc  mov     ecx, ebp
0x14000e0be  mov     edx, 1Ch
0x14000e0c3  call    WPP_SF_d
0x14000e0c8  jmp     loc_14000DE4C
0x14000e0cd  mov     r8d, edi; Size
0x14000e0d0  mov     dword ptr [r15+204h], 0
0x14000e0db  mov     ebx, edi
0x14000e0dd  call    memmove
0x14000e0e2  mov     byte ptr [rbx+r15], 0
0x14000e0e7  mov     [r15+200h], edi
0x14000e0ee  jmp     loc_14000DF15
0x14000e0f3  mov     eax, [r13+0E4h]
0x14000e0fa  lea     rcx, [r15+210h]; void *
0x14000e101  mov     edx, 1Ah
0x14000e106  cmp     eax, edx
0x14000e108  cmova   eax, edx
0x14000e10b  mov     rdx, [r13+0E8h]; Src
0x14000e112  mov     ebx, eax
0x14000e114  lea     r8, ds:0[rax*4]; Size
0x14000e11c  call    memmove
0x14000e121  mov     dword ptr [r15+rbx*4+210h], 0
0x14000e12d  jmp     loc_14000DF15
0x14000e132  mov     edx, 1Dh
0x14000e137  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14000e13e  mov     ecx, 519h
0x14000e143  mov     r9d, ebx
0x14000e146  call    WPP_SF_d
0x14000e14b  jmp     loc_14000DE5E
0x14000e150  cmp     r12d, 1
0x14000e154  mov     [rsp+78h+BugCheckOnFailure], ebx
0x14000e158  lea     rax, aNbtPingIpAddrs; "NBT_PING_IP_ADDRS"
0x14000e15f  mov     edx, 1Eh
0x14000e164  lea     r9, aNbtResolveWith; "NBT_RESOLVE_WITH_DNS"
0x14000e16b  mov     ecx, ebp
0x14000e16d  cmovnz  r9, rax
0x14000e171  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14000e178  call    WPP_SF_sD
0x14000e17d  jmp     loc_14000DE6B
0x14000e182  lea     rdx, NbtCancelWaitForLmhSvcIrp
0x14000e189  call    NTCheckSetCancelRoutine
0x14000e18e  mov     ebx, eax
0x14000e190  test    eax, eax
0x14000e192  jns     loc_14000DFC8
0x14000e198  mov     sil, 2
0x14000e19b  mov     ebp, 419h
0x14000e1a0  test    byte ptr cs:xmmword_140038420+3, sil
0x14000e1a7  jz      loc_14000DFEA
0x14000e1ad  cmp     r12d, 1
0x14000e1b1  mov     [rsp+78h+BugCheckOnFailure], ebx
0x14000e1b5  lea     rax, aNbtPingIpAddrs; "NBT_PING_IP_ADDRS"
0x14000e1bc  mov     edx, 1Fh
0x14000e1c1  lea     r9, aNbtResolveWith; "NBT_RESOLVE_WITH_DNS"
0x14000e1c8  mov     ecx, ebp
0x14000e1ca  cmovnz  r9, rax
0x14000e1ce  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14000e1d5  call    WPP_SF_sD
0x14000e1da  test    byte ptr cs:xmmword_140038420+3, sil
0x14000e1e1  jz      loc_14000DFEA
0x14000e1e7  mov     edx, 20h ; ' '
0x14000e1ec  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14000e1f3  mov     ecx, ebp
0x14000e1f5  mov     r9d, ebx
0x14000e1f8  call    WPP_SF_d
0x14000e1fd  jmp     loc_14000DFEA
0x14000e202  cmp     r12d, 1
0x14000e206  lea     rax, aNbtPingIpAddrs; "NBT_PING_IP_ADDRS"
0x14000e20d  lea     r9, aNbtResolveWith; "NBT_RESOLVE_WITH_DNS"
0x14000e214  mov     edx, 18h
0x14000e219  cmovnz  r9, rax
0x14000e21d  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14000e224  mov     ecx, ebp
0x14000e226  call    WPP_SF_s
0x14000e22b  jmp     loc_14000DF82
0x14000e230  test    byte ptr cs:xmmword_140038420+3, sil
0x14000e237  jz      loc_14000DFAB
0x14000e23d  mov     edx, 19h
0x14000e242  mov     ecx, ebp
0x14000e244  jmp     short loc_14000E250
0x14000e246  mov     edx, 1Ah
0x14000e24b  mov     ecx, 219h
0x14000e250  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14000e257  call    WPP_SF_
0x14000e25c  jmp     loc_14000DFAB
```
