# SaveRestoreFromReg

- ea: `0x18004bd74`
- end: `0x18004c37f`
- name: `SaveRestoreFromReg`
- size: `1547`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18002aab0`

## callees

- `0x1800115f0`
- `0x18002405c`
- `0x180026364`
- `0x1800273f0`
- `0x18002851c`
- `0x18002878c`
- `0x180035fe0`
- `0x18004a6e4`
- `0x18004bd74`
- `0x18008ea60`

## import_xrefs

- `ADVAPI32!RegCreateKeyW` at `0x18004be5e`
- `ADVAPI32!RegCreateKeyW` at `0x18004be5e`
- `ADVAPI32!RegOpenKeyExW` at `0x18004bf48`
- `ADVAPI32!RegOpenKeyExW` at `0x18004bf48`
- `ADVAPI32!RegQueryValueExW` at `0x18004bf78`
- `ADVAPI32!RegQueryValueExW` at `0x18004bfd7`
- `ADVAPI32!RegQueryValueExW` at `0x18004bf78`
- `ADVAPI32!RegQueryValueExW` at `0x18004bfd7`
- `ADVAPI32!RegCloseKey` at `0x18004bf0b`
- `ADVAPI32!RegCloseKey` at `0x18004c34d`
- `ADVAPI32!RegCloseKey` at `0x18004bf0b`
- `ADVAPI32!RegCloseKey` at `0x18004c34d`
- `ADVAPI32!RegSetValueExW` at `0x18004befa`
- `ADVAPI32!RegSetValueExW` at `0x18004befa`
- `KERNEL32!LocalFree` at `0x18004bf1f`
- `KERNEL32!LocalFree` at `0x18004c342`
- `KERNEL32!LocalFree` at `0x18004bf1f`
- `KERNEL32!LocalFree` at `0x18004c342`
- `KERNEL32!LocalAlloc` at `0x18004be20`
- `KERNEL32!LocalAlloc` at `0x18004bf9d`
- `KERNEL32!LocalAlloc` at `0x18004be20`
- `KERNEL32!LocalAlloc` at `0x18004bf9d`
- `USER32!SendMessageW` at `0x18004c0a6`
- `USER32!SendMessageW` at `0x18004c2e3`
- `USER32!SendMessageW` at `0x18004c30d`
- `USER32!SendMessageW` at `0x18004c0a6`
- `USER32!SendMessageW` at `0x18004c2e3`
- `USER32!SendMessageW` at `0x18004c30d`
- `USER32!InvalidateRect` at `0x18004c31c`
- `USER32!InvalidateRect` at `0x18004c31c`

## pseudocode

```c
__int64 __fastcall SaveRestoreFromReg(__int64 a1, int a2, HKEY a3, const WCHAR *a4, const WCHAR *lpValueName)
{
  unsigned int v8; // esi
  int v9; // ecx
  int v10; // r15d
  HLOCAL v11; // rcx
  HLOCAL v12; // rax
  int i; // edi
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // rax
  unsigned __int64 v17; // rdi
  HLOCAL v18; // r13
  int v19; // edi
  __int64 v20; // rax
  HWND v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  HLOCAL v26; // rdx
  __int64 v27; // rax
  unsigned int v28; // edi
  __int64 j; // rdx
  int v30; // eax
  __int128 v31; // xmm1
  __int64 v32; // rcx
  __int64 v33; // rax
  LPARAM v34; // xmm0_8
  int v35; // edi
  __int64 v36; // rsi
  __int64 v37; // rcx
  unsigned __int64 v38; // rdx
  LPARAM v39; // rax
  HWND v40; // rcx
  DWORD v42; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type[4]; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL lpData[12]; // [rsp+50h] [rbp-B0h] BYREF
  LPARAM lParam[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v47[256]; // [rsp+F0h] [rbp-10h] BYREF

  v8 = 0;
  if ( a2 )
  {
    memset(lpData, 0, 0x58u);
    v9 = *(_DWORD *)(a1 + 200);
    lpData[4] = 0;
    v10 = 0;
    LODWORD(lpData[6]) = v9;
    HIDWORD(lpData[5]) = -1;
    LODWORD(lpData[5]) = 4 * v9;
    CCSendNotify(a1, 4294966574LL, lpData);
    v11 = lpData[3];
    if ( !lpData[3] )
    {
      v11 = LocalAlloc(0x40u, LODWORD(lpData[5]));
      lpData[3] = v11;
      v10 = 1;
    }
    v12 = lpData[4];
    if ( !lpData[4] )
      v12 = v11;
    lpData[4] = v12;
    if ( v11 )
    {
      phkResult = 0;
      if ( !RegCreateKeyW(a3, a4, &phkResult) )
      {
        for ( i = 0; i < *(_DWORD *)(a1 + 200); ++i )
        {
          v14 = *(_QWORD *)(a1 + 80);
          v15 = *(_DWORD *)(v14 + 40LL * i + 4);
          if ( !v15 )
            v15 = ((unsigned __int8)~*(_BYTE *)(v14 + 40LL * i + 8) >> 3) | 0xFFFFFFFE;
          *(_DWORD *)lpData[4] = v15;
          v16 = *(_QWORD *)(a1 + 80);
          lpData[4] = (char *)lpData[4] + 4;
          HIDWORD(lpData[5]) = i;
          TBOutputStruct(a1, v16 + 40LL * i, &lpData[7]);
          CCSendNotify(a1, 4294966574LL, lpData);
        }
        LOBYTE(v8) = RegSetValueExW(phkResult, lpValueName, 0, 3u, (const BYTE *)lpData[3], (DWORD)lpData[5]) == 0;
        RegCloseKey(phkResult);
      }
      if ( v10 )
        LocalFree(lpData[3]);
    }
  }
  else
  {
    phkResult = 0;
    if ( !RegOpenKeyExW(a3, a4, 0, 0x20019u, &phkResult) )
    {
      v42 = 0;
      if ( !RegQueryValueExW(phkResult, lpValueName, 0, 0, 0, &v42) )
      {
        v17 = (int)v42;
        if ( v42 > 4 )
        {
          v18 = LocalAlloc(0x40u, v42);
          if ( v18 )
          {
            Type[0] = 0;
            v42 = v17;
            if ( !RegQueryValueExW(phkResult, lpValueName, 0, Type, (LPBYTE)v18, &v42)
              && Type[0] == 3
              && v42 == (_DWORD)v17 )
            {
              memset(lpData, 0, 0x58u);
              lpData[3] = v18;
              LODWORD(lpData[6]) = v17 >> 2;
              lpData[4] = v18;
              HIDWORD(lpData[6]) = 4;
              lpData[5] = (HLOCAL)(v17 | 0xFFFFFFFF00000000uLL);
              if ( !CCSendNotify(a1, 4294966575LL, lpData) )
              {
                if ( *(_QWORD *)(a1 + 104) )
                {
                  memset(lParam, 0, sizeof(lParam));
                  v19 = 0;
                  lParam[1] = *(_QWORD *)a1;
                  for ( LODWORD(lParam[0]) = 64; v19 < *(_DWORD *)(a1 + 200); ++v19 )
                  {
                    v20 = *(_QWORD *)(a1 + 80);
                    if ( (*(_BYTE *)(v20 + 40LL * v19 + 9) & 1) == 0 )
                    {
                      v21 = *(HWND *)(a1 + 104);
                      lParam[2] = *(int *)(v20 + 40LL * v19 + 4);
                      SendMessageW(v21, 0x433u, 0, (LPARAM)lParam);
                    }
                  }
                }
                if ( (unsigned int)TBReallocButtons(a1, LODWORD(lpData[6])) )
                {
                  v22 = *(int *)(a1 + 200);
                  v23 = (int)lpData[6];
                  if ( (int)v22 < SLODWORD(lpData[6]) )
                  {
                    memset((void *)(*(_QWORD *)(a1 + 80) + 40 * v22), 0, 32LL * (LODWORD(lpData[6]) - (int)v22));
                    v23 = (int)lpData[6];
                  }
                  *(_DWORD *)(a1 + 200) = v23;
                  if ( v23 > 0 )
                  {
                    do
                    {
                      v24 = *(_QWORD *)(a1 + 80);
                      HIDWORD(lpData[5]) = v8;
                      if ( *(int *)lpData[4] >= 0 )
                      {
                        *(_BYTE *)(v24 + 40LL * (int)v8 + 9) = 0;
                        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 40LL * (int)v8 + 4) = *(_DWORD *)lpData[4];
                        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 40LL * (int)v8) = -1;
                      }
                      else
                      {
                        *(_BYTE *)(v24 + 40LL * (int)v8 + 9) = 1;
                        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 40LL * (int)v8) = 8;
                        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 40LL * (int)v8 + 4) = 0;
                        *(_BYTE *)(*(_QWORD *)(a1 + 80) + 40LL * (int)v8 + 8) = *(_DWORD *)lpData[4] != -1 ? 8 : 0;
                      }
                      v25 = *(_QWORD *)(a1 + 80);
                      lpData[4] = (char *)lpData[4] + 4;
                      TBOutputStruct(a1, v25 + 40LL * (int)v8, &lpData[7]);
                      CCSendNotify(a1, 4294966575LL, lpData);
                      v26 = lpData[10];
                      v27 = *(_QWORD *)(a1 + 80);
                      if ( WORD1(lpData[10]) )
                        v26 = 0;
                      lpData[10] = v26;
                      TBInputStruct(a1, v27 + 40LL * (int)v8++, &lpData[7]);
                    }
                    while ( (signed int)v8 < *(_DWORD *)(a1 + 200) );
                  }
                  if ( !CCSendNotify(a1, 4294966593LL, 0) || *(__int64 *)(a1 + 40) < 5 )
                  {
                    v28 = 0;
                    for ( j = 0; ; j = v28 )
                    {
                      memset(lParam, 0, 40);
                      if ( !(unsigned int)GetAdjustInfo(a1, j, lParam, v47) )
                        break;
                      if ( (lParam[1] & 0x100) == 0 || HIDWORD(lParam[0]) )
                      {
                        v30 = PositionFromID(a1, SHIDWORD(lParam[0]));
                        if ( v30 >= 0 )
                        {
                          v31 = *(_OWORD *)&lParam[2];
                          v32 = 5LL * v30;
                          v33 = *(_QWORD *)(a1 + 80);
                          *(_OWORD *)(v33 + 8 * v32) = *(_OWORD *)lParam;
                          v34 = lParam[4];
                          *(_OWORD *)(v33 + 8 * v32 + 16) = v31;
                          *(_QWORD *)(v33 + 8 * v32 + 32) = v34;
                        }
                      }
                      ++v28;
                    }
                    CCSendNotify(a1, 4294966592LL, 0);
                  }
                  v35 = *(_DWORD *)(a1 + 200) - 1;
                  if ( v35 >= 0 )
                  {
                    v36 = v35;
                    do
                    {
                      v37 = *(_QWORD *)(a1 + 80);
                      if ( *(int *)(v37 + 40 * v36) >= 0 )
                      {
                        if ( *(_QWORD *)(a1 + 104) )
                        {
                          if ( (*(_BYTE *)(v37 + 40 * v36 + 9) & 1) == 0 )
                          {
                            v38 = *(int *)(v37 + 40 * v36 + 4);
                            if ( (_DWORD)v38 )
                            {
                              v39 = *(_QWORD *)a1;
                              v40 = *(HWND *)(a1 + 104);
                              *(_OWORD *)&lParam[2] = v38;
                              *(_OWORD *)&lParam[4] = 0;
                              lParam[1] = v39;
                              lParam[7] = 0;
                              lParam[0] = 64;
                              lParam[6] = -1;
                              SendMessageW(v40, 0x432u, 0, (LPARAM)lParam);
                            }
                          }
                        }
                      }
                      else
                      {
                        DeleteButton(a1, (unsigned int)v35);
                      }
                      --v36;
                      --v35;
                    }
                    while ( v35 >= 0 );
                  }
                  v8 = *(_DWORD *)(a1 + 200) != 0;
                  SendMessageW(*(HWND *)a1, 0x421u, 0, 0);
                  InvalidateRect(*(HWND *)a1, 0, 1);
                  *(_DWORD *)(a1 + 316) &= ~0x10000u;
                  *(_DWORD *)(a1 + 316) |= 0x10u;
                  *(_DWORD *)(a1 + 232) = -1;
                  *(_DWORD *)(a1 + 236) = -1;
                }
              }
            }
            LocalFree(v18);
          }
        }
      }
      RegCloseKey(phkResult);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18004bd74  mov     [rsp-8+arg_8], rbx
