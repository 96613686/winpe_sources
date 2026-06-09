# DetailsView::OnCmdProperties(void)

- ea: `0x18000d800`
- end: `0x18000da55`
- name: `?OnCmdProperties@DetailsView@@AEAA_JXZ`
- size: `597`
- prototype: `__int64 __fastcall(DetailsView *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x18000de10`
- `0x18000eb10`

## callees

- `0x180006ea4`
- `0x18000d800`
- `0x18001101c`
- `0x180011160`
- `0x1800112e8`
- `0x180016f08`
- `0x180017060`
- `0x180018298`
- `0x18001c718`
- `0x18001c81c`
- `0x18001ce34`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d936`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d936`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d8cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d8f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d8cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d8f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d9ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d9ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d839`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d839`
- `USER32!SendMessageW` at `0x18000d875`
- `USER32!SendMessageW` at `0x18000d94e`
- `USER32!SendMessageW` at `0x18000d875`
- `USER32!SendMessageW` at `0x18000d94e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DetailsView::OnCmdProperties(DetailsView *this)
{
  signed int v2; // eax
  signed int v3; // esi
  int v4; // ebx
  void *pitem; // [rsp+30h] [rbp-D0h] BYREF
  signed int v7; // [rsp+38h] [rbp-C8h]
  int v8; // [rsp+3Ch] [rbp-C4h]
  __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  void **v10; // [rsp+48h] [rbp-B8h] BYREF
  HDSA hdsa; // [rsp+50h] [rbp-B0h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+58h] [rbp-A8h] BYREF
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+80h] [rbp-80h]
  int v14; // [rsp+88h] [rbp-78h]
  struct _RTL_CRITICAL_SECTION *p_CriticalSection; // [rsp+90h] [rbp-70h]
  int v16; // [rsp+98h] [rbp-68h]
  _BYTE v17[208]; // [rsp+A0h] [rbp-60h] BYREF
  void *pExceptionObject; // [rsp+190h] [rbp+90h] BYREF

  v9 = *((_QWORD *)this + 13);
  v10 = &StructureList::`vftable';
  if ( !InitializeCriticalSectionAndSpinCount(&CriticalSection, 0) )
  {
    CAllocException::CAllocException((CAllocException *)&pExceptionObject);
    throw (CAllocException *)&pExceptionObject;
  }
  hdsa = DSA_Create(16, 10);
  if ( !hdsa )
  {
    DeleteCriticalSection(&CriticalSection);
    CAllocException::CAllocException((CAllocException *)&pExceptionObject);
    throw (CAllocException *)&pExceptionObject;
  }
  v2 = SendMessageW(*((HWND *)this + 13), 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
  v3 = v2;
  while ( v2 != -1 )
  {
    pExceptionObject = 0;
    if ( PointerList::Retrieve((DetailsView *)((char *)this + 40), &pExceptionObject, v3) )
    {
      v8 = 0;
      pitem = pExceptionObject;
      v7 = v3;
      p_CriticalSection = &CriticalSection;
      EnterCriticalSection(&CriticalSection);
      v16 = 1;
      v4 = *(_DWORD *)hdsa;
      v13 = &CriticalSection;
      EnterCriticalSection(&CriticalSection);
      v14 = 1;
      if ( DSA_InsertItem(hdsa, v4, &pitem) < 0 )
      {
        CAllocException::CAllocException((CAllocException *)&pExceptionObject);
        throw (CAllocException *)&pExceptionObject;
      }
      v14 = 0;
      LeaveCriticalSection(&CriticalSection);
      v16 = 0;
      LeaveCriticalSection(&CriticalSection);
    }
    v2 = SendMessageW(*((HWND *)this + 13), 0x100Cu, v3, 2);
    v3 = v2;
  }
  if ( (int)StructureList::Count((StructureList *)&v10) > 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 22) + 8LL))(*((_QWORD *)this + 22));
    UserPropSheet::UserPropSheet(
      (UserPropSheet *)v17,
      *((struct IDiskQuotaControl **)this + 22),
      (DetailsView *)((char *)this + 248),
      *((HWND *)this + 13),
      (struct LVSelection *)&v9,
      *((struct UndoList **)this + 24));
    UserPropSheet::Run((UserPropSheet *)v17);
    UserPropSheet::~UserPropSheet((UserPropSheet *)v17);
  }
  StructureList::~StructureList((StructureList *)&v10);
  return 0;
}

