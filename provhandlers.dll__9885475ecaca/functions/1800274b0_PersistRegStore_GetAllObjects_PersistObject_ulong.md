# PersistRegStore::GetAllObjects(PersistObject * *,ulong *)

- ea: `0x1800274b0`
- end: `0x1800276aa`
- name: `?GetAllObjects@PersistRegStore@@UEAAJPEAPEAVPersistObject@@PEAK@Z`
- size: `506`
- prototype: `__int64 __fastcall(HKEY *this, struct PersistObject **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800274b0`
- `0x18002812c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002763f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002763f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027669`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027549`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027549`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027607`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027607`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800275de`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800275de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002765f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002765f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002758c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002758c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistRegStore::GetAllObjects(HKEY *this, struct PersistObject **a2, unsigned int *a3)
{
  struct PersistObject *v3; // rdi
  WCHAR *v4; // r15
  signed int ObjectFromKey; // ebx
  LSTATUS v9; // eax
  bool v10; // cc
  SIZE_T v11; // rdx
  DWORD v12; // eax
  __int64 v13; // r14
  HKEY v14; // rcx
  PersistRegStore *v15; // rcx
  DWORD cchName; // [rsp+60h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-18h] BYREF
  struct PersistObject *v19; // [rsp+70h] [rbp-10h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+C8h] [rbp+48h] BYREF
  DWORD cSubKeys; // [rsp+D8h] [rbp+58h] BYREF

  v3 = 0;
  cSubKeys = 0;
  v4 = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  phkResult = 0;
  v19 = 0;
  if ( !a2 || !a3 )
  {
    ObjectFromKey = -2147467261;
    goto LABEL_17;
  }
  v9 = RegQueryInfoKeyW(this[2], 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  ObjectFromKey = v9;
  v10 = v9 <= 0;
  if ( !v9 )
  {
    if ( *a3 < cSubKeys )
    {
      ObjectFromKey = -2147024809;
      goto LABEL_17;
    }
    v11 = 2LL * ++cbMaxSubKeyLen;
    v4 = (WCHAR *)LocalAlloc(0x40u, v11);
    if ( !v4 )
    {
      ObjectFromKey = -2147024882;
      goto LABEL_17;
    }
    v12 = cSubKeys;
    ObjectFromKey = 0;
    v13 = 0;
    if ( !cSubKeys )
    {
LABEL_16:
      *a3 = v12;
      goto LABEL_17;
    }
    while ( 1 )
    {
      v14 = this[2];
      cchName = cbMaxSubKeyLen;
      v9 = RegEnumKeyExW(v14, v13, v4, &cchName, 0, 0, 0, 0);
      ObjectFromKey = v9;
      v10 = v9 <= 0;
      if ( v9 )
        break;
      v9 = RegOpenKeyExW(this[2], v4, 0, 0xF003Fu, &phkResult);
      ObjectFromKey = v9;
      v10 = v9 <= 0;
      if ( v9 )
        break;
      ObjectFromKey = PersistRegStore::GetObjectFromKey(v15, phkResult, v4, &v19);
      if ( ObjectFromKey < 0 )
      {
        v3 = v19;
        goto LABEL_17;
      }
      v3 = 0;
      a2[v13] = v19;
      v19 = 0;
      RegCloseKey(phkResult);
      v12 = cSubKeys;
      v13 = (unsigned int)(v13 + 1);
      phkResult = 0;
      if ( (unsigned int)v13 >= cSubKeys )
        goto LABEL_16;
    }
  }
  if ( !v10 )
    ObjectFromKey = (unsigned __int16)v9 | 0x80070000;
LABEL_17:
  LocalFree(v4);
  RegCloseKey(phkResult);
  if ( v3 )
    (**(void (__fastcall ***)(struct PersistObject *, __int64))v3)(v3, 1);
  return (unsigned int)ObjectFromKey;
}

```

## disassembly

