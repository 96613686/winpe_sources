# CAddProgram::EnumFoldersAndAddPrograms(IShellFolder *)

- ea: `0x1800278b8`
- end: `0x180027aab`
- name: `?EnumFoldersAndAddPrograms@CAddProgram@@AEAAJPEAUIShellFolder@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(CAddProgram *__hidden this, struct IShellFolder *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800278b8`
- `0x180028110`

## callees

- `0x180027438`
- `0x1800278b8`
- `0x180030e6e`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180027a2d`
- `msvcrt!_wcsicmp` at `0x180027a2d`
- `SHCORE!__imp_StrRetToBufW` at `0x180027a05`
- `SHCORE!__imp_StrRetToBufW` at `0x180027a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a6b`

## pseudocode

```c
__int64 __fastcall CAddProgram::EnumFoldersAndAddPrograms(CAddProgram *this, struct IShellFolder *a2)
{
  struct IShellFolderVtbl *lpVtbl; // rax
  HRESULT (__stdcall *EnumObjects)(IShellFolder *, HWND, SHCONTF, IEnumIDList **); // rax
  int v6; // ebx
  struct IShellFolderVtbl *v7; // rax
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+38h] [rbp-C8h] BYREF
  IShellFolder *pshf; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  STRRET pstr; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszBuf[264]; // [rsp+170h] [rbp+70h] BYREF

  lpVtbl = a2->lpVtbl;
  pshf = 0;
  v13 = 0;
  pidl = 0;
  EnumObjects = lpVtbl->EnumObjects;
  v10 = 0;
  v6 = ((__int64 (__fastcall *)(struct IShellFolder *, _QWORD, __int64, __int64 *))EnumObjects)(a2, 0, 32, &v13);
  if ( v6 >= 0 )
  {
    while ( 1 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, LPCITEMIDLIST *, int *))(*(_QWORD *)v13 + 24LL))(
             v13,
             1,
             &pidl,
             &v10);
      if ( v6 || v10 != 1 )
        break;
      v7 = a2->lpVtbl;
      v12 = 1074266112;
      if ( ((int (__fastcall *)(struct IShellFolder *, _QWORD, LPCITEMIDLIST *, int *))v7->GetAttributesOf)(
             a2,
             (unsigned int)(v6 + 1),
             &pidl,
             &v12) >= 0
        && ((int (__fastcall *)(struct IShellFolder *, LPCITEMIDLIST, _QWORD, GUID *, IShellFolder **))a2->lpVtbl->BindToObject)(
             a2,
             pidl,
             0,
             &IID_IShellFolder,
             &pshf) >= 0 )
      {
        memset_0(&pstr, 0, sizeof(pstr));
        if ( !((unsigned int (__fastcall *)(struct IShellFolder *, LPCITEMIDLIST, _QWORD, STRRET *))a2->lpVtbl->GetDisplayNameOf)(
                a2,
                pidl,
                (unsigned int)(v6 + 1),
                &pstr)
          && !StrRetToBufW(&pstr, pidl, pszBuf, 0x104u) )
        {
          while ( (unsigned __int64)v6 < 3 )
          {
            if ( !_wcsicmp(pszBuf, (const wchar_t *)&dword_1800453B4[131 * v6]) )
              goto LABEL_12;
            ++v6;
          }
          CAddProgram::AddProgramsToList(this, pshf);
          CAddProgram::EnumFoldersAndAddPrograms(this, pshf);
        }
LABEL_12:
        ((void (__fastcall *)(IShellFolder *))pshf->lpVtbl->Release)(pshf);
      }
      CoTaskMemFree((LPVOID)pidl);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800278b8  mov     [rsp-8+arg_10], rbx
