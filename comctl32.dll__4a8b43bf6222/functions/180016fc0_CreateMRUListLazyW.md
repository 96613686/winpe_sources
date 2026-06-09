# CreateMRUListLazyW

- ea: `0x180016fc0`
- end: `0x1800173ca`
- name: `CreateMRUListLazyW`
- size: `1034`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016f10`
- `0x1800173d0`

## callees

- `0x180016fc0`
- `0x1800179c0`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18001704b`
- `ADVAPI32!RegCreateKeyExW` at `0x18001704b`
- `ADVAPI32!RegQueryValueExW` at `0x18001709f`
- `ADVAPI32!RegQueryValueExW` at `0x1800171ad`
- `ADVAPI32!RegQueryValueExW` at `0x180017209`
- `ADVAPI32!RegQueryValueExW` at `0x1800172df`
- `ADVAPI32!RegQueryValueExW` at `0x18001732a`
- `ADVAPI32!RegQueryValueExW` at `0x18001709f`
- `ADVAPI32!RegQueryValueExW` at `0x1800171ad`
- `ADVAPI32!RegQueryValueExW` at `0x180017209`
- `ADVAPI32!RegQueryValueExW` at `0x1800172df`
- `ADVAPI32!RegQueryValueExW` at `0x18001732a`
- `ADVAPI32!RegCloseKey` at `0x1800173b0`
- `ADVAPI32!RegCloseKey` at `0x1800173b0`
- `KERNEL32!lstrcmpiA` at `0x18001712e`
- `KERNEL32!lstrcmpiW` at `0x180017127`
- `KERNEL32!LocalFree` at `0x1800170f4`
- `KERNEL32!LocalFree` at `0x180017358`
- `KERNEL32!LocalFree` at `0x18001739c`
- `KERNEL32!LocalFree` at `0x1800170f4`
- `KERNEL32!LocalFree` at `0x180017358`
- `KERNEL32!LocalFree` at `0x18001739c`
- `KERNEL32!LocalAlloc` at `0x18001706a`
- `KERNEL32!LocalAlloc` at `0x1800170c8`
- `KERNEL32!LocalAlloc` at `0x1800170e2`
- `KERNEL32!LocalAlloc` at `0x1800171d5`
- `KERNEL32!LocalAlloc` at `0x1800172ff`
- `KERNEL32!LocalAlloc` at `0x18001706a`
- `KERNEL32!LocalAlloc` at `0x1800170c8`
- `KERNEL32!LocalAlloc` at `0x1800170e2`
- `KERNEL32!LocalAlloc` at `0x1800171d5`
- `KERNEL32!LocalAlloc` at `0x1800172ff`
- `USER32!CharLowerW` at `0x1800170b2`
- `USER32!CharLowerW` at `0x1800170b2`

## pseudocode

