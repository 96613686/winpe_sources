# FvepSetVolumeEncryptedCached

- ea: `0x180171220`
- end: `0x180171374`
- name: `FvepSetVolumeEncryptedCached`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180171014`

## callees

- `0x180170808`
- `0x180170e8c`
- `0x180171220`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180171333`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180171333`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180171341`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180171341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180171350`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180171367`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180171350`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180171367`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180171328`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180171328`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801712bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180171302`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801712bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180171302`

## string_xrefs

- `0x1801712d7`: `Cache`

## pseudocode

```c
int __fastcall FvepSetVolumeEncryptedCached(__int64 a1, int a2)
{
  int result; // eax
  WCHAR *v4; // rbx
  HANDLE ProcessHeap; // rax
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+28h] BYREF
  LPCWSTR lpValueName; // [rsp+88h] [rbp+30h] BYREF

  hKey = 0;
  phkResult = 0;
  lpValueName = 0;
  result = a2 != 0;
  Data = result;
  if ( a1 )
  {
    result = FvepIsNonDriverEncryptionStatusCachingAllowed();
    if ( result )
    {
      result = FvepConvertVolumeNameToCacheValueName(a1, &lpValueName);
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
0x180171220  push    rbp
0x180171222  push    rbx
0x180171223  mov     rbp, rsp
0x180171226  sub     rsp, 58h
0x18017122a  xor     eax, eax
0x18017122c  mov     [rbp+hKey], 0
0x180171234  test    edx, edx
0x180171236  mov     [rbp+arg_0], 0
0x18017123e  mov     rbx, rcx
0x180171241  mov     [rbp+lpValueName], 0
0x180171249  setnz   al
0x18017124c  mov     [rbp+Data], eax
0x18017124f  test    rcx, rcx
0x180171252  jz      loc_18017136D
0x180171258  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x18017125d  test    eax, eax
0x18017125f  jz      loc_180171347
0x180171265  lea     rdx, [rbp+lpValueName]
0x180171269  mov     rcx, rbx
0x18017126c  call    FvepConvertVolumeNameToCacheValueName
0x180171271  mov     rbx, [rbp+lpValueName]
0x180171275  test    eax, eax
0x180171277  js      loc_18017132E
0x18017127d  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180171286  lea     rax, [rbp+hKey]
0x18017128a  mov     [rsp+58h+phkResult], rax; phkResult
0x18017128f  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180171296  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18017129f  xor     r9d, r9d; lpClass
0x1801712a2  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1801712aa  xor     r8d, r8d; Reserved
0x1801712ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801712b4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1801712bc  call    cs:__imp_RegCreateKeyExW
0x1801712c2  test    eax, eax
0x1801712c4  jnz     short loc_18017132E
0x1801712c6  mov     rcx, [rbp+hKey]; hKey
0x1801712ca  lea     rax, [rbp+arg_0]
0x1801712ce  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1801712d7  lea     rdx, aCache_0; "Cache"
0x1801712de  mov     [rsp+58h+phkResult], rax; phkResult
0x1801712e3  xor     r9d, r9d; lpClass
0x1801712e6  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801712ef  xor     r8d, r8d; Reserved
0x1801712f2  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1801712fa  mov     [rsp+58h+dwOptions], 1; dwOptions
0x180171302  call    cs:__imp_RegCreateKeyExW
0x180171308  test    eax, eax
0x18017130a  jnz     short loc_18017132E
0x18017130c  mov     rcx, [rbp+arg_0]; hKey
0x180171310  lea     r9d, [rax+4]; dwType
0x180171314  lea     rax, [rbp+Data]
0x180171318  mov     [rsp+58h+samDesired], r9d; cbData
0x18017131d  xor     r8d, r8d; Reserved
0x180171320  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180171325  mov     rdx, rbx; lpValueName
0x180171328  call    cs:__imp_RegSetValueExW
0x18017132e  test    rbx, rbx
0x180171331  jz      short loc_180171347
0x180171333  call    cs:__imp_GetProcessHeap
0x180171339  mov     r8, rbx; lpMem
0x18017133c  xor     edx, edx; dwFlags
0x18017133e  mov     rcx, rax; hHeap
0x180171341  call    cs:__imp_HeapFree
0x180171347  mov     rcx, [rbp+arg_0]; hKey
0x18017134b  test    rcx, rcx
0x18017134e  jz      short loc_18017135E
0x180171350  call    cs:__imp_RegCloseKey
0x180171356  mov     [rbp+arg_0], 0
0x18017135e  mov     rcx, [rbp+hKey]; hKey
0x180171362  test    rcx, rcx
0x180171365  jz      short loc_18017136D
0x180171367  call    cs:__imp_RegCloseKey
0x18017136d  add     rsp, 58h
0x180171371  pop     rbx
0x180171372  pop     rbp
0x180171373  retn
```
