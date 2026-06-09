# CClfsKernelMarshallingContext::Initialize(_FILE_OBJECT *,_POOL_TYPE,void * (*)(_POOL_TYPE,unsigned __int64,ulong),void (*)(void *),ulong,ulong,ulong,ulong,unsigned __int64)

- ea: `0x1400705e8`
- end: `0x140070a30`
- name: `?Initialize@CClfsKernelMarshallingContext@@QEAAJPEAU_FILE_OBJECT@@W4_POOL_TYPE@@P6APEAX1_KK@ZP6AXPEAX@ZKKKK2@Z`
- size: `1096`
- prototype: `int(CClfsKernelMarshallingContext *__hidden this, struct _FILE_OBJECT *, enum _POOL_TYPE, void *(*)(enum _POOL_TYPE, unsigned __int64, unsigned int), void (*)(void *), unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140070224`

## callees

- `0x140017e40`
- `0x140018280`
- `0x140057980`
- `0x140059b80`
- `0x1400705e8`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1400708b2`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400708e5`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400708b2`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400708e5`
- `ntoskrnl!ObfReferenceObject` at `0x14007071f`
- `ntoskrnl!ObfReferenceObject` at `0x14007071f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140070a15`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140070a15`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140070825`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14007087a`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140070825`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14007087a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400707e6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007083a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140070893`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400708c6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400709d9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400707e6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007083a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140070893`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400708c6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400709d9`

## pseudocode

```c
NTSTATUS __fastcall CClfsKernelMarshallingContext::Initialize(
        union _CLS_LSN *this,
        struct _FILE_OBJECT *a2,
        CLFS_RECORD_INDEX a3,
        void *(*a4)(enum _POOL_TYPE, unsigned __int64, unsigned int),
        void (*Free)(void *),
        unsigned int a6,
        CLFS_CONTAINER_ID a7,
        CLFS_RECORD_INDEX a8,
        unsigned int a9,
        unsigned __int64 a10)
{
  NTSTATUS result; // eax
  unsigned int v15; // r8d
  unsigned int v16; // ecx
  unsigned int v17; // edx
  unsigned int v18; // edi
  bool v19; // zf
  CLFS_CONTAINER_ID cidContainer; // edx
  unsigned int v21; // ecx
  CLFS_CONTAINER_ID v22; // r8d
  unsigned int v23; // ecx
  CLFS_RECORD_INDEX idxRecord; // eax
  struct _PAGED_LOOKASIDE_LIST *PoolWithTag; // rax
  struct _PAGED_LOOKASIDE_LIST *v26; // rax
  struct _ERESOURCE *v27; // rax
  struct _ERESOURCE *v28; // rax
  CLFS_CONTAINER_ID v29; // ecx
  unsigned int v30; // eax
  union _CLS_LSN v31; // rcx
  union _CLS_LSN v32; // r14
  struct _NPAGED_LOOKASIDE_LIST *v33; // rax
  char v34; // [rsp+60h] [rbp-A0h]
  struct _IRP *v35; // [rsp+68h] [rbp-98h]
  ULONG pcbInfoBuffer; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v37[3]; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  _QWORD pinfoBuffer[16]; // [rsp+90h] [rbp-70h] BYREF

  memset(pinfoBuffer, 0, 0x78u);
  *(_QWORD *)&v37[1] = 0;
  pcbInfoBuffer = 120;
  result = ClfsQueryLogFileInformation(a2, ClfsLogBasicInformation, 0, 0, pinfoBuffer, &pcbInfoBuffer);
  if ( result >= 0 )
  {
    if ( !LODWORD(pinfoBuffer[5]) )
      return -1072037853;
    v15 = HIDWORD(pinfoBuffer[7]);
    v16 = a9;
    v17 = a9 % HIDWORD(pinfoBuffer[7]);
    this[8].offset.cidContainer = HIDWORD(pinfoBuffer[7]);
    if ( v17 )
      return -1073741811;
    if ( v15 > a9 )
      v16 = v15;
    this[8].offset.cidContainer = v16;
    if ( v16 )
      v18 = -v16 & (v16 + a6 - 1);
    else
      v18 = 0;
    this[2].offset.idxRecord = a3;
    if ( !a3 )
      this[2].offset.idxRecord = 512;
    this[4].offset.cidContainer = a7;
    this[8].offset.idxRecord = a8;
    this[24].ullOffset = a10;
    if ( v18 + 152 < v18 )
      goto LABEL_11;
    this[5].offset.cidContainer = v18 + 152;
    this[1].ullOffset = (ULONGLONG)a2;
    ObfReferenceObject(a2);
    v19 = this[8].offset.idxRecord == 0;
    this[10].ullOffset = 0;
    if ( v19 )
    {
LABEL_15:
      cidContainer = this[8].offset.cidContainer;
      this[9] = (union _CLS_LSN)pinfoBuffer[4];
      this[2].offset.cidContainer = HIDWORD(pinfoBuffer[6]);
      this[13] = (union _CLS_LSN)pinfoBuffer[11];
      this[15] = (union _CLS_LSN)pinfoBuffer[12];
      if ( cidContainer )
        v21 = -cidContainer & (cidContainer + this[5].offset.cidContainer - 1);
      else
        v21 = 0;
      if ( v21 < this[5].offset.cidContainer )
        return -1073741306;
      v22 = v18 + 2 * ((v21 >> 9) + 76);
      if ( v22 < v18 )
        goto LABEL_11;
      this[5].offset.cidContainer = v22;
      if ( cidContainer )
        v23 = ~(cidContainer - 1) & (cidContainer - 1 + v22);
      else
        v23 = 0;
      if ( v23 < v22 )
        return -1073741306;
      if ( v23 + 40 < v23 )
      {
LABEL_11:
        this[5].offset.cidContainer = -1;
        return -1073741306;
      }
      this[5].offset.cidContainer = v23 + 40;
      idxRecord = this[2].offset.idxRecord;
      this[6].offset.idxRecord = v23;
      if ( idxRecord == 1 )
      {
        PoolWithTag = (struct _PAGED_LOOKASIDE_LIST *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x80u, 0x73666C43u);
        this[22].ullOffset = (ULONGLONG)PoolWithTag;
        if ( PoolWithTag )
        {
          ExInitializePagedLookasideList(PoolWithTag, a4, Free, 0, this[5].offset.cidContainer, 0x49666C43u, 0);
LABEL_26:
          v26 = (struct _PAGED_LOOKASIDE_LIST *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x80u, 0x73666C43u);
          this[21].ullOffset = (ULONGLONG)v26;
          if ( v26 )
          {
            ExInitializePagedLookasideList(v26, a4, Free, 0, 0xB0u, 0x48666C43u, 0);
            v27 = (struct _ERESOURCE *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x68u, 0x73666C43u);
            this[17].ullOffset = (ULONGLONG)v27;
            if ( v27 )
            {
              ExInitializeResourceLite(v27);
              v28 = (struct _ERESOURCE *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x68u, 0x73666C43u);
              this[18].ullOffset = (ULONGLONG)v28;
              if ( v28 )
              {
                ExInitializeResourceLite(v28);
                return 0;
              }
            }
          }
          return -1073741670;
        }
        return -1073741670;
      }
      if ( idxRecord == 512 )
      {
        v33 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x80u, 0x73666C43u);
        this[22].ullOffset = (ULONGLONG)v33;
        if ( v33 )
        {
          ExInitializeNPagedLookasideList(v33, a4, Free, 0x200u, this[5].offset.cidContainer, 0x49666C43u, 0);
          goto LABEL_26;
        }
        return -1073741670;
      }
      return -1073741811;
    }
    v29 = this[8].offset.cidContainer;
    if ( v29 )
      v30 = -v29 & (v29 + this[5].offset.cidContainer + 983);
    else
      v30 = 0;
    v31 = this[1];
    v32.ullOffset = v30;
    v38 = v30;
    result = ClfsReserveAndAppendLogInternal(
               v31.offset.idxRecord,
               0,
               0,
               0,
               &v38,
               (__int64 *)&this[10],
               (__int64 *)&v37[1],
               0,
               0,
               (__int64)v37,
               this + 13,
               0,
               v34,
               v35);
    if ( result >= 0 )
    {
      this[10] = v32;
      goto LABEL_15;
    }
    if ( result == -1072037859 || result == -1073741790 )
      goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x1400705e8  push    rbp
0x1400705ea  push    rbx
0x1400705eb  push    rsi
0x1400705ec  push    rdi
0x1400705ed  push    r12
0x1400705ef  push    r14
0x1400705f1  push    r15
0x1400705f3  lea     rbp, [rsp-20h]
0x1400705f8  sub     rsp, 120h
0x1400705ff  mov     rax, cs:__security_cookie
0x140070606  xor     rax, rsp
0x140070609  mov     [rbp+50h+var_40], rax
0x14007060d  mov     r12, [rbp+50h+Free]
0x140070614  mov     esi, r8d
0x140070617  mov     r14, rdx
0x14007061a  mov     rbx, rcx
0x14007061d  mov     edi, 78h ; 'x'
0x140070622  lea     rcx, [rbp+50h+var_C0]; void *
0x140070626  mov     r8d, edi; Size
0x140070629  xor     edx, edx; Val
0x14007062b  mov     r15, r9
0x14007062e  call    memset
0x140070633  lea     rax, [rsp+150h+var_E0]
0x140070638  mov     qword ptr [rsp+150h+var_DC+4], 0
0x140070641  mov     [rsp+150h+pcbInfoBuffer], rax; pcbInfoBuffer
0x140070646  xor     r9d, r9d; cbinfoInputBuffer
0x140070649  lea     rax, [rbp+50h+var_C0]
0x14007064d  mov     [rsp+150h+var_E0], edi
0x140070651  xor     r8d, r8d; pinfoInputBuffer
0x140070654  mov     [rsp+150h+pinfoBuffer], rax; pinfoBuffer
0x140070659  xor     edx, edx; eInformationClass
0x14007065b  mov     rcx, r14; plfoLog
0x14007065e  call    ClfsQueryLogFileInformation
0x140070663  test    eax, eax
0x140070665  js      loc_1400706F6
0x14007066b  cmp     [rbp+50h+var_98], 0
0x14007066f  jz      loc_14007099D
0x140070675  mov     r8d, [rbp+50h+var_84]
0x140070679  xor     edx, edx
0x14007067b  mov     ecx, [rbp+50h+arg_40]
0x140070681  mov     eax, ecx
0x140070683  div     r8d
0x140070686  mov     [rbx+44h], r8d
0x14007068a  test    edx, edx
0x14007068c  jnz     loc_140070A26
0x140070692  cmp     r8d, ecx
0x140070695  cmova   ecx, r8d
0x140070699  mov     [rbx+44h], ecx
0x14007069c  test    ecx, ecx
0x14007069e  jz      loc_140070984
0x1400706a4  mov     edi, [rbp+50h+arg_28]
0x1400706aa  dec     edi
0x1400706ac  add     edi, ecx
0x1400706ae  neg     ecx
0x1400706b0  and     edi, ecx
0x1400706b2  mov     [rbx+10h], esi
0x1400706b5  test    esi, esi
0x1400706b7  jnz     short loc_1400706C0
0x1400706b9  mov     dword ptr [rbx+10h], 200h
0x1400706c0  mov     eax, [rbp+50h+arg_30]
0x1400706c6  mov     [rbx+24h], eax
0x1400706c9  mov     eax, [rbp+50h+arg_38]
0x1400706cf  mov     [rbx+40h], eax
0x1400706d2  mov     rax, [rbp+50h+arg_48]
0x1400706d9  mov     [rbx+0C0h], rax
0x1400706e0  lea     eax, [rdi+98h]
0x1400706e6  cmp     eax, edi
0x1400706e8  jnb     short loc_140070715
0x1400706ea  mov     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x1400706f1  mov     eax, 0C0000206h
0x1400706f6  mov     rcx, [rbp+50h+var_40]
0x1400706fa  xor     rcx, rsp; StackCookie
0x1400706fd  call    __security_check_cookie
0x140070702  add     rsp, 120h
0x140070709  pop     r15
0x14007070b  pop     r14
0x14007070d  pop     r12
0x14007070f  pop     rdi
0x140070710  pop     rsi
0x140070711  pop     rbx
0x140070712  pop     rbp
0x140070713  retn
0x140070715  mov     rcx, r14; Object
0x140070718  mov     [rbx+2Ch], eax
0x14007071b  mov     [rbx+8], r14
0x14007071f  call    cs:__imp_ObfReferenceObject
0x140070726  nop     dword ptr [rax+rax+00h]
0x14007072b  cmp     dword ptr [rbx+40h], 0
0x14007072f  lea     rsi, [rbx+50h]
0x140070733  mov     qword ptr [rsi], 0
0x14007073a  ja      loc_1400708F8
0x140070740  mov     rax, [rbp+50h+var_A0]
0x140070744  mov     edx, [rbx+44h]
0x140070747  mov     [rbx+48h], rax
0x14007074b  mov     eax, [rbp+50h+var_8C]
0x14007074e  mov     [rbx+14h], eax
0x140070751  mov     rax, [rbp+50h+var_68]
0x140070755  mov     [rbx+68h], rax
0x140070759  mov     rax, [rbp+50h+var_60]
0x14007075d  mov     [rbx+78h], rax
0x140070761  test    edx, edx
0x140070763  jz      loc_14007098F
0x140070769  mov     ecx, [rbx+2Ch]
0x14007076c  mov     eax, edx
0x14007076e  dec     ecx
0x140070770  neg     eax
0x140070772  add     ecx, edx
0x140070774  and     ecx, eax
0x140070776  cmp     ecx, [rbx+2Ch]
0x140070779  jb      loc_1400706F1
0x14007077f  shr     ecx, 9
0x140070782  lea     r8d, [rcx+4Ch]
0x140070786  lea     r8d, [rdi+r8*2]
0x14007078a  cmp     r8d, edi
0x14007078d  jb      loc_1400706EA
0x140070793  mov     [rbx+2Ch], r8d
0x140070797  test    edx, edx
0x140070799  jz      loc_140070996
0x14007079f  lea     eax, [rdx-1]
0x1400707a2  lea     ecx, [rax+r8]
0x1400707a6  not     eax
0x1400707a8  and     ecx, eax
0x1400707aa  cmp     ecx, r8d
0x1400707ad  jb      loc_1400706F1
0x1400707b3  lea     eax, [rcx+28h]
0x1400707b6  cmp     eax, ecx
0x1400707b8  jb      loc_1400706EA
0x1400707be  mov     [rbx+2Ch], eax
0x1400707c1  mov     r14d, 200h
0x1400707c7  mov     eax, [rbx+10h]
0x1400707ca  mov     [rbx+30h], ecx
0x1400707cd  cmp     eax, 1
0x1400707d0  jnz     loc_1400709C2
0x1400707d6  lea     esi, [rax+7Fh]
0x1400707d9  mov     edi, 73666C43h
0x1400707de  mov     r8d, edi; Tag
0x1400707e1  mov     edx, esi; NumberOfBytes
0x1400707e3  mov     ecx, r14d; PoolType
0x1400707e6  call    cs:__imp_ExAllocatePoolWithTag
0x1400707ed  nop     dword ptr [rax+rax+00h]
0x1400707f2  mov     [rbx+0B0h], rax
0x1400707f9  test    rax, rax
0x1400707fc  jz      loc_14007097A
0x140070802  mov     edx, [rbx+2Ch]
0x140070805  xor     ecx, ecx
0x140070807  mov     [rsp+150h+Depth], cx; Depth
0x14007080c  xor     r9d, r9d; Flags
0x14007080f  mov     dword ptr [rsp+150h+pcbInfoBuffer], 49666C43h; Tag
0x140070817  mov     r8, r12; Free
0x14007081a  mov     [rsp+150h+pinfoBuffer], rdx; Size
0x14007081f  mov     rcx, rax; Lookaside
0x140070822  mov     rdx, r15; Allocate
0x140070825  call    cs:__imp_ExInitializePagedLookasideList
0x14007082c  nop     dword ptr [rax+rax+00h]
0x140070831  mov     r8d, edi; Tag
0x140070834  mov     rdx, rsi; NumberOfBytes
0x140070837  mov     ecx, r14d; PoolType
0x14007083a  call    cs:__imp_ExAllocatePoolWithTag
0x140070841  nop     dword ptr [rax+rax+00h]
0x140070846  mov     [rbx+0A8h], rax
0x14007084d  test    rax, rax
0x140070850  jz      loc_14007097A
0x140070856  xor     ecx, ecx
0x140070858  xor     r9d, r9d; Flags
0x14007085b  mov     [rsp+150h+Depth], cx; Depth
0x140070860  mov     r8, r12; Free
0x140070863  mov     dword ptr [rsp+150h+pcbInfoBuffer], 48666C43h; Tag
0x14007086b  mov     rcx, rax; Lookaside
0x14007086e  mov     rdx, r15; Allocate
0x140070871  mov     [rsp+150h+pinfoBuffer], 0B0h; Size
0x14007087a  call    cs:__imp_ExInitializePagedLookasideList
0x140070881  nop     dword ptr [rax+rax+00h]
0x140070886  mov     esi, 68h ; 'h'
0x14007088b  mov     r8d, edi; Tag
0x14007088e  mov     edx, esi; NumberOfBytes
0x140070890  mov     ecx, r14d; PoolType
0x140070893  call    cs:__imp_ExAllocatePoolWithTag
0x14007089a  nop     dword ptr [rax+rax+00h]
0x14007089f  mov     [rbx+88h], rax
0x1400708a6  test    rax, rax
0x1400708a9  jz      loc_14007097A
0x1400708af  mov     rcx, rax; Resource
0x1400708b2  call    cs:__imp_ExInitializeResourceLite
0x1400708b9  nop     dword ptr [rax+rax+00h]
0x1400708be  mov     r8d, edi; Tag
0x1400708c1  mov     edx, esi; NumberOfBytes
0x1400708c3  mov     ecx, r14d; PoolType
0x1400708c6  call    cs:__imp_ExAllocatePoolWithTag
0x1400708cd  nop     dword ptr [rax+rax+00h]
0x1400708d2  mov     [rbx+90h], rax
0x1400708d9  test    rax, rax
0x1400708dc  jz      loc_14007097A
0x1400708e2  mov     rcx, rax; Resource
0x1400708e5  call    cs:__imp_ExInitializeResourceLite
0x1400708ec  nop     dword ptr [rax+rax+00h]
0x1400708f1  xor     eax, eax
0x1400708f3  jmp     loc_1400706F6
0x1400708f8  mov     ecx, [rbx+44h]
0x1400708fb  test    ecx, ecx
0x1400708fd  jz      loc_14007098B
0x140070903  mov     eax, [rbx+2Ch]
0x140070906  add     eax, 3D7h
0x14007090b  add     eax, ecx
0x14007090d  neg     ecx
0x14007090f  and     eax, ecx
0x140070911  mov     rcx, [rbx+8]; int
0x140070915  xor     r9d, r9d; int
0x140070918  mov     [rsp+150h+var_F8], 0; union _CLS_LSN *
0x140070921  xor     r8d, r8d; int
0x140070924  mov     r14d, eax
0x140070927  xor     edx, edx; int
0x140070929  lea     rax, [rbx+68h]
0x14007092d  mov     [rbp+50h+var_D0], r14
0x140070931  mov     [rsp+150h+var_100], rax; union _CLS_LSN *
0x140070936  lea     rax, [rsp+150h+var_DC]
0x14007093b  mov     [rsp+150h+var_108], rax; __int64
0x140070940  lea     rax, [rsp+150h+var_DC+4]
0x140070945  mov     [rsp+150h+var_110], 0; union _CLS_LSN *
0x14007094e  mov     [rsp+150h+var_118], 0; int
0x140070956  mov     qword ptr [rsp+150h+Depth], rax; __int64 *
0x14007095b  lea     rax, [rbp+50h+var_D0]
0x14007095f  mov     [rsp+150h+pcbInfoBuffer], rsi; __int64 *
0x140070964  mov     [rsp+150h+pinfoBuffer], rax; __int64 *
0x140070969  call    ClfsReserveAndAppendLogInternal
0x14007096e  test    eax, eax
0x140070970  js      short loc_1400709A7
0x140070972  mov     [rsi], r14
0x140070975  jmp     loc_140070740
0x14007097a  mov     eax, 0C000009Ah
0x14007097f  jmp     loc_1400706F6
0x140070984  xor     edi, edi
0x140070986  jmp     loc_1400706B2
0x14007098b  xor     eax, eax
0x14007098d  jmp     short loc_140070911
0x14007098f  xor     ecx, ecx
0x140070991  jmp     loc_140070776
0x140070996  xor     ecx, ecx
0x140070998  jmp     loc_1400707AA
0x14007099d  mov     eax, 0C01A0023h
0x1400709a2  jmp     loc_1400706F6
0x1400709a7  cmp     eax, 0C01A001Dh
0x1400709ac  jz      loc_140070740
0x1400709b2  cmp     eax, 0C0000022h
0x1400709b7  jz      loc_140070740
0x1400709bd  jmp     loc_1400706F6
0x1400709c2  cmp     eax, r14d
0x1400709c5  jnz     short loc_140070A26
0x1400709c7  mov     edi, 73666C43h
0x1400709cc  mov     esi, 80h
0x1400709d1  mov     r8d, edi; Tag
0x1400709d4  mov     edx, esi; NumberOfBytes
0x1400709d6  mov     ecx, r14d; PoolType
0x1400709d9  call    cs:__imp_ExAllocatePoolWithTag
0x1400709e0  nop     dword ptr [rax+rax+00h]
0x1400709e5  mov     [rbx+0B0h], rax
0x1400709ec  test    rax, rax
0x1400709ef  jz      short loc_14007097A
0x1400709f1  mov     r8d, [rbx+2Ch]
0x1400709f5  xor     ecx, ecx
0x1400709f7  mov     [rsp+150h+Depth], cx; Depth
0x1400709fc  mov     r9d, r14d; Flags
0x1400709ff  mov     dword ptr [rsp+150h+pcbInfoBuffer], 49666C43h; Tag
0x140070a07  mov     rdx, r15; Allocate
0x140070a0a  mov     [rsp+150h+pinfoBuffer], r8; Size
0x140070a0f  mov     rcx, rax; Lookaside
0x140070a12  mov     r8, r12; Free
0x140070a15  call    cs:__imp_ExInitializeNPagedLookasideList
0x140070a1c  nop     dword ptr [rax+rax+00h]
0x140070a21  jmp     loc_140070831
0x140070a26  mov     eax, 0C000000Dh
0x140070a2b  jmp     loc_1400706F6
```
