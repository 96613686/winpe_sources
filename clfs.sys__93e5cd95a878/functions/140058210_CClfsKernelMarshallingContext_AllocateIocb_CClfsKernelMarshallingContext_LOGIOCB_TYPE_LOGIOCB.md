# CClfsKernelMarshallingContext::AllocateIocb(CClfsKernelMarshallingContext::_LOGIOCB_TYPE,_LOGIOCB * &)

- ea: `0x140058210`
- end: `0x140058659`
- name: `?AllocateIocb@CClfsKernelMarshallingContext@@AEAAJW4_LOGIOCB_TYPE@1@AEAPEAU_LOGIOCB@@@Z`
- size: `1097`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004b0b0`
- `0x1400548c4`
- `0x140055ef0`
- `0x14005935c`
- `0x14005c770`
- `0x140076070`

## callees

- `0x140016d90`
- `0x140018280`
- `0x14005584c`
- `0x1400577c0`
- `0x140058210`
- `0x140058660`
- `0x140058670`
- `0x1400587c0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005852c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005852c`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140058583`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005864b`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140079b06`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140058583`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005864b`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140079b06`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140058272`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400582e2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140058272`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400582e2`
- `ntoskrnl!IoFreeIrp` at `0x1400585de`
- `ntoskrnl!IoFreeIrp` at `0x1400585de`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005847e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400584f6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005847e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400584f6`
- `ntoskrnl!IoAllocateIrp` at `0x14005845b`
- `ntoskrnl!IoAllocateIrp` at `0x14005845b`

## pseudocode

```c
__int64 __fastcall CClfsKernelMarshallingContext::AllocateIocb(CLFS_LSN a1, int a2, CLFS_LSN **a3)
{
  int v6; // esi
  BOOLEAN v7; // r14
  volatile signed __int32 *v8; // r13
  unsigned __int32 v9; // r12d
  CLFS_LSN *v10; // rax
  struct _PAGED_LOOKASIDE_LIST *v11; // rcx
  PVOID v12; // rax
  int v13; // r8d
  CLFS_LSN v14; // rcx
  CLFS_LSN *v15; // rsi
  struct _FILE_OBJECT *v16; // r14
  struct CClfsLogFcbCommon *v17; // r13
  struct _FILE_OBJECT *const v18; // rcx
  PIRP Irp; // rax
  CClfsRequest *v20; // rax
  CClfsRequest *v21; // rax
  struct CClfsLogCcb *v23; // [rsp+C8h] [rbp+20h]

  v6 = 0;
  v7 = 0;
  *a3 = 0;
  if ( a2 != 1 )
  {
    v8 = (volatile signed __int32 *)(a1.ullOffset + 28);
    v9 = _InterlockedIncrement((volatile signed __int32 *)(a1.ullOffset + 28));
    if ( v9 <= *(_DWORD *)(a1.ullOffset + 36) )
      goto LABEL_3;
LABEL_28:
    _InterlockedDecrement(v8);
    v6 = -1072037882;
    goto LABEL_35;
  }
  v8 = (volatile signed __int32 *)(a1.ullOffset + 32);
  v9 = _InterlockedIncrement((volatile signed __int32 *)(a1.ullOffset + 32));
  if ( v9 > *(_DWORD *)(a1.ullOffset + 64) )
  {
    _InterlockedDecrement(v8);
    v7 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1.ullOffset + 144), 1u);
    if ( *(_QWORD *)(a1.ullOffset + 152) != a1.ullOffset + 152 )
    {
      v6 = CClfsKernelMarshallingContext::Flush((CClfsKernelMarshallingContext *)a1.ullOffset);
      if ( v6 < 0 )
        goto LABEL_35;
    }
    v9 = _InterlockedIncrement(v8);
    if ( v9 > *(_DWORD *)(a1.ullOffset + 64) )
      goto LABEL_28;
    ExReleaseResourceForThreadLite(*(PERESOURCE *)(a1.ullOffset + 144), (ERESOURCE_THREAD)KeGetCurrentThread());
  }
