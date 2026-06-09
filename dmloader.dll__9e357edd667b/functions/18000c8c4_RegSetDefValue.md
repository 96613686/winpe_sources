# RegSetDefValue

- ea: `0x18000c8c4`
- end: `0x18000ca2f`
- name: `RegSetDefValue`
- size: `363`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey, char *, LPCSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000cae4`

## callees

- `0x1800015d0`
- `0x18000c8c4`
- `0x18000ca38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18000c9f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18000c9f6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18000c99d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18000c99d`

## pseudocode

```c
LSTATUS __fastcall RegSetDefValue(char *lpSubKey, char *a2, LPCSTR lpValueName, BYTE *lpData)
{
  char *v7; // r9
  __int64 v8; // r10
  __int64 v9; // rax
  char *v10; // rax
  LSTATUS result; // eax
  BYTE *v12; // rax
  __int64 v13; // rcx
  LSTATUS v14; // ebx
  HKEY hKey; // [rsp+50h] [rbp-448h] BYREF
  char v16[1024]; // [rsp+60h] [rbp-438h] BYREF

  hKey = 0;
  if ( a2 )
  {
    v7 = v16;
    v8 = 1024;
    v9 = 2147483646;
    do
    {
      if ( !v9 )
        break;
      if ( !*lpSubKey )
        break;
      *v7++ = *lpSubKey++;
      --v9;
      --v8;
    }
    while ( v8 );
    v10 = v7 - 1;
    if ( v8 )
      v10 = v7;
    *v10 = 0;
    StringCchCatA(v16, 0x400u, "\\");
    StringCchCatA(v16, 0x400u, a2);
    lpSubKey = v16;
  }
  result = RegCreateKeyExA(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( !result )
  {
    if ( !lpData )
      return 14;
    v12 = lpData;
    v13 = 0x7FFFFFFF;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v13;
    }
    while ( v13 );
    if ( v13 )
    {
      v14 = RegSetValueExA(hKey, lpValueName, 0, 1u, lpData, v13 != 0 ? 0x7FFFFFFF - v13 + 1 : 1);
      RegCloseKey(hKey);
      return v14;
    }
    else
    {
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c8c4  push    rbx
0x18000c8c6  push    rsi
0x18000c8c7  push    rdi
0x18000c8c8  push    r14
0x18000c8ca  sub     rsp, 478h
0x18000c8d1  mov     rax, cs:__security_cookie
0x18000c8d8  xor     rax, rsp
0x18000c8db  mov     [rsp+498h+var_38], rax
0x18000c8e3  mov     [rsp+498h+hKey], 0
0x18000c8ec  mov     rbx, r9
0x18000c8ef  mov     rsi, r8
0x18000c8f2  mov     rdi, rdx
0x18000c8f5  test    rdx, rdx
0x18000c8f8  jz      short loc_18000C961
0x18000c8fa  mov     r14d, 400h
0x18000c900  lea     r9, [rsp+498h+var_438]
0x18000c905  mov     r10d, r14d
0x18000c908  mov     eax, 7FFFFFFEh
0x18000c90d  test    rax, rax
0x18000c910  jz      short loc_18000C92A
0x18000c912  mov     dl, [rcx]
0x18000c914  test    dl, dl
0x18000c916  jz      short loc_18000C92A
0x18000c918  mov     [r9], dl
0x18000c91b  inc     rcx
0x18000c91e  inc     r9
0x18000c921  dec     rax
0x18000c924  sub     r10, 1
0x18000c928  jnz     short loc_18000C90D
0x18000c92a  test    r10, r10
0x18000c92d  lea     rax, [r9-1]
0x18000c931  lea     r8, asc_1800121F4; "\\"
0x18000c938  mov     rdx, r14; unsigned __int64
0x18000c93b  cmovnz  rax, r9
0x18000c93f  lea     rcx, [rsp+498h+var_438]; char *
0x18000c944  mov     byte ptr [rax], 0
0x18000c947  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18000c94c  mov     r8, rdi; char *
0x18000c94f  lea     rcx, [rsp+498h+var_438]; char *
0x18000c954  mov     rdx, r14; unsigned __int64
0x18000c957  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18000c95c  lea     rcx, [rsp+498h+var_438]
0x18000c961  mov     [rsp+498h+lpdwDisposition], 0; lpdwDisposition
0x18000c96a  lea     rax, [rsp+498h+hKey]
0x18000c96f  mov     [rsp+498h+phkResult], rax; phkResult
0x18000c974  mov     rdx, rcx; lpSubKey
0x18000c977  mov     [rsp+498h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000c980  xor     r9d, r9d; lpClass
0x18000c983  mov     [rsp+498h+samDesired], 0F003Fh; samDesired
0x18000c98b  xor     r8d, r8d; Reserved
0x18000c98e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000c995  mov     [rsp+498h+dwOptions], 0; dwOptions
0x18000c99d  call    cs:__imp_RegCreateKeyExA
0x18000c9a3  test    eax, eax
0x18000c9a5  jnz     short loc_18000CA12
0x18000c9a7  test    rbx, rbx
0x18000c9aa  jz      short loc_18000CA0D
0x18000c9ac  mov     r8d, 7FFFFFFFh
0x18000c9b2  mov     rax, rbx
0x18000c9b5  mov     ecx, r8d
0x18000c9b8  cmp     byte ptr [rax], 0
0x18000c9bb  jz      short loc_18000C9C6
0x18000c9bd  inc     rax
0x18000c9c0  sub     rcx, 1
0x18000c9c4  jnz     short loc_18000C9B8
0x18000c9c6  sub     r8, rcx
0x18000c9c9  mov     rax, rcx
0x18000c9cc  neg     rax
0x18000c9cf  sbb     rax, rax
0x18000c9d2  and     rax, r8
0x18000c9d5  test    rcx, rcx
0x18000c9d8  jz      short loc_18000CA0D
0x18000c9da  mov     rcx, [rsp+498h+hKey]; hKey
0x18000c9df  inc     eax
0x18000c9e1  mov     [rsp+498h+samDesired], eax; cbData
0x18000c9e5  mov     r9d, 1; dwType
0x18000c9eb  xor     r8d, r8d; Reserved
0x18000c9ee  mov     qword ptr [rsp+498h+dwOptions], rbx; lpData
0x18000c9f3  mov     rdx, rsi; lpValueName
0x18000c9f6  call    cs:__imp_RegSetValueExA
0x18000c9fc  mov     rcx, [rsp+498h+hKey]; hKey
0x18000ca01  mov     ebx, eax
0x18000ca03  call    cs:__imp_RegCloseKey
0x18000ca09  mov     eax, ebx
0x18000ca0b  jmp     short loc_18000CA12
0x18000ca0d  mov     eax, 0Eh
0x18000ca12  mov     rcx, [rsp+498h+var_38]
0x18000ca1a  xor     rcx, rsp; StackCookie
0x18000ca1d  call    __security_check_cookie
0x18000ca22  add     rsp, 478h
0x18000ca29  pop     r14
0x18000ca2b  pop     rdi
0x18000ca2c  pop     rsi
0x18000ca2d  pop     rbx
0x18000ca2e  retn
```
