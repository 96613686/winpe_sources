# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &> &&)

- ea: `0x1800c72dc`
- end: `0x1800c73c3`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `231`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800caeb4`

## callees

- `0x1800c72dc`
- `0x1800cad8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c735e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c73a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c735e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c73a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c734b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c734b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c73a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c73a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c733a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c733a`

## pseudocode

```c
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
0x1800c72dc  push    rbx
0x1800c72de  push    rbp
0x1800c72df  push    rsi
0x1800c72e0  push    rdi
0x1800c72e1  push    r14
0x1800c72e3  sub     rsp, 40h
0x1800c72e7  mov     rax, [rdx]
0x1800c72ea  mov     rdi, rcx
0x1800c72ed  mov     r8b, [rdx+8]
0x1800c72f1  mov     [rcx+10h], rax
0x1800c72f5  xor     eax, eax
0x1800c72f7  mov     [rcx+18h], r8b
0x1800c72fb  mov     rsi, [rdx+10h]
0x1800c72ff  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x1800c7304  mov     [rsp+68h+var_37], eax
0x1800c7308  mov     [rsp+68h+var_33], ax
0x1800c730d  mov     [rsp+68h+var_31], al
0x1800c7311  mov     [rsp+68h+var_48], 0
0x1800c731a  mov     [rsp+68h+var_40], 0
0x1800c7323  mov     [rsp+68h+var_38], 0
0x1800c7328  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x1800c732d  mov     rcx, [rsp+68h+var_40]
0x1800c7332  test    rcx, rcx
0x1800c7335  jz      short loc_1800C738D
0x1800c7337  add     rcx, rcx; cb
0x1800c733a  call    cs:__imp_CoTaskMemAlloc
0x1800c7340  mov     r14, [rsi]
0x1800c7343  mov     rbp, rax
0x1800c7346  test    r14, r14
0x1800c7349  jz      short loc_1800C7364
0x1800c734b  call    cs:__imp_GetLastError
0x1800c7351  mov     rcx, r14; pv
0x1800c7354  mov     ebx, eax
0x1800c7356  call    cs:__imp_CoTaskMemFree
0x1800c735c  mov     ecx, ebx; dwErrCode
0x1800c735e  call    cs:__imp_SetLastError
0x1800c7364  mov     [rsi], rbp
0x1800c7367  test    rbp, rbp
0x1800c736a  jz      short loc_1800C7380
0x1800c736c  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x1800c7371  mov     [rsp+68h+var_48], rbp
0x1800c7376  mov     rcx, rdi; this
0x1800c7379  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x1800c737e  jmp     short loc_1800C73B5
0x1800c7380  cmp     dword ptr [rdi+8], 0
0x1800c7384  jl      short loc_1800C738D
0x1800c7386  mov     dword ptr [rdi+8], 8007000Eh
0x1800c738d  mov     rbp, [rsi]
0x1800c7390  test    rbp, rbp
0x1800c7393  jz      short loc_1800C73AE
0x1800c7395  call    cs:__imp_GetLastError
0x1800c739b  mov     rcx, rbp; pv
0x1800c739e  mov     ebx, eax
0x1800c73a0  call    cs:__imp_CoTaskMemFree
0x1800c73a6  mov     ecx, ebx; dwErrCode
0x1800c73a8  call    cs:__imp_SetLastError
0x1800c73ae  mov     qword ptr [rsi], 0
0x1800c73b5  mov     rax, rdi
0x1800c73b8  add     rsp, 40h
0x1800c73bc  pop     r14
0x1800c73be  pop     rdi
0x1800c73bf  pop     rsi
0x1800c73c0  pop     rbp
0x1800c73c1  pop     rbx
0x1800c73c2  retn
```