LABEL_3:
  v10 = (CLFS_LSN *)ExAllocateFromPagedLookasideList(*(PPAGED_LOOKASIDE_LIST *)(a1.ullOffset + 168));
  *a3 = v10;
  if ( v10 )
  {
    *(_OWORD *)&v10[20].offset.idxRecord = 0;
    (*a3)[1].ullOffset = 0;
    (*a3)[8].ullOffset = 0;
    (*a3)->offset.idxRecord = (a2 == 1) - 1040322545;
    (*a3)[19] = a1;
    _InterlockedIncrement((volatile signed __int32 *)(a1.ullOffset + 24));
    *(_OWORD *)&(*a3)[20].offset.idxRecord = 0;
    v11 = *(struct _PAGED_LOOKASIDE_LIST **)(a1.ullOffset + 176);
    if ( *(_DWORD *)(a1.ullOffset + 16) == 1 )
      v12 = ExAllocateFromPagedLookasideList(v11);
    else
      v12 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v11);
    (*a3)[1].ullOffset = (ULONGLONG)v12;
    v14 = (*a3)[1];
    if ( v14.ullOffset )
    {
      (*a3)[8] = v14;
      if ( a2 != 1 )
        goto LABEL_33;
      v15 = *a3;
      v16 = *(struct _FILE_OBJECT **)(a1.ullOffset + 8);
      v17 = CClfsLogFcbCommon::FcbFromFileObject(v16);
      v23 = CClfsLogFcbCommon::CcbFromFileObject(v18);
      v15[20].ullOffset = 0;
      v15[21].ullOffset = 0;
      Irp = IoAllocateIrp(1, 0);
      v15[20].ullOffset = (ULONGLONG)Irp;
      if ( Irp )
      {
        v20 = (CClfsRequest *)ExAllocateFromNPagedLookasideList(&CClfsRequest::m_laList);
        v21 = v20 ? CClfsRequest::CClfsRequest(v20, v16, v17, v23) : 0LL;
        v15[21].ullOffset = (ULONGLONG)v21;
        if ( v21 )
        {
          v6 = 0;
        }
        else
        {
          IoFreeIrp((PIRP)v15[20].ullOffset);
          v15[20].ullOffset = 0;
          v6 = -1073741670;
        }
      }
      else
      {
        v6 = -1073741670;
      }
      v7 = 0;
      if ( v6 >= 0 )
      {
LABEL_33:
        if ( (*(_BYTE *)(a1.ullOffset + 192) & 1) == 0 || a2 != 1 )
          memset((void *)(*a3)[1].ullOffset, 0, *(unsigned int *)(a1.ullOffset + 44));
        (*a3)->offset.cidContainer = 176;
        (*a3)[16].offset.idxRecord = 0;
        (*a3)[5].offset.idxRecord = 0;
        (*a3)[6].ullOffset = 0;
        (*a3)[9].offset.idxRecord = 0;
        (*a3)[7].ullOffset = 0;
        (*a3)[11] = CLFS_LSN_NULL;
        (*a3)[14] = CLFS_LSN_NULL;
        (*a3)[15] = CLFS_LSN_INVALID;
        (*a3)[2].offset.cidContainer = 0;
        (*a3)[4].ullOffset = 0;
        (*a3)[2].offset.idxRecord = 0;
        (*a3)[3].offset.idxRecord = 0;
        v7 = 0;
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slqqDddd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            12,
            v13,
            (unsigned int)"CClfsKernelMarshallingContext::AllocateIocb",
            93,
            a1.offset.idxRecord,
            (char)*a3,
            a2,
            v9,
            *(_DWORD *)(a1.ullOffset + 40),
            *(_DWORD *)(a1.ullOffset + 184));
        }
      }
    }
    else
    {
      v6 = -1073741670;
      v7 = 0;
    }
  }
  else
  {
    _InterlockedDecrement(v8);
    v6 = -1073741670;
    v7 = 0;
  }
