# CflApi::GetProtectedScenarioDataSecurityDescriptor

- ea: `0x18001e55c`
- end: `0x18001e67b`
- name: `CflApi::GetProtectedScenarioDataSecurityDescriptor`
- size: `287`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020378`

## callees

- `0x1800067a4`
- `0x18001e55c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e614`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e5b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e627`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e5b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e5b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e61f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e5b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e61f`
- `ntdll!RtlIsMultiSessionSku` at `0x18001e593`
- `ntdll!RtlIsMultiSessionSku` at `0x18001e593`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e5db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e649`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e5db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e649`

## string_xrefs

- `0x18001e5ee`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
__int64 __fastcall CflApi::GetProtectedScenarioDataSecurityDescriptor(HLOCAL *a1, ULONG *a2)
{
  char IsMultiSessionSku; // al
  HLOCAL v5; // rdi
  DWORD v6; // ebx
  const char *v7; // r9
  __int64 v8; // rdx
  unsigned int v9; // ebx
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  ULONG SecurityDescriptorSize; // [rsp+40h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp+28h] BYREF

  *a1 = 0;
  *a2 = 0;
  hMem = 0;
  SecurityDescriptorSize = 0;
  IsMultiSessionSku = RtlIsMultiSessionSku();
  v5 = hMem;
  if ( !IsMultiSessionSku )
  {
    if ( hMem )
    {
      LastError = GetLastError();
      LocalFree(v5);
      SetLastError(LastError);
    }
    hMem = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;OICI;KA;;;SY)(XA;CI;KRKWSD;;;S-1-15-3-1024-1730716382-2949791265-2036182297-688374192-553408039-4133924"
             "312-4201181712-267922143;(!(WIN://ISMULTISESSIONSKU)))(A;OICI;KRKW;;;WD)(A;OICI;SD;;;WD)",
            1u,
            &hMem,
            &SecurityDescriptorSize) )
    {
      v8 = 1650;
      goto LABEL_6;
    }
LABEL_13:
    *a1 = hMem;
    *a2 = SecurityDescriptorSize;
    return 0;
  }
  if ( hMem )
  {
    v6 = GetLastError();
    LocalFree(v5);
    SetLastError(v6);
  }
  hMem = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;OICI;KA;;;SY)(D;OICI;KR;;;WD)(A;OICI;KW;;;WD)(A;OICI;SD;;;WD)",
         1u,
         &hMem,
         &SecurityDescriptorSize) )
  {
    goto LABEL_13;
  }
  v8 = 1624;
LABEL_6:
  v9 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v8,
         (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
         v7);
  if ( hMem )
    LocalFree(hMem);
  return v9;
}

```

## disassembly

```asm
0x18001e55c  mov     [rsp-18h+arg_10], rbx
0x18001e561  mov     [rsp-18h+arg_18], rsi
0x18001e566  push    rbp
0x18001e567  push    rdi
0x18001e568  push    r14
0x18001e56a  mov     rbp, rsp
0x18001e56d  sub     rsp, 20h
0x18001e571  mov     qword ptr [rcx], 0
0x18001e578  mov     rsi, rdx
0x18001e57b  mov     dword ptr [rdx], 0
0x18001e581  mov     r14, rcx
0x18001e584  mov     [rbp+hMem], 0
0x18001e58c  mov     [rbp+SecurityDescriptorSize], 0
0x18001e593  call    cs:__imp_RtlIsMultiSessionSku
0x18001e599  mov     rdi, [rbp+hMem]
0x18001e59d  test    al, al
0x18001e59f  jz      short loc_18001E60F
0x18001e5a1  test    rdi, rdi
0x18001e5a4  jz      short loc_18001E5BF
0x18001e5a6  call    cs:__imp_GetLastError
0x18001e5ac  mov     rcx, rdi; hMem
0x18001e5af  mov     ebx, eax
0x18001e5b1  call    cs:__imp_LocalFree
0x18001e5b7  mov     ecx, ebx; dwErrCode
0x18001e5b9  call    cs:__imp_SetLastError
0x18001e5bf  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18001e5c3  mov     [rbp+hMem], 0
0x18001e5cb  lea     r8, [rbp+hMem]; SecurityDescriptor
0x18001e5cf  mov     edx, 1; StringSDRevision
0x18001e5d4  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;KA;;;SY)(D;OICI;KR;;;WD)(A;OI"...
0x18001e5db  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001e5e1  test    eax, eax
0x18001e5e3  jnz     short loc_18001E65A
0x18001e5e5  mov     edx, 658h; void *
0x18001e5ea  mov     rcx, [rbp+18h]; this
0x18001e5ee  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001e5f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e5fa  mov     rcx, [rbp+hMem]; hMem
0x18001e5fe  mov     ebx, eax
0x18001e600  test    rcx, rcx
0x18001e603  jz      short loc_18001E60B
0x18001e605  call    cs:__imp_LocalFree
0x18001e60b  mov     eax, ebx
0x18001e60d  jmp     short loc_18001E668
0x18001e60f  test    rdi, rdi
0x18001e612  jz      short loc_18001E62D
0x18001e614  call    cs:__imp_GetLastError
0x18001e61a  mov     rcx, rdi; hMem
0x18001e61d  mov     ebx, eax
0x18001e61f  call    cs:__imp_LocalFree
0x18001e625  mov     ecx, ebx; dwErrCode
0x18001e627  call    cs:__imp_SetLastError
0x18001e62d  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18001e631  mov     [rbp+hMem], 0
0x18001e639  lea     r8, [rbp+hMem]; SecurityDescriptor
0x18001e63d  mov     edx, 1; StringSDRevision
0x18001e642  lea     rcx, aDAOiciKaSyXaCi; "D:(A;OICI;KA;;;SY)(XA;CI;KRKWSD;;;S-1-1"...
0x18001e649  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001e64f  test    eax, eax
0x18001e651  jnz     short loc_18001E65A
0x18001e653  mov     edx, 672h
0x18001e658  jmp     short loc_18001E5EA
0x18001e65a  mov     rax, [rbp+hMem]
0x18001e65e  mov     [r14], rax
0x18001e661  mov     eax, [rbp+SecurityDescriptorSize]
0x18001e664  mov     [rsi], eax
0x18001e666  xor     eax, eax
0x18001e668  mov     rbx, [rsp+20h+arg_10]
0x18001e66d  mov     rsi, [rsp+20h+arg_18]
0x18001e672  add     rsp, 20h
0x18001e676  pop     r14
0x18001e678  pop     rdi
0x18001e679  pop     rbp
0x18001e67a  retn
```
