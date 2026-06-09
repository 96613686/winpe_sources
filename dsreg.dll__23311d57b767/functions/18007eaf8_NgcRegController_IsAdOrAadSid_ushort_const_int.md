# NgcRegController::IsAdOrAadSid(ushort const *,int *)

- ea: `0x18007eaf8`
- end: `0x18007ec25`
- name: `?IsAdOrAadSid@NgcRegController@@CAJPEBGPEAH@Z`
- size: `301`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029e68`

## callees

- `0x1800084f4`
- `0x1800307c4`
- `0x18007eaf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eb94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eb94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007ec12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007ec12`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007eb8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007eb8a`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18007ebd6`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18007ebd6`

## string_xrefs

- `0x18007eb1b`: `pcszSid`
- `0x18007eb3a`: `pcszSid`
- `0x18007eb57`: `isAdOrAadSid`
- `0x18007eb76`: `isAdOrAadSid`
- `0x18007eb27`: `NgcRegController::IsAdOrAadSid`
- `0x18007eb41`: `NgcRegController::IsAdOrAadSid`
- `0x18007eb63`: `NgcRegController::IsAdOrAadSid`
- `0x18007ebb7`: `NgcRegController::IsAdOrAadSid`
- `0x18007ebad`: `ConvertStringSidToSid`

## pseudocode

```c
__int64 __fastcall NgcRegController::IsAdOrAadSid(const unsigned __int16 *a1, int *a2)
{
  int v3; // ebx
  const unsigned __int16 *v4; // rdx
  signed int LastError; // eax
  const wchar_t *v6; // r8
  int v7; // eax
  int v9; // [rsp+30h] [rbp+8h] BYREF
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  Sid = 0;
  v9 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcRegController::IsAdOrAadSid", L"pcszSid");
    v4 = L"pcszSid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"NgcRegController::IsAdOrAadSid", v4);
    goto LABEL_17;
  }
  if ( !a2 )
  {
    v3 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcRegController::IsAdOrAadSid", L"isAdOrAadSid");
    v4 = L"isAdOrAadSid";
    goto LABEL_3;
  }
  *a2 = 0;
  if ( !ConvertStringSidToSidW(a1, &Sid) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
    {
      v6 = L"ConvertStringSidToSid";
LABEL_11:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"NgcRegController::IsAdOrAadSid",
        v6,
        (unsigned int)v3);
      goto LABEL_17;
    }
  }
  v7 = LsaLookupUserAccountType(Sid, &v9);
  v3 = v7 | 0x10000000;
  if ( v7 < 0 )
  {
    v6 = L"LsaLookupUserAccountType";
    goto LABEL_11;
  }
  if ( ((v9 - 2) & 0xFFFFFFFC) == 0 && v9 != 4 )
    *a2 = 1;
LABEL_17:
  if ( Sid )
    LocalFree(Sid);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18007eaf8  mov     [rsp+arg_8], rbx
0x18007eafd  push    rdi
0x18007eafe  sub     rsp, 20h
0x18007eb02  mov     [rsp+28h+Sid], 0
0x18007eb0b  mov     rdi, rdx
0x18007eb0e  mov     [rsp+28h+arg_0], 0
0x18007eb16  test    rcx, rcx
0x18007eb19  jnz     short loc_18007EB52
0x18007eb1b  lea     r8, aPcszsid; "pcszSid"
0x18007eb22  mov     ebx, 80070057h
0x18007eb27  lea     rdx, aNgcregcontroll_13; "NgcRegController::IsAdOrAadSid"
0x18007eb2e  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007eb35  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007eb3a  lea     rdx, aPcszsid; "pcszSid"
0x18007eb41  lea     rcx, aNgcregcontroll_13; "NgcRegController::IsAdOrAadSid"
0x18007eb48  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007eb4d  jmp     loc_18007EC08
0x18007eb52  test    rdi, rdi
0x18007eb55  jnz     short loc_18007EB7F
0x18007eb57  lea     r8, aIsadoraadsid; "isAdOrAadSid"
0x18007eb5e  mov     ebx, 80070057h
0x18007eb63  lea     rdx, aNgcregcontroll_13; "NgcRegController::IsAdOrAadSid"
0x18007eb6a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007eb71  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007eb76  lea     rdx, aIsadoraadsid; "isAdOrAadSid"
0x18007eb7d  jmp     short loc_18007EB41
0x18007eb7f  mov     dword ptr [rdx], 0
0x18007eb85  lea     rdx, [rsp+28h+Sid]; Sid
0x18007eb8a  call    cs:__imp_ConvertStringSidToSidW
0x18007eb90  test    eax, eax
0x18007eb92  jnz     short loc_18007EBCC
0x18007eb94  call    cs:__imp_GetLastError
0x18007eb9a  mov     ebx, eax
0x18007eb9c  test    eax, eax
0x18007eb9e  jle     short loc_18007EBA9
0x18007eba0  movzx   ebx, ax
0x18007eba3  or      ebx, 80070000h
0x18007eba9  test    ebx, ebx
0x18007ebab  jns     short loc_18007EBCC
0x18007ebad  lea     r8, aConvertstrings_0; "ConvertStringSidToSid"
0x18007ebb4  mov     r9d, ebx
0x18007ebb7  lea     rdx, aNgcregcontroll_13; "NgcRegController::IsAdOrAadSid"
0x18007ebbe  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18007ebc5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007ebca  jmp     short loc_18007EC08
0x18007ebcc  mov     rcx, [rsp+28h+Sid]
0x18007ebd1  lea     rdx, [rsp+28h+arg_0]
0x18007ebd6  call    cs:__imp_LsaLookupUserAccountType
0x18007ebdc  mov     ebx, eax
0x18007ebde  or      ebx, 10000000h
0x18007ebe4  jge     short loc_18007EBEF
0x18007ebe6  lea     r8, aLsalookupusera_0; "LsaLookupUserAccountType"
0x18007ebed  jmp     short loc_18007EBB4
0x18007ebef  mov     ecx, [rsp+28h+arg_0]
0x18007ebf3  lea     eax, [rcx-2]
0x18007ebf6  test    eax, 0FFFFFFFCh
0x18007ebfb  jnz     short loc_18007EC08
0x18007ebfd  cmp     ecx, 4
0x18007ec00  jz      short loc_18007EC08
0x18007ec02  mov     dword ptr [rdi], 1
0x18007ec08  mov     rcx, [rsp+28h+Sid]; hMem
0x18007ec0d  test    rcx, rcx
0x18007ec10  jz      short loc_18007EC18
0x18007ec12  call    cs:__imp_LocalFree
0x18007ec18  mov     eax, ebx
0x18007ec1a  mov     rbx, [rsp+28h+arg_8]
0x18007ec1f  add     rsp, 20h
0x18007ec23  pop     rdi
0x18007ec24  retn
```
