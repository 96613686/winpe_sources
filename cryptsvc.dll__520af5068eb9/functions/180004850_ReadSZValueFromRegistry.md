# _ReadSZValueFromRegistry

- ea: `0x180004850`
- end: `0x180004956`
- name: `_ReadSZValueFromRegistry`
- size: `262`
- prototype: `BYTE *__fastcall(HKEY hKey, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004530`
- `0x180005bd0`

## callees

- `0x1800042e0`
- `0x180004850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800048d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800048d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000488b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004927`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000488b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004927`

## pseudocode

```c
BYTE *__fastcall ReadSZValueFromRegistry(HKEY hKey, __int64 a2)
{
  LSTATUS v3; // eax
  BYTE *lpData; // rbx
  DWORD v5; // ecx
  DWORD LastError; // edi
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  int v9; // [rsp+5Ch] [rbp+14h]
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  DWORD lpcbData; // [rsp+68h] [rbp+20h] BYREF

  v9 = HIDWORD(a2);
  Type = 0;
  cbData = 0;
  lpcbData = 0;
  v3 = RegQueryValueExW(hKey, L"RootDirUrl", 0, &Type, 0, &cbData);
  if ( v3 )
  {
    v5 = v3;
    goto LABEL_8;
  }
  lpData = 0;
  if ( Type != 1 || cbData < 2 )
    goto LABEL_6;
  if ( cbData > 0xFFFF )
  {
    v5 = 534;
LABEL_8:
    SetLastError(v5);
    return 0;
  }
  lpData = (BYTE *)PkiNonzeroAlloc(cbData + 2LL);
  if ( !lpData )
    return 0;
  lpcbData = cbData;
  if ( RegQueryValueExW(hKey, L"RootDirUrl", 0, &Type, lpData, &lpcbData) || lpcbData != cbData )
  {
LABEL_6:
    SetLastError(0xDu);
    if ( !lpData )
      return 0;
    goto LABEL_7;
  }
  *(_WORD *)&lpData[2 * ((unsigned __int64)lpcbData >> 1)] = 0;
  if ( !*(_WORD *)lpData )
  {
LABEL_7:
    LastError = GetLastError();
    LocalFree(lpData);
    v5 = LastError;
    goto LABEL_8;
  }
  return lpData;
}

```

## disassembly

```asm
0x180004850  mov     qword ptr [rsp+cbData], rdx
0x180004855  push    rbx
0x180004856  push    rsi
0x180004857  push    rdi
0x180004858  sub     rsp, 30h
0x18000485c  xor     esi, esi
0x18000485e  lea     rax, [rsp+48h+cbData]
0x180004863  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180004868  lea     r9, [rsp+48h+Type]; lpType
0x18000486d  xor     r8d, r8d; lpReserved
0x180004870  mov     [rsp+48h+lpData], rsi; lpData
0x180004875  lea     rdx, aRootdirurl; "RootDirUrl"
0x18000487c  mov     [rsp+48h+Type], esi
0x180004880  mov     rdi, rcx
0x180004883  mov     [rsp+48h+cbData], esi
0x180004887  mov     [rsp+48h+arg_18], esi
0x18000488b  call    cs:__imp_RegQueryValueExW
0x180004891  test    eax, eax
0x180004893  jnz     short loc_1800048E9
0x180004895  cmp     [rsp+48h+Type], 1
0x18000489a  mov     ebx, esi
0x18000489c  jnz     short loc_1800048B5
0x18000489e  mov     eax, [rsp+48h+cbData]
0x1800048a2  cmp     eax, 2
0x1800048a5  jb      short loc_1800048B5
0x1800048a7  cmp     eax, 0FFFFh
0x1800048ac  jbe     short loc_1800048ED
0x1800048ae  mov     ecx, 216h
0x1800048b3  jmp     short loc_1800048D8
0x1800048b5  mov     ecx, 0Dh; dwErrCode
0x1800048ba  call    cs:__imp_SetLastError
0x1800048c0  test    rbx, rbx
0x1800048c3  jz      short loc_1800048DE
0x1800048c5  call    cs:__imp_GetLastError
0x1800048cb  mov     rcx, rbx; hMem
0x1800048ce  mov     edi, eax
0x1800048d0  call    cs:__imp_LocalFree
0x1800048d6  mov     ecx, edi; dwErrCode
0x1800048d8  call    cs:__imp_SetLastError
0x1800048de  mov     rax, rsi
0x1800048e1  add     rsp, 30h
0x1800048e5  pop     rdi
0x1800048e6  pop     rsi
0x1800048e7  pop     rbx
0x1800048e8  retn
0x1800048e9  mov     ecx, eax
0x1800048eb  jmp     short loc_1800048D8
0x1800048ed  lea     rcx, [rax+2]; uBytes
0x1800048f1  call    PkiNonzeroAlloc
0x1800048f6  mov     rbx, rax
0x1800048f9  test    rax, rax
0x1800048fc  jz      short loc_1800048DE
0x1800048fe  mov     eax, [rsp+48h+cbData]
0x180004902  lea     r9, [rsp+48h+Type]; lpType
0x180004907  mov     [rsp+48h+arg_18], eax
0x18000490b  lea     rdx, aRootdirurl; "RootDirUrl"
0x180004912  lea     rax, [rsp+48h+arg_18]
0x180004917  xor     r8d, r8d; lpReserved
0x18000491a  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000491f  mov     rcx, rdi; hKey
0x180004922  mov     [rsp+48h+lpData], rbx; lpData
0x180004927  call    cs:__imp_RegQueryValueExW
0x18000492d  test    eax, eax
0x18000492f  jnz     short loc_1800048B5
0x180004931  mov     eax, [rsp+48h+arg_18]
0x180004935  cmp     eax, [rsp+48h+cbData]
0x180004939  jnz     loc_1800048B5
0x18000493f  mov     ecx, eax
0x180004941  shr     rcx, 1
0x180004944  mov     [rbx+rcx*2], si
0x180004948  cmp     si, [rbx]
0x18000494b  jz      loc_1800048C5
0x180004951  mov     rax, rbx
0x180004954  jmp     short loc_1800048E1
```
