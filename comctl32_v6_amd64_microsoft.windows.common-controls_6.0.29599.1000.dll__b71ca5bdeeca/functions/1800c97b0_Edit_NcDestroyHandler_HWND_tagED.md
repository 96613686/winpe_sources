# Edit_NcDestroyHandler(HWND__ *,tagED *)

- ea: `0x1800c97b0`
- end: `0x1800c997e`
- name: `?Edit_NcDestroyHandler@@YAXPEAUHWND__@@PEAUtagED@@@Z`
- size: `462`
- prototype: `void(HWND, struct tagED *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180059720`

## callees

- `0x18008f108`
- `0x1800b7140`
- `0x1800c97b0`
- `0x180116cac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c9834`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c9854`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c987d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c989d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c98bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c9834`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c9854`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c987d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c989d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c98bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c9842`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c9862`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c988b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c98ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c98cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c9842`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c9862`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c988b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c98ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c98cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c9822`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c9822`
- `api-ms-win-core-heap-l2-1-0!LocalUnlock` at `0x1800c9819`
- `api-ms-win-core-heap-l2-1-0!LocalUnlock` at `0x1800c9819`
- `api-ms-win-core-heap-l2-1-0!LocalLock` at `0x1800c97f3`
- `api-ms-win-core-heap-l2-1-0!LocalLock` at `0x1800c97f3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800c97ff`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800c97ff`
- `GDI32!DeleteObject` at `0x1800c98dd`
- `GDI32!DeleteObject` at `0x1800c990f`
- `GDI32!DeleteObject` at `0x1800c9921`
- `GDI32!DeleteObject` at `0x1800c9933`
- `GDI32!DeleteObject` at `0x1800c98dd`
- `GDI32!DeleteObject` at `0x1800c990f`
- `GDI32!DeleteObject` at `0x1800c9921`
- `GDI32!DeleteObject` at `0x1800c9933`
- `USER32!SetWindowLongPtrW` at `0x1800c9977`
- `UxTheme!CloseThemeData` at `0x1800c98ef`
- `UxTheme!CloseThemeData` at `0x1800c98ef`
- `UxTheme!BufferedPaintUnInit` at `0x1800c97dd`
- `UxTheme!BufferedPaintUnInit` at `0x1800c97dd`
- `UxTheme!BufferedPaintStopAllAnimations` at `0x1800c97d7`
- `UxTheme!BufferedPaintStopAllAnimations` at `0x1800c97d7`

## pseudocode

```c
void __fastcall Edit_NcDestroyHandler(HWND a1, struct tagED *a2)
{
  _BYTE *v4; // rdi
  SIZE_T i; // rax
  void *v6; // rdi
  HANDLE ProcessHeap; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  void *v10; // rdi
  HANDLE v11; // rax
  void *v12; // rdi
  HANDLE v13; // rax
  void *v14; // rdi
  HANDLE v15; // rax
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx

  if ( a2 )
  {
    if ( (*((_BYTE *)a2 + 404) & 4) != 0 )
    {
      BufferedPaintStopAllAnimations(a1);
      BufferedPaintUnInit();
    }
    if ( (*(_BYTE *)(*((_QWORD *)a2 + 46) + 12LL) & 0x20) != 0 )
    {
      v4 = LocalLock(*(HLOCAL *)a2);
      for ( i = LocalSize(*(HLOCAL *)a2); i; --i )
        *v4++ = 0;
      LocalUnlock(*(HLOCAL *)a2);
    }
    LocalFree(*(HLOCAL *)a2);
    v6 = (void *)*((_QWORD *)a2 + 21);
    if ( v6 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
    v8 = (void *)*((_QWORD *)a2 + 29);
    if ( v8 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v8);
    }
    v10 = (void *)*((_QWORD *)a2 + 73);
    if ( v10 && *((void **)a2 + 16) != v10 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
    }
    v12 = (void *)*((_QWORD *)a2 + 16);
    if ( v12 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v12);
    }
    v14 = (void *)*((_QWORD *)a2 + 30);
    if ( v14 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
    }
    v16 = (void *)*((_QWORD *)a2 + 37);
    if ( v16 )
      DeleteObject(v16);
    v17 = (void *)*((_QWORD *)a2 + 45);
    if ( v17 )
      CloseThemeData(v17);
    Str_SetPtrW((LPWSTR *)a2 + 48, 0);
    v18 = (void *)*((_QWORD *)a2 + 53);
    if ( v18 )
      DeleteObject(v18);
    v19 = (void *)*((_QWORD *)a2 + 54);
    if ( v19 )
      DeleteObject(v19);
    v20 = (void *)*((_QWORD *)a2 + 24);
    if ( v20 )
      DeleteObject(v20);
    Str_SetPtrW((LPWSTR *)a2 + 51, 0);
    CCompositedDraw::~CCompositedDraw((struct tagED *)((char *)a2 + 520));
    operator delete(a2, 0x268u);
  }
  SetWindowLongPtrW(a1, 0, 0);
}

```

## disassembly

