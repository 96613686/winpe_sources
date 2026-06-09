# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &> &&)

- ea: `0x180003b7c`
- end: `0x180003ca0`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `292`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180017a34`

## callees

- `0x180003b7c`
- `0x180017904`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003bf6`
- `KERNEL32!GetLastError` at `0x180003c52`
- `KERNEL32!GetLastError` at `0x180003bf6`
- `KERNEL32!GetLastError` at `0x180003c52`
- `KERNEL32!SetLastError` at `0x180003c15`
- `KERNEL32!SetLastError` at `0x180003c71`
- `KERNEL32!SetLastError` at `0x180003c15`
- `KERNEL32!SetLastError` at `0x180003c71`
- `ole32!CoTaskMemFree` at `0x180003c07`
- `ole32!CoTaskMemFree` at `0x180003c63`
- `ole32!CoTaskMemFree` at `0x180003c07`
- `ole32!CoTaskMemFree` at `0x180003c63`
- `ole32!CoTaskMemAlloc` at `0x180003bdf`
- `ole32!CoTaskMemAlloc` at `0x180003bdf`

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
0x180003b7c  mov     r11, rsp
0x180003b7f  mov     [r11+8], rbx
0x180003b83  mov     [r11+10h], rbp
0x180003b87  mov     [r11+18h], rsi
0x180003b8b  mov     [r11+20h], rdi
0x180003b8f  push    r14
0x180003b91  sub     rsp, 40h
0x180003b95  mov     rax, [rdx]
0x180003b98  mov     rdi, rcx
0x180003b9b  and     qword ptr [r11-28h], 0
0x180003ba0  and     qword ptr [r11-20h], 0
0x180003ba5  mov     r8b, [rdx+8]
0x180003ba9  mov     [rcx+10h], rax
0x180003bad  xor     eax, eax
0x180003baf  mov     [rcx+18h], r8b
0x180003bb3  mov     rsi, [rdx+10h]
0x180003bb7  lea     rdx, [r11-28h]; struct tson::string_tag *
0x180003bbb  mov     [rsp+48h+var_17], eax
0x180003bbf  mov     [rsp+48h+var_13], ax
0x180003bc4  mov     [rsp+48h+var_11], al
0x180003bc8  mov     [rsp+48h+var_18], 0
0x180003bcd  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x180003bd2  mov     rcx, [rsp+48h+var_20]
0x180003bd7  test    rcx, rcx
0x180003bda  jz      short loc_180003C4A
0x180003bdc  add     rcx, rcx; cb
0x180003bdf  call    cs:__imp_CoTaskMemAlloc
0x180003be6  nop     dword ptr [rax+rax+00h]
0x180003beb  mov     r14, [rsi]
0x180003bee  mov     rbp, rax
0x180003bf1  test    r14, r14
0x180003bf4  jz      short loc_180003C21
0x180003bf6  call    cs:__imp_GetLastError
0x180003bfd  nop     dword ptr [rax+rax+00h]
0x180003c02  mov     rcx, r14; pv
0x180003c05  mov     ebx, eax
0x180003c07  call    cs:__imp_CoTaskMemFree
0x180003c0e  nop     dword ptr [rax+rax+00h]
0x180003c13  mov     ecx, ebx; dwErrCode
0x180003c15  call    cs:__imp_SetLastError
0x180003c1c  nop     dword ptr [rax+rax+00h]
0x180003c21  mov     [rsi], rbp
0x180003c24  test    rbp, rbp
0x180003c27  jz      short loc_180003C3D
0x180003c29  lea     rdx, [rsp+48h+var_28]; struct tson::string_tag *
0x180003c2e  mov     [rsp+48h+var_28], rbp
0x180003c33  mov     rcx, rdi; this
0x180003c36  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x180003c3b  jmp     short loc_180003C81
0x180003c3d  cmp     dword ptr [rdi+8], 0
0x180003c41  jl      short loc_180003C4A
0x180003c43  mov     dword ptr [rdi+8], 8007000Eh
0x180003c4a  mov     rbp, [rsi]
0x180003c4d  test    rbp, rbp
0x180003c50  jz      short loc_180003C7D
0x180003c52  call    cs:__imp_GetLastError
0x180003c59  nop     dword ptr [rax+rax+00h]
0x180003c5e  mov     rcx, rbp; pv
0x180003c61  mov     ebx, eax
0x180003c63  call    cs:__imp_CoTaskMemFree
0x180003c6a  nop     dword ptr [rax+rax+00h]
0x180003c6f  mov     ecx, ebx; dwErrCode
0x180003c71  call    cs:__imp_SetLastError
0x180003c78  nop     dword ptr [rax+rax+00h]
0x180003c7d  and     qword ptr [rsi], 0
0x180003c81  mov     rbx, [rsp+48h+arg_0]
0x180003c86  mov     rax, rdi
0x180003c89  mov     rdi, [rsp+48h+arg_18]
0x180003c8e  mov     rbp, [rsp+48h+arg_8]
0x180003c93  mov     rsi, [rsp+48h+arg_10]
0x180003c98  add     rsp, 40h
0x180003c9c  pop     r14
0x180003c9e  retn
```
