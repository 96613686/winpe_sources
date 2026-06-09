# CPersistentStoreRegistry::BeginTransaction(PersistenceOp)

- ea: `0x1800a0f70`
- end: `0x1800a112c`
- name: `?BeginTransaction@CPersistentStoreRegistry@@UEAA?AVTxScopeExit@IPersistentStore@@W4PersistenceOp@@@Z`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800a0f70`
- `0x1800a1f08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a105d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a105d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0ff0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a1070`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0ff0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a1070`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800a103c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800a103c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a0fe8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1068`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a0fe8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1068`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a109e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a109e`

## string_xrefs

- `0x1800a10f1`: `CPersistentStoreRegistry::BeginTransaction`
- `0x1800a10de`: `Failed to open reg key, op: %d, key: %s`

## pseudocode

```c
__int64 __fastcall CPersistentStoreRegistry::BeginTransaction(__int64 a1, __int64 a2, int a3)
{
  REGSAM samDesired; // ebp
  HKEY *phkResult; // r12
  HKEY v8; // r15
  DWORD LastError; // ebx
  const CHAR *v10; // rbx
  const CHAR *v11; // rdx
  LSTATUS Key; // eax
  HKEY *v13; // r12
  HKEY v14; // r15
  DWORD v15; // ebx
  const CHAR *v16; // rdx
  signed int v17; // ecx
  signed int v18; // ebp
  __int64 result; // rax

  samDesired = 0;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        goto LABEL_5;
      case 2:
        samDesired = 3;
        goto LABEL_7;
      case 3:
LABEL_5:
        samDesired = 2;
        break;
    }
    if ( a3 != 3 )
    {
LABEL_7:
      phkResult = (HKEY *)(a1 + 48);
      v8 = *(HKEY *)(a1 + 48);
      if ( v8 )
      {
        LastError = GetLastError();
        RegCloseKey(v8);
        SetLastError(LastError);
      }
      v10 = (const CHAR *)(a1 + 16);
      *phkResult = 0;
      v11 = (const CHAR *)(a1 + 16);
      if ( *(_QWORD *)(a1 + 40) > 0xFu )
        v11 = *(const CHAR **)v10;
      Key = RegCreateKeyExA(*(HKEY *)(a1 + 8), v11, 0, 0, 0, samDesired, 0, phkResult, 0);
      goto LABEL_19;
    }
  }
  else
  {
    samDesired = 1;
  }
  v13 = (HKEY *)(a1 + 48);
  v14 = *(HKEY *)(a1 + 48);
  if ( v14 )
  {
    v15 = GetLastError();
    RegCloseKey(v14);
    SetLastError(v15);
  }
  v10 = (const CHAR *)(a1 + 16);
  *v13 = 0;
  v16 = (const CHAR *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) > 0xFu )
    v16 = *(const CHAR **)v10;
  Key = RegOpenKeyExA(*(HKEY *)(a1 + 8), v16, 0, samDesired, v13);
LABEL_19:
  v17 = (unsigned __int16)Key | 0x80070000;
  if ( Key <= 0 )
    v17 = Key;
  v18 = v17;
  if ( v17 == -2147024894 )
  {
    if ( a3 == 3 )
      v17 = 0;
  }
  else if ( v17 < 0 )
  {
    if ( *((_QWORD *)v10 + 3) > 0xFu )
      v10 = *(const CHAR **)v10;
    LogResult(
      2u,
      "CPersistentStoreRegistry::BeginTransaction",
      0x34u,
      v17,
      "Failed to open reg key, op: %d, key: %s",
      a3,
      v10);
    v17 = v18;
  }
  *(_QWORD *)a2 = a1;
  result = a2;
  *(_DWORD *)(a2 + 8) = v17;
  return result;
}

