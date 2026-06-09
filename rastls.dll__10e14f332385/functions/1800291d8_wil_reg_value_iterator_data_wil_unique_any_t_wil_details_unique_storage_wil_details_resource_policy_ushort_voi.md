# wil::reg::value_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)

- ea: `0x1800291d8`
- end: `0x180029379`
- name: `?enumerate_current_index@?$value_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ`
- size: `417`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180027c44`
- `0x180062bec`

## callees

- `0x1800291d8`
- `0x18002b7b4`
- `0x18002b7d8`
- `0x180038af0`
- `0x18006219c`
- `0x180063840`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800292b3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800292b3`

## string_xrefs

- `0x180029230`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x1800292eb`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180029338`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180029367`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

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
0x1800291d8  mov     [rsp+arg_8], rbx
0x1800291dd  mov     [rsp+arg_10], rdi
0x1800291e2  push    r14
0x1800291e4  sub     rsp, 40h
0x1800291e8  cmp     dword ptr [rcx+18h], 0FFFFFFFFh
0x1800291ec  mov     rbx, rcx
0x1800291ef  jz      loc_180029362
0x1800291f5  cmp     dword ptr [rcx+20h], 0
0x1800291f9  mov     eax, 20h ; ' '
0x1800291fe  mov     r14d, 4000h
0x180029204  cmova   eax, [rcx+20h]
0x180029208  mov     edi, eax
0x18002920a  mov     [rsp+48h+cchValueName], eax
0x18002920e  cmp     rdi, [rbx+20h]
0x180029212  jbe     short loc_18002925C
0x180029214  lea     edx, [rax+rax]
0x180029217  mov     rcx, rbx
0x18002921a  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18002921f  test    eax, eax
0x180029221  jns     short loc_180029260
0x180029223  mov     qword ptr [rbx+20h], 0
0x18002922b  mov     rcx, [rsp+48h]; this
0x180029230  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180029237  mov     ebx, 8007000Eh
0x18002923c  mov     edx, 696h; void *
0x180029241  mov     r9d, ebx; char *
0x180029244  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029249  mov     eax, ebx
0x18002924b  mov     rbx, [rsp+48h+arg_8]
0x180029250  mov     rdi, [rsp+48h+arg_10]
0x180029255  add     rsp, 40h
0x180029259  pop     r14
0x18002925b  retn
0x18002925c  mov     rdi, [rbx+20h]
0x180029260  mov     rdx, rdi
0x180029263  mov     rcx, rbx
0x180029266  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18002926b  mov     [rbx+20h], rdi
0x18002926f  test    rdi, rdi
0x180029272  jz      short loc_18002922B
0x180029274  cmp     [rsp+48h+cchValueName], 0
0x180029279  lea     rax, [rbx+8]
0x18002927d  jnz     short loc_180029284
0x18002927f  xor     r8d, r8d
0x180029282  jmp     short loc_180029287
0x180029284  mov     r8, [rbx]; lpValueName
0x180029287  mov     edx, [rbx+18h]; dwIndex
0x18002928a  lea     r9, [rsp+48h+cchValueName]; lpcchValueName
0x18002928f  mov     rcx, [rbx+10h]; hKey
0x180029293  mov     [rsp+48h+lpcbData], 0; lpcbData
0x18002929c  mov     [rsp+48h+lpData], 0; lpData
0x1800292a5  mov     [rsp+48h+lpType], rax; lpType
0x1800292aa  mov     [rsp+48h+lpReserved], 0; int
0x1800292b3  call    cs:__imp_RegEnumValueW
0x1800292b9  test    eax, eax
0x1800292bb  jz      short loc_180029319
0x1800292bd  cmp     eax, 103h
0x1800292c2  jz      short loc_180029304
0x1800292c4  cmp     eax, 0EAh
0x1800292c9  jnz     short loc_1800292E6
0x1800292cb  mov     eax, [rsp+48h+cchValueName]
0x1800292cf  cmp     eax, r14d
0x1800292d2  jz      loc_18002935B
0x1800292d8  add     eax, eax
0x1800292da  cmp     eax, r14d
0x1800292dd  cmova   eax, r14d
0x1800292e1  jmp     loc_180029208
0x1800292e6  mov     rcx, [rsp+48h]; this
0x1800292eb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800292f2  mov     r9d, eax; char *
0x1800292f5  mov     edx, 6CAh; void *
0x1800292fa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800292ff  jmp     loc_18002924B
0x180029304  mov     rdx, [rbx+20h]
0x180029308  mov     rcx, rbx
0x18002930b  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x180029310  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x180029317  jmp     short loc_18002935B
0x180029319  mov     edx, [rsp+48h+cchValueName]
0x18002931d  mov     rcx, rbx
0x180029320  inc     edx
0x180029322  mov     [rsp+48h+cchValueName], edx
0x180029326  add     edx, edx
0x180029328  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18002932d  mov     edi, eax
0x18002932f  test    eax, eax
0x180029331  jns     short loc_180029353
0x180029333  mov     rcx, [rsp+48h]; this
0x180029338  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002933f  mov     r9d, eax; char *
0x180029342  mov     edx, 6ACh; void *
0x180029347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002934c  mov     eax, edi
0x18002934e  jmp     loc_18002924B
0x180029353  mov     eax, [rsp+48h+cchValueName]
0x180029357  mov     [rbx+20h], rax
0x18002935b  xor     eax, eax
0x18002935d  jmp     loc_18002924B
0x180029362  mov     rcx, [rsp+48h]; this
0x180029367  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002936e  mov     edx, 68Dh; void *
0x180029373  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
