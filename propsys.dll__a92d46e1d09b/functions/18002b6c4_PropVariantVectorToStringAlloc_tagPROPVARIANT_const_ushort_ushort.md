# _PropVariantVectorToStringAlloc(tagPROPVARIANT const &,ushort,ushort * *)

- ea: `0x18002b6c4`
- end: `0x18002b9e0`
- name: `?_PropVariantVectorToStringAlloc@@YAJAEBUtagPROPVARIANT@@GPEAPEAG@Z`
- size: `796`
- prototype: `__int64 __fastcall(PROPVARIANT *propvarIn, unsigned __int16, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ca30`
- `0x18002b3d4`

## callees

- `0x180007f40`
- `0x18000b560`
- `0x18000ca30`
- `0x1800272f8`
- `0x18002b6c4`
- `0x18002b9e8`
- `0x18006ed20`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b9b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b9b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b844`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b9ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b844`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b9ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b728`

## pseudocode

```c
__int64 __fastcall _PropVariantVectorToStringAlloc(PROPVARIANT *propvarIn, __int16 a2, unsigned __int16 **a3)
{
  HRESULT inited; // ebx
  unsigned int v7; // esi
  void *v8; // rax
  _WORD *v9; // rdi
  size_t v10; // rax
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  const unsigned __int16 **v18; // r15
  __int64 v19; // r14
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  _QWORD *v27; // r15
  __int64 v28; // r14
  const unsigned __int16 *v29; // r8
  ULONG v30; // r14d
  unsigned int v31; // [rsp+20h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-38h] BYREF
  PWSTR ppszOut; // [rsp+30h] [rbp-30h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v35; // [rsp+48h] [rbp-18h]

  *a3 = 0;
  ppszOut = 0;
  v31 = 260;
  if ( !is_mul_ok(0x104u, 2u) )
    return (unsigned int)-2147024362;
  v7 = *((_DWORD *)propvarIn + 2);
  v8 = CoTaskMemAlloc(0x208u);
  pv = v8;
  v9 = v8;
  if ( v8 )
  {
    v10 = CTCoAllocPolicy::_CoTaskMemSize(v8);
    memset_0(v9, 0, v10);
    inited = 0;
  }
  else
  {
    inited = -2147024882;
  }
  if ( inited >= 0 )
  {
    *v9 = 0;
    v11 = *(_WORD *)propvarIn & 0xEFFF;
    if ( v11 > 0x40 )
      goto LABEL_37;
    inited = 0;
    if ( v11 != 64 )
    {
      if ( v11 <= 0x10 )
      {
        if ( v11 != 16 )
        {
          v21 = v11 - 2;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              v23 = v22 - 1;
              if ( v23 )
              {
                v24 = v23 - 1;
                if ( v24 )
                {
                  v25 = v24 - 2;
                  if ( v25 )
                  {
                    v26 = v25 - 1;
                    if ( !v26 )
                    {
                      v27 = propvarIn[2];
                      v28 = 0;
                      if ( !v7 )
                        goto LABEL_17;
                      while ( inited >= 0 )
                      {
                        v29 = &Src;
                        if ( v27[v28] )
                          v29 = (const unsigned __int16 *)v27[v28];
                        inited = _StringCchCatRealloc((unsigned __int16 **)&pv, &v31, v29);
                        if ( (_DWORD)v28 != v7 - 1 )
                          inited = _StringCchCatRealloc((unsigned __int16 **)&pv, &v31, L"; ");
                        v28 = (unsigned int)(v28 + 1);
                        if ( (unsigned int)v28 >= v7 )
                        {
LABEL_24:
                          if ( inited < 0 )
                            goto LABEL_26;
                          v9 = pv;
                          goto LABEL_17;
                        }
                      }
                      goto LABEL_26;
                    }
                    if ( v26 - 3 >= 2 )
                    {
LABEL_37:
                      inited = -2147316576;
                      goto LABEL_27;
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        v12 = v11 - 17;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              v15 = v14 - 1;
              if ( v15 )
              {
                v16 = v15 - 1;
                if ( v16 )
                {
                  v17 = v16 - 9;
                  if ( v17 )
                  {
                    if ( v17 == 1 )
                    {
                      v18 = (const unsigned __int16 **)propvarIn[2];
                      v19 = 0;
                      if ( !v7 )
                      {
LABEL_17:
                        if ( a2 == 31 )
                        {
                          *a3 = v9;
                          return (unsigned int)inited;
                        }
                        inited = SHSysAllocString(v9, a3);
LABEL_27:
                        CoTaskMemFree(v9);
                        return (unsigned int)inited;
                      }
                      while ( inited >= 0 )
                      {
                        inited = _StringCchCatRealloc((unsigned __int16 **)&pv, &v31, v18[v19]);
                        if ( (_DWORD)v19 != v7 - 1 )
                          inited = _StringCchCatRealloc((unsigned __int16 **)&pv, &v31, L"; ");
                        v19 = (unsigned int)(v19 + 1);
                        if ( (unsigned int)v19 >= v7 )
                          goto LABEL_24;
                      }
LABEL_26:
                      v9 = pv;
                      goto LABEL_27;
                    }
                    goto LABEL_37;
                  }
                }
              }
            }
          }
        }
      }
    }
    v30 = 0;
    if ( !v7 )
      goto LABEL_17;
    while ( inited >= 0 )
    {
      v35 = 0;
      *(_OWORD *)ppropvar = 0;
      inited = InitPropVariantFromPropVariantVectorElem(propvarIn, v30, ppropvar);
      if ( inited >= 0 )
      {
        ppszOut = 0;
        inited = PropVariantToStringAlloc(ppropvar, &ppszOut);
        if ( inited >= 0 )
        {
          inited = _StringCchCatRealloc((unsigned __int16 **)&pv, &v31, ppszOut);
          if ( inited >= 0 && v30 != v7 - 1 )
            inited = _StringCchCatRealloc((unsigned __int16 **)&pv, &v31, L"; ");
          CoTaskMemFree(ppszOut);
        }
        PropVariantClear(ppropvar);
      }
      if ( ++v30 >= v7 )
        goto LABEL_24;
    }
    goto LABEL_26;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002b6c4  mov     [rsp-38h+arg_8], rbx
0x18002b6c9  push    rbp
0x18002b6ca  push    rsi
0x18002b6cb  push    rdi
0x18002b6cc  push    r12
0x18002b6ce  push    r13
0x18002b6d0  push    r14
0x18002b6d2  push    r15
0x18002b6d4  mov     rbp, rsp
0x18002b6d7  sub     rsp, 60h
0x18002b6db  mov     rax, cs:__security_cookie
0x18002b6e2  xor     rax, rsp
0x18002b6e5  mov     [rbp+var_10], rax
0x18002b6e9  mov     r15, rcx
0x18002b6ec  mov     qword ptr [r8], 0
0x18002b6f3  mov     ecx, 104h
0x18002b6f8  mov     [rbp+ppszOut], 0
0x18002b700  mov     eax, 2
0x18002b705  mov     [rbp+var_40], ecx
0x18002b708  movzx   r13d, dx
0x18002b70c  mov     r12, r8
0x18002b70f  mul     rcx
0x18002b712  test    rdx, rdx
0x18002b715  jz      short loc_18002B721
0x18002b717  mov     ebx, 80070216h
0x18002b71c  jmp     loc_18002B7E6
0x18002b721  mov     esi, [r15+8]
0x18002b725  mov     rcx, rax; cb
0x18002b728  call    cs:__imp_CoTaskMemAlloc
0x18002b72e  mov     [rbp+pv], rax
0x18002b732  mov     rdi, rax
0x18002b735  test    rax, rax
0x18002b738  jz      loc_18002B84C
0x18002b73e  mov     rcx, rax; void *
0x18002b741  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18002b746  mov     r8, rax; Size
0x18002b749  xor     edx, edx; Val
0x18002b74b  mov     rcx, rdi; void *
0x18002b74e  call    memset_0
0x18002b753  xor     ebx, ebx
0x18002b755  test    ebx, ebx
0x18002b757  js      loc_18002B7E6
0x18002b75d  xor     eax, eax
0x18002b75f  mov     [rdi], ax
0x18002b762  movzx   ecx, word ptr [r15]
0x18002b766  and     ecx, 0EFFFh
0x18002b76c  cmp     ecx, 40h ; '@'
0x18002b76f  ja      loc_18002B8A0
0x18002b775  xor     ebx, ebx
0x18002b777  cmp     ecx, 40h ; '@'
0x18002b77a  jz      loc_18002B924
0x18002b780  cmp     ecx, 10h
0x18002b783  jbe     loc_18002B856
0x18002b789  sub     ecx, 11h
0x18002b78c  jz      loc_18002B924
0x18002b792  sub     ecx, 1
0x18002b795  jz      loc_18002B924
0x18002b79b  sub     ecx, 1
0x18002b79e  jz      loc_18002B924
0x18002b7a4  sub     ecx, 1
0x18002b7a7  jz      loc_18002B924
0x18002b7ad  sub     ecx, 1
0x18002b7b0  jz      loc_18002B924
0x18002b7b6  sub     ecx, 9
0x18002b7b9  jz      loc_18002B924
0x18002b7bf  cmp     ecx, 1
0x18002b7c2  jnz     loc_18002B8A0
0x18002b7c8  mov     r15, [r15+10h]
0x18002b7cc  xor     r14d, r14d
0x18002b7cf  test    esi, esi
0x18002b7d1  jnz     short loc_18002B80C
0x18002b7d3  mov     eax, 1Fh
0x18002b7d8  cmp     ax, r13w
0x18002b7dc  jnz     loc_18002B9CE
0x18002b7e2  mov     [r12], rdi
0x18002b7e6  mov     eax, ebx
0x18002b7e8  mov     rcx, [rbp+var_10]
0x18002b7ec  xor     rcx, rsp; StackCookie
0x18002b7ef  call    __security_check_cookie
0x18002b7f4  mov     rbx, [rsp+60h+arg_8]
0x18002b7fc  add     rsp, 60h
0x18002b800  pop     r15
0x18002b802  pop     r14
0x18002b804  pop     r13
0x18002b806  pop     r12
0x18002b808  pop     rdi
0x18002b809  pop     rsi
0x18002b80a  pop     rbp
0x18002b80b  retn
0x18002b80c  test    ebx, ebx
0x18002b80e  js      short loc_18002B83D
0x18002b810  mov     r8, [r15+r14*8]; unsigned __int16 *
0x18002b814  lea     rdx, [rbp+var_40]; unsigned int *
0x18002b818  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18002b81c  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x18002b821  mov     ebx, eax
0x18002b823  lea     eax, [rsi-1]
0x18002b826  cmp     r14d, eax
0x18002b829  jnz     short loc_18002B8A7
0x18002b82b  inc     r14d
0x18002b82e  cmp     r14d, esi
0x18002b831  jb      short loc_18002B80C
0x18002b833  test    ebx, ebx
0x18002b835  js      short loc_18002B83D
0x18002b837  mov     rdi, [rbp+pv]
0x18002b83b  jmp     short loc_18002B7D3
0x18002b83d  mov     rdi, [rbp+pv]
0x18002b841  mov     rcx, rdi; pv
0x18002b844  call    cs:__imp_CoTaskMemFree
0x18002b84a  jmp     short loc_18002B7E6
0x18002b84c  mov     ebx, 8007000Eh
0x18002b851  jmp     loc_18002B755
0x18002b856  jz      loc_18002B924
0x18002b85c  sub     ecx, 2
0x18002b85f  jz      loc_18002B924
0x18002b865  sub     ecx, 1
0x18002b868  jz      loc_18002B924
0x18002b86e  sub     ecx, 1
0x18002b871  jz      loc_18002B924
0x18002b877  sub     ecx, 1
0x18002b87a  jz      loc_18002B924
0x18002b880  sub     ecx, 2
0x18002b883  jz      loc_18002B924
0x18002b889  sub     ecx, 1
0x18002b88c  jz      short loc_18002B8C2
0x18002b88e  sub     ecx, 3
0x18002b891  jz      loc_18002B924
0x18002b897  cmp     ecx, 1
0x18002b89a  jz      loc_18002B924
0x18002b8a0  mov     ebx, 80028CA0h
0x18002b8a5  jmp     short loc_18002B841
0x18002b8a7  lea     r8, asc_1800CD530; "; "
0x18002b8ae  lea     rdx, [rbp+var_40]; unsigned int *
0x18002b8b2  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18002b8b6  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x18002b8bb  mov     ebx, eax
0x18002b8bd  jmp     loc_18002B82B
0x18002b8c2  mov     r15, [r15+10h]
0x18002b8c6  xor     r14d, r14d
0x18002b8c9  test    esi, esi
0x18002b8cb  jz      loc_18002B7D3
0x18002b8d1  test    ebx, ebx
0x18002b8d3  js      loc_18002B83D
0x18002b8d9  cmp     qword ptr [r15+r14*8], 0
0x18002b8de  lea     r8, Src
0x18002b8e5  lea     rdx, [rbp+var_40]; unsigned int *
0x18002b8e9  cmovnz  r8, [r15+r14*8]; unsigned __int16 *
0x18002b8ee  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18002b8f2  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x18002b8f7  mov     ebx, eax
0x18002b8f9  lea     eax, [rsi-1]
0x18002b8fc  cmp     r14d, eax
0x18002b8ff  jz      short loc_18002B917
0x18002b901  lea     r8, asc_1800CD530; "; "
0x18002b908  lea     rdx, [rbp+var_40]; unsigned int *
0x18002b90c  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18002b910  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x18002b915  mov     ebx, eax
0x18002b917  inc     r14d
0x18002b91a  cmp     r14d, esi
0x18002b91d  jb      short loc_18002B8D1
0x18002b91f  jmp     loc_18002B833
0x18002b924  xor     r14d, r14d
0x18002b927  test    esi, esi
0x18002b929  jz      loc_18002B7D3
0x18002b92f  test    ebx, ebx
0x18002b931  js      loc_18002B83D
0x18002b937  xorps   xmm0, xmm0
0x18002b93a  lea     r8, [rbp+ppropvar]; ppropvar
0x18002b93e  xor     eax, eax
0x18002b940  mov     edx, r14d; iElem
0x18002b943  mov     rcx, r15; propvarIn
0x18002b946  mov     [rbp+var_18], rax
0x18002b94a  movups  xmmword ptr [rbp+ppropvar], xmm0
0x18002b94e  call    InitPropVariantFromPropVariantVectorElem
0x18002b953  mov     ebx, eax
0x18002b955  test    eax, eax
0x18002b957  js      short loc_18002B9BD
0x18002b959  lea     rdx, [rbp+ppszOut]; ppszOut
0x18002b95d  mov     [rbp+ppszOut], 0
0x18002b965  lea     rcx, [rbp+ppropvar]; propvar
0x18002b969  call    PropVariantToStringAlloc
0x18002b96e  mov     ebx, eax
0x18002b970  test    eax, eax
0x18002b972  js      short loc_18002B9B3
0x18002b974  mov     r8, [rbp+ppszOut]; unsigned __int16 *
0x18002b978  lea     rdx, [rbp+var_40]; unsigned int *
0x18002b97c  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18002b980  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x18002b985  mov     ebx, eax
0x18002b987  test    eax, eax
0x18002b989  js      short loc_18002B9A9
0x18002b98b  lea     eax, [rsi-1]
0x18002b98e  cmp     r14d, eax
0x18002b991  jz      short loc_18002B9A9
0x18002b993  lea     r8, asc_1800CD530; "; "
0x18002b99a  lea     rdx, [rbp+var_40]; unsigned int *
0x18002b99e  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18002b9a2  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x18002b9a7  mov     ebx, eax
0x18002b9a9  mov     rcx, [rbp+ppszOut]; pv
0x18002b9ad  call    cs:__imp_CoTaskMemFree
0x18002b9b3  lea     rcx, [rbp+ppropvar]; pvar
0x18002b9b7  call    cs:__imp_PropVariantClear
0x18002b9bd  inc     r14d
0x18002b9c0  cmp     r14d, esi
0x18002b9c3  jb      loc_18002B92F
0x18002b9c9  jmp     loc_18002B833
0x18002b9ce  mov     rdx, r12; unsigned __int16 **
0x18002b9d1  mov     rcx, rdi; unsigned __int16 *
0x18002b9d4  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x18002b9d9  mov     ebx, eax
0x18002b9db  jmp     loc_18002B841
```
