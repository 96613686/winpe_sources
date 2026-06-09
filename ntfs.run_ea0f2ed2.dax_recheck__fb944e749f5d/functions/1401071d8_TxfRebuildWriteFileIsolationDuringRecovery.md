# TxfRebuildWriteFileIsolationDuringRecovery

- ea: `0x1401071d8`
- end: `0x140107784`
- name: `TxfRebuildWriteFileIsolationDuringRecovery`
- size: `1452`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140103260`

## callees

- `0x14000cb00`
- `0x140059250`
- `0x1400596c0`
- `0x14010033c`
- `0x140100e38`
- `0x1401071d8`
- `0x140294b1c`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14010739b`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140107614`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14010739b`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140107614`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140107767`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140107767`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14010735c`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14010735c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140107433`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c5447`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140107433`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c5447`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401072af`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401072af`
- `ntoskrnl!ExReleaseResourceLite` at `0x140107300`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401073ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c53d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140107300`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401073ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c53d6`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010731b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010731b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140107416`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c542a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140107416`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c542a`

## pseudocode

```c
__int64 __fastcall TxfRebuildWriteFileIsolationDuringRecovery(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v8; // rsi
  __int64 v9; // r15
  __int64 v10; // rdi
  ULONG i; // r9d
  __m128i *v12; // rax
  __int64 *v13; // rbx
  _BYTE *v14; // rax
  char v15; // cl
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // esi
  __m128i v21; // xmm6
  __m128i v22; // xmm7
  __m128i v23; // xmm8
  int v24; // r9d
  __int64 v25; // rdx
  int v26; // r8d
  int v27; // r9d
  unsigned int v28; // edx
  _BYTE *inserted; // rax
  char v30; // cl
  __int64 v31; // r9
  __int64 v32; // r8
  unsigned int v33; // edi
  __int64 j; // rdx
  unsigned int v35; // ecx
  int RestartKey; // [rsp+20h] [rbp-268h]
  unsigned __int8 NewElement; // [rsp+41h] [rbp-247h] BYREF
  char v38; // [rsp+42h] [rbp-246h]
  unsigned int v39; // [rsp+44h] [rbp-244h]
  PVOID Entry; // [rsp+48h] [rbp-240h] BYREF
  __int64 v41; // [rsp+50h] [rbp-238h] BYREF
  ULONG DeleteCount; // [rsp+58h] [rbp-230h] BYREF
  __int64 v43; // [rsp+60h] [rbp-228h]
  PVOID v44; // [rsp+68h] [rbp-220h] BYREF
  __int64 v45; // [rsp+70h] [rbp-218h]
  __m128i *v46; // [rsp+78h] [rbp-210h]
  __int64 v47; // [rsp+80h] [rbp-208h]
  __m128i v48; // [rsp+88h] [rbp-200h]
  __m128i v49; // [rsp+98h] [rbp-1F0h]
  _BYTE v50[20]; // [rsp+A8h] [rbp-1E0h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-1C8h]
  unsigned int *v52; // [rsp+C8h] [rbp-1C0h]
  __m128i *v53; // [rsp+D0h] [rbp-1B8h]
  _QWORD v54[38]; // [rsp+E0h] [rbp-1A8h] BYREF

  v51 = a2;
  memset(v54, 0, 0x124u);
  v8 = *(_QWORD *)(a2 + 208);
  v43 = v8;
  DeleteCount = 0;
  v44 = 0;
  v46 = 0;
  v45 = 0;
  v48 = 0;
  v49 = 0;
  memset(v50, 0, sizeof(v50));
  v38 = 0;
  NewElement = 0;
  v41 = 0;
  v47 = 0;
  Entry = ExAllocateFromLookasideListEx(&TxfTopsRangeEntryLookasideList);
  NtfsAcquireExclusiveScbEx(a1, a3, 0);
  TxfRebuildTxfStructuresForRecovery(a1, a3, a2, &v41);
  v47 = *(_QWORD *)(*(_QWORD *)(a3 + 528) + 56LL);
  v9 = v47;
  ExReleaseResourceLite(*(PERESOURCE *)(v41 + 136));
  v10 = 0;
  v41 = 0;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v9 + 256));
  v38 = 1;
  for ( i = 0; ; i = 1 )
  {
    v12 = (__m128i *)RtlEnumerateGenericTableLikeADirectory(
                       (PRTL_AVL_TABLE)(v9 + 152),
                       TxfMatchPageRange,
                       a4,
                       i,
                       &v44,
                       &DeleteCount,
                       a4);
    v13 = (__int64 *)v12;
    v46 = v12;
    if ( !v12 )
      break;
    v17 = *a4;
    v18 = v12->m128i_i64[0];
    if ( v12->m128i_i64[0] >= (unsigned __int64)*a4 )
    {
      v31 = *((unsigned int *)a4 + 6);
      v32 = v12->m128i_i64[1];
      if ( v17 + v31 >= v18 + (unsigned __int64)v12[1].m128i_u32[2] )
      {
        if ( v32 != a4[1] )
        {
          TxfInsertNewTopsRange(*(_QWORD *)(v8 + 16), v9, v32, v12[1].m128i_i32[2], (__int64)&Entry, 0);
          RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v9 + 152), v13);
        }
      }
      else
      {
        v33 = v31 + v17 - v18;
        TxfInsertNewTopsRange(*(_QWORD *)(v8 + 16), v9, v32, v33, (__int64)&Entry, 0);
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          v39 = j;
          v35 = *((_DWORD *)v13 + 6) - v33;
          if ( (unsigned int)j >= 8 * v35 )
            break;
          *((_WORD *)&v54[4] + j + 2) = *((_WORD *)&v13[2 * v33 + 4] + (unsigned int)j + 2);
        }
        v13[1] += v33;
        *v13 += v33;
        *((_DWORD *)v13 + 6) = v35;
        *((_DWORD *)v13 + 8) -= v33 << 12;
      }
    }
    else
    {
      v19 = v12[1].m128i_u32[2];
      v52 = &v12[1].m128i_u32[2];
      v53 = v12 + 2;
      v20 = v17 - v18;
      if ( v17 + (unsigned __int64)*((unsigned int *)a4 + 6) >= v18 + v19 )
      {
        TxfInsertNewTopsRange(*(_QWORD *)(v43 + 16), v9, v12->m128i_i32[2] + v20, v19 - v20, (__int64)&Entry, 0);
        *v52 = v20;
        v53->m128i_i32[0] = v20 << 12;
        v8 = v43;
      }
      else
      {
        v48 = *v12;
        v21 = v48;
        v49 = v12[1];
        v22 = v49;
        *(__m128i *)v50 = v12[2];
        v23 = *(__m128i *)v50;
        v45 = v12[3].m128i_u32[0];
        *(_DWORD *)&v50[16] = v45;
        v12[1].m128i_i32[2] = v20;
        v12[2].m128i_i32[0] = v20 << 12;
        v54[0] = v21.m128i_i64[0];
        v54[1] = _mm_srli_si128(v21, 8).m128i_u64[0];
        v54[2] = v49.m128i_i64[0];
        v24 = _mm_cvtsi128_si32(_mm_srli_si128(v22, 8));
        LODWORD(v54[3]) = v24;
        HIDWORD(v54[3]) = _mm_srli_si128(v22, 8).m128i_i32[1];
        LODWORD(v54[4]) = _mm_cvtsi128_si32(v23);
        *(_OWORD *)((char *)&v54[4] + 4) = *(_OWORD *)&v50[4];
        v25 = *((unsigned int *)a4 + 6);
        v26 = v24 - v25 - v12[1].m128i_i32[2];
        LODWORD(v54[3]) = v26;
        LODWORD(v54[4]) = LODWORD(v54[4]) - ((_DWORD)v25 << 12) - (v12[1].m128i_i32[2] << 12);
        v54[0] = v25 + *a4;
        v54[1] = v12->m128i_i64[1] + v25 + v12[1].m128i_u32[2];
        v27 = v24 - v26;
        v28 = 0;
        v39 = 0;
        while ( v28 < 8 * v26 )
        {
          *((_WORD *)&v54[4] + v28 + 2) = v12[v27 + 2].m128i_i16[v28 + 2];
          v39 = ++v28;
          v26 = v54[3];
        }
        inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(v9 + 152), v54, 16 * (v26 - 1) + 52, &NewElement);
        inserted[30] |= 1u;
        v30 = inserted[30] | 8;
        inserted[30] = v30;
        inserted[30] = v30 | 0x20;
        v8 = v43;
        TxfInsertNewTopsRange(
          *(_QWORD *)(v43 + 16),
          v9,
          *((_DWORD *)v13 + 2) + *((_DWORD *)v13 + 6),
          *((_DWORD *)a4 + 6),
          (__int64)&Entry,
          0);
      }
    }
    v10 = v41;
  }
  v44 = 0;
  v14 = RtlInsertElementGenericTableAvl(
          (PRTL_AVL_TABLE)(v9 + 152),
          a4,
          16 * (*((_DWORD *)a4 + 6) - 1) + 52,
          &NewElement);
  v14[30] |= 1u;
  v15 = v14[30] | 0x10;
  v14[30] = v15;
  v14[30] = v15 | 0x20;
  LOBYTE(RestartKey) = 0;
  TxfDirectlyAllocateTopsRange(*(_QWORD *)(v51 + 208), v9, *((_QWORD *)v14 + 1), *((unsigned int *)v14 + 6), RestartKey);
  if ( v10 )
    ExReleaseResourceLite(*(PERESOURCE *)(v10 + 136));
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v9 + 256));
  if ( Entry )
    ExFreeToLookasideListEx(&TxfTopsRangeEntryLookasideList, Entry);
  return 0;
}

