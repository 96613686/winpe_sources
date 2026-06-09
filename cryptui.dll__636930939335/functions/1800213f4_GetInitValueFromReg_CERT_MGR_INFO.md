# GetInitValueFromReg(_CERT_MGR_INFO *)

- ea: `0x1800213f4`
- end: `0x18002171c`
- name: `?GetInitValueFromReg@@YAXPEAU_CERT_MGR_INFO@@@Z`
- size: `808`
- prototype: `void __fastcall(struct _CERT_MGR_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022490`

## callees

- `0x1800213f4`

## import_xrefs

- `msvcrt!_stricmp` at `0x180021620`
- `msvcrt!_stricmp` at `0x180021620`
- `msvcrt!strtok` at `0x18002164b`
- `msvcrt!strtok` at `0x18002164b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002157f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002165e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002157f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002165e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800216d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800216e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800216d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800216e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021565`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800215b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021565`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800215b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800214b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800214b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021474`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002152f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021474`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002152f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800216f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021705`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800216f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021705`

## pseudocode

```c
void __fastcall GetInitValueFromReg(struct _CERT_MGR_INFO *a1)
{
  unsigned int v1; // r15d
  BYTE *v3; // r12
  int v4; // r14d
  __int64 v5; // rax
  unsigned int v6; // esi
  _QWORD *v7; // rdi
  unsigned int j; // r14d
  const char *v9; // rax
  char *i; // rcx
  BYTE *v11; // rcx
  unsigned int v12; // edx
  __int64 v13; // rax
  HKEY phkResult; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  __int128 v16; // [rsp+40h] [rbp-28h]
  _QWORD v17[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD Type; // [rsp+B0h] [rbp+48h] BYREF
  DWORD lpcbData; // [rsp+B8h] [rbp+50h] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+58h] BYREF
  int Data; // [rsp+C8h] [rbp+60h] BYREF

  v1 = 0;
  v17[0] = "1.3.6.1.5.5.7.3.2";
  v17[1] = "1.3.6.1.5.5.7.3.4";
  hKey = 0;
  phkResult = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  lpcbData = 0;
  if ( !a1 )
    return;
  v3 = 0;
  v4 = 0;
  v16 = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Cryptography\\UI\\Certmgr\\ExportFormat",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"Export", 0, &Type, (LPBYTE)&Data, &cbData) && Type - 3 <= 1 )
    {
      switch ( Data )
      {
        case 1:
          *((_QWORD *)a1 + 5) = 1;
          break;
        case 2:
          *((_QWORD *)a1 + 5) = 4;
          break;
        case 3:
          *((_QWORD *)a1 + 5) = 3;
          break;
        case 4:
          *((_DWORD *)a1 + 10) = 1;
          goto LABEL_14;
        case 5:
          *((_DWORD *)a1 + 10) = 4;
          goto LABEL_14;
        case 6:
          *((_DWORD *)a1 + 10) = 3;
LABEL_14:
          *((_DWORD *)a1 + 11) = 1;
          break;
      }
    }
  }
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Cryptography\\UI\\Certmgr\\Purpose",
         0,
         0x20019u,
         &phkResult) )
  {
    goto LABEL_27;
  }
  Type = 0;
  lpcbData = 0;
  if ( RegQueryValueExA(phkResult, "Purpose", 0, &Type, 0, &lpcbData) || !lpcbData )
    goto LABEL_27;
  v3 = (BYTE *)LocalAlloc(0x40u, lpcbData);
  if ( v3 )
  {
    if ( RegQueryValueExA(phkResult, "Purpose", 0, &Type, v3, &lpcbData) )
    {
      v7 = (_QWORD *)*((_QWORD *)&v16 + 1);
    }
    else
    {
      v5 = -1;
      do
        ++v5;
      while ( v3[v5] );
      if ( !(_DWORD)v5 )
      {
        v4 = 1;
LABEL_27:
        v6 = v16;
        v7 = (_QWORD *)*((_QWORD *)&v16 + 1);
        goto LABEL_28;
      }
      v6 = 0;
      for ( i = (char *)v3; strtok(i, ","); i = 0 )
        ++v6;
      v7 = LocalAlloc(0x40u, 8LL * v6);
      if ( v7 )
      {
        v11 = v3;
        v12 = 0;
        if ( !v6 )
        {
LABEL_29:
          if ( v4 != 1 )
          {
            v6 = 2;
            v7 = v17;
          }
LABEL_31:
          for ( j = 0; j < *((_DWORD *)a1 + 6); v1 = 0 )
          {
            v9 = *(const char **)(*((_QWORD *)a1 + 4) + 24LL * j + 16);
            *(_QWORD *)&v16 = v9;
            while ( v1 < v6 )
            {
              if ( !_stricmp((const char *)v7[v1], v9) )
                goto LABEL_50;
              v9 = (const char *)v16;
              ++v1;
            }
            *(_DWORD *)(*((_QWORD *)a1 + 4) + 24LL * j + 8) = 1;
LABEL_50:
            ++j;
          }
          if ( !v3 )
            goto LABEL_54;
          goto LABEL_52;
        }
        do
        {
          v7[v12] = v11;
          if ( v11 )
          {
            v13 = -1;
            do
              ++v13;
            while ( v11[v13] );
          }
          else
          {
            LODWORD(v13) = 0;
          }
          v11 += (int)v13 + 1;
          ++v12;
        }
        while ( v12 < v6 );
LABEL_28:
        if ( v6 )
          goto LABEL_31;
        goto LABEL_29;
      }
    }
LABEL_52:
    LocalFree(v3);
    if ( v7 )
      LocalFree(v7);
  }
