# CProvisioningNode::OpenProvisioningCertStore(void * *)

- ea: `0x180009b80`
- end: `0x180009c5d`
- name: `?OpenProvisioningCertStore@CProvisioningNode@@CAJPEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d78`
- `0x18000dcb0`
- `0x18000ed40`
- `0x18000f1a0`

## callees

- `0x180006954`
- `0x180009b80`
- `0x180009eb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009be8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009be8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bb3`
- `CRYPT32!CertOpenStore` at `0x180009c14`
- `CRYPT32!CertOpenStore` at `0x180009c14`

## pseudocode

```c
__int64 __fastcall CProvisioningNode::OpenProvisioningCertStore(void **a1)
{
  unsigned int v2; // eax
  int LastError; // eax
  unsigned int v4; // ebx
  HCERTSTORE v6; // rax
  const char *v7; // r9
  HKEY v8; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\TrustedProvisioners", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x1A,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provisioningnode.cpp",
                  (const char *)v2,
                  phkResult);
LABEL_3:
    v4 = LastError;
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  v6 = CertOpenStore((LPCSTR)4, 0x10001u, 0, 0x4000u, hKey);
  if ( !v6 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x20,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provisioningnode.cpp",
                  v7);
    goto LABEL_3;
  }
  v8 = hKey;
  *a1 = v6;
  if ( v8 )
    RegCloseKey(v8);
  return 0;
}

```

## disassembly

```asm
0x180009b80  push    rbx
0x180009b82  sub     rsp, 30h
0x180009b86  mov     rbx, rcx
0x180009b89  mov     [rsp+38h+hKey], 0
0x180009b92  lea     rax, [rsp+38h+hKey]
0x180009b97  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009b9e  mov     r9d, 20019h; samDesired
0x180009ba4  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x180009ba9  xor     r8d, r8d; ulOptions
0x180009bac  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Provisioning\\Trus"...
0x180009bb3  call    cs:__imp_RegOpenKeyExW
0x180009bba  nop     dword ptr [rax+rax+00h]
0x180009bbf  test    eax, eax
0x180009bc1  jz      short loc_180009BF8
0x180009bc3  mov     rcx, [rsp+38h]; this
0x180009bc8  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\provcsp\\provi"...
0x180009bcf  mov     r9d, eax; char *
0x180009bd2  mov     edx, 1Ah; void *
0x180009bd7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009bdc  mov     rcx, [rsp+38h+hKey]; hKey
0x180009be1  mov     ebx, eax
0x180009be3  test    rcx, rcx
0x180009be6  jz      short loc_180009BF4
0x180009be8  call    cs:__imp_RegCloseKey
0x180009bef  nop     dword ptr [rax+rax+00h]
0x180009bf4  mov     eax, ebx
0x180009bf6  jmp     short loc_180009C56
0x180009bf8  mov     rax, [rsp+38h+hKey]
0x180009bfd  xor     r8d, r8d; hCryptProv
0x180009c00  mov     r9d, 4000h; dwFlags
0x180009c06  mov     qword ptr [rsp+38h+phkResult], rax; pvPara
0x180009c0b  mov     edx, 10001h; dwEncodingType
0x180009c10  lea     ecx, [r8+4]; lpszStoreProvider
0x180009c14  call    cs:__imp_CertOpenStore
0x180009c1b  nop     dword ptr [rax+rax+00h]
0x180009c20  test    rax, rax
0x180009c23  jnz     short loc_180009C3B
0x180009c25  mov     rcx, [rsp+38h]; this
0x180009c2a  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\provcsp\\provi"...
0x180009c31  lea     edx, [rax+20h]; void *
0x180009c34  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009c39  jmp     short loc_180009BDC
0x180009c3b  mov     rcx, [rsp+38h+hKey]; hKey
0x180009c40  mov     [rbx], rax
0x180009c43  test    rcx, rcx
0x180009c46  jz      short loc_180009C54
0x180009c48  call    cs:__imp_RegCloseKey
0x180009c4f  nop     dword ptr [rax+rax+00h]
0x180009c54  xor     eax, eax
0x180009c56  add     rsp, 30h
0x180009c5a  pop     rbx
0x180009c5b  retn
```
