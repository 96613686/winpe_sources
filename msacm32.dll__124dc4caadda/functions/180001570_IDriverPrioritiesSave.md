# IDriverPrioritiesSave

- ea: `0x180001570`
- end: `0x1800017e8`
- name: `IDriverPrioritiesSave`
- size: `632`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800089c0`
- `0x180008c00`
- `0x180008d00`

## callees

- `0x180001570`
- `0x180001c40`
- `0x180001cd0`
- `0x180002220`
- `0x180007cf0`
- `0x180009270`
- `0x180012020`
- `0x1800120a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001763`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001763`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800016ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800016ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000177f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000177f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001775`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001775`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800017a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800017ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800017a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800017ab`

## pseudocode

```c
HKEY __fastcall IDriverPrioritiesSave(__int64 a1)
{
  HKEY result; // rax
  HKEY v3; // rbp
  char *v4; // r14
  char *v5; // rbx
  __int64 v6; // rsi
  unsigned int v7; // edi
  char *v8; // rax
  __int64 v9; // rcx
  const BYTE *lpData; // rcx
  __int64 v11; // rax
  bool v12; // zf
  char *v13; // rbx
  __int64 v14; // [rsp+30h] [rbp-98h] BYREF
  __int64 v15; // [rsp+38h] [rbp-90h] BYREF
  int v16; // [rsp+40h] [rbp-88h]
  HLOCAL hMem; // [rsp+44h] [rbp-84h]
  wchar_t pszDest[32]; // [rsp+50h] [rbp-78h] BYREF

  v15 = 0;
  v16 = 0;
  v14 = 0;
  result = IRegOpenKeyAcm(L"Priority v4.00");
  v3 = result;
  if ( !result )
    return result;
  hMem = 0;
  IPrioritiesThunklistCreate(a1, &v15);
  v4 = (char *)hMem;
  v5 = (char *)hMem;
  IDriverGetNext(a1, &v14, 0, 3221225472LL);
  v6 = v14;
  v7 = 1;
  while ( v5 || v6 )
  {
    StringCchPrintfW(pszDest, 0x20u, L"Priority%u", v7);
    if ( v5 && *(_DWORD *)v5 )
    {
      if ( v6 )
      {
        v8 = v5;
        while ( 1 )
        {
          v8 = *(char **)(v8 + 12);
          if ( !v8 )
            break;
          if ( !*(_DWORD *)v8 )
          {
            v9 = *(_QWORD *)(v8 + 4);
            goto LABEL_13;
          }
        }
        v9 = 0;
LABEL_13:
        if ( v6 != v9 )
        {
          IDriverPrioritiesWriteHadid(v3, pszDest, v6);
LABEL_15:
          IPrioritiesThunklistRemoveHadid(v5, v6);
          goto LABEL_16;
        }
      }
      lpData = *(const BYTE **)(v5 + 4);
      v11 = -1;
      do
        v12 = *(_WORD *)&lpData[2 * v11++ + 2] == 0;
      while ( !v12 );
      RegSetValueExW(v3, pszDest, 0, 1u, lpData, 2 * v11 + 2);
      v5 = *(char **)(v5 + 12);
      ++v7;
    }
    else
    {
      IDriverPrioritiesWriteHadid(v3, pszDest, v6);
      if ( v5 )
      {
        if ( v6 != *(_QWORD *)(v5 + 4) )
          goto LABEL_15;
        v5 = *(char **)(v5 + 12);
      }
LABEL_16:
      IDriverGetNext(a1, &v14, v6, 3221225472LL);
      v6 = v14;
      ++v7;
    }
  }
  while ( 1 )
  {
    StringCchPrintfW(pszDest, 0x20u, L"Priority%u", v7);
    if ( RegQueryValueExW(v3, pszDest, 0, 0, 0, 0) )
      break;
    RegDeleteValueW(v3, pszDest);
    ++v7;
  }
  RegCloseKey(v3);
  while ( v4 )
  {
    v12 = *(_DWORD *)v4 == 0;
    v13 = v4;
    v4 = *(char **)(v4 + 12);
    if ( !v12 )
      LocalFree(*(HLOCAL *)(v13 + 4));
    LocalFree(v13);
  }
  return (HKEY)1;
}

