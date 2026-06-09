# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000799c`
- end: `0x180007b54`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `HRESULT __fastcall(const wchar_t *name, bool value, unsigned __int64 *name, bool *is64Bit)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007918`

## callees

- `0x180002790`
- `0x1800057c4`
- `0x18000650c`
- `0x1800071d4`
- `0x1800071f4`
- `0x180007714`
- `0x180007808`
- `0x18000799c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007a00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007a9e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007a00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a10`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *name,
        bool value,
        unsigned __int64 *a3,
        bool *is64Bit)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int LastError; // ebx
  HRESULT ValueFromSemaphore; // eax
  unsigned __int64 v9; // rdx
  HANDLE v10; // rax
  HRESULT v11; // eax
  unsigned __int64 v13; // [rsp+20h] [rbp-E0h]
  int countHigh; // [rsp+30h] [rbp-D0h] BYREF
  int countLow; // [rsp+34h] [rbp-CCh] BYREF
  wil::unique_any_t<wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > semaphoreHigh; // [rsp+38h] [rbp-C8h] BYREF
  wil::unique_any_t<wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > semaphoreLow; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR localName[264]; // [rsp+50h] [rbp-B0h] BYREF
  void *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(localName, 0x104u, a3, name, v13);
  StringCchCatW(localName, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, localName);
  semaphoreLow.m_ptr = v6;
  if ( v6 )
  {
    countLow = 0;
    countHigh = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &countLow);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0xD6u, "wil", ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(localName, v9, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, localName);
    semaphoreHigh.m_ptr = v10;
    if ( v10 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &countHigh);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&semaphoreHigh);
        *a3 = countLow | (unsigned __int64)((__int64)countHigh << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, 0xDEu, "wil", v11);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, 0xDCu, "wil");
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&semaphoreHigh);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, 0xD0u, "wil");
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&semaphoreLow);
  return LastError;
}

```

## disassembly

```asm
0x18000799c  mov     [rsp-8+arg_8], rbx
0x1800079a1  mov     [rsp-8+arg_18], rdi
0x1800079a6  push    rbp
0x1800079a7  lea     rbp, [rsp-170h]
0x1800079af  sub     rsp, 270h
0x1800079b6  mov     rax, cs:__security_cookie
0x1800079bd  xor     rax, rsp
0x1800079c0  mov     [rbp+170h+var_10], rax
0x1800079c7  mov     r9, name; pszDest
0x1800079ca  mov     qword ptr [value], 0
0x1800079d1  lea     name, [rsp+270h+localName]; pszDest
0x1800079d6  mov     edx, 104h; cchDest
0x1800079db  mov     rdi, value
0x1800079de  call    StringCopyWorkerW
0x1800079e3  lea     value, aP0; "_p0"
0x1800079ea  lea     name, [rsp+270h+localName]; pszDest
0x1800079ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800079f4  lea     value, [rsp+270h+localName]; lpName
0x1800079f9  xor     edx, edx; bInheritHandle
0x1800079fb  mov     ecx, 1F0003h; dwDesiredAccess
0x180007a00  call    cs:__imp_OpenSemaphoreW
0x180007a06  mov     [rsp+270h+semaphoreLow.m_ptr], rax
0x180007a0b  test    rax, rax
0x180007a0e  jnz     short loc_180007A3E
0x180007a10  call    cs:__imp_GetLastError
0x180007a16  cmp     eax, 2
0x180007a19  jz      loc_180007B22
0x180007a1f  mov     name, [rbp+178h]; callerReturnAddress
0x180007a26  lea     value, aWil; "wil"
0x180007a2d  mov     edx, 0D0h; lineNumber
0x180007a32  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007a37  mov     ebx, eax
0x180007a39  jmp     loc_180007B24
0x180007a3e  lea     rdx, [rsp+270h+countLow]; count
0x180007a43  mov     [rsp+270h+countLow], 0
0x180007a4b  mov     name, rax; semaphore
0x180007a4e  mov     [rsp+270h+countHigh], 0
0x180007a56  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007a5b  mov     ebx, eax
0x180007a5d  test    eax, eax
0x180007a5f  jns     short loc_180007A81
0x180007a61  mov     name, [rbp+178h]; callerReturnAddress
0x180007a68  lea     value, aWil; "wil"
0x180007a6f  mov     r9d, eax; hr
0x180007a72  mov     edx, 0D6h; lineNumber
0x180007a77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a7c  jmp     loc_180007B24
0x180007a81  lea     value, asc_180074568; "h"
0x180007a88  lea     name, [rsp+270h+localName]; pszDest
0x180007a8d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007a92  lea     value, [rsp+270h+localName]; lpName
0x180007a97  xor     edx, edx; bInheritHandle
0x180007a99  mov     ecx, 1F0003h; dwDesiredAccess
0x180007a9e  call    cs:__imp_OpenSemaphoreW
0x180007aa4  mov     [rsp+270h+semaphoreHigh.m_ptr], rax
0x180007aa9  test    rax, rax
0x180007aac  jnz     short loc_180007AD4
0x180007aae  mov     name, [rbp+178h]; callerReturnAddress
0x180007ab5  lea     value, aWil; "wil"
0x180007abc  mov     edx, 0DCh; lineNumber
0x180007ac1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007ac6  mov     ebx, eax
0x180007ac8  lea     name, [rsp+270h+semaphoreHigh]; this
0x180007acd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007ad2  jmp     short loc_180007B24
0x180007ad4  lea     rdx, [rsp+270h+countHigh]; count
0x180007ad9  mov     name, rax; semaphore
0x180007adc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007ae1  mov     ebx, eax
0x180007ae3  test    eax, eax
0x180007ae5  jns     short loc_180007B04
0x180007ae7  mov     name, [rbp+178h]; callerReturnAddress
0x180007aee  lea     value, aWil; "wil"
0x180007af5  mov     r9d, eax; hr
0x180007af8  mov     edx, 0DEh; lineNumber
0x180007afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b02  jmp     short loc_180007AC8
0x180007b04  lea     name, [rsp+270h+semaphoreHigh]; this
0x180007b09  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007b0e  movsxd  name, [rsp+270h+countHigh]
0x180007b13  movsxd  rax, [rsp+270h+countLow]
0x180007b18  shl     name, 1Fh
0x180007b1c  or      name, rax
0x180007b1f  mov     [rdi], name
0x180007b22  xor     ebx, ebx
0x180007b24  lea     name, [rsp+270h+semaphoreLow]; this
0x180007b29  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007b2e  mov     eax, ebx
0x180007b30  mov     name, [rbp+170h+var_10]
0x180007b37  xor     name, rsp; StackCookie
0x180007b3a  call    __security_check_cookie
0x180007b3f  lea     r11, [rsp+270h+var_s0]
0x180007b47  mov     rbx, [r11+18h]
0x180007b4b  mov     rdi, [r11+28h]
0x180007b4f  mov     rsp, r11
0x180007b52  pop     rbp
0x180007b53  retn
```
