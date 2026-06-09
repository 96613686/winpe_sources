# tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180061634`
- end: `0x180061745`
- name: `??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006447c`
- `0x180068840`
- `0x18006991c`

## callees

- `0x180061634`
- `0x1800696cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006169b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800616f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006169b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800616f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800616ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061716`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800616ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800616ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800616ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061684`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061684`

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
  void *v11; // [rsp+20h] [rbp-28h] BYREF
  SIZE_T cb; // [rsp+28h] [rbp-20h]
  char v13; // [rsp+30h] [rbp-18h]
  int v14; // [rsp+31h] [rbp-17h]
  __int16 v15; // [rsp+35h] [rbp-13h]
  char v16; // [rsp+37h] [rbp-11h]

  v11 = 0;
  cb = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
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
0x180061634  mov     rax, rsp
0x180061637  mov     [rax+8], rbx
0x18006163b  mov     [rax+10h], rbp
0x18006163f  mov     [rax+18h], rsi
0x180061643  mov     [rax+20h], rdi
0x180061647  push    r14
0x180061649  sub     rsp, 40h
0x18006164d  and     qword ptr [rax-28h], 0
0x180061652  mov     rsi, rdx
0x180061655  and     qword ptr [rax-20h], 0
0x18006165a  lea     rdx, [rsp+48h+var_28]; struct tson::ansistring_tag *
0x18006165f  mov     byte ptr [rax-18h], 0
0x180061663  mov     rdi, rcx
0x180061666  xor     eax, eax
0x180061668  mov     [rsp+48h+var_17], eax
0x18006166c  mov     [rsp+48h+var_13], ax
0x180061671  mov     [rsp+48h+var_11], al
0x180061675  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18006167a  mov     rcx, [rsp+48h+cb]; cb
0x18006167f  test    rcx, rcx
0x180061682  jz      short loc_1800616EF
0x180061684  call    cs:__imp_CoTaskMemAlloc
0x18006168b  nop     dword ptr [rax+rax+00h]
0x180061690  mov     r14, [rsi]
0x180061693  mov     rbp, rax
0x180061696  test    r14, r14
0x180061699  jz      short loc_1800616C6
0x18006169b  call    cs:__imp_GetLastError
0x1800616a2  nop     dword ptr [rax+rax+00h]
0x1800616a7  mov     rcx, r14; pv
0x1800616aa  mov     ebx, eax
0x1800616ac  call    cs:__imp_CoTaskMemFree
0x1800616b3  nop     dword ptr [rax+rax+00h]
0x1800616b8  mov     ecx, ebx; dwErrCode
0x1800616ba  call    cs:__imp_SetLastError
0x1800616c1  nop     dword ptr [rax+rax+00h]
0x1800616c6  mov     [rsi], rbp
0x1800616c9  test    rbp, rbp
0x1800616cc  jz      short loc_1800616E2
0x1800616ce  lea     rdx, [rsp+48h+var_28]; struct tson::ansistring_tag *
0x1800616d3  mov     [rsp+48h+var_28], rbp
0x1800616d8  mov     rcx, rdi; this
0x1800616db  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x1800616e0  jmp     short loc_180061726
0x1800616e2  cmp     dword ptr [rdi+8], 0
0x1800616e6  jl      short loc_1800616EF
0x1800616e8  mov     dword ptr [rdi+8], 8007000Eh
0x1800616ef  mov     rbp, [rsi]
0x1800616f2  test    rbp, rbp
0x1800616f5  jz      short loc_180061722
0x1800616f7  call    cs:__imp_GetLastError
0x1800616fe  nop     dword ptr [rax+rax+00h]
0x180061703  mov     rcx, rbp; pv
0x180061706  mov     ebx, eax
0x180061708  call    cs:__imp_CoTaskMemFree
0x18006170f  nop     dword ptr [rax+rax+00h]
0x180061714  mov     ecx, ebx; dwErrCode
0x180061716  call    cs:__imp_SetLastError
0x18006171d  nop     dword ptr [rax+rax+00h]
0x180061722  and     qword ptr [rsi], 0
0x180061726  mov     rbx, [rsp+48h+arg_0]
0x18006172b  mov     rax, rdi
0x18006172e  mov     rdi, [rsp+48h+arg_18]
0x180061733  mov     rbp, [rsp+48h+arg_8]
0x180061738  mov     rsi, [rsp+48h+arg_10]
0x18006173d  add     rsp, 40h
0x180061741  pop     r14
0x180061743  retn
```
