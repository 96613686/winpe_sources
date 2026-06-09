# CModule::SDKLoadLibraryW(ushort const *)

- ea: `0x18005efbc`
- end: `0x18005f251`
- name: `?SDKLoadLibraryW@CModule@@QEAAPEAUHINSTANCE__@@PEBG@Z`
- size: `661`
- prototype: `HINSTANCE(CModule *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004ef4c`
- `0x18008f2ec`

## callees

- `0x18000fd40`
- `0x18001960c`
- `0x18005efbc`
- `0x180076f14`
- `0x180076f20`
- `0x1800894c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f0c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f14d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f1d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f0c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f14d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f1d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
HINSTANCE __fastcall CModule::SDKLoadLibraryW(CModule *this, const unsigned __int16 *a2)
{
  HMODULE Library; // rsi
  __int64 v4; // r14
  unsigned __int64 v5; // rbx
  char *v6; // r15
  unsigned __int64 v7; // rcx
  char *v8; // rax
  size_t v9; // rbx
  __int64 v10; // rbx
  __int64 v12; // rbx
  __int64 v13; // rbx
  void *v14[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v15; // [rsp+30h] [rbp-48h]

  Library = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(v14);
  if ( HIDWORD(qword_180109B78) <= 1 )
    goto LABEL_26;
  v5 = v4 + HIDWORD(qword_180109B78) + 1LL;
  v6 = (char *)v14[1];
  v7 = ((char *)v14[1] - (char *)v14[0]) >> 1;
  if ( v5 < v7 )
  {
    v8 = (char *)v14[0] + 2 * v5;
LABEL_10:
    v14[1] = v8;
    goto LABEL_11;
  }
  if ( v5 > v7 )
  {
    if ( v5 <= (signed __int64)(v15 - (unsigned __int64)v14[0]) >> 1 )
    {
      v9 = 2 * (v5 - v7);
      memset_0(v14[1], 0, v9);
      v8 = &v6[v9];
      goto LABEL_10;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v14, v5);
  }
LABEL_11:
  memmove_0((char *)v14[0] + 2 * HIDWORD(qword_180109B78) - 2, a2, 2 * v4 + 2);
  if ( (unsigned int)qword_180109B70 > 1 )
  {
    v10 = (unsigned int)(HIDWORD(qword_180109B78) - qword_180109B70);
    memmove_0((char *)v14[0] + 2 * v10, lpMem, 2LL * (unsigned int)(qword_180109B70 - 1));
    Library = LoadLibraryExW((LPCWSTR)v14[0] + v10, 0, 0);
    if ( Library )
    {
      if ( v14[0] )
      {
        std::_Deallocate<16>(v14[0], 2 * ((signed __int64)(v15 - (unsigned __int64)v14[0]) >> 1));
        *(_OWORD *)v14 = 0;
        v15 = 0;
      }
      return Library;
    }
  }
  if ( HIDWORD(qword_180109B70) > 1 )
  {
    v12 = (unsigned int)(HIDWORD(qword_180109B78) - HIDWORD(qword_180109B70));
    memmove_0((char *)v14[0] + 2 * v12, xmmword_180109B60, 2LL * (unsigned int)(HIDWORD(qword_180109B70) - 1));
    Library = LoadLibraryExW((LPCWSTR)v14[0] + v12, 0, 0);
    if ( Library )
    {
      if ( v14[0] )
      {
        std::_Deallocate<16>(v14[0], 2 * ((signed __int64)(v15 - (unsigned __int64)v14[0]) >> 1));
        *(_OWORD *)v14 = 0;
        v15 = 0;
      }
      return Library;
    }
  }
  if ( (unsigned int)qword_180109B78 > 1 )
  {
    v13 = (unsigned int)(HIDWORD(qword_180109B78) - qword_180109B78);
    memmove_0((char *)v14[0] + 2 * v13, *(&xmmword_180109B60 + 1), 2LL * (unsigned int)(qword_180109B78 - 1));
    Library = LoadLibraryExW((LPCWSTR)v14[0] + v13, 0, 0);
    if ( Library )
    {
      if ( v14[0] )
      {
        std::_Deallocate<16>(v14[0], 2 * ((signed __int64)(v15 - (unsigned __int64)v14[0]) >> 1));
        *(_OWORD *)v14 = 0;
        v15 = 0;
      }
      return Library;
    }
  }
LABEL_26:
  if ( v14[0] )
    std::_Deallocate<16>(v14[0], 2 * ((signed __int64)(v15 - (unsigned __int64)v14[0]) >> 1));
  return Library;
}

```

## disassembly

