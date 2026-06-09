# NatCreateIcmpMapping

- ea: `0x140008a54`
- end: `0x140009185`
- name: `NatCreateIcmpMapping`
- size: `1841`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000adb8`
- `0x14000b5a8`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x1400052a0`
- `0x140006a08`
- `0x140006e18`
- `0x140008a54`
- `0x14000927c`
- `0x140009380`
- `0x14000bb78`
- `0x140011e00`
- `0x1400138fc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008c61`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008c61`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008cc3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008d26`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008cc3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008d26`

## pseudocode

```c
__int64 __fastcall NatCreateIcmpMapping(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        __int64 a7,
        __int64 a8,
        PVOID ***a9)
{
  __int64 v9; // rbx
  __int64 v11; // r15
  __int64 v12; // r14
  PVOID **v14; // rdi
  int v15; // eax
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 v19; // rax
  unsigned __int16 v20; // cx
  PVOID *v21; // r8
  bool v22; // zf
  __int64 v23; // rbx
  PVOID *v24; // rax
  unsigned __int16 v25; // cx
  unsigned __int64 v26; // r8
  PVOID ***v27; // rax
  PVOID *v28; // rax
  PVOID *v29; // rcx
  PVOID *v30; // rcx
  PVOID Entry; // [rsp+40h] [rbp-18h] BYREF
  __int64 v32; // [rsp+48h] [rbp-10h] BYREF

  v9 = a4;
  v11 = a3;
  v12 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids, a2, a3, a4);
  }
  Entry = 0;
  v32 = 0;
  if ( !(_DWORD)v9 && !a1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids, 3221225485LL);
      }
    }
    return 3221225485LL;
  }
  NatAllocateBlockWithLimitCheck(&IcmpLookasideList, &Entry, 64);
  v14 = (PVOID **)Entry;
  if ( !Entry )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids,
              3221225495LL);
          }
        }
      }
    }
    return 3221225495LL;
  }
  *((_QWORD *)Entry + 4) = v12 | (v11 << 32);
  if ( !(_DWORD)v9 )
  {
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 24));
    v15 = NatAcquireFromAddressPool(a1, (unsigned int)v11, 0, &v32);
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids,
          (unsigned int)v15);
      }
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 24));
      NatFreeBlockAndUpdateStateAllocationUsage(&IcmpLookasideList, v14, 64);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 3221225473LL;
      }
      v17 = 18;
      goto LABEL_119;
    }
    v9 = *(unsigned int *)(v32 + 52);
    NatDereferenceAddressPoolEntry(a1, v32);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 24));
  }
  v14[5] = (PVOID *)(v12 | (v9 << 32));
  if ( a5 )
  {
    v18 = a8;
    *((_WORD *)v14 + 24) = *a5;
  }
  else
  {
    v19 = qword_14003E4B0;
    v20 = 1;
    if ( (__int64 *)qword_14003E4B0 != &qword_14003E4B0 )
    {
      v21 = v14[4];
      do
      {
        if ( (unsigned __int64)v21 <= *(_QWORD *)(v19 + 16) )
        {
          if ( (unsigned __int64)v21 < *(_QWORD *)(v19 + 16) )
            break;
          if ( v20 <= *(_WORD *)(v19 + 32) )
          {
            if ( v20 < *(_WORD *)(v19 + 32) )
              break;
            ++v20;
          }
        }
        v19 = *(_QWORD *)v19;
      }
      while ( (__int64 *)v19 != &qword_14003E4B0 );
    }
    if ( (__int64 *)v19 == &qword_14003E4B0 && !v20 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids, 3221225473LL);
      }
      NatFreeBlockAndUpdateStateAllocationUsage(&IcmpLookasideList, v14, 64);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 3221225473LL;
      }
      v17 = 20;
      goto LABEL_119;
    }
    v18 = a8;
    v22 = a8 == 0;
    *((_WORD *)v14 + 24) = v20;
    if ( v22 )
      v18 = v19;
    a8 = v18;
  }
  if ( a6 )
  {
    v23 = a7;
    *((_WORD *)v14 + 25) = *a6;
  }
  else
  {
    v24 = (PVOID *)IcmpMappingList;
    v25 = 1;
    if ( IcmpMappingList != &IcmpMappingList )
    {
      v26 = (unsigned __int64)v14[5];
      do
      {
        if ( v26 <= (unsigned __int64)v24[5] )
        {
          if ( v26 < (unsigned __int64)v24[5] )
            break;
          if ( v25 <= *((_WORD *)v24 + 25) )
          {
            if ( v25 < *((_WORD *)v24 + 25) )
              break;
            ++v25;
          }
        }
        v24 = (PVOID *)*v24;
      }
      while ( v24 != &IcmpMappingList );
      if ( v24 == &IcmpMappingList && !v25 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids,
            3221225473LL);
        }
        NatFreeBlockAndUpdateStateAllocationUsage(&IcmpLookasideList, v14, 64);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
        {
          return 3221225473LL;
        }
        v17 = 22;
        goto LABEL_119;
      }
    }
    v23 = a7;
    v22 = a7 == 0;
    *((_WORD *)v14 + 25) = v25;
    if ( v22 )
      v23 = (__int64)v24;
    a7 = v23;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_iDiD(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      (unsigned int)WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids,
      (unsigned int)v14[4],
      *((_WORD *)v14 + 24),
      (char)v14[5],
      *((_WORD *)v14 + 25));
  }
  if ( !v23 )
  {
    if ( NatLookupInboundIcmpMapping(v14[4], *((unsigned __int16 *)v14 + 24), &a7) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids, 3221225473LL);
      }
      NatFreeBlockAndUpdateStateAllocationUsage(&IcmpLookasideList, v14, 64);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 3221225473LL;
      }
      v17 = 25;
      goto LABEL_119;
    }
    v23 = a7;
  }
  v27 = *(PVOID ****)(v23 + 8);
  if ( *v27 != (PVOID **)v23 )