LABEL_54:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x1800213f4  push    rbp
0x1800213f6  push    rbx
0x1800213f7  push    rsi
0x1800213f8  push    rdi
0x1800213f9  push    r12
0x1800213fb  push    r13
0x1800213fd  push    r14
0x1800213ff  push    r15
0x180021401  mov     rbp, rsp
0x180021404  sub     rsp, 68h
0x180021408  xor     r15d, r15d
0x18002140b  lea     rax, a136155732; "1.3.6.1.5.5.7.3.2"
0x180021412  mov     [rbp+var_18], rax
0x180021416  lea     rax, a136155734; "1.3.6.1.5.5.7.3.4"
0x18002141d  mov     [rbp+var_10], rax
0x180021421  mov     rbx, rcx
0x180021424  mov     [rbp+hKey], r15
0x180021428  mov     [rbp+var_38], r15
0x18002142c  mov     [rbp+Type], r15d
0x180021430  mov     [rbp+Data], r15d
0x180021434  mov     [rbp+cbData], r15d
0x180021438  mov     [rbp+arg_8], r15d
0x18002143c  test    rcx, rcx
0x18002143f  jz      loc_18002170B
0x180021445  xorps   xmm0, xmm0
0x180021448  lea     rax, [rbp+hKey]
0x18002144c  mov     esi, 20019h
0x180021451  mov     [rsp+68h+phkResult], rax; phkResult
0x180021456  mov     r9d, esi; samDesired
0x180021459  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Cryptography\\UI\\"...
0x180021460  xor     r8d, r8d; ulOptions
0x180021463  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002146a  mov     r12d, r15d
0x18002146d  mov     r14d, r15d
0x180021470  movups  [rbp+var_28], xmm0
0x180021474  call    cs:__imp_RegOpenKeyExW
0x18002147a  lea     r13d, [r15+1]
0x18002147e  test    eax, eax
0x180021480  jnz     loc_180021512
0x180021486  mov     rcx, [rbp+hKey]; hKey
0x18002148a  lea     edi, [rax+4]
0x18002148d  lea     rax, [rbp+cbData]
0x180021491  mov     [rbp+cbData], edi
0x180021494  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180021499  lea     r9, [rbp+Type]; lpType
0x18002149d  lea     rax, [rbp+Data]
0x1800214a1  xor     r8d, r8d; lpReserved
0x1800214a4  lea     rdx, aExport; "Export"
0x1800214ab  mov     [rsp+68h+phkResult], rax; lpData
0x1800214b0  call    cs:__imp_RegQueryValueExW
0x1800214b6  test    eax, eax
0x1800214b8  jnz     short loc_180021512
0x1800214ba  mov     eax, [rbp+Type]
0x1800214bd  add     eax, 0FFFFFFFDh
0x1800214c0  cmp     eax, r13d
0x1800214c3  ja      short loc_180021512
0x1800214c5  mov     eax, [rbp+Data]
0x1800214c8  sub     eax, r13d
0x1800214cb  jz      short loc_18002150E
0x1800214cd  sub     eax, r13d
0x1800214d0  jz      short loc_180021508
0x1800214d2  sub     eax, r13d
0x1800214d5  jz      short loc_1800214FE
0x1800214d7  sub     eax, r13d
0x1800214da  jz      short loc_1800214F4
0x1800214dc  sub     eax, r13d
0x1800214df  jz      short loc_1800214EF
0x1800214e1  cmp     eax, r13d
0x1800214e4  jnz     short loc_180021512
0x1800214e6  mov     dword ptr [rbx+28h], 3
0x1800214ed  jmp     short loc_1800214F8
0x1800214ef  mov     [rbx+28h], edi
0x1800214f2  jmp     short loc_1800214F8
0x1800214f4  mov     [rbx+28h], r13d
0x1800214f8  mov     [rbx+2Ch], r13d
0x1800214fc  jmp     short loc_180021512
0x1800214fe  mov     qword ptr [rbx+28h], 3
0x180021506  jmp     short loc_180021512
0x180021508  mov     [rbx+28h], rdi
0x18002150c  jmp     short loc_180021512
0x18002150e  mov     [rbx+28h], r13
0x180021512  lea     rax, [rbp+var_38]
0x180021516  mov     r9d, esi; samDesired
0x180021519  xor     r8d, r8d; ulOptions
0x18002151c  mov     [rsp+68h+phkResult], rax; phkResult
0x180021521  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Cryptography\\UI\\"...
0x180021528  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002152f  call    cs:__imp_RegOpenKeyExW
0x180021535  test    eax, eax
0x180021537  jnz     loc_1800215D3
0x18002153d  mov     rcx, [rbp+var_38]; hKey
0x180021541  lea     rax, [rbp+arg_8]
0x180021545  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18002154a  lea     r9, [rbp+Type]; lpType
0x18002154e  xor     r8d, r8d; lpReserved
0x180021551  mov     [rsp+68h+phkResult], r15; lpData
0x180021556  lea     rdx, aPurpose; "Purpose"
0x18002155d  mov     [rbp+Type], r15d
0x180021561  mov     [rbp+arg_8], r15d
0x180021565  call    cs:__imp_RegQueryValueExA
0x18002156b  test    eax, eax
0x18002156d  jnz     short loc_1800215D3
0x18002156f  mov     eax, [rbp+arg_8]
0x180021572  test    eax, eax
0x180021574  jz      short loc_1800215D3
0x180021576  mov     edi, 40h ; '@'
0x18002157b  mov     edx, eax; uBytes
0x18002157d  mov     ecx, edi; uFlags
0x18002157f  call    cs:__imp_LocalAlloc
0x180021585  mov     r12, rax
0x180021588  test    rax, rax
0x18002158b  jz      loc_1800216ED
0x180021591  mov     rcx, [rbp+var_38]; hKey
0x180021595  lea     rax, [rbp+arg_8]
0x180021599  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18002159e  lea     r9, [rbp+Type]; lpType
0x1800215a2  xor     r8d, r8d; lpReserved
0x1800215a5  mov     [rsp+68h+phkResult], r12; lpData
0x1800215aa  lea     rdx, aPurpose; "Purpose"
0x1800215b1  call    cs:__imp_RegQueryValueExA
0x1800215b7  test    eax, eax
0x1800215b9  jnz     loc_1800216AB
0x1800215bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800215c3  inc     rax
0x1800215c6  cmp     [r12+rax], r15b
0x1800215ca  jnz     short loc_1800215C3
0x1800215cc  test    eax, eax
0x1800215ce  jnz     short loc_180021637
0x1800215d0  mov     r14d, r13d
0x1800215d3  mov     esi, dword ptr [rbp+var_28]
0x1800215d6  mov     rdi, qword ptr [rbp+var_28+8]
0x1800215da  test    esi, esi
0x1800215dc  jnz     short loc_1800215EC
0x1800215de  cmp     r14d, r13d
0x1800215e1  jz      short loc_1800215EC
0x1800215e3  mov     esi, 2
0x1800215e8  lea     rdi, [rbp+var_18]
0x1800215ec  mov     r14d, r15d
0x1800215ef  cmp     [rbx+18h], r15d
0x1800215f3  jbe     loc_1800216D1
0x1800215f9  mov     eax, r14d
0x1800215fc  lea     r13, [rax+rax*2]
0x180021600  mov     rax, [rbx+20h]
0x180021604  mov     rax, [rax+r13*8+10h]
0x180021609  mov     qword ptr [rbp+var_28], rax
0x18002160d  cmp     r15d, esi
0x180021610  jnb     loc_1800216B1
0x180021616  mov     ecx, r15d
0x180021619  mov     rdx, rax; String2
0x18002161c  mov     rcx, [rdi+rcx*8]; String1
0x180021620  call    cs:__imp__stricmp
0x180021626  test    eax, eax
0x180021628  jz      loc_1800216BE
0x18002162e  mov     rax, qword ptr [rbp+var_28]
0x180021632  inc     r15d
0x180021635  jmp     short loc_18002160D
0x180021637  mov     esi, r15d
0x18002163a  mov     rcx, r12
0x18002163d  jmp     short loc_180021644
0x18002163f  add     esi, r13d
0x180021642  xor     ecx, ecx; String
0x180021644  lea     rdx, Delimiter; ","
0x18002164b  call    cs:__imp_strtok
0x180021651  test    rax, rax
0x180021654  jnz     short loc_18002163F
0x180021656  mov     edx, esi
0x180021658  mov     ecx, edi; uFlags
0x18002165a  shl     rdx, 3; uBytes
0x18002165e  call    cs:__imp_LocalAlloc
0x180021664  mov     rdi, rax
0x180021667  test    rax, rax
0x18002166a  jz      short loc_1800216D6
0x18002166c  mov     rcx, r12
0x18002166f  mov     edx, r15d
0x180021672  test    esi, esi
0x180021674  jz      loc_1800215DE
0x18002167a  mov     eax, edx
0x18002167c  mov     [rdi+rax*8], rcx
0x180021680  test    rcx, rcx
0x180021683  jz      short loc_180021694
0x180021685  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021689  inc     rax
0x18002168c  cmp     [rcx+rax], r15b
0x180021690  jnz     short loc_180021689
0x180021692  jmp     short loc_180021697
0x180021694  mov     eax, r15d
0x180021697  inc     rcx
0x18002169a  cdqe
0x18002169c  add     rcx, rax
0x18002169f  add     edx, r13d
0x1800216a2  cmp     edx, esi
0x1800216a4  jb      short loc_18002167A
0x1800216a6  jmp     loc_1800215DA
0x1800216ab  mov     rdi, qword ptr [rbp+var_28+8]
0x1800216af  jmp     short loc_1800216D6
0x1800216b1  mov     rax, [rbx+20h]
0x1800216b5  mov     dword ptr [rax+r13*8+8], 1
0x1800216be  inc     r14d
0x1800216c1  mov     r15d, 0
0x1800216c7  cmp     r14d, [rbx+18h]
0x1800216cb  jb      loc_1800215F9
0x1800216d1  test    r12, r12
0x1800216d4  jz      short loc_1800216ED
0x1800216d6  mov     rcx, r12; hMem
0x1800216d9  call    cs:__imp_LocalFree
0x1800216df  test    rdi, rdi
0x1800216e2  jz      short loc_1800216ED
0x1800216e4  mov     rcx, rdi; hMem
0x1800216e7  call    cs:__imp_LocalFree
0x1800216ed  mov     rcx, [rbp+hKey]; hKey
0x1800216f1  test    rcx, rcx
0x1800216f4  jz      short loc_1800216FC
0x1800216f6  call    cs:__imp_RegCloseKey
0x1800216fc  mov     rcx, [rbp+var_38]; hKey
0x180021700  test    rcx, rcx
0x180021703  jz      short loc_18002170B
0x180021705  call    cs:__imp_RegCloseKey
0x18002170b  add     rsp, 68h
0x18002170f  pop     r15
0x180021711  pop     r14
0x180021713  pop     r13
0x180021715  pop     r12
0x180021717  pop     rdi
0x180021718  pop     rsi
0x180021719  pop     rbx
0x18002171a  pop     rbp
0x18002171b  retn
```
