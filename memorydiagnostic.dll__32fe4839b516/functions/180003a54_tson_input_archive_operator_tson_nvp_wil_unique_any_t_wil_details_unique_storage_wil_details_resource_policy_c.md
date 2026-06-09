# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)

- ea: `0x180003a54`
- end: `0x180003b75`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `289`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180017a34`

## callees

- `0x180003a54`
- `0x1800177e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003acb`
- `KERNEL32!GetLastError` at `0x180003b27`
- `KERNEL32!GetLastError` at `0x180003acb`
- `KERNEL32!GetLastError` at `0x180003b27`
- `KERNEL32!SetLastError` at `0x180003aea`
- `KERNEL32!SetLastError` at `0x180003b46`
- `KERNEL32!SetLastError` at `0x180003aea`
- `KERNEL32!SetLastError` at `0x180003b46`
- `ole32!CoTaskMemFree` at `0x180003adc`
- `ole32!CoTaskMemFree` at `0x180003b38`
- `ole32!CoTaskMemFree` at `0x180003adc`
- `ole32!CoTaskMemFree` at `0x180003b38`
- `ole32!CoTaskMemAlloc` at `0x180003ab4`
- `ole32!CoTaskMemAlloc` at `0x180003ab4`

## pseudocode

```c
tson::input_archive *__fastcall tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(
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
  SIZE_T cb; // [rsp+28h] [rbp-20h]
  char v15; // [rsp+30h] [rbp-18h]
  int v16; // [rsp+31h] [rbp-17h]
  __int16 v17; // [rsp+35h] [rbp-13h]
  char v18; // [rsp+37h] [rbp-11h]

  v2 = *a2;
  v13 = 0;
  cb = 0;
  v4 = *((_BYTE *)a2 + 8);
  *((_QWORD *)this + 2) = v2;
  *((_BYTE *)this + 24) = v4;
  v5 = (void **)a2[2];
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v15 = 0;
  tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v13);
  if ( cb )
  {
    v6 = CoTaskMemAlloc(cb);
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
      tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v13);
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
0x180003a54  mov     r11, rsp
0x180003a57  mov     [r11+8], rbx
0x180003a5b  mov     [r11+10h], rbp
0x180003a5f  mov     [r11+18h], rsi
0x180003a63  mov     [r11+20h], rdi
0x180003a67  push    r14
0x180003a69  sub     rsp, 40h
0x180003a6d  mov     rax, [rdx]
0x180003a70  mov     rdi, rcx
0x180003a73  and     qword ptr [r11-28h], 0
0x180003a78  and     qword ptr [r11-20h], 0
0x180003a7d  mov     r8b, [rdx+8]
0x180003a81  mov     [rcx+10h], rax
0x180003a85  xor     eax, eax
0x180003a87  mov     [rcx+18h], r8b
0x180003a8b  mov     rsi, [rdx+10h]
0x180003a8f  lea     rdx, [r11-28h]; struct tson::ansistring_tag *
0x180003a93  mov     [rsp+48h+var_17], eax
0x180003a97  mov     [rsp+48h+var_13], ax
0x180003a9c  mov     [rsp+48h+var_11], al
0x180003aa0  mov     [rsp+48h+var_18], 0
0x180003aa5  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x180003aaa  mov     rcx, [rsp+48h+cb]; cb
0x180003aaf  test    rcx, rcx
0x180003ab2  jz      short loc_180003B1F
0x180003ab4  call    cs:__imp_CoTaskMemAlloc
0x180003abb  nop     dword ptr [rax+rax+00h]
0x180003ac0  mov     r14, [rsi]
0x180003ac3  mov     rbp, rax
0x180003ac6  test    r14, r14
0x180003ac9  jz      short loc_180003AF6
0x180003acb  call    cs:__imp_GetLastError
0x180003ad2  nop     dword ptr [rax+rax+00h]
0x180003ad7  mov     rcx, r14; pv
0x180003ada  mov     ebx, eax
0x180003adc  call    cs:__imp_CoTaskMemFree
0x180003ae3  nop     dword ptr [rax+rax+00h]
0x180003ae8  mov     ecx, ebx; dwErrCode
0x180003aea  call    cs:__imp_SetLastError
0x180003af1  nop     dword ptr [rax+rax+00h]
0x180003af6  mov     [rsi], rbp
0x180003af9  test    rbp, rbp
0x180003afc  jz      short loc_180003B12
0x180003afe  lea     rdx, [rsp+48h+var_28]; struct tson::ansistring_tag *
0x180003b03  mov     [rsp+48h+var_28], rbp
0x180003b08  mov     rcx, rdi; this
0x180003b0b  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x180003b10  jmp     short loc_180003B56
0x180003b12  cmp     dword ptr [rdi+8], 0
0x180003b16  jl      short loc_180003B1F
0x180003b18  mov     dword ptr [rdi+8], 8007000Eh
0x180003b1f  mov     rbp, [rsi]
0x180003b22  test    rbp, rbp
0x180003b25  jz      short loc_180003B52
0x180003b27  call    cs:__imp_GetLastError
0x180003b2e  nop     dword ptr [rax+rax+00h]
0x180003b33  mov     rcx, rbp; pv
0x180003b36  mov     ebx, eax
0x180003b38  call    cs:__imp_CoTaskMemFree
0x180003b3f  nop     dword ptr [rax+rax+00h]
0x180003b44  mov     ecx, ebx; dwErrCode
0x180003b46  call    cs:__imp_SetLastError
0x180003b4d  nop     dword ptr [rax+rax+00h]
0x180003b52  and     qword ptr [rsi], 0
0x180003b56  mov     rbx, [rsp+48h+arg_0]
0x180003b5b  mov     rax, rdi
0x180003b5e  mov     rdi, [rsp+48h+arg_18]
0x180003b63  mov     rbp, [rsp+48h+arg_8]
0x180003b68  mov     rsi, [rsp+48h+arg_10]
0x180003b6d  add     rsp, 40h
0x180003b71  pop     r14
0x180003b73  retn
```
