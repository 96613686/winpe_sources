# LsaDbpDsOpenSamUser(_UNICODE_STRING *,_SECPKG_NAME_TYPE,void * *)

- ea: `0x180019c64`
- end: `0x180019dac`
- name: `?LsaDbpDsOpenSamUser@@YAJPEAU_UNICODE_STRING@@W4_SECPKG_NAME_TYPE@@PEAPEAX@Z`
- size: `328`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, enum _SECPKG_NAME_TYPE, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001819c`
- `0x18001863c`

## callees

- `0x18000fd40`
- `0x180012fa4`
- `0x180019c64`

## import_xrefs

- `LSASRV!LsapGetAccountDomainHandle` at `0x180019c96`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180019d0b`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180019c96`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180019d0b`
- `SAMSRV!SamrOpenUser` at `0x180019d1f`
- `SAMSRV!SamrOpenUser` at `0x180019d1f`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180019d2b`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180019d35`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180019d82`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180019d9b`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180019d2b`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180019d35`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180019d82`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180019d9b`
- `SAMSRV!SamrLookupNamesInDomain` at `0x180019cb4`
- `SAMSRV!SamrLookupNamesInDomain` at `0x180019cb4`

## pseudocode

```c
__int64 __fastcall LsaDbpDsOpenSamUser(struct _UNICODE_STRING *a1, enum _SECPKG_NAME_TYPE a2, void **a3)
{
  __int64 AccountDomainHandle; // rax
  int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  unsigned int *v13; // [rsp+38h] [rbp-20h]
  __int64 v14; // [rsp+40h] [rbp-18h] BYREF
  _DWORD *v15; // [rsp+48h] [rbp-10h]

  v12 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  AccountDomainHandle = LsapGetAccountDomainHandle(a1);
  v6 = SamrLookupNamesInDomain(AccountDomainHandle, 1, a1, &v12, &v14);
  v8 = v6;
  if ( v6 >= 0 )
  {
    if ( *v15 == 1 )
    {
      v9 = *v13;
      v10 = LsapGetAccountDomainHandle(v7);
      v8 = SamrOpenUser(v10, 985087, v9, a3);
      SamIFree_SAMPR_ULONG_ARRAY(&v12);
      SamIFree_SAMPR_ULONG_ARRAY(&v14);
      v13 = 0;
      v15 = 0;
      if ( (v8 & 0x80000000) == 0 || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        return v8;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids, v8);
    }
    else
    {
      v8 = -1073741724;
    }
  }
  else if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_ZD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      (unsigned int)&WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
      (_DWORD)a1,
      v6);
  }
  if ( v13 )
  {
    SamIFree_SAMPR_ULONG_ARRAY(&v12);
    v13 = 0;
  }
  if ( v15 )
    SamIFree_SAMPR_ULONG_ARRAY(&v14);
  return v8;
}

```

## disassembly

```asm
0x180019c64  push    rbp
0x180019c66  push    rbx
0x180019c67  push    rsi
0x180019c68  push    rdi
0x180019c69  mov     rbp, rsp
0x180019c6c  sub     rsp, 58h
0x180019c70  mov     rsi, r8
0x180019c73  mov     [rbp+var_28], 0
0x180019c7b  mov     rdi, rcx
0x180019c7e  mov     [rbp+var_18], 0
0x180019c86  mov     [rbp+var_20], 0
0x180019c8e  mov     [rbp+var_10], 0
0x180019c96  call    cs:__imp_LsapGetAccountDomainHandle
0x180019c9c  lea     r9, [rbp+var_28]
0x180019ca0  mov     r8, rdi
0x180019ca3  mov     rcx, rax
0x180019ca6  mov     edx, 1
0x180019cab  lea     rax, [rbp+var_18]
0x180019caf  mov     [rsp+58h+var_38], rax
0x180019cb4  call    cs:__imp_SamrLookupNamesInDomain
0x180019cba  mov     ebx, eax
0x180019cbc  test    eax, eax
0x180019cbe  jns     short loc_180019CF5
0x180019cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180019cc7  test    dword ptr [rcx+1Ch], 100h
0x180019cce  jz      loc_180019D77
0x180019cd4  mov     rcx, [rcx+10h]
0x180019cd8  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180019cdf  mov     edx, 49h ; 'I'
0x180019ce4  mov     dword ptr [rsp+58h+var_38], eax
0x180019ce8  mov     r9, rdi
0x180019ceb  call    WPP_SF_ZD
0x180019cf0  jmp     loc_180019D77
0x180019cf5  mov     rax, [rbp+var_10]
0x180019cf9  cmp     dword ptr [rax], 1
0x180019cfc  jz      short loc_180019D05
0x180019cfe  mov     ebx, 0C0000064h
0x180019d03  jmp     short loc_180019D77
0x180019d05  mov     rax, [rbp+var_20]
0x180019d09  mov     ebx, [rax]
0x180019d0b  call    cs:__imp_LsapGetAccountDomainHandle
0x180019d11  mov     r9, rsi
0x180019d14  mov     r8d, ebx
0x180019d17  mov     rcx, rax
0x180019d1a  mov     edx, 0F07FFh
0x180019d1f  call    cs:__imp_SamrOpenUser
0x180019d25  lea     rcx, [rbp+var_28]
0x180019d29  mov     ebx, eax
0x180019d2b  call    cs:__imp_SamIFree_SAMPR_ULONG_ARRAY
0x180019d31  lea     rcx, [rbp+var_18]
0x180019d35  call    cs:__imp_SamIFree_SAMPR_ULONG_ARRAY
0x180019d3b  mov     [rbp+var_20], 0
0x180019d43  mov     [rbp+var_10], 0
0x180019d4b  test    ebx, ebx
0x180019d4d  jns     short loc_180019DA1
0x180019d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d56  test    dword ptr [rcx+1Ch], 100h
0x180019d5d  jz      short loc_180019DA1
0x180019d5f  mov     rcx, [rcx+10h]
0x180019d63  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180019d6a  mov     edx, 4Ah ; 'J'
0x180019d6f  mov     r9d, ebx
0x180019d72  call    WPP_SF_d
0x180019d77  cmp     [rbp+var_20], 0
0x180019d7c  jz      short loc_180019D90
0x180019d7e  lea     rcx, [rbp+var_28]
0x180019d82  call    cs:__imp_SamIFree_SAMPR_ULONG_ARRAY
0x180019d88  mov     [rbp+var_20], 0
0x180019d90  cmp     [rbp+var_10], 0
0x180019d95  jz      short loc_180019DA1
0x180019d97  lea     rcx, [rbp+var_18]
0x180019d9b  call    cs:__imp_SamIFree_SAMPR_ULONG_ARRAY
0x180019da1  mov     eax, ebx
0x180019da3  add     rsp, 58h
0x180019da7  pop     rdi
0x180019da8  pop     rsi
0x180019da9  pop     rbx
0x180019daa  pop     rbp
0x180019dab  retn
```
