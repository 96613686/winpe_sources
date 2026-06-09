# _ReadWeakConfigParameters

- ea: `0x1800a80ac`
- end: `0x1800a885c`
- name: `_ReadWeakConfigParameters`
- size: `1968`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001a570`

## callees

- `0x1800584c4`
- `0x180058efc`
- `0x180059194`
- `0x1800a80ac`
- `0x1800f31a8`
- `0x1800f3310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a881d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a882c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a883b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a881d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a882c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a883b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8105`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8130`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a815d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8105`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8130`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a815d`

## string_xrefs

- `0x1800a8122`: `SYSTEM\CurrentControlSet\Control\CI\Config`

## pseudocode

```c
void __fastcall ReadWeakConfigParameters(HKEY hKey, __int64 a2)
{
  HKEY v3; // r13
  __int64 v4; // rsi
  unsigned int v5; // r14d
  HKEY v6; // r12
  int v7; // ebx
  int WeakDWORDValue; // r15d
  HKEY v9; // r12
  int v10; // eax
  int v11; // r15d
  int v12; // ecx
  int v13; // r13d
  int v14; // r12d
  int v15; // eax
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rbx
  HKEY v19; // r12
  __int64 v20; // rbx
  int v21; // eax
  int v22; // r12d
  int v23; // r13d
  int v24; // r15d
  HKEY v25; // rcx
  __int64 v26; // rbx
  int *v27; // r15
  HKEY v28; // r12
  __int64 v29; // rbx
  __int64 v30; // rbx
  int v31; // ecx
  __int64 v32; // r14
  unsigned int v33; // eax
  __int64 v34; // r12
  __int64 v35; // rbx
  BOOL v36; // r14d
  int v37; // esi
  int v38; // esi
  int v39; // eax
  int v40; // ecx
  __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned __int64 v43; // rbx
  int v44; // ecx
  __int64 v45; // rsi
  unsigned int v46; // eax
  unsigned int v47; // eax
  HKEY v48; // [rsp+30h] [rbp-39h] BYREF
  HKEY v49; // [rsp+38h] [rbp-31h] BYREF
  __int64 v50; // [rsp+40h] [rbp-29h]
  HKEY phkResult; // [rsp+48h] [rbp-21h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-19h] BYREF
  HKEY v53; // [rsp+58h] [rbp-11h] BYREF
  int v54; // [rsp+60h] [rbp-9h]
  _QWORD v55[11]; // [rsp+68h] [rbp-1h] BYREF
  unsigned int v57; // [rsp+E0h] [rbp+77h]
  int v58; // [rsp+E8h] [rbp+7Fh]
  int v59; // [rsp+E8h] [rbp+7Fh]

  if ( !hKey )
    return;
  phkResult = 0;
  hKeya = 0;
  v53 = 0;
  v3 = hKey;
  if ( RegOpenKeyExW(hKey, L"Default", 0, 0x20119u, &phkResult) )
    phkResult = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\CI\\Config", 0, 0x20119u, &hKeya) )
    hKeya = 0;
  if ( hKeya && RegOpenKeyExW(hKeya, L"Default", 0, 0x20119u, &v53) )
    v53 = 0;
  v55[1] = phkResult;
  v4 = 0;
  v55[2] = hKeya;
  v55[3] = v53;
  v55[0] = v3;
  v57 = 0;
  do
  {
    v5 = 0;
    v50 = 0;
    do
    {
      v6 = hKeya;
      v49 = hKeya;
      v48 = v3;
      v7 = 0;
      WeakDWORDValue = ReadWeakDWORDValue(v3);
      if ( v5 == 1 )
        v7 = ReadWeakDWORDValue(v6);
      if ( WeakDWORDValue < 0 || v7 < 0 )
        goto LABEL_19;
      v9 = v53;
      v48 = phkResult;
      v49 = v53;
      WeakDWORDValue = ReadWeakDWORDValue(phkResult);
      if ( v5 == 1 )
        v7 = ReadWeakDWORDValue(v9);
      if ( WeakDWORDValue < 0 || v7 < 0 )
      {
LABEL_19:
        v10 = 0;
        if ( WeakDWORDValue < 0 )
          v10 = WeakDWORDValue;
        v11 = 0;
        if ( v7 < 0 )
          v11 = v7;
        v12 = v10 & 0x4000000C;
        v13 = v10 & 0xC000;
        v58 = v10 & 0x4000000C;
        v14 = v10 & 0x3000;
        v54 = v13;
        v15 = v10 & 0x3FF70010;
        if ( v15 )
        {
          v16 = v12 | v15;
          v17 = v50 + 2 * v4;
          *(_DWORD *)(a2 + 56 * v17 + 104) = v16;
          if ( (v16 & 0x33220000) != 0 )
            *(_QWORD *)(56 * (v17 + 2) + a2) = ReadWeakQWORDValue(v48);
          ReadWeakAfterTimeValue(v48, 0, 56 * v17 + a2 + 120);
          v12 = v58;
          v13 = v54;
        }
        v18 = v50 + 2 * v4;
        if ( v14 )
        {
          *(_DWORD *)(56 * v18 + a2 + 104) |= v12 | v14;
          v19 = v48;
          ReadWeakAfterTimeValue(v48, 1, a2 + 56 * v18 + 128);
        }
        else
        {
          v19 = v48;
        }
        v20 = 56 * v18;
        if ( v13 )
        {
          *(_DWORD *)(v20 + a2 + 104) |= v58 | v13;
          ReadWeakAfterTimeValue(v19, 1, v20 + a2 + 136);
        }
        v21 = v11 & 0x4000000C;
        v22 = v11 & 0x3000;
        v59 = v11 & 0x4000000C;
        v23 = v11 & 0xC000;
        v24 = v11 & 0xCD50010;
        if ( v24 )
        {
          v25 = v49;
          v48 = 0;
          v26 = a2 + v20;
          *(_DWORD *)(v26 + 104) |= v21 | v24;
          ReadWeakAfterTimeValue(v25, 0, (__int64)&v48);
          CopyEarlierFileTime(&v48, v26 + 120);
          v21 = v59;
        }
        else
        {
          v26 = a2 + v20;
        }
        v27 = (int *)(v26 + 104);
        if ( v22 )
        {
          v48 = 0;
          *v27 |= v21 | v22;
          v28 = v49;
          ReadWeakAfterTimeValue(v49, 1, (__int64)&v48);
          CopyEarlierFileTime(&v48, v26 + 128);
        }
        else
        {
          v28 = v49;
        }
        if ( v23 )
        {
          v49 = 0;
          v29 = 56 * (v50 + 2LL * v57);
          *v27 = v59 | *(_DWORD *)(v29 + a2 + 104) | v23;
          ReadWeakAfterTimeValue(v28, 1, (__int64)&v49);
          CopyEarlierFileTime(&v49, v29 + a2 + 136);
        }
        v3 = hKey;
      }
      ++v50;
      ++v5;
    }
    while ( v5 < 2 );
    v30 = 112 * v4;
    v31 = *(_DWORD *)(112 * v4 + a2 + 160);
    v32 = 112 * v4 + a2;
    if ( v31 )
    {
      v33 = v31 & 0xFFFFFFF3;
      if ( !*(_DWORD *)(v32 + 104) )
        v33 = *(_DWORD *)(112 * v4 + a2 + 160);
      *(_DWORD *)(v32 + 104) |= v33;
      *(_QWORD *)(v30 + a2 + 112) |= *(_QWORD *)(v30 + a2 + 168);
      CopyEarlierFileTime(v30 + a2 + 176, v30 + a2 + 120);
      CopyEarlierFileTime(v30 + a2 + 184, v30 + a2 + 128);
      CopyEarlierFileTime(v30 + a2 + 192, v30 + a2 + 136);
    }
    if ( *(_DWORD *)(v32 + 104) )
      ReadWeakSha256AllowValue(4, (unsigned int)v55, (unsigned int)off_1801574D0[v4], v30 + a2 + 144, v30 + a2 + 152);
    ++v4;
    ++v57;
  }
  while ( v57 < 2 );
  v34 = 0;
  do
  {
    v35 = 0;
    do
    {
      v36 = 0;
      if ( !(_DWORD)v34 && !(_DWORD)v35 )
        v36 = *(_DWORD *)(a2 + 60) != 0;
      v37 = ReadWeakDWORDValue(hKey);
      if ( v37 < 0 || (v3 = phkResult, v37 = ReadWeakDWORDValue(phkResult), v37 < 0) || v36 )
      {
        if ( v36 )
        {
          if ( v37 >= 0 )
          {
            v42 = 32 * (v35 + 2 * v34);
            *(_DWORD *)(v42 + a2 + 328) = 0x100000;
            *(_DWORD *)(v42 + a2 + 332) = *(_DWORD *)(a2 + 60);
            goto LABEL_70;
          }
          *(_DWORD *)(a2 + 60) = 0;
        }
        if ( (v37 & 0xCD50010) == 0 )
          goto LABEL_70;
        v38 = v37 & 0x4CD5001C;
        v39 = ReadWeakDWORDValue(v3);
        v40 = 0;
        if ( v39 != -1 )
          v40 = v39;
        if ( v40 )
          goto LABEL_68;
        if ( (v38 & 0x10) != 0 && (_DWORD)v34 == 2 )
        {
          v40 = 128;
LABEL_68:
          v41 = 32 * (v35 + 2 * v34);
          *(_DWORD *)(v41 + a2 + 332) = v40;
          *(_DWORD *)(v41 + a2 + 328) = v38;
          ReadWeakAfterTimeValue(v3, 0, v41 + a2 + 336);
        }
      }
LABEL_70:
      v3 = hKey;
      v35 = (unsigned int)(v35 + 1);
    }
    while ( (unsigned int)v35 < 2 );
    v43 = (unsigned __int64)(unsigned int)v34 << 6;
    v44 = *(_DWORD *)(v43 + a2 + 360);
    v45 = v43 + a2;
    if ( v44 )
    {
      v46 = v44 & 0xFFFFFFF3;
      if ( !*(_DWORD *)(v45 + 328) )
        v46 = *(_DWORD *)(((unsigned __int64)(unsigned int)v34 << 6) + a2 + 360);
      *(_DWORD *)(v45 + 328) |= v46;
      v47 = *(_DWORD *)(v43 + a2 + 364);
      if ( v47 > *(_DWORD *)(v43 + a2 + 332) )
        *(_DWORD *)(v43 + a2 + 332) = v47;
      CopyEarlierFileTime(v43 + a2 + 368, v43 + a2 + 336);
    }
    if ( *(_DWORD *)(v45 + 328) )
      ReadWeakSha256AllowValue(2, (unsigned int)v55, (unsigned int)off_18012D510[v34], v43 + a2 + 344, v43 + a2 + 352);
    v3 = hKey;
    v34 = (unsigned int)(v34 + 1);
  }
  while ( (unsigned int)v34 < 3 );
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v53 )
    RegCloseKey(v53);
}

