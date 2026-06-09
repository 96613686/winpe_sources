# CmsVolumeContainer::Initialize(CmsTransactionContext *,_MS_CREATE_DISPOSITION,_LcnWithChecksum * * const,ulong)

- ea: `0x1c002bf8c`
- end: `0x1c002c4c5`
- name: `?Initialize@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@W4_MS_CREATE_DISPOSITION@@QEAPEAU_LcnWithChecksum@@K@Z`
- size: `1337`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1c0044c68`

## callees

- `0x1c00035d0`
- `0x1c002b230`
- `0x1c002bf8c`
- `0x1c002c7a0`
- `0x1c004871c`
- `0x1c0048758`
- `0x1c0049624`
- `0x1c0066380`
- `0x1c00663e8`
- `0x1c00672f0`
- `0x1c0067e70`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002c067`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002c0e5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002c11b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007cf53`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007cfc6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002c067`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002c0e5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002c11b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007cf53`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007cfc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007d00a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007d00a`
- `ntoskrnl!ExAllocateAutoExpandPushLock` at `0x1c002c01c`
- `ntoskrnl!ExAllocateAutoExpandPushLock` at `0x1c002c01c`
- `ntoskrnl!RtlCreateHashTableEx` at `0x1c002c0a7`
- `ntoskrnl!RtlCreateHashTableEx` at `0x1c002c0a7`

## pseudocode

