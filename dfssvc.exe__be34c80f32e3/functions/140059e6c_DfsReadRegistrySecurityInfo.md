# DfsReadRegistrySecurityInfo

- ea: `0x140059e6c`
- end: `0x140059f03`
- name: `DfsReadRegistrySecurityInfo`
- size: `151`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021100`
- `0x140021e40`
- `0x140059f0c`

## callees

- `0x140059e6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140059e92`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140059ee6`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140059e92`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140059ee6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140059ebb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140059ebb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140059ea7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140059ea7`

## pseudocode

```c
LSTATUS __fastcall DfsReadRegistrySecurityInfo(HKEY hKey, void **a2)
{
  void *v2; // r8
  LSTATUS result; // eax
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  void *v8; // rax
  SIZE_T dwBytes; // [rsp+40h] [rbp+18h] BYREF

  v2 = *a2;
  LODWORD(dwBytes) = 0;
  result = RegGetKeySecurity(hKey, 0x80000007, v2, (LPDWORD)&dwBytes);
  if ( result == 122 )
  {
    v6 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 0, v6);
    *a2 = v8;
    if ( v8 )
      return RegGetKeySecurity(hKey, 0x80000007, v8, (LPDWORD)&dwBytes);
    else
      return 8;
  }
  return result;
}

```

## disassembly

```asm
0x140059e6c  mov     rax, rsp
0x140059e6f  mov     [rax+8], rbx
0x140059e73  mov     [rax+10h], rsi
0x140059e77  push    rdi
0x140059e78  sub     rsp, 20h
0x140059e7c  mov     r8, [rdx]; pSecurityDescriptor
0x140059e7f  lea     r9, [rax+18h]; lpcbSecurityDescriptor
0x140059e83  and     dword ptr [rax+18h], 0
0x140059e87  mov     rsi, rdx
0x140059e8a  mov     edx, 80000007h; SecurityInformation
0x140059e8f  mov     rdi, rcx
0x140059e92  call    cs:__imp_RegGetKeySecurity
0x140059e99  nop     dword ptr [rax+rax+00h]
0x140059e9e  cmp     eax, 7Ah ; 'z'
0x140059ea1  jnz     short loc_140059EF2
0x140059ea3  mov     ebx, dword ptr [rsp+28h+dwBytes]
0x140059ea7  call    cs:__imp_GetProcessHeap
0x140059eae  nop     dword ptr [rax+rax+00h]
0x140059eb3  mov     r8d, ebx; dwBytes
0x140059eb6  xor     edx, edx; dwFlags
0x140059eb8  mov     rcx, rax; hHeap
0x140059ebb  call    cs:__imp_HeapAlloc
0x140059ec2  nop     dword ptr [rax+rax+00h]
0x140059ec7  mov     [rsi], rax
0x140059eca  test    rax, rax
0x140059ecd  jnz     short loc_140059ED6
0x140059ecf  mov     eax, 8
0x140059ed4  jmp     short loc_140059EF2
0x140059ed6  lea     r9, [rsp+28h+dwBytes]; lpcbSecurityDescriptor
0x140059edb  mov     r8, rax; pSecurityDescriptor
0x140059ede  mov     edx, 80000007h; SecurityInformation
0x140059ee3  mov     rcx, rdi; hKey
0x140059ee6  call    cs:__imp_RegGetKeySecurity
0x140059eed  nop     dword ptr [rax+rax+00h]
0x140059ef2  mov     rbx, [rsp+28h+arg_0]
0x140059ef7  mov     rsi, [rsp+28h+arg_8]
0x140059efc  add     rsp, 20h
0x140059f00  pop     rdi
0x140059f01  retn
```
