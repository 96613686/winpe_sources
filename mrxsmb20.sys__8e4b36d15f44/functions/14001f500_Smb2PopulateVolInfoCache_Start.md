# Smb2PopulateVolInfoCache_Start

- ea: `0x14001f500`
- end: `0x14001f933`
- name: `Smb2PopulateVolInfoCache_Start`
- size: `1075`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001f500`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001f8ac`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001f8d2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001f8ac`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001f8d2`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001f6cd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001f6dc`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001f7e3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001f7f2`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001f6cd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001f6dc`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001f7e3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001f7f2`
- `rdbss!RxFreeMdl` at `0x14001f913`
- `rdbss!RxFreeMdl` at `0x14001f922`
- `rdbss!RxFreeMdl` at `0x14001f913`
- `rdbss!RxFreeMdl` at `0x14001f922`
- `rdbss!RxAllocateMdl2` at `0x14001f683`
- `rdbss!RxAllocateMdl2` at `0x14001f6b2`
- `rdbss!RxAllocateMdl2` at `0x14001f799`
- `rdbss!RxAllocateMdl2` at `0x14001f7c8`
- `rdbss!RxAllocateMdl2` at `0x14001f683`
- `rdbss!RxAllocateMdl2` at `0x14001f6b2`
- `rdbss!RxAllocateMdl2` at `0x14001f799`
- `rdbss!RxAllocateMdl2` at `0x14001f7c8`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001f75f`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001f86d`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001f75f`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001f86d`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14001f720`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14001f836`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14001f720`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14001f836`

## pseudocode

