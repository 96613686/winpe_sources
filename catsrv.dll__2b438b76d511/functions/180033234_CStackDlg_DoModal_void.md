# CStackDlg::DoModal(void)

- ea: `0x180033234`
- end: `0x180033371`
- name: `?DoModal@CStackDlg@@QEAA_JXZ`
- size: `317`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800328a0`

## callees

- `0x1800330ac`
- `0x180033234`
- `0x180033378`
- `0x1800335ec`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800332ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800332ff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800332c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800332c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033256`

## string_xrefs

- `0x1800332ba`: `comres.dll`

## pseudocode

```c
__int64 __fastcall CStackDlg::DoModal(CStackDlg *this)
{
  CUser32Api *v2; // rax
  CUser32Api *v3; // rbx
  HMODULE Library; // rbx
  __int64 v5; // rdi

  if ( !qword_180073338 )
  {
    v2 = (CUser32Api *)CoTaskMemAlloc(0x88u);
    v3 = v2;
    if ( v2 )
    {
      *(_QWORD *)v2 = 0;
      if ( !CUser32Api::Initialize(v2) || _InterlockedCompareExchange64(&qword_180073338, (signed __int64)v3, 0) )
      {
        CUser32Api::~CUser32Api(v3);
        CoTaskMemFree(v3);
      }
    }
    if ( !qword_180073338 )
      return -1;
  }
  if ( !CStackDlg::SwitchToInteractiveDesktop(this) )
    return -1;
  Library = LoadLibraryExW(L"comres.dll", 0, 2u);
  v5 = (*(__int64 (__fastcall **)(HMODULE, __int64, _QWORD, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64), _QWORD))(qword_180073338 + 8))(
         Library,
         601,
         0,
         CStackDlg::StackDlgProc,
         *((_QWORD *)this + 1));
  FreeLibrary(Library);
  (*(void (__fastcall **)(_QWORD))(qword_180073338 + 80))(*((_QWORD *)this + 5));
  (*(void (__fastcall **)(_QWORD))(qword_180073338 + 112))(*((_QWORD *)this + 2));
  (*(void (__fastcall **)(_QWORD))(qword_180073338 + 96))(*((_QWORD *)this + 6));
  (*(void (__fastcall **)(_QWORD))(qword_180073338 + 128))(*((_QWORD *)this + 4));
  return v5;
}

```

## disassembly

```asm
0x180033234  mov     [rsp+arg_0], rbx
0x180033239  mov     [rsp+arg_10], rsi
0x18003323e  push    rdi
0x18003323f  sub     rsp, 30h
0x180033243  xor     edi, edi
0x180033245  mov     rsi, rcx
0x180033248  cmp     cs:qword_180073338, rdi
0x18003324f  jnz     short loc_1800332A8
0x180033251  mov     ecx, 88h; cb
0x180033256  call    cs:__imp_CoTaskMemAlloc
0x18003325c  mov     [rsp+38h+arg_8], rax
0x180033261  mov     rbx, rax
0x180033264  test    rax, rax
0x180033267  jz      short loc_18003329B
0x180033269  mov     [rax], rdi
0x18003326c  test    rax, rax
0x18003326f  jz      short loc_18003329B
0x180033271  mov     rcx, rax; this
0x180033274  call    ?Initialize@CUser32Api@@QEAA_NXZ; CUser32Api::Initialize(void)
0x180033279  test    al, al
0x18003327b  jz      short loc_18003328A
0x18003327d  xor     eax, eax
0x18003327f  lock cmpxchg cs:qword_180073338, rbx
0x180033288  jz      short loc_18003329B
0x18003328a  mov     rcx, rbx; this
0x18003328d  call    ??1CUser32Api@@QEAA@XZ; CUser32Api::~CUser32Api(void)
0x180033292  mov     rcx, rbx; pv
0x180033295  call    cs:__imp_CoTaskMemFree
0x18003329b  cmp     cs:qword_180073338, rdi
0x1800332a2  jz      loc_18003335D
0x1800332a8  mov     rcx, rsi; this
0x1800332ab  call    ?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ; CStackDlg::SwitchToInteractiveDesktop(void)
0x1800332b0  test    eax, eax
0x1800332b2  jz      loc_18003335D
0x1800332b8  xor     edx, edx; hFile
0x1800332ba  lea     rcx, aComresDll; "comres.dll"
0x1800332c1  lea     r8d, [rdx+2]; dwFlags
0x1800332c5  call    cs:__imp_LoadLibraryExW
0x1800332cb  mov     rcx, cs:qword_180073338
0x1800332d2  lea     r9, ?StackDlgProc@CStackDlg@@SA_JPEAUHWND__@@I_K_J@Z; CStackDlg::StackDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800332d9  mov     rbx, rax
0x1800332dc  xor     r8d, r8d
0x1800332df  mov     edx, 259h
0x1800332e4  mov     rax, [rcx+8]
0x1800332e8  mov     rcx, [rsi+8]
0x1800332ec  mov     [rsp+38h+var_18], rcx
0x1800332f1  mov     rcx, rbx
0x1800332f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332f9  mov     rcx, rbx; hLibModule
0x1800332fc  mov     rdi, rax
0x1800332ff  call    cs:__imp_FreeLibrary
0x180033305  mov     rcx, cs:qword_180073338
0x18003330c  mov     rax, [rcx+50h]
0x180033310  mov     rcx, [rsi+28h]
0x180033314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033319  mov     rcx, cs:qword_180073338
0x180033320  mov     rax, [rcx+70h]
0x180033324  mov     rcx, [rsi+10h]
0x180033328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003332d  mov     rax, cs:qword_180073338
0x180033334  mov     rcx, [rsi+30h]
0x180033338  mov     rax, [rax+60h]
0x18003333c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033341  mov     rax, cs:qword_180073338
0x180033348  mov     rcx, [rsi+20h]
0x18003334c  mov     rax, [rax+80h]
0x180033353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033358  mov     rax, rdi
0x18003335b  jmp     short loc_180033361
0x18003335d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033361  mov     rbx, [rsp+38h+arg_0]
0x180033366  mov     rsi, [rsp+38h+arg_10]
0x18003336b  add     rsp, 30h
0x18003336f  pop     rdi
0x180033370  retn
```
