# CStackDlg::DoModal(void)

- ea: `0x1800442a0`
- end: `0x1800443df`
- name: `?DoModal@CStackDlg@@QEAA_JXZ`
- size: `319`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043a58`

## callees

- `0x180044118`
- `0x1800442a0`
- `0x1800443e8`
- `0x18004465c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004436d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004436d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044333`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800442c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800442c2`

## string_xrefs

- `0x18004432c`: `comres.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStackDlg::DoModal(CStackDlg *this)
{
  CUser32Api *v2; // rax
  CUser32Api *v3; // rbx
  HMODULE Library; // rbx
  __int64 v5; // rdi

  if ( !qword_1800733F0 )
  {
    v2 = (CUser32Api *)CoTaskMemAlloc(0x88u);
    v3 = v2;
    if ( v2 )
    {
      *(_QWORD *)v2 = 0;
      if ( !CUser32Api::Initialize(v2) || _InterlockedCompareExchange64(&qword_1800733F0, (signed __int64)v3, 0) )
      {
        CUser32Api::~CUser32Api(v3);
        CoTaskMemFree(v3);
      }
    }
    if ( !qword_1800733F0 )
      return -1;
  }
  if ( !CStackDlg::SwitchToInteractiveDesktop(this) )
    return -1;
  Library = LoadLibraryExW(L"comres.dll", 0, 2u);
  v5 = (*(__int64 (__fastcall **)(HMODULE, __int64, _QWORD, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64), _QWORD))(qword_1800733F0 + 8))(
         Library,
         601,
         0,
         CStackDlg::StackDlgProc,
         *((_QWORD *)this + 1));
  FreeLibrary(Library);
  (*(void (__fastcall **)(_QWORD))(qword_1800733F0 + 80))(*((_QWORD *)this + 5));
  (*(void (__fastcall **)(_QWORD))(qword_1800733F0 + 112))(*((_QWORD *)this + 2));
  (*(void (__fastcall **)(_QWORD))(qword_1800733F0 + 96))(*((_QWORD *)this + 6));
  (*(void (__fastcall **)(_QWORD))(qword_1800733F0 + 128))(*((_QWORD *)this + 4));
  return v5;
}

```

## disassembly

```asm
0x1800442a0  mov     [rsp+arg_0], rbx
0x1800442a5  mov     [rsp+arg_10], rsi
0x1800442aa  push    rdi
0x1800442ab  sub     rsp, 30h
0x1800442af  mov     rsi, rcx
0x1800442b2  xor     edi, edi
0x1800442b4  cmp     cs:qword_1800733F0, rdi
0x1800442bb  jnz     short loc_180044316
0x1800442bd  mov     ecx, 88h; cb
0x1800442c2  call    cs:__imp_CoTaskMemAlloc
0x1800442c8  mov     rbx, rax
0x1800442cb  mov     [rsp+38h+arg_8], rax
0x1800442d0  test    rax, rax
0x1800442d3  jz      short loc_180044309
0x1800442d5  mov     [rax], rdi
0x1800442d8  test    rax, rax
0x1800442db  jz      short loc_180044309
0x1800442dd  mov     rcx, rax; this
0x1800442e0  call    ?Initialize@CUser32Api@@QEAA_NXZ; CUser32Api::Initialize(void)
0x1800442e5  test    al, al
0x1800442e7  jz      short loc_1800442F6
0x1800442e9  xor     eax, eax
0x1800442eb  lock cmpxchg cs:qword_1800733F0, rbx
0x1800442f4  jz      short loc_180044309
0x1800442f6  mov     rcx, rbx; this
0x1800442f9  call    ??1CUser32Api@@QEAA@XZ; CUser32Api::~CUser32Api(void)
0x1800442fe  nop
0x1800442ff  mov     rcx, rbx; pv
0x180044302  call    cs:__imp_CoTaskMemFree
0x180044308  nop
0x180044309  cmp     cs:qword_1800733F0, rdi
0x180044310  jz      loc_1800443CB
0x180044316  mov     rcx, rsi; this
0x180044319  call    ?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ; CStackDlg::SwitchToInteractiveDesktop(void)
0x18004431e  test    eax, eax
0x180044320  jz      loc_1800443CB
0x180044326  xor     edx, edx; hFile
0x180044328  lea     r8d, [rdx+2]; dwFlags
0x18004432c  lea     rcx, LibFileName; "comres.dll"
0x180044333  call    cs:__imp_LoadLibraryExW
0x180044339  mov     rbx, rax
0x18004433c  mov     rcx, cs:qword_1800733F0
0x180044343  mov     rax, [rcx+8]
0x180044347  mov     rcx, [rsi+8]
0x18004434b  mov     [rsp+38h+var_18], rcx
0x180044350  lea     r9, ?StackDlgProc@CStackDlg@@SA_JPEAUHWND__@@I_K_J@Z; CStackDlg::StackDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180044357  xor     r8d, r8d
0x18004435a  mov     edx, 259h
0x18004435f  mov     rcx, rbx
0x180044362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044367  mov     rdi, rax
0x18004436a  mov     rcx, rbx; hLibModule
0x18004436d  call    cs:__imp_FreeLibrary
0x180044373  mov     rcx, cs:qword_1800733F0
0x18004437a  mov     rax, [rcx+50h]
0x18004437e  mov     rcx, [rsi+28h]
0x180044382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044387  mov     rcx, cs:qword_1800733F0
0x18004438e  mov     rax, [rcx+70h]
0x180044392  mov     rcx, [rsi+10h]
0x180044396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004439b  mov     rax, cs:qword_1800733F0
0x1800443a2  mov     rcx, [rsi+30h]
0x1800443a6  mov     rax, [rax+60h]
0x1800443aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443af  mov     rax, cs:qword_1800733F0
0x1800443b6  mov     rcx, [rsi+20h]
0x1800443ba  mov     rax, [rax+80h]
0x1800443c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443c6  mov     rax, rdi
0x1800443c9  jmp     short loc_1800443CF
0x1800443cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800443cf  mov     rbx, [rsp+38h+arg_0]
0x1800443d4  mov     rsi, [rsp+38h+arg_10]
0x1800443d9  add     rsp, 30h
0x1800443dd  pop     rdi
0x1800443de  retn
```