```asm
0x1800c97b0  mov     [rsp+arg_0], rbx
0x1800c97b5  mov     [rsp+arg_8], rsi
0x1800c97ba  push    rdi
0x1800c97bb  sub     rsp, 20h
0x1800c97bf  mov     rbx, rdx
0x1800c97c2  mov     rsi, rcx
0x1800c97c5  test    rdx, rdx
0x1800c97c8  jz      loc_1800C9960
0x1800c97ce  test    byte ptr [rdx+194h], 4
0x1800c97d5  jz      short loc_1800C97E3
0x1800c97d7  call    cs:__imp_BufferedPaintStopAllAnimations
0x1800c97dd  call    cs:__imp_BufferedPaintUnInit
0x1800c97e3  mov     rax, [rbx+170h]
0x1800c97ea  test    byte ptr [rax+0Ch], 20h
0x1800c97ee  jz      short loc_1800C981F
0x1800c97f0  mov     rcx, [rbx]; hMem
0x1800c97f3  call    cs:__imp_LocalLock
0x1800c97f9  mov     rcx, [rbx]; hMem
0x1800c97fc  mov     rdi, rax
0x1800c97ff  call    cs:__imp_LocalSize
0x1800c9805  test    rax, rax
0x1800c9808  jz      short loc_1800C9816
0x1800c980a  mov     byte ptr [rdi], 0
0x1800c980d  inc     rdi
0x1800c9810  sub     rax, 1
0x1800c9814  jnz     short loc_1800C980A
0x1800c9816  mov     rcx, [rbx]; hMem
0x1800c9819  call    cs:__imp_LocalUnlock
0x1800c981f  mov     rcx, [rbx]; hMem
0x1800c9822  call    cs:__imp_LocalFree
0x1800c9828  mov     rdi, [rbx+0A8h]
0x1800c982f  test    rdi, rdi
0x1800c9832  jz      short loc_1800C9848
0x1800c9834  call    cs:__imp_GetProcessHeap
0x1800c983a  mov     r8, rdi; lpMem
0x1800c983d  xor     edx, edx; dwFlags
0x1800c983f  mov     rcx, rax; hHeap
0x1800c9842  call    cs:__imp_HeapFree
0x1800c9848  mov     rdi, [rbx+0E8h]
0x1800c984f  test    rdi, rdi
0x1800c9852  jz      short loc_1800C9868
0x1800c9854  call    cs:__imp_GetProcessHeap
0x1800c985a  mov     r8, rdi; lpMem
0x1800c985d  xor     edx, edx; dwFlags
0x1800c985f  mov     rcx, rax; hHeap
0x1800c9862  call    cs:__imp_HeapFree
0x1800c9868  mov     rdi, [rbx+248h]
0x1800c986f  test    rdi, rdi
0x1800c9872  jz      short loc_1800C9891
0x1800c9874  cmp     [rbx+80h], rdi
0x1800c987b  jz      short loc_1800C9891
0x1800c987d  call    cs:__imp_GetProcessHeap
0x1800c9883  mov     r8, rdi; lpMem
0x1800c9886  xor     edx, edx; dwFlags
0x1800c9888  mov     rcx, rax; hHeap
0x1800c988b  call    cs:__imp_HeapFree
0x1800c9891  mov     rdi, [rbx+80h]
0x1800c9898  test    rdi, rdi
0x1800c989b  jz      short loc_1800C98B1
0x1800c989d  call    cs:__imp_GetProcessHeap
0x1800c98a3  mov     r8, rdi; lpMem
0x1800c98a6  xor     edx, edx; dwFlags
0x1800c98a8  mov     rcx, rax; hHeap
0x1800c98ab  call    cs:__imp_HeapFree
0x1800c98b1  mov     rdi, [rbx+0F0h]
0x1800c98b8  test    rdi, rdi
0x1800c98bb  jz      short loc_1800C98D1
0x1800c98bd  call    cs:__imp_GetProcessHeap
0x1800c98c3  mov     r8, rdi; lpMem
0x1800c98c6  xor     edx, edx; dwFlags
0x1800c98c8  mov     rcx, rax; hHeap
0x1800c98cb  call    cs:__imp_HeapFree
0x1800c98d1  mov     rcx, [rbx+128h]; ho
0x1800c98d8  test    rcx, rcx
0x1800c98db  jz      short loc_1800C98E3
0x1800c98dd  call    cs:__imp_DeleteObject
0x1800c98e3  mov     rcx, [rbx+168h]; hTheme
0x1800c98ea  test    rcx, rcx
0x1800c98ed  jz      short loc_1800C98F5
0x1800c98ef  call    cs:__imp_CloseThemeData
0x1800c98f5  lea     rcx, [rbx+180h]; ppsz
0x1800c98fc  xor     edx, edx; psz
0x1800c98fe  call    Str_SetPtrW
0x1800c9903  mov     rcx, [rbx+1A8h]; ho
0x1800c990a  test    rcx, rcx
0x1800c990d  jz      short loc_1800C9915
0x1800c990f  call    cs:__imp_DeleteObject
0x1800c9915  mov     rcx, [rbx+1B0h]; ho
0x1800c991c  test    rcx, rcx
0x1800c991f  jz      short loc_1800C9927
0x1800c9921  call    cs:__imp_DeleteObject
0x1800c9927  mov     rcx, [rbx+0C0h]; ho
0x1800c992e  test    rcx, rcx
0x1800c9931  jz      short loc_1800C9939
0x1800c9933  call    cs:__imp_DeleteObject
0x1800c9939  lea     rcx, [rbx+198h]; ppsz
0x1800c9940  xor     edx, edx; psz
0x1800c9942  call    Str_SetPtrW
0x1800c9947  lea     rcx, [rbx+208h]; this
0x1800c994e  call    ??1CCompositedDraw@@UEAA@XZ; CCompositedDraw::~CCompositedDraw(void)
0x1800c9953  mov     edx, 268h; unsigned __int64
0x1800c9958  mov     rcx, rbx; void *
0x1800c995b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c9960  xor     r8d, r8d
0x1800c9963  xor     edx, edx
0x1800c9965  mov     rcx, rsi
0x1800c9968  mov     rbx, [rsp+28h+arg_0]
0x1800c996d  mov     rsi, [rsp+28h+arg_8]
0x1800c9972  add     rsp, 20h
0x1800c9976  pop     rdi
0x1800c9977  jmp     cs:__imp_SetWindowLongPtrW
```
