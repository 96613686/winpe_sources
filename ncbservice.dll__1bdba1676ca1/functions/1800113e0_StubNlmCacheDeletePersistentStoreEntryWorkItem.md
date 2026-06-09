# StubNlmCacheDeletePersistentStoreEntryWorkItem

- ea: `0x1800113e0`
- end: `0x180011583`
- name: `StubNlmCacheDeletePersistentStoreEntryWorkItem`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800113e0`
- `0x180011758`
- `0x18001182c`
- `0x180011930`
- `0x180011c70`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800114eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800114eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800114de`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800114de`

## pseudocode

```c
__int64 __fastcall StubNlmCacheDeletePersistentStoreEntryWorkItem(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int *v3; // rbx
  unsigned int v4; // eax
  PVOID *v5; // rcx
  __int64 v6; // rcx
  __int64 result; // rax
  HKEY hKey; // [rsp+20h] [rbp-78h] BYREF
  wchar_t pszDest[8]; // [rsp+28h] [rbp-70h] BYREF
  __int128 v10; // [rsp+38h] [rbp-60h]
  _BYTE v11[28]; // [rsp+48h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  v2 = *(_QWORD *)(a1 + 40);
  v3 = *(unsigned int **)(a1 + 32);
  memset(v11, 0, sizeof(v11));
  hKey = 0;
  *(_OWORD *)pszDest = 0;
  v10 = 0;
  v4 = StubNlmCacheOpenPersistentStore(v2, &hKey);
  if ( !v4 )
    goto LABEL_10;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v4);
