# DetailsView::Importer::Import(ushort const *)

- ea: `0x18000c01c`
- end: `0x18000c21c`
- name: `?Import@Importer@DetailsView@@QEAAJPEBG@Z`
- size: `512`
- prototype: `__int64 __fastcall(DetailsView::Importer *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18000bd88`
- `0x18000d4d0`

## callees

- `0x180006ec0`
- `0x180007614`
- `0x180007ae4`
- `0x18000b52c`
- `0x18000c01c`
- `0x18001ab24`
- `0x18001bd7c`
- `0x18001bdd8`
- `0x18001f010`

## import_xrefs

- `ole32!StgIsStorageFile` at `0x18000c046`
- `ole32!StgIsStorageFile` at `0x18000c046`
- `ole32!StgOpenStorage` at `0x18000c0fa`
- `ole32!StgOpenStorage` at `0x18000c0fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DetailsView::Importer::Import(DetailsView::Importer *this, const unsigned __int16 *a2)
{
  int v4; // esi
  int v5; // ebx
  struct IStream *v6; // rax
  unsigned int v7; // r8d
  unsigned int v8; // edx
  HWND v9; // rcx
  void **v11; // [rsp+40h] [rbp-30h] BYREF
  struct IStream *v12; // [rsp+48h] [rbp-28h]
  __m128i si128; // [rsp+50h] [rbp-20h] BYREF
  __int128 v14; // [rsp+60h] [rbp-10h]
  struct IStream *v15; // [rsp+90h] [rbp+20h] BYREF
  IStorage *ppstgOpen; // [rsp+A0h] [rbp+30h] BYREF

  v4 = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 104LL))((char *)this + 16);
  if ( StgIsStorageFile(a2) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v14 = 0;
    v5 = MappedFile::Open((MappedFile *)&si128, a2);
    if ( v5 >= 0 )
    {
      v11 = &DetailsView::Importer::Source::`vftable';
      v12 = 0;
      v6 = (struct IStream *)operator new(0x18u);
      v15 = v6;
      if ( v6 )
      {
        *(_QWORD *)v6 = &DetailsView::Importer::MemorySource::`vftable';
        *((_QWORD *)v6 + 1) = v14;
        *((_DWORD *)v6 + 4) = DWORD2(v14);
      }
      v12 = v6;
      v5 = DetailsView::Importer::Import(this, (struct DetailsView::Importer::Source *)&v11);
      DetailsView::Importer::Source::~Source((DetailsView::Importer::Source *)&v11);
    }
    MappedFile::~MappedFile((MappedFile *)&si128);
LABEL_12:
    if ( v5 >= 0 )
      return (unsigned int)v5;
    goto LABEL_13;
  }
  ppstgOpen = 0;
  v5 = StgOpenStorage(a2, 0, 0x10u, 0, 0, &ppstgOpen);
  if ( v5 >= 0 )
  {
    v15 = 0;
    v5 = ((__int64 (__fastcall *)(IStorage *, const wchar_t *, _QWORD, __int64, _DWORD, struct IStream **))ppstgOpen->lpVtbl->OpenStream)(
           ppstgOpen,
           L"NT DISKQUOTA IMPORTEXPORT",
           0,
           16,
           0,
           &v15);
    if ( v5 < 0 )
    {
      v4 = 1;
    }
    else
    {
      DetailsView::Importer::Source::Source((DetailsView::Importer::Source *)&v11, v15);
      v5 = DetailsView::Importer::Import(this, (struct DetailsView::Importer::Source *)&v11);
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v15 + 16LL))(v15);
      DetailsView::Importer::Source::~Source((DetailsView::Importer::Source *)&v11);
    }
    ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    goto LABEL_12;
  }
LABEL_13:
  switch ( v5 )
  {
    case -2147287038:
      v8 = v4 != 0 ? 40591 : 40597;
      goto LABEL_25;
    case -2147287036:
      v8 = 40596;
      goto LABEL_25;
    case -2147287035:
      v8 = 40593;
      goto LABEL_25;
    case -2147287032:
      goto LABEL_21;
    case -2147286788:
      v8 = 40595;
      goto LABEL_25;
    case -2147024882:
LABEL_21:
      v8 = 40594;
      goto LABEL_25;
  }
  v8 = 40592;
LABEL_25:
  v9 = (HWND)*((_QWORD *)this + 7);
  if ( !v9 )
    v9 = (HWND)*((_QWORD *)this + 8);
  DiskQuotaMsgBox(v9, v8, v7, 0x10u);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c01c  mov     [rsp-18h+arg_8], rbx
0x18000c021  push    rbp
0x18000c022  push    rsi
0x18000c023  push    rdi
0x18000c024  mov     rbp, rsp
0x18000c027  sub     rsp, 70h
0x18000c02b  mov     rbx, rdx
0x18000c02e  mov     rdi, rcx
0x18000c031  xor     esi, esi
0x18000c033  add     rcx, 10h
0x18000c037  mov     rax, [rcx]
0x18000c03a  mov     rax, [rax+68h]
0x18000c03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c043  mov     rcx, rbx; pwcsName
0x18000c046  call    cs:__imp_StgIsStorageFile
0x18000c04c  test    eax, eax
0x18000c04e  jz      loc_18000C0DD
0x18000c054  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000c05c  movdqu  [rbp+var_20], xmm0
0x18000c061  xorps   xmm0, xmm0
0x18000c064  movdqu  [rbp+var_10], xmm0
0x18000c069  mov     rdx, rbx; unsigned __int16 *
0x18000c06c  lea     rcx, [rbp+var_20]; this
0x18000c070  call    ?Open@MappedFile@@QEAAJPEBG@Z; MappedFile::Open(ushort const *)
0x18000c075  mov     ebx, eax
0x18000c077  test    eax, eax
0x18000c079  js      short loc_18000C0CF
0x18000c07b  lea     rax, ??_7Source@Importer@DetailsView@@6B@; const DetailsView::Importer::Source::`vftable'
0x18000c082  mov     [rbp+var_30], rax
0x18000c086  mov     [rbp+var_28], rsi
0x18000c08a  lea     ecx, [rsi+18h]; uBytes
0x18000c08d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c092  mov     [rbp+arg_0], rax
0x18000c096  test    rax, rax
0x18000c099  jz      short loc_18000C0B3
0x18000c09b  lea     rcx, ??_7MemorySource@Importer@DetailsView@@6B@; const DetailsView::Importer::MemorySource::`vftable'
0x18000c0a2  mov     [rax], rcx
0x18000c0a5  mov     rcx, qword ptr [rbp+var_10]
0x18000c0a9  mov     [rax+8], rcx
0x18000c0ad  mov     ecx, dword ptr [rbp+var_10+8]
0x18000c0b0  mov     [rax+10h], ecx
0x18000c0b3  mov     [rbp+var_28], rax
0x18000c0b7  lea     rdx, [rbp+var_30]; struct DetailsView::Importer::Source *
0x18000c0bb  mov     rcx, rdi; this
0x18000c0be  call    ?Import@Importer@DetailsView@@AEAAJAEAVSource@12@@Z; DetailsView::Importer::Import(DetailsView::Importer::Source &)
0x18000c0c3  mov     ebx, eax
0x18000c0c5  lea     rcx, [rbp+var_30]; this
0x18000c0c9  call    ??1Source@Importer@DetailsView@@UEAA@XZ; DetailsView::Importer::Source::~Source(void)
0x18000c0ce  nop
0x18000c0cf  lea     rcx, [rbp+var_20]; this
0x18000c0d3  call    ??1MappedFile@@QEAA@XZ; MappedFile::~MappedFile(void)
0x18000c0d8  jmp     loc_18000C18E
0x18000c0dd  mov     [rbp+arg_10], rsi
0x18000c0e1  lea     rax, [rbp+arg_10]
0x18000c0e5  mov     [rsp+70h+ppstgOpen], rax; ppstgOpen
0x18000c0ea  mov     [rsp+70h+reserved], esi; reserved
0x18000c0ee  xor     r9d, r9d; snbExclude
0x18000c0f1  xor     edx, edx; pstgPriority
0x18000c0f3  lea     r8d, [r9+10h]; grfMode
0x18000c0f7  mov     rcx, rbx; pwcsName
0x18000c0fa  call    cs:__imp_StgOpenStorage
0x18000c100  mov     ebx, eax
0x18000c102  test    eax, eax
0x18000c104  js      loc_18000C192
0x18000c10a  mov     [rbp+arg_0], rsi
0x18000c10e  mov     rcx, [rbp+arg_10]
0x18000c112  mov     rax, [rcx]
0x18000c115  lea     rdx, [rbp+arg_0]
0x18000c119  mov     [rsp+70h+ppstgOpen], rdx
0x18000c11e  mov     [rsp+70h+reserved], esi
0x18000c122  mov     r9d, 10h
0x18000c128  xor     r8d, r8d
0x18000c12b  lea     rdx, aNtDiskquotaImp; "NT DISKQUOTA IMPORTEXPORT"
0x18000c132  mov     rax, [rax+20h]
0x18000c136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c13b  mov     ebx, eax
0x18000c13d  test    eax, eax
0x18000c13f  js      short loc_18000C179
0x18000c141  mov     rdx, [rbp+arg_0]; struct IStream *
0x18000c145  lea     rcx, [rbp+var_30]; this
0x18000c149  call    ??0Source@Importer@DetailsView@@QEAA@PEAUIStream@@@Z; DetailsView::Importer::Source::Source(IStream *)
0x18000c14e  nop
0x18000c14f  lea     rdx, [rbp+var_30]; struct DetailsView::Importer::Source *
0x18000c153  mov     rcx, rdi; this
0x18000c156  call    ?Import@Importer@DetailsView@@AEAAJAEAVSource@12@@Z; DetailsView::Importer::Import(DetailsView::Importer::Source &)
0x18000c15b  mov     ebx, eax
0x18000c15d  mov     rcx, [rbp+arg_0]
0x18000c161  mov     rax, [rcx]
0x18000c164  mov     rax, [rax+10h]
0x18000c168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c16d  nop
0x18000c16e  lea     rcx, [rbp+var_30]; this
0x18000c172  call    ??1Source@Importer@DetailsView@@UEAA@XZ; DetailsView::Importer::Source::~Source(void)
0x18000c177  jmp     short loc_18000C17E
0x18000c179  mov     esi, 1
0x18000c17e  mov     rcx, [rbp+arg_10]
0x18000c182  mov     rax, [rcx]
0x18000c185  mov     rax, [rax+10h]
0x18000c189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c18e  test    ebx, ebx
0x18000c190  jns     short loc_18000C20A
0x18000c192  cmp     ebx, 80030002h
0x18000c198  jz      short loc_18000C1E5
0x18000c19a  cmp     ebx, 80030004h
0x18000c1a0  jz      short loc_18000C1DE
0x18000c1a2  cmp     ebx, 80030005h
0x18000c1a8  jz      short loc_18000C1D7
0x18000c1aa  cmp     ebx, 80030008h
0x18000c1b0  jz      short loc_18000C1D0
0x18000c1b2  cmp     ebx, 800300FCh
0x18000c1b8  jz      short loc_18000C1C9
0x18000c1ba  cmp     ebx, 8007000Eh
0x18000c1c0  jz      short loc_18000C1D0
0x18000c1c2  mov     edx, 9E90h
0x18000c1c7  jmp     short loc_18000C1F2
0x18000c1c9  mov     edx, 9E93h
0x18000c1ce  jmp     short loc_18000C1F2
0x18000c1d0  mov     edx, 9E92h
0x18000c1d5  jmp     short loc_18000C1F2
0x18000c1d7  mov     edx, 9E91h
0x18000c1dc  jmp     short loc_18000C1F2
0x18000c1de  mov     edx, 9E94h
0x18000c1e3  jmp     short loc_18000C1F2
0x18000c1e5  neg     esi
0x18000c1e7  sbb     edx, edx
0x18000c1e9  and     edx, 0FFFFFFFAh
0x18000c1ec  add     edx, 9E95h; unsigned int
0x18000c1f2  mov     rcx, [rdi+38h]
0x18000c1f6  test    rcx, rcx
0x18000c1f9  jnz     short loc_18000C1FF
0x18000c1fb  mov     rcx, [rdi+40h]; hWnd
0x18000c1ff  mov     r9d, 10h; unsigned int
0x18000c205  call    ?DiskQuotaMsgBox@@YAHPEAUHWND__@@III@Z; DiskQuotaMsgBox(HWND__ *,uint,uint,uint)
0x18000c20a  mov     eax, ebx
0x18000c20c  mov     rbx, [rsp+70h+arg_8]
0x18000c214  add     rsp, 70h
0x18000c218  pop     rdi
0x18000c219  pop     rsi
0x18000c21a  pop     rbp
0x18000c21b  retn
```
