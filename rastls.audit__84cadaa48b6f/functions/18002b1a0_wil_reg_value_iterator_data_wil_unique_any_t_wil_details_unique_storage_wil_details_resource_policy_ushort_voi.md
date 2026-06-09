# wil::reg::value_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)

- ea: `0x18002b1a0`
- end: `0x18002b348`
- name: `?enumerate_current_index@?$value_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ`
- size: `424`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180029ba8`
- `0x1800665a0`

## callees

- `0x18002b1a0`
- `0x18002dc28`
- `0x18002dc50`
- `0x18003b7a4`
- `0x180065b1c`
- `0x180067288`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002b27c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002b27c`

## string_xrefs

- `0x18002b1f8`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18002b2ba`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18002b307`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18002b336`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::reg::value_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::enumerate_current_index(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  DWORD v5; // eax
  __int64 v6; // rdi
  WCHAR *v8; // r8
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // edi
  unsigned int lpReserved; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD cchValueName; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 24) == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x68D,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      a4);
  v5 = 32;
  if ( *(_DWORD *)(a1 + 32) )
    v5 = *(_DWORD *)(a1 + 32);
  while ( 1 )
  {
    v6 = v5;
    cchValueName = v5;
    if ( (unsigned __int64)v5 <= *(_QWORD *)(a1 + 32) )
    {
      v6 = *(_QWORD *)(a1 + 32);
    }
    else if ( (int)wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a1, 2 * v5) < 0 )
    {
      *(_QWORD *)(a1 + 32) = 0;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x696,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        (const char *)0x8007000ELL,
        lpReserved);
      return 2147942414LL;
    }
    wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      a1,
      v6);
    *(_QWORD *)(a1 + 32) = v6;
    if ( !v6 )
      goto LABEL_7;
    v8 = cchValueName ? *(WCHAR **)a1 : 0LL;
    v9 = RegEnumValueW(*(HKEY *)(a1 + 16), *(_DWORD *)(a1 + 24), v8, &cchValueName, 0, (LPDWORD)(a1 + 8), 0, 0);
    if ( !v9 )
      break;
    if ( v9 == 259 )
    {
      wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        a1,
        *(_QWORD *)(a1 + 32));
      *(_DWORD *)(a1 + 24) = -1;
      return 0;
    }
    if ( v9 != 234 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x6CA,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
               (const char *)v9,
               lpReserved);
    if ( cchValueName == 0x4000 )
      return 0;
    v5 = 2 * cchValueName;
    if ( 2 * cchValueName > 0x4000 )
      v5 = 0x4000;
  }
  ++cchValueName;
  v10 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a1, 2 * cchValueName);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6AC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      (const char *)(unsigned int)v10,
      lpReserved);
    return v11;
  }
  *(_QWORD *)(a1 + 32) = cchValueName;
  return 0;
}

```

## disassembly

