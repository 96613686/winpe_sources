# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x1800cddfc`
- end: `0x1800cdfe4`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18001b900`

## callees

- `0x180015e90`
- `0x18002201c`
- `0x1800cddfc`
- `0x1800cdfec`
- `0x1800ce4a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cdec3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cdec3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cdf9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cdf9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cdead`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cdf8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cdead`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cdf8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cde83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cdfbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cde83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cdfbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cde53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cde53`
- `CRYPT32!CertCloseStore` at `0x1800cdf7a`
- `CRYPT32!CertCloseStore` at `0x1800cdf7a`
- `CRYPT32!CertFreeCertificateContext` at `0x1800cdf64`
- `CRYPT32!CertFreeCertificateContext` at `0x1800cdf64`
- `DMCmnUtils!DmRevertToSelf` at `0x1800cdf49`
- `DMCmnUtils!DmRevertToSelf` at `0x1800cdf49`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800cdef7`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800cdef7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDeviceCertExpiryTime(unsigned __int16 *a1, struct _FILETIME *a2)
{
  void *v4; // r14
  struct _CERT_CONTEXT *v5; // rsi
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  signed int String; // ebx
  HKEY v9; // rcx
  unsigned __int16 *v10; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rax
  int v13; // r9d
  HANDLE v14; // rax
  HKEY v15; // rcx
  unsigned int *phkResult; // [rsp+20h] [rbp-20h]
  void *v18; // [rsp+30h] [rbp-10h] BYREF
  struct _CERT_CONTEXT *v19; // [rsp+38h] [rbp-8h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  v4 = 0;
  v18 = 0;
  v5 = 0;
  v19 = 0;
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
          String = GetInstalledCert(v10, &v18, (const struct _CERT_CONTEXT **)&v19, v13, phkResult);
          v5 = v19;
          v4 = v18;
          if ( String >= 0 )
            *a2 = v19->pCertInfo->NotAfter;
        }
      }
      else
      {
        String = -2147024882;
      }
    }
    if ( byte_180157D64 )
    {
      DmRevertToSelf();
      byte_180157D64 = 0;
    }
    if ( v5 )
      CertFreeCertificateContext(v5);
    if ( v4 )
      CertCloseStore(v4, 0);
    if ( v10 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v10);
    }
    v15 = hKey;
    hKey = 0;
    if ( v15 )
      RegCloseKey(v15);
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
0x1800cddfc  mov     [rsp-28h+arg_0], rbx
0x1800cde01  mov     [rsp-28h+arg_8], rsi
0x1800cde06  push    rbp
0x1800cde07  push    rdi
0x1800cde08  push    r12
0x1800cde0a  push    r14
0x1800cde0c  push    r15
0x1800cde0e  mov     rbp, rsp
0x1800cde11  sub     rsp, 40h
0x1800cde15  mov     r15, rdx
0x1800cde18  mov     r12, rcx
0x1800cde1b  xor     r14d, r14d
0x1800cde1e  mov     [rbp+var_10], r14
0x1800cde22  xor     esi, esi
0x1800cde24  mov     [rbp+var_8], rsi
0x1800cde28  mov     dword ptr [rbp+dwBytes], esi
0x1800cde2b  mov     [rbp+hKey], rsi
0x1800cde2f  lea     ecx, [rsi+1]
0x1800cde32  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800cde37  lea     rcx, [rbp+hKey]
0x1800cde3b  mov     [rsp+40h+phkResult], rcx; phkResult
0x1800cde40  mov     r9d, 20019h; samDesired
0x1800cde46  xor     r8d, r8d; ulOptions
0x1800cde49  mov     rdx, rax; lpSubKey
0x1800cde4c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cde53  call    cs:__imp_RegOpenKeyExW
0x1800cde5a  nop     dword ptr [rax+rax+00h]
0x1800cde5f  mov     ebx, eax
0x1800cde61  test    eax, eax
0x1800cde63  jle     short loc_1800CDE6E
0x1800cde65  movzx   ebx, ax
0x1800cde68  or      ebx, 80070000h
0x1800cde6e  test    ebx, ebx
0x1800cde70  jns     short loc_1800CDE95
0x1800cde72  mov     rcx, [rbp+hKey]; hKey
0x1800cde76  mov     [rbp+hKey], 0
0x1800cde7e  test    rcx, rcx
0x1800cde81  jz      short loc_1800CDE90
0x1800cde83  call    cs:__imp_RegCloseKey
0x1800cde8a  nop     dword ptr [rax+rax+00h]
0x1800cde8f  nop
0x1800cde90  jmp     loc_1800CDFCA
0x1800cde95  xor     edi, edi
0x1800cde97  lea     rdx, [rbp+dwBytes]; unsigned int *
0x1800cde9b  lea     ecx, [rdi+54h]; unsigned __int64
0x1800cde9e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800cdea3  mov     ebx, eax
0x1800cdea5  test    eax, eax
0x1800cdea7  js      loc_1800CDF40
0x1800cdead  call    cs:__imp_GetProcessHeap
0x1800cdeb4  nop     dword ptr [rax+rax+00h]
0x1800cdeb9  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x1800cdebd  lea     edx, [rdi+8]; dwFlags
0x1800cdec0  mov     rcx, rax; hHeap
0x1800cdec3  call    cs:__imp_HeapAlloc
0x1800cdeca  nop     dword ptr [rax+rax+00h]
0x1800cdecf  mov     rdi, rax
0x1800cded2  test    rax, rax
0x1800cded5  jnz     short loc_1800CDEDE
0x1800cded7  mov     ebx, 8007000Eh
0x1800cdedc  jmp     short loc_1800CDF40
0x1800cdede  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'; unsigned int *
0x1800cdee6  mov     r9, rdi
0x1800cdee9  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x1800cdef0  mov     rdx, r12
0x1800cdef3  mov     rcx, [rbp+hKey]
0x1800cdef7  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x1800cdefe  nop     dword ptr [rax+rax+00h]
0x1800cdf03  mov     ebx, eax
0x1800cdf05  test    eax, eax
0x1800cdf07  js      short loc_1800CDF40
0x1800cdf09  mov     rcx, r12; unsigned __int16 *
0x1800cdf0c  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x1800cdf11  lea     r8, [rbp+var_8]; struct _CERT_CONTEXT **
0x1800cdf15  lea     rdx, [rbp+var_10]; void **
0x1800cdf19  mov     rcx, rdi; unsigned __int16 *
0x1800cdf1c  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x1800cdf21  mov     ebx, eax
0x1800cdf23  mov     rsi, [rbp+var_8]
0x1800cdf27  mov     r14, [rbp+var_10]
0x1800cdf2b  test    eax, eax
0x1800cdf2d  js      short loc_1800CDF40
0x1800cdf2f  mov     rcx, [rsi+18h]
0x1800cdf33  mov     eax, [rcx+4Ch]
0x1800cdf36  mov     [r15+4], eax
0x1800cdf3a  mov     eax, [rcx+48h]
0x1800cdf3d  mov     [r15], eax
0x1800cdf40  cmp     cs:byte_180157D64, 0
0x1800cdf47  jz      short loc_1800CDF5C
0x1800cdf49  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x1800cdf50  nop     dword ptr [rax+rax+00h]
0x1800cdf55  mov     cs:byte_180157D64, 0
0x1800cdf5c  test    rsi, rsi
0x1800cdf5f  jz      short loc_1800CDF70
0x1800cdf61  mov     rcx, rsi; pCertContext
0x1800cdf64  call    cs:__imp_CertFreeCertificateContext
0x1800cdf6b  nop     dword ptr [rax+rax+00h]
0x1800cdf70  test    r14, r14
0x1800cdf73  jz      short loc_1800CDF86
0x1800cdf75  xor     edx, edx; dwFlags
0x1800cdf77  mov     rcx, r14; hCertStore
0x1800cdf7a  call    cs:__imp_CertCloseStore
0x1800cdf81  nop     dword ptr [rax+rax+00h]
0x1800cdf86  test    rdi, rdi
0x1800cdf89  jz      short loc_1800CDFAC
0x1800cdf8b  call    cs:__imp_GetProcessHeap
0x1800cdf92  nop     dword ptr [rax+rax+00h]
0x1800cdf97  mov     rcx, rax; hHeap
0x1800cdf9a  mov     r8, rdi; lpMem
0x1800cdf9d  xor     edx, edx; dwFlags
0x1800cdf9f  call    cs:__imp_HeapFree
0x1800cdfa6  nop     dword ptr [rax+rax+00h]
0x1800cdfab  nop
0x1800cdfac  mov     rcx, [rbp+hKey]; hKey
0x1800cdfb0  mov     [rbp+hKey], 0
0x1800cdfb8  test    rcx, rcx
0x1800cdfbb  jz      short loc_1800CDFCA
0x1800cdfbd  call    cs:__imp_RegCloseKey
0x1800cdfc4  nop     dword ptr [rax+rax+00h]
0x1800cdfc9  nop
0x1800cdfca  mov     eax, ebx
0x1800cdfcc  mov     rbx, [rsp+40h+arg_0]
0x1800cdfd1  mov     rsi, [rsp+40h+arg_8]
0x1800cdfd6  add     rsp, 40h
0x1800cdfda  pop     r15
0x1800cdfdc  pop     r14
0x1800cdfde  pop     r12
0x1800cdfe0  pop     rdi
0x1800cdfe1  pop     rbp
0x1800cdfe2  retn
```
