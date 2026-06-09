# Smb2QueryInfo_Start

- ea: `0x140017cb0`
- end: `0x140018029`
- name: `Smb2QueryInfo_Start`
- size: `889`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140017cb0`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017f55`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017f55`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140017e32`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140017e32`
- `rdbss!RxFreeMdl` at `0x140017ff8`
- `rdbss!RxFreeMdl` at `0x140018007`
- `rdbss!RxFreeMdl` at `0x140018016`
- `rdbss!RxFreeMdl` at `0x140017ff8`
- `rdbss!RxFreeMdl` at `0x140018007`
- `rdbss!RxFreeMdl` at `0x140018016`
- `rdbss!RxAllocateMdl2` at `0x140017e17`
- `rdbss!RxAllocateMdl2` at `0x140017f18`
- `rdbss!RxAllocateMdl2` at `0x140017f9d`
- `rdbss!RxAllocateMdl2` at `0x140017e17`
- `rdbss!RxAllocateMdl2` at `0x140017f18`
- `rdbss!RxAllocateMdl2` at `0x140017f9d`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140017fe0`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140017fe0`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140017edc`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140017edc`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140017e8b`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140017e8b`

## pseudocode

```c
__int64 __fastcall Smb2QueryInfo_Start(__int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // r13
  __int64 v4; // rdi
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // rbp
  __int64 v8; // r12
  unsigned int v9; // r15d
  int v10; // eax
  __int128 v11; // xmm0
  struct _MDL *Mdl2; // rax
  _QWORD *p_Next; // r14
  __int64 v14; // rdx
  ULONG v15; // edi
  int v16; // edi
  PVOID v17; // rax
  __int64 result; // rax
  ULONG Priority; // [rsp+28h] [rbp-70h]
  int v20; // [rsp+38h] [rbp-60h]
  __int16 v21; // [rsp+40h] [rbp-58h]

  v2 = 0;
  v3 = 0;
  v4 = a1 + 2488;
  v5 = *(_QWORD *)(a1 + 72);
  v6 = *(_QWORD *)(a1 + 80);
  v7 = *(_QWORD *)(a1 + 88);
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 72LL) + 48LL);
  memset((void *)(a1 + 2488), 0, 0x40u);
  *(_DWORD *)v4 = 1112364030;
  *(_DWORD *)(v4 + 32) = 65279;
  *(_WORD *)(v4 + 4) = 64;
  if ( *(char *)(v5 + 736) < 0 )
    *(_DWORD *)(v4 + 16) = (16 * *(_BYTE *)(a1 + 33) + 16) & 0x70;
  *(_WORD *)(v4 + 14) = 1;
  if ( v6 )
  {
    *(_QWORD *)(v4 + 40) = *(_QWORD *)(v6 + 440);
    if ( (*(_DWORD *)(v5 + 716) & 0x3000) != 0 )
      *(_WORD *)(v4 + 8) = *(_WORD *)(v5 + 700);
  }
  if ( v7 )
  {
    *(_DWORD *)(v4 + 36) = *(_DWORD *)(v7 + 436);
    if ( (*(_DWORD *)(*(_QWORD *)(v7 + 424) + 176LL) & 2) != 0 && (*(_DWORD *)(a1 + 68) & 0x8000) != 0 )
      *(_DWORD *)(v4 + 16) |= 0x10000000u;
  }
  if ( (*(_DWORD *)(v5 + 716) & 0x3000) != 0 && (*(_DWORD *)(a1 + 68) & 0x4000) != 0 )
    *(_DWORD *)(v4 + 16) |= 0x20000000u;
  v9 = 104;
  *(_BYTE *)(a1 + 2554) = *(_BYTE *)(a1 + 2420);
  *(_BYTE *)(a1 + 2555) = *(_BYTE *)(a1 + 2424);
  *(_DWORD *)(a1 + 2568) = *(_DWORD *)(a1 + 2432);
  *(_DWORD *)(a1 + 2572) = *(_DWORD *)(a1 + 2428);
  v10 = *(_DWORD *)(a1 + 2416);
  *(_WORD *)(a1 + 2500) = 16;
  *(_WORD *)(a1 + 2552) = 41;
  v11 = *(_OWORD *)(v8 + 28);
  *(_DWORD *)(a1 + 2556) = v10;
  *(_WORD *)(a1 + 2560) = 104;
  *(_OWORD *)(a1 + 2576) = v11;
  *(_DWORD *)(a1 + 2564) = 0;
  Mdl2 = (struct _MDL *)RxAllocateMdl2(v4, 104, 0, 0, 0);
  p_Next = &Mdl2->Next;
  if ( !Mdl2 )
    goto LABEL_22;
  MmBuildMdlForNonPagedPool(Mdl2);
  v14 = *(unsigned int *)(a1 + 2448);
  if ( (_DWORD)v14 )
  {
    v3 = RxAllocateMdl2(*(_QWORD *)(a1 + 2440), v14, 0, 0, 0);
    if ( !v3 )
    {
LABEL_22:
      v16 = -1073741670;
      goto LABEL_30;
    }
    *(_DWORD *)(a1 + 2564) = *(_DWORD *)(a1 + 2448);
    *p_Next = v3;
    v9 = *(_DWORD *)(a1 + 2448) + 104;
  }
  v15 = *(_DWORD *)(a1 + 2416);
  if ( v15 )
  {
    v2 = RxAllocateMdl2(*(_QWORD *)(a1 + 2408), v15, 0, 0, 0);
    if ( !v2 )
      goto LABEL_22;
  }
  v21 = 0;
  v20 = 0;
  Priority = v15;
  v16 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 1024, a1, p_Next, v9, v2, Priority, 0, v20, v21, 4);
  if ( v16 < 0 )
  {
LABEL_30:
    RxFreeMdl(p_Next);
    RxFreeMdl(v2);
    RxFreeMdl(v3);
    return (unsigned int)v16;
  }
  *(_DWORD *)(a1 + 1888) = *(_DWORD *)(a1 + 2424) | (*(_DWORD *)(a1 + 2420) << 16);
  if ( v2 )
  {
    v17 = (*(_BYTE *)(v2 + 10) & 5) != 0
        ? *(PVOID *)(v2 + 24)
        : MmMapLockedPagesSpecifyCache((PMDL)v2, 0, MmCached, 0, 0, 0x40000000u);
    *(_QWORD *)(a1 + 1736) = v17;
    if ( !v17 )
    {
      v16 = -1073741670;
      SmbCseFinalizeBufferContext(a1 + 1024);
      goto LABEL_29;
    }
  }
  result = SmbCseSubmitBufferContext(a1 + 1024);
  v16 = result;
  if ( (int)result < 0 )
  {
LABEL_29:
    v2 = 0;
    p_Next = 0;
    v3 = 0;
    goto LABEL_30;
  }
  return result;
}