```asm
0x1800274b0  mov     [rsp-38h+arg_0], rbx
0x1800274b5  push    rbp
0x1800274b6  push    rsi
0x1800274b7  push    rdi
0x1800274b8  push    r12
0x1800274ba  push    r13
0x1800274bc  push    r14
0x1800274be  push    r15
0x1800274c0  mov     rbp, rsp
0x1800274c3  sub     rsp, 80h
0x1800274ca  xor     edi, edi
0x1800274cc  mov     [rbp+cSubKeys], 0
0x1800274d3  xor     r15d, r15d
0x1800274d6  mov     [rbp+cbMaxSubKeyLen], 0
0x1800274dd  mov     [rbp+cchName], 0
0x1800274e4  mov     rsi, r8
0x1800274e7  mov     [rbp+phkResult], 0
0x1800274ef  mov     r12, rdx
0x1800274f2  mov     [rbp+var_10], rdi
0x1800274f6  mov     r13, rcx
0x1800274f9  test    rdx, rdx
0x1800274fc  jnz     short loc_180027508
0x1800274fe  mov     ebx, 80004003h
0x180027503  jmp     loc_18002765C
0x180027508  test    rsi, rsi
0x18002750b  jz      short loc_1800274FE
0x18002750d  mov     rcx, [rcx+10h]; hKey
0x180027511  lea     rax, [rbp+cbMaxSubKeyLen]
0x180027515  mov     [rsp+80h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18002751a  xor     r9d, r9d; lpReserved
0x18002751d  mov     [rsp+80h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180027522  xor     r8d, r8d; lpcchClass
0x180027525  mov     [rsp+80h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18002752a  xor     edx, edx; lpClass
0x18002752c  mov     [rsp+80h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180027531  mov     [rsp+80h+lpcValues], rdi; lpcValues
0x180027536  mov     [rsp+80h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18002753b  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180027540  lea     rax, [rbp+cSubKeys]
0x180027544  mov     [rsp+80h+lpcSubKeys], rax; lpcSubKeys
0x180027549  call    cs:__imp_RegQueryInfoKeyW
0x18002754f  mov     ebx, eax
0x180027551  test    eax, eax
0x180027553  jz      short loc_180027569
0x180027555  jle     loc_18002765C
0x18002755b  movzx   ebx, ax
0x18002755e  or      ebx, 80070000h
0x180027564  jmp     loc_18002765C
0x180027569  mov     eax, [rbp+cSubKeys]
0x18002756c  cmp     [rsi], eax
0x18002756e  jnb     short loc_18002757A
0x180027570  mov     ebx, 80070057h
0x180027575  jmp     loc_18002765C
0x18002757a  mov     eax, [rbp+cbMaxSubKeyLen]
0x18002757d  mov     ecx, 40h ; '@'; uFlags
0x180027582  inc     eax
0x180027584  mov     edx, eax
0x180027586  add     rdx, rdx; uBytes
0x180027589  mov     [rbp+cbMaxSubKeyLen], eax
0x18002758c  call    cs:__imp_LocalAlloc
0x180027592  mov     r15, rax
0x180027595  test    rax, rax
0x180027598  jnz     short loc_1800275A4
0x18002759a  mov     ebx, 8007000Eh
0x18002759f  jmp     loc_18002765C
0x1800275a4  mov     eax, [rbp+cSubKeys]
0x1800275a7  xor     ebx, ebx
0x1800275a9  xor     r14d, r14d
0x1800275ac  xor     ecx, ecx
0x1800275ae  test    eax, eax
0x1800275b0  jz      loc_18002765A
0x1800275b6  mov     eax, [rbp+cbMaxSubKeyLen]
0x1800275b9  lea     r9, [rbp+cchName]; lpcchName
0x1800275bd  mov     [rsp+80h+lpcValues], rcx; lpftLastWriteTime
0x1800275c2  mov     r8, r15; lpName
0x1800275c5  mov     [rsp+80h+lpcbMaxClassLen], rcx; lpcchClass
0x1800275ca  mov     edx, r14d; dwIndex
0x1800275cd  mov     [rsp+80h+lpcbMaxSubKeyLen], rcx; lpClass
0x1800275d2  mov     [rsp+80h+lpcSubKeys], rcx; lpReserved
0x1800275d7  mov     rcx, [r13+10h]; hKey
0x1800275db  mov     [rbp+cchName], eax
0x1800275de  call    cs:__imp_RegEnumKeyExW
0x1800275e4  mov     ebx, eax
0x1800275e6  test    eax, eax
0x1800275e8  jnz     loc_180027555
0x1800275ee  mov     rcx, [r13+10h]; hKey
0x1800275f2  lea     rax, [rbp+phkResult]
0x1800275f6  mov     r9d, 0F003Fh; samDesired
0x1800275fc  mov     [rsp+80h+lpcSubKeys], rax; phkResult
0x180027601  xor     r8d, r8d; ulOptions
0x180027604  mov     rdx, r15; lpSubKey
0x180027607  call    cs:__imp_RegOpenKeyExW
0x18002760d  mov     ebx, eax
0x18002760f  test    eax, eax
0x180027611  jnz     loc_180027555
0x180027617  mov     rdx, [rbp+phkResult]; HKEY
0x18002761b  lea     r9, [rbp+var_10]; struct PersistObject **
0x18002761f  mov     r8, r15; unsigned __int16 *
0x180027622  call    ?GetObjectFromKey@PersistRegStore@@IEAAJPEAUHKEY__@@PEBGPEAPEAVPersistObject@@@Z; PersistRegStore::GetObjectFromKey(HKEY__ *,ushort const *,PersistObject * *)
0x180027627  mov     ebx, eax
0x180027629  test    eax, eax
0x18002762b  js      short loc_1800276A4
0x18002762d  mov     rcx, [rbp+var_10]
0x180027631  xor     edi, edi
0x180027633  mov     [r12+r14*8], rcx
0x180027637  mov     rcx, [rbp+phkResult]; hKey
0x18002763b  mov     [rbp+var_10], rdi
0x18002763f  call    cs:__imp_RegCloseKey
0x180027645  mov     eax, [rbp+cSubKeys]
0x180027648  xor     ecx, ecx
0x18002764a  inc     r14d
0x18002764d  mov     [rbp+phkResult], rcx
0x180027651  cmp     r14d, eax
0x180027654  jb      loc_1800275B6
0x18002765a  mov     [rsi], eax
0x18002765c  mov     rcx, r15; hMem
0x18002765f  call    cs:__imp_LocalFree
0x180027665  mov     rcx, [rbp+phkResult]; hKey
0x180027669  call    cs:__imp_RegCloseKey
0x18002766f  test    rdi, rdi
0x180027672  jz      short loc_180027687
0x180027674  mov     rax, [rdi]
0x180027677  mov     edx, 1
0x18002767c  mov     rcx, rdi
0x18002767f  mov     rax, [rax]
0x180027682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027687  mov     eax, ebx
0x180027689  mov     rbx, [rsp+80h+arg_0]
0x180027691  add     rsp, 80h
0x180027698  pop     r15
0x18002769a  pop     r14
0x18002769c  pop     r13
0x18002769e  pop     r12
0x1800276a0  pop     rdi
0x1800276a1  pop     rsi
0x1800276a2  pop     rbp
0x1800276a3  retn
0x1800276a4  mov     rdi, [rbp+var_10]
0x1800276a8  jmp     short loc_18002765C
```
