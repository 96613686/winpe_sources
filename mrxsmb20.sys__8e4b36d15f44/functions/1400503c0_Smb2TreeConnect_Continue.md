# Smb2TreeConnect_Continue

- ea: `0x1400503c0`
- end: `0x1400506b4`
- name: `Smb2TreeConnect_Continue`
- size: `756`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000e700`
- `0x1400290f8`
- `0x140029730`
- `0x1400297a8`
- `0x1400503c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140050630`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140050630`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140050574`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140050574`
- `rdbss!RxFreeMdl` at `0x140050687`
- `rdbss!RxFreeMdl` at `0x140050696`
- `rdbss!RxFreeMdl` at `0x140050687`
- `rdbss!RxFreeMdl` at `0x140050696`
- `rdbss!RxAllocateMdl2` at `0x140050550`
- `rdbss!RxAllocateMdl2` at `0x140050596`
- `rdbss!RxAllocateMdl2` at `0x140050550`
- `rdbss!RxAllocateMdl2` at `0x140050596`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140050650`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140050650`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14005066a`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14005066a`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x1400505e2`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x1400505e2`

## pseudocode

```c
__int64 __fastcall Smb2TreeConnect_Continue(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v3; // rdi
  __int64 v4; // r11
  __m128i si128; // xmm0
  __int64 v6; // rcx
  __int16 v7; // cx
  unsigned int v8; // r8d
  unsigned int i; // r9d
  __int64 v10; // rdx
  unsigned int v11; // edi
  struct _MDL *Mdl2; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  struct _MDL *v16; // rbp
  __int64 v17; // rsi
  int v18; // edi
  __int64 v19; // rax
  PVOID v20; // rax
  __int64 v21; // rcx

  v1 = a1 + 3864;
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL);
  SmbCeBuildSmb2Header(a1, a1 + 3864, 64);
  *(_DWORD *)(a1 + 3880) |= 8u;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(_WORD *)(a1 + 3876) = 11;
  *(_DWORD *)(a1 + 3928) = 57;
  *(_DWORD *)(a1 + 3932) = 1311236;
  *(_DWORD *)(a1 + 3960) = 0;
  *(_DWORD *)(a1 + 3952) = 120;
  *(_QWORD *)(a1 + 3964) = 120;
  *(_DWORD *)(a1 + 3976) = 1;
  *(_DWORD *)(a1 + 3972) = 24;
  *(__m128i *)(a1 + 3936) = si128;
  *(_WORD *)(a1 + 4004) = (*(_BYTE *)(v3 + 607) != 0) + 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DD(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids,
      *(unsigned __int8 *)(v4 + 1312),
      *(unsigned __int8 *)(v3 + 607));
  }
  v6 = *(_QWORD *)(a1 + 72);
  *(_DWORD *)(a1 + 3984) = *(_DWORD *)(v6 + 680);
  *(_OWORD *)(a1 + 3988) = *(_OWORD *)(v6 + 684);
  v7 = *(_WORD *)(*(_QWORD *)(a1 + 72) + 740LL);
  if ( v7 )
  {
    v8 = 1;
    *(_WORD *)(a1 + 4008) = v7;
  }
  else
  {
    v8 = *(_DWORD *)(v3 + 624);
    for ( i = 0; i < v8; *(_WORD *)(a1 + 2 * v10 + 4008) = *(_WORD *)(*(_QWORD *)(v3 + 616) + 2 * v10) )
      v10 = i++;
  }
  *(_WORD *)(a1 + 4006) = v8;
  v11 = 2 * v8 + 144;
  *(_DWORD *)(a1 + 3956) = 2 * v8 + 24;
  Mdl2 = (struct _MDL *)RxAllocateMdl2(v1, v11, 0, 0, 0);
  v16 = Mdl2;
  if ( !Mdl2 )
  {
    v17 = 0;
LABEL_12:
    v18 = -1073741670;
LABEL_24:
    Smb2ProcessNegotiateValidationFailure(a1, v13, v14, v15);
    RxFreeMdl(v16);
    RxFreeMdl(v17);
    return (unsigned int)v18;
  }
  MmBuildMdlForNonPagedPool(Mdl2);
  v19 = RxAllocateMdl2(a1 + 3988, 24, 0, 0, 0);
  v17 = v19;
  if ( !v19 )
    goto LABEL_12;
  v18 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 2416, a1, v16, v11, v19, 24, 0, 0, 0, 4100);
  if ( !v18 )
  {
    if ( (unsigned __int8)TreeConnectContinueExchangeRequiresEncryption(a1) )
      *(_DWORD *)(a1 + 2420) |= 0x8000u;
    if ( (*(_BYTE *)(v17 + 10) & 5) != 0 )
      v20 = *(PVOID *)(v17 + 24);
    else
      v20 = MmMapLockedPagesSpecifyCache((PMDL)v17, 0, MmCached, 0, 0, 0x40000000u);
    *(_QWORD *)(a1 + 3128) = v20;
    v21 = a1 + 2416;
    if ( !v20 )
    {
      v18 = -1073741670;
      SmbCseFinalizeBufferContext(v21);
      v16 = 0;
      v17 = 0;
      goto LABEL_24;
    }
    v16 = 0;
    v17 = 0;
    v18 = SmbCseSubmitBufferContext(v21);
  }
  if ( v18 < 0 )
    goto LABEL_24;
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400503c0  push    rbx
0x1400503c2  push    rbp
0x1400503c3  push    rsi
0x1400503c4  push    rdi
0x1400503c5  push    r12
0x1400503c7  push    r14
0x1400503c9  push    r15
0x1400503cb  sub     rsp, 50h
0x1400503cf  mov     rax, [rcx+60h]
0x1400503d3  lea     rsi, [rcx+0F18h]
0x1400503da  mov     r8d, 40h ; '@'
0x1400503e0  mov     rdx, rsi
0x1400503e3  mov     rbx, rcx
0x1400503e6  mov     rdi, [rax+188h]
0x1400503ed  mov     rax, [rcx+48h]
0x1400503f1  mov     r11, [rax+18h]
0x1400503f5  call    SmbCeBuildSmb2Header
0x1400503fa  or      dword ptr [rbx+0F28h], 8
0x140050401  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140050409  xor     r15d, r15d
0x14005040c  mov     word ptr [rbx+0F24h], 0Bh
0x140050415  mov     dword ptr [rbx+0F58h], 39h ; '9'
0x14005041f  mov     dword ptr [rbx+0F5Ch], 140204h
0x140050429  lea     eax, [r15+78h]
0x14005042d  mov     [rbx+0F78h], r15d
0x140050434  lea     r12d, [r15+1]
0x140050438  mov     [rbx+0F70h], eax
0x14005043e  mov     [rbx+0F7Ch], rax
0x140050445  mov     [rbx+0F88h], r12d
0x14005044c  mov     dword ptr [rbx+0F84h], 18h
0x140050456  movups  xmmword ptr [rbx+0F60h], xmm0
0x14005045d  mov     al, [rdi+25Fh]; __annotation("TMF:",
0x140050463  neg     al
0x140050465  lea     rax, WPP_GLOBAL_Control
0x14005046c  sbb     cx, cx
0x14005046f  neg     cx
0x140050472  add     cx, r12w
0x140050476  mov     [rbx+0FA4h], cx
0x14005047d  mov     rcx, cs:WPP_GLOBAL_Control
0x140050484  cmp     rcx, rax
0x140050487  jz      short loc_1400504BD
0x140050489  mov     eax, [rcx+2Ch]
0x14005048c  test    al, 4
0x14005048e  jz      short loc_1400504BD
0x140050490  cmp     byte ptr [rcx+29h], 4
0x140050494  jb      short loc_1400504BD
0x140050496  movzx   eax, byte ptr [rdi+25Fh]
0x14005049d  lea     edx, [r15+12h]
0x1400504a1  movzx   r9d, byte ptr [r11+520h]
0x1400504a9  lea     r8, WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids
0x1400504b0  mov     rcx, [rcx+18h]
0x1400504b4  mov     [rsp+88h+BugCheckOnFailure], eax
0x1400504b8  call    WPP_SF_DD
0x1400504bd  mov     rcx, [rbx+48h]
0x1400504c1  mov     eax, [rcx+2A8h]
0x1400504c7  mov     [rbx+0F90h], eax
0x1400504cd  movups  xmm0, xmmword ptr [rcx+2ACh]
0x1400504d4  movdqu  xmmword ptr [rbx+0F94h], xmm0
0x1400504dc  mov     rax, [rbx+48h]
0x1400504e0  movzx   ecx, word ptr [rax+2E4h]
0x1400504e7  test    cx, cx
0x1400504ea  jnz     short loc_14005051B
0x1400504ec  mov     r8d, [rdi+270h]
0x1400504f3  mov     r9d, r15d
0x1400504f6  test    r8d, r8d
0x1400504f9  jz      short loc_140050525
0x1400504fb  mov     rax, [rdi+268h]
0x140050502  mov     edx, r9d
0x140050505  add     r9d, r12d
0x140050508  movzx   ecx, word ptr [rax+rdx*2]
0x14005050c  mov     [rbx+rdx*2+0FA8h], cx
0x140050514  cmp     r9d, r8d
0x140050517  jb      short loc_1400504FB
0x140050519  jmp     short loc_140050525
0x14005051b  mov     r8d, r12d
0x14005051e  mov     [rbx+0FA8h], cx
0x140050525  lea     edx, [r8+r8]
0x140050529  mov     [rbx+0FA6h], r8w
0x140050531  lea     eax, [rdx+18h]
0x140050534  mov     qword ptr [rsp+88h+BugCheckOnFailure], r15
0x140050539  lea     edi, [rdx+90h]
0x14005053f  mov     [rbx+0F74h], eax
0x140050545  mov     edx, edi
0x140050547  xor     r9d, r9d
0x14005054a  xor     r8d, r8d
0x14005054d  mov     rcx, rsi
0x140050550  call    cs:__imp_RxAllocateMdl2
0x140050557  nop     dword ptr [rax+rax+00h]
0x14005055c  mov     rbp, rax
0x14005055f  test    rax, rax
0x140050562  jnz     short loc_140050571
0x140050564  mov     rsi, r15
0x140050567  mov     edi, 0C000009Ah
0x14005056c  jmp     loc_14005067C
0x140050571  mov     rcx, rbp; MemoryDescriptorList
0x140050574  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14005057b  nop     dword ptr [rax+rax+00h]
0x140050580  xor     r9d, r9d
0x140050583  mov     qword ptr [rsp+88h+BugCheckOnFailure], r15
0x140050588  lea     rcx, [rbx+0F94h]
0x14005058f  xor     r8d, r8d
0x140050592  lea     edx, [r9+18h]
0x140050596  call    cs:__imp_RxAllocateMdl2
0x14005059d  nop     dword ptr [rax+rax+00h]
0x1400505a2  mov     rsi, rax
0x1400505a5  test    rax, rax
0x1400505a8  jz      short loc_140050567
0x1400505aa  mov     [rsp+88h+var_40], 1004h
0x1400505b2  lea     r14, [rbx+970h]
0x1400505b9  mov     [rsp+88h+var_48], r15w
0x1400505bf  mov     r9d, edi
0x1400505c2  mov     [rsp+88h+var_50], r15d
0x1400505c7  mov     r8, rbp
0x1400505ca  mov     [rsp+88h+var_58], r15
0x1400505cf  mov     rdx, rbx
0x1400505d2  mov     [rsp+88h+Priority], 18h
0x1400505da  mov     rcx, r14
0x1400505dd  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax
0x1400505e2  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x1400505e9  nop     dword ptr [rax+rax+00h]
0x1400505ee  mov     edi, eax
0x1400505f0  test    eax, eax
0x1400505f2  jnz     loc_140050678
0x1400505f8  mov     rcx, rbx
0x1400505fb  call    TreeConnectContinueExchangeRequiresEncryption
0x140050600  test    al, al
0x140050602  jz      short loc_14005060C
0x140050604  bts     dword ptr [rbx+974h], 0Fh
0x14005060c  test    byte ptr [rsi+0Ah], 5
0x140050610  jz      short loc_140050618
0x140050612  mov     rax, [rsi+18h]
0x140050616  jmp     short loc_14005063C
0x140050618  mov     [rsp+88h+Priority], 40000000h; Priority
0x140050620  xor     r9d, r9d; RequestedAddress
0x140050623  mov     r8d, r12d; CacheType
0x140050626  mov     [rsp+88h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x14005062b  xor     edx, edx; AccessMode
0x14005062d  mov     rcx, rsi; MemoryDescriptorList
0x140050630  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140050637  nop     dword ptr [rax+rax+00h]
0x14005063c  mov     [rbx+0C38h], rax
0x140050643  mov     rcx, r14
0x140050646  test    rax, rax
0x140050649  jnz     short loc_140050664
0x14005064b  mov     edi, 0C000009Ah
0x140050650  call    cs:__imp_SmbCseFinalizeBufferContext
0x140050657  nop     dword ptr [rax+rax+00h]
0x14005065c  mov     rbp, r15
0x14005065f  mov     rsi, r15
0x140050662  jmp     short loc_14005067C
0x140050664  mov     rbp, r15
0x140050667  mov     rsi, r15
0x14005066a  call    cs:__imp_SmbCseSubmitBufferContext
0x140050671  nop     dword ptr [rax+rax+00h]
0x140050676  mov     edi, eax
0x140050678  test    edi, edi
0x14005067a  jns     short loc_1400506A2
0x14005067c  mov     rcx, rbx
0x14005067f  call    Smb2ProcessNegotiateValidationFailure
0x140050684  mov     rcx, rbp
0x140050687  call    cs:__imp_RxFreeMdl
0x14005068e  nop     dword ptr [rax+rax+00h]
0x140050693  mov     rcx, rsi
0x140050696  call    cs:__imp_RxFreeMdl
0x14005069d  nop     dword ptr [rax+rax+00h]
0x1400506a2  mov     eax, edi
0x1400506a4  add     rsp, 50h
0x1400506a8  pop     r15
0x1400506aa  pop     r14
0x1400506ac  pop     r12
0x1400506ae  pop     rdi
0x1400506af  pop     rsi
0x1400506b0  pop     rbp
0x1400506b1  pop     rbx
0x1400506b2  retn
```