LABEL_10:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 && *((_BYTE *)v5 + 25) >= 2u )
      WPP_SF_(v5[2], 121, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  else
  {
    if ( v3 )
    {
      StringCbPrintfW(pszDest, 0x3Cu, L"%ld", *v3);
      RegDeleteKeyExW(hKey, pszDest, 0x300u, 0);
    }
    else
    {
      RegDeleteTreeW(hKey, 0);
    }
    StubNlmCacheClosePersistentStore(v6, hKey);
  }
  result = (*(__int64 (__fastcall **)(__int64))(v2 + 48))(a1);
  if ( v3 )
    result = StubNlmCacheDereferenceEntry(v2, v3);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x1800113e0  push    rbx
0x1800113e2  push    rsi
0x1800113e3  push    rdi
0x1800113e4  push    r14
0x1800113e6  sub     rsp, 78h
0x1800113ea  mov     rax, cs:__security_cookie
0x1800113f1  xor     rax, rsp
0x1800113f4  mov     [rsp+98h+var_30], rax
0x1800113f9  mov     rsi, rcx
0x1800113fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011403  lea     r14, WPP_GLOBAL_Control
0x18001140a  cmp     rcx, r14
0x18001140d  jz      short loc_180011430
0x18001140f  test    byte ptr [rcx+1Ch], 4
0x180011413  jz      short loc_180011430
0x180011415  cmp     byte ptr [rcx+19h], 6
0x180011419  jb      short loc_180011430
0x18001141b  mov     rcx, [rcx+10h]
0x18001141f  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x180011426  mov     edx, 77h ; 'w'
0x18001142b  call    WPP_SF_
0x180011430  mov     rdi, [rsi+28h]
0x180011434  lea     rdx, [rsp+98h+hKey]
0x180011439  mov     rbx, [rsi+20h]
0x18001143d  xorps   xmm0, xmm0
0x180011440  xor     eax, eax
0x180011442  mov     rcx, rdi
0x180011445  movups  xmmword ptr [rsp+98h+var_50], xmm0
0x18001144a  mov     [rsp+98h+hKey], rax
0x18001144f  movups  xmmword ptr [rsp+98h+var_50+0Ch], xmm0
0x180011454  movups  xmmword ptr [rsp+98h+pszDest], xmm0
0x180011459  movups  [rsp+98h+var_60], xmm0
0x18001145e  call    StubNlmCacheOpenPersistentStore
0x180011463  test    eax, eax
0x180011465  jz      short loc_180011497
0x180011467  mov     rcx, cs:WPP_GLOBAL_Control
0x18001146e  cmp     rcx, r14
0x180011471  jz      short loc_18001149E
0x180011473  test    byte ptr [rcx+1Ch], 4
0x180011477  jz      short loc_18001149E
0x180011479  cmp     byte ptr [rcx+19h], 2
0x18001147d  jb      short loc_18001149E
0x18001147f  mov     rcx, [rcx+10h]
0x180011483  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x18001148a  mov     edx, 78h ; 'x'
0x18001148f  mov     r9d, eax
0x180011492  call    WPP_SF_d
0x180011497  mov     rcx, cs:WPP_GLOBAL_Control
0x18001149e  mov     r8, [rsp+98h+hKey]
0x1800114a3  lea     rax, [r8-1]
0x1800114a7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800114ab  ja      short loc_1800114FD
0x1800114ad  test    rbx, rbx
0x1800114b0  jz      short loc_1800114E6
0x1800114b2  mov     r9d, [rbx]
0x1800114b5  lea     r8, aLd; "%ld"
0x1800114bc  mov     edx, 3Ch ; '<'; cbDest
0x1800114c1  lea     rcx, [rsp+98h+pszDest]; pszDest
0x1800114c6  call    StringCbPrintfW
0x1800114cb  mov     rcx, [rsp+98h+hKey]; hKey
0x1800114d0  lea     rdx, [rsp+98h+pszDest]; lpSubKey
0x1800114d5  xor     r9d, r9d; Reserved
0x1800114d8  mov     r8d, 300h; samDesired
0x1800114de  call    cs:__imp_RegDeleteKeyExW
0x1800114e4  jmp     short loc_1800114F1
0x1800114e6  xor     edx, edx; lpSubKey
0x1800114e8  mov     rcx, r8; hKey
0x1800114eb  call    cs:__imp_RegDeleteTreeW
0x1800114f1  mov     rdx, [rsp+98h+hKey]
0x1800114f6  call    StubNlmCacheClosePersistentStore
0x1800114fb  jmp     short loc_180011523
0x1800114fd  cmp     rcx, r14
0x180011500  jz      short loc_180011523
0x180011502  test    byte ptr [rcx+1Ch], 4
0x180011506  jz      short loc_180011523
0x180011508  cmp     byte ptr [rcx+19h], 2
0x18001150c  jb      short loc_180011523
0x18001150e  mov     rcx, [rcx+10h]
0x180011512  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x180011519  mov     edx, 79h ; 'y'
0x18001151e  call    WPP_SF_
0x180011523  mov     rax, [rdi+30h]
0x180011527  mov     rcx, rsi
0x18001152a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001152f  test    rbx, rbx
0x180011532  jz      short loc_18001153F
0x180011534  mov     rdx, rbx
0x180011537  mov     rcx, rdi
0x18001153a  call    StubNlmCacheDereferenceEntry
0x18001153f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011546  cmp     rcx, r14
0x180011549  jz      short loc_18001156C
0x18001154b  test    byte ptr [rcx+1Ch], 4
0x18001154f  jz      short loc_18001156C
0x180011551  cmp     byte ptr [rcx+19h], 6
0x180011555  jb      short loc_18001156C
0x180011557  mov     rcx, [rcx+10h]
0x18001155b  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x180011562  mov     edx, 7Ah ; 'z'
0x180011567  call    WPP_SF_
0x18001156c  mov     rcx, [rsp+98h+var_30]
0x180011571  xor     rcx, rsp; StackCookie
0x180011574  call    __security_check_cookie
0x180011579  add     rsp, 78h
0x18001157d  pop     r14
0x18001157f  pop     rdi
0x180011580  pop     rsi
0x180011581  pop     rbx
0x180011582  retn
```
