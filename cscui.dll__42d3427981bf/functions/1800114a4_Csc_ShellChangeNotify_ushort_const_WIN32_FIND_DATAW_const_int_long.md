# Csc_ShellChangeNotify(ushort const *,_WIN32_FIND_DATAW const *,int,long)

- ea: `0x1800114a4`
- end: `0x1800115af`
- name: `?Csc_ShellChangeNotify@@YAXPEBGPEBU_WIN32_FIND_DATAW@@HJ@Z`
- size: `267`
- prototype: `void __fastcall(PCWSTR pszPath, const struct _WIN32_FIND_DATAW *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000db90`
- `0x18000dfc4`

## callees

- `0x1800114a4`
- `0x180011cd0`
- `0x18004d010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x180011501`
- `SHELL32!SHParseDisplayName` at `0x180011501`
- `SHELL32!SHChangeNotify` at `0x18001158b`
- `SHELL32!SHChangeNotify` at `0x18001158b`
- `SHELL32!__imp_ILCreateFromPathW` at `0x18001152b`
- `SHELL32!__imp_ILCreateFromPathW` at `0x18001152b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011596`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011596`

## pseudocode

```c
void __fastcall Csc_ShellChangeNotify(WCHAR *pszPath, const struct _WIN32_FIND_DATAW *a2, int a3, LONG a4)
{
  HRESULT v7; // ebx
  LPITEMIDLIST v8; // r8
  UINT v9; // edx
  LONG v10; // ecx
  int v11; // r9d
  IBindCtx *pbc; // [rsp+30h] [rbp-28h] BYREF
  LPITEMIDLIST ppidl; // [rsp+60h] [rbp+8h] BYREF

  ppidl = 0;
  if ( pszPath )
  {
    if ( a2
      && *pszPath
      && (pbc = 0, _CreateFileSysBindCtx((struct IBindCtx *)pszPath, a2, &pbc) >= 0)
      && (v7 = SHParseDisplayName(pszPath, pbc, &ppidl, 0, 0),
          ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc),
          v7 >= 0) )
    {
      v8 = ppidl;
      v9 = 0;
    }
    else
    {
      ppidl = ILCreateFromPathW(pszPath);
      v8 = ppidl;
      if ( ppidl )
      {
        v9 = 0;
      }
      else
      {
        v9 = 5;
        v8 = (LPITEMIDLIST)pszPath;
      }
    }
    v10 = 0x2000;
    if ( a4 )
      v10 = a4;
  }
  else
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
  }
  v11 = dword_180069464++;
  if ( v11 > 8 || a3 )
  {
    v9 |= 0x3000u;
    dword_180069464 = 0;
  }
  SHChangeNotify(v10, v9, v8, 0);
  CoTaskMemFree(ppidl);
}

```

## disassembly

```asm
0x1800114a4  mov     rax, rsp
0x1800114a7  mov     [rax+10h], rbx
0x1800114ab  mov     [rax+18h], rbp
0x1800114af  push    rsi
0x1800114b0  push    rdi
0x1800114b1  push    r14
0x1800114b3  sub     rsp, 40h
0x1800114b7  xor     r14d, r14d
0x1800114ba  mov     esi, r9d
0x1800114bd  mov     [rax+8], r14
0x1800114c1  mov     ebp, r8d
0x1800114c4  mov     rdi, rcx
0x1800114c7  test    rcx, rcx
0x1800114ca  jz      loc_180011557
0x1800114d0  test    rdx, rdx
0x1800114d3  jz      short loc_180011528
0x1800114d5  cmp     [rcx], r14w
0x1800114d9  jz      short loc_180011528
0x1800114db  lea     r8, [rax-28h]; struct IBindCtx **
0x1800114df  mov     [rax-28h], r14
0x1800114e3  call    ?_CreateFileSysBindCtx@@YAJPEAUIBindCtx@@PEBU_WIN32_FIND_DATAW@@PEAPEAU1@@Z; _CreateFileSysBindCtx(IBindCtx *,_WIN32_FIND_DATAW const *,IBindCtx * *)
0x1800114e8  test    eax, eax
0x1800114ea  js      short loc_180011528
0x1800114ec  mov     rdx, [rsp+58h+pbc]; pbc
0x1800114f1  lea     r8, [rsp+58h+ppidl]; ppidl
0x1800114f6  xor     r9d, r9d; sfgaoIn
0x1800114f9  mov     [rsp+58h+psfgaoOut], r14; psfgaoOut
0x1800114fe  mov     rcx, rdi; pszName
0x180011501  call    cs:__imp_SHParseDisplayName
0x180011507  mov     rcx, [rsp+58h+pbc]
0x18001150c  mov     ebx, eax
0x18001150e  mov     rdx, [rcx]
0x180011511  mov     rax, [rdx+10h]
0x180011515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001151a  test    ebx, ebx
0x18001151c  js      short loc_180011528
0x18001151e  mov     r8, [rsp+58h+ppidl]
0x180011523  mov     edx, r14d
0x180011526  jmp     short loc_18001154B
0x180011528  mov     rcx, rdi; pszPath
0x18001152b  call    cs:__imp_ILCreateFromPathW
0x180011531  mov     [rsp+58h+ppidl], rax
0x180011536  mov     r8, rax
0x180011539  test    rax, rax
0x18001153c  jz      short loc_180011543
0x18001153e  mov     edx, r14d
0x180011541  jmp     short loc_18001154B
0x180011543  mov     edx, 5
0x180011548  mov     r8, rdi
0x18001154b  test    esi, esi
0x18001154d  mov     ecx, 2000h
0x180011552  cmovnz  ecx, esi
0x180011555  jmp     short loc_180011560
0x180011557  mov     r8, r14; dwItem1
0x18001155a  mov     edx, r14d
0x18001155d  mov     ecx, r14d; wEventId
0x180011560  mov     eax, cs:dword_180069464
0x180011566  mov     r9d, eax
0x180011569  inc     eax
0x18001156b  mov     cs:dword_180069464, eax
0x180011571  cmp     r9d, 8
0x180011575  jg      short loc_18001157B
0x180011577  test    ebp, ebp
0x180011579  jz      short loc_180011588
0x18001157b  or      edx, 3000h; uFlags
0x180011581  mov     cs:dword_180069464, r14d
0x180011588  xor     r9d, r9d; dwItem2
0x18001158b  call    cs:__imp_SHChangeNotify
0x180011591  mov     rcx, [rsp+58h+ppidl]; pv
0x180011596  call    cs:__imp_CoTaskMemFree
0x18001159c  mov     rbx, [rsp+58h+arg_8]
0x1800115a1  mov     rbp, [rsp+58h+arg_10]
0x1800115a6  add     rsp, 40h
0x1800115aa  pop     r14
0x1800115ac  pop     rdi
0x1800115ad  pop     rsi
0x1800115ae  retn
```
