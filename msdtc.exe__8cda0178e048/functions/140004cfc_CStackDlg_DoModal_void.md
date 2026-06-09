# CStackDlg::DoModal(void)

- ea: `0x140004cfc`
- end: `0x140004e3e`
- name: `?DoModal@CStackDlg@@QEAA_JXZ`
- size: `322`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140003fec`

## callees

- `0x140001290`
- `0x1400012d0`
- `0x140004cfc`
- `0x140004e44`
- `0x1400050bc`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004d59`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004dcc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004d59`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004dcc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004d92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004d92`

## string_xrefs

- `0x140004d8b`: `comres.dll`

## pseudocode

```c
__int64 __fastcall CStackDlg::DoModal(CStackDlg *this)
{
  CUser32Api *v2; // rax
  HMODULE *v3; // rbx
  HMODULE Library; // rbx
  __int64 v5; // rdi

  if ( !qword_1400107C8 )
  {
    v2 = (CUser32Api *)operator new(0x88u);
    v3 = (HMODULE *)v2;
    if ( v2 )
    {
      *(_QWORD *)v2 = 0;
      if ( !CUser32Api::Initialize(v2) || _InterlockedCompareExchange64(&qword_1400107C8, (signed __int64)v3, 0) )
      {
        if ( *v3 )
          FreeLibrary(*v3);
        operator delete(v3);
      }
    }
    if ( !qword_1400107C8 )
      return -1;
  }
  if ( !(unsigned int)CStackDlg::SwitchToInteractiveDesktop(this) )
    return -1;
  Library = LoadLibraryExW(L"comres.dll", 0, 2u);
  v5 = (*(__int64 (__fastcall **)(HMODULE, __int64, _QWORD, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64), _QWORD))(qword_1400107C8 + 8))(
         Library,
         601,
         0,
         CStackDlg::StackDlgProc,
         *((_QWORD *)this + 1));
  FreeLibrary(Library);
  (*(void (__fastcall **)(_QWORD))(qword_1400107C8 + 80))(*((_QWORD *)this + 5));
  (*(void (__fastcall **)(_QWORD))(qword_1400107C8 + 112))(*((_QWORD *)this + 2));
  (*(void (__fastcall **)(_QWORD))(qword_1400107C8 + 96))(*((_QWORD *)this + 6));
  (*(void (__fastcall **)(_QWORD))(qword_1400107C8 + 128))(*((_QWORD *)this + 4));
  return v5;
}

```

## disassembly

```asm
0x140004cfc  mov     [rsp+arg_0], rbx
0x140004d01  mov     [rsp+arg_10], rsi
0x140004d06  push    rdi
0x140004d07  sub     rsp, 30h
0x140004d0b  mov     rsi, rcx
0x140004d0e  xor     edi, edi
0x140004d10  cmp     cs:qword_1400107C8, rdi
0x140004d17  jnz     short loc_140004D75
0x140004d19  mov     ecx, 88h; Size
0x140004d1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004d23  mov     rbx, rax
0x140004d26  mov     [rsp+38h+arg_8], rax
0x140004d2b  test    rax, rax
0x140004d2e  jz      short loc_140004D68
0x140004d30  mov     [rax], rdi
0x140004d33  test    rax, rax
0x140004d36  jz      short loc_140004D68
0x140004d38  mov     rcx, rax; this
0x140004d3b  call    ?Initialize@CUser32Api@@QEAA_NXZ; CUser32Api::Initialize(void)
0x140004d40  test    al, al
0x140004d42  jz      short loc_140004D51
0x140004d44  xor     eax, eax
0x140004d46  lock cmpxchg cs:qword_1400107C8, rbx
0x140004d4f  jz      short loc_140004D68
0x140004d51  mov     rcx, [rbx]; hLibModule
0x140004d54  test    rcx, rcx
0x140004d57  jz      short loc_140004D60
0x140004d59  call    cs:__imp_FreeLibrary
0x140004d5f  nop
0x140004d60  mov     rcx, rbx; Block
0x140004d63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004d68  cmp     cs:qword_1400107C8, rdi
0x140004d6f  jz      loc_140004E2A
0x140004d75  mov     rcx, rsi; this
0x140004d78  call    ?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ; CStackDlg::SwitchToInteractiveDesktop(void)
0x140004d7d  test    eax, eax
0x140004d7f  jz      loc_140004E2A
0x140004d85  xor     edx, edx; hFile
0x140004d87  lea     r8d, [rdx+2]; dwFlags
0x140004d8b  lea     rcx, aComresDll; "comres.dll"
0x140004d92  call    cs:__imp_LoadLibraryExW
0x140004d98  mov     rbx, rax
0x140004d9b  mov     rcx, cs:qword_1400107C8
0x140004da2  mov     rax, [rcx+8]
0x140004da6  mov     rcx, [rsi+8]
0x140004daa  mov     [rsp+38h+var_18], rcx
0x140004daf  lea     r9, ?StackDlgProc@CStackDlg@@SA_JPEAUHWND__@@I_K_J@Z; CStackDlg::StackDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x140004db6  xor     r8d, r8d
0x140004db9  mov     edx, 259h
0x140004dbe  mov     rcx, rbx
0x140004dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004dc6  mov     rdi, rax
0x140004dc9  mov     rcx, rbx; hLibModule
0x140004dcc  call    cs:__imp_FreeLibrary
0x140004dd2  mov     rcx, cs:qword_1400107C8
0x140004dd9  mov     rax, [rcx+50h]
0x140004ddd  mov     rcx, [rsi+28h]
0x140004de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004de6  mov     rcx, cs:qword_1400107C8
0x140004ded  mov     rax, [rcx+70h]
0x140004df1  mov     rcx, [rsi+10h]
0x140004df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004dfa  mov     rax, cs:qword_1400107C8
0x140004e01  mov     rcx, [rsi+30h]
0x140004e05  mov     rax, [rax+60h]
0x140004e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e0e  mov     rax, cs:qword_1400107C8
0x140004e15  mov     rcx, [rsi+20h]
0x140004e19  mov     rax, [rax+80h]
0x140004e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e25  mov     rax, rdi
0x140004e28  jmp     short loc_140004E2E
0x140004e2a  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004e2e  mov     rbx, [rsp+38h+arg_0]
0x140004e33  mov     rsi, [rsp+38h+arg_10]
0x140004e38  add     rsp, 30h
0x140004e3c  pop     rdi
0x140004e3d  retn
```
