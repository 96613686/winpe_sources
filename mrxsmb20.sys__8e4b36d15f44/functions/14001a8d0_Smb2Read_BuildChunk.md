# Smb2Read_BuildChunk

- ea: `0x14001a8d0`
- end: `0x14001b008`
- name: `Smb2Read_BuildChunk`
- size: `1848`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int128 *, __int64, unsigned int, ULONG Length, int, unsigned __int16, char)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001a2b0`
- `0x14002d950`
- `0x14002dde0`

## callees

- `0x1400191c0`
- `0x14001a8d0`
- `0x140028950`
- `0x1400297fc`
- `0x14002e344`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001a9c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a9c0`
- `ntoskrnl!ExAllocatePool2` at `0x14001a969`
- `ntoskrnl!ExAllocatePool2` at `0x14001a969`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001af1d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001af1d`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001abda`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001ac6f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001acc2`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001abda`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001ac6f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001acc2`
- `ntoskrnl!IoBuildPartialMdl` at `0x14001ad65`
- `ntoskrnl!IoBuildPartialMdl` at `0x14001ad65`
- `rdbss!RxFreeMdl` at `0x14001a984`
- `rdbss!RxFreeMdl` at `0x14001a993`
- `rdbss!RxFreeMdl` at `0x14001abb7`
- `rdbss!RxFreeMdl` at `0x14001abc6`
- `rdbss!RxFreeMdl` at `0x14001a984`
- `rdbss!RxFreeMdl` at `0x14001a993`
- `rdbss!RxFreeMdl` at `0x14001abb7`
- `rdbss!RxFreeMdl` at `0x14001abc6`
- `rdbss!RxAllocateMdl2` at `0x14001ab9c`
- `rdbss!RxAllocateMdl2` at `0x14001ac54`
- `rdbss!RxAllocateMdl2` at `0x14001aca7`
- `rdbss!RxAllocateMdl2` at `0x14001ad18`
- `rdbss!RxAllocateMdl2` at `0x14001ab9c`
- `rdbss!RxAllocateMdl2` at `0x14001ac54`
- `rdbss!RxAllocateMdl2` at `0x14001aca7`
- `rdbss!RxAllocateMdl2` at `0x14001ad18`
- `mrxsmb!SmbCeAllocateImplicitExchangeBuffer` at `0x14001a921`
- `mrxsmb!SmbCeAllocateImplicitExchangeBuffer` at `0x14001a921`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14001adca`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14001aea6`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14001adca`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14001aea6`

## pseudocode

```c
__int64 __fastcall Smb2Read_BuildChunk(
        __int64 *a1,
        __int64 a2,
        __int128 *a3,
        __int64 a4,
        unsigned int a5,
        ULONG Length,
        int a7,
        unsigned __int16 a8,
        char a9)
{
  unsigned __int16 v9; // bx
  struct _MDL *v10; // r15
  char v11; // bp
  unsigned int v14; // r13d
  __int64 ImplicitExchangeBuffer; // rax
  __int64 v16; // rdi
  _OWORD *v17; // r14
  __int64 Pool2; // rax
  int v19; // ebx
  unsigned int v20; // r11d
  ULONG v21; // r10d
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int128 v26; // xmm0
  struct _MDL *Mdl2; // rax
  __int64 v28; // rcx
  _QWORD *v29; // r12
  __int64 v30; // rbp
  __int64 v31; // r13
  __int64 v32; // rcx
  __int64 v33; // rax
  struct _MDL *v34; // rbx
  unsigned int v35; // ecx
  __int64 v36; // r13
  __int64 v37; // rax
  unsigned int v38; // ecx
  int *v39; // rax
  PVOID v40; // rax
  int v41; // r8d
  int v42; // r8d
  unsigned int v45; // [rsp+98h] [rbp+10h]
  int v47; // [rsp+D0h] [rbp+48h]

  v9 = a8;
  v10 = 0;
  v11 = 0;
  *a1 = 0;
  v14 = a8 + 113;
  v45 = v14;
  if ( *(_BYTE *)(a2 + 1052)
    || (ImplicitExchangeBuffer = SmbCeAllocateImplicitExchangeBuffer(a2, (unsigned int)a8 + 145)) == 0
    || (v16 = a2 + 1056, *(_BYTE *)(a2 + 1052) = 1, v17 = (_OWORD *)(ImplicitExchangeBuffer + 32), v11 = 1, a2 == -1056) )
  {
    Pool2 = ExAllocatePool2(66, (v14 + 1407LL) & 0xFFFFFFFFFFFFFFF8uLL, 1834181458);
    v16 = Pool2;
    if ( !Pool2 )
      goto LABEL_5;
    v17 = (_OWORD *)(Pool2 + 1400);
  }
  memset(v17, 0, v14);
  if ( !v17 )
  {
LABEL_5:
    v19 = -1073741670;
    RxFreeMdl(0);
    RxFreeMdl(0);
    if ( !v16 )
      return (unsigned int)v19;
    goto LABEL_6;
  }
  v20 = a5;
  v21 = Length;
  *(_DWORD *)(v16 + 1384) = HIWORD(a5);
  v47 = a9 & 4;
  *(_DWORD *)(v16 + 1392) = a5;
  *(_DWORD *)(v16 + 1396) = Length;
  *(_DWORD *)(v16 + 1388) = ((Length - 1) >> 16) + 1;
  if ( !v47 )
  {
    v23 = *(_QWORD *)(a2 + 72);
    v24 = *(_QWORD *)(a2 + 80);
    v25 = *(_QWORD *)(a2 + 88);
    *v17 = 0;
    v17[1] = 0;
    v17[2] = 0;
    v17[3] = 0;
    *(_DWORD *)v17 = 1112364030;
    *((_DWORD *)v17 + 8) = 65279;
    *((_WORD *)v17 + 2) = 64;
    if ( *(char *)(v23 + 736) < 0 )
      *((_DWORD *)v17 + 4) = (16 * *(_BYTE *)(a2 + 33) + 16) & 0x70;
    *((_WORD *)v17 + 7) = 1;
    if ( v24 )
    {
      *((_QWORD *)v17 + 5) = *(_QWORD *)(v24 + 440);
      if ( (*(_DWORD *)(v23 + 716) & 0x3000) != 0 )
        *((_WORD *)v17 + 4) = *(_WORD *)(v23 + 700);
    }
    if ( v25 )
    {
      *((_DWORD *)v17 + 9) = *(_DWORD *)(v25 + 436);
      if ( (*(_DWORD *)(*(_QWORD *)(v25 + 424) + 176LL) & 2) != 0 && (*(_DWORD *)(a2 + 68) & 0x8000) != 0 )
        *((_DWORD *)v17 + 4) |= 0x10000000u;
    }
    if ( (*(_DWORD *)(v23 + 716) & 0x3000) != 0 && (*(_DWORD *)(a2 + 68) & 0x4000) != 0 )
      *((_DWORD *)v17 + 4) |= 0x20000000u;
    *((_WORD *)v17 + 6) = 8;
    *((_WORD *)v17 + 32) = 49;
    *((_BYTE *)v17 + 67) = 0;
    *(_QWORD *)((char *)v17 + 100) = 0;
    *((_DWORD *)v17 + 27) = 0;
    v26 = *a3;
    *((_DWORD *)v17 + 17) = Length;
    *((_QWORD *)v17 + 9) = a4 + a5;
    *((_DWORD *)v17 + 24) = 0;
    *((_BYTE *)v17 + 66) = 80;
    v17[5] = v26;
    *((_BYTE *)v17 + 112) = 0;
    if ( (a9 & 1) != 0 )
      *((_BYTE *)v17 + 67) = 1;
    if ( (unsigned int)Smb2IsTrafficCompressionActive(a2) )
      *((_BYTE *)v17 + 67) |= 2u;
    if ( a8 )
    {
      *((_DWORD *)v17 + 25) = a7;
      *((_WORD *)v17 + 55) = a8;
      *((_WORD *)v17 + 54) = 112;
    }
    Mdl2 = (struct _MDL *)RxAllocateMdl2(v17, v14, 0, 0, 0);
    v10 = Mdl2;
    if ( !Mdl2 )
    {
      v28 = 0;
LABEL_31:
      v19 = -1073741670;
LABEL_32:
      RxFreeMdl(v28);
      RxFreeMdl(v10);
LABEL_6:
      if ( v16 == a2 + 1056 )
        *(_BYTE *)(a2 + 1052) = 0;
      else
        ExFreePoolWithTag((PVOID)v16, 0x6D536352u);
      return (unsigned int)v19;
    }
    MmBuildMdlForNonPagedPool(Mdl2);
    v21 = Length;
    v20 = a5;
    if ( v11 )
      v10->MdlFlags |= 0x1000u;
  }
  if ( a8 && (v29 = (_QWORD *)(a2 + 1032), !*(_QWORD *)(a2 + 1032)) && (*(_DWORD *)(a2 + 68) & 0x1000800) != 0 )
  {
    __int2c();
  }
  else
  {
    v29 = (_QWORD *)(a2 + 1032);
    if ( !a8 )
      goto LABEL_43;
  }
  if ( *v29 )
  {
    v30 = RxAllocateMdl2(v20 + (*v29 & 0xFFFFFFFFFFFFFFF8uLL), v21, 0, 0, 0);
    v28 = v30;
    if ( !v30 )
      goto LABEL_31;
    MmBuildMdlForNonPagedPool((PMDL)v30);
    v31 = v30;
    goto LABEL_56;
  }
LABEL_43:
  v32 = *(_QWORD *)(a2 + 1024);
  if ( v32 )
  {
    v30 = RxAllocateMdl2(v20 + (v32 & 0xFFFFFFFFFFFFFFF8uLL), v21, 0, 0, 0);
    v28 = v30;
    if ( !v30 )
      goto LABEL_31;
    MmBuildMdlForNonPagedPool((PMDL)v30);
  }
  else
  {
    v33 = *(_QWORD *)(a2 + 2464);
    if ( v33 )
    {
      v34 = *(struct _MDL **)(a2 + 2456);
      v35 = *(_DWORD *)(v33 + 8);
    }
    else
    {
      v35 = 0;
      v34 = *(struct _MDL **)(*(_QWORD *)(a2 + 48) + 544LL);
    }
    v36 = v20;
    v30 = RxAllocateMdl2((char *)v34->StartVa + v20 + (unsigned __int64)v35 + v34->ByteOffset, v21, 0, 0, 0);
    if ( !v30 )
    {
      v28 = 0;
      goto LABEL_31;
    }
    v37 = *(_QWORD *)(a2 + 2464);
    if ( v37 )
      v38 = *(_DWORD *)(v37 + 8);
    else
      v38 = 0;
    IoBuildPartialMdl(v34, (PMDL)v30, (char *)v34->StartVa + v36 + v38 + v34->ByteOffset, Length);
    v9 = a8;
  }
  v31 = v30;
  if ( !v9 )
  {
    v19 = SmbCseInitializeBufferContextWithMemoryRegistration(v16, a2, v10, v45, v30, Length, 0, 0, 0, 4);
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqs(WPP_GLOBAL_Control->AttachedDevice, 11, v41, a2, v16, (__int64)&dword_14003ECEC);
      }
LABEL_73:
      v28 = v30;
      goto LABEL_32;
    }
    goto LABEL_66;
  }
