# ReadBinary

- ea: `0x180034b9c`
- end: `0x180034cb5`
- name: `ReadBinary`
- size: `281`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180035440`
- `0x1800355e4`

## callees

- `0x1800327a8`
- `0x180034b9c`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180034c8e`
- `ntdll!RtlFreeHeap` at `0x180034c8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034bde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034c4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034bde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034c4d`

## string_xrefs

- `0x180034c5f`: `Failed to read the binary value from the registry`

## pseudocode

```c
__int64 __fastcall ReadBinary(HKEY hKey, LPCWSTR lpValueName, BYTE **a3, DWORD *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  const wchar_t *v10; // rdx
  __int64 v11; // rcx
  BYTE *lpData; // rdi
  const wchar_t *v13; // rdx
  DWORD cbData; // [rsp+30h] [rbp-48h] BYREF
  DWORD Type[17]; // [rsp+34h] [rbp-44h] BYREF

  Type[0] = 0;
  cbData = 0;
  v8 = RegQueryValueExW(hKey, lpValueName, 0, Type, 0, &cbData);
  v9 = v8;
  if ( v8 )
  {
    v10 = L"Failed to determine binary length";
    v11 = v8;
LABEL_5:
    LogError(v11, v10);
    return v9;
  }
  lpData = (BYTE *)SockAllocateHeapRoutine(SockPrivateHeap, 0, cbData);
  if ( !lpData )
  {
    v9 = 8;
    v11 = 8;
    v10 = L"Failed to allocate space for the binary value";
    goto LABEL_5;
  }
  v9 = RegQueryValueExW(hKey, lpValueName, 0, Type, lpData, &cbData);
  if ( v9 )
  {
    v13 = L"Failed to read the binary value from the registry";
  }
  else
  {
    if ( Type[0] == 3 )
    {
      *a4 = cbData;
      *a3 = lpData;
      return v9;
    }
    v9 = 1804;
    v13 = L"Expected REG_BINARY value, and got a different value type";
  }
  LogError(v9, v13);
  RtlFreeHeap(SockPrivateHeap, 0, lpData);
  return v9;
}

```

## disassembly

```asm
0x180034b9c  mov     r11, rsp
0x180034b9f  push    rbx
0x180034ba0  push    rbp
0x180034ba1  push    rsi
0x180034ba2  push    rdi
0x180034ba3  push    r14
0x180034ba5  push    r15
0x180034ba7  sub     rsp, 48h
0x180034bab  lea     rax, [r11-48h]
0x180034baf  mov     [rsp+78h+Type], 0
0x180034bb7  mov     rsi, r9
0x180034bba  mov     [r11-50h], rax
0x180034bbe  mov     r14, r8
0x180034bc1  mov     qword ptr [r11-58h], 0
0x180034bc9  lea     r9, [r11-44h]; lpType
0x180034bcd  mov     [rsp+78h+cbData], 0
0x180034bd5  xor     r8d, r8d; lpReserved
0x180034bd8  mov     rbp, rdx
0x180034bdb  mov     r15, rcx
0x180034bde  call    cs:__imp_RegQueryValueExW
0x180034be5  nop     dword ptr [rax+rax+00h]
0x180034bea  mov     ebx, eax
0x180034bec  test    eax, eax
0x180034bee  jz      short loc_180034BFB
0x180034bf0  lea     rdx, aFailedToDeterm; "Failed to determine binary length"
0x180034bf7  mov     ecx, eax
0x180034bf9  jmp     short loc_180034C29
0x180034bfb  mov     r8d, [rsp+78h+cbData]
0x180034c00  xor     edx, edx
0x180034c02  mov     rcx, cs:SockPrivateHeap
0x180034c09  mov     rax, cs:SockAllocateHeapRoutine
0x180034c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c15  mov     rdi, rax
0x180034c18  test    rax, rax
0x180034c1b  jnz     short loc_180034C30
0x180034c1d  lea     ebx, [rax+8]
0x180034c20  mov     ecx, ebx
0x180034c22  lea     rdx, aFailedToAlloca_6; "Failed to allocate space for the binary"...
0x180034c29  call    LogError
0x180034c2e  jmp     short loc_180034CA5
0x180034c30  lea     rax, [rsp+78h+cbData]
0x180034c35  xor     r8d, r8d; lpReserved
0x180034c38  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180034c3d  lea     r9, [rsp+78h+Type]; lpType
0x180034c42  mov     rdx, rbp; lpValueName
0x180034c45  mov     [rsp+78h+lpData], rdi; lpData
0x180034c4a  mov     rcx, r15; hKey
0x180034c4d  call    cs:__imp_RegQueryValueExW
0x180034c54  nop     dword ptr [rax+rax+00h]
0x180034c59  mov     ebx, eax
0x180034c5b  test    eax, eax
0x180034c5d  jz      short loc_180034C68
0x180034c5f  lea     rdx, aFailedToReadTh_4; "Failed to read the binary value from th"...
0x180034c66  jmp     short loc_180034C7B
0x180034c68  cmp     [rsp+78h+Type], 3
0x180034c6d  jz      short loc_180034C9C
0x180034c6f  mov     ebx, 70Ch
0x180034c74  lea     rdx, aExpectedRegBin; "Expected REG_BINARY value, and got a di"...
0x180034c7b  mov     ecx, ebx
0x180034c7d  call    LogError
0x180034c82  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180034c89  mov     r8, rdi; P
0x180034c8c  xor     edx, edx; Flags
0x180034c8e  call    cs:__imp_RtlFreeHeap
0x180034c95  nop     dword ptr [rax+rax+00h]
0x180034c9a  jmp     short loc_180034CA5
0x180034c9c  mov     eax, [rsp+78h+cbData]
0x180034ca0  mov     [rsi], eax
0x180034ca2  mov     [r14], rdi
0x180034ca5  mov     eax, ebx
0x180034ca7  add     rsp, 48h
0x180034cab  pop     r15
0x180034cad  pop     r14
0x180034caf  pop     rdi
0x180034cb0  pop     rsi
0x180034cb1  pop     rbp
0x180034cb2  pop     rbx
0x180034cb3  retn
```
