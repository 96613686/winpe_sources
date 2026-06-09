# ReadMultiSz

- ea: `0x180034da4`
- end: `0x180034ebe`
- name: `ReadMultiSz`
- size: `282`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800328c0`
- `0x180034ec4`

## callees

- `0x1800327a8`
- `0x180034da4`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180034e97`
- `ntdll!RtlFreeHeap` at `0x180034e97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034de7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034e56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034de7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034e56`

## string_xrefs

- `0x180034e2b`: `Failed to allocate memory for string value in registry`
- `0x180034e68`: `Failed to read the string value`

## pseudocode

```c
__int64 __fastcall ReadMultiSz(HKEY hKey, LPCWSTR lpValueName, BYTE **a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  const wchar_t *v8; // rdx
  __int64 v9; // rcx
  BYTE *lpData; // rdi
  const wchar_t *v11; // rdx
  DWORD Type[10]; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF

  Type[0] = 0;
  cbData = 0;
  v6 = RegQueryValueExW(hKey, lpValueName, 0, Type, 0, &cbData);
  v7 = v6;
  if ( v6 )
  {
    v8 = L"Failed to determine value length of string value";
    v9 = v6;
LABEL_5:
    LogError(v9, v8);
    return v7;
  }
  lpData = (BYTE *)SockAllocateHeapRoutine(SockPrivateHeap, 0, cbData);
  if ( !lpData )
  {
    v7 = 8;
    v9 = 8;
    v8 = L"Failed to allocate memory for string value in registry";
    goto LABEL_5;
  }
  v7 = RegQueryValueExW(hKey, lpValueName, 0, Type, lpData, &cbData);
  if ( v7 )
  {
    v11 = L"Failed to read the string value";
  }
  else
  {
    if ( Type[0] == 7 )
    {
      *a3 = lpData;
      return v7;
    }
    v7 = 1804;
    v11 = L"Expected REG_MULTI_SZ value, and got a different value type";
  }
  LogError(v7, v11);
  RtlFreeHeap(SockPrivateHeap, 0, lpData);
  return v7;
}

```

## disassembly

```asm
0x180034da4  mov     r11, rsp
0x180034da7  mov     [r11+8], rbx
0x180034dab  mov     [r11+10h], rbp
0x180034daf  push    rsi
0x180034db0  push    rdi
0x180034db1  push    r14
0x180034db3  sub     rsp, 40h
0x180034db7  lea     rax, [r11+20h]
0x180034dbb  mov     [rsp+58h+Type], 0
0x180034dc3  mov     rsi, r8
0x180034dc6  mov     [r11-30h], rax
0x180034dca  lea     r9, [r11-28h]; lpType
0x180034dce  mov     qword ptr [r11-38h], 0
0x180034dd6  xor     r8d, r8d; lpReserved
0x180034dd9  mov     [rsp+58h+cbData], 0
0x180034de1  mov     rbp, rdx
0x180034de4  mov     r14, rcx
0x180034de7  call    cs:__imp_RegQueryValueExW
0x180034dee  nop     dword ptr [rax+rax+00h]
0x180034df3  mov     ebx, eax
0x180034df5  test    eax, eax
0x180034df7  jz      short loc_180034E04
0x180034df9  lea     rdx, aFailedToDeterm_0; "Failed to determine value length of str"...
0x180034e00  mov     ecx, eax
0x180034e02  jmp     short loc_180034E32
0x180034e04  mov     r8d, [rsp+58h+cbData]
0x180034e09  xor     edx, edx
0x180034e0b  mov     rcx, cs:SockPrivateHeap
0x180034e12  mov     rax, cs:SockAllocateHeapRoutine
0x180034e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e1e  mov     rdi, rax
0x180034e21  test    rax, rax
0x180034e24  jnz     short loc_180034E39
0x180034e26  lea     ebx, [rax+8]
0x180034e29  mov     ecx, ebx
0x180034e2b  lea     rdx, aFailedToAlloca_9; "Failed to allocate memory for string va"...
0x180034e32  call    LogError
0x180034e37  jmp     short loc_180034EA8
0x180034e39  lea     rax, [rsp+58h+cbData]
0x180034e3e  xor     r8d, r8d; lpReserved
0x180034e41  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180034e46  lea     r9, [rsp+58h+Type]; lpType
0x180034e4b  mov     rdx, rbp; lpValueName
0x180034e4e  mov     [rsp+58h+lpData], rdi; lpData
0x180034e53  mov     rcx, r14; hKey
0x180034e56  call    cs:__imp_RegQueryValueExW
0x180034e5d  nop     dword ptr [rax+rax+00h]
0x180034e62  mov     ebx, eax
0x180034e64  test    eax, eax
0x180034e66  jz      short loc_180034E71
0x180034e68  lea     rdx, aFailedToReadTh_6; "Failed to read the string value"
0x180034e6f  jmp     short loc_180034E84
0x180034e71  cmp     [rsp+58h+Type], 7
0x180034e76  jz      short loc_180034EA5
0x180034e78  mov     ebx, 70Ch
0x180034e7d  lea     rdx, aExpectedRegMul; "Expected REG_MULTI_SZ value, and got a "...
0x180034e84  mov     ecx, ebx
0x180034e86  call    LogError
0x180034e8b  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180034e92  mov     r8, rdi; P
0x180034e95  xor     edx, edx; Flags
0x180034e97  call    cs:__imp_RtlFreeHeap
0x180034e9e  nop     dword ptr [rax+rax+00h]
0x180034ea3  jmp     short loc_180034EA8
0x180034ea5  mov     [rsi], rdi
0x180034ea8  mov     rbp, [rsp+58h+arg_8]
0x180034ead  mov     eax, ebx
0x180034eaf  mov     rbx, [rsp+58h+arg_0]
0x180034eb4  add     rsp, 40h
0x180034eb8  pop     r14
0x180034eba  pop     rdi
0x180034ebb  pop     rsi
0x180034ebc  retn
```
