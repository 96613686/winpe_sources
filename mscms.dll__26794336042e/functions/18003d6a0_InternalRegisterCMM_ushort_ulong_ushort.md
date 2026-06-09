# InternalRegisterCMM(ushort *,ulong,ushort *)

- ea: `0x18003d6a0`
- end: `0x18003d7e2`
- name: `?InternalRegisterCMM@@YAHPEAGK0@Z`
- size: `322`
- prototype: `int(unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003e0e0`
- `0x18003e180`

## callees

- `0x18002e5f0`
- `0x18003ce28`
- `0x18003d6a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d793`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d793`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003d728`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003d728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d79f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d7bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d79f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d7bb`

## pseudocode

```c
__int64 __fastcall InternalRegisterCMM(unsigned __int16 *a1, unsigned int a2, const BYTE *a3)
{
  unsigned int valid; // ebx
  LSTATUS v5; // eax
  DWORD v6; // ecx
  int i; // r8d
  char *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  LSTATUS v11; // eax
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  WCHAR ValueName[8]; // [rsp+58h] [rbp-20h] BYREF
  int v15; // [rsp+88h] [rbp+10h] BYREF

  HIBYTE(v15) = HIBYTE(a2);
  hKey = 0;
  if ( !a3 || a1 )
  {
    v6 = 87;
    goto LABEL_15;
  }
  valid = ValidColorMatchingModule(a2, a3);
  if ( !valid )
    return valid;
  v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, gszICMatcher, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
  if ( !v5 )
  {
    for ( i = 0; i < 4; ++i )
    {
      v8 = (char *)&v15 - (unsigned int)i + 3;
      v9 = (unsigned int)i;
      ValueName[v9] = *v8;
    }
    ValueName[4] = 0;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&a3[2 * v10] );
    v11 = RegSetValueExW(hKey, ValueName, 0, 1u, a3, 2 * v10 + 2);
    if ( v11 )
    {
      SetLastError(v11);
      valid = 0;
    }
    RegCloseKey(hKey);
    return valid;
  }
  v6 = v5;
LABEL_15:
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x18003d6a0  mov     [rsp+arg_0], rbx
0x18003d6a5  mov     [rsp+arg_18], rsi
0x18003d6aa  mov     [rsp+arg_8], edx
0x18003d6ae  push    rdi
0x18003d6af  sub     rsp, 70h
0x18003d6b3  mov     rax, cs:__security_cookie
0x18003d6ba  xor     rax, rsp
0x18003d6bd  mov     [rsp+78h+var_10], rax
0x18003d6c2  xor     esi, esi
0x18003d6c4  mov     rdi, r8
0x18003d6c7  mov     [rsp+78h+hKey], rsi
0x18003d6cc  mov     eax, edx
0x18003d6ce  test    r8, r8
0x18003d6d1  jz      loc_18003D7B6
0x18003d6d7  test    rcx, rcx
0x18003d6da  jnz     loc_18003D7B6
0x18003d6e0  mov     rdx, r8
0x18003d6e3  mov     ecx, eax
0x18003d6e5  call    ValidColorMatchingModule
0x18003d6ea  mov     ebx, eax
0x18003d6ec  test    eax, eax
0x18003d6ee  jz      loc_18003D7B2
0x18003d6f4  mov     [rsp+78h+lpdwDisposition], rsi; lpdwDisposition
0x18003d6f9  lea     rax, [rsp+78h+hKey]
0x18003d6fe  mov     [rsp+78h+phkResult], rax; phkResult
0x18003d703  lea     rdx, gszICMatcher; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003d70a  mov     [rsp+78h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18003d70f  xor     r9d, r9d; lpClass
0x18003d712  mov     [rsp+78h+samDesired], 2000000h; samDesired
0x18003d71a  xor     r8d, r8d; Reserved
0x18003d71d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d724  mov     [rsp+78h+dwOptions], esi; dwOptions
0x18003d728  call    cs:__imp_RegCreateKeyExW
0x18003d72e  test    eax, eax
0x18003d730  jz      short loc_18003D739
0x18003d732  mov     ecx, eax
0x18003d734  jmp     loc_18003D7BB
0x18003d739  mov     r8d, esi
0x18003d73c  mov     r9d, 1; dwType
0x18003d742  mov     eax, r8d
0x18003d745  lea     rcx, [rsp+78h+arg_8+3]
0x18003d74d  sub     rcx, rax
0x18003d750  mov     eax, r8d
0x18003d753  add     r8d, r9d
0x18003d756  movsx   edx, byte ptr [rcx]
0x18003d759  mov     [rsp+rax*2+78h+ValueName], dx
0x18003d75e  cmp     r8d, 4
0x18003d762  jl      short loc_18003D742
0x18003d764  mov     [rsp+78h+var_18], si
0x18003d769  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d76d  inc     rax
0x18003d770  cmp     [rdi+rax*2], si
0x18003d774  jnz     short loc_18003D76D
0x18003d776  mov     rcx, [rsp+78h+hKey]; hKey
0x18003d77b  lea     eax, ds:2[rax*2]
0x18003d782  mov     [rsp+78h+samDesired], eax; cbData
0x18003d786  lea     rdx, [rsp+78h+ValueName]; lpValueName
0x18003d78b  xor     r8d, r8d; Reserved
0x18003d78e  mov     qword ptr [rsp+78h+dwOptions], rdi; lpData
0x18003d793  call    cs:__imp_RegSetValueExW
0x18003d799  test    eax, eax
0x18003d79b  jz      short loc_18003D7A7
0x18003d79d  mov     ecx, eax; dwErrCode
0x18003d79f  call    cs:__imp_SetLastError
0x18003d7a5  mov     ebx, esi
0x18003d7a7  mov     rcx, [rsp+78h+hKey]; hKey
0x18003d7ac  call    cs:__imp_RegCloseKey
0x18003d7b2  mov     eax, ebx
0x18003d7b4  jmp     short loc_18003D7C3
0x18003d7b6  mov     ecx, 57h ; 'W'; dwErrCode
0x18003d7bb  call    cs:__imp_SetLastError
0x18003d7c1  xor     eax, eax
0x18003d7c3  mov     rcx, [rsp+78h+var_10]
0x18003d7c8  xor     rcx, rsp; StackCookie
0x18003d7cb  call    __security_check_cookie
0x18003d7d0  lea     r11, [rsp+78h+var_8]
0x18003d7d5  mov     rbx, [r11+10h]
0x18003d7d9  mov     rsi, [r11+28h]
0x18003d7dd  mov     rsp, r11
0x18003d7e0  pop     rdi
0x18003d7e1  retn
```
