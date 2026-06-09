# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &> &&)

- ea: `0x1800633f4`
- end: `0x180063506`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `274`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006b3b0`

## callees

- `0x1800633f4`
- `0x18006b288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063488`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800634e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063488`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800634e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800634c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800634c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006347a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800634d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006347a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800634d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063452`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063452`

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
0x1800633f4  push    rbx
0x1800633f6  push    rbp
0x1800633f7  push    rsi
0x1800633f8  push    rdi
0x1800633f9  push    r14
0x1800633fb  sub     rsp, 40h
0x1800633ff  mov     rax, [rdx]
0x180063402  mov     rdi, rcx
0x180063405  mov     r8b, [rdx+8]
0x180063409  mov     [rcx+10h], rax
0x18006340d  xor     eax, eax
0x18006340f  mov     [rcx+18h], r8b
0x180063413  mov     rsi, [rdx+10h]
0x180063417  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x18006341c  mov     [rsp+68h+var_37], eax
0x180063420  mov     [rsp+68h+var_33], ax
0x180063425  mov     [rsp+68h+var_31], al
0x180063429  mov     [rsp+68h+var_48], 0
0x180063432  mov     [rsp+68h+var_40], 0
0x18006343b  mov     [rsp+68h+var_38], 0
0x180063440  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x180063445  mov     rcx, [rsp+68h+var_40]
0x18006344a  test    rcx, rcx
0x18006344d  jz      short loc_1800634BD
0x18006344f  add     rcx, rcx; cb
0x180063452  call    cs:__imp_CoTaskMemAlloc
0x180063459  nop     dword ptr [rax+rax+00h]
0x18006345e  mov     r14, [rsi]
0x180063461  mov     rbp, rax
0x180063464  test    r14, r14
0x180063467  jz      short loc_180063494
0x180063469  call    cs:__imp_GetLastError
0x180063470  nop     dword ptr [rax+rax+00h]
0x180063475  mov     rcx, r14; pv
0x180063478  mov     ebx, eax
0x18006347a  call    cs:__imp_CoTaskMemFree
0x180063481  nop     dword ptr [rax+rax+00h]
0x180063486  mov     ecx, ebx; dwErrCode
0x180063488  call    cs:__imp_SetLastError
0x18006348f  nop     dword ptr [rax+rax+00h]
0x180063494  mov     [rsi], rbp
0x180063497  test    rbp, rbp
0x18006349a  jz      short loc_1800634B0
0x18006349c  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x1800634a1  mov     [rsp+68h+var_48], rbp
0x1800634a6  mov     rcx, rdi; this
0x1800634a9  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x1800634ae  jmp     short loc_1800634F7
0x1800634b0  cmp     dword ptr [rdi+8], 0
0x1800634b4  jl      short loc_1800634BD
0x1800634b6  mov     dword ptr [rdi+8], 8007000Eh
0x1800634bd  mov     rbp, [rsi]
0x1800634c0  test    rbp, rbp
0x1800634c3  jz      short loc_1800634F0
0x1800634c5  call    cs:__imp_GetLastError
0x1800634cc  nop     dword ptr [rax+rax+00h]
0x1800634d1  mov     rcx, rbp; pv
0x1800634d4  mov     ebx, eax
0x1800634d6  call    cs:__imp_CoTaskMemFree
0x1800634dd  nop     dword ptr [rax+rax+00h]
0x1800634e2  mov     ecx, ebx; dwErrCode
0x1800634e4  call    cs:__imp_SetLastError
0x1800634eb  nop     dword ptr [rax+rax+00h]
0x1800634f0  mov     qword ptr [rsi], 0
0x1800634f7  mov     rax, rdi
0x1800634fa  add     rsp, 40h
0x1800634fe  pop     r14
0x180063500  pop     rdi
0x180063501  pop     rsi
0x180063502  pop     rbp
0x180063503  pop     rbx
0x180063504  retn
```
