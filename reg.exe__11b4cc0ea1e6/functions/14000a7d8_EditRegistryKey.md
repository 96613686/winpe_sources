# EditRegistryKey

- ea: `0x14000a7d8`
- end: `0x14000a92c`
- name: `EditRegistryKey`
- size: `340`
- prototype: `__int64 __fastcall(PHKEY phkResult, LPCWSTR lpString2)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000a934`
- `0x14000b640`

## callees

- `0x14000a7d8`
- `0x14000c348`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a917`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a917`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000a8f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000a8f5`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x14000a820`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x14000a820`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x14000a800`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x14000a800`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x14000a83c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x14000a83c`

## pseudocode

```c
__int64 __fastcall EditRegistryKey(PHKEY phkResult, WCHAR *lpString2, int a3, REGSAM a4)
{
  WCHAR v6; // r12
  PWSTR v9; // rax
  const WCHAR *v10; // rbx
  unsigned int v11; // edi
  unsigned int v12; // edi
  HKEY v14; // rcx
  int v15; // esi

  v6 = 0;
  v9 = StrChrW(lpString2, 0x5Cu);
  v10 = v9;
  if ( v9 )
  {
    v6 = *v9;
    *v9 = 0;
    v10 = v9 + 1;
  }
  CharUpperW(lpString2);
  v11 = 0;
  while ( lstrcmpW((&g_RegistryRoots)[2 * v11], lpString2) )
  {
    if ( ++v11 >= 6 )
      goto LABEL_6;
  }
  v14 = (HKEY)*(&g_RegistryRoots + 2 * v11 + 1);
  if ( !v14 )
  {
LABEL_6:
    v12 = 1010;
    goto LABEL_7;
  }
  v12 = 1011;
  if ( a3 )
  {
    v15 = a3 - 1;
    if ( v15 )
    {
      if ( v15 == 1 )
      {
        RegDeleteKeyRecursive(v14, v10, a4);
        v12 = 0;
        *phkResult = 0;
      }
    }
    else
    {
      if ( (unsigned __int64)v14 + 2147483646 <= 1 && !v10 )
        return 0;
      v12 = RegCreateKeyExW(v14, v10, 0, 0, 0, a4 | 0x2001F, 0, phkResult, 0) != 0 ? 0x3F3 : 0;
    }
  }
  else if ( !RegOpenKeyExW(v14, v10, 0, a4 | 9, phkResult) )
  {
    v12 = 0;
  }
LABEL_7:
  if ( v10 )
    *((_WORD *)v10 - 1) = v6;
  return v12;
}

```

## disassembly

```asm
0x14000a7d8  push    rbx
0x14000a7da  push    rbp
0x14000a7db  push    rsi
0x14000a7dc  push    rdi
0x14000a7dd  push    r12
0x14000a7df  push    r13
0x14000a7e1  push    r14
0x14000a7e3  push    r15
0x14000a7e5  sub     rsp, 58h
0x14000a7e9  mov     r15, rdx
0x14000a7ec  mov     r13, rcx
0x14000a7ef  xor     r12d, r12d
0x14000a7f2  mov     rcx, r15; pszStart
0x14000a7f5  mov     ebp, r9d
0x14000a7f8  mov     esi, r8d
0x14000a7fb  lea     edx, [r12+5Ch]; wMatch
0x14000a800  call    cs:__imp_StrChrW
0x14000a806  mov     rbx, rax
0x14000a809  test    rax, rax
0x14000a80c  jz      short loc_14000A81D
0x14000a80e  movzx   r12d, word ptr [rax]
0x14000a812  xor     r8d, r8d
0x14000a815  mov     [rax], r8w
0x14000a819  add     rbx, 2
0x14000a81d  mov     rcx, r15; lpsz
0x14000a820  call    cs:__imp_CharUpperW
0x14000a826  xor     edi, edi
0x14000a828  lea     rax, g_RegistryRoots
0x14000a82f  mov     r14d, edi
0x14000a832  mov     rdx, r15; lpString2
0x14000a835  add     r14, r14
0x14000a838  mov     rcx, [rax+r14*8]; lpString1
0x14000a83c  call    cs:__imp_lstrcmpW
0x14000a842  test    eax, eax
0x14000a844  jz      short loc_14000A876
0x14000a846  inc     edi
0x14000a848  lea     rax, g_RegistryRoots
0x14000a84f  cmp     edi, 6
0x14000a852  jb      short loc_14000A82F
0x14000a854  mov     edi, 3F2h
0x14000a859  test    rbx, rbx
0x14000a85c  jz      short loc_14000A863
0x14000a85e  mov     [rbx-2], r12w
0x14000a863  mov     eax, edi
0x14000a865  add     rsp, 58h
0x14000a869  pop     r15
0x14000a86b  pop     r14
0x14000a86d  pop     r13
0x14000a86f  pop     r12
0x14000a871  pop     rdi
0x14000a872  pop     rsi
0x14000a873  pop     rbp
0x14000a874  pop     rbx
0x14000a875  retn
0x14000a876  lea     rcx, g_RegistryRoots
0x14000a87d  mov     rcx, [rcx+r14*8+8]; hKey
0x14000a882  test    rcx, rcx
0x14000a885  jz      short loc_14000A854
0x14000a887  mov     edi, 3F3h
0x14000a88c  test    esi, esi
0x14000a88e  jz      short loc_14000A906
0x14000a890  sub     esi, 1
0x14000a893  jz      short loc_14000A8AD
0x14000a895  cmp     esi, 1
0x14000a898  jnz     short loc_14000A859
0x14000a89a  mov     r8d, ebp
0x14000a89d  mov     rdx, rbx
0x14000a8a0  call    RegDeleteKeyRecursive
0x14000a8a5  xor     edi, edi
0x14000a8a7  mov     [r13+0], rdi
0x14000a8ab  jmp     short loc_14000A859
0x14000a8ad  lea     rax, [rcx+7FFFFFFEh]
0x14000a8b4  cmp     rax, 1
0x14000a8b8  ja      short loc_14000A8C3
0x14000a8ba  test    rbx, rbx
0x14000a8bd  jnz     short loc_14000A8C3
0x14000a8bf  xor     edi, edi
0x14000a8c1  jmp     short loc_14000A863
0x14000a8c3  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x14000a8cc  or      ebp, 2001Fh
0x14000a8d2  mov     [rsp+98h+phkResult], r13; phkResult
0x14000a8d7  xor     r9d, r9d; lpClass
0x14000a8da  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000a8e3  xor     r8d, r8d; Reserved
0x14000a8e6  mov     [rsp+98h+samDesired], ebp; samDesired
0x14000a8ea  mov     rdx, rbx; lpSubKey
0x14000a8ed  mov     [rsp+98h+dwOptions], 0; dwOptions
0x14000a8f5  call    cs:__imp_RegCreateKeyExW
0x14000a8fb  neg     eax
0x14000a8fd  sbb     ecx, ecx
0x14000a8ff  and     edi, ecx
0x14000a901  jmp     loc_14000A859
0x14000a906  or      ebp, 9
0x14000a909  mov     qword ptr [rsp+98h+dwOptions], r13; phkResult
0x14000a90e  mov     r9d, ebp; samDesired
0x14000a911  xor     r8d, r8d; ulOptions
0x14000a914  mov     rdx, rbx; lpSubKey
0x14000a917  call    cs:__imp_RegOpenKeyExW
0x14000a91d  test    eax, eax
0x14000a91f  jnz     loc_14000A859
0x14000a925  xor     edi, edi
0x14000a927  jmp     loc_14000A859
```
