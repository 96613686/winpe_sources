# UxpTpAllocateChunkTracker

- ea: `0x1c000c7b0`
- end: `0x1c000cb49`
- name: `UxpTpAllocateChunkTracker`
- size: `921`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c000c170`
- `0x1c000d860`

## callees

- `0x1c0001118`
- `0x1c000be10`
- `0x1c000c7b0`
- `0x1c001b610`
- `0x1c001b900`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0022989`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00229dd`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0022989`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00229dd`
- `ntoskrnl!IoAllocateIrpEx` at `0x1c000ca77`
- `ntoskrnl!IoAllocateIrpEx` at `0x1c000ca77`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1c0022a34`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1c0022a34`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0022948`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0022948`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c002290d`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c002290d`

## pseudocode

```c
__int64 __fastcall UxpTpAllocateChunkTracker(__int64 a1, unsigned int a2, PSLIST_ENTRY *a3)
{
  __int64 v3; // r15
  __int64 v4; // r13
  NTSTATUS v5; // ebp
  unsigned __int64 v6; // r11
  int v7; // ecx
  unsigned __int64 v8; // r9
  unsigned __int64 v9; // r10
  __int64 v10; // rbx
  unsigned __int64 v11; // rdi
  unsigned int v12; // edx
  unsigned int v13; // r14d
  __int64 v14; // r8
  __int64 *v15; // rcx
  unsigned int i; // r8d
  int v17; // eax
  __int16 v18; // r12
  int v19; // eax
  unsigned int v20; // r8d
  unsigned int v21; // r11d
  unsigned int v22; // esi
  int v23; // r12d
  unsigned int v24; // ebx
  __int64 v25; // rdx
  __int64 *v26; // rcx
  unsigned int j; // edx
  int v28; // eax
  int v29; // eax
  PSLIST_ENTRY v30; // rbx
  unsigned int v31; // r14d
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 Irp; // rax
  unsigned int v36; // eax
  int v37; // eax
  struct _SLIST_ENTRY *PoolWithTagPriority; // rax
  __int64 v39; // rbx
  unsigned int v40; // r8d
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // r15
  unsigned int v45; // r8d
  unsigned int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 (__fastcall *v52)(__int64, __int64, __int64, __int64); // rax
  int v53; // [rsp+30h] [rbp-58h]
  int v54; // [rsp+34h] [rbp-54h]
  __int64 v55; // [rsp+40h] [rbp-48h]
  __int16 v58; // [rsp+A8h] [rbp+20h]

  v3 = *(_QWORD *)(a1 + 136);
  v4 = a1;
  v5 = 0;
  v6 = a2;
  v7 = 5;
  v8 = 0;
  v53 = 5;
  v9 = *(_QWORD *)(v4 + 120);
  v10 = *(unsigned int *)(v4 + 132);
  v55 = *(_QWORD *)(v4 + 40);
  *a3 = 0;
  if ( v9 )
  {
    v11 = v9;
    v12 = v10 + 1;
  }
  else
  {
    v11 = 0;
    v12 = v10;
  }
  v13 = *(_DWORD *)(v4 + 128);
  if ( v12 < v13 )
  {
    while ( 1 )
    {
      v14 = v3 + 80LL * v12;
      switch ( *(_DWORD *)v14 )
      {
        case 1:
          v8 = *(unsigned int *)(v14 + 16);
          break;
        case 2:
          goto LABEL_49;
        case 3:
          v15 = *(__int64 **)(v14 + 8);
          for ( i = 0; v15; i += v17 )
          {
            v17 = *((_DWORD *)v15 + 10);
            v15 = (__int64 *)*v15;
          }
          v8 = i;
          break;
        case 4:
LABEL_49:
          v8 = *(_QWORD *)(v14 + 16);
          break;
      }
      if ( v8 + v11 < v11 )
        return 3221225621LL;
      ++v12;
      v11 += v8;
      if ( v12 >= v13 )
      {
        v7 = 5;
        break;
      }
    }
  }
  v18 = *(_WORD *)(v4 + 96) & 8;
  v58 = v18;
  if ( v18 )
  {
    if ( v11 >= (unsigned int)(2 * v6) )
    {
      v7 = 5;
      if ( v11 < (unsigned int)(3 * v6) )
        LODWORD(v11) = v11 - v6;
      else
        LODWORD(v11) = v6;
    }
    else
    {
      v7 = 5;
    }
  }
  else if ( v11 > v6 )
  {
    LODWORD(v11) = v6;
  }
  if ( !v9 )
  {
    v9 = 0;
    v21 = v11;
    v22 = 0;
    v20 = v10;
LABEL_20:
    v54 = 0;
    goto LABEL_21;
  }
  if ( v9 > (unsigned int)v11 )
    v19 = v11;
  else
    v19 = v9;
  v20 = v10 + 1;
  v21 = v11 - v19;
  v22 = 1;
  v7 = *(_DWORD *)(v3 + 80 * v10);
  v53 = v7;
  if ( v7 != 1 )
    goto LABEL_20;
  v37 = v11;
  if ( v9 <= (unsigned int)v11 )
    v37 = v9;
  v54 = v37;
LABEL_21:
  if ( v20 < v13 )
  {
    v23 = v54;
    do
    {
      v24 = v22;
      if ( v9 >= (unsigned int)v11 )
        break;
      v25 = v3 + 80LL * v20;
      switch ( *(_DWORD *)v25 )
      {
        case 1:
          v8 = *(unsigned int *)(v25 + 16);
          v36 = v21;
          if ( v8 <= v21 )
            v36 = *(_DWORD *)(v25 + 16);
          v23 += v36;
          if ( *(_DWORD *)(v25 + 16) )
            ++v22;
          v7 = 1;
          v53 = 1;
          break;
        case 2:
          v8 = *(_QWORD *)(v25 + 16);
          if ( v8 )
            ++v22;
          v7 = 2;
          v53 = 2;
          break;
        case 3:
          v26 = *(__int64 **)(v25 + 8);
          for ( j = 0; v26; j += v28 )
          {
            v28 = *((_DWORD *)v26 + 10);
            v26 = (__int64 *)*v26;
          }
          v8 = j;
          if ( v53 != 3 )
            ++v22;
          v7 = 3;
          v53 = 3;
          break;
        case 4:
          v8 = *(_QWORD *)(v25 + 16);
          ++v22;
          v7 = 4;
          v53 = 4;
          if ( !v8 )
            v22 = v24;
          break;
        default:
          v7 = v53;
          break;
      }
      v9 += v8;
      v29 = v21;
      if ( v8 <= v21 )
        v29 = v8;
      v21 -= v29;
      ++v20;
    }
    while ( v20 < v13 );
    v4 = a1;
    v54 = v23;
    v18 = v58;
  }
  if ( v22 > 0xFFFF )
    return 3221225621LL;
  if ( v7 == 3 && !v18 && v9 <= 0xFFFFFFFF && !*(_BYTE *)(*(_QWORD *)(v55 + 8) + 368LL) )
    LODWORD(v11) = v9;
  if ( v22 > 5 )
  {
    v31 = 144 * (unsigned __int16)v22 + 336;
    PoolWithTagPriority = (struct _SLIST_ENTRY *)ExAllocatePoolWithTagPriority(
                                                   (POOL_TYPE)512,
                                                   v31,
                                                   0x4B436C55u,
                                                   LowPoolPriority);
    v30 = PoolWithTagPriority;
    if ( PoolWithTagPriority )
    {
      HIDWORD(PoolWithTagPriority[1].Next) = 1;
LABEL_85:
      LODWORD(v30[1].Next) = 1262709845;
      goto LABEL_41;
    }
    return 3221225626LL;
  }
  v30 = *(PSLIST_ENTRY *)(v4 + 104);
  LOWORD(v22) = 5;
  v31 = UxTpChunkTrackerSize;
  if ( !v30 )
  {
    if ( UxCompactMode )
    {
      v39 = qword_1C0074150;
      v40 = KeGetCurrentNodeNumber() + 1;
      v41 = *(_DWORD *)v39 - 1;
      if ( v40 < *(_DWORD *)v39 )
        v41 = v40;
      v42 = v41;
      v43 = *(_QWORD *)(v39 + 32);
      v44 = *(_QWORD *)(v43 + 8 * v42);
      if ( !*(_BYTE *)(v44 + 112) )
        PplpLazyInitializeLookasideList(v39, *(_QWORD *)(v43 + 8 * v42));
      ++*(_DWORD *)(v44 + 20);
      v30 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v44);
      if ( v30 )
        goto LABEL_99;
    }
    else
    {
      v45 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v46 = *(_DWORD *)qword_1C0074150 - 1;
      if ( v45 < *(_DWORD *)qword_1C0074150 )
        v46 = v45;
      v47 = v46;
      v48 = *(_QWORD *)(qword_1C0074150 + 32);
      v44 = *(_QWORD *)(v48 + 8 * v47);
      if ( !*(_BYTE *)(v44 + 112) )
        PplpLazyInitializeLookasideList(qword_1C0074150, *(_QWORD *)(v48 + 8 * v47));
      ++*(_DWORD *)(v44 + 20);
      v30 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v44);
      if ( v30 )
      {
LABEL_99:
        if ( v30 )
        {
          HIDWORD(v30[1].Next) = 0;
          goto LABEL_85;
        }
        return 3221225626LL;
      }
    }
    v49 = *(unsigned int *)(v44 + 40);
    v50 = *(unsigned int *)(v44 + 44);
    v51 = *(unsigned int *)(v44 + 36);
    v52 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v44 + 48);
    ++*(_DWORD *)(v44 + 24);
    v30 = (PSLIST_ENTRY)v52(v51, v50, v49, v44);
    goto LABEL_99;
  }
  *(_QWORD *)(v4 + 104) = 0;
