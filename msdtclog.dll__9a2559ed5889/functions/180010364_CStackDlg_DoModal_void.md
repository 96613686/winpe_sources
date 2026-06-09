# CStackDlg::DoModal(void)

- ea: `0x180010364`
- end: `0x1800104a6`
- name: `?DoModal@CStackDlg@@QEAA_JXZ`
- size: `322`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000f654`

## callees

- `0x1800012c0`
- `0x180001300`
- `0x180010364`
- `0x1800104ac`
- `0x18001071c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800103fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800103fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800103c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010434`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800103c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010434`

## string_xrefs

- `0x1800103f3`: `comres.dll`

## pseudocode

```c
__int64 __fastcall CStackDlg::DoModal(CStackDlg *this)
{
  CUser32Api *v2; // rax
  HMODULE *v3; // rbx
  HMODULE Library; // rbx
  __int64 v5; // rdi

  if ( !qword_18001FA80 )
  {
    v2 = (CUser32Api *)operator new(0x88u);
    v3 = (HMODULE *)v2;
    if ( v2 )
    {
      *(_QWORD *)v2 = 0;
      if ( !CUser32Api::Initialize(v2) || _InterlockedCompareExchange64(&qword_18001FA80, (signed __int64)v3, 0) )
      {
        if ( *v3 )
          FreeLibrary(*v3);
        operator delete(v3);
      }
    }
    if ( !qword_18001FA80 )
      return -1;
  }
  if ( !(unsigned int)CStackDlg::SwitchToInteractiveDesktop(this) )
    return -1;
  Library = LoadLibraryExW(L"comres.dll", 0, 2u);
  v5 = (*(__int64 (__fastcall **)(HMODULE, __int64, _QWORD, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64), _QWORD))(qword_18001FA80 + 8))(
         Library,
         601,
         0,
         CStackDlg::StackDlgProc,
         *((_QWORD *)this + 1));
  FreeLibrary(Library);
  (*(void (__fastcall **)(_QWORD))(qword_18001FA80 + 80))(*((_QWORD *)this + 5));
  (*(void (__fastcall **)(_QWORD))(qword_18001FA80 + 112))(*((_QWORD *)this + 2));
  (*(void (__fastcall **)(_QWORD))(qword_18001FA80 + 96))(*((_QWORD *)this + 6));
  (*(void (__fastcall **)(_QWORD))(qword_18001FA80 + 128))(*((_QWORD *)this + 4));
  return v5;
}

```

## disassembly

```asm
0x180010364  mov     [rsp+arg_0], rbx
0x180010369  mov     [rsp+arg_10], rsi
0x18001036e  push    rdi
0x18001036f  sub     rsp, 30h
0x180010373  mov     rsi, rcx
0x180010376  xor     edi, edi
0x180010378  cmp     cs:qword_18001FA80, rdi
0x18001037f  jnz     short loc_1800103DD
0x180010381  mov     ecx, 88h; Size
0x180010386  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001038b  mov     rbx, rax
0x18001038e  mov     [rsp+38h+arg_8], rax
0x180010393  test    rax, rax
0x180010396  jz      short loc_1800103D0
0x180010398  mov     [rax], rdi
0x18001039b  test    rax, rax
0x18001039e  jz      short loc_1800103D0
0x1800103a0  mov     rcx, rax; this
0x1800103a3  call    ?Initialize@CUser32Api@@QEAA_NXZ; CUser32Api::Initialize(void)
0x1800103a8  test    al, al
0x1800103aa  jz      short loc_1800103B9
0x1800103ac  xor     eax, eax
0x1800103ae  lock cmpxchg cs:qword_18001FA80, rbx
0x1800103b7  jz      short loc_1800103D0
0x1800103b9  mov     rcx, [rbx]; hLibModule
0x1800103bc  test    rcx, rcx
0x1800103bf  jz      short loc_1800103C8
0x1800103c1  call    cs:__imp_FreeLibrary
0x1800103c7  nop
0x1800103c8  mov     rcx, rbx; Block
0x1800103cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800103d0  cmp     cs:qword_18001FA80, rdi
0x1800103d7  jz      loc_180010492
0x1800103dd  mov     rcx, rsi; this
0x1800103e0  call    ?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ; CStackDlg::SwitchToInteractiveDesktop(void)
0x1800103e5  test    eax, eax
0x1800103e7  jz      loc_180010492
0x1800103ed  xor     edx, edx; hFile
0x1800103ef  lea     r8d, [rdx+2]; dwFlags
0x1800103f3  lea     rcx, aComresDll; "comres.dll"
0x1800103fa  call    cs:__imp_LoadLibraryExW
0x180010400  mov     rbx, rax
0x180010403  mov     rcx, cs:qword_18001FA80
0x18001040a  mov     rax, [rcx+8]
0x18001040e  mov     rcx, [rsi+8]
0x180010412  mov     [rsp+38h+var_18], rcx
0x180010417  lea     r9, ?StackDlgProc@CStackDlg@@SA_JPEAUHWND__@@I_K_J@Z; CStackDlg::StackDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001041e  xor     r8d, r8d
0x180010421  mov     edx, 259h
0x180010426  mov     rcx, rbx
0x180010429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001042e  mov     rdi, rax
0x180010431  mov     rcx, rbx; hLibModule
0x180010434  call    cs:__imp_FreeLibrary
0x18001043a  mov     rcx, cs:qword_18001FA80
0x180010441  mov     rax, [rcx+50h]
0x180010445  mov     rcx, [rsi+28h]
0x180010449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001044e  mov     rcx, cs:qword_18001FA80
0x180010455  mov     rax, [rcx+70h]
0x180010459  mov     rcx, [rsi+10h]
0x18001045d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010462  mov     rax, cs:qword_18001FA80
0x180010469  mov     rcx, [rsi+30h]
0x18001046d  mov     rax, [rax+60h]
0x180010471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010476  mov     rax, cs:qword_18001FA80
0x18001047d  mov     rcx, [rsi+20h]
0x180010481  mov     rax, [rax+80h]
0x180010488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001048d  mov     rax, rdi
0x180010490  jmp     short loc_180010496
0x180010492  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010496  mov     rbx, [rsp+38h+arg_0]
0x18001049b  mov     rsi, [rsp+38h+arg_10]
0x1800104a0  add     rsp, 30h
0x1800104a4  pop     rdi
0x1800104a5  retn
```
