# DrvGetProfileString(ushort const *,ushort const *,ushort const *,ushort *,unsigned __int64)

- ea: `0x10046c448`
- end: `0x10046c6be`
- name: `?DrvGetProfileString@@YA_KPEBG00PEAG_K@Z`
- size: `630`
- prototype: `unsigned __int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1004e8904`
- `0x100538e0c`

## callees

- `0x10045839c`
- `0x10046c448`
- `0x100548210`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x10046c539`
- `ADVAPI32!RegEnumValueW` at `0x10046c59f`
- `ADVAPI32!RegEnumValueW` at `0x10046c539`
- `ADVAPI32!RegEnumValueW` at `0x10046c59f`
- `ADVAPI32!RegQueryValueExW` at `0x10046c60d`
- `ADVAPI32!RegQueryValueExW` at `0x10046c60d`
- `ADVAPI32!RegOpenKeyExW` at `0x10046c4ac`
- `ADVAPI32!RegOpenKeyExW` at `0x10046c4ac`
- `ADVAPI32!RegCloseKey` at `0x10046c690`
- `ADVAPI32!RegCloseKey` at `0x10046c690`

## pseudocode

```c
unsigned __int64 __fastcall DrvGetProfileString(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int64 a5)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v10; // rdi
  DWORD v11; // r14d
  DWORD v12; // r15d
  LSTATUS v13; // eax
  __int64 v14; // rax
  LSTATUS Value; // eax
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rcx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[136]; // [rsp+70h] [rbp-90h] BYREF

  v5 = a5;
  if ( a5 )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
    {
      if ( (int)StringCchCopyExW(a4, a5, a3, 0, &v20, 0) >= 0 )
        return a5 - v20;
      return 0;
    }
    if ( lpValueName )
    {
      cbData[0] = 2 * a5;
      Value = RegQueryValueExW(hKey, lpValueName, 0, Type, (LPBYTE)a4, cbData);
      v16 = (unsigned __int64)cbData[0] >> 1;
      if ( Value != 234 )
      {
        if ( Value )
        {
          StringCchCopyExW(a4, a5, a3, 0, &v20, 0);
          v17 = a5 - v20;
        }
        else if ( Type[0] == 1 )
        {
          if ( a4[v16 - 1] )
          {
            v18 = a5 - 1;
            if ( v16 < a5 )
              v18 = (unsigned __int64)cbData[0] >> 1;
            v17 = v18;
            a4[v18] = 0;
          }
          else
          {
            v17 = v16 - 1;
          }
        }
        else
        {
          v17 = 0;
          *a4 = 0;
        }
        goto LABEL_27;
      }
      a4[a5 - 1] = 0;
    }
    else
    {
      v10 = a5 - 1;
      *(_QWORD *)cbData = a4;
      v20 = a5 - 1;
      v11 = 0;
      if ( a5 != 1 )
      {
        while ( 1 )
        {
          v12 = v11;
          cchValueName = v10;
          v13 = RegEnumValueW(hKey, v11++, a4, &cchValueName, 0, 0, 0, 0);
          if ( v13 )
            break;
          if ( cchValueName )
          {
            v14 = cchValueName + 1;
            v10 -= (unsigned int)v14;
            v20 = v10;
            a4 += v14;
            *(_QWORD *)cbData = a4;
          }
        }
        if ( v13 == 234 )
        {
          if ( v10 )
          {
            cchValueName = 129;
            if ( !RegEnumValueW(hKey, v12, ValueName, &cchValueName, 0, 0, 0, 0) )
            {
              StringCchCopyExW(a4, v10, ValueName, (unsigned __int16 **)cbData, &v20, 0);
              a4 = (unsigned __int16 *)(*(_QWORD *)cbData + 2LL);
              v10 = v20 - 1;
            }
          }
        }
      }
      *a4 = 0;
      v5 = a5 - v10;
    }
    v17 = v5 - 1;
LABEL_27:
    RegCloseKey(hKey);
    return v17;
  }
  return 0;
}

