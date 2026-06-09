# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x18001d3fc`
- end: `0x18001d58a`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18000be00`

## callees

- `0x18001d3fc`
- `0x18001d590`
- `0x18001d97c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d496`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d496`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d484`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d546`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d484`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d546`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d554`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d554`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d56b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d56b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d45e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d45e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001d42c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001d42c`
- `DMCmnUtils!DmRevertToSelf` at `0x18001d516`
- `DMCmnUtils!DmRevertToSelf` at `0x18001d516`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18001d4c4`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18001d4c4`
- `CRYPT32!CertFreeCertificateContext` at `0x18001d52b`
- `CRYPT32!CertFreeCertificateContext` at `0x18001d52b`
- `CRYPT32!CertCloseStore` at `0x18001d53b`
- `CRYPT32!CertCloseStore` at `0x18001d53b`

## pseudocode

```c
__int64 __fastcall GetDeviceCertExpiryTime(const unsigned __int16 *a1, struct _FILETIME *a2)
{
  struct _CERT_CONTEXT *v2; // rdi
  void *v3; // r14
  char IsStateSeparationEnabled; // al
  LSTATUS v7; // eax
  signed int String; // ebx
  HKEY v9; // rcx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rsi
  int v13; // r9d
  int InstalledCert; // eax
  HANDLE v15; // rax
  unsigned int *phkResult; // [rsp+20h] [rbp-20h]
  struct _CERT_CONTEXT *v18; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  void *v20; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v3 = 0;
  v20 = 0;
  v18 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_180021160 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  String = v7;
  if ( v7 > 0 )
    String = (unsigned __int16)v7 | 0x80070000;
  if ( String >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v11 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x54u);
    v12 = v11;
    if ( v11 )
    {
      String = OmaDmRegistryGetString(hKey, a1, L"DMPCertThumbPrint", v11, 0x2Au);
      if ( String >= 0 )
      {
        ImpersonateForCertAccess(a1);
        InstalledCert = GetInstalledCert(v12, &v20, (const struct _CERT_CONTEXT **)&v18, v13, phkResult);
        v2 = v18;
        String = InstalledCert;
        v3 = v20;
        if ( InstalledCert >= 0 )
        {
          a2->dwHighDateTime = v18->pCertInfo->NotAfter.dwHighDateTime;
          a2->dwLowDateTime = v2->pCertInfo->NotAfter.dwLowDateTime;
        }
      }
    }
    else
    {
      String = -2147024882;
    }
    if ( byte_18002B844 )
    {
      DmRevertToSelf();
      byte_18002B844 = 0;
    }
    if ( v2 )
      CertFreeCertificateContext(v2);
    if ( v3 )
      CertCloseStore(v3, 0);
    if ( v12 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v12);
    }
    v9 = hKey;
    hKey = 0;
  }
  else
  {
    v9 = hKey;
    hKey = 0;
  }
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18001d3fc  mov     [rsp-28h+arg_0], rbx
0x18001d401  mov     [rsp-28h+arg_8], rsi
0x18001d406  push    rbp
0x18001d407  push    rdi
0x18001d408  push    r12
0x18001d40a  push    r14
0x18001d40c  push    r15
0x18001d40e  mov     rbp, rsp
0x18001d411  sub     rsp, 40h
0x18001d415  xor     edi, edi
0x18001d417  xor     r14d, r14d
0x18001d41a  mov     [rbp+arg_18], r14
0x18001d41e  mov     r12, rdx
0x18001d421  mov     [rbp+var_10], rdi
0x18001d425  mov     r15, rcx
0x18001d428  mov     [rbp+hKey], rdi
0x18001d42c  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001d432  lea     rcx, off_180021160; "Software\\Microsoft\\Enrollments"
0x18001d439  mov     r9d, 20019h; samDesired
0x18001d43f  neg     al
0x18001d441  lea     rax, [rbp+hKey]
0x18001d445  sbb     rdx, rdx
0x18001d448  mov     [rsp+40h+phkResult], rax; phkResult
0x18001d44d  and     edx, 8
0x18001d450  xor     r8d, r8d; ulOptions
0x18001d453  mov     rdx, [rdx+rcx]; lpSubKey
0x18001d457  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d45e  call    cs:__imp_RegOpenKeyExW
0x18001d464  mov     ebx, eax
0x18001d466  test    eax, eax
0x18001d468  jle     short loc_18001D473
0x18001d46a  movzx   ebx, ax
0x18001d46d  or      ebx, 80070000h
0x18001d473  test    ebx, ebx
0x18001d475  jns     short loc_18001D484
0x18001d477  mov     rcx, [rbp+hKey]
0x18001d47b  mov     [rbp+hKey], rdi
0x18001d47f  jmp     loc_18001D566
0x18001d484  call    cs:__imp_GetProcessHeap
0x18001d48a  mov     edx, 8; dwFlags
0x18001d48f  mov     rcx, rax; hHeap
0x18001d492  lea     r8d, [rdx+4Ch]; dwBytes
0x18001d496  call    cs:__imp_HeapAlloc
0x18001d49c  mov     rsi, rax
0x18001d49f  test    rax, rax
0x18001d4a2  jnz     short loc_18001D4AB
0x18001d4a4  mov     ebx, 8007000Eh
0x18001d4a9  jmp     short loc_18001D50D
0x18001d4ab  mov     rcx, [rbp+hKey]
0x18001d4af  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x18001d4b6  mov     r9, rsi
0x18001d4b9  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'; unsigned int *
0x18001d4c1  mov     rdx, r15
0x18001d4c4  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x18001d4ca  mov     ebx, eax
0x18001d4cc  test    eax, eax
0x18001d4ce  js      short loc_18001D50D
0x18001d4d0  mov     rcx, r15; unsigned __int16 *
0x18001d4d3  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x18001d4d8  lea     r8, [rbp+var_10]; struct _CERT_CONTEXT **
0x18001d4dc  mov     rcx, rsi; unsigned __int16 *
0x18001d4df  lea     rdx, [rbp+arg_18]; void **
0x18001d4e3  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x18001d4e8  mov     rdi, [rbp+var_10]
0x18001d4ec  mov     ebx, eax
0x18001d4ee  mov     r14, [rbp+arg_18]
0x18001d4f2  test    eax, eax
0x18001d4f4  js      short loc_18001D50D
0x18001d4f6  mov     rax, [rdi+18h]
0x18001d4fa  mov     ecx, [rax+4Ch]
0x18001d4fd  mov     [r12+4], ecx
0x18001d502  mov     rax, [rdi+18h]
0x18001d506  mov     ecx, [rax+48h]
0x18001d509  mov     [r12], ecx
0x18001d50d  cmp     cs:byte_18002B844, 0
0x18001d514  jz      short loc_18001D523
0x18001d516  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001d51c  mov     cs:byte_18002B844, 0
0x18001d523  test    rdi, rdi
0x18001d526  jz      short loc_18001D531
0x18001d528  mov     rcx, rdi; pCertContext
0x18001d52b  call    cs:__imp_CertFreeCertificateContext
0x18001d531  test    r14, r14
0x18001d534  jz      short loc_18001D541
0x18001d536  xor     edx, edx; dwFlags
0x18001d538  mov     rcx, r14; hCertStore
0x18001d53b  call    cs:__imp_CertCloseStore
0x18001d541  test    rsi, rsi
0x18001d544  jz      short loc_18001D55A
0x18001d546  call    cs:__imp_GetProcessHeap
0x18001d54c  mov     r8, rsi; lpMem
0x18001d54f  xor     edx, edx; dwFlags
0x18001d551  mov     rcx, rax; hHeap
0x18001d554  call    cs:__imp_HeapFree
0x18001d55a  mov     rcx, [rbp+hKey]; hKey
0x18001d55e  mov     [rbp+hKey], 0
0x18001d566  test    rcx, rcx
0x18001d569  jz      short loc_18001D571
0x18001d56b  call    cs:__imp_RegCloseKey
0x18001d571  mov     rsi, [rsp+40h+arg_8]
0x18001d576  mov     eax, ebx
0x18001d578  mov     rbx, [rsp+40h+arg_0]
0x18001d57d  add     rsp, 40h
0x18001d581  pop     r15
0x18001d583  pop     r14
0x18001d585  pop     r12
0x18001d587  pop     rdi
0x18001d588  pop     rbp
0x18001d589  retn
```
