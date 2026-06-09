# RegistryRegRow::AssociateWithPerUser(ushort const *,int *)

- ea: `0x18003a720`
- end: `0x18003a934`
- name: `?AssociateWithPerUser@RegistryRegRow@@UEAAJPEBGPEAH@Z`
- size: `532`
- prototype: `int __fastcall(RegistryRegRow *this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006194`
- `0x1800084c8`
- `0x18000c910`
- `0x180017aa0`
- `0x18003a720`
- `0x1800434de`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a819`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a832`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a832`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a8a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a8a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a8f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a8f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a7c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a7c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a843`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a911`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a843`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a911`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003a80f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003a80f`

## pseudocode

```c
int __fastcall RegistryRegRow::AssociateWithPerUser(RegistryRegRow *this, const unsigned __int16 *a2, int *a3)
{
  int result; // eax
  unsigned int v7; // r14d
  int v8; // eax
  int v9; // r15d
  signed int v10; // ebx
  int v11; // r12d
  unsigned __int16 *v12; // rax
  WCHAR *v13; // r15
  WCHAR *v14; // r14
  int LastError; // eax
  unsigned __int16 *v16; // rax
  HKEY v17; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-11h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-9h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+E8h] [rbp+7Fh] BYREF

  result = wcscmp_0(a2, L"S-1-5-18");
  if ( result )
  {
    if ( *((_QWORD *)this + 16) == -2147483645 )
      return -2147418113;
    v7 = safe_lstrlenW(a2);
    v8 = safe_lstrlenW(*((const unsigned __int16 **)this + 15));
    StringSecurityDescriptor = 0;
    v9 = v8;
    v10 = InitializeStringSecurityDescriptorForEventSystemKey(v7, a2, (unsigned __int16 **)&StringSecurityDescriptor);
    if ( v10 < 0 )
      return v10;
    v11 = v9 + v7 + 2;
    v12 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v11, 2u));
    v13 = (WCHAR *)StringSecurityDescriptor;
    v14 = v12;
    if ( !v12 )
    {
      v10 = -2147024882;
      goto LABEL_16;
    }
    v10 = StringCchPrintfW(v12, v11, L"%s\\%s", a2, *((_QWORD *)this + 15));
    if ( v10 < 0 )
      goto LABEL_10;
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v13, 1u, &SecurityDescriptor, 0) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError <= 0 )
        goto LABEL_9;
      goto LABEL_8;
    }
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    hKey = 0;
    LODWORD(StringSecurityDescriptor) = 0;
    LastError = RegCreateKeyExW(
                  HKEY_USERS,
                  v14,
                  0,
                  0,
                  0,
                  0x20019u,
                  &SecurityAttributes,
                  &hKey,
                  (LPDWORD)&StringSecurityDescriptor);
    if ( LastError )
    {
      if ( LastError > 0 )
      {
LABEL_8:
        v10 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_9;
      }
      v10 = LastError;
    }
    else
    {
      *a3 = (_DWORD)StringSecurityDescriptor == 1;
      CoTaskMemFree(*((LPVOID *)this + 14));
      CoTaskMemFree(*((LPVOID *)this + 15));
      v16 = WStringCopy(v13);
      v17 = hKey;
      *((_QWORD *)this + 14) = v16;
      *((_QWORD *)this + 15) = v14;
      *((_DWORD *)this + 35) = v11;
      *((_QWORD *)this + 16) = -2147483645;
      RegCloseKey(v17);
    }
LABEL_9:
    LocalFree(SecurityDescriptor);
    if ( v10 >= 0 )
    {
LABEL_16:
      CoTaskMemFree(v13);
      return v10;
    }
LABEL_10:
    CoTaskMemFree(v14);
    goto LABEL_16;
  }
  return result;
}

```

## disassembly

