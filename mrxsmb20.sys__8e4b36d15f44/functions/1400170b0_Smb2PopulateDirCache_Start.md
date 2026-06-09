# Smb2PopulateDirCache_Start

- ea: `0x1400170b0`
- end: `0x140017640`
- name: `Smb2PopulateDirCache_Start`
- size: `1424`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400170b0`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140017361`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400173bf`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400174b1`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140017522`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140017361`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400173bf`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400174b1`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140017522`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140017136`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140017136`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140017117`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140017117`
- `rdbss!RxFreeMdl` at `0x140017620`
- `rdbss!RxFreeMdl` at `0x14001762f`
- `rdbss!RxFreeMdl` at `0x140017620`
- `rdbss!RxFreeMdl` at `0x14001762f`
- `rdbss!RxAllocateMdl2` at `0x140017346`
- `rdbss!RxAllocateMdl2` at `0x1400173a4`
- `rdbss!RxAllocateMdl2` at `0x140017496`
- `rdbss!RxAllocateMdl2` at `0x140017507`
- `rdbss!RxAllocateMdl2` at `0x140017346`
- `rdbss!RxAllocateMdl2` at `0x1400173a4`
- `rdbss!RxAllocateMdl2` at `0x140017496`
- `rdbss!RxAllocateMdl2` at `0x140017507`
- `mrxsmb!SmbCeQueryOptimalBufferSize` at `0x140017157`
- `mrxsmb!SmbCeQueryOptimalBufferSize` at `0x140017157`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x140017377`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x1400174da`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x140017377`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x1400174da`
- `mrxsmb!RDR_PERF_ENTER` at `0x1400170fc`
- `mrxsmb!RDR_PERF_ENTER` at `0x1400170fc`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140017455`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x1400175a0`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140017455`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x1400175a0`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140017406`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140017569`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140017406`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140017569`

## pseudocode

```c
__int64 __fastcall Smb2PopulateDirCache_Start(__int64 a1, __int64 a2)
{
  __int64 v3; // rbp
  struct _MDL *v4; // r12
  char v5; // r13
  __int64 v6; // rsi
  int v7; // r13d
  unsigned int v8; // esi
  __int64 v9; // r14
  __int64 v10; // r15
  __int64 v11; // rbp
  __int64 v12; // rax
  __int128 v13; // xmm0
  struct _MDL *Mdl2; // rax
  struct _MDL *v15; // rsi
  __int64 ExchangeBuffer; // rax
  __int64 v17; // r14
  struct _MDL *v18; // rax
  int v19; // edi
  unsigned int v20; // eax
  __int64 result; // rax
  struct _MDL *v22; // rax
  __int64 v23; // rax
  __int64 v24; // r14
  struct _MDL *v25; // rax
  __int64 v26; // [rsp+28h] [rbp-60h]
  __int64 v27; // [rsp+38h] [rbp-50h]
  int v28; // [rsp+40h] [rbp-48h]
  unsigned int v29; // [rsp+90h] [rbp+8h] BYREF
  __int64 v30; // [rsp+98h] [rbp+10h]

  v3 = *(_QWORD *)(a1 + 3792);
  LOBYTE(a2) = 15;
  v4 = 0;
  v5 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 72LL) + 48LL);
  v30 = v6;
  v29 = 0;
  RDR_PERF_ENTER(a1 + 512, a2);
  if ( *(_BYTE *)(a1 + 3800) )
  {
    ExAcquirePushLockExclusiveEx(v6 + 16, 0);
    v7 = *(_DWORD *)(v6 + 8);
    *(_DWORD *)(v6 + 8) = v7 | 0x10;
    ExReleasePushLockExclusiveEx(v6 + 16, 0);
    v5 = v7 & 0x10;
  }
  SmbCeQueryOptimalBufferSize(*(_QWORD *)(a1 + 96), 0, 0, &v29);
  v8 = v29;
  if ( v29 >= 0x100000 )
  {
    v8 = 0x100000;
    v29 = 0x100000;
  }
  if ( v8 >= *(_DWORD *)(v3 + 8) )
  {
    v8 = *(_DWORD *)(v3 + 8);
    v29 = v8;
  }
  if ( *(_BYTE *)(a1 + 3800) && v8 >= 0x10000 || v8 <= 0x10000 )
  {
    v8 = 0x10000;
    v29 = 0x10000;
  }
  v9 = *(_QWORD *)(a1 + 72);
  v10 = *(_QWORD *)(a1 + 80);
  v11 = *(_QWORD *)(a1 + 88);
  memset((void *)(a1 + 3808), 0, 0x40u);
  *(_DWORD *)(a1 + 3808) = 1112364030;
  *(_DWORD *)(a1 + 3840) = 65279;
  *(_WORD *)(a1 + 3812) = 64;
  if ( *(char *)(v9 + 736) < 0 )
    *(_DWORD *)(a1 + 3824) = (16 * *(_BYTE *)(a1 + 33) + 16) & 0x70;
  *(_WORD *)(a1 + 3822) = 1;
  if ( v10 )
  {
    *(_QWORD *)(a1 + 3848) = *(_QWORD *)(v10 + 440);
    if ( (*(_DWORD *)(v9 + 716) & 0x3000) != 0 )
      *(_WORD *)(a1 + 3816) = *(_WORD *)(v9 + 700);
  }
  if ( v11 )
  {
    *(_DWORD *)(a1 + 3844) = *(_DWORD *)(v11 + 436);
    if ( (*(_DWORD *)(*(_QWORD *)(v11 + 424) + 176LL) & 2) != 0 )
    {
      v8 = v29;
      if ( (*(_DWORD *)(a1 + 68) & 0x8000) != 0 )
        *(_DWORD *)(a1 + 3824) |= 0x10000000u;
    }
  }
  if ( (*(_DWORD *)(v9 + 716) & 0x3000) != 0 )
  {
    v8 = v29;
    if ( (*(_DWORD *)(a1 + 68) & 0x4000) != 0 )
      *(_DWORD *)(a1 + 3824) |= 0x20000000u;
  }
  v12 = v30;
  *(_WORD *)(a1 + 3820) = 14;
  *(_OWORD *)(a1 + 3872) = 0;
  *(_OWORD *)(a1 + 3888) = 0;
  *(_WORD *)(a1 + 3872) = 33;
  v13 = *(_OWORD *)(v12 + 28);
  LOBYTE(v12) = *(_BYTE *)(a1 + 3801);
  *(_DWORD *)(a1 + 3896) = 131168;
  *(_OWORD *)(a1 + 3880) = v13;
  *(_BYTE *)(a1 + 3874) = v12;
  *(_BYTE *)(a1 + 3875) = v5;
  *(_DWORD *)(a1 + 3876) = 0;
  *(_DWORD *)(a1 + 3900) = v8;
  *(_WORD *)(a1 + 3904) = 42;
  if ( *(_BYTE *)(a1 + 3800) )
  {
    *(_OWORD *)(a1 + 3920) = *(_OWORD *)(a1 + 3808);
    *(_OWORD *)(a1 + 3936) = *(_OWORD *)(a1 + 3824);
    *(_OWORD *)(a1 + 3952) = *(_OWORD *)(a1 + 3840);
    *(_OWORD *)(a1 + 3968) = *(_OWORD *)(a1 + 3856);
    *(_OWORD *)(a1 + 3984) = *(_OWORD *)(a1 + 3872);
    *(_OWORD *)(a1 + 4000) = *(_OWORD *)(a1 + 3888);
    *(_WORD *)(a1 + 4016) = *(_WORD *)(a1 + 3904);
  }
  Mdl2 = (struct _MDL *)RxAllocateMdl2(a1 + 3808, 98, 0, 0, 0);
  v15 = Mdl2;
  if ( !Mdl2 )
    goto LABEL_40;
  MmBuildMdlForNonPagedPool(Mdl2);
  ExchangeBuffer = SmbCeAllocateExchangeBuffer(a1);
  v17 = ExchangeBuffer;
  if ( !ExchangeBuffer )
    goto LABEL_40;
  v18 = (struct _MDL *)RxAllocateMdl2(ExchangeBuffer, v29, 0, 0, 0);
  v4 = v18;
  if ( !v18 )
    goto LABEL_40;
  MmBuildMdlForNonPagedPool(v18);
  v19 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 1024, a1, v15, 98, v4, v29, 0, 0, 0, 4);
  if ( v19 )
    goto LABEL_33;
  v20 = v29 - 1;
  *(_QWORD *)(a1 + 1736) = v17;
  v15 = 0;
  v4 = 0;
  *(_DWORD *)(a1 + 1104) = HIWORD(v20) + 1;
  *(_DWORD *)(a1 + 1888) = *(unsigned __int8 *)(a1 + 3801) | 0x10000;
  result = SmbCseSubmitBufferContext(a1 + 1024);
  v19 = result;
  if ( (int)result < 0 )
  {
LABEL_41:
    RxFreeMdl(v15);
    RxFreeMdl(v4);
    return (unsigned int)v19;
  }
  if ( !*(_BYTE *)(a1 + 3800) )
    return result;
  *(_BYTE *)(a1 + 3987) = 0;
  v22 = (struct _MDL *)RxAllocateMdl2(a1 + 3920, 98, 0, 0, 0);
  v15 = v22;
  if ( !v22
    || (MmBuildMdlForNonPagedPool(v22),
        v29 = 1024,
        *(_DWORD *)(a1 + 4012) = 1024,
        v23 = SmbCeAllocateExchangeBuffer(a1),
        (v24 = v23) == 0)
    || (v25 = (struct _MDL *)RxAllocateMdl2(v23, v29, 0, 0, 0), (v4 = v25) == 0) )
  {
LABEL_40:
    v19 = -1073741670;
    goto LABEL_41;
  }
  MmBuildMdlForNonPagedPool(v25);
  LOWORD(v28) = 0;
  LODWORD(v27) = 0;
  LODWORD(v26) = v29;
  v19 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 2408, a1, v15, 98, v4, v26, 0, v27, v28, 4);
  if ( !v19 )
  {
    *(_QWORD *)(a1 + 3120) = v24;
    v15 = 0;
    v4 = 0;
    *(_DWORD *)(a1 + 3272) = *(unsigned __int8 *)(a1 + 3801) | 0x10000;
    v19 = SmbCseSubmitBufferContext(a1 + 2408);
  }
