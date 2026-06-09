# CClfsLogFcbPhysical::Finalize(uchar)

- ea: `0x140008eac`
- end: `0x1400092cf`
- name: `?Finalize@CClfsLogFcbPhysical@@AEAAXE@Z`
- size: `1059`
- prototype: `void __fastcall(CClfsLogFcbPhysical *__hidden this, unsigned __int8)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008c70`
- `0x140075e08`

## callees

- `0x140006fa4`
- `0x1400072f8`
- `0x140008eac`
- `0x14000a228`
- `0x14000dcd8`
- `0x14000dfa4`
- `0x140017f20`
- `0x140018280`
- `0x14005fd18`
- `0x140062df0`
- `0x140075cd4`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140008f94`
- `ntoskrnl!ExDeleteResourceLite` at `0x140008f94`
- `ntoskrnl!ObfDereferenceObject` at `0x140008ee6`
- `ntoskrnl!ObfDereferenceObject` at `0x140008ee6`
- `ntoskrnl!KeSetEvent` at `0x140009197`
- `ntoskrnl!KeSetEvent` at `0x140009197`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400092b7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400092b7`
- `ntoskrnl!IoFreeWorkItem` at `0x140009264`
- `ntoskrnl!IoFreeWorkItem` at `0x140009264`
- `ntoskrnl!InitializeSListHead` at `0x14000912b`
- `ntoskrnl!InitializeSListHead` at `0x14000912b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000920f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009229`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000927e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009298`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000920f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009229`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000927e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009298`

## pseudocode

```c
void __fastcall CClfsLogFcbPhysical::Finalize(CClfsLogFcbPhysical *this, char a2)
{
  CClfsBaseFile *v3; // rcx
  _DWORD *v5; // rdi
  void *v6; // rcx
  struct _IO_WORKITEM *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  struct _ERESOURCE *v13; // rcx
  void *v14; // rdx
  CClfsLogFcbPhysical *v15; // rcx

  v3 = (CClfsBaseFile *)*((_QWORD *)this + 89);
  v5 = (_DWORD *)((char *)this + 364);
  if ( v3 )
  {
    if ( (*v5 & 0x10) != 0 )
    {
      CClfsLogFcbPhysical::DeleteBaseFileAndContainers(this);
    }
    else
    {
      if ( CClfsBaseFile::ContainerCount(v3) )
      {
        CClfsLogFcbPhysical::CloseContainers(this);
        if ( !CClfsLogFcbCommon::IsReadOnly(this) && (*v5 & 0x40) != 0 )
        {
          CClfsLogFcbPhysical::ResetLog(v15);
          (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 112LL))(this);
        }
      }
      CClfsBaseFilePersisted::CloseImage(*((CClfsBaseFilePersisted **)this + 89));
    }
    CClfsBaseFile::Release(*((CClfsBaseFile **)this + 89));
    *((_QWORD *)this + 89) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 170);
  *v5 = 1;
  if ( v6 )
  {
    ObfDereferenceObject(v6);
    *((_QWORD *)this + 170) = 0;
  }
  v7 = (struct _IO_WORKITEM *)*((_QWORD *)this + 174);
  if ( v7 )
  {
    IoFreeWorkItem(v7);
    *((_QWORD *)this + 174) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 119);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0);
    *((_QWORD *)this + 119) = 0;
  }
  if ( *((_QWORD *)this + 705) )
  {
    CClfsLogFcbPhysical::ClearContainerQueue(this);
    ExFreePoolWithTag(*((PVOID *)this + 705), 0);
    *((_QWORD *)this + 705) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 124);
  if ( v9 )
  {
    ExFreePoolWithTag(v9, 0);
    *((_QWORD *)this + 124) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 120);
  if ( v10 )
  {
    ExFreePoolWithTag(v10, 0);
    *((_QWORD *)this + 120) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 136);
  if ( v11 )
  {
    ExFreePoolWithTag(v11, 0);
    *((_QWORD *)this + 136) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 706);
  if ( v12 )
  {
    ExFreePoolWithTag(v12, 0);
    *((_QWORD *)this + 706) = 0;
  }
  v13 = (struct _ERESOURCE *)*((_QWORD *)this + 176);
  if ( v13 )
  {
    ExDeleteResourceLite(v13);
    ExFreePoolWithTag(*((PVOID *)this + 176), 0);
    *((_QWORD *)this + 176) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 88);
  if ( v14 )
  {
    ExFreeToPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage, v14);
    *((_QWORD *)this + 88) = 0;
  }
  *((_DWORD *)this + 93) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_DWORD *)this + 95) = 0;
  *((CLFS_LSN *)this + 62) = CLFS_LSN_NULL;
  *((CLFS_LSN *)this + 61) = CLFS_LSN_NULL;
  *((CLFS_LSN *)this + 171) = CLFS_LSN_INVALID;
  *((CLFS_LSN *)this + 63) = CLFS_LSN_NULL;
  *((CLFS_LSN *)this + 64) = CLFS_LSN_INVALID;
  *((CLFS_LSN *)this + 60) = CLFS_LSN_NULL;
  *((_WORD *)this + 188) = 0;
  *((_QWORD *)this + 70) = 0;
  *((CLFS_LSN *)this + 65) = CLFS_LSN_INVALID;
  *((CLFS_LSN *)this + 66) = CLFS_LSN_INVALID;
  *((CLFS_LSN *)this + 68) = CLFS_LSN_INVALID;
  *((CLFS_LSN *)this + 67) = CLFS_LSN_INVALID;
  *((_DWORD *)this + 350) = 0;
  *((_DWORD *)this + 333) = 0;
  *(_QWORD *)((char *)this + 1340) = 0;
  *((_WORD *)this + 344) = 0;
  *(_QWORD *)((char *)this + 1316) = 0;
  *((_DWORD *)this + 327) = 0;
  *((_DWORD *)this + 331) = 0;
  *((_QWORD *)this + 177) = 0;
  *((_QWORD *)this + 176) = 0;
  *((CLFS_LSN *)this + 172) = CLFS_LSN_NULL;
  *((CLFS_LSN *)this + 173) = CLFS_LSN_INVALID;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 49) = (char *)this + 384;
  *((_QWORD *)this + 48) = (char *)this + 384;
  *((_QWORD *)this + 51) = (char *)this + 400;
  *((_QWORD *)this + 50) = (char *)this + 400;
  *((_QWORD *)this + 91) = (char *)this + 720;
  *((_QWORD *)this + 90) = (char *)this + 720;
  InitializeSListHead((PSLIST_HEADER)this + 61);
  memset((char *)this + 1424, 0, 0x1000u);
  *(_OWORD *)((char *)this + 5528) = 0;
  *(_OWORD *)((char *)this + 5544) = 0;
  *(_OWORD *)((char *)this + 5560) = 0;
  *((_WORD *)this + 2768) = 48;
  *((_DWORD *)this + 1385) = 16;
  *((_DWORD *)this + 91) &= 0xFFF80FFF;
  if ( a2 )
  {
    *((_DWORD *)this + 236) = 0;
    KeSetEvent((PRKEVENT)((char *)this + 920), 0, 0);
  }
}

