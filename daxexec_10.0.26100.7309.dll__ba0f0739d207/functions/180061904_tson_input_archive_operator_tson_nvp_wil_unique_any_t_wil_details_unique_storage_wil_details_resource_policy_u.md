# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &> &&)

- ea: `0x180061904`
- end: `0x180061a28`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `292`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006991c`

## callees

- `0x180061904`
- `0x1800697ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006197e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800619da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006197e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800619da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006199d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800619f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006199d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800619f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006198f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800619eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006198f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800619eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061967`

## pseudocode

```c
tson::input_archive *__fastcall tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &>>(
        tson::input_archive *this,
        __int64 *a2)
{
  __int64 v2; // rax
  char v4; // r8
  void **v5; // rsi
  LPVOID v6; // rax
  void *v7; // r14
  void *v8; // rbp
  DWORD LastError; // ebx
  void *v10; // rbp
  DWORD v11; // ebx
  void *v13; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+28h] [rbp-20h]
  char v15; // [rsp+30h] [rbp-18h]
  int v16; // [rsp+31h] [rbp-17h]
  __int16 v17; // [rsp+35h] [rbp-13h]
  char v18; // [rsp+37h] [rbp-11h]

  v2 = *a2;
  v13 = 0;
  v14 = 0;
  v4 = *((_BYTE *)a2 + 8);
  *((_QWORD *)this + 2) = v2;
  *((_BYTE *)this + 24) = v4;
  v5 = (void **)a2[2];
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v15 = 0;
  tson::input_archive::loadValue(this, (struct tson::string_tag *)&v13);
  if ( v14 )
  {
    v6 = CoTaskMemAlloc(2 * v14);
    v7 = *v5;
    v8 = v6;
    if ( *v5 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v7);
      SetLastError(LastError);
    }
    *v5 = v8;
    if ( v8 )
    {
      v13 = v8;
      tson::input_archive::loadValue(this, (struct tson::string_tag *)&v13);
      return this;
    }
    if ( *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147024882;
  }
  v10 = *v5;
  if ( *v5 )
  {
    v11 = GetLastError();
    CoTaskMemFree(v10);
    SetLastError(v11);
  }
  *v5 = 0;
  return this;
}

```

## disassembly

```asm
0x180061904  mov     r11, rsp
0x180061907  mov     [r11+8], rbx
0x18006190b  mov     [r11+10h], rbp
0x18006190f  mov     [r11+18h], rsi
0x180061913  mov     [r11+20h], rdi
0x180061917  push    r14
0x180061919  sub     rsp, 40h
0x18006191d  mov     rax, [rdx]
0x180061920  mov     rdi, rcx
0x180061923  and     qword ptr [r11-28h], 0
0x180061928  and     qword ptr [r11-20h], 0
0x18006192d  mov     r8b, [rdx+8]
0x180061931  mov     [rcx+10h], rax
0x180061935  xor     eax, eax
0x180061937  mov     [rcx+18h], r8b
0x18006193b  mov     rsi, [rdx+10h]
0x18006193f  lea     rdx, [r11-28h]; struct tson::string_tag *
0x180061943  mov     [rsp+48h+var_17], eax
0x180061947  mov     [rsp+48h+var_13], ax
0x18006194c  mov     [rsp+48h+var_11], al
0x180061950  mov     [rsp+48h+var_18], 0
0x180061955  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x18006195a  mov     rcx, [rsp+48h+var_20]
0x18006195f  test    rcx, rcx
0x180061962  jz      short loc_1800619D2
0x180061964  add     rcx, rcx; cb
0x180061967  call    cs:__imp_CoTaskMemAlloc
0x18006196e  nop     dword ptr [rax+rax+00h]
0x180061973  mov     r14, [rsi]
0x180061976  mov     rbp, rax
0x180061979  test    r14, r14
0x18006197c  jz      short loc_1800619A9
0x18006197e  call    cs:__imp_GetLastError
0x180061985  nop     dword ptr [rax+rax+00h]
0x18006198a  mov     rcx, r14; pv
0x18006198d  mov     ebx, eax
0x18006198f  call    cs:__imp_CoTaskMemFree
0x180061996  nop     dword ptr [rax+rax+00h]
0x18006199b  mov     ecx, ebx; dwErrCode
0x18006199d  call    cs:__imp_SetLastError
0x1800619a4  nop     dword ptr [rax+rax+00h]
0x1800619a9  mov     [rsi], rbp
0x1800619ac  test    rbp, rbp
0x1800619af  jz      short loc_1800619C5
0x1800619b1  lea     rdx, [rsp+48h+var_28]; struct tson::string_tag *
0x1800619b6  mov     [rsp+48h+var_28], rbp
0x1800619bb  mov     rcx, rdi; this
0x1800619be  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x1800619c3  jmp     short loc_180061A09
0x1800619c5  cmp     dword ptr [rdi+8], 0
0x1800619c9  jl      short loc_1800619D2
0x1800619cb  mov     dword ptr [rdi+8], 8007000Eh
0x1800619d2  mov     rbp, [rsi]
0x1800619d5  test    rbp, rbp
0x1800619d8  jz      short loc_180061A05
0x1800619da  call    cs:__imp_GetLastError
0x1800619e1  nop     dword ptr [rax+rax+00h]
0x1800619e6  mov     rcx, rbp; pv
0x1800619e9  mov     ebx, eax
0x1800619eb  call    cs:__imp_CoTaskMemFree
0x1800619f2  nop     dword ptr [rax+rax+00h]
0x1800619f7  mov     ecx, ebx; dwErrCode
0x1800619f9  call    cs:__imp_SetLastError
0x180061a00  nop     dword ptr [rax+rax+00h]
0x180061a05  and     qword ptr [rsi], 0
0x180061a09  mov     rbx, [rsp+48h+arg_0]
0x180061a0e  mov     rax, rdi
0x180061a11  mov     rdi, [rsp+48h+arg_18]
0x180061a16  mov     rbp, [rsp+48h+arg_8]
0x180061a1b  mov     rsi, [rsp+48h+arg_10]
0x180061a20  add     rsp, 40h
0x180061a24  pop     r14
0x180061a26  retn
```
