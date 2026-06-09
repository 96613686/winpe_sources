# FltpInitLookasideLists

- ea: `0x180051278`
- end: `0x1800517ea`
- name: `FltpInitLookasideLists`
- size: `1394`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180051060`

## callees

- `0x180051278`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800512ef`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051322`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051354`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051387`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051444`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051477`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800514aa`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800514dd`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18005153f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051572`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800515a5`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051635`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051664`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800512ef`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051322`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051354`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051387`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051444`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051477`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800514aa`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800514dd`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18005153f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051572`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800515a5`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051635`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180051664`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x180051510`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800515d4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800516d6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x180051709`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005174f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x180051799`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800517d3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x180051510`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800515d4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800516d6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x180051709`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18005174f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x180051799`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800517d3`
- `ntoskrnl!FsRtlInitExtraCreateParameterLookasideList` at `0x180051298`
- `ntoskrnl!FsRtlInitExtraCreateParameterLookasideList` at `0x1800512b7`
- `ntoskrnl!FsRtlInitExtraCreateParameterLookasideList` at `0x180051682`
- `ntoskrnl!FsRtlInitExtraCreateParameterLookasideList` at `0x1800516a3`
- `ntoskrnl!FsRtlInitExtraCreateParameterLookasideList` at `0x180051298`
- `ntoskrnl!FsRtlInitExtraCreateParameterLookasideList` at `0x1800512b7`
- `ntoskrnl!FsRtlInitExtraCreateParameterLookasideList` at `0x180051682`
- `ntoskrnl!FsRtlInitExtraCreateParameterLookasideList` at `0x1800516a3`
- `ntoskrnl!IoSizeofWorkItem` at `0x180051393`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513a6`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513b6`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513c6`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513de`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513ee`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513fe`
- `ntoskrnl!IoSizeofWorkItem` at `0x180051413`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800515f5`
- `ntoskrnl!IoSizeofWorkItem` at `0x180051393`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513a6`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513b6`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513c6`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513de`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513ee`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800513fe`
- `ntoskrnl!IoSizeofWorkItem` at `0x180051413`
- `ntoskrnl!IoSizeofWorkItem` at `0x1800515f5`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1800515e0`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x1800515e0`

## pseudocode

```c
void FltpInitLookasideLists()
{
  SIZE_T Size; // rbx
  unsigned int v1; // ebx
  ULONG v2; // eax
  unsigned int i; // ebx

  FsRtlInitExtraCreateParameterLookasideList(qword_18003EA40, 2u, 0x60u, 0x63664D46u);
  FsRtlInitExtraCreateParameterLookasideList(qword_18003EAC0, 0, 0x18u, 0x68644D46u);
  ExInitializeNPagedLookasideList(&stru_18003EB40, 0, 0, 0x200u, 0x1B8u, 0x6C734D46u, 0);
  ExInitializeNPagedLookasideList(&stru_18003EBC0, 0, 0, 0x200u, 0xE0u, 0x7A664D46u, 0);
  Size = 56;
  ExInitializeNPagedLookasideList(&stru_18003EC40, 0, 0, 0x200u, 0x38u, 0x636E4D46u, 0);
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x10u, 0x73614D46u, 0);
  if ( IoSizeofWorkItem() >= 0x70 && IoSizeofWorkItem() <= 0x38
    || IoSizeofWorkItem() < 0x70
    || IoSizeofWorkItem() > 0x30 )
  {
    if ( IoSizeofWorkItem() < 0x70 || IoSizeofWorkItem() > 0x38 )
    {
      if ( IoSizeofWorkItem() >= 0x70 )
        Size = IoSizeofWorkItem();
      else
        Size = 112;
    }
  }
  else
  {
    Size = 48;
  }
  ExInitializeNPagedLookasideList(&stru_18003ED40, 0, 0, 0x200u, Size, 0x69774D46u, 0);
  ExInitializeNPagedLookasideList(&stru_18003EDC0, 0, 0, 0x200u, 0x120u, 0x336E4D46u, 0);
  ExInitializeNPagedLookasideList(&stru_18003EE40, 0, 0, 0x200u, 0x60u, 0x736F4D46u, 0);
  ExInitializeNPagedLookasideList(&stru_18003EEC0, 0, 0, 0x200u, 0x100u, 0x676E4D46u, 0);
  ExInitializePagedLookasideList(&stru_18003EF40, 0, 0, 0, 0x68u, 0x6B664D46u, 0);
  ExInitializeNPagedLookasideList(&stru_18003EFC0, 0, 0, 0x200u, 0x10u, 0x62744D46u, 0);
  ExInitializeNPagedLookasideList(&stru_18003F040, 0, 0, 0x200u, 0x48u, 0x6E634D46u, 0);
  ExInitializeNPagedLookasideList(&stru_18003F0C0, 0, 0, 0x200u, 0xB8u, 0x70744D46u, 0);
  ExInitializePagedLookasideList(&stru_18003F140, 0, 0, 0, 0x48u, 0x706C4D46u, 0);
  RunRefSize = ExSizeOfRundownProtectionCacheAware();
  v1 = 0;
  v2 = IoSizeofWorkItem();
  ExInitializeNPagedLookasideList(&stru_18003F1C0, 0, 0, 0x200u, v2 + RunRefSize + 336, 0x63734D46u, 0);
  ExInitializeNPagedLookasideList(&stru_18003F240, 0, 0, 0x200u, 0x58u, 0x6E634D46u, 0);
  FsRtlInitExtraCreateParameterLookasideList(qword_18003F2C0, 0, 0x10u, 0x726F4D46u);
  FsRtlInitExtraCreateParameterLookasideList(qword_18003F3C0, 0, 0xC8u, 0x63514D46u);
  ExInitializePagedLookasideList(&stru_18003F340, 0, 0, 0, 0x30u, 0x65724D46u, 0);
  ExInitializePagedLookasideList(&stru_18003F440, 0, 0, 0, 0x400u, 0x346E4D46u, 0);
  do
  {
    ExInitializePagedLookasideList(
      (PPAGED_LOOKASIDE_LIST)&qword_18003F4C0[16 * (unsigned __int64)v1],
      0,
      0,
      0,
      ((unsigned __int64)v1 << 6) + 336,
      0x316E4D46u,
      0);
    ++v1;
  }
  while ( v1 < 7 );
  for ( i = 0; i < 7; ++i )
    ExInitializePagedLookasideList(
      (PPAGED_LOOKASIDE_LIST)&qword_18003F840[16 * (unsigned __int64)i],
      0,
      0,
      0,
      ((unsigned __int64)i << 6) + 336,
      0x376E4D46u,
      0);
  ExInitializePagedLookasideList(&stru_18003FBC0, 0, 0, 0, 0x18u, 0x356E4D46u, 0);
}

