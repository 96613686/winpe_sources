# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x18002d48c`
- end: `0x18002d62e`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180050558`

## callees

- `0x18000dd20`
- `0x18002d48c`
- `0x18002d998`
- `0x18006fdd8`
- `0x18006fff4`
- `0x180070114`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d5f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d5f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d531`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d5e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d531`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d5e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d541`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d541`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d4e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d4e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d50d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d60e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d50d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d60e`
- `CRYPT32!CertCloseStore` at `0x18002d5dd`
- `CRYPT32!CertCloseStore` at `0x18002d5dd`
- `CRYPT32!CertFreeCertificateContext` at `0x18002d5cd`
- `CRYPT32!CertFreeCertificateContext` at `0x18002d5cd`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18002d56f`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18002d56f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDeviceCertExpiryTime(const unsigned __int16 *a1, struct _FILETIME *a2)
{
  void *v4; // r14
  struct _CERT_CONTEXT *v5; // rdi
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  signed int String; // ebx
  HKEY v9; // rcx
  unsigned __int16 *v10; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rax
  HANDLE v13; // rax
  HKEY v14; // rcx
  void *v16; // [rsp+30h] [rbp-10h] BYREF
  struct _CERT_CONTEXT *v17; // [rsp+38h] [rbp-8h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  v4 = 0;
  v16 = 0;
  v5 = 0;
  v17 = 0;
  LODWORD(dwBytes) = 0;
  hKey = 0;
  v6 = (const WCHAR *)DMGetKnownRegPath(1);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
  String = v7;
  if ( v7 > 0 )
    String = (unsigned __int16)v7 | 0x80070000;
  if ( String >= 0 )
  {
    v10 = 0;
    String = ULongLongToULong(0x54u, (unsigned int *)&dwBytes);
    if ( String >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)dwBytes);
      v10 = v12;
      if ( v12 )
      {
        String = OmaDmRegistryGetString(hKey, a1, L"DMPCertThumbPrint", v12, 0x2Au);
        if ( String >= 0 )
        {
          ImpersonateForCertAccess(a1);
          String = GetInstalledCert(v10, &v16, (const struct _CERT_CONTEXT **)&v17, 0, 0);
          v5 = v17;
          v4 = v16;
          if ( String >= 0 )
          {
            a2->dwHighDateTime = v17->pCertInfo->NotAfter.dwHighDateTime;
            a2->dwLowDateTime = v5->pCertInfo->NotAfter.dwLowDateTime;
          }
        }
      }
      else
      {
        String = -2147024882;
      }
    }
    RevertToSelfFromCertAccess();
    if ( v5 )
      CertFreeCertificateContext(v5);
    if ( v4 )
      CertCloseStore(v4, 0);
    if ( v10 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v10);
    }
    v14 = hKey;
    hKey = 0;
    if ( v14 )
      RegCloseKey(v14);
  }
  else
  {
    v9 = hKey;
    hKey = 0;
    if ( v9 )
      RegCloseKey(v9);
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18002d48c  mov     [rsp-28h+arg_0], rbx
0x18002d491  mov     [rsp-28h+arg_8], rsi
0x18002d496  push    rbp
0x18002d497  push    rdi
0x18002d498  push    r12
0x18002d49a  push    r14
0x18002d49c  push    r15
0x18002d49e  mov     rbp, rsp
0x18002d4a1  sub     rsp, 40h
0x18002d4a5  mov     r12, rdx
0x18002d4a8  mov     r15, rcx
0x18002d4ab  xor     r14d, r14d
0x18002d4ae  mov     [rbp+var_10], r14
0x18002d4b2  xor     edi, edi
0x18002d4b4  mov     [rbp+var_8], rdi
0x18002d4b8  mov     dword ptr [rbp+dwBytes], edi
0x18002d4bb  mov     [rbp+hKey], rdi
0x18002d4bf  lea     ecx, [rdi+1]
0x18002d4c2  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18002d4c7  lea     rcx, [rbp+hKey]
0x18002d4cb  mov     [rsp+40h+phkResult], rcx; phkResult
0x18002d4d0  mov     r9d, 20019h; samDesired
0x18002d4d6  xor     r8d, r8d; ulOptions
0x18002d4d9  mov     rdx, rax; lpSubKey
0x18002d4dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d4e3  call    cs:__imp_RegOpenKeyExW
0x18002d4e9  mov     ebx, eax
0x18002d4eb  test    eax, eax
0x18002d4ed  jle     short loc_18002D4F8
0x18002d4ef  movzx   ebx, ax
0x18002d4f2  or      ebx, 80070000h
0x18002d4f8  test    ebx, ebx
0x18002d4fa  jns     short loc_18002D519
0x18002d4fc  mov     rcx, [rbp+hKey]; hKey
0x18002d500  mov     [rbp+hKey], 0
0x18002d508  test    rcx, rcx
0x18002d50b  jz      short loc_18002D514
0x18002d50d  call    cs:__imp_RegCloseKey
0x18002d513  nop
0x18002d514  jmp     loc_18002D615
0x18002d519  xor     esi, esi
0x18002d51b  lea     rdx, [rbp+dwBytes]; unsigned int *
0x18002d51f  lea     ecx, [rsi+54h]; unsigned __int64
0x18002d522  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002d527  mov     ebx, eax
0x18002d529  test    eax, eax
0x18002d52b  js      loc_18002D5C0
0x18002d531  call    cs:__imp_GetProcessHeap
0x18002d537  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x18002d53b  lea     edx, [rsi+8]; dwFlags
0x18002d53e  mov     rcx, rax; hHeap
0x18002d541  call    cs:__imp_HeapAlloc
0x18002d547  mov     rsi, rax
0x18002d54a  test    rax, rax
0x18002d54d  jnz     short loc_18002D556
0x18002d54f  mov     ebx, 8007000Eh
0x18002d554  jmp     short loc_18002D5C0
0x18002d556  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'
0x18002d55e  mov     r9, rsi
0x18002d561  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x18002d568  mov     rdx, r15
0x18002d56b  mov     rcx, [rbp+hKey]
0x18002d56f  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x18002d575  mov     ebx, eax
0x18002d577  test    eax, eax
0x18002d579  js      short loc_18002D5C0
0x18002d57b  mov     rcx, r15; unsigned __int16 *
0x18002d57e  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x18002d583  mov     [rsp+40h+phkResult], rdi; unsigned int *
0x18002d588  xor     r9d, r9d; int
0x18002d58b  lea     r8, [rbp+var_8]; struct _CERT_CONTEXT **
0x18002d58f  lea     rdx, [rbp+var_10]; void **
0x18002d593  mov     rcx, rsi; unsigned __int16 *
0x18002d596  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x18002d59b  mov     ebx, eax
0x18002d59d  mov     rdi, [rbp+var_8]
0x18002d5a1  mov     r14, [rbp+var_10]
0x18002d5a5  test    eax, eax
0x18002d5a7  js      short loc_18002D5C0
0x18002d5a9  mov     rax, [rdi+18h]
0x18002d5ad  mov     ecx, [rax+4Ch]
0x18002d5b0  mov     [r12+4], ecx
0x18002d5b5  mov     rax, [rdi+18h]
0x18002d5b9  mov     ecx, [rax+48h]
0x18002d5bc  mov     [r12], ecx
0x18002d5c0  call    ?RevertToSelfFromCertAccess@@YAXXZ; RevertToSelfFromCertAccess(void)
0x18002d5c5  test    rdi, rdi
0x18002d5c8  jz      short loc_18002D5D3
0x18002d5ca  mov     rcx, rdi; pCertContext
0x18002d5cd  call    cs:__imp_CertFreeCertificateContext
0x18002d5d3  test    r14, r14
0x18002d5d6  jz      short loc_18002D5E3
0x18002d5d8  xor     edx, edx; dwFlags
0x18002d5da  mov     rcx, r14; hCertStore
0x18002d5dd  call    cs:__imp_CertCloseStore
0x18002d5e3  test    rsi, rsi
0x18002d5e6  jz      short loc_18002D5FD
0x18002d5e8  call    cs:__imp_GetProcessHeap
0x18002d5ee  mov     rcx, rax; hHeap
0x18002d5f1  mov     r8, rsi; lpMem
0x18002d5f4  xor     edx, edx; dwFlags
0x18002d5f6  call    cs:__imp_HeapFree
0x18002d5fc  nop
0x18002d5fd  mov     rcx, [rbp+hKey]; hKey
0x18002d601  mov     [rbp+hKey], 0
0x18002d609  test    rcx, rcx
0x18002d60c  jz      short loc_18002D615
0x18002d60e  call    cs:__imp_RegCloseKey
0x18002d614  nop
0x18002d615  mov     eax, ebx
0x18002d617  mov     rbx, [rsp+40h+arg_0]
0x18002d61c  mov     rsi, [rsp+40h+arg_8]
0x18002d621  add     rsp, 40h
0x18002d625  pop     r15
0x18002d627  pop     r14
0x18002d629  pop     r12
0x18002d62b  pop     rdi
0x18002d62c  pop     rbp
0x18002d62d  retn
```
