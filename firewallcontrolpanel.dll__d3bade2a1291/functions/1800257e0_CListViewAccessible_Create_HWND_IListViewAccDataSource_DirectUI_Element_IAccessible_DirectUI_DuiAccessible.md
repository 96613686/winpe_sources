# CListViewAccessible::Create(HWND__ *,IListViewAccDataSource *,DirectUI::Element *,IAccessible *,DirectUI::DuiAccessible * *)

- ea: `0x1800257e0`
- end: `0x180025905`
- name: `?Create@CListViewAccessible@@SAJPEAUHWND__@@PEAVIListViewAccDataSource@@PEAVElement@DirectUI@@PEAUIAccessible@@PEAPEAVDuiAccessible@5@@Z`
- size: `293`
- prototype: `__int64 __fastcall(HWND, struct IListViewAccDataSource *, struct DirectUI::Element *, struct IAccessible *, struct DirectUI::DuiAccessible **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800100f0`

## callees

- `0x180009b30`
- `0x1800257e0`
- `0x180032010`

## import_xrefs

- `DUI70!??0HWNDHostClientAccessible@DirectUI@@QEAA@XZ` at `0x180025825`
- `DUI70!??0HWNDHostClientAccessible@DirectUI@@QEAA@XZ` at `0x180025825`
- `DUI70!?Initialize@HWNDHostAccessible@DirectUI@@QEAAJPEAVElement@2@PEAUIAccessible@@@Z` at `0x1800258a8`
- `DUI70!?Initialize@HWNDHostAccessible@DirectUI@@QEAAJPEAVElement@2@PEAUIAccessible@@@Z` at `0x1800258a8`

## pseudocode

