# CreateFileSysBindCtx(_WIN32_FIND_DATAW const *,IBindCtx * *)

- ea: `0x1800193e8`
- end: `0x1800194ce`
- name: `?CreateFileSysBindCtx@@YAJPEBU_WIN32_FIND_DATAW@@PEAPEAUIBindCtx@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(const struct _WIN32_FIND_DATAW *, struct IBindCtx **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b814`

## callees

- `0x180006270`
- `0x1800193e8`
- `0x1800195b8`
- `0x18003d010`

## import_xrefs

- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180019410`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180019410`

## pseudocode

```c
__int64 __fastcall CreateFileSysBindCtx(const struct _WIN32_FIND_DATAW *a1, struct IBindCtx **a2)
{
  HRESULT BindCtx; // edi
  LPBC v4; // rcx
  LPBC v5; // rcx
  struct IBindCtxVtbl *lpVtbl; // rax
  IBindCtx *v7; // rbx
  _QWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  BindCtx = CreateBindCtx(0, a2);
  if ( BindCtx >= 0 )
  {
    v4 = *a2;
    v9[0] = 16;
    v9[1] = 4096;
    BindCtx = ((__int64 (__fastcall *)(LPBC, _QWORD *))v4->lpVtbl->SetBindOptions)(v4, v9);
    if ( BindCtx >= 0 )
    {
      v9[0] = 0;
      BindCtx = ATL::CComObject<CFileSystemBindData>::CreateInstance(v9);
      if ( BindCtx >= 0 )
      {
        v7 = (IBindCtx *)v9[0];
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[0] + 8LL))(v9[0]);
        BindCtx = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, IBindCtx *))(*a2)->lpVtbl->RegisterObjectParam)(
                    *a2,
                    L"File System Bind Data",
                    v7);
        v5 = v7;
        lpVtbl = v7->lpVtbl;
        goto LABEL_7;
      }
    }
    else
    {
      v5 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        lpVtbl = v5->lpVtbl;
LABEL_7:
        ((void (__fastcall *)(LPBC))lpVtbl->Release)(v5);
      }
    }
  }
  return (unsigned int)BindCtx;
}

```

## disassembly

```asm
0x1800193e8  mov     [rsp+arg_0], rbx
0x1800193ed  mov     [rsp+arg_10], rsi
0x1800193f2  push    rdi
0x1800193f3  sub     rsp, 40h
0x1800193f7  mov     rax, cs:__security_cookie
0x1800193fe  xor     rax, rsp
0x180019401  mov     [rsp+48h+var_18], rax
0x180019406  xor     ebx, ebx
0x180019408  xor     ecx, ecx; reserved
0x18001940a  mov     [rdx], rbx
0x18001940d  mov     rsi, rdx
0x180019410  call    cs:__imp_CreateBindCtx
0x180019416  mov     edi, eax
0x180019418  test    eax, eax
0x18001941a  js      loc_1800194AF
0x180019420  mov     rcx, [rsi]
0x180019423  lea     rdx, [rsp+48h+var_28]
0x180019428  mov     [rsp+48h+var_28], 10h
0x180019431  mov     [rsp+48h+var_20], 1000h
0x18001943a  mov     rax, [rcx]
0x18001943d  mov     rax, [rax+30h]
0x180019441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019446  mov     edi, eax
0x180019448  test    eax, eax
0x18001944a  jns     short loc_18001945C
0x18001944c  mov     rcx, [rsi]
0x18001944f  test    rcx, rcx
0x180019452  jz      short loc_1800194AF
0x180019454  mov     [rsi], rbx
0x180019457  mov     rax, [rcx]
0x18001945a  jmp     short loc_1800194A6
0x18001945c  lea     rcx, [rsp+48h+var_28]
0x180019461  mov     [rsp+48h+var_28], rbx
0x180019466  call    ?CreateInstance@?$CComObject@VCFileSystemBindData@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileSystemBindData>::CreateInstance(ATL::CComObject<CFileSystemBindData> * *)
0x18001946b  mov     edi, eax
0x18001946d  test    eax, eax
0x18001946f  js      short loc_1800194AF
0x180019471  mov     rbx, [rsp+48h+var_28]
0x180019476  mov     rcx, rbx
0x180019479  mov     rax, [rbx]
0x18001947c  mov     rax, [rax+8]
0x180019480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019485  mov     rcx, [rsi]
0x180019488  lea     rdx, aFileSystemBind; "File System Bind Data"
0x18001948f  mov     r8, rbx
0x180019492  mov     rax, [rcx]
0x180019495  mov     rax, [rax+48h]
0x180019499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001949e  mov     edi, eax
0x1800194a0  mov     rcx, rbx
0x1800194a3  mov     rax, [rbx]
0x1800194a6  mov     rax, [rax+10h]
0x1800194aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194af  mov     eax, edi
0x1800194b1  mov     rcx, [rsp+48h+var_18]
0x1800194b6  xor     rcx, rsp; StackCookie
0x1800194b9  call    __security_check_cookie
0x1800194be  mov     rbx, [rsp+48h+arg_0]
0x1800194c3  mov     rsi, [rsp+48h+arg_10]
0x1800194c8  add     rsp, 40h
0x1800194cc  pop     rdi
0x1800194cd  retn
```
