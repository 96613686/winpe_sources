# FvepSetVolumeEncryptedCached

- ea: `0x1801f63cc`
- end: `0x1801f654b`
- name: `FvepSetVolumeEncryptedCached`
- size: `383`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801f6188`

## callees

- `0x1801f5938`
- `0x1801f5fe8`
- `0x1801f63cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801f6505`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801f6505`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801f64f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801f64f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f651a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6537`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f651a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6537`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801f64e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801f64e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801f6468`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801f64b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801f6468`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801f64b4`

## string_xrefs

- `0x1801f6489`: `Cache`

## pseudocode

```c
int __fastcall FvepSetVolumeEncryptedCached(STRSAFE_PCNZWCH pszSrc, int a2)
{
  int result; // eax
  WCHAR *v4; // rbx
  HANDLE ProcessHeap; // rax
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+28h] BYREF
  LPCWSTR lpValueName; // [rsp+88h] [rbp+30h]

  hKey = 0;
  phkResult = 0;
  lpValueName = 0;
  result = a2 != 0;
  Data = result;
  if ( pszSrc )
  {
    result = FvepIsNonDriverEncryptionStatusCachingAllowed();
    if ( result )
    {
      result = FvepConvertVolumeNameToCacheValueName(pszSrc);
      v4 = (WCHAR *)lpValueName;
      if ( result >= 0 )
      {
        result = RegCreateKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FveDetect",
                   0,
                   0,
                   0,
                   0xF003Fu,
                   0,
                   &hKey,
                   0);
        if ( !result )
        {
          result = RegCreateKeyExW(hKey, L"Cache", 0, 0, 1u, 0xF003Fu, 0, &phkResult, 0);
          if ( !result )
            result = RegSetValueExW(phkResult, v4, 0, 4u, (const BYTE *)&Data, 4u);
        }
      }
      if ( v4 )
      {
        ProcessHeap = GetProcessHeap();
        result = HeapFree(ProcessHeap, 0, v4);
      }
    }
    if ( phkResult )
    {
      result = RegCloseKey(phkResult);
      phkResult = 0;
    }
    if ( hKey )
      return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x1801f63cc  push    rbp
0x1801f63ce  push    rbx
0x1801f63cf  mov     rbp, rsp
0x1801f63d2  sub     rsp, 58h
0x1801f63d6  xor     eax, eax
0x1801f63d8  mov     [rbp+hKey], 0
0x1801f63e0  test    edx, edx
0x1801f63e2  mov     [rbp+arg_0], 0
0x1801f63ea  mov     rbx, rcx
0x1801f63ed  mov     [rbp+lpValueName], 0
0x1801f63f5  setnz   al
0x1801f63f8  mov     [rbp+Data], eax
0x1801f63fb  test    rcx, rcx
0x1801f63fe  jz      loc_1801F6543
0x1801f6404  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x1801f6409  test    eax, eax
0x1801f640b  jz      loc_1801F6511
0x1801f6411  lea     rdx, [rbp+lpValueName]
0x1801f6415  mov     rcx, rbx; pszSrc
0x1801f6418  call    FvepConvertVolumeNameToCacheValueName
0x1801f641d  mov     rbx, [rbp+lpValueName]
0x1801f6421  test    eax, eax
0x1801f6423  js      loc_1801F64EC
0x1801f6429  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1801f6432  lea     rax, [rbp+hKey]
0x1801f6436  mov     [rsp+58h+phkResult], rax; phkResult
0x1801f643b  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1801f6442  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801f644b  xor     r9d, r9d; lpClass
0x1801f644e  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1801f6456  xor     r8d, r8d; Reserved
0x1801f6459  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801f6460  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1801f6468  call    cs:__imp_RegCreateKeyExW
0x1801f646f  nop     dword ptr [rax+rax+00h]
0x1801f6474  test    eax, eax
0x1801f6476  jnz     short loc_1801F64EC
0x1801f6478  mov     rcx, [rbp+hKey]; hKey
0x1801f647c  lea     rax, [rbp+arg_0]
0x1801f6480  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1801f6489  lea     rdx, aCache; "Cache"
0x1801f6490  mov     [rsp+58h+phkResult], rax; phkResult
0x1801f6495  xor     r9d, r9d; lpClass
0x1801f6498  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801f64a1  xor     r8d, r8d; Reserved
0x1801f64a4  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1801f64ac  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1801f64b4  call    cs:__imp_RegCreateKeyExW
0x1801f64bb  nop     dword ptr [rax+rax+00h]
0x1801f64c0  test    eax, eax
0x1801f64c2  jnz     short loc_1801F64EC
0x1801f64c4  mov     rcx, [rbp+arg_0]; hKey
0x1801f64c8  lea     r9d, [rax+4]; dwType
0x1801f64cc  lea     rax, [rbp+Data]
0x1801f64d0  mov     [rsp+58h+samDesired], r9d; cbData
0x1801f64d5  xor     r8d, r8d; Reserved
0x1801f64d8  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1801f64dd  mov     rdx, rbx; lpValueName
0x1801f64e0  call    cs:__imp_RegSetValueExW
0x1801f64e7  nop     dword ptr [rax+rax+00h]
0x1801f64ec  test    rbx, rbx
0x1801f64ef  jz      short loc_1801F6511
0x1801f64f1  call    cs:__imp_GetProcessHeap
0x1801f64f8  nop     dword ptr [rax+rax+00h]
0x1801f64fd  mov     r8, rbx; lpMem
0x1801f6500  xor     edx, edx; dwFlags
0x1801f6502  mov     rcx, rax; hHeap
0x1801f6505  call    cs:__imp_HeapFree
0x1801f650c  nop     dword ptr [rax+rax+00h]
0x1801f6511  mov     rcx, [rbp+arg_0]; hKey
0x1801f6515  test    rcx, rcx
0x1801f6518  jz      short loc_1801F652E
0x1801f651a  call    cs:__imp_RegCloseKey
0x1801f6521  nop     dword ptr [rax+rax+00h]
0x1801f6526  mov     [rbp+arg_0], 0
0x1801f652e  mov     rcx, [rbp+hKey]; hKey
0x1801f6532  test    rcx, rcx
0x1801f6535  jz      short loc_1801F6543
0x1801f6537  call    cs:__imp_RegCloseKey
0x1801f653e  nop     dword ptr [rax+rax+00h]
0x1801f6543  add     rsp, 58h
0x1801f6547  pop     rbx
0x1801f6548  pop     rbp
0x1801f6549  retn
```