```

## disassembly

```asm
0x140017cb0  push    rbx
0x140017cb2  push    rbp
0x140017cb3  push    rsi
0x140017cb4  push    rdi
0x140017cb5  push    r12
0x140017cb7  push    r13
0x140017cb9  push    r14
0x140017cbb  push    r15
0x140017cbd  sub     rsp, 58h
0x140017cc1  mov     rax, [rcx+30h]
0x140017cc5  mov     rbx, rcx
0x140017cc8  xor     edx, edx; Val
0x140017cca  mov     r8d, 40h ; '@'; Size
0x140017cd0  xor     esi, esi
0x140017cd2  xor     r13d, r13d
0x140017cd5  mov     rcx, [rax+48h]
0x140017cd9  lea     rdi, [rbx+9B8h]
0x140017ce0  mov     r14, [rbx+48h]
0x140017ce4  mov     r15, [rbx+50h]
0x140017ce8  mov     rbp, [rbx+58h]
0x140017cec  mov     r12, [rcx+30h]
0x140017cf0  mov     rcx, rdi; void *
0x140017cf3  call    memset
0x140017cf8  mov     dword ptr [rdi], 424D53FEh
0x140017cfe  mov     dword ptr [rdi+20h], 0FEFFh
0x140017d05  mov     word ptr [rdi+4], 40h ; '@'
0x140017d0b  cmp     [r14+2E0h], sil
0x140017d12  jge     short loc_140017D24
0x140017d14  movzx   eax, byte ptr [rbx+21h]
0x140017d18  shl     eax, 4
0x140017d1b  add     eax, 10h
0x140017d1e  and     eax, 70h
0x140017d21  mov     [rdi+10h], eax
0x140017d24  mov     word ptr [rdi+0Eh], 1
0x140017d2a  test    r15, r15
0x140017d2d  jz      short loc_140017D53
0x140017d2f  mov     rax, [r15+1B8h]
0x140017d36  mov     [rdi+28h], rax
0x140017d3a  test    dword ptr [r14+2CCh], 3000h
0x140017d45  jz      short loc_140017D53
0x140017d47  movzx   eax, word ptr [r14+2BCh]
0x140017d4f  mov     [rdi+8], ax
0x140017d53  test    rbp, rbp
0x140017d56  jz      short loc_140017D77
0x140017d58  mov     eax, [rbp+1B4h]
0x140017d5e  mov     [rdi+24h], eax
0x140017d61  mov     rax, [rbp+1A8h]
0x140017d68  mov     ecx, [rax+0B0h]
0x140017d6e  test    cl, 2
0x140017d71  jnz     loc_140017F66
0x140017d77  test    dword ptr [r14+2CCh], 3000h
0x140017d82  jz      short loc_140017D91
0x140017d84  mov     eax, [rbx+44h]
0x140017d87  bt      eax, 0Eh
0x140017d8b  jb      loc_140017F7F
0x140017d91  movzx   eax, byte ptr [rbx+974h]
0x140017d98  mov     r15d, 68h ; 'h'
0x140017d9e  mov     [rbx+9FAh], al
0x140017da4  xor     r9d, r9d
0x140017da7  movzx   eax, byte ptr [rbx+978h]
0x140017dae  xor     r8d, r8d
0x140017db1  mov     [rbx+9FBh], al
0x140017db7  mov     edx, r15d
0x140017dba  mov     eax, [rbx+980h]
0x140017dc0  mov     rcx, rdi
0x140017dc3  mov     [rbx+0A08h], eax
0x140017dc9  mov     eax, [rbx+97Ch]
0x140017dcf  mov     [rbx+0A0Ch], eax
0x140017dd5  mov     eax, [rbx+970h]
0x140017ddb  mov     word ptr [rbx+9C4h], 10h
0x140017de4  mov     word ptr [rbx+9F8h], 29h ; ')'
0x140017ded  movups  xmm0, xmmword ptr [r12+1Ch]
0x140017df3  xor     r12d, r12d
0x140017df6  mov     [rbx+9FCh], eax
0x140017dfc  mov     [rbx+0A00h], r15w
0x140017e04  movups  xmmword ptr [rbx+0A10h], xmm0
0x140017e0b  mov     [rbx+0A04h], r12d
0x140017e12  mov     qword ptr [rsp+98h+BugCheckOnFailure], r12
0x140017e17  call    cs:__imp_RxAllocateMdl2
0x140017e1e  nop     dword ptr [rax+rax+00h]
0x140017e23  mov     r14, rax
0x140017e26  test    rax, rax
0x140017e29  jz      loc_140017F30
0x140017e2f  mov     rcx, rax; MemoryDescriptorList
0x140017e32  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140017e39  nop     dword ptr [rax+rax+00h]
0x140017e3e  mov     edx, [rbx+990h]
0x140017e44  test    edx, edx
0x140017e46  jnz     loc_140017F8B
0x140017e4c  mov     edi, [rbx+970h]
0x140017e52  test    edi, edi
0x140017e54  jnz     loc_140017F04
0x140017e5a  mov     [rsp+98h+var_50], 4
0x140017e62  lea     rcx, [rbx+400h]
0x140017e69  mov     [rsp+98h+var_58], r12w
0x140017e6f  mov     r9d, r15d
0x140017e72  mov     [rsp+98h+var_60], r12d
0x140017e77  mov     r8, r14
0x140017e7a  mov     [rsp+98h+var_68], r12
0x140017e7f  mov     rdx, rbx
0x140017e82  mov     [rsp+98h+Priority], edi
0x140017e86  mov     qword ptr [rsp+98h+BugCheckOnFailure], rsi
0x140017e8b  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x140017e92  nop     dword ptr [rax+rax+00h]
0x140017e97  mov     edi, eax
0x140017e99  test    eax, eax
0x140017e9b  js      loc_140017FF5
0x140017ea1  mov     eax, [rbx+974h]
0x140017ea7  shl     eax, 10h
0x140017eaa  or      eax, [rbx+978h]
0x140017eb0  mov     [rbx+760h], eax
0x140017eb6  test    rsi, rsi
0x140017eb9  jz      short loc_140017ED5
0x140017ebb  test    byte ptr [rsi+0Ah], 5
0x140017ebf  jz      short loc_140017F3A
0x140017ec1  mov     rax, [rsi+18h]
0x140017ec5  mov     [rbx+6C8h], rax
0x140017ecc  test    rax, rax
0x140017ecf  jz      loc_140017FD4
0x140017ed5  lea     rcx, [rbx+400h]
0x140017edc  call    cs:__imp_SmbCseSubmitBufferContext
0x140017ee3  nop     dword ptr [rax+rax+00h]
0x140017ee8  mov     edi, eax
0x140017eea  test    eax, eax
0x140017eec  js      loc_140017FEC
0x140017ef2  add     rsp, 58h
0x140017ef6  pop     r15
0x140017ef8  pop     r14
0x140017efa  pop     r13
0x140017efc  pop     r12
0x140017efe  pop     rdi
0x140017eff  pop     rsi
0x140017f00  pop     rbp
0x140017f01  pop     rbx
0x140017f02  retn
0x140017f04  mov     rcx, [rbx+968h]
0x140017f0b  xor     r9d, r9d
0x140017f0e  xor     r8d, r8d
0x140017f11  mov     qword ptr [rsp+98h+BugCheckOnFailure], r12
0x140017f16  mov     edx, edi
0x140017f18  call    cs:__imp_RxAllocateMdl2
0x140017f1f  nop     dword ptr [rax+rax+00h]
0x140017f24  mov     rsi, rax
0x140017f27  test    rax, rax
0x140017f2a  jnz     loc_140017E5A
0x140017f30  mov     edi, 0C000009Ah
0x140017f35  jmp     loc_140017FF5
0x140017f3a  mov     [rsp+98h+Priority], 40000000h; Priority
0x140017f42  xor     r9d, r9d; RequestedAddress
0x140017f45  xor     edx, edx; AccessMode
0x140017f47  mov     [rsp+98h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140017f4c  mov     r8d, 1; CacheType
0x140017f52  mov     rcx, rsi; MemoryDescriptorList
0x140017f55  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140017f5c  nop     dword ptr [rax+rax+00h]
0x140017f61  jmp     loc_140017EC5
0x140017f66  mov     eax, [rbx+44h]
0x140017f69  bt      eax, 0Fh
0x140017f6d  jnb     loc_140017D77
0x140017f73  or      dword ptr [rdi+10h], 10000000h
0x140017f7a  jmp     loc_140017D77
0x140017f7f  or      dword ptr [rdi+10h], 20000000h
0x140017f86  jmp     loc_140017D91
0x140017f8b  mov     rcx, [rbx+988h]
0x140017f92  xor     r9d, r9d
0x140017f95  xor     r8d, r8d
0x140017f98  mov     qword ptr [rsp+98h+BugCheckOnFailure], r12
0x140017f9d  call    cs:__imp_RxAllocateMdl2
0x140017fa4  nop     dword ptr [rax+rax+00h]
0x140017fa9  mov     r13, rax
0x140017fac  test    rax, rax
0x140017faf  jz      loc_140017F30
0x140017fb5  mov     eax, [rbx+990h]
0x140017fbb  mov     [rbx+0A04h], eax
0x140017fc1  mov     [r14], r13
0x140017fc4  mov     r15d, [rbx+990h]
0x140017fcb  add     r15d, 68h ; 'h'
0x140017fcf  jmp     loc_140017E4C
0x140017fd4  lea     rcx, [rbx+400h]
0x140017fdb  mov     edi, 0C000009Ah
0x140017fe0  call    cs:__imp_SmbCseFinalizeBufferContext
0x140017fe7  nop     dword ptr [rax+rax+00h]
0x140017fec  mov     rsi, r12
0x140017fef  mov     r14, r12
0x140017ff2  mov     r13, r12
0x140017ff5  mov     rcx, r14
0x140017ff8  call    cs:__imp_RxFreeMdl
0x140017fff  nop     dword ptr [rax+rax+00h]
0x140018004  mov     rcx, rsi
0x140018007  call    cs:__imp_RxFreeMdl
0x14001800e  nop     dword ptr [rax+rax+00h]
0x140018013  mov     rcx, r13
0x140018016  call    cs:__imp_RxFreeMdl
0x14001801d  nop     dword ptr [rax+rax+00h]
0x140018022  mov     eax, edi
0x140018024  jmp     loc_140017EF2
```
