# CflApiNew::GetProtectedScenarioDataSecurityDescriptor

- ea: `0x18002a6a4`
- end: `0x18002a7c3`
- name: `CflApiNew::GetProtectedScenarioDataSecurityDescriptor`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ba10`

## callees

- `0x1800067a4`
- `0x18002a6a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a75c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a75c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a701`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a76f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a701`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a76f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a74d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a767`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a74d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a767`
- `ntdll!RtlIsMultiSessionSku` at `0x18002a6db`
- `ntdll!RtlIsMultiSessionSku` at `0x18002a6db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a723`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a791`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a723`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a791`

## string_xrefs

- `0x18002a736`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
__int64 __fastcall CflApiNew::GetProtectedScenarioDataSecurityDescriptor(HLOCAL *a1, ULONG *a2)
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
      v8 = 962;
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
  v8 = 936;
LABEL_6:
  v9 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v8,
         (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
         v7);
  if ( hMem )
    LocalFree(hMem);
  return v9;
}

```

## disassembly

```asm
0x18002a6a4  mov     [rsp-18h+arg_10], rbx
0x18002a6a9  mov     [rsp-18h+arg_18], rsi
0x18002a6ae  push    rbp
0x18002a6af  push    rdi
0x18002a6b0  push    r14
0x18002a6b2  mov     rbp, rsp
0x18002a6b5  sub     rsp, 20h
0x18002a6b9  mov     qword ptr [rcx], 0
0x18002a6c0  mov     rsi, rdx
0x18002a6c3  mov     dword ptr [rdx], 0
0x18002a6c9  mov     r14, rcx
0x18002a6cc  mov     [rbp+hMem], 0
0x18002a6d4  mov     [rbp+SecurityDescriptorSize], 0
0x18002a6db  call    cs:__imp_RtlIsMultiSessionSku
0x18002a6e1  mov     rdi, [rbp+hMem]
0x18002a6e5  test    al, al
0x18002a6e7  jz      short loc_18002A757
0x18002a6e9  test    rdi, rdi
0x18002a6ec  jz      short loc_18002A707
0x18002a6ee  call    cs:__imp_GetLastError
0x18002a6f4  mov     rcx, rdi; hMem
0x18002a6f7  mov     ebx, eax
0x18002a6f9  call    cs:__imp_LocalFree
0x18002a6ff  mov     ecx, ebx; dwErrCode
0x18002a701  call    cs:__imp_SetLastError
0x18002a707  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18002a70b  mov     [rbp+hMem], 0
0x18002a713  lea     r8, [rbp+hMem]; SecurityDescriptor
0x18002a717  mov     edx, 1; StringSDRevision
0x18002a71c  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;KA;;;SY)(D;OICI;KR;;;WD)(A;OI"...
0x18002a723  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002a729  test    eax, eax
0x18002a72b  jnz     short loc_18002A7A2
0x18002a72d  mov     edx, 3A8h; void *
0x18002a732  mov     rcx, [rbp+18h]; this
0x18002a736  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002a73d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a742  mov     rcx, [rbp+hMem]; hMem
0x18002a746  mov     ebx, eax
0x18002a748  test    rcx, rcx
0x18002a74b  jz      short loc_18002A753
0x18002a74d  call    cs:__imp_LocalFree
0x18002a753  mov     eax, ebx
0x18002a755  jmp     short loc_18002A7B0
0x18002a757  test    rdi, rdi
0x18002a75a  jz      short loc_18002A775
0x18002a75c  call    cs:__imp_GetLastError
0x18002a762  mov     rcx, rdi; hMem
0x18002a765  mov     ebx, eax
0x18002a767  call    cs:__imp_LocalFree
0x18002a76d  mov     ecx, ebx; dwErrCode
0x18002a76f  call    cs:__imp_SetLastError
0x18002a775  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18002a779  mov     [rbp+hMem], 0
0x18002a781  lea     r8, [rbp+hMem]; SecurityDescriptor
0x18002a785  mov     edx, 1; StringSDRevision
0x18002a78a  lea     rcx, aDAOiciKaSyXaCi; "D:(A;OICI;KA;;;SY)(XA;CI;KRKWSD;;;S-1-1"...
0x18002a791  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002a797  test    eax, eax
0x18002a799  jnz     short loc_18002A7A2
0x18002a79b  mov     edx, 3C2h
0x18002a7a0  jmp     short loc_18002A732
0x18002a7a2  mov     rax, [rbp+hMem]
0x18002a7a6  mov     [r14], rax
0x18002a7a9  mov     eax, [rbp+SecurityDescriptorSize]
0x18002a7ac  mov     [rsi], eax
0x18002a7ae  xor     eax, eax
0x18002a7b0  mov     rbx, [rsp+20h+arg_10]
0x18002a7b5  mov     rsi, [rsp+20h+arg_18]
0x18002a7ba  add     rsp, 20h
0x18002a7be  pop     r14
0x18002a7c0  pop     rdi
0x18002a7c1  pop     rbp
0x18002a7c2  retn
```
