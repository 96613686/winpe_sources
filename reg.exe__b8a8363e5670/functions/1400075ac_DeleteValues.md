# DeleteValues

- ea: `0x1400075ac`
- end: `0x140007995`
- name: `DeleteValues`
- size: `1001`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400073d4`

## callees

- `0x140001bb2`
- `0x140002b6c`
- `0x140002ce4`
- `0x1400075ac`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000d694`
- `0x14000e560`
- `0x14000e798`
- `0x14000f294`
- `0x14000f43c`
- `0x14000f8e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140007816`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140007816`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400076ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400076ae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000771b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400078ad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000771b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400078ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400076db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007906`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400076db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007906`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007774`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007774`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007627`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007627`

## pseudocode

```c
__int64 __fastcall DeleteValues(__int64 a1)
{
  int v1; // r12d
  __int64 v3; // rcx
  unsigned int v4; // r14d
  __int64 v5; // r8
  __int64 v6; // rdx
  const WCHAR *v7; // rcx
  const WCHAR *ResString2FromModule; // rsi
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  unsigned int v12; // eax
  __int64 v13; // rcx
  FILE *v14; // rax
  const WCHAR *v15; // rdx
  WCHAR *v16; // r13
  int v17; // r15d
  DWORD i; // edi
  WCHAR *v19; // rax
  __int64 j; // rcx
  LSTATUS v21; // eax
  unsigned int v22; // edi
  unsigned int k; // r15d
  __int64 Item; // rax
  const WCHAR *v25; // rdx
  LSTATUS v26; // eax
  DWORD v27; // eax
  HKEY v28; // rcx
  __int64 v29; // rax
  _DWORD *DynamicArray; // [rsp+60h] [rbp-18h]
  LPVOID v32[2]; // [rsp+68h] [rbp-10h] BYREF
  DWORD cchValueName; // [rsp+C0h] [rbp+48h] BYREF
  DWORD cValues; // [rsp+C8h] [rbp+50h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+D0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+60h] BYREF

  v1 = 0;
  cchValueName = 0;
  hKey = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  if ( !a1 )
    goto LABEL_64;
  GetResString2FromModule(a1, 206, 1);
  v4 = 2;
  if ( *(_DWORD *)(a1 + 28) == 1 )
  {
    v5 = 0;
    v6 = 204;
    goto LABEL_8;
  }
  v7 = *(const WCHAR **)(a1 + 96);
  if ( !v7 )
  {
LABEL_64:
    v10 = 87;
    SaveErrorMessage(87);
    v11 = 2;
    goto LABEL_65;
  }
  if ( !lstrlenW(v7) )
    GetResString2FromModule(v3, 501, 0);
  v5 = 2;
  v6 = 205;
LABEL_8:
  ResString2FromModule = (const WCHAR *)GetResString2FromModule(v3, v6, v5);
  do
    v9 = Prompt(ResString2FromModule);
  while ( v9 > 2 );
  if ( v9 == 2 )
  {
    v10 = 1223;
    SaveErrorMessage(1223);
    v11 = 1;
LABEL_65:
    v14 = o___acrt_iob_func_0(v11);
    goto LABEL_66;
  }
  v12 = RegOpenKeyExW(*(HKEY *)(a1 + 8), *(LPCWSTR *)(a1 + 80), 0, *(_DWORD *)(a1 + 140) | 0xF003F, &hKey);
  v10 = v12;
  if ( v12 )
  {
    v13 = v12;
LABEL_18:
    SaveErrorMessage(v13);
    v14 = o___acrt_iob_func_0(2u);
    goto LABEL_66;
  }
  DynamicArray = (_DWORD *)CreateDynamicArray();
  if ( !DynamicArray )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v10 = 14;
    v13 = 14;
    goto LABEL_18;
  }
  v15 = *(const WCHAR **)(a1 + 96);
  if ( v15 )
  {
    v10 = RegDeleteValueW(hKey, v15);
  }
  else if ( *(_DWORD *)(a1 + 28) == 1 )
  {
    v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( !v10 )
    {
      if ( cValues )
      {
        ++cbMaxValueNameLen;
        v32[0] = AllocateMemory(2 * cbMaxValueNameLen + 4);
        v16 = (WCHAR *)v32[0];
        v10 = 14;
        if ( v32[0] )
        {
          v17 = 0;
          for ( i = 0; i < cValues; ++i )
          {
            cchValueName = cbMaxValueNameLen;
            v19 = v16;
            for ( j = 2LL * cbMaxValueNameLen; j; --j )
            {
              *(_BYTE *)v19 = 0;
              v19 = (WCHAR *)((char *)v19 + 1);
            }
            v21 = RegEnumValueW(hKey, i, v16, &cchValueName, 0, 0, 0, 0);
            v1 = v21;
            if ( v21 )
            {
              if ( !v17 )
                v17 = v21;
            }
            else if ( (unsigned int)DynArrayAppendString(DynamicArray, v16) == -1 )
            {
              v17 = 14;
              v1 = 14;
              break;
            }
          }
          FreeMemory(v32);
          if ( *DynamicArray == 9 )
            v22 = DynamicArray[1];
          else
            v22 = 0;
          if ( v1 == 14 || !v22 )
          {
            v10 = v17;
          }
          else
          {
            cchValueName = 0;
            v10 = 0;
            for ( k = 0; k < v22; ++k )
            {
              Item = _DynArrayGetItem(DynamicArray, k, 0);
              v25 = 0;
              if ( Item && *(_DWORD *)(Item + 4) == 0x20000 )
                v25 = *(const WCHAR **)(Item + 16);
              v26 = RegDeleteValueW(hKey, v25);
              if ( v26 )
              {
                if ( !v10 )
                  v10 = v26;
                v27 = cchValueName;
              }
              else
              {
                v27 = ++cchValueName;
              }
            }
            v4 = 2;
            if ( v27 )
            {
              if ( v22 == cValues && v27 == v22 )
                v10 = 0;
              else
                v10 = -2147286527;
            }
          }
        }
      }
    }
  }
  v28 = hKey;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v10 )
  {
    if ( v10 == -2147286527 )
    {
      v29 = GetResString2FromModule(v28, 141, 0);
      SetReason(v29);
    }
    else
    {
      SaveErrorMessage(v10);
    }
  }
  else
  {
    SaveErrorMessage(0);
    v4 = 1;
  }
  v14 = o___acrt_iob_func_0(v4);