LABEL_33:
  if ( v19 < 0 )
    goto LABEL_41;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1400170b0  mov     [rsp+arg_10], rbx
0x1400170b5  push    rbp
0x1400170b6  push    rsi
0x1400170b7  push    rdi
0x1400170b8  push    r12
0x1400170ba  push    r13
0x1400170bc  push    r14
0x1400170be  push    r15
0x1400170c0  sub     rsp, 50h
0x1400170c4  mov     rax, [rcx+30h]
0x1400170c8  mov     rbx, rcx
0x1400170cb  mov     rbp, [rcx+0ED0h]
0x1400170d2  mov     dl, 0Fh
0x1400170d4  xor     r12d, r12d
0x1400170d7  xor     r13b, r13b
0x1400170da  mov     rcx, [rax+48h]
0x1400170de  mov     rsi, [rcx+30h]
0x1400170e2  lea     rcx, [rbx+200h]
0x1400170e9  mov     [rsp+88h+arg_8], rsi
0x1400170f1  mov     [rsp+88h+arg_0], 0
0x1400170fc  call    cs:__imp_RDR_PERF_ENTER
0x140017103  nop     dword ptr [rax+rax+00h]
0x140017108  cmp     [rbx+0ED8h], r12b
0x14001710f  jz      short loc_140017146
0x140017111  xor     edx, edx
0x140017113  lea     rcx, [rsi+10h]
0x140017117  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001711e  nop     dword ptr [rax+rax+00h]
0x140017123  mov     r13d, [rsi+8]
0x140017127  lea     rcx, [rsi+10h]
0x14001712b  mov     eax, r13d
0x14001712e  xor     edx, edx
0x140017130  or      eax, 10h
0x140017133  mov     [rsi+8], eax
0x140017136  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001713d  nop     dword ptr [rax+rax+00h]
0x140017142  and     r13b, 10h
0x140017146  mov     rcx, [rbx+60h]
0x14001714a  lea     r9, [rsp+88h+arg_0]
0x140017152  xor     r8d, r8d
0x140017155  xor     edx, edx
0x140017157  call    cs:__imp_SmbCeQueryOptimalBufferSize
0x14001715e  nop     dword ptr [rax+rax+00h]
0x140017163  mov     esi, [rsp+88h+arg_0]
0x14001716a  cmp     esi, 100000h
0x140017170  jb      short loc_14001717E
0x140017172  mov     esi, 100000h
0x140017177  mov     [rsp+88h+arg_0], esi
0x14001717e  mov     eax, [rbp+8]
0x140017181  cmp     esi, eax
0x140017183  jnb     loc_1400175DE
0x140017189  cmp     [rbx+0ED8h], r12b
0x140017190  jz      loc_1400175CD
0x140017196  cmp     esi, 10000h
0x14001719c  jb      loc_1400175CD
0x1400171a2  mov     esi, 10000h
0x1400171a7  mov     [rsp+88h+arg_0], esi
0x1400171ae  mov     r14, [rbx+48h]
0x1400171b2  lea     rdi, [rbx+0EE0h]
0x1400171b9  mov     r15, [rbx+50h]
0x1400171bd  mov     rcx, rdi; void *
0x1400171c0  mov     rbp, [rbx+58h]
0x1400171c4  xor     edx, edx; Val
0x1400171c6  mov     r8d, 40h ; '@'; Size
0x1400171cc  call    memset
0x1400171d1  mov     dword ptr [rdi], 424D53FEh
0x1400171d7  mov     dword ptr [rdi+20h], 0FEFFh
0x1400171de  mov     word ptr [rdi+4], 40h ; '@'
0x1400171e4  cmp     [r14+2E0h], r12b
0x1400171eb  jge     short loc_1400171FD
0x1400171ed  movzx   eax, byte ptr [rbx+21h]
0x1400171f1  shl     eax, 4
0x1400171f4  add     eax, 10h
0x1400171f7  and     eax, 70h
0x1400171fa  mov     [rdi+10h], eax
0x1400171fd  mov     word ptr [rdi+0Eh], 1
0x140017203  test    r15, r15
0x140017206  jz      short loc_14001722C
0x140017208  mov     rax, [r15+1B8h]
0x14001720f  mov     [rdi+28h], rax
0x140017213  test    dword ptr [r14+2CCh], 3000h
0x14001721e  jz      short loc_14001722C
0x140017220  movzx   eax, word ptr [r14+2BCh]
0x140017228  mov     [rdi+8], ax
0x14001722c  test    rbp, rbp
0x14001722f  jz      short loc_140017250
0x140017231  mov     eax, [rbp+1B4h]
0x140017237  mov     [rdi+24h], eax
0x14001723a  mov     rax, [rbp+1A8h]
0x140017241  mov     ecx, [rax+0B0h]
0x140017247  test    cl, 2
0x14001724a  jnz     loc_1400175EC
0x140017250  test    dword ptr [r14+2CCh], 3000h
0x14001725b  jz      short loc_140017271
0x14001725d  mov     eax, [rbx+44h]
0x140017260  mov     esi, [rsp+88h+arg_0]
0x140017267  bt      eax, 0Eh
0x14001726b  jb      loc_14001760C
0x140017271  mov     rax, [rsp+88h+arg_8]
0x140017279  xorps   xmm0, xmm0
0x14001727c  mov     word ptr [rbx+0EECh], 0Eh
0x140017285  xor     r15d, r15d
0x140017288  movups  xmmword ptr [rbx+0F20h], xmm0
0x14001728f  movups  xmmword ptr [rbx+0F30h], xmm0
0x140017296  mov     word ptr [rbx+0F20h], 21h ; '!'
0x14001729f  movups  xmm0, xmmword ptr [rax+1Ch]
0x1400172a3  movzx   eax, byte ptr [rbx+0ED9h]
0x1400172aa  mov     dword ptr [rbx+0F38h], 20060h
0x1400172b4  movups  xmmword ptr [rbx+0F28h], xmm0
0x1400172bb  mov     [rbx+0F22h], al
0x1400172c1  mov     [rbx+0F23h], r13b
0x1400172c8  mov     [rbx+0F24h], r15d
0x1400172cf  mov     [rbx+0F3Ch], esi
0x1400172d5  mov     word ptr [rbx+0F40h], 2Ah ; '*'
0x1400172de  cmp     [rbx+0ED8h], r12b
0x1400172e5  jz      short loc_140017333
0x1400172e7  movups  xmm0, xmmword ptr [rdi]
0x1400172ea  movups  xmmword ptr [rbx+0F50h], xmm0
0x1400172f1  movups  xmm1, xmmword ptr [rdi+10h]
0x1400172f5  movups  xmmword ptr [rbx+0F60h], xmm1
0x1400172fc  movups  xmm0, xmmword ptr [rdi+20h]
0x140017300  movups  xmmword ptr [rbx+0F70h], xmm0
0x140017307  movups  xmm1, xmmword ptr [rdi+30h]
0x14001730b  movups  xmmword ptr [rbx+0F80h], xmm1
0x140017312  movups  xmm0, xmmword ptr [rdi+40h]
0x140017316  movups  xmmword ptr [rbx+0F90h], xmm0
0x14001731d  movups  xmm1, xmmword ptr [rdi+50h]
0x140017321  movups  xmmword ptr [rbx+0FA0h], xmm1
0x140017328  movzx   eax, word ptr [rdi+60h]
0x14001732c  mov     [rbx+0FB0h], ax
0x140017333  xor     r9d, r9d
0x140017336  mov     [rsp+88h+var_68], r15
0x14001733b  xor     r8d, r8d
0x14001733e  mov     edx, 62h ; 'b'
0x140017343  mov     rcx, rdi
0x140017346  call    cs:__imp_RxAllocateMdl2
0x14001734d  nop     dword ptr [rax+rax+00h]
0x140017352  mov     rsi, rax
0x140017355  test    rax, rax
0x140017358  jz      loc_140017618
0x14001735e  mov     rcx, rax; MemoryDescriptorList
0x140017361  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140017368  nop     dword ptr [rax+rax+00h]
0x14001736d  mov     edx, [rsp+88h+arg_0]
0x140017374  mov     rcx, rbx
0x140017377  call    cs:__imp_SmbCeAllocateExchangeBuffer
0x14001737e  nop     dword ptr [rax+rax+00h]
0x140017383  mov     r14, rax
0x140017386  test    rax, rax
0x140017389  jz      loc_140017618
0x14001738f  mov     edx, [rsp+88h+arg_0]
0x140017396  xor     r9d, r9d
0x140017399  xor     r8d, r8d
0x14001739c  mov     [rsp+88h+var_68], r15
0x1400173a1  mov     rcx, rax
0x1400173a4  call    cs:__imp_RxAllocateMdl2
0x1400173ab  nop     dword ptr [rax+rax+00h]
0x1400173b0  mov     r12, rax
0x1400173b3  test    rax, rax
0x1400173b6  jz      loc_140017618
0x1400173bc  mov     rcx, rax; MemoryDescriptorList
0x1400173bf  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400173c6  nop     dword ptr [rax+rax+00h]
0x1400173cb  mov     ecx, [rsp+88h+arg_0]
0x1400173d2  mov     r9d, 62h ; 'b'
0x1400173d8  mov     [rsp+88h+var_40], 4
0x1400173e0  mov     r8, rsi
0x1400173e3  mov     [rsp+88h+var_48], r15w
0x1400173e9  mov     rdx, rbx
0x1400173ec  mov     dword ptr [rsp+88h+var_50], r15d
0x1400173f1  mov     [rsp+88h+var_58], r15
0x1400173f6  mov     dword ptr [rsp+88h+var_60], ecx
0x1400173fa  lea     rcx, [rbx+400h]
0x140017401  mov     [rsp+88h+var_68], r12
0x140017406  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x14001740d  nop     dword ptr [rax+rax+00h]
0x140017412  mov     edi, eax
0x140017414  test    eax, eax
0x140017416  jnz     loc_1400175AE
0x14001741c  mov     eax, [rsp+88h+arg_0]
0x140017423  lea     rcx, [rbx+400h]
0x14001742a  dec     eax
0x14001742c  mov     [rbx+6C8h], r14
0x140017433  shr     eax, 10h
0x140017436  mov     rsi, r15
0x140017439  inc     eax
0x14001743b  mov     r12, r15
0x14001743e  mov     [rbx+450h], eax
0x140017444  movzx   eax, byte ptr [rbx+0ED9h]
0x14001744b  bts     eax, 10h
0x14001744f  mov     [rbx+760h], eax
0x140017455  call    cs:__imp_SmbCseSubmitBufferContext
0x14001745c  nop     dword ptr [rax+rax+00h]
0x140017461  mov     edi, eax
0x140017463  test    eax, eax
0x140017465  js      loc_14001761D
0x14001746b  cmp     [rbx+0ED8h], sil
0x140017472  jz      loc_1400175B4
0x140017478  lea     rcx, [rbx+0F50h]
0x14001747f  mov     [rbx+0F93h], sil
0x140017486  xor     r9d, r9d
0x140017489  mov     [rsp+88h+var_68], r15
0x14001748e  xor     r8d, r8d
0x140017491  mov     edx, 62h ; 'b'
0x140017496  call    cs:__imp_RxAllocateMdl2
0x14001749d  nop     dword ptr [rax+rax+00h]
0x1400174a2  mov     rsi, rax
0x1400174a5  test    rax, rax
0x1400174a8  jz      loc_140017618
0x1400174ae  mov     rcx, rax; MemoryDescriptorList
0x1400174b1  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400174b8  nop     dword ptr [rax+rax+00h]
0x1400174bd  mov     edx, 400h
0x1400174c2  mov     [rsp+88h+arg_0], 400h
0x1400174cd  mov     rcx, rbx
0x1400174d0  mov     dword ptr [rbx+0FACh], 400h
0x1400174da  call    cs:__imp_SmbCeAllocateExchangeBuffer
0x1400174e1  nop     dword ptr [rax+rax+00h]
0x1400174e6  mov     r14, rax
0x1400174e9  test    rax, rax
0x1400174ec  jz      loc_140017618
0x1400174f2  mov     edx, [rsp+88h+arg_0]
0x1400174f9  xor     r9d, r9d
0x1400174fc  xor     r8d, r8d
0x1400174ff  mov     [rsp+88h+var_68], r15
0x140017504  mov     rcx, rax
0x140017507  call    cs:__imp_RxAllocateMdl2
0x14001750e  nop     dword ptr [rax+rax+00h]
0x140017513  mov     r12, rax
0x140017516  test    rax, rax
0x140017519  jz      loc_140017618
0x14001751f  mov     rcx, rax; MemoryDescriptorList
0x140017522  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140017529  nop     dword ptr [rax+rax+00h]
0x14001752e  mov     ecx, [rsp+88h+arg_0]
0x140017535  mov     r9d, 62h ; 'b'
0x14001753b  mov     [rsp+88h+var_40], 4
0x140017543  mov     r8, rsi
0x140017546  mov     [rsp+88h+var_48], r15w
0x14001754c  mov     rdx, rbx
0x14001754f  mov     dword ptr [rsp+88h+var_50], r15d
0x140017554  mov     [rsp+88h+var_58], r15
0x140017559  mov     dword ptr [rsp+88h+var_60], ecx
0x14001755d  lea     rcx, [rbx+968h]
0x140017564  mov     [rsp+88h+var_68], r12
0x140017569  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x140017570  nop     dword ptr [rax+rax+00h]
0x140017575  mov     edi, eax
0x140017577  test    eax, eax
0x140017579  jnz     short loc_1400175AE
0x14001757b  mov     [rbx+0C30h], r14
0x140017582  lea     rcx, [rbx+968h]
0x140017589  movzx   eax, byte ptr [rbx+0ED9h]
0x140017590  mov     rsi, r15
0x140017593  bts     eax, 10h
0x140017597  mov     r12, r15
0x14001759a  mov     [rbx+0CC8h], eax
0x1400175a0  call    cs:__imp_SmbCseSubmitBufferContext
0x1400175a7  nop     dword ptr [rax+rax+00h]
0x1400175ac  mov     edi, eax
0x1400175ae  test    edi, edi
0x1400175b0  js      short loc_14001761D
0x1400175b2  mov     eax, edi
0x1400175b4  mov     rbx, [rsp+88h+arg_10]
0x1400175bc  add     rsp, 50h
0x1400175c0  pop     r15
0x1400175c2  pop     r14
0x1400175c4  pop     r13
0x1400175c6  pop     r12
0x1400175c8  pop     rdi
0x1400175c9  pop     rsi
0x1400175ca  pop     rbp
0x1400175cb  retn
0x1400175cd  cmp     esi, 10000h
0x1400175d3  jbe     loc_1400171A2
0x1400175d9  jmp     loc_1400171AE
0x1400175de  mov     esi, eax
0x1400175e0  mov     [rsp+88h+arg_0], eax
0x1400175e7  jmp     loc_140017189
0x1400175ec  mov     eax, [rbx+44h]
0x1400175ef  mov     esi, [rsp+88h+arg_0]
0x1400175f6  bt      eax, 0Fh
0x1400175fa  jnb     loc_140017250
0x140017600  or      dword ptr [rdi+10h], 10000000h
0x140017607  jmp     loc_140017250
0x14001760c  or      dword ptr [rdi+10h], 20000000h
0x140017613  jmp     loc_140017271
0x140017618  mov     edi, 0C000009Ah
0x14001761d  mov     rcx, rsi
0x140017620  call    cs:__imp_RxFreeMdl
0x140017627  nop     dword ptr [rax+rax+00h]
0x14001762c  mov     rcx, r12
0x14001762f  call    cs:__imp_RxFreeMdl
0x140017636  nop     dword ptr [rax+rax+00h]
0x14001763b  jmp     loc_1400175B2
```
