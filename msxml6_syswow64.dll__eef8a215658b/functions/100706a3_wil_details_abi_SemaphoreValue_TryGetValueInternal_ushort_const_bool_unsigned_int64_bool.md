# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x100706a3`
- end: `0x10070773`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CGJPBG_NPA_KPA_N@Z`
- size: `208`
- prototype: `HRESULT __userpurge@<eax>(const wchar_t *name@<ecx>, bool value, unsigned __int64 *name@<ecx>, bool *is64Bit)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1006d2cf`

## callees

- `0x100552db`
- `0x1006b470`
- `0x1006d7d4`
- `0x1006e88e`
- `0x1006ff2c`
- `0x1006ff48`
- `0x10070310`
- `0x100706a3`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x100706f4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x100706f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10070702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10070702`

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
0x100706a3  mov     edi, edi
0x100706a5  push    ebp
0x100706a6  mov     ebp, esp
0x100706a8  and     esp, 0FFFFFFF8h
0x100706ab  sub     esp, 21Ch
0x100706b1  mov     eax, ___security_cookie
0x100706b6  xor     eax, esp
0x100706b8  mov     [esp+21Ch+var_4], eax
0x100706bf  push    ebx
0x100706c0  push    esi
0x100706c1  push    edi
0x100706c2  mov     edi, [ebp+value]
0x100706c5  xor     ebx, ebx
0x100706c7  push    name; pszSrc
0x100706c8  mov     edx, 104h; cchDest
0x100706cd  lea     name, [esp+22Ch+localName]; pszDest
0x100706d1  mov     [edi], ebx
0x100706d3  mov     [edi+4], ebx
0x100706d6  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x100706db  push    offset aP0; "_p0"
0x100706e0  lea     name, [esp+22Ch+localName]; pszDest
0x100706e4  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x100706e9  lea     eax, [esp+228h+localName]
0x100706ed  push    eax; lpName
0x100706ee  push    ebx; bInheritHandle
0x100706ef  push    1F0003h; dwDesiredAccess
0x100706f4  call    ds:__imp__OpenSemaphoreW@12; OpenSemaphoreW(x,x,x)
0x100706fa  mov     [esp+228h+semaphoreLow.m_ptr], eax
0x100706fe  test    eax, eax
0x10070700  jnz     short loc_1007071F
0x10070702  call    ds:__imp__GetLastError@0; GetLastError()
0x10070708  cmp     eax, 2
0x1007070b  jz      short loc_1007074F
0x1007070d  push    name
0x1007070e  mov     name, [ebp+4]; callerReturnAddress
0x10070711  mov     edx, 0D0h; lineNumber
0x10070716  call    ?Return_GetLastError@in1diag3@details@wil@@YGJPAXIPBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1007071b  mov     esi, eax
0x1007071d  jmp     short loc_10070751
0x1007071f  lea     edx, [esp+228h+countLow]; count
0x10070723  mov     [esp+228h+countLow], ebx
0x10070727  mov     name, eax; semaphore
0x10070729  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CGJPAXPAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1007072e  mov     esi, eax
0x10070730  test    esi, esi
0x10070732  jns     short loc_10070745
0x10070734  push    esi
0x10070735  push    name; hr
0x10070736  mov     name, [ebp+4]; callerReturnAddress
0x10070739  mov     edx, 0D6h; lineNumber
0x1007073e  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10070743  jmp     short loc_10070751
0x10070745  mov     eax, [esp+228h+countLow]
0x10070749  cdq
0x1007074a  mov     [edi], eax
0x1007074c  mov     [edi+4], edx
0x1007074f  mov     esi, ebx
0x10070751  lea     name, [esp+228h+semaphoreLow]; this
0x10070755  call    ??1?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAE@XZ
0x1007075a  mov     name, [esp+228h+var_4]
0x10070761  mov     eax, esi
0x10070763  pop     edi
0x10070764  pop     esi
0x10070765  pop     ebx
0x10070766  xor     name, esp; cookie
0x10070768  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1007076d  mov     esp, ebp
0x1007076f  pop     ebp
0x10070770  retn    8
```