LABEL_128:
    __fastfail(3u);
  *v14 = (PVOID *)v23;
  v14[1] = (PVOID *)v27;
  *v27 = v14;
  *(_QWORD *)(v23 + 8) = v14;
  if ( !v18 )
  {
    if ( NatLookupOutboundIcmpMapping(v14[5], *((unsigned __int16 *)v14 + 25), &a8) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids, 3221225473LL);
      }
      v28 = *v14;
      if ( (*v14)[1] == v14 )
      {
        v29 = v14[1];
        if ( *v29 == v14 )
        {
          *v29 = v28;
          v28[1] = v29;
          NatFreeBlockAndUpdateStateAllocationUsage(&IcmpLookasideList, v14, 64);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
          {
            return 3221225473LL;
          }
          v17 = 27;
LABEL_119:
          WPP_SF_d(v16->AttachedDevice, v17, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids, 3221225473LL);
          return 3221225473LL;
        }
      }
      goto LABEL_128;
    }
    v18 = a8;
  }
  v30 = *(PVOID **)(v18 + 8);
  if ( *v30 != (PVOID)v18 )
    goto LABEL_128;
  v14[2] = (PVOID *)v18;
  v14[3] = v30;
  *v30 = v14 + 2;
  *(_QWORD *)(v18 + 8) = v14 + 2;
  *a9 = v14;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140008a54  push    rbp