```

## disassembly

```asm
0x180051278  push    rbx
0x18005127a  push    rsi
0x18005127b  push    rdi
0x18005127c  push    r15
0x18005127e  sub     rsp, 48h
0x180051282  mov     edx, 2; Flags
0x180051287  lea     rcx, qword_18003EA40; Lookaside
0x18005128e  mov     r9d, 63664D46h; Tag
0x180051294  lea     r8d, [rdx+5Eh]; Size
0x180051298  call    cs:__imp_FsRtlInitExtraCreateParameterLookasideList
0x18005129f  nop     dword ptr [rax+rax+00h]
0x1800512a4  xor     edx, edx; Flags
0x1800512a6  lea     rcx, qword_18003EAC0; Lookaside
0x1800512ad  mov     r9d, 68644D46h; Tag
0x1800512b3  lea     r8d, [rdx+18h]; Size
0x1800512b7  call    cs:__imp_FsRtlInitExtraCreateParameterLookasideList
0x1800512be  nop     dword ptr [rax+rax+00h]
0x1800512c3  xor     eax, eax
0x1800512c5  lea     rcx, stru_18003EB40; Lookaside
0x1800512cc  mov     [rsp+68h+Depth], ax; Depth
0x1800512d1  mov     esi, 200h
0x1800512d6  mov     [rsp+68h+Tag], 6C734D46h; Tag
0x1800512de  mov     r9d, esi; Flags
0x1800512e1  xor     r8d, r8d; Free
0x1800512e4  mov     [rsp+68h+Size], 1B8h; Size
0x1800512ed  xor     edx, edx; Allocate
0x1800512ef  call    cs:__imp_ExInitializeNPagedLookasideList
0x1800512f6  nop     dword ptr [rax+rax+00h]
0x1800512fb  xor     eax, eax
0x1800512fd  lea     rcx, stru_18003EBC0; Lookaside
0x180051304  mov     [rsp+68h+Depth], ax; Depth
0x180051309  mov     r9d, esi; Flags
0x18005130c  mov     [rsp+68h+Tag], 7A664D46h; Tag
0x180051314  xor     r8d, r8d; Free
0x180051317  xor     edx, edx; Allocate
0x180051319  mov     [rsp+68h+Size], 0E0h; Size
0x180051322  call    cs:__imp_ExInitializeNPagedLookasideList
0x180051329  nop     dword ptr [rax+rax+00h]
0x18005132e  xor     eax, eax
0x180051330  lea     rcx, stru_18003EC40; Lookaside
0x180051337  mov     [rsp+68h+Depth], ax; Depth
0x18005133c  mov     r9d, esi; Flags
0x18005133f  mov     [rsp+68h+Tag], 636E4D46h; Tag
0x180051347  xor     r8d, r8d; Free
0x18005134a  xor     edx, edx; Allocate
0x18005134c  lea     ebx, [rax+38h]
0x18005134f  mov     [rsp+68h+Size], rbx; Size
0x180051354  call    cs:__imp_ExInitializeNPagedLookasideList
0x18005135b  nop     dword ptr [rax+rax+00h]
0x180051360  xor     eax, eax
0x180051362  lea     r15d, [rbx-28h]
0x180051366  mov     [rsp+68h+Depth], ax; Depth
0x18005136b  lea     rcx, Lookaside; Lookaside
0x180051372  mov     [rsp+68h+Tag], 73614D46h; Tag
0x18005137a  mov     r9d, esi; Flags
0x18005137d  xor     r8d, r8d; Free
0x180051380  mov     [rsp+68h+Size], r15; Size
0x180051385  xor     edx, edx; Allocate
0x180051387  call    cs:__imp_ExInitializeNPagedLookasideList
0x18005138e  nop     dword ptr [rax+rax+00h]
0x180051393  call    cs:__imp_IoSizeofWorkItem
0x18005139a  nop     dword ptr [rax+rax+00h]
0x18005139f  lea     edi, [rbx+38h]
0x1800513a2  cmp     eax, edi
0x1800513a4  jb      short loc_1800513B6
0x1800513a6  call    cs:__imp_IoSizeofWorkItem
0x1800513ad  nop     dword ptr [rax+rax+00h]
0x1800513b2  cmp     eax, ebx
0x1800513b4  jbe     short loc_1800513DE
0x1800513b6  call    cs:__imp_IoSizeofWorkItem
0x1800513bd  nop     dword ptr [rax+rax+00h]
0x1800513c2  cmp     eax, edi
0x1800513c4  jb      short loc_1800513DE
0x1800513c6  call    cs:__imp_IoSizeofWorkItem
0x1800513cd  nop     dword ptr [rax+rax+00h]
0x1800513d2  cmp     eax, 30h ; '0'
0x1800513d5  ja      short loc_1800513DE
0x1800513d7  mov     ebx, 30h ; '0'
0x1800513dc  jmp     short loc_180051421
0x1800513de  call    cs:__imp_IoSizeofWorkItem
0x1800513e5  nop     dword ptr [rax+rax+00h]
0x1800513ea  cmp     eax, edi
0x1800513ec  jb      short loc_1800513FE
0x1800513ee  call    cs:__imp_IoSizeofWorkItem
0x1800513f5  nop     dword ptr [rax+rax+00h]
0x1800513fa  cmp     eax, ebx
0x1800513fc  jbe     short loc_180051421
0x1800513fe  call    cs:__imp_IoSizeofWorkItem
0x180051405  nop     dword ptr [rax+rax+00h]
0x18005140a  cmp     eax, edi
0x18005140c  jnb     short loc_180051413
0x18005140e  mov     rbx, rdi
0x180051411  jmp     short loc_180051421
0x180051413  call    cs:__imp_IoSizeofWorkItem
0x18005141a  nop     dword ptr [rax+rax+00h]
0x18005141f  mov     ebx, eax
0x180051421  xor     eax, eax
0x180051423  lea     rcx, stru_18003ED40; Lookaside
0x18005142a  mov     [rsp+68h+Depth], ax; Depth
0x18005142f  mov     r9d, esi; Flags
0x180051432  mov     [rsp+68h+Tag], 69774D46h; Tag
0x18005143a  xor     r8d, r8d; Free
0x18005143d  xor     edx, edx; Allocate
0x18005143f  mov     [rsp+68h+Size], rbx; Size
0x180051444  call    cs:__imp_ExInitializeNPagedLookasideList
0x18005144b  nop     dword ptr [rax+rax+00h]
0x180051450  xor     eax, eax
0x180051452  lea     rcx, stru_18003EDC0; Lookaside
0x180051459  mov     [rsp+68h+Depth], ax; Depth
0x18005145e  mov     r9d, esi; Flags
0x180051461  mov     [rsp+68h+Tag], 336E4D46h; Tag
0x180051469  xor     r8d, r8d; Free
0x18005146c  xor     edx, edx; Allocate
0x18005146e  mov     [rsp+68h+Size], 120h; Size
0x180051477  call    cs:__imp_ExInitializeNPagedLookasideList
0x18005147e  nop     dword ptr [rax+rax+00h]
0x180051483  xor     eax, eax
0x180051485  lea     rcx, stru_18003EE40; Lookaside
0x18005148c  mov     [rsp+68h+Depth], ax; Depth
0x180051491  mov     r9d, esi; Flags
0x180051494  mov     [rsp+68h+Tag], 736F4D46h; Tag
0x18005149c  xor     r8d, r8d; Free
0x18005149f  xor     edx, edx; Allocate
0x1800514a1  mov     [rsp+68h+Size], 60h ; '`'; Size
0x1800514aa  call    cs:__imp_ExInitializeNPagedLookasideList
0x1800514b1  nop     dword ptr [rax+rax+00h]
0x1800514b6  xor     eax, eax
0x1800514b8  lea     rcx, stru_18003EEC0; Lookaside
0x1800514bf  mov     [rsp+68h+Depth], ax; Depth
0x1800514c4  mov     r9d, esi; Flags
0x1800514c7  mov     [rsp+68h+Tag], 676E4D46h; Tag
0x1800514cf  xor     r8d, r8d; Free
0x1800514d2  xor     edx, edx; Allocate
0x1800514d4  mov     [rsp+68h+Size], 100h; Size
0x1800514dd  call    cs:__imp_ExInitializeNPagedLookasideList
0x1800514e4  nop     dword ptr [rax+rax+00h]
0x1800514e9  xor     eax, eax
0x1800514eb  lea     rcx, stru_18003EF40; Lookaside
0x1800514f2  mov     [rsp+68h+Depth], ax; Depth
0x1800514f7  xor     r9d, r9d; Flags
0x1800514fa  mov     [rsp+68h+Tag], 6B664D46h; Tag
0x180051502  xor     r8d, r8d; Free
0x180051505  xor     edx, edx; Allocate
0x180051507  mov     [rsp+68h+Size], 68h ; 'h'; Size
0x180051510  call    cs:__imp_ExInitializePagedLookasideList
0x180051517  nop     dword ptr [rax+rax+00h]
0x18005151c  xor     eax, eax
0x18005151e  lea     rcx, stru_18003EFC0; Lookaside
0x180051525  mov     [rsp+68h+Depth], ax; Depth
0x18005152a  mov     r9d, esi; Flags
0x18005152d  mov     [rsp+68h+Tag], 62744D46h; Tag
0x180051535  xor     r8d, r8d; Free
0x180051538  xor     edx, edx; Allocate
0x18005153a  mov     [rsp+68h+Size], r15; Size
0x18005153f  call    cs:__imp_ExInitializeNPagedLookasideList
0x180051546  nop     dword ptr [rax+rax+00h]
0x18005154b  xor     eax, eax
0x18005154d  lea     rcx, stru_18003F040; Lookaside
0x180051554  mov     [rsp+68h+Depth], ax; Depth
0x180051559  mov     edi, 6E634D46h
0x18005155e  mov     [rsp+68h+Tag], edi; Tag
0x180051562  mov     r9d, esi; Flags
0x180051565  xor     r8d, r8d; Free
0x180051568  xor     edx, edx; Allocate
0x18005156a  lea     ebx, [rax+48h]
0x18005156d  mov     [rsp+68h+Size], rbx; Size
0x180051572  call    cs:__imp_ExInitializeNPagedLookasideList
0x180051579  nop     dword ptr [rax+rax+00h]
0x18005157e  xor     eax, eax
0x180051580  lea     rcx, stru_18003F0C0; Lookaside
0x180051587  mov     [rsp+68h+Depth], ax; Depth
0x18005158c  mov     r9d, esi; Flags
0x18005158f  mov     [rsp+68h+Tag], 70744D46h; Tag
0x180051597  xor     r8d, r8d; Free
0x18005159a  xor     edx, edx; Allocate
0x18005159c  mov     [rsp+68h+Size], 0B8h; Size
0x1800515a5  call    cs:__imp_ExInitializeNPagedLookasideList
0x1800515ac  nop     dword ptr [rax+rax+00h]
0x1800515b1  xor     eax, eax
0x1800515b3  xor     r9d, r9d; Flags
0x1800515b6  mov     [rsp+68h+Depth], ax; Depth
0x1800515bb  xor     r8d, r8d; Free
0x1800515be  mov     [rsp+68h+Tag], 706C4D46h; Tag
0x1800515c6  xor     edx, edx; Allocate
0x1800515c8  mov     [rsp+68h+Size], rbx; Size
0x1800515cd  lea     rcx, stru_18003F140; Lookaside
0x1800515d4  call    cs:__imp_ExInitializePagedLookasideList
0x1800515db  nop     dword ptr [rax+rax+00h]
0x1800515e0  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x1800515e7  nop     dword ptr [rax+rax+00h]
0x1800515ec  mov     cs:RunRefSize, rax
0x1800515f3  xor     ebx, ebx
0x1800515f5  call    cs:__imp_IoSizeofWorkItem
0x1800515fc  nop     dword ptr [rax+rax+00h]
0x180051601  mov     rdx, cs:RunRefSize
0x180051608  mov     r9d, esi; Flags
0x18005160b  add     rdx, 150h
0x180051612  mov     ecx, eax
0x180051614  add     rdx, rcx
0x180051617  mov     [rsp+68h+Depth], bx; Depth
0x18005161c  mov     [rsp+68h+Tag], 63734D46h; Tag
0x180051624  lea     rcx, stru_18003F1C0; Lookaside
0x18005162b  mov     [rsp+68h+Size], rdx; Size
0x180051630  xor     r8d, r8d; Free
0x180051633  xor     edx, edx; Allocate
0x180051635  call    cs:__imp_ExInitializeNPagedLookasideList
0x18005163c  nop     dword ptr [rax+rax+00h]
0x180051641  xor     eax, eax
0x180051643  lea     rcx, stru_18003F240; Lookaside
0x18005164a  mov     [rsp+68h+Depth], ax; Depth
0x18005164f  mov     r9d, esi; Flags
0x180051652  mov     [rsp+68h+Tag], edi; Tag
0x180051656  xor     r8d, r8d; Free
0x180051659  xor     edx, edx; Allocate
0x18005165b  mov     [rsp+68h+Size], 58h ; 'X'; Size
0x180051664  call    cs:__imp_ExInitializeNPagedLookasideList
0x18005166b  nop     dword ptr [rax+rax+00h]
0x180051670  mov     r9d, 726F4D46h; Tag
0x180051676  lea     rcx, qword_18003F2C0; Lookaside
0x18005167d  mov     r8, r15; Size
0x180051680  xor     edx, edx; Flags
0x180051682  call    cs:__imp_FsRtlInitExtraCreateParameterLookasideList
0x180051689  nop     dword ptr [rax+rax+00h]
0x18005168e  xor     edx, edx; Flags
0x180051690  lea     rcx, qword_18003F3C0; Lookaside
0x180051697  mov     r9d, 63514D46h; Tag
0x18005169d  mov     r8d, 0C8h; Size
0x1800516a3  call    cs:__imp_FsRtlInitExtraCreateParameterLookasideList
0x1800516aa  nop     dword ptr [rax+rax+00h]
0x1800516af  xor     eax, eax
0x1800516b1  lea     rcx, stru_18003F340; Lookaside
0x1800516b8  mov     [rsp+68h+Depth], ax; Depth
0x1800516bd  xor     r9d, r9d; Flags
0x1800516c0  mov     [rsp+68h+Tag], 65724D46h; Tag
0x1800516c8  xor     r8d, r8d; Free
0x1800516cb  xor     edx, edx; Allocate
0x1800516cd  mov     [rsp+68h+Size], 30h ; '0'; Size
0x1800516d6  call    cs:__imp_ExInitializePagedLookasideList
0x1800516dd  nop     dword ptr [rax+rax+00h]
0x1800516e2  xor     eax, eax
0x1800516e4  lea     rcx, stru_18003F440; Lookaside
0x1800516eb  mov     [rsp+68h+Depth], ax; Depth
0x1800516f0  xor     r9d, r9d; Flags
0x1800516f3  mov     [rsp+68h+Tag], 346E4D46h; Tag
0x1800516fb  xor     r8d, r8d; Free
0x1800516fe  xor     edx, edx; Allocate
0x180051700  mov     [rsp+68h+Size], 400h; Size
0x180051709  call    cs:__imp_ExInitializePagedLookasideList
0x180051710  nop     dword ptr [rax+rax+00h]
0x180051715  mov     edi, 150h
0x18005171a  xor     eax, eax
0x18005171c  mov     edx, ebx
0x18005171e  shl     rdx, 6
0x180051722  lea     r8, qword_18003F4C0
0x180051729  add     rdx, rdi
0x18005172c  mov     [rsp+68h+Depth], ax; Depth
0x180051731  mov     ecx, ebx
0x180051733  xor     r9d, r9d; Flags
0x180051736  shl     rcx, 7
0x18005173a  add     rcx, r8; Lookaside
0x18005173d  mov     [rsp+68h+Tag], 316E4D46h; Tag
0x180051745  mov     [rsp+68h+Size], rdx; Size
0x18005174a  xor     r8d, r8d; Free
0x18005174d  xor     edx, edx; Allocate
0x18005174f  call    cs:__imp_ExInitializePagedLookasideList
0x180051756  nop     dword ptr [rax+rax+00h]
0x18005175b  inc     ebx
0x18005175d  cmp     ebx, 7
0x180051760  jb      short loc_18005171A
0x180051762  xor     ebx, ebx
0x180051764  xor     eax, eax
0x180051766  mov     edx, ebx
0x180051768  shl     rdx, 6
0x18005176c  lea     r8, qword_18003F840
0x180051773  add     rdx, rdi
0x180051776  mov     [rsp+68h+Depth], ax; Depth
0x18005177b  mov     ecx, ebx
0x18005177d  xor     r9d, r9d; Flags
0x180051780  shl     rcx, 7
0x180051784  add     rcx, r8; Lookaside
0x180051787  mov     [rsp+68h+Tag], 376E4D46h; Tag
0x18005178f  mov     [rsp+68h+Size], rdx; Size
0x180051794  xor     r8d, r8d; Free
0x180051797  xor     edx, edx; Allocate
0x180051799  call    cs:__imp_ExInitializePagedLookasideList
0x1800517a0  nop     dword ptr [rax+rax+00h]
0x1800517a5  inc     ebx
0x1800517a7  cmp     ebx, 7
0x1800517aa  jb      short loc_180051764
0x1800517ac  xor     eax, eax
0x1800517ae  lea     rcx, stru_18003FBC0; Lookaside
0x1800517b5  mov     [rsp+68h+Depth], ax; Depth
0x1800517ba  xor     r9d, r9d; Flags
0x1800517bd  mov     [rsp+68h+Tag], 356E4D46h; Tag
0x1800517c5  xor     r8d, r8d; Free
0x1800517c8  xor     edx, edx; Allocate
0x1800517ca  mov     [rsp+68h+Size], 18h; Size
0x1800517d3  call    cs:__imp_ExInitializePagedLookasideList
0x1800517da  nop     dword ptr [rax+rax+00h]
0x1800517df  add     rsp, 48h
  ... truncated ...
```
