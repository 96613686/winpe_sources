# wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)

- ea: `0x180005ecc`
- end: `0x180006132`
- name: `??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006138`

## callees

- `0x180005de8`
- `0x180005ecc`
- `0x18000b0f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000606f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000606f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000608e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000608e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060ea`

## string_xrefs

- `0x1800060c0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800060ff`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        char *a1,
        __int64 a2,
        void *a3)
{
  __int64 v3; // rbp
  __int64 v4; // rsi
  __int64 v6; // rdi
  __int64 v7; // rax
  char *v8; // rbx
  int *v9; // rax
  char *v10; // r8
  char *v11; // r15
  _WORD *v12; // rcx
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rax
  signed int v15; // edi
  char *v16; // rdx
  char *v17; // r9
  __int64 v18; // r11
  char *v19; // rcx
  __int64 v20; // rax
  void *v21; // rsi
  DWORD LastError; // edi
  int v24; // [rsp+20h] [rbp-38h] BYREF
  char v25; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF

  hMem = a3;
  v3 = a2 + 48;
  v4 = a2;
  v6 = 0;
  v7 = a2;
  do
  {
    v6 += *(_QWORD *)(v7 + 8);
    v7 += 16;
  }
  while ( v7 != v3 );
  v8 = 0;
  v9 = (int *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &hMem,
                0,
                v6);
  if ( &v24 != v9 )
  {
    v8 = *(char **)v9;
    *(_QWORD *)v9 = 0;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v24);
    return 2147942414LL;
  }
  v10 = v8;
  v11 = &v8[2 * v6 + 2];
  if ( v4 == v3 )
  {
LABEL_35:
    if ( a1 == &v25 )
    {
      LocalFree(v8);
    }
    else
    {
      v21 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        LastError = GetLastError();
        LocalFree(v21);
        SetLastError(LastError);
      }
      *(_QWORD *)a1 = v8;
    }
    return 0;
  }
  while ( 1 )
  {
    v12 = *(_WORD **)v4;
    if ( !*(_QWORD *)v4 )
      goto LABEL_34;
    v13 = (v11 - v10) >> 1;
    if ( !v10 && v13 )
    {
      v15 = -2147024809;
      goto LABEL_42;
    }
    if ( v13 > 0x7FFFFFFF )
      break;
    v14 = *(_QWORD *)(v4 + 8);
    if ( v14 < 0x7FFFFFFF )
    {
      if ( v13 )
      {
        v17 = v10;
        v18 = 0;
        do
        {
          if ( !v14 )
            break;
          if ( !*v12 )
            break;
          *(_WORD *)v17 = *v12++;
          v17 += 2;
          --v14;
          ++v18;
          --v13;
        }
        while ( v13 );
        v19 = v17 - 2;
        if ( v13 )
          v19 = v17;
        v20 = v18 - 1;
        v15 = v13 != 0 ? 0 : 0x8007007A;
        *(_WORD *)v19 = 0;
        if ( v13 )
          v20 = v18;
        v16 = &v10[2 * v20];
      }
      else
      {
        v16 = v10;
        v15 = 0;
        if ( v14 && *v12 )
        {
          if ( !v10 )
          {
            v15 = -2147024809;
            goto LABEL_43;
          }
          v15 = -2147024774;
        }
      }
      if ( v15 >= 0 || v15 == -2147024774 )
        v10 = v16;
    }
    else
    {
      v15 = -2147024809;
      if ( v13 )
        *(_WORD *)v10 = 0;
    }
    if ( v15 < 0 )
      goto LABEL_43;
LABEL_34:
    v4 += 16;
    if ( v4 == v3 )
      goto LABEL_35;
  }
  v15 = -2147024809;
LABEL_42:
  *(_WORD *)v10 = 0;
LABEL_43:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x791,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)(unsigned int)v15,
    v24);
  LocalFree(v8);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180005ecc  mov     [rsp+arg_0], rbx