```

## disassembly

```asm
0x18000d800  mov     [rsp-8+arg_8], rbx
0x18000d805  mov     [rsp-8+arg_10], rsi
0x18000d80a  push    rbp
0x18000d80b  push    rdi
0x18000d80c  push    r14
0x18000d80e  lea     rbp, [rsp-70h]
0x18000d813  sub     rsp, 170h
0x18000d81a  mov     rdi, rcx
0x18000d81d  mov     rax, [rcx+68h]
0x18000d821  mov     [rsp+180h+var_140], rax
0x18000d826  lea     rax, ??_7StructureList@@6B@; const StructureList::`vftable'
0x18000d82d  mov     [rsp+180h+var_138], rax
0x18000d832  xor     edx, edx; dwSpinCount
0x18000d834  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x18000d839  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d83f  test    eax, eax
0x18000d841  jz      loc_18000DA35
0x18000d847  mov     edx, 0Ah; cItemGrow
0x18000d84c  lea     ecx, [rdx+6]; cbItem
0x18000d84f  call    DSA_Create
0x18000d854  mov     [rsp+180h+hdsa], rax
0x18000d859  test    rax, rax
0x18000d85c  jz      loc_18000D9EA
0x18000d862  mov     r9d, 2; lParam
0x18000d868  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18000d86c  mov     edx, 100Ch; Msg
0x18000d871  mov     rcx, [rdi+68h]; hWnd
0x18000d875  call    cs:__imp_SendMessageW
0x18000d87b  mov     rsi, rax
0x18000d87e  jmp     loc_18000D956
0x18000d883  mov     [rbp+80h+pExceptionObject], 0
0x18000d88e  mov     r8d, esi; unsigned int
0x18000d891  lea     rdx, [rbp+80h+pExceptionObject]; void **
0x18000d898  lea     rcx, [rdi+28h]; this
0x18000d89c  call    ?Retrieve@PointerList@@QEAAHPEAPEAXI@Z; PointerList::Retrieve(void * *,uint)
0x18000d8a1  test    eax, eax
0x18000d8a3  jz      loc_18000D93C
0x18000d8a9  mov     [rsp+180h+var_144], 0
0x18000d8b1  mov     rax, [rbp+80h+pExceptionObject]
0x18000d8b8  mov     [rsp+180h+pitem], rax
0x18000d8bd  mov     [rsp+180h+var_148], esi
0x18000d8c1  lea     rax, [rsp+180h+CriticalSection]
0x18000d8c6  mov     [rbp+80h+var_F0], rax
0x18000d8ca  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x18000d8cf  call    cs:__imp_EnterCriticalSection
0x18000d8d5  mov     [rbp+80h+var_E8], 1
0x18000d8dc  mov     rax, [rsp+180h+hdsa]
0x18000d8e1  mov     ebx, [rax]
0x18000d8e3  lea     rax, [rsp+180h+CriticalSection]
0x18000d8e8  mov     [rbp+80h+var_100], rax
0x18000d8ec  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x18000d8f1  call    cs:__imp_EnterCriticalSection
0x18000d8f7  mov     [rbp+80h+var_F8], 1
0x18000d8fe  lea     r8, [rsp+180h+pitem]; pitem
0x18000d903  mov     edx, ebx; i
0x18000d905  mov     rcx, [rsp+180h+hdsa]; hdsa
0x18000d90a  call    DSA_InsertItem
0x18000d90f  test    eax, eax
0x18000d911  js      loc_18000DA15
0x18000d917  mov     [rbp+80h+var_F8], 0
0x18000d91e  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x18000d923  call    cs:__imp_LeaveCriticalSection
0x18000d929  nop
0x18000d92a  mov     [rbp+80h+var_E8], 0
0x18000d931  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x18000d936  call    cs:__imp_LeaveCriticalSection
0x18000d93c  movsxd  r8, esi; wParam
0x18000d93f  mov     edx, 100Ch; Msg
0x18000d944  mov     r9d, 2; lParam
0x18000d94a  mov     rcx, [rdi+68h]; hWnd
0x18000d94e  call    cs:__imp_SendMessageW
0x18000d954  mov     esi, eax
0x18000d956  cmp     eax, 0FFFFFFFFh
0x18000d959  jnz     loc_18000D883
0x18000d95f  lea     rcx, [rsp+180h+var_138]; this
0x18000d964  call    ?Count@StructureList@@QEAAIXZ; StructureList::Count(void)
0x18000d969  test    eax, eax
0x18000d96b  jle     short loc_18000D9C6
0x18000d96d  mov     rcx, [rdi+0B0h]
0x18000d974  mov     rax, [rcx]
0x18000d977  mov     rax, [rax+8]
0x18000d97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d980  lea     r8, [rdi+0F8h]; struct CVolumeID *
0x18000d987  mov     rax, [rdi+0C0h]
0x18000d98e  mov     [rsp+180h+var_158], rax; struct UndoList *
0x18000d993  lea     rax, [rsp+180h+var_140]
0x18000d998  mov     [rsp+180h+var_160], rax; struct LVSelection *
0x18000d99d  mov     r9, [rdi+68h]; HWND
0x18000d9a1  mov     rdx, [rdi+0B0h]; struct IDiskQuotaControl *
0x18000d9a8  lea     rcx, [rbp+80h+var_E0]; this
0x18000d9ac  call    ??0UserPropSheet@@QEAA@PEAUIDiskQuotaControl@@AEBVCVolumeID@@PEAUHWND__@@AEAVLVSelection@@AEAVUndoList@@@Z; UserPropSheet::UserPropSheet(IDiskQuotaControl *,CVolumeID const &,HWND__ *,LVSelection &,UndoList &)
0x18000d9b1  nop
0x18000d9b2  lea     rcx, [rbp+80h+var_E0]; this
0x18000d9b6  call    ?Run@UserPropSheet@@QEAAJXZ; UserPropSheet::Run(void)
0x18000d9bb  nop
0x18000d9bc  lea     rcx, [rbp+80h+var_E0]; this
0x18000d9c0  call    ??1UserPropSheet@@QEAA@XZ; UserPropSheet::~UserPropSheet(void)
0x18000d9c5  nop
0x18000d9c6  lea     rcx, [rsp+180h+var_138]; this
0x18000d9cb  call    ??1StructureList@@UEAA@XZ; StructureList::~StructureList(void)
0x18000d9d0  xor     eax, eax
0x18000d9d2  lea     r11, [rsp+180h+var_10]
0x18000d9da  mov     rbx, [r11+28h]
0x18000d9de  mov     rsi, [r11+30h]
0x18000d9e2  mov     rsp, r11
0x18000d9e5  pop     r14
0x18000d9e7  pop     rdi
0x18000d9e8  pop     rbp
0x18000d9e9  retn
0x18000d9ea  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x18000d9ef  call    cs:__imp_DeleteCriticalSection
0x18000d9f5  lea     rcx, [rbp+80h+pExceptionObject]; this
0x18000d9fc  call    ??0CAllocException@@QEAA@XZ; CAllocException::CAllocException(void)
0x18000da01  lea     rdx, _TI3?AVCAllocException@@; pThrowInfo
0x18000da08  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18000da0f  call    _CxxThrowException_0
0x18000da15  lea     rcx, [rbp+80h+pExceptionObject]; this
0x18000da1c  call    ??0CAllocException@@QEAA@XZ; CAllocException::CAllocException(void)
0x18000da21  lea     rdx, _TI3?AVCAllocException@@; pThrowInfo
0x18000da28  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18000da2f  call    _CxxThrowException_0
0x18000da35  lea     rcx, [rbp+80h+pExceptionObject]; this
0x18000da3c  call    ??0CAllocException@@QEAA@XZ; CAllocException::CAllocException(void)
0x18000da41  lea     rdx, _TI3?AVCAllocException@@; pThrowInfo
0x18000da48  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18000da4f  call    _CxxThrowException_0
```