LABEL_35:
  if ( v6 < 0 && *a3 )
  {
    CClfsKernelMarshallingContext::DeallocateIocb((CClfsKernelMarshallingContext *)a1.ullOffset, *a3);
    *a3 = 0;
  }
  if ( v7 )
    ExReleaseResourceForThreadLite(*(PERESOURCE *)(a1.ullOffset + 144), (ERESOURCE_THREAD)KeGetCurrentThread());
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140058210  mov     [rsp+arg_10], r8
0x140058215  mov     [rsp+arg_0], rcx
0x14005821a  push    rbx
0x14005821b  push    rsi
0x14005821c  push    rdi
0x14005821d  push    r12
0x14005821f  push    r13
0x140058221  push    r14
0x140058223  push    r15
0x140058225  sub     rsp, 70h
0x140058229  mov     rbx, r8
0x14005822c  mov     r15d, edx
0x14005822f  mov     rdi, rcx
0x140058232  xor     eax, eax
0x140058234  mov     esi, eax
0x140058236  mov     [rsp+0A8h+var_44], eax
0x14005823a  xor     r14b, r14b
0x14005823d  mov     [rsp+0A8h+var_48], r14b
0x140058242  mov     [r8], rax
0x140058245  mov     r12d, 1
0x14005824b  cmp     edx, r12d
0x14005824e  jz      loc_140058507
0x140058254  lea     r13, [rcx+1Ch]
0x140058258  lock xadd [r13+0], r12d
0x14005825e  inc     r12d
0x140058261  cmp     r12d, [rcx+24h]
0x140058265  ja      loc_140058599
0x14005826b  mov     rcx, [rdi+0A8h]; Lookaside
0x140058272  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140058279  nop     dword ptr [rax+rax+00h]
0x14005827e  mov     [rbx], rax
0x140058281  test    rax, rax
0x140058284  jz      loc_1400584D8
0x14005828a  xorps   xmm0, xmm0
0x14005828d  movups  xmmword ptr [rax+0A0h], xmm0
0x140058294  mov     rax, [rbx]
0x140058297  xor     r13d, r13d
0x14005829a  mov     [rax+8], r13
0x14005829e  mov     rax, [rbx]
0x1400582a1  mov     [rax+40h], r13
0x1400582a5  mov     rcx, [rbx]
0x1400582a8  mov     eax, r13d
0x1400582ab  cmp     r15d, 1
0x1400582af  setz    al
0x1400582b2  add     eax, 0C1FDF00Fh
0x1400582b7  mov     [rcx], eax
0x1400582b9  mov     rax, [rbx]
0x1400582bc  mov     [rax+98h], rdi
0x1400582c3  lock inc dword ptr [rdi+18h]
0x1400582c7  mov     rax, [rbx]
0x1400582ca  movups  xmmword ptr [rax+0A0h], xmm0
0x1400582d1  mov     rcx, [rdi+0B0h]; Lookaside
0x1400582d8  cmp     dword ptr [rdi+10h], 1
0x1400582dc  jnz     loc_1400584F6
0x1400582e2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400582e9  nop     dword ptr [rax+rax+00h]
0x1400582ee  mov     rcx, [rbx]
0x1400582f1  mov     [rcx+8], rax
0x1400582f5  mov     rax, [rbx]
0x1400582f8  mov     rcx, [rax+8]
0x1400582fc  test    rcx, rcx
0x1400582ff  jz      loc_1400585AC
0x140058305  mov     [rax+40h], rcx
0x140058309  cmp     r15d, 1
0x14005830d  jz      loc_140058428
0x140058313  test    byte ptr [rdi+0C0h], 1
0x14005831a  jnz     loc_1400585FB
0x140058320  mov     r8d, [rdi+2Ch]; Size
0x140058324  mov     rcx, [rbx]
0x140058327  xor     edx, edx; Val
0x140058329  mov     rcx, [rcx+8]; void *
0x14005832d  call    memset
0x140058332  mov     rax, [rbx]
0x140058335  mov     dword ptr [rax+4], 0B0h
0x14005833c  mov     rax, [rbx]
0x14005833f  mov     [rax+80h], r13d
0x140058346  mov     rax, [rbx]
0x140058349  mov     [rax+28h], r13d
0x14005834d  mov     rax, [rbx]
0x140058350  mov     [rax+30h], r13
0x140058354  mov     rax, [rbx]
0x140058357  mov     [rax+48h], r13d
0x14005835b  mov     rax, [rbx]
0x14005835e  mov     [rax+38h], r13
0x140058362  mov     rcx, [rbx]
0x140058365  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x14005836c  mov     [rcx+58h], rax
0x140058370  mov     rcx, [rbx]
0x140058373  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x14005837a  mov     [rcx+70h], rax
0x14005837e  mov     rcx, [rbx]
0x140058381  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140058388  mov     [rcx+78h], rax
0x14005838c  mov     rax, [rbx]
0x14005838f  mov     [rax+14h], r13d
0x140058393  mov     rax, [rbx]
0x140058396  mov     [rax+20h], r13
0x14005839a  mov     rax, [rbx]
0x14005839d  mov     [rax+10h], r13d
0x1400583a1  mov     rax, [rbx]
0x1400583a4  mov     [rax+18h], r13d
0x1400583a8  xor     r14b, r14b
0x1400583ab  mov     [rsp+0A8h+var_48], r14b
0x1400583b0  lea     rax, WPP_GLOBAL_Control
0x1400583b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400583be  cmp     rcx, rax
0x1400583c1  jz      loc_14005860A
0x1400583c7  mov     [rsp+0A8h+var_48], r14b
0x1400583cc  mov     eax, [rcx+2Ch]
0x1400583cf  bt      eax, 1Ah
0x1400583d3  jnb     loc_14005860A
0x1400583d9  mov     edx, 0Ch
0x1400583de  mov     eax, [rdi+0B8h]
0x1400583e4  mov     [rsp+0A8h+var_58], eax
0x1400583e8  mov     eax, [rdi+28h]
0x1400583eb  mov     [rsp+0A8h+var_60], eax
0x1400583ef  mov     [rsp+0A8h+var_68], r12d
0x1400583f4  mov     [rsp+0A8h+var_70], r15d
0x1400583f9  mov     rax, [rbx]
0x1400583fc  mov     [rsp+0A8h+var_78], rax
0x140058401  mov     [rsp+0A8h+var_80], rdi
0x140058406  mov     [rsp+0A8h+var_88], 55Dh
0x14005840e  lea     r9, aCclfskernelmar_2; "CClfsKernelMarshallingContext::Allocate"...
0x140058415  mov     rcx, [rcx+18h]
0x140058419  call    WPP_SF_slqqDddd
0x14005841e  mov     [rsp+0A8h+var_48], r14b
0x140058423  jmp     loc_14005860A
0x140058428  mov     rsi, [rbx]
0x14005842b  mov     r14, [rdi+8]
0x14005842f  mov     rcx, r14; struct _FILE_OBJECT *
0x140058432  call    ?FcbFromFileObject@CClfsLogFcbCommon@@SAPEAV1@QEAU_FILE_OBJECT@@@Z; CClfsLogFcbCommon::FcbFromFileObject(_FILE_OBJECT * const)
0x140058437  mov     r13, rax
0x14005843a  call    ?CcbFromFileObject@CClfsLogFcbCommon@@SAPEAVCClfsLogCcb@@QEAU_FILE_OBJECT@@@Z; CClfsLogFcbCommon::CcbFromFileObject(_FILE_OBJECT * const)
0x14005843f  mov     [rsp+0A8h+arg_18], rax
0x140058447  xor     eax, eax
0x140058449  mov     [rsi+0A0h], rax
0x140058450  mov     [rsi+0A8h], rax
0x140058457  xor     edx, edx; ChargeQuota
0x140058459  mov     cl, 1; StackSize
0x14005845b  call    cs:__imp_IoAllocateIrp
0x140058462  nop     dword ptr [rax+rax+00h]
0x140058467  mov     [rsi+0A0h], rax
0x14005846e  test    rax, rax
0x140058471  jz      loc_1400585BF
0x140058477  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14005847e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140058485  nop     dword ptr [rax+rax+00h]
0x14005848a  test    rax, rax
0x14005848d  jz      loc_1400585CC
0x140058493  mov     r9, [rsp+0A8h+arg_18]; struct CClfsLogCcb *
0x14005849b  mov     r8, r13; struct CClfsLogFcbCommon *
0x14005849e  mov     rdx, r14; struct _FILE_OBJECT *
0x1400584a1  mov     rcx, rax; this
0x1400584a4  call    ??0CClfsRequest@@QEAA@PEAU_FILE_OBJECT@@PEAVCClfsLogFcbCommon@@PEAVCClfsLogCcb@@@Z; CClfsRequest::CClfsRequest(_FILE_OBJECT *,CClfsLogFcbCommon *,CClfsLogCcb *)
0x1400584a9  xor     r13d, r13d
0x1400584ac  mov     [rsi+0A8h], rax
0x1400584b3  test    rax, rax
0x1400584b6  jz      loc_1400585D7
0x1400584bc  mov     esi, r13d
0x1400584bf  mov     [rsp+0A8h+var_44], esi
0x1400584c3  xor     r14b, r14b
0x1400584c6  mov     [rsp+0A8h+var_48], r14b
0x1400584cb  test    esi, esi
0x1400584cd  jns     loc_140058313
0x1400584d3  jmp     loc_14005860A
0x1400584d8  lock dec dword ptr [r13+0]
0x1400584dd  mov     esi, 0C000009Ah
0x1400584e2  mov     [rsp+0A8h+var_44], esi
0x1400584e6  xor     r14b, r14b
0x1400584e9  mov     [rsp+0A8h+var_48], r14b
0x1400584ee  xor     r13d, r13d
0x1400584f1  jmp     loc_14005860A
0x1400584f6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400584fd  nop     dword ptr [rax+rax+00h]
0x140058502  jmp     loc_1400582EE
0x140058507  lea     r13, [rcx+20h]
0x14005850b  lock xadd [r13+0], r12d
0x140058511  inc     r12d
0x140058514  cmp     r12d, [rcx+40h]
0x140058518  jbe     loc_14005826B
0x14005851e  lock dec dword ptr [r13+0]
0x140058523  mov     dl, 1; Wait
0x140058525  mov     rcx, [rcx+90h]; Resource
0x14005852c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140058533  nop     dword ptr [rax+rax+00h]
0x140058538  movzx   r14d, al
0x14005853c  mov     [rsp+0A8h+var_48], al
0x140058540  lea     rax, [rdi+98h]
0x140058547  cmp     [rax], rax
0x14005854a  jz      short loc_14005855E
0x14005854c  mov     rcx, rdi; this
0x14005854f  call    ?Flush@CClfsKernelMarshallingContext@@QEAAJXZ; CClfsKernelMarshallingContext::Flush(void)
0x140058554  mov     esi, eax
0x140058556  mov     [rsp+0A8h+var_44], eax
0x14005855a  test    eax, eax
0x14005855c  js      short loc_1400584EE
0x14005855e  mov     r12d, 1
0x140058564  lock xadd [r13+0], r12d
0x14005856a  inc     r12d
0x14005856d  cmp     r12d, [rdi+40h]
0x140058571  ja      short loc_140058599
0x140058573  mov     rdx, gs:188h; ResourceThreadId
0x14005857c  mov     rcx, [rdi+90h]; Resource
0x140058583  call    cs:__imp_ExReleaseResourceForThreadLite
0x14005858a  nop     dword ptr [rax+rax+00h]
0x14005858f  mov     [rsp+0A8h+var_48], 0
0x140058594  jmp     loc_14005826B
0x140058599  lock dec dword ptr [r13+0]
0x14005859e  mov     esi, 0C01A0006h
0x1400585a3  mov     [rsp+0A8h+var_44], esi
0x1400585a7  jmp     loc_1400584EE
0x1400585ac  mov     esi, 0C000009Ah
0x1400585b1  mov     [rsp+0A8h+var_44], esi
0x1400585b5  xor     r14b, r14b
0x1400585b8  mov     [rsp+0A8h+var_48], r14b
0x1400585bd  jmp     short loc_14005860A
0x1400585bf  mov     esi, 0C000009Ah
0x1400585c4  xor     r13d, r13d
0x1400585c7  jmp     loc_1400584BF
0x1400585cc  xor     r13d, r13d
0x1400585cf  mov     eax, r13d
0x1400585d2  jmp     loc_1400584AC
0x1400585d7  mov     rcx, [rsi+0A0h]; Irp
0x1400585de  call    cs:__imp_IoFreeIrp
0x1400585e5  nop     dword ptr [rax+rax+00h]
0x1400585ea  mov     [rsi+0A0h], r13
0x1400585f1  mov     esi, 0C000009Ah
0x1400585f6  jmp     loc_1400584BF
0x1400585fb  cmp     r15d, 1
0x1400585ff  jz      loc_140058332
0x140058605  jmp     loc_140058320
0x14005860a  test    esi, esi
0x14005860c  js      short loc_140058626
0x14005860e  test    r14b, r14b
0x140058611  jnz     short loc_14005863B
0x140058613  mov     eax, esi
0x140058615  add     rsp, 70h
0x140058619  pop     r15
0x14005861b  pop     r14
0x14005861d  pop     r13
0x14005861f  pop     r12
0x140058621  pop     rdi
0x140058622  pop     rsi
0x140058623  pop     rbx
0x140058624  retn
0x140058626  mov     rdx, [rbx]; Entry
0x140058629  test    rdx, rdx
0x14005862c  jz      short loc_14005860E
0x14005862e  mov     rcx, rdi; this
0x140058631  call    ?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)
0x140058636  mov     [rbx], r13
0x140058639  jmp     short loc_14005860E
0x14005863b  mov     rdx, gs:188h; ResourceThreadId
0x140058644  mov     rcx, [rdi+90h]; Resource
0x14005864b  call    cs:__imp_ExReleaseResourceForThreadLite
0x140058652  nop     dword ptr [rax+rax+00h]
0x140058657  jmp     short loc_140058613
0x140079ab0  push    rbx
0x140079ab2  push    rbp
0x140079ab3  push    rdi
0x140079ab4  sub     rsp, 60h
0x140079ab8  mov     rbp, rdx
0x140079abb  cmp     dword ptr [rbp+64h], 0
0x140079abf  jge     short loc_140079AE9
0x140079ac1  mov     rbx, [rbp+0C0h]
0x140079ac8  cmp     qword ptr [rbx], 0
0x140079acc  jz      short loc_140079AE9
0x140079ace  mov     rdx, [rbx]; Entry
0x140079ad1  mov     rdi, [rbp+0B0h]
0x140079ad8  mov     rcx, rdi; this
0x140079adb  call    ?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)
0x140079ae0  mov     qword ptr [rbx], 0
0x140079ae7  jmp     short loc_140079AF0
0x140079ae9  mov     rdi, [rbp+0B0h]
0x140079af0  cmp     byte ptr [rbp+60h], 0
0x140079af4  jz      short loc_140079B16
0x140079af6  mov     rdx, gs:188h; ResourceThreadId
0x140079aff  mov     rcx, [rdi+90h]; Resource
0x140079b06  call    cs:__imp_ExReleaseResourceForThreadLite
0x140079b0d  nop     dword ptr [rax+rax+00h]
0x140079b12  mov     byte ptr [rbp+60h], 0
0x140079b16  add     rsp, 60h
0x140079b1a  pop     rdi
0x140079b1b  pop     rbp
0x140079b1c  pop     rbx
0x140079b1d  retn
```
