# AutoImpersonation::SwitchIfNecessary(void *)

- ea: `0x180026f30`
- end: `0x18002701f`
- name: `?SwitchIfNecessary@AutoImpersonation@@QEAAKPEAX@Z`
- size: `239`
- prototype: `unsigned int(AutoImpersonation *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026d90`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc2c`
- `0x18001d284`
- `0x180025560`
- `0x180026f30`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f88`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180026f7a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180026f7a`

## string_xrefs

- `0x180026fde`: `Handle Impersonation -  failed, object already did impersonation!`
- `0x180026f94`: `Handle Impersonation - Failed to impersonate the token - %d`
- `0x180026fa6`: `AutoImpersonation::SwitchIfNecessary`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AutoImpersonation::SwitchIfNecessary(AutoImpersonation *this, void *a2)
{
  DWORD LastError; // edi
  DWORD v6; // [rsp+28h] [rbp-C0h]
  __int64 v7; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+60h] [rbp-88h] BYREF

  if ( *(_QWORD *)this != -1 || *((_BYTE *)this + 8) )
  {
    std::wstring::wstring(v8, L"Handle Impersonation -  failed, object already did impersonation!");
    v7 = 5023;
    cxl::Exception::Exception(pExceptionObject, &v7, v8);
    throw (cxl::Exception *)pExceptionObject;
  }
  ObtainThreadTokenIfExists((PHANDLE)this);
  LastError = 0;
  if ( a2 != (void *)-1LL )
  {
    *((_BYTE *)this + 8) = 1;
    if ( !ImpersonateLoggedOnUser(a2) )
    {
      *((_BYTE *)this + 8) = 0;
      LastError = GetLastError();
      v6 = LastError;
      TraceMsg(
        2,
        0,
        L"AutoImpersonation::SwitchIfNecessary",
        8718,
        L"Handle Impersonation - Failed to impersonate the token - %d",
        v6);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180026f30  mov     [rsp+arg_10], rbx
0x180026f35  mov     [rsp+arg_18], rsi
0x180026f3a  push    rdi
0x180026f3b  sub     rsp, 0E0h
0x180026f42  mov     rax, cs:__security_cookie
0x180026f49  xor     rax, rsp
0x180026f4c  mov     [rsp+0E8h+var_18], rax
0x180026f54  mov     rsi, rdx
0x180026f57  mov     rbx, rcx
0x180026f5a  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180026f5e  jnz     short loc_180026FDE
0x180026f60  cmp     byte ptr [rcx+8], 0
0x180026f64  jnz     short loc_180026FDE
0x180026f66  call    ?ObtainThreadTokenIfExists@@YAKPEAPEAX@Z; ObtainThreadTokenIfExists(void * *)
0x180026f6b  xor     edi, edi
0x180026f6d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180026f71  jz      short loc_180026FB7
0x180026f73  mov     byte ptr [rbx+8], 1
0x180026f77  mov     rcx, rsi; hToken
0x180026f7a  call    cs:__imp_ImpersonateLoggedOnUser
0x180026f80  test    eax, eax
0x180026f82  jnz     short loc_180026FB7
0x180026f84  mov     [rbx+8], dil
0x180026f88  call    cs:__imp_GetLastError
0x180026f8e  mov     edi, eax
0x180026f90  mov     [rsp+0E8h+var_C0], eax
0x180026f94  lea     rax, aHandleImperson_2; "Handle Impersonation - Failed to impers"...
0x180026f9b  mov     [rsp+0E8h+var_C8], rax
0x180026fa0  mov     r9d, 220Eh
0x180026fa6  lea     r8, aAutoimpersonat; "AutoImpersonation::SwitchIfNecessary"
0x180026fad  xor     edx, edx
0x180026faf  lea     ecx, [rdx+2]
0x180026fb2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180026fb7  mov     eax, edi
0x180026fb9  mov     rcx, [rsp+0E8h+var_18]
0x180026fc1  xor     rcx, rsp; StackCookie
0x180026fc4  call    __security_check_cookie
0x180026fc9  lea     r11, [rsp+0E8h+var_8]
0x180026fd1  mov     rbx, [r11+20h]
0x180026fd5  mov     rsi, [r11+28h]
0x180026fd9  mov     rsp, r11
0x180026fdc  pop     rdi
0x180026fdd  retn
0x180026fde  lea     rdx, aHandleImperson_0; "Handle Impersonation -  failed, object "...
0x180026fe5  lea     rcx, [rsp+0E8h+var_B0]
0x180026fea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180026fef  nop
0x180026ff0  mov     [rsp+0E8h+var_B8], 139Fh
0x180026ff9  lea     r8, [rsp+0E8h+var_B0]
0x180026ffe  lea     rdx, [rsp+0E8h+var_B8]
0x180027003  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180027008  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18002700d  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180027014  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180027019  call    _CxxThrowException_0
```
