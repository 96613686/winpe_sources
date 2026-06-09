# DetailsView::~DetailsView(void)

- ea: `0x1800078d0`
- end: `0x180007a55`
- name: `??1DetailsView@@QEAA@XZ`
- size: `389`
- prototype: `void __fastcall(DetailsView *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000f4d0`
- `0x1800190e4`

## callees

- `0x180001534`
- `0x180007894`
- `0x1800078d0`
- `0x18000f564`
- `0x180010fc4`
- `0x180016b5c`
- `0x180019ee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007979`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DetailsView::~DetailsView(DetailsView *this)
{
  PointerList *v2; // rbx
  void *v3; // rbx
  void *v4; // rcx

  *(_QWORD *)this = &DetailsView::`vftable'{for `IDiskQuotaEvents'};
  *((_QWORD *)this + 1) = &DetailsView::`vftable'{for `IDropSource'};
  *((_QWORD *)this + 2) = &DetailsView::`vftable'{for `IDropTarget'};
  *((_QWORD *)this + 3) = &DetailsView::`vftable'{for `IDataObject'};
  DetailsView::ReleaseObjects(this);
  operator delete(*((void **)this + 23), 0x20u);
  v2 = (PointerList *)*((_QWORD *)this + 24);
  if ( v2 )
  {
    UndoList::Clear(*((UndoList **)this + 24));
    PointerList::~PointerList(v2);
    operator delete(v2, 0x48u);
  }
  v3 = (void *)*((_QWORD *)this + 30);
  if ( v3 )
  {
    DetailsView::DataObject::~DataObject(*((DetailsView::DataObject **)this + 30));
    operator delete(v3, 0x28u);
  }
  if ( *((_DWORD *)this + 168) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  CString::~CString((DetailsView *)((char *)this + 480));
  CString::~CString((DetailsView *)((char *)this + 464));
  CString::~CString((DetailsView *)((char *)this + 448));
  CString::~CString((DetailsView *)((char *)this + 432));
  CString::~CString((DetailsView *)((char *)this + 416));
  CString::~CString((DetailsView *)((char *)this + 400));
  CString::~CString((DetailsView *)((char *)this + 384));
  CString::~CString((DetailsView *)((char *)this + 368));
  CString::~CString((DetailsView *)((char *)this + 352));
  CString::~CString((DetailsView *)((char *)this + 336));
  CString::~CString((DetailsView *)((char *)this + 320));
  CString::~CString((DetailsView *)((char *)this + 304));
  CString::~CString((DetailsView *)((char *)this + 280));
  CString::~CString((DetailsView *)((char *)this + 264));
  CString::~CString((DetailsView *)((char *)this + 248));
  v4 = (void *)*((_QWORD *)this + 25);
  if ( v4 )
    LocalFree(v4);
  PointerList::~PointerList((DetailsView *)((char *)this + 40));
}

```

## disassembly

```asm
0x1800078d0  mov     [rsp+arg_0], rbx
0x1800078d5  push    rdi
0x1800078d6  sub     rsp, 20h
0x1800078da  mov     rdi, rcx
0x1800078dd  lea     rax, ??_7DetailsView@@6BIDiskQuotaEvents@@@; const DetailsView::`vftable'{for `IDiskQuotaEvents'}
0x1800078e4  mov     [rcx], rax
0x1800078e7  lea     rax, ??_7DetailsView@@6BIDropSource@@@; const DetailsView::`vftable'{for `IDropSource'}
0x1800078ee  mov     [rcx+8], rax
0x1800078f2  lea     rax, ??_7DetailsView@@6BIDropTarget@@@; const DetailsView::`vftable'{for `IDropTarget'}
0x1800078f9  mov     [rcx+10h], rax
0x1800078fd  lea     rax, ??_7DetailsView@@6BIDataObject@@@; const DetailsView::`vftable'{for `IDataObject'}
0x180007904  mov     [rcx+18h], rax
0x180007908  call    ?ReleaseObjects@DetailsView@@AEAAJXZ; DetailsView::ReleaseObjects(void)
0x18000790d  mov     edx, 20h ; ' '; unsigned __int64
0x180007912  mov     rcx, [rdi+0B8h]; void *
0x180007919  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000791e  mov     rbx, [rdi+0C0h]
0x180007925  test    rbx, rbx
0x180007928  jz      short loc_180007948
0x18000792a  mov     rcx, rbx; this
0x18000792d  call    ?Clear@UndoList@@QEAAXXZ; UndoList::Clear(void)
0x180007932  mov     rcx, rbx; this
0x180007935  call    ??1PointerList@@UEAA@XZ; PointerList::~PointerList(void)
0x18000793a  nop
0x18000793b  mov     edx, 48h ; 'H'; unsigned __int64
0x180007940  mov     rcx, rbx; void *
0x180007943  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007948  mov     rbx, [rdi+0F0h]
0x18000794f  test    rbx, rbx
0x180007952  jz      short loc_180007969
0x180007954  mov     rcx, rbx; this
0x180007957  call    ??1DataObject@DetailsView@@QEAA@XZ; DetailsView::DataObject::~DataObject(void)
0x18000795c  mov     edx, 28h ; '('; unsigned __int64
0x180007961  mov     rcx, rbx; void *
0x180007964  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007969  cmp     dword ptr [rdi+2A0h], 0
0x180007970  jz      short loc_18000797F
0x180007972  lea     rcx, [rdi+210h]; lpCriticalSection
0x180007979  call    cs:__imp_DeleteCriticalSection
0x18000797f  lea     rcx, [rdi+1E0h]; this
0x180007986  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18000798b  lea     rcx, [rdi+1D0h]; this
0x180007992  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180007997  lea     rcx, [rdi+1C0h]; this
0x18000799e  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800079a3  lea     rcx, [rdi+1B0h]; this
0x1800079aa  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800079af  lea     rcx, [rdi+1A0h]; this
0x1800079b6  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800079bb  lea     rcx, [rdi+190h]; this
0x1800079c2  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800079c7  lea     rcx, [rdi+180h]; this
0x1800079ce  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800079d3  lea     rcx, [rdi+170h]; this
0x1800079da  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800079df  lea     rcx, [rdi+160h]; this
0x1800079e6  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800079eb  lea     rcx, [rdi+150h]; this
0x1800079f2  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800079f7  lea     rcx, [rdi+140h]; this
0x1800079fe  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180007a03  lea     rcx, [rdi+130h]; this
0x180007a0a  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180007a0f  lea     rbx, [rdi+0F8h]
0x180007a16  lea     rcx, [rbx+20h]; this
0x180007a1a  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180007a1f  lea     rcx, [rbx+10h]; this
0x180007a23  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180007a28  mov     rcx, rbx; this
0x180007a2b  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180007a30  mov     rcx, [rdi+0C8h]; hMem
0x180007a37  test    rcx, rcx
0x180007a3a  jz      short loc_180007A42
0x180007a3c  call    cs:__imp_LocalFree
0x180007a42  lea     rcx, [rdi+28h]; this
0x180007a46  mov     rbx, [rsp+28h+arg_0]
0x180007a4b  add     rsp, 20h
0x180007a4f  pop     rdi
0x180007a50  jmp     ??1PointerList@@UEAA@XZ; PointerList::~PointerList(void)
```
