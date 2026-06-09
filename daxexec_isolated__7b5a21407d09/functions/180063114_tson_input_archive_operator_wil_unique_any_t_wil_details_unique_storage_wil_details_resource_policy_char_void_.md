# tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180063114`
- end: `0x180063213`
- name: `??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066208`
- `0x18006a300`
- `0x18006b3b0`

## callees

- `0x180063114`
- `0x18006b168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063195`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800631f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063195`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800631f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800631e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800631e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006315f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006315f`

## pseudocode

```c
tson::input_archive *__fastcall tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
        tson::input_archive *this,
        void **a2)
{
  LPVOID v4; // rax
  void *v5; // r14
  void *v6; // rbp
  DWORD LastError; // ebx
  void *v8; // rbp
  DWORD v9; // ebx
  void *v11; // [rsp+20h] [rbp-48h] BYREF
  SIZE_T cb; // [rsp+28h] [rbp-40h]
  char v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+31h] [rbp-37h]
  __int16 v15; // [rsp+35h] [rbp-33h]
  char v16; // [rsp+37h] [rbp-31h]

  v11 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  cb = 0;
  v13 = 0;
  tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v11);
  if ( cb )
  {
    v4 = CoTaskMemAlloc(cb);
    v5 = *a2;
    v6 = v4;
    if ( *a2 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v5);
      SetLastError(LastError);
    }
    *a2 = v6;
    if ( v6 )
    {
      v11 = v6;
      tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v11);
      return this;
    }
    if ( *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147024882;
  }
  v8 = *a2;
  if ( *a2 )
  {
    v9 = GetLastError();
    CoTaskMemFree(v8);
    SetLastError(v9);
  }
  *a2 = 0;
  return this;
}

```

## disassembly

```asm
0x180063114  push    rbx
0x180063116  push    rbp
0x180063117  push    rsi
0x180063118  push    rdi
0x180063119  push    r14
0x18006311b  sub     rsp, 40h
0x18006311f  xor     eax, eax
0x180063121  mov     [rsp+68h+var_48], 0
0x18006312a  mov     rsi, rdx
0x18006312d  mov     [rsp+68h+var_37], eax
0x180063131  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x180063136  mov     [rsp+68h+var_33], ax
0x18006313b  mov     [rsp+68h+var_31], al
0x18006313f  mov     rdi, rcx
0x180063142  mov     [rsp+68h+cb], 0
0x18006314b  mov     [rsp+68h+var_38], 0
0x180063150  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x180063155  mov     rcx, [rsp+68h+cb]; cb
0x18006315a  test    rcx, rcx
0x18006315d  jz      short loc_1800631CA
0x18006315f  call    cs:__imp_CoTaskMemAlloc
0x180063166  nop     dword ptr [rax+rax+00h]
0x18006316b  mov     r14, [rsi]
0x18006316e  mov     rbp, rax
0x180063171  test    r14, r14
0x180063174  jz      short loc_1800631A1
0x180063176  call    cs:__imp_GetLastError
0x18006317d  nop     dword ptr [rax+rax+00h]
0x180063182  mov     rcx, r14; pv
0x180063185  mov     ebx, eax
0x180063187  call    cs:__imp_CoTaskMemFree
0x18006318e  nop     dword ptr [rax+rax+00h]
0x180063193  mov     ecx, ebx; dwErrCode
0x180063195  call    cs:__imp_SetLastError
0x18006319c  nop     dword ptr [rax+rax+00h]
0x1800631a1  mov     [rsi], rbp
0x1800631a4  test    rbp, rbp
0x1800631a7  jz      short loc_1800631BD
0x1800631a9  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x1800631ae  mov     [rsp+68h+var_48], rbp
0x1800631b3  mov     rcx, rdi; this
0x1800631b6  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x1800631bb  jmp     short loc_180063204
0x1800631bd  cmp     dword ptr [rdi+8], 0
0x1800631c1  jl      short loc_1800631CA
0x1800631c3  mov     dword ptr [rdi+8], 8007000Eh
0x1800631ca  mov     rbp, [rsi]
0x1800631cd  test    rbp, rbp
0x1800631d0  jz      short loc_1800631FD
0x1800631d2  call    cs:__imp_GetLastError
0x1800631d9  nop     dword ptr [rax+rax+00h]
0x1800631de  mov     rcx, rbp; pv
0x1800631e1  mov     ebx, eax
0x1800631e3  call    cs:__imp_CoTaskMemFree
0x1800631ea  nop     dword ptr [rax+rax+00h]
0x1800631ef  mov     ecx, ebx; dwErrCode
0x1800631f1  call    cs:__imp_SetLastError
0x1800631f8  nop     dword ptr [rax+rax+00h]
0x1800631fd  mov     qword ptr [rsi], 0
0x180063204  mov     rax, rdi
0x180063207  add     rsp, 40h
0x18006320b  pop     r14
0x18006320d  pop     rdi
0x18006320e  pop     rsi
0x18006320f  pop     rbp
0x180063210  pop     rbx
0x180063211  retn
```
