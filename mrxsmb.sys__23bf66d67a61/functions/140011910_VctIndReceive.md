# VctIndReceive

- ea: `0x140011910`
- end: `0x140012183`
- name: `VctIndReceive`
- size: `2163`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a950`

## callees

- `0x140006ec0`
- `0x14000c270`
- `0x140011910`
- `0x140020e90`
- `0x1400215b0`
- `0x140028230`
- `0x140028960`
- `0x140028a84`
- `0x14002d320`
- `0x140037fa4`
- `0x14003822c`
- `0x1400383d0`
- `0x140039fa8`
- `0x14003e14c`
- `0x1400420b8`
- `0x140042a00`
- `0x140042e0c`
- `0x140059dc0`
- `0x140059f00`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011cd7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011cfd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011d23`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011d46`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011d69`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011cd7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011cfd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011d23`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011d46`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011d69`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140011dfb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140011dfb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011b23`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011b23`
- `ntoskrnl!ExAllocatePool2` at `0x140011add`
- `ntoskrnl!ExAllocatePool2` at `0x140011d8a`
- `ntoskrnl!ExAllocatePool2` at `0x140011add`
- `ntoskrnl!ExAllocatePool2` at `0x140011d8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f85`
- `rdbss!RxFreeMdl` at `0x140011ca5`
- `rdbss!RxFreeMdl` at `0x140011ca5`
- `rdbss!RxAllocateMdl2` at `0x140011dc8`
- `rdbss!RxAllocateMdl2` at `0x140011dc8`

## pseudocode

```c
__int64 __fastcall VctIndReceive(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7,
        struct _MDL *a8,
        struct _MDL **a9,
        _DWORD *a10)
{
  unsigned int v10; // r13d
  unsigned int v11; // r12d
  __int64 v12; // rbx
  __int64 v13; // r14
  struct _MDL *p_P; // rsi
  int v15; // r15d
  unsigned int v16; // eax
  PVOID *p_MappedSystemVa; // rdi
  __int64 v18; // rcx
  int v19; // eax
  int v20; // ebx
  ULONG ByteCount; // ecx
  unsigned int v22; // eax
  unsigned int v23; // ebx
  struct _MDL *v24; // r14
  ULONG v25; // esi
  char *v26; // r13
  PVOID MappedSystemVa; // rax
  unsigned int v28; // edi
  ULONG v29; // edi
  unsigned int v30; // ecx
  int v31; // ebx
  __int64 v32; // rcx
  __int64 v33; // rax
  struct _MDL *Next; // rcx
  __int64 v35; // rdi
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rdx
  struct _MDL *Mdl2; // rax
  struct _MDL *v41; // rdi
  ULONG *p_ByteOffset; // rdi
  ULONG *v43; // rbx
  ULONG v44; // ecx
  __int64 result; // rax
  struct _MDL *v46; // rbx
  struct _MDL *v47; // rdx
  struct _MDL *v48; // r9
  unsigned int v49; // r10d
  ULONG v50; // ecx
  ULONG v51; // r10d
  char P; // [rsp+30h] [rbp-40h] BYREF
  __int64 v53; // [rsp+38h] [rbp-38h]
  __int64 v54; // [rsp+40h] [rbp-30h]
  __int64 v55; // [rsp+48h] [rbp-28h]
  __int64 v56; // [rsp+50h] [rbp-20h]
  __int64 v57; // [rsp+58h] [rbp-18h]
  __int64 v58; // [rsp+60h] [rbp-10h]
  __int64 v59; // [rsp+68h] [rbp-8h]
  char v60; // [rsp+70h] [rbp+0h]
  int v61; // [rsp+74h] [rbp+4h]
  unsigned int v62; // [rsp+78h] [rbp+8h] BYREF
  __int64 v63; // [rsp+80h] [rbp+10h]
  struct _MDL *Pool2; // [rsp+88h] [rbp+18h] BYREF
  struct _MDL *v65; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v66; // [rsp+9Ch] [rbp+2Ch]
  __int64 v67; // [rsp+A8h] [rbp+38h]

  v67 = a2;
  v10 = a4;
  v63 = a1;
  v11 = a3;
  v12 = a2;
  v13 = a1;
  if ( a3 == a4 )
  {
    p_P = (struct _MDL *)&P;
    Pool2 = (struct _MDL *)&P;
    v15 = 0;
    v60 = 1;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
  }
  else
  {
    v15 = 0;
    v60 = 0;
    p_P = (struct _MDL *)_InterlockedExchange64((volatile __int64 *)(a1 + 480), 0);
    Pool2 = p_P;
    if ( !p_P )
    {
      Pool2 = (struct _MDL *)ExAllocatePool2(64, 64, 1834173266);
      p_P = Pool2;
      if ( !Pool2 )
      {
        v28 = 401;
        v20 = -1073741670;
LABEL_103:
        if ( (unsigned int)VctSetEndpointState(v13, 1, 0) != 1 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) )
              WPP_SF_qDD(
                WPP_GLOBAL_Control->AttachedDevice,
                17,
                WPP_39c16dc859303064795977fd63584161_Traceguids,
                v13,
                v20,
                v28);
          }
          VctIndDisconnect(v13, ((unsigned __int64)v28 << 32) | 0xC000020C);
        }
        return 0;
      }
    }
  }
  v61 = 0;
  HIDWORD(p_P->Next) = v10;
  LODWORD(p_P->Next) = v10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_39c16dc859303064795977fd63584161_Traceguids, v13, v11, v10);
  }
  if ( v11 )
  {
    v16 = 256;
    if ( v10 <= 0x100 )
      v16 = v10;
    while ( 1 )
    {
      if ( v11 < v16 )
      {
        v13 = v63;
        break;
      }
      p_MappedSystemVa = &p_P->MappedSystemVa;
      p_P->ByteCount = 0;
      p_P->StartVa = 0;
      v18 = v63;
      v62 = 0;
      p_P->MappedSystemVa = 0;
      *(_DWORD *)(&p_P->MdlFlags + 1) = 0;
      v19 = SmbCeReceiveInd(
              v18,
              v11,
              v10,
              a5,
              &v62,
              a7,
              (_QWORD **)&p_P->MappedSystemVa,
              &p_P->StartVa,
              &p_P->ByteCount,
              v12);
      v20 = v19;
      if ( v19 == -1073741802 )
      {
        ByteCount = p_P->ByteCount;
        v22 = v62;
        v23 = ByteCount + v62;
        a2 = HIDWORD(p_P->Next) - (ByteCount + v62);
        LODWORD(v65) = ByteCount + v62;
        v10 -= ByteCount + v62;
        HIDWORD(p_P->Next) = a2;
        v66 = v10;
        if ( v23 > v11 )
        {
          if ( v22 > v11 )
          {
            *(_DWORD *)(&p_P->MdlFlags + 1) = v22 - v11;
            v22 = v11;
            v62 = v11;
          }
          v31 = v22 + v61;
          v61 += v22;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          {
            v13 = v63;
          }
          else
          {
            v13 = v63;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_qDqDD(
                WPP_GLOBAL_Control->AttachedDevice,
                a2,
                WPP_GLOBAL_Control,
                v63,
                v31,
                *p_MappedSystemVa,
                ByteCount,
                a2);
          }
          break;
        }
        v61 += v23;
        v11 -= v23;
        v24 = (struct _MDL *)*p_MappedSystemVa;
        if ( ByteCount )
        {
          v25 = ByteCount;
          v26 = (char *)(a7 + v22);
          do
          {
            if ( (v24->MdlFlags & 5) != 0 )
              MappedSystemVa = v24->MappedSystemVa;
            else
              MappedSystemVa = MmMapLockedPagesSpecifyCache(v24, 0, MmCached, 0, 0, 0x40000010u);
            if ( !MappedSystemVa )
              break;
            v29 = v25;
            if ( v24->ByteCount < v25 )
              v29 = v24->ByteCount;
            memmove(MappedSystemVa, v26, v29);
            v24 = v24->Next;
            v26 += v29;
            v25 -= v29;
          }
          while ( v25 );
          p_P = Pool2;
          v10 = v66;
          v23 = (unsigned int)v65;
        }
        v13 = v63;
        a7 += v23;
        SmbCeDataReadyInd(v63, p_P->StartVa, p_P->ByteCount, 0);
      }
      else
      {
        if ( v19 )
        {
          v28 = 403;
          goto LABEL_94;
        }
        v30 = v62;
        v10 -= v62;
        HIDWORD(p_P->Next) -= v62;
        if ( v30 > v11 )
        {
          *(_DWORD *)(&p_P->MdlFlags + 1) = v30 - v11;
          v30 = v11;
          v62 = v11;
          v11 = 0;
        }
        else
        {
          v11 -= v30;
        }
        p_P->StartVa = 0;
        v61 += v30;
        a7 += v30;
        v13 = v63;
        *p_MappedSystemVa = 0;
        p_P->ByteCount = 0;
      }
      v16 = v10;
      if ( v10 > 0x100 )
        v16 = 256;
      if ( !v11 )
        break;
      v12 = v67;
    }
  }
  if ( v10 )
  {
    v32 = *(_QWORD *)&p_P[1].Size;
    if ( v32 )
    {
      v33 = *(_QWORD *)&p_P[1].Size & 7LL;
      if ( (unsigned int)v33 > 4 || v10 > *((_DWORD *)qword_140065880 + v33) )
      {
        SmbMmFreeSmbBuffer(v32, 1834176598);
        Next = p_P[1].Next;
        *(_QWORD *)&p_P[1].Size = 0;
        RxFreeMdl(Next);
        p_P[1].Next = 0;
        p_P->ByteOffset = 0;
      }
    }
    if ( !*(_QWORD *)&p_P[1].Size )
    {
      if ( v10 > 0x4000 )
      {
        if ( v10 > 0x9000 )
        {
          if ( v10 > 0x11000 )
          {
            if ( v10 > 0x101000 )
            {
              if ( v10 > 0x801000 )
              {
                v35 = 5;
                v36 = ExAllocatePool2(66, v10, 1834176598);
              }
              else
              {
                v35 = 4;
                v36 = (__int64)ExAllocateFromNPagedLookasideList(&stru_140070840);
              }
            }
            else
            {
              v35 = 3;
              v36 = (__int64)ExAllocateFromNPagedLookasideList(&stru_1400707C0);
            }
          }
          else
          {
            v35 = 2;
            v36 = (__int64)ExAllocateFromNPagedLookasideList(&stru_140070740);
          }
        }
        else
        {
          v35 = 1;
          v36 = (__int64)ExAllocateFromNPagedLookasideList(&Lookaside);
        }
      }
      else
      {
        v35 = 0;
        v36 = (__int64)ExAllocateFromNPagedLookasideList(&SmbBufferLookasideList);
      }
      if ( !v36 )
        goto LABEL_68;
      v37 = v35 | v36;
      v38 = ((unsigned __int8)v35 | (unsigned __int8)v36) & 7;
      if ( (unsigned int)v38 > 4 || (v39 = *((unsigned int *)qword_140065880 + v38), !(_DWORD)v39) )
        v39 = v10;
      Mdl2 = (struct _MDL *)RxAllocateMdl2(v37 & 0xFFFFFFFFFFFFFFF8uLL, v39, 0, 0, 0);
      v41 = Mdl2;
      if ( !Mdl2 )
      {
        SmbMmFreeSmbBuffer(v37, 1834176598);
LABEL_68:
        v20 = -1073741670;
        v28 = 404;
        goto LABEL_94;
      }
      MmBuildMdlForNonPagedPool(Mdl2);
      *(_QWORD *)&p_P[1].Size = v37;
      p_P[1].Next = v41;
    }
    p_ByteOffset = &p_P->ByteOffset;
    p_P->ByteOffset = v10;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_39c16dc859303064795977fd63584161_Traceguids,
        p_P[1].Next,
        v10);
    }
    HIDWORD(p_P->Next) = 0;
  }
  else
  {
    p_ByteOffset = &p_P->ByteOffset;
  }
  if ( *(_DWORD *)(&p_P->MdlFlags + 1) || p_P->ByteCount )
  {
    v43 = p_ByteOffset;
  }
  else
  {
    v43 = &p_P->ByteOffset;
    if ( !p_P->ByteOffset )
    {
      v28 = 0;
      v20 = 0;
      *a6 = p_P->Next;
      goto LABEL_94;
    }
  }
  if ( !(unsigned __int8)VctReferenceEndpointSafe(v13, a2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_39c16dc859303064795977fd63584161_Traceguids, v13);
    }
    v28 = 405;
    v20 = -1073741300;
    goto LABEL_94;
  }
  v44 = *(_DWORD *)(&p_P->MdlFlags + 1);
  if ( v44 )
  {
    Pool2 = 0;
    v65 = 0;
    v20 = SmbMmAllocateTrashMdl(v44, &Pool2, &v65);
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_39c16dc859303064795977fd63584161_Traceguids);
      }
      v28 = 402;