```c
_DWORD *__fastcall CreateMRUListLazyW(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  const WCHAR *v4; // rdx
  _DWORD *v5; // r14
  unsigned int v8; // r12d
  HKEY v9; // rcx
  _DWORD *v10; // rbx
  int v11; // edi
  BYTE *v12; // r15
  HLOCAL v13; // rax
  void *v14; // rax
  BYTE *v15; // rsi
  WCHAR v16; // cx
  _WORD *v17; // rdi
  unsigned int v18; // eax
  BYTE *v19; // rax
  BYTE *v20; // r14
  __int16 *v21; // rsi
  __int16 v22; // ax
  _WORD *v23; // r14
  WCHAR ValueName[2]; // [rsp+50h] [rbp-28h] BYREF
  DWORD Type; // [rsp+54h] [rbp-24h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+48h] BYREF
  __int64 v29; // [rsp+C8h] [rbp+50h]
  unsigned int v30; // [rsp+D0h] [rbp+58h]
  _DWORD *v31; // [rsp+D8h] [rbp+60h]

  v31 = a4;
  v30 = a3;
  v29 = a2;
  v4 = *(const WCHAR **)(a1 + 24);
  cbData = 0;
  v5 = a4;
  dwDisposition = 0;
  Type = 0;
  hKey = 0;
  if ( !v4 )
    return 0;
  v8 = *(_DWORD *)(a1 + 4);
  v9 = *(HKEY *)(a1 + 16);
  v10 = 0;
  if ( v8 > 0x1D )
    v8 = 29;
  if ( RegCreateKeyExW(v9, v4, 0, (LPWSTR)L"Shell", 0, 0x2001Fu, 0, &hKey, &dwDisposition) )
    goto LABEL_47;
  v11 = 2 * v8 + 2;
  v12 = (BYTE *)LocalAlloc(0x40u, v11);
  if ( !v12 )
    goto LABEL_47;
  cbData = 2 * v8 + 2;
  if ( RegQueryValueExW(hKey, L"MRUList", 0, &Type, v12, &cbData) )
    *(_WORD *)v12 = 0;
  CharLowerW((LPWSTR)v12);
  v10 = LocalAlloc(0x40u, (int)(8 * v8 + 32));
  if ( !v10 )
    goto LABEL_46;
  v13 = LocalAlloc(0x40u, v11);
  *((_QWORD *)v10 + 3) = v13;
  if ( !v13 )
  {
    LocalFree(v10);
    goto LABEL_46;
  }
  *v10 = *(_DWORD *)(a1 + 8);
  v10[1] = v8;
  v14 = *(void **)(a1 + 32);
  if ( !v14 )
  {
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
    {
      v14 = mymemcmp;
    }
    else
    {
      v14 = lstrcmpiW;
      if ( (*(_BYTE *)(a1 + 8) & 4) != 0 )
        v14 = lstrcmpiA;
    }
  }
  *((_QWORD *)v10 + 1) = v14;
  v15 = v12;
  *((_QWORD *)v10 + 2) = hKey;
  ValueName[1] = 0;
  v16 = *(_WORD *)v12;
  v17 = (_WORD *)*((_QWORD *)v10 + 3);
  ValueName[0] = v16;
  if ( !v16 )
  {
LABEL_42:
    *v17 = 0;
    if ( v29 && v5 )
      goto LABEL_44;
    goto LABEL_46;
  }
  while ( 1 )
  {
    v18 = v16 - 97;
    if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
    {
      if ( v18 < v8 && !*(_QWORD *)&v10[2 * v16 - 186] )
      {
        cbData = 0;
        if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData) && Type == 1 )
        {
          cbData *= 2;
          v23 = LocalAlloc(0x40u, (int)cbData);
          if ( v23 )
          {
            if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, (LPBYTE)v23, &cbData) )
            {
              if ( *v23 )
              {
                *(_QWORD *)&v10[2 * ValueName[0] - 186] = v23;
                *v17++ = ValueName[0];
              }
              else
              {
                LocalFree(v23);
              }
            }
          }
        }
      }
      goto LABEL_40;
    }
    if ( v18 < v8 && !*(_QWORD *)&v10[2 * v16 - 186] )
    {
      cbData = 0;
      if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData) && Type == 3 )
      {
        v19 = (BYTE *)LocalAlloc(0x40u, (int)(cbData + 4));
        v20 = v19;
        if ( v19 )
        {
          *(_DWORD *)v19 = cbData;
          if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, v19 + 4, (LPDWORD)v19) )
          {
            *(_QWORD *)&v10[2 * ValueName[0] - 186] = v20;
            *v17++ = ValueName[0];
            if ( v29 )
            {
              if ( v31 && (unsigned int)MRUIsSameData(v10, v20, v29, v30) )
                break;
            }
          }
        }
      }
    }
LABEL_40:
    v15 += 2;
    v16 = *(_WORD *)v15;
    ValueName[0] = v16;
    if ( !v16 )
    {
      v5 = v31;
      goto LABEL_42;
    }
  }
  v5 = v31;
  v21 = (__int16 *)(v15 + 2);
  *v31 = ((__int64)v17 - *((_QWORD *)v10 + 3)) >> 1;
  *v10 |= 0x8000u;
  v22 = *v21;
  if ( !*v21 )
    goto LABEL_42;
  do
  {
    *v17 = v22;
    v22 = *++v21;
    ++v17;
  }
  while ( *v21 );
  *v17 = 0;
LABEL_44:
  if ( (*v10 & 0x8000) == 0 )
    *v5 = -1;
LABEL_46:
  LocalFree(v12);
  if ( !v10 )
  {
LABEL_47:
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v10;
}

```

## disassembly

