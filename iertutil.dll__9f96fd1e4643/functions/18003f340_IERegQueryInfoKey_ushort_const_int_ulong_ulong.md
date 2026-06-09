# IERegQueryInfoKey(ushort const *,int,ulong *,ulong *)

- ea: `0x18003f340`
- end: `0x18003f5b8`
- name: `?IERegQueryInfoKey@@YAJPEBGHPEAK1@Z`
- size: `632`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, int, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ee9c`
- `0x18003f2a0`

## callees

- `0x18003f340`
- `0x18003f5c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f3fc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f3fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f4e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f4e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f523`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f59e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f59e`

## pseudocode

```c
__int64 __fastcall IERegQueryInfoKey(PCNZWCH lpString1, int a2, unsigned int *a3, unsigned int *a4)
{
  PCNZWCH v7; // rax
  __int64 v8; // r10
  __int64 v10; // rbx
  unsigned int v11; // ebp
  int v12; // edi
  struct IERegCacheEntry *v13; // r14
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // r9
  unsigned int v16; // edx
  __int64 v17; // rcx
  const WCHAR *v18; // rdx
  bool v19; // cf
  LSTATUS v20; // eax
  HKEY phkResult; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int *v22; // [rsp+B0h] [rbp+18h]

  v22 = a3;
  phkResult = 0;
  IERegInit();
  if ( !lpString1 )
    return 2147942487LL;
  v7 = lpString1;
  v8 = 260;
  while ( *v7 )
  {
    ++v7;
    if ( !--v8 )
      return 2147942487LL;
  }
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = (struct IERegCacheEntry *)(260 - v8);
  while ( !v12 )
  {
    v14 = 40 * v10;
    if ( a2 == *((_DWORD *)&g_IERegPolicyKeyCache + 10 * v10) )
    {
      v15 = *(unsigned __int64 *)((char *)&g_IERegPolicyKeyCache + v14 + 16);
      if ( (unsigned __int64)v13 >= v15
        && CompareStringW(
             0x7Fu,
             1u,
             lpString1,
             v15,
             *(PCNZWCH *)((char *)&g_IERegPolicyKeyCache + v14 + 8),
             (int)*(struct IERegCacheEntry near **)((char *)&g_IERegPolicyKeyCache + v14 + 16)) == 2 )
      {
        if ( *(_DWORD *)((char *)&g_IERegPolicyKeyCache + v14 + 24) )
        {
          if ( v13 == *(struct IERegCacheEntry near **)((char *)&g_IERegPolicyKeyCache + v14 + 16)
            || !*(_DWORD *)((char *)&g_IERegPolicyKeyCache + v14 + 28) )
          {
            v11 = v10;
            v12 = 1;
          }
        }
        else
        {
          v18 = *(const WCHAR **)((char *)&g_IERegPolicyKeyCache + v14 + 8);
          v19 = *(_DWORD *)((char *)&g_IERegPolicyKeyCache + v14) != 0;
          phkResult = 0;
          v20 = RegOpenKeyExW((HKEY)(-(__int64)v19 - 2147483646), v18, 0, 1u, &phkResult);
          if ( v20 == 2
            || !v20
            && !RegQueryInfoKeyW(
                  phkResult,
                  0,
                  0,
                  0,
                  (LPDWORD)&qword_1802930B0[v14 / 8 + 1] + 1,
                  0,
                  0,
                  (LPDWORD)&qword_1802930B0[v14 / 8 + 2],
                  0,
                  0,
                  0,
                  0) )
          {
            *(_DWORD *)((char *)&g_IERegPolicyKeyCache + v14 + 24) = 1;
            if ( v13 == *(struct IERegCacheEntry near **)((char *)&g_IERegPolicyKeyCache + v14 + 16)
              || !*(_DWORD *)((char *)&g_IERegPolicyKeyCache + v14 + 28) )
            {
              v11 = v10;
              v12 = 1;
            }
          }
          if ( phkResult )
            RegCloseKey(phkResult);
        }
      }
    }
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= 0xA )
    {
      v16 = -2147467259;
      if ( !v12 )
        return v16;
      break;
    }
  }
  v16 = 0;
  v17 = 40LL * v11;
  if ( v22 )
    *v22 = *(_DWORD *)((char *)&g_IERegPolicyKeyCache + v17 + 28);
  if ( a4 )
  {
    if ( v13 == *(struct IERegCacheEntry near **)((char *)&g_IERegPolicyKeyCache + v17 + 16) )
      *a4 = *(_DWORD *)((char *)&g_IERegPolicyKeyCache + v17 + 32);
    else
      *a4 = 0;
  }
  return v16;
}

```

