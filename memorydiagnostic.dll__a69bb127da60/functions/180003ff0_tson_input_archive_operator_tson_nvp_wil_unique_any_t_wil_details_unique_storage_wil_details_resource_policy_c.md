# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)

- ea: `0x180003ff0`
- end: `0x1800040d4`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `228`
- prototype: `tson::input_archive *__fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180016dec`

## callees

- `0x180003ff0`
- `0x180016ba4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000405c`
- `KERNEL32!GetLastError` at `0x1800040a6`
- `KERNEL32!GetLastError` at `0x18000405c`
- `KERNEL32!GetLastError` at `0x1800040a6`
- `KERNEL32!SetLastError` at `0x18000406f`
- `KERNEL32!SetLastError` at `0x1800040b9`
- `KERNEL32!SetLastError` at `0x18000406f`
- `KERNEL32!SetLastError` at `0x1800040b9`
- `ole32!CoTaskMemAlloc` at `0x18000404b`
- `ole32!CoTaskMemAlloc` at `0x18000404b`
- `ole32!CoTaskMemFree` at `0x180004067`
- `ole32!CoTaskMemFree` at `0x1800040b1`
- `ole32!CoTaskMemFree` at `0x180004067`
- `ole32!CoTaskMemFree` at `0x1800040b1`

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
0x180003ff0  push    rbx
0x180003ff2  push    rbp
0x180003ff3  push    rsi
0x180003ff4  push    rdi
0x180003ff5  push    r14
0x180003ff7  sub     rsp, 40h
0x180003ffb  mov     rax, [rdx]
0x180003ffe  mov     rdi, rcx
0x180004001  mov     r8b, [rdx+8]
0x180004005  mov     [rcx+10h], rax
0x180004009  xor     eax, eax
0x18000400b  mov     [rcx+18h], r8b
0x18000400f  mov     rsi, [rdx+10h]
0x180004013  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x180004018  mov     [rsp+68h+var_37], eax
0x18000401c  mov     [rsp+68h+var_33], ax
0x180004021  mov     [rsp+68h+var_31], al
0x180004025  mov     [rsp+68h+var_48], 0
0x18000402e  mov     [rsp+68h+cb], 0
0x180004037  mov     [rsp+68h+var_38], 0
0x18000403c  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x180004041  mov     rcx, [rsp+68h+cb]; cb
0x180004046  test    rcx, rcx
0x180004049  jz      short loc_18000409E
0x18000404b  call    cs:__imp_CoTaskMemAlloc
0x180004051  mov     r14, [rsi]
0x180004054  mov     rbp, rax
0x180004057  test    r14, r14
0x18000405a  jz      short loc_180004075
0x18000405c  call    cs:__imp_GetLastError
0x180004062  mov     rcx, r14; pv
0x180004065  mov     ebx, eax
0x180004067  call    cs:__imp_CoTaskMemFree
0x18000406d  mov     ecx, ebx; dwErrCode
0x18000406f  call    cs:__imp_SetLastError
0x180004075  mov     [rsi], rbp
0x180004078  test    rbp, rbp
0x18000407b  jz      short loc_180004091
0x18000407d  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x180004082  mov     [rsp+68h+var_48], rbp
0x180004087  mov     rcx, rdi; this
0x18000408a  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18000408f  jmp     short loc_1800040C6
0x180004091  cmp     dword ptr [rdi+8], 0
0x180004095  jl      short loc_18000409E
0x180004097  mov     dword ptr [rdi+8], 8007000Eh
0x18000409e  mov     rbp, [rsi]
0x1800040a1  test    rbp, rbp
0x1800040a4  jz      short loc_1800040BF
0x1800040a6  call    cs:__imp_GetLastError
0x1800040ac  mov     rcx, rbp; pv
0x1800040af  mov     ebx, eax
0x1800040b1  call    cs:__imp_CoTaskMemFree
0x1800040b7  mov     ecx, ebx; dwErrCode
0x1800040b9  call    cs:__imp_SetLastError
0x1800040bf  mov     qword ptr [rsi], 0
0x1800040c6  mov     rax, rdi
0x1800040c9  add     rsp, 40h
0x1800040cd  pop     r14
0x1800040cf  pop     rdi
0x1800040d0  pop     rsi
0x1800040d1  pop     rbp
0x1800040d2  pop     rbx
0x1800040d3  retn
```