LABEL_94:
      if ( v60 )
      {
        v13 = v63;
      }
      else
      {
        *(_OWORD *)&p_P->Next = 0;
        *(_OWORD *)&p_P->Process = 0;
        *(_OWORD *)&p_P->StartVa = 0;
        if ( *(_QWORD *)&p_P[1].Size && (unsigned int)SmbMmGetMaxBufferLength() > 0x11000 )
          VctTeardownReceiveContext(p_P);
        v13 = v63;
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v63 + 480), (signed __int64)p_P, 0) )
        {
          VctTeardownReceiveContext(p_P);
          ExFreePoolWithTag(p_P, 0x6D534352u);
        }
      }
      if ( (int)(v20 + 0x80000000) < 0 || v20 == -1073741802 )
        return (unsigned int)v20;
      goto LABEL_103;
    }
    v46 = Pool2;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_39c16dc859303064795977fd63584161_Traceguids,
        p_P,
        Pool2,
        *(_DWORD *)(&p_P->MdlFlags + 1));
    }
    v47 = v65;
    p_P->Process = (struct _EPROCESS *)v46;
    a8->Next = v46;
  }
  else
  {
    v47 = a8;
    p_ByteOffset = v43;
  }
  if ( p_P->ByteCount )
  {
    v47->Next = (struct _MDL *)p_P->MappedSystemVa;
    if ( *p_ByteOffset )
    {
      v48 = (struct _MDL *)p_P->MappedSystemVa;
      if ( v48 )
      {
        v49 = p_P->ByteCount;
        while ( 1 )
        {
          v50 = v48->ByteCount;
          if ( v50 + v15 >= v49 )
            break;
          v48 = v48->Next;
          v15 += v50;
          if ( !v48 )
            goto LABEL_129;
        }
        *(_DWORD *)&p_P->Size = v50;
        v51 = v49 - v15;
        p_P[1].Next->Next = v48->Next;
        v48->ByteCount = v51;
        v48->Next = p_P[1].Next;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qDDqq(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            (unsigned int)WPP_39c16dc859303064795977fd63584161_Traceguids,
            (_DWORD)v48,
            *(_DWORD *)&p_P->Size,
            v51,
            (char)p_P[1].Next,
            (char)p_P[1].Next->Next);
        }
      }
    }
  }
  else
  {
    v47->Next = p_P[1].Next;
  }
