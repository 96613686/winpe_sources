# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)

- ea: `0x1800c71f0`
- end: `0x1800c72d4`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `228`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800caeb4`

## callees

- `0x1800c71f0`
- `0x1800cac6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c726f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c72b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c726f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c72b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c725c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c72a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c725c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c72a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7267`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c72b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7267`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c72b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c724b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c724b`

## pseudocode

```c
tson::input_archive *__fastcall tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(
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
  SIZE_T cb; // [rsp+28h] [rbp-40h]
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
  cb = 0;
  v14 = 0;
  tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v12);
  if ( cb )
  {
    v5 = CoTaskMemAlloc(cb);
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
      tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v12);
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
0x1800c71f0  push    rbx
0x1800c71f2  push    rbp
0x1800c71f3  push    rsi
0x1800c71f4  push    rdi
0x1800c71f5  push    r14
0x1800c71f7  sub     rsp, 40h
0x1800c71fb  mov     rax, [rdx]
0x1800c71fe  mov     rdi, rcx
0x1800c7201  mov     r8b, [rdx+8]
0x1800c7205  mov     [rcx+10h], rax
0x1800c7209  xor     eax, eax
0x1800c720b  mov     [rcx+18h], r8b
0x1800c720f  mov     rsi, [rdx+10h]
0x1800c7213  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x1800c7218  mov     [rsp+68h+var_37], eax
0x1800c721c  mov     [rsp+68h+var_33], ax
0x1800c7221  mov     [rsp+68h+var_31], al
0x1800c7225  mov     [rsp+68h+var_48], 0
0x1800c722e  mov     [rsp+68h+cb], 0
0x1800c7237  mov     [rsp+68h+var_38], 0
0x1800c723c  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x1800c7241  mov     rcx, [rsp+68h+cb]; cb
0x1800c7246  test    rcx, rcx
0x1800c7249  jz      short loc_1800C729E
0x1800c724b  call    cs:__imp_CoTaskMemAlloc
0x1800c7251  mov     r14, [rsi]
0x1800c7254  mov     rbp, rax
0x1800c7257  test    r14, r14
0x1800c725a  jz      short loc_1800C7275
0x1800c725c  call    cs:__imp_GetLastError
0x1800c7262  mov     rcx, r14; pv
0x1800c7265  mov     ebx, eax
0x1800c7267  call    cs:__imp_CoTaskMemFree
0x1800c726d  mov     ecx, ebx; dwErrCode
0x1800c726f  call    cs:__imp_SetLastError
0x1800c7275  mov     [rsi], rbp
0x1800c7278  test    rbp, rbp
0x1800c727b  jz      short loc_1800C7291
0x1800c727d  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x1800c7282  mov     [rsp+68h+var_48], rbp
0x1800c7287  mov     rcx, rdi; this
0x1800c728a  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x1800c728f  jmp     short loc_1800C72C6
0x1800c7291  cmp     dword ptr [rdi+8], 0
0x1800c7295  jl      short loc_1800C729E
0x1800c7297  mov     dword ptr [rdi+8], 8007000Eh
0x1800c729e  mov     rbp, [rsi]
0x1800c72a1  test    rbp, rbp
0x1800c72a4  jz      short loc_1800C72BF
0x1800c72a6  call    cs:__imp_GetLastError
0x1800c72ac  mov     rcx, rbp; pv
0x1800c72af  mov     ebx, eax
0x1800c72b1  call    cs:__imp_CoTaskMemFree
0x1800c72b7  mov     ecx, ebx; dwErrCode
0x1800c72b9  call    cs:__imp_SetLastError
0x1800c72bf  mov     qword ptr [rsi], 0
0x1800c72c6  mov     rax, rdi
0x1800c72c9  add     rsp, 40h
0x1800c72cd  pop     r14
0x1800c72cf  pop     rdi
0x1800c72d0  pop     rsi
0x1800c72d1  pop     rbp
0x1800c72d2  pop     rbx
0x1800c72d3  retn
```
