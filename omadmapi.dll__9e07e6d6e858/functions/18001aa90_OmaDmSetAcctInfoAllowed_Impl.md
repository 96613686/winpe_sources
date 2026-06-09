# OmaDmSetAcctInfoAllowed_Impl

- ea: `0x18001aa90`
- end: `0x18001ac27`
- name: `OmaDmSetAcctInfoAllowed_Impl`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d9c0`

## callees

- `0x18000f47c`
- `0x18001aa90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abe1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abe1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abf6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001abb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001abb4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ab8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ab8a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ab2b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ab2b`
- `DMCmnUtils!CopyString` at `0x18001aae3`
- `DMCmnUtils!CopyString` at `0x18001aae3`

## pseudocode

```c
__int64 __fastcall OmaDmSetAcctInfoAllowed_Impl(const unsigned __int16 *a1, int a2, _DWORD *a3)
{
  signed int AccountIDFromLookupID; // ebx
  int v5; // edi
  char IsStateSeparationEnabled; // al
  const WCHAR *v7; // rdx
  LSTATUS v8; // eax
  bool v9; // cc
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v12; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp+10h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp+28h] BYREF

  lpSubKey = 0;
  v12 = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( !a1 )
    goto LABEL_2;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
LABEL_2:
      AccountIDFromLookupID = -2147024809;
      goto LABEL_21;
    }
    AccountIDFromLookupID = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&lpSubKey);
    if ( AccountIDFromLookupID >= 0 )
      goto LABEL_9;
  }
  else
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a1, 0, &lpSubKey);
  }
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_21;
LABEL_9:
  if ( (a3[30] & 0x400000) != 0 && (a3[1] & 0x100000) != 0 )
    v5 = a3[114];
  else
    v5 = 2;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v7 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
  if ( !IsStateSeparationEnabled )
    v7 = L"Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
  v8 = RegCreateKeyExW((HKEY)qword_18002A510[v5], v7, 0, 0, 0, 0x20119u, 0, &hKey, &dwDisposition);
  v9 = v8 <= 0;
  if ( !v8 )
  {
    v8 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20106u, &v12);
    if ( (v8 & 0xFFFFFFFD) == 0 )
      goto LABEL_21;
    v9 = v8 <= 0;
  }
  if ( v9 )
    AccountIDFromLookupID = v8;
  else
    AccountIDFromLookupID = (unsigned __int16)v8 | 0x80070000;
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v12 )
    RegCloseKey(v12);
  LocalFree((HLOCAL)lpSubKey);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x18001aa90  mov     [rsp-8+arg_8], rbx
