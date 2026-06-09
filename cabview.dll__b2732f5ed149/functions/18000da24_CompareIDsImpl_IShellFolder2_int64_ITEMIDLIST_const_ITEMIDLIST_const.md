# CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x18000da24`
- end: `0x18000dc5c`
- name: `?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST@@2@Z`
- size: `568`
- prototype: `int(struct IShellFolder2 *, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d9d0`

## callees

- `0x180002620`
- `0x18000da24`
- `0x18000f200`
- `0x18000f488`
- `0x18001230c`
- `0x180013010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18000dc2b`
- `SHELL32!__imp_ILFree` at `0x18000dc34`
- `SHELL32!__imp_ILFree` at `0x18000dc2b`
- `SHELL32!__imp_ILFree` at `0x18000dc34`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18000db4c`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18000dbc8`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18000db4c`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18000dbc8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000dbd6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000dbd6`
- `OLEAUT32!__imp_VariantInit` at `0x18000db83`
- `OLEAUT32!__imp_VariantInit` at `0x18000dbbd`
- `OLEAUT32!__imp_VariantInit` at `0x18000db83`
- `OLEAUT32!__imp_VariantInit` at `0x18000dbbd`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc18`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc22`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc18`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc22`
- `PROPSYS!VariantCompare` at `0x18000dbe4`
- `PROPSYS!VariantCompare` at `0x18000dbe4`

## pseudocode