```

## disassembly

```asm
0x10046c448  push    rbp
0x10046c44a  push    rbx
0x10046c44b  push    rsi
0x10046c44c  push    rdi
0x10046c44d  push    r12
0x10046c44f  push    r14
0x10046c451  push    r15
0x10046c453  lea     rbp, [rsp-90h]
0x10046c45b  sub     rsp, 190h
0x10046c462  mov     rax, cs:__security_cookie
0x10046c469  xor     rax, rsp
0x10046c46c  mov     [rbp+0C0h+var_40], rax
0x10046c473  mov     rbx, [rbp+0C0h+arg_20]
0x10046c47a  xor     r12d, r12d
0x10046c47d  mov     rsi, r9
0x10046c480  mov     r14, r8
0x10046c483  mov     rdi, rdx
0x10046c486  test    rbx, rbx
0x10046c489  jz      loc_10046C69B
0x10046c48f  lea     rax, [rsp+1C0h+hKey]
0x10046c494  mov     rdx, rcx; lpSubKey
0x10046c497  mov     rcx, 0FFFFFFFF80000002h; hKey
0x10046c49e  mov     [rsp+1C0h+phkResult], rax; phkResult
0x10046c4a3  mov     r9d, 20019h; samDesired
0x10046c4a9  xor     r8d, r8d; ulOptions
0x10046c4ac  call    cs:__imp_RegOpenKeyExW
0x10046c4b2  test    eax, eax
0x10046c4b4  jz      short loc_10046C4EB
0x10046c4b6  lea     rax, [rsp+1C0h+var_178]
0x10046c4bb  mov     dword ptr [rsp+1C0h+lpType], r12d; unsigned int
0x10046c4c0  xor     r9d, r9d; unsigned __int16 **
0x10046c4c3  mov     [rsp+1C0h+phkResult], rax; unsigned __int64 *
0x10046c4c8  mov     r8, r14; unsigned __int16 *
0x10046c4cb  mov     rdx, rbx; unsigned __int64
0x10046c4ce  mov     rcx, rsi; unsigned __int16 *
0x10046c4d1  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x10046c4d6  test    eax, eax
0x10046c4d8  js      loc_10046C69B
0x10046c4de  sub     rbx, [rsp+1C0h+var_178]
0x10046c4e3  mov     rax, rbx
0x10046c4e6  jmp     loc_10046C69D
0x10046c4eb  test    rdi, rdi
0x10046c4ee  jnz     loc_10046C5E7
0x10046c4f4  lea     rdi, [rbx-1]
0x10046c4f8  mov     qword ptr [rsp+1C0h+cbData], rsi
0x10046c4fd  mov     [rsp+1C0h+var_178], rdi
0x10046c502  mov     r14d, r12d
0x10046c505  test    rdi, rdi
0x10046c508  jz      loc_10046C5DE
0x10046c50e  mov     rcx, [rsp+1C0h+hKey]; hKey
0x10046c513  lea     r9, [rsp+1C0h+cchValueName]; lpcchValueName
0x10046c518  mov     [rsp+1C0h+lpcbData], r12; lpcbData
0x10046c51d  mov     r8, rsi; lpValueName
0x10046c520  mov     [rsp+1C0h+lpData], r12; lpData
0x10046c525  mov     edx, r14d; dwIndex
0x10046c528  mov     [rsp+1C0h+lpType], r12; lpType
0x10046c52d  mov     r15d, r14d
0x10046c530  mov     [rsp+1C0h+phkResult], r12; lpReserved
0x10046c535  mov     [rsp+1C0h+cchValueName], edi
0x10046c539  call    cs:__imp_RegEnumValueW
0x10046c53f  inc     r14d
0x10046c542  test    eax, eax
0x10046c544  jnz     short loc_10046C565
0x10046c546  mov     eax, [rsp+1C0h+cchValueName]
0x10046c54a  test    eax, eax
0x10046c54c  jz      short loc_10046C50E
0x10046c54e  inc     eax
0x10046c550  mov     ecx, eax
0x10046c552  sub     rdi, rcx
0x10046c555  mov     [rsp+1C0h+var_178], rdi
0x10046c55a  lea     rsi, [rsi+rax*2]
0x10046c55e  mov     qword ptr [rsp+1C0h+cbData], rsi
0x10046c563  jmp     short loc_10046C50E
0x10046c565  cmp     eax, 0EAh
0x10046c56a  jnz     short loc_10046C5DE
0x10046c56c  test    rdi, rdi
0x10046c56f  jz      short loc_10046C5DE
0x10046c571  mov     rcx, [rsp+1C0h+hKey]; hKey
0x10046c576  lea     r9, [rsp+1C0h+cchValueName]; lpcchValueName
0x10046c57b  mov     [rsp+1C0h+lpcbData], r12; lpcbData
0x10046c580  lea     r8, [rsp+1C0h+ValueName]; lpValueName
0x10046c585  mov     [rsp+1C0h+lpData], r12; lpData
0x10046c58a  mov     edx, r15d; dwIndex
0x10046c58d  mov     [rsp+1C0h+lpType], r12; lpType
0x10046c592  mov     [rsp+1C0h+phkResult], r12; lpReserved
0x10046c597  mov     [rsp+1C0h+cchValueName], 81h
0x10046c59f  call    cs:__imp_RegEnumValueW
0x10046c5a5  test    eax, eax
0x10046c5a7  jnz     short loc_10046C5DE
0x10046c5a9  lea     rax, [rsp+1C0h+var_178]
0x10046c5ae  mov     dword ptr [rsp+1C0h+lpType], r12d; unsigned int
0x10046c5b3  lea     r9, [rsp+1C0h+cbData]; unsigned __int16 **
0x10046c5b8  mov     [rsp+1C0h+phkResult], rax; unsigned __int64 *
0x10046c5bd  lea     r8, [rsp+1C0h+ValueName]; unsigned __int16 *
0x10046c5c2  mov     rdx, rdi; unsigned __int64
0x10046c5c5  mov     rcx, rsi; unsigned __int16 *
0x10046c5c8  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x10046c5cd  mov     rsi, qword ptr [rsp+1C0h+cbData]
0x10046c5d2  mov     rdi, [rsp+1C0h+var_178]
0x10046c5d7  add     rsi, 2
0x10046c5db  dec     rdi
0x10046c5de  mov     [rsi], r12w
0x10046c5e2  sub     rbx, rdi
0x10046c5e5  jmp     short loc_10046C627
0x10046c5e7  mov     rcx, [rsp+1C0h+hKey]; hKey
0x10046c5ec  lea     eax, [rbx+rbx]
0x10046c5ef  mov     [rsp+1C0h+cbData], eax
0x10046c5f3  lea     r9, [rsp+1C0h+Type]; lpType
0x10046c5f8  lea     rax, [rsp+1C0h+cbData]
0x10046c5fd  xor     r8d, r8d; lpReserved
0x10046c600  mov     [rsp+1C0h+lpType], rax; lpcbData
0x10046c605  mov     rdx, rdi; lpValueName
0x10046c608  mov     [rsp+1C0h+phkResult], rsi; lpData
0x10046c60d  call    cs:__imp_RegQueryValueExW
0x10046c613  mov     edi, [rsp+1C0h+cbData]
0x10046c617  shr     rdi, 1
0x10046c61a  cmp     eax, 0EAh
0x10046c61f  jnz     short loc_10046C62D
0x10046c621  mov     [rsi+rbx*2-2], r12w
0x10046c627  lea     rdi, [rbx-1]
0x10046c62b  jmp     short loc_10046C68B
0x10046c62d  test    eax, eax
0x10046c62f  jz      short loc_10046C65B
0x10046c631  lea     rax, [rsp+1C0h+var_178]
0x10046c636  mov     dword ptr [rsp+1C0h+lpType], r12d; unsigned int
0x10046c63b  xor     r9d, r9d; unsigned __int16 **
0x10046c63e  mov     [rsp+1C0h+phkResult], rax; unsigned __int64 *
0x10046c643  mov     r8, r14; unsigned __int16 *
0x10046c646  mov     rdx, rbx; unsigned __int64
0x10046c649  mov     rcx, rsi; unsigned __int16 *
0x10046c64c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x10046c651  mov     rdi, rbx
0x10046c654  sub     rdi, [rsp+1C0h+var_178]
0x10046c659  jmp     short loc_10046C68B
0x10046c65b  cmp     [rsp+1C0h+Type], 1
0x10046c660  jz      short loc_10046C66B
0x10046c662  mov     rdi, r12
0x10046c665  mov     [rsi], r12w
0x10046c669  jmp     short loc_10046C68B
0x10046c66b  cmp     [rsi+rdi*2-2], r12w
0x10046c671  jnz     short loc_10046C678
0x10046c673  dec     rdi
0x10046c676  jmp     short loc_10046C68B
0x10046c678  cmp     rdi, rbx
0x10046c67b  lea     rcx, [rbx-1]
0x10046c67f  cmovb   rcx, rdi
0x10046c683  mov     rdi, rcx
0x10046c686  mov     [rsi+rcx*2], r12w
0x10046c68b  mov     rcx, [rsp+1C0h+hKey]; hKey
0x10046c690  call    cs:__imp_RegCloseKey
0x10046c696  mov     rax, rdi
0x10046c699  jmp     short loc_10046C69D
0x10046c69b  xor     eax, eax
0x10046c69d  mov     rcx, [rbp+0C0h+var_40]
0x10046c6a4  xor     rcx, rsp; StackCookie
0x10046c6a7  call    __security_check_cookie
0x10046c6ac  add     rsp, 190h
0x10046c6b3  pop     r15
0x10046c6b5  pop     r14
0x10046c6b7  pop     r12
0x10046c6b9  pop     rdi
0x10046c6ba  pop     rsi
0x10046c6bb  pop     rbx
0x10046c6bc  pop     rbp
0x10046c6bd  retn
```
