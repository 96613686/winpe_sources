# CToolbar::TB_OnDestroy(void)

- ea: `0x1800c44a4`
- end: `0x1800c46d9`
- name: `?TB_OnDestroy@CToolbar@@AEAAXXZ`
- size: `565`
- prototype: `void __fastcall(CToolbar *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800134f0`

## callees

- `0x1800168c0`
- `0x180034b4c`
- `0x18003bbd0`
- `0x1800be380`
- `0x1800c44a4`
- `0x1800c46e0`
- `0x1800ef354`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c454f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c4632`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c46c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c454f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c4632`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c46c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c455d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c4640`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c46ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c455d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c4640`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c46ce`
- `GDI32!DeleteObject` at `0x1800c464b`
- `GDI32!DeleteObject` at `0x1800c4699`
- `GDI32!DeleteObject` at `0x1800c464b`
- `GDI32!DeleteObject` at `0x1800c4699`
- `USER32!DestroyWindow` at `0x1800c461c`
- `USER32!DestroyWindow` at `0x1800c461c`
- `USER32!SetWindowLongPtrW` at `0x1800c4599`
- `USER32!SetWindowLongPtrW` at `0x1800c4599`
- `USER32!IsWindow` at `0x1800c4607`
- `USER32!IsWindow` at `0x1800c4607`
- `UxTheme!CloseThemeData` at `0x1800c4677`
- `UxTheme!CloseThemeData` at `0x1800c4677`
- `UxTheme!BufferedPaintUnInit` at `0x1800c466c`
- `UxTheme!BufferedPaintUnInit` at `0x1800c466c`
- `UxTheme!BufferedPaintStopAllAnimations` at `0x1800c4666`
- `UxTheme!BufferedPaintStopAllAnimations` at `0x1800c4666`

## pseudocode

```c
void __fastcall CToolbar::TB_OnDestroy(CToolbar *this)
{
  HWND v2; // rsi
  int i; // ebx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rbx
  void *v7; // rbx
  HANDLE v8; // rax
  void *v9; // rcx
  void *v10; // rbx
  _QWORD *v11; // rcx
  HANDLE v12; // rax
  struct _IMAGELIST *v13; // rax
  HANDLE ProcessHeap; // rax

  v2 = (HWND)*((_QWORD *)this + 7);
  if ( (*((_DWORD *)this + 95) & 0x100000) != 0 )
  {
    BufferedPaintStopAllAnimations(*((HWND *)this + 7));
    BufferedPaintUnInit();
  }
  for ( i = 0; i < *((_DWORD *)this + 66); ++i )
  {
    v11 = (_QWORD *)(*((_QWORD *)this + 18) + 24LL + 80LL * i);
    if ( *v11 != -1 && *v11 >= 0x10000u )
      Str_Set(v11, 0);
  }
  if ( (*((_DWORD *)this + 18) & 0x100) != 0 && IsWindow(*((HWND *)this + 21)) )
  {
    DestroyWindow(*((HWND *)this + 21));
    *((_QWORD *)this + 21) = 0;
  }
  if ( *((_QWORD *)this + 38) )
    DestroyDragProxy();
  v4 = (void *)*((_QWORD *)this + 17);
  if ( v4 )
    DeleteObject(v4);
  CToolbar::ReleaseMonoDC(this);
  if ( *((int *)this + 56) > 0 )
    CToolbar::DestroyStrings(this);
  v5 = (void *)*((_QWORD *)this + 24);
  if ( v5 && (*((_BYTE *)this + 380) & 4) != 0 )
    DeleteObject(v5);
  if ( *((_QWORD *)this + 26) )
  {
    v13 = CToolbar::TBGetImageList(this, 0, 0);
    ImageList_DestroyPrivate(v13, 0);
  }
  v6 = (void *)*((_QWORD *)this + 26);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v7 = (void *)*((_QWORD *)this + 42);
  v8 = GetProcessHeap();
  HeapFree(v8, 0, v7);
  Str_Set((char *)this + 176, 0);
  v9 = (void *)*((_QWORD *)this + 51);
  if ( v9 )
    CloseThemeData(v9);
  v10 = (void *)*((_QWORD *)this + 18);
  if ( v10 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v10);
  }
  SetWindowLongPtrW(v2, 0, 0);
  (**(void (__fastcall ***)(CToolbar *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x1800c44a4  mov     [rsp+arg_0], rbx
0x1800c44a9  mov     [rsp+arg_8], rsi
0x1800c44ae  push    rdi
0x1800c44af  sub     rsp, 20h
0x1800c44b3  test    dword ptr [rcx+17Ch], 100000h
0x1800c44bd  mov     rdi, rcx
0x1800c44c0  mov     rsi, [rcx+38h]
0x1800c44c4  jnz     loc_1800C4663
0x1800c44ca  xor     ebx, ebx
0x1800c44cc  cmp     [rdi+108h], ebx
0x1800c44d2  jg      loc_1800C45C1
0x1800c44d8  test    dword ptr [rdi+48h], 100h
0x1800c44df  jnz     loc_1800C4600
0x1800c44e5  mov     rcx, [rdi+130h]
0x1800c44ec  test    rcx, rcx
0x1800c44ef  jnz     loc_1800C4682
0x1800c44f5  mov     rcx, [rdi+88h]; ho
0x1800c44fc  test    rcx, rcx
0x1800c44ff  jnz     loc_1800C464B
0x1800c4505  mov     rcx, rdi; this
0x1800c4508  call    ?ReleaseMonoDC@CToolbar@@AEAAXXZ; CToolbar::ReleaseMonoDC(void)
0x1800c450d  cmp     dword ptr [rdi+0E0h], 0
0x1800c4514  jg      loc_1800C4656
0x1800c451a  mov     rcx, [rdi+0C0h]; ho
0x1800c4521  test    rcx, rcx
0x1800c4524  jnz     loc_1800C468C
0x1800c452a  cmp     qword ptr [rdi+0D0h], 0
0x1800c4532  jnz     loc_1800C46A4
0x1800c4538  mov     rbx, [rdi+0D0h]
0x1800c453f  test    rbx, rbx
0x1800c4542  jnz     loc_1800C46C0
0x1800c4548  mov     rbx, [rdi+150h]
0x1800c454f  call    cs:__imp_GetProcessHeap
0x1800c4555  mov     r8, rbx; lpMem
0x1800c4558  xor     edx, edx; dwFlags
0x1800c455a  mov     rcx, rax; hHeap
0x1800c455d  call    cs:__imp_HeapFree
0x1800c4563  lea     rcx, [rdi+0B0h]
0x1800c456a  xor     edx, edx
0x1800c456c  call    Str_Set
0x1800c4571  mov     rcx, [rdi+198h]; hTheme
0x1800c4578  test    rcx, rcx
0x1800c457b  jnz     loc_1800C4677
0x1800c4581  mov     rbx, [rdi+90h]
0x1800c4588  test    rbx, rbx
0x1800c458b  jnz     loc_1800C4632
0x1800c4591  xor     r8d, r8d; dwNewLong
0x1800c4594  xor     edx, edx; nIndex
0x1800c4596  mov     rcx, rsi; hWnd
0x1800c4599  call    cs:__imp_SetWindowLongPtrW
0x1800c459f  mov     rax, [rdi]
0x1800c45a2  mov     edx, 1
0x1800c45a7  mov     rcx, rdi
0x1800c45aa  mov     rax, [rax]
0x1800c45ad  mov     rbx, [rsp+28h+arg_0]
0x1800c45b2  mov     rsi, [rsp+28h+arg_8]
0x1800c45b7  add     rsp, 20h
0x1800c45bb  pop     rdi
0x1800c45bc  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800c45c1  movsxd  rax, ebx
0x1800c45c4  lea     rcx, [rax+rax*4]
0x1800c45c8  mov     rax, [rdi+90h]
0x1800c45cf  add     rax, 18h
0x1800c45d3  shl     rcx, 4
0x1800c45d7  add     rcx, rax
0x1800c45da  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800c45de  jz      short loc_1800C45F0
0x1800c45e0  cmp     qword ptr [rcx], 10000h
0x1800c45e7  jb      short loc_1800C45F0
0x1800c45e9  xor     edx, edx
0x1800c45eb  call    Str_Set
0x1800c45f0  inc     ebx
0x1800c45f2  cmp     ebx, [rdi+108h]
0x1800c45f8  jge     loc_1800C44D8
0x1800c45fe  jmp     short loc_1800C45C1
0x1800c4600  mov     rcx, [rdi+0A8h]; hWnd
0x1800c4607  call    cs:__imp_IsWindow
0x1800c460d  test    eax, eax
0x1800c460f  jz      loc_1800C44E5
0x1800c4615  mov     rcx, [rdi+0A8h]; hWnd
0x1800c461c  call    cs:__imp_DestroyWindow
0x1800c4622  mov     qword ptr [rdi+0A8h], 0
0x1800c462d  jmp     loc_1800C44E5
0x1800c4632  call    cs:__imp_GetProcessHeap
0x1800c4638  mov     r8, rbx; lpMem
0x1800c463b  xor     edx, edx; dwFlags
0x1800c463d  mov     rcx, rax; hHeap
0x1800c4640  call    cs:__imp_HeapFree
0x1800c4646  jmp     loc_1800C4591
0x1800c464b  call    cs:__imp_DeleteObject
0x1800c4651  jmp     loc_1800C4505
0x1800c4656  mov     rcx, rdi; this
0x1800c4659  call    ?DestroyStrings@CToolbar@@AEAAXXZ; CToolbar::DestroyStrings(void)
0x1800c465e  jmp     loc_1800C451A
0x1800c4663  mov     rcx, rsi; hwnd
0x1800c4666  call    cs:__imp_BufferedPaintStopAllAnimations
0x1800c466c  call    cs:__imp_BufferedPaintUnInit
0x1800c4672  jmp     loc_1800C44CA
0x1800c4677  call    cs:__imp_CloseThemeData
0x1800c467d  jmp     loc_1800C4581
0x1800c4682  call    DestroyDragProxy
0x1800c4687  jmp     loc_1800C44F5
0x1800c468c  test    byte ptr [rdi+17Ch], 4
0x1800c4693  jz      loc_1800C452A
0x1800c4699  call    cs:__imp_DeleteObject
0x1800c469f  jmp     loc_1800C452A
0x1800c46a4  xor     r8d, r8d; int
0x1800c46a7  xor     edx, edx; int
0x1800c46a9  mov     rcx, rdi; this
0x1800c46ac  call    ?TBGetImageList@CToolbar@@AEAAPEAU_IMAGELIST@@HH@Z; CToolbar::TBGetImageList(int,int)
0x1800c46b1  xor     edx, edx
0x1800c46b3  mov     rcx, rax
0x1800c46b6  call    ImageList_DestroyPrivate
0x1800c46bb  jmp     loc_1800C4538
0x1800c46c0  call    cs:__imp_GetProcessHeap
0x1800c46c6  mov     r8, rbx; lpMem
0x1800c46c9  xor     edx, edx; dwFlags
0x1800c46cb  mov     rcx, rax; hHeap
0x1800c46ce  call    cs:__imp_HeapFree
0x1800c46d4  jmp     loc_1800C4548
```
