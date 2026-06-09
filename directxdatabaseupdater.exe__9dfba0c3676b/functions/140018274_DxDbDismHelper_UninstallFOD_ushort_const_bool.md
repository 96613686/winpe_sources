# DxDbDismHelper::UninstallFOD(ushort const *,bool *)

- ea: `0x140018274`
- end: `0x1400183a9`
- name: `?UninstallFOD@DxDbDismHelper@@QEAAJPEBGPEA_N@Z`
- size: `309`
- prototype: `__int64 __fastcall(DxDbDismHelper *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007ad8`

## callees

- `0x14000a4bc`
- `0x1400181fc`
- `0x140018274`
- `0x1400184b4`

## import_xrefs

- `DismApi!_DismRemovePackageEx` at `0x14001837d`
- `DismApi!_DismRemovePackageEx` at `0x14001837d`
- `DismApi!DismGetPackages` at `0x1400182d7`
- `DismApi!DismGetPackages` at `0x1400182d7`

## string_xrefs

- `0x1400182ae`: `onecore\windows\directx\database\updater\dismhelper\dismhelper.cpp`
- `0x140018391`: `onecore\windows\directx\database\updater\dismhelper\dismhelper.cpp`

## pseudocode

```c
__int64 __fastcall DxDbDismHelper::UninstallFOD(DxDbDismHelper *this, const unsigned __int16 *a2, bool *a3)
{
  int Packages; // edi
  __int64 v6; // rdx
  __int64 v8; // rcx
  unsigned int v9; // ebp
  __int64 v10; // r15
  unsigned int v11; // edi
  size_t v12; // r8
  __int64 v13; // r14
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( a3 )
    *a3 = 0;
  Packages = DxDbDismHelper::Init(this);
  if ( Packages < 0 )
  {
    v6 = 89;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\dismhelper\\dismhelper.cpp",
      (const char *)(unsigned int)Packages,
      v16);
    return (unsigned int)Packages;
  }
  v8 = *(unsigned int *)this;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  Packages = DismGetPackages(v8, (char *)this + 8, (char *)this + 16);
  if ( Packages < 0 )
  {
    v6 = 93;
    goto LABEL_5;
  }
  v9 = *((_DWORD *)this + 4);
  if ( !v9 )
    goto LABEL_14;
  v10 = *((_QWORD *)this + 1);
  v11 = 0;
  while ( 1 )
  {
    v12 = -1;
    do
      ++v12;
    while ( DxDbDismHelper::g_dxDbFODPackageName[v12] );
    v13 = 32LL * v11;
    if ( !wcsncmp_0(*(const wchar_t **)(v13 + v10), L"Microsoft-OneCore-DirectX-Database-FOD-Package", v12) )
      break;
    if ( ++v11 >= v9 )
      goto LABEL_14;
  }
  if ( v11 == -1 || (*(_DWORD *)(v13 + v10 + 8) & 0xFFFFFFFC) == 0 && *(_DWORD *)(v13 + v10 + 8) != 2 )
  {
LABEL_14:
    if ( a3 )
      *a3 = 1;
    return 0;
  }
  v14 = _DismRemovePackageEx(*(unsigned int *)this, *(_QWORD *)(v13 + v10), 1, 2);
  v15 = v14;
  if ( v14 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecore\\windows\\directx\\database\\updater\\dismhelper\\dismhelper.cpp",
    (const char *)(unsigned int)v14,
    0);
  return v15;
}

```

## disassembly

