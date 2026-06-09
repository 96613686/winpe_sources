# NatTimerRoutine

- ea: `0x14001f110`
- end: `0x14001f78c`
- name: `NatTimerRoutine`
- size: `1660`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callees

- `0x14000218c`
- `0x140006e18`
- `0x14000bb78`
- `0x14000e378`
- `0x14000fbb0`
- `0x14000fe48`
- `0x14001526c`
- `0x140017100`
- `0x14001d7ac`
- `0x14001f074`
- `0x14001f110`
- `0x14001f868`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14001f19e`
- `ntoskrnl!KfRaiseIrql` at `0x14001f19e`
- `ntoskrnl!KeLowerIrql` at `0x14001f739`
- `ntoskrnl!KeLowerIrql` at `0x14001f739`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f1b4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f217`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f335`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f413`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f53c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f64b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f671`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f1b4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f217`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f335`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f413`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f53c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f64b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f671`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f61d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f61d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f24d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f270`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f31f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f3fd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f526`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f638`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f6f3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f717`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f72a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f24d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f270`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f31f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f3fd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f526`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f638`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f6f3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f717`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f72a`

## pseudocode

```c
void __fastcall NatTimerRoutine(struct _KDPC *Dpc, PVOID DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)
{
  unsigned int v4; // edi
  __int64 v5; // r12
  signed __int64 v6; // r14
  signed __int64 v7; // r15
  KIRQL v8; // r13
  KSPIN_LOCK *i; // rbx
  int v10; // eax
  signed __int64 v11; // rcx
  bool v12; // zf
  bool v13; // cc
  char *v14; // rbp
  KSPIN_LOCK *v15; // rbp
  PVOID *j; // rbx
  KSPIN_LOCK *v17; // rcx
  PVOID *v18; // rsi
  PVOID *k; // rbx
  PVOID v20; // rcx
  PVOID *v21; // rax
  PVOID **v22; // r8
  PVOID **v23; // rdx
  PVOID *v24; // rsi
  PVOID *m; // rbx
  PVOID v26; // rcx
  PVOID *v27; // rax
  PVOID **v28; // r8
  PVOID **v29; // rdx
  PVOID *v30; // rsi
  KSPIN_LOCK *v31; // rsi
  KSPIN_LOCK *n; // rbx
  int v33; // eax
  bool v34; // cc
  KSPIN_LOCK *v35; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
  }
  v4 = 0;
  v5 = MEMORY[0xFFFFF78000000320];
  v6 = MEMORY[0xFFFFF78000000320]
     - 10000000 * (unsigned __int64)(unsigned int)TcpTimeoutSeconds / (unsigned int)TimeIncrement;
  v7 = MEMORY[0xFFFFF78000000320]
     - 10000000 * (unsigned __int64)(unsigned int)UdpTimeoutSeconds / (unsigned int)TimeIncrement;
  v8 = KfRaiseIrql(2u);
  KeAcquireSpinLockAtDpcLevel(&MappingLock);
  for ( i = (KSPIN_LOCK *)MappingList; ; i = (KSPIN_LOCK *)*i )
  {
    if ( i == (KSPIN_LOCK *)&MappingList )
    {
      KeReleaseSpinLockFromDpcLevel(&MappingLock);
      v15 = &PptpMappingLock;
      KeAcquireSpinLockAtDpcLevel(&PptpMappingLock);
      for ( j = (PVOID *)PptpMappingList; j != &PptpMappingList; j = (PVOID *)*j )
      {
        ++v4;
        if ( v4 == 10 * (v4 / 0xA) && (unsigned __int8)NatShouldYieldProcessor() )
        {
LABEL_44:
          v17 = v15;
          goto LABEL_92;
        }
        if ( ((_DWORD)j[7] & 2) != 0 && (__int64)j[8] < v7 )
        {
          v18 = j;
          j = (PVOID *)j[1];
          NatDeletePptpMapping(v18);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_iiddd(
              WPP_GLOBAL_Control->AttachedDevice,
              *((unsigned __int16 *)v18 + 25),
              *((unsigned __int16 *)v18 + 24),
              v18[4],
              v18[5],
              *((unsigned __int16 *)v18 + 24),
              *((unsigned __int16 *)v18 + 25),
              *((unsigned __int16 *)v18 + 26));
          }
        }
      }
      KeReleaseSpinLockFromDpcLevel(&PptpMappingLock);
      v15 = &IcmpMappingLock;
      KeAcquireSpinLockAtDpcLevel(&IcmpMappingLock);
      for ( k = (PVOID *)IcmpMappingList; k != &IcmpMappingList; k = (PVOID *)*k )
      {
        ++v4;
        if ( v4 == 10 * (v4 / 0xA) && (unsigned __int8)NatShouldYieldProcessor() )
          goto LABEL_44;
        if ( (__int64)k[7] < v7 )
        {
          v20 = *k;
          if ( *((PVOID **)*k + 1) != k
            || (v21 = (PVOID *)k[1], *v21 != k)
            || (*v21 = v20, *((_QWORD *)v20 + 1) = v21, v22 = (PVOID **)k[2], v22[1] != k + 2)
            || (v23 = (PVOID **)k[3], *v23 != k + 2) )
          {
LABEL_75:
            __fastfail(3u);
          }
          v24 = k;
          *v23 = (PVOID *)v22;
          k = v21;
          v22[1] = (PVOID *)v23;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_iDiD(
              WPP_GLOBAL_Control->AttachedDevice,
              24,
              (unsigned int)WPP_f31671e38d5b33600ddc283ab761c181_Traceguids,
              (unsigned int)v24[4],
              *((_WORD *)v24 + 24),
              (char)v24[5],
              *((_WORD *)v24 + 25));
          }
          NatFreeBlockAndUpdateStateAllocationUsage(&IcmpLookasideList, v24, 64);
        }
      }
      KeReleaseSpinLockFromDpcLevel(&IcmpMappingLock);
      v15 = &IpMappingLock;
      KeAcquireSpinLockAtDpcLevel(&IpMappingLock);
      for ( m = (PVOID *)IpMappingList; m != &IpMappingList; m = (PVOID *)*m )
      {
        ++v4;
        if ( v4 == 10 * (v4 / 0xA) && (unsigned __int8)NatShouldYieldProcessor() )
          goto LABEL_44;
        if ( (__int64)m[7] < v7 )
        {
          v26 = *m;
          if ( *((PVOID **)*m + 1) != m )
            goto LABEL_75;
          v27 = (PVOID *)m[1];
          if ( *v27 != m )
            goto LABEL_75;
          *v27 = v26;
          *((_QWORD *)v26 + 1) = v27;
          v28 = (PVOID **)m[2];
          if ( v28[1] != m + 2 )
            goto LABEL_75;
          v29 = (PVOID **)m[3];
          if ( *v29 != m + 2 )
            goto LABEL_75;
          v30 = m;
          *v29 = (PVOID *)v28;
          m = v27;
          v28[1] = (PVOID *)v29;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_dii(WPP_GLOBAL_Control->AttachedDevice, v29, v28, *((unsigned __int8 *)v30 + 48), v30[5], v30[4]);
          }
          ExFreeToNPagedLookasideList(&IpLookasideList, v30);
        }
      }
      KeReleaseSpinLockFromDpcLevel(&IpMappingLock);
      KeAcquireSpinLockAtDpcLevel(&InterfaceLock);
      v31 = (KSPIN_LOCK *)InterfaceList;
LABEL_88:
      if ( v31 == (KSPIN_LOCK *)&InterfaceList )
      {
LABEL_91:
        v17 = &InterfaceLock;
        goto LABEL_92;
      }
      KeAcquireSpinLockAtDpcLevel(v31 + 3);
      for ( n = (KSPIN_LOCK *)v31[21]; ; n = (KSPIN_LOCK *)*n )
      {
        if ( n == v31 + 21 )
        {
          KeReleaseSpinLockFromDpcLevel(v31 + 3);
          v31 = (KSPIN_LOCK *)*v31;
          goto LABEL_88;
        }
        ++v4;
        if ( v4 == 10 * (v4 / 0xA) && (unsigned __int8)NatShouldYieldProcessor() )
        {
          KeReleaseSpinLockFromDpcLevel(v31 + 3);
          goto LABEL_91;
        }
        v33 = *((_DWORD *)n + 12);
        if ( (v33 & 1) != 0 )
        {
          if ( (v33 & 8) == 0 )
            continue;
          v34 = (__int64)n[7] < (__int64)(v5
                                        - 10000
                                        * (unsigned __int64)*((unsigned int *)n + 13)
                                        / (unsigned int)TimeIncrement);
        }
        else
        {
          v34 = (__int64)n[7] < v7;
        }
        if ( v34 )
        {
          v35 = n;
          n = (KSPIN_LOCK *)n[1];
          NatDeleteTicket(v31, v35);
        }
      }
    }
    ++v4;
    if ( v4 == 10 * (v4 / 0xA) )
    {
      if ( (unsigned __int8)NatShouldYieldProcessor() )
        break;
    }
    NatUpdateStatisticsMapping(i);
    if ( (i[30] & 0x41) != 0x40 || !i[26] )
    {
      KeAcquireSpinLockAtDpcLevel(i + 13);
      v10 = *((_DWORD *)i + 60);
      if ( (v10 & 1) != 0
        || ((v11 = i[12], *((_BYTE *)i + 86) == 6)
         && ((v10 & 0x20) != 0 ? (v12 = (v10 & 0x48200) == 0) : (v12 = (i[30] & 0x8006) == 2), !v12)
          ? (v13 = v11 < v6)
          : (v13 = v11 < v7),
            v13) )
      {
        v14 = (char *)i;
        KeReleaseSpinLockFromDpcLevel(i + 13);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_ii(
              WPP_GLOBAL_Control->AttachedDevice,
              21,
              WPP_f31671e38d5b33600ddc283ab761c181_Traceguids,
              i[10],
              i[8]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_ii(
              WPP_GLOBAL_Control->AttachedDevice,
              22,
              WPP_f31671e38d5b33600ddc283ab761c181_Traceguids,
              i[11],
              i[9]);
          }
        }
        i = (KSPIN_LOCK *)i[1];
        NatDeleteMapping(v14);
      }
      else
      {
        KeReleaseSpinLockFromDpcLevel(i + 13);
      }
    }
  }
  v17 = &MappingLock;
LABEL_92:
  KeReleaseSpinLockFromDpcLevel(v17);
  KeLowerIrql(v8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
  }
}

```