```asm
0x180016fc0  mov     [rsp-40h+arg_18], r9
0x180016fc5  mov     [rsp-40h+arg_10], r8d
0x180016fca  mov     [rsp-40h+arg_8], rdx
0x180016fcf  push    rbp
0x180016fd0  push    rbx
0x180016fd1  push    rsi
0x180016fd2  push    rdi
0x180016fd3  push    r12
0x180016fd5  push    r13
0x180016fd7  push    r14
0x180016fd9  push    r15
0x180016fdb  mov     rbp, rsp
0x180016fde  sub     rsp, 78h
0x180016fe2  mov     rdx, [rcx+18h]; lpSubKey
0x180016fe6  xor     edi, edi
0x180016fe8  mov     [rbp+cbData], edi
0x180016feb  mov     r14, r9
0x180016fee  mov     [rbp+dwDisposition], edi
0x180016ff1  mov     r13, rcx
0x180016ff4  mov     [rbp+Type], edi
0x180016ff7  mov     [rbp+hKey], rdi
0x180016ffb  test    rdx, rdx
0x180016ffe  jnz     short loc_180017007
0x180017000  xor     eax, eax
0x180017002  jmp     loc_1800173B9
0x180017007  mov     r12d, [rcx+4]
0x18001700b  lea     r9, c_szShell; "Shell"
0x180017012  mov     rcx, [rcx+10h]; hKey
0x180017016  mov     eax, 1Dh
0x18001701b  cmp     r12d, eax
0x18001701e  mov     rbx, rdi
0x180017021  cmova   r12d, eax
0x180017025  lea     rax, [rbp+dwDisposition]
0x180017029  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18001702e  xor     r8d, r8d; Reserved
0x180017031  lea     rax, [rbp+hKey]
0x180017035  mov     [rsp+78h+phkResult], rax; phkResult
0x18001703a  mov     [rsp+78h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18001703f  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180017047  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18001704b  call    cs:__imp_RegCreateKeyExW
0x180017051  test    eax, eax
0x180017053  jnz     loc_1800173A7
0x180017059  lea     edi, ds:2[r12*2]
0x180017061  movsxd  rsi, edi
0x180017064  lea     ecx, [rax+40h]; uFlags
0x180017067  mov     rdx, rsi; uBytes
0x18001706a  call    cs:__imp_LocalAlloc
0x180017070  mov     r15, rax
0x180017073  test    rax, rax
0x180017076  jz      loc_1800173A7
0x18001707c  mov     rcx, [rbp+hKey]; hKey
0x180017080  lea     rax, [rbp+cbData]
0x180017084  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x180017089  lea     r9, [rbp+Type]; lpType
0x18001708d  xor     r8d, r8d; lpReserved
0x180017090  mov     qword ptr [rsp+78h+dwOptions], r15; lpData
0x180017095  lea     rdx, ValueName; "MRUList"
0x18001709c  mov     [rbp+cbData], edi
0x18001709f  call    cs:__imp_RegQueryValueExW
0x1800170a5  xor     edi, edi
0x1800170a7  test    eax, eax
0x1800170a9  jz      short loc_1800170AF
0x1800170ab  mov     [r15], di
0x1800170af  mov     rcx, r15; lpsz
0x1800170b2  call    cs:__imp_CharLowerW
0x1800170b8  lea     eax, ds:20h[r12*8]
0x1800170c0  mov     ecx, 40h ; '@'; uFlags
0x1800170c5  movsxd  rdx, eax; uBytes
0x1800170c8  call    cs:__imp_LocalAlloc
0x1800170ce  mov     rbx, rax
0x1800170d1  test    rax, rax
0x1800170d4  jz      loc_180017399
0x1800170da  mov     rdx, rsi; uBytes
0x1800170dd  mov     ecx, 40h ; '@'; uFlags
0x1800170e2  call    cs:__imp_LocalAlloc
0x1800170e8  mov     [rbx+18h], rax
0x1800170ec  test    rax, rax
0x1800170ef  jnz     short loc_1800170FF
0x1800170f1  mov     rcx, rbx; hMem
0x1800170f4  call    cs:__imp_LocalFree
0x1800170fa  jmp     loc_180017399
0x1800170ff  mov     eax, [r13+8]
0x180017103  mov     [rbx], eax
0x180017105  mov     [rbx+4], r12d
0x180017109  mov     rax, [r13+20h]
0x18001710d  test    rax, rax
0x180017110  jnz     short loc_180017136
0x180017112  test    byte ptr [r13+8], 1
0x180017117  jz      short loc_180017122
0x180017119  lea     rax, _mymemcmp
0x180017120  jmp     short loc_180017136
0x180017122  test    byte ptr [r13+8], 4
0x180017127  mov     rax, cs:__imp_lstrcmpiW
0x18001712e  cmovnz  rax, cs:__imp_lstrcmpiA
0x180017136  mov     [rbx+8], rax
0x18001713a  xor     edx, edx
0x18001713c  mov     rax, [rbp+hKey]
0x180017140  mov     rsi, r15
0x180017143  mov     [rbx+10h], rax
0x180017147  mov     [rbp+var_26], di
0x18001714b  movzx   ecx, word ptr [r15]
0x18001714f  mov     rdi, [rbx+18h]
0x180017153  mov     [rbp+ValueName], cx
0x180017157  test    cx, cx
0x18001715a  jz      loc_180017378
0x180017160  movzx   eax, cx
0x180017163  sub     eax, 61h ; 'a'
0x180017166  test    byte ptr [r13+8], 1
0x18001716b  jz      loc_1800172A3
0x180017171  cmp     eax, r12d
0x180017174  jnb     loc_180017360
0x18001717a  movzx   eax, cx
0x18001717d  xor     ecx, ecx
0x18001717f  cmp     [rbx+rax*8-2E8h], rcx
0x180017187  jnz     loc_18001735E
0x18001718d  lea     rax, [rbp+cbData]
0x180017191  mov     [rbp+cbData], ecx
0x180017194  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x180017199  lea     r9, [rbp+Type]; lpType
0x18001719d  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x1800171a2  lea     rdx, [rbp+ValueName]; lpValueName
0x1800171a6  mov     rcx, [rbp+hKey]; hKey
0x1800171aa  xor     r8d, r8d; lpReserved
0x1800171ad  call    cs:__imp_RegQueryValueExW
0x1800171b3  xor     edx, edx
0x1800171b5  test    eax, eax
0x1800171b7  jnz     loc_180017360
0x1800171bd  cmp     [rbp+Type], 3
0x1800171c1  jnz     loc_180017360
0x1800171c7  mov     eax, [rbp+cbData]
0x1800171ca  mov     ecx, 40h ; '@'; uFlags
0x1800171cf  add     eax, 4
0x1800171d2  movsxd  rdx, eax; uBytes
0x1800171d5  call    cs:__imp_LocalAlloc
0x1800171db  mov     r14, rax
0x1800171de  test    rax, rax
0x1800171e1  jz      loc_18001735E
0x1800171e7  mov     ecx, [rbp+cbData]
0x1800171ea  lea     r9, [rbp+Type]; lpType
0x1800171ee  mov     [rax], ecx
0x1800171f0  lea     rdx, [rbp+ValueName]; lpValueName
0x1800171f4  lea     rcx, [rax+4]
0x1800171f8  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x1800171fd  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x180017202  xor     r8d, r8d; lpReserved
0x180017205  mov     rcx, [rbp+hKey]; hKey
0x180017209  call    cs:__imp_RegQueryValueExW
0x18001720f  xor     ecx, ecx
0x180017211  test    eax, eax
0x180017213  jnz     loc_18001735E
0x180017219  movzx   eax, [rbp+ValueName]
0x18001721d  mov     [rbx+rax*8-2E8h], r14
0x180017225  movzx   eax, [rbp+ValueName]
0x180017229  mov     [rdi], ax
0x18001722c  add     rdi, 2
0x180017230  mov     rax, [rbp+arg_8]
0x180017234  test    rax, rax
0x180017237  jz      loc_18001735E
0x18001723d  cmp     [rbp+arg_18], rcx
0x180017241  jz      loc_18001735E
0x180017247  mov     r9d, [rbp+arg_10]
0x18001724b  mov     r8, rax
0x18001724e  mov     rdx, r14
0x180017251  mov     rcx, rbx
0x180017254  call    MRUIsSameData
0x180017259  xor     ecx, ecx
0x18001725b  test    eax, eax
0x18001725d  jz      loc_18001735E
0x180017263  mov     r14, [rbp+arg_18]
0x180017267  add     rsi, 2
0x18001726b  mov     rax, rdi
0x18001726e  sub     rax, [rbx+18h]
0x180017272  sar     rax, 1
0x180017275  mov     [r14], eax
0x180017278  bts     dword ptr [rbx], 0Fh
0x18001727c  movzx   eax, word ptr [rsi]
0x18001727f  test    ax, ax
0x180017282  jz      loc_18001737A
0x180017288  mov     [rdi], ax
0x18001728b  lea     rsi, [rsi+2]
0x18001728f  movzx   eax, word ptr [rsi]
0x180017292  lea     rdi, [rdi+2]
0x180017296  test    ax, ax
0x180017299  jnz     short loc_180017288
0x18001729b  mov     [rdi], cx
0x18001729e  jmp     loc_18001738A
0x1800172a3  cmp     eax, r12d
0x1800172a6  jnb     loc_180017360
0x1800172ac  movzx   eax, cx
0x1800172af  xor     ecx, ecx
0x1800172b1  cmp     [rbx+rax*8-2E8h], rcx
0x1800172b9  jnz     loc_18001735E
0x1800172bf  lea     rax, [rbp+cbData]
0x1800172c3  mov     [rbp+cbData], ecx
0x1800172c6  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x1800172cb  lea     r9, [rbp+Type]; lpType
0x1800172cf  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x1800172d4  lea     rdx, [rbp+ValueName]; lpValueName
0x1800172d8  mov     rcx, [rbp+hKey]; hKey
0x1800172dc  xor     r8d, r8d; lpReserved
0x1800172df  call    cs:__imp_RegQueryValueExW
0x1800172e5  test    eax, eax
0x1800172e7  jnz     short loc_18001735E
0x1800172e9  cmp     [rbp+Type], 1
0x1800172ed  jnz     short loc_18001735E
0x1800172ef  mov     eax, [rbp+cbData]
0x1800172f2  mov     ecx, 40h ; '@'; uFlags
0x1800172f7  add     eax, eax
0x1800172f9  movsxd  rdx, eax; uBytes
0x1800172fc  mov     [rbp+cbData], eax
0x1800172ff  call    cs:__imp_LocalAlloc
0x180017305  mov     r14, rax
0x180017308  test    rax, rax
0x18001730b  jz      short loc_18001735E
0x18001730d  mov     rcx, [rbp+hKey]; hKey
0x180017311  lea     rax, [rbp+cbData]
0x180017315  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x18001731a  lea     r9, [rbp+Type]; lpType
0x18001731e  xor     r8d, r8d; lpReserved
0x180017321  mov     qword ptr [rsp+78h+dwOptions], r14; lpData
0x180017326  lea     rdx, [rbp+ValueName]; lpValueName
0x18001732a  call    cs:__imp_RegQueryValueExW
0x180017330  xor     ecx, ecx
0x180017332  test    eax, eax
0x180017334  jnz     short loc_18001735E
0x180017336  cmp     [r14], cx
0x18001733a  jz      short loc_180017355
0x18001733c  movzx   eax, [rbp+ValueName]
0x180017340  mov     [rbx+rax*8-2E8h], r14
0x180017348  movzx   eax, [rbp+ValueName]
0x18001734c  mov     [rdi], ax
0x18001734f  add     rdi, 2
0x180017353  jmp     short loc_18001735E
0x180017355  mov     rcx, r14; hMem
0x180017358  call    cs:__imp_LocalFree
0x18001735e  xor     edx, edx
0x180017360  add     rsi, 2
0x180017364  movzx   ecx, word ptr [rsi]
0x180017367  mov     [rbp+ValueName], cx
0x18001736b  test    cx, cx
0x18001736e  jnz     loc_180017160
0x180017374  mov     r14, [rbp+arg_18]
0x180017378  xor     ecx, ecx
0x18001737a  mov     [rdi], cx
0x18001737d  xor     edi, edi
0x18001737f  cmp     [rbp+arg_8], rdi
0x180017383  jz      short loc_180017399
0x180017385  test    r14, r14
0x180017388  jz      short loc_180017399
0x18001738a  test    dword ptr [rbx], 8000h
0x180017390  jnz     short loc_180017399
0x180017392  mov     dword ptr [r14], 0FFFFFFFFh
0x180017399  mov     rcx, r15; hMem
0x18001739c  call    cs:__imp_LocalFree
0x1800173a2  test    rbx, rbx
0x1800173a5  jnz     short loc_1800173B6
0x1800173a7  mov     rcx, [rbp+hKey]; hKey
0x1800173ab  test    rcx, rcx
0x1800173ae  jz      short loc_1800173B6
0x1800173b0  call    cs:__imp_RegCloseKey
0x1800173b6  mov     rax, rbx
0x1800173b9  add     rsp, 78h
0x1800173bd  pop     r15
0x1800173bf  pop     r14
0x1800173c1  pop     r13
0x1800173c3  pop     r12
0x1800173c5  pop     rdi
0x1800173c6  pop     rsi
0x1800173c7  pop     rbx
0x1800173c8  pop     rbp
0x1800173c9  retn
```
