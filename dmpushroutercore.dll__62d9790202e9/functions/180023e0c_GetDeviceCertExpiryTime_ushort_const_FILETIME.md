# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x180023e0c`
- end: `0x180023f9a`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18000ea90`

## callees

- `0x180023e0c`
- `0x180023fa0`
- `0x18002438c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023f64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023f64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023ea6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023ea6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023f56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023f56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023f7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023f7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023e6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023e6e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180023e3c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180023e3c`
- `CRYPT32!CertFreeCertificateContext` at `0x180023f3b`
- `CRYPT32!CertFreeCertificateContext` at `0x180023f3b`
- `CRYPT32!CertCloseStore` at `0x180023f4b`
- `CRYPT32!CertCloseStore` at `0x180023f4b`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180023ed4`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180023ed4`
- `DMCmnUtils!DmRevertToSelf` at `0x180023f26`
- `DMCmnUtils!DmRevertToSelf` at `0x180023f26`

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
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_18003CA70 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
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
    if ( byte_180051144 )
    {
      DmRevertToSelf();
      byte_180051144 = 0;
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
0x180023e0c  mov     [rsp-28h+arg_0], rbx
0x180023e11  mov     [rsp-28h+arg_8], rsi
0x180023e16  push    rbp
0x180023e17  push    rdi
0x180023e18  push    r12
0x180023e1a  push    r14
0x180023e1c  push    r15
0x180023e1e  mov     rbp, rsp
0x180023e21  sub     rsp, 40h
0x180023e25  xor     edi, edi
0x180023e27  xor     r14d, r14d
0x180023e2a  mov     [rbp+arg_18], r14
0x180023e2e  mov     r12, rdx
0x180023e31  mov     [rbp+var_10], rdi
0x180023e35  mov     r15, rcx
0x180023e38  mov     [rbp+hKey], rdi
0x180023e3c  call    cs:__imp_RtlIsStateSeparationEnabled
0x180023e42  lea     rcx, off_18003CA70; "Software\\Microsoft\\Enrollments"
0x180023e49  mov     r9d, 20019h; samDesired
0x180023e4f  neg     al
0x180023e51  lea     rax, [rbp+hKey]
0x180023e55  sbb     rdx, rdx
0x180023e58  mov     [rsp+40h+phkResult], rax; phkResult
0x180023e5d  and     edx, 8
0x180023e60  xor     r8d, r8d; ulOptions
0x180023e63  mov     rdx, [rdx+rcx]; lpSubKey
0x180023e67  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023e6e  call    cs:__imp_RegOpenKeyExW
0x180023e74  mov     ebx, eax
0x180023e76  test    eax, eax
0x180023e78  jle     short loc_180023E83
0x180023e7a  movzx   ebx, ax
0x180023e7d  or      ebx, 80070000h
0x180023e83  test    ebx, ebx
0x180023e85  jns     short loc_180023E94
0x180023e87  mov     rcx, [rbp+hKey]
0x180023e8b  mov     [rbp+hKey], rdi
0x180023e8f  jmp     loc_180023F76
0x180023e94  call    cs:__imp_GetProcessHeap
0x180023e9a  mov     edx, 8; dwFlags
0x180023e9f  mov     rcx, rax; hHeap
0x180023ea2  lea     r8d, [rdx+4Ch]; dwBytes
0x180023ea6  call    cs:__imp_HeapAlloc
0x180023eac  mov     rsi, rax
0x180023eaf  test    rax, rax
0x180023eb2  jnz     short loc_180023EBB
0x180023eb4  mov     ebx, 8007000Eh
0x180023eb9  jmp     short loc_180023F1D
0x180023ebb  mov     rcx, [rbp+hKey]
0x180023ebf  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x180023ec6  mov     r9, rsi
0x180023ec9  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'; unsigned int *
0x180023ed1  mov     rdx, r15
0x180023ed4  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180023eda  mov     ebx, eax
0x180023edc  test    eax, eax
0x180023ede  js      short loc_180023F1D
0x180023ee0  mov     rcx, r15; unsigned __int16 *
0x180023ee3  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x180023ee8  lea     r8, [rbp+var_10]; struct _CERT_CONTEXT **
0x180023eec  mov     rcx, rsi; unsigned __int16 *
0x180023eef  lea     rdx, [rbp+arg_18]; void **
0x180023ef3  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x180023ef8  mov     rdi, [rbp+var_10]
0x180023efc  mov     ebx, eax
0x180023efe  mov     r14, [rbp+arg_18]
0x180023f02  test    eax, eax
0x180023f04  js      short loc_180023F1D
0x180023f06  mov     rax, [rdi+18h]
0x180023f0a  mov     ecx, [rax+4Ch]
0x180023f0d  mov     [r12+4], ecx
0x180023f12  mov     rax, [rdi+18h]
0x180023f16  mov     ecx, [rax+48h]
0x180023f19  mov     [r12], ecx
0x180023f1d  cmp     cs:byte_180051144, 0
0x180023f24  jz      short loc_180023F33
0x180023f26  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180023f2c  mov     cs:byte_180051144, 0
0x180023f33  test    rdi, rdi
0x180023f36  jz      short loc_180023F41
0x180023f38  mov     rcx, rdi; pCertContext
0x180023f3b  call    cs:__imp_CertFreeCertificateContext
0x180023f41  test    r14, r14
0x180023f44  jz      short loc_180023F51
0x180023f46  xor     edx, edx; dwFlags
0x180023f48  mov     rcx, r14; hCertStore
0x180023f4b  call    cs:__imp_CertCloseStore
0x180023f51  test    rsi, rsi
0x180023f54  jz      short loc_180023F6A
0x180023f56  call    cs:__imp_GetProcessHeap
0x180023f5c  mov     r8, rsi; lpMem
0x180023f5f  xor     edx, edx; dwFlags
0x180023f61  mov     rcx, rax; hHeap
0x180023f64  call    cs:__imp_HeapFree
0x180023f6a  mov     rcx, [rbp+hKey]; hKey
0x180023f6e  mov     [rbp+hKey], 0
0x180023f76  test    rcx, rcx
0x180023f79  jz      short loc_180023F81
0x180023f7b  call    cs:__imp_RegCloseKey
0x180023f81  mov     rsi, [rsp+40h+arg_8]
0x180023f86  mov     eax, ebx
0x180023f88  mov     rbx, [rsp+40h+arg_0]
0x180023f8d  add     rsp, 40h
0x180023f91  pop     r15
0x180023f93  pop     r14
0x180023f95  pop     r12
0x180023f97  pop     rdi
0x180023f98  pop     rbp
0x180023f99  retn
```