```

## disassembly

```asm
0x1800a80ac  test    rcx, rcx
0x1800a80af  jz      locret_1800A885B
0x1800a80b5  mov     [rsp-8+arg_8], rbx
0x1800a80ba  mov     [rsp-8+arg_0], rcx
0x1800a80bf  push    rbp
0x1800a80c0  push    rsi
0x1800a80c1  push    rdi
0x1800a80c2  push    r12
0x1800a80c4  push    r13
0x1800a80c6  push    r14
0x1800a80c8  push    r15
0x1800a80ca  lea     rbp, [rsp-27h]
0x1800a80cf  sub     rsp, 90h
0x1800a80d6  xor     ebx, ebx
0x1800a80d8  lea     rax, [rbp+57h+var_78]
0x1800a80dc  mov     rdi, rdx
0x1800a80df  mov     [rbp+57h+var_78], rbx
0x1800a80e3  mov     esi, 20119h
0x1800a80e8  mov     [rbp+57h+hKey], rbx
0x1800a80ec  mov     r9d, esi; samDesired
0x1800a80ef  mov     [rbp+57h+var_68], rbx
0x1800a80f3  xor     r8d, r8d; ulOptions
0x1800a80f6  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800a80fb  lea     rdx, aDefault_1; "Default"
0x1800a8102  mov     r13, rcx
0x1800a8105  call    cs:__imp_RegOpenKeyExW
0x1800a810b  test    eax, eax
0x1800a810d  jz      short loc_1800A8113
0x1800a810f  mov     [rbp+57h+var_78], rbx
0x1800a8113  lea     rax, [rbp+57h+hKey]
0x1800a8117  mov     r9d, esi; samDesired
0x1800a811a  xor     r8d, r8d; ulOptions
0x1800a811d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800a8122  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\CI"...
0x1800a8129  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a8130  call    cs:__imp_RegOpenKeyExW
0x1800a8136  test    eax, eax
0x1800a8138  jz      short loc_1800A813E
0x1800a813a  mov     [rbp+57h+hKey], rbx
0x1800a813e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a8142  test    rcx, rcx
0x1800a8145  jz      short loc_1800A816B
0x1800a8147  lea     rax, [rbp+57h+var_68]
0x1800a814b  mov     r9d, esi; samDesired
0x1800a814e  xor     r8d, r8d; ulOptions
0x1800a8151  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800a8156  lea     rdx, aDefault_1; "Default"
0x1800a815d  call    cs:__imp_RegOpenKeyExW
0x1800a8163  test    eax, eax
0x1800a8165  jz      short loc_1800A816B
0x1800a8167  mov     [rbp+57h+var_68], rbx
0x1800a816b  mov     rax, [rbp+57h+var_78]
0x1800a816f  lea     r15, __ImageBase
0x1800a8176  mov     [rbp+57h+var_50], rax
0x1800a817a  xor     esi, esi
0x1800a817c  mov     rax, [rbp+57h+hKey]
0x1800a8180  mov     [rbp+57h+var_48], rax
0x1800a8184  mov     rax, [rbp+57h+var_68]
0x1800a8188  mov     [rbp+57h+var_40], rax
0x1800a818c  mov     [rbp+57h+var_58], r13
0x1800a8190  mov     [rbp+57h+arg_10], ebx
0x1800a8193  xor     r14d, r14d
0x1800a8196  mov     [rbp+57h+var_80], r14
0x1800a819a  mov     r12, [rbp+57h+hKey]
0x1800a819e  lea     r9, ValueName; "Flags"
0x1800a81a5  mov     rdx, rva off_1801574D0[r15+rsi*8]; "MD5" ...
0x1800a81ad  mov     r8d, r14d
0x1800a81b0  mov     rcx, r13; hKey
0x1800a81b3  mov     [rbp+57h+var_88], r12
0x1800a81b7  mov     [rbp+57h+var_90], r13
0x1800a81bb  xor     ebx, ebx
0x1800a81bd  call    _ReadWeakDWORDValue
0x1800a81c2  mov     r15d, eax
0x1800a81c5  lea     eax, [rbx+1]
0x1800a81c8  cmp     r14d, eax
0x1800a81cb  jnz     short loc_1800A81F0
0x1800a81cd  mov     r8d, eax
0x1800a81d0  lea     r9, ValueName; "Flags"
0x1800a81d7  lea     rax, __ImageBase
0x1800a81de  mov     rcx, r12; hKey
0x1800a81e1  mov     rdx, rva off_1801574D0[rax+rsi*8]; "MD5" ...
0x1800a81e9  call    _ReadWeakDWORDValue
0x1800a81ee  mov     ebx, eax
0x1800a81f0  test    r15d, r15d
0x1800a81f3  js      short loc_1800A8267
0x1800a81f5  test    ebx, ebx
0x1800a81f7  js      short loc_1800A8267
0x1800a81f9  mov     rax, [rbp+57h+var_78]
0x1800a81fd  lea     rdx, __ImageBase
0x1800a8204  mov     r12, [rbp+57h+var_68]
0x1800a8208  lea     r9, ValueName; "Flags"
0x1800a820f  mov     rdx, rva off_1801574D0[rdx+rsi*8]; "MD5" ...
0x1800a8217  mov     rcx, rax; hKey
0x1800a821a  mov     r8d, r14d
0x1800a821d  mov     [rbp+57h+var_90], rax
0x1800a8221  mov     [rbp+57h+var_88], r12
0x1800a8225  call    _ReadWeakDWORDValue
0x1800a822a  mov     r15d, eax
0x1800a822d  mov     eax, 1
0x1800a8232  cmp     r14d, eax
0x1800a8235  jnz     short loc_1800A825A
0x1800a8237  mov     r8d, eax
0x1800a823a  lea     r9, ValueName; "Flags"
0x1800a8241  lea     rax, __ImageBase
0x1800a8248  mov     rcx, r12; hKey
0x1800a824b  mov     rdx, rva off_1801574D0[rax+rsi*8]; "MD5" ...
0x1800a8253  call    _ReadWeakDWORDValue
0x1800a8258  mov     ebx, eax
0x1800a825a  test    r15d, r15d
0x1800a825d  js      short loc_1800A8267
0x1800a825f  test    ebx, ebx
0x1800a8261  jns     loc_1800A851F
0x1800a8267  xor     eax, eax
0x1800a8269  test    r15d, r15d
0x1800a826c  cmovs   eax, r15d
0x1800a8270  xor     r15d, r15d
0x1800a8273  test    ebx, ebx
0x1800a8275  mov     ecx, eax
0x1800a8277  mov     r12d, eax
0x1800a827a  mov     r13d, eax
0x1800a827d  cmovs   r15d, ebx
0x1800a8281  and     ecx, 4000000Ch
0x1800a8287  and     r13d, 0C000h
0x1800a828e  mov     [rbp+57h+arg_18], ecx
0x1800a8291  and     r12d, 3000h
0x1800a8298  mov     [rbp+57h+var_60], r13d
0x1800a829c  and     eax, 3FF70010h
0x1800a82a1  jz      short loc_1800A8321
0x1800a82a3  or      eax, ecx
0x1800a82a5  mov     rcx, [rbp+57h+var_80]
0x1800a82a9  lea     rbx, [rcx+rsi*2]
0x1800a82ad  imul    r13, rbx, 38h ; '8'
0x1800a82b1  mov     [rdi+r13+68h], eax
0x1800a82b6  test    eax, 33220000h
0x1800a82bb  jz      short loc_1800A82E4
0x1800a82bd  mov     rcx, [rbp+57h+var_90]; HKEY
0x1800a82c1  lea     rax, __ImageBase
0x1800a82c8  mov     rdx, rva off_1801574D0[rax+rsi*8]; "MD5" ...
0x1800a82d0  mov     r8d, r14d
0x1800a82d3  call    _ReadWeakQWORDValue
0x1800a82d8  lea     rcx, [rbx+2]
0x1800a82dc  imul    rdx, rcx, 38h ; '8'
0x1800a82e0  mov     [rdx+rdi], rax
0x1800a82e4  mov     rcx, [rbp+57h+var_90]; hKey
0x1800a82e8  lea     rax, [rdi+78h]
0x1800a82ec  add     rax, r13
0x1800a82ef  lea     r9, aAftertime; "AfterTime"
0x1800a82f6  mov     [rsp+0C0h+var_98], rax; __int64
0x1800a82fb  mov     r8d, r14d
0x1800a82fe  lea     rax, __ImageBase
0x1800a8305  mov     dword ptr [rsp+0C0h+phkResult], 0; int
0x1800a830d  mov     rdx, rva off_1801574D0[rax+rsi*8]; "MD5" ...
0x1800a8315  call    _ReadWeakAfterTimeValue
0x1800a831a  mov     ecx, [rbp+57h+arg_18]
0x1800a831d  mov     r13d, [rbp+57h+var_60]
0x1800a8321  mov     rax, [rbp+57h+var_80]
0x1800a8325  lea     rbx, [rax+rsi*2]
0x1800a8329  test    r12d, r12d
0x1800a832c  jz      short loc_1800A8375
0x1800a832e  or      r12d, ecx
0x1800a8331  lea     r9, aFilehashaftert; "FileHashAfterTime"
0x1800a8338  imul    rax, rbx, 38h ; '8'
0x1800a833c  mov     r8d, r14d
0x1800a833f  or      [rax+rdi+68h], r12d
0x1800a8344  sub     rax, 0FFFFFFFFFFFFFF80h
0x1800a8348  mov     r12, [rbp+57h+var_90]
0x1800a834c  add     rax, rdi
0x1800a834f  mov     [rsp+0C0h+var_98], rax; __int64
0x1800a8354  mov     rcx, r12; hKey
0x1800a8357  lea     rax, __ImageBase
0x1800a835e  mov     dword ptr [rsp+0C0h+phkResult], 1; int
0x1800a8366  mov     rdx, rva off_1801574D0[rax+rsi*8]; "MD5" ...
0x1800a836e  call    _ReadWeakAfterTimeValue
0x1800a8373  jmp     short loc_1800A8379
0x1800a8375  mov     r12, [rbp+57h+var_90]
0x1800a8379  imul    rbx, 38h ; '8'
0x1800a837d  test    r13d, r13d
0x1800a8380  jz      short loc_1800A83C3
0x1800a8382  or      r13d, [rbp+57h+arg_18]
0x1800a8386  lea     rax, [rdi+88h]
0x1800a838d  or      [rbx+rdi+68h], r13d
0x1800a8392  lea     r9, aTimestamphasha; "TimestampHashAfterTime"
0x1800a8399  add     rax, rbx
0x1800a839c  mov     r8d, r14d
0x1800a839f  mov     [rsp+0C0h+var_98], rax; __int64
0x1800a83a4  mov     rcx, r12; hKey
0x1800a83a7  lea     rax, __ImageBase
0x1800a83ae  mov     dword ptr [rsp+0C0h+phkResult], 1; int
0x1800a83b6  mov     rdx, rva off_1801574D0[rax+rsi*8]; "MD5" ...
0x1800a83be  call    _ReadWeakAfterTimeValue
0x1800a83c3  mov     eax, r15d
0x1800a83c6  mov     r12d, r15d
0x1800a83c9  mov     r13d, r15d
0x1800a83cc  and     eax, 4000000Ch
0x1800a83d1  and     r12d, 3000h
0x1800a83d8  mov     [rbp+57h+arg_18], eax
0x1800a83db  and     r13d, 0C000h
0x1800a83e2  and     r15d, 0CD50010h
0x1800a83e9  jz      short loc_1800A8442
0x1800a83eb  mov     rcx, [rbp+57h+var_88]; hKey
0x1800a83ef  lea     r9, aAftertime; "AfterTime"
0x1800a83f6  or      r15d, eax
0x1800a83f9  mov     [rbp+57h+var_90], 0
0x1800a8401  lea     rax, [rbp+57h+var_90]
0x1800a8405  add     rbx, rdi
0x1800a8408  mov     [rsp+0C0h+var_98], rax; __int64
0x1800a840d  mov     r8d, r14d
0x1800a8410  lea     rax, __ImageBase
0x1800a8417  mov     dword ptr [rsp+0C0h+phkResult], 0; int
0x1800a841f  or      [rbx+68h], r15d
0x1800a8423  mov     rdx, rva off_1801574D0[rax+rsi*8]; "MD5" ...
0x1800a842b  call    _ReadWeakAfterTimeValue
0x1800a8430  lea     rdx, [rbx+78h]
0x1800a8434  lea     rcx, [rbp+57h+var_90]
0x1800a8438  call    _CopyEarlierFileTime
0x1800a843d  mov     eax, [rbp+57h+arg_18]
0x1800a8440  jmp     short loc_1800A8445
0x1800a8442  add     rbx, rdi
0x1800a8445  lea     r15, [rbx+68h]
0x1800a8449  test    r12d, r12d
0x1800a844c  jz      short loc_1800A84A4
0x1800a844e  or      r12d, eax
0x1800a8451  mov     [rbp+57h+var_90], 0
0x1800a8459  or      [r15], r12d
0x1800a845c  lea     rax, [rbp+57h+var_90]
0x1800a8460  mov     r12, [rbp+57h+var_88]
0x1800a8464  lea     r9, aFilehashaftert; "FileHashAfterTime"
0x1800a846b  mov     [rsp+0C0h+var_98], rax; __int64
0x1800a8470  mov     r8d, r14d
0x1800a8473  lea     rax, __ImageBase
0x1800a847a  mov     dword ptr [rsp+0C0h+phkResult], 1; int
0x1800a8482  mov     rdx, rva off_1801574D0[rax+rsi*8]; "MD5" ...
0x1800a848a  mov     rcx, r12; hKey
0x1800a848d  call    _ReadWeakAfterTimeValue
0x1800a8492  lea     rdx, [rbx+80h]
0x1800a8499  lea     rcx, [rbp+57h+var_90]
0x1800a849d  call    _CopyEarlierFileTime
0x1800a84a2  jmp     short loc_1800A84A8
0x1800a84a4  mov     r12, [rbp+57h+var_88]
0x1800a84a8  test    r13d, r13d
0x1800a84ab  jz      short loc_1800A851B
0x1800a84ad  mov     eax, [rbp+57h+arg_10]
0x1800a84b0  lea     r9, aTimestamphasha; "TimestampHashAfterTime"
0x1800a84b7  mov     rcx, [rbp+57h+var_80]
0x1800a84bb  mov     r8d, r14d
0x1800a84be  mov     [rbp+57h+var_88], 0
0x1800a84c6  lea     rcx, [rcx+rax*2]
0x1800a84ca  imul    rbx, rcx, 38h ; '8'
0x1800a84ce  lea     rax, [rbp+57h+var_88]
0x1800a84d2  mov     rcx, r12; hKey
0x1800a84d5  mov     [rsp+0C0h+var_98], rax; __int64
0x1800a84da  mov     dword ptr [rsp+0C0h+phkResult], 1; int
0x1800a84e2  or      r13d, [rbx+rdi+68h]
0x1800a84e7  or      r13d, [rbp+57h+arg_18]
0x1800a84eb  mov     [r15], r13d
0x1800a84ee  lea     r15, __ImageBase
0x1800a84f5  mov     rdx, rva off_1801574D0[r15+rsi*8]; "MD5" ...
0x1800a84fd  call    _ReadWeakAfterTimeValue
0x1800a8502  lea     rdx, [rdi+88h]
0x1800a8509  add     rdx, rbx
0x1800a850c  lea     rcx, [rbp+57h+var_88]
0x1800a8510  call    _CopyEarlierFileTime
0x1800a8515  mov     r13, [rbp+57h+arg_0]
0x1800a8519  jmp     short loc_1800A8526
0x1800a851b  mov     r13, [rbp+57h+arg_0]
0x1800a851f  lea     r15, __ImageBase
0x1800a8526  mov     r12d, 1
0x1800a852c  add     [rbp+57h+var_80], r12
0x1800a8530  add     r14d, r12d
0x1800a8533  cmp     r14d, 2
0x1800a8537  jb      loc_1800A819A
0x1800a853d  imul    rbx, rsi, 70h ; 'p'
0x1800a8541  mov     ecx, [rbx+rdi+0A0h]
0x1800a8548  lea     r14, [rbx+rdi]
0x1800a854c  test    ecx, ecx
0x1800a854e  jz      short loc_1800A85B6
0x1800a8550  mov     eax, ecx
0x1800a8552  lea     rdx, [rdi+78h]
0x1800a8556  and     eax, 0FFFFFFF3h
0x1800a8559  cmp     dword ptr [r14+68h], 0
0x1800a855e  cmovz   eax, ecx
0x1800a8561  lea     rcx, [rdi+0B0h]
0x1800a8568  or      [r14+68h], eax
0x1800a856c  add     rdx, rbx
0x1800a856f  mov     rax, [rbx+rdi+0A8h]
0x1800a8577  add     rcx, rbx
0x1800a857a  or      [rbx+rdi+70h], rax
0x1800a857f  call    _CopyEarlierFileTime
0x1800a8584  lea     rdx, [rdi+80h]
0x1800a858b  lea     rcx, [rdi+0B8h]
0x1800a8592  add     rdx, rbx
0x1800a8595  add     rcx, rbx
0x1800a8598  call    _CopyEarlierFileTime
0x1800a859d  lea     rdx, [rdi+88h]
0x1800a85a4  lea     rcx, [rdi+0C0h]
0x1800a85ab  add     rdx, rbx
0x1800a85ae  add     rcx, rbx
0x1800a85b1  call    _CopyEarlierFileTime
0x1800a85b6  cmp     dword ptr [r14+68h], 0
0x1800a85bb  jz      short loc_1800A85EC
  ... truncated ...
```
