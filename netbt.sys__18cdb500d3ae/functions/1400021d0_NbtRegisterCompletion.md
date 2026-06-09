# NbtRegisterCompletion

- ea: `0x1400021d0`
- end: `0x14000272c`
- name: `NbtRegisterCompletion`
- size: `1372`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001938`
- `0x1400021d0`
- `0x140004038`
- `0x140004880`
- `0x140006e2c`
- `0x1400089c8`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000220b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002235`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000224b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002322`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000245a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000246b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002606`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002619`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000268f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000220b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002235`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000224b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002322`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000245a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000246b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002606`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002619`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000268f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002411`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400025c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002644`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000266e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002706`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000271b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002411`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400025c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002644`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000266e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002706`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000271b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400023b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400023b4`

## pseudocode

```c
__int64 __fastcall NbtRegisterCompletion(__int64 **a1, NTSTATUS a2)
{
  int v3; // r14d
  KIRQL v5; // al
  __int64 v6; // r12
  __int64 *v7; // r13
  KSPIN_LOCK *v8; // rdi
  KIRQL v9; // bl
  __int64 v10; // r15
  unsigned int v11; // eax
  KIRQL v12; // r9
  __int64 *v13; // r12
  __int64 **v14; // rbx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  KIRQL v17; // al
  __int64 j; // r14
  __int64 v19; // rcx
  __int64 **v20; // rcx
  __int64 ***v21; // rax
  __int64 *v22; // rax
  __int64 v23; // rdx
  KIRQL v25; // bl
  KIRQL v26; // al
  __int64 *i; // r8
  __int64 *v28; // rax
  __int64 v29; // rax
  __int64 *v30; // rcx
  __int64 **v31; // rax
  __int64 *v32; // rax
  __int64 v33; // rax
  unsigned int v34; // edi
  BOOL v35; // ecx
  int v36; // r9d
  KIRQL v37; // al
  IRP *v38; // rbx
  __int64 v39; // rdx
  __int64 v40; // [rsp+28h] [rbp-50h]
  __int64 v41; // [rsp+40h] [rbp-38h]
  KSPIN_LOCK *SpinLock; // [rsp+48h] [rbp-30h]
  __int64 *v43; // [rsp+50h] [rbp-28h]
  __int64 v44; // [rsp+50h] [rbp-28h]
  __int64 *v45; // [rsp+58h] [rbp-20h] BYREF
  __int64 **v46; // [rsp+60h] [rbp-18h]
  KIRQL v48; // [rsp+C8h] [rbp+50h]
  KIRQL NewIrql; // [rsp+D0h] [rbp+58h]
  int v50; // [rsp+D8h] [rbp+60h]

  v46 = &v45;
  v3 = 0;
  v45 = (__int64 *)&v45;
  v50 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc(&::SpinLock);
  v6 = (__int64)a1[4];
  v7 = a1[5];
  v48 = v5;
  v41 = v6;
  SpinLock = (KSPIN_LOCK *)(v6 + 848);
  v8 = (KSPIN_LOCK *)(v7 + 7);
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 848));
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 7);
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      *((_DWORD *)v7 + 5) + 1,
      14,
      (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
      (_DWORD)v7,
      *((_DWORD *)v7 + 5),
      *((_DWORD *)v7 + 5) + 1,
      133,
      (__int64)"minio\\netbt\\sys\\name.c");
  _InterlockedIncrement((volatile signed __int32 *)v7 + 5);
  v10 = v7[5];
  v11 = *(_DWORD *)(v10 + 72) & 0xFFFFFF0F;
  *(_QWORD *)(v10 + 112) = 0;
  if ( !a2 || a2 == 258 )
  {
    *(_DWORD *)(v10 + 72) = v11 | 0x10;
  }
  else
  {
    a2 = -1073741635;
    *(_DWORD *)(v10 + 72) = v11 | 0x40;
    *(_QWORD *)(v10 + 104) |= *(_QWORD *)(v6 + 560);
  }
  NbtCheckNameAddrTimer(v10);
  KeReleaseSpinLock(&::SpinLock, v9);
  v12 = NewIrql;
  v13 = v7 + 3;
  while ( 2 )
  {
    v14 = (__int64 **)*v13;
    if ( (__int64 *)*v13 != v13 )
    {
      do
      {
        v43 = *v14;
        if ( v14[3] && (v14 == a1 || v14[4] == (__int64 *)v41 && *((_BYTE *)v14 + 274) || a2 && *((_BYTE *)v14 + 274)) )
        {
          if ( a2 < 0 )
          {
            *(_QWORD *)(v10 + 80) = 0;
            v32 = v14[5];
            if ( v32 )
            {
              v33 = v32[5];
              if ( v33 )
              {
                if ( *(_BYTE *)(v33 + 164) != 42 && *(_BYTE *)(v33 + 179) == 32 )
                {
                  --*(_DWORD *)(v41 + 904);
                  CheckSetWakeupPattern(v41, (char *)(v33 + 164), 0, 1);
                }
              }
            }
            v28 = v14[3];
            v14[5] = 0;
            v29 = *(_QWORD *)(v28[23] + 48);
            *(_QWORD *)(v29 + 24) = 0;
            *(_QWORD *)(v29 + 32) = 0;
            v30 = *v14;
            if ( (__int64 **)(*v14)[1] != v14 || (v31 = (__int64 **)v14[1], *v31 != (__int64 *)v14) )
LABEL_34:
              __fastfail(3u);
            *v31 = v30;
            v30[1] = (__int64)v31;
          }
          *((_BYTE *)v14 + 274) = 0;
          v20 = v46;
          if ( *v46 != (__int64 *)&v45 )
            goto LABEL_34;
          v21 = (__int64 ***)(v14[3] + 21);
          *v21 = &v45;
          v21[1] = v20;
          *v20 = (__int64 *)v21;
          v46 = (__int64 **)v21;
          v14[3] = 0;
          if ( a2 < 0 )
          {
            *((_DWORD *)v14 + 4) += 10;
            ExFreePoolWithTag(v14, 0);
          }
        }
        v14 = (__int64 **)v43;
      }
      while ( v43 != v13 );
      v12 = NewIrql;
    }
    KeReleaseSpinLock(v8, v12);
    KeReleaseSpinLock(SpinLock, v48);
    while ( 1 )
    {
      v16 = v45;
      if ( v45 == (__int64 *)&v45 )
        break;
      if ( (__int64 **)v45[1] != &v45 )
        goto LABEL_34;
      v22 = (__int64 *)*v45;
      if ( *(__int64 **)(*v45 + 8) != v45 )
        goto LABEL_34;
      v45 = (__int64 *)*v45;
      v22[1] = (__int64)&v45;
      NTIoComplete((PIRP)(v16 - 21), a2, 0);
      v50 = ++v3;
    }
    if ( a2 < 0 )
    {
      for ( ; v3; --v3 )
        NbtDereferenceAddress(v7, v15, 1567, "minio\\netbt\\sys\\name.c");
      v25 = KeAcquireSpinLockRaiseToDpc(&::SpinLock);
      v26 = KeAcquireSpinLockRaiseToDpc(v8);
      for ( i = (__int64 *)*v13; i != v13; i = (__int64 *)*i )
      {
        v39 = i[4];
        if ( *(_DWORD *)(v39 + 340) != 1 )
          *(_QWORD *)(v10 + 80) |= *(_QWORD *)(v39 + 560);
      }
      KeReleaseSpinLock(v8, v26);
      KeReleaseSpinLock(&::SpinLock, v25);
      goto LABEL_26;
    }
    v17 = KeAcquireSpinLockRaiseToDpc(v8);
    for ( j = *v13; ; j = v19 )
    {
      if ( (__int64 *)j == v13 )
        goto LABEL_25;
      v19 = *(_QWORD *)j;
      v44 = *(_QWORD *)j;
      if ( *(_BYTE *)(j + 274) )
        break;
LABEL_16:
      ;
    }
    *(_BYTE *)(j + 274) = 0;
    v34 = *(_DWORD *)(v10 + 72);
    KeReleaseSpinLock((PKSPIN_LOCK)v7 + 7, v17);
    v35 = ((v34 >> 1) & 1) == 0;
    a2 = NbtRegisterName(v35, 0, (int)v10 + 164, v36, j, v40, v35, *(_QWORD *)(j + 32));
    v48 = KeAcquireSpinLockRaiseToDpc(SpinLock);
    v37 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 7);
    *(_DWORD *)(v10 + 72) = v34;
    NewIrql = v37;
    NbtCheckNameAddrTimer(v10);
    if ( a2 < 0 )
    {
      *(_BYTE *)(j + 274) = 1;
      v8 = (KSPIN_LOCK *)(v7 + 7);
      v3 = v50;
      continue;
    }
    break;
  }
  KeReleaseSpinLock(SpinLock, v12);
  v8 = (KSPIN_LOCK *)(v7 + 7);
  if ( a2 != 259 )
  {
    v38 = *(IRP **)(j + 24);
    *(_QWORD *)(j + 24) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)v7 + 7, v48);
    if ( v38 )
      NTIoComplete(v38, a2, 0);
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 7);
    v19 = v44;
    goto LABEL_16;
  }
  v17 = v48;
LABEL_25:
  KeReleaseSpinLock(v8, v17);
LABEL_26:
  NbtDereferenceAddress(v7, v23, 1687, "minio\\netbt\\sys\\name.c");
  return 0;
}

```

