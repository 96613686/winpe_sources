# CStackDlg::DoModal(void)

- ea: `0x18004269c`
- end: `0x1800427d9`
- name: `?DoModal@CStackDlg@@QEAA_JXZ`
- size: `317`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180041fc8`

## callees

- `0x180042514`
- `0x18004269c`
- `0x1800427e0`
- `0x180042a4c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004272d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004272d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042767`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042767`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800426be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800426be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800426fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800426fd`

## string_xrefs

- `0x180042722`: `comres.dll`

## pseudocode

```c
__int64 __fastcall CStackDlg::DoModal(CStackDlg *this)
{
  CUser32Api *v2; // rax
  CUser32Api *v3; // rbx
  HMODULE Library; // rbx
  __int64 v5; // rdi

  if ( !qword_1800642C0 )
  {
    v2 = (CUser32Api *)CoTaskMemAlloc(0x88u);
    v3 = v2;
    if ( v2 )
    {
      *(_QWORD *)v2 = 0;
      if ( !CUser32Api::Initialize(v2) || _InterlockedCompareExchange64(&qword_1800642C0, (signed __int64)v3, 0) )
      {
        CUser32Api::~CUser32Api(v3);
        CoTaskMemFree(v3);
      }
    }
    if ( !qword_1800642C0 )
      return -1;
  }
  if ( !(unsigned int)CStackDlg::SwitchToInteractiveDesktop(this) )
    return -1;
  Library = LoadLibraryExW(L"comres.dll", 0, 2u);
  v5 = (*(__int64 (__fastcall **)(HMODULE, __int64, _QWORD, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64), _QWORD))(qword_1800642C0 + 8))(
         Library,
         601,
         0,
         CStackDlg::StackDlgProc,
         *((_QWORD *)this + 1));
  FreeLibrary(Library);
  (*(void (__fastcall **)(_QWORD))(qword_1800642C0 + 80))(*((_QWORD *)this + 5));
  (*(void (__fastcall **)(_QWORD))(qword_1800642C0 + 112))(*((_QWORD *)this + 2));
  (*(void (__fastcall **)(_QWORD))(qword_1800642C0 + 96))(*((_QWORD *)this + 6));
  (*(void (__fastcall **)(_QWORD))(qword_1800642C0 + 128))(*((_QWORD *)this + 4));
  return v5;
}

```

## disassembly

```asm
0x18004269c  mov     [rsp+arg_0], rbx
0x1800426a1  mov     [rsp+arg_10], rsi
0x1800426a6  push    rdi
0x1800426a7  sub     rsp, 30h
0x1800426ab  xor     edi, edi
0x1800426ad  mov     rsi, rcx
0x1800426b0  cmp     cs:qword_1800642C0, rdi
0x1800426b7  jnz     short loc_180042710
0x1800426b9  mov     ecx, 88h; cb
0x1800426be  call    cs:__imp_CoTaskMemAlloc
0x1800426c4  mov     [rsp+38h+arg_8], rax
0x1800426c9  mov     rbx, rax
0x1800426cc  test    rax, rax
0x1800426cf  jz      short loc_180042703
0x1800426d1  mov     [rax], rdi
0x1800426d4  test    rax, rax
0x1800426d7  jz      short loc_180042703
0x1800426d9  mov     rcx, rax; this
0x1800426dc  call    ?Initialize@CUser32Api@@QEAA_NXZ; CUser32Api::Initialize(void)
0x1800426e1  test    al, al
0x1800426e3  jz      short loc_1800426F2
0x1800426e5  xor     eax, eax
0x1800426e7  lock cmpxchg cs:qword_1800642C0, rbx
0x1800426f0  jz      short loc_180042703
0x1800426f2  mov     rcx, rbx; this
0x1800426f5  call    ??1CUser32Api@@QEAA@XZ; CUser32Api::~CUser32Api(void)
0x1800426fa  mov     rcx, rbx; pv
0x1800426fd  call    cs:__imp_CoTaskMemFree
0x180042703  cmp     cs:qword_1800642C0, rdi
0x18004270a  jz      loc_1800427C5
0x180042710  mov     rcx, rsi; this
0x180042713  call    ?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ; CStackDlg::SwitchToInteractiveDesktop(void)
0x180042718  test    eax, eax
0x18004271a  jz      loc_1800427C5
0x180042720  xor     edx, edx; hFile
0x180042722  lea     rcx, LibFileName; "comres.dll"
0x180042729  lea     r8d, [rdx+2]; dwFlags
0x18004272d  call    cs:__imp_LoadLibraryExW
0x180042733  mov     rcx, cs:qword_1800642C0
0x18004273a  lea     r9, ?StackDlgProc@CStackDlg@@SA_JPEAUHWND__@@I_K_J@Z; CStackDlg::StackDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180042741  mov     rbx, rax
0x180042744  xor     r8d, r8d
0x180042747  mov     edx, 259h
0x18004274c  mov     rax, [rcx+8]
0x180042750  mov     rcx, [rsi+8]
0x180042754  mov     [rsp+38h+var_18], rcx
0x180042759  mov     rcx, rbx
0x18004275c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042761  mov     rcx, rbx; hLibModule
0x180042764  mov     rdi, rax
0x180042767  call    cs:__imp_FreeLibrary
0x18004276d  mov     rcx, cs:qword_1800642C0
0x180042774  mov     rax, [rcx+50h]
0x180042778  mov     rcx, [rsi+28h]
0x18004277c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042781  mov     rcx, cs:qword_1800642C0
0x180042788  mov     rax, [rcx+70h]
0x18004278c  mov     rcx, [rsi+10h]
0x180042790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042795  mov     rax, cs:qword_1800642C0
0x18004279c  mov     rcx, [rsi+30h]
0x1800427a0  mov     rax, [rax+60h]
0x1800427a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427a9  mov     rax, cs:qword_1800642C0
0x1800427b0  mov     rcx, [rsi+20h]
0x1800427b4  mov     rax, [rax+80h]
0x1800427bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427c0  mov     rax, rdi
0x1800427c3  jmp     short loc_1800427C9
0x1800427c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800427c9  mov     rbx, [rsp+38h+arg_0]
0x1800427ce  mov     rsi, [rsp+38h+arg_10]
0x1800427d3  add     rsp, 30h
0x1800427d7  pop     rdi
0x1800427d8  retn
```