```

## disassembly

```asm
0x180001570  push    rbp
0x180001572  push    r12
0x180001574  push    r15
0x180001576  sub     rsp, 0B0h
0x18000157d  mov     rax, cs:__security_cookie
0x180001584  xor     rax, rsp
0x180001587  mov     [rsp+0C8h+var_38], rax
0x18000158f  xor     r12d, r12d
0x180001592  mov     r15, rcx
0x180001595  lea     rcx, gszSecPriority; "Priority v4.00"
0x18000159c  mov     [rsp+0C8h+var_90], r12
0x1800015a1  mov     [rsp+0C8h+var_88], r12d
0x1800015a6  mov     [rsp+0C8h+var_98], r12
0x1800015ab  call    IRegOpenKeyAcm
0x1800015b0  mov     rbp, rax
0x1800015b3  test    rax, rax
0x1800015b6  jz      loc_1800017CB
0x1800015bc  mov     [rsp+0C8h+arg_8], rbx
0x1800015c4  lea     rdx, [rsp+0C8h+var_90]
0x1800015c9  mov     [rsp+0C8h+arg_10], rsi
0x1800015d1  mov     rcx, r15
0x1800015d4  mov     [rsp+0C8h+var_20], rdi
0x1800015dc  mov     [rsp+0C8h+var_28], r14
0x1800015e4  mov     [rsp+0C8h+hMem], r12
0x1800015e9  call    IPrioritiesThunklistCreate
0x1800015ee  mov     r14, [rsp+0C8h+hMem]
0x1800015f3  lea     rdx, [rsp+0C8h+var_98]
0x1800015f8  mov     r9d, 0C0000000h
0x1800015fe  xor     r8d, r8d
0x180001601  mov     rcx, r15
0x180001604  mov     rbx, r14
0x180001607  call    IDriverGetNext
0x18000160c  mov     rsi, [rsp+0C8h+var_98]
0x180001611  mov     edi, 1
0x180001616  test    rbx, rbx
0x180001619  jnz     short loc_180001624
0x18000161b  test    rsi, rsi
0x18000161e  jz      loc_18000172A
0x180001624  mov     r9d, edi
0x180001627  lea     r8, gszKeyPriority; "Priority%u"
0x18000162e  mov     edx, 20h ; ' '; cchDest
0x180001633  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x180001638  call    StringCchPrintfW
0x18000163d  test    rbx, rbx
0x180001640  jz      loc_1800016FE
0x180001646  cmp     [rbx], r12d
0x180001649  jz      loc_1800016FE
0x18000164f  test    rsi, rsi
0x180001652  jz      short loc_1800016B0
0x180001654  mov     rax, rbx
0x180001657  mov     rax, [rax+0Ch]
0x18000165b  test    rax, rax
0x18000165e  jz      short loc_18000166B
0x180001660  cmp     [rax], r12d
0x180001663  jnz     short loc_180001657
0x180001665  mov     rcx, [rax+4]
0x180001669  jmp     short loc_18000166E
0x18000166b  mov     rcx, r12
0x18000166e  cmp     rsi, rcx
0x180001671  jz      short loc_1800016B0
0x180001673  mov     r8, rsi
0x180001676  lea     rdx, [rsp+0C8h+pszDest]
0x18000167b  mov     rcx, rbp
0x18000167e  call    IDriverPrioritiesWriteHadid
0x180001683  mov     rdx, rsi
0x180001686  mov     rcx, rbx
0x180001689  call    IPrioritiesThunklistRemoveHadid
0x18000168e  mov     r9d, 0C0000000h
0x180001694  lea     rdx, [rsp+0C8h+var_98]
0x180001699  mov     r8, rsi
0x18000169c  mov     rcx, r15
0x18000169f  call    IDriverGetNext
0x1800016a4  mov     rsi, [rsp+0C8h+var_98]
0x1800016a9  inc     edi
0x1800016ab  jmp     loc_180001616
0x1800016b0  mov     rcx, [rbx+4]
0x1800016b4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800016bb  nop     dword ptr [rax+rax+00h]
0x1800016c0  cmp     [rcx+rax*2+2], r12w
0x1800016c6  lea     rax, [rax+1]
0x1800016ca  jnz     short loc_1800016C0
0x1800016cc  lea     eax, ds:2[rax*2]
0x1800016d3  mov     r9d, 1; dwType
0x1800016d9  mov     [rsp+0C8h+cbData], eax; cbData
0x1800016dd  lea     rdx, [rsp+0C8h+pszDest]; lpValueName
0x1800016e2  mov     [rsp+0C8h+lpData], rcx; lpData
0x1800016e7  xor     r8d, r8d; Reserved
0x1800016ea  mov     rcx, rbp; hKey
0x1800016ed  call    cs:__imp_RegSetValueExW
0x1800016f3  mov     rbx, [rbx+0Ch]
0x1800016f7  inc     edi
0x1800016f9  jmp     loc_180001616
0x1800016fe  mov     r8, rsi
0x180001701  lea     rdx, [rsp+0C8h+pszDest]
0x180001706  mov     rcx, rbp
0x180001709  call    IDriverPrioritiesWriteHadid
0x18000170e  test    rbx, rbx
0x180001711  jz      loc_18000168E
0x180001717  cmp     rsi, [rbx+4]
0x18000171b  jnz     loc_180001683
0x180001721  mov     rbx, [rbx+0Ch]
0x180001725  jmp     loc_18000168E
0x18000172a  mov     rsi, [rsp+0C8h+arg_10]
0x180001732  mov     r9d, edi
0x180001735  lea     r8, gszKeyPriority; "Priority%u"
0x18000173c  mov     edx, 20h ; ' '; cchDest
0x180001741  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x180001746  call    StringCchPrintfW
0x18000174b  xor     r9d, r9d; lpType
0x18000174e  mov     qword ptr [rsp+0C8h+cbData], r12; lpcbData
0x180001753  xor     r8d, r8d; lpReserved
0x180001756  mov     [rsp+0C8h+lpData], r12; lpData
0x18000175b  lea     rdx, [rsp+0C8h+pszDest]; lpValueName
0x180001760  mov     rcx, rbp; hKey
0x180001763  call    cs:__imp_RegQueryValueExW
0x180001769  mov     rcx, rbp; hKey
0x18000176c  test    eax, eax
0x18000176e  jnz     short loc_18000177F
0x180001770  lea     rdx, [rsp+0C8h+pszDest]; lpValueName
0x180001775  call    cs:__imp_RegDeleteValueW
0x18000177b  inc     edi
0x18000177d  jmp     short loc_180001732
0x18000177f  call    cs:__imp_RegCloseKey
0x180001785  mov     rdi, [rsp+0C8h+var_20]
0x18000178d  test    r14, r14
0x180001790  jz      short loc_1800017B6
0x180001792  cmp     [r14], r12d
0x180001795  mov     rbx, r14
0x180001798  mov     r14, [r14+0Ch]
0x18000179c  jz      short loc_1800017A8
0x18000179e  mov     rcx, [rbx+4]; hMem
0x1800017a2  call    cs:__imp_LocalFree
0x1800017a8  mov     rcx, rbx; hMem
0x1800017ab  call    cs:__imp_LocalFree
0x1800017b1  test    r14, r14
0x1800017b4  jnz     short loc_180001792
0x1800017b6  mov     r14, [rsp+0C8h+var_28]
0x1800017be  mov     eax, 1
0x1800017c3  mov     rbx, [rsp+0C8h+arg_8]
0x1800017cb  mov     rcx, [rsp+0C8h+var_38]
0x1800017d3  xor     rcx, rsp; StackCookie
0x1800017d6  call    __security_check_cookie
0x1800017db  add     rsp, 0B0h
0x1800017e2  pop     r15
0x1800017e4  pop     r12
0x1800017e6  pop     rbp
0x1800017e7  retn
```