```

## disassembly

```asm
0x1401071d8  mov     rax, rsp
0x1401071db  push    rbx
0x1401071dc  push    rsi
0x1401071dd  push    rdi
0x1401071de  push    r12
0x1401071e0  push    r13
0x1401071e2  push    r14
0x1401071e4  push    r15
0x1401071e6  sub     rsp, 250h
0x1401071ed  movaps  xmmword ptr [rax-48h], xmm6
0x1401071f1  movaps  xmmword ptr [rax-58h], xmm7
0x1401071f5  movaps  xmmword ptr [rax-68h], xmm8
0x1401071fa  mov     rax, cs:__security_cookie
0x140107201  xor     rax, rsp
0x140107204  mov     [rsp+288h+var_78], rax
0x14010720c  mov     r14, r9
0x14010720f  mov     rbx, r8
0x140107212  mov     r15, rdx
0x140107215  mov     [rsp+288h+var_1C8], rdx
0x14010721d  mov     rdi, rcx
0x140107220  xor     edx, edx; Val
0x140107222  mov     r8d, 124h; Size
0x140107228  lea     rcx, [rsp+288h+var_1A8]; void *
0x140107230  call    memset
0x140107235  mov     rsi, [r15+0D0h]
0x14010723c  mov     [rsp+288h+var_228], rsi
0x140107241  xor     r12d, r12d
0x140107244  mov     [rsp+288h+var_230], r12d
0x140107249  mov     [rsp+288h+var_220], r12
0x14010724e  mov     [rsp+288h+var_210], r12
0x140107253  xorps   xmm6, xmm6
0x140107256  xor     eax, eax
0x140107258  mov     [rsp+288h+var_218], rax
0x14010725d  movups  [rsp+288h+var_200], xmm6
0x140107265  xorps   xmm7, xmm7
0x140107268  movups  [rsp+288h+var_1F0], xmm7
0x140107270  xorps   xmm8, xmm8
0x140107274  movups  [rsp+288h+var_1E0], xmm8
0x14010727d  mov     [rsp+288h+var_1D0], eax
0x140107284  mov     [rsp+288h+var_246], r12b
0x140107289  mov     r13b, r12b
0x14010728c  mov     [rsp+288h+var_248], r12b
0x140107291  mov     [rsp+288h+NewElement], r12b
0x140107296  mov     [rsp+288h+var_238], r12
0x14010729b  mov     [rsp+288h+var_208], r12
0x1401072a3  mov     [rsp+288h+Entry], r12
0x1401072a8  lea     rcx, TxfTopsRangeEntryLookasideList; Lookaside
0x1401072af  call    cs:__imp_ExAllocateFromLookasideListEx
0x1401072b6  nop     dword ptr [rax+rax+00h]
0x1401072bb  mov     [rsp+288h+Entry], rax
0x1401072c0  xor     r8d, r8d
0x1401072c3  mov     rdx, rbx
0x1401072c6  mov     rcx, rdi
0x1401072c9  call    NtfsAcquireExclusiveScbEx
0x1401072ce  lea     r9, [rsp+288h+var_238]
0x1401072d3  mov     r8, r15
0x1401072d6  mov     rdx, rbx
0x1401072d9  mov     rcx, rdi
0x1401072dc  call    TxfRebuildTxfStructuresForRecovery
0x1401072e1  mov     rax, [rbx+210h]
0x1401072e8  mov     r15, [rax+38h]
0x1401072ec  mov     [rsp+288h+var_208], r15
0x1401072f4  mov     rcx, [rsp+288h+var_238]
0x1401072f9  mov     rcx, [rcx+88h]; Resource
0x140107300  call    cs:__imp_ExReleaseResourceLite
0x140107307  nop     dword ptr [rax+rax+00h]
0x14010730c  mov     edi, r12d
0x14010730f  mov     [rsp+288h+var_238], r12
0x140107314  mov     rcx, [r15+100h]; FastMutex
0x14010731b  call    cs:__imp_ExAcquireFastMutex
0x140107322  nop     dword ptr [rax+rax+00h]
0x140107327  mov     [rsp+288h+var_246], 1
0x14010732c  mov     r9d, r12d; NextFlag
0x14010732f  lea     r12, [r15+98h]
0x140107336  mov     [rsp+288h+Buffer], r14; Buffer
0x14010733b  lea     rax, [rsp+288h+var_230]
0x140107340  mov     [rsp+288h+DeleteCount], rax; DeleteCount
0x140107345  lea     rax, [rsp+288h+var_220]
0x14010734a  mov     [rsp+288h+RestartKey], rax; RestartKey
0x14010734f  mov     r8, r14; MatchData
0x140107352  lea     rdx, TxfMatchPageRange; MatchFunction
0x140107359  mov     rcx, r12; Table
0x14010735c  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x140107363  nop     dword ptr [rax+rax+00h]
0x140107368  mov     rbx, rax
0x14010736b  mov     [rsp+288h+var_210], rax
0x140107370  xor     r11d, r11d
0x140107373  test    rax, rax
0x140107376  jnz     loc_140107478
0x14010737c  mov     [rsp+288h+var_220], r11
0x140107381  mov     r8d, [r14+18h]
0x140107385  dec     r8d
0x140107388  shl     r8d, 4
0x14010738c  add     r8d, 34h ; '4'; BufferSize
0x140107390  lea     r9, [rsp+288h+NewElement]; NewElement
0x140107395  mov     rdx, r14; Buffer
0x140107398  mov     rcx, r12; Table
0x14010739b  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1401073a2  nop     dword ptr [rax+rax+00h]
0x1401073a7  or      byte ptr [rax+1Eh], 1
0x1401073ab  mov     cl, [rax+1Eh]
0x1401073ae  or      cl, 10h
0x1401073b1  mov     [rax+1Eh], cl
0x1401073b4  or      cl, 20h
0x1401073b7  mov     [rax+1Eh], cl
0x1401073ba  mov     byte ptr [rsp+288h+RestartKey], bl
0x1401073be  mov     r9d, [rax+18h]
0x1401073c2  mov     r8, [rax+8]
0x1401073c6  mov     rdx, r15
0x1401073c9  mov     rcx, [rsp+288h+var_1C8]
0x1401073d1  mov     rcx, [rcx+0D0h]
0x1401073d8  call    TxfDirectlyAllocateTopsRange
0x1401073dd  nop
0x1401073de  test    rdi, rdi
0x1401073e1  jz      short loc_1401073F6
0x1401073e3  mov     rcx, [rdi+88h]; Resource
0x1401073ea  call    cs:__imp_ExReleaseResourceLite
0x1401073f1  nop     dword ptr [rax+rax+00h]
0x1401073f6  test    r13b, r13b
0x1401073f9  jz      short loc_14010740F
0x1401073fb  movups  xmmword ptr [rbx], xmm6
0x1401073fe  movups  xmmword ptr [rbx+10h], xmm7
0x140107402  movups  xmmword ptr [rbx+20h], xmm8
0x140107407  mov     rax, [rsp+288h+var_218]
0x14010740c  mov     [rbx+30h], eax
0x14010740f  mov     rcx, [r15+100h]; FastMutex
0x140107416  call    cs:__imp_ExReleaseFastMutex
0x14010741d  nop     dword ptr [rax+rax+00h]
0x140107422  mov     rdx, [rsp+288h+Entry]; Entry
0x140107427  test    rdx, rdx
0x14010742a  jz      short loc_14010743F
0x14010742c  lea     rcx, TxfTopsRangeEntryLookasideList; Lookaside
0x140107433  call    cs:__imp_ExFreeToLookasideListEx
0x14010743a  nop     dword ptr [rax+rax+00h]
0x14010743f  xor     eax, eax
0x140107441  mov     rcx, [rsp+288h+var_78]
0x140107449  xor     rcx, rsp; StackCookie
0x14010744c  call    __security_check_cookie
0x140107451  lea     r11, [rsp+288h+var_38]
0x140107459  movaps  xmm6, xmmword ptr [r11-10h]
0x14010745e  movaps  xmm7, xmmword ptr [r11-20h]
0x140107463  movaps  xmm8, xmmword ptr [r11-30h]
0x140107468  mov     rsp, r11
0x14010746b  pop     r15
0x14010746d  pop     r14
0x14010746f  pop     r13
0x140107471  pop     r12
0x140107473  pop     rdi
0x140107474  pop     rsi
0x140107475  pop     rbx
0x140107476  retn
0x140107478  mov     rdi, [r14]
0x14010747b  mov     rdx, [rax]
0x14010747e  cmp     rdx, rdi
0x140107481  jnb     loc_1401076BB
0x140107487  mov     r9d, [rax+18h]
0x14010748b  add     rax, 18h
0x14010748f  mov     [rsp+288h+var_1C0], rax
0x140107497  lea     r8, [rbx+20h]
0x14010749b  mov     [rsp+288h+var_1B8], r8
0x1401074a3  mov     esi, edi
0x1401074a5  sub     esi, edx
0x1401074a7  mov     ecx, [r14+18h]
0x1401074ab  add     rcx, rdi
0x1401074ae  lea     rax, [rdx+r9]
0x1401074b2  cmp     rcx, rax
0x1401074b5  jnb     loc_140107670
0x1401074bb  movups  xmm6, xmmword ptr [rbx]
0x1401074be  movups  [rsp+288h+var_200], xmm6
0x1401074c6  movups  xmm7, xmmword ptr [rbx+10h]
0x1401074ca  movups  [rsp+288h+var_1F0], xmm7
0x1401074d2  movups  xmm8, xmmword ptr [rbx+20h]
0x1401074d7  movups  [rsp+288h+var_1E0], xmm8
0x1401074e0  mov     eax, [rbx+30h]
0x1401074e3  mov     [rsp+288h+var_218], rax
0x1401074e8  mov     [rsp+288h+var_1D0], eax
0x1401074ef  mov     [rsp+288h+var_248], 1
0x1401074f4  mov     [rbx+18h], esi
0x1401074f7  shl     esi, 0Ch
0x1401074fa  mov     [r8], esi
0x1401074fd  movsd   [rsp+288h+var_1A8], xmm6
0x140107506  movdqa  xmm0, xmm6
0x14010750a  psrldq  xmm0, 8
0x14010750f  movq    [rsp+288h+var_1A0], xmm0
0x140107518  mov     rax, qword ptr [rsp+288h+var_1F0]
0x140107520  mov     [rsp+288h+var_198], rax
0x140107528  movdqa  xmm0, xmm7
0x14010752c  psrldq  xmm0, 8
0x140107531  movd    r9d, xmm0
0x140107536  mov     [rsp+288h+var_190], r9d
0x14010753e  movdqa  xmm1, xmm7
0x140107542  psrldq  xmm1, 8
0x140107547  movq    rax, xmm1
0x14010754c  shr     rax, 20h
0x140107550  mov     [rsp+288h+var_18C], eax
0x140107557  movd    ecx, xmm8
0x14010755c  mov     [rsp+288h+var_188], ecx
0x140107563  movups  xmm0, [rsp+288h+var_1E0+4]
0x14010756b  movdqu  [rsp+288h+var_184], xmm0
0x140107574  mov     edx, [r14+18h]
0x140107578  mov     r8d, r9d
0x14010757b  sub     r8d, edx
0x14010757e  sub     r8d, [rbx+18h]
0x140107582  mov     [rsp+288h+var_190], r8d
0x14010758a  mov     eax, edx
0x14010758c  shl     eax, 0Ch
0x14010758f  sub     ecx, eax
0x140107591  mov     eax, [rbx+18h]
0x140107594  shl     eax, 0Ch
0x140107597  sub     ecx, eax
0x140107599  mov     [rsp+288h+var_188], ecx
0x1401075a0  mov     rcx, [r14]
0x1401075a3  add     rcx, rdx
0x1401075a6  mov     [rsp+288h+var_1A8], rcx
0x1401075ae  mov     eax, [rbx+18h]
0x1401075b1  add     rax, rdx
0x1401075b4  add     rax, [rbx+8]
0x1401075b8  mov     [rsp+288h+var_1A0], rax
0x1401075c0  sub     r9d, r8d
0x1401075c3  mov     edx, r11d
0x1401075c6  mov     [rsp+288h+var_244], edx
0x1401075ca  lea     eax, ds:0[r8*8]
0x1401075d2  cmp     edx, eax
0x1401075d4  jnb     short loc_1401075F9
0x1401075d6  lea     eax, [rdx+r9*8]
0x1401075da  mov     ecx, edx
0x1401075dc  movzx   eax, word ptr [rbx+rax*2+24h]
0x1401075e1  mov     word ptr [rsp+rcx*2+288h+var_184], ax
0x1401075e9  inc     edx
0x1401075eb  mov     [rsp+288h+var_244], edx
0x1401075ef  mov     r8d, [rsp+288h+var_190]
0x1401075f7  jmp     short loc_1401075CA
0x1401075f9  dec     r8d
0x1401075fc  shl     r8d, 4
0x140107600  add     r8d, 34h ; '4'; BufferSize
0x140107604  lea     r9, [rsp+288h+NewElement]; NewElement
0x140107609  lea     rdx, [rsp+288h+var_1A8]; Buffer
0x140107611  mov     rcx, r12; Table
0x140107614  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14010761b  nop     dword ptr [rax+rax+00h]
0x140107620  xor     r13b, r13b
0x140107623  mov     [rsp+288h+var_248], r13b
0x140107628  or      byte ptr [rax+1Eh], 1
0x14010762c  mov     cl, [rax+1Eh]
0x14010762f  or      cl, 8
0x140107632  mov     [rax+1Eh], cl
0x140107635  or      cl, 20h
0x140107638  mov     [rax+1Eh], cl
0x14010763b  mov     r8d, [rbx+18h]
0x14010763f  add     r8, [rbx+8]
0x140107643  mov     [rsp+288h+DeleteCount], 0
0x14010764c  lea     rax, [rsp+288h+Entry]
0x140107651  mov     [rsp+288h+RestartKey], rax
0x140107656  mov     r9d, [r14+18h]
0x14010765a  mov     rdx, r15
0x14010765d  mov     rsi, [rsp+288h+var_228]
0x140107662  mov     rcx, [rsi+10h]
0x140107666  call    TxfInsertNewTopsRange
0x14010766b  jmp     loc_140107773
0x140107670  sub     r9d, esi
0x140107673  mov     r8d, esi
0x140107676  add     r8, [rbx+8]
0x14010767a  mov     [rsp+288h+DeleteCount], r11
0x14010767f  lea     rax, [rsp+288h+Entry]
0x140107684  mov     [rsp+288h+RestartKey], rax
0x140107689  mov     rdx, r15
0x14010768c  mov     rcx, [rsp+288h+var_228]
0x140107691  mov     rcx, [rcx+10h]
0x140107695  call    TxfInsertNewTopsRange
0x14010769a  mov     rax, [rsp+288h+var_1C0]
0x1401076a2  mov     [rax], esi
0x1401076a4  shl     esi, 0Ch
0x1401076a7  mov     rax, [rsp+288h+var_1B8]
0x1401076af  mov     [rax], esi
0x1401076b1  mov     rsi, [rsp+288h+var_228]
0x1401076b6  jmp     loc_140107773
0x1401076bb  mov     r9d, [r14+18h]
0x1401076bf  mov     r8, [rax+8]
0x1401076c3  mov     ecx, [rax+18h]
0x1401076c6  add     rcx, rdx
0x1401076c9  lea     rax, [rdi+r9]
0x1401076cd  cmp     rax, rcx
0x1401076d0  jnb     short loc_14010773C
0x1401076d2  sub     edi, edx
0x1401076d4  add     edi, r9d
0x1401076d7  mov     [rsp+288h+DeleteCount], r11
0x1401076dc  lea     rax, [rsp+288h+Entry]
0x1401076e1  mov     [rsp+288h+RestartKey], rax
0x1401076e6  mov     r9d, edi
0x1401076e9  mov     rdx, r15
0x1401076ec  mov     rcx, [rsi+10h]
0x1401076f0  call    TxfInsertNewTopsRange
0x1401076f5  lea     r8d, ds:0[rdi*8]
0x1401076fd  xor     edx, edx
0x1401076ff  mov     [rsp+288h+var_244], edx
0x140107703  mov     ecx, [rbx+18h]
0x140107706  sub     ecx, edi
0x140107708  lea     eax, ds:0[rcx*8]
0x14010770f  cmp     edx, eax
0x140107711  jnb     short loc_140107728
  ... truncated ...
```
