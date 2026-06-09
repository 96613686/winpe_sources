# CmsVolume::InitializeUpcaseTable(CmsTransactionContext *,_MS_CREATE_DISPOSITION)

- ea: `0x1c002af24`
- end: `0x1c002b223`
- name: `?InitializeUpcaseTable@CmsVolume@@AEAAJPEAVCmsTransactionContext@@W4_MS_CREATE_DISPOSITION@@@Z`
- size: `767`
- prototype: `int __high(struct CmsTransactionContext *, enum _MS_CREATE_DISPOSITION)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1c0050ad0`

## callees

- `0x1c0001b70`
- `0x1c0002774`
- `0x1c00224d0`
- `0x1c002af24`
- `0x1c002b230`
- `0x1c0049c8c`
- `0x1c0053ab4`
- `0x1c0068960`
- `0x1c006acc0`
- `0x1c00b10c0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002b0b0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002b0b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c002b125`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c002b1fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007c19d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c002b125`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c002b1fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007c19d`
- `ntoskrnl!RtlCompareMemory` at `0x1c002b1d0`
- `ntoskrnl!RtlCompareMemory` at `0x1c002b1d0`

## pseudocode

```c
__int64 __fastcall CmsVolume::InitializeUpcaseTable(__int64 a1, struct CmsTransactionContext *a2)
{
  int v4; // edi
  unsigned int v5; // edi
  int v6; // edx
  int v7; // esi
  bool v8; // cc
  bool v9; // of
  SIZE_T v10; // rax
  PVOID PoolWithTag; // rax
  unsigned __int8 v12; // r9
  bool v13; // zf
  __int64 v14; // rax
  CmsVolume *v15; // rcx
  void *v17; // rcx
  PVOID v18; // rax
  int v19; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  int *v22; // [rsp+50h] [rbp-B0h]
  __int128 v23; // [rsp+58h] [rbp-A8h]
  unsigned int v24; // [rsp+70h] [rbp-90h] BYREF
  int *v25; // [rsp+78h] [rbp-88h]
  size_t Size; // [rsp+80h] [rbp-80h]
  void *Src; // [rsp+88h] [rbp-78h]
  PVOID P; // [rsp+90h] [rbp-70h]
  char v29; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+9Ch] [rbp-64h]
  char v31; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v32[42]; // [rsp+E0h] [rbp-20h] BYREF

  v20[0] = 8;
  v20[1] = 7;
  v4 = CmsVolume::InitializeFailoverMetadataTable(a1, a2, v20);
  if ( v4 < 0 )
    goto LABEL_40;
  v21[1] = 0;
  v19 = 0;
  P = &v31;
  v30 = 64;
  v22 = &v19;
  v23 = 0;
  v29 = 0;
  v5 = 0;
  v21[0] = 4;
  CmsTableCursor::CmsTableCursor((CmsTableCursor *)v32, 0, (const struct _CmsRow *)v21, (const struct _CmsRow *)v21);
  Src = 0;
  v32[0] = &CmsMatchAllCursor::`vftable';
  while ( 1 )
  {
    v6 = CmsFailoverBPlusTable::Enumerate(
           0,
           a2,
           (struct CmsTableCursor *)v32,
           Src != 0 ? 5 : 1,
           (struct CmsRowWithBuffer *)&v24,
           0);
    if ( v6 < 0 )
      break;
    if ( v24 < 4 )
      goto LABEL_35;
    v7 = *v25;
    if ( *v25 )
    {
      v8 = v7 == 1;
      if ( v7 == 1 )
      {
        if ( (unsigned int)Size < 4 )
        {
LABEL_35:
          v6 = -1073741774;
          break;
        }
        v10 = 2LL * *(unsigned int *)Src;
        v9 = (*(unsigned int *)Src * (unsigned __int128)2uLL) >> 64 != 0;
        *(_DWORD *)(a1 + 3128) = *(_DWORD *)Src;
        if ( v9 )
          v10 = -1;
        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v10, 0x6950534Du);
        *(_QWORD *)(a1 + 3120) = PoolWithTag;
        if ( !PoolWithTag )
        {
          v6 = -1073741670;
          break;
        }
        *(_DWORD *)(a1 + 3116) |= 0x20000u;
        v8 = 1;
      }
      if ( !v8 )
      {
        if ( (unsigned int)Size + v5 > 2 * (unsigned __int64)*(unsigned int *)(a1 + 3128) )
          goto LABEL_35;
        memmove((void *)(*(_QWORD *)(a1 + 3120) + v5), Src, (unsigned int)Size);
        v5 += Size;
      }
    }
  }
  if ( v5 != 2LL * *(unsigned int *)(a1 + 3128) || !v5 )
    v6 = -1073741774;
  v4 = 0;
  if ( v6 != -1073741197 )
    v4 = v6;
  CmsTableCursor::~CmsTableCursor((CmsTableCursor *)v32);
  if ( v4 < 0 )
  {
    if ( v29 && P )
      ExFreePoolWithTag(P, 0);
  }
  else
  {
    if ( v29 && P )
      ExFreePoolWithTag(P, 0);
    if ( (*(_DWORD *)(a1 + 3116) & 0x20000) != 0 )
    {
      v13 = _InterlockedCompareExchange64((volatile signed __int64 *)&FirstUpcaseTable, *(_QWORD *)(a1 + 3120), 0) == 0;
      v14 = *(unsigned int *)(a1 + 3128);
      if ( v13 )
      {
        FirstUpcaseTableSize = *(_DWORD *)(a1 + 3128);
      }
      else if ( FirstUpcaseTableSize == (_DWORD)v14
             && RtlCompareMemory(FirstUpcaseTable, *(const void **)(a1 + 3120), 2 * v14) == 2LL
                                                                                          * *(unsigned int *)(a1 + 3128) )
      {
        v17 = *(void **)(a1 + 3120);
        if ( v17 )
          ExFreePoolWithTag(v17, 0);
        v18 = FirstUpcaseTable;
        *(_DWORD *)(a1 + 3116) &= ~0x20000u;
        *(_QWORD *)(a1 + 3120) = v18;
      }
    }
  }
  if ( v4 < 0 )