```c
__int64 __fastcall CompareIDsImpl(struct IShellFolder2 *a1, __int64 a2, struct _ITEMIDLIST *a3, struct _ITEMIDLIST *a4)
{
  int v7; // ebx
  __int64 cb; // rcx
  ITEMIDLIST *v9; // r14
  _WORD *v10; // rcx
  LPITEMIDLIST v11; // r12
  ITEMIDLIST *v12; // r15
  _WORD *v13; // rcx
  int v14; // eax
  struct IShellFolder2Vtbl *lpVtbl; // rax
  const WCHAR *v16; // rdx
  int v17; // ebx
  struct IShellFolder2Vtbl *v18; // rax
  const WCHAR *v19; // rdx
  int v20; // eax
  LPITEMIDLIST pidl; // [rsp+30h] [rbp-49h] BYREF
  __int64 v23; // [rsp+38h] [rbp-41h]
  __int128 v24; // [rsp+40h] [rbp-39h] BYREF
  int v25; // [rsp+50h] [rbp-29h]
  VARIANTARG var2; // [rsp+58h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-9h] BYREF

  v23 = a2;
  v7 = -2147024809;
  if ( a3 && a4 && a3->mkid.cb && a4->mkid.cb )
  {
    if ( a3 == a4 )
    {
      return 0;
    }
    else
    {
      cb = a3->mkid.cb;
      v9 = 0;
      pidl = 0;
      v10 = (USHORT *)((char *)&a3->mkid.cb + cb);
      if ( v10 && *v10 )
      {
        v7 = SHILCloneFirst(a3, &pidl);
        if ( v7 < 0 )
          return (unsigned int)v7;
        v9 = pidl;
        v11 = pidl;
      }
      else
      {
        v11 = a3;
      }
      v12 = 0;
      pidl = 0;
      if ( a4->mkid.cb && (v13 = (USHORT *)((char *)&a4->mkid.cb + a4->mkid.cb)) != 0 && *v13 )
      {
        v14 = SHILCloneFirst(a4, &pidl);
        v12 = pidl;
        v7 = v14;
      }
      else
      {
        pidl = a4;
        v7 = 0;
      }
      if ( v7 >= 0 )
      {
        v25 = 0;
        lpVtbl = a1->lpVtbl;
        v24 = 0;
        v7 = ((__int64 (__fastcall *)(struct IShellFolder2 *, _QWORD, __int128 *))lpVtbl->MapColumnToSCID)(
               a1,
               (unsigned __int16)v23,
               &v24);
        if ( v7 >= 0 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          v17 = 0;
          if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v16) )
            v17 = SHCoInitialize();
          if ( ((int (__fastcall *)(struct IShellFolder2 *, LPITEMIDLIST, __int128 *, VARIANTARG *))a1->lpVtbl->GetDetailsEx)(
                 a1,
                 v11,
                 &v24,
                 &pvarg) < 0 )
            VariantInit(&pvarg);
          v18 = a1->lpVtbl;
          memset(&var2, 0, sizeof(var2));
          if ( ((int (__fastcall *)(struct IShellFolder2 *, LPITEMIDLIST, __int128 *, VARIANTARG *))v18->GetDetailsEx)(
                 a1,
                 pidl,
                 &v24,
                 &var2) < 0 )
            VariantInit(&var2);
          if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v19) && !v17 )
            CoUninitialize();
          v20 = VariantCompare(&pvarg, &var2);
          if ( v20 )
          {
            if ( v20 >= 0 )
              v7 = v20 > 0;
            else
              v7 = 0xFFFF;
          }
          else
          {
            v7 = ILCompareRelIDs(a1, a3, a4, v23);
          }
          VariantClear(&var2);
          VariantClear(&pvarg);
        }
        ILFree(v12);
      }
      ILFree(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000da24  push    rbp
0x18000da26  push    rbx
0x18000da27  push    rsi
0x18000da28  push    rdi
0x18000da29  push    r12
0x18000da2b  push    r13
0x18000da2d  push    r14
0x18000da2f  push    r15
0x18000da31  lea     rbp, [rsp-1Fh]
0x18000da36  sub     rsp, 98h
0x18000da3d  mov     rax, cs:__security_cookie
0x18000da44  xor     rax, rsp
0x18000da47  mov     [rbp+57h+var_48], rax
0x18000da4b  mov     [rbp+57h+var_98], rdx
0x18000da4f  mov     rdi, r9
0x18000da52  xor     edx, edx
0x18000da54  mov     rsi, r8
0x18000da57  mov     r13, rcx
0x18000da5a  mov     ebx, 80070057h
0x18000da5f  test    r8, r8
0x18000da62  jz      loc_18000DC3A
0x18000da68  test    r9, r9
0x18000da6b  jz      loc_18000DC3A
0x18000da71  cmp     [r8], dx
0x18000da75  jz      loc_18000DC3A
0x18000da7b  cmp     [r9], dx
0x18000da7f  jz      loc_18000DC3A
0x18000da85  cmp     r8, r9
0x18000da88  jnz     short loc_18000DA91
0x18000da8a  mov     ebx, edx
0x18000da8c  jmp     loc_18000DC3A
0x18000da91  movzx   ecx, word ptr [r8]
0x18000da95  mov     r14, rdx
0x18000da98  mov     [rbp+57h+pidl], rdx
0x18000da9c  add     rcx, rsi
0x18000da9f  jz      short loc_18000DAC7
0x18000daa1  cmp     [rcx], dx
0x18000daa4  jz      short loc_18000DAC7
0x18000daa6  lea     rdx, [rbp+57h+pidl]; struct _ITEMIDLIST **
0x18000daaa  mov     rcx, rsi; struct _ITEMIDLIST *
0x18000daad  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST@@PEAPEFAU1@@Z; SHILCloneFirst(_ITEMIDLIST const *,_ITEMIDLIST * *)
0x18000dab2  xor     edx, edx
0x18000dab4  mov     ebx, eax
0x18000dab6  test    eax, eax
0x18000dab8  js      loc_18000DC3A
0x18000dabe  mov     r14, [rbp+57h+pidl]
0x18000dac2  mov     r12, r14
0x18000dac5  jmp     short loc_18000DACA
0x18000dac7  mov     r12, rsi
0x18000daca  mov     r15, rdx
0x18000dacd  mov     [rbp+57h+pidl], rdx
0x18000dad1  cmp     [rdi], dx
0x18000dad4  jz      short loc_18000DAFB
0x18000dad6  movzx   ecx, word ptr [rdi]
0x18000dad9  add     rcx, rdi
0x18000dadc  jz      short loc_18000DAFB
0x18000dade  cmp     [rcx], dx
0x18000dae1  jz      short loc_18000DAFB
0x18000dae3  lea     rdx, [rbp+57h+pidl]; struct _ITEMIDLIST **
0x18000dae7  mov     rcx, rdi; struct _ITEMIDLIST *
0x18000daea  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST@@PEAPEFAU1@@Z; SHILCloneFirst(_ITEMIDLIST const *,_ITEMIDLIST * *)
0x18000daef  mov     r15, [rbp+57h+pidl]
0x18000daf3  mov     ebx, eax
0x18000daf5  mov     [rbp+57h+pidl], r15
0x18000daf9  jmp     short loc_18000DB01
0x18000dafb  mov     [rbp+57h+pidl], rdi
0x18000daff  mov     ebx, edx
0x18000db01  test    ebx, ebx
0x18000db03  js      loc_18000DC31
0x18000db09  movzx   edx, word ptr [rbp+57h+var_98]
0x18000db0d  lea     r8, [rbp+57h+var_90]
0x18000db11  xor     eax, eax
0x18000db13  xorps   xmm0, xmm0
0x18000db16  mov     [rbp+57h+var_80], eax
0x18000db19  mov     rcx, r13
0x18000db1c  mov     rax, [r13+0]
0x18000db20  movups  [rbp+57h+var_90], xmm0
0x18000db24  mov     rax, [rax+98h]
0x18000db2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db30  mov     ebx, eax
0x18000db32  test    eax, eax
0x18000db34  js      loc_18000DC28
0x18000db3a  xor     eax, eax
0x18000db3c  xorps   xmm0, xmm0
0x18000db3f  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000db43  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000db47  xor     ebx, ebx
0x18000db49  lea     ecx, [rax+19h]; pszPath
0x18000db4c  call    cs:__imp_IsAppCompatModeEnabled
0x18000db52  test    eax, eax
0x18000db54  jz      short loc_18000DB5D
0x18000db56  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x18000db5b  mov     ebx, eax
0x18000db5d  mov     rcx, [r13+0]
0x18000db61  lea     r9, [rbp+57h+pvarg]
0x18000db65  lea     r8, [rbp+57h+var_90]
0x18000db69  mov     rdx, r12
0x18000db6c  mov     rax, [rcx+88h]
0x18000db73  mov     rcx, r13
0x18000db76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db7b  test    eax, eax
0x18000db7d  jns     short loc_18000DB89
0x18000db7f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000db83  call    cs:__imp_VariantInit
0x18000db89  mov     rdx, [rbp+57h+pidl]
0x18000db8d  lea     r9, [rbp+57h+var2]
0x18000db91  xor     eax, eax
0x18000db93  lea     r8, [rbp+57h+var_90]
0x18000db97  mov     qword ptr [rbp+57h+var2+10h], rax
0x18000db9b  xorps   xmm0, xmm0
0x18000db9e  mov     rax, [r13+0]
0x18000dba2  mov     rcx, r13
0x18000dba5  movups  xmmword ptr [rbp+57h+var2], xmm0
0x18000dba9  mov     rax, [rax+88h]
0x18000dbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbb5  test    eax, eax
0x18000dbb7  jns     short loc_18000DBC3
0x18000dbb9  lea     rcx, [rbp+57h+var2]; pvarg
0x18000dbbd  call    cs:__imp_VariantInit
0x18000dbc3  mov     ecx, 19h; pszPath
0x18000dbc8  call    cs:__imp_IsAppCompatModeEnabled
0x18000dbce  test    eax, eax
0x18000dbd0  jz      short loc_18000DBDC
0x18000dbd2  test    ebx, ebx
0x18000dbd4  jnz     short loc_18000DBDC
0x18000dbd6  call    cs:__imp_CoUninitialize
0x18000dbdc  lea     rdx, [rbp+57h+var2]; var2
0x18000dbe0  lea     rcx, [rbp+57h+pvarg]; var1
0x18000dbe4  call    cs:__imp_VariantCompare
0x18000dbea  test    eax, eax
0x18000dbec  jz      short loc_18000DC00
0x18000dbee  jns     short loc_18000DBF7
0x18000dbf0  mov     ebx, 0FFFFh
0x18000dbf5  jmp     short loc_18000DC14
0x18000dbf7  xor     ebx, ebx
0x18000dbf9  test    eax, eax
0x18000dbfb  setnle  bl
0x18000dbfe  jmp     short loc_18000DC14
0x18000dc00  mov     r9, [rbp+57h+var_98]
0x18000dc04  mov     r8, rdi
0x18000dc07  mov     rdx, rsi
0x18000dc0a  mov     rcx, r13
0x18000dc0d  call    ILCompareRelIDs
0x18000dc12  mov     ebx, eax
0x18000dc14  lea     rcx, [rbp+57h+var2]; pvarg
0x18000dc18  call    cs:__imp_VariantClear
0x18000dc1e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000dc22  call    cs:__imp_VariantClear
0x18000dc28  mov     rcx, r15; pidl
0x18000dc2b  call    cs:__imp_ILFree
0x18000dc31  mov     rcx, r14; pidl
0x18000dc34  call    cs:__imp_ILFree
0x18000dc3a  mov     eax, ebx
0x18000dc3c  mov     rcx, [rbp+57h+var_48]
0x18000dc40  xor     rcx, rsp; StackCookie
0x18000dc43  call    __security_check_cookie
0x18000dc48  add     rsp, 98h
0x18000dc4f  pop     r15
0x18000dc51  pop     r14
0x18000dc53  pop     r13
0x18000dc55  pop     r12
0x18000dc57  pop     rdi
0x18000dc58  pop     rsi
0x18000dc59  pop     rbx
0x18000dc5a  pop     rbp
0x18000dc5b  retn
```
