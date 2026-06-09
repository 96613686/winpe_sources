# CClfsLogFcbPhysical::GetPhysicalToVirtualLsnMappings(_CLS_LSN const &,_CLFS_LSN_MAP * *)

- ea: `0x140046880`
- end: `0x140046afa`
- name: `?GetPhysicalToVirtualLsnMappings@CClfsLogFcbPhysical@@UEAAJAEBT_CLS_LSN@@PEAPEAU_CLFS_LSN_MAP@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this, const union _CLS_LSN *, struct _CLFS_LSN_MAP **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x140005840`
- `0x140008394`
- `0x14000ee30`
- `0x140017f20`
- `0x140017f80`
- `0x140046880`
- `0x1400646d0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400468fc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400468fc`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004692d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004692d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046aad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fcc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046aad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fcc0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046a0a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046a0a`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::GetPhysicalToVirtualLsnMappings(
        CClfsLogFcbPhysical *this,
        const union _CLS_LSN *a2,
        struct _CLFS_LSN_MAP **a3)
{
  struct _CLFS_LSN_MAP **v3; // r13
  char v5; // r12
  union _CLS_LSN *v6; // rdi
  unsigned int *v7; // rsi
  char *v8; // r15
  int v9; // ebx
  unsigned __int64 v10; // rax
  __int128 *v11; // r13
  unsigned __int8 v12; // bl
  union _CLS_LSN *PoolWithTag; // rax
  unsigned __int8 i; // r8
  char v16; // [rsp+30h] [rbp-98h]
  BOOLEAN v17; // [rsp+31h] [rbp-97h]
  char *v19; // [rsp+48h] [rbp-80h]
  union _CLS_LSN v20; // [rsp+68h] [rbp-60h] BYREF
  struct _CLFS_LSN_MAP **v21; // [rsp+70h] [rbp-58h]
  __int128 v22; // [rsp+78h] [rbp-50h] BYREF

  v3 = a3;
  v21 = a3;
  v16 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v20 = CLFS_LSN_INVALID;
  v22 = 0;
  v8 = (char *)this - 640;
  v19 = (char *)this - 640;
  v17 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this - 440), 1u);
  if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v8 + 312LL))(v8) )
  {
    v7 = (unsigned int *)ExAllocateFromPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage);
    if ( !v7 )
    {
      v9 = -1073741670;
      goto LABEL_17;
    }
    v5 = 1;
    if ( (unsigned __int8)operator>=(a2) )
    {
      memmove(v7, *((const void **)v8 + 88), 0x1000u);
    }
    else
    {
      v9 = CClfsLogFcbPhysical::ReadOwnerPage((CClfsLogFcbPhysical *)v8, a2, 0, 1u, (unsigned __int8 *)v7, &v20);
      if ( v9 < 0 )
        goto LABEL_17;
    }
    v10 = v7[12];
    v11 = (__int128 *)((char *)v7 + v10);
    v12 = -24 - (v10 >> 4);
  }
  else
  {
    v12 = 1;
    v11 = &v22;
    *((union _CLS_LSN *)&v22 + 1) = *a2;
  }
  PoolWithTag = (union _CLS_LSN *)ExAllocatePoolWithTag(PagedPool, v12 + 8 * (unsigned int)v12 + 32, 0x73666C43u);
  v6 = PoolWithTag;
  if ( PoolWithTag )
  {
    v16 = 1;
    PoolWithTag[1].offset.idxRecord = v12;
    *PoolWithTag = *a2;
    PoolWithTag[2].ullOffset = (ULONGLONG)&PoolWithTag[4];
    PoolWithTag[3].ullOffset = (ULONGLONG)&PoolWithTag[(unsigned int)v12 + 4];
    for ( i = 0; i < v12; ++i )
    {
      *(_QWORD *)(PoolWithTag[2].ullOffset + 8LL * i) = *((_QWORD *)&v11[i] + 1);
      *(_BYTE *)(i + PoolWithTag[3].ullOffset) = i;
    }
    v3 = a3;
    *a3 = (struct _CLFS_LSN_MAP *)PoolWithTag;
    v9 = 0;
  }
  else
  {
    v9 = -1073741670;
    v3 = a3;
  }
  v8 = v19;
LABEL_17:
  if ( v9 < 0 )
  {
    if ( v16 )
      ExFreePoolWithTag(v6, 0);
    *v3 = 0;
  }
  if ( v5 )
    CClfsLogFcbPhysical::FreeOwnerPage((struct CClfsLogFcbPhysical *)v8, (unsigned __int8 *)v7);
  if ( v17 )
    ClfsReleaseResourceLite((struct _ERESOURCE *)(v8 + 200));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140046880  push    rbx
0x140046882  push    rsi
0x140046883  push    rdi
0x140046884  push    r12
0x140046886  push    r13
0x140046888  push    r14
0x14004688a  push    r15
0x14004688c  sub     rsp, 90h
0x140046893  mov     r13, r8
0x140046896  mov     [rsp+0C8h+var_88], r8
0x14004689b  mov     r14, rdx
0x14004689e  mov     rbx, rcx
0x1400468a1  mov     [rsp+0C8h+var_68], rcx
0x1400468a6  mov     [rsp+0C8h+var_58], r8
0x1400468ab  mov     [rsp+0C8h+var_97], 0
0x1400468b0  mov     [rsp+0C8h+var_98], 0
0x1400468b5  xor     r12b, r12b
0x1400468b8  mov     [rsp+0C8h+var_96], r12b
0x1400468bd  xor     edi, edi
0x1400468bf  mov     [rsp+0C8h+var_78], rdi
0x1400468c4  xor     esi, esi
0x1400468c6  mov     [rsp+0C8h+var_70], rsi
0x1400468cb  mov     [rsp+0C8h+var_94], 0C0000001h
0x1400468d3  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400468da  mov     qword ptr [rsp+0C8h+var_60], rax
0x1400468df  xorps   xmm0, xmm0
0x1400468e2  movups  [rsp+0C8h+var_50], xmm0
0x1400468e7  lea     r15, [rcx-280h]
0x1400468ee  mov     [rsp+0C8h+var_80], r15
0x1400468f3  lea     rcx, [r15+0C8h]; Resource
0x1400468fa  mov     dl, 1; Wait
0x1400468fc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140046903  nop     dword ptr [rax+rax+00h]
0x140046908  mov     [rsp+0C8h+var_97], al
0x14004690c  mov     rcx, [r15]
0x14004690f  mov     rax, [rcx+138h]
0x140046916  mov     rcx, r15
0x140046919  call    _guard_dispatch_icall
0x14004691e  test    al, al
0x140046920  jz      loc_1400469DB
0x140046926  lea     rcx, ?m_laOwnerPage@CClfsLogFcbPhysical@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004692d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140046934  nop     dword ptr [rax+rax+00h]
0x140046939  mov     rsi, rax
0x14004693c  mov     [rsp+0C8h+var_70], rax
0x140046941  test    rax, rax
0x140046944  jnz     short loc_140046950
0x140046946  mov     ebx, 0C000009Ah
0x14004694b  jmp     loc_140046A99
0x140046950  mov     r12b, 1
0x140046953  mov     [rsp+0C8h+var_96], r12b
0x140046958  lea     rdx, [rbx+2E8h]
0x14004695f  mov     rcx, r14
0x140046962  call    ??P@YAEAEBT_CLS_LSN@@0@Z; operator>=(_CLS_LSN const &,_CLS_LSN const &)
0x140046967  test    al, al
0x140046969  jz      short loc_1400469AC
0x14004696b  mov     r8d, 1000h; Size
0x140046971  mov     rdx, [r15+2C0h]; Src
0x140046978  mov     rcx, rsi; void *
0x14004697b  call    memmove
0x140046980  mov     eax, [rsi+30h]
0x140046983  lea     r13, [rax+rsi]
0x140046987  mov     [rsp+0C8h+var_90], 0
0x14004698f  mov     [rsp+0C8h+var_90], 8
0x140046997  mov     [rsp+0C8h+var_90], 9
0x14004699f  shr     rax, 4
0x1400469a3  mov     ebx, 0E8h
0x1400469a8  sub     bl, al
0x1400469aa  jmp     short loc_1400469ED
0x1400469ac  lea     rax, [rsp+0C8h+var_60]
0x1400469b1  mov     [rsp+0C8h+var_A0], rax; union _CLS_LSN *
0x1400469b6  mov     [rsp+0C8h+var_A8], rsi; unsigned __int8 *
0x1400469bb  mov     r9b, r12b; unsigned __int8
0x1400469be  xor     r8d, r8d; unsigned int
0x1400469c1  mov     rdx, r14; union _CLS_LSN *
0x1400469c4  mov     rcx, r15; this
0x1400469c7  call    ?ReadOwnerPage@CClfsLogFcbPhysical@@AEAAJAEBT_CLS_LSN@@KEPEAEAEAT2@@Z; CClfsLogFcbPhysical::ReadOwnerPage(_CLS_LSN const &,ulong,uchar,uchar *,_CLS_LSN &)
0x1400469cc  mov     ebx, eax
0x1400469ce  test    eax, eax
0x1400469d0  jns     short loc_140046980
0x1400469d2  mov     [rsp+0C8h+var_94], eax
0x1400469d6  jmp     loc_140046A9D
0x1400469db  mov     bl, 1
0x1400469dd  lea     r13, [rsp+0C8h+var_50]
0x1400469e2  mov     rax, [r14]
0x1400469e5  mov     qword ptr [rsp+0C8h+var_50+8], rax
0x1400469ed  movzx   r15d, bl
0x1400469f1  lea     edx, ds:0[r15*8]
0x1400469f9  add     edx, 20h ; ' '
0x1400469fc  add     edx, r15d; NumberOfBytes
0x1400469ff  mov     ecx, 1; PoolType
0x140046a04  mov     r8d, 73666C43h; Tag
0x140046a0a  call    cs:__imp_ExAllocatePoolWithTag
0x140046a11  nop     dword ptr [rax+rax+00h]
0x140046a16  mov     rdi, rax
0x140046a19  mov     [rsp+0C8h+var_78], rax
0x140046a1e  test    rax, rax
0x140046a21  jnz     short loc_140046A2F
0x140046a23  mov     ebx, 0C000009Ah
0x140046a28  mov     r13, [rsp+0C8h+var_88]
0x140046a2d  jmp     short loc_140046A94
0x140046a2f  mov     [rsp+0C8h+var_98], 1
0x140046a34  mov     [rax+8], r15d
0x140046a38  mov     rax, [r14]
0x140046a3b  mov     [rdi], rax
0x140046a3e  lea     rax, [rdi+20h]
0x140046a42  mov     [rdi+10h], rax
0x140046a46  lea     eax, ds:0[r15*8]
0x140046a4e  lea     rcx, [rax+20h]
0x140046a52  add     rcx, rdi
0x140046a55  mov     [rdi+18h], rcx
0x140046a59  xor     r8b, r8b
0x140046a5c  mov     [rsp+0C8h+var_95], r8b
0x140046a61  cmp     r8b, bl
0x140046a64  jnb     short loc_140046A89
0x140046a66  movzx   edx, r8b
0x140046a6a  mov     eax, edx
0x140046a6c  add     rax, rax
0x140046a6f  mov     rcx, [rdi+10h]
0x140046a73  mov     rax, [r13+rax*8+8]
0x140046a78  mov     [rcx+rdx*8], rax
0x140046a7c  mov     rax, [rdi+18h]
0x140046a80  mov     [rdx+rax], r8b
0x140046a84  inc     r8b
0x140046a87  jmp     short loc_140046A5C
0x140046a89  mov     r13, [rsp+0C8h+var_88]
0x140046a8e  mov     [r13+0], rdi
0x140046a92  xor     ebx, ebx
0x140046a94  mov     r15, [rsp+0C8h+var_80]
0x140046a99  mov     [rsp+0C8h+var_94], ebx
0x140046a9d  test    ebx, ebx
0x140046a9f  jns     short loc_140046AC1
0x140046aa1  cmp     [rsp+0C8h+var_98], 0
0x140046aa6  jz      short loc_140046AB9
0x140046aa8  xor     edx, edx; Tag
0x140046aaa  mov     rcx, rdi; P
0x140046aad  call    cs:__imp_ExFreePoolWithTag
0x140046ab4  nop     dword ptr [rax+rax+00h]
0x140046ab9  mov     qword ptr [r13+0], 0
0x140046ac1  test    r12b, r12b
0x140046ac4  jz      short loc_140046AD1
0x140046ac6  mov     rdx, rsi; unsigned __int8 *
0x140046ac9  mov     rcx, r15; struct CClfsLogFcbPhysical *
0x140046acc  call    ?FreeOwnerPage@CClfsLogFcbPhysical@@CAXPEAV1@PEAE@Z; CClfsLogFcbPhysical::FreeOwnerPage(CClfsLogFcbPhysical *,uchar *)
0x140046ad1  cmp     [rsp+0C8h+var_97], 0
0x140046ad6  jz      short loc_140046AE4
0x140046ad8  lea     rcx, [r15+0C8h]
0x140046adf  call    ClfsReleaseResourceLite
0x140046ae4  mov     eax, ebx
0x140046ae6  add     rsp, 90h
0x140046aed  pop     r15
0x140046aef  pop     r14
0x140046af1  pop     r13
0x140046af3  pop     r12
0x140046af5  pop     rdi
0x140046af6  pop     rsi
0x140046af7  pop     rbx
0x140046af8  retn
0x14007fca5  push    rbp
0x14007fca7  sub     rsp, 30h
0x14007fcab  mov     rbp, rdx
0x14007fcae  cmp     dword ptr [rbp+34h], 0
0x14007fcb2  jge     short loc_14007FCDB
0x14007fcb4  cmp     byte ptr [rbp+30h], 0
0x14007fcb8  jz      short loc_14007FCD0
0x14007fcba  xor     edx, edx; Tag
0x14007fcbc  mov     rcx, [rbp+50h]; P
0x14007fcc0  call    cs:__imp_ExFreePoolWithTag
0x14007fcc7  nop     dword ptr [rax+rax+00h]
0x14007fccc  mov     byte ptr [rbp+30h], 0
0x14007fcd0  mov     rax, [rbp+70h]
0x14007fcd4  mov     qword ptr [rax], 0
0x14007fcdb  cmp     byte ptr [rbp+32h], 0
0x14007fcdf  jz      short loc_14007FCF9
0x14007fce1  mov     rcx, [rbp+60h]
0x14007fce5  add     rcx, 0FFFFFFFFFFFFFD80h; struct CClfsLogFcbPhysical *
0x14007fcec  mov     rdx, [rbp+58h]; unsigned __int8 *
0x14007fcf0  call    ?FreeOwnerPage@CClfsLogFcbPhysical@@CAXPEAV1@PEAE@Z; CClfsLogFcbPhysical::FreeOwnerPage(CClfsLogFcbPhysical *,uchar *)
0x14007fcf5  mov     byte ptr [rbp+32h], 0
0x14007fcf9  cmp     byte ptr [rbp+31h], 0
0x14007fcfd  jz      short loc_14007FD13
0x14007fcff  mov     rcx, [rbp+60h]
0x14007fd03  add     rcx, 0FFFFFFFFFFFFFE48h
0x14007fd0a  call    ClfsReleaseResourceLite
0x14007fd0f  mov     byte ptr [rbp+31h], 0
0x14007fd13  add     rsp, 30h
0x14007fd17  pop     rbp
0x14007fd18  retn
```
