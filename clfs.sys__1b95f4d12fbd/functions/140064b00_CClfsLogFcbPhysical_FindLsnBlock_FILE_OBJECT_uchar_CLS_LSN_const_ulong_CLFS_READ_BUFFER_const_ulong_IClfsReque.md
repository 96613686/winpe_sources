# CClfsLogFcbPhysical::FindLsnBlock(_FILE_OBJECT *,uchar,_CLS_LSN const &,ulong,_CLFS_READ_BUFFER const &,ulong,IClfsRequestAsync *,ulong,_CLS_LSN &,ulong &)

- ea: `0x140064b00`
- end: `0x140064da4`
- name: `?FindLsnBlock@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@EAEBT_CLS_LSN@@KAEBU_CLFS_READ_BUFFER@@KPEAUIClfsRequestAsync@@KAEAT3@AEAK@Z`
- size: `676`
- prototype: `int(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *, unsigned __int8, const union _CLS_LSN *, unsigned int, const struct _CLFS_READ_BUFFER *, unsigned int, struct IClfsRequestAsync *, unsigned int, union _CLS_LSN *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x140005840`
- `0x140008394`
- `0x140008c40`
- `0x14000a920`
- `0x14000ee30`
- `0x140017f20`
- `0x140017f80`
- `0x140064378`
- `0x140064b00`
- `0x140065860`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140064b66`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140064b66`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140064bd2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140064bd2`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::FindLsnBlock(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        unsigned __int8 a3,
        const union _CLS_LSN *a4,
        unsigned int a5,
        const struct _CLFS_READ_BUFFER *a6,
        unsigned int a7,
        struct IClfsRequestAsync *a8,
        unsigned int a9,
        union _CLS_LSN *a10,
        unsigned int *a11)
{
  __int64 v12; // r13
  unsigned int *v14; // rsi
  char v15; // r14
  char *v16; // r15
  __int64 v17; // r8
  int LsnRegion; // ebx
  bool v19; // bl
  const CLFS_LSN *v20; // rdx
  CClfsLogFcbPhysical *v21; // rcx
  unsigned int v23; // [rsp+38h] [rbp-A0h]
  BOOLEAN v24; // [rsp+70h] [rbp-68h]
  union _CLS_LSN v25; // [rsp+78h] [rbp-60h] BYREF
  unsigned int *v26; // [rsp+80h] [rbp-58h]
  union _CLS_LSN v27; // [rsp+88h] [rbp-50h] BYREF
  __int64 v28[9]; // [rsp+90h] [rbp-48h] BYREF
  unsigned int v30; // [rsp+F8h] [rbp+20h] BYREF

  v12 = a3;
  v25 = CLFS_LSN_INVALID;
  v14 = 0;
  v26 = 0;
  v15 = 0;
  v30 = 0;
  *a10 = CLFS_LSN_INVALID;
  v16 = (char *)this - 608;
  v24 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this - 408), 1u);
  LOBYTE(v17) = v12;
  v27 = *(union _CLS_LSN *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, __int64 *, __int64))(*(_QWORD *)this + 288LL))(
                             this,
                             v28,
                             v17);
  if ( (*((_DWORD *)this - 61) & 0x1000) != 0 )
  {
    LsnRegion = -1072037845;
    if ( !*((_DWORD *)this - 5) )
    {
      *((_DWORD *)this - 5) = 17;
      *((_DWORD *)this - 4) = -1072037845;
    }
  }
  else
  {
    v14 = (unsigned int *)ExAllocateFromPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage);
    v26 = v14;
    if ( v14 )
    {
      v15 = 1;
      v19 = 0;
      v28[0] = 16 * v12;
      if ( (unsigned __int8)operator>=(a4) )
        v19 = ClfsLsnLess(a4, v20 + 1) != 0;
      v21 = (CClfsLogFcbPhysical *)((char *)this - 608);
      if ( v19 )
      {
        v25 = **(union _CLS_LSN **)&CClfsLogFcbPhysical::GetNextRegionLsn(v21, &v27, (int)this - 104);
        memmove(v14, *((const void **)this + 12), 0x1000u);
      }
      else
      {
        LsnRegion = CClfsLogFcbPhysical::FindLsnRegion(v21, v12, a4, &v27, (unsigned __int8 *)v14, &v25);
        if ( LsnRegion < 0 )
          goto LABEL_13;
      }
      LsnRegion = CClfsLogFcbPhysical::ReadClientBlock(
                    (CClfsLogFcbPhysical *)((char *)this - 608),
                    a2,
                    v12,
                    a4,
                    &v25,
                    (const struct _CLFS_OWNER_REFERRAL *)((char *)v14 + v28[0] + v14[12]),
                    (const struct _CLFS_OWNER_ENTRY *const)((char *)v14 + v14[11]),
                    v23,
                    a6,
                    a7,
                    a8,
                    a9,
                    a10,
                    &v30);
      if ( LsnRegion >= 0 )
        *a11 = v30 << 9;
    }
    else
    {
      LsnRegion = -1073741670;
    }
  }
LABEL_13:
  if ( v24 )
    ClfsReleaseResourceLite(v16 + 200);
  if ( v15 )
    CClfsLogFcbPhysical::FreeOwnerPage((CClfsLogFcbPhysical *)((char *)this - 608), (unsigned __int8 *)v14);
  return (unsigned int)LsnRegion;
}

```