```c
__int64 __fastcall Smb2PopulateVolInfoCache_Start(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  __int64 v4; // r14
  __int64 v5; // rsi
  __int64 v6; // r15
  __int128 v7; // xmm0
  struct _MDL *Mdl2; // rbp
  struct _MDL *v9; // rsi
  int v10; // edi
  __int64 v11; // rcx
  PVOID v12; // rax
  __int64 v13; // rcx
  PVOID v14; // rax
  __int64 Priority; // [rsp+28h] [rbp-70h]
  __int64 v17; // [rsp+38h] [rbp-60h]
  int v18; // [rsp+40h] [rbp-58h]

  v2 = a1 + 5449;
  v3 = *(_QWORD *)(a1 + 72);
  v4 = *(_QWORD *)(a1 + 80);
  v5 = *(_QWORD *)(a1 + 88);
  v6 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 72LL) + 48LL);
  memset((void *)(a1 + 5449), 0, 0x40u);
  *(_DWORD *)v2 = 1112364030;
  *(_DWORD *)(v2 + 32) = 65279;
  *(_WORD *)(v2 + 4) = 64;
  if ( *(char *)(v3 + 736) < 0 )
    *(_DWORD *)(v2 + 16) = (16 * *(_BYTE *)(a1 + 33) + 16) & 0x70;
  *(_WORD *)(v2 + 14) = 1;
  if ( v4 )
  {
    *(_QWORD *)(v2 + 40) = *(_QWORD *)(v4 + 440);
    if ( (*(_DWORD *)(v3 + 716) & 0x3000) != 0 )
      *(_WORD *)(v2 + 8) = *(_WORD *)(v3 + 700);
  }
  if ( v5 )
  {
    *(_DWORD *)(v2 + 36) = *(_DWORD *)(v5 + 436);
    if ( (*(_DWORD *)(*(_QWORD *)(v5 + 424) + 176LL) & 2) != 0 && (*(_DWORD *)(a1 + 68) & 0x8000) != 0 )
      *(_DWORD *)(v2 + 16) |= 0x10000000u;
  }
  if ( (*(_DWORD *)(v3 + 716) & 0x3000) != 0 && (*(_DWORD *)(a1 + 68) & 0x4000) != 0 )
    *(_DWORD *)(v2 + 16) |= 0x20000000u;
  *(_WORD *)(a1 + 5461) = 16;
  *(_OWORD *)(a1 + 5513) = 0;
  *(_OWORD *)(a1 + 5529) = 0;
  *(_OWORD *)(a1 + 5538) = 0;
  *(_WORD *)(a1 + 5513) = 41;
  v7 = *(_OWORD *)(v6 + 28);
  *(_WORD *)(a1 + 5515) = 258;
  *(_DWORD *)(a1 + 5517) = 82;
  *(_OWORD *)(a1 + 5537) = v7;
  *(_OWORD *)(a1 + 5554) = *(_OWORD *)v2;
  *(_OWORD *)(a1 + 5570) = *(_OWORD *)(v2 + 16);
  *(_OWORD *)(a1 + 5586) = *(_OWORD *)(v2 + 32);
  *(_OWORD *)(a1 + 5602) = *(_OWORD *)(v2 + 48);
  *(_OWORD *)(a1 + 5618) = *(_OWORD *)(v2 + 64);
  *(_OWORD *)(a1 + 5634) = *(_OWORD *)(v2 + 80);
  *(_OWORD *)(a1 + 5643) = *(_OWORD *)(v2 + 89);
  Mdl2 = (struct _MDL *)RxAllocateMdl2(v2, 105, 0, 0, 0);
  if ( !Mdl2 )
  {
    v9 = 0;
    goto LABEL_30;
  }
  v9 = (struct _MDL *)RxAllocateMdl2(a1 + 5256, 82, 0, 0, 0);
  if ( !v9 )
    goto LABEL_30;
  MmBuildMdlForNonPagedPool(Mdl2);
  MmBuildMdlForNonPagedPool(v9);
  v10 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 3792, a1, Mdl2, 105, v9, 82, 0, 0, 0, 4);
  if ( v10 )
    goto LABEL_23;
  v11 = *(_QWORD *)(a1 + 4512);
  Mdl2 = 0;
  v9 = 0;
  if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
    v12 = *(PVOID *)(v11 + 24);
  else
    v12 = MmMapLockedPagesSpecifyCache((PMDL)v11, 0, MmCached, 0, 0, 0x40000000u);
  *(_QWORD *)(a1 + 4504) = v12;
  v10 = SmbCseSubmitBufferContext(a1 + 3792);
  if ( v10 < 0 )
    goto LABEL_31;
  *(_BYTE *)(a1 + 5621) = 5;
  *(_DWORD *)(a1 + 5622) = 76;
  Mdl2 = (struct _MDL *)RxAllocateMdl2(a1 + 5554, 105, 0, 0, 0);
  if ( !Mdl2 || (v9 = (struct _MDL *)RxAllocateMdl2(a1 + 5176, 76, 0, 0, 0)) == 0 )
  {
LABEL_30:
    v10 = -1073741670;
    goto LABEL_31;
  }
  MmBuildMdlForNonPagedPool(Mdl2);
  MmBuildMdlForNonPagedPool(v9);
  LOWORD(v18) = 0;
  LODWORD(v17) = 0;
  LODWORD(Priority) = 76;
  v10 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 2408, a1, Mdl2, 105, v9, Priority, 0, v17, v18, 4);
  if ( !v10 )
  {
    v13 = *(_QWORD *)(a1 + 3128);
    Mdl2 = 0;
    v9 = 0;
    if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
      v14 = *(PVOID *)(v13 + 24);
    else
      v14 = MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x40000000u);
    *(_QWORD *)(a1 + 3120) = v14;
    v10 = SmbCseSubmitBufferContext(a1 + 2408);
  }
LABEL_23:
  if ( v10 < 0 )
  {
LABEL_31:
    RxFreeMdl(Mdl2);
    RxFreeMdl(v9);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001f500  push    rbx
0x14001f502  push    rbp
0x14001f503  push    rsi
0x14001f504  push    rdi
0x14001f505  push    r12
0x14001f507  push    r13
0x14001f509  push    r14
0x14001f50b  push    r15
0x14001f50d  sub     rsp, 58h
0x14001f511  mov     rax, [rcx+30h]
0x14001f515  mov     rbx, rcx
0x14001f518  mov     r12d, 40h ; '@'
0x14001f51e  xor     edx, edx; Val
0x14001f520  mov     r8d, r12d; Size
0x14001f523  mov     rcx, [rax+48h]
0x14001f527  lea     rdi, [rbx+1549h]
0x14001f52e  mov     rbp, [rbx+48h]
0x14001f532  mov     r14, [rbx+50h]
0x14001f536  mov     rsi, [rbx+58h]
0x14001f53a  mov     r15, [rcx+30h]
0x14001f53e  mov     rcx, rdi; void *
0x14001f541  call    memset
0x14001f546  mov     dword ptr [rdi], 424D53FEh
0x14001f54c  mov     dword ptr [rdi+20h], 0FEFFh
0x14001f553  mov     [rdi+4], r12w
0x14001f558  cmp     byte ptr [rbp+2E0h], 0
0x14001f55f  jge     short loc_14001F571
0x14001f561  movzx   eax, byte ptr [rbx+21h]
0x14001f565  shl     eax, 4
0x14001f568  add     eax, 10h
0x14001f56b  and     eax, 70h
0x14001f56e  mov     [rdi+10h], eax
0x14001f571  mov     r13d, 1
0x14001f577  mov     [rdi+0Eh], r13w
0x14001f57c  test    r14, r14
0x14001f57f  jz      short loc_14001F5A3
0x14001f581  mov     rax, [r14+1B8h]
0x14001f588  mov     [rdi+28h], rax
0x14001f58c  test    dword ptr [rbp+2CCh], 3000h
0x14001f596  jz      short loc_14001F5A3
0x14001f598  movzx   eax, word ptr [rbp+2BCh]
0x14001f59f  mov     [rdi+8], ax
0x14001f5a3  test    rsi, rsi
0x14001f5a6  jz      short loc_14001F5C7
0x14001f5a8  mov     eax, [rsi+1B4h]
0x14001f5ae  mov     [rdi+24h], eax
0x14001f5b1  mov     rax, [rsi+1A8h]
0x14001f5b8  mov     ecx, [rax+0B0h]
0x14001f5be  test    cl, 2
0x14001f5c1  jnz     loc_14001F8E3
0x14001f5c7  test    dword ptr [rbp+2CCh], 3000h
0x14001f5d1  jz      short loc_14001F5E0
0x14001f5d3  mov     eax, [rbx+44h]
0x14001f5d6  bt      eax, 0Eh
0x14001f5da  jb      loc_14001F8FC
0x14001f5e0  mov     word ptr [rbx+1555h], 10h
0x14001f5e9  lea     r14, [rbx+15B2h]
0x14001f5f0  xorps   xmm0, xmm0
0x14001f5f3  xor     r12d, r12d
0x14001f5f6  movups  xmmword ptr [rbx+1589h], xmm0
0x14001f5fd  xor     r9d, r9d
0x14001f600  xor     r8d, r8d
0x14001f603  movups  xmmword ptr [rbx+1599h], xmm0
0x14001f60a  mov     edx, 69h ; 'i'
0x14001f60f  mov     rcx, rdi
0x14001f612  movups  xmmword ptr [rbx+15A2h], xmm0
0x14001f619  mov     word ptr [rbx+1589h], 29h ; ')'
0x14001f622  movups  xmm0, xmmword ptr [r15+1Ch]
0x14001f627  mov     word ptr [rbx+158Bh], 102h
0x14001f630  mov     dword ptr [rbx+158Dh], 52h ; 'R'
0x14001f63a  movups  xmmword ptr [rbx+15A1h], xmm0
0x14001f641  mov     qword ptr [rsp+98h+BugCheckOnFailure], r12
0x14001f646  movups  xmm0, xmmword ptr [rdi]
0x14001f649  movups  xmmword ptr [r14], xmm0
0x14001f64d  movups  xmm1, xmmword ptr [rdi+10h]
0x14001f651  movups  xmmword ptr [r14+10h], xmm1
0x14001f656  movups  xmm0, xmmword ptr [rdi+20h]
0x14001f65a  movups  xmmword ptr [r14+20h], xmm0
0x14001f65f  movups  xmm1, xmmword ptr [rdi+30h]
0x14001f663  movups  xmmword ptr [r14+30h], xmm1
0x14001f668  movups  xmm0, xmmword ptr [rdi+40h]
0x14001f66c  movups  xmmword ptr [r14+40h], xmm0
0x14001f671  movups  xmm1, xmmword ptr [rdi+50h]
0x14001f675  movups  xmmword ptr [r14+50h], xmm1
0x14001f67a  movups  xmm0, xmmword ptr [rdi+59h]
0x14001f67e  movups  xmmword ptr [r14+59h], xmm0
0x14001f683  call    cs:__imp_RxAllocateMdl2
0x14001f68a  nop     dword ptr [rax+rax+00h]
0x14001f68f  mov     rbp, rax
0x14001f692  test    rax, rax
0x14001f695  jz      loc_14001F908
0x14001f69b  lea     rcx, [rbx+1488h]
0x14001f6a2  mov     qword ptr [rsp+98h+BugCheckOnFailure], r12
0x14001f6a7  xor     r9d, r9d
0x14001f6aa  xor     r8d, r8d
0x14001f6ad  mov     edx, 52h ; 'R'
0x14001f6b2  call    cs:__imp_RxAllocateMdl2
0x14001f6b9  nop     dword ptr [rax+rax+00h]
0x14001f6be  mov     rsi, rax
0x14001f6c1  test    rax, rax
0x14001f6c4  jz      loc_14001F90B
0x14001f6ca  mov     rcx, rbp; MemoryDescriptorList
0x14001f6cd  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001f6d4  nop     dword ptr [rax+rax+00h]
0x14001f6d9  mov     rcx, rsi; MemoryDescriptorList
0x14001f6dc  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001f6e3  nop     dword ptr [rax+rax+00h]
0x14001f6e8  mov     [rsp+98h+var_50], 4
0x14001f6f0  lea     rcx, [rbx+0ED0h]
0x14001f6f7  mov     [rsp+98h+var_58], r12w
0x14001f6fd  mov     r9d, 69h ; 'i'
0x14001f703  mov     dword ptr [rsp+98h+var_60], r12d
0x14001f708  mov     r8, rbp
0x14001f70b  mov     [rsp+98h+var_68], r12
0x14001f710  mov     rdx, rbx
0x14001f713  mov     dword ptr [rsp+98h+Priority], 52h ; 'R'
0x14001f71b  mov     qword ptr [rsp+98h+BugCheckOnFailure], rsi
0x14001f720  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x14001f727  nop     dword ptr [rax+rax+00h]
0x14001f72c  mov     edi, eax
0x14001f72e  test    eax, eax
0x14001f730  jnz     loc_14001F87B
0x14001f736  mov     rcx, [rbx+11A0h]; MemoryDescriptorList
0x14001f73d  mov     ebp, r12d
0x14001f740  mov     esi, r12d
0x14001f743  test    byte ptr [rcx+0Ah], 5
0x14001f747  jz      loc_14001F897
0x14001f74d  mov     rax, [rcx+18h]
0x14001f751  lea     rcx, [rbx+0ED0h]
0x14001f758  mov     [rbx+1198h], rax
0x14001f75f  call    cs:__imp_SmbCseSubmitBufferContext
0x14001f766  nop     dword ptr [rax+rax+00h]
0x14001f76b  mov     edi, eax
0x14001f76d  test    eax, eax
0x14001f76f  js      loc_14001F910
0x14001f775  xor     r9d, r9d
0x14001f778  mov     byte ptr [rbx+15F5h], 5
0x14001f77f  xor     r8d, r8d
0x14001f782  mov     dword ptr [rbx+15F6h], 4Ch ; 'L'
0x14001f78c  mov     edx, 69h ; 'i'
0x14001f791  mov     qword ptr [rsp+98h+BugCheckOnFailure], r12
0x14001f796  mov     rcx, r14
0x14001f799  call    cs:__imp_RxAllocateMdl2
0x14001f7a0  nop     dword ptr [rax+rax+00h]
0x14001f7a5  mov     rbp, rax
0x14001f7a8  test    rax, rax
0x14001f7ab  jz      loc_14001F90B
0x14001f7b1  lea     rcx, [rbx+1438h]
0x14001f7b8  mov     qword ptr [rsp+98h+BugCheckOnFailure], r12
0x14001f7bd  xor     r9d, r9d
0x14001f7c0  xor     r8d, r8d
0x14001f7c3  mov     edx, 4Ch ; 'L'
0x14001f7c8  call    cs:__imp_RxAllocateMdl2
0x14001f7cf  nop     dword ptr [rax+rax+00h]
0x14001f7d4  mov     rsi, rax
0x14001f7d7  test    rax, rax
0x14001f7da  jz      loc_14001F90B
0x14001f7e0  mov     rcx, rbp; MemoryDescriptorList
0x14001f7e3  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001f7ea  nop     dword ptr [rax+rax+00h]
0x14001f7ef  mov     rcx, rsi; MemoryDescriptorList
0x14001f7f2  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001f7f9  nop     dword ptr [rax+rax+00h]
0x14001f7fe  mov     [rsp+98h+var_50], 4
0x14001f806  lea     rcx, [rbx+968h]
0x14001f80d  mov     [rsp+98h+var_58], r12w
0x14001f813  mov     r9d, 69h ; 'i'
0x14001f819  mov     dword ptr [rsp+98h+var_60], r12d
0x14001f81e  mov     r8, rbp
0x14001f821  mov     [rsp+98h+var_68], r12
0x14001f826  mov     rdx, rbx
0x14001f829  mov     dword ptr [rsp+98h+Priority], 4Ch ; 'L'
0x14001f831  mov     qword ptr [rsp+98h+BugCheckOnFailure], rsi
0x14001f836  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x14001f83d  nop     dword ptr [rax+rax+00h]
0x14001f842  mov     edi, eax
0x14001f844  test    eax, eax
0x14001f846  jnz     short loc_14001F87B
0x14001f848  mov     rcx, [rbx+0C38h]; MemoryDescriptorList
0x14001f84f  mov     rbp, r12
0x14001f852  mov     rsi, r12
0x14001f855  test    byte ptr [rcx+0Ah], 5
0x14001f859  jz      short loc_14001F8BD
0x14001f85b  mov     rax, [rcx+18h]
0x14001f85f  lea     rcx, [rbx+968h]
0x14001f866  mov     [rbx+0C30h], rax
0x14001f86d  call    cs:__imp_SmbCseSubmitBufferContext
0x14001f874  nop     dword ptr [rax+rax+00h]
0x14001f879  mov     edi, eax
0x14001f87b  test    edi, edi
0x14001f87d  js      loc_14001F910
0x14001f883  mov     eax, edi
0x14001f885  add     rsp, 58h
0x14001f889  pop     r15
0x14001f88b  pop     r14
0x14001f88d  pop     r13
0x14001f88f  pop     r12
0x14001f891  pop     rdi
0x14001f892  pop     rsi
0x14001f893  pop     rbp
0x14001f894  pop     rbx
0x14001f895  retn
0x14001f897  mov     dword ptr [rsp+98h+Priority], 40000000h; Priority
0x14001f89f  xor     r9d, r9d; RequestedAddress
0x14001f8a2  mov     r8d, r13d; CacheType
0x14001f8a5  mov     [rsp+98h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14001f8aa  xor     edx, edx; AccessMode
0x14001f8ac  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001f8b3  nop     dword ptr [rax+rax+00h]
0x14001f8b8  jmp     loc_14001F751
0x14001f8bd  mov     dword ptr [rsp+98h+Priority], 40000000h; Priority
0x14001f8c5  xor     r9d, r9d; RequestedAddress
0x14001f8c8  mov     r8d, r13d; CacheType
0x14001f8cb  mov     [rsp+98h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14001f8d0  xor     edx, edx; AccessMode
0x14001f8d2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001f8d9  nop     dword ptr [rax+rax+00h]
0x14001f8de  jmp     loc_14001F85F
0x14001f8e3  mov     eax, [rbx+44h]
0x14001f8e6  bt      eax, 0Fh
0x14001f8ea  jnb     loc_14001F5C7
0x14001f8f0  or      dword ptr [rdi+10h], 10000000h
0x14001f8f7  jmp     loc_14001F5C7
0x14001f8fc  or      dword ptr [rdi+10h], 20000000h
0x14001f903  jmp     loc_14001F5E0
0x14001f908  mov     rsi, r12
0x14001f90b  mov     edi, 0C000009Ah
0x14001f910  mov     rcx, rbp
0x14001f913  call    cs:__imp_RxFreeMdl
0x14001f91a  nop     dword ptr [rax+rax+00h]
0x14001f91f  mov     rcx, rsi
0x14001f922  call    cs:__imp_RxFreeMdl
0x14001f929  nop     dword ptr [rax+rax+00h]
0x14001f92e  jmp     loc_14001F883
```