0x180005ed1  mov     [rsp+arg_8], rbp
0x180005ed6  mov     [rsp+hMem], r8
0x180005edb  push    rsi
0x180005edc  push    rdi
0x180005edd  push    r12
0x180005edf  push    r14
0x180005ee1  push    r15
0x180005ee3  sub     rsp, 30h
0x180005ee7  xor     r12d, r12d
0x180005eea  lea     rbp, [rdx+30h]
0x180005eee  mov     rsi, rdx
0x180005ef1  mov     r14, rcx
0x180005ef4  mov     edi, r12d
0x180005ef7  mov     rax, rdx
0x180005efa  cmp     rdx, rbp
0x180005efd  jz      short loc_180005F0C
0x180005eff  add     rdi, [rax+8]
0x180005f03  add     rax, 10h
0x180005f07  cmp     rax, rbp
0x180005f0a  jnz     short loc_180005EFF
0x180005f0c  mov     r8, rdi
0x180005f0f  lea     rcx, [rsp+58h+hMem]
0x180005f14  xor     edx, edx
0x180005f16  mov     rbx, r12
0x180005f19  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180005f1e  lea     rcx, [rsp+58h+var_38]
0x180005f23  cmp     rcx, rax
0x180005f26  jz      short loc_180005F2E
0x180005f28  mov     rbx, [rax]
0x180005f2b  mov     [rax], r12
0x180005f2e  mov     rcx, [rsp+58h+hMem]; hMem
0x180005f33  test    rcx, rcx
0x180005f36  jz      short loc_180005F44
0x180005f38  call    cs:__imp_LocalFree
0x180005f3f  nop     dword ptr [rax+rax+00h]
0x180005f44  test    rbx, rbx
0x180005f47  jz      loc_1800060FA
0x180005f4d  lea     r15, [rdi+1]
0x180005f51  mov     r8, rbx
0x180005f54  lea     r15, [rbx+r15*2]
0x180005f58  cmp     rsi, rbp
0x180005f5b  jz      loc_180006059
0x180005f61  mov     r9d, 8007007Ah
0x180005f67  mov     rcx, [rsi]
0x180005f6a  test    rcx, rcx
0x180005f6d  jz      loc_18000604C
0x180005f73  mov     rdx, r15
0x180005f76  sub     rdx, r8
0x180005f79  sar     rdx, 1
0x180005f7c  test    r8, r8
0x180005f7f  jnz     short loc_180005F8A
0x180005f81  test    rdx, rdx
0x180005f84  jnz     loc_18000609F
0x180005f8a  cmp     rdx, 7FFFFFFFh
0x180005f91  ja      loc_1800060B2
0x180005f97  mov     rax, [rsi+8]
0x180005f9b  cmp     rax, 7FFFFFFFh
0x180005fa1  jb      short loc_180005FBA
0x180005fa3  mov     edi, 80070057h
0x180005fa8  test    rdx, rdx
0x180005fab  jz      loc_180006048
0x180005fb1  mov     [r8], r12w
0x180005fb5  jmp     loc_180006048
0x180005fba  test    rdx, rdx
0x180005fbd  jnz     short loc_180005FDE
0x180005fbf  mov     rdx, r8
0x180005fc2  mov     edi, r12d
0x180005fc5  test    rax, rax
0x180005fc8  jz      short loc_18000603C
0x180005fca  cmp     [rcx], r12w
0x180005fce  jz      short loc_18000603C
0x180005fd0  test    r8, r8
0x180005fd3  jz      loc_1800060AB
0x180005fd9  mov     edi, r9d
0x180005fdc  jmp     short loc_18000603C
0x180005fde  mov     r9, r8
0x180005fe1  mov     r11, r12
0x180005fe4  test    rax, rax
0x180005fe7  jz      short loc_18000600B
0x180005fe9  movzx   r10d, word ptr [rcx]
0x180005fed  test    r10w, r10w
0x180005ff1  jz      short loc_18000600B
0x180005ff3  mov     [r9], r10w
0x180005ff7  add     rcx, 2
0x180005ffb  add     r9, 2
0x180005fff  dec     rax
0x180006002  inc     r11
0x180006005  sub     rdx, 1
0x180006009  jnz     short loc_180005FE4
0x18000600b  test    rdx, rdx
0x18000600e  lea     rcx, [r9-2]
0x180006012  mov     rax, rdx
0x180006015  cmovnz  rcx, r9
0x180006019  neg     rax
0x18000601c  mov     r9d, 8007007Ah
0x180006022  lea     rax, [r11-1]
0x180006026  sbb     edi, edi
0x180006028  not     edi
0x18000602a  and     edi, r9d
0x18000602d  mov     [rcx], r12w
0x180006031  test    rdx, rdx
0x180006034  cmovnz  rax, r11
0x180006038  lea     rdx, [r8+rax*2]
0x18000603c  test    edi, edi
0x18000603e  jns     short loc_180006045
0x180006040  cmp     edi, r9d
0x180006043  jnz     short loc_180006048
0x180006045  mov     r8, rdx
0x180006048  test    edi, edi
0x18000604a  js      short loc_1800060BB
0x18000604c  add     rsi, 10h
0x180006050  cmp     rsi, rbp
0x180006053  jnz     loc_180005F67
0x180006059  lea     rax, [rsp+58h+var_30]
0x18000605e  cmp     r14, rax
0x180006061  jz      loc_1800060E7
0x180006067  mov     rsi, [r14]
0x18000606a  test    rsi, rsi
0x18000606d  jz      short loc_18000609A
0x18000606f  call    cs:__imp_GetLastError
0x180006076  nop     dword ptr [rax+rax+00h]
0x18000607b  mov     rcx, rsi; hMem
0x18000607e  mov     edi, eax
0x180006080  call    cs:__imp_LocalFree
0x180006087  nop     dword ptr [rax+rax+00h]
0x18000608c  mov     ecx, edi; dwErrCode
0x18000608e  call    cs:__imp_SetLastError
0x180006095  nop     dword ptr [rax+rax+00h]
0x18000609a  mov     [r14], rbx
0x18000609d  jmp     short loc_1800060F6
0x18000609f  mov     edi, 80070057h
0x1800060a4  test    rdx, rdx
0x1800060a7  jz      short loc_1800060BB
0x1800060a9  jmp     short loc_1800060B7
0x1800060ab  mov     edi, 80070057h
0x1800060b0  jmp     short loc_1800060BB
0x1800060b2  mov     edi, 80070057h
0x1800060b7  mov     [r8], r12w
0x1800060bb  mov     rcx, [rsp+58h]; this
0x1800060c0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800060c7  mov     r9d, edi; char *
0x1800060ca  mov     edx, 791h; void *
0x1800060cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060d4  mov     rcx, rbx; hMem
0x1800060d7  call    cs:__imp_LocalFree
0x1800060de  nop     dword ptr [rax+rax+00h]
0x1800060e3  mov     eax, edi
0x1800060e5  jmp     short loc_18000611A
0x1800060e7  mov     rcx, rbx; hMem
0x1800060ea  call    cs:__imp_LocalFree
0x1800060f1  nop     dword ptr [rax+rax+00h]
0x1800060f6  xor     eax, eax
0x1800060f8  jmp     short loc_18000611A
0x1800060fa  mov     rcx, [rsp+58h]; this
0x1800060ff  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006106  mov     ebx, 8007000Eh
0x18000610b  mov     edx, 788h; void *
0x180006110  mov     r9d, ebx; char *
0x180006113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006118  mov     eax, ebx
0x18000611a  mov     rbx, [rsp+58h+arg_0]
0x18000611f  mov     rbp, [rsp+58h+arg_8]
0x180006124  add     rsp, 30h
0x180006128  pop     r15
0x18000612a  pop     r14
0x18000612c  pop     r12
0x18000612e  pop     rdi
0x18000612f  pop     rsi
0x180006130  retn
```