## disassembly

```asm
0x14001f110  push    rbx
0x14001f112  push    rbp
0x14001f113  push    rsi
0x14001f114  push    rdi
0x14001f115  push    r12
0x14001f117  push    r13
0x14001f119  push    r14
0x14001f11b  push    r15
0x14001f11d  sub     rsp, 48h
0x14001f121  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f128  lea     rsi, WPP_GLOBAL_Control
0x14001f12f  cmp     rcx, rsi
0x14001f132  jz      short loc_14001F156
0x14001f134  mov     eax, [rcx+2Ch]
0x14001f137  test    al, 1
0x14001f139  jz      short loc_14001F156
0x14001f13b  cmp     byte ptr [rcx+29h], 6
0x14001f13f  jb      short loc_14001F156
0x14001f141  mov     rcx, [rcx+18h]
0x14001f145  lea     r8, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids
0x14001f14c  mov     edx, 14h
0x14001f151  call    WPP_SF_
0x14001f156  xor     edx, edx
0x14001f158  mov     r12, 0FFFFF78000000320h
0x14001f162  xor     edi, edi
0x14001f164  mov     r12, [r12]
0x14001f168  mov     ecx, cs:TimeIncrement
0x14001f16e  mov     r14, r12
0x14001f171  mov     eax, cs:TcpTimeoutSeconds
0x14001f177  mov     r15, r12
0x14001f17a  imul    rax, 989680h
0x14001f181  div     rcx
0x14001f184  xor     edx, edx
0x14001f186  sub     r14, rax
0x14001f189  mov     eax, cs:UdpTimeoutSeconds
0x14001f18f  imul    rax, 989680h
0x14001f196  div     rcx
0x14001f199  mov     cl, 2; NewIrql
0x14001f19b  sub     r15, rax
0x14001f19e  call    cs:__imp_KfRaiseIrql
0x14001f1a5  nop     dword ptr [rax+rax+00h]
0x14001f1aa  lea     rcx, MappingLock; SpinLock
0x14001f1b1  mov     r13b, al
0x14001f1b4  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001f1bb  nop     dword ptr [rax+rax+00h]
0x14001f1c0  mov     rbx, cs:MappingList
0x14001f1c7  jmp     loc_14001F308
0x14001f1cc  inc     edi
0x14001f1ce  mov     eax, 0CCCCCCCDh
0x14001f1d3  mul     edi
0x14001f1d5  shr     edx, 3
0x14001f1d8  lea     ecx, [rdx+rdx*4]
0x14001f1db  add     ecx, ecx
0x14001f1dd  cmp     edi, ecx
0x14001f1df  jnz     short loc_14001F1EE
0x14001f1e1  call    NatShouldYieldProcessor
0x14001f1e6  test    al, al
0x14001f1e8  jnz     loc_14001F354
0x14001f1ee  mov     rcx, rbx
0x14001f1f1  call    NatUpdateStatisticsMapping
0x14001f1f6  mov     eax, [rbx+0F0h]
0x14001f1fc  and     al, 41h
0x14001f1fe  cmp     al, 40h ; '@'
0x14001f200  jnz     short loc_14001F210
0x14001f202  cmp     qword ptr [rbx+0D0h], 0
0x14001f20a  jnz     loc_14001F305
0x14001f210  lea     rsi, [rbx+68h]
0x14001f214  mov     rcx, rsi; SpinLock
0x14001f217  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001f21e  nop     dword ptr [rax+rax+00h]
0x14001f223  mov     eax, [rbx+0F0h]
0x14001f229  test    al, 1
0x14001f22b  jnz     short loc_14001F26A
0x14001f22d  cmp     byte ptr [rbx+56h], 6
0x14001f231  mov     rcx, [rbx+60h]
0x14001f235  jnz     short loc_14001F245
0x14001f237  test    al, 20h
0x14001f239  jnz     short loc_14001F263
0x14001f23b  and     eax, 8006h
0x14001f240  cmp     eax, 2
0x14001f243  jnz     short loc_14001F25E
0x14001f245  cmp     rcx, r15
0x14001f248  jl      short loc_14001F26A
0x14001f24a  mov     rcx, rsi; SpinLock
0x14001f24d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001f254  nop     dword ptr [rax+rax+00h]
0x14001f259  jmp     loc_14001F305
0x14001f25e  cmp     rcx, r14
0x14001f261  jmp     short loc_14001F248
0x14001f263  test    eax, 48200h
0x14001f268  jmp     short loc_14001F243
0x14001f26a  mov     rcx, rsi; SpinLock
0x14001f26d  mov     rbp, rbx
0x14001f270  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001f277  nop     dword ptr [rax+rax+00h]
0x14001f27c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f283  lea     rsi, WPP_GLOBAL_Control
0x14001f28a  cmp     rcx, rsi
0x14001f28d  jz      short loc_14001F2F9
0x14001f28f  mov     eax, [rcx+2Ch]
0x14001f292  test    al, 1
0x14001f294  jz      short loc_14001F2BE
0x14001f296  cmp     byte ptr [rcx+29h], 5
0x14001f29a  jb      short loc_14001F2BE
0x14001f29c  mov     rax, [rbx+40h]
0x14001f2a0  lea     r8, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids
0x14001f2a7  mov     r9, [rbx+50h]
0x14001f2ab  mov     edx, 15h
0x14001f2b0  mov     rcx, [rcx+18h]
0x14001f2b4  mov     [rsp+88h+var_68], rax
0x14001f2b9  call    WPP_SF_ii
0x14001f2be  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f2c5  cmp     rcx, rsi
0x14001f2c8  jz      short loc_14001F2F9
0x14001f2ca  mov     eax, [rcx+2Ch]
0x14001f2cd  test    al, 1
0x14001f2cf  jz      short loc_14001F2F9
0x14001f2d1  cmp     byte ptr [rcx+29h], 5
0x14001f2d5  jb      short loc_14001F2F9
0x14001f2d7  mov     rax, [rbx+48h]
0x14001f2db  lea     r8, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids
0x14001f2e2  mov     r9, [rbx+58h]
0x14001f2e6  mov     edx, 16h
0x14001f2eb  mov     rcx, [rcx+18h]
0x14001f2ef  mov     [rsp+88h+var_68], rax
0x14001f2f4  call    WPP_SF_ii
0x14001f2f9  mov     rbx, [rbx+8]
0x14001f2fd  mov     rcx, rbp; Entry
0x14001f300  call    NatDeleteMapping
0x14001f305  mov     rbx, [rbx]
0x14001f308  lea     rax, MappingList
0x14001f30f  cmp     rbx, rax
0x14001f312  jnz     loc_14001F1CC
0x14001f318  lea     rcx, MappingLock; SpinLock
0x14001f31f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001f326  nop     dword ptr [rax+rax+00h]
0x14001f32b  lea     rbp, PptpMappingLock
0x14001f332  mov     rcx, rbp; SpinLock
0x14001f335  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001f33c  nop     dword ptr [rax+rax+00h]
0x14001f341  mov     rbx, cs:PptpMappingList
0x14001f348  lea     r14, PptpMappingList
0x14001f34f  jmp     loc_14001F3F1
0x14001f354  lea     rcx, MappingLock
0x14001f35b  jmp     loc_14001F72A
0x14001f360  inc     edi
0x14001f362  mov     eax, 0CCCCCCCDh
0x14001f367  mul     edi
0x14001f369  shr     edx, 3
0x14001f36c  lea     ecx, [rdx+rdx*4]
0x14001f36f  add     ecx, ecx
0x14001f371  cmp     edi, ecx
0x14001f373  jnz     short loc_14001F382
0x14001f375  call    NatShouldYieldProcessor
0x14001f37a  test    al, al
0x14001f37c  jnz     loc_14001F432
0x14001f382  mov     eax, [rbx+38h]
0x14001f385  test    al, 2
0x14001f387  jz      short loc_14001F3EE
0x14001f389  cmp     [rbx+40h], r15
0x14001f38d  jge     short loc_14001F3EE
0x14001f38f  mov     rsi, rbx
0x14001f392  mov     rbx, [rbx+8]
0x14001f396  mov     rcx, rsi; Entry
0x14001f399  call    NatDeletePptpMapping
0x14001f39e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f3a5  lea     rax, WPP_GLOBAL_Control
0x14001f3ac  cmp     rcx, rax
0x14001f3af  jz      short loc_14001F3EE
0x14001f3b1  mov     eax, [rcx+2Ch]
0x14001f3b4  test    al, 1
0x14001f3b6  jz      short loc_14001F3EE
0x14001f3b8  cmp     byte ptr [rcx+29h], 5
0x14001f3bc  jb      short loc_14001F3EE
0x14001f3be  movzx   eax, word ptr [rsi+34h]
0x14001f3c2  movzx   edx, word ptr [rsi+32h]
0x14001f3c6  movzx   r8d, word ptr [rsi+30h]
0x14001f3cb  mov     r9, [rsi+20h]
0x14001f3cf  mov     rcx, [rcx+18h]
0x14001f3d3  mov     [rsp+88h+var_50], eax
0x14001f3d7  mov     rax, [rsi+28h]
0x14001f3db  mov     [rsp+88h+var_58], edx
0x14001f3df  mov     dword ptr [rsp+88h+var_60], r8d
0x14001f3e4  mov     [rsp+88h+var_68], rax
0x14001f3e9  call    WPP_SF_iiddd
0x14001f3ee  mov     rbx, [rbx]
0x14001f3f1  cmp     rbx, r14
0x14001f3f4  jnz     loc_14001F360
0x14001f3fa  mov     rcx, rbp; SpinLock
0x14001f3fd  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001f404  nop     dword ptr [rax+rax+00h]
0x14001f409  lea     rbp, IcmpMappingLock
0x14001f410  mov     rcx, rbp; SpinLock
0x14001f413  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001f41a  nop     dword ptr [rax+rax+00h]
0x14001f41f  mov     rbx, cs:IcmpMappingList
0x14001f426  lea     r14, IcmpMappingList
0x14001f42d  jmp     loc_14001F51A
0x14001f432  mov     rcx, rbp
0x14001f435  jmp     loc_14001F72A
0x14001f43a  inc     edi
0x14001f43c  mov     eax, 0CCCCCCCDh
0x14001f441  mul     edi
0x14001f443  shr     edx, 3
0x14001f446  lea     ecx, [rdx+rdx*4]
0x14001f449  add     ecx, ecx
0x14001f44b  cmp     edi, ecx
0x14001f44d  jnz     short loc_14001F458
0x14001f44f  call    NatShouldYieldProcessor
0x14001f454  test    al, al
0x14001f456  jnz     short loc_14001F432
0x14001f458  cmp     [rbx+38h], r15
0x14001f45c  jge     loc_14001F517
0x14001f462  mov     rcx, [rbx]
0x14001f465  cmp     [rcx+8], rbx
0x14001f469  jnz     loc_14001F663
0x14001f46f  mov     rax, [rbx+8]
0x14001f473  cmp     [rax], rbx
0x14001f476  jnz     loc_14001F663
0x14001f47c  mov     [rax], rcx
0x14001f47f  mov     [rcx+8], rax
0x14001f483  lea     rcx, [rbx+10h]
0x14001f487  mov     r8, [rcx]
0x14001f48a  cmp     [r8+8], rcx
0x14001f48e  jnz     loc_14001F663
0x14001f494  mov     rdx, [rbx+18h]
0x14001f498  cmp     [rdx], rcx
0x14001f49b  jnz     loc_14001F663
0x14001f4a1  mov     rsi, rbx
0x14001f4a4  mov     [rdx], r8
0x14001f4a7  mov     rbx, rax
0x14001f4aa  mov     [r8+8], rdx
0x14001f4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f4b5  lea     rax, WPP_GLOBAL_Control
0x14001f4bc  cmp     rcx, rax
0x14001f4bf  jz      short loc_14001F502
0x14001f4c1  mov     eax, [rcx+2Ch]
0x14001f4c4  test    al, 1
0x14001f4c6  jz      short loc_14001F502
0x14001f4c8  cmp     byte ptr [rcx+29h], 2
0x14001f4cc  jb      short loc_14001F502
0x14001f4ce  movzx   eax, word ptr [rsi+32h]
0x14001f4d2  mov     edx, 18h
0x14001f4d7  movzx   r8d, word ptr [rsi+30h]
0x14001f4dc  mov     r9, [rsi+20h]
0x14001f4e0  mov     rcx, [rcx+18h]
0x14001f4e4  mov     [rsp+88h+var_58], eax
0x14001f4e8  mov     rax, [rsi+28h]
0x14001f4ec  mov     [rsp+88h+var_60], rax
0x14001f4f1  mov     dword ptr [rsp+88h+var_68], r8d
0x14001f4f6  lea     r8, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids
0x14001f4fd  call    WPP_SF_iDiD
0x14001f502  mov     r8d, 40h ; '@'
0x14001f508  lea     rcx, IcmpLookasideList; Lookaside
0x14001f50f  mov     rdx, rsi; Entry
0x14001f512  call    NatFreeBlockAndUpdateStateAllocationUsage
0x14001f517  mov     rbx, [rbx]
0x14001f51a  cmp     rbx, r14
0x14001f51d  jnz     loc_14001F43A
0x14001f523  mov     rcx, rbp; SpinLock
0x14001f526  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001f52d  nop     dword ptr [rax+rax+00h]
0x14001f532  lea     rbp, IpMappingLock
0x14001f539  mov     rcx, rbp; SpinLock
0x14001f53c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001f543  nop     dword ptr [rax+rax+00h]
0x14001f548  mov     rbx, cs:IpMappingList
0x14001f54f  lea     r14, IpMappingList
0x14001f556  jmp     loc_14001F62C
0x14001f55b  inc     edi
0x14001f55d  mov     eax, 0CCCCCCCDh
0x14001f562  mul     edi
0x14001f564  shr     edx, 3
0x14001f567  lea     ecx, [rdx+rdx*4]
0x14001f56a  add     ecx, ecx
0x14001f56c  cmp     edi, ecx
0x14001f56e  jnz     short loc_14001F57D
0x14001f570  call    NatShouldYieldProcessor
0x14001f575  test    al, al
0x14001f577  jnz     loc_14001F432
0x14001f57d  cmp     [rbx+38h], r15
0x14001f581  jge     loc_14001F629
0x14001f587  mov     rcx, [rbx]
0x14001f58a  cmp     [rcx+8], rbx
0x14001f58e  jnz     loc_14001F663
0x14001f594  mov     rax, [rbx+8]
0x14001f598  cmp     [rax], rbx
0x14001f59b  jnz     loc_14001F663
0x14001f5a1  mov     [rax], rcx
0x14001f5a4  mov     [rcx+8], rax
0x14001f5a8  lea     rcx, [rbx+10h]
0x14001f5ac  mov     r8, [rcx]
0x14001f5af  cmp     [r8+8], rcx
0x14001f5b3  jnz     loc_14001F663
0x14001f5b9  mov     rdx, [rbx+18h]
0x14001f5bd  cmp     [rdx], rcx
0x14001f5c0  jnz     loc_14001F663
0x14001f5c6  mov     rsi, rbx
0x14001f5c9  mov     [rdx], r8
0x14001f5cc  mov     rbx, rax
  ... truncated ...
```
