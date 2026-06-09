# NtfsBuildAlignedMdl

- ea: `0x140032768`
- end: `0x140032d05`
- name: `NtfsBuildAlignedMdl`
- size: `1437`
- prototype: `_QWORD *__fastcall(__int64, __int64, __int64, __int64, unsigned int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140245ba8`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x140032768`
- `0x140059234`
- `0x1400593c0`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14005b705`
- `ntoskrnl!MmUnmapLockedPages` at `0x14005b705`
- `ntoskrnl!IoAllocateMdl` at `0x140032978`
- `ntoskrnl!IoAllocateMdl` at `0x140032978`
- `ntoskrnl!IoFreeMdl` at `0x14005b715`
- `ntoskrnl!IoFreeMdl` at `0x14005b715`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400329a4`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400329a4`
- `ntoskrnl!MmMdlPageContentsState` at `0x140032a6a`
- `ntoskrnl!MmMdlPageContentsState` at `0x140032a7b`
- `ntoskrnl!MmMdlPageContentsState` at `0x140032a6a`
- `ntoskrnl!MmMdlPageContentsState` at `0x140032a7b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005b74a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005b74a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400327ce`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400327ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b72d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b72d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003293e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003293e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140032b0f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140032b4e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140032b0f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140032b4e`

## pseudocode

```c
_QWORD *__fastcall NtfsBuildAlignedMdl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        _QWORD *a7)
{
  struct _MDL *v10; // r15
  _QWORD *v11; // rbx
  __int64 v12; // r14
  unsigned __int64 v13; // r8
  __int64 v14; // rsi
  unsigned __int64 MappedSystemVa; // r15
  unsigned __int64 v16; // r13
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rsi
  unsigned __int64 v19; // r12
  unsigned __int64 v20; // r14
  PMDL Mdl; // rsi
  size_t v22; // rax
  unsigned __int64 v23; // r12
  struct _MDL *v24; // r15
  CSHORT v25; // ax
  PVOID v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *result; // rax
  __int64 v30; // [rsp+0h] [rbp-E8h] BYREF
  unsigned __int64 v31; // [rsp+30h] [rbp-B8h]
  unsigned int v32; // [rsp+38h] [rbp-B0h]
  int v33; // [rsp+3Ch] [rbp-ACh]
  PMDL v34; // [rsp+40h] [rbp-A8h]
  char *v35; // [rsp+48h] [rbp-A0h]
  _QWORD *v36; // [rsp+50h] [rbp-98h]
  void *v37; // [rsp+58h] [rbp-90h]
  unsigned __int64 v38; // [rsp+60h] [rbp-88h]
  unsigned __int64 v39; // [rsp+68h] [rbp-80h]
  SIZE_T v40; // [rsp+70h] [rbp-78h]
  struct _MDL *v41; // [rsp+78h] [rbp-70h]
  char *PoolWithTag; // [rsp+80h] [rbp-68h]
  __int64 v43; // [rsp+88h] [rbp-60h]
  __int64 v44; // [rsp+90h] [rbp-58h]
  _QWORD *v45; // [rsp+98h] [rbp-50h]
  __int64 *v46; // [rsp+A0h] [rbp-48h]

  v46 = &v30;
  v44 = a4;
  v43 = a2;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v10 = *(struct _MDL **)(a2 + 8);
  v41 = v10;
  v45 = a7;
  *a7 = 0;
  v11 = ExAllocateFromLookasideListEx(&NtfsAlignedMdlContextLookasideList);
  v36 = v11;
  v33 = a6;
  v12 = a4 & -a6;
  v32 = a5;
  v13 = a5;
  v31 = a5;
  v14 = -a6 & (a4 + a5 + (__int64)(a6 - 1));
  if ( v12 == a4 && v14 == a5 + a4 )
  {
    local_unwind_0(v46, &loc_140032CF1);
LABEL_38:
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC000009A, 0xC2C10u);
    NtfsRaiseStatusInternal(a1, -1073741670, 0, 0, 797712);
  }
  if ( (v10->MdlFlags & 5) != 0 )
  {
    MappedSystemVa = (unsigned __int64)v10->MappedSystemVa;
  }
  else
  {
    MappedSystemVa = (unsigned __int64)MmMapLockedPagesSpecifyCache(
                                         v10,
                                         0,
                                         MmCached,
                                         0,
                                         0,
                                         ((v10->MdlFlags & 0x40) != 0 ? 32 : 16) | 0x40000000u);
    v13 = v31;
  }
  if ( !MappedSystemVa )
    goto LABEL_38;
  if ( v14 <= v12
    || v14 > *(_QWORD *)(a3 + 24)
    || v14 - v12 > 0xFFFFFFFFLL
    || (v16 = v12 + MappedSystemVa - a4, v16 > MappedSystemVa)
    || (v17 = v13 + MappedSystemVa, v13 + MappedSystemVa <= MappedSystemVa)
    || (v18 = MappedSystemVa - a4 + v14, v18 < v17) )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0xC2C28u);
    NtfsRaiseStatusInternal(a1, -1073741811, 0, 0, 797736);
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 192) + 248LL) + 8LL) + 152LL) & (unsigned int)v16) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC0000474, 0xC2C32u);
    NtfsRaiseStatusInternal(a1, -1073740684, 0, 0, 797746);
  }
  if ( v16 >= MappedSystemVa )
    v19 = 0;
  else
    v19 = ((unsigned __int64)(((_WORD)v12 + (_WORD)MappedSystemVa - (_WORD)a4) & 0xFFF) - (v12 - a4) + 4095) >> 12;
  if ( v18 <= v17 )
  {
    v20 = 0;
LABEL_16:
    v39 = v20;
    goto LABEL_17;
  }
  v20 = (v18 + (v17 & 0xFFF) - v17 + 4095) >> 12;
  v39 = v20;
  if ( v19 && (v17 & 0xFFFFFFFFFFFFF000uLL) < MappedSystemVa )
  {
    --v20;
    goto LABEL_16;
  }
