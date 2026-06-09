# RefsCreateFcb(_IRP_CONTEXT *,_REFS_FILE_REFERENCE,_REFS_ACQUIRE_FLAGS,_REFS_CREATE_FCB_INFLAGS,IndexSCB *,_REFS_CREATE_FCB_OUTFLAGS *)

- ea: `0x140304220`
- end: `0x14030472a`
- name: `?RefsCreateFcb@@YAPEAU_FCB@@PEAU_IRP_CONTEXT@@U_REFS_FILE_REFERENCE@@W4_REFS_ACQUIRE_FLAGS@@W4_REFS_CREATE_FCB_INFLAGS@@PEAUIndexSCB@@PEAW4_REFS_CREATE_FCB_OUTFLAGS@@@Z`
- size: `1290`
- prototype: ``
- caller_count: `15`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d0ecc`
- `0x1400d5b60`
- `0x1400fb6fc`
- `0x1400fe670`
- `0x140290de0`
- `0x140291760`
- `0x140293194`
- `0x140295074`
- `0x1402a3624`
- `0x1402c7948`
- `0x1402f7a78`
- `0x1403036e4`
- `0x1403040a0`
- `0x140304730`
- `0x14033a130`

## callees

- `0x140038f80`
- `0x140080680`
- `0x140081670`
- `0x14008dbd0`
- `0x14008e2b0`
- `0x14008e330`
- `0x1400a5780`
- `0x1400ca788`
- `0x1402867ec`
- `0x140304220`
- `0x1403240d0`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403042bd`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403045bf`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033f220`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403042bd`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403045bf`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033f220`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1403043a3`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1403043c3`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1403043a3`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1403043c3`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14030447c`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14030447c`
- `ntoskrnl!ExReleaseFastResource` at `0x140304561`
- `ntoskrnl!ExReleaseFastResource` at `0x1403045dc`
- `ntoskrnl!ExReleaseFastResource` at `0x140304609`
- `ntoskrnl!ExReleaseFastResource` at `0x140304627`
- `ntoskrnl!ExReleaseFastResource` at `0x14033f1e4`
- `ntoskrnl!ExReleaseFastResource` at `0x14033f23d`
- `ntoskrnl!ExReleaseFastResource` at `0x14033f26e`
- `ntoskrnl!ExReleaseFastResource` at `0x140304561`
- `ntoskrnl!ExReleaseFastResource` at `0x1403045dc`
- `ntoskrnl!ExReleaseFastResource` at `0x140304609`
- `ntoskrnl!ExReleaseFastResource` at `0x140304627`
- `ntoskrnl!ExReleaseFastResource` at `0x14033f1e4`
- `ntoskrnl!ExReleaseFastResource` at `0x14033f23d`
- `ntoskrnl!ExReleaseFastResource` at `0x14033f26e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f1ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f1ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140304352`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140304352`

## pseudocode