LABEL_56:
  if ( v47 )
    __int2c();
  v19 = SmbCseInitializeBufferContextWithMemoryRegistration(v16, a2, v10, v45, 0, 0, v30, Length, v9, 8196);
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v39 = (int *)"D";
      if ( !a8 )
        v39 = &dword_14003ECEC;
      WPP_SF_qqs(WPP_GLOBAL_Control->AttachedDevice, 10, (_DWORD)WPP_GLOBAL_Control, a2, v16, (__int64)v39);
      v28 = v30;
      goto LABEL_32;
    }
    goto LABEL_73;
  }
  if ( *v29 )
  {
LABEL_66:
    if ( (*(_BYTE *)(v30 + 10) & 5) != 0 )
      v40 = *(PVOID *)(v30 + 24);
    else
      v40 = MmMapLockedPagesSpecifyCache((PMDL)v30, 0, MmCached, 0, 0, 0x40000010u);
    *(_QWORD *)(v16 + 712) = v40;
    if ( !v40 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids, a2);
      }
      v28 = v31;
      goto LABEL_31;
    }
  }
  v42 = *(_DWORD *)(v16 + 1388);
  *(_DWORD *)(v16 + 80) = v42;
  *(_QWORD *)(v16 + 88) = v17;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_a0b49660c994371bf323b193efb7fcea_Traceguids,
      v16,
      *(_DWORD *)(v16 + 1384),
      v42);
  }
  *a1 = v16;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14001a8d0  mov     [rsp+arg_18], rbx