LABEL_41:
  memset(&v30[1].Next + 1, 0, v31 - 24LL);
  v30[17].Next = v30 + 21;
  v30[11].Next = v30 + 10;
  *((_DWORD *)&v30[16].Next + 2) = (unsigned __int16)v22;
  v32 = 0;
  v33 = (unsigned __int16)v22;
  do
  {
    v32 += 9;
    LODWORD(v30[17].Next[v32 - 9].Next) = 5;
    --v33;
  }
  while ( v33 );
  *((_DWORD *)&v30[8].Next + 2) = v54;
  *((_DWORD *)&v30[1].Next + 2) = v31;
  *((_DWORD *)&v30[16].Next + 3) = v11;
  v30[2].Next = (struct _SLIST_ENTRY *)v4;
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 20));
  v30[13].Next = 0;
  v30[14].Next = 0;
  v30[15].Next = 0;
  if ( HIDWORD(v30[1].Next) > 1 )
  {
LABEL_44:
    Irp = IoAllocateIrpEx(-1, *(unsigned __int8 *)(v4 + 98));
    *((_QWORD *)&v30[2].Next + 1) = Irp;
    if ( !Irp )
      v5 = -1073740696;
    goto LABEL_46;
  }
  v5 = PsChargeProcessPoolQuota(*(PEPROCESS *)(v4 + 48), (POOL_TYPE)512, v31);
  if ( v5 >= 0 )
  {
    LOBYTE(v30[16].Next) = 1;
    goto LABEL_44;
  }
