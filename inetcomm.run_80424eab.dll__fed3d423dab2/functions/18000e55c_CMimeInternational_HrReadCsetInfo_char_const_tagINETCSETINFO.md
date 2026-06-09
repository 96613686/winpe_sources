# CMimeInternational::_HrReadCsetInfo(char const *,tagINETCSETINFO * *)

- ea: `0x18000e55c`
- end: `0x18000e7fa`
- name: `?_HrReadCsetInfo@CMimeInternational@@AEAAJPEBDPEAPEAUtagINETCSETINFO@@@Z`
- size: `670`
- prototype: `__int64 __fastcall(CMimeInternational *__hidden this, const char *, struct tagINETCSETINFO **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e400`

## callees

- `0x180002098`
- `0x18000e55c`
- `0x180012cd0`
- `0x180019dd8`
- `0x180019fe8`
- `0x180033fa4`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18000e65d`
- `KERNEL32!MultiByteToWideChar` at `0x18000e65d`
- `KERNEL32!GetLastError` at `0x18000e667`
- `KERNEL32!GetLastError` at `0x18000e667`
- `ole32!CoCreateInstance` at `0x18000e5d5`
- `ole32!CoCreateInstance` at `0x18000e5fc`
- `ole32!CoCreateInstance` at `0x18000e5d5`
- `ole32!CoCreateInstance` at `0x18000e5fc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000e627`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000e627`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7d4`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e642`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e642`

## pseudocode

```c
__int64 __fastcall CMimeInternational::_HrReadCsetInfo(
        CMimeInternational *this,
        const char *a2,
        struct tagINETCSETINFO **a3)
{
  WCHAR *v6; // rdi
  int v7; // ebx
  __int64 v8; // rdx
  OLECHAR *v9; // rax
  UINT v10; // eax
  signed int LastError; // eax
  LPVOID v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // r8d
  _DWORD *v15; // rax
  _DWORD *v16; // r15
  int v17; // r8d
  unsigned int v19; // [rsp+30h] [rbp-79h] BYREF
  LPVOID v20; // [rsp+38h] [rbp-71h] BYREF
  LPVOID ppv[2]; // [rsp+40h] [rbp-69h] BYREF
  _DWORD v22[28]; // [rsp+50h] [rbp-59h] BYREF