```asm
0x18003a720  push    rbp
0x18003a722  push    rbx
0x18003a723  push    rsi
0x18003a724  push    rdi
0x18003a725  push    r12
0x18003a727  push    r13
0x18003a729  push    r14
0x18003a72b  push    r15
0x18003a72d  lea     rbp, [rsp-1Fh]
0x18003a732  sub     rsp, 88h
0x18003a739  mov     rsi, rdx
0x18003a73c  mov     rdi, rcx
0x18003a73f  mov     rcx, rsi; String1
0x18003a742  lea     rdx, aS1518; "S-1-5-18"
0x18003a749  mov     r13, r8
0x18003a74c  call    wcscmp_0
0x18003a751  test    eax, eax
0x18003a753  jz      loc_18003A920
0x18003a759  cmp     qword ptr [rdi+80h], 0FFFFFFFF80000003h
0x18003a764  jz      loc_18003A919
0x18003a76a  mov     rcx, rsi; unsigned __int16 *
0x18003a76d  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003a772  mov     rcx, [rdi+78h]; unsigned __int16 *
0x18003a776  mov     r14d, eax
0x18003a779  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003a77e  lea     r8, [rbp+57h+StringSecurityDescriptor]; unsigned __int16 **
0x18003a782  mov     [rbp+57h+StringSecurityDescriptor], 0
0x18003a78a  mov     rdx, rsi; unsigned __int16 *
0x18003a78d  mov     ecx, r14d; unsigned int
0x18003a790  mov     r15d, eax
0x18003a793  call    ?InitializeStringSecurityDescriptorForEventSystemKey@@YAJKPEBGPEAPEAG@Z; InitializeStringSecurityDescriptorForEventSystemKey(ulong,ushort const *,ushort * *)
0x18003a798  mov     ebx, eax
0x18003a79a  test    eax, eax
0x18003a79c  js      loc_18003A91E
0x18003a7a2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003a7a9  lea     r12d, [r14+2]
0x18003a7ad  add     r12d, r15d
0x18003a7b0  mov     eax, 2
0x18003a7b5  movsxd  rbx, r12d
0x18003a7b8  mul     rbx
0x18003a7bb  cmovb   rax, rcx
0x18003a7bf  mov     rcx, rax; cb
0x18003a7c2  call    cs:__imp_CoTaskMemAlloc
0x18003a7c8  mov     r15, [rbp+57h+StringSecurityDescriptor]
0x18003a7cc  mov     r14, rax
0x18003a7cf  test    rax, rax
0x18003a7d2  jz      loc_18003A909
0x18003a7d8  mov     rcx, [rdi+78h]
0x18003a7dc  lea     r8, aSS; "%s\\%s"
0x18003a7e3  mov     qword ptr [rsp+0C0h+dwOptions], rcx
0x18003a7e8  mov     r9, rsi
0x18003a7eb  mov     rcx, rax; unsigned __int16 *
0x18003a7ee  mov     rdx, rbx; unsigned __int64
0x18003a7f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a7f6  xor     esi, esi
0x18003a7f8  mov     ebx, eax
0x18003a7fa  test    eax, eax
0x18003a7fc  js      short loc_18003A840
0x18003a7fe  xor     r9d, r9d; SecurityDescriptorSize
0x18003a801  mov     [rbp+57h+SecurityDescriptor], rsi
0x18003a805  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18003a809  mov     rcx, r15; StringSecurityDescriptor
0x18003a80c  lea     edx, [rsi+1]; StringSDRevision
0x18003a80f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003a815  test    eax, eax
0x18003a817  jnz     short loc_18003A84E
0x18003a819  call    cs:__imp_GetLastError
0x18003a81f  mov     ebx, eax
0x18003a821  test    eax, eax
0x18003a823  jle     short loc_18003A82E
0x18003a825  movzx   ebx, ax
0x18003a828  or      ebx, 80070000h
0x18003a82e  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18003a832  call    cs:__imp_LocalFree
0x18003a838  test    ebx, ebx
0x18003a83a  jns     loc_18003A90E
0x18003a840  mov     rcx, r14; pv
0x18003a843  call    cs:__imp_CoTaskMemFree
0x18003a849  jmp     loc_18003A90E
0x18003a84e  mov     rax, [rbp+57h+SecurityDescriptor]
0x18003a852  xor     r9d, r9d; lpClass
0x18003a855  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18003a859  xor     r8d, r8d; Reserved
0x18003a85c  lea     rax, [rbp+57h+StringSecurityDescriptor]
0x18003a860  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18003a868  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18003a86d  mov     rdx, r14; lpSubKey
0x18003a870  lea     rax, [rbp+57h+hKey]
0x18003a874  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rsi
0x18003a878  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18003a87d  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003a884  lea     rax, [rbp+57h+SecurityAttributes]
0x18003a888  mov     [rbp+57h+hKey], rsi
0x18003a88c  mov     [rsp+0C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18003a891  mov     [rsp+0C0h+samDesired], 20019h; samDesired
0x18003a899  mov     [rsp+0C0h+dwOptions], esi; dwOptions
0x18003a89d  mov     dword ptr [rbp+57h+StringSecurityDescriptor], esi
0x18003a8a0  call    cs:__imp_RegCreateKeyExW
0x18003a8a6  test    eax, eax
0x18003a8a8  jnz     short loc_18003A8FC
0x18003a8aa  cmp     dword ptr [rbp+57h+StringSecurityDescriptor], 1
0x18003a8ae  mov     eax, esi
0x18003a8b0  setz    al
0x18003a8b3  mov     [r13+0], eax
0x18003a8b7  mov     rcx, [rdi+70h]; pv
0x18003a8bb  call    cs:__imp_CoTaskMemFree
0x18003a8c1  mov     rcx, [rdi+78h]; pv
0x18003a8c5  call    cs:__imp_CoTaskMemFree
0x18003a8cb  mov     rcx, r15; Src
0x18003a8ce  call    ?WStringCopy@@YAPEAGPEBG@Z; WStringCopy(ushort const *)
0x18003a8d3  mov     rcx, [rbp+57h+hKey]; hKey
0x18003a8d7  mov     [rdi+70h], rax
0x18003a8db  mov     [rdi+78h], r14
0x18003a8df  mov     [rdi+8Ch], r12d
0x18003a8e6  mov     qword ptr [rdi+80h], 0FFFFFFFF80000003h
0x18003a8f1  call    cs:__imp_RegCloseKey
0x18003a8f7  jmp     loc_18003A82E
0x18003a8fc  jg      loc_18003A825
0x18003a902  mov     ebx, eax
0x18003a904  jmp     loc_18003A82E
0x18003a909  mov     ebx, 8007000Eh
0x18003a90e  mov     rcx, r15; pv
0x18003a911  call    cs:__imp_CoTaskMemFree
0x18003a917  jmp     short loc_18003A91E
0x18003a919  mov     ebx, 8000FFFFh
0x18003a91e  mov     eax, ebx
0x18003a920  add     rsp, 88h
0x18003a927  pop     r15
0x18003a929  pop     r14
0x18003a92b  pop     r13
0x18003a92d  pop     r12
0x18003a92f  pop     rdi
0x18003a930  pop     rsi
0x18003a931  pop     rbx
0x18003a932  pop     rbp
0x18003a933  retn
```
