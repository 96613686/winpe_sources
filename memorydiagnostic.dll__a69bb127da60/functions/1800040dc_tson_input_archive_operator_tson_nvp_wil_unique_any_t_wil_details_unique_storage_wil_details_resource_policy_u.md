# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &> &&)

- ea: `0x1800040dc`
- end: `0x1800041c3`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `231`
- prototype: `tson::input_archive *__fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180016dec`

## callees

- `0x1800040dc`
- `0x180016cc4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000414b`
- `KERNEL32!GetLastError` at `0x180004195`
- `KERNEL32!GetLastError` at `0x18000414b`
- `KERNEL32!GetLastError` at `0x180004195`
- `KERNEL32!SetLastError` at `0x18000415e`
- `KERNEL32!SetLastError` at `0x1800041a8`
- `KERNEL32!SetLastError` at `0x18000415e`
- `KERNEL32!SetLastError` at `0x1800041a8`
- `ole32!CoTaskMemAlloc` at `0x18000413a`
- `ole32!CoTaskMemAlloc` at `0x18000413a`
- `ole32!CoTaskMemFree` at `0x180004156`
- `ole32!CoTaskMemFree` at `0x1800041a0`
- `ole32!CoTaskMemFree` at `0x180004156`
- `ole32!CoTaskMemFree` at `0x1800041a0`

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
0x1800040dc  push    rbx
0x1800040de  push    rbp
0x1800040df  push    rsi
0x1800040e0  push    rdi
0x1800040e1  push    r14
0x1800040e3  sub     rsp, 40h
0x1800040e7  mov     rax, [rdx]
0x1800040ea  mov     rdi, rcx
0x1800040ed  mov     r8b, [rdx+8]
0x1800040f1  mov     [rcx+10h], rax
0x1800040f5  xor     eax, eax
0x1800040f7  mov     [rcx+18h], r8b
0x1800040fb  mov     rsi, [rdx+10h]
0x1800040ff  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x180004104  mov     [rsp+68h+var_37], eax
0x180004108  mov     [rsp+68h+var_33], ax
0x18000410d  mov     [rsp+68h+var_31], al
0x180004111  mov     [rsp+68h+var_48], 0
0x18000411a  mov     [rsp+68h+var_40], 0
0x180004123  mov     [rsp+68h+var_38], 0
0x180004128  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x18000412d  mov     rcx, [rsp+68h+var_40]
0x180004132  test    rcx, rcx
0x180004135  jz      short loc_18000418D
0x180004137  add     rcx, rcx; cb
0x18000413a  call    cs:__imp_CoTaskMemAlloc
0x180004140  mov     r14, [rsi]
0x180004143  mov     rbp, rax
0x180004146  test    r14, r14
0x180004149  jz      short loc_180004164
0x18000414b  call    cs:__imp_GetLastError
0x180004151  mov     rcx, r14; pv
0x180004154  mov     ebx, eax
0x180004156  call    cs:__imp_CoTaskMemFree
0x18000415c  mov     ecx, ebx; dwErrCode
0x18000415e  call    cs:__imp_SetLastError
0x180004164  mov     [rsi], rbp
0x180004167  test    rbp, rbp
0x18000416a  jz      short loc_180004180
0x18000416c  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x180004171  mov     [rsp+68h+var_48], rbp
0x180004176  mov     rcx, rdi; this
0x180004179  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x18000417e  jmp     short loc_1800041B5
0x180004180  cmp     dword ptr [rdi+8], 0
0x180004184  jl      short loc_18000418D
0x180004186  mov     dword ptr [rdi+8], 8007000Eh
0x18000418d  mov     rbp, [rsi]
0x180004190  test    rbp, rbp
0x180004193  jz      short loc_1800041AE
0x180004195  call    cs:__imp_GetLastError
0x18000419b  mov     rcx, rbp; pv
0x18000419e  mov     ebx, eax
0x1800041a0  call    cs:__imp_CoTaskMemFree
0x1800041a6  mov     ecx, ebx; dwErrCode
0x1800041a8  call    cs:__imp_SetLastError
0x1800041ae  mov     qword ptr [rsi], 0
0x1800041b5  mov     rax, rdi
0x1800041b8  add     rsp, 40h
0x1800041bc  pop     r14
0x1800041be  pop     rdi
0x1800041bf  pop     rsi
0x1800041c0  pop     rbp
0x1800041c1  pop     rbx
0x1800041c2  retn
```