```c
_FCB *__fastcall RefsCreateFcb(struct _IRP_CONTEXT *a1, __int64 a2, __int64 a3, char a4, struct _SRV_OPEN *a5, int *a6)
{
  struct _VCB *v8; // rdi
  char v9; // si
  int *v10; // r15
  _FCB *PoolWithTag; // rbx
  _QWORD *v12; // rdi
  char v13; // r12
  int v14; // eax
  _QWORD *v15; // rax
  __int64 v16; // r12
  unsigned int v17; // r8d
  __int64 v18; // rsi
  _FCB *v19; // rax
  unsigned __int64 v20; // r8
  struct _VCB *v21; // r12
  unsigned int v22; // r8d
  __int64 NonpagedFcb; // r9
  unsigned __int64 v24; // rdx
  char v25; // r8
  char v26; // di
  __int64 v27; // r9
  char v28; // al
  _QWORD *v29; // r13
  __int64 v30; // r9
  unsigned __int8 v32; // [rsp+31h] [rbp-97h]
  unsigned __int8 v33; // [rsp+32h] [rbp-96h]
  int v35; // [rsp+38h] [rbp-90h]
  _QWORD *v36; // [rsp+48h] [rbp-80h]
  int v37; // [rsp+60h] [rbp-68h] BYREF
  struct _VCB *v38; // [rsp+68h] [rbp-60h]
  __int64 v39; // [rsp+70h] [rbp-58h]
  struct _VCB *v40; // [rsp+78h] [rbp-50h]
  int *v41; // [rsp+80h] [rbp-48h]

  v35 = a3;
  v8 = (struct _VCB *)*((_QWORD *)a1 + 8);
  v38 = v8;
  v40 = v8;
  v37 = 0;
  v9 = 0;
  v39 = 0;
  if ( *(_QWORD *)a2 || (v32 = 1, !*(_QWORD *)(a2 + 8)) )
    v32 = 0;
  v10 = &v37;
  if ( a6 )
    v10 = a6;
  v41 = v10;
  *v10 = 0;
  PoolWithTag = 0;
  v36 = (_QWORD *)((char *)v8 + 624);
  LOBYTE(a3) = 1;
  ExAcquireFastResourceExclusive((char *)v8 + 624, 0, a3);
  v12 = (_QWORD *)*((_QWORD *)v8 + 104);
  v33 = 0;
  v13 = 0;
  if ( v12 )
  {
    while ( 1 )
    {
      v14 = RefsFcbTableCompare(a2, v12);
      if ( v14 <= 0 )
      {
        if ( v14 >= 0 )
        {
          v13 = 1;
          break;
        }
        v15 = (_QWORD *)*v12;
        if ( !*v12 )
        {
          v33 = 0;
          break;
        }
      }
      else
      {
        v15 = (_QWORD *)v12[1];
        if ( !v15 )
        {
          v33 = 1;
          break;
        }
      }
      v12 = v15;
    }
  }
  if ( v13 )
  {
    PoolWithTag = (_FCB *)*(v12 - 1);
    *v10 |= 1u;
  }
  if ( !PoolWithTag )
  {
    if ( (a4 & 9) != 0 )
    {
      v16 = 368;
      PoolWithTag = (_FCB *)ExAllocatePoolWithTag((POOL_TYPE)528, 0x170u, 0x66666552u);
      v18 = 2;
      if ( (a4 & 1) != 0 )
      {
        if ( (*((_DWORD *)v38 + 6) & 0x2000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              WPP_a4a5732f13c731212091050c8dbbcecd_Traceguids,
              3221225634LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741662, a1, "StrucSup.c", 0xC24u);
          RefsRaiseStatusInternal(a1, -1073741662, v17);
          goto LABEL_66;
        }
        v18 = 6;
      }
    }
    else
    {
      if ( v32 )
      {
        v19 = (_FCB *)ExAllocateFromLookasideListEx(&RefsFcbIndexLookasideList);
        v18 = 1024;
        v16 = 1520;
      }
      else
      {
        v19 = (_FCB *)ExAllocateFromLookasideListEx(&RefsFcbDataLookasideList);
        v18 = 512;
        v16 = 1248;
      }
      PoolWithTag = v19;
    }
    v20 = v16;
    v21 = v38;
    _FCB::Initialize(PoolWithTag, v38, v20);
    PoolWithTag->Header.Resource = (PERESOURCE)v18;
    PoolWithTag->ScavengerFinalizationList.Blink = 0;
    NonpagedFcb = RefsCreateNonpagedFcb((_DWORD)a1, (_DWORD)PoolWithTag, a2, v32, v35);
    PoolWithTag->pNetRoot = (PMRX_NET_ROOT)NonpagedFcb;
    v39 = NonpagedFcb;
    if ( NonpagedFcb )
    {
      v9 = 1;
      PoolWithTag->InternalSrvOpen = a5;
      if ( (a4 & 8) != 0 )
      {
        PoolWithTag->Header.Resource = (PERESOURCE)((unsigned __int64)PoolWithTag->Header.Resource | 0x1000000);
      }
      else
      {
        RtlAvlInsertNodeEx(PoolWithTag->Header.FileContextSupportPointer + 104, v12, v33, NonpagedFcb + 272);
        ++*((_DWORD *)PoolWithTag->Header.FileContextSupportPointer + 210);
        PoolWithTag->Header.Resource = (PERESOURCE)((unsigned __int64)PoolWithTag->Header.Resource | 0x40);
      }
      if ( RefsIsSystemObjectId((const struct _REFS_FILE_REFERENCE *)a2) )
      {
        v24 |= 0x100u;
        PoolWithTag->Header.Resource = (PERESOURCE)v24;
      }
      if ( (v25 & 0x10) != 0 )
      {
        v24 |= 0x10000000u;
        PoolWithTag->Header.Resource = (PERESOURCE)v24;
      }
      if ( (v25 & 0x20) != 0 )
      {
        v24 |= 0x200000u;
        PoolWithTag->Header.Resource = (PERESOURCE)v24;
      }
      if ( (*((_DWORD *)v21 + 7) & 1) != 0 )
      {
        v24 |= 0x80u;
        PoolWithTag->Header.Resource = (PERESOURCE)v24;
      }
      if ( (*((_DWORD *)v21 + 7) & 0x40) != 0 )
        PoolWithTag->Header.Resource = (PERESOURCE)(v24 | 0x20);
      goto LABEL_40;
    }
LABEL_66:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_a4a5732f13c731212091050c8dbbcecd_Traceguids, 3221225626LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741670, a1, "StrucSup.c", 0xC58u);
    RefsRaiseStatusInternal(a1, -1073741670, v22);
    __debugbreak();
    JUMPOUT(0x14030472ALL);
  }
LABEL_40:
  v26 = 1;
  if ( !PoolWithTag )
  {
    ExReleaseFastResource(v36, 0);
    return PoolWithTag;
  }
  if ( !v9 )
  {
    v27 = v35 | 2u;
    if ( (v35 & 0x10) != 0 )
      v28 = RefsAcquireFcbWithPaging((__int64)a1, (__int64)PoolWithTag, 0, v27);
    else
      v28 = RefsAcquireExclusiveFcb(a1, PoolWithTag, 0, v27);
    if ( !v28 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&PoolWithTag->Header.AllocationSize);
      v29 = v36;
      ExReleaseFastResource(v36, 0);
      v26 = 0;
      *v10 |= 4u;
      if ( (a4 & 0x40) == 0 )
      {
        v30 = v35 | 4u;
        if ( (v35 & 0x10) != 0 )
          RefsAcquireFcbWithPaging((__int64)a1, (__int64)PoolWithTag, 0, v30);
        else
          RefsAcquireExclusiveFcb(a1, PoolWithTag, 0, v30);
        v9 = 1;
        *v10 &= ~4u;
        ExAcquireFastResourceExclusive(PoolWithTag->Header.FileContextSupportPointer + 78, 0, 1);
        _InterlockedDecrement((volatile signed __int32 *)&PoolWithTag->Header.AllocationSize);
        ExReleaseFastResource(PoolWithTag->Header.FileContextSupportPointer + 78, 0);
      }
      goto LABEL_53;
    }
    v9 = 1;
  }
  v29 = v36;
LABEL_53:
  if ( v26 )
    ExReleaseFastResource(v29, 0);
  if ( v9 )
    *v10 |= 8u;
  return PoolWithTag;
}

```

