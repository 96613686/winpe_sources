# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)

- ea: `0x1800ad420`
- end: `0x1800ad504`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `228`
- prototype: `tson::input_archive *__fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b1f94`

## callees

- `0x1800ad420`
- `0x1800b1d4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad49f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad4e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad49f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ad4e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad4d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad4d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad4e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad4e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad47b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad47b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x1800ad420  push    rbx
0x1800ad422  push    rbp
0x1800ad423  push    rsi
0x1800ad424  push    rdi
0x1800ad425  push    r14
0x1800ad427  sub     rsp, 40h
0x1800ad42b  mov     rax, [rdx]
0x1800ad42e  mov     rdi, rcx
0x1800ad431  mov     r8b, [rdx+8]
0x1800ad435  mov     [rcx+10h], rax
0x1800ad439  xor     eax, eax
0x1800ad43b  mov     [rcx+18h], r8b
0x1800ad43f  mov     rsi, [rdx+10h]
0x1800ad443  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x1800ad448  mov     [rsp+68h+var_37], eax
0x1800ad44c  mov     [rsp+68h+var_33], ax
0x1800ad451  mov     [rsp+68h+var_31], al
0x1800ad455  mov     [rsp+68h+var_48], 0
0x1800ad45e  mov     [rsp+68h+cb], 0
0x1800ad467  mov     [rsp+68h+var_38], 0
0x1800ad46c  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x1800ad471  mov     rcx, [rsp+68h+cb]; cb
0x1800ad476  test    rcx, rcx
0x1800ad479  jz      short loc_1800AD4CE
0x1800ad47b  call    cs:__imp_CoTaskMemAlloc
0x1800ad481  mov     r14, [rsi]
0x1800ad484  mov     rbp, rax
0x1800ad487  test    r14, r14
0x1800ad48a  jz      short loc_1800AD4A5
0x1800ad48c  call    cs:__imp_GetLastError
0x1800ad492  mov     rcx, r14; pv
0x1800ad495  mov     ebx, eax
0x1800ad497  call    cs:__imp_CoTaskMemFree
0x1800ad49d  mov     ecx, ebx; dwErrCode
0x1800ad49f  call    cs:__imp_SetLastError
0x1800ad4a5  mov     [rsi], rbp
0x1800ad4a8  test    rbp, rbp
0x1800ad4ab  jz      short loc_1800AD4C1
0x1800ad4ad  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x1800ad4b2  mov     [rsp+68h+var_48], rbp
0x1800ad4b7  mov     rcx, rdi; this
0x1800ad4ba  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x1800ad4bf  jmp     short loc_1800AD4F6
0x1800ad4c1  cmp     dword ptr [rdi+8], 0
0x1800ad4c5  jl      short loc_1800AD4CE
0x1800ad4c7  mov     dword ptr [rdi+8], 8007000Eh
0x1800ad4ce  mov     rbp, [rsi]
0x1800ad4d1  test    rbp, rbp
0x1800ad4d4  jz      short loc_1800AD4EF
0x1800ad4d6  call    cs:__imp_GetLastError
0x1800ad4dc  mov     rcx, rbp; pv
0x1800ad4df  mov     ebx, eax
0x1800ad4e1  call    cs:__imp_CoTaskMemFree
0x1800ad4e7  mov     ecx, ebx; dwErrCode
0x1800ad4e9  call    cs:__imp_SetLastError
0x1800ad4ef  mov     qword ptr [rsi], 0
0x1800ad4f6  mov     rax, rdi
0x1800ad4f9  add     rsp, 40h
0x1800ad4fd  pop     r14
0x1800ad4ff  pop     rdi
0x1800ad500  pop     rsi
0x1800ad501  pop     rbp
0x1800ad502  pop     rbx
0x1800ad503  retn
```
