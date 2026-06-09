# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &> &&)

- ea: `0x1800ad50c`
- end: `0x1800ad5f3`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `231`
- prototype: `tson::input_archive *__fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b1f94`

## callees

- `0x1800ad50c`
- `0x1800b1e6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad58e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad58e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad57b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad5c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad57b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad5c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad5d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad5d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad56a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad56a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
tson::input_archive *__fastcall tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &>>(
        tson::input_archive *this,
        __int64 a2)
{
  char v3; // r8
  void **v4; // rsi
  LPVOID v5; // rax
  void *v6; // r14
  void *v7; // rbp
  DWORD LastError; // ebx
  void *v9; // rbp
  DWORD v10; // ebx
  void *v12; // [rsp+20h] [rbp-48h] BYREF
  __int64 v13; // [rsp+28h] [rbp-40h]
  char v14; // [rsp+30h] [rbp-38h]
  int v15; // [rsp+31h] [rbp-37h]
  __int16 v16; // [rsp+35h] [rbp-33h]
  char v17; // [rsp+37h] [rbp-31h]

  v3 = *(_BYTE *)(a2 + 8);
  *((_QWORD *)this + 2) = *(_QWORD *)a2;
  *((_BYTE *)this + 24) = v3;
  v4 = *(void ***)(a2 + 16);
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  tson::input_archive::loadValue(this, (struct tson::string_tag *)&v12);
  if ( v13 )
  {
    v5 = CoTaskMemAlloc(2 * v13);
    v6 = *v4;
    v7 = v5;
    if ( *v4 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v6);
      SetLastError(LastError);
    }
    *v4 = v7;
    if ( v7 )
    {
      v12 = v7;
      tson::input_archive::loadValue(this, (struct tson::string_tag *)&v12);
      return this;
    }
    if ( *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147024882;
  }
  v9 = *v4;
  if ( *v4 )
  {
    v10 = GetLastError();
    CoTaskMemFree(v9);
    SetLastError(v10);
  }
  *v4 = 0;
  return this;
}

```

## disassembly

```asm
0x1800ad50c  push    rbx
0x1800ad50e  push    rbp
0x1800ad50f  push    rsi
0x1800ad510  push    rdi
0x1800ad511  push    r14
0x1800ad513  sub     rsp, 40h
0x1800ad517  mov     rax, [rdx]
0x1800ad51a  mov     rdi, rcx
0x1800ad51d  mov     r8b, [rdx+8]
0x1800ad521  mov     [rcx+10h], rax
0x1800ad525  xor     eax, eax
0x1800ad527  mov     [rcx+18h], r8b
0x1800ad52b  mov     rsi, [rdx+10h]
0x1800ad52f  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x1800ad534  mov     [rsp+68h+var_37], eax
0x1800ad538  mov     [rsp+68h+var_33], ax
0x1800ad53d  mov     [rsp+68h+var_31], al
0x1800ad541  mov     [rsp+68h+var_48], 0
0x1800ad54a  mov     [rsp+68h+var_40], 0
0x1800ad553  mov     [rsp+68h+var_38], 0
0x1800ad558  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x1800ad55d  mov     rcx, [rsp+68h+var_40]
0x1800ad562  test    rcx, rcx
0x1800ad565  jz      short loc_1800AD5BD
0x1800ad567  add     rcx, rcx; cb
0x1800ad56a  call    cs:__imp_CoTaskMemAlloc
0x1800ad570  mov     r14, [rsi]
0x1800ad573  mov     rbp, rax
0x1800ad576  test    r14, r14
0x1800ad579  jz      short loc_1800AD594
0x1800ad57b  call    cs:__imp_GetLastError
0x1800ad581  mov     rcx, r14; pv
0x1800ad584  mov     ebx, eax
0x1800ad586  call    cs:__imp_CoTaskMemFree
0x1800ad58c  mov     ecx, ebx; dwErrCode
0x1800ad58e  call    cs:__imp_SetLastError
0x1800ad594  mov     [rsi], rbp
0x1800ad597  test    rbp, rbp
0x1800ad59a  jz      short loc_1800AD5B0
0x1800ad59c  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x1800ad5a1  mov     [rsp+68h+var_48], rbp
0x1800ad5a6  mov     rcx, rdi; this
0x1800ad5a9  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x1800ad5ae  jmp     short loc_1800AD5E5
0x1800ad5b0  cmp     dword ptr [rdi+8], 0
0x1800ad5b4  jl      short loc_1800AD5BD
0x1800ad5b6  mov     dword ptr [rdi+8], 8007000Eh
0x1800ad5bd  mov     rbp, [rsi]
0x1800ad5c0  test    rbp, rbp
0x1800ad5c3  jz      short loc_1800AD5DE
0x1800ad5c5  call    cs:__imp_GetLastError
0x1800ad5cb  mov     rcx, rbp; pv
0x1800ad5ce  mov     ebx, eax
0x1800ad5d0  call    cs:__imp_CoTaskMemFree
0x1800ad5d6  mov     ecx, ebx; dwErrCode
0x1800ad5d8  call    cs:__imp_SetLastError
0x1800ad5de  mov     qword ptr [rsi], 0
0x1800ad5e5  mov     rax, rdi
0x1800ad5e8  add     rsp, 40h
0x1800ad5ec  pop     r14
0x1800ad5ee  pop     rdi
0x1800ad5ef  pop     rsi
0x1800ad5f0  pop     rbp
0x1800ad5f1  pop     rbx
0x1800ad5f2  retn
```