LABEL_129:
  result = 3221225494LL;
  *a10 = *(_DWORD *)(&p_P->MdlFlags + 1) + p_P->ByteCount + *p_ByteOffset;
  *a6 = v61;
  *a9 = p_P;
  return result;
}

```

## disassembly

```asm
0x140011910  push    rbp
0x140011912  push    rbx
0x140011913  push    rsi
0x140011914  push    rdi
0x140011915  push    r12
0x140011917  push    r13
0x140011919  push    r14
0x14001191b  push    r15
0x14001191d  sub     rsp, 0A8h
0x140011924  lea     rbp, [rsp+50h]
0x140011929  mov     rax, cs:__security_cookie
0x140011930  xor     rax, rbp
0x140011933  mov     [rbp+90h+var_50], rax
0x140011937  mov     [rbp+90h+var_58], rdx
0x14001193b  mov     r13d, r9d
0x14001193e  mov     [rbp+90h+var_80], rcx
0x140011942  mov     r12d, r8d
0x140011945  lea     rdi, WPP_GLOBAL_Control
0x14001194c  mov     rbx, rdx
0x14001194f  mov     r14, rcx
0x140011952  cmp     r8d, r9d
0x140011955  jnz     loc_140011AB2
0x14001195b  mov     eax, dword ptr [rsp+0E0h+var_E0]
0x14001195e  sub     rsp, 40h
0x140011962  lea     rsi, [rsp+120h+P]
0x140011967  mov     eax, [rsi]
0x140011969  mov     [rbp+90h+var_78], rsi
0x14001196d  xor     r15d, r15d
0x140011970  mov     [rbp+90h+var_90], 1
0x140011974  mov     [rsi+8], r15
0x140011978  mov     [rsi+10h], r15
0x14001197c  mov     [rsi+18h], r15
0x140011980  mov     [rsi+20h], r15
0x140011984  mov     [rsi+28h], r15
0x140011988  mov     [rsi+30h], r15
0x14001198c  mov     [rsi+38h], r15
0x140011990  mov     [rbp+90h+var_8C], r15d
0x140011994  mov     [rsi+4], r13d
0x140011998  mov     [rsi], r13d
0x14001199b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400119a2  cmp     rcx, rdi
0x1400119a5  jz      short loc_1400119D6
0x1400119a7  mov     eax, [rcx+2Ch]
0x1400119aa  test    al, 4
0x1400119ac  jz      short loc_1400119D6
0x1400119ae  cmp     byte ptr [rcx+29h], 4
0x1400119b2  jb      short loc_1400119D6
0x1400119b4  mov     rcx, [rcx+18h]
0x1400119b8  lea     r8, WPP_39c16dc859303064795977fd63584161_Traceguids
0x1400119bf  mov     edx, 0Bh
0x1400119c4  mov     [rsp+120h+Priority], r13d
0x1400119c9  mov     r9, r14
0x1400119cc  mov     [rsp+120h+BugCheckOnFailure], r12d
0x1400119d1  call    WPP_SF_qDD
0x1400119d6  test    r12d, r12d
0x1400119d9  jz      loc_140011C63
0x1400119df  mov     eax, 100h
0x1400119e4  cmp     r13d, eax
0x1400119e7  cmovbe  eax, r13d
0x1400119eb  nop     dword ptr [rax+rax+00h]
0x1400119f0  cmp     r12d, eax
0x1400119f3  jb      loc_140011C5F
0x1400119f9  mov     r14, [rbp+90h+arg_30]
0x140011a00  lea     rax, [rsi+28h]
0x140011a04  mov     r9, [rbp+90h+arg_20]
0x140011a0b  lea     rcx, [rsi+20h]
0x140011a0f  mov     [rsp+120h+var_D8], rbx
0x140011a14  lea     rdi, [rsi+18h]
0x140011a18  mov     [rsp+120h+var_E0], rax
0x140011a1d  mov     r8d, r13d
0x140011a20  mov     [rsp+120h+var_E8], rcx
0x140011a25  mov     edx, r12d
0x140011a28  mov     [rax], r15d
0x140011a2b  lea     rax, [rbp+90h+var_88]
0x140011a2f  mov     [rsp+120h+var_F0], rdi
0x140011a34  mov     [rcx], r15
0x140011a37  mov     rcx, [rbp+90h+var_80]
0x140011a3b  mov     qword ptr [rsp+120h+Priority], r14
0x140011a40  mov     qword ptr [rsp+120h+BugCheckOnFailure], rax
0x140011a45  mov     [rbp+90h+var_88], r15d
0x140011a49  mov     [rdi], r15
0x140011a4c  mov     [rsi+0Ch], r15d
0x140011a50  call    SmbCeReceiveInd
0x140011a55  mov     ebx, eax
0x140011a57  cmp     eax, 0C0000016h
0x140011a5c  jnz     loc_140011B8A
0x140011a62  mov     edx, [rsi+4]
0x140011a65  mov     ecx, [rsi+28h]
0x140011a68  mov     eax, [rbp+90h+var_88]
0x140011a6b  lea     ebx, [rcx+rax]
0x140011a6e  sub     edx, ebx
0x140011a70  mov     dword ptr [rbp+90h+var_70], ebx
0x140011a73  sub     r13d, ebx
0x140011a76  mov     [rsi+4], edx
0x140011a79  mov     [rbp+90h+var_64], r13d
0x140011a7d  cmp     ebx, r12d
0x140011a80  ja      loc_140011BEE
0x140011a86  add     [rbp+90h+var_8C], ebx
0x140011a89  mov     edx, eax
0x140011a8b  add     rdx, [rbp+90h+arg_30]
0x140011a92  sub     r12d, ebx
0x140011a95  mov     r14, [rdi]
0x140011a98  test    ecx, ecx
0x140011a9a  jz      loc_140011B68
0x140011aa0  mov     esi, ecx
0x140011aa2  mov     r13, rdx
0x140011aa5  test    byte ptr [r14+0Ah], 5
0x140011aaa  jz      short loc_140011B08
0x140011aac  mov     rax, [r14+18h]
0x140011ab0  jmp     short loc_140011B2F
0x140011ab2  xor     r15d, r15d
0x140011ab5  mov     [rbp+90h+var_90], 0
0x140011ab9  mov     esi, r15d
0x140011abc  xchg    rsi, [rcx+1E0h]
0x140011ac3  mov     [rbp+90h+var_78], rsi
0x140011ac7  test    rsi, rsi
0x140011aca  jnz     loc_140011990
0x140011ad0  mov     edx, 40h ; '@'
0x140011ad5  mov     r8d, 6D534352h
0x140011adb  mov     ecx, edx
0x140011add  call    cs:__imp_ExAllocatePool2
0x140011ae4  nop     dword ptr [rax+rax+00h]
0x140011ae9  mov     [rbp+90h+var_78], rax
0x140011aed  mov     rsi, rax
0x140011af0  test    rax, rax
0x140011af3  jnz     loc_140011990
0x140011af9  mov     edi, 191h
0x140011afe  mov     ebx, 0C000009Ah
0x140011b03  jmp     loc_140011FAB
0x140011b08  mov     [rsp+120h+Priority], 40000010h; Priority
0x140011b10  xor     r9d, r9d; RequestedAddress
0x140011b13  xor     edx, edx; AccessMode
0x140011b15  mov     [rsp+120h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x140011b1a  mov     r8d, 1; CacheType
0x140011b20  mov     rcx, r14; MemoryDescriptorList
0x140011b23  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140011b2a  nop     dword ptr [rax+rax+00h]
0x140011b2f  test    rax, rax
0x140011b32  jz      short loc_140011B5D
0x140011b34  mov     ecx, [r14+28h]
0x140011b38  mov     edi, esi
0x140011b3a  cmp     ecx, esi
0x140011b3c  mov     rdx, r13; Src
0x140011b3f  cmovb   edi, ecx
0x140011b42  mov     rcx, rax; void *
0x140011b45  mov     r8d, edi; Size
0x140011b48  mov     ebx, edi
0x140011b4a  call    memmove
0x140011b4f  mov     r14, [r14]
0x140011b52  add     r13, rbx
0x140011b55  sub     esi, edi
0x140011b57  jnz     loc_140011AA5
0x140011b5d  mov     rsi, [rbp+90h+var_78]
0x140011b61  mov     r13d, [rbp+90h+var_64]
0x140011b65  mov     ebx, dword ptr [rbp+90h+var_70]
0x140011b68  mov     r14, [rbp+90h+var_80]
0x140011b6c  xor     r9d, r9d
0x140011b6f  mov     r8d, [rsi+28h]
0x140011b73  mov     rcx, r14
0x140011b76  mov     rdx, [rsi+20h]
0x140011b7a  mov     eax, ebx
0x140011b7c  add     [rbp+90h+arg_30], rax
0x140011b83  call    SmbCeDataReadyInd
0x140011b88  jmp     short loc_140011BD2
0x140011b8a  test    eax, eax
0x140011b8c  jnz     loc_140011C4F
0x140011b92  mov     ecx, [rbp+90h+var_88]
0x140011b95  sub     r13d, ecx
0x140011b98  sub     [rsi+4], ecx
0x140011b9b  cmp     ecx, r12d
0x140011b9e  ja      short loc_140011BA5
0x140011ba0  sub     r12d, ecx
0x140011ba3  jmp     short loc_140011BB4
0x140011ba5  sub     ecx, r12d
0x140011ba8  mov     [rsi+0Ch], ecx
0x140011bab  mov     ecx, r12d
0x140011bae  mov     [rbp+90h+var_88], ecx
0x140011bb1  mov     r12d, r15d
0x140011bb4  mov     eax, ecx
0x140011bb6  add     r14, rax
0x140011bb9  mov     [rsi+20h], r15
0x140011bbd  add     [rbp+90h+var_8C], ecx
0x140011bc0  mov     [rbp+90h+arg_30], r14
0x140011bc7  mov     r14, [rbp+90h+var_80]
0x140011bcb  mov     [rdi], r15
0x140011bce  mov     [rsi+28h], r15d
0x140011bd2  mov     ecx, 100h
0x140011bd7  mov     eax, r13d
0x140011bda  cmp     r13d, ecx
0x140011bdd  cmova   eax, ecx
0x140011be0  test    r12d, r12d
0x140011be3  jz      short loc_140011C63
0x140011be5  mov     rbx, [rbp+90h+var_58]
0x140011be9  jmp     loc_1400119F0
0x140011bee  cmp     eax, r12d
0x140011bf1  jbe     short loc_140011BFF
0x140011bf3  sub     eax, r12d
0x140011bf6  mov     [rsi+0Ch], eax
0x140011bf9  mov     eax, r12d
0x140011bfc  mov     [rbp+90h+var_88], eax
0x140011bff  mov     ebx, [rbp+90h+var_8C]
0x140011c02  add     ebx, eax
0x140011c04  mov     [rbp+90h+var_8C], ebx
0x140011c07  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140011c0e  lea     r12, WPP_GLOBAL_Control
0x140011c15  cmp     r8, r12
0x140011c18  jz      short loc_140011C59
0x140011c1a  mov     eax, [r8+2Ch]
0x140011c1e  test    al, 4
0x140011c20  jz      short loc_140011C59
0x140011c22  cmp     byte ptr [r8+29h], 4
0x140011c27  mov     r14, [rbp+90h+var_80]
0x140011c2b  jb      short loc_140011C6A
0x140011c2d  mov     rax, [rdi]
0x140011c30  mov     r9, r14
0x140011c33  mov     dword ptr [rsp+120h+var_E8], edx
0x140011c37  mov     dword ptr [rsp+120h+var_F0], ecx
0x140011c3b  mov     rcx, [r8+18h]
0x140011c3f  mov     qword ptr [rsp+120h+Priority], rax
0x140011c44  mov     [rsp+120h+BugCheckOnFailure], ebx
0x140011c48  call    WPP_SF_qDqDD
0x140011c4d  jmp     short loc_140011C6A
0x140011c4f  mov     edi, 193h
0x140011c54  jmp     loc_140011F33
0x140011c59  mov     r14, [rbp+90h+var_80]
0x140011c5d  jmp     short loc_140011C6A
0x140011c5f  mov     r14, [rbp+90h+var_80]
0x140011c63  lea     r12, WPP_GLOBAL_Control
0x140011c6a  test    r13d, r13d
0x140011c6d  jz      loc_140011E5A
0x140011c73  mov     rcx, [rsi+38h]
0x140011c77  lea     r12, qword_140065880
0x140011c7e  test    rcx, rcx
0x140011c81  jz      short loc_140011CB9
0x140011c83  mov     eax, ecx
0x140011c85  and     eax, 7
0x140011c88  cmp     eax, 4
0x140011c8b  ja      short loc_140011C93
0x140011c8d  cmp     r13d, [r12+rax*4]
0x140011c91  jbe     short loc_140011CB9
0x140011c93  mov     edx, 6D535056h
0x140011c98  call    SmbMmFreeSmbBuffer
0x140011c9d  mov     rcx, [rsi+30h]
0x140011ca1  mov     [rsi+38h], r15
0x140011ca5  call    cs:__imp_RxFreeMdl
0x140011cac  nop     dword ptr [rax+rax+00h]
0x140011cb1  mov     [rsi+30h], r15
0x140011cb5  mov     [rsi+2Ch], r15d
0x140011cb9  cmp     qword ptr [rsi+38h], 0
0x140011cbe  jnz     loc_140011E0F
0x140011cc4  cmp     r13d, 4000h
0x140011ccb  ja      short loc_140011CE8
0x140011ccd  lea     rcx, SmbBufferLookasideList; Lookaside
0x140011cd4  mov     rdi, r15
0x140011cd7  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140011cde  nop     dword ptr [rax+rax+00h]
0x140011ce3  jmp     loc_140011D96
0x140011ce8  cmp     r13d, 9000h
0x140011cef  ja      short loc_140011D0E
0x140011cf1  lea     rcx, Lookaside; Lookaside
0x140011cf8  mov     edi, 1
0x140011cfd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140011d04  nop     dword ptr [rax+rax+00h]
0x140011d09  jmp     loc_140011D96
0x140011d0e  cmp     r13d, 11000h
0x140011d15  ja      short loc_140011D31
0x140011d17  lea     rcx, stru_140070740; Lookaside
0x140011d1e  mov     edi, 2
0x140011d23  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140011d2a  nop     dword ptr [rax+rax+00h]
0x140011d2f  jmp     short loc_140011D96
0x140011d31  cmp     r13d, 101000h
0x140011d38  ja      short loc_140011D54
0x140011d3a  lea     rcx, stru_1400707C0; Lookaside
0x140011d41  mov     edi, 3
0x140011d46  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140011d4d  nop     dword ptr [rax+rax+00h]
0x140011d52  jmp     short loc_140011D96
0x140011d54  cmp     r13d, 801000h
0x140011d5b  ja      short loc_140011D77
0x140011d5d  lea     rcx, stru_140070840; Lookaside
0x140011d64  mov     edi, 4
0x140011d69  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140011d70  nop     dword ptr [rax+rax+00h]
0x140011d75  jmp     short loc_140011D96
0x140011d77  mov     edx, r13d
0x140011d7a  mov     ecx, 42h ; 'B'
0x140011d7f  mov     r8d, 6D535056h
0x140011d85  mov     edi, 5
0x140011d8a  call    cs:__imp_ExAllocatePool2
0x140011d91  nop     dword ptr [rax+rax+00h]
0x140011d96  mov     rbx, rax
0x140011d99  test    rax, rax
0x140011d9c  jz      short loc_140011DE9
0x140011d9e  or      rbx, rdi
0x140011da1  mov     eax, ebx
0x140011da3  and     eax, 7
0x140011da6  cmp     eax, 4
0x140011da9  ja      short loc_140011DB3
0x140011dab  mov     edx, [r12+rax*4]
  ... truncated ...
```
