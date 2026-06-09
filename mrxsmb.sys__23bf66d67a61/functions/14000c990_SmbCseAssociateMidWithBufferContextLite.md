# SmbCseAssociateMidWithBufferContextLite

- ea: `0x14000c990`
- end: `0x14000cf91`
- name: `SmbCseAssociateMidWithBufferContextLite`
- size: `1537`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000b4b0`

## callees

- `0x140004760`
- `0x14000c990`
- `0x1400207f0`
- `0x140037fa4`
- `0x1400383d0`
- `0x140048a34`
- `0x140048b40`
- `0x140048c94`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000cb88`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000cb88`
- `ntoskrnl!ExAllocatePool2` at `0x14000ca24`
- `ntoskrnl!ExAllocatePool2` at `0x14000ca24`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cac0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cac0`
- `HAL!KeQueryPerformanceCounter` at `0x14000cc2c`
- `HAL!KeQueryPerformanceCounter` at `0x14000cc2c`

## pseudocode

```c
__int64 __fastcall SmbCseAssociateMidWithBufferContextLite(__int64 a1, __int64 a2)
{
  unsigned int v4; // esi
  __int64 v5; // rcx
  __int64 v6; // r15
  unsigned int v7; // r14d
  unsigned int v8; // edi
  __int64 Pool2; // r12
  unsigned int i; // r8d
  __int64 v11; // r9
  __int32 v12; // edx
  int v13; // ecx
  int v14; // r8d
  unsigned int v15; // ecx
  int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // edx
  unsigned int v19; // ecx
  unsigned int v20; // edi
  unsigned int v21; // eax
  __int64 v22; // rcx
  _WORD *v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdi
  unsigned __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned __int16 v28; // ax
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  unsigned int v32; // ecx
  __int32 v33; // edx
  __int64 v34; // rbx
  __int64 v35; // rcx
  _QWORD *v36; // rdx
  __int64 v37; // r8
  unsigned int v38; // ecx
  __int32 v39; // edx
  _QWORD *v40; // r8
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rcx
  unsigned int v45; // [rsp+B0h] [rbp+8h]

  if ( *(_DWORD *)(a1 + 12) )
  {
    return (unsigned int)-1073741300;
  }
  else
  {
    v4 = 0;
    v5 = *(_QWORD *)(a2 + 56);
    if ( (*(_DWORD *)(a2 + 4) & 0x40) != 0 )
    {
      v6 = *(_QWORD *)(v5 + 56);
      v45 = 0;
      v7 = *(_DWORD *)(v6 + 72);
    }
    else
    {
      v6 = 0;
      v7 = *(_DWORD *)(a2 + 80);
      v45 = *(_DWORD *)(v5 + 64);
    }
    v8 = *(_DWORD *)(a1 + 96);
    if ( v7 + *(_DWORD *)(a1 + 80) + 8 >= v8 )
    {
      Pool2 = ExAllocatePool2(64, 16LL * v8, 1834182999);
      if ( Pool2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_292ccbb15a33399a00ff0fb71a7a37d6_Traceguids,
            a1,
            v8,
            2 * v8);
        }
        for ( i = 0; i < v8; ++i )
        {
          v11 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * i);
          if ( v11 )
            *(_QWORD *)(Pool2 + 8 * (*(_QWORD *)(v11 + 40) % (unsigned __int64)(2 * v8))) = v11;
        }
        ExFreePoolWithTag(*(PVOID *)(a1 + 104), 0x6D536957u);
        *(_DWORD *)(a1 + 96) = 2 * v8;
        *(_QWORD *)(a1 + 104) = Pool2;
      }
    }
    v12 = _InterlockedExchange((volatile __int32 *)(a1 + 88), 0);
    if ( v12 )
    {
      v13 = *(_DWORD *)(a1 + 84);
      v14 = *(_DWORD *)(a1 + 80);
      if ( v13 + v12 >= v14 )
      {
        v16 = v13 + v12;
        v15 = 0;
        *(_DWORD *)(a1 + 84) = v16;
      }
      else
      {
        *(_DWORD *)(a1 + 84) = v14;
        v15 = v12 + v13 - v14;
      }
      v17 = *(_DWORD *)(a1 + 96);
      v18 = *(_DWORD *)(a1 + 84);
      if ( v18 > v17 )
      {
        *(_DWORD *)(a1 + 84) = v17;
        v15 = v18 - v17;
      }
      _InterlockedAdd((volatile signed __int32 *)(a1 + 88), v15);
    }
    v19 = *(_DWORD *)(a1 + 84);
    if ( v45 && v19 >= *(_DWORD *)(a1 + 144) )
      v19 = *(_DWORD *)(a1 + 144);
    v20 = *(_DWORD *)(a1 + 80);
    if ( v19 >= v20 )
      v20 = v19;
    if ( v20 >= v7 )
    {
      v22 = *(_QWORD *)(a2 + 96);
      if ( (*(_BYTE *)(v22 + 10) & 5) != 0 )
        v23 = *(_WORD **)(v22 + 24);
      else
        v23 = MmMapLockedPagesSpecifyCache((PMDL)v22, 0, MmCached, 0, 0, 0x40000010u);
      if ( v23 )
      {
        if ( (v23[6] == 8 || v23[6] == 9) && (byte_14007D0C0 & 1) != 0 )
        {
          v24 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 56) + 88LL) + 424LL);
          _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                          * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                         % *(_DWORD *)(v24 + 1488))
                                                          + *(_QWORD *)(v24 + 1480)
                                                          + 88));
          *(_BYTE *)(a2 + 856) = 1;
          *(LARGE_INTEGER *)(a2 + 848) = KeQueryPerformanceCounter(0);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_292ccbb15a33399a00ff0fb71a7a37d6_Traceguids, a2);
      }
      if ( v20 - *(_DWORD *)(a1 + 80) < v7 )
      {
        v35 = a1 + 16 * (v45 + 2LL);
        v36 = *(_QWORD **)(v35 + 8);
        if ( *v36 != v35 )
          __fastfail(3u);
        *(_QWORD *)(a2 + 24) = v35;
        *(_QWORD *)(a2 + 32) = v36;
        *v36 = a2 + 24;
        *(_QWORD *)(v35 + 8) = a2 + 24;
        v37 = *(_QWORD *)(*(_QWORD *)(a2 + 56) + 88LL);
        if ( v37 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                          * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                         % *(_DWORD *)(*(_QWORD *)(v37 + 424) + 1488LL))
                                                          + *(_QWORD *)(*(_QWORD *)(v37 + 424) + 1480LL)
                                                          + 92));
          v38 = *(_DWORD *)(a1 + 80);
          v39 = *(_DWORD *)(a1 + 84) - v38;
          if ( *(_DWORD *)(a1 + 84) < v38 )
            v39 = 0;
          v35 = *(_QWORD *)(*(_QWORD *)(a2 + 56) + 88LL);
          _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(v35 + 424) + 1492LL), v39);
        }
        if ( byte_14007D25F && (Microsoft_Windows_SMBClientEnableBits & 8) != 0 )
          McTemplateK0ppqpqqq_EtwWriteTransfer(
            v35,
            (unsigned int)SmbSuspendBufferCtxt,
            a2 + 880,
            a2,
            *(_QWORD *)(a2 + 56),
            v7,
            a1,
            *(_DWORD *)(a1 + 84),
            *(_DWORD *)(a1 + 144),
            *(_DWORD *)(a1 + 80));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v40 = *(_QWORD **)(a2 + 56);
          WPP_SF_Dqqqqqqqqq(
            WPP_GLOBAL_Control->AttachedDevice,
            v40[12],
            v40,
            v7,
            v40,
            a2,
            v6,
            v40[6],
            *(_QWORD *)(v40[12] + 392LL),
            v40[12],
            v40[10],
            v40[11],
            v40[9]);
        }
        if ( v6 )
        {
          v41 = *(_QWORD *)(v6 + 48);
          if ( v41 != v6 + 48 )
          {
            v42 = v41 - 64;
            while ( v42 )
            {
              v43 = *(_QWORD *)(v42 + 64);
              *(_BYTE *)(v42 + 84) = 1;
              v42 = 0;
              if ( v43 != v6 + 48 )
                v42 = v43 - 64;
            }
          }
        }
        else
        {
          *(_BYTE *)(a2 + 84) = 1;
        }
        return 259;
      }
      else
      {
        v25 = a2;
        *(_QWORD *)(a1 + 128) = MEMORY[0xFFFFF78000000008];
        do
        {
          v26 = *(unsigned int *)(a1 + 96);
          *(_DWORD *)(a1 + 80) += *(_DWORD *)(v25 + 80);
          *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * (*(_QWORD *)(a1 + 72) % v26)) = v25;
          v27 = *(unsigned int *)(v25 + 80);
          *(_QWORD *)(v25 + 40) = *(_QWORD *)(a1 + 72);
          v28 = SmbCseEstimateRequiredCreditsLite(a1, v27);
          *(_DWORD *)(v25 + 4) |= 1u;
          *(_DWORD *)(v25 + 732) = v28;
          *(_DWORD *)(a1 + 92) += v28;
          *(_QWORD *)(a1 + 72) += *(unsigned int *)(v25 + 80);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qid(WPP_GLOBAL_Control->AttachedDevice, 14, v29, v25, *(_QWORD *)(v25 + 40), *(_DWORD *)(v25 + 80));
          }
          if ( v6 )
          {
            v30 = *(_QWORD *)(v25 + 64);
            v25 = 0;
            if ( v30 != v6 + 48 )
              v25 = v30 - 64;
          }
          else
          {
            v25 = 0;
          }
          if ( byte_14007D25F && (Microsoft_Windows_SMBClientEnableBits & 8) != 0 )
            McTemplateK0pqqqxxd_EtwWriteTransfer(
              *(_DWORD *)(a1 + 72),
              *(_DWORD *)(a1 + 64),
              a2 + 880,
              a1,
              *(_DWORD *)(a1 + 80),
              *(_DWORD *)(a1 + 84),
              *(_DWORD *)(a1 + 144),
              *(_DWORD *)(a1 + 64),
              *(_DWORD *)(a1 + 72),
              *(_DWORD *)(a1 + 88));
        }
        while ( v25 );
        v31 = *(_QWORD *)(*(_QWORD *)(a2 + 56) + 88LL);
        if ( v31 )
        {
          v32 = *(_DWORD *)(a1 + 80);
          v33 = *(_DWORD *)(a1 + 84) - v32;
          if ( *(_DWORD *)(a1 + 84) < v32 )
            v33 = 0;
          _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(v31 + 424) + 1492LL), v33);
        }
        if ( *(_DWORD *)(a1 + 80) >= (unsigned int)dword_14007D098 )
        {
          v34 = *(_QWORD *)(*(_QWORD *)(a2 + 56) + 72LL);
          if ( *(_QWORD *)(v34 + 576) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_292ccbb15a33399a00ff0fb71a7a37d6_Traceguids, v34);
            }
            *(_DWORD *)(v34 + 4) |= 1u;
          }
        }
      }
    }
    else
    {
      v21 = -1073741507;
      if ( v7 <= 1 )
        return (unsigned int)-1073741300;
      return v21;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14000c990  mov     [rsp+arg_10], rbx
0x14000c995  push    rbp
0x14000c996  push    rsi
0x14000c997  push    rdi
0x14000c998  push    r12
0x14000c99a  push    r13
0x14000c99c  push    r14
0x14000c99e  push    r15
0x14000c9a0  sub     rsp, 70h
0x14000c9a4  cmp     dword ptr [rcx+0Ch], 0
0x14000c9a8  mov     rbp, rdx
0x14000c9ab  mov     rbx, rcx
0x14000c9ae  jz      short loc_14000C9BA
0x14000c9b0  mov     esi, 0C000020Ch
0x14000c9b5  jmp     loc_14000CF76
0x14000c9ba  mov     eax, [rdx+4]
0x14000c9bd  xor     esi, esi
0x14000c9bf  mov     rcx, [rdx+38h]
0x14000c9c3  test    al, 40h
0x14000c9c5  jz      short loc_14000C9D8
0x14000c9c7  mov     r15, [rcx+38h]
0x14000c9cb  mov     [rsp+0A8h+arg_0], esi
0x14000c9d2  mov     r14d, [r15+48h]
0x14000c9d6  jmp     short loc_14000C9E9
0x14000c9d8  mov     eax, [rcx+40h]
0x14000c9db  mov     r15, rsi
0x14000c9de  mov     r14d, [rdx+50h]
0x14000c9e2  mov     [rsp+0A8h+arg_0], eax
0x14000c9e9  mov     ecx, [rbx+50h]
0x14000c9ec  lea     r13, WPP_GLOBAL_Control
0x14000c9f3  mov     edi, [rbx+60h]
0x14000c9f6  add     ecx, 8
0x14000c9f9  add     ecx, r14d
0x14000c9fc  cmp     ecx, edi
0x14000c9fe  jb      loc_14000CAE1
0x14000ca04  lea     eax, [rdi+rdi]
0x14000ca07  mov     ecx, 40h ; '@'
0x14000ca0c  lea     rdx, ds:0[rax*8]
0x14000ca14  mov     [rsp+0A8h+arg_8], eax
0x14000ca1b  mov     r8d, 6D536957h
0x14000ca21  mov     r13d, eax
0x14000ca24  call    cs:__imp_ExAllocatePool2
0x14000ca2b  nop     dword ptr [rax+rax+00h]
0x14000ca30  mov     r12, rax
0x14000ca33  test    rax, rax
0x14000ca36  jz      loc_14000CADA
0x14000ca3c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ca43  lea     rax, WPP_GLOBAL_Control
0x14000ca4a  cmp     rcx, rax
0x14000ca4d  jz      short loc_14000CA7F
0x14000ca4f  mov     eax, [rcx+2Ch]
0x14000ca52  test    al, al
0x14000ca54  jns     short loc_14000CA7F
0x14000ca56  cmp     byte ptr [rcx+29h], 2
0x14000ca5a  jb      short loc_14000CA7F
0x14000ca5c  mov     rcx, [rcx+18h]
0x14000ca60  lea     eax, [rdi+rdi]
0x14000ca63  mov     [rsp+0A8h+Priority], eax
0x14000ca67  lea     r8, WPP_292ccbb15a33399a00ff0fb71a7a37d6_Traceguids
0x14000ca6e  mov     edx, 17h
0x14000ca73  mov     [rsp+0A8h+BugCheckOnFailure], edi
0x14000ca77  mov     r9, rbx
0x14000ca7a  call    WPP_SF_qDD
0x14000ca7f  mov     r8d, esi
0x14000ca82  test    edi, edi
0x14000ca84  jz      short loc_14000CAB7
0x14000ca86  nop     word ptr [rax+rax+00000000h]
0x14000ca90  mov     rax, [rbx+68h]
0x14000ca94  mov     ecx, r8d
0x14000ca97  mov     r9, [rax+rcx*8]
0x14000ca9b  test    r9, r9
0x14000ca9e  jz      short loc_14000CAAF
0x14000caa0  mov     rax, [r9+28h]
0x14000caa4  xor     edx, edx
0x14000caa6  div     r13
0x14000caa9  mov     eax, edx
0x14000caab  mov     [r12+rax*8], r9
0x14000caaf  inc     r8d
0x14000cab2  cmp     r8d, edi
0x14000cab5  jb      short loc_14000CA90
0x14000cab7  mov     rcx, [rbx+68h]; P
0x14000cabb  mov     edx, 6D536957h; Tag
0x14000cac0  call    cs:__imp_ExFreePoolWithTag
0x14000cac7  nop     dword ptr [rax+rax+00h]
0x14000cacc  mov     eax, [rsp+0A8h+arg_8]
0x14000cad3  mov     [rbx+60h], eax
0x14000cad6  mov     [rbx+68h], r12
0x14000cada  lea     r13, WPP_GLOBAL_Control
0x14000cae1  mov     edx, esi
0x14000cae3  xchg    edx, [rbx+58h]
0x14000cae6  test    edx, edx
0x14000cae8  jz      short loc_14000CB21
0x14000caea  mov     ecx, [rbx+54h]
0x14000caed  mov     r8d, [rbx+50h]
0x14000caf1  lea     eax, [rcx+rdx]
0x14000caf4  cmp     eax, r8d
0x14000caf7  jge     short loc_14000CB04
0x14000caf9  sub     ecx, r8d
0x14000cafc  mov     [rbx+54h], r8d
0x14000cb00  add     ecx, edx
0x14000cb02  jmp     short loc_14000CB0C
0x14000cb04  lea     eax, [rcx+rdx]
0x14000cb07  mov     ecx, esi
0x14000cb09  mov     [rbx+54h], eax
0x14000cb0c  mov     eax, [rbx+60h]
0x14000cb0f  mov     edx, [rbx+54h]
0x14000cb12  cmp     edx, eax
0x14000cb14  jbe     short loc_14000CB1D
0x14000cb16  mov     ecx, edx
0x14000cb18  mov     [rbx+54h], eax
0x14000cb1b  sub     ecx, eax
0x14000cb1d  lock add [rbx+58h], ecx
0x14000cb21  mov     r12d, [rsp+0A8h+arg_0]
0x14000cb29  mov     ecx, [rbx+54h]
0x14000cb2c  test    r12d, r12d
0x14000cb2f  jz      short loc_14000CB3C
0x14000cb31  mov     eax, [rbx+90h]
0x14000cb37  cmp     ecx, eax
0x14000cb39  cmovnb  ecx, eax
0x14000cb3c  mov     edi, [rbx+50h]
0x14000cb3f  cmp     ecx, edi
0x14000cb41  cmovnb  edi, ecx
0x14000cb44  cmp     edi, r14d
0x14000cb47  jnb     short loc_14000CB61
0x14000cb49  mov     esi, 0C000020Ch
0x14000cb4e  cmp     r14d, 1
0x14000cb52  mov     eax, 0C000013Dh
0x14000cb57  cmovbe  eax, esi
0x14000cb5a  mov     esi, eax
0x14000cb5c  jmp     loc_14000CF76
0x14000cb61  mov     rcx, [rbp+60h]; MemoryDescriptorList
0x14000cb65  test    byte ptr [rcx+0Ah], 5
0x14000cb69  jz      short loc_14000CB71
0x14000cb6b  mov     rax, [rcx+18h]
0x14000cb6f  jmp     short loc_14000CB94
0x14000cb71  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x14000cb79  xor     r9d, r9d; RequestedAddress
0x14000cb7c  xor     edx, edx; AccessMode
0x14000cb7e  mov     [rsp+0A8h+BugCheckOnFailure], esi; BugCheckOnFailure
0x14000cb82  mov     r8d, 1; CacheType
0x14000cb88  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000cb8f  nop     dword ptr [rax+rax+00h]
0x14000cb94  test    rax, rax
0x14000cb97  jnz     short loc_14000CBD8
0x14000cb99  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000cba0  cmp     rcx, r13
0x14000cba3  jz      loc_14000CC3F
0x14000cba9  mov     eax, [rcx+2Ch]
0x14000cbac  test    al, 1
0x14000cbae  jz      loc_14000CC3F
0x14000cbb4  cmp     byte ptr [rcx+29h], 1
0x14000cbb8  jb      loc_14000CC3F
0x14000cbbe  mov     rcx, [rcx+18h]
0x14000cbc2  lea     r8, WPP_292ccbb15a33399a00ff0fb71a7a37d6_Traceguids
0x14000cbc9  mov     edx, 0Dh
0x14000cbce  mov     r9, rbp
0x14000cbd1  call    WPP_SF_q
0x14000cbd6  jmp     short loc_14000CC3F
0x14000cbd8  movzx   ecx, word ptr [rax+0Ch]
0x14000cbdc  sub     ecx, 8
0x14000cbdf  jz      short loc_14000CBE6
0x14000cbe1  cmp     ecx, 1
0x14000cbe4  jnz     short loc_14000CC3F
0x14000cbe6  test    cs:byte_14007D0C0, 1
0x14000cbed  jz      short loc_14000CC3F
0x14000cbef  mov     rax, [rbp+38h]
0x14000cbf3  xor     edx, edx
0x14000cbf5  mov     rcx, [rax+58h]
0x14000cbf9  mov     eax, gs:1A4h
0x14000cc01  mov     r8, [rcx+1A8h]
0x14000cc08  div     dword ptr [r8+5D0h]
0x14000cc0f  mov     rax, [r8+5C8h]
0x14000cc16  lea     rdx, [rdx+rdx*2]
0x14000cc1a  shl     rdx, 6
0x14000cc1e  lock inc dword ptr [rdx+rax+58h]
0x14000cc23  xor     ecx, ecx; PerformanceFrequency
0x14000cc25  mov     byte ptr [rbp+358h], 1
0x14000cc2c  call    cs:__imp_KeQueryPerformanceCounter
0x14000cc33  nop     dword ptr [rax+rax+00h]
0x14000cc38  mov     [rbp+350h], rax
0x14000cc3f  sub     edi, [rbx+50h]
0x14000cc42  cmp     edi, r14d
0x14000cc45  jb      loc_14000CDE2
0x14000cc4b  mov     rax, ds:0FFFFF78000000008h
0x14000cc55  mov     rdi, rbp
0x14000cc58  mov     [rbx+80h], rax
0x14000cc5f  nop
0x14000cc60  mov     eax, [rdi+50h]
0x14000cc63  xor     edx, edx
0x14000cc65  add     eax, [rbx+50h]
0x14000cc68  mov     ecx, [rbx+60h]
0x14000cc6b  mov     [rbx+50h], eax
0x14000cc6e  mov     rax, [rbx+48h]
0x14000cc72  div     rcx
0x14000cc75  mov     rax, [rbx+68h]
0x14000cc79  mov     rcx, rbx
0x14000cc7c  mov     [rax+rdx*8], rdi
0x14000cc80  mov     rax, [rbx+48h]
0x14000cc84  mov     edx, [rdi+50h]
0x14000cc87  mov     [rdi+28h], rax
0x14000cc8b  call    SmbCseEstimateRequiredCreditsLite
0x14000cc90  or      dword ptr [rdi+4], 1
0x14000cc94  movzx   ecx, ax
0x14000cc97  mov     [rdi+2DCh], ecx
0x14000cc9d  add     [rbx+5Ch], ecx
0x14000cca0  mov     eax, [rdi+50h]
0x14000cca3  add     [rbx+48h], rax
0x14000cca7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ccae  cmp     rcx, r13
0x14000ccb1  jz      short loc_14000CCE1
0x14000ccb3  mov     eax, [rcx+2Ch]
0x14000ccb6  test    al, al
0x14000ccb8  jns     short loc_14000CCE1
0x14000ccba  cmp     byte ptr [rcx+29h], 4
0x14000ccbe  jb      short loc_14000CCE1
0x14000ccc0  mov     eax, [rdi+50h]
0x14000ccc3  mov     edx, 0Eh
0x14000ccc8  mov     rcx, [rcx+18h]
0x14000cccc  mov     r9, rdi
0x14000cccf  mov     [rsp+0A8h+Priority], eax
0x14000ccd3  mov     rax, [rdi+28h]
0x14000ccd7  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax
0x14000ccdc  call    WPP_SF_qid
0x14000cce1  test    r15, r15
0x14000cce4  jz      short loc_14000CCFE
0x14000cce6  mov     rdx, [rdi+40h]
0x14000ccea  lea     rcx, [r15+30h]
0x14000ccee  cmp     rdx, rcx
0x14000ccf1  mov     rdi, rsi
0x14000ccf4  lea     rax, [rdx-40h]
0x14000ccf8  cmovnz  rdi, rax
0x14000ccfc  jmp     short loc_14000CD01
0x14000ccfe  mov     rdi, rsi
0x14000cd01  cmp     cs:byte_14007D25F, 0
0x14000cd08  jz      short loc_14000CD51
0x14000cd0a  test    cs:Microsoft_Windows_SMBClientEnableBits, 8
0x14000cd11  jz      short loc_14000CD51
0x14000cd13  mov     eax, [rbx+58h]
0x14000cd16  lea     r8, [rbp+370h]
0x14000cd1d  mov     ecx, [rbx+48h]
0x14000cd20  mov     r9, rbx
0x14000cd23  mov     edx, [rbx+40h]
0x14000cd26  mov     dword ptr [rsp+0A8h+var_60], eax
0x14000cd2a  mov     eax, [rbx+90h]
0x14000cd30  mov     [rsp+0A8h+var_68], rcx
0x14000cd35  mov     [rsp+0A8h+var_70], rdx
0x14000cd3a  mov     dword ptr [rsp+0A8h+var_78], eax
0x14000cd3e  mov     eax, [rbx+54h]
0x14000cd41  mov     [rsp+0A8h+Priority], eax
0x14000cd45  mov     eax, [rbx+50h]
0x14000cd48  mov     [rsp+0A8h+BugCheckOnFailure], eax
0x14000cd4c  call    McTemplateK0pqqqxxd_EtwWriteTransfer
0x14000cd51  test    rdi, rdi
0x14000cd54  jnz     loc_14000CC60
0x14000cd5a  mov     rax, [rbp+38h]
0x14000cd5e  mov     r8, [rax+58h]
0x14000cd62  test    r8, r8
0x14000cd65  jz      short loc_14000CD83
0x14000cd67  mov     eax, [rbx+54h]
0x14000cd6a  mov     edx, eax
0x14000cd6c  mov     ecx, [rbx+50h]
0x14000cd6f  sub     edx, ecx
0x14000cd71  cmp     eax, ecx
0x14000cd73  mov     rax, [r8+1A8h]
0x14000cd7a  cmovb   edx, esi
0x14000cd7d  xchg    edx, [rax+5D4h]
0x14000cd83  mov     eax, cs:dword_14007D098
0x14000cd89  cmp     [rbx+50h], eax
0x14000cd8c  jb      loc_14000CF76
0x14000cd92  mov     rax, [rbp+38h]
0x14000cd96  mov     rbx, [rax+48h]
0x14000cd9a  cmp     qword ptr [rbx+240h], 0
0x14000cda2  jz      loc_14000CF76
0x14000cda8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000cdaf  cmp     rcx, r13
0x14000cdb2  jz      short loc_14000CDD9
0x14000cdb4  mov     eax, [rcx+2Ch]
0x14000cdb7  test    al, al
0x14000cdb9  jns     short loc_14000CDD9
0x14000cdbb  cmp     byte ptr [rcx+29h], 4
0x14000cdbf  jb      short loc_14000CDD9
0x14000cdc1  mov     rcx, [rcx+18h]
0x14000cdc5  lea     r8, WPP_292ccbb15a33399a00ff0fb71a7a37d6_Traceguids
0x14000cdcc  mov     edx, 0Fh
0x14000cdd1  mov     r9, rbx
0x14000cdd4  call    WPP_SF_q
0x14000cdd9  or      dword ptr [rbx+4], 1
0x14000cddd  jmp     loc_14000CF76
0x14000cde2  lea     rcx, [r12+2]
0x14000cde7  shl     rcx, 4
0x14000cdeb  add     rcx, rbx
0x14000cdee  mov     rdx, [rcx+8]
0x14000cdf2  cmp     [rdx], rcx
0x14000cdf5  jz      short loc_14000CDFE
0x14000cdf7  mov     ecx, 3
0x14000cdfc  int     29h; Win8: RtlFailFast(ecx)
0x14000cdfe  lea     rax, [rbp+18h]
0x14000ce02  mov     [rax], rcx
0x14000ce05  mov     [rax+8], rdx
0x14000ce09  mov     [rdx], rax
  ... truncated ...
```
