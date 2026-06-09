# VmbusTlDeliverDataIndications

- ea: `0x14000309c`
- end: `0x1400034eb`
- name: `VmbusTlDeliverDataIndications`
- size: `1103`
- prototype: `void __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140003890`
- `0x140003bc8`
- `0x140004750`
- `0x140005280`

## callees

- `0x14000309c`
- `0x1400034f4`
- `0x1400036d0`
- `0x140003cec`
- `0x14000483c`
- `0x1400058d0`
- `0x14000975c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003156`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400032e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003389`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000344a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003480`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003156`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400032e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003389`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000344a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003480`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003189`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400031db`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003367`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003427`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000346d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000349e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003189`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400031db`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003367`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003427`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000346d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000349e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400030b8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400030b8`

## pseudocode

```c
void __fastcall VmbusTlDeliverDataIndications(__int64 a1, char a2)
{
  signed __int32 v4; // ett
  int *v5; // r15
  int v6; // ebx
  KIRQL v7; // al
  char v8; // di
  __int64 v9; // r14
  KIRQL v10; // al
  __int64 v11; // rbp
  int v12; // edi
  _QWORD *v13; // rdi
  _QWORD *v14; // r14
  int v15; // eax
  bool v16; // zf
  _QWORD *v17; // rdi
  KIRQL v18; // r8
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int64 v23; // rcx
  int v24; // edi
  char v25; // di
  KIRQL v26; // al
  KIRQL v27; // cl
  bool v28; // bp
  KIRQL v29; // al
  char v30; // bl
  KIRQL v31; // al
  signed __int32 v32[20]; // [rsp+0h] [rbp-E8h] BYREF
  __int128 v33; // [rsp+50h] [rbp-98h]
  _QWORD *v34; // [rsp+100h] [rbp+18h]
  _QWORD *v35; // [rsp+100h] [rbp+18h]
  KIRQL v36; // [rsp+100h] [rbp+18h]
  __int64 v37; // [rsp+108h] [rbp+20h]

  if ( KeGetCurrentIrql() >= 2u )
  {
    v4 = *(_DWORD *)(a1 + 780) & 0x7FFFFFFF;
    if ( v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 780), (v4 + 1) | 0x80000000, v4) )
      VmbusTlQueueEndpointAction(a1, a1 + 1080, 1, 0);
    return;
  }
  if ( a2 )
  {
    *(_OWORD *)(a1 + 1080) = 0;
    *(_OWORD *)(a1 + 1096) = 0;
    *(_OWORD *)(a1 + 1112) = 0;
    *(_QWORD *)(a1 + 1128) = 0;
    _InterlockedOr(v32, 0);
    *(_DWORD *)(a1 + 780) &= ~0x80000000;
  }
  v5 = (int *)(a1 + 772);
  while ( 2 )
  {
    while ( 2 )
    {
      v6 = 0;
      v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 744));
      if ( *(_BYTE *)(a1 + 776) || (unsigned int)(*v5 - 1) <= 1 )
      {
        v8 = 0;
      }
      else
      {
        v8 = 1;
        *(_BYTE *)(a1 + 776) = 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 744), v7);
      if ( !v8 )
        return;
      v9 = a1 + 752;
      do
      {
        v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 744));
        v11 = 0;
        v12 = *v5;
        if ( *(_QWORD *)v9 != v9 )
          v11 = *(_QWORD *)v9 - 40LL;
        v37 = *(_QWORD *)(a1 + 784);
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 744), v10);
        if ( !v11 )
          break;
        v33 = *(_OWORD *)(v11 + 48);
        if ( v12 )
        {
          v13 = (_QWORD *)v11;
          v14 = 0;
          do
          {
            v15 = VmbusTlFulfillReceiveRequest(a1, (__int64)v13);
            v6 = v15;
            if ( v13[3] )
              break;
            v14 = v13;
            v13 = (_QWORD *)*v13;
            if ( v15 == -1073741300 )
              break;
          }
          while ( v13 );
          v34 = v14;
          v16 = v14 == 0;
          v9 = a1 + 752;
          if ( v16 )
          {
            v35 = (_QWORD *)v11;
          }
          else
          {
            *v34 = 0;
            VmbusTlpReleaseIndicationList(a1, v11, 0);
            v35 = v13;
          }
          if ( !v13 )
          {
            if ( v6 != -1073741300 )
              v6 = 0;
            goto LABEL_32;
          }
          if ( v6 == -1073741300 )
          {
            VmbusTlpReleaseIndicationList(a1, v13, 0);
            v17 = 0;
            goto LABEL_35;
          }
          v6 = VmbusTlIndicateDataToClient(a1, v13);
          if ( v6 < 0 )
          {
            if ( (unsigned int)dword_140013058 > 2 )
              HvsocketTraceEndpointError("VmbusTlDeliverSingleDataIndicationList", 688, (unsigned int)v6, a1);
LABEL_32:
            v17 = v35;
            goto LABEL_35;
          }
        }
        else
        {
          VmbusTlpReleaseIndicationList(a1, v11, 0);
        }
        v17 = 0;
        v6 = 0;
LABEL_35:
        v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 744));
        v19 = *(_QWORD *)v9 - 40LL;
        if ( v19 == v11 && *(_QWORD *)(v19 + 56) == *((_QWORD *)&v33 + 1) )
        {
          v20 = (_QWORD *)(v11 + 40);
          v21 = *(_QWORD *)(v11 + 40);
          if ( *(_QWORD *)(v21 + 8) != v11 + 40 || (v22 = *(_QWORD **)(v11 + 48), (_QWORD *)*v22 != v20) )
LABEL_69:
            __fastfail(3u);
          *v22 = v21;
          *(_QWORD *)(v21 + 8) = v22;
          *(_QWORD *)(v11 + 48) = v11 + 40;
          *v20 = v20;
        }
        if ( v17 )
        {
          v23 = *(_QWORD *)v9;
          if ( *(_QWORD *)(*(_QWORD *)v9 + 8LL) != v9 )
            goto LABEL_69;
          v17[5] = v23;
          v17[6] = v9;
          *(_QWORD *)(v23 + 8) = v17 + 5;
          *(_QWORD *)v9 = v17 + 5;
        }
        v24 = *v5;
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 744), v18);
      }
      while ( v6 >= 0 || !v24 );
      v25 = 0;
      v26 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 744));
      *(_BYTE *)(a1 + 776) = 0;
      v27 = v26;
      v36 = v26;
      if ( v6 != -1073741285 )
      {
        if ( v6 < 0 )
          goto LABEL_49;
        goto LABEL_56;
      }
      if ( v37 > *(_QWORD *)(a1 + 784) )
      {
        v6 = 0;
        goto LABEL_56;
      }
LABEL_49:
      v28 = 0;
      if ( (unsigned int)dword_140013058 > 2 )
      {
        HvsocketTraceEndpointError("VmbusTlDeliverDataIndications", 920, (unsigned int)v6, a1);
        v27 = v36;
      }
      if ( *v5 != 3 )
      {
        if ( *v5 )
          goto LABEL_57;
LABEL_56:
        v28 = *(_QWORD *)v9 != v9;
        goto LABEL_57;
      }
      if ( v6 == -1073741300 )
      {
        *v5 = 0;
        goto LABEL_56;
      }
      *v5 = 2;
      v25 = 1;
LABEL_57:
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 744), v27);
      if ( !v25 || v6 == -1073741300 )
      {
        if ( !v28 )
        {
          if ( v6 == -1073741300 )
            VmbusTlCommonOppositeEndpointDisconnectRequest(a1);
          return;
        }
        continue;
      }
      break;
    }
    v29 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 848));
    v30 = v28;
    if ( *(_QWORD *)(a1 + 832) != a1 + 832 )
      v30 = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 848), v29);
    if ( v30 )
    {
      v31 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 744));
      if ( *v5 == 2 )
        *v5 = 3;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 744), v31);
      continue;
    }
    break;
  }
}

```