0x1800278bd  push    rbp
0x1800278be  push    rsi
0x1800278bf  push    rdi
0x1800278c0  lea     rbp, [rsp-290h]
0x1800278c8  sub     rsp, 390h
0x1800278cf  mov     rax, cs:__security_cookie
0x1800278d6  xor     rax, rsp
0x1800278d9  mov     [rbp+2A0h+var_20], rax
0x1800278e0  mov     rax, [rdx]
0x1800278e3  lea     r9, [rsp+3A0h+var_350]
0x1800278e8  mov     rdi, rdx
0x1800278eb  mov     [rsp+3A0h+pshf], 0
0x1800278f4  xor     edx, edx
0x1800278f6  mov     [rsp+3A0h+var_350], 0
0x1800278ff  mov     rsi, rcx
0x180027902  mov     [rsp+3A0h+pidl], 0
0x18002790b  mov     rax, [rax+20h]
0x18002790f  mov     rcx, rdi
0x180027912  mov     [rsp+3A0h+var_368], 0
0x18002791a  lea     r8d, [rdx+20h]
0x18002791e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027923  mov     ebx, eax
0x180027925  test    eax, eax
0x180027927  js      loc_180027A87
0x18002792d  mov     rcx, [rsp+3A0h+var_350]
0x180027932  lea     r9, [rsp+3A0h+var_368]
0x180027937  lea     r8, [rsp+3A0h+pidl]
0x18002793c  mov     edx, 1
0x180027941  mov     rax, [rcx]
0x180027944  mov     rax, [rax+18h]
0x180027948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002794d  mov     ebx, eax
0x18002794f  test    eax, eax
0x180027951  jnz     loc_180027A76
0x180027957  cmp     [rsp+3A0h+var_368], 1
0x18002795c  jnz     loc_180027A76
0x180027962  mov     rax, [rdi]
0x180027965  lea     r9, [rsp+3A0h+var_358]
0x18002796a  lea     r8, [rsp+3A0h+pidl]
0x18002796f  mov     [rsp+3A0h+var_358], 40080000h
0x180027977  lea     edx, [rbx+1]
0x18002797a  mov     rcx, rdi
0x18002797d  mov     rax, [rax+48h]
0x180027981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027986  test    eax, eax
0x180027988  js      loc_180027A66
0x18002798e  mov     rax, [rdi]
0x180027991  lea     rcx, [rsp+3A0h+pshf]
0x180027996  mov     rdx, [rsp+3A0h+pidl]
0x18002799b  lea     r9, IID_IShellFolder
0x1800279a2  mov     [rsp+3A0h+var_380], rcx
0x1800279a7  xor     r8d, r8d
0x1800279aa  mov     rcx, rdi
0x1800279ad  mov     rax, [rax+28h]
0x1800279b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279b6  test    eax, eax
0x1800279b8  js      loc_180027A66
0x1800279be  xor     edx, edx; Val
0x1800279c0  lea     rcx, [rsp+3A0h+pstr]; void *
0x1800279c5  mov     r8d, 110h; Size
0x1800279cb  call    memset_0
0x1800279d0  mov     rax, [rdi]
0x1800279d3  lea     r9, [rsp+3A0h+pstr]
0x1800279d8  mov     rdx, [rsp+3A0h+pidl]
0x1800279dd  lea     r8d, [rbx+1]
0x1800279e1  mov     rcx, rdi
0x1800279e4  mov     rax, [rax+58h]
0x1800279e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279ed  test    eax, eax
0x1800279ef  jnz     short loc_180027A55
0x1800279f1  mov     rdx, [rsp+3A0h+pidl]; pidl
0x1800279f6  lea     r8, [rbp+2A0h+pszBuf]; pszBuf
0x1800279fa  mov     r9d, 104h; cchBuf
0x180027a00  lea     rcx, [rsp+3A0h+pstr]; pstr
0x180027a05  call    cs:__imp_StrRetToBufW
0x180027a0b  test    eax, eax
0x180027a0d  jnz     short loc_180027A55
0x180027a0f  movsxd  rax, ebx
0x180027a12  cmp     rax, 3
0x180027a16  jnb     short loc_180027A3B
0x180027a18  imul    rdx, rax, 20Ch
0x180027a1f  lea     rax, dword_1800453B4
0x180027a26  add     rdx, rax; String2
0x180027a29  lea     rcx, [rbp+2A0h+pszBuf]; String1
0x180027a2d  call    cs:__imp__wcsicmp
0x180027a33  test    eax, eax
0x180027a35  jz      short loc_180027A55
0x180027a37  inc     ebx
0x180027a39  jmp     short loc_180027A0F
0x180027a3b  mov     rdx, [rsp+3A0h+pshf]; pshf
0x180027a40  mov     rcx, rsi; this
0x180027a43  call    ?AddProgramsToList@CAddProgram@@AEAAJPEAUIShellFolder@@@Z; CAddProgram::AddProgramsToList(IShellFolder *)
0x180027a48  mov     rdx, [rsp+3A0h+pshf]; struct IShellFolder *
0x180027a4d  mov     rcx, rsi; this
0x180027a50  call    ?EnumFoldersAndAddPrograms@CAddProgram@@AEAAJPEAUIShellFolder@@@Z; CAddProgram::EnumFoldersAndAddPrograms(IShellFolder *)
0x180027a55  mov     rcx, [rsp+3A0h+pshf]
0x180027a5a  mov     rax, [rcx]
0x180027a5d  mov     rax, [rax+10h]
0x180027a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a66  mov     rcx, [rsp+3A0h+pidl]; pv
0x180027a6b  call    cs:__imp_CoTaskMemFree
0x180027a71  jmp     loc_18002792D
0x180027a76  mov     rcx, [rsp+3A0h+var_350]
0x180027a7b  mov     rax, [rcx]
0x180027a7e  mov     rax, [rax+10h]
0x180027a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a87  mov     eax, ebx
0x180027a89  mov     rcx, [rbp+2A0h+var_20]
0x180027a90  xor     rcx, rsp; StackCookie
0x180027a93  call    __security_check_cookie
0x180027a98  mov     rbx, [rsp+3A0h+arg_10]
0x180027aa0  add     rsp, 390h
0x180027aa7  pop     rdi
0x180027aa8  pop     rsi
0x180027aa9  pop     rbp
0x180027aaa  retn
```
