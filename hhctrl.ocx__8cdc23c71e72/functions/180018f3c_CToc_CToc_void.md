# CToc::~CToc(void)

- ea: `0x180018f3c`
- end: `0x180019149`
- name: `??1CToc@@UEAA@XZ`
- size: `525`
- prototype: `void __fastcall(CToc *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180019180`

## callees

- `0x180003fc0`
- `0x180006708`
- `0x180011104`
- `0x180011ab8`
- `0x180018f3c`
- `0x180019150`
- `0x180019590`
- `0x180053e40`
- `0x180078010`

## import_xrefs

- `msvcrt!free` at `0x1800190d4`
- `msvcrt!free` at `0x180019114`
- `msvcrt!free` at `0x1800190d4`
- `msvcrt!free` at `0x180019114`
- `USER32!RemovePropA` at `0x18001907a`
- `USER32!RemovePropA` at `0x18001907a`
- `USER32!DestroyWindow` at `0x180019087`
- `USER32!DestroyWindow` at `0x180019087`
- `USER32!SendMessageA` at `0x180018f9d`
- `USER32!SendMessageA` at `0x180018fd8`
- `USER32!SendMessageA` at `0x180019017`
- `USER32!SendMessageA` at `0x180018f9d`
- `USER32!SendMessageA` at `0x180018fd8`
- `USER32!SendMessageA` at `0x180019017`
- `GDI32!DeleteObject` at `0x180019099`
- `GDI32!DeleteObject` at `0x1800190bd`
- `GDI32!DeleteObject` at `0x1800190e6`
- `GDI32!DeleteObject` at `0x180019099`
- `GDI32!DeleteObject` at `0x1800190bd`
- `GDI32!DeleteObject` at `0x1800190e6`

## pseudocode

```c
void __fastcall CToc::~CToc(CToc *this, unsigned int a2)
{
  CInfoType *v3; // rcx
  struct _TREEITEM *v4; // rdi
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  void *v6; // rcx
  int v7; // eax
  int v8; // edi
  void *v9; // rcx
  void *v10; // rcx
  struct tagTVITEMW lParam; // [rsp+20h] [rbp-40h] BYREF

  *(_QWORD *)this = &CToc::`vftable';
  v3 = (CInfoType *)*((_QWORD *)this + 70);
  if ( v3 )
    CInfoType::`scalar deleting destructor'(v3, a2);
  if ( *((_DWORD *)this + 2) )
  {
    memset(&lParam, 0, sizeof(lParam));
    v4 = (struct _TREEITEM *)SendMessageA(*((HWND *)this + 53), 0x110Au, 0, 0);
    for ( lParam.hItem = v4; v4; lParam.hItem = v4 )
    {
      FreeChildrenAllocations(*((HWND *)this + 53), v4);
      v4 = (struct _TREEITEM *)SendMessageA(*((HWND *)this + 53), 0x110Au, 1u, (LPARAM)lParam.hItem);
      lParam.mask = 4;
      if ( W_TreeView_GetItem_fn(*((HWND *)this + 53), &lParam) == 1 )
      {
        if ( lParam.lParam )
        {
          SendMessageA(*((HWND *)this + 53), 0x1101u, 0, (LPARAM)lParam.hItem);
          if ( lParam.lParam )
            (**(void (__fastcall ***)(LPARAM, __int64))lParam.lParam)(lParam.lParam, 1);
        }
      }
    }
  }
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v5 )
    (**v5)(v5, 1);
  if ( (unsigned int)IsValidWindow(*((HWND *)this + 53)) )
  {
    RemovePropA(*((HWND *)this + 53), "HHDefProc");
    DestroyWindow(*((HWND *)this + 53));
  }
  v6 = (void *)*((_QWORD *)this + 56);
  if ( v6 )
    DeleteObject(v6);
  v7 = *((_DWORD *)this + 116);
  if ( v7 )
  {
    v8 = 0;
    if ( v7 > 0 )
    {
      do
        DeleteObject(*(HGDIOBJ *)(*((_QWORD *)this + 59) + 8LL * v8++));
      while ( v8 < *((_DWORD *)this + 116) );
    }
    free(*((void **)this + 59));
  }
  v9 = (void *)*((_QWORD *)this + 54);
  if ( v9 )
    DeleteObject(v9);
  if ( *((_QWORD *)this + 61) )
  {
    IsolationAwareImageList_Destroy();
    *((_QWORD *)this + 61) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 48);
  if ( v10 )
    free(v10);
  CWStr::~CWStr((CToc *)((char *)this + 544));
  CSiteMap::~CSiteMap((CToc *)((char *)this + 32));
  *(_QWORD *)this = &INavUI::`vftable';
}

