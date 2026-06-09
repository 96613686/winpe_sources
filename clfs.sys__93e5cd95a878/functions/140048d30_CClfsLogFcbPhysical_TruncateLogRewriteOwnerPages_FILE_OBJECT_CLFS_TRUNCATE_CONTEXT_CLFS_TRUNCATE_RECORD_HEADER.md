# CClfsLogFcbPhysical::TruncateLogRewriteOwnerPages(_FILE_OBJECT *,_CLFS_TRUNCATE_CONTEXT *,_CLFS_TRUNCATE_RECORD_HEADER *)

- ea: `0x140048d30`
- end: `0x1400491c3`
- name: `?TruncateLogRewriteOwnerPages@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@PEAU_CLFS_TRUNCATE_CONTEXT@@PEAU_CLFS_TRUNCATE_RECORD_HEADER@@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *, struct _CLFS_TRUNCATE_CONTEXT *, struct _CLFS_TRUNCATE_RECORD_HEADER *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x140048318`

## callees

- `0x1400032d0`
- `0x140007470`
- `0x14000a990`
- `0x14000e050`
- `0x14000ee30`
- `0x140011d90`
- `0x140015934`
- `0x140016574`
- `0x140017f20`
- `0x140017f80`
- `0x140048d30`
- `0x14004ae18`
- `0x14005fc68`
- `0x140060efc`
- `0x1400646d0`
- `0x140066e90`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140049191`
- `ntoskrnl!ObfDereferenceObject` at `0x14008021e`
- `ntoskrnl!ObfDereferenceObject` at `0x140049191`
- `ntoskrnl!ObfDereferenceObject` at `0x14008021e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140048e9c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140048e9c`
- `ntoskrnl!KeClearEvent` at `0x140048e1c`
- `ntoskrnl!KeClearEvent` at `0x140048e1c`

## string_xrefs

- `0x14004906b`: `CClfsLogFcbPhysical::TruncateLogRewriteOwnerPages`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::TruncateLogRewriteOwnerPages(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        struct _CLFS_TRUNCATE_CONTEXT *a3,
        struct _CLFS_TRUNCATE_RECORD_HEADER *a4)
{
  struct _CLFS_TRUNCATE_RECORD_HEADER *v4; // r12
  struct _CLFS_TRUNCATE_CONTEXT *v5; // r13
  struct _KEVENT *v7; // r14
  unsigned __int8 *v8; // r15
  unsigned int v9; // ecx
  CClfsLogFcbPhysical *v10; // rcx
  int v11; // edi
  enum _EVENT_TYPE v12; // ecx
  CLFS_LSN v13; // rbx
  char v14; // al
  __int64 v15; // rax
  char *v16; // r13
  struct _CLFS_TRUNCATE_CONTEXT *v17; // rbx
  char *v18; // rbx
  __int64 v19; // r12
  __int64 v20; // rcx
  __int64 v21; // r10
  struct _CLFS_TRUNCATE_RECORD_HEADER *v22; // r8
  __int64 v23; // rdx
  char *v24; // rcx
  char v25; // al
  unsigned int v26; // ebx
  int v27; // r12d
  CLFS_LSN plsn; // [rsp+48h] [rbp-90h] BYREF
  PRKEVENT Event; // [rsp+50h] [rbp-88h] BYREF
  int v31; // [rsp+58h] [rbp-80h]
  unsigned int v32; // [rsp+5Ch] [rbp-7Ch]
  unsigned int v33[2]; // [rsp+60h] [rbp-78h] BYREF
  struct CClfsAuthContainer *v34; // [rsp+68h] [rbp-70h] BYREF
  __int64 v35; // [rsp+70h] [rbp-68h]
  unsigned __int8 *v36; // [rsp+78h] [rbp-60h]
  union _CLS_LSN v37; // [rsp+80h] [rbp-58h] BYREF
  union _CLS_LSN v38; // [rsp+88h] [rbp-50h] BYREF
  union _CLS_LSN v39; // [rsp+90h] [rbp-48h] BYREF
  union _CLS_LSN v40; // [rsp+98h] [rbp-40h] BYREF
  unsigned int v41; // [rsp+E8h] [rbp+10h] BYREF
  int v42; // [rsp+ECh] [rbp+14h]
  struct _CLFS_TRUNCATE_CONTEXT *v43; // [rsp+F0h] [rbp+18h]
  struct _CLFS_TRUNCATE_RECORD_HEADER *v44; // [rsp+F8h] [rbp+20h]

  v44 = a4;
  v43 = a3;
  v42 = HIDWORD(a2);
  v4 = a4;
  v5 = a3;
  v34 = 0;
  v7 = 0;
  Event = 0;
  v8 = 0;
  v36 = 0;
  v33[0] = 0;
  v41 = 0;
  v9 = *(_DWORD *)(*((_QWORD *)this + 89) + 144LL);
  v31 = v9;
  if ( v9 - 1 > 0xFFF || (v9 & 0x1FF) != 0 || (v32 = 0x1000 / v9, 0x1000 % v9) )
  {
    v11 = -1073741672;
    goto LABEL_43;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
  {
LABEL_5:
    v11 = -1072037875;
    goto LABEL_43;
  }
  v11 = CClfsLogFcbPhysical::ValidateTruncateRecord(v10, v4);
  if ( v11 >= 0 )
  {
    v11 = ClfsCreateEventObject(v12, &Event);
    if ( v11 < 0 )
    {
      v7 = 0;
      Event = 0;
      goto LABEL_43;
    }
    v7 = Event;
    KeClearEvent(Event);
    v13 = *(CLFS_LSN *)((char *)v5 + 8);
    plsn = v13;
    while ( 1 )
    {
      if ( v5 == (struct _CLFS_TRUNCATE_CONTEXT *)-16LL )
      {
        v14 = 0;
      }
      else
      {
        if ( v13.ullOffset >= *((_QWORD *)v5 + 2) )
          goto LABEL_41;
        v14 = 1;
      }
      if ( !v14 )
      {
LABEL_41:
        *(_DWORD *)v5 = 4;
        v11 = CClfsBaseFilePersisted::FlushControlRecord(*((CClfsBaseFilePersisted **)this + 89));
        break;
      }
      v15 = *((unsigned int *)v4 + 3);
      if ( (v15 & 7) != 0 )
        goto LABEL_5;
      v16 = (char *)v4 + v15;
      v17 = v43;
      if ( *(_DWORD *)v43 == 2 )
      {
        v37.ullOffset = 0;
        if ( !v8 )
        {
          v8 = (unsigned __int8 *)ExAllocateFromPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage);
          v36 = v8;
          if ( !v8 )
            break;
        }
        v11 = CClfsLogFcbPhysical::ReadOwnerPage(this, &plsn, 0, 0, v8, &v37);
        if ( v11 < 0 )
          break;
        memmove(v16, v8, 0x1000u);
        v11 = CClfsBaseFilePersisted::WriteMetadataBlock(*((CClfsBaseFilePersisted **)this + 89), 4u, 1u);
        if ( v11 < 0 )
          break;
        *(_DWORD *)v17 = 3;
        v11 = CClfsBaseFilePersisted::FlushControlRecord(*((CClfsBaseFilePersisted **)this + 89));
        if ( v11 < 0 )
          break;
      }
      v18 = &v16[*((unsigned int *)v16 + 12)];
      v19 = *((unsigned int *)v4 + 2);
      v35 = *(_QWORD *)CClfsLogFcbPhysical::GetNextBlockLsn(
                         this,
                         (union _CLS_LSN)&v38,
                         *(_QWORD *)((char *)v44 + v19 + 16)).ullOffset;
      if ( *((_DWORD *)v16 + 12) > *((unsigned __int16 *)v16 + 2) << 9 )
        goto LABEL_5;
      v20 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 89) + 48LL) + 96LL);
      v11 = RtlULongSub(*(_DWORD *)(v20 + 104), *(_DWORD *)(v20 + 40), &v41);
      if ( v11 < 0 )
        break;
      v22 = v44;
      v23 = 16LL * *((unsigned __int8 *)v44 + v19);
      if ( &v18[v23 + 16] > (char *)v44 + v41 )
        goto LABEL_5;
      *(_QWORD *)&v18[v23 + 8] = v21;
      v24 = &v18[16 * *((unsigned __int8 *)v22 + v19)];
      if ( v24 )
      {
        if ( *(_QWORD *)v24 <= __PAIR64__(HIDWORD(v35), v21) )
          goto LABEL_31;
        v25 = 1;
      }
      else
      {
        v25 = 0;
      }
      if ( v25 )
        *(_QWORD *)v24 = v21;
LABEL_31:
      v11 = ClfsEncodeBlock((struct _CLFS_LOG_BLOCK_HEADER *)v16, 0x1000u, v16[2], 8u, 0);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            52,
            (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
            (unsigned int)"CClfsLogFcbPhysical::TruncateLogRewriteOwnerPages",
            151);
        }
        break;
      }
      v26 = 0;
      v27 = v31;
      while ( 1 )
      {
        v33[1] = v26;
        if ( v26 >= v32 )
          break;
        v11 = CClfsLogFcbPhysical::WriteOneRawSectorSync(
                this,
                &v34,
                v33,
                (unsigned __int8 *)&v16[v27 * v26],
                &plsn,
                0,
                v7);
        if ( v11 < 0 )
          goto LABEL_43;
        plsn = **(CLFS_LSN **)&CClfsLogFcbPhysical::AddLsnOffset(this, &v39, (unsigned int)&plsn);
        ++v26;
      }
      v13 = **(CLFS_LSN **)&CClfsLogFcbPhysical::GetNextOwnerPageLsn(this, &v40, (unsigned int)&plsn);
      plsn = v13;
      v5 = v43;
      *((CLFS_LSN *)v43 + 1) = v13;
      *(_DWORD *)v5 = 2;
      v11 = CClfsBaseFilePersisted::FlushControlRecord(*((CClfsBaseFilePersisted **)this + 89));
      if ( v11 < 0 )
        break;
      v4 = v44;
    }
  }
LABEL_43:
  if ( v34 )
    (*(void (__fastcall **)(struct CClfsAuthContainer *))(*(_QWORD *)v34 + 8LL))(v34);
  if ( v7 )
    ObfDereferenceObject(v7);
  if ( v8 )
    CClfsLogFcbPhysical::FreeOwnerPage(this, v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140048d30  mov     rax, rsp
0x140048d33  mov     [rax+20h], r9
0x140048d37  mov     [rax+18h], r8
0x140048d3b  mov     [rax+10h], rdx
0x140048d3f  mov     [rax+8], rcx
0x140048d43  push    rbx
0x140048d44  push    rsi
0x140048d45  push    rdi
0x140048d46  push    r12
0x140048d48  push    r13
0x140048d4a  push    r14
0x140048d4c  push    r15
0x140048d4e  sub     rsp, 0A0h
0x140048d55  mov     r12, r9
0x140048d58  mov     r13, r8
0x140048d5b  mov     rsi, rcx
0x140048d5e  mov     qword ptr [rax-70h], 0
0x140048d66  xor     r14d, r14d
0x140048d69  mov     [rsp+0D8h+Event], r14
0x140048d6e  xor     r15d, r15d
0x140048d71  mov     [rax-60h], r15
0x140048d75  mov     [rax-78h], r14d
0x140048d79  mov     [rax+10h], r14d
0x140048d7d  mov     rax, [rcx+2C8h]
0x140048d84  mov     ecx, [rax+90h]
0x140048d8a  mov     [rsp+0D8h+var_80], ecx
0x140048d8e  lea     eax, [rcx-1]
0x140048d91  cmp     eax, 0FFFh
0x140048d96  ja      loc_14004916A
0x140048d9c  test    ecx, 1FFh
0x140048da2  jnz     loc_14004916A
0x140048da8  xor     edx, edx
0x140048daa  mov     eax, 1000h
0x140048daf  div     ecx
0x140048db1  mov     [rsp+0D8h+var_7C], eax
0x140048db5  test    edx, edx
0x140048db7  jnz     loc_14004916A
0x140048dbd  mov     rax, [rsi]
0x140048dc0  mov     rax, [rax+138h]
0x140048dc7  mov     rcx, rsi
0x140048dca  call    _guard_dispatch_icall
0x140048dcf  test    al, al
0x140048dd1  jnz     short loc_140048DDD
0x140048dd3  mov     edi, 0C01A000Dh
0x140048dd8  jmp     loc_14004916F
0x140048ddd  mov     rdx, r12; struct _CLFS_TRUNCATE_RECORD_HEADER *
0x140048de0  call    ?ValidateTruncateRecord@CClfsLogFcbPhysical@@AEAAJPEAU_CLFS_TRUNCATE_RECORD_HEADER@@@Z; CClfsLogFcbPhysical::ValidateTruncateRecord(_CLFS_TRUNCATE_RECORD_HEADER *)
0x140048de5  mov     edi, eax
0x140048de7  mov     [rsp+0D8h+var_98], eax
0x140048deb  test    eax, eax
0x140048ded  js      loc_140049173
0x140048df3  lea     rdx, [rsp+0D8h+Event]; struct _KEVENT **
0x140048df8  call    ?ClfsCreateEventObject@@YAJW4_EVENT_TYPE@@AEAPEAU_KEVENT@@@Z; ClfsCreateEventObject(_EVENT_TYPE,_KEVENT * &)
0x140048dfd  mov     edi, eax
0x140048dff  mov     [rsp+0D8h+var_98], eax
0x140048e03  test    eax, eax
0x140048e05  jns     short loc_140048E14
0x140048e07  xor     r14d, r14d
0x140048e0a  mov     [rsp+0D8h+Event], r14
0x140048e0f  jmp     loc_140049173
0x140048e14  mov     r14, [rsp+0D8h+Event]
0x140048e19  mov     rcx, r14; Event
0x140048e1c  call    cs:__imp_KeClearEvent
0x140048e23  nop     dword ptr [rax+rax+00h]
0x140048e28  mov     rbx, [r13+8]
0x140048e2c  mov     qword ptr [rsp+0D8h+var_90], rbx
0x140048e31  mov     rax, rbx
0x140048e34  lea     rcx, [r13+10h]
0x140048e38  test    rcx, rcx
0x140048e3b  jz      short loc_140048E58
0x140048e3d  shr     rax, 20h
0x140048e41  cmp     eax, [rcx+4]
0x140048e44  ja      loc_14004914E
0x140048e4a  jnz     short loc_140048E54
0x140048e4c  cmp     ebx, [rcx]
0x140048e4e  jnb     loc_14004914E
0x140048e54  mov     al, 1
0x140048e56  jmp     short loc_140048E5A
0x140048e58  xor     al, al
0x140048e5a  test    al, al
0x140048e5c  jz      loc_14004914E
0x140048e62  mov     eax, [r12+0Ch]
0x140048e67  test    al, 7
0x140048e69  jnz     loc_140048DD3
0x140048e6f  lea     r13, [r12+rax]
0x140048e73  mov     rbx, [rsp+0D8h+arg_10]
0x140048e7b  cmp     dword ptr [rbx], 2
0x140048e7e  jnz     loc_140048F3F
0x140048e84  mov     qword ptr [rsp+0D8h+var_58], 0
0x140048e90  test    r15, r15
0x140048e93  jnz     short loc_140048EB9
0x140048e95  lea     rcx, ?m_laOwnerPage@CClfsLogFcbPhysical@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140048e9c  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140048ea3  nop     dword ptr [rax+rax+00h]
0x140048ea8  mov     r15, rax
0x140048eab  mov     [rsp+0D8h+var_60], rax
0x140048eb0  test    rax, rax
0x140048eb3  jz      loc_140049173
0x140048eb9  lea     rax, [rsp+0D8h+var_58]
0x140048ec1  mov     [rsp+0D8h+var_B0], rax; union _CLS_LSN *
0x140048ec6  mov     [rsp+0D8h+plsn], r15; unsigned __int8 *
0x140048ecb  xor     r9d, r9d; unsigned __int8
0x140048ece  xor     r8d, r8d; unsigned int
0x140048ed1  lea     rdx, [rsp+0D8h+var_90]; union _CLS_LSN *
0x140048ed6  mov     rcx, rsi; this
0x140048ed9  call    ?ReadOwnerPage@CClfsLogFcbPhysical@@AEAAJAEBT_CLS_LSN@@KEPEAEAEAT2@@Z; CClfsLogFcbPhysical::ReadOwnerPage(_CLS_LSN const &,ulong,uchar,uchar *,_CLS_LSN &)
0x140048ede  mov     edi, eax
0x140048ee0  mov     [rsp+0D8h+var_98], eax
0x140048ee4  test    eax, eax
0x140048ee6  js      loc_140049173
0x140048eec  mov     r8d, 1000h; Size
0x140048ef2  mov     rdx, r15; Src
0x140048ef5  mov     rcx, r13; void *
0x140048ef8  call    memmove
0x140048efd  mov     r8b, 1; unsigned __int8
0x140048f00  mov     edx, 4; unsigned int
0x140048f05  mov     rcx, [rsi+2C8h]; this
0x140048f0c  call    ?WriteMetadataBlock@CClfsBaseFilePersisted@@QEAAJKE@Z; CClfsBaseFilePersisted::WriteMetadataBlock(ulong,uchar)
0x140048f11  mov     edi, eax
0x140048f13  mov     [rsp+0D8h+var_98], eax
0x140048f17  test    eax, eax
0x140048f19  js      loc_140049173
0x140048f1f  mov     dword ptr [rbx], 3
0x140048f25  mov     rcx, [rsi+2C8h]; this
0x140048f2c  call    ?FlushControlRecord@CClfsBaseFilePersisted@@AEAAJXZ; CClfsBaseFilePersisted::FlushControlRecord(void)
0x140048f31  mov     edi, eax
0x140048f33  mov     [rsp+0D8h+var_98], eax
0x140048f37  test    eax, eax
0x140048f39  js      loc_140049173
0x140048f3f  mov     ebx, [r13+30h]
0x140048f43  add     rbx, r13
0x140048f46  mov     r12d, [r12+8]
0x140048f4b  mov     r8, [rsp+0D8h+arg_18]
0x140048f53  movzx   r9d, word ptr [r12+r8+20h]
0x140048f59  shl     r9d, 9
0x140048f5d  mov     r8, [r12+r8+10h]; unsigned int
0x140048f62  lea     rdx, [rsp+0D8h+var_50]; union _CLS_LSN
0x140048f6a  mov     rcx, rsi; this
0x140048f6d  call    ?GetNextBlockLsn@CClfsLogFcbPhysical@@AEAA?AT_CLS_LSN@@T2@K@Z; CClfsLogFcbPhysical::GetNextBlockLsn(_CLS_LSN,ulong)
0x140048f72  mov     r10, [rax]
0x140048f75  mov     [rsp+0D8h+var_68], r10
0x140048f7a  movzx   eax, word ptr [r13+4]
0x140048f7f  shl     eax, 9
0x140048f82  cmp     [r13+30h], eax
0x140048f86  ja      loc_140048DD3
0x140048f8c  mov     rax, [rsi+2C8h]
0x140048f93  mov     rcx, [rax+30h]
0x140048f97  mov     rcx, [rcx+60h]
0x140048f9b  lea     r8, [rsp+0D8h+arg_8]; unsigned int *
0x140048fa3  mov     edx, [rcx+28h]; unsigned int
0x140048fa6  mov     ecx, [rcx+68h]; unsigned int
0x140048fa9  call    ?RtlULongSub@@YAJKKPEAK@Z; RtlULongSub(ulong,ulong,ulong *)
0x140048fae  mov     edi, eax
0x140048fb0  mov     [rsp+0D8h+var_98], eax
0x140048fb4  test    eax, eax
0x140048fb6  js      loc_140049173
0x140048fbc  mov     r8, [rsp+0D8h+arg_18]
0x140048fc4  movzx   edx, byte ptr [r12+r8]
0x140048fc9  shl     rdx, 4
0x140048fcd  mov     ecx, [rsp+0D8h+arg_8]
0x140048fd4  add     rcx, r8
0x140048fd7  lea     rax, [rdx+10h]
0x140048fdb  add     rax, rbx
0x140048fde  cmp     rax, rcx
0x140048fe1  ja      loc_140048DD3
0x140048fe7  mov     [rdx+rbx+8], r10
0x140048fec  movzx   ecx, byte ptr [r12+r8]
0x140048ff1  shl     rcx, 4
0x140048ff5  add     rcx, rbx
0x140048ff8  jz      short loc_14004900E
0x140048ffa  mov     eax, [rcx+4]
0x140048ffd  cmp     eax, dword ptr [rsp+0D8h+var_68+4]
0x140049001  jb      short loc_140049017
0x140049003  jnz     short loc_14004900A
0x140049005  cmp     [rcx], r10d
0x140049008  jbe     short loc_140049017
0x14004900a  mov     al, 1
0x14004900c  jmp     short loc_140049010
0x14004900e  xor     al, al
0x140049010  test    al, al
0x140049012  jz      short loc_140049017
0x140049014  mov     [rcx], r10
0x140049017  mov     byte ptr [rsp+0D8h+plsn], 0; char
0x14004901c  mov     r9b, 8; unsigned __int8
0x14004901f  mov     r8b, [r13+2]; unsigned __int8
0x140049023  mov     edx, 1000h; unsigned int
0x140049028  mov     rcx, r13; struct _CLFS_LOG_BLOCK_HEADER *
0x14004902b  call    ?ClfsEncodeBlock@@YAJPEAU_CLFS_LOG_BLOCK_HEADER@@KEEE@Z; ClfsEncodeBlock(_CLFS_LOG_BLOCK_HEADER *,ulong,uchar,uchar,uchar)
0x140049030  mov     edi, eax
0x140049032  mov     [rsp+0D8h+var_98], eax
0x140049036  test    eax, eax
0x140049038  jns     short loc_140049087
0x14004903a  lea     rax, WPP_GLOBAL_Control
0x140049041  mov     rcx, cs:WPP_GLOBAL_Control
0x140049048  cmp     rcx, rax
0x14004904b  jz      loc_140049173
0x140049051  mov     eax, [rcx+2Ch]
0x140049054  bt      eax, 1Bh
0x140049058  jnb     loc_140049173
0x14004905e  mov     edx, 34h ; '4'
0x140049063  mov     dword ptr [rsp+0D8h+plsn], 5497h
0x14004906b  lea     r9, aCclfslogfcbphy_0; "CClfsLogFcbPhysical::TruncateLogRewrite"...
0x140049072  lea     r8, WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids
0x140049079  mov     rcx, [rcx+18h]
0x14004907d  call    WPP_SF_sd
0x140049082  jmp     loc_140049173
0x140049087  xor     ebx, ebx
0x140049089  mov     r12d, [rsp+0D8h+var_80]
0x14004908e  mov     [rsp+0D8h+var_74], ebx
0x140049092  mov     rcx, rsi; this
0x140049095  cmp     ebx, [rsp+0D8h+var_7C]
0x140049099  jnb     short loc_1400490FA
0x14004909b  mov     r9d, ebx
0x14004909e  imul    r9d, r12d
0x1400490a2  add     r9, r13; unsigned __int8 *
0x1400490a5  mov     [rsp+0D8h+var_A8], r14; struct _KEVENT *
0x1400490aa  mov     byte ptr [rsp+0D8h+var_B0], 0; char
0x1400490af  lea     rax, [rsp+0D8h+var_90]
0x1400490b4  mov     [rsp+0D8h+plsn], rax; plsn
0x1400490b9  lea     r8, [rsp+0D8h+var_78]; unsigned int *
0x1400490be  lea     rdx, [rsp+0D8h+var_70]; struct CClfsAuthContainer **
0x1400490c3  call    ?WriteOneRawSectorSync@CClfsLogFcbPhysical@@AEAAJAEAPEAVCClfsAuthContainer@@AEAKPEAEAEAT_CLS_LSN@@EPEAU_KEVENT@@@Z; CClfsLogFcbPhysical::WriteOneRawSectorSync(CClfsAuthContainer * &,ulong &,uchar *,_CLS_LSN &,uchar,_KEVENT *)
0x1400490c8  mov     edi, eax
0x1400490ca  mov     [rsp+0D8h+var_98], eax
0x1400490ce  test    eax, eax
0x1400490d0  js      loc_140049173
0x1400490d6  mov     r9d, r12d
0x1400490d9  lea     r8, [rsp+0D8h+var_90]; unsigned int
0x1400490de  lea     rdx, [rsp+0D8h+var_48]; union _CLS_LSN *
0x1400490e6  mov     rcx, rsi; this
0x1400490e9  call    ?AddLsnOffset@CClfsLogFcbPhysical@@AEAA?AT_CLS_LSN@@AEBT2@K@Z; CClfsLogFcbPhysical::AddLsnOffset(_CLS_LSN const &,ulong)
0x1400490ee  mov     rcx, [rax]
0x1400490f1  mov     qword ptr [rsp+0D8h+var_90], rcx
0x1400490f6  inc     ebx
0x1400490f8  jmp     short loc_14004908E
0x1400490fa  xor     r9d, r9d
0x1400490fd  lea     r8, [rsp+0D8h+var_90]; unsigned int
0x140049102  lea     rdx, [rsp+0D8h+var_40]; union _CLS_LSN *
0x14004910a  call    ?GetNextOwnerPageLsn@CClfsLogFcbPhysical@@AEAA?AT_CLS_LSN@@AEBT2@K@Z; CClfsLogFcbPhysical::GetNextOwnerPageLsn(_CLS_LSN const &,ulong)
0x14004910f  mov     rbx, [rax]
0x140049112  mov     qword ptr [rsp+0D8h+var_90], rbx
0x140049117  mov     r13, [rsp+0D8h+arg_10]
0x14004911f  mov     [r13+8], rbx
0x140049123  mov     dword ptr [r13+0], 2
0x14004912b  mov     rcx, [rsi+2C8h]; this
0x140049132  call    ?FlushControlRecord@CClfsBaseFilePersisted@@AEAAJXZ; CClfsBaseFilePersisted::FlushControlRecord(void)
0x140049137  mov     edi, eax
0x140049139  mov     [rsp+0D8h+var_98], eax
0x14004913d  test    eax, eax
0x14004913f  js      short loc_140049173
0x140049141  mov     r12, [rsp+0D8h+arg_18]
0x140049149  jmp     loc_140048E31
0x14004914e  mov     dword ptr [r13+0], 4
0x140049156  mov     rcx, [rsi+2C8h]; this
0x14004915d  call    ?FlushControlRecord@CClfsBaseFilePersisted@@AEAAJXZ; CClfsBaseFilePersisted::FlushControlRecord(void)
0x140049162  mov     edi, eax
0x140049164  mov     [rsp+0D8h+var_98], eax
0x140049168  jmp     short loc_140049173
0x14004916a  mov     edi, 0C0000098h
0x14004916f  mov     [rsp+0D8h+var_98], edi
0x140049173  mov     rcx, [rsp+0D8h+var_70]
0x140049178  test    rcx, rcx
0x14004917b  jz      short loc_140049189
0x14004917d  mov     rax, [rcx]
0x140049180  mov     rax, [rax+8]
0x140049184  call    _guard_dispatch_icall
0x140049189  test    r14, r14
0x14004918c  jz      short loc_14004919D
0x14004918e  mov     rcx, r14; Object
0x140049191  call    cs:__imp_ObfDereferenceObject
0x140049198  nop     dword ptr [rax+rax+00h]
0x14004919d  test    r15, r15
0x1400491a0  jz      short loc_1400491AD
0x1400491a2  mov     rdx, r15; unsigned __int8 *
0x1400491a5  mov     rcx, rsi; struct CClfsLogFcbPhysical *
0x1400491a8  call    ?FreeOwnerPage@CClfsLogFcbPhysical@@CAXPEAV1@PEAE@Z; CClfsLogFcbPhysical::FreeOwnerPage(CClfsLogFcbPhysical *,uchar *)
0x1400491ad  mov     eax, edi
0x1400491af  add     rsp, 0A0h
0x1400491b6  pop     r15
0x1400491b8  pop     r14
0x1400491ba  pop     r13
0x1400491bc  pop     r12
0x1400491be  pop     rdi
0x1400491bf  pop     rsi
0x1400491c0  pop     rbx
0x1400491c1  retn
0x1400801f6  push    rbp
0x1400801f8  sub     rsp, 40h
0x1400801fc  mov     rbp, rdx
0x1400801ff  mov     rcx, [rbp+68h]
0x140080203  test    rcx, rcx
0x140080206  jz      short loc_140080215
0x140080208  mov     rax, [rcx]
0x14008020b  mov     rax, [rax+8]
0x14008020f  call    _guard_dispatch_icall
0x140080214  nop
0x140080215  mov     rcx, [rbp+50h]; Object
0x140080219  test    rcx, rcx
0x14008021c  jz      short loc_14008022B
0x14008021e  call    cs:__imp_ObfDereferenceObject
  ... truncated ...
```
