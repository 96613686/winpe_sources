# CPropertyStoreOverFolder::_GetLinkTargetSFGAOFlags(CPropertyStoreOverFolder *,_ITEMID_CHILD const *,tagPROPVARIANT *,int,ushort * *)

- ea: `0x180047cd0`
- end: `0x180047f25`
- name: `?_GetLinkTargetSFGAOFlags@CPropertyStoreOverFolder@@CAJPEAV1@PEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@HPEAPEAG@Z`
- size: `597`
- prototype: `__int64 __fastcall(struct CPropertyStoreOverFolder *, const struct _ITEMID_CHILD *, struct tagPROPVARIANT *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180047cd0`
- `0x1800480e8`
- `0x180048484`
- `0x18006ed20`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047e4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047e93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047e4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047e93`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x180047eed`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x180047eed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropertyStoreOverFolder::_GetLinkTargetSFGAOFlags(
        struct IShellFolder **a1,
        const struct _ITEMID_CHILD *a2,
        struct tagPROPVARIANT *a3,
        __int64 a4,
        unsigned __int16 **a5)
{
  int v7; // ebx
  unsigned __int16 *v8; // rdi
  __int64 v9; // rcx
  const wchar_t *v10; // r8
  __int64 v11; // rdx
  wchar_t *v12; // rax
  __int64 v13; // r10
  wchar_t v14; // r9
  __int64 v15; // r9
  wchar_t *v16; // rcx
  struct IBindCtx *v17; // r8
  unsigned int v18; // r9d
  struct IShellFolder *v19; // rsi
  int AttributesFromFolderAndRelativeIDList; // eax
  unsigned int v21; // ebx
  __int64 v23; // rsi
  unsigned __int16 *v24; // rax
  unsigned int v25; // [rsp+40h] [rbp-40h] BYREF
  LPVOID v26; // [rsp+48h] [rbp-38h] BYREF
  __int64 v27; // [rsp+50h] [rbp-30h]
  __int64 v28; // [rsp+58h] [rbp-28h]
  LPVOID pv; // [rsp+60h] [rbp-20h] BYREF
  __int64 v30; // [rsp+68h] [rbp-18h] BYREF
  const struct _ITEMID_CHILD *v31; // [rsp+70h] [rbp-10h] BYREF

  v31 = a2;
  v27 = -1;
  v28 = -1;
  v26 = 0;
  v7 = _AllocArray<unsigned short,CTCoAllocPolicy>(a1, 0, 20, &v26);
  v8 = (unsigned __int16 *)v26;
  if ( v7 >= 0 )
  {
    if ( v26 )
    {
      v9 = 19;
      v10 = L"PropStoreOverFolder";
      v11 = 20;
      v12 = (wchar_t *)v26;
      v13 = 0;
      do
      {
        if ( !v9 )
          break;
        v14 = *v10;
        if ( !*v10 )
          break;
        ++v10;
        *v12++ = v14;
        --v9;
        ++v13;
        --v11;
      }
      while ( v11 );
      v15 = v13 - 1;
      if ( v11 )
        v15 = v13;
      v16 = v12 - 1;
      if ( v11 )
        v16 = v12;
      *v16 = 0;
      if ( v11 )
      {
        v23 = 20 - v15;
        if ( v15 != 20 && v15 != 19 && (unsigned __int64)(2 * v23) > 2 )
          memset_0(&v8[v15 + 1], 0, 2 * v23 - 2);
      }
    }
    else
    {
      MEMORY[0] = 0;
    }
    v30 = 0;
    v7 = ((__int64 (__fastcall *)(struct IShellFolder *, _QWORD, __int64, const struct _ITEMID_CHILD **, GUID *, _QWORD, __int64 *))a1[7]->lpVtbl->GetUIObjectOf)(
           a1[7],
           0,
           1,
           &v31,
           &GUID_000214f9_0000_0000_c000_000000000046,
           0,
           &v30);
    if ( v7 >= 0 )
    {
      pv = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v30 + 32LL))(v30, &pv);
      if ( v7 >= 0 )
      {
        if ( pv )
        {
          v19 = a1[6];
          v25 = 0;
          AttributesFromFolderAndRelativeIDList = _GetAttributesFromFolderAndRelativeIDList(
                                                    v19,
                                                    (const struct _ITEMIDLIST_RELATIVE *)pv,
                                                    v17,
                                                    v18,
                                                    &v25);
          v21 = v25;
          if ( AttributesFromFolderAndRelativeIDList >= 0
            && (v25 & 0x20C00000) == 0x20400000
            && (SHGetObjectCompatFlags(v19, 0) & 0x200) != 0 )
          {
            v21 = v21 & 0xFF3FFFFF | 0x800000;
          }
          a3->vt = 19;
          a3->lVal = v21 & 0x7EFBBFFF;
          v7 = 0;
          if ( a5 )
          {
            v24 = v8;
            v8 = 0;
            v26 = 0;
            v28 = 0;
            v27 = 0;
            *a5 = v24;
          }
          CoTaskMemFree(pv);
        }
        else
        {
          v7 = -2147467259;
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
  }
  if ( v8 )
    CoTaskMemFree(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180047cd0  mov     [rsp-38h+arg_18], rbx
0x180047cd5  push    rbp
0x180047cd6  push    rsi
0x180047cd7  push    rdi
0x180047cd8  push    r12
0x180047cda  push    r13
0x180047cdc  push    r14
0x180047cde  push    r15
0x180047ce0  mov     rbp, rsp
0x180047ce3  sub     rsp, 80h
0x180047cea  mov     rax, cs:__security_cookie
0x180047cf1  xor     rax, rsp
0x180047cf4  mov     [rbp+var_8], rax
0x180047cf8  mov     r15, r8
0x180047cfb  mov     r13, rcx
0x180047cfe  mov     [rbp+var_10], rdx
0x180047d02  mov     r14, [rbp+arg_20]
0x180047d06  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047d0a  mov     [rbp+var_30], rax
0x180047d0e  mov     [rbp+var_28], rax
0x180047d12  xor     r12d, r12d
0x180047d15  mov     [rbp+var_38], r12
0x180047d19  lea     r9, [rbp+var_38]
0x180047d1d  lea     esi, [rax+15h]
0x180047d20  mov     r8d, esi
0x180047d23  xor     edx, edx
0x180047d25  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180047d2a  mov     ebx, eax
0x180047d2c  mov     rdi, [rbp+var_38]
0x180047d30  test    eax, eax
0x180047d32  js      loc_180047E62
0x180047d38  test    rdi, rdi
0x180047d3b  jz      loc_180047ECD
0x180047d41  lea     ecx, [rsi-1]
0x180047d44  lea     r8, aPropstoreoverf_0; "PropStoreOverFolder"
0x180047d4b  mov     edx, esi
0x180047d4d  mov     rax, rdi
0x180047d50  mov     r10d, r12d
0x180047d53  test    rcx, rcx
0x180047d56  jz      short loc_180047D7A
0x180047d58  movzx   r9d, word ptr [r8]
0x180047d5c  test    r9w, r9w
0x180047d60  jz      short loc_180047D7A
0x180047d62  add     r8, 2
0x180047d66  mov     [rax], r9w
0x180047d6a  add     rax, 2
0x180047d6e  dec     rcx
0x180047d71  inc     r10
0x180047d74  sub     rdx, 1
0x180047d78  jnz     short loc_180047D53
0x180047d7a  lea     r9, [r10-1]
0x180047d7e  test    rdx, rdx
0x180047d81  cmovnz  r9, r10
0x180047d85  lea     rcx, [rax-2]
0x180047d89  cmovnz  rcx, rax
0x180047d8d  mov     [rcx], r12w
0x180047d91  jnz     loc_180047E9B
0x180047d97  mov     [rbp+var_18], r12
0x180047d9b  mov     rcx, [r13+38h]
0x180047d9f  mov     rax, [rcx]
0x180047da2  lea     rdx, [rbp+var_18]
0x180047da6  mov     [rsp+80h+var_50], rdx
0x180047dab  mov     [rsp+80h+var_58], r12
0x180047db0  lea     rdx, _GUID_000214f9_0000_0000_c000_000000000046
0x180047db7  mov     [rsp+80h+var_60], rdx
0x180047dbc  lea     r9, [rbp+var_10]
0x180047dc0  xor     edx, edx
0x180047dc2  lea     r8d, [rdx+1]
0x180047dc6  mov     rax, [rax+50h]
0x180047dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dcf  mov     ebx, eax
0x180047dd1  test    eax, eax
0x180047dd3  js      loc_180047E62
0x180047dd9  mov     [rbp+pv], r12
0x180047ddd  mov     rcx, [rbp+var_18]
0x180047de1  mov     rax, [rcx]
0x180047de4  lea     rdx, [rbp+pv]
0x180047de8  mov     rax, [rax+20h]
0x180047dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047df1  mov     ebx, eax
0x180047df3  test    eax, eax
0x180047df5  js      short loc_180047E51
0x180047df7  mov     rdx, [rbp+pv]; Src
0x180047dfb  test    rdx, rdx
0x180047dfe  jnz     short loc_180047E07
0x180047e00  mov     ebx, 80004005h
0x180047e05  jmp     short loc_180047E51
0x180047e07  mov     rsi, [r13+30h]
0x180047e0b  mov     [rbp+var_40], r12d
0x180047e0f  lea     rax, [rbp+var_40]
0x180047e13  mov     [rsp+80h+var_60], rax; unsigned int *
0x180047e18  mov     rcx, rsi; struct IShellFolder *
0x180047e1b  call    ?_GetAttributesFromFolderAndRelativeIDList@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@KPEAK@Z; _GetAttributesFromFolderAndRelativeIDList(IShellFolder *,_ITEMIDLIST_RELATIVE const *,IBindCtx *,ulong,ulong *)
0x180047e20  mov     ebx, [rbp+var_40]
0x180047e23  test    eax, eax
0x180047e25  jns     loc_180047ED6
0x180047e2b  mov     word ptr [r15], 13h
0x180047e31  and     ebx, 7EFBBFFFh
0x180047e37  mov     [r15+8], ebx
0x180047e3b  mov     ebx, r12d
0x180047e3e  test    r14, r14
0x180047e41  jnz     loc_180047F0A
0x180047e47  mov     rcx, [rbp+pv]; pv
0x180047e4b  call    cs:__imp_CoTaskMemFree
0x180047e51  mov     rcx, [rbp+var_18]
0x180047e55  mov     rax, [rcx]
0x180047e58  mov     rax, [rax+10h]
0x180047e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e61  nop
0x180047e62  test    rdi, rdi
0x180047e65  jnz     short loc_180047E90
0x180047e67  mov     eax, ebx
0x180047e69  mov     rcx, [rbp+var_8]
0x180047e6d  xor     rcx, rsp; StackCookie
0x180047e70  call    __security_check_cookie
0x180047e75  mov     rbx, [rsp+80h+arg_18]
0x180047e7d  add     rsp, 80h
0x180047e84  pop     r15
0x180047e86  pop     r14
0x180047e88  pop     r13
0x180047e8a  pop     r12
0x180047e8c  pop     rdi
0x180047e8d  pop     rsi
0x180047e8e  pop     rbp
0x180047e8f  retn
0x180047e90  mov     rcx, rdi; pv
0x180047e93  call    cs:__imp_CoTaskMemFree
0x180047e99  jmp     short loc_180047E67
0x180047e9b  sub     rsi, r9
0x180047e9e  cmp     rsi, 1
0x180047ea2  jbe     loc_180047D97
0x180047ea8  lea     r8, [rsi+rsi]
0x180047eac  cmp     r8, 2
0x180047eb0  jbe     loc_180047D97
0x180047eb6  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180047eba  inc     r9
0x180047ebd  lea     rcx, [rdi+r9*2]; void *
0x180047ec1  xor     edx, edx; Val
0x180047ec3  call    memset_0
0x180047ec8  jmp     loc_180047D97
0x180047ecd  mov     [rdi], r12w
0x180047ed1  jmp     loc_180047D97
0x180047ed6  mov     eax, ebx
0x180047ed8  and     eax, 20C00000h
0x180047edd  cmp     eax, 20400000h
0x180047ee2  jnz     loc_180047E2B
0x180047ee8  xor     edx, edx
0x180047eea  mov     rcx, rsi
0x180047eed  call    cs:__imp_SHGetObjectCompatFlags
0x180047ef3  bt      eax, 9
0x180047ef7  jnb     loc_180047E2B
0x180047efd  btr     ebx, 16h
0x180047f01  bts     ebx, 17h
0x180047f05  jmp     loc_180047E2B
0x180047f0a  mov     rax, rdi
0x180047f0d  mov     rdi, r12
0x180047f10  mov     [rbp+var_38], r12
0x180047f14  mov     [rbp+var_28], r12
0x180047f18  mov     [rbp+var_30], r12
0x180047f1c  mov     [r14], rax
0x180047f1f  jmp     loc_180047E47
```
