# OmaDmDeleteAcctInfo_Impl

- ea: `0x1800165a0`
- end: `0x1800166f7`
- name: `OmaDmDeleteAcctInfo_Impl`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800075f0`
- `0x180007930`
- `0x18000c920`
- `0x18000dfc0`
- `0x18000f47c`
- `0x1800165a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800166c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800166c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016687`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016687`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001669f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001669f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180016651`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180016651`
- `DMCmnUtils!CopyString` at `0x180016612`
- `DMCmnUtils!CopyString` at `0x180016612`

## pseudocode

```c
__int64 __fastcall OmaDmDeleteAcctInfo_Impl(const unsigned __int16 *a1, __int64 a2)
{
  int v2; // edi
  signed int AccountIDFromLookupID; // ebx
  __int64 v5; // rdx
  char IsStateSeparationEnabled; // al
  const WCHAR *v7; // rdx
  LSTATUS v8; // eax
  bool v9; // cc
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-8h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+38h] BYREF

  v2 = a2;
  hObject = 0;
  lpSubKey = 0;
  phkResult = 0;
  hKey = 0;
  if ( !(unsigned int)IsValidAccountID(a1, a2) )
    goto LABEL_2;
  AccountIDFromLookupID = AcquireOmaDmMutex(&hObject);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_19;
  if ( !a1 )
    goto LABEL_2;
  if ( !v2 )
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a1, 0, &lpSubKey);
LABEL_10:
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_19;
    goto LABEL_11;
  }
  if ( v2 != 1 )
  {
LABEL_2:
    AccountIDFromLookupID = -2147024809;
    goto LABEL_19;
  }
  AccountIDFromLookupID = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&lpSubKey);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_10;
LABEL_11:
  AccountIDFromLookupID = GetAccountRootKey(lpSubKey, v5, &hKey);
  if ( AccountIDFromLookupID >= 0 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v7 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
    if ( !IsStateSeparationEnabled )
      v7 = L"Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
    v8 = RegOpenKeyExW(hKey, v7, 0, 0x3010Eu, &phkResult);
    v9 = v8 <= 0;
    if ( v8 || (v8 = RegDeleteTreeW(phkResult, lpSubKey), v9 = v8 <= 0, v8) )
    {
      if ( v9 )
        AccountIDFromLookupID = v8;
      else
        AccountIDFromLookupID = (unsigned __int16)v8 | 0x80070000;
    }
  }
LABEL_19:
  RegCloseKey(phkResult);
  LocalFree((HLOCAL)lpSubKey);
  ReleaseOmaDmMutex(hObject);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x1800165a0  mov     [rsp-18h+arg_0], rbx
0x1800165a5  push    rbp
0x1800165a6  push    rsi
0x1800165a7  push    rdi
0x1800165a8  mov     rbp, rsp
0x1800165ab  sub     rsp, 40h
0x1800165af  mov     edi, edx
0x1800165b1  mov     [rbp+hObject], 0
0x1800165b9  mov     rsi, rcx
0x1800165bc  mov     [rbp+lpSubKey], 0
0x1800165c4  mov     [rbp+arg_18], 0
0x1800165cc  mov     [rbp+hKey], 0
0x1800165d4  call    IsValidAccountID
0x1800165d9  test    eax, eax
0x1800165db  jnz     short loc_1800165E7
0x1800165dd  mov     ebx, 80070057h
0x1800165e2  jmp     loc_1800166BE
0x1800165e7  lea     rcx, [rbp+hObject]; void **
0x1800165eb  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x1800165f0  mov     ebx, eax
0x1800165f2  test    eax, eax
0x1800165f4  js      loc_1800166BE
0x1800165fa  test    rsi, rsi
0x1800165fd  jz      short loc_1800165DD
0x1800165ff  test    edi, edi
0x180016601  jz      short loc_180016626
0x180016603  cmp     edi, 1
0x180016606  jnz     short loc_1800165DD
0x180016608  lea     r8, [rbp+lpSubKey]
0x18001660c  or      edx, 0FFFFFFFFh
0x18001660f  mov     rcx, rsi
0x180016612  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180016619  nop     dword ptr [rax+rax+00h]
0x18001661e  mov     ebx, eax
0x180016620  test    eax, eax
0x180016622  js      short loc_180016636
0x180016624  jmp     short loc_18001663E
0x180016626  lea     r8, [rbp+lpSubKey]
0x18001662a  xor     edx, edx
0x18001662c  mov     rcx, rsi
0x18001662f  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x180016634  mov     ebx, eax
0x180016636  test    ebx, ebx
0x180016638  js      loc_1800166BE
0x18001663e  mov     rcx, [rbp+lpSubKey]
0x180016642  lea     r8, [rbp+hKey]
0x180016646  call    GetAccountRootKey
0x18001664b  mov     ebx, eax
0x18001664d  test    eax, eax
0x18001664f  js      short loc_1800166BE
0x180016651  call    cs:__imp_RtlIsStateSeparationEnabled
0x180016658  nop     dword ptr [rax+rax+00h]
0x18001665d  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x180016664  mov     r9d, 3010Eh; samDesired
0x18001666a  test    al, al
0x18001666c  lea     rdx, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x180016673  lea     rax, [rbp+arg_18]
0x180016677  cmovz   rdx, rcx; lpSubKey
0x18001667b  mov     [rsp+40h+phkResult], rax; phkResult
0x180016680  mov     rcx, [rbp+hKey]; hKey
0x180016684  xor     r8d, r8d; ulOptions
0x180016687  call    cs:__imp_RegOpenKeyExW
0x18001668e  nop     dword ptr [rax+rax+00h]
0x180016693  test    eax, eax
0x180016695  jnz     short loc_1800166AF
0x180016697  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001669b  mov     rcx, [rbp+arg_18]; hKey
0x18001669f  call    cs:__imp_RegDeleteTreeW
0x1800166a6  nop     dword ptr [rax+rax+00h]
0x1800166ab  test    eax, eax
0x1800166ad  jz      short loc_1800166BE
0x1800166af  jg      short loc_1800166B5
0x1800166b1  mov     ebx, eax
0x1800166b3  jmp     short loc_1800166BE
0x1800166b5  movzx   ebx, ax
0x1800166b8  or      ebx, 80070000h
0x1800166be  mov     rcx, [rbp+arg_18]; hKey
0x1800166c2  call    cs:__imp_RegCloseKey
0x1800166c9  nop     dword ptr [rax+rax+00h]
0x1800166ce  mov     rcx, [rbp+lpSubKey]; hMem
0x1800166d2  call    cs:__imp_LocalFree
0x1800166d9  nop     dword ptr [rax+rax+00h]
0x1800166de  mov     rcx, [rbp+hObject]; hObject
0x1800166e2  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x1800166e7  mov     eax, ebx
0x1800166e9  mov     rbx, [rsp+40h+arg_0]
0x1800166ee  add     rsp, 40h
0x1800166f2  pop     rdi
0x1800166f3  pop     rsi
0x1800166f4  pop     rbp
0x1800166f5  retn
```