```asm
0x18002b1a0  mov     [rsp+arg_8], rbx
0x18002b1a5  mov     [rsp+arg_10], rdi
0x18002b1aa  push    r14
0x18002b1ac  sub     rsp, 40h
0x18002b1b0  cmp     dword ptr [rcx+18h], 0FFFFFFFFh
0x18002b1b4  mov     rbx, rcx
0x18002b1b7  jz      loc_18002B331
0x18002b1bd  cmp     dword ptr [rcx+20h], 0
0x18002b1c1  mov     eax, 20h ; ' '
0x18002b1c6  mov     r14d, 4000h
0x18002b1cc  cmova   eax, [rcx+20h]
0x18002b1d0  mov     edi, eax
0x18002b1d2  mov     [rsp+48h+cchValueName], eax
0x18002b1d6  cmp     rdi, [rbx+20h]
0x18002b1da  jbe     short loc_18002B225
0x18002b1dc  lea     edx, [rax+rax]
0x18002b1df  mov     rcx, rbx
0x18002b1e2  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18002b1e7  test    eax, eax
0x18002b1e9  jns     short loc_18002B229
0x18002b1eb  mov     qword ptr [rbx+20h], 0
0x18002b1f3  mov     rcx, [rsp+48h]; this
0x18002b1f8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b1ff  mov     ebx, 8007000Eh
0x18002b204  mov     edx, 696h; void *
0x18002b209  mov     r9d, ebx; char *
0x18002b20c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b211  mov     eax, ebx
0x18002b213  mov     rbx, [rsp+48h+arg_8]
0x18002b218  mov     rdi, [rsp+48h+arg_10]
0x18002b21d  add     rsp, 40h
0x18002b221  pop     r14
0x18002b223  retn
0x18002b225  mov     rdi, [rbx+20h]
0x18002b229  mov     rdx, rdi
0x18002b22c  mov     rcx, rbx
0x18002b22f  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18002b234  mov     [rbx+20h], rdi
0x18002b238  test    rdi, rdi
0x18002b23b  jz      short loc_18002B1F3
0x18002b23d  cmp     [rsp+48h+cchValueName], 0
0x18002b242  lea     rax, [rbx+8]
0x18002b246  jnz     short loc_18002B24D
0x18002b248  xor     r8d, r8d
0x18002b24b  jmp     short loc_18002B250
0x18002b24d  mov     r8, [rbx]; lpValueName
0x18002b250  mov     edx, [rbx+18h]; dwIndex
0x18002b253  lea     r9, [rsp+48h+cchValueName]; lpcchValueName
0x18002b258  mov     rcx, [rbx+10h]; hKey
0x18002b25c  mov     [rsp+48h+lpcbData], 0; lpcbData
0x18002b265  mov     [rsp+48h+lpData], 0; lpData
0x18002b26e  mov     [rsp+48h+lpType], rax; lpType
0x18002b273  mov     [rsp+48h+lpReserved], 0; int
0x18002b27c  call    cs:__imp_RegEnumValueW
0x18002b283  nop     dword ptr [rax+rax+00h]
0x18002b288  test    eax, eax
0x18002b28a  jz      short loc_18002B2E8
0x18002b28c  cmp     eax, 103h
0x18002b291  jz      short loc_18002B2D3
0x18002b293  cmp     eax, 0EAh
0x18002b298  jnz     short loc_18002B2B5
0x18002b29a  mov     eax, [rsp+48h+cchValueName]
0x18002b29e  cmp     eax, r14d
0x18002b2a1  jz      loc_18002B32A
0x18002b2a7  add     eax, eax
0x18002b2a9  cmp     eax, r14d
0x18002b2ac  cmova   eax, r14d
0x18002b2b0  jmp     loc_18002B1D0
0x18002b2b5  mov     rcx, [rsp+48h]; this
0x18002b2ba  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b2c1  mov     r9d, eax; char *
0x18002b2c4  mov     edx, 6CAh; void *
0x18002b2c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b2ce  jmp     loc_18002B213
0x18002b2d3  mov     rdx, [rbx+20h]
0x18002b2d7  mov     rcx, rbx
0x18002b2da  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18002b2df  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x18002b2e6  jmp     short loc_18002B32A
0x18002b2e8  mov     edx, [rsp+48h+cchValueName]
0x18002b2ec  mov     rcx, rbx
0x18002b2ef  inc     edx
0x18002b2f1  mov     [rsp+48h+cchValueName], edx
0x18002b2f5  add     edx, edx
0x18002b2f7  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18002b2fc  mov     edi, eax
0x18002b2fe  test    eax, eax
0x18002b300  jns     short loc_18002B322
0x18002b302  mov     rcx, [rsp+48h]; this
0x18002b307  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b30e  mov     r9d, eax; char *
0x18002b311  mov     edx, 6ACh; void *
0x18002b316  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b31b  mov     eax, edi
0x18002b31d  jmp     loc_18002B213
0x18002b322  mov     eax, [rsp+48h+cchValueName]
0x18002b326  mov     [rbx+20h], rax
0x18002b32a  xor     eax, eax
0x18002b32c  jmp     loc_18002B213
0x18002b331  mov     rcx, [rsp+48h]; this
0x18002b336  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b33d  mov     edx, 68Dh; void *
0x18002b342  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
