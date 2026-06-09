# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x10070733`
- end: `0x10070803`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CGJPBG_NPA_KPA_N@Z`
- size: `208`
- prototype: `HRESULT __userpurge@<eax>(const wchar_t *name@<ecx>, bool value, unsigned __int64 *name@<ecx>, bool *is64Bit)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1006d35f`

## callees

- `0x1005536b`
- `0x1006b510`
- `0x1006d864`
- `0x1006e91e`
- `0x1006ffbc`
- `0x1006ffd8`
- `0x100703a0`
- `0x10070733`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x10070784`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x10070784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10070792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10070792`

## pseudocode

```c
HRESULT __userpurge wil::details_abi::SemaphoreValue::TryGetValueInternal@<eax>(
        const wchar_t *a1@<ecx>,
        unsigned __int64 *value,
        bool *is64Bit,
        unsigned __int64 *a4,
        bool *a5)
{
  HANDLE v5; // eax
  wil::details::in1diag3 *v6; // ecx
  HRESULT LastError; // esi
  HRESULT ValueFromSemaphore; // eax
  wil::details::in1diag3 *v9; // ecx
  unsigned int v11; // [esp+0h] [ebp-228h]
  void *v12; // [esp+0h] [ebp-228h]
  const unsigned __int16 *v13; // [esp+4h] [ebp-224h]
  const char *v14; // [esp+4h] [ebp-224h]
  const char *v15; // [esp+8h] [ebp-220h]
  int countLow; // [esp+10h] [ebp-218h] BYREF
  wil::unique_any_t<wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__stdcall*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned int,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > semaphoreLow; // [esp+14h] [ebp-214h] BYREF
  wchar_t localName[262]; // [esp+18h] [ebp-210h] BYREF

  *(_DWORD *)value = 0;
  *((_DWORD *)value + 1) = 0;
  StringCchCopyW(localName, 0x104u, a1);
  StringCchCatW(L"_p0", v11, v13);
  v5 = OpenSemaphoreW(0x1F0003u, 0, localName);
  semaphoreLow.m_ptr = v5;
  if ( v5 )
  {
    countLow = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &countLow);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(v9, ValueFromSemaphore, (unsigned int)v12, v14, v15);
      goto LABEL_8;
    }
    *value = countLow;
LABEL_7:
    LastError = 0;
    goto LABEL_8;
  }
  if ( GetLastError() == 2 )
    goto LABEL_7;
  LastError = wil::details::in1diag3::Return_GetLastError(v6, v12, (unsigned int)v14, v15);
LABEL_8:
  __1__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAE_XZ(&semaphoreLow);
  return LastError;
}

```

## disassembly

```asm
0x10070733  mov     edi, edi
0x10070735  push    ebp
0x10070736  mov     ebp, esp
0x10070738  and     esp, 0FFFFFFF8h
0x1007073b  sub     esp, 21Ch
0x10070741  mov     eax, ___security_cookie
0x10070746  xor     eax, esp
0x10070748  mov     [esp+21Ch+var_4], eax
0x1007074f  push    ebx
0x10070750  push    esi
0x10070751  push    edi
0x10070752  mov     edi, [ebp+value]
0x10070755  xor     ebx, ebx
0x10070757  push    name; pszSrc
0x10070758  mov     edx, 104h; cchDest
0x1007075d  lea     name, [esp+22Ch+localName]; pszDest
0x10070761  mov     [edi], ebx
0x10070763  mov     [edi+4], ebx
0x10070766  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x1007076b  push    offset aP0; "_p0"
0x10070770  lea     name, [esp+22Ch+localName]; pszDest
0x10070774  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x10070779  lea     eax, [esp+228h+localName]
0x1007077d  push    eax; lpName
0x1007077e  push    ebx; bInheritHandle
0x1007077f  push    1F0003h; dwDesiredAccess
0x10070784  call    ds:__imp__OpenSemaphoreW@12; OpenSemaphoreW(x,x,x)
0x1007078a  mov     [esp+228h+semaphoreLow.m_ptr], eax
0x1007078e  test    eax, eax
0x10070790  jnz     short loc_100707AF
0x10070792  call    ds:__imp__GetLastError@0; GetLastError()
0x10070798  cmp     eax, 2
0x1007079b  jz      short loc_100707DF
0x1007079d  push    name
0x1007079e  mov     name, [ebp+4]; callerReturnAddress
0x100707a1  mov     edx, 0D0h; lineNumber
0x100707a6  call    ?Return_GetLastError@in1diag3@details@wil@@YGJPAXIPBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x100707ab  mov     esi, eax
0x100707ad  jmp     short loc_100707E1
0x100707af  lea     edx, [esp+228h+countLow]; count
0x100707b3  mov     [esp+228h+countLow], ebx
0x100707b7  mov     name, eax; semaphore
0x100707b9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CGJPAXPAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x100707be  mov     esi, eax
0x100707c0  test    esi, esi
0x100707c2  jns     short loc_100707D5
0x100707c4  push    esi
0x100707c5  push    name; hr
0x100707c6  mov     name, [ebp+4]; callerReturnAddress
0x100707c9  mov     edx, 0D6h; lineNumber
0x100707ce  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x100707d3  jmp     short loc_100707E1
0x100707d5  mov     eax, [esp+228h+countLow]
0x100707d9  cdq
0x100707da  mov     [edi], eax
0x100707dc  mov     [edi+4], edx
0x100707df  mov     esi, ebx
0x100707e1  lea     name, [esp+228h+semaphoreLow]; this
0x100707e5  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x100707ea  mov     name, [esp+228h+var_4]
0x100707f1  mov     eax, esi
0x100707f3  pop     edi
0x100707f4  pop     esi
0x100707f5  pop     ebx
0x100707f6  xor     name, esp; cookie
0x100707f8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100707fd  mov     esp, ebp
0x100707ff  pop     ebp
0x10070800  retn    8
```