0x18001aa95  mov     [rsp-8+arg_10], rdi
0x18001aa9a  push    rbp
0x18001aa9b  mov     rbp, rsp
0x18001aa9e  sub     rsp, 60h
0x18001aaa2  mov     [rbp+lpSubKey], 0
0x18001aaaa  mov     rdi, r8
0x18001aaad  mov     [rbp+var_8], 0
0x18001aab5  mov     [rbp+hKey], 0
0x18001aabd  mov     [rbp+dwDisposition], 0
0x18001aac4  test    rcx, rcx
0x18001aac7  jnz     short loc_18001AAD3
0x18001aac9  mov     ebx, 80070057h
0x18001aace  jmp     loc_18001ABD8
0x18001aad3  test    edx, edx
0x18001aad5  jz      short loc_18001AAF7
0x18001aad7  cmp     edx, 1
0x18001aada  jnz     short loc_18001AAC9
0x18001aadc  lea     r8, [rbp+lpSubKey]
0x18001aae0  or      edx, 0FFFFFFFFh
0x18001aae3  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001aaea  nop     dword ptr [rax+rax+00h]
0x18001aaef  mov     ebx, eax
0x18001aaf1  test    eax, eax
0x18001aaf3  js      short loc_18001AB04
0x18001aaf5  jmp     short loc_18001AB0C
0x18001aaf7  lea     r8, [rbp+lpSubKey]
0x18001aafb  xor     edx, edx
0x18001aafd  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x18001ab02  mov     ebx, eax
0x18001ab04  test    ebx, ebx
0x18001ab06  js      loc_18001ABD8
0x18001ab0c  test    dword ptr [rdi+78h], 400000h
0x18001ab13  jz      short loc_18001AB26
0x18001ab15  test    dword ptr [rdi+4], 100000h
0x18001ab1c  jz      short loc_18001AB26
0x18001ab1e  mov     edi, [rdi+1C8h]
0x18001ab24  jmp     short loc_18001AB2B
0x18001ab26  mov     edi, 2
0x18001ab2b  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001ab32  nop     dword ptr [rax+rax+00h]
0x18001ab37  test    al, al
0x18001ab39  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18001ab40  lea     rax, [rbp+dwDisposition]
0x18001ab44  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18001ab49  lea     r10, qword_18002A510
0x18001ab50  lea     rax, [rbp+hKey]
0x18001ab54  mov     [rsp+60h+phkResult], rax; phkResult
0x18001ab59  lea     rdx, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001ab60  cmovz   rdx, rcx; lpSubKey
0x18001ab64  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001ab6d  movsxd  rcx, edi
0x18001ab70  xor     r9d, r9d; lpClass
0x18001ab73  mov     [rsp+60h+samDesired], 20119h; samDesired
0x18001ab7b  xor     r8d, r8d; Reserved
0x18001ab7e  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18001ab86  mov     rcx, [r10+rcx*8]; hKey
0x18001ab8a  call    cs:__imp_RegCreateKeyExW
0x18001ab91  nop     dword ptr [rax+rax+00h]
0x18001ab96  test    eax, eax
0x18001ab98  jnz     short loc_18001ABC9
0x18001ab9a  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001ab9e  lea     rax, [rbp+var_8]
0x18001aba2  mov     rcx, [rbp+hKey]; hKey
0x18001aba6  mov     r9d, 20106h; samDesired
0x18001abac  xor     r8d, r8d; ulOptions
0x18001abaf  mov     qword ptr [rsp+60h+dwOptions], rax; phkResult
0x18001abb4  call    cs:__imp_RegOpenKeyExW
0x18001abbb  nop     dword ptr [rax+rax+00h]
0x18001abc0  test    eax, 0FFFFFFFDh
0x18001abc5  jz      short loc_18001ABD8
0x18001abc7  test    eax, eax
0x18001abc9  jg      short loc_18001ABCF
0x18001abcb  mov     ebx, eax
0x18001abcd  jmp     short loc_18001ABD8
0x18001abcf  movzx   ebx, ax
0x18001abd2  or      ebx, 80070000h
0x18001abd8  mov     rcx, [rbp+hKey]; hKey
0x18001abdc  test    rcx, rcx
0x18001abdf  jz      short loc_18001ABED
0x18001abe1  call    cs:__imp_RegCloseKey
0x18001abe8  nop     dword ptr [rax+rax+00h]
0x18001abed  mov     rcx, [rbp+var_8]; hKey
0x18001abf1  test    rcx, rcx
0x18001abf4  jz      short loc_18001AC02
0x18001abf6  call    cs:__imp_RegCloseKey
0x18001abfd  nop     dword ptr [rax+rax+00h]
0x18001ac02  mov     rcx, [rbp+lpSubKey]; hMem
0x18001ac06  call    cs:__imp_LocalFree
0x18001ac0d  nop     dword ptr [rax+rax+00h]
0x18001ac12  lea     r11, [rsp+60h+var_s0]
0x18001ac17  mov     eax, ebx
0x18001ac19  mov     rbx, [r11+18h]
0x18001ac1d  mov     rdi, [r11+20h]
0x18001ac21  mov     rsp, r11
0x18001ac24  pop     rbp
0x18001ac25  retn
```