```

## disassembly

```asm
0x140008eac  push    rbx
0x140008eae  push    rbp
0x140008eaf  push    rsi
0x140008eb0  push    rdi
0x140008eb1  sub     rsp, 28h
0x140008eb5  mov     rbx, rcx
0x140008eb8  xor     ebp, ebp
0x140008eba  mov     rcx, [rcx+2C8h]; this
0x140008ec1  mov     sil, dl
0x140008ec4  lea     rdi, [rbx+16Ch]
0x140008ecb  test    rcx, rcx
0x140008ece  jnz     loc_1400091AD
0x140008ed4  mov     rcx, [rbx+550h]; Object
0x140008edb  mov     dword ptr [rdi], 1
0x140008ee1  test    rcx, rcx
0x140008ee4  jz      short loc_140008EF9
0x140008ee6  call    cs:__imp_ObfDereferenceObject
0x140008eed  nop     dword ptr [rax+rax+00h]
0x140008ef2  mov     [rbx+550h], rbp
0x140008ef9  mov     rcx, [rbx+570h]; IoWorkItem
0x140008f00  test    rcx, rcx
0x140008f03  jnz     loc_140009264
0x140008f09  mov     rcx, [rbx+3B8h]; P
0x140008f10  test    rcx, rcx
0x140008f13  jnz     loc_14000927C
0x140008f19  cmp     [rbx+1608h], rbp
0x140008f20  jnz     loc_1400091FE
0x140008f26  mov     rcx, [rbx+3E0h]; P
0x140008f2d  test    rcx, rcx
0x140008f30  jz      short loc_140008F47
0x140008f32  xor     edx, edx; Tag
0x140008f34  call    cs:__imp_ExFreePoolWithTag
0x140008f3b  nop     dword ptr [rax+rax+00h]
0x140008f40  mov     [rbx+3E0h], rbp
0x140008f47  mov     rcx, [rbx+3C0h]; P
0x140008f4e  test    rcx, rcx
0x140008f51  jz      short loc_140008F68
0x140008f53  xor     edx, edx; Tag
0x140008f55  call    cs:__imp_ExFreePoolWithTag
0x140008f5c  nop     dword ptr [rax+rax+00h]
0x140008f61  mov     [rbx+3C0h], rbp
0x140008f68  mov     rcx, [rbx+440h]; P
0x140008f6f  test    rcx, rcx
0x140008f72  jnz     loc_140009296
0x140008f78  mov     rcx, [rbx+1610h]; P
0x140008f7f  test    rcx, rcx
0x140008f82  jnz     loc_140009227
0x140008f88  mov     rcx, [rbx+580h]; Resource
0x140008f8f  test    rcx, rcx
0x140008f92  jz      short loc_140008FBC
0x140008f94  call    cs:__imp_ExDeleteResourceLite
0x140008f9b  nop     dword ptr [rax+rax+00h]
0x140008fa0  mov     rcx, [rbx+580h]; P
0x140008fa7  xor     edx, edx; Tag
0x140008fa9  call    cs:__imp_ExFreePoolWithTag
0x140008fb0  nop     dword ptr [rax+rax+00h]
0x140008fb5  mov     [rbx+580h], rbp
0x140008fbc  mov     rdx, [rbx+2C0h]; Entry
0x140008fc3  test    rdx, rdx
0x140008fc6  jnz     loc_1400092B0
0x140008fcc  mov     [rbx+174h], ebp
0x140008fd2  lea     rcx, [rbx+3D0h]; SListHead
0x140008fd9  mov     [rbx+1D0h], rbp
0x140008fe0  mov     [rbx+1D8h], rbp
0x140008fe7  mov     [rbx+1C8h], rbp
0x140008fee  mov     [rbx+17Ch], ebp
0x140008ff4  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140008ffb  mov     [rbx+1F0h], rax
0x140009002  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140009009  mov     [rbx+1E8h], rax
0x140009010  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140009017  mov     [rbx+558h], rax
0x14000901e  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140009025  mov     [rbx+1F8h], rax
0x14000902c  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140009033  mov     [rbx+200h], rax
0x14000903a  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140009041  mov     [rbx+1E0h], rax
0x140009048  mov     [rbx+178h], bp
0x14000904f  mov     [rbx+230h], rbp
0x140009056  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14000905d  mov     [rbx+208h], rax
0x140009064  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14000906b  mov     [rbx+210h], rax
0x140009072  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140009079  mov     [rbx+220h], rax
0x140009080  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140009087  mov     [rbx+218h], rax
0x14000908e  mov     [rbx+578h], ebp
0x140009094  mov     [rbx+534h], ebp
0x14000909a  mov     [rbx+53Ch], rbp
0x1400090a1  mov     [rbx+2B0h], bp
0x1400090a8  mov     [rbx+524h], rbp
0x1400090af  mov     [rbx+51Ch], ebp
0x1400090b5  mov     [rbx+52Ch], ebp
0x1400090bb  mov     [rbx+588h], rbp
0x1400090c2  mov     [rbx+580h], rbp
0x1400090c9  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x1400090d0  mov     [rbx+560h], rax
0x1400090d7  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400090de  mov     [rbx+568h], rax
0x1400090e5  lea     rax, [rbx+180h]
0x1400090ec  mov     [rbx+2B8h], rbp
0x1400090f3  mov     [rbx+1B0h], rbp
0x1400090fa  mov     [rbx+1C0h], rbp
0x140009101  mov     [rbx+1B8h], rbp
0x140009108  mov     [rax+8], rax
0x14000910c  mov     [rax], rax
0x14000910f  lea     rax, [rbx+190h]
0x140009116  mov     [rax+8], rax
0x14000911a  mov     [rax], rax
0x14000911d  lea     rax, [rbx+2D0h]
0x140009124  mov     [rax+8], rax
0x140009128  mov     [rax], rax
0x14000912b  call    cs:__imp_InitializeSListHead
0x140009132  nop     dword ptr [rax+rax+00h]
0x140009137  lea     rcx, [rbx+590h]; void *
0x14000913e  xor     edx, edx; Val
0x140009140  mov     r8d, 1000h; Size
0x140009146  call    memset
0x14000914b  xorps   xmm0, xmm0
0x14000914e  movups  xmmword ptr [rbx+1598h], xmm0
0x140009155  movups  xmmword ptr [rbx+15A8h], xmm0
0x14000915c  movups  xmmword ptr [rbx+15B8h], xmm0
0x140009163  mov     word ptr [rbx+15A0h], 30h ; '0'
0x14000916c  mov     dword ptr [rbx+15A4h], 10h
0x140009176  and     dword ptr [rbx+16Ch], 0FFF80FFFh
0x140009180  test    sil, sil
0x140009183  jz      short loc_1400091A3
0x140009185  lea     rcx, [rbx+398h]; Event
0x14000918c  mov     [rbx+3B0h], ebp
0x140009192  xor     r8d, r8d; Wait
0x140009195  xor     edx, edx; Increment
0x140009197  call    cs:__imp_KeSetEvent
0x14000919e  nop     dword ptr [rax+rax+00h]
0x1400091a3  add     rsp, 28h
0x1400091a7  pop     rdi
0x1400091a8  pop     rsi
0x1400091a9  pop     rbp
0x1400091aa  pop     rbx
0x1400091ab  retn
0x1400091ad  mov     eax, [rdi]
0x1400091af  test    al, 10h
0x1400091b1  jnz     loc_140009241
0x1400091b7  call    ?ContainerCount@CClfsBaseFile@@QEAAKXZ; CClfsBaseFile::ContainerCount(void)
0x1400091bc  test    eax, eax
0x1400091be  jz      short loc_1400091DA
0x1400091c0  mov     rcx, rbx; this
0x1400091c3  call    ?CloseContainers@CClfsLogFcbPhysical@@AEAAJXZ; CClfsLogFcbPhysical::CloseContainers(void)
0x1400091c8  mov     rcx, rbx; this
0x1400091cb  call    ?IsReadOnly@CClfsLogFcbCommon@@QEBAEXZ; CClfsLogFcbCommon::IsReadOnly(void)
0x1400091d0  test    al, al
0x1400091d2  jnz     short loc_1400091DA
0x1400091d4  mov     eax, [rdi]
0x1400091d6  test    al, 40h
0x1400091d8  jnz     short loc_14000924B
0x1400091da  mov     rcx, [rbx+2C8h]; this
0x1400091e1  call    ?CloseImage@CClfsBaseFilePersisted@@QEAAJXZ; CClfsBaseFilePersisted::CloseImage(void)
0x1400091e6  mov     rcx, [rbx+2C8h]; this
0x1400091ed  call    ?Release@CClfsBaseFile@@QEAAKXZ; CClfsBaseFile::Release(void)
0x1400091f2  mov     [rbx+2C8h], rbp
0x1400091f9  jmp     loc_140008ED4
0x1400091fe  mov     rcx, rbx; this
0x140009201  call    ?ClearContainerQueue@CClfsLogFcbPhysical@@AEAAXXZ; CClfsLogFcbPhysical::ClearContainerQueue(void)
0x140009206  mov     rcx, [rbx+1608h]; P
0x14000920d  xor     edx, edx; Tag
0x14000920f  call    cs:__imp_ExFreePoolWithTag
0x140009216  nop     dword ptr [rax+rax+00h]
0x14000921b  mov     [rbx+1608h], rbp
0x140009222  jmp     loc_140008F26
0x140009227  xor     edx, edx; Tag
0x140009229  call    cs:__imp_ExFreePoolWithTag
0x140009230  nop     dword ptr [rax+rax+00h]
0x140009235  mov     [rbx+1610h], rbp
0x14000923c  jmp     loc_140008F88
0x140009241  mov     rcx, rbx; this
0x140009244  call    ?DeleteBaseFileAndContainers@CClfsLogFcbPhysical@@AEAAXXZ; CClfsLogFcbPhysical::DeleteBaseFileAndContainers(void)
0x140009249  jmp     short loc_1400091E6
0x14000924b  call    ?ResetLog@CClfsLogFcbPhysical@@AEAAJXZ; CClfsLogFcbPhysical::ResetLog(void)
0x140009250  mov     rax, [rbx]
0x140009253  mov     rcx, rbx
0x140009256  mov     rax, [rax+70h]
0x14000925a  call    _guard_dispatch_icall
0x14000925f  jmp     loc_1400091DA
0x140009264  call    cs:__imp_IoFreeWorkItem
0x14000926b  nop     dword ptr [rax+rax+00h]
0x140009270  mov     [rbx+570h], rbp
0x140009277  jmp     loc_140008F09
0x14000927c  xor     edx, edx; Tag
0x14000927e  call    cs:__imp_ExFreePoolWithTag
0x140009285  nop     dword ptr [rax+rax+00h]
0x14000928a  mov     [rbx+3B8h], rbp
0x140009291  jmp     loc_140008F19
0x140009296  xor     edx, edx; Tag
0x140009298  call    cs:__imp_ExFreePoolWithTag
0x14000929f  nop     dword ptr [rax+rax+00h]
0x1400092a4  mov     [rbx+440h], rbp
0x1400092ab  jmp     loc_140008F78
0x1400092b0  lea     rcx, ?m_laOwnerPage@CClfsLogFcbPhysical@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400092b7  call    cs:__imp_ExFreeToPagedLookasideList
0x1400092be  nop     dword ptr [rax+rax+00h]
0x1400092c3  mov     [rbx+2C0h], rbp
0x1400092ca  jmp     loc_140008FCC
```