0x14001a8d5  mov     [rsp+arg_10], r8
0x14001a8da  mov     [rsp+arg_0], rcx
0x14001a8df  push    rbp
0x14001a8e0  push    rsi
0x14001a8e1  push    rdi
0x14001a8e2  push    r12
0x14001a8e4  push    r13
0x14001a8e6  push    r14
0x14001a8e8  push    r15
0x14001a8ea  sub     rsp, 50h
0x14001a8ee  movzx   ebx, [rsp+88h+arg_38]
0x14001a8f6  xor     r15d, r15d
0x14001a8f9  xor     bpl, bpl
0x14001a8fc  mov     [rcx], r15
0x14001a8ff  mov     r12, r9
0x14001a902  mov     rsi, rdx
0x14001a905  lea     r13d, [rbx+71h]
0x14001a909  mov     [rsp+88h+arg_8], r13d
0x14001a911  cmp     [rdx+41Ch], bpl
0x14001a918  jnz     short loc_14001A950
0x14001a91a  lea     edx, [r13+20h]
0x14001a91e  mov     rcx, rsi
0x14001a921  call    cs:__imp_SmbCeAllocateImplicitExchangeBuffer
0x14001a928  nop     dword ptr [rax+rax+00h]
0x14001a92d  test    rax, rax
0x14001a930  jz      short loc_14001A950
0x14001a932  lea     rdi, [rsi+420h]
0x14001a939  mov     byte ptr [rsi+41Ch], 1
0x14001a940  lea     r14, [rax+20h]
0x14001a944  mov     bpl, 1
0x14001a947  test    rdi, rdi
0x14001a94a  jnz     loc_14001A9D8
0x14001a950  mov     edx, r13d
0x14001a953  mov     ecx, 42h ; 'B'
0x14001a958  add     rdx, 57Fh
0x14001a95f  mov     r8d, 6D536352h
0x14001a965  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14001a969  call    cs:__imp_ExAllocatePool2
0x14001a970  nop     dword ptr [rax+rax+00h]
0x14001a975  mov     rdi, rax
0x14001a978  test    rax, rax
0x14001a97b  jnz     short loc_14001A9D1
0x14001a97d  xor     ecx, ecx
0x14001a97f  mov     ebx, 0C000009Ah
0x14001a984  call    cs:__imp_RxFreeMdl
0x14001a98b  nop     dword ptr [rax+rax+00h]
0x14001a990  mov     rcx, r15
0x14001a993  call    cs:__imp_RxFreeMdl
0x14001a99a  nop     dword ptr [rax+rax+00h]
0x14001a99f  test    rdi, rdi
0x14001a9a2  jz      loc_14001AFED
0x14001a9a8  lea     rax, [rsi+420h]
0x14001a9af  cmp     rdi, rax
0x14001a9b2  jz      loc_14001AFE6
0x14001a9b8  mov     edx, 6D536352h; Tag
0x14001a9bd  mov     rcx, rdi; P
0x14001a9c0  call    cs:__imp_ExFreePoolWithTag
0x14001a9c7  nop     dword ptr [rax+rax+00h]
0x14001a9cc  jmp     loc_14001AFED
0x14001a9d1  lea     r14, [rax+578h]
0x14001a9d8  mov     r8d, r13d; Size
0x14001a9db  xor     edx, edx; Val
0x14001a9dd  mov     rcx, r14; void *
0x14001a9e0  call    memset
0x14001a9e5  test    r14, r14
0x14001a9e8  jz      short loc_14001A97D
0x14001a9ea  mov     r11d, [rsp+88h+arg_20]
0x14001a9f2  mov     r10d, [rsp+88h+Length]
0x14001a9fa  mov     eax, r11d
0x14001a9fd  mov     r9d, [rsp+88h+arg_40]
0x14001aa05  mov     ecx, r9d
0x14001aa08  shr     eax, 10h
0x14001aa0b  and     ecx, 4
0x14001aa0e  mov     [rdi+568h], eax
0x14001aa14  lea     eax, [r10-1]
0x14001aa18  mov     [rsp+88h+arg_40], ecx
0x14001aa1f  shr     eax, 10h
0x14001aa22  inc     eax
0x14001aa24  mov     [rdi+570h], r11d
0x14001aa2b  mov     [rdi+574h], r10d
0x14001aa32  mov     [rdi+56Ch], eax
0x14001aa38  test    ecx, ecx
0x14001aa3a  jnz     loc_14001AC05
0x14001aa40  mov     rdx, [rsi+48h]
0x14001aa44  xorps   xmm0, xmm0
0x14001aa47  mov     r8, [rsi+50h]
0x14001aa4b  mov     rcx, [rsi+58h]
0x14001aa4f  movups  xmmword ptr [r14], xmm0
0x14001aa53  movups  xmmword ptr [r14+10h], xmm0
0x14001aa58  movups  xmmword ptr [r14+20h], xmm0
0x14001aa5d  movups  xmmword ptr [r14+30h], xmm0
0x14001aa62  mov     dword ptr [r14], 424D53FEh
0x14001aa69  mov     dword ptr [r14+20h], 0FEFFh
0x14001aa71  mov     word ptr [r14+4], 40h ; '@'
0x14001aa78  cmp     [rdx+2E0h], r15b
0x14001aa7f  jge     short loc_14001AA92
0x14001aa81  movzx   eax, byte ptr [rsi+21h]
0x14001aa85  shl     eax, 4
0x14001aa88  add     eax, 10h
0x14001aa8b  and     eax, 70h
0x14001aa8e  mov     [r14+10h], eax
0x14001aa92  mov     word ptr [r14+0Eh], 1
0x14001aa99  test    r8, r8
0x14001aa9c  jz      short loc_14001AAC1
0x14001aa9e  mov     rax, [r8+1B8h]
0x14001aaa5  mov     [r14+28h], rax
0x14001aaa9  test    dword ptr [rdx+2CCh], 3000h
0x14001aab3  jz      short loc_14001AAC1
0x14001aab5  movzx   eax, word ptr [rdx+2BCh]
0x14001aabc  mov     [r14+8], ax
0x14001aac1  test    rcx, rcx
0x14001aac4  jz      short loc_14001AAF3
0x14001aac6  mov     eax, [rcx+1B4h]
0x14001aacc  mov     [r14+24h], eax
0x14001aad0  mov     rax, [rcx+1A8h]
0x14001aad7  mov     ecx, [rax+0B0h]
0x14001aadd  test    cl, 2
0x14001aae0  jz      short loc_14001AAF3
0x14001aae2  mov     eax, [rsi+44h]
0x14001aae5  bt      eax, 0Fh
0x14001aae9  jnb     short loc_14001AAF3
0x14001aaeb  or      dword ptr [r14+10h], 10000000h
0x14001aaf3  test    dword ptr [rdx+2CCh], 3000h
0x14001aafd  jz      short loc_14001AB10
0x14001aaff  mov     eax, [rsi+44h]
0x14001ab02  bt      eax, 0Eh
0x14001ab06  jnb     short loc_14001AB10
0x14001ab08  or      dword ptr [r14+10h], 20000000h
0x14001ab10  mov     rax, [rsp+88h+arg_10]
0x14001ab18  mov     word ptr [r14+0Ch], 8
0x14001ab1f  mov     word ptr [r14+40h], 31h ; '1'
0x14001ab26  mov     [r14+43h], r15b
0x14001ab2a  mov     [r14+64h], r15
0x14001ab2e  mov     [r14+6Ch], r15d
0x14001ab32  movups  xmm0, xmmword ptr [rax]
0x14001ab35  mov     [r14+44h], r10d
0x14001ab39  lea     rax, [r12+r11]
0x14001ab3d  mov     [r14+48h], rax
0x14001ab41  mov     [r14+60h], r15d
0x14001ab45  mov     byte ptr [r14+42h], 50h ; 'P'
0x14001ab4a  movups  xmmword ptr [r14+50h], xmm0
0x14001ab4f  mov     [r14+70h], r15b
0x14001ab53  test    r9b, 1
0x14001ab57  jz      short loc_14001AB5E
0x14001ab59  mov     byte ptr [r14+43h], 1
0x14001ab5e  mov     rcx, rsi
0x14001ab61  call    Smb2IsTrafficCompressionActive
0x14001ab66  test    eax, eax
0x14001ab68  jz      short loc_14001AB6F
0x14001ab6a  or      byte ptr [r14+43h], 2
0x14001ab6f  test    bx, bx
0x14001ab72  jz      short loc_14001AB8B
0x14001ab74  mov     eax, [rsp+88h+arg_30]
0x14001ab7b  mov     [r14+64h], eax
0x14001ab7f  mov     [r14+6Eh], bx
0x14001ab84  mov     word ptr [r14+6Ch], 70h ; 'p'
0x14001ab8b  xor     r9d, r9d
0x14001ab8e  mov     qword ptr [rsp+88h+BugCheckOnFailure], r15
0x14001ab93  xor     r8d, r8d
0x14001ab96  mov     edx, r13d
0x14001ab99  mov     rcx, r14
0x14001ab9c  call    cs:__imp_RxAllocateMdl2
0x14001aba3  nop     dword ptr [rax+rax+00h]
0x14001aba8  mov     r15, rax
0x14001abab  test    rax, rax
0x14001abae  jnz     short loc_14001ABD7
0x14001abb0  xor     ecx, ecx
0x14001abb2  mov     ebx, 0C000009Ah
0x14001abb7  call    cs:__imp_RxFreeMdl
0x14001abbe  nop     dword ptr [rax+rax+00h]
0x14001abc3  mov     rcx, r15
0x14001abc6  call    cs:__imp_RxFreeMdl
0x14001abcd  nop     dword ptr [rax+rax+00h]
0x14001abd2  jmp     loc_14001A9A8
0x14001abd7  mov     rcx, r15; MemoryDescriptorList
0x14001abda  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001abe1  nop     dword ptr [rax+rax+00h]
0x14001abe6  mov     r10d, [rsp+88h+Length]
0x14001abee  mov     r11d, [rsp+88h+arg_20]
0x14001abf6  test    bpl, bpl
0x14001abf9  jz      short loc_14001AC05
0x14001abfb  mov     eax, 1000h
0x14001ac00  or      [r15+0Ah], ax
0x14001ac05  xor     edx, edx
0x14001ac07  cmp     dx, bx
0x14001ac0a  jz      short loc_14001AC27
0x14001ac0c  lea     r12, [rsi+408h]
0x14001ac13  cmp     [r12], rdx
0x14001ac17  jnz     short loc_14001AC27
0x14001ac19  mov     eax, [rsi+44h]
0x14001ac1c  test    eax, 1000800h
0x14001ac21  jz      short loc_14001AC27
0x14001ac23  int     2Ch; Windows NT - assertion failure
0x14001ac25  jmp     short loc_14001AC33
0x14001ac27  lea     r12, [rsi+408h]
0x14001ac2e  test    bx, bx
0x14001ac31  jz      short loc_14001AC83
0x14001ac33  mov     rcx, [r12]
0x14001ac37  test    rcx, rcx
0x14001ac3a  jz      short loc_14001AC83
0x14001ac3c  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14001ac40  mov     eax, r11d
0x14001ac43  mov     qword ptr [rsp+88h+BugCheckOnFailure], rdx
0x14001ac48  add     rcx, rax
0x14001ac4b  xor     r9d, r9d
0x14001ac4e  xor     r8d, r8d
0x14001ac51  mov     edx, r10d
0x14001ac54  call    cs:__imp_RxAllocateMdl2
0x14001ac5b  nop     dword ptr [rax+rax+00h]
0x14001ac60  mov     rbp, rax
0x14001ac63  mov     rcx, rax; MemoryDescriptorList
0x14001ac66  test    rax, rax
0x14001ac69  jz      loc_14001ABB2
0x14001ac6f  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001ac76  nop     dword ptr [rax+rax+00h]
0x14001ac7b  mov     r13, rbp
0x14001ac7e  jmp     loc_14001AD85
0x14001ac83  mov     rcx, [rsi+400h]
0x14001ac8a  test    rcx, rcx
0x14001ac8d  jz      short loc_14001ACD3
0x14001ac8f  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14001ac93  mov     eax, r11d
0x14001ac96  mov     qword ptr [rsp+88h+BugCheckOnFailure], rdx
0x14001ac9b  add     rcx, rax
0x14001ac9e  xor     r9d, r9d
0x14001aca1  xor     r8d, r8d
0x14001aca4  mov     edx, r10d
0x14001aca7  call    cs:__imp_RxAllocateMdl2
0x14001acae  nop     dword ptr [rax+rax+00h]
0x14001acb3  mov     rbp, rax
0x14001acb6  mov     rcx, rax; MemoryDescriptorList
0x14001acb9  test    rax, rax
0x14001acbc  jz      loc_14001ABB2
0x14001acc2  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001acc9  nop     dword ptr [rax+rax+00h]
0x14001acce  jmp     loc_14001AD79
0x14001acd3  mov     rax, [rsi+9A0h]
0x14001acda  test    rax, rax
0x14001acdd  jz      short loc_14001ACEB
0x14001acdf  mov     rbx, [rsi+998h]
0x14001ace6  mov     ecx, [rax+8]
0x14001ace9  jmp     short loc_14001ACF8
0x14001aceb  mov     rax, [rsi+30h]
0x14001acef  mov     ecx, edx
0x14001acf1  mov     rbx, [rax+220h]
0x14001acf8  mov     eax, ecx
0x14001acfa  xor     r9d, r9d
0x14001acfd  mov     ecx, [rbx+2Ch]
0x14001ad00  xor     r8d, r8d
0x14001ad03  mov     r13d, r11d
0x14001ad06  add     rax, r13
0x14001ad09  mov     qword ptr [rsp+88h+BugCheckOnFailure], rdx
0x14001ad0e  add     rcx, rax
0x14001ad11  mov     edx, r10d
0x14001ad14  add     rcx, [rbx+20h]
0x14001ad18  call    cs:__imp_RxAllocateMdl2
0x14001ad1f  nop     dword ptr [rax+rax+00h]
0x14001ad24  mov     rbp, rax
0x14001ad27  test    rax, rax
0x14001ad2a  jnz     short loc_14001AD34
0x14001ad2c  mov     rcx, rax
0x14001ad2f  jmp     loc_14001ABB2
0x14001ad34  mov     rax, [rsi+9A0h]
0x14001ad3b  test    rax, rax
0x14001ad3e  jz      short loc_14001AD45
0x14001ad40  mov     ecx, [rax+8]
0x14001ad43  jmp     short loc_14001AD47
0x14001ad45  xor     ecx, ecx
0x14001ad47  mov     r8d, [rbx+2Ch]
0x14001ad4b  mov     rdx, rbp; TargetMdl
0x14001ad4e  mov     r9d, [rsp+88h+Length]; Length
0x14001ad56  mov     eax, ecx
0x14001ad58  mov     rcx, rbx; SourceMdl
0x14001ad5b  add     rax, r13
0x14001ad5e  add     r8, rax
0x14001ad61  add     r8, [rbx+20h]; VirtualAddress
0x14001ad65  call    cs:__imp_IoBuildPartialMdl
0x14001ad6c  nop     dword ptr [rax+rax+00h]
0x14001ad71  movzx   ebx, [rsp+88h+arg_38]
0x14001ad79  mov     r13, rbp
0x14001ad7c  test    bx, bx
0x14001ad7f  jz      loc_14001AE6A
0x14001ad85  cmp     [rsp+88h+arg_40], 0
0x14001ad8d  jz      short loc_14001AD91
0x14001ad8f  int     2Ch; Windows NT - assertion failure
0x14001ad91  mov     eax, [rsp+88h+Length]
0x14001ad98  mov     r8, r15
0x14001ad9b  mov     r9d, [rsp+88h+arg_8]
0x14001ada3  mov     rdx, rsi
0x14001ada6  mov     [rsp+88h+var_40], 2004h
0x14001adae  mov     rcx, rdi
0x14001adb1  mov     [rsp+88h+var_48], bx
0x14001adb6  mov     [rsp+88h+var_50], eax
0x14001adba  xor     eax, eax
0x14001adbc  mov     [rsp+88h+var_58], rbp
0x14001adc1  mov     [rsp+88h+Priority], eax
0x14001adc5  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax
0x14001adca  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x14001add1  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