LABEL_46:
  if ( v5 < 0 )
    UxpTpFreeChunkTracker(v30);
  else
    *a3 = v30;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1c000c7b0  mov     [rsp+arg_10], r8
0x1c000c7b5  mov     [rsp+arg_0], rcx
0x1c000c7ba  push    rbx
0x1c000c7bb  push    rbp
0x1c000c7bc  push    rdi
0x1c000c7bd  push    r13
0x1c000c7bf  push    r14
0x1c000c7c1  push    r15
0x1c000c7c3  sub     rsp, 58h
0x1c000c7c7  mov     r15, [rcx+88h]
0x1c000c7ce  mov     r13, rcx
0x1c000c7d1  xor     ebp, ebp
0x1c000c7d3  mov     r11d, edx
0x1c000c7d6  mov     ecx, 5
0x1c000c7db  mov     [rsp+88h+var_50], r15
0x1c000c7e0  mov     r9d, ebp
0x1c000c7e3  mov     [rsp+88h+var_58], ecx
0x1c000c7e7  mov     r10, [r13+78h]
0x1c000c7eb  mov     rax, [r13+28h]
0x1c000c7ef  mov     ebx, [r13+84h]
0x1c000c7f6  mov     [rsp+88h+var_48], rax
0x1c000c7fb  mov     [r8], rbp
0x1c000c7fe  test    r10, r10
0x1c000c801  jz      loc_1C0022836
0x1c000c807  mov     rdi, r10
0x1c000c80a  lea     edx, [rbx+1]
0x1c000c80d  mov     r14d, [r13+80h]
0x1c000c814  cmp     edx, r14d
0x1c000c817  jnb     short loc_1C000C87C
0x1c000c819  mov     eax, edx
0x1c000c81b  lea     r8, [rax+rax*4]
0x1c000c81f  shl     r8, 4
0x1c000c823  add     r8, r15
0x1c000c826  mov     ecx, [r8]
0x1c000c829  sub     ecx, 1
0x1c000c82c  jz      loc_1C000CAE3
0x1c000c832  sub     ecx, 1
0x1c000c835  jz      loc_1C000CAC1
0x1c000c83b  sub     ecx, 1
0x1c000c83e  jnz     loc_1C0022840
0x1c000c844  mov     rcx, [r8+8]
0x1c000c848  mov     r8, rbp
0x1c000c84b  test    rcx, rcx
0x1c000c84e  jz      short loc_1C000C85E
0x1c000c850  mov     eax, [rcx+28h]
0x1c000c853  mov     rcx, [rcx]
0x1c000c856  add     r8, rax
0x1c000c859  test    rcx, rcx
0x1c000c85c  jnz     short loc_1C000C850
0x1c000c85e  mov     r9d, r8d
0x1c000c861  lea     rax, [r9+rdi]
0x1c000c865  cmp     rax, rdi
0x1c000c868  jb      loc_1C002284E
0x1c000c86e  inc     edx
0x1c000c870  mov     rdi, rax
0x1c000c873  cmp     edx, r14d
0x1c000c876  jb      short loc_1C000C819
0x1c000c878  mov     ecx, [rsp+88h+var_58]
0x1c000c87c  mov     [rsp+88h+arg_8], rsi
0x1c000c884  mov     [rsp+88h+var_38], r12
0x1c000c889  movzx   r12d, word ptr [r13+60h]
0x1c000c88e  and     r12w, 8
0x1c000c893  mov     [rsp+88h+arg_18], r12w
0x1c000c89c  jnz     loc_1C0022858
0x1c000c8a2  cmp     rdi, r11
0x1c000c8a5  cmova   edi, r11d
0x1c000c8a9  test    r10, r10
0x1c000c8ac  jz      loc_1C00228A1
0x1c000c8b2  mov     edx, edi
0x1c000c8b4  cmp     r10, rdx
0x1c000c8b7  ja      loc_1C0022887
0x1c000c8bd  mov     rax, r10
0x1c000c8c0  lea     rcx, [rbx+rbx*4]
0x1c000c8c4  mov     r11d, edi
0x1c000c8c7  add     rcx, rcx
0x1c000c8ca  lea     r8d, [rbx+1]
0x1c000c8ce  sub     r11d, eax
0x1c000c8d1  mov     esi, 1
0x1c000c8d6  mov     ecx, [r15+rcx*8]
0x1c000c8da  mov     [rsp+88h+var_58], ecx
0x1c000c8de  cmp     ecx, esi
0x1c000c8e0  jz      loc_1C002288F
0x1c000c8e6  mov     [rsp+88h+var_54], ebp
0x1c000c8ea  cmp     r8d, r14d
0x1c000c8ed  jnb     loc_1C000C992
0x1c000c8f3  mov     r13, [rsp+88h+var_50]
0x1c000c8f8  mov     r12d, [rsp+88h+var_54]
0x1c000c8fd  mov     r15d, edi
0x1c000c900  mov     ebx, esi
0x1c000c902  cmp     r10, r15
0x1c000c905  jnb     short loc_1C000C97C
0x1c000c907  mov     eax, r8d
0x1c000c90a  lea     rdx, [rax+rax*4]
0x1c000c90e  shl     rdx, 4
0x1c000c912  add     rdx, r13
0x1c000c915  mov     ecx, [rdx]
0x1c000c917  sub     ecx, 1
0x1c000c91a  jz      loc_1C000CAEC
0x1c000c920  sub     ecx, 1
0x1c000c923  jz      loc_1C000CACA
0x1c000c929  sub     ecx, 1
0x1c000c92c  jnz     loc_1C00228B1
0x1c000c932  mov     rcx, [rdx+8]
0x1c000c936  mov     rdx, rbp
0x1c000c939  test    rcx, rcx
0x1c000c93c  jz      short loc_1C000C94C
0x1c000c93e  mov     eax, [rcx+28h]
0x1c000c941  mov     rcx, [rcx]
0x1c000c944  add     rdx, rax
0x1c000c947  test    rcx, rcx
0x1c000c94a  jnz     short loc_1C000C93E
0x1c000c94c  cmp     [rsp+88h+var_58], 3
0x1c000c951  mov     r9d, edx
0x1c000c954  jnz     loc_1C00228D0
0x1c000c95a  mov     ecx, 3
0x1c000c95f  mov     [rsp+88h+var_58], ecx
0x1c000c963  add     r10, r9
0x1c000c966  mov     eax, r11d
0x1c000c969  cmp     r9, rax
0x1c000c96c  ja      short loc_1C000C971
0x1c000c96e  mov     rax, r9
0x1c000c971  sub     r11d, eax
0x1c000c974  inc     r8d
0x1c000c977  cmp     r8d, r14d
0x1c000c97a  jb      short loc_1C000C900
0x1c000c97c  mov     r13, [rsp+88h+arg_0]
0x1c000c984  mov     [rsp+88h+var_54], r12d
0x1c000c989  movzx   r12d, [rsp+88h+arg_18]
0x1c000c992  cmp     esi, 0FFFFh
0x1c000c998  ja      loc_1C00228E0
0x1c000c99e  cmp     ecx, 3
0x1c000c9a1  jz      loc_1C000CB13
0x1c000c9a7  cmp     esi, 5
0x1c000c9aa  ja      loc_1C00228EA
0x1c000c9b0  mov     rbx, [r13+68h]
0x1c000c9b4  mov     esi, 5
0x1c000c9b9  mov     r14d, cs:UxTpChunkTrackerSize
0x1c000c9c0  test    rbx, rbx
0x1c000c9c3  jz      loc_1C0022938
0x1c000c9c9  mov     [r13+68h], rbp
0x1c000c9cd  mov     r12d, r14d
0x1c000c9d0  lea     rcx, [rbx+18h]; void *
0x1c000c9d4  xor     edx, edx; Val
0x1c000c9d6  lea     r8, [r12-18h]; Size
0x1c000c9db  call    memset
0x1c000c9e0  lea     rax, [rbx+150h]
0x1c000c9e7  movzx   ecx, si
0x1c000c9ea  mov     [rbx+110h], rax
0x1c000c9f1  lea     rax, [rbx+0A0h]
0x1c000c9f8  mov     [rbx+0B0h], rax
0x1c000c9ff  mov     [rbx+108h], ecx
0x1c000ca05  test    ecx, ecx
0x1c000ca07  jz      short loc_1C000CA2F
0x1c000ca09  mov     rax, rbp
0x1c000ca0c  mov     edx, ecx
0x1c000ca0e  xchg    ax, ax
0x1c000ca10  mov     rcx, [rbx+110h]
0x1c000ca17  lea     rax, [rax+90h]
0x1c000ca1e  mov     dword ptr [rax+rcx-90h], 5
0x1c000ca29  sub     rdx, 1
0x1c000ca2d  jnz     short loc_1C000CA10
0x1c000ca2f  mov     eax, [rsp+88h+var_54]
0x1c000ca33  mov     [rbx+88h], eax
0x1c000ca39  mov     [rbx+18h], r14d
0x1c000ca3d  mov     [rbx+10Ch], edi
0x1c000ca43  mov     [rbx+20h], r13
0x1c000ca47  lock inc dword ptr [r13+14h]
0x1c000ca4c  mov     [rbx+0D0h], rbp
0x1c000ca53  mov     [rbx+0E0h], rbp
0x1c000ca5a  mov     [rbx+0F0h], rbp
0x1c000ca61  cmp     dword ptr [rbx+14h], 1
0x1c000ca65  jbe     loc_1C0022A28
0x1c000ca6b  movzx   edx, byte ptr [r13+62h]
0x1c000ca70  xor     r8d, r8d
0x1c000ca73  lea     rcx, [r8-1]
0x1c000ca77  call    cs:__imp_IoAllocateIrpEx
0x1c000ca7e  nop     dword ptr [rax+rax+00h]
0x1c000ca83  mov     [rbx+28h], rax
0x1c000ca87  test    rax, rax
0x1c000ca8a  jz      loc_1C0022A56
0x1c000ca90  test    ebp, ebp
0x1c000ca92  js      loc_1C0022A60
0x1c000ca98  mov     rax, [rsp+88h+arg_10]
0x1c000caa0  mov     [rax], rbx
0x1c000caa3  mov     eax, ebp
0x1c000caa5  mov     rsi, [rsp+88h+arg_8]
0x1c000caad  mov     r12, [rsp+88h+var_38]
0x1c000cab2  add     rsp, 58h
0x1c000cab6  pop     r15
0x1c000cab8  pop     r14
0x1c000caba  pop     r13
0x1c000cabc  pop     rdi
0x1c000cabd  pop     rbp
0x1c000cabe  pop     rbx
0x1c000cabf  retn
0x1c000cac1  mov     r9, [r8+10h]
0x1c000cac5  jmp     loc_1C000C861
0x1c000caca  mov     r9, [rdx+10h]
0x1c000cace  test    r9, r9
0x1c000cad1  jz      short loc_1C000CAD5
0x1c000cad3  inc     esi
0x1c000cad5  mov     ecx, 2
0x1c000cada  mov     [rsp+88h+var_58], ecx
0x1c000cade  jmp     loc_1C000C963
0x1c000cae3  mov     r9d, [r8+10h]
0x1c000cae7  jmp     loc_1C000C861
0x1c000caec  mov     r9d, [rdx+10h]
0x1c000caf0  mov     eax, r11d
0x1c000caf3  cmp     r9, rax
0x1c000caf6  ja      short loc_1C000CAFB
0x1c000caf8  mov     eax, r9d
0x1c000cafb  add     r12d, eax
0x1c000cafe  test    r9, r9
0x1c000cb01  jz      short loc_1C000CB05
0x1c000cb03  inc     esi
0x1c000cb05  mov     ecx, 1
0x1c000cb0a  mov     [rsp+88h+var_58], ecx
0x1c000cb0e  jmp     loc_1C000C963
0x1c000cb13  cmp     bp, r12w
0x1c000cb17  jnz     loc_1C000C9A7
0x1c000cb1d  mov     eax, 0FFFFFFFFh
0x1c000cb22  cmp     r10, rax
0x1c000cb25  ja      loc_1C000C9A7
0x1c000cb2b  mov     rax, [rsp+88h+var_48]
0x1c000cb30  mov     rax, [rax+8]
0x1c000cb34  cmp     [rax+170h], bpl
0x1c000cb3b  jnz     loc_1C000C9A7
0x1c000cb41  mov     edi, r10d
0x1c000cb44  jmp     loc_1C000C9A7
0x1c0022836  mov     rdi, rbp
0x1c0022839  mov     edx, ebx
0x1c002283b  jmp     loc_1C000C80D
0x1c0022840  cmp     ecx, 1
0x1c0022843  jnz     loc_1C000C861
0x1c0022849  jmp     loc_1C000CAC1
0x1c002284e  mov     eax, 0C0000095h
0x1c0022853  jmp     loc_1C000CAB2
0x1c0022858  lea     ecx, [r11+r11]
0x1c002285c  cmp     rdi, rcx
0x1c002285f  jnb     short loc_1C002286A
0x1c0022861  mov     ecx, [rsp+88h+var_58]
0x1c0022865  jmp     loc_1C000C8A9
0x1c002286a  lea     ecx, [r11+r11*2]
0x1c002286e  cmp     rdi, rcx
0x1c0022871  mov     ecx, [rsp+88h+var_58]
0x1c0022875  jb      short loc_1C002287F
0x1c0022877  mov     edi, r11d
0x1c002287a  jmp     loc_1C000C8A9
0x1c002287f  sub     edi, r11d
0x1c0022882  jmp     loc_1C000C8A9
0x1c0022887  mov     rax, rdx
0x1c002288a  jmp     loc_1C000C8C0
0x1c002288f  cmp     r10, rdx
0x1c0022892  mov     eax, edi
0x1c0022894  cmovbe  eax, r10d
0x1c0022898  mov     [rsp+88h+var_54], eax
0x1c002289c  jmp     loc_1C000C8EA
0x1c00228a1  mov     r10, rbp
0x1c00228a4  mov     r11d, edi
0x1c00228a7  mov     esi, ebp
0x1c00228a9  mov     r8d, ebx
0x1c00228ac  jmp     loc_1C000C8E6
0x1c00228b1  cmp     ecx, 1
0x1c00228b4  jnz     short loc_1C00228D7
0x1c00228b6  mov     r9, [rdx+10h]
0x1c00228ba  inc     esi
0x1c00228bc  test    r9, r9
0x1c00228bf  mov     ecx, 4
0x1c00228c4  mov     [rsp+88h+var_58], ecx
0x1c00228c8  cmovz   esi, ebx
0x1c00228cb  jmp     loc_1C000C963
0x1c00228d0  inc     esi
0x1c00228d2  jmp     loc_1C000C95A
0x1c00228d7  mov     ecx, [rsp+88h+var_58]
0x1c00228db  jmp     loc_1C000C963
0x1c00228e0  mov     eax, 0C0000095h
0x1c00228e5  jmp     loc_1C000CAA5
0x1c00228ea  movzx   eax, si
0x1c00228ed  xor     r9d, r9d; Priority
0x1c00228f0  mov     ecx, 200h; PoolType
0x1c00228f5  mov     r8d, 4B436C55h; Tag
0x1c00228fb  lea     r14d, [rax+rax*8]
0x1c00228ff  shl     r14d, 4
0x1c0022903  add     r14d, 150h
0x1c002290a  mov     edx, r14d; NumberOfBytes
0x1c002290d  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c0022914  nop     dword ptr [rax+rax+00h]
0x1c0022919  mov     rbx, rax
0x1c002291c  test    rax, rax
0x1c002291f  jz      loc_1C0022A1E
0x1c0022925  mov     dword ptr [rax+14h], 1
0x1c002292c  mov     dword ptr [rbx+10h], 4B436C55h
0x1c0022933  jmp     loc_1C000C9CD
0x1c0022938  cmp     cs:UxCompactMode, bpl
0x1c002293f  jz      short loc_1C002299F
0x1c0022941  mov     rbx, cs:qword_1C0074150
0x1c0022948  call    cs:__imp_KeGetCurrentNodeNumber
0x1c002294f  nop     dword ptr [rax+rax+00h]
0x1c0022954  mov     edx, [rbx]
0x1c0022956  movzx   r8d, ax
  ... truncated ...
```