  v20 = 0;
  ppv[0] = 0;
  memset_0(v22, 0, 0x6Cu);
  v6 = 0;
  *a3 = 0;
  if ( (g_dwCompatMode & 2) == 0 || CoCreateInstance(&CLSID_CMultiLanguage, 0, 3u, &IID_IMultiLanguage2, ppv) < 0 )
  {
    v7 = CoCreateInstance(&CLSID_CMultiLanguage, 0, 3u, &IID_IMultiLanguage, &v20);
    if ( v7 < 0 )
      goto LABEL_29;
  }
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  v9 = SysAllocStringLen(0, v8);
  v6 = v9;
  if ( !v9 )
    goto LABEL_10;
  v10 = SysStringLen(v9);
  if ( MultiByteToWideChar(0, 0, a2, -1, v6, v10 + 1) )
  {
    v12 = ppv[0];
    if ( !ppv[0] )
      v12 = v20;
    if ( (*(int (__fastcall **)(LPVOID, WCHAR *, _DWORD *))(*(_QWORD *)v12 + 56LL))(v12, v6, v22) < 0 )
    {
      v7 = -2146644475;
      goto LABEL_29;
    }
    v13 = *((_DWORD *)this + 4);
    if ( v13 + 1 < v13 )
    {
      v7 = -2147024362;
      goto LABEL_29;
    }
    v14 = *((_DWORD *)this + 5);
    v7 = 0;
    if ( v13 + 1 >= v14 )
    {
      v19 = 0;
      v7 = SafeScaleSumD2((unsigned int)&v19, 8, v14, 5, 0);
      if ( v7 < 0 )
        goto LABEL_29;
      v7 = HrRealloc((void **)this + 3, v19);
      if ( v7 < 0 )
        goto LABEL_29;
      *((_DWORD *)this + 5) += 5;
    }
    v15 = (_DWORD *)((__int64 (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 152);
    v16 = v15;
    if ( !v15 )
    {
LABEL_10:
      v7 = -2147024882;
      goto LABEL_29;
    }
    memset_0(v15, 0, 0x98u);
    v16[36] = *((_DWORD *)this + 4);
    *((_QWORD *)v16 + 16) = ((unsigned __int64)*((unsigned __int16 *)this + 8) << 16)
                          | (unsigned __int16)(*((_WORD *)this + 6) + 40);
    StringCchCopyA((char *)v16, 0x80u, a2);
    v16[35] = v22[1];
    v16[34] = v22[0];
    *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * *((unsigned int *)this + 4)) = v16;
    *a3 = (struct tagINETCSETINFO *)v16;
    v17 = *((_DWORD *)this + 4);
    *((_DWORD *)this + 4) = v17 + 1;
    CMimeInternational::_QuickSortCsetInfo(this, 0, v17);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2147467259;
  }
LABEL_29:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v20);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(ppv);
  if ( v6 )
    SysFreeString(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e55c  push    rbp
0x18000e55e  push    rbx
0x18000e55f  push    rsi
0x18000e560  push    rdi
0x18000e561  push    r12
0x18000e563  push    r14
0x18000e565  push    r15
0x18000e567  lea     rbp, [rsp-27h]
0x18000e56c  sub     rsp, 0D0h
0x18000e573  mov     rax, cs:__security_cookie
0x18000e57a  xor     rax, rsp
0x18000e57d  mov     [rbp+57h+var_40], rax
0x18000e581  mov     r14, rdx
0x18000e584  mov     [rbp+57h+var_C8], 0
0x18000e58c  xor     edx, edx; Val
0x18000e58e  mov     [rbp+57h+var_C0], 0
0x18000e596  mov     r12, r8
0x18000e599  mov     rsi, rcx
0x18000e59c  lea     rcx, [rbp+57h+var_B0]; void *
0x18000e5a0  lea     r8d, [rdx+6Ch]; Size
0x18000e5a4  call    memset_0
0x18000e5a9  xor     edi, edi
0x18000e5ab  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18000e5b2  xor     edx, edx; pUnkOuter
0x18000e5b4  mov     [r12], rdi
0x18000e5b8  test    byte ptr cs:?g_dwCompatMode@@3KA, 2; ulong g_dwCompatMode
0x18000e5bf  lea     r8d, [rdi+3]; dwClsContext
0x18000e5c3  jz      short loc_18000E5EC
0x18000e5c5  lea     rax, [rbp+57h+var_C0]
0x18000e5c9  lea     r9, IID_IMultiLanguage2; riid
0x18000e5d0  mov     [rsp+100h+ppv], rax; ppv
0x18000e5d5  call    cs:__imp_CoCreateInstance
0x18000e5db  test    eax, eax
0x18000e5dd  jns     short loc_18000E60C
0x18000e5df  xor     edx, edx; pUnkOuter
0x18000e5e1  lea     r8d, [rdi+3]; dwClsContext
0x18000e5e5  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18000e5ec  lea     rax, [rbp+57h+var_C8]
0x18000e5f0  lea     r9, IID_IMultiLanguage; riid
0x18000e5f7  mov     [rsp+100h+ppv], rax; ppv
0x18000e5fc  call    cs:__imp_CoCreateInstance
0x18000e602  mov     ebx, eax
0x18000e604  test    eax, eax
0x18000e606  js      loc_18000E7BA
0x18000e60c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e610  test    r14, r14
0x18000e613  jz      short loc_18000E623
0x18000e615  mov     rdx, rbx
0x18000e618  inc     rdx
0x18000e61b  cmp     [r14+rdx], dil
0x18000e61f  jnz     short loc_18000E618
0x18000e621  jmp     short loc_18000E625
0x18000e623  xor     edx, edx; ui
0x18000e625  xor     ecx, ecx; strIn
0x18000e627  call    cs:__imp_SysAllocStringLen
0x18000e62d  mov     rdi, rax
0x18000e630  test    rax, rax
0x18000e633  jnz     short loc_18000E63F
0x18000e635  mov     ebx, 8007000Eh
0x18000e63a  jmp     loc_18000E7BA
0x18000e63f  mov     rcx, rdi; pbstr
0x18000e642  call    cs:__imp_SysStringLen
0x18000e648  mov     r9d, ebx; cbMultiByte
0x18000e64b  mov     r8, r14; lpMultiByteStr
0x18000e64e  inc     eax
0x18000e650  xor     edx, edx; dwFlags
0x18000e652  mov     [rsp+100h+cchWideChar], eax; cchWideChar
0x18000e656  xor     ecx, ecx; CodePage
0x18000e658  mov     [rsp+100h+ppv], rdi; lpWideCharStr
0x18000e65d  call    cs:__imp_MultiByteToWideChar
0x18000e663  test    eax, eax
0x18000e665  jnz     short loc_18000E68B
0x18000e667  call    cs:__imp_GetLastError
0x18000e66d  mov     ebx, eax
0x18000e66f  test    eax, eax
0x18000e671  jle     short loc_18000E67C
0x18000e673  movzx   ebx, ax
0x18000e676  or      ebx, 80070000h
0x18000e67c  test    ebx, ebx
0x18000e67e  mov     eax, 80004005h
0x18000e683  cmovns  ebx, eax
0x18000e686  jmp     loc_18000E7BA
0x18000e68b  mov     rcx, [rbp+57h+var_C0]
0x18000e68f  lea     r8, [rbp+57h+var_B0]
0x18000e693  mov     rdx, rdi
0x18000e696  test    rcx, rcx
0x18000e699  jz      short loc_18000E6B5
0x18000e69b  mov     rax, [rcx]
0x18000e69e  mov     rax, [rax+38h]
0x18000e6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a7  test    eax, eax
0x18000e6a9  jns     short loc_18000E6BB
0x18000e6ab  mov     ebx, 800CCE05h
0x18000e6b0  jmp     loc_18000E7BA
0x18000e6b5  mov     rcx, [rbp+57h+var_C8]
0x18000e6b9  jmp     short loc_18000E69B
0x18000e6bb  mov     eax, [rsi+10h]
0x18000e6be  lea     ecx, [rax+1]
0x18000e6c1  cmp     ecx, eax
0x18000e6c3  jb      loc_18000E7B5
0x18000e6c9  mov     r8d, [rsi+14h]
0x18000e6cd  xor     ebx, ebx
0x18000e6cf  cmp     ecx, r8d
0x18000e6d2  jb      short loc_18000E70F
0x18000e6d4  lea     edx, [rbx+8]
0x18000e6d7  mov     [rbp+57h+var_D0], ebx
0x18000e6da  lea     r9d, [rbx+5]
0x18000e6de  mov     dword ptr [rsp+100h+ppv], ebx
0x18000e6e2  lea     rcx, [rbp+57h+var_D0]
0x18000e6e6  call    SafeScaleSumD2
0x18000e6eb  mov     ebx, eax
0x18000e6ed  test    eax, eax
0x18000e6ef  js      loc_18000E7BA
0x18000e6f5  mov     edx, [rbp+57h+var_D0]; unsigned int
0x18000e6f8  lea     rcx, [rsi+18h]; void **
0x18000e6fc  call    ?HrRealloc@@YAJPEAPEAXK@Z; HrRealloc(void * *,ulong)
0x18000e701  mov     ebx, eax
0x18000e703  test    eax, eax
0x18000e705  js      loc_18000E7BA
0x18000e70b  add     dword ptr [rsi+14h], 5
0x18000e70f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000e716  mov     edx, 98h
0x18000e71b  mov     rax, [rcx]
0x18000e71e  mov     rax, [rax+18h]
0x18000e722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e727  mov     r15, rax
0x18000e72a  test    rax, rax
0x18000e72d  jz      loc_18000E635
0x18000e733  xor     edx, edx; Val
0x18000e735  mov     r8d, 98h; Size
0x18000e73b  mov     rcx, rax; void *
0x18000e73e  call    memset_0
0x18000e743  mov     eax, [rsi+10h]
0x18000e746  mov     r8, r14; char *
0x18000e749  mov     [r15+90h], eax
0x18000e750  mov     edx, 80h; unsigned __int64
0x18000e755  movzx   eax, word ptr [rsi+0Ch]
0x18000e759  add     ax, 28h ; '('
0x18000e75d  movzx   ecx, ax
0x18000e760  movzx   eax, word ptr [rsi+10h]
0x18000e764  shl     rax, 10h
0x18000e768  or      rcx, rax
0x18000e76b  mov     [r15+80h], rcx
0x18000e772  mov     rcx, r15; char *
0x18000e775  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000e77a  mov     r10d, [rbp+57h+var_AC]
0x18000e77e  mov     rcx, rsi; this
0x18000e781  mov     [r15+8Ch], r10d
0x18000e788  mov     eax, [rbp+57h+var_B0]
0x18000e78b  mov     [r15+88h], eax
0x18000e792  mov     edx, [rsi+10h]
0x18000e795  mov     rax, [rsi+18h]
0x18000e799  mov     [rax+rdx*8], r15
0x18000e79d  xor     edx, edx; int
0x18000e79f  mov     [r12], r15
0x18000e7a3  mov     r8d, [rsi+10h]; int
0x18000e7a7  lea     eax, [r8+1]
0x18000e7ab  mov     [rsi+10h], eax
0x18000e7ae  call    ?_QuickSortCsetInfo@CMimeInternational@@AEAAXJJ@Z; CMimeInternational::_QuickSortCsetInfo(long,long)
0x18000e7b3  jmp     short loc_18000E7BA
0x18000e7b5  mov     ebx, 80070216h
0x18000e7ba  lea     rcx, [rbp+57h+var_C8]
0x18000e7be  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000e7c3  lea     rcx, [rbp+57h+var_C0]
0x18000e7c7  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000e7cc  test    rdi, rdi
0x18000e7cf  jz      short loc_18000E7DA
0x18000e7d1  mov     rcx, rdi; bstrString
0x18000e7d4  call    cs:__imp_SysFreeString
0x18000e7da  mov     eax, ebx
0x18000e7dc  mov     rcx, [rbp+57h+var_40]
0x18000e7e0  xor     rcx, rsp; StackCookie
0x18000e7e3  call    __security_check_cookie
0x18000e7e8  add     rsp, 0D0h
0x18000e7ef  pop     r15
0x18000e7f1  pop     r14
0x18000e7f3  pop     r12
0x18000e7f5  pop     rdi
0x18000e7f6  pop     rsi
0x18000e7f7  pop     rbx
0x18000e7f8  pop     rbp
0x18000e7f9  retn
```
