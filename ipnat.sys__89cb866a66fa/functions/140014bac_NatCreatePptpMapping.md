# NatCreatePptpMapping

- ea: `0x140014bac`
- end: `0x140014f29`
- name: `NatCreatePptpMapping`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400145f8`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140006a08`
- `0x140006e18`
- `0x14000bbfc`
- `0x140014068`
- `0x140014bac`
- `0x1400158c8`
- `0x140016ad8`
- `0x14002cbc0`

## pseudocode

```c
__int64 __fastcall NatCreatePptpMapping(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        _QWORD *a7)
{
  __int64 v7; // rdi
  unsigned __int16 v8; // si
  __int64 v9; // rbp
  __int64 v10; // r14
  int v11; // r15d
  _QWORD *v12; // rbx
  int v14; // eax
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // rdx
  PVOID Entry; // [rsp+40h] [rbp-48h] BYREF

  v7 = a4;
  v8 = a3;
  v9 = (unsigned int)a2;
  v10 = a1;
  v11 = a6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_DDdDL(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, a2, (unsigned __int16)a3, a4, a6);
  }
  a5 = 0;
  Entry = 0;
  NatAllocateBlockWithLimitCheck(&PptpLookasideList, &Entry, 72);
  v12 = Entry;
  if ( !Entry )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, 3221225495LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, 3221225495LL);
      }
    }
    return 3221225495LL;
  }
  memset(Entry, 0, 0x48u);
  *((_DWORD *)v12 + 14) = 1;
  v12[5] = v10 | (v7 << 32);
  v12[4] = v10 | (v9 << 32);
  if ( v11 == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
    }
    *((_WORD *)v12 + 24) = v8;
    v14 = NatAllocatePublicPptpCallId(v12[5], (char *)v12 + 50, &a5);
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids,
          (unsigned int)v14);
      }
      NatFreeBlockAndUpdateStateAllocationUsage(&PptpLookasideList, v12, 72);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 3221225473LL;
      }
      v16 = 22;
LABEL_44:
      WPP_SF_d(v15->AttachedDevice, v16, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, 3221225473LL);
      return 3221225473LL;
    }
    v17 = a5;
    v18 = *(_QWORD **)(a5 + 8);
    if ( *v18 == a5 )
    {
      *v12 = a5;
      v12[1] = v18;
      *v18 = v12;
      *(_QWORD *)(v17 + 8) = v12;
      v12[3] = v12 + 2;
      v12[2] = v12 + 2;
      goto LABEL_49;
    }
LABEL_47:
    __fastfail(3u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
  *((_WORD *)v12 + 26) = v8;
  if ( NatLookupOutboundPptpMapping(v12[4], v8, &a5) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_id(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids,
        v12[4],
        *((unsigned __int16 *)v12 + 26));
    }
    NatFreeBlockAndUpdateStateAllocationUsage(&PptpLookasideList, v12, 72);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225473LL;
    }
    v16 = 25;
    goto LABEL_44;
  }
  v19 = a5;
  v20 = *(_QWORD **)(a5 + 8);
  if ( *v20 != a5 )
    goto LABEL_47;
  v12[2] = a5;
  v12[3] = v20;
  *v20 = v12 + 2;
  *(_QWORD *)(v19 + 8) = v12 + 2;
  v12[1] = v12;
  *v12 = v12;
LABEL_49:
  *a7 = v12;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140014bac  push    rbx
0x140014bae  push    rbp
0x140014baf  push    rsi
0x140014bb0  push    rdi
0x140014bb1  push    r13
0x140014bb3  push    r14
0x140014bb5  push    r15
0x140014bb7  sub     rsp, 50h
0x140014bbb  mov     edi, r9d
0x140014bbe  movzx   esi, r8w
0x140014bc2  mov     ebp, edx
0x140014bc4  mov     r14d, ecx
0x140014bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140014bce  lea     r13, WPP_GLOBAL_Control
0x140014bd5  mov     r15d, [rsp+88h+arg_28]
0x140014bdd  cmp     rcx, r13
0x140014be0  jz      short loc_140014C0C
0x140014be2  mov     eax, [rcx+2Ch]
0x140014be5  test    al, 1
0x140014be7  jz      short loc_140014C0C
0x140014be9  cmp     byte ptr [rcx+29h], 6
0x140014bed  jb      short loc_140014C0C
0x140014bef  mov     rcx, [rcx+18h]
0x140014bf3  mov     r9d, r14d
0x140014bf6  mov     [rsp+88h+var_50], r15d
0x140014bfb  mov     [rsp+88h+var_58], edi
0x140014bff  mov     [rsp+88h+var_60], esi
0x140014c03  mov     [rsp+88h+var_68], ebp
0x140014c07  call    WPP_SF_DDdDL
0x140014c0c  mov     r8d, 48h ; 'H'
0x140014c12  mov     [rsp+88h+arg_20], 0
0x140014c1e  lea     rdx, [rsp+88h+Entry]
0x140014c23  mov     [rsp+88h+Entry], 0
0x140014c2c  lea     rcx, PptpLookasideList; Lookaside
0x140014c33  call    NatAllocateBlockWithLimitCheck
0x140014c38  mov     rbx, [rsp+88h+Entry]
0x140014c3d  test    rbx, rbx
0x140014c40  jnz     short loc_140014CB0
0x140014c42  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c49  mov     ebx, 0C0000017h
0x140014c4e  cmp     rcx, r13
0x140014c51  jz      short loc_140014CA9
0x140014c53  mov     eax, [rcx+2Ch]
0x140014c56  lea     rdi, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x140014c5d  test    al, 1
0x140014c5f  jz      short loc_140014C7B
0x140014c61  cmp     byte ptr [rcx+29h], 2
0x140014c65  jb      short loc_140014C7B
0x140014c67  mov     rcx, [rcx+18h]
0x140014c6b  mov     edx, 10h
0x140014c70  mov     r9d, ebx
0x140014c73  mov     r8, rdi
0x140014c76  call    WPP_SF_d
0x140014c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c82  cmp     rcx, r13
0x140014c85  jz      short loc_140014CA9
0x140014c87  mov     edx, [rcx+2Ch]
0x140014c8a  test    dl, 1
0x140014c8d  jz      short loc_140014CA9
0x140014c8f  cmp     byte ptr [rcx+29h], 6
0x140014c93  jb      short loc_140014CA9
0x140014c95  mov     rcx, [rcx+18h]
0x140014c99  mov     edx, 11h
0x140014c9e  mov     r9d, ebx
0x140014ca1  mov     r8, rdi
0x140014ca4  call    WPP_SF_d
0x140014ca9  mov     eax, ebx
0x140014cab  jmp     loc_140014F19
0x140014cb0  xor     edx, edx; Val
0x140014cb2  mov     rcx, rbx; void *
0x140014cb5  lea     r8d, [rdx+48h]; Size
0x140014cb9  call    memset
0x140014cbe  mov     dword ptr [rbx+38h], 1
0x140014cc5  mov     rax, rdi
0x140014cc8  shl     rax, 20h
0x140014ccc  or      rax, r14
0x140014ccf  mov     [rbx+28h], rax
0x140014cd3  mov     rax, rbp
0x140014cd6  shl     rax, 20h
0x140014cda  mov     ebp, 0C0000001h
0x140014cdf  or      rax, r14
0x140014ce2  mov     [rbx+20h], rax
0x140014ce6  cmp     r15d, 1
0x140014cea  jnz     loc_140014DE3
0x140014cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x140014cf7  lea     rdi, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x140014cfe  cmp     rcx, r13
0x140014d01  jz      short loc_140014D21
0x140014d03  mov     eax, [rcx+2Ch]
0x140014d06  test    r15b, al
0x140014d09  jz      short loc_140014D21
0x140014d0b  cmp     byte ptr [rcx+29h], 5
0x140014d0f  jb      short loc_140014D21
0x140014d11  mov     rcx, [rcx+18h]
0x140014d15  lea     edx, [r15+11h]
0x140014d19  mov     r8, rdi
0x140014d1c  call    WPP_SF_
0x140014d21  mov     [rbx+30h], si
0x140014d25  lea     rdx, [rbx+32h]
0x140014d29  mov     rcx, [rbx+28h]
0x140014d2d  lea     r8, [rsp+88h+arg_20]
0x140014d35  call    NatAllocatePublicPptpCallId
0x140014d3a  test    eax, eax
0x140014d3c  jns     short loc_140014DB0
0x140014d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d45  cmp     rcx, r13
0x140014d48  jz      short loc_140014D6C
0x140014d4a  mov     edx, [rcx+2Ch]
0x140014d4d  test    dl, 1
0x140014d50  jz      short loc_140014D6C
0x140014d52  cmp     byte ptr [rcx+29h], 2
0x140014d56  jb      short loc_140014D6C
0x140014d58  mov     rcx, [rcx+18h]
0x140014d5c  mov     edx, 15h
0x140014d61  mov     r9d, eax
0x140014d64  mov     r8, rdi
0x140014d67  call    WPP_SF_d
0x140014d6c  mov     r8d, 48h ; 'H'
0x140014d72  lea     rcx, PptpLookasideList; Lookaside
0x140014d79  mov     rdx, rbx; Entry
0x140014d7c  call    NatFreeBlockAndUpdateStateAllocationUsage
0x140014d81  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d88  cmp     rcx, r13
0x140014d8b  jz      loc_140014EAA
0x140014d91  mov     eax, [rcx+2Ch]
0x140014d94  test    al, 1
0x140014d96  jz      loc_140014EAA
0x140014d9c  cmp     byte ptr [rcx+29h], 6
0x140014da0  jb      loc_140014EAA
0x140014da6  mov     edx, 16h
0x140014dab  jmp     loc_140014E9B
0x140014db0  mov     rax, [rsp+88h+arg_20]
0x140014db8  mov     rcx, [rax+8]
0x140014dbc  cmp     [rcx], rax
0x140014dbf  jnz     loc_140014EBF
0x140014dc5  mov     [rbx], rax
0x140014dc8  mov     [rbx+8], rcx
0x140014dcc  mov     [rcx], rbx
0x140014dcf  mov     [rax+8], rbx
0x140014dd3  lea     rax, [rbx+10h]
0x140014dd7  mov     [rax+8], rax
0x140014ddb  mov     [rax], rax
0x140014dde  jmp     loc_140014EDF
0x140014de3  mov     rcx, cs:WPP_GLOBAL_Control
0x140014dea  lea     rdi, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x140014df1  cmp     rcx, r13
0x140014df4  jz      short loc_140014E14
0x140014df6  mov     eax, [rcx+2Ch]
0x140014df9  test    al, 1
0x140014dfb  jz      short loc_140014E14
0x140014dfd  cmp     byte ptr [rcx+29h], 5
0x140014e01  jb      short loc_140014E14
0x140014e03  mov     rcx, [rcx+18h]
0x140014e07  mov     edx, 17h
0x140014e0c  mov     r8, rdi
0x140014e0f  call    WPP_SF_
0x140014e14  mov     [rbx+34h], si
0x140014e18  lea     r8, [rsp+88h+arg_20]
0x140014e20  mov     rcx, [rbx+20h]
0x140014e24  movzx   edx, si
0x140014e27  call    NatLookupOutboundPptpMapping
0x140014e2c  test    rax, rax
0x140014e2f  jz      short loc_140014EAE
0x140014e31  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e38  cmp     rcx, r13
0x140014e3b  jz      short loc_140014E67
0x140014e3d  mov     eax, [rcx+2Ch]
0x140014e40  test    al, 1
0x140014e42  jz      short loc_140014E67
0x140014e44  cmp     byte ptr [rcx+29h], 5
0x140014e48  jb      short loc_140014E67
0x140014e4a  movzx   eax, word ptr [rbx+34h]
0x140014e4e  mov     edx, 18h
0x140014e53  mov     r9, [rbx+20h]
0x140014e57  mov     r8, rdi
0x140014e5a  mov     rcx, [rcx+18h]
0x140014e5e  mov     [rsp+88h+var_68], eax
0x140014e62  call    WPP_SF_id
0x140014e67  mov     r8d, 48h ; 'H'
0x140014e6d  lea     rcx, PptpLookasideList; Lookaside
0x140014e74  mov     rdx, rbx; Entry
0x140014e77  call    NatFreeBlockAndUpdateStateAllocationUsage
0x140014e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e83  cmp     rcx, r13
0x140014e86  jz      short loc_140014EAA
0x140014e88  mov     edx, [rcx+2Ch]
0x140014e8b  test    dl, 1
0x140014e8e  jz      short loc_140014EAA
0x140014e90  cmp     byte ptr [rcx+29h], 6
0x140014e94  jb      short loc_140014EAA
0x140014e96  mov     edx, 19h
0x140014e9b  mov     rcx, [rcx+18h]
0x140014e9f  mov     r9d, ebp
0x140014ea2  mov     r8, rdi
0x140014ea5  call    WPP_SF_d
0x140014eaa  mov     eax, ebp
0x140014eac  jmp     short loc_140014F19
0x140014eae  mov     rcx, [rsp+88h+arg_20]
0x140014eb6  mov     rdx, [rcx+8]
0x140014eba  cmp     [rdx], rcx
0x140014ebd  jz      short loc_140014EC6
0x140014ebf  mov     ecx, 3
0x140014ec4  int     29h; Win8: RtlFailFast(ecx)
0x140014ec6  lea     rax, [rbx+10h]
0x140014eca  mov     [rax], rcx
0x140014ecd  mov     [rax+8], rdx
0x140014ed1  mov     [rdx], rax
0x140014ed4  mov     [rcx+8], rax
0x140014ed8  mov     [rbx+8], rbx
0x140014edc  mov     [rbx], rbx
0x140014edf  mov     rax, [rsp+88h+arg_30]
0x140014ee7  mov     [rax], rbx
0x140014eea  mov     rcx, cs:WPP_GLOBAL_Control
0x140014ef1  cmp     rcx, r13
0x140014ef4  jz      short loc_140014F17
0x140014ef6  mov     eax, [rcx+2Ch]
0x140014ef9  test    al, 1
0x140014efb  jz      short loc_140014F17
0x140014efd  cmp     byte ptr [rcx+29h], 6
0x140014f01  jb      short loc_140014F17
0x140014f03  mov     rcx, [rcx+18h]
0x140014f07  mov     edx, 1Ah
0x140014f0c  xor     r9d, r9d
0x140014f0f  mov     r8, rdi
0x140014f12  call    WPP_SF_d
0x140014f17  xor     eax, eax
0x140014f19  add     rsp, 50h
0x140014f1d  pop     r15
0x140014f1f  pop     r14
0x140014f21  pop     r13
0x140014f23  pop     rdi
0x140014f24  pop     rsi
0x140014f25  pop     rbp
0x140014f26  pop     rbx
0x140014f27  retn
```