LABEL_17:
  v31 = v16 & 0xFFF;
  v38 = (v18 - v16 + 4095 + v31) >> 12;
  v40 = (v20 + v19) << 12;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)528, v40, 0x4446744Eu);
  v35 = PoolWithTag;
  v37 = (void *)(unsigned int)(v18 - v16);
  Mdl = IoAllocateMdl(&PoolWithTag[v31], (int)v18 - (int)v16, 0, 0, 0);
  v34 = Mdl;
  if ( !Mdl )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC000009A, 0xC2C88u);
    NtfsRaiseStatusInternal(a1, -1073741670, 0, 0, 797832);
  }
  Mdl->ByteCount = v40 - v31;
  MmBuildMdlForNonPagedPool(Mdl);
  Mdl->ByteCount = (unsigned int)v37;
  if ( v38 - v20 == v19 )
  {
    v27 = 1;
  }
  else
  {
    v37 = &Mdl[1].Next + v19;
    v22 = 8 * (v38 - v20 - v19);
    v38 = v22;
    if ( v20 )
    {
      memmove((char *)&Mdl[1].Next + 8 * v19 + v22, &Mdl[1].Next + v19, 8 * v20);
      v22 = v38;
    }
    v23 = (v19 << 12) - (MappedSystemVa & 0xFFFFFFFFFFFFF000uLL);
    v24 = v41;
    memmove(v37, &v41[1].Next + ((v23 + (v16 & 0xFFFFFFFFFFFFF000uLL)) >> 12), v22);
    Mdl->MdlFlags &= ~4u;
    v25 = Mdl->MdlFlags | 0x10;
    Mdl->MdlFlags = v25;
    if ( (v25 & 5) != 0 )
      v26 = Mdl->MappedSystemVa;
    else
      v26 = MmMapLockedPagesSpecifyCache(Mdl, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v26 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC000009A, 0xC2CCCu);
      NtfsRaiseStatusInternal(a1, -1073741670, 0, 0, 797900);
    }
    Mdl->StartVa = (PVOID)((unsigned __int64)Mdl->MappedSystemVa & 0xFFFFFFFFFFFFF000uLL);
    v27 = (unsigned int)MmMdlPageContentsState(v24, 2);
  }
  MmMdlPageContentsState(Mdl, v27);
  v11[2] = 0;
  v11[3] = 0;
  v11[4] = 0;
  v11[5] = 0;
  v11[1] = PoolWithTag;
  *v11 = Mdl;
  v28 = v43;
  v11[2] = *(_QWORD *)(v43 + 8);
  v11[3] = *(_QWORD *)(v28 + 112);
  v11[4] = v44;
  *((_DWORD *)v11 + 10) = v32;
  *((_DWORD *)v11 + 11) = v33;
  result = v45;
  *v45 = v11;
  return result;
}