## disassembly

```asm
0x18003f340  mov     [rsp+arg_10], r8
0x18003f345  push    rsi
0x18003f346  push    r12
0x18003f348  push    r13
0x18003f34a  push    r14
0x18003f34c  push    r15
0x18003f34e  sub     rsp, 70h
0x18003f352  mov     r12, r9
0x18003f355  mov     [rsp+98h+phkResult], 0
0x18003f361  mov     r13d, edx
0x18003f364  mov     r15, rcx
0x18003f367  call    IERegInit
0x18003f36c  test    r15, r15
0x18003f36f  jz      short loc_18003F390
0x18003f371  mov     r14d, 104h
0x18003f377  mov     rax, r15
0x18003f37a  mov     r10d, r14d
0x18003f37d  nop     dword ptr [rax]
0x18003f380  cmp     word ptr [rax], 0
0x18003f384  jz      short loc_18003F39A
0x18003f386  add     rax, 2
0x18003f38a  sub     r10, 1
0x18003f38e  jnz     short loc_18003F380
0x18003f390  mov     eax, 80070057h
0x18003f395  jmp     loc_18003F432
0x18003f39a  mov     [rsp+98h+arg_8], rbx
0x18003f3a2  xor     ebx, ebx
0x18003f3a4  mov     [rsp+98h+var_30], rbp
0x18003f3a9  xor     ebp, ebp
0x18003f3ab  mov     [rsp+98h+var_38], rdi
0x18003f3b0  xor     edi, edi
0x18003f3b2  sub     r14, r10
0x18003f3b5  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18003f3bc  test    edi, edi
0x18003f3be  jnz     loc_18003F458
0x18003f3c4  lea     rcx, [rbx+rbx*4]
0x18003f3c8  lea     rsi, ds:0[rcx*8]
0x18003f3d0  cmp     r13d, [rsi+r10]
0x18003f3d4  jnz     short loc_18003F40E
0x18003f3d6  mov     r9, [rsi+r10+10h]; cchCount1
0x18003f3db  cmp     r14, r9
0x18003f3de  jb      short loc_18003F40E
0x18003f3e0  mov     rax, [rsi+r10+8]
0x18003f3e5  mov     r8, r15; lpString1
0x18003f3e8  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x18003f3ed  mov     edx, 1; dwCmpFlags
0x18003f3f2  mov     ecx, 7Fh; Locale
0x18003f3f7  mov     [rsp+98h+lpString2], rax; lpString2
0x18003f3fc  call    cs:__imp_CompareStringW
0x18003f402  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18003f409  cmp     eax, 2
0x18003f40c  jz      short loc_18003F440
0x18003f40e  inc     ebx
0x18003f410  cmp     ebx, 0Ah
0x18003f413  jb      short loc_18003F3BC
0x18003f415  mov     edx, 80004005h
0x18003f41a  test    edi, edi
0x18003f41c  jnz     short loc_18003F458
0x18003f41e  mov     rdi, [rsp+98h+var_38]
0x18003f423  mov     eax, edx
0x18003f425  mov     rbp, [rsp+98h+var_30]
0x18003f42a  mov     rbx, [rsp+98h+arg_8]
0x18003f432  add     rsp, 70h
0x18003f436  pop     r15
0x18003f438  pop     r14
0x18003f43a  pop     r13
0x18003f43c  pop     r12
0x18003f43e  pop     rsi
0x18003f43f  retn
0x18003f440  cmp     dword ptr [rsi+r10+18h], 0
0x18003f446  jz      short loc_18003F4AA
0x18003f448  cmp     r14, [rsi+r10+10h]
0x18003f44d  jnz     short loc_18003F493
0x18003f44f  mov     ebp, ebx
0x18003f451  mov     edi, 1
0x18003f456  jmp     short loc_18003F40E
0x18003f458  mov     rsi, [rsp+98h+arg_10]
0x18003f460  xor     edx, edx
0x18003f462  mov     eax, ebp
0x18003f464  lea     rcx, [rax+rax*4]
0x18003f468  lea     rcx, ds:0[rcx*8]
0x18003f470  test    rsi, rsi
0x18003f473  jz      short loc_18003F47C
0x18003f475  mov     eax, [rcx+r10+1Ch]
0x18003f47a  mov     [rsi], eax
0x18003f47c  test    r12, r12
0x18003f47f  jz      short loc_18003F41E
0x18003f481  cmp     r14, [rcx+r10+10h]
0x18003f486  jnz     short loc_18003F4A1
0x18003f488  mov     eax, [rcx+r10+20h]
0x18003f48d  mov     [r12], eax
0x18003f491  jmp     short loc_18003F41E
0x18003f493  cmp     dword ptr [rsi+r10+1Ch], 0
0x18003f499  jnz     loc_18003F40E
0x18003f49f  jmp     short loc_18003F44F
0x18003f4a1  mov     [r12], edx
0x18003f4a5  jmp     loc_18003F41E
0x18003f4aa  mov     eax, [rsi+r10]
0x18003f4ae  mov     r9d, 1; samDesired
0x18003f4b4  mov     rdx, [rsi+r10+8]; lpSubKey
0x18003f4b9  neg     eax
0x18003f4bb  lea     rax, [rsp+98h+phkResult]
0x18003f4c3  mov     [rsp+98h+phkResult], 0
0x18003f4cf  sbb     rcx, rcx
0x18003f4d2  mov     [rsp+98h+lpString2], rax; phkResult
0x18003f4d7  add     rcx, 0FFFFFFFF80000002h; hKey
0x18003f4de  xor     r8d, r8d; ulOptions
0x18003f4e1  call    cs:__imp_RegOpenKeyExW
0x18003f4e7  cmp     eax, 2
0x18003f4ea  jnz     short loc_18003F535
0x18003f4ec  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18003f4f3  mov     dword ptr [rsi+r10+18h], 1
0x18003f4fc  cmp     r14, [rsi+r10+10h]
0x18003f501  jz      short loc_18003F50B
0x18003f503  cmp     dword ptr [rsi+r10+1Ch], 0
0x18003f509  jnz     short loc_18003F512
0x18003f50b  mov     ebp, ebx
0x18003f50d  mov     edi, 1
0x18003f512  mov     rcx, [rsp+98h+phkResult]; hKey
0x18003f51a  test    rcx, rcx
0x18003f51d  jz      loc_18003F40E
0x18003f523  call    cs:__imp_RegCloseKey
0x18003f529  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18003f530  jmp     loc_18003F40E
0x18003f535  test    eax, eax
0x18003f537  jnz     short loc_18003F5AC
0x18003f539  mov     [rsp+98h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18003f542  lea     rcx, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18003f549  mov     [rsp+98h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18003f552  lea     rax, [rcx+20h]
0x18003f556  mov     [rsp+98h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18003f55f  add     rcx, 1Ch
0x18003f563  mov     [rsp+98h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18003f56c  add     rcx, rsi
0x18003f56f  add     rax, rsi
0x18003f572  xor     r9d, r9d; lpReserved
0x18003f575  mov     [rsp+98h+lpcValues], rax; lpcValues
0x18003f57a  xor     r8d, r8d; lpcchClass
0x18003f57d  mov     [rsp+98h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18003f586  xor     edx, edx; lpClass
0x18003f588  mov     qword ptr [rsp+98h+cchCount2], 0; lpcbMaxSubKeyLen
0x18003f591  mov     [rsp+98h+lpString2], rcx; lpcSubKeys
0x18003f596  mov     rcx, [rsp+98h+phkResult]; hKey
0x18003f59e  call    cs:__imp_RegQueryInfoKeyW
0x18003f5a4  test    eax, eax
0x18003f5a6  jz      loc_18003F4EC
0x18003f5ac  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18003f5b3  jmp     loc_18003F512
```
