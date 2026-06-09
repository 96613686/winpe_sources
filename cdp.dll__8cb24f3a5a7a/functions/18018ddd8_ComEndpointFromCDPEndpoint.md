# ComEndpointFromCDPEndpoint

- ea: `0x18018ddd8`
- end: `0x18018e132`
- name: `ComEndpointFromCDPEndpoint`
- size: `858`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18018dbe4`
- `0x1801b5fe8`
- `0x1801b6e0c`

## callees

- `0x1800c3a94`
- `0x1800f6590`
- `0x1800fd420`
- `0x18018ddd8`
- `0x1801fc5e8`
- `0x1802c36e4`
- `0x1802c37fc`
- `0x180354010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18018de87`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18018defb`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18018de87`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18018defb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e0cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e0cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018de50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018dec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018dfc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018de50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018dec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018dfc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComEndpointFromCDPEndpoint(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  int v4; // ebx
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rcx
  rsize_t v9; // r15
  LPVOID v10; // rax
  char *v11; // r13
  const char *v12; // rax
  char *v13; // r15
  __int64 v14; // rax
  LPVOID v15; // rax
  const char *v16; // rax
  unsigned __int16 v17; // ax
  char *v18; // rdi
  const struct std::nothrow_t *v19; // rdx
  int v20; // r12d
  __int64 unique; // rax
  void *v22; // rcx
  int v23; // r13d
  int v24; // esi
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  char *v30; // rax
  char *v31; // rsi
  char *v32; // r14
  char *v33; // [rsp+30h] [rbp-30h] BYREF
  char *Destination; // [rsp+38h] [rbp-28h] BYREF
  char *v35; // [rsp+40h] [rbp-20h]
  char *v36; // [rsp+48h] [rbp-18h] BYREF
  char *v37; // [rsp+50h] [rbp-10h]
  char *v38; // [rsp+58h] [rbp-8h]
  __int16 v40; // [rsp+A8h] [rbp+48h]
  unsigned __int16 v41; // [rsp+B0h] [rbp+50h] BYREF
  void *v42; // [rsp+B8h] [rbp+58h] BYREF

  v2 = a2;
  v4 = 0;
  if ( !a2 )
    return 2147500035LL;
  if ( !a1 )
    return 2147942487LL;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  Destination = 0;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_BYTE *)(v6 + v8) );
  v9 = v8 + 1;
  v10 = CoTaskMemAlloc(v8 + 1);
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &Destination,
    v10);
  v11 = Destination;
  v37 = Destination;
  if ( Destination )
  {
    v12 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    strcpy_s(v11, v9, v12);
  }
  else
  {
    v4 = -2147024882;
  }
  v13 = 0;
  v35 = 0;
  v33 = 0;
  if ( v4 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    do
      ++v7;
    while ( *(_BYTE *)(v14 + v7) );
    v15 = CoTaskMemAlloc(v7 + 1);
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v33,
      v15);
    if ( v11 )
    {
      v16 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      v35 = v33;
      strcpy_s(v33, v7 + 1, v16);
      v41 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(
             a1,
             0,
             0,
             &v41);
      v17 = v41;
      goto LABEL_17;
    }
    v4 = -2147024882;
    v35 = v33;
  }
  v17 = 0;
  v41 = 0;
LABEL_17:
  v18 = 0;
  v36 = 0;
  v38 = 0;
  v19 = 0;
  if ( v4 >= 0 )
  {
    v20 = 0;
    if ( !v17 )
      goto LABEL_29;
    unique = wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(&v42, v17);
    wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(
      &v36,
      unique);
    v22 = v42;
    v19 = 0;
    v42 = 0;
    if ( v22 )
      operator delete(v22, 0);
    v18 = v36;
    if ( !v36 )
    {
      v4 = -2147024882;
      goto LABEL_35;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(
           a1,
           v36,
           v41,
           &v41);
    v23 = v4;
    if ( v4 >= 0 )
    {
      v13 = (char *)CoTaskMemAlloc(16LL * v41);
      v38 = v13;
      v19 = 0;
      if ( v13 )
      {
        v20 = v4;
        if ( v41 )
        {
          v24 = 0;
          do
          {
            v25 = (*(__int64 (__fastcall **)(_QWORD, const struct std::nothrow_t *))(**(_QWORD **)&v18[8 * v24] + 32LL))(
                    *(_QWORD *)&v18[8 * v24],
                    v19);
            v4 = CDPComAccountFromCDPAccount(v25, &v13[16 * v24++]);
          }
          while ( v24 < v41 );
          v2 = a2;
          if ( v4 < 0 )
          {
LABEL_35:
            if ( v18 )
            {
              if ( v20 >= 0 )
              {
                v31 = v18;
                v32 = &v18[8 * v41];
                if ( v18 != v32 )
                {
                  do
                  {
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
                    v31 += 8;
                  }
                  while ( v31 != v32 );
                }
              }
            }
            goto LABEL_39;
          }
        }
        v11 = v37;
LABEL_29:
        v40 = (*(__int64 (__fastcall **)(__int64, const struct std::nothrow_t *))(*(_QWORD *)a1 + 56LL))(a1, v19);
        v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
        *(_DWORD *)(v2 + 16) = v26;
        v27 = v26 - 1;
        if ( v27 )
        {
          v28 = v27 - 2;
          if ( !v28 )
          {
            *(_DWORD *)(v2 + 20) |= 4u;
            goto LABEL_34;
          }
          v29 = v28 - 2;
          if ( v29 && v29 != 2 )
            goto LABEL_34;
        }
        *(_DWORD *)(v2 + 20) |= 1u;
LABEL_34:
        v19 = 0;
        Destination = 0;
        *(_QWORD *)v2 = v11;
        v33 = 0;
        *(_QWORD *)(v2 + 8) = v35;
        *(_WORD *)(v2 + 34) = v40;
        v30 = v13;
        v13 = 0;
        v38 = 0;
        *(_QWORD *)(v2 + 24) = v30;
        *(_WORD *)(v2 + 32) = v41;
        goto LABEL_35;
      }
      v4 = -2147024882;
    }
    v20 = v23;
    goto LABEL_35;
  }
LABEL_39:
  if ( v13 )
    CoTaskMemFree(v13);
  if ( v18 )
    operator delete(v18, v19);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v33);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Destination);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18018ddd8  mov     [rsp-38h+arg_0], rbx
0x18018dddd  mov     [rsp-38h+arg_8], rdx
0x18018dde2  push    rbp
0x18018dde3  push    rsi
0x18018dde4  push    rdi
0x18018dde5  push    r12
0x18018dde7  push    r13
0x18018dde9  push    r14
0x18018ddeb  push    r15
0x18018dded  mov     rbp, rsp
0x18018ddf0  sub     rsp, 60h
0x18018ddf4  mov     rsi, rdx
0x18018ddf7  mov     r14, rcx
0x18018ddfa  xor     ebx, ebx
0x18018ddfc  test    rdx, rdx
0x18018ddff  jnz     short loc_18018DE0B
0x18018de01  mov     eax, 80004003h
0x18018de06  jmp     loc_18018E0F9
0x18018de0b  test    r14, r14
0x18018de0e  jnz     short loc_18018DE1A
0x18018de10  mov     eax, 80070057h
0x18018de15  jmp     loc_18018E0F9
0x18018de1a  xorps   xmm0, xmm0
0x18018de1d  xor     eax, eax
0x18018de1f  movups  xmmword ptr [rdx], xmm0
0x18018de22  movups  xmmword ptr [rdx+10h], xmm0
0x18018de26  mov     [rdx+20h], rax
0x18018de2a  mov     [rbp+Destination], rbx
0x18018de2e  mov     rax, [rcx]
0x18018de31  mov     rax, [rax+18h]
0x18018de35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018de3a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18018de3e  mov     rcx, rdi
0x18018de41  inc     rcx
0x18018de44  cmp     [rax+rcx], bl
0x18018de47  jnz     short loc_18018DE41
0x18018de49  lea     r15, [rcx+1]
0x18018de4d  mov     rcx, r15; cb
0x18018de50  call    cs:__imp_CoTaskMemAlloc
0x18018de56  mov     rdx, rax
0x18018de59  lea     rcx, [rbp+Destination]
0x18018de5d  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x18018de62  mov     r13, [rbp+Destination]
0x18018de66  mov     [rbp+var_10], r13
0x18018de6a  test    r13, r13
0x18018de6d  jz      short loc_18018DE8F
0x18018de6f  mov     rax, [r14]
0x18018de72  mov     rcx, r14
0x18018de75  mov     rax, [rax+18h]
0x18018de79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018de7e  mov     r8, rax; Source
0x18018de81  mov     rdx, r15; SizeInBytes
0x18018de84  mov     rcx, r13; Destination
0x18018de87  call    cs:__imp_strcpy_s
0x18018de8d  jmp     short loc_18018DE94
0x18018de8f  mov     ebx, 8007000Eh
0x18018de94  xor     r15d, r15d
0x18018de97  mov     [rbp+var_20], r15
0x18018de9b  mov     [rbp+var_30], r15
0x18018de9f  test    ebx, ebx
0x18018dea1  js      loc_18018DF33
0x18018dea7  mov     rax, [r14]
0x18018deaa  mov     rcx, r14
0x18018dead  mov     rax, [rax+20h]
0x18018deb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018deb6  inc     rdi
0x18018deb9  cmp     [rax+rdi], r15b
0x18018debd  jnz     short loc_18018DEB6
0x18018debf  lea     rcx, [rdi+1]; cb
0x18018dec3  call    cs:__imp_CoTaskMemAlloc
0x18018dec9  mov     rdx, rax
0x18018decc  lea     rcx, [rbp+var_30]
0x18018ded0  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x18018ded5  test    r13, r13
0x18018ded8  jz      short loc_18018DF26
0x18018deda  mov     rax, [r14]
0x18018dedd  mov     rcx, r14
0x18018dee0  mov     rax, [rax+20h]
0x18018dee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018dee9  mov     r8, rax; Source
0x18018deec  lea     rdx, [rdi+1]; SizeInBytes
0x18018def0  mov     r12, [rbp+var_30]
0x18018def4  mov     [rbp+var_20], r12
0x18018def8  mov     rcx, r12; Destination
0x18018defb  call    cs:__imp_strcpy_s
0x18018df01  mov     [rbp+arg_10], r15w
0x18018df06  mov     rax, [r14]
0x18018df09  xor     r8d, r8d
0x18018df0c  lea     r9, [rbp+arg_10]
0x18018df10  xor     edx, edx
0x18018df12  mov     rcx, r14
0x18018df15  mov     rax, [rax+30h]
0x18018df19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018df1e  mov     ebx, eax
0x18018df20  movzx   eax, [rbp+arg_10]
0x18018df24  jmp     short loc_18018DF3A
0x18018df26  mov     ebx, 8007000Eh
0x18018df2b  mov     rcx, [rbp+var_30]
0x18018df2f  mov     [rbp+var_20], rcx
0x18018df33  mov     eax, r15d
0x18018df36  mov     [rbp+arg_10], ax
0x18018df3a  mov     rdi, r15
0x18018df3d  mov     [rbp+var_18], r15
0x18018df41  mov     [rbp+var_8], r15
0x18018df45  xor     edx, edx
0x18018df47  test    ebx, ebx
0x18018df49  js      loc_18018E0C7
0x18018df4f  mov     r12d, edx
0x18018df52  test    ax, ax
0x18018df55  jz      loc_18018E021
0x18018df5b  movzx   edx, ax
0x18018df5e  lea     rcx, [rbp+arg_18]
0x18018df62  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x18018df67  mov     rdx, rax
0x18018df6a  lea     rcx, [rbp+var_18]
0x18018df6e  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x18018df73  mov     rcx, [rbp+arg_18]; void *
0x18018df77  xor     edx, edx; struct std::nothrow_t *
0x18018df79  mov     [rbp+arg_18], rdx
0x18018df7d  test    rcx, rcx
0x18018df80  jz      short loc_18018DF87
0x18018df82  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018df87  mov     rdi, [rbp+var_18]
0x18018df8b  test    rdi, rdi
0x18018df8e  jz      loc_18018E11E
0x18018df94  mov     rax, [r14]
0x18018df97  lea     r9, [rbp+arg_10]
0x18018df9b  movzx   r8d, [rbp+arg_10]
0x18018dfa0  mov     rdx, rdi
0x18018dfa3  mov     rcx, r14
0x18018dfa6  mov     rax, [rax+30h]
0x18018dfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018dfaf  mov     ebx, eax
0x18018dfb1  mov     r13d, eax
0x18018dfb4  test    eax, eax
0x18018dfb6  js      loc_18018E116
0x18018dfbc  movzx   ecx, [rbp+arg_10]
0x18018dfc0  shl     rcx, 4; cb
0x18018dfc4  call    cs:__imp_CoTaskMemAlloc
0x18018dfca  mov     r15, rax
0x18018dfcd  mov     [rbp+var_8], rax
0x18018dfd1  xor     edx, edx
0x18018dfd3  test    rax, rax
0x18018dfd6  jz      loc_18018E111
0x18018dfdc  mov     r12d, ebx
0x18018dfdf  cmp     dx, [rbp+arg_10]
0x18018dfe3  jnb     short loc_18018E01D
0x18018dfe5  mov     esi, edx
0x18018dfe7  movsxd  rbx, esi
0x18018dfea  mov     rcx, [rdi+rbx*8]
0x18018dfee  mov     rax, [rcx]
0x18018dff1  mov     rax, [rax+20h]
0x18018dff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018dffa  add     rbx, rbx
0x18018dffd  lea     rdx, [r15+rbx*8]
0x18018e001  mov     rcx, rax
0x18018e004  call    CDPComAccountFromCDPAccount
0x18018e009  mov     ebx, eax
0x18018e00b  inc     esi
0x18018e00d  movzx   eax, [rbp+arg_10]
0x18018e011  cmp     esi, eax
0x18018e013  jl      short loc_18018DFE7
0x18018e015  test    ebx, ebx
0x18018e017  mov     rsi, [rbp+arg_8]
0x18018e01b  js      short loc_18018E095
0x18018e01d  mov     r13, [rbp+var_10]
0x18018e021  mov     rax, [r14]
0x18018e024  mov     rcx, r14
0x18018e027  mov     rax, [rax+38h]
0x18018e02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e030  mov     word ptr [rbp+arg_8], ax
0x18018e034  mov     rcx, [r14]
0x18018e037  mov     rax, [rcx+28h]
0x18018e03b  mov     rcx, r14
0x18018e03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e043  mov     [rsi+10h], eax
0x18018e046  sub     eax, 1
0x18018e049  jz      short loc_18018E05E
0x18018e04b  sub     eax, 2
0x18018e04e  jz      loc_18018E128
0x18018e054  sub     eax, 2
0x18018e057  jz      short loc_18018E05E
0x18018e059  cmp     eax, 2
0x18018e05c  jnz     short loc_18018E062
0x18018e05e  or      dword ptr [rsi+14h], 1
0x18018e062  xor     edx, edx
0x18018e064  mov     [rbp+Destination], rdx
0x18018e068  mov     [rsi], r13
0x18018e06b  mov     [rbp+var_30], rdx
0x18018e06f  mov     rax, [rbp+var_20]
0x18018e073  mov     [rsi+8], rax
0x18018e077  movzx   eax, word ptr [rbp+arg_8]
0x18018e07b  mov     [rsi+22h], ax
0x18018e07f  mov     rax, r15
0x18018e082  mov     r15d, edx
0x18018e085  mov     [rbp+var_8], rdx
0x18018e089  mov     [rsi+18h], rax
0x18018e08d  movzx   eax, [rbp+arg_10]
0x18018e091  mov     [rsi+20h], ax
0x18018e095  test    rdi, rdi
0x18018e098  jz      short loc_18018E0C7
0x18018e09a  test    r12d, r12d
0x18018e09d  js      short loc_18018E0C7
0x18018e09f  mov     rsi, rdi
0x18018e0a2  movzx   eax, [rbp+arg_10]
0x18018e0a6  lea     r14, [rdi+rax*8]
0x18018e0aa  cmp     rdi, r14
0x18018e0ad  jz      short loc_18018E0C7
0x18018e0af  mov     rcx, [rsi]
0x18018e0b2  mov     rax, [rcx]
0x18018e0b5  mov     rax, [rax+10h]
0x18018e0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e0be  add     rsi, 8
0x18018e0c2  cmp     rsi, r14
0x18018e0c5  jnz     short loc_18018E0AF
0x18018e0c7  test    r15, r15
0x18018e0ca  jz      short loc_18018E0D6
0x18018e0cc  mov     rcx, r15; pv
0x18018e0cf  call    cs:__imp_CoTaskMemFree
0x18018e0d5  nop
0x18018e0d6  test    rdi, rdi
0x18018e0d9  jz      short loc_18018E0E4
0x18018e0db  mov     rcx, rdi; void *
0x18018e0de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18018e0e3  nop
0x18018e0e4  lea     rcx, [rbp+var_30]
0x18018e0e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18018e0ed  nop
0x18018e0ee  lea     rcx, [rbp+Destination]
0x18018e0f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18018e0f7  mov     eax, ebx
0x18018e0f9  mov     rbx, [rsp+60h+arg_0]
0x18018e101  add     rsp, 60h
0x18018e105  pop     r15
0x18018e107  pop     r14
0x18018e109  pop     r13
0x18018e10b  pop     r12
0x18018e10d  pop     rdi
0x18018e10e  pop     rsi
0x18018e10f  pop     rbp
0x18018e110  retn
0x18018e111  mov     ebx, 8007000Eh
0x18018e116  mov     r12d, r13d
0x18018e119  jmp     loc_18018E095
0x18018e11e  mov     ebx, 8007000Eh
0x18018e123  jmp     loc_18018E095
0x18018e128  or      dword ptr [rsi+14h], 4
0x18018e12c  jmp     loc_18018E062
```
