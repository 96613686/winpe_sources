# IsCurrentBinaryEnabledForTracing(void)

- ea: `0x180038abc`
- end: `0x180038c72`
- name: `?IsCurrentBinaryEnabledForTracing@@YAHXZ`
- size: `438`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047ef0`

## callees

- `0x18002f278`
- `0x180038abc`
- `0x180042800`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038b59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038c4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038b59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038c4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038b87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038b87`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180038b10`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180038b10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038b3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038b3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038bbc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038bbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038c3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038c3b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180038c01`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180038c13`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180038c01`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180038c13`

## pseudocode

```c
__int64 IsCurrentBinaryEnabledForTracing(void)
{
  void *v0; // rsi
  unsigned int v1; // edi
  SIZE_T v2; // rax
  LSTATUS v3; // eax
  const unsigned __int16 *i; // rbx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF

  Type = 7;
  cbData = 1024;
  hKey = 0;
  v0 = 0;
  v1 = 0;
  if ( GetModuleFileNameW(0, Filename, 0x104u) < 0x104
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\OLE\\Tracing", 0, 0x20019u, &hKey) )
  {
    while ( 1 )
    {
      HeapFree(g_hHeap, 0, v0);
      v2 = 2 * ((unsigned __int64)(cbData + 1) >> 1);
      if ( !is_mul_ok((unsigned __int64)(cbData + 1) >> 1, 2u) )
        v2 = -1;
      v0 = HeapAlloc(g_hHeap, 0, v2);
      if ( !v0 )
        break;
      v3 = RegQueryValueExW(hKey, L"ExecutablesToTrace", 0, &Type, (LPBYTE)v0, &cbData);
      if ( v3 != 234 )
      {
        if ( !v3 && Type == 7 )
        {
          for ( i = (const unsigned __int16 *)v0; *i; i += v9 + 1 )
          {
            v9 = 0;
            if ( (int)StringCchLengthW(i, cbData, &v9) < 0 )
              break;
            if ( !lstrcmpiW(i, L"*") || !lstrcmpiW(i, Filename) )
            {
              v1 = 1;
              goto LABEL_16;
            }
          }
        }
        break;
      }
    }
  }
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  HeapFree(g_hHeap, 0, v0);
  return v1;
}

```

## disassembly

```asm
0x180038abc  push    rbp
0x180038abe  push    rbx
0x180038abf  push    rsi
0x180038ac0  push    rdi
0x180038ac1  push    r14
0x180038ac3  lea     rbp, [rsp-170h]
0x180038acb  sub     rsp, 270h
0x180038ad2  mov     rax, cs:__security_cookie
0x180038ad9  xor     rax, rsp
0x180038adc  mov     [rbp+190h+var_30], rax
0x180038ae3  xor     r14d, r14d
0x180038ae6  mov     [rsp+290h+Type], 7
0x180038aee  mov     ebx, 104h
0x180038af3  mov     [rsp+290h+cbData], 400h
0x180038afb  mov     r8d, ebx; nSize
0x180038afe  mov     [rsp+290h+hKey], r14
0x180038b03  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180038b08  xor     ecx, ecx; hModule
0x180038b0a  mov     esi, r14d
0x180038b0d  mov     edi, r14d
0x180038b10  call    cs:__imp_GetModuleFileNameW
0x180038b16  cmp     eax, ebx
0x180038b18  jnb     loc_180038C31
0x180038b1e  lea     rax, [rsp+290h+hKey]
0x180038b23  mov     r9d, 20019h; samDesired
0x180038b29  xor     r8d, r8d; ulOptions
0x180038b2c  mov     [rsp+290h+phkResult], rax; phkResult
0x180038b31  lea     rdx, SubKey; "Software\\Microsoft\\OLE\\Tracing"
0x180038b38  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038b3f  call    cs:__imp_RegOpenKeyExW
0x180038b45  test    eax, eax
0x180038b47  jnz     loc_180038C31
0x180038b4d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180038b54  mov     r8, rsi; lpMem
0x180038b57  xor     edx, edx; dwFlags
0x180038b59  call    cs:__imp_HeapFree
0x180038b5f  mov     ecx, [rsp+290h+cbData]
0x180038b63  mov     eax, 2
0x180038b68  inc     ecx
0x180038b6a  shr     rcx, 1
0x180038b6d  mul     rcx
0x180038b70  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180038b77  cmovb   rax, rcx
0x180038b7b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180038b82  mov     r8, rax; dwBytes
0x180038b85  xor     edx, edx; dwFlags
0x180038b87  call    cs:__imp_HeapAlloc
0x180038b8d  mov     rsi, rax
0x180038b90  test    rax, rax
0x180038b93  jz      loc_180038C31
0x180038b99  mov     rcx, [rsp+290h+hKey]; hKey
0x180038b9e  lea     rax, [rsp+290h+cbData]
0x180038ba3  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180038ba8  lea     r9, [rsp+290h+Type]; lpType
0x180038bad  xor     r8d, r8d; lpReserved
0x180038bb0  mov     [rsp+290h+phkResult], rsi; lpData
0x180038bb5  lea     rdx, ValueName; "ExecutablesToTrace"
0x180038bbc  call    cs:__imp_RegQueryValueExW
0x180038bc2  cmp     eax, 0EAh
0x180038bc7  jz      short loc_180038B4D
0x180038bc9  test    eax, eax
0x180038bcb  jnz     short loc_180038C31
0x180038bcd  cmp     [rsp+290h+Type], 7
0x180038bd2  jnz     short loc_180038C31
0x180038bd4  mov     rbx, rsi
0x180038bd7  cmp     [rbx], r14w
0x180038bdb  jz      short loc_180038C31
0x180038bdd  mov     edx, [rsp+290h+cbData]; unsigned __int64
0x180038be1  lea     r8, [rsp+290h+var_250]; unsigned __int64 *
0x180038be6  mov     rcx, rbx; unsigned __int16 *
0x180038be9  mov     [rsp+290h+var_250], r14
0x180038bee  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180038bf3  test    eax, eax
0x180038bf5  js      short loc_180038C31
0x180038bf7  lea     rdx, String2; "*"
0x180038bfe  mov     rcx, rbx; lpString1
0x180038c01  call    cs:__imp_lstrcmpiW
0x180038c07  test    eax, eax
0x180038c09  jz      short loc_180038C2C
0x180038c0b  lea     rdx, [rsp+290h+Filename]; lpString2
0x180038c10  mov     rcx, rbx; lpString1
0x180038c13  call    cs:__imp_lstrcmpiW
0x180038c19  test    eax, eax
0x180038c1b  jz      short loc_180038C2C
0x180038c1d  mov     rax, [rsp+290h+var_250]
0x180038c22  lea     rbx, [rbx+rax*2]
0x180038c26  add     rbx, 2
0x180038c2a  jmp     short loc_180038BD7
0x180038c2c  mov     edi, 1
0x180038c31  mov     rcx, [rsp+290h+hKey]; hKey
0x180038c36  test    rcx, rcx
0x180038c39  jz      short loc_180038C41
0x180038c3b  call    cs:__imp_RegCloseKey
0x180038c41  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180038c48  mov     r8, rsi; lpMem
0x180038c4b  xor     edx, edx; dwFlags
0x180038c4d  call    cs:__imp_HeapFree
0x180038c53  mov     eax, edi
0x180038c55  mov     rcx, [rbp+190h+var_30]
0x180038c5c  xor     rcx, rsp; StackCookie
0x180038c5f  call    __security_check_cookie
0x180038c64  add     rsp, 270h
0x180038c6b  pop     r14
0x180038c6d  pop     rdi
0x180038c6e  pop     rsi
0x180038c6f  pop     rbx
0x180038c70  pop     rbp
0x180038c71  retn
```