```

## disassembly

```asm
0x140032768  mov     r11, rsp
0x14003276b  mov     [r11+20h], r9
0x14003276f  mov     [r11+18h], r8
0x140032773  mov     [r11+10h], rdx
0x140032777  push    rbx
0x140032778  push    rsi
0x140032779  push    rdi
0x14003277a  push    r12
0x14003277c  push    r13
0x14003277e  push    r14
0x140032780  push    r15
0x140032782  sub     rsp, 0B0h
0x140032789  mov     [rsp+0E8h+var_48], rsp
0x140032791  mov     r12, r9
0x140032794  mov     [r11-58h], r9
0x140032798  mov     r13, r8
0x14003279b  mov     [r11-60h], rdx
0x14003279f  mov     rdi, rcx
0x1400327a2  xor     ecx, ecx
0x1400327a4  mov     [rsp+0E8h+var_98], rcx
0x1400327a9  mov     [rsp+0E8h+var_A0], rcx
0x1400327ae  mov     [rsp+0E8h+var_A8], rcx
0x1400327b3  mov     r15, [rdx+8]
0x1400327b7  mov     [rsp+0E8h+var_70], r15
0x1400327bc  mov     rax, [r11+38h]
0x1400327c0  mov     [r11-50h], rax
0x1400327c4  mov     [rax], rcx
0x1400327c7  lea     rcx, NtfsAlignedMdlContextLookasideList; Lookaside
0x1400327ce  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400327d5  nop     dword ptr [rax+rax+00h]
0x1400327da  mov     rbx, rax
0x1400327dd  mov     [rsp+0E8h+var_98], rax
0x1400327e2  mov     eax, [rsp+0E8h+arg_28]
0x1400327e9  mov     [rsp+0E8h+var_AC], eax
0x1400327ed  mov     ecx, eax
0x1400327ef  neg     ecx
0x1400327f1  movsxd  rdx, ecx
0x1400327f4  mov     r14, rdx
0x1400327f7  and     r14, r12
0x1400327fa  mov     ecx, [rsp+0E8h+arg_20]
0x140032801  mov     [rsp+0E8h+var_B0], ecx
0x140032805  mov     r8d, ecx
0x140032808  mov     [rsp+0E8h+var_B8], rcx
0x14003280d  lea     ecx, [rax-1]
0x140032810  movsxd  rsi, ecx
0x140032813  add     rsi, r8
0x140032816  add     rsi, r12
0x140032819  and     rsi, rdx
0x14003281c  cmp     r14, r12
0x14003281f  jz      loc_140032B7F
0x140032825  movzx   ecx, word ptr [r15+0Ah]
0x14003282a  mov     al, cl
0x14003282c  and     al, 40h
0x14003282e  neg     al
0x140032830  sbb     edx, edx
0x140032832  mov     eax, 10h
0x140032837  and     edx, eax
0x140032839  add     edx, eax
0x14003283b  test    cl, 5
0x14003283e  jz      loc_140032AF3
0x140032844  mov     r15, [r15+18h]
0x140032848  test    r15, r15
0x14003284b  jz      loc_140032BA0
0x140032851  cmp     rsi, r14
0x140032854  jle     loc_140032A8C
0x14003285a  cmp     rsi, [r13+18h]
0x14003285e  jg      loc_140032A8C
0x140032864  mov     rax, rsi
0x140032867  sub     rax, r14
0x14003286a  mov     ecx, 0FFFFFFFFh
0x14003286f  cmp     rax, rcx
0x140032872  jg      loc_140032A8C
0x140032878  mov     rax, r15
0x14003287b  sub     rax, r12
0x14003287e  lea     r13, [r14+rax]
0x140032882  cmp     r13, r15
0x140032885  ja      loc_140032A8C
0x14003288b  lea     rdx, [r8+r15]
0x14003288f  cmp     rdx, r15
0x140032892  jbe     loc_140032A8C
0x140032898  add     rsi, rax
0x14003289b  cmp     rsi, rdx
0x14003289e  jb      loc_140032A8C
0x1400328a4  mov     rax, [rsp+0E8h+arg_10]
0x1400328ac  mov     rax, [rax+0C0h]
0x1400328b3  mov     rcx, [rax+0F8h]
0x1400328ba  mov     rax, [rcx+8]
0x1400328be  mov     ecx, [rax+98h]
0x1400328c4  test    r13, rcx
0x1400328c7  jnz     loc_140032BD9
0x1400328cd  mov     ecx, r13d
0x1400328d0  mov     r8d, 0FFFh
0x1400328d6  cmp     r13, r15
0x1400328d9  jnb     loc_140032B77
0x1400328df  mov     r12d, r13d
0x1400328e2  and     r12, r8
0x1400328e5  sub     r12, r13
0x1400328e8  add     r12, r8
0x1400328eb  add     r12, r15
0x1400328ee  shr     r12, 0Ch
0x1400328f2  cmp     rsi, rdx
0x1400328f5  ja      loc_140032AB6
0x1400328fb  xor     r14d, r14d
0x1400328fe  mov     [rsp+0E8h+var_80], r14
0x140032903  and     rcx, r8
0x140032906  mov     [rsp+0E8h+var_B8], rcx
0x14003290b  mov     rax, rsi
0x14003290e  sub     rax, r13
0x140032911  add     rax, 0FFFh
0x140032917  add     rcx, rax
0x14003291a  shr     rcx, 0Ch
0x14003291e  mov     [rsp+0E8h+var_88], rcx
0x140032923  lea     rax, [r14+r12]
0x140032927  shl     rax, 0Ch
0x14003292b  mov     [rsp+0E8h+var_78], rax
0x140032930  mov     r8d, 4446744Eh; Tag
0x140032936  mov     rdx, rax; NumberOfBytes
0x140032939  mov     ecx, 210h; PoolType
0x14003293e  call    cs:__imp_ExAllocatePoolWithTag
0x140032945  nop     dword ptr [rax+rax+00h]
0x14003294a  mov     [rsp+0E8h+var_68], rax
0x140032952  mov     [rsp+0E8h+var_A0], rax
0x140032957  sub     esi, r13d
0x14003295a  mov     [rsp+0E8h+var_90], rsi
0x14003295f  mov     rcx, [rsp+0E8h+var_B8]
0x140032964  add     rcx, rax; VirtualAddress
0x140032967  mov     [rsp+0E8h+Irp], 0; Irp
0x140032970  xor     r9d, r9d; ChargeQuota
0x140032973  xor     r8d, r8d; SecondaryBuffer
0x140032976  mov     edx, esi; Length
0x140032978  call    cs:__imp_IoAllocateMdl
0x14003297f  nop     dword ptr [rax+rax+00h]
0x140032984  mov     rsi, rax
0x140032987  mov     [rsp+0E8h+var_A8], rax
0x14003298c  test    rax, rax
0x14003298f  jz      loc_140032C12
0x140032995  mov     rax, [rsp+0E8h+var_78]
0x14003299a  sub     eax, dword ptr [rsp+0E8h+var_B8]
0x14003299e  mov     [rsi+28h], eax
0x1400329a1  mov     rcx, rsi; MemoryDescriptorList
0x1400329a4  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400329ab  nop     dword ptr [rax+rax+00h]
0x1400329b0  mov     rax, [rsp+0E8h+var_90]
0x1400329b5  mov     [rsi+28h], eax
0x1400329b8  mov     rax, [rsp+0E8h+var_88]
0x1400329bd  sub     rax, r14
0x1400329c0  sub     rax, r12
0x1400329c3  jz      loc_140032B28
0x1400329c9  lea     rdx, [r12+6]
0x1400329ce  lea     rdx, [rsi+rdx*8]; Src
0x1400329d2  mov     [rsp+0E8h+var_90], rdx
0x1400329d7  shl     rax, 3
0x1400329db  mov     [rsp+0E8h+var_88], rax
0x1400329e0  test    r14, r14
0x1400329e3  jz      short loc_1400329FB
0x1400329e5  lea     r8, ds:0[r14*8]; Size
0x1400329ed  lea     rcx, [rax+rdx]; void *
0x1400329f1  call    memmove
0x1400329f6  mov     rax, [rsp+0E8h+var_88]
0x1400329fb  mov     r14, 0FFFFFFFFFFFFF000h
0x140032a02  and     r15, r14
0x140032a05  shl     r12, 0Ch
0x140032a09  sub     r12, r15
0x140032a0c  and     r13, r14
0x140032a0f  lea     rdx, [r12+r13]
0x140032a13  shr     rdx, 0Ch
0x140032a17  mov     r15, [rsp+0E8h+var_70]
0x140032a1c  add     rdx, 6
0x140032a20  lea     rdx, [r15+rdx*8]; Src
0x140032a24  mov     r8, rax; Size
0x140032a27  mov     rcx, [rsp+0E8h+var_90]; void *
0x140032a2c  call    memmove
0x140032a31  and     word ptr [rsi+0Ah], 0FFFBh
0x140032a36  movzx   eax, word ptr [rsi+0Ah]
0x140032a3a  or      ax, 10h
0x140032a3e  mov     [rsi+0Ah], ax
0x140032a42  test    al, 5
0x140032a44  jz      loc_140032B32
0x140032a4a  mov     rax, [rsi+18h]
0x140032a4e  test    rax, rax
0x140032a51  jz      loc_140032C4B
0x140032a57  mov     rax, [rsi+18h]
0x140032a5b  and     rax, r14
0x140032a5e  mov     [rsi+20h], rax
0x140032a62  mov     edx, 2
0x140032a67  mov     rcx, r15
0x140032a6a  call    cs:__imp_MmMdlPageContentsState
0x140032a71  nop     dword ptr [rax+rax+00h]
0x140032a76  mov     edx, eax
0x140032a78  mov     rcx, rsi
0x140032a7b  call    cs:__imp_MmMdlPageContentsState
0x140032a82  nop     dword ptr [rax+rax+00h]
0x140032a87  jmp     loc_140032C85
0x140032a8c  mov     al, cs:NtfsStatusDebugFlags
0x140032a92  test    al, al
0x140032a94  jnz     loc_140032B5F
0x140032a9a  mov     [rsp+0E8h+Irp], 0C2C28h
0x140032aa3  xor     r9d, r9d
0x140032aa6  xor     r8d, r8d
0x140032aa9  mov     edx, 0C000000Dh
0x140032aae  mov     rcx, rdi
0x140032ab1  call    NtfsRaiseStatusInternal
0x140032ab6  mov     r14d, edx
0x140032ab9  and     r14, r8
0x140032abc  sub     r14, rdx
0x140032abf  add     r14, 0FFFh
0x140032ac6  add     r14, rsi
0x140032ac9  shr     r14, 0Ch
0x140032acd  mov     [rsp+0E8h+var_80], r14
0x140032ad2  test    r12, r12
0x140032ad5  jz      loc_140032903
0x140032adb  and     rdx, 0FFFFFFFFFFFFF000h
0x140032ae2  cmp     rdx, r15
0x140032ae5  jnb     loc_140032903
0x140032aeb  dec     r14
0x140032aee  jmp     loc_1400328FE
0x140032af3  bts     edx, 1Eh
0x140032af7  mov     [rsp+0E8h+Priority], edx; Priority
0x140032afb  mov     dword ptr [rsp+0E8h+Irp], 0; BugCheckOnFailure
0x140032b03  xor     r9d, r9d; RequestedAddress
0x140032b06  xor     edx, edx; AccessMode
0x140032b08  lea     r8d, [r9+1]; CacheType
0x140032b0c  mov     rcx, r15; MemoryDescriptorList
0x140032b0f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140032b16  nop     dword ptr [rax+rax+00h]
0x140032b1b  mov     r15, rax
0x140032b1e  mov     r8, [rsp+0E8h+var_B8]
0x140032b23  jmp     loc_140032848
0x140032b28  mov     edx, 1
0x140032b2d  jmp     loc_140032A78
0x140032b32  mov     [rsp+0E8h+Priority], 40000010h; Priority
0x140032b3a  mov     dword ptr [rsp+0E8h+Irp], 0; BugCheckOnFailure
0x140032b42  xor     r9d, r9d; RequestedAddress
0x140032b45  xor     edx, edx; AccessMode
0x140032b47  lea     r8d, [r9+1]; CacheType
0x140032b4b  mov     rcx, rsi; MemoryDescriptorList
0x140032b4e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140032b55  nop     dword ptr [rax+rax+00h]
0x140032b5a  jmp     loc_140032A4E
0x140032b5f  mov     edx, 0C000000Dh
0x140032b64  mov     r8d, 0C2C28h
0x140032b6a  mov     rcx, rdi
0x140032b6d  call    NtfsStatusTraceAndDebugInternal
0x140032b72  jmp     loc_140032A9A
0x140032b77  xor     r12d, r12d
0x140032b7a  jmp     loc_1400328F2
0x140032b7f  lea     rax, [r8+r12]
0x140032b83  cmp     rsi, rax
0x140032b86  jnz     loc_140032825
0x140032b8c  lea     rdx, loc_140032CF1
0x140032b93  mov     rcx, [rsp+0E8h+var_48]
0x140032b9b  call    _local_unwind_0
0x140032ba0  mov     al, cs:NtfsStatusDebugFlags
0x140032ba6  test    al, al
0x140032ba8  jz      short loc_140032BBD
0x140032baa  mov     edx, 0C000009Ah
0x140032baf  mov     r8d, 0C2C10h
0x140032bb5  mov     rcx, rdi
0x140032bb8  call    NtfsStatusTraceAndDebugInternal
0x140032bbd  mov     [rsp+0E8h+Irp], 0C2C10h
0x140032bc6  xor     r9d, r9d
0x140032bc9  xor     r8d, r8d
0x140032bcc  mov     edx, 0C000009Ah
0x140032bd1  mov     rcx, rdi
0x140032bd4  call    NtfsRaiseStatusInternal
0x140032bd9  mov     al, cs:NtfsStatusDebugFlags
0x140032bdf  test    al, al
0x140032be1  jz      short loc_140032BF6
0x140032be3  mov     edx, 0C0000474h
0x140032be8  mov     r8d, 0C2C32h
0x140032bee  mov     rcx, rdi
0x140032bf1  call    NtfsStatusTraceAndDebugInternal
0x140032bf6  mov     [rsp+0E8h+Irp], 0C2C32h
0x140032bff  xor     r9d, r9d
0x140032c02  xor     r8d, r8d
0x140032c05  mov     edx, 0C0000474h
0x140032c0a  mov     rcx, rdi
0x140032c0d  call    NtfsRaiseStatusInternal
0x140032c12  mov     al, cs:NtfsStatusDebugFlags
0x140032c18  test    al, al
0x140032c1a  jz      short loc_140032C2F
0x140032c1c  mov     edx, 0C000009Ah
0x140032c21  mov     r8d, 0C2C88h
0x140032c27  mov     rcx, rdi
0x140032c2a  call    NtfsStatusTraceAndDebugInternal
0x140032c2f  mov     [rsp+0E8h+Irp], 0C2C88h
0x140032c38  xor     r9d, r9d
0x140032c3b  xor     r8d, r8d
0x140032c3e  mov     edx, 0C000009Ah
0x140032c43  mov     rcx, rdi
0x140032c46  call    NtfsRaiseStatusInternal
0x140032c4b  mov     al, cs:NtfsStatusDebugFlags
0x140032c51  test    al, al
0x140032c53  jz      short loc_140032C68
0x140032c55  mov     edx, 0C000009Ah
0x140032c5a  mov     r8d, 0C2CCCh
0x140032c60  mov     rcx, rdi
0x140032c63  call    NtfsStatusTraceAndDebugInternal
0x140032c68  mov     [rsp+0E8h+Irp], 0C2CCCh
0x140032c71  xor     r9d, r9d
  ... truncated ...
```