LABEL_66:
  ShowLastErrorEx(v14);
  return v10;
}

```

## disassembly

```asm
0x1400075ac  push    rbp
0x1400075ae  push    rbx
0x1400075af  push    rsi
0x1400075b0  push    rdi
0x1400075b1  push    r12
0x1400075b3  push    r13
0x1400075b5  push    r14
0x1400075b7  push    r15
0x1400075b9  mov     rbp, rsp
0x1400075bc  sub     rsp, 78h
0x1400075c0  xor     r12d, r12d
0x1400075c3  mov     rdi, rcx
0x1400075c6  mov     [rbp+cchValueName], r12d
0x1400075ca  mov     [rbp+hKey], r12
0x1400075ce  mov     [rbp+cValues], r12d
0x1400075d2  mov     [rbp+cbMaxValueNameLen], r12d
0x1400075d6  test    rcx, rcx
0x1400075d9  jnz     short loc_1400075ED
0x1400075db  lea     ebx, [rcx+57h]
0x1400075de  mov     ecx, ebx
0x1400075e0  call    SaveErrorMessage
0x1400075e5  lea     ecx, [rdi+2]
0x1400075e8  jmp     loc_14000796F
0x1400075ed  mov     edx, 0CEh
0x1400075f2  mov     r8d, 1
0x1400075f8  call    GetResString2FromModule
0x1400075fd  cmp     dword ptr [rdi+1Ch], 1
0x140007601  mov     r15, rax
0x140007604  mov     r14d, 2
0x14000760a  jnz     short loc_14000761A
0x14000760c  mov     rbx, [rdi+58h]
0x140007610  xor     r8d, r8d
0x140007613  mov     edx, 0CCh
0x140007618  jmp     short loc_140007655
0x14000761a  mov     rcx, [rdi+60h]; lpString
0x14000761e  test    rcx, rcx
0x140007621  jz      loc_140007960
0x140007627  call    cs:__imp_lstrlenW
0x14000762e  nop     dword ptr [rax+rax+00h]
0x140007633  test    eax, eax
0x140007635  jnz     short loc_140007649
0x140007637  xor     r8d, r8d
0x14000763a  mov     edx, 1F5h
0x14000763f  call    GetResString2FromModule
0x140007644  mov     rbx, rax
0x140007647  jmp     short loc_14000764D
0x140007649  mov     rbx, [rdi+60h]
0x14000764d  mov     r8d, r14d
0x140007650  mov     edx, 0CDh
0x140007655  call    GetResString2FromModule
0x14000765a  mov     rsi, rax
0x14000765d  mov     r9d, [rdi+18h]
0x140007661  mov     r8, r15
0x140007664  mov     rdx, rbx
0x140007667  mov     rcx, rsi
0x14000766a  call    Prompt
0x14000766f  cmp     eax, r14d
0x140007672  jg      short loc_14000765D
0x140007674  jnz     short loc_14000768C
0x140007676  mov     ebx, 4C7h
0x14000767b  mov     ecx, ebx
0x14000767d  call    SaveErrorMessage
0x140007682  mov     ecx, 1
0x140007687  jmp     loc_14000796F
0x14000768c  mov     r9d, [rdi+8Ch]
0x140007693  lea     rax, [rbp+hKey]
0x140007697  mov     rdx, [rdi+50h]; lpSubKey
0x14000769b  or      r9d, 0F003Fh; samDesired
0x1400076a2  mov     rcx, [rdi+8]; hKey
0x1400076a6  xor     r8d, r8d; ulOptions
0x1400076a9  mov     [rsp+78h+phkResult], rax; phkResult
0x1400076ae  call    cs:__imp_RegOpenKeyExW
0x1400076b5  nop     dword ptr [rax+rax+00h]
0x1400076ba  mov     ebx, eax
0x1400076bc  test    eax, eax
0x1400076be  jz      short loc_1400076C4
0x1400076c0  mov     ecx, eax
0x1400076c2  jmp     short loc_1400076F2
0x1400076c4  call    CreateDynamicArray
0x1400076c9  mov     [rbp+var_18], rax
0x1400076cd  test    rax, rax
0x1400076d0  jnz     short loc_140007709
0x1400076d2  mov     rcx, [rbp+hKey]; hKey
0x1400076d6  test    rcx, rcx
0x1400076d9  jz      short loc_1400076EB
0x1400076db  call    cs:__imp_RegCloseKey
0x1400076e2  nop     dword ptr [rax+rax+00h]
0x1400076e7  mov     [rbp+hKey], r12
0x1400076eb  mov     ebx, 0Eh
0x1400076f0  mov     ecx, ebx
0x1400076f2  call    SaveErrorMessage
0x1400076f7  mov     ecx, r14d; Ix
0x1400076fa  call    _o___acrt_iob_func_0
0x1400076ff  mov     edx, 20001h
0x140007704  jmp     loc_140007979
0x140007709  mov     rdx, [rdi+60h]; lpValueName
0x14000770d  mov     esi, 20000h
0x140007712  test    rdx, rdx
0x140007715  jz      short loc_14000772E
0x140007717  mov     rcx, [rbp+hKey]; hKey
0x14000771b  call    cs:__imp_RegDeleteValueW
0x140007722  nop     dword ptr [rax+rax+00h]
0x140007727  mov     ebx, eax
0x140007729  jmp     loc_1400078FD
0x14000772e  cmp     dword ptr [rdi+1Ch], 1
0x140007732  jnz     loc_1400078FD
0x140007738  mov     rcx, [rbp+hKey]; hKey
0x14000773c  lea     rax, [rbp+cbMaxValueNameLen]
0x140007740  mov     [rsp+78h+lpftLastWriteTime], r12; lpftLastWriteTime
0x140007745  xor     r9d, r9d; lpReserved
0x140007748  mov     [rsp+78h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x14000774d  xor     r8d, r8d; lpcchClass
0x140007750  mov     [rsp+78h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x140007755  xor     edx, edx; lpClass
0x140007757  mov     [rsp+78h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x14000775c  lea     rax, [rbp+cValues]
0x140007760  mov     [rsp+78h+lpcValues], rax; lpcValues
0x140007765  mov     [rsp+78h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x14000776a  mov     [rsp+78h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x14000776f  mov     [rsp+78h+phkResult], r12; lpcSubKeys
0x140007774  call    cs:__imp_RegQueryInfoKeyW
0x14000777b  nop     dword ptr [rax+rax+00h]
0x140007780  mov     ebx, eax
0x140007782  test    eax, eax
0x140007784  jnz     loc_1400078FD
0x14000778a  cmp     [rbp+cValues], r12d
0x14000778e  jz      loc_1400078FD
0x140007794  mov     ecx, [rbp+cbMaxValueNameLen]
0x140007797  inc     ecx
0x140007799  mov     [rbp+cbMaxValueNameLen], ecx
0x14000779c  lea     ecx, ds:4[rcx*2]; dwBytes
0x1400077a3  call    AllocateMemory
0x1400077a8  mov     [rbp+var_10], rax
0x1400077ac  mov     r13, rax
0x1400077af  mov     ebx, 0Eh
0x1400077b4  test    rax, rax
0x1400077b7  jz      loc_1400078FD
0x1400077bd  xor     r15d, r15d
0x1400077c0  mov     edi, r12d
0x1400077c3  cmp     [rbp+cValues], r12d
0x1400077c7  jbe     short loc_140007840
0x1400077c9  mov     eax, [rbp+cbMaxValueNameLen]
0x1400077cc  mov     ecx, eax
0x1400077ce  mov     [rbp+cchValueName], eax
0x1400077d1  mov     rax, r13
0x1400077d4  add     rcx, rcx
0x1400077d7  jz      short loc_1400077E5
0x1400077d9  mov     byte ptr [rax], 0
0x1400077dc  inc     rax
0x1400077df  sub     rcx, 1
0x1400077e3  jnz     short loc_1400077D9
0x1400077e5  mov     rcx, [rbp+hKey]; hKey
0x1400077e9  lea     r9, [rbp+cchValueName]; lpcchValueName
0x1400077ed  mov     [rsp+78h+lpcValues], 0; lpcbData
0x1400077f6  mov     r8, r13; lpValueName
0x1400077f9  mov     [rsp+78h+lpcbMaxClassLen], 0; lpData
0x140007802  mov     edx, edi; dwIndex
0x140007804  mov     [rsp+78h+lpcbMaxSubKeyLen], 0; lpType
0x14000780d  mov     [rsp+78h+phkResult], 0; lpReserved
0x140007816  call    cs:__imp_RegEnumValueW
0x14000781d  nop     dword ptr [rax+rax+00h]
0x140007822  mov     r12d, eax
0x140007825  test    eax, eax
0x140007827  jnz     short loc_140007857
0x140007829  mov     rcx, [rbp+var_18]
0x14000782d  mov     rdx, r13
0x140007830  call    DynArrayAppendString
0x140007835  cmp     eax, 0FFFFFFFFh
0x140007838  jnz     short loc_14000785E
0x14000783a  mov     r15d, ebx
0x14000783d  mov     r12d, ebx
0x140007840  lea     rcx, [rbp+var_10]
0x140007844  call    FreeMemory
0x140007849  mov     rax, [rbp+var_18]
0x14000784d  cmp     dword ptr [rax], 9
0x140007850  jnz     short loc_14000786B
0x140007852  mov     edi, [rax+4]
0x140007855  jmp     short loc_14000786D
0x140007857  test    r15d, r15d
0x14000785a  cmovz   r15d, eax
0x14000785e  inc     edi
0x140007860  cmp     edi, [rbp+cValues]
0x140007863  jb      loc_1400077C9
0x140007869  jmp     short loc_140007840
0x14000786b  xor     edi, edi
0x14000786d  cmp     r12d, ebx
0x140007870  jz      loc_1400078F7
0x140007876  xor     r12d, r12d
0x140007879  test    edi, edi
0x14000787b  jz      short loc_1400078FA
0x14000787d  mov     [rbp+cchValueName], r12d
0x140007881  mov     ebx, r12d
0x140007884  mov     r15d, r12d
0x140007887  mov     r14, rax
0x14000788a  xor     r8d, r8d
0x14000788d  mov     edx, r15d
0x140007890  mov     rcx, r14
0x140007893  call    __DynArrayGetItem
0x140007898  mov     rdx, r12
0x14000789b  test    rax, rax
0x14000789e  jz      short loc_1400078A9
0x1400078a0  cmp     [rax+4], esi
0x1400078a3  jnz     short loc_1400078A9
0x1400078a5  mov     rdx, [rax+10h]; lpValueName
0x1400078a9  mov     rcx, [rbp+hKey]; hKey
0x1400078ad  call    cs:__imp_RegDeleteValueW
0x1400078b4  nop     dword ptr [rax+rax+00h]
0x1400078b9  test    eax, eax
0x1400078bb  jz      short loc_1400078C8
0x1400078bd  test    ebx, ebx
0x1400078bf  jnz     short loc_1400078C3
0x1400078c1  mov     ebx, eax
0x1400078c3  mov     eax, [rbp+cchValueName]
0x1400078c6  jmp     short loc_1400078D0
0x1400078c8  mov     eax, [rbp+cchValueName]
0x1400078cb  inc     eax
0x1400078cd  mov     [rbp+cchValueName], eax
0x1400078d0  inc     r15d
0x1400078d3  cmp     r15d, edi
0x1400078d6  jb      short loc_14000788A
0x1400078d8  mov     r14d, 2
0x1400078de  test    eax, eax
0x1400078e0  jz      short loc_1400078FD
0x1400078e2  cmp     edi, [rbp+cValues]
0x1400078e5  jnz     short loc_1400078F0
0x1400078e7  cmp     eax, edi
0x1400078e9  jnz     short loc_1400078F0
0x1400078eb  mov     ebx, r12d
0x1400078ee  jmp     short loc_1400078FD
0x1400078f0  mov     ebx, 80030201h
0x1400078f5  jmp     short loc_1400078FD
0x1400078f7  xor     r12d, r12d
0x1400078fa  mov     ebx, r15d
0x1400078fd  mov     rcx, [rbp+hKey]; hKey
0x140007901  test    rcx, rcx
0x140007904  jz      short loc_140007916
0x140007906  call    cs:__imp_RegCloseKey
0x14000790d  nop     dword ptr [rax+rax+00h]
0x140007912  mov     [rbp+hKey], r12
0x140007916  test    ebx, ebx
0x140007918  jz      short loc_140007947
0x14000791a  cmp     ebx, 80030201h
0x140007920  jnz     short loc_140007939
0x140007922  xor     r8d, r8d
0x140007925  mov     edx, 8Dh
0x14000792a  call    GetResString2FromModule
0x14000792f  mov     rcx, rax
0x140007932  call    SetReason
0x140007937  jmp     short loc_140007940
0x140007939  mov     ecx, ebx
0x14000793b  call    SaveErrorMessage
0x140007940  mov     esi, 20001h
0x140007945  jmp     short loc_140007954
0x140007947  xor     ecx, ecx
0x140007949  call    SaveErrorMessage
0x14000794e  mov     r14d, 1
0x140007954  mov     ecx, r14d; Ix
0x140007957  call    _o___acrt_iob_func_0
0x14000795c  mov     edx, esi
0x14000795e  jmp     short loc_140007979
0x140007960  mov     ebx, 57h ; 'W'
0x140007965  mov     ecx, ebx
0x140007967  call    SaveErrorMessage
0x14000796c  mov     ecx, r14d; Ix
0x14000796f  call    _o___acrt_iob_func_0
0x140007974  mov     edx, 20000h
0x140007979  mov     rcx, rax
0x14000797c  call    ShowLastErrorEx
0x140007981  mov     eax, ebx
0x140007983  add     rsp, 78h
0x140007987  pop     r15
0x140007989  pop     r14
0x14000798b  pop     r13
0x14000798d  pop     r12
0x14000798f  pop     rdi
0x140007990  pop     rsi
0x140007991  pop     rbx
0x140007992  pop     rbp
0x140007993  retn
```