## disassembly

```asm
0x1400021d0  mov     [rsp-40h+arg_0], rcx
0x1400021d5  push    rbp
0x1400021d6  push    rbx
0x1400021d7  push    rsi
0x1400021d8  push    rdi
0x1400021d9  push    r12
0x1400021db  push    r13
0x1400021dd  push    r14
0x1400021df  push    r15
0x1400021e1  mov     rbp, rsp
0x1400021e4  sub     rsp, 78h
0x1400021e8  lea     rax, [rbp+var_20]
0x1400021ec  mov     rbx, rcx
0x1400021ef  mov     [rbp+var_18], rax
0x1400021f3  lea     rcx, SpinLock; SpinLock
0x1400021fa  lea     rax, [rbp+var_20]
0x1400021fe  xor     r14d, r14d
0x140002201  mov     [rbp+var_20], rax
0x140002205  mov     esi, edx
0x140002207  mov     [rbp+arg_18], r14d
0x14000220b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002212  nop     dword ptr [rax+rax+00h]
0x140002217  mov     r12, [rbx+20h]
0x14000221b  mov     r13, [rbx+28h]
0x14000221f  mov     [rbp+arg_8], al
0x140002222  mov     [rbp+var_38], r12
0x140002226  lea     rax, [r12+350h]
0x14000222e  mov     rcx, rax; SpinLock
0x140002231  mov     [rbp+SpinLock], rax
0x140002235  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000223c  nop     dword ptr [rax+rax+00h]
0x140002241  lea     rdi, [r13+38h]
0x140002245  mov     [rbp+NewIrql], al
0x140002248  mov     rcx, rdi; SpinLock
0x14000224b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002252  nop     dword ptr [rax+rax+00h]
0x140002257  mov     bl, al
0x140002259  test    byte ptr cs:xmmword_140038420+9, 40h
0x140002260  lea     rax, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x140002267  jnz     loc_1400024ED
0x14000226d  lock inc dword ptr [r13+14h]
0x140002272  mov     r15, [r13+28h]
0x140002276  mov     eax, [r15+48h]
0x14000227a  and     eax, 0FFFFFF0Fh
0x14000227f  mov     [r15+70h], r14
0x140002283  test    esi, esi
0x140002285  jnz     loc_140002524
0x14000228b  or      eax, 10h
0x14000228e  mov     [r15+48h], eax
0x140002292  mov     rcx, r15
0x140002295  call    NbtCheckNameAddrTimer
0x14000229a  mov     dl, bl; NewIrql
0x14000229c  lea     rcx, SpinLock; SpinLock
0x1400022a3  call    cs:__imp_KeReleaseSpinLock
0x1400022aa  nop     dword ptr [rax+rax+00h]
0x1400022af  mov     r9b, [rbp+NewIrql]
0x1400022b3  lea     r12, [r13+18h]
0x1400022b7  xor     r8d, r8d
0x1400022ba  mov     rbx, [r12]
0x1400022be  cmp     rbx, r12
0x1400022c1  jz      short loc_1400022E1
0x1400022c3  mov     rdx, [rbx]
0x1400022c6  mov     [rbp+var_28], rdx
0x1400022ca  cmp     [rbx+18h], r8
0x1400022ce  jnz     loc_140002355
0x1400022d4  mov     rbx, [rbp+var_28]
0x1400022d8  cmp     rbx, r12
0x1400022db  jnz     short loc_1400022C3
0x1400022dd  mov     r9b, [rbp+NewIrql]
0x1400022e1  mov     dl, r9b; NewIrql
0x1400022e4  mov     rcx, rdi; SpinLock
0x1400022e7  call    cs:__imp_KeReleaseSpinLock
0x1400022ee  nop     dword ptr [rax+rax+00h]
0x1400022f3  mov     dl, [rbp+arg_8]; NewIrql
0x1400022f6  mov     rcx, [rbp+SpinLock]; SpinLock
0x1400022fa  call    cs:__imp_KeReleaseSpinLock
0x140002301  nop     dword ptr [rax+rax+00h]
0x140002306  mov     rcx, [rbp+var_20]
0x14000230a  lea     rax, [rbp+var_20]
0x14000230e  cmp     rcx, rax
0x140002311  jnz     loc_1400023C8
0x140002317  test    esi, esi
0x140002319  js      loc_14000244A
0x14000231f  mov     rcx, rdi; SpinLock
0x140002322  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002329  nop     dword ptr [rax+rax+00h]
0x14000232e  mov     r14, [r12]
0x140002332  cmp     r14, r12
0x140002335  jz      loc_14000240C
0x14000233b  cmp     byte ptr [r14+112h], 0
0x140002343  mov     rcx, [r14]
0x140002346  mov     [rbp+var_28], rcx
0x14000234a  jnz     loc_1400025A1
0x140002350  mov     r14, rcx
0x140002353  jmp     short loc_140002332
0x140002355  mov     rcx, [rbp+var_38]
0x140002359  cmp     rbx, [rbp+arg_0]
0x14000235d  jnz     loc_140002480
0x140002363  test    esi, esi
0x140002365  js      loc_14000254D
0x14000236b  mov     [rbx+112h], r8b
0x140002372  lea     rax, [rbp+var_20]
0x140002376  mov     rcx, [rbp+var_18]
0x14000237a  cmp     [rcx], rax
0x14000237d  jnz     loc_1400024AD
0x140002383  mov     rax, [rbx+18h]
0x140002387  lea     rdx, [rbp+var_20]
0x14000238b  add     rax, 0A8h
0x140002391  mov     [rax], rdx
0x140002394  mov     [rax+8], rcx
0x140002398  mov     [rcx], rax
0x14000239b  mov     [rbp+var_18], rax
0x14000239f  mov     [rbx+18h], r8
0x1400023a3  test    esi, esi
0x1400023a5  jns     loc_1400022D4
0x1400023ab  add     dword ptr [rbx+10h], 0Ah
0x1400023af  xor     edx, edx; Tag
0x1400023b1  mov     rcx, rbx; P
0x1400023b4  call    cs:__imp_ExFreePoolWithTag
0x1400023bb  nop     dword ptr [rax+rax+00h]
0x1400023c0  xor     r8d, r8d
0x1400023c3  jmp     loc_1400022D4
0x1400023c8  lea     rax, [rbp+var_20]
0x1400023cc  cmp     [rcx+8], rax
0x1400023d0  jnz     loc_1400024AD
0x1400023d6  mov     rax, [rcx]
0x1400023d9  cmp     [rax+8], rcx
0x1400023dd  jnz     loc_1400024AD
0x1400023e3  lea     rdx, [rbp+var_20]
0x1400023e7  mov     [rbp+var_20], rax
0x1400023eb  mov     [rax+8], rdx
0x1400023ef  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1400023f6  mov     edx, esi
0x1400023f8  xor     r8d, r8d
0x1400023fb  call    NTIoComplete
0x140002400  inc     r14d
0x140002403  mov     [rbp+arg_18], r14d
0x140002407  jmp     loc_140002306
0x14000240c  mov     dl, al; NewIrql
0x14000240e  mov     rcx, rdi; SpinLock
0x140002411  call    cs:__imp_KeReleaseSpinLock
0x140002418  nop     dword ptr [rax+rax+00h]
0x14000241d  test    esi, esi
0x14000241f  js      short loc_140002453
0x140002421  lea     r9, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x140002428  mov     r8d, 697h
0x14000242e  mov     rcx, r13
0x140002431  call    NbtDereferenceAddress
0x140002436  xor     eax, eax
0x140002438  add     rsp, 78h
0x14000243c  pop     r15
0x14000243e  pop     r14
0x140002440  pop     r13
0x140002442  pop     r12
0x140002444  pop     rdi
0x140002445  pop     rsi
0x140002446  pop     rbx
0x140002447  pop     rbp
0x140002448  retn
0x14000244a  test    r14d, r14d
0x14000244d  jnz     loc_1400026C1
0x140002453  lea     rcx, SpinLock; SpinLock
0x14000245a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002461  nop     dword ptr [rax+rax+00h]
0x140002466  mov     rcx, rdi; SpinLock
0x140002469  mov     bl, al
0x14000246b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002472  nop     dword ptr [rax+rax+00h]
0x140002477  mov     r8, [r12]
0x14000247b  jmp     loc_1400026FC
0x140002480  cmp     [rbx+20h], rcx
0x140002484  jnz     short loc_140002493
0x140002486  cmp     [rbx+112h], r8b
0x14000248d  jnz     loc_140002363
0x140002493  test    esi, esi
0x140002495  jz      loc_1400022D4
0x14000249b  cmp     [rbx+112h], r8b
0x1400024a2  jz      loc_1400022D4
0x1400024a8  jmp     loc_140002363
0x1400024ad  mov     ecx, 3
0x1400024b2  int     29h; Win8: RtlFailFast(ecx)
0x1400024b4  mov     rax, [rbx+18h]
0x1400024b8  mov     [rbx+28h], r8
0x1400024bc  mov     rcx, [rax+0B8h]
0x1400024c3  mov     rax, [rcx+30h]
0x1400024c7  mov     [rax+18h], r8
0x1400024cb  mov     [rax+20h], r8
0x1400024cf  mov     rcx, [rbx]
0x1400024d2  cmp     [rcx+8], rbx
0x1400024d6  jnz     short loc_1400024AD
0x1400024d8  mov     rax, [rbx+8]
0x1400024dc  cmp     [rax], rbx
0x1400024df  jnz     short loc_1400024AD
0x1400024e1  mov     [rax], rcx
0x1400024e4  mov     [rcx+8], rax
0x1400024e8  jmp     loc_14000236B
0x1400024ed  mov     r8d, [r13+14h]
0x1400024f1  mov     edx, 0Eh
0x1400024f6  mov     [rsp+78h+var_40], rax
0x1400024fb  mov     r9, r13
0x1400024fe  mov     dword ptr [rsp+78h+var_48], 585h
0x140002506  lea     ecx, [r8+1]
0x14000250a  mov     dword ptr [rsp+78h+var_50], ecx
0x14000250e  mov     dword ptr [rsp+78h+var_58], r8d
0x140002513  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x14000251a  call    WPP_SF_qddds
0x14000251f  jmp     loc_14000226D
0x140002524  cmp     esi, 102h
0x14000252a  jz      loc_14000228B
0x140002530  or      eax, 40h
0x140002533  mov     esi, 0C00000BDh
0x140002538  mov     [r15+48h], eax
0x14000253c  mov     rax, [r12+230h]
0x140002544  or      [r15+68h], rax
0x140002548  jmp     loc_140002292
0x14000254d  mov     [r15+50h], r8
0x140002551  mov     rax, [rbx+28h]
0x140002555  test    rax, rax
0x140002558  jz      loc_1400024B4
0x14000255e  mov     rax, [rax+28h]
0x140002562  test    rax, rax
0x140002565  jz      loc_1400024B4
0x14000256b  lea     rdx, [rax+0A4h]
0x140002572  cmp     byte ptr [rdx], 2Ah ; '*'
0x140002575  jz      loc_1400024B4
0x14000257b  cmp     byte ptr [rax+0B3h], 20h ; ' '
0x140002582  jnz     loc_1400024B4
0x140002588  dec     dword ptr [rcx+388h]
0x14000258e  mov     r9b, 1
0x140002591  xor     r8d, r8d
0x140002594  call    CheckSetWakeupPattern
0x140002599  xor     r8d, r8d
0x14000259c  jmp     loc_1400024B4
0x1400025a1  mov     byte ptr [r14+112h], 0
0x1400025a9  lea     rcx, [r13+38h]; SpinLock
0x1400025ad  mov     edi, [r15+48h]
0x1400025b1  mov     esi, 1
0x1400025b6  mov     ebx, edi
0x1400025b8  mov     dl, al; NewIrql
0x1400025ba  shr     ebx, 1
0x1400025bc  not     bx
0x1400025bf  and     bx, si
0x1400025c2  call    cs:__imp_KeReleaseSpinLock
0x1400025c9  nop     dword ptr [rax+rax+00h]
0x1400025ce  mov     rax, [r14+20h]
0x1400025d2  lea     r8, [r15+0A4h]; int
0x1400025d9  mov     [rsp+78h+var_40], rax; __int64
0x1400025de  movzx   ecx, bx
0x1400025e1  or      cx, 2
0x1400025e5  test    sil, dil
0x1400025e8  cmovz   cx, bx; int
0x1400025ec  xor     edx, edx; int
0x1400025ee  mov     word ptr [rsp+78h+var_48], cx; NewIrql
0x1400025f3  mov     [rsp+78h+var_58], r14; __int64
0x1400025f8  call    NbtRegisterName
0x1400025fd  mov     rbx, [rbp+SpinLock]
0x140002601  mov     esi, eax
0x140002603  mov     rcx, rbx; SpinLock
0x140002606  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000260d  nop     dword ptr [rax+rax+00h]
0x140002612  lea     rcx, [r13+38h]; SpinLock
0x140002616  mov     [rbp+arg_8], al
0x140002619  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002620  nop     dword ptr [rax+rax+00h]
0x140002625  mov     rcx, r15
0x140002628  mov     [r15+48h], edi
0x14000262c  mov     r9b, al
0x14000262f  mov     [rbp+NewIrql], al
0x140002632  call    NbtCheckNameAddrTimer
0x140002637  xor     r8d, r8d
0x14000263a  test    esi, esi
0x14000263c  js      short loc_1400026A4
0x14000263e  mov     dl, r9b; NewIrql
0x140002641  mov     rcx, rbx; SpinLock
0x140002644  call    cs:__imp_KeReleaseSpinLock
0x14000264b  nop     dword ptr [rax+rax+00h]
0x140002650  lea     rdi, [r13+38h]
0x140002654  cmp     esi, 103h
0x14000265a  jz      short loc_1400026B9
0x14000265c  mov     rbx, [r14+18h]
0x140002660  mov     rcx, rdi; SpinLock
0x140002663  mov     dl, [rbp+arg_8]; NewIrql
0x140002666  mov     qword ptr [r14+18h], 0
0x14000266e  call    cs:__imp_KeReleaseSpinLock
0x140002675  nop     dword ptr [rax+rax+00h]
0x14000267a  test    rbx, rbx
0x14000267d  jz      short loc_14000268C
0x14000267f  xor     r8d, r8d
0x140002682  mov     edx, esi
0x140002684  mov     rcx, rbx; Irp
0x140002687  call    NTIoComplete
0x14000268c  mov     rcx, rdi; SpinLock
0x14000268f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002696  nop     dword ptr [rax+rax+00h]
0x14000269b  mov     rcx, [rbp+var_28]
0x14000269f  jmp     loc_140002350
0x1400026a4  mov     byte ptr [r14+112h], 1
0x1400026ac  lea     rdi, [r13+38h]
0x1400026b0  mov     r14d, [rbp+arg_18]
0x1400026b4  jmp     loc_1400022BA
  ... truncated ...
```