## disassembly

```asm
0x140304220  push    rbx
0x140304222  push    rsi
0x140304223  push    rdi
0x140304224  push    r12
0x140304226  push    r13
0x140304228  push    r14
0x14030422a  push    r15
0x14030422c  sub     rsp, 90h
0x140304233  mov     [rsp+0C8h+var_94], r9d
0x140304238  mov     [rsp+0C8h+var_90], r8d
0x14030423d  mov     r13, rdx
0x140304240  mov     r14, rcx
0x140304243  mov     rax, [rsp+0C8h+arg_28]
0x14030424b  xor     ecx, ecx
0x14030424d  mov     [rsp+0C8h+var_88], rcx
0x140304252  mov     rdi, [r14+40h]
0x140304256  mov     [rsp+0C8h+var_60], rdi
0x14030425b  mov     [rsp+0C8h+var_50], rdi
0x140304260  mov     [rsp+0C8h+var_68], ecx
0x140304264  xor     sil, sil
0x140304267  mov     [rsp+0C8h+var_98], sil
0x14030426c  mov     [rsp+0C8h+var_70], rcx
0x140304271  mov     [rsp+0C8h+var_58], rcx
0x140304276  cmp     [rdx], rcx
0x140304279  jnz     short loc_140304286
0x14030427b  cmp     [rdx+8], rcx
0x14030427f  mov     [rsp+0C8h+var_97], 1
0x140304284  jnz     short loc_14030428A
0x140304286  mov     [rsp+0C8h+var_97], cl
0x14030428a  lea     r15, [rsp+0C8h+var_68]
0x14030428f  test    rax, rax
0x140304292  cmovnz  r15, rax
0x140304296  mov     [rsp+0C8h+var_48], r15
0x14030429e  mov     [r15], ecx
0x1403042a1  mov     rbx, rcx
0x1403042a4  mov     [rsp+0C8h+var_88], rcx
0x1403042a9  lea     rax, [rdi+270h]
0x1403042b0  mov     [rsp+0C8h+var_80], rax
0x1403042b5  mov     r8b, 1
0x1403042b8  xor     edx, edx
0x1403042ba  mov     rcx, rax
0x1403042bd  call    cs:__imp_ExAcquireFastResourceExclusive
0x1403042c4  nop     dword ptr [rax+rax+00h]
0x1403042c9  mov     rdi, [rdi+340h]
0x1403042d0  mov     [rsp+0C8h+var_96], bl
0x1403042d4  xor     r12b, r12b
0x1403042d7  test    rdi, rdi
0x1403042da  jz      short loc_140304317
0x1403042dc  nop     dword ptr [rax+00h]
0x1403042e0  mov     rdx, rdi
0x1403042e3  mov     rcx, r13
0x1403042e6  call    RefsFcbTableCompare
0x1403042eb  test    eax, eax
0x1403042ed  jle     short loc_1403042FF
0x1403042ef  mov     rax, [rdi+8]
0x1403042f3  test    rax, rax
0x1403042f6  jnz     short loc_140304309
0x1403042f8  mov     [rsp+0C8h+var_96], 1
0x1403042fd  jmp     short loc_140304317
0x1403042ff  jns     short loc_140304314
0x140304301  mov     rax, [rdi]
0x140304304  test    rax, rax
0x140304307  jz      short loc_14030430E
0x140304309  mov     rdi, rax
0x14030430c  jmp     short loc_1403042E0
0x14030430e  mov     [rsp+0C8h+var_96], bl
0x140304312  jmp     short loc_140304317
0x140304314  mov     r12b, 1
0x140304317  test    r12b, r12b
0x14030431a  jz      short loc_140304329
0x14030431c  mov     rbx, [rdi-8]
0x140304320  mov     [rsp+0C8h+var_88], rbx
0x140304325  or      dword ptr [r15], 1
0x140304329  test    rbx, rbx
0x14030432c  jnz     loc_140304501
0x140304332  mov     [rsp+0C8h+var_78], rbx
0x140304337  test    byte ptr [rsp+0C8h+var_94], 9
0x14030433c  jz      short loc_140304395
0x14030433e  mov     r8d, 66666552h; Tag
0x140304344  mov     r12d, 170h
0x14030434a  mov     edx, r12d; NumberOfBytes
0x14030434d  mov     ecx, 210h; PoolType
0x140304352  call    cs:__imp_ExAllocatePoolWithTag
0x140304359  nop     dword ptr [rax+rax+00h]
0x14030435e  mov     rbx, rax
0x140304361  mov     [rsp+0C8h+var_70], rax
0x140304366  mov     [rsp+0C8h+var_88], rax
0x14030436b  mov     esi, 2
0x140304370  mov     [rsp+0C8h+var_78], rsi
0x140304375  test    byte ptr [rsp+0C8h+var_94], 1
0x14030437a  jz      short loc_1403043EC
0x14030437c  mov     rax, [rsp+0C8h+var_60]
0x140304381  test    dword ptr [rax+18h], 2000000h
0x140304388  jnz     loc_14030464A
0x14030438e  mov     esi, 6
0x140304393  jmp     short loc_1403043E7
0x140304395  cmp     [rsp+0C8h+var_97], 0
0x14030439a  jz      short loc_1403043BC
0x14030439c  lea     rcx, ?RefsFcbIndexLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1403043a3  call    cs:__imp_ExAllocateFromLookasideListEx
0x1403043aa  nop     dword ptr [rax+rax+00h]
0x1403043af  mov     esi, 400h
0x1403043b4  mov     r12d, 5F0h
0x1403043ba  jmp     short loc_1403043DA
0x1403043bc  lea     rcx, ?RefsFcbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1403043c3  call    cs:__imp_ExAllocateFromLookasideListEx
0x1403043ca  nop     dword ptr [rax+rax+00h]
0x1403043cf  mov     esi, 200h
0x1403043d4  mov     r12d, 4E0h
0x1403043da  mov     [rsp+0C8h+var_70], rax
0x1403043df  mov     [rsp+0C8h+var_88], rax
0x1403043e4  mov     rbx, rax
0x1403043e7  mov     [rsp+0C8h+var_78], rsi
0x1403043ec  mov     r8, r12; unsigned __int64
0x1403043ef  mov     r12, [rsp+0C8h+var_60]
0x1403043f4  mov     rdx, r12; struct _VCB *
0x1403043f7  mov     rcx, rbx; this
0x1403043fa  call    ?Initialize@_FCB@@QEAAXAEAU_VCB@@_K@Z; _FCB::Initialize(_VCB &,unsigned __int64)
0x1403043ff  mov     [rbx+8], rsi
0x140304403  mov     qword ptr [rbx+0C8h], 0
0x14030440e  mov     eax, [rsp+0C8h+var_90]
0x140304412  mov     [rsp+0C8h+var_A8], eax
0x140304416  movzx   r9d, [rsp+0C8h+var_97]
0x14030441c  mov     r8, r13
0x14030441f  mov     rdx, rbx
0x140304422  mov     rcx, r14
0x140304425  call    RefsCreateNonpagedFcb
0x14030442a  mov     r9, rax
0x14030442d  mov     [rbx+58h], rax
0x140304431  mov     [rsp+0C8h+var_58], rax
0x140304436  test    rax, rax
0x140304439  jz      loc_1403046B9
0x14030443f  mov     sil, 1
0x140304442  mov     [rsp+0C8h+var_98], sil
0x140304447  mov     rax, [rsp+0C8h+arg_20]
0x14030444f  mov     [rbx+148h], rax
0x140304456  mov     r8d, [rsp+0C8h+var_94]
0x14030445b  test    r8b, 8
0x14030445f  jnz     short loc_14030449E
0x140304461  add     r9, 110h
0x140304468  mov     rcx, [rbx+50h]
0x14030446c  add     rcx, 340h
0x140304473  movzx   r8d, [rsp+0C8h+var_96]
0x140304479  mov     rdx, rdi
0x14030447c  call    cs:__imp_RtlAvlInsertNodeEx
0x140304483  nop     dword ptr [rax+rax+00h]
0x140304488  mov     rax, [rbx+50h]
0x14030448c  inc     dword ptr [rax+348h]
0x140304492  or      qword ptr [rbx+8], 40h
0x140304497  mov     r8d, [rsp+0C8h+var_94]
0x14030449c  jmp     short loc_1403044A6
0x14030449e  or      qword ptr [rbx+8], 1000000h
0x1403044a6  mov     rdx, [rbx+8]
0x1403044aa  mov     rcx, r13; struct _REFS_FILE_REFERENCE *
0x1403044ad  call    ?RefsIsSystemObjectId@@YAEPEBU_REFS_FILE_REFERENCE@@@Z; RefsIsSystemObjectId(_REFS_FILE_REFERENCE const *)
0x1403044b2  test    al, al
0x1403044b4  jz      short loc_1403044BF
0x1403044b6  bts     rdx, 8
0x1403044bb  mov     [rbx+8], rdx
0x1403044bf  test    r8b, 10h
0x1403044c3  jz      short loc_1403044CE
0x1403044c5  bts     rdx, 1Ch
0x1403044ca  mov     [rbx+8], rdx
0x1403044ce  test    r8b, 20h
0x1403044d2  jz      short loc_1403044DD
0x1403044d4  bts     rdx, 15h
0x1403044d9  mov     [rbx+8], rdx
0x1403044dd  mov     eax, [r12+1Ch]
0x1403044e2  test    sil, al
0x1403044e5  jz      short loc_1403044F0
0x1403044e7  bts     rdx, 7
0x1403044ec  mov     [rbx+8], rdx
0x1403044f0  mov     eax, [r12+1Ch]
0x1403044f5  test    al, 40h
0x1403044f7  jz      short loc_140304501
0x1403044f9  or      rdx, 20h
0x1403044fd  mov     [rbx+8], rdx
0x140304501  mov     dil, 1
0x140304504  mov     [rsp+0C8h+var_95], dil
0x140304509  test    rbx, rbx
0x14030450c  jz      loc_140304620
0x140304512  mov     r12d, [rsp+0C8h+var_90]
0x140304517  test    sil, sil
0x14030451a  jnz     loc_1403045FA
0x140304520  mov     r9d, r12d
0x140304523  or      r9d, 2
0x140304527  xor     r8d, r8d
0x14030452a  mov     rdx, rbx
0x14030452d  mov     rcx, r14
0x140304530  test    r12b, 10h
0x140304534  jnz     short loc_140304540
0x140304536  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14030453b  jmp     loc_1403045EA
0x140304540  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140304545  jmp     loc_1403045EA
0x14030454a  test    sil, sil
0x14030454d  jnz     loc_1403045FA
0x140304553  lock inc dword ptr [rbx+18h]
0x140304557  xor     edx, edx
0x140304559  mov     r13, [rsp+0C8h+var_80]
0x14030455e  mov     rcx, r13
0x140304561  call    cs:__imp_ExReleaseFastResource
0x140304568  nop     dword ptr [rax+rax+00h]
0x14030456d  xor     dil, dil
0x140304570  mov     [rsp+0C8h+var_95], dil
0x140304575  or      dword ptr [r15], 4
0x140304579  test    byte ptr [rsp+0C8h+var_94], 40h
0x14030457e  jnz     short loc_1403045FF
0x140304580  mov     r9d, r12d
0x140304583  or      r9d, 4
0x140304587  xor     r8d, r8d
0x14030458a  mov     rdx, rbx
0x14030458d  mov     rcx, r14
0x140304590  test    r12b, 10h
0x140304594  jnz     short loc_14030459D
0x140304596  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14030459b  jmp     short loc_1403045A2
0x14030459d  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x1403045a2  mov     sil, 1
0x1403045a5  mov     [rsp+0C8h+var_98], sil
0x1403045aa  and     dword ptr [r15], 0FFFFFFFBh
0x1403045ae  mov     rcx, [rbx+50h]
0x1403045b2  add     rcx, 270h
0x1403045b9  movzx   r8d, sil
0x1403045bd  xor     edx, edx
0x1403045bf  call    cs:__imp_ExAcquireFastResourceExclusive
0x1403045c6  nop     dword ptr [rax+rax+00h]
0x1403045cb  lock dec dword ptr [rbx+18h]
0x1403045cf  mov     rcx, [rbx+50h]
0x1403045d3  add     rcx, 270h
0x1403045da  xor     edx, edx
0x1403045dc  call    cs:__imp_ExReleaseFastResource
0x1403045e3  nop     dword ptr [rax+rax+00h]
0x1403045e8  jmp     short loc_1403045FF
0x1403045ea  test    al, al
0x1403045ec  jz      loc_14030454A
0x1403045f2  mov     sil, 1
0x1403045f5  mov     [rsp+0C8h+var_98], sil
0x1403045fa  mov     r13, [rsp+0C8h+var_80]
0x1403045ff  test    dil, dil
0x140304602  jz      short loc_140304615
0x140304604  xor     edx, edx
0x140304606  mov     rcx, r13
0x140304609  call    cs:__imp_ExReleaseFastResource
0x140304610  nop     dword ptr [rax+rax+00h]
0x140304615  test    sil, sil
0x140304618  jz      short loc_140304633
0x14030461a  or      dword ptr [r15], 8
0x14030461e  jmp     short loc_140304633
0x140304620  xor     edx, edx
0x140304622  mov     rcx, [rsp+0C8h+var_80]
0x140304627  call    cs:__imp_ExReleaseFastResource
0x14030462e  nop     dword ptr [rax+rax+00h]
0x140304633  mov     rax, rbx
0x140304636  add     rsp, 90h
0x14030463d  pop     r15
0x14030463f  pop     r14
0x140304641  pop     r13
0x140304643  pop     r12
0x140304645  pop     rdi
0x140304646  pop     rsi
0x140304647  pop     rbx
0x140304648  retn
0x14030464a  lea     rax, WPP_GLOBAL_Control
0x140304651  mov     rcx, cs:WPP_GLOBAL_Control
0x140304658  cmp     rcx, rax
0x14030465b  jz      short loc_140304687
0x14030465d  test    dword ptr [rcx+2Ch], 100h
0x140304664  jz      short loc_140304687
0x140304666  cmp     byte ptr [rcx+29h], 4
0x14030466a  jb      short loc_140304687
0x14030466c  mov     edx, 0Eh
0x140304671  mov     r9d, 0C00000A2h
0x140304677  lea     r8, WPP_a4a5732f13c731212091050c8dbbcecd_Traceguids
0x14030467e  mov     rcx, [rcx+18h]
0x140304682  call    WPP_SF_d
0x140304687  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030468e  test    al, al
0x140304690  jz      short loc_1403046AC
0x140304692  mov     r9d, 0C24h; unsigned int
0x140304698  lea     r8, aStrucsupC; "StrucSup.c"
0x14030469f  mov     rdx, r14; struct _IRP_CONTEXT *
0x1403046a2  mov     ecx, 0C00000A2h; Status
0x1403046a7  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1403046ac  mov     edx, 0C00000A2h; int
0x1403046b1  mov     rcx, r14; struct _IRP_CONTEXT *
0x1403046b4  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1403046b9  lea     rax, WPP_GLOBAL_Control
0x1403046c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1403046c7  cmp     rcx, rax
0x1403046ca  jz      short loc_1403046F6
0x1403046cc  test    dword ptr [rcx+2Ch], 100h
0x1403046d3  jz      short loc_1403046F6
0x1403046d5  cmp     byte ptr [rcx+29h], 4
0x1403046d9  jb      short loc_1403046F6
0x1403046db  mov     edx, 0Fh
0x1403046e0  mov     r9d, 0C000009Ah
0x1403046e6  lea     r8, WPP_a4a5732f13c731212091050c8dbbcecd_Traceguids
0x1403046ed  mov     rcx, [rcx+18h]
0x1403046f1  call    WPP_SF_d
  ... truncated ...
```
