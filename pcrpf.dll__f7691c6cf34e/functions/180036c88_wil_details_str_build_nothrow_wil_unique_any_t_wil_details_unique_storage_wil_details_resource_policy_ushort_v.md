# wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)

- ea: `0x180036c88`
- end: `0x180036f01`
- name: `??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z`
- size: `633`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180039210`

## callees

- `0x180009c64`
- `0x18000f0c8`
- `0x18002b8f4`
- `0x180036c88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036cf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036e47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036ea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036cf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036e47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036ea5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036e5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036eb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036e5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036eb9`

## string_xrefs

- `0x180036e8c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180036ece`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v4; // rsi
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rbp
  _QWORD *v9; // rax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  void *v12; // rbx
  char *v13; // r8
  char *v14; // r14
  _WORD *v15; // rcx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  signed int v18; // edi
  char *v19; // rdx
  char *v20; // r9
  __int64 v21; // r11
  char *v22; // rcx
  __int64 v23; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  HANDLE v27; // rax
  int v28; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID v30; // [rsp+58h] [rbp+10h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp+18h] BYREF

  v4 = a2;
  v6 = 0;
  v7 = a2;
  v8 = a2 + 16 * a3;
  if ( a2 != v8 )
  {
    do
    {
      v6 += *(_QWORD *)(v7 + 8);
      v7 += 16;
    }
    while ( v7 != v8 );
  }
  v30 = 0;
  v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         &lpMem,
         0,
         v6,
         a4);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v30,
    v9);
  v10 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  v12 = v30;
  if ( !v30 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v28);
    return 2147942414LL;
  }
  v13 = (char *)v30;
  v14 = (char *)v30 + 2 * v6 + 2;
  if ( v4 == v8 )
  {
LABEL_33:
    v30 = v12;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1,
      &v30);
    v24 = v30;
    if ( v30 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v24);
    }
    return 0;
  }
  while ( 1 )
  {
    v15 = *(_WORD **)v4;
    if ( !*(_QWORD *)v4 )
      goto LABEL_32;
    v16 = (v14 - v13) >> 1;
    if ( !v13 && v16 )
    {
      v18 = -2147024809;
      goto LABEL_39;
    }
    if ( v16 > 0x7FFFFFFF )
      break;
    v17 = *(_QWORD *)(v4 + 8);
    if ( v17 < 0x7FFFFFFF )
    {
      if ( v16 )
      {
        v20 = v13;
        v21 = 0;
        do
        {
          if ( !v17 )
            break;
          if ( !*v15 )
            break;
          *(_WORD *)v20 = *v15++;
          v20 += 2;
          --v17;
          ++v21;
          --v16;
        }
        while ( v16 );
        v22 = v20 - 2;
        if ( v16 )
          v22 = v20;
        v23 = v21 - 1;
        v18 = v16 != 0 ? 0 : 0x8007007A;
        *(_WORD *)v22 = 0;
        if ( v16 )
          v23 = v21;
        v19 = &v13[2 * v23];
      }
      else
      {
        v19 = v13;
        v18 = 0;
        if ( v17 && *v15 )
        {
          if ( !v13 )
          {
            v18 = -2147024809;
            goto LABEL_40;
          }
          v18 = -2147024774;
        }
      }
      if ( v18 >= 0 || v18 == -2147024774 )
        v13 = v19;
    }
    else
    {
      v18 = -2147024809;
      if ( v16 )
        *(_WORD *)v13 = 0;
    }
    if ( v18 < 0 )
      goto LABEL_40;
LABEL_32:
    v4 += 16;
    if ( v4 == v8 )
      goto LABEL_33;
  }
  v18 = -2147024809;
LABEL_39:
  *(_WORD *)v13 = 0;
LABEL_40:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x791,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)(unsigned int)v18,
    v28);
  if ( v12 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v12);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180036c88  mov     [rsp+arg_0], rbx
0x180036c8d  mov     [rsp+arg_18], rbp
0x180036c92  push    rsi
0x180036c93  push    rdi
0x180036c94  push    r12
0x180036c96  push    r14
0x180036c98  push    r15; int
0x180036c9a  sub     rsp, 20h
0x180036c9e  add     r8, r8
0x180036ca1  xor     r12d, r12d
0x180036ca4  mov     rsi, rdx
0x180036ca7  mov     r15, rcx
0x180036caa  mov     edi, r12d
0x180036cad  mov     rax, rdx
0x180036cb0  lea     rbp, [rdx+r8*8]
0x180036cb4  cmp     rdx, rbp
0x180036cb7  jz      short loc_180036CC6
0x180036cb9  add     rdi, [rax+8]
0x180036cbd  add     rax, 10h
0x180036cc1  cmp     rax, rbp
0x180036cc4  jnz     short loc_180036CB9
0x180036cc6  mov     r8, rdi
0x180036cc9  mov     [rsp+48h+arg_8], r12
0x180036cce  xor     edx, edx
0x180036cd0  lea     rcx, [rsp+48h+lpMem]
0x180036cd5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180036cda  mov     rdx, rax
0x180036cdd  lea     rcx, [rsp+48h+arg_8]
0x180036ce2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180036ce7  mov     rbx, [rsp+48h+lpMem]
0x180036cec  test    rbx, rbx
0x180036cef  jz      short loc_180036D11
0x180036cf1  call    cs:__imp_GetProcessHeap
0x180036cf8  nop     dword ptr [rax+rax+00h]
0x180036cfd  mov     r8, rbx; lpMem
0x180036d00  xor     edx, edx; dwFlags
0x180036d02  mov     rcx, rax; hHeap
0x180036d05  call    cs:__imp_HeapFree
0x180036d0c  nop     dword ptr [rax+rax+00h]
0x180036d11  mov     rbx, [rsp+48h+arg_8]
0x180036d16  test    rbx, rbx
0x180036d19  jz      loc_180036EC9
0x180036d1f  lea     r14, [rbx+2]
0x180036d23  mov     r8, rbx
0x180036d26  lea     r14, [r14+rdi*2]
0x180036d2a  cmp     rsi, rbp
0x180036d2d  jz      loc_180036E2B
0x180036d33  mov     r9d, 8007007Ah
0x180036d39  mov     rcx, [rsi]
0x180036d3c  test    rcx, rcx
0x180036d3f  jz      loc_180036E1E
0x180036d45  mov     rdx, r14
0x180036d48  sub     rdx, r8
0x180036d4b  sar     rdx, 1
0x180036d4e  test    r8, r8
0x180036d51  jnz     short loc_180036D5C
0x180036d53  test    rdx, rdx
0x180036d56  jnz     loc_180036E6B
0x180036d5c  cmp     rdx, 7FFFFFFFh
0x180036d63  ja      loc_180036E7E
0x180036d69  mov     rax, [rsi+8]
0x180036d6d  cmp     rax, 7FFFFFFFh
0x180036d73  jb      short loc_180036D8C
0x180036d75  mov     edi, 80070057h
0x180036d7a  test    rdx, rdx
0x180036d7d  jz      loc_180036E1A
0x180036d83  mov     [r8], r12w
0x180036d87  jmp     loc_180036E1A
0x180036d8c  test    rdx, rdx
0x180036d8f  jnz     short loc_180036DB0
0x180036d91  mov     rdx, r8
0x180036d94  mov     edi, r12d
0x180036d97  test    rax, rax
0x180036d9a  jz      short loc_180036E0E
0x180036d9c  cmp     [rcx], r12w
0x180036da0  jz      short loc_180036E0E
0x180036da2  test    r8, r8
0x180036da5  jz      loc_180036E77
0x180036dab  mov     edi, r9d
0x180036dae  jmp     short loc_180036E0E
0x180036db0  mov     r9, r8
0x180036db3  mov     r11, r12
0x180036db6  test    rax, rax
0x180036db9  jz      short loc_180036DDD
0x180036dbb  movzx   r10d, word ptr [rcx]
0x180036dbf  test    r10w, r10w
0x180036dc3  jz      short loc_180036DDD
0x180036dc5  mov     [r9], r10w
0x180036dc9  add     rcx, 2
0x180036dcd  add     r9, 2
0x180036dd1  dec     rax
0x180036dd4  inc     r11
0x180036dd7  sub     rdx, 1
0x180036ddb  jnz     short loc_180036DB6
0x180036ddd  test    rdx, rdx
0x180036de0  lea     rcx, [r9-2]
0x180036de4  mov     rax, rdx
0x180036de7  cmovnz  rcx, r9
0x180036deb  neg     rax
0x180036dee  mov     r9d, 8007007Ah
0x180036df4  lea     rax, [r11-1]
0x180036df8  sbb     edi, edi
0x180036dfa  not     edi
0x180036dfc  and     edi, r9d
0x180036dff  mov     [rcx], r12w
0x180036e03  test    rdx, rdx
0x180036e06  cmovnz  rax, r11
0x180036e0a  lea     rdx, [r8+rax*2]
0x180036e0e  test    edi, edi
0x180036e10  jns     short loc_180036E17
0x180036e12  cmp     edi, r9d
0x180036e15  jnz     short loc_180036E1A
0x180036e17  mov     r8, rdx
0x180036e1a  test    edi, edi
0x180036e1c  js      short loc_180036E87
0x180036e1e  add     rsi, 10h
0x180036e22  cmp     rsi, rbp
0x180036e25  jnz     loc_180036D39
0x180036e2b  lea     rdx, [rsp+48h+arg_8]
0x180036e30  mov     [rsp+48h+arg_8], rbx
0x180036e35  mov     rcx, r15
0x180036e38  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180036e3d  mov     rbx, [rsp+48h+arg_8]
0x180036e42  test    rbx, rbx
0x180036e45  jz      short loc_180036E67
0x180036e47  call    cs:__imp_GetProcessHeap
0x180036e4e  nop     dword ptr [rax+rax+00h]
0x180036e53  mov     r8, rbx; lpMem
0x180036e56  xor     edx, edx; dwFlags
0x180036e58  mov     rcx, rax; hHeap
0x180036e5b  call    cs:__imp_HeapFree
0x180036e62  nop     dword ptr [rax+rax+00h]
0x180036e67  xor     eax, eax
0x180036e69  jmp     short loc_180036EE9
0x180036e6b  mov     edi, 80070057h
0x180036e70  test    rdx, rdx
0x180036e73  jz      short loc_180036E87
0x180036e75  jmp     short loc_180036E83
0x180036e77  mov     edi, 80070057h
0x180036e7c  jmp     short loc_180036E87
0x180036e7e  mov     edi, 80070057h
0x180036e83  mov     [r8], r12w
0x180036e87  mov     rcx, [rsp+48h]; this
0x180036e8c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180036e93  mov     r9d, edi; char *
0x180036e96  mov     edx, 791h; void *
0x180036e9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036ea0  test    rbx, rbx
0x180036ea3  jz      short loc_180036EC5
0x180036ea5  call    cs:__imp_GetProcessHeap
0x180036eac  nop     dword ptr [rax+rax+00h]
0x180036eb1  mov     r8, rbx; lpMem
0x180036eb4  xor     edx, edx; dwFlags
0x180036eb6  mov     rcx, rax; hHeap
0x180036eb9  call    cs:__imp_HeapFree
0x180036ec0  nop     dword ptr [rax+rax+00h]
0x180036ec5  mov     eax, edi
0x180036ec7  jmp     short loc_180036EE9
0x180036ec9  mov     rcx, [rsp+48h]; this
0x180036ece  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180036ed5  mov     ebx, 8007000Eh
0x180036eda  mov     edx, 788h; void *
0x180036edf  mov     r9d, ebx; char *
0x180036ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036ee7  mov     eax, ebx
0x180036ee9  mov     rbx, [rsp+48h+arg_0]
0x180036eee  mov     rbp, [rsp+48h+arg_18]
0x180036ef3  add     rsp, 20h
0x180036ef7  pop     r15
0x180036ef9  pop     r14
0x180036efb  pop     r12
0x180036efd  pop     rdi
0x180036efe  pop     rsi
0x180036eff  retn
```
