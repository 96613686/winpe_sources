# EDL_IsDomainAllowed(_GUID const &,ushort const *,int *)

- ea: `0x1800641f0`
- end: `0x1800642ce`
- name: `?EDL_IsDomainAllowed@@YAJAEBU_GUID@@PEBGPEAH@Z`
- size: `222`
- prototype: `__int64 __fastcall(const struct _GUID *, LPCWSTR lpSubKey, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180063ad0`

## callees

- `0x180063fb0`
- `0x1800641f0`
- `0x18006441c`
- `0x180071b64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006426f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006428f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006426f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006428f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800642a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800642ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800642a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800642ad`

## pseudocode

```c
__int64 __fastcall EDL_IsDomainAllowed(const struct _GUID *a1, LPCWSTR lpSubKey, int *a3)
{
  unsigned int v6; // edx
  HKEY v7; // rcx
  HKEY phkResult; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  *a3 = 0;
  LODWORD(phkResult) = 0;
  if ( (unsigned int)EDL_DoesAllowedDomainsListExists(a1, (int *)&phkResult) || !(_DWORD)phkResult )
  {
    *a3 = IsPreApproved(a1);
  }
  else
  {
    hKey = 0;
    if ( !OpenAllowedDomainsKey(a1, v6, &hKey) )
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(hKey, L"*", 0, 0x20019u, &phkResult)
        || !RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
      {
        v7 = phkResult;
        *a3 = 1;
        RegCloseKey(v7);
      }
      RegCloseKey(hKey);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800641f0  mov     [rsp-18h+arg_0], rbx
0x1800641f5  push    rbp
0x1800641f6  push    rsi
0x1800641f7  push    rdi
0x1800641f8  mov     rbp, rsp
0x1800641fb  sub     rsp, 30h
0x1800641ff  mov     rsi, rdx
0x180064202  mov     dword ptr [r8], 0
0x180064209  lea     rdx, [rbp+arg_10]; int *
0x18006420d  mov     dword ptr [rbp+arg_10], 0
0x180064214  mov     rbx, r8
0x180064217  mov     rdi, rcx
0x18006421a  call    ?EDL_DoesAllowedDomainsListExists@@YAJAEBU_GUID@@PEAH@Z; EDL_DoesAllowedDomainsListExists(_GUID const &,int *)
0x18006421f  test    eax, eax
0x180064221  jnz     loc_1800642B5
0x180064227  cmp     dword ptr [rbp+arg_10], eax
0x18006422a  jz      loc_1800642B5
0x180064230  lea     r8, [rbp+hKey]; HKEY *
0x180064234  mov     [rbp+hKey], 0
0x18006423c  mov     rcx, rdi; struct _GUID *
0x18006423f  call    ?OpenAllowedDomainsKey@@YAJAEBU_GUID@@KPEAPEAUHKEY__@@@Z; OpenAllowedDomainsKey(_GUID const &,ulong,HKEY__ * *)
0x180064244  test    eax, eax
0x180064246  jnz     short loc_1800642BF
0x180064248  mov     rcx, [rbp+hKey]; hKey
0x18006424c  lea     rax, [rbp+arg_10]
0x180064250  mov     edi, 20019h
0x180064255  mov     [rbp+arg_10], 0
0x18006425d  mov     r9d, edi; samDesired
0x180064260  mov     [rsp+30h+phkResult], rax; phkResult
0x180064265  xor     r8d, r8d; ulOptions
0x180064268  lea     rdx, Value; "*"
0x18006426f  call    cs:__imp_RegOpenKeyExW
0x180064275  test    eax, eax
0x180064277  jz      short loc_180064299
0x180064279  mov     rcx, [rbp+hKey]; hKey
0x18006427d  lea     rax, [rbp+arg_10]
0x180064281  mov     r9d, edi; samDesired
0x180064284  mov     [rsp+30h+phkResult], rax; phkResult
0x180064289  xor     r8d, r8d; ulOptions
0x18006428c  mov     rdx, rsi; lpSubKey
0x18006428f  call    cs:__imp_RegOpenKeyExW
0x180064295  test    eax, eax
0x180064297  jnz     short loc_1800642A9
0x180064299  mov     rcx, [rbp+arg_10]; hKey
0x18006429d  mov     dword ptr [rbx], 1
0x1800642a3  call    cs:__imp_RegCloseKey
0x1800642a9  mov     rcx, [rbp+hKey]; hKey
0x1800642ad  call    cs:__imp_RegCloseKey
0x1800642b3  jmp     short loc_1800642BF
0x1800642b5  mov     rcx, rdi; struct _GUID *
0x1800642b8  call    ?IsPreApproved@@YAHAEBU_GUID@@@Z; IsPreApproved(_GUID const &)
0x1800642bd  mov     [rbx], eax
0x1800642bf  mov     rbx, [rsp+30h+arg_0]
0x1800642c4  xor     eax, eax
0x1800642c6  add     rsp, 30h
0x1800642ca  pop     rdi
0x1800642cb  pop     rsi
0x1800642cc  pop     rbp
0x1800642cd  retn
```