```

## disassembly

```asm
0x180018f3c  mov     [rsp-8+arg_0], rbx
0x180018f41  mov     [rsp-8+arg_8], rdi
0x180018f46  push    rbp
0x180018f47  mov     rbp, rsp
0x180018f4a  sub     rsp, 60h
0x180018f4e  mov     rbx, rcx
0x180018f51  lea     rax, ??_7CToc@@6B@; const CToc::`vftable'
0x180018f58  mov     [rcx], rax
0x180018f5b  mov     rcx, [rcx+230h]; this
0x180018f62  test    rcx, rcx
0x180018f65  jz      short loc_180018F6C
0x180018f67  call    ??_GCInfoType@@QEAAPEAXI@Z; CInfoType::`scalar deleting destructor'(uint)
0x180018f6c  cmp     dword ptr [rbx+8], 0
0x180018f70  jz      loc_180019043
0x180018f76  xorps   xmm0, xmm0
0x180018f79  xor     eax, eax
0x180018f7b  movups  xmmword ptr [rbp+lParam], xmm0
0x180018f7f  movups  [rbp+var_30], xmm0
0x180018f83  movups  [rbp+var_20], xmm0
0x180018f87  mov     [rbp+var_10], rax
0x180018f8b  xor     r9d, r9d; lParam
0x180018f8e  xor     r8d, r8d; wParam
0x180018f91  mov     edx, 110Ah; Msg
0x180018f96  mov     rcx, [rbx+1A8h]; hWnd
0x180018f9d  call    cs:__imp_SendMessageA
0x180018fa3  mov     rdi, rax
0x180018fa6  mov     [rbp+lParam+8], rax
0x180018faa  test    rax, rax
0x180018fad  jz      loc_180019043
0x180018fb3  mov     rdx, rdi; struct _TREEITEM *
0x180018fb6  mov     rcx, [rbx+1A8h]; hWnd
0x180018fbd  call    ?FreeChildrenAllocations@@YAXPEAUHWND__@@PEAU_TREEITEM@@@Z; FreeChildrenAllocations(HWND__ *,_TREEITEM *)
0x180018fc2  mov     r9, [rbp+lParam+8]; lParam
0x180018fc6  mov     edx, 110Ah; Msg
0x180018fcb  mov     r8d, 1; wParam
0x180018fd1  mov     rcx, [rbx+1A8h]; hWnd
0x180018fd8  call    cs:__imp_SendMessageA
0x180018fde  mov     rdi, rax
0x180018fe1  mov     dword ptr [rbp+lParam], 4
0x180018fe8  lea     rdx, [rbp+lParam]; struct tagTVITEMW *
0x180018fec  mov     rcx, [rbx+1A8h]; HWND
0x180018ff3  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x180018ff8  cmp     eax, 1
0x180018ffb  jnz     short loc_180019036
0x180018ffd  cmp     [rbp+var_10], 0
0x180019002  jz      short loc_180019036
0x180019004  mov     r9, [rbp+lParam+8]; lParam
0x180019008  xor     r8d, r8d; wParam
0x18001900b  mov     edx, 1101h; Msg
0x180019010  mov     rcx, [rbx+1A8h]; hWnd
0x180019017  call    cs:__imp_SendMessageA
0x18001901d  mov     rcx, [rbp+var_10]
0x180019021  test    rcx, rcx
0x180019024  jz      short loc_180019036
0x180019026  mov     rax, [rcx]
0x180019029  mov     edx, 1
0x18001902e  mov     rax, [rax]
0x180019031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019036  mov     [rbp+lParam+8], rdi
0x18001903a  test    rdi, rdi
0x18001903d  jnz     loc_180018FB3
0x180019043  mov     rcx, [rbx+10h]
0x180019047  test    rcx, rcx
0x18001904a  jz      short loc_18001905C
0x18001904c  mov     rax, [rcx]
0x18001904f  mov     edx, 1
0x180019054  mov     rax, [rax]
0x180019057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001905c  mov     rcx, [rbx+1A8h]; HWND
0x180019063  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180019068  test    eax, eax
0x18001906a  jz      short loc_18001908D
0x18001906c  lea     rdx, aHhdefproc; "HHDefProc"
0x180019073  mov     rcx, [rbx+1A8h]; hWnd
0x18001907a  call    cs:__imp_RemovePropA
0x180019080  mov     rcx, [rbx+1A8h]; hWnd
0x180019087  call    cs:__imp_DestroyWindow
0x18001908d  mov     rcx, [rbx+1C0h]; ho
0x180019094  test    rcx, rcx
0x180019097  jz      short loc_18001909F
0x180019099  call    cs:__imp_DeleteObject
0x18001909f  mov     eax, [rbx+1D0h]
0x1800190a5  test    eax, eax
0x1800190a7  jz      short loc_1800190DA
0x1800190a9  xor     edi, edi
0x1800190ab  test    eax, eax
0x1800190ad  jle     short loc_1800190CD
0x1800190af  movsxd  rax, edi
0x1800190b2  mov     rcx, [rbx+1D8h]
0x1800190b9  mov     rcx, [rcx+rax*8]; ho
0x1800190bd  call    cs:__imp_DeleteObject
0x1800190c3  inc     edi
0x1800190c5  cmp     edi, [rbx+1D0h]
0x1800190cb  jl      short loc_1800190AF
0x1800190cd  mov     rcx, [rbx+1D8h]; Block
0x1800190d4  call    cs:__imp_free
0x1800190da  mov     rcx, [rbx+1B0h]; ho
0x1800190e1  test    rcx, rcx
0x1800190e4  jz      short loc_1800190EC
0x1800190e6  call    cs:__imp_DeleteObject
0x1800190ec  mov     rcx, [rbx+1E8h]
0x1800190f3  test    rcx, rcx
0x1800190f6  jz      short loc_180019108
0x1800190f8  call    IsolationAwareImageList_Destroy
0x1800190fd  mov     qword ptr [rbx+1E8h], 0
0x180019108  mov     rcx, [rbx+180h]; Block
0x18001910f  test    rcx, rcx
0x180019112  jz      short loc_18001911A
0x180019114  call    cs:__imp_free
0x18001911a  lea     rcx, [rbx+220h]; this
0x180019121  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180019126  lea     rcx, [rbx+20h]; this
0x18001912a  call    ??1CSiteMap@@UEAA@XZ; CSiteMap::~CSiteMap(void)
0x18001912f  lea     rax, ??_7INavUI@@6B@; const INavUI::`vftable'
0x180019136  mov     [rbx], rax
0x180019139  mov     rbx, [rsp+60h+arg_0]
0x18001913e  mov     rdi, [rsp+60h+arg_8]
0x180019143  add     rsp, 60h
0x180019147  pop     rbp
0x180019148  retn
```