```asm
0x140018274  push    rbx
0x140018276  push    rbp
0x140018277  push    rsi
0x140018278  push    rdi
0x140018279  push    r12
0x14001827b  push    r13
0x14001827d  push    r14
0x14001827f  push    r15
0x140018281  sub     rsp, 48h
0x140018285  xor     r12d, r12d
0x140018288  mov     rbx, r8
0x14001828b  mov     rsi, rcx
0x14001828e  test    r8, r8
0x140018291  jz      short loc_140018296
0x140018293  mov     [r8], r12b
0x140018296  call    ?Init@DxDbDismHelper@@QEAAJXZ; DxDbDismHelper::Init(void)
0x14001829b  mov     edi, eax
0x14001829d  test    eax, eax
0x14001829f  jns     short loc_1400182C1
0x1400182a1  mov     edx, 59h ; 'Y'; void *
0x1400182a6  mov     rcx, [rsp+88h]; this
0x1400182ae  lea     r8, aOnecoreWindows_3; "onecore\\windows\\directx\\database\\up"...
0x1400182b5  mov     r9d, edi; char *
0x1400182b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400182bd  mov     eax, edi
0x1400182bf  jmp     short loc_140018334
0x1400182c1  mov     ecx, [rsi]
0x1400182c3  lea     r15, [rsi+8]
0x1400182c7  lea     r14, [rsi+10h]
0x1400182cb  mov     [r15], r12
0x1400182ce  mov     r8, r14
0x1400182d1  mov     [r14], r12d
0x1400182d4  mov     rdx, r15
0x1400182d7  call    cs:__imp_DismGetPackages
0x1400182dd  mov     edi, eax
0x1400182df  test    eax, eax
0x1400182e1  jns     short loc_1400182EA
0x1400182e3  mov     edx, 5Dh ; ']'
0x1400182e8  jmp     short loc_1400182A6
0x1400182ea  mov     ebp, [r14]
0x1400182ed  test    ebp, ebp
0x1400182ef  jz      short loc_14001832A
0x1400182f1  mov     r15, [r15]
0x1400182f4  lea     r13, ?g_dxDbFODPackageName@DxDbDismHelper@@2QBGB; "Microsoft-OneCore-DirectX-Database-FOD-"...
0x1400182fb  mov     edi, r12d
0x1400182fe  or      r8, 0FFFFFFFFFFFFFFFFh
0x140018302  inc     r8; MaxCount
0x140018305  cmp     [r13+r8*2+0], r12w
0x14001830b  jnz     short loc_140018302
0x14001830d  mov     r14d, edi
0x140018310  mov     rdx, r13; String2
0x140018313  shl     r14, 5
0x140018317  mov     rcx, [r14+r15]; String1
0x14001831b  call    wcsncmp_0
0x140018320  test    eax, eax
0x140018322  jz      short loc_140018345
0x140018324  inc     edi
0x140018326  cmp     edi, ebp
0x140018328  jb      short loc_1400182FE
0x14001832a  test    rbx, rbx
0x14001832d  jz      short loc_140018332
0x14001832f  mov     byte ptr [rbx], 1
0x140018332  xor     eax, eax
0x140018334  add     rsp, 48h
0x140018338  pop     r15
0x14001833a  pop     r14
0x14001833c  pop     r13
0x14001833e  pop     r12
0x140018340  pop     rdi
0x140018341  pop     rsi
0x140018342  pop     rbp
0x140018343  pop     rbx
0x140018344  retn
0x140018345  cmp     edi, 0FFFFFFFFh
0x140018348  jz      short loc_14001832A
0x14001834a  test    dword ptr [r14+r15+8], 0FFFFFFFCh
0x140018353  mov     r9d, 2
0x140018359  jnz     short loc_140018362
0x14001835b  cmp     [r14+r15+8], r9d
0x140018360  jnz     short loc_14001832A
0x140018362  mov     rdx, [r14+r15]
0x140018366  mov     r8d, 1
0x14001836c  mov     ecx, [rsi]
0x14001836e  mov     [rsp+88h+var_58], r12
0x140018373  mov     [rsp+88h+var_60], r12
0x140018378  mov     qword ptr [rsp+88h+var_68], r12; int
0x14001837d  call    cs:__imp__DismRemovePackageEx
0x140018383  mov     ebx, eax
0x140018385  test    eax, eax
0x140018387  jns     short loc_140018332
0x140018389  mov     rcx, [rsp+88h]; this
0x140018391  lea     r8, aOnecoreWindows_3; "onecore\\windows\\directx\\database\\up"...
0x140018398  mov     r9d, eax; char *
0x14001839b  mov     edx, 7Bh ; '{'; void *
0x1400183a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400183a5  mov     eax, ebx
0x1400183a7  jmp     short loc_140018334
```