```c
int __fastcall CmsVolumeContainer::Initialize(__int64 a1, struct CmsTransactionContext *a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rdx
  unsigned __int64 v8; // r8
  int v9; // eax
  __int64 AutoExpandPushLock; // rax
  unsigned __int64 v11; // rcx
  SIZE_T v12; // rax
  PVOID PoolWithTag; // rax
  unsigned __int64 v14; // rdx
  SIZE_T v15; // rax
  PVOID v16; // rax
  _DWORD *v17; // rax
  unsigned int v18; // r14d
  __int64 v19; // r12
  void **v20; // rsi
  struct _SmsSchema *Schema; // rax
  unsigned int v22; // r11d
  int result; // eax
  struct CmsBPlusTable *v24; // rax
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int v28; // r11d
  __int64 v29; // r9
  __int64 v30; // r10
  int v31; // ebx
  __int64 v32; // rax
  _OWORD *v33; // rax
  struct CmsTransactionContext *v34; // rdx
  unsigned __int64 v35; // r9
  int v36; // ecx
  int v37; // eax
  struct CmsTableCursor *v38; // rsi
  __int64 v39; // rbx
  int v40; // eax
  __int64 v41; // r13
  unsigned __int64 i; // r14
  int v43; // ecx
  __int64 v44; // r12
  int v45; // r14d
  int v46; // r14d
  int v47; // eax
  SIZE_T v48; // rax
  PVOID v49; // rax
  void *v50; // rcx
  __int64 v51; // rax
  SIZE_T v52; // rax
  PVOID v53; // rax
  void *v54; // r12
  void *v55; // rcx
  struct CmsCowRootComposite **v56; // [rsp+38h] [rbp-C8h]
  int v57; // [rsp+40h] [rbp-C0h]
  struct CmsBPlusTable *v58[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *v59[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct CmsContainerCursor *v60; // [rsp+70h] [rbp-90h] BYREF
  __int128 v61; // [rsp+80h] [rbp-80h] BYREF
  __int128 v62; // [rsp+90h] [rbp-70h]
  _QWORD v63[2]; // [rsp+A0h] [rbp-60h]
  _BYTE v64[80]; // [rsp+B0h] [rbp-50h] BYREF

  v63[0] = 11;
  v60 = 0;
  v58[0] = 0;
  *(_OWORD *)v59 = 0;
  v63[1] = 12;
  v57 = 0;
  if ( !*(_DWORD *)(a1 + 180) )
  {
    v7 = *(_QWORD *)(a1 + 8);
    v8 = *(_QWORD *)(v7 + 56) << *(_DWORD *)(v7 + 64);
    if ( *(_DWORD *)(v7 + 3504) >= 2u )
    {
      if ( (*(_DWORD *)(v7 + 3116) & 0x800000) != 0 )
      {
        v9 = 6;
      }
      else if ( byte_1C0114F74[12 * *(int *)(v7 + 3484)] && v8 >= 0xE100000000LL )
      {
        v9 = 48;
      }
      else
      {
        v9 = v8 < 0x800000000LL ? 4 : 24;
      }
    }
    else
    {
      v9 = 2;
    }
    *(_DWORD *)(a1 + 180) = v9;
  }
  AutoExpandPushLock = ExAllocateAutoExpandPushLock(1);
  *(_QWORD *)(a1 + 56) = AutoExpandPushLock;
  if ( !AutoExpandPushLock )
    return -1073741670;
  v11 = *(unsigned int *)(a1 + 180);
  *(_DWORD *)(a1 + 320) = 0;
  v12 = 8 * v11;
  if ( !is_mul_ok(v11, 8u) )
    v12 = -1;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v12, 0x6950534Du);
  *(_QWORD *)(a1 + 312) = PoolWithTag;
  if ( !PoolWithTag )
    return -1073741670;
  memset(PoolWithTag, 0, 8LL * *(unsigned int *)(a1 + 180));
  if ( !(unsigned __int8)RtlCreateHashTableEx(a1 + 48, 0x10000, 0, 0) )
    return -1073741670;
  v14 = (*(__int64 *)(*(_QWORD *)(a1 + 8) + 56LL) >> *(_DWORD *)(*(_QWORD *)(a1 + 8) + 76LL)) + 1;
  *(_QWORD *)(a1 + 24) = v14;
  v15 = 8 * v14;
  if ( !is_mul_ok(v14, 8u) )
    v15 = -1;
  v16 = ExAllocatePoolWithTag((POOL_TYPE)512, v15, 0x6950534Du);
  *(_QWORD *)(a1 + 32) = v16;
  if ( v16 )
  {
    memset(v16, 0, 8LL * *(_QWORD *)(a1 + 24));
    v17 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x70u, 0x6274534Du);
    if ( v17 )
    {
      v17[2] = 1;
      *(_QWORD *)v17 = &CmsFailoverBPlusTable::`vftable';
      *((_QWORD *)v17 + 3) = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 4) = 0;
      *((_QWORD *)v17 + 5) = 0;
      *((_QWORD *)v17 + 6) = 0;
      *((_QWORD *)v17 + 7) = 0;
      v17[26] = 1;
      *((_QWORD *)v17 + 12) = 0;
    }
    else
    {
      v17 = 0;
    }
    *(_QWORD *)(a1 + 16) = v17;
    if ( v17 )
    {
      v18 = 0;
      v19 = a4 - (_QWORD)v59;
      v20 = v59;
      while ( 1 )
      {
        Schema = CmsSchemaTable::GetSchema(*(CmsSchemaTable **)(*(_QWORD *)(a1 + 8) + 3104LL), 0xE0C0u);
        result = CmsTableFactory::ProduceBTableObject(
                   a2,
                   Schema,
                   *(struct _LcnWithChecksum **)((char *)v20 + v19),
                   0,
                   v22,
                   0,
                   v58,
                   v56);
        if ( result < 0 )
          break;
        v24 = v58[0];
        *v20 = v58[0];
        ++v18;
        ++v20;
        *((_BYTE *)v24 + 152) = 2;
        *((_QWORD *)v24 + 2) |= 0x1040000uLL;
        if ( v18 >= 2 )
        {
          v25 = 0;
          do
          {
            v26 = *(__int64 *)((char *)v59 + v25);
            v27 = *(_QWORD *)(a1 + 16);
            v58[1] = *(struct CmsBPlusTable **)((char *)v63 + v25);
            v58[0] = 0;
            v61 = *(_OWORD *)v58;
            CmsFailoverBPlusTable::AddTable(v27, v26, &v61);
            v25 = v29 + 8;
          }
          while ( v30 != 1 );
          v31 = CmsFailoverBPlusTable::InitializeTablesWithCaching(*(_QWORD *)(a1 + 16), a2, v28, v25);
          if ( v31 >= 0 )
          {
            memset(v64, 0, 0x48u);
            v32 = *(_QWORD *)(a1 + 16);
            v59[0] = 0;
            LODWORD(v58[0]) = 0;
            (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v32 + 48) + 160LL))(*(_QWORD *)(v32 + 48), v64);
            v31 = CmsFailoverBPlusTable::PinDataWithRoot(
                    *(CmsFailoverBPlusTable **)(a1 + 16),
                    a2,
                    0,
                    v59,
                    (unsigned int *)v58,
                    (struct _SmsLookupStack *)v64,
                    0);
            if ( v31 >= 0 )
            {
              v33 = v59[0];
              *(_OWORD *)(a1 + 72) = *(_OWORD *)v59[0];
              *(_OWORD *)(a1 + 88) = v33[1];
              *(_OWORD *)(a1 + 104) = v33[2];
            }
            (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, _BYTE *))(**(_QWORD **)(*(_QWORD *)(a1 + 16)
                                                                                                  + 48LL)
                                                                                    + 168LL))(
              *(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL),
              a2,
              v64);
            if ( v31 >= 0 )
            {
              v36 = *(_DWORD *)(a1 + 104);
              if ( v36 )
              {
                v48 = 24LL * (unsigned int)(v36 + 1);
                if ( !is_mul_ok((unsigned int)(v36 + 1), 0x18u) )
                  v48 = -1;
                v49 = ExAllocatePoolWithTag((POOL_TYPE)512, v48, 0x6950534Du);
                *(_QWORD *)(a1 + 136) = v49;
                v50 = v49;
                if ( !v49 )
                  return -1073741670;
                v51 = (unsigned int)(*(_DWORD *)(a1 + 104) + 1);
                *(_DWORD *)(a1 + 188) = v51;
                memset(v50, 0, 24 * v51);
              }
              v37 = CmsVolumeContainer::CreateContainerEnumerateCursor((CmsVolumeContainer *)a1, v34, &v60, v35);
              v38 = v60;
              v31 = v37;
              if ( v37 >= 0 )
              {
                v61 = 0;
                v62 = 0;
                while ( 1 )
                {
                  v39 = *((_QWORD *)&v62 + 1);
                  do
                  {
                    v40 = CmsFailoverBPlusTable::Enumerate(
                            *(CmsFailoverBPlusTable **)(a1 + 16),
                            a2,
                            v38,
                            v39 != 0 ? 133 : 129,
                            (struct CmsRowWithBuffer *)&v61,
                            0);
                    v31 = v40;
                    if ( v40 < 0 )
                    {
                      if ( v40 == -1073741197 )
                      {
                        (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct CmsTableCursor *))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 48LL) + 152LL))(
                          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL),
                          a2,
                          v38);
                        *(_BYTE *)(a1 + 372) |= 1u;
                        v31 = 0;
                      }
                      goto LABEL_41;
                    }
                    v39 = *((_QWORD *)&v62 + 1);
                  }
                  while ( (*(_DWORD *)(*((_QWORD *)&v62 + 1) + 20LL) & 8) != 0 );
                  v41 = (unsigned int)(*(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228));
                  for ( i = *(_QWORD *)(a1 + 24); ; *(_QWORD *)(a1 + 24) = i )
                  {
                    v43 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 76LL);
                    if ( *(_QWORD *)(v39 + v41 + 80) >> v43 < i )
                      break;
                    *(_DWORD *)(*((_QWORD *)a2 + 4) + 3116LL) |= 0x80000000;
                    i = *(_QWORD *)(a1 + 24)
                      + (*(__int64 *)(*(_QWORD *)(a1 + 8) + 56LL) >> *(_DWORD *)(*(_QWORD *)(a1 + 8) + 76LL));
                    v52 = 8 * i;
                    if ( !is_mul_ok(i, 8u) )
                      v52 = -1;
                    v53 = ExAllocatePoolWithTag((POOL_TYPE)512, v52, 0x6950534Du);
                    v54 = v53;
                    if ( !v53 )
                    {
                      v31 = -1073741670;
                      goto LABEL_41;
                    }
                    memset(v53, 0, 8 * i);
                    memmove(v54, *(const void **)(a1 + 32), 8LL * *(_QWORD *)(a1 + 24));
                    v55 = *(void **)(a1 + 32);
                    if ( v55 )
                      ExFreePoolWithTag(v55, 0);
                    *(_QWORD *)(a1 + 32) = v54;
                  }
                  *(_QWORD *)(*(_QWORD *)(a1 + 32)
                            + 8LL
                            * (*(_QWORD *)((unsigned int)(*(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228)) + v39 + 80) >> v43)) = *(_QWORD *)v39;
                  v44 = (unsigned int)(*(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228));
                  CmsVolume::GetStorageTierForRange(*(_QWORD *)(a1 + 8), a2, v44 + v39 + 80);
                  v45 = *(_DWORD *)(v39 + 20);
                  if ( (v45 & 0x40) != 0 )
                  {
                    v46 = -__CFSHR__(v45, 11);
                    v31 = CmsVolumeContainer::AddReservedContainer(
                            (CmsVolumeContainer *)a1,
                            a2,
                            (const struct _RANGE *)(v44 + v39 + 80),
                            0,
                            v46 != 0);
                    v47 = v57 + 1;
                    if ( !v46 )
                      v47 = v57;
                    v57 = v47;
                    if ( v31 < 0 )
                      break;
                  }
                }
              }