0x18004bd79  push    rbp
0x18004bd7a  push    rsi
0x18004bd7b  push    rdi
0x18004bd7c  push    r12
0x18004bd7e  push    r13
0x18004bd80  push    r14
0x18004bd82  push    r15
0x18004bd84  lea     rbp, [rsp-100h]
0x18004bd8c  sub     rsp, 200h
0x18004bd93  mov     rax, cs:__security_cookie
0x18004bd9a  xor     rax, rsp
0x18004bd9d  mov     [rbp+130h+var_40], rax
0x18004bda4  mov     r12, [rbp+130h+lpValueName]
0x18004bdab  xor     r14d, r14d
0x18004bdae  mov     r13, r9
0x18004bdb1  mov     rdi, r8
0x18004bdb4  mov     rbx, rcx
0x18004bdb7  mov     esi, r14d
0x18004bdba  test    edx, edx
0x18004bdbc  jz      loc_18004BF2A
0x18004bdc2  xor     edx, edx; Val
0x18004bdc4  lea     r8d, [r14+58h]; Size
0x18004bdc8  lea     rcx, [rsp+230h+var_1E0]; void *
0x18004bdcd  call    memset
0x18004bdd2  mov     ecx, [rbx+0C8h]
0x18004bdd8  lea     r8, [rsp+230h+var_1E0]
0x18004bddd  mov     [rsp+230h+var_1C0], r14
0x18004bde2  mov     r15d, r14d
0x18004bde5  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004bde9  mov     [rbp+130h+var_1B0], ecx
0x18004bdec  mov     dword ptr [rsp+230h+uBytes+4], r14d
0x18004bdf1  mov     r14d, 0FFFFFD2Eh
0x18004bdf7  lea     eax, ds:0[rcx*4]
0x18004bdfe  mov     edx, r14d
0x18004be01  mov     rcx, rbx
0x18004be04  mov     dword ptr [rsp+230h+uBytes], eax
0x18004be08  call    CCSendNotify
0x18004be0d  mov     rcx, [rsp+230h+hMem]
0x18004be12  test    rcx, rcx
0x18004be15  jnz     short loc_18004BE34
0x18004be17  mov     edx, dword ptr [rsp+230h+uBytes]; uBytes
0x18004be1b  mov     ecx, 40h ; '@'; uFlags
0x18004be20  call    cs:__imp_LocalAlloc
0x18004be26  mov     rcx, rax
0x18004be29  mov     [rsp+230h+hMem], rax
0x18004be2e  mov     r15d, 1
0x18004be34  mov     rax, [rsp+230h+var_1C0]
0x18004be39  test    rax, rax
0x18004be3c  cmovz   rax, rcx
0x18004be40  mov     [rsp+230h+var_1C0], rax
0x18004be45  test    rcx, rcx
0x18004be48  jz      loc_18004C353
0x18004be4e  lea     r8, [rsp+230h+phkResult]; phkResult
0x18004be53  mov     [rsp+230h+phkResult], rsi
0x18004be58  mov     rdx, r13; lpSubKey
0x18004be5b  mov     rcx, rdi; hKey
0x18004be5e  call    cs:__imp_RegCreateKeyW
0x18004be64  test    eax, eax
0x18004be66  jnz     loc_18004BF11
0x18004be6c  xor     edi, edi
0x18004be6e  cmp     [rbx+0C8h], esi
0x18004be74  jle     short loc_18004BED7
0x18004be76  movsxd  rax, edi
0x18004be79  lea     rdx, [rax+rax*4]
0x18004be7d  mov     rax, [rbx+50h]
0x18004be81  mov     ecx, [rax+rdx*8+4]
0x18004be85  test    ecx, ecx
0x18004be87  jnz     short loc_18004BE98
0x18004be89  mov     al, [rax+rdx*8+8]
0x18004be8d  not     al
0x18004be8f  movzx   ecx, al
0x18004be92  shr     ecx, 3
0x18004be95  or      ecx, 0FFFFFFFEh
0x18004be98  mov     rax, [rsp+230h+var_1C0]
0x18004be9d  lea     r8, [rbp+130h+var_1A8]
0x18004bea1  mov     [rax], ecx
0x18004bea3  mov     rcx, rbx
0x18004bea6  mov     rax, [rbx+50h]
0x18004beaa  add     [rsp+230h+var_1C0], 4
0x18004beb0  mov     dword ptr [rsp+230h+uBytes+4], edi
0x18004beb4  lea     rdx, [rax+rdx*8]
0x18004beb8  call    TBOutputStruct
0x18004bebd  lea     r8, [rsp+230h+var_1E0]
0x18004bec2  mov     edx, r14d
0x18004bec5  mov     rcx, rbx
0x18004bec8  call    CCSendNotify
0x18004becd  inc     edi
0x18004becf  cmp     edi, [rbx+0C8h]
0x18004bed5  jl      short loc_18004BE76
0x18004bed7  mov     eax, dword ptr [rsp+230h+uBytes]
0x18004bedb  mov     r9d, 3; dwType
0x18004bee1  mov     rcx, [rsp+230h+phkResult]; hKey
0x18004bee6  xor     r8d, r8d; Reserved
0x18004bee9  mov     [rsp+230h+cbData], eax; cbData
0x18004beed  mov     rdx, r12; lpValueName
0x18004bef0  mov     rax, [rsp+230h+hMem]
0x18004bef5  mov     [rsp+230h+lpData], rax; lpData
0x18004befa  call    cs:__imp_RegSetValueExW
0x18004bf00  mov     rcx, [rsp+230h+phkResult]; hKey
0x18004bf05  test    eax, eax
0x18004bf07  setz    sil
0x18004bf0b  call    cs:__imp_RegCloseKey
0x18004bf11  test    r15d, r15d
0x18004bf14  jz      loc_18004C353
0x18004bf1a  mov     rcx, [rsp+230h+hMem]; hMem
0x18004bf1f  call    cs:__imp_LocalFree
0x18004bf25  jmp     loc_18004C353
0x18004bf2a  lea     rax, [rsp+230h+phkResult]
0x18004bf2f  mov     [rsp+230h+phkResult], r14
0x18004bf34  mov     r9d, 20019h; samDesired
0x18004bf3a  mov     [rsp+230h+lpData], rax; phkResult
0x18004bf3f  xor     r8d, r8d; ulOptions
0x18004bf42  mov     rdx, r13; lpSubKey
0x18004bf45  mov     rcx, rdi; hKey
0x18004bf48  call    cs:__imp_RegOpenKeyExW
0x18004bf4e  test    eax, eax
0x18004bf50  jnz     loc_18004C353
0x18004bf56  mov     rcx, [rsp+230h+phkResult]; hKey
0x18004bf5b  lea     rax, [rsp+230h+var_200]
0x18004bf60  mov     qword ptr [rsp+230h+cbData], rax; lpcbData
0x18004bf65  xor     r9d, r9d; lpType
0x18004bf68  xor     r8d, r8d; lpReserved
0x18004bf6b  mov     [rsp+230h+lpData], r14; lpData
0x18004bf70  mov     rdx, r12; lpValueName
0x18004bf73  mov     [rsp+230h+var_200], r14d
0x18004bf78  call    cs:__imp_RegQueryValueExW
0x18004bf7e  test    eax, eax
0x18004bf80  jnz     loc_18004C348
0x18004bf86  movsxd  rdi, [rsp+230h+var_200]
0x18004bf8b  cmp     edi, 4
0x18004bf8e  jbe     loc_18004C348
0x18004bf94  lea     r15d, [rax+40h]
0x18004bf98  mov     edx, edi; uBytes
0x18004bf9a  mov     ecx, r15d; uFlags
0x18004bf9d  call    cs:__imp_LocalAlloc
0x18004bfa3  mov     r13, rax
0x18004bfa6  test    rax, rax
0x18004bfa9  jz      loc_18004C348
0x18004bfaf  mov     rcx, [rsp+230h+phkResult]; hKey
0x18004bfb4  lea     rax, [rsp+230h+var_200]
0x18004bfb9  mov     qword ptr [rsp+230h+cbData], rax; lpcbData
0x18004bfbe  lea     r9, [rsp+230h+Type]; lpType
0x18004bfc3  xor     r8d, r8d; lpReserved
0x18004bfc6  mov     [rsp+230h+lpData], r13; lpData
0x18004bfcb  mov     rdx, r12; lpValueName
0x18004bfce  mov     [rsp+230h+Type], r14d
0x18004bfd3  mov     [rsp+230h+var_200], edi
0x18004bfd7  call    cs:__imp_RegQueryValueExW
0x18004bfdd  xor     r12d, r12d
0x18004bfe0  test    eax, eax
0x18004bfe2  jnz     loc_18004C33F
0x18004bfe8  cmp     [rsp+230h+Type], 3
0x18004bfed  jnz     loc_18004C33F
0x18004bff3  cmp     [rsp+230h+var_200], edi
0x18004bff7  jnz     loc_18004C33F
0x18004bffd  xor     edx, edx; Val
0x18004bfff  lea     r8d, [r15+18h]; Size
0x18004c003  lea     rcx, [rsp+230h+var_1E0]; void *
0x18004c008  call    memset
0x18004c00d  mov     rax, rdi
0x18004c010  mov     [rsp+230h+hMem], r13
0x18004c015  shr     rax, 2
0x18004c019  lea     r8, [rsp+230h+var_1E0]
0x18004c01e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004c022  mov     [rbp+130h+var_1B0], eax
0x18004c025  mov     edx, 0FFFFFD2Fh
0x18004c02a  mov     [rsp+230h+var_1C0], r13
0x18004c02f  mov     rcx, rbx
0x18004c032  mov     dword ptr [rsp+230h+uBytes+4], r14d
0x18004c037  mov     [rbp+130h+var_1AC], 4
0x18004c03e  mov     dword ptr [rsp+230h+uBytes], edi
0x18004c042  call    CCSendNotify
0x18004c047  test    rax, rax
0x18004c04a  jnz     loc_18004C33F
0x18004c050  cmp     [rbx+68h], r12
0x18004c054  jz      short loc_18004C0B6
0x18004c056  mov     r8d, r15d; Size
0x18004c059  lea     rcx, [rbp+130h+lParam]; void *
0x18004c05d  xor     edx, edx; Val
0x18004c05f  call    memset
0x18004c064  mov     edi, r12d
0x18004c067  mov     rax, [rbx]
0x18004c06a  mov     [rbp+130h+lParam+8], rax
0x18004c06e  mov     dword ptr [rbp+130h+lParam], r15d
0x18004c072  cmp     [rbx+0C8h], r12d
0x18004c079  jle     short loc_18004C0B6
0x18004c07b  movsxd  rax, edi
0x18004c07e  lea     rcx, [rax+rax*4]
0x18004c082  mov     rax, [rbx+50h]
0x18004c086  test    byte ptr [rax+rcx*8+9], 1
0x18004c08b  jnz     short loc_18004C0AC
0x18004c08d  movsxd  rax, dword ptr [rax+rcx*8+4]
0x18004c092  lea     r9, [rbp+130h+lParam]; lParam
0x18004c096  mov     rcx, [rbx+68h]; hWnd
0x18004c09a  xor     r8d, r8d; wParam
0x18004c09d  mov     edx, 433h; Msg
0x18004c0a2  mov     qword ptr [rbp+130h+var_170], rax
0x18004c0a6  call    cs:__imp_SendMessageW
0x18004c0ac  inc     edi
0x18004c0ae  cmp     edi, [rbx+0C8h]
0x18004c0b4  jl      short loc_18004C07B
0x18004c0b6  mov     edx, [rbp+130h+var_1B0]
0x18004c0b9  mov     rcx, rbx
0x18004c0bc  call    TBReallocButtons
0x18004c0c1  test    eax, eax
0x18004c0c3  jz      loc_18004C33F
0x18004c0c9  movsxd  rcx, dword ptr [rbx+0C8h]
0x18004c0d0  mov     eax, [rbp+130h+var_1B0]
0x18004c0d3  cmp     ecx, eax
0x18004c0d5  jge     short loc_18004C0F6
0x18004c0d7  sub     eax, ecx
0x18004c0d9  xor     edx, edx; Val
0x18004c0db  movsxd  r8, eax
0x18004c0de  lea     rcx, [rcx+rcx*4]
0x18004c0e2  mov     rax, [rbx+50h]
0x18004c0e6  shl     r8, 5; Size
0x18004c0ea  lea     rcx, [rax+rcx*8]; void *
0x18004c0ee  call    memset
0x18004c0f3  mov     eax, [rbp+130h+var_1B0]
0x18004c0f6  mov     [rbx+0C8h], eax
0x18004c0fc  test    eax, eax
0x18004c0fe  jle     loc_18004C1CF
0x18004c104  mov     rcx, [rbx+50h]
0x18004c108  movsxd  rax, esi
0x18004c10b  mov     dword ptr [rsp+230h+uBytes+4], esi
0x18004c10f  lea     rdi, [rax+rax*4]
0x18004c113  mov     rax, [rsp+230h+var_1C0]
0x18004c118  cmp     [rax], r12d
0x18004c11b  jge     short loc_18004C14F
0x18004c11d  mov     byte ptr [rcx+rdi*8+9], 1
0x18004c122  mov     rax, [rbx+50h]
0x18004c126  mov     dword ptr [rax+rdi*8], 8
0x18004c12d  mov     rax, [rbx+50h]
0x18004c131  mov     [rax+rdi*8+4], r12d
0x18004c136  mov     rax, [rsp+230h+var_1C0]
0x18004c13b  mov     rdx, [rbx+50h]
0x18004c13f  mov     ecx, [rax]
0x18004c141  inc     ecx
0x18004c143  neg     ecx
0x18004c145  sbb     al, al
0x18004c147  and     al, 8
0x18004c149  mov     [rdx+rdi*8+8], al
0x18004c14d  jmp     short loc_18004C16B
0x18004c14f  mov     [rcx+rdi*8+9], r12b
0x18004c154  mov     rax, [rsp+230h+var_1C0]
0x18004c159  mov     rdx, [rbx+50h]
0x18004c15d  mov     ecx, [rax]
0x18004c15f  mov     [rdx+rdi*8+4], ecx
0x18004c163  mov     rax, [rbx+50h]
0x18004c167  mov     [rax+rdi*8], r14d
0x18004c16b  mov     rax, [rbx+50h]
0x18004c16f  lea     r8, [rbp+130h+var_1A8]
0x18004c173  add     [rsp+230h+var_1C0], 4
0x18004c179  mov     rcx, rbx
0x18004c17c  lea     rdx, [rax+rdi*8]
0x18004c180  call    TBOutputStruct
0x18004c185  lea     r8, [rsp+230h+var_1E0]
0x18004c18a  mov     edx, 0FFFFFD2Fh
0x18004c18f  mov     rcx, rbx
0x18004c192  call    CCSendNotify
0x18004c197  mov     rdx, [rbp+130h+var_190]
0x18004c19b  lea     r8, [rbp+130h+var_1A8]
0x18004c19f  mov     rax, [rbx+50h]
0x18004c1a3  mov     rcx, rdx
0x18004c1a6  shr     rcx, 10h
0x18004c1aa  test    cx, cx
0x18004c1ad  mov     rcx, rbx
0x18004c1b0  cmovnz  rdx, r12
0x18004c1b4  mov     [rbp+130h+var_190], rdx
0x18004c1b8  lea     rdx, [rax+rdi*8]
0x18004c1bc  call    TBInputStruct
0x18004c1c1  inc     esi
0x18004c1c3  cmp     esi, [rbx+0C8h]
0x18004c1c9  jl      loc_18004C104
0x18004c1cf  xor     r8d, r8d
0x18004c1d2  mov     edx, 0FFFFFD41h
0x18004c1d7  mov     rcx, rbx
0x18004c1da  call    CCSendNotify
0x18004c1df  test    rax, rax
0x18004c1e2  jz      short loc_18004C1EF
0x18004c1e4  cmp     qword ptr [rbx+28h], 5
0x18004c1e9  jge     loc_18004C272
0x18004c1ef  mov     edi, r12d
0x18004c1f2  xor     edx, edx
0x18004c1f4  jmp     short loc_18004C23D
0x18004c1f6  test    byte ptr [rbp+130h+lParam+9], 1
0x18004c1fa  movsxd  rax, dword ptr [rbp+130h+lParam+4]
0x18004c1fe  jz      short loc_18004C204
0x18004c200  test    eax, eax
0x18004c202  jz      short loc_18004C239
0x18004c204  mov     rdx, rax
0x18004c207  mov     rcx, rbx
0x18004c20a  call    PositionFromID
0x18004c20f  test    eax, eax
0x18004c211  js      short loc_18004C239
0x18004c213  movups  xmm0, xmmword ptr [rbp+130h+lParam]
0x18004c217  cdqe
0x18004c219  movups  xmm1, [rbp+130h+var_170]
0x18004c21d  lea     rcx, [rax+rax*4]
  ... truncated ...
```