```

## disassembly

```asm
0x1800a0f70  mov     rax, rsp
0x1800a0f73  mov     [rax+8], rbx
0x1800a0f77  mov     [rax+10h], rbp
0x1800a0f7b  mov     [rax+18h], rsi
0x1800a0f7f  mov     [rax+20h], rdi
0x1800a0f83  push    r12
0x1800a0f85  push    r14
0x1800a0f87  push    r15
0x1800a0f89  sub     rsp, 50h
0x1800a0f8d  xor     ebp, ebp
0x1800a0f8f  mov     edi, r8d
0x1800a0f92  mov     r14, rdx
0x1800a0f95  mov     rsi, rcx
0x1800a0f98  mov     r9d, r8d
0x1800a0f9b  test    r8d, r8d
0x1800a0f9e  jz      loc_1800A104B
0x1800a0fa4  sub     r9d, 1
0x1800a0fa8  jz      short loc_1800A0FBA
0x1800a0faa  sub     r9d, 1
0x1800a0fae  jz      loc_1800A1044
0x1800a0fb4  cmp     r9d, 1
0x1800a0fb8  jnz     short loc_1800A0FBF
0x1800a0fba  mov     ebp, 2
0x1800a0fbf  test    edi, edi
0x1800a0fc1  jz      loc_1800A1050
0x1800a0fc7  cmp     edi, 3
0x1800a0fca  jz      loc_1800A1050
0x1800a0fd0  lea     r12, [rcx+30h]
0x1800a0fd4  mov     r15, [r12]
0x1800a0fd8  test    r15, r15
0x1800a0fdb  jz      short loc_1800A0FF6
0x1800a0fdd  call    cs:__imp_GetLastError
0x1800a0fe3  mov     rcx, r15; hKey
0x1800a0fe6  mov     ebx, eax
0x1800a0fe8  call    cs:__imp_RegCloseKey
0x1800a0fee  mov     ecx, ebx; dwErrCode
0x1800a0ff0  call    cs:__imp_SetLastError
0x1800a0ff6  lea     rbx, [rsi+10h]
0x1800a0ffa  mov     qword ptr [r12], 0
0x1800a1002  cmp     qword ptr [rbx+18h], 0Fh
0x1800a1007  mov     rdx, rbx
0x1800a100a  jbe     short loc_1800A100F
0x1800a100c  mov     rdx, [rbx]; lpSubKey
0x1800a100f  mov     rcx, [rsi+8]; hKey
0x1800a1013  xor     r9d, r9d; lpClass
0x1800a1016  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x1800a101f  xor     r8d, r8d; Reserved
0x1800a1022  mov     [rsp+68h+phkResult], r12; phkResult
0x1800a1027  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a1030  mov     [rsp+68h+samDesired], ebp; samDesired
0x1800a1034  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800a103c  call    cs:__imp_RegCreateKeyExA
0x1800a1042  jmp     short loc_1800A10A4
0x1800a1044  mov     ebp, 3
0x1800a1049  jmp     short loc_1800A0FD0
0x1800a104b  mov     ebp, 1
0x1800a1050  lea     r12, [rcx+30h]
0x1800a1054  mov     r15, [r12]
0x1800a1058  test    r15, r15
0x1800a105b  jz      short loc_1800A1076
0x1800a105d  call    cs:__imp_GetLastError
0x1800a1063  mov     rcx, r15; hKey
0x1800a1066  mov     ebx, eax
0x1800a1068  call    cs:__imp_RegCloseKey
0x1800a106e  mov     ecx, ebx; dwErrCode
0x1800a1070  call    cs:__imp_SetLastError
0x1800a1076  lea     rbx, [rsi+10h]
0x1800a107a  mov     qword ptr [r12], 0
0x1800a1082  cmp     qword ptr [rbx+18h], 0Fh
0x1800a1087  mov     rdx, rbx
0x1800a108a  jbe     short loc_1800A108F
0x1800a108c  mov     rdx, [rbx]; lpSubKey
0x1800a108f  mov     rcx, [rsi+8]; hKey
0x1800a1093  mov     r9d, ebp; samDesired
0x1800a1096  xor     r8d, r8d; ulOptions
0x1800a1099  mov     qword ptr [rsp+68h+dwOptions], r12; phkResult
0x1800a109e  call    cs:__imp_RegOpenKeyExA
0x1800a10a4  movzx   ecx, ax
0x1800a10a7  or      ecx, 80070000h
0x1800a10ad  test    eax, eax
0x1800a10af  cmovle  ecx, eax
0x1800a10b2  mov     ebp, ecx
0x1800a10b4  cmp     ecx, 80070002h
0x1800a10ba  jnz     short loc_1800A10C5
0x1800a10bc  cmp     edi, 3
0x1800a10bf  jnz     short loc_1800A1103
0x1800a10c1  xor     ecx, ecx
0x1800a10c3  jmp     short loc_1800A1103
0x1800a10c5  test    ebp, ebp
0x1800a10c7  jns     short loc_1800A1103
0x1800a10c9  cmp     qword ptr [rbx+18h], 0Fh
0x1800a10ce  jbe     short loc_1800A10D3
0x1800a10d0  mov     rbx, [rbx]
0x1800a10d3  mov     r8d, 34h ; '4'; unsigned int
0x1800a10d9  mov     [rsp+68h+lpSecurityAttributes], rbx
0x1800a10de  lea     rax, aFailedToOpenRe; "Failed to open reg key, op: %d, key: %s"
0x1800a10e5  mov     [rsp+68h+samDesired], edi
0x1800a10e9  mov     r9d, ebp; int
0x1800a10ec  mov     qword ptr [rsp+68h+dwOptions], rax; char *
0x1800a10f1  lea     rdx, aCpersistentsto; "CPersistentStoreRegistry::BeginTransact"...
0x1800a10f8  lea     ecx, [r8-32h]; unsigned __int8
0x1800a10fc  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800a1101  mov     ecx, ebp
0x1800a1103  lea     r11, [rsp+68h+var_18]
0x1800a1108  mov     [r14], rsi
0x1800a110b  mov     rbx, [r11+20h]
0x1800a110f  mov     rax, r14
0x1800a1112  mov     rbp, [r11+28h]
0x1800a1116  mov     rsi, [r11+30h]
0x1800a111a  mov     rdi, [r11+38h]
0x1800a111e  mov     [r14+8], ecx
0x1800a1122  mov     rsp, r11
0x1800a1125  pop     r15
0x1800a1127  pop     r14
0x1800a1129  pop     r12
0x1800a112b  retn
```
