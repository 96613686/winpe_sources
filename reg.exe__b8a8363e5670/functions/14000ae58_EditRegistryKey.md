# EditRegistryKey

- ea: `0x14000ae58`
- end: `0x14000afcb`
- name: `EditRegistryKey`
- size: `371`
- prototype: `__int64 __fastcall(PHKEY phkResult, LPCWSTR lpString2)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000afd4`
- `0x14000bdc4`

## callees

- `0x14000ae58`
- `0x14000cb3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000afb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000afb0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000af88`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000af88`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x14000aea6`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x14000aea6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x14000ae80`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x14000ae80`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x14000aec8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x14000aec8`

## pseudocode

```c
__int64 __fastcall EditRegistryKey(PHKEY phkResult, WCHAR *lpString2, int a3, unsigned int a4)
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
0x14000ae58  push    rbx
0x14000ae5a  push    rbp
0x14000ae5b  push    rsi
0x14000ae5c  push    rdi
0x14000ae5d  push    r12
0x14000ae5f  push    r13
0x14000ae61  push    r14
0x14000ae63  push    r15
0x14000ae65  sub     rsp, 58h
0x14000ae69  mov     r15, rdx
0x14000ae6c  mov     r13, rcx
0x14000ae6f  xor     r12d, r12d
0x14000ae72  mov     rcx, r15; pszStart
0x14000ae75  mov     ebp, r9d
0x14000ae78  mov     esi, r8d
0x14000ae7b  lea     edx, [r12+5Ch]; wMatch
0x14000ae80  call    cs:__imp_StrChrW
0x14000ae87  nop     dword ptr [rax+rax+00h]
0x14000ae8c  mov     rbx, rax
0x14000ae8f  test    rax, rax
0x14000ae92  jz      short loc_14000AEA3
0x14000ae94  movzx   r12d, word ptr [rax]
0x14000ae98  xor     r8d, r8d
0x14000ae9b  mov     [rax], r8w
0x14000ae9f  add     rbx, 2
0x14000aea3  mov     rcx, r15; lpsz
0x14000aea6  call    cs:__imp_CharUpperW
0x14000aead  nop     dword ptr [rax+rax+00h]
0x14000aeb2  xor     edi, edi
0x14000aeb4  lea     rax, g_RegistryRoots
0x14000aebb  mov     r14d, edi
0x14000aebe  mov     rdx, r15; lpString2
0x14000aec1  add     r14, r14
0x14000aec4  mov     rcx, [rax+r14*8]; lpString1
0x14000aec8  call    cs:__imp_lstrcmpW
0x14000aecf  nop     dword ptr [rax+rax+00h]
0x14000aed4  test    eax, eax
0x14000aed6  jz      short loc_14000AF09
0x14000aed8  inc     edi
0x14000aeda  lea     rax, g_RegistryRoots
0x14000aee1  cmp     edi, 6
0x14000aee4  jb      short loc_14000AEBB
0x14000aee6  mov     edi, 3F2h
0x14000aeeb  test    rbx, rbx
0x14000aeee  jz      short loc_14000AEF5
0x14000aef0  mov     [rbx-2], r12w
0x14000aef5  mov     eax, edi
0x14000aef7  add     rsp, 58h
0x14000aefb  pop     r15
0x14000aefd  pop     r14
0x14000aeff  pop     r13
0x14000af01  pop     r12
0x14000af03  pop     rdi
0x14000af04  pop     rsi
0x14000af05  pop     rbp
0x14000af06  pop     rbx
0x14000af07  retn
0x14000af09  lea     rcx, g_RegistryRoots
0x14000af10  mov     rcx, [rcx+r14*8+8]; hKey
0x14000af15  test    rcx, rcx
0x14000af18  jz      short loc_14000AEE6
0x14000af1a  mov     edi, 3F3h
0x14000af1f  test    esi, esi
0x14000af21  jz      short loc_14000AF9F
0x14000af23  sub     esi, 1
0x14000af26  jz      short loc_14000AF40
0x14000af28  cmp     esi, 1
0x14000af2b  jnz     short loc_14000AEEB
0x14000af2d  mov     r8d, ebp
0x14000af30  mov     rdx, rbx
0x14000af33  call    RegDeleteKeyRecursive
0x14000af38  xor     edi, edi
0x14000af3a  mov     [r13+0], rdi
0x14000af3e  jmp     short loc_14000AEEB
0x14000af40  lea     rax, [rcx+7FFFFFFEh]
0x14000af47  cmp     rax, 1
0x14000af4b  ja      short loc_14000AF56
0x14000af4d  test    rbx, rbx
0x14000af50  jnz     short loc_14000AF56
0x14000af52  xor     edi, edi
0x14000af54  jmp     short loc_14000AEF5
0x14000af56  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x14000af5f  or      ebp, 2001Fh
0x14000af65  mov     [rsp+98h+phkResult], r13; phkResult
0x14000af6a  xor     r9d, r9d; lpClass
0x14000af6d  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000af76  xor     r8d, r8d; Reserved
0x14000af79  mov     [rsp+98h+samDesired], ebp; samDesired
0x14000af7d  mov     rdx, rbx; lpSubKey
0x14000af80  mov     [rsp+98h+dwOptions], 0; dwOptions
0x14000af88  call    cs:__imp_RegCreateKeyExW
0x14000af8f  nop     dword ptr [rax+rax+00h]
0x14000af94  neg     eax
0x14000af96  sbb     ecx, ecx
0x14000af98  and     edi, ecx
0x14000af9a  jmp     loc_14000AEEB
0x14000af9f  or      ebp, 9
0x14000afa2  mov     qword ptr [rsp+98h+dwOptions], r13; phkResult
0x14000afa7  mov     r9d, ebp; samDesired
0x14000afaa  xor     r8d, r8d; ulOptions
0x14000afad  mov     rdx, rbx; lpSubKey
0x14000afb0  call    cs:__imp_RegOpenKeyExW
0x14000afb7  nop     dword ptr [rax+rax+00h]
0x14000afbc  test    eax, eax
0x14000afbe  jnz     loc_14000AEEB
0x14000afc4  xor     edi, edi
0x14000afc6  jmp     loc_14000AEEB
```