## disassembly

```asm
0x14000309c  mov     [rsp+arg_0], rbx
0x1400030a1  push    rbp
0x1400030a2  push    rsi
0x1400030a3  push    rdi
0x1400030a4  push    r12
0x1400030a6  push    r13
0x1400030a8  push    r14
0x1400030aa  push    r15
0x1400030ac  sub     rsp, 0B0h
0x1400030b3  mov     bl, dl
0x1400030b5  mov     rsi, rcx
0x1400030b8  call    cs:__imp_KeGetCurrentIrql
0x1400030bf  nop     dword ptr [rax+rax+00h]
0x1400030c4  cmp     al, 2
0x1400030c6  jb      short loc_140003104
0x1400030c8  mov     eax, [rsi+30Ch]
0x1400030ce  btr     eax, 1Fh
0x1400030d2  lea     edx, [rax+1]
0x1400030d5  or      edx, 80000000h
0x1400030db  lock cmpxchg [rsi+30Ch], edx
0x1400030e3  jnz     loc_1400034C8
0x1400030e9  xor     r9d, r9d
0x1400030ec  lea     rdx, [rsi+438h]
0x1400030f3  mov     rcx, rsi
0x1400030f6  lea     r8d, [r9+1]
0x1400030fa  call    VmbusTlQueueEndpointAction
0x1400030ff  jmp     loc_1400034C8
0x140003104  test    bl, bl
0x140003106  jz      short loc_14000313D
0x140003108  xorps   xmm0, xmm0
0x14000310b  xor     eax, eax
0x14000310d  movups  xmmword ptr [rsi+438h], xmm0
0x140003114  movups  xmmword ptr [rsi+448h], xmm0
0x14000311b  movups  xmmword ptr [rsi+458h], xmm0
0x140003122  mov     [rsi+468h], rax
0x140003129  lock or [rsp+0E8h+var_E8], eax
0x14000312d  mov     eax, [rsi+30Ch]
0x140003133  btr     eax, 1Fh
0x140003137  mov     [rsi+30Ch], eax
0x14000313d  lea     r13, [rsi+2E8h]
0x140003144  mov     r12d, 1
0x14000314a  lea     r15, [rsi+304h]
0x140003151  mov     rcx, r13; SpinLock
0x140003154  xor     ebx, ebx
0x140003156  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000315d  nop     dword ptr [rax+rax+00h]
0x140003162  cmp     [rsi+308h], bl
0x140003168  jnz     short loc_140003181
0x14000316a  mov     ecx, [r15]
0x14000316d  sub     ecx, r12d
0x140003170  cmp     ecx, r12d
0x140003173  jbe     short loc_140003181
0x140003175  mov     dil, r12b
0x140003178  mov     [rsi+308h], r12b
0x14000317f  jmp     short loc_140003184
0x140003181  xor     dil, dil
0x140003184  mov     dl, al; NewIrql
0x140003186  mov     rcx, r13; SpinLock
0x140003189  call    cs:__imp_KeReleaseSpinLock
0x140003190  nop     dword ptr [rax+rax+00h]
0x140003195  test    dil, dil
0x140003198  jz      loc_1400034C8
0x14000319e  lea     r14, [rsi+2F0h]
0x1400031a5  mov     rcx, r13; SpinLock
0x1400031a8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400031af  nop     dword ptr [rax+rax+00h]
0x1400031b4  mov     rdx, [r14]
0x1400031b7  xor     ebp, ebp
0x1400031b9  mov     edi, [r15]
0x1400031bc  cmp     rdx, r14
0x1400031bf  lea     rcx, [rdx-28h]
0x1400031c3  mov     dl, al; NewIrql
0x1400031c5  cmovnz  rbp, rcx
0x1400031c9  mov     rcx, [rsi+310h]
0x1400031d0  mov     [rsp+0E8h+arg_18], rcx
0x1400031d8  mov     rcx, r13; SpinLock
0x1400031db  call    cs:__imp_KeReleaseSpinLock
0x1400031e2  nop     dword ptr [rax+rax+00h]
0x1400031e7  test    rbp, rbp
0x1400031ea  jz      loc_140003383
0x1400031f0  movups  xmm1, xmmword ptr [rbp+30h]
0x1400031f4  movups  [rsp+0E8h+var_98], xmm1
0x1400031f9  test    edi, edi
0x1400031fb  jz      loc_1400032D3
0x140003201  mov     rdi, rbp
0x140003204  xor     r14d, r14d
0x140003207  mov     rdx, rdi
0x14000320a  mov     rcx, rsi
0x14000320d  call    VmbusTlFulfillReceiveRequest
0x140003212  cmp     qword ptr [rdi+18h], 0
0x140003217  mov     ebx, eax
0x140003219  jnz     short loc_14000322D
0x14000321b  mov     r14, rdi
0x14000321e  mov     rdi, [rdi]
0x140003221  cmp     eax, 0C000020Ch
0x140003226  jz      short loc_14000322D
0x140003228  test    rdi, rdi
0x14000322b  jnz     short loc_140003207
0x14000322d  mov     [rsp+0E8h+arg_10], r14
0x140003235  test    r14, r14
0x140003238  lea     r14, [rsi+2F0h]
0x14000323f  jz      short loc_140003268
0x140003241  mov     rax, [rsp+0E8h+arg_10]
0x140003249  xor     r8d, r8d
0x14000324c  mov     rdx, rbp
0x14000324f  mov     rcx, rsi
0x140003252  mov     qword ptr [rax], 0
0x140003259  call    VmbusTlpReleaseIndicationList
0x14000325e  mov     [rsp+0E8h+arg_10], rdi
0x140003266  jmp     short loc_140003270
0x140003268  mov     [rsp+0E8h+arg_10], rbp
0x140003270  test    rdi, rdi
0x140003273  jz      short loc_1400032BE
0x140003275  mov     rdx, rdi
0x140003278  mov     rcx, rsi
0x14000327b  cmp     ebx, 0C000020Ch
0x140003281  jz      short loc_1400032B2
0x140003283  call    VmbusTlIndicateDataToClient
0x140003288  mov     ebx, eax
0x14000328a  test    eax, eax
0x14000328c  jns     short loc_1400032E1
0x14000328e  mov     eax, cs:dword_140013058
0x140003294  cmp     eax, 2
0x140003297  jbe     short loc_1400032C9
0x140003299  mov     r9, rsi
0x14000329c  lea     rcx, aVmbustldeliver; "VmbusTlDeliverSingleDataIndicationList"
0x1400032a3  mov     r8d, ebx
0x1400032a6  mov     edx, 2B0h
0x1400032ab  call    HvsocketTraceEndpointError
0x1400032b0  jmp     short loc_1400032C9
0x1400032b2  xor     r8d, r8d
0x1400032b5  call    VmbusTlpReleaseIndicationList
0x1400032ba  xor     edi, edi
0x1400032bc  jmp     short loc_1400032E5
0x1400032be  xor     eax, eax
0x1400032c0  cmp     ebx, 0C000020Ch
0x1400032c6  cmovnz  ebx, eax
0x1400032c9  mov     rdi, [rsp+0E8h+arg_10]
0x1400032d1  jmp     short loc_1400032E5
0x1400032d3  xor     r8d, r8d
0x1400032d6  mov     rdx, rbp
0x1400032d9  mov     rcx, rsi
0x1400032dc  call    VmbusTlpReleaseIndicationList
0x1400032e1  xor     edi, edi
0x1400032e3  xor     ebx, ebx
0x1400032e5  mov     rcx, r13; SpinLock
0x1400032e8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400032ef  nop     dword ptr [rax+rax+00h]
0x1400032f4  mov     rdx, [r14]
0x1400032f7  mov     r8b, al
0x1400032fa  add     rdx, 0FFFFFFFFFFFFFFD8h
0x1400032fe  cmp     rdx, rbp
0x140003301  jnz     short loc_14000333A
0x140003303  mov     rcx, qword ptr [rsp+0E8h+var_98+8]
0x140003308  cmp     [rdx+38h], rcx
0x14000330c  jnz     short loc_14000333A
0x14000330e  lea     rcx, [rbp+28h]
0x140003312  mov     rdx, [rcx]
0x140003315  cmp     [rdx+8], rcx
0x140003319  jnz     loc_1400034E4
0x14000331f  mov     rax, [rbp+30h]
0x140003323  cmp     [rax], rcx
0x140003326  jnz     loc_1400034E4
0x14000332c  mov     [rax], rdx
0x14000332f  mov     [rdx+8], rax
0x140003333  mov     [rcx+8], rcx
0x140003337  mov     [rcx], rcx
0x14000333a  test    rdi, rdi
0x14000333d  jz      short loc_14000335E
0x14000333f  mov     rcx, [r14]
0x140003342  cmp     [rcx+8], r14
0x140003346  jnz     loc_1400034E4
0x14000334c  lea     rax, [rdi+28h]
0x140003350  mov     [rax], rcx
0x140003353  mov     [rax+8], r14
0x140003357  mov     [rcx+8], rax
0x14000335b  mov     [r14], rax
0x14000335e  mov     edi, [r15]
0x140003361  mov     dl, r8b; NewIrql
0x140003364  mov     rcx, r13; SpinLock
0x140003367  call    cs:__imp_KeReleaseSpinLock
0x14000336e  nop     dword ptr [rax+rax+00h]
0x140003373  test    ebx, ebx
0x140003375  jns     loc_1400031A5
0x14000337b  test    edi, edi
0x14000337d  jz      loc_1400031A5
0x140003383  mov     rcx, r13; SpinLock
0x140003386  xor     dil, dil
0x140003389  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003390  nop     dword ptr [rax+rax+00h]
0x140003395  mov     [rsi+308h], dil
0x14000339c  mov     cl, al
0x14000339e  mov     byte ptr [rsp+0E8h+arg_10], al
0x1400033a5  cmp     ebx, 0C000021Bh
0x1400033ab  jnz     short loc_1400033C2
0x1400033ad  mov     rax, [rsp+0E8h+arg_18]
0x1400033b5  cmp     rax, [rsi+310h]
0x1400033bc  jle     short loc_1400033C6
0x1400033be  xor     ebx, ebx
0x1400033c0  jmp     short loc_14000341B
0x1400033c2  test    ebx, ebx
0x1400033c4  jns     short loc_14000341B
0x1400033c6  mov     eax, cs:dword_140013058
0x1400033cc  xor     bpl, bpl
0x1400033cf  cmp     eax, 2
0x1400033d2  jbe     short loc_1400033F2
0x1400033d4  mov     r9, rsi
0x1400033d7  lea     rcx, aVmbustldeliver_0; "VmbusTlDeliverDataIndications"
0x1400033de  mov     r8d, ebx
0x1400033e1  mov     edx, 398h
0x1400033e6  call    HvsocketTraceEndpointError
0x1400033eb  mov     cl, byte ptr [rsp+0E8h+arg_10]
0x1400033f2  mov     eax, [r15]
0x1400033f5  cmp     eax, 3
0x1400033f8  jnz     short loc_140003417
0x1400033fa  cmp     ebx, 0C000020Ch
0x140003400  jnz     short loc_14000340B
0x140003402  mov     dword ptr [r15], 0
0x140003409  jmp     short loc_14000341B
0x14000340b  mov     dword ptr [r15], 2
0x140003412  mov     dil, r12b
0x140003415  jmp     short loc_140003422
0x140003417  test    eax, eax
0x140003419  jnz     short loc_140003422
0x14000341b  cmp     [r14], r14
0x14000341e  setnz   bpl
0x140003422  mov     dl, cl; NewIrql
0x140003424  mov     rcx, r13; SpinLock
0x140003427  call    cs:__imp_KeReleaseSpinLock
0x14000342e  nop     dword ptr [rax+rax+00h]
0x140003433  test    dil, dil
0x140003436  jz      short loc_1400034AF
0x140003438  cmp     ebx, 0C000020Ch
0x14000343e  jz      short loc_1400034AF
0x140003440  lea     rdi, [rsi+350h]
0x140003447  mov     rcx, rdi; SpinLock
0x14000344a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003451  nop     dword ptr [rax+rax+00h]
0x140003456  lea     rdx, [rsi+340h]
0x14000345d  movzx   ebx, bpl
0x140003461  cmp     [rdx], rdx
0x140003464  mov     rcx, rdi; SpinLock
0x140003467  mov     dl, al; NewIrql
0x140003469  cmovnz  ebx, r12d
0x14000346d  call    cs:__imp_KeReleaseSpinLock
0x140003474  nop     dword ptr [rax+rax+00h]
0x140003479  test    bl, bl
0x14000347b  jz      short loc_1400034C8
0x14000347d  mov     rcx, r13; SpinLock
0x140003480  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003487  nop     dword ptr [rax+rax+00h]
0x14000348c  cmp     dword ptr [r15], 2
0x140003490  jnz     short loc_140003499
0x140003492  mov     dword ptr [r15], 3
0x140003499  mov     dl, al; NewIrql
0x14000349b  mov     rcx, r13; SpinLock
0x14000349e  call    cs:__imp_KeReleaseSpinLock
0x1400034a5  nop     dword ptr [rax+rax+00h]
0x1400034aa  jmp     loc_140003151
0x1400034af  test    bpl, bpl
0x1400034b2  jnz     loc_140003151
0x1400034b8  cmp     ebx, 0C000020Ch
0x1400034be  jnz     short loc_1400034C8
0x1400034c0  mov     rcx, rsi
0x1400034c3  call    VmbusTlCommonOppositeEndpointDisconnectRequest
0x1400034c8  mov     rbx, [rsp+0E8h+arg_0]
0x1400034d0  add     rsp, 0B0h
0x1400034d7  pop     r15
0x1400034d9  pop     r14
0x1400034db  pop     r13
0x1400034dd  pop     r12
0x1400034df  pop     rdi
0x1400034e0  pop     rsi
0x1400034e1  pop     rbp
0x1400034e2  retn
0x1400034e4  mov     ecx, 3
0x1400034e9  int     29h; Win8: RtlFailFast(ecx)
```