0x140008a56  push    rbx
0x140008a57  push    rsi
0x140008a58  push    rdi
0x140008a59  push    r12
0x140008a5b  push    r13
0x140008a5d  push    r14
0x140008a5f  push    r15
0x140008a61  mov     rbp, rsp
0x140008a64  sub     rsp, 58h
0x140008a68  mov     ebx, r9d
0x140008a6b  mov     rsi, rcx
0x140008a6e  mov     r15d, r8d
0x140008a71  mov     r14d, edx
0x140008a74  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a7b  lea     rdi, WPP_GLOBAL_Control
0x140008a82  mov     r13d, 1
0x140008a88  cmp     rcx, rdi
0x140008a8b  jz      short loc_140008ABB
0x140008a8d  mov     eax, [rcx+2Ch]
0x140008a90  test    r13b, al
0x140008a93  jz      short loc_140008ABB
0x140008a95  cmp     byte ptr [rcx+29h], 6
0x140008a99  jb      short loc_140008ABB
0x140008a9b  mov     rcx, [rcx+18h]
0x140008a9f  lea     edx, [r13+9]
0x140008aa3  mov     dword ptr [rsp+58h+var_30], ebx
0x140008aa7  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008aae  mov     r9d, r14d
0x140008ab1  mov     [rsp+58h+var_38], r15d
0x140008ab6  call    WPP_SF_DDD
0x140008abb  xor     r12d, r12d
0x140008abe  mov     [rbp+Entry], r12
0x140008ac2  mov     [rbp+var_10], r12
0x140008ac6  test    ebx, ebx
0x140008ac8  jnz     short loc_140008B47
0x140008aca  test    rsi, rsi
0x140008acd  jnz     short loc_140008B47
0x140008acf  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ad6  mov     ebx, 0C000000Dh
0x140008adb  cmp     rcx, rdi
0x140008ade  jz      short loc_140008B33
0x140008ae0  mov     eax, [rcx+2Ch]
0x140008ae3  test    r13b, al
0x140008ae6  jz      short loc_140008B01
0x140008ae8  cmp     byte ptr [rcx+29h], 2
0x140008aec  jb      short loc_140008B01
0x140008aee  mov     rcx, [rcx+18h]
0x140008af2  lea     edx, [rsi+0Bh]
0x140008af5  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008afc  call    WPP_SF_
0x140008b01  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b08  cmp     rcx, rdi
0x140008b0b  jz      short loc_140008B33
0x140008b0d  mov     edx, [rcx+2Ch]
0x140008b10  test    r13b, dl
0x140008b13  jz      short loc_140008B33
0x140008b15  cmp     byte ptr [rcx+29h], 6
0x140008b19  jb      short loc_140008B33
0x140008b1b  mov     rcx, [rcx+18h]
0x140008b1f  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008b26  mov     edx, 0Ch
0x140008b2b  mov     r9d, ebx
0x140008b2e  call    WPP_SF_d
0x140008b33  mov     eax, ebx
0x140008b35  add     rsp, 58h
0x140008b39  pop     r15
0x140008b3b  pop     r14
0x140008b3d  pop     r13
0x140008b3f  pop     r12
0x140008b41  pop     rdi
0x140008b42  pop     rsi
0x140008b43  pop     rbx
0x140008b44  pop     rbp
0x140008b45  retn
0x140008b47  mov     r8d, 40h ; '@'
0x140008b4d  lea     rdx, [rbp+Entry]
0x140008b51  lea     rcx, IcmpLookasideList; Lookaside
0x140008b58  call    NatAllocateBlockWithLimitCheck
0x140008b5d  mov     rdi, [rbp+Entry]
0x140008b61  test    rdi, rdi
0x140008b64  jnz     loc_140008C44
0x140008b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b71  lea     rbx, WPP_GLOBAL_Control
0x140008b78  mov     edi, 0C0000017h
0x140008b7d  cmp     rcx, rbx
0x140008b80  jz      loc_140008C3D
0x140008b86  mov     eax, [rcx+2Ch]
0x140008b89  test    r13b, al
0x140008b8c  jz      short loc_140008BA9
0x140008b8e  cmp     byte ptr [rcx+29h], 2
0x140008b92  jb      short loc_140008BA9
0x140008b94  mov     rcx, [rcx+18h]
0x140008b98  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008b9f  mov     edx, 0Dh
0x140008ba4  call    WPP_SF_
0x140008ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bb0  cmp     rcx, rbx
0x140008bb3  jz      loc_140008C3D
0x140008bb9  mov     eax, [rcx+2Ch]
0x140008bbc  test    r13b, al
0x140008bbf  jz      short loc_140008BDC
0x140008bc1  cmp     byte ptr [rcx+29h], 2
0x140008bc5  jb      short loc_140008BDC
0x140008bc7  mov     rcx, [rcx+18h]
0x140008bcb  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008bd2  mov     edx, 0Eh
0x140008bd7  call    WPP_SF_
0x140008bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140008be3  cmp     rcx, rbx
0x140008be6  jz      short loc_140008C3D
0x140008be8  mov     eax, [rcx+2Ch]
0x140008beb  test    r13b, al
0x140008bee  jz      short loc_140008C0B
0x140008bf0  cmp     byte ptr [rcx+29h], 2
0x140008bf4  jb      short loc_140008C0B
0x140008bf6  mov     rcx, [rcx+18h]
0x140008bfa  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008c01  mov     edx, 0Fh
0x140008c06  call    WPP_SF_
0x140008c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c12  cmp     rcx, rbx
0x140008c15  jz      short loc_140008C3D
0x140008c17  mov     edx, [rcx+2Ch]
0x140008c1a  test    r13b, dl
0x140008c1d  jz      short loc_140008C3D
0x140008c1f  cmp     byte ptr [rcx+29h], 6
0x140008c23  jb      short loc_140008C3D
0x140008c25  mov     rcx, [rcx+18h]
0x140008c29  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008c30  mov     edx, 10h
0x140008c35  mov     r9d, edi
0x140008c38  call    WPP_SF_d
0x140008c3d  mov     eax, edi
0x140008c3f  jmp     loc_140008B35
0x140008c44  mov     rax, r15
0x140008c47  shl     rax, 20h
0x140008c4b  or      rax, r14
0x140008c4e  mov     [rdi+20h], rax
0x140008c52  test    ebx, ebx
0x140008c54  jnz     loc_140008D32
0x140008c5a  lea     r12, [rsi+18h]
0x140008c5e  mov     rcx, r12; SpinLock
0x140008c61  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140008c68  nop     dword ptr [rax+rax+00h]
0x140008c6d  lea     r9, [rbp+var_10]
0x140008c71  xor     r8d, r8d
0x140008c74  mov     edx, r15d
0x140008c77  mov     rcx, rsi
0x140008c7a  call    NatAcquireFromAddressPool
0x140008c7f  test    eax, eax
0x140008c81  jns     loc_140008D14
0x140008c87  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c8e  lea     rbx, WPP_GLOBAL_Control
0x140008c95  cmp     rcx, rbx
0x140008c98  jz      short loc_140008CC0
0x140008c9a  mov     edx, [rcx+2Ch]
0x140008c9d  test    r13b, dl
0x140008ca0  jz      short loc_140008CC0
0x140008ca2  cmp     byte ptr [rcx+29h], 2
0x140008ca6  jb      short loc_140008CC0
0x140008ca8  mov     rcx, [rcx+18h]
0x140008cac  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008cb3  mov     edx, 11h
0x140008cb8  mov     r9d, eax
0x140008cbb  call    WPP_SF_d
0x140008cc0  mov     rcx, r12; SpinLock
0x140008cc3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008cca  nop     dword ptr [rax+rax+00h]
0x140008ccf  mov     r8d, 40h ; '@'
0x140008cd5  lea     rcx, IcmpLookasideList; Lookaside
0x140008cdc  mov     rdx, rdi; Entry
0x140008cdf  call    NatFreeBlockAndUpdateStateAllocationUsage
0x140008ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ceb  cmp     rcx, rbx
0x140008cee  jz      loc_14000910F
0x140008cf4  mov     eax, [rcx+2Ch]
0x140008cf7  test    r13b, al
0x140008cfa  jz      loc_14000910F
0x140008d00  cmp     byte ptr [rcx+29h], 6
0x140008d04  jb      loc_14000910F
0x140008d0a  mov     edx, 12h
0x140008d0f  jmp     loc_1400090F9
0x140008d14  mov     rdx, [rbp+var_10]
0x140008d18  mov     rcx, rsi
0x140008d1b  mov     ebx, [rdx+34h]
0x140008d1e  call    NatDereferenceAddressPoolEntry
0x140008d23  mov     rcx, r12; SpinLock
0x140008d26  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008d2d  nop     dword ptr [rax+rax+00h]
0x140008d32  mov     rax, rbx
0x140008d35  shl     rax, 20h
0x140008d39  or      rax, r14
0x140008d3c  mov     [rdi+28h], rax
0x140008d40  mov     rax, [rbp+arg_20]
0x140008d44  test    rax, rax
0x140008d47  jz      short loc_140008D5C
0x140008d49  movzx   eax, word ptr [rax]
0x140008d4c  mov     rsi, [rbp+arg_38]
0x140008d53  mov     [rdi+30h], ax
0x140008d57  jmp     loc_140008E46
0x140008d5c  mov     rax, cs:qword_14003E4B0
0x140008d63  lea     r9, qword_14003E4B0
0x140008d6a  movzx   ecx, r13w
0x140008d6e  cmp     rax, r9
0x140008d71  jz      short loc_140008D93
0x140008d73  mov     r8, [rdi+20h]
0x140008d77  cmp     r8, [rax+10h]
0x140008d7b  ja      short loc_140008D8B
0x140008d7d  jb      short loc_140008D93
0x140008d7f  cmp     cx, [rax+20h]
0x140008d83  ja      short loc_140008D8B
0x140008d85  jb      short loc_140008D93
0x140008d87  add     cx, r13w
0x140008d8b  mov     rax, [rax]
0x140008d8e  cmp     rax, r9
0x140008d91  jnz     short loc_140008D77
0x140008d93  lea     rdx, qword_14003E4B0
0x140008d9a  cmp     rax, rdx
0x140008d9d  jnz     loc_140008E2D
0x140008da3  test    cx, cx
0x140008da6  jnz     loc_140008E2D
0x140008dac  mov     rcx, cs:WPP_GLOBAL_Control
0x140008db3  lea     rbx, WPP_GLOBAL_Control
0x140008dba  cmp     rcx, rbx
0x140008dbd  jz      short loc_140008DE8
0x140008dbf  mov     eax, [rcx+2Ch]
0x140008dc2  test    r13b, al
0x140008dc5  jz      short loc_140008DE8
0x140008dc7  cmp     byte ptr [rcx+29h], 2
0x140008dcb  jb      short loc_140008DE8
0x140008dcd  mov     rcx, [rcx+18h]
0x140008dd1  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008dd8  mov     edx, 13h
0x140008ddd  mov     r9d, 0C0000001h
0x140008de3  call    WPP_SF_d
0x140008de8  mov     r8d, 40h ; '@'
0x140008dee  lea     rcx, IcmpLookasideList; Lookaside
0x140008df5  mov     rdx, rdi; Entry
0x140008df8  call    NatFreeBlockAndUpdateStateAllocationUsage
0x140008dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e04  cmp     rcx, rbx
0x140008e07  jz      loc_14000910F
0x140008e0d  mov     eax, [rcx+2Ch]
0x140008e10  test    r13b, al
0x140008e13  jz      loc_14000910F
0x140008e19  cmp     byte ptr [rcx+29h], 6
0x140008e1d  jb      loc_14000910F
0x140008e23  mov     edx, 14h
0x140008e28  jmp     loc_1400090F9
0x140008e2d  mov     rsi, [rbp+arg_38]
0x140008e34  test    rsi, rsi
0x140008e37  mov     [rdi+30h], cx
0x140008e3b  cmovz   rsi, rax
0x140008e3f  mov     [rbp+arg_38], rsi
0x140008e46  mov     rax, [rbp+arg_28]
0x140008e4a  test    rax, rax
0x140008e4d  jz      short loc_140008E5F
0x140008e4f  movzx   eax, word ptr [rax]
0x140008e52  mov     rbx, [rbp+arg_30]
0x140008e56  mov     [rdi+32h], ax
0x140008e5a  jmp     loc_140008F40
0x140008e5f  mov     rax, cs:IcmpMappingList
0x140008e66  lea     r9, IcmpMappingList
0x140008e6d  movzx   ecx, r13w
0x140008e71  cmp     rax, r9
0x140008e74  jz      loc_140008F2D
0x140008e7a  mov     r8, [rdi+28h]
0x140008e7e  cmp     r8, [rax+28h]
0x140008e82  ja      short loc_140008E92
0x140008e84  jb      short loc_140008E9A
0x140008e86  cmp     cx, [rax+32h]
0x140008e8a  ja      short loc_140008E92
0x140008e8c  jb      short loc_140008E9A
0x140008e8e  add     cx, r13w
0x140008e92  mov     rax, [rax]
0x140008e95  cmp     rax, r9
0x140008e98  jnz     short loc_140008E7E
0x140008e9a  cmp     rax, r9
0x140008e9d  jnz     loc_140008F2D
0x140008ea3  test    cx, cx
0x140008ea6  jnz     loc_140008F2D
0x140008eac  mov     rcx, cs:WPP_GLOBAL_Control
0x140008eb3  lea     rbx, WPP_GLOBAL_Control
0x140008eba  cmp     rcx, rbx
0x140008ebd  jz      short loc_140008EE8
0x140008ebf  mov     eax, [rcx+2Ch]
0x140008ec2  test    r13b, al
0x140008ec5  jz      short loc_140008EE8
0x140008ec7  cmp     byte ptr [rcx+29h], 2
0x140008ecb  jb      short loc_140008EE8
0x140008ecd  mov     rcx, [rcx+18h]
0x140008ed1  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140008ed8  mov     edx, 15h
0x140008edd  mov     r9d, 0C0000001h
0x140008ee3  call    WPP_SF_d
0x140008ee8  mov     r8d, 40h ; '@'
0x140008eee  lea     rcx, IcmpLookasideList; Lookaside
0x140008ef5  mov     rdx, rdi; Entry
0x140008ef8  call    NatFreeBlockAndUpdateStateAllocationUsage
  ... truncated ...
```