## disassembly

```asm
0x140064b00  mov     r11, rsp
0x140064b03  mov     [r11+10h], rdx
0x140064b07  mov     [r11+8], rcx
0x140064b0b  push    rbx
0x140064b0c  push    rsi
0x140064b0d  push    rdi
0x140064b0e  push    r12
0x140064b10  push    r13
0x140064b12  push    r14
0x140064b14  push    r15
0x140064b16  sub     rsp, 0A0h
0x140064b1d  mov     r12, r9
0x140064b20  movzx   r13d, r8b
0x140064b24  mov     rdi, rcx
0x140064b27  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140064b2e  mov     [r11-60h], rax
0x140064b32  xor     esi, esi
0x140064b34  mov     [r11-58h], rsi
0x140064b38  mov     [rsp+0D8h+var_68], sil
0x140064b3d  xor     r14b, r14b
0x140064b40  mov     [r11-67h], r14b
0x140064b44  mov     [r11+20h], esi
0x140064b48  mov     rcx, [rsp+0D8h+arg_48]
0x140064b50  mov     [rcx], rax
0x140064b53  lea     r15, [rdi-260h]
0x140064b5a  lea     rcx, [r15+0C8h]; Resource
0x140064b61  lea     ebx, [rsi+1]
0x140064b64  mov     dl, bl; Wait
0x140064b66  call    cs:__imp_ExAcquireResourceSharedLite
0x140064b6d  nop     dword ptr [rax+rax+00h]
0x140064b72  mov     [rsp+0D8h+var_68], al
0x140064b76  mov     rcx, [rdi]
0x140064b79  mov     rax, [rcx+120h]
0x140064b80  mov     r8b, r13b
0x140064b83  lea     rdx, [rsp+0D8h+var_48]
0x140064b8b  mov     rcx, rdi
0x140064b8e  call    _guard_dispatch_icall
0x140064b93  mov     rcx, [rax]
0x140064b96  mov     qword ptr [rsp+0D8h+var_50], rcx
0x140064b9e  test    dword ptr [rdi-0F4h], 1000h
0x140064ba8  jz      short loc_140064BCB
0x140064baa  mov     ebx, 0C01A002Bh
0x140064baf  mov     [rsp+0D8h+var_64], ebx
0x140064bb3  cmp     [rdi-14h], esi
0x140064bb6  jnz     loc_140064D6B
0x140064bbc  mov     dword ptr [rdi-14h], 11h
0x140064bc3  mov     [rdi-10h], ebx
0x140064bc6  jmp     loc_140064D6B
0x140064bcb  lea     rcx, ?m_laOwnerPage@CClfsLogFcbPhysical@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140064bd2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140064bd9  nop     dword ptr [rax+rax+00h]
0x140064bde  mov     rsi, rax
0x140064be1  mov     [rsp+0D8h+var_58], rax
0x140064be9  test    rax, rax
0x140064bec  jz      loc_140064D3E
0x140064bf2  mov     r14b, bl
0x140064bf5  mov     [rsp+0D8h+var_67], bl
0x140064bf9  mov     rcx, [rdi+60h]
0x140064bfd  xor     bl, bl
0x140064bff  mov     [rsp+0D8h+var_66], bl
0x140064c03  mov     rdx, r13
0x140064c06  shl     rdx, 4
0x140064c0a  mov     [rsp+0D8h+var_48], rdx
0x140064c12  mov     eax, [rcx+30h]
0x140064c15  add     rax, rcx
0x140064c18  add     rdx, rax
0x140064c1b  mov     rcx, r12
0x140064c1e  call    ??P@YAEAEBT_CLS_LSN@@0@Z; operator>=(_CLS_LSN const &,_CLS_LSN const &)
0x140064c23  test    al, al
0x140064c25  jnz     loc_140064D49
0x140064c2b  mov     rcx, r15; this
0x140064c2e  test    bl, bl
0x140064c30  jnz     loc_140064D0E
0x140064c36  lea     rax, [rsp+0D8h+var_60]
0x140064c3b  mov     [rsp+0D8h+var_B0], rax; union _CLS_LSN *
0x140064c40  mov     [rsp+0D8h+var_B8], rsi; unsigned __int8 *
0x140064c45  lea     r9, [rsp+0D8h+var_50]; union _CLS_LSN *
0x140064c4d  mov     r8, r12; union _CLS_LSN *
0x140064c50  mov     dl, r13b; unsigned __int8
0x140064c53  call    ?FindLsnRegion@CClfsLogFcbPhysical@@QEAAJEAEBT_CLS_LSN@@0PEAEAEAT2@@Z; CClfsLogFcbPhysical::FindLsnRegion(uchar,_CLS_LSN const &,_CLS_LSN const &,uchar *,_CLS_LSN &)
0x140064c58  mov     ebx, eax
0x140064c5a  mov     [rsp+0D8h+var_64], eax
0x140064c5e  test    eax, eax
0x140064c60  js      loc_140064D6B
0x140064c66  mov     edx, [rsi+2Ch]
0x140064c69  add     rdx, rsi
0x140064c6c  mov     ecx, [rsi+30h]
0x140064c6f  add     rcx, [rsp+0D8h+var_48]
0x140064c77  add     rcx, rsi
0x140064c7a  lea     rax, [rsp+0D8h+arg_18]
0x140064c82  mov     [rsp+0D8h+var_70], rax; unsigned int *
0x140064c87  mov     rax, [rsp+0D8h+arg_48]
0x140064c8f  mov     [rsp+0D8h+var_78], rax; union _CLS_LSN *
0x140064c94  mov     eax, [rsp+0D8h+arg_40]
0x140064c9b  mov     [rsp+0D8h+var_80], eax; unsigned int
0x140064c9f  mov     rax, [rsp+0D8h+arg_38]
0x140064ca7  mov     [rsp+0D8h+var_88], rax; struct IClfsRequestAsync *
0x140064cac  mov     eax, [rsp+0D8h+arg_30]
0x140064cb3  mov     [rsp+0D8h+var_90], eax; unsigned int
0x140064cb7  mov     rax, [rsp+0D8h+arg_28]
0x140064cbf  mov     [rsp+0D8h+var_98], rax; struct _CLFS_READ_BUFFER *
0x140064cc4  mov     [rsp+0D8h+var_A8], rdx; struct _CLFS_OWNER_ENTRY *
0x140064cc9  mov     [rsp+0D8h+var_B0], rcx; struct _CLFS_OWNER_REFERRAL *
0x140064cce  lea     rax, [rsp+0D8h+var_60]
0x140064cd3  mov     [rsp+0D8h+var_B8], rax; union _CLS_LSN *
0x140064cd8  mov     r9, r12; union _CLS_LSN *
0x140064cdb  mov     r8b, r13b; unsigned __int8
0x140064cde  mov     rdx, [rsp+0D8h+arg_8]; struct _FILE_OBJECT *
0x140064ce6  mov     rcx, r15; this
0x140064ce9  call    ?ReadClientBlock@CClfsLogFcbPhysical@@QEAAJPEAU_FILE_OBJECT@@EAEBT_CLS_LSN@@1AEBU_CLFS_OWNER_REFERRAL@@QEBU_CLFS_OWNER_ENTRY@@KAEBU_CLFS_READ_BUFFER@@KPEAUIClfsRequestAsync@@KAEAT3@AEAK@Z; CClfsLogFcbPhysical::ReadClientBlock(_FILE_OBJECT *,uchar,_CLS_LSN const &,_CLS_LSN const &,_CLFS_OWNER_REFERRAL const &,_CLFS_OWNER_ENTRY const * const,ulong,_CLFS_READ_BUFFER const &,ulong,IClfsRequestAsync *,ulong,_CLS_LSN &,ulong &)
0x140064cee  mov     ebx, eax
0x140064cf0  mov     [rsp+0D8h+var_64], eax
0x140064cf4  test    eax, eax
0x140064cf6  js      short loc_140064D6B
0x140064cf8  mov     ecx, [rsp+0D8h+arg_18]
0x140064cff  shl     ecx, 9
0x140064d02  mov     rax, [rsp+0D8h+arg_50]
0x140064d0a  mov     [rax], ecx
0x140064d0c  jmp     short loc_140064D6B
0x140064d0e  lea     r8, [rdi-68h]; unsigned int
0x140064d12  lea     rdx, [rsp+0D8h+var_50]; union _CLS_LSN *
0x140064d1a  call    ?GetNextRegionLsn@CClfsLogFcbPhysical@@AEAA?AT_CLS_LSN@@AEBT2@K@Z; CClfsLogFcbPhysical::GetNextRegionLsn(_CLS_LSN const &,ulong)
0x140064d1f  mov     rcx, [rax]
0x140064d22  mov     qword ptr [rsp+0D8h+var_60], rcx
0x140064d27  mov     r8d, 1000h; Size
0x140064d2d  mov     rdx, [rdi+60h]; Src
0x140064d31  mov     rcx, rsi; void *
0x140064d34  call    memmove
0x140064d39  jmp     loc_140064C66
0x140064d3e  mov     ebx, 0C000009Ah
0x140064d43  mov     [rsp+0D8h+var_64], ebx
0x140064d47  jmp     short loc_140064D6B
0x140064d49  add     rdx, 8; plsn2
0x140064d4d  mov     rcx, r12; plsn1
0x140064d50  call    ClfsLsnLess
0x140064d55  movzx   ebx, bl
0x140064d58  test    al, al
0x140064d5a  mov     eax, 1
0x140064d5f  cmovnz  ebx, eax
0x140064d62  mov     [rsp+0D8h+var_66], bl
0x140064d66  jmp     loc_140064C2B
0x140064d6b  cmp     [rsp+0D8h+var_68], 0
0x140064d70  jz      short loc_140064D7E
0x140064d72  lea     rcx, [r15+0C8h]
0x140064d79  call    ClfsReleaseResourceLite
0x140064d7e  test    r14b, r14b
0x140064d81  jz      short loc_140064D8E
0x140064d83  mov     rdx, rsi; unsigned __int8 *
0x140064d86  mov     rcx, r15; struct CClfsLogFcbPhysical *
0x140064d89  call    ?FreeOwnerPage@CClfsLogFcbPhysical@@CAXPEAV1@PEAE@Z; CClfsLogFcbPhysical::FreeOwnerPage(CClfsLogFcbPhysical *,uchar *)
0x140064d8e  mov     eax, ebx
0x140064d90  add     rsp, 0A0h
0x140064d97  pop     r15
0x140064d99  pop     r14
0x140064d9b  pop     r13
0x140064d9d  pop     r12
0x140064d9f  pop     rdi
0x140064da0  pop     rsi
0x140064da1  pop     rbx
0x140064da2  retn
0x14007abf6  push    rbp
0x14007abf8  sub     rsp, 70h
0x14007abfc  mov     rbp, rdx
0x14007abff  cmp     byte ptr [rbp+70h], 0
0x14007ac03  jz      short loc_14007AC1C
0x14007ac05  mov     rcx, [rbp+0E0h]
0x14007ac0c  add     rcx, 0FFFFFFFFFFFFFE68h
0x14007ac13  call    ClfsReleaseResourceLite
0x14007ac18  mov     byte ptr [rbp+70h], 0
0x14007ac1c  cmp     byte ptr [rbp+71h], 0
0x14007ac20  jz      short loc_14007AC47
0x14007ac22  mov     rcx, [rbp+0E0h]
0x14007ac29  add     rcx, 0FFFFFFFFFFFFFDA0h; struct CClfsLogFcbPhysical *
0x14007ac30  mov     rdx, [rbp+80h]; unsigned __int8 *
0x14007ac37  call    ?FreeOwnerPage@CClfsLogFcbPhysical@@CAXPEAV1@PEAE@Z; CClfsLogFcbPhysical::FreeOwnerPage(CClfsLogFcbPhysical *,uchar *)
0x14007ac3c  mov     qword ptr [rbp+80h], 0
0x14007ac47  add     rsp, 70h
0x14007ac4b  pop     rbp
0x14007ac4c  retn
```