LABEL_40:
    CmsTransactionContext::Abort(a2);
  else
    CmsTransactionContext::Commit(a2, 0, 0, v12);
  CmsVolume::CloseFailoverMetadataTable(v15, a2, 0, byte_1C0136978 == 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1c002af24  mov     [rsp-8+arg_10], rbx
0x1c002af29  mov     [rsp-8+arg_18], rsi
0x1c002af2e  push    rbp
0x1c002af2f  push    rdi
0x1c002af30  push    r14
0x1c002af32  lea     rbp, [rsp-140h]
0x1c002af3a  sub     rsp, 240h
0x1c002af41  mov     rax, cs:__security_cookie
0x1c002af48  xor     rax, rsp
0x1c002af4b  mov     [rbp+150h+var_20], rax
0x1c002af52  and     [rsp+250h+var_220], 0
0x1c002af58  lea     rax, [rsp+250h+var_220]
0x1c002af5d  lea     r8, [rsp+250h+var_210]
0x1c002af62  mov     [rsp+250h+var_230], rax
0x1c002af67  mov     r14, rdx
0x1c002af6a  mov     [rsp+250h+var_210], 8
0x1c002af72  mov     rbx, rcx
0x1c002af75  mov     [rsp+250h+var_20C], 7
0x1c002af7d  call    ?InitializeFailoverMetadataTable@CmsVolume@@AEAAJPEAVCmsTransactionContext@@QEAKW4_MS_CREATE_DISPOSITION@@PEAPEAVCmsFailoverBPlusTable@@@Z; CmsVolume::InitializeFailoverMetadataTable(CmsTransactionContext *,ulong * const,_MS_CREATE_DISPOSITION,CmsFailoverBPlusTable * *)
0x1c002af82  mov     edi, eax
0x1c002af84  test    eax, eax
0x1c002af86  js      loc_1C007C1AF
0x1c002af8c  mov     rdx, [rsp+250h+var_220]; struct CmsTable *
0x1c002af91  lea     rax, [rbp+150h+var_1B0]
0x1c002af95  and     [rsp+250h+var_204], 0
0x1c002af9a  lea     r9, [rsp+250h+var_208]; struct _CmsRow *
0x1c002af9f  and     [rsp+250h+var_218], 0
0x1c002afa4  lea     r8, [rsp+250h+var_208]; struct _CmsRow *
0x1c002afa9  mov     [rbp+150h+P], rax
0x1c002afad  lea     rcx, [rbp+150h+var_170]; this
0x1c002afb1  lea     rax, [rsp+250h+var_218]
0x1c002afb6  mov     [rbp+150h+var_1B4], 40h ; '@'
0x1c002afbd  xorps   xmm0, xmm0
0x1c002afc0  mov     [rsp+250h+var_200], rax
0x1c002afc5  movdqu  [rsp+250h+var_1F8], xmm0
0x1c002afcb  mov     [rbp+150h+var_1B8], 0
0x1c002afcf  xor     edi, edi
0x1c002afd1  mov     [rsp+250h+var_208], 4
0x1c002afd9  call    ??0CmsTableCursor@@QEAA@PEAVCmsTable@@PEBU_CmsRow@@1@Z; CmsTableCursor::CmsTableCursor(CmsTable *,_CmsRow const *,_CmsRow const *)
0x1c002afde  and     [rbp+150h+Src], rdi
0x1c002afe2  lea     rax, ??_7CmsMatchAllCursor@@6B@; const CmsMatchAllCursor::`vftable'
0x1c002afe9  mov     [rbp+150h+var_170], rax
0x1c002afed  mov     rax, [rbp+150h+Src]
0x1c002aff1  lea     r8, [rbp+150h+var_170]; struct CmsTableCursor *
0x1c002aff5  mov     rcx, [rsp+250h+var_220]; this
0x1c002affa  neg     rax
0x1c002affd  lea     rax, [rsp+250h+var_1E0]
0x1c002b002  mov     [rsp+250h+var_228], 0; char
0x1c002b007  sbb     r9d, r9d
0x1c002b00a  mov     [rsp+250h+var_230], rax; struct CmsRowWithBuffer *
0x1c002b00f  and     r9d, 4
0x1c002b013  mov     rdx, r14; struct CmsTransactionContext *
0x1c002b016  inc     r9d; unsigned int
0x1c002b019  call    ?Enumerate@CmsFailoverBPlusTable@@UEAAJPEAVCmsTransactionContext@@PEAVCmsTableCursor@@KPEAVCmsRowWithBuffer@@E@Z; CmsFailoverBPlusTable::Enumerate(CmsTransactionContext *,CmsTableCursor *,ulong,CmsRowWithBuffer *,uchar)
0x1c002b01e  mov     edx, eax
0x1c002b020  test    eax, eax
0x1c002b022  js      loc_1C002B0DC
0x1c002b028  cmp     [rsp+250h+var_1E0], 4
0x1c002b02d  jb      loc_1C007C170
0x1c002b033  mov     rax, [rsp+250h+var_1D8]
0x1c002b038  mov     esi, [rax]
0x1c002b03a  test    esi, esi
0x1c002b03c  jz      short loc_1C002AFED
0x1c002b03e  cmp     esi, 1
0x1c002b041  jz      short loc_1C002B079
0x1c002b043  jbe     short loc_1C002AFED
0x1c002b045  mov     r8d, dword ptr [rbp+150h+Size]; Size
0x1c002b049  mov     edx, [rbx+0C38h]
0x1c002b04f  add     rdx, rdx
0x1c002b052  lea     ecx, [r8+rdi]
0x1c002b056  cmp     rcx, rdx
0x1c002b059  ja      loc_1C007C170
0x1c002b05f  mov     rdx, [rbp+150h+Src]; Src
0x1c002b063  mov     ecx, edi
0x1c002b065  add     rcx, [rbx+0C30h]; void *
0x1c002b06c  call    memmove
0x1c002b071  add     edi, dword ptr [rbp+150h+Size]
0x1c002b074  jmp     loc_1C002AFED
0x1c002b079  cmp     dword ptr [rbp+150h+Size], 4
0x1c002b07d  jb      loc_1C007C170
0x1c002b083  mov     rax, [rbp+150h+Src]
0x1c002b087  mov     r8d, 6950534Dh; Tag
0x1c002b08d  mov     ecx, [rax]
0x1c002b08f  mov     eax, 2
0x1c002b094  mul     rcx
0x1c002b097  mov     [rbx+0C38h], ecx
0x1c002b09d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1c002b0a4  cmovo   rax, rcx
0x1c002b0a8  mov     ecx, 200h; PoolType
0x1c002b0ad  mov     rdx, rax; NumberOfBytes
0x1c002b0b0  call    cs:__imp_ExAllocatePoolWithTag
0x1c002b0b7  nop     dword ptr [rax+rax+00h]
0x1c002b0bc  mov     [rbx+0C30h], rax
0x1c002b0c3  test    rax, rax
0x1c002b0c6  jz      loc_1C007C166
0x1c002b0cc  bts     dword ptr [rbx+0C2Ch], 11h
0x1c002b0d4  cmp     esi, 1
0x1c002b0d7  jmp     loc_1C002B043
0x1c002b0dc  mov     ecx, [rbx+0C38h]
0x1c002b0e2  add     rcx, rcx
0x1c002b0e5  mov     eax, edi
0x1c002b0e7  cmp     rax, rcx
0x1c002b0ea  jnz     loc_1C007C17A
0x1c002b0f0  test    edi, edi
0x1c002b0f2  jz      loc_1C007C17A
0x1c002b0f8  xor     edi, edi
0x1c002b0fa  lea     rcx, [rbp+150h+var_170]; this
0x1c002b0fe  cmp     edx, 0C0000273h
0x1c002b104  cmovnz  edi, edx
0x1c002b107  call    ??1CmsTableCursor@@UEAA@XZ; CmsTableCursor::~CmsTableCursor(void)
0x1c002b10c  test    edi, edi
0x1c002b10e  js      loc_1C007C184
0x1c002b114  cmp     [rbp+150h+var_1B8], 0
0x1c002b118  jz      short loc_1C002B131
0x1c002b11a  mov     rcx, [rbp+150h+P]; P
0x1c002b11e  test    rcx, rcx
0x1c002b121  jz      short loc_1C002B131
0x1c002b123  xor     edx, edx; Tag
0x1c002b125  call    cs:__imp_ExFreePoolWithTag
0x1c002b12c  nop     dword ptr [rax+rax+00h]
0x1c002b131  test    dword ptr [rbx+0C2Ch], 20000h
0x1c002b13b  jz      short loc_1C002B15D
0x1c002b13d  mov     rcx, [rbx+0C30h]
0x1c002b144  xor     eax, eax
0x1c002b146  lock cmpxchg cs:?FirstUpcaseTable@@3PEAGEA, rcx; ushort * FirstUpcaseTable
0x1c002b14f  mov     eax, [rbx+0C38h]
0x1c002b155  jnz     short loc_1C002B1B4
0x1c002b157  mov     cs:?FirstUpcaseTableSize@@3KA, eax; ulong FirstUpcaseTableSize
0x1c002b15d  test    edi, edi
0x1c002b15f  js      loc_1C007C1AF
0x1c002b165  xor     r8d, r8d; struct _SmsLsn *
0x1c002b168  xor     edx, edx; unsigned __int8
0x1c002b16a  mov     rcx, r14; this
0x1c002b16d  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x1c002b172  cmp     cs:byte_1C0136978, 0
0x1c002b179  mov     rdx, r14; struct CmsTransactionContext *
0x1c002b17c  mov     r8, [rsp+250h+var_220]; struct CmsFailoverBPlusTable *
0x1c002b181  setz    r9b; unsigned __int8
0x1c002b185  call    ?CloseFailoverMetadataTable@CmsVolume@@AEAAXPEAVCmsTransactionContext@@PEAVCmsFailoverBPlusTable@@E@Z; CmsVolume::CloseFailoverMetadataTable(CmsTransactionContext *,CmsFailoverBPlusTable *,uchar)
0x1c002b18a  mov     eax, edi
0x1c002b18c  mov     rcx, [rbp+150h+var_20]
0x1c002b193  xor     rcx, rsp; StackCookie
0x1c002b196  call    __security_check_cookie
0x1c002b19b  lea     r11, [rsp+250h+var_10]
0x1c002b1a3  mov     rbx, [r11+30h]
0x1c002b1a7  mov     rsi, [r11+38h]
0x1c002b1ab  mov     rsp, r11
0x1c002b1ae  pop     r14
0x1c002b1b0  pop     rdi
0x1c002b1b1  pop     rbp
0x1c002b1b2  retn
0x1c002b1b4  cmp     cs:?FirstUpcaseTableSize@@3KA, eax; ulong FirstUpcaseTableSize
0x1c002b1ba  jnz     short loc_1C002B15D
0x1c002b1bc  mov     rdx, [rbx+0C30h]; Source2
0x1c002b1c3  mov     r8, rax
0x1c002b1c6  mov     rcx, cs:?FirstUpcaseTable@@3PEAGEA; Source1
0x1c002b1cd  add     r8, r8; Length
0x1c002b1d0  call    cs:__imp_RtlCompareMemory
0x1c002b1d7  nop     dword ptr [rax+rax+00h]
0x1c002b1dc  mov     ecx, [rbx+0C38h]
0x1c002b1e2  add     rcx, rcx
0x1c002b1e5  cmp     rax, rcx
0x1c002b1e8  jnz     loc_1C002B15D
0x1c002b1ee  mov     rcx, [rbx+0C30h]; P
0x1c002b1f5  test    rcx, rcx
0x1c002b1f8  jz      short loc_1C002B208
0x1c002b1fa  xor     edx, edx; Tag
0x1c002b1fc  call    cs:__imp_ExFreePoolWithTag
0x1c002b203  nop     dword ptr [rax+rax+00h]
0x1c002b208  mov     rax, cs:?FirstUpcaseTable@@3PEAGEA; ushort * FirstUpcaseTable
0x1c002b20f  btr     dword ptr [rbx+0C2Ch], 11h
0x1c002b217  mov     [rbx+0C30h], rax
0x1c002b21e  jmp     loc_1C002B15D
0x1c007c166  mov     edx, 0C000009Ah
0x1c007c16b  jmp     loc_1C002B0DC
0x1c007c170  mov     edx, 0C0000032h
0x1c007c175  jmp     loc_1C002B0DC
0x1c007c17a  mov     edx, 0C0000032h
0x1c007c17f  jmp     loc_1C002B0F8
0x1c007c184  cmp     [rbp+150h+var_1B8], 0
0x1c007c188  jz      loc_1C002B15D
0x1c007c18e  mov     rcx, [rbp+150h+P]; P
0x1c007c192  test    rcx, rcx
0x1c007c195  jz      loc_1C002B15D
0x1c007c19b  xor     edx, edx; Tag
0x1c007c19d  call    cs:__imp_ExFreePoolWithTag
0x1c007c1a4  nop     dword ptr [rax+rax+00h]
0x1c007c1a9  nop
0x1c007c1aa  jmp     loc_1C002B15D
0x1c007c1af  mov     rcx, r14; this
0x1c007c1b2  call    ?Abort@CmsTransactionContext@@QEAAXXZ; CmsTransactionContext::Abort(void)
0x1c007c1b7  nop
0x1c007c1b8  jmp     loc_1C002B172
```