```asm
0x18005efbc  mov     [rsp+arg_0], rcx
0x18005efc1  push    rbx
0x18005efc2  push    rsi
0x18005efc3  push    rdi
0x18005efc4  push    r12
0x18005efc6  push    r14
0x18005efc8  push    r15
0x18005efca  sub     rsp, 48h
0x18005efce  mov     r12, rdx
0x18005efd1  xor     edi, edi
0x18005efd3  mov     esi, edi
0x18005efd5  mov     [rsp+78h+arg_0], rdi
0x18005efdd  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005efe1  inc     r14
0x18005efe4  cmp     [rdx+r14*2], di
0x18005efe9  jnz     short loc_18005EFE1
0x18005efeb  lea     rcx, [rsp+78h+var_58]
0x18005eff0  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x18005eff5  nop
0x18005eff6  mov     eax, dword ptr cs:qword_180109B78+4
0x18005effc  cmp     eax, 1
0x18005efff  jbe     loc_18005F223
0x18005f005  lea     rbx, [rax+1]
0x18005f009  add     rbx, r14
0x18005f00c  mov     rdx, [rsp+78h+var_58]
0x18005f011  mov     r15, [rsp+78h+var_58+8]
0x18005f016  mov     rcx, r15
0x18005f019  sub     rcx, rdx
0x18005f01c  sar     rcx, 1
0x18005f01f  cmp     rbx, rcx
0x18005f022  jnb     short loc_18005F02A
0x18005f024  lea     rax, [rdx+rbx*2]
0x18005f028  jmp     short loc_18005F062
0x18005f02a  jbe     short loc_18005F067
0x18005f02c  mov     rax, [rsp+78h+var_48]
0x18005f031  sub     rax, rdx
0x18005f034  sar     rax, 1
0x18005f037  cmp     rbx, rax
0x18005f03a  jbe     short loc_18005F04B
0x18005f03c  mov     rdx, rbx
0x18005f03f  lea     rcx, [rsp+78h+var_58]
0x18005f044  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005f049  jmp     short loc_18005F067
0x18005f04b  sub     rbx, rcx
0x18005f04e  add     rbx, rbx
0x18005f051  mov     r8, rbx; Size
0x18005f054  xor     edx, edx; Val
0x18005f056  mov     rcx, r15; void *
0x18005f059  call    memset_0
0x18005f05e  lea     rax, [r15+rbx]
0x18005f062  mov     [rsp+78h+var_58+8], rax
0x18005f067  lea     r8, ds:2[r14*2]; Size
0x18005f06f  mov     ecx, dword ptr cs:qword_180109B78+4
0x18005f075  mov     rax, [rsp+78h+var_58]
0x18005f07a  sub     rax, 2
0x18005f07e  lea     rcx, [rax+rcx*2]; void *
0x18005f082  mov     rdx, r12; Src
0x18005f085  call    memmove_0
0x18005f08a  mov     ecx, dword ptr cs:qword_180109B70
0x18005f090  cmp     ecx, 1
0x18005f093  jbe     short loc_18005F110
0x18005f095  mov     ebx, dword ptr cs:qword_180109B78+4
0x18005f09b  sub     ebx, ecx
0x18005f09d  lea     r8d, [rcx-1]
0x18005f0a1  add     r8, r8; Size
0x18005f0a4  mov     rax, [rsp+78h+var_58]
0x18005f0a9  lea     rcx, [rax+rbx*2]; void *
0x18005f0ad  mov     rdx, cs:lpMem; Src
0x18005f0b4  call    memmove_0
0x18005f0b9  mov     rax, [rsp+78h+var_58]
0x18005f0be  lea     rcx, [rax+rbx*2]; lpLibFileName
0x18005f0c2  xor     r8d, r8d; dwFlags
0x18005f0c5  xor     edx, edx; hFile
0x18005f0c7  call    cs:__imp_LoadLibraryExW
0x18005f0cd  mov     rsi, rax
0x18005f0d0  mov     [rsp+78h+arg_0], rax
0x18005f0d8  test    rax, rax
0x18005f0db  jz      short loc_18005F110
0x18005f0dd  mov     rcx, [rsp+78h+var_58]
0x18005f0e2  test    rcx, rcx
0x18005f0e5  jz      short loc_18005F108
0x18005f0e7  mov     rdx, [rsp+78h+var_48]
0x18005f0ec  sub     rdx, rcx
0x18005f0ef  sar     rdx, 1
0x18005f0f2  add     rdx, rdx
0x18005f0f5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005f0fa  xorps   xmm0, xmm0
0x18005f0fd  movdqu  xmmword ptr [rsp+78h+var_58], xmm0
0x18005f103  mov     [rsp+78h+var_48], rdi
0x18005f108  mov     rax, rsi
0x18005f10b  jmp     loc_18005F243
0x18005f110  mov     ecx, dword ptr cs:qword_180109B70+4
0x18005f116  cmp     ecx, 1
0x18005f119  jbe     short loc_18005F196
0x18005f11b  mov     ebx, dword ptr cs:qword_180109B78+4
0x18005f121  sub     ebx, ecx
0x18005f123  lea     r8d, [rcx-1]
0x18005f127  add     r8, r8; Size
0x18005f12a  mov     rax, [rsp+78h+var_58]
0x18005f12f  lea     rcx, [rax+rbx*2]; void *
0x18005f133  mov     rdx, qword ptr cs:xmmword_180109B60; Src
0x18005f13a  call    memmove_0
0x18005f13f  mov     rax, [rsp+78h+var_58]
0x18005f144  lea     rcx, [rax+rbx*2]; lpLibFileName
0x18005f148  xor     r8d, r8d; dwFlags
0x18005f14b  xor     edx, edx; hFile
0x18005f14d  call    cs:__imp_LoadLibraryExW
0x18005f153  mov     rsi, rax
0x18005f156  mov     [rsp+78h+arg_0], rax
0x18005f15e  test    rax, rax
0x18005f161  jz      short loc_18005F196
0x18005f163  mov     rcx, [rsp+78h+var_58]
0x18005f168  test    rcx, rcx
0x18005f16b  jz      short loc_18005F18E
0x18005f16d  mov     rdx, [rsp+78h+var_48]
0x18005f172  sub     rdx, rcx
0x18005f175  sar     rdx, 1
0x18005f178  add     rdx, rdx
0x18005f17b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005f180  xorps   xmm0, xmm0
0x18005f183  movdqu  xmmword ptr [rsp+78h+var_58], xmm0
0x18005f189  mov     [rsp+78h+var_48], rdi
0x18005f18e  mov     rax, rsi
0x18005f191  jmp     loc_18005F243
0x18005f196  mov     ecx, dword ptr cs:qword_180109B78
0x18005f19c  cmp     ecx, 1
0x18005f19f  jbe     short loc_18005F219
0x18005f1a1  mov     ebx, dword ptr cs:qword_180109B78+4
0x18005f1a7  sub     ebx, ecx
0x18005f1a9  lea     r8d, [rcx-1]
0x18005f1ad  add     r8, r8; Size
0x18005f1b0  mov     rax, [rsp+78h+var_58]
0x18005f1b5  lea     rcx, [rax+rbx*2]; void *
0x18005f1b9  mov     rdx, qword ptr cs:xmmword_180109B60+8; Src
0x18005f1c0  call    memmove_0
0x18005f1c5  mov     rax, [rsp+78h+var_58]
0x18005f1ca  lea     rcx, [rax+rbx*2]; lpLibFileName
0x18005f1ce  xor     r8d, r8d; dwFlags
0x18005f1d1  xor     edx, edx; hFile
0x18005f1d3  call    cs:__imp_LoadLibraryExW
0x18005f1d9  mov     rsi, rax
0x18005f1dc  mov     [rsp+78h+arg_0], rax
0x18005f1e4  test    rax, rax
0x18005f1e7  jz      short loc_18005F219
0x18005f1e9  mov     rcx, [rsp+78h+var_58]
0x18005f1ee  test    rcx, rcx
0x18005f1f1  jz      short loc_18005F214
0x18005f1f3  mov     rdx, [rsp+78h+var_48]
0x18005f1f8  sub     rdx, rcx
0x18005f1fb  sar     rdx, 1
0x18005f1fe  add     rdx, rdx
0x18005f201  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005f206  xorps   xmm0, xmm0
0x18005f209  movdqu  xmmword ptr [rsp+78h+var_58], xmm0
0x18005f20f  mov     [rsp+78h+var_48], rdi
0x18005f214  mov     rax, rsi
0x18005f217  jmp     short loc_18005F243
0x18005f219  jmp     short loc_18005F223
0x18005f21b  mov     rsi, [rsp+78h+arg_0]
0x18005f223  mov     rcx, [rsp+78h+var_58]
0x18005f228  test    rcx, rcx
0x18005f22b  jz      short loc_18005F240
0x18005f22d  mov     rdx, [rsp+78h+var_48]
0x18005f232  sub     rdx, rcx
0x18005f235  sar     rdx, 1
0x18005f238  add     rdx, rdx
0x18005f23b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005f240  mov     rax, rsi
0x18005f243  add     rsp, 48h
0x18005f247  pop     r15
0x18005f249  pop     r14
0x18005f24b  pop     r12
0x18005f24d  pop     rdi
0x18005f24e  pop     rsi
0x18005f24f  pop     rbx
0x18005f250  retn
```