LABEL_41:
              if ( v38 )
              {
                (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct CmsTableCursor *))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 48LL) + 152LL))(
                  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL),
                  a2,
                  v38);
                CmsContainerCursor::`vector deleting destructor'(v38, 1u);
              }
            }
          }
          return v31;
        }
      }
    }
    else
    {
      return -1073741670;
    }
  }
  else
  {
    return -1073741670;
  }
  return result;
}

```

## disassembly

```asm
0x1c002bf8c  mov     [rsp-8+arg_10], rbx
0x1c002bf91  push    rbp
0x1c002bf92  push    rsi
0x1c002bf93  push    rdi
0x1c002bf94  push    r12
0x1c002bf96  push    r13
0x1c002bf98  push    r14
0x1c002bf9a  push    r15
0x1c002bf9c  lea     rbp, [rsp-10h]
0x1c002bfa1  sub     rsp, 110h
0x1c002bfa8  mov     rax, cs:__security_cookie
0x1c002bfaf  xor     rax, rsp
0x1c002bfb2  mov     [rbp+40h+var_40], rax
0x1c002bfb6  xor     r13d, r13d
0x1c002bfb9  mov     [rbp+40h+var_A0], 0Bh
0x1c002bfc1  xorps   xmm0, xmm0
0x1c002bfc4  mov     r12, r9
0x1c002bfc7  mov     r15, rdx
0x1c002bfca  mov     rdi, rcx
0x1c002bfcd  mov     [rsp+140h+var_D0], r13
0x1c002bfd2  mov     [rsp+140h+var_F0], r13
0x1c002bfd7  movups  xmmword ptr [rsp+140h+var_E0], xmm0
0x1c002bfdc  mov     [rbp+40h+var_98], 0Ch
0x1c002bfe4  mov     [rsp+140h+var_100], r13d
0x1c002bfe9  cmp     [rcx+0B4h], r13d
0x1c002bff0  jnz     short loc_1C002C017
0x1c002bff2  mov     rdx, [rcx+8]
0x1c002bff6  mov     r8, [rdx+38h]
0x1c002bffa  mov     ecx, [rdx+40h]
0x1c002bffd  shl     r8, cl
0x1c002c000  cmp     dword ptr [rdx+0DB0h], 2
0x1c002c007  jnb     loc_1C007CEB2
0x1c002c00d  lea     eax, [r13+2]
0x1c002c011  mov     [rdi+0B4h], eax
0x1c002c017  mov     ecx, 1
0x1c002c01c  call    cs:__imp_ExAllocateAutoExpandPushLock
0x1c002c023  nop     dword ptr [rax+rax+00h]
0x1c002c028  mov     [rdi+38h], rax
0x1c002c02c  test    rax, rax
0x1c002c02f  jz      loc_1C007CF13
0x1c002c035  mov     ecx, [rdi+0B4h]
0x1c002c03b  mov     ebx, 8
0x1c002c040  mov     eax, ebx
0x1c002c042  mov     [rdi+140h], r13d
0x1c002c049  mul     rcx
0x1c002c04c  lea     rcx, [rbx-9]
0x1c002c050  mov     r14d, 6950534Dh
0x1c002c056  mov     esi, 200h
0x1c002c05b  mov     r8d, r14d; Tag
0x1c002c05e  cmovo   rax, rcx
0x1c002c062  mov     ecx, esi; PoolType
0x1c002c064  mov     rdx, rax; NumberOfBytes
0x1c002c067  call    cs:__imp_ExAllocatePoolWithTag
0x1c002c06e  nop     dword ptr [rax+rax+00h]
0x1c002c073  mov     [rdi+138h], rax
0x1c002c07a  test    rax, rax
0x1c002c07d  jz      loc_1C007CF13
0x1c002c083  mov     r8d, [rdi+0B4h]
0x1c002c08a  xor     edx, edx; Val
0x1c002c08c  shl     r8, 3; Size
0x1c002c090  mov     rcx, rax; void *
0x1c002c093  call    memset
0x1c002c098  lea     rcx, [rdi+30h]
0x1c002c09c  xor     r9d, r9d
0x1c002c09f  xor     r8d, r8d
0x1c002c0a2  mov     edx, 10000h
0x1c002c0a7  call    cs:__imp_RtlCreateHashTableEx
0x1c002c0ae  nop     dword ptr [rax+rax+00h]
0x1c002c0b3  test    al, al
0x1c002c0b5  jz      loc_1C007CF13
0x1c002c0bb  mov     rax, [rdi+8]
0x1c002c0bf  mov     r8d, r14d; Tag
0x1c002c0c2  mov     ecx, [rax+4Ch]
0x1c002c0c5  mov     rdx, [rax+38h]
0x1c002c0c9  mov     eax, ebx
0x1c002c0cb  sar     rdx, cl
0x1c002c0ce  lea     rcx, [rbx-9]
0x1c002c0d2  inc     rdx
0x1c002c0d5  mov     [rdi+18h], rdx
0x1c002c0d9  mul     rdx
0x1c002c0dc  cmovo   rax, rcx
0x1c002c0e0  mov     ecx, esi; PoolType
0x1c002c0e2  mov     rdx, rax; NumberOfBytes
0x1c002c0e5  call    cs:__imp_ExAllocatePoolWithTag
0x1c002c0ec  nop     dword ptr [rax+rax+00h]
0x1c002c0f1  mov     [rdi+20h], rax
0x1c002c0f5  test    rax, rax
0x1c002c0f8  jz      loc_1C007CF13
0x1c002c0fe  mov     r8, [rdi+18h]
0x1c002c102  xor     edx, edx; Val
0x1c002c104  shl     r8, 3; Size
0x1c002c108  mov     rcx, rax; void *
0x1c002c10b  call    memset
0x1c002c110  lea     edx, [rbx+68h]; NumberOfBytes
0x1c002c113  mov     r8d, 6274534Dh; Tag
0x1c002c119  mov     ecx, esi; PoolType
0x1c002c11b  call    cs:__imp_ExAllocatePoolWithTag
0x1c002c122  nop     dword ptr [rax+rax+00h]
0x1c002c127  test    rax, rax
0x1c002c12a  jz      loc_1C007CF1D
0x1c002c130  lea     rcx, ??_7CmsFailoverBPlusTable@@6B@; const CmsFailoverBPlusTable::`vftable'
0x1c002c137  mov     dword ptr [rax+8], 1
0x1c002c13e  mov     [rax], rcx
0x1c002c141  mov     [rax+18h], r13
0x1c002c145  mov     [rax+10h], r13
0x1c002c149  mov     [rax+20h], r13
0x1c002c14d  mov     [rax+28h], r13
0x1c002c151  mov     [rax+30h], r13
0x1c002c155  mov     [rax+38h], r13
0x1c002c159  mov     dword ptr [rax+68h], 1
0x1c002c160  mov     [rax+60h], r13
0x1c002c164  mov     [rdi+10h], rax
0x1c002c168  test    rax, rax
0x1c002c16b  jz      loc_1C007CF25
0x1c002c171  lea     rax, [rsp+140h+var_E0]
0x1c002c176  mov     r14d, r13d
0x1c002c179  sub     r12, rax
0x1c002c17c  lea     rsi, [rsp+140h+var_E0]
0x1c002c181  mov     rax, [rdi+8]
0x1c002c185  mov     edx, 0E0C0h; unsigned int
0x1c002c18a  mov     ecx, [rax+40h]
0x1c002c18d  mov     r11d, [rax+0C0Ch]
0x1c002c194  shr     r11d, cl
0x1c002c197  mov     rcx, [rax+0C20h]; this
0x1c002c19e  call    ?GetSchema@CmsSchemaTable@@QEAAPEAU_SmsSchema@@K@Z; CmsSchemaTable::GetSchema(ulong)
0x1c002c1a3  mov     r8, [r12+rsi]; struct _LcnWithChecksum *
0x1c002c1a7  lea     rcx, [rsp+140h+var_F0]
0x1c002c1ac  mov     [rsp+140h+var_110], rcx; struct CmsBPlusTable **
0x1c002c1b1  xor     r9d, r9d; union _LCN_TUPLE *
0x1c002c1b4  mov     byte ptr [rsp+140h+var_118], r13b; unsigned __int8
0x1c002c1b9  mov     rcx, r15; struct CmsTransactionContext *
0x1c002c1bc  mov     rdx, rax; struct _SmsSchema *
0x1c002c1bf  mov     dword ptr [rsp+140h+var_120], r11d; unsigned int
0x1c002c1c4  call    ?ProduceBTableObject@CmsTableFactory@@SAJPEAVCmsTransactionContext@@PEAU_SmsSchema@@PEAU_LcnWithChecksum@@PEBT_LCN_TUPLE@@KEPEAPEAVCmsBPlusTable@@PEAPEAVCmsCowRootComposite@@@Z; CmsTableFactory::ProduceBTableObject(CmsTransactionContext *,_SmsSchema *,_LcnWithChecksum *,_LCN_TUPLE const *,ulong,uchar,CmsBPlusTable * *,CmsCowRootComposite * *)
0x1c002c1c9  test    eax, eax
0x1c002c1cb  js      loc_1C002C49D
0x1c002c1d1  mov     rax, [rsp+140h+var_F0]
0x1c002c1d6  mov     r11d, 2
0x1c002c1dc  mov     [rsi], rax
0x1c002c1df  inc     r14d
0x1c002c1e2  add     rsi, rbx
0x1c002c1e5  mov     [rax+98h], r11b
0x1c002c1ec  or      qword ptr [rax+10h], 1040000h
0x1c002c1f4  cmp     r14d, r11d
0x1c002c1f7  jb      short loc_1C002C181
0x1c002c1f9  mov     r9, r13
0x1c002c1fc  mov     r10d, r11d
0x1c002c1ff  mov     rax, [rbp+r9+40h+var_A0]
0x1c002c204  lea     r8, [rbp+40h+var_C0]
0x1c002c208  mov     rdx, [rsp+r9+140h+var_E0]
0x1c002c20d  mov     rcx, [rdi+10h]
0x1c002c211  mov     [rsp+140h+var_F0+8], rax
0x1c002c216  mov     [rsp+140h+var_F0], r13
0x1c002c21b  movaps  xmm0, xmmword ptr [rsp+140h+var_F0]
0x1c002c220  movdqa  [rbp+40h+var_C0], xmm0
0x1c002c225  call    ?AddTable@CmsFailoverBPlusTable@@QEAAJPEAVCmsBPlusTable@@T_SmsBigIdentifier@@@Z; CmsFailoverBPlusTable::AddTable(CmsBPlusTable *,_SmsBigIdentifier)
0x1c002c22a  lea     r9, [r9+8]
0x1c002c22e  sub     r10, 1
0x1c002c232  jnz     short loc_1C002C1FF
0x1c002c234  mov     rcx, [rdi+10h]
0x1c002c238  mov     r8d, r11d
0x1c002c23b  mov     rdx, r15
0x1c002c23e  call    ?InitializeTablesWithCaching@CmsFailoverBPlusTable@@QEAAJPEAVCmsTransactionContext@@W4_MS_CREATE_DISPOSITION@@PEAPEAU_SCB@@@Z; CmsFailoverBPlusTable::InitializeTablesWithCaching(CmsTransactionContext *,_MS_CREATE_DISPOSITION,_SCB * *)
0x1c002c243  mov     ebx, eax
0x1c002c245  test    eax, eax
0x1c002c247  js      loc_1C002C49B
0x1c002c24d  xor     edx, edx; Val
0x1c002c24f  lea     rcx, [rbp+40h+var_90]; void *
0x1c002c253  lea     r8d, [rdx+48h]; Size
0x1c002c257  call    memset
0x1c002c25c  mov     rax, [rdi+10h]
0x1c002c260  lea     rdx, [rbp+40h+var_90]
0x1c002c264  mov     [rsp+140h+var_E0], r13
0x1c002c269  mov     dword ptr [rsp+140h+var_F0], r13d
0x1c002c26e  mov     rcx, [rax+30h]
0x1c002c272  mov     rax, [rcx]
0x1c002c275  mov     rax, [rax+0A0h]
0x1c002c27c  call    cs:__guard_dispatch_icall_fptr
0x1c002c282  mov     rcx, [rdi+10h]; this
0x1c002c286  lea     rax, [rbp+40h+var_90]
0x1c002c28a  mov     byte ptr [rsp+140h+var_110], r13b; unsigned __int8
0x1c002c28f  lea     r9, [rsp+140h+var_E0]; void **
0x1c002c294  mov     [rsp+140h+var_118], rax; struct _SmsLookupStack *
0x1c002c299  xor     r8d, r8d; unsigned int
0x1c002c29c  lea     rax, [rsp+140h+var_F0]
0x1c002c2a1  mov     rdx, r15; struct CmsTransactionContext *
0x1c002c2a4  mov     [rsp+140h+var_120], rax; unsigned int *
0x1c002c2a9  call    ?PinDataWithRoot@CmsFailoverBPlusTable@@UEAAJPEAVCmsTransactionContext@@KPEAPEAXPEAKPEAU_SmsLookupStack@@E@Z; CmsFailoverBPlusTable::PinDataWithRoot(CmsTransactionContext *,ulong,void * *,ulong *,_SmsLookupStack *,uchar)
0x1c002c2ae  mov     ebx, eax
0x1c002c2b0  test    eax, eax
0x1c002c2b2  js      short loc_1C002C2D0
0x1c002c2b4  mov     rax, [rsp+140h+var_E0]
0x1c002c2b9  movups  xmm0, xmmword ptr [rax]
0x1c002c2bc  movups  xmmword ptr [rdi+48h], xmm0
0x1c002c2c0  movups  xmm1, xmmword ptr [rax+10h]
0x1c002c2c4  movups  xmmword ptr [rdi+58h], xmm1
0x1c002c2c8  movups  xmm0, xmmword ptr [rax+20h]
0x1c002c2cc  movups  xmmword ptr [rdi+68h], xmm0
0x1c002c2d0  mov     rax, [rdi+10h]
0x1c002c2d4  lea     r8, [rbp+40h+var_90]
0x1c002c2d8  mov     rdx, r15
0x1c002c2db  mov     rcx, [rax+30h]
0x1c002c2df  mov     rax, [rcx]
0x1c002c2e2  mov     rax, [rax+0A8h]
0x1c002c2e9  call    cs:__guard_dispatch_icall_fptr
0x1c002c2ef  test    ebx, ebx
0x1c002c2f1  js      loc_1C002C49B
0x1c002c2f7  mov     ecx, [rdi+68h]
0x1c002c2fa  test    ecx, ecx
0x1c002c2fc  jnz     loc_1C007CF2F
0x1c002c302  or      r12, 0FFFFFFFFFFFFFFFFh
0x1c002c306  lea     r8, [rsp+140h+var_D0]; struct CmsContainerCursor **
0x1c002c30b  mov     rcx, rdi; this
0x1c002c30e  call    ?CreateContainerEnumerateCursor@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAPEAVCmsContainerCursor@@_K@Z; CmsVolumeContainer::CreateContainerEnumerateCursor(CmsTransactionContext *,CmsContainerCursor * *,unsigned __int64)
0x1c002c313  mov     rsi, [rsp+140h+var_D0]
0x1c002c318  mov     ebx, eax
0x1c002c31a  test    eax, eax
0x1c002c31c  js      loc_1C002C46B
0x1c002c322  xorps   xmm0, xmm0
0x1c002c325  movups  [rbp+40h+var_C0], xmm0
0x1c002c329  movups  [rbp+40h+var_B0], xmm0
0x1c002c32d  mov     rbx, qword ptr [rbp+40h+var_B0+8]
0x1c002c331  mov     rcx, [rdi+10h]; this
0x1c002c335  lea     rax, [rbp+40h+var_C0]
0x1c002c339  neg     rbx
0x1c002c33c  mov     byte ptr [rsp+140h+var_118], r13b; char
0x1c002c341  mov     r8, rsi; struct CmsTableCursor *
0x1c002c344  mov     [rsp+140h+var_120], rax; struct CmsRowWithBuffer *
0x1c002c349  sbb     r9d, r9d
0x1c002c34c  mov     rdx, r15; struct CmsTransactionContext *
0x1c002c34f  and     r9d, 4
0x1c002c353  add     r9d, 81h; unsigned int
0x1c002c35a  call    ?Enumerate@CmsFailoverBPlusTable@@UEAAJPEAVCmsTransactionContext@@PEAVCmsTableCursor@@KPEAVCmsRowWithBuffer@@E@Z; CmsFailoverBPlusTable::Enumerate(CmsTransactionContext *,CmsTableCursor *,ulong,CmsRowWithBuffer *,uchar)
0x1c002c35f  mov     ebx, eax
0x1c002c361  test    eax, eax
0x1c002c363  js      loc_1C002C43C
0x1c002c369  mov     rbx, qword ptr [rbp+40h+var_B0+8]
0x1c002c36d  mov     eax, [rbx+14h]
0x1c002c370  test    al, 8
0x1c002c372  jnz     short loc_1C002C331
0x1c002c374  mov     r13d, [rdi+0E4h]
0x1c002c37b  imul    r13d, [rdi+0E8h]
0x1c002c383  mov     r14, [rdi+18h]
0x1c002c387  mov     rax, [rdi+8]
0x1c002c38b  mov     ecx, [rax+4Ch]
0x1c002c38e  mov     rax, [rbx+r13+50h]
0x1c002c393  shr     rax, cl
0x1c002c396  cmp     rax, r14
0x1c002c399  jnb     loc_1C007CF8E
0x1c002c39f  mov     eax, [rdi+0E4h]
0x1c002c3a5  lea     r8, [rbx+50h]
0x1c002c3a9  imul    eax, [rdi+0E8h]
0x1c002c3b0  mov     rdx, [rax+rbx+50h]
0x1c002c3b5  mov     rax, [rbx]
0x1c002c3b8  shr     rdx, cl
0x1c002c3bb  mov     rcx, [rdi+20h]
0x1c002c3bf  mov     [rcx+rdx*8], rax
0x1c002c3c3  mov     rdx, r15
0x1c002c3c6  mov     r12d, [rdi+0E4h]
0x1c002c3cd  imul    r12d, [rdi+0E8h]
0x1c002c3d5  mov     rcx, [rdi+8]
0x1c002c3d9  add     r8, r12
0x1c002c3dc  call    ?GetStorageTierForRange@CmsVolume@@QEAA?AW4_EMS_STORAGE_TIER_MEDIA_TYPE@@PEAVCmsTransactionCore@@PEBU_RANGE@@@Z; CmsVolume::GetStorageTierForRange(CmsTransactionCore *,_RANGE const *)
0x1c002c3e1  mov     r14d, [rbx+14h]
0x1c002c3e5  test    r14b, 40h
0x1c002c3e9  jnz     short loc_1C002C3F7
0x1c002c3eb  xor     r13d, r13d
0x1c002c3ee  or      r12, 0FFFFFFFFFFFFFFFFh
0x1c002c3f2  jmp     loc_1C002C32D
0x1c002c3f7  shr     r14d, 0Bh
0x1c002c3fb  lea     r8, [rbx+50h]
0x1c002c3ff  mov     rdx, r15; struct CmsTransactionContext *
0x1c002c402  mov     rcx, rdi; this
0x1c002c405  sbb     r14d, r14d
0x1c002c408  test    r14d, r14d
0x1c002c40b  setnz   al
0x1c002c40e  xor     r9d, r9d; unsigned __int8
0x1c002c411  add     r8, r12; struct _RANGE *
0x1c002c414  mov     byte ptr [rsp+140h+var_120], al; char
0x1c002c418  call    ?AddReservedContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@AEBU_RANGE@@EE@Z; CmsVolumeContainer::AddReservedContainer(CmsTransactionContext *,_RANGE const &,uchar,uchar)
0x1c002c41d  mov     r13d, [rsp+140h+var_100]
0x1c002c422  mov     ebx, eax
0x1c002c424  test    r14d, r14d
0x1c002c427  lea     eax, [r13+1]
0x1c002c42b  cmovz   eax, r13d
0x1c002c42f  xor     r13d, r13d
0x1c002c432  mov     [rsp+140h+var_100], eax
0x1c002c436  test    ebx, ebx
0x1c002c438  jns     short loc_1C002C3EE
0x1c002c43a  jmp     short loc_1C002C46B
0x1c002c43c  cmp     eax, 0C0000273h
0x1c002c441  jnz     short loc_1C002C46B
0x1c002c443  mov     rax, [rdi+10h]
0x1c002c447  mov     r8, rsi
0x1c002c44a  mov     rdx, r15
0x1c002c44d  mov     rcx, [rax+30h]
0x1c002c451  mov     rax, [rcx]
0x1c002c454  mov     rax, [rax+98h]
0x1c002c45b  call    cs:__guard_dispatch_icall_fptr
0x1c002c461  or      byte ptr [rdi+174h], 1
  ... truncated ...
```