```c
__int64 __fastcall CListViewAccessible::Create(
        HWND a1,
        struct IListViewAccDataSource *a2,
        struct DirectUI::Element *a3,
        struct IAccessible *a4,
        struct DirectUI::DuiAccessible **a5)
{
  DirectUI::HWNDHostClientAccessible *v9; // rax
  DirectUI::HWNDHostAccessible *v10; // rbx
  int v11; // edi

  *a5 = 0;
  v9 = (DirectUI::HWNDHostClientAccessible *)DirectUI::HAllocAndZero((DirectUI *)0x68, (unsigned __int64)a2);
  v10 = v9;
  if ( v9 )
  {
    DirectUI::HWNDHostClientAccessible::HWNDHostClientAccessible(v9);
    *(_QWORD *)v10 = &CListViewAccessible::`vftable'{for `IAccessible'};
    *((_QWORD *)v10 + 1) = &CListViewAccessible::`vftable'{for `IEnumVARIANT'};
    *((_QWORD *)v10 + 2) = &CListViewAccessible::`vftable'{for `IOleWindow'};
    *((_QWORD *)v10 + 3) = &CListViewAccessible::`vftable'{for `IAccIdentity'};
    *((_QWORD *)v10 + 4) = &CListViewAccessible::`vftable'{for `IServiceProvider'};
    *((_QWORD *)v10 + 11) = 0;
    *((_QWORD *)v10 + 10) = 0;
    *((_QWORD *)v10 + 12) = 0;
    _InterlockedIncrement(&g_cLocks);
  }
  else
  {
    v10 = 0;
  }
  if ( v10 )
  {
    if ( a1 && a2 && a4 )
    {
      v11 = DirectUI::HWNDHostAccessible::Initialize(v10, a3, a4);
      if ( v11 >= 0 )
      {
        *((_QWORD *)v10 + 10) = a1;
        *((_QWORD *)v10 + 11) = a4;
        ((void (__fastcall *)(struct IAccessible *))a4->lpVtbl->AddRef)(a4);
        *((_QWORD *)v10 + 12) = a2;
        (**(void (__fastcall ***)(struct IListViewAccDataSource *))a2)(a2);
        *a5 = v10;
        return (unsigned int)v11;
      }
    }
    else
    {
      v11 = -2147024809;
    }
    (*(void (__fastcall **)(DirectUI::HWNDHostAccessible *))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v11;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800257e0  push    rbx
0x1800257e2  push    rbp
0x1800257e3  push    rsi
0x1800257e4  push    rdi
0x1800257e5  push    r14
0x1800257e7  push    r15
0x1800257e9  sub     rsp, 28h
0x1800257ed  mov     rsi, r9
0x1800257f0  mov     rdi, r8
0x1800257f3  mov     r14, rdx
0x1800257f6  mov     rbp, rcx
0x1800257f9  mov     r15, [rsp+58h+arg_20]
0x180025801  mov     qword ptr [r15], 0
0x180025808  mov     ecx, 68h ; 'h'; this
0x18002580d  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180025812  mov     rbx, rax
0x180025815  mov     [rsp+58h+arg_20], rax
0x18002581d  test    rax, rax
0x180025820  jz      short loc_180025882
0x180025822  mov     rcx, rax
0x180025825  call    cs:__imp_??0HWNDHostClientAccessible@DirectUI@@QEAA@XZ; DirectUI::HWNDHostClientAccessible::HWNDHostClientAccessible(void)
0x18002582b  lea     rax, ??_7CListViewAccessible@@6BIAccessible@@@; const CListViewAccessible::`vftable'{for `IAccessible'}
0x180025832  mov     [rbx], rax
0x180025835  lea     rax, ??_7CListViewAccessible@@6BIEnumVARIANT@@@; const CListViewAccessible::`vftable'{for `IEnumVARIANT'}
0x18002583c  mov     [rbx+8], rax
0x180025840  lea     rax, ??_7CListViewAccessible@@6BIOleWindow@@@; const CListViewAccessible::`vftable'{for `IOleWindow'}
0x180025847  mov     [rbx+10h], rax
0x18002584b  lea     rax, ??_7CListViewAccessible@@6BIAccIdentity@@@; const CListViewAccessible::`vftable'{for `IAccIdentity'}
0x180025852  mov     [rbx+18h], rax
0x180025856  lea     rax, ??_7CListViewAccessible@@6BIServiceProvider@@@; const CListViewAccessible::`vftable'{for `IServiceProvider'}
0x18002585d  mov     [rbx+20h], rax
0x180025861  mov     qword ptr [rbx+58h], 0
0x180025869  mov     qword ptr [rbx+50h], 0
0x180025871  mov     qword ptr [rbx+60h], 0
0x180025879  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180025880  jmp     short loc_180025884
0x180025882  xor     ebx, ebx
0x180025884  test    rbx, rbx
0x180025887  jnz     short loc_180025890
0x180025889  mov     edi, 8007000Eh
0x18002588e  jmp     short loc_1800258F6
0x180025890  test    rbp, rbp
0x180025893  jz      short loc_1800258E2
0x180025895  test    r14, r14
0x180025898  jz      short loc_1800258E2
0x18002589a  test    rsi, rsi
0x18002589d  jz      short loc_1800258E2
0x18002589f  mov     r8, rsi
0x1800258a2  mov     rdx, rdi
0x1800258a5  mov     rcx, rbx
0x1800258a8  call    cs:__imp_?Initialize@HWNDHostAccessible@DirectUI@@QEAAJPEAVElement@2@PEAUIAccessible@@@Z; DirectUI::HWNDHostAccessible::Initialize(DirectUI::Element *,IAccessible *)
0x1800258ae  mov     edi, eax
0x1800258b0  test    eax, eax
0x1800258b2  js      short loc_1800258E7
0x1800258b4  mov     [rbx+50h], rbp
0x1800258b8  mov     [rbx+58h], rsi
0x1800258bc  mov     rax, [rsi]
0x1800258bf  mov     rcx, rsi
0x1800258c2  mov     rax, [rax+8]
0x1800258c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258cb  mov     [rbx+60h], r14
0x1800258cf  mov     rax, [r14]
0x1800258d2  mov     rcx, r14
0x1800258d5  mov     rax, [rax]
0x1800258d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258dd  mov     [r15], rbx
0x1800258e0  jmp     short loc_1800258F6
0x1800258e2  mov     edi, 80070057h
0x1800258e7  mov     rdx, [rbx]
0x1800258ea  mov     rcx, rbx
0x1800258ed  mov     rax, [rdx+10h]
0x1800258f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258f6  mov     eax, edi
0x1800258f8  add     rsp, 28h
0x1800258fc  pop     r15
0x1800258fe  pop     r14
0x180025900  pop     rdi
0x180025901  pop     rsi
0x180025902  pop     rbp
0x180025903  pop     rbx
0x180025904  retn
```
