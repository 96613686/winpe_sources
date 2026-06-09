# RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)

- ea: `0x18007999c`
- end: `0x180079bd5`
- name: `?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z`
- size: `569`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *const)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180078c44`
- `0x180078e68`
- `0x180079558`
- `0x1800798b0`
- `0x18007999c`

## callees

- `0x18000949c`
- `0x180016698`
- `0x18001e820`
- `0x1800450e8`
- `0x1800782f8`
- `0x18007952c`
- `0x18007999c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180079b21`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180079b21`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180079b47`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180079b47`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180079a66`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180079a66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079ac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079ac6`

## string_xrefs

- `0x180079a29`: `onecore\base\flighting\common\inc\RegWow64Helpers.h`
- `0x180079ae4`: `onecore\base\flighting\common\inc\RegWow64Helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegWow64Helpers::DeleteTree(HKEY a1, const unsigned __int16 *a2, __int64 a3)
{
  unsigned int v5; // r8d
  int v6; // ebx
  char v7; // r12
  HKEY v8; // r14
  WCHAR *v9; // rbx
  LSTATUS v10; // eax
  signed int v11; // edi
  int v12; // edi
  WCHAR *v14; // rbx
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  int lpReserved; // [rsp+20h] [rbp-38h]
  int lpReserveda; // [rsp+20h] [rbp-38h]
  _QWORD v19[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  DWORD cchName; // [rsp+A0h] [rbp+48h] BYREF
  DWORD cchValueName; // [rsp+A8h] [rbp+50h] BYREF
  WCHAR *v23; // [rsp+B0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+60h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0,
      a3);
    v6 = RegWow64Helpers::OpenKey(a1, a2, v5, 0xF003Fu, &hKey);
    if ( v6 < 0 )
    {
LABEL_29:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return (unsigned int)v6;
    }
    v7 = 1;
    v8 = hKey;
  }
  else
  {
    v8 = a1;
    v7 = 0;
  }
  v9 = (WCHAR *)CoTaskMemAlloc(0x200u);
  v23 = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\RegWow64Helpers.h",
      (const char *)0x8007000ELL,
      lpReserved);
LABEL_28:
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v23);
    goto LABEL_29;
  }
  while ( 1 )
  {
    cchName = 256;
    v10 = RegEnumKeyExW(v8, 0, v9, &cchName, 0, 0, 0, 0);
    v11 = v10;
    if ( v10 == 259 )
      break;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    if ( v11 < 0 )
    {
LABEL_14:
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v23);
      v6 = v11;
      goto LABEL_29;
    }
    v12 = RegWow64Helpers::DeleteTree(v8, v9);
    if ( v12 < 0 )
    {
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v23);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return (unsigned int)v12;
    }
  }
  v14 = (WCHAR *)CoTaskMemAlloc(0x7FFFu);
  v19[0] = v14;
  if ( !v14 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\RegWow64Helpers.h",
      (const char *)0x8007000ELL,
      lpReserveda);
LABEL_27:
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v19);
    goto LABEL_28;
  }
  while ( 1 )
  {
    cchValueName = 0x3FFF;
    v15 = RegEnumValueW(v8, 0, v14, &cchValueName, 0, 0, 0, 0);
    v11 = v15;
    if ( v15 == 259 )
      break;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( v11 >= 0 )
    {
      v16 = RegDeleteValueW(v8, v14);
      v11 = v16;
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      if ( v11 >= 0 )
        continue;
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v19);
    goto LABEL_14;
  }
  if ( v7 )
  {
    v6 = RegWow64Helpers::DeleteKey(a1, a2);
    if ( v6 < 0 )
      goto LABEL_27;
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v19);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v23);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18007999c  push    rbp
0x18007999e  push    rbx
0x18007999f  push    rsi
0x1800799a0  push    rdi
0x1800799a1  push    r12
0x1800799a3  push    r13
0x1800799a5  push    r14
0x1800799a7  push    r15
0x1800799a9  mov     rbp, rsp
0x1800799ac  sub     rsp, 58h
0x1800799b0  mov     rsi, rdx
0x1800799b3  mov     r15, rcx
0x1800799b6  xor     r13d, r13d
0x1800799b9  mov     [rbp+hKey], r13
0x1800799bd  test    rdx, rdx
0x1800799c0  jz      short loc_180079A00
0x1800799c2  cmp     [rdx], r13w
0x1800799c6  jz      short loc_180079A00
0x1800799c8  xor     edx, edx
0x1800799ca  lea     rcx, [rbp+hKey]
0x1800799ce  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800799d3  lea     rax, [rbp+hKey]
0x1800799d7  mov     [rsp+58h+lpReserved], rax; PHKEY
0x1800799dc  mov     r9d, 0F003Fh; unsigned int
0x1800799e2  mov     rdx, rsi; unsigned __int16 *
0x1800799e5  mov     rcx, r15; HKEY
0x1800799e8  call    ?OpenKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKPEAPEAU2@@Z; RegWow64Helpers::OpenKey(HKEY__ * const,ushort const * const,ulong,ulong,HKEY__ * *)
0x1800799ed  mov     ebx, eax
0x1800799ef  test    eax, eax
0x1800799f1  js      loc_180079B98
0x1800799f7  mov     r12b, 1
0x1800799fa  mov     r14, [rbp+hKey]
0x1800799fe  jmp     short loc_180079A06
0x180079a00  mov     r14, r15
0x180079a03  mov     r12b, r13b
0x180079a06  mov     ecx, 200h; cb
0x180079a0b  call    cs:__imp_CoTaskMemAlloc
0x180079a11  mov     rbx, rax
0x180079a14  mov     [rbp+arg_10], rax
0x180079a18  test    rax, rax
0x180079a1b  jnz     short loc_180079A3F
0x180079a1d  mov     rcx, [rbp+40h]; this
0x180079a21  mov     ebx, 8007000Eh
0x180079a26  mov     r9d, ebx; char *
0x180079a29  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\inc\\"...
0x180079a30  mov     edx, 232h; void *
0x180079a35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079a3a  jmp     loc_180079B8E
0x180079a3f  mov     [rbp+cchName], 100h
0x180079a46  mov     [rsp+58h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180079a4b  mov     [rsp+58h+lpcchClass], r13; lpcchClass
0x180079a50  mov     [rsp+58h+lpClass], r13; lpClass
0x180079a55  mov     [rsp+58h+lpReserved], r13; int
0x180079a5a  lea     r9, [rbp+cchName]; lpcchName
0x180079a5e  mov     r8, rbx; lpName
0x180079a61  xor     edx, edx; dwIndex
0x180079a63  mov     rcx, r14; hKey
0x180079a66  call    cs:__imp_RegEnumKeyExW
0x180079a6c  mov     edi, eax
0x180079a6e  cmp     eax, 103h
0x180079a73  jz      short loc_180079AC1
0x180079a75  test    eax, eax
0x180079a77  jle     short loc_180079A82
0x180079a79  movzx   edi, ax
0x180079a7c  or      edi, 80070000h
0x180079a82  test    edi, edi
0x180079a84  js      short loc_180079AB1
0x180079a86  mov     rdx, rbx; unsigned __int16 *
0x180079a89  mov     rcx, r14; HKEY
0x180079a8c  call    ?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)
0x180079a91  mov     edi, eax
0x180079a93  test    eax, eax
0x180079a95  jns     short loc_180079A3F
0x180079a97  lea     rcx, [rbp+arg_10]
0x180079a9b  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180079aa0  nop
0x180079aa1  lea     rcx, [rbp+hKey]
0x180079aa5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180079aaa  mov     eax, edi
0x180079aac  jmp     loc_180079BC4
0x180079ab1  lea     rcx, [rbp+arg_10]
0x180079ab5  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180079aba  mov     ebx, edi
0x180079abc  jmp     loc_180079B98
0x180079ac1  mov     ecx, 7FFFh; cb
0x180079ac6  call    cs:__imp_CoTaskMemAlloc
0x180079acc  mov     rbx, rax
0x180079acf  mov     [rbp+var_18], rax
0x180079ad3  test    rax, rax
0x180079ad6  jnz     short loc_180079AFA
0x180079ad8  mov     rcx, [rbp+40h]; this
0x180079adc  mov     ebx, 8007000Eh
0x180079ae1  mov     r9d, ebx; char *
0x180079ae4  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\inc\\"...
0x180079aeb  mov     edx, 255h; void *
0x180079af0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079af5  jmp     loc_180079B84
0x180079afa  mov     [rbp+cchValueName], 3FFFh
0x180079b01  mov     [rsp+58h+lpftLastWriteTime], r13; lpcbData
0x180079b06  mov     [rsp+58h+lpcchClass], r13; lpData
0x180079b0b  mov     [rsp+58h+lpClass], r13; lpType
0x180079b10  mov     [rsp+58h+lpReserved], r13; lpReserved
0x180079b15  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180079b19  mov     r8, rbx; lpValueName
0x180079b1c  xor     edx, edx; dwIndex
0x180079b1e  mov     rcx, r14; hKey
0x180079b21  call    cs:__imp_RegEnumValueW
0x180079b27  mov     edi, eax
0x180079b29  cmp     eax, 103h
0x180079b2e  jz      short loc_180079B6E
0x180079b30  test    eax, eax
0x180079b32  jle     short loc_180079B3D
0x180079b34  movzx   edi, ax
0x180079b37  or      edi, 80070000h
0x180079b3d  test    edi, edi
0x180079b3f  js      short loc_180079B60
0x180079b41  mov     rdx, rbx; lpValueName
0x180079b44  mov     rcx, r14; hKey
0x180079b47  call    cs:__imp_RegDeleteValueW
0x180079b4d  mov     edi, eax
0x180079b4f  test    eax, eax
0x180079b51  jle     short loc_180079B5C
0x180079b53  movzx   edi, ax
0x180079b56  or      edi, 80070000h
0x180079b5c  test    edi, edi
0x180079b5e  jns     short loc_180079AFA
0x180079b60  lea     rcx, [rbp+var_18]
0x180079b64  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180079b69  jmp     loc_180079AB1
0x180079b6e  test    r12b, r12b
0x180079b71  jz      short loc_180079BA5
0x180079b73  mov     rdx, rsi; unsigned __int16 *
0x180079b76  mov     rcx, r15; HKEY
0x180079b79  call    ?DeleteKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteKey(HKEY__ * const,ushort const * const)
0x180079b7e  mov     ebx, eax
0x180079b80  test    eax, eax
0x180079b82  jns     short loc_180079BA5
0x180079b84  lea     rcx, [rbp+var_18]
0x180079b88  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180079b8d  nop
0x180079b8e  lea     rcx, [rbp+arg_10]
0x180079b92  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180079b97  nop
0x180079b98  lea     rcx, [rbp+hKey]
0x180079b9c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180079ba1  mov     eax, ebx
0x180079ba3  jmp     short loc_180079BC4
0x180079ba5  lea     rcx, [rbp+var_18]
0x180079ba9  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180079bae  nop
0x180079baf  lea     rcx, [rbp+arg_10]
0x180079bb3  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180079bb8  nop
0x180079bb9  lea     rcx, [rbp+hKey]
0x180079bbd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180079bc2  xor     eax, eax
0x180079bc4  add     rsp, 58h
0x180079bc8  pop     r15
0x180079bca  pop     r14
0x180079bcc  pop     r13
0x180079bce  pop     r12
0x180079bd0  pop     rdi
0x180079bd1  pop     rsi
0x180079bd2  pop     rbx
0x180079bd3  pop     rbp
0x180079bd4  retn
```
