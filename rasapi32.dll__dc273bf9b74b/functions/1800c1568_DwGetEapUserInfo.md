# DwGetEapUserInfo

- ea: `0x1800c1568`
- end: `0x1800c17cb`
- name: `DwGetEapUserInfo`
- size: `611`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180067888`
- `0x180070a40`

## callees

- `0x1800c13d4`
- `0x1800c1568`
- `0x1800decee`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c162a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c162a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c17ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c17ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1685`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1685`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1777`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c179b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1777`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c179b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1697`

## pseudocode

```c
__int64 __fastcall DwGetEapUserInfo(int a1, void *a2, _DWORD *a3, _QWORD *a4, int a5, int a6)
{
  _QWORD *v6; // r15
  void *v8; // rbp
  DWORD EapInfo; // ebx
  unsigned int v10; // edi
  unsigned int *v11; // rsi
  unsigned int v12; // r15d
  unsigned int *v13; // r12
  char *v14; // rbp
  char *i; // rcx
  unsigned int *v16; // rax
  unsigned int *v17; // r13
  unsigned int v18; // ecx
  unsigned int *v19; // rdx
  __int64 v20; // rax
  _DWORD *v21; // rdi
  unsigned int *v22; // rdi
  unsigned int *v23; // rsi
  __int64 v24; // rdx
  void *Src; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey[8]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v29; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v30; // [rsp+98h] [rbp+20h]

  v30 = a4;
  Src = 0;
  v6 = a4;
  v29 = 0;
  hKey[0] = 0;
  v8 = a2;
  if ( !a3 )
    return (DWORD)-2147024809;
  if ( !a4 )
  {
    EapInfo = 0;
    *a3 = 0;
    return EapInfo;
  }
  EapInfo = DwGetEapInfo(a1, a5, (unsigned int)&Src, (unsigned int)&v29, (__int64)hKey);
  if ( EapInfo || (v10 = v29) == 0 )
  {
    v11 = (unsigned int *)Src;
    goto LABEL_39;
  }
  v11 = (unsigned int *)Src;
  if ( v29 < 4 )
    goto LABEL_10;
  if ( *(_DWORD *)Src == 827343173 )
  {
    v12 = 0;
    v13 = (unsigned int *)((char *)Src + v29);
    v14 = (char *)Src;
    for ( i = (char *)Src; i < (char *)v13; i += (unsigned int)(*((_DWORD *)i + 6) + 32) )
    {
      if ( *((_DWORD *)i + 6) >= 0xFFFFFFE0 || v12 + ((*((_DWORD *)i + 6) + 39) & 0xFFFFFFF8) < v12 )
      {
        EapInfo = -2147024362;
        goto LABEL_39;
      }
      v12 += (*((_DWORD *)i + 6) + 39) & 0xFFFFFFF8;
    }
    v16 = (unsigned int *)LocalAlloc(0x40u, v12);
    v17 = v16;
    if ( v16 )
    {
      EapInfo = 0;
      v22 = v11;
      v23 = v16;
      if ( v14 < (char *)v13 )
      {
        do
        {
          memcpy_0(v23, v22, v22[6] + 32LL);
          *v23 = 844120389;
          v24 = v22[6];
          v22 = (unsigned int *)((char *)v22 + v24 + 32);
          v23 = (unsigned int *)((char *)v23 + ((v24 + 39) & 0xFFFFFFFFFFFFFFF8uLL));
        }
        while ( v22 < v13 );
      }
      v11 = v17;
      v10 = v12;
      if ( v14 )
      {
        LocalFree(v14);
LABEL_21:
        v8 = a2;
        v6 = v30;
        goto LABEL_22;
      }
    }
    else
    {
      EapInfo = GetLastError();
    }
    if ( EapInfo )
      goto LABEL_39;
    goto LABEL_21;
  }
  if ( *(_DWORD *)Src != 844120389 )
  {
LABEL_10:
    RegDeleteValueW(hKey[0], L"EapInfo");
LABEL_11:
    *a3 = 0;
    goto LABEL_39;
  }
LABEL_22:
  v18 = 0;
  v19 = v11;
  if ( !v10 )
    goto LABEL_11;
  do
  {
    v20 = *v6 - *((_QWORD *)v19 + 1);
    if ( *v6 == *((_QWORD *)v19 + 1) )
      v20 = v6[1] - *((_QWORD *)v19 + 2);
    if ( !v20 && a6 == v19[1] )
      break;
    v18 += (v19[6] + 39) & 0xFFFFFFF8;
    v19 = (unsigned int *)((char *)v11 + v18);
  }
  while ( v18 < v10 );
  if ( v18 >= v10 )
    goto LABEL_11;
  v21 = v19 + 6;
  if ( v8 && *a3 >= *v21 )
    memcpy_0(v8, v19 + 7, (unsigned int)*v21);
  else
    EapInfo = 603;
  *a3 = *v21;
LABEL_39:
  if ( v11 )
    LocalFree(v11);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return EapInfo;
}

```

## disassembly

```asm
0x1800c1568  mov     rax, rsp
0x1800c156b  mov     [rax+8], rbx
0x1800c156f  mov     [rax+20h], r9
0x1800c1573  mov     [rax+10h], rdx
0x1800c1577  push    rbp
0x1800c1578  push    rsi
0x1800c1579  push    rdi
0x1800c157a  push    r12
0x1800c157c  push    r13
0x1800c157e  push    r14
0x1800c1580  push    r15
0x1800c1582  sub     rsp, 40h
0x1800c1586  mov     qword ptr [rax-48h], 0
0x1800c158e  mov     r15, r9
0x1800c1591  mov     dword ptr [rax+18h], 0
0x1800c1598  mov     r14, r8
0x1800c159b  mov     qword ptr [rax-40h], 0
0x1800c15a3  mov     rbp, rdx
0x1800c15a6  test    r8, r8
0x1800c15a9  jnz     short loc_1800C15B5
0x1800c15ab  mov     ebx, 80070057h
0x1800c15b0  jmp     loc_1800C17B1
0x1800c15b5  test    r9, r9
0x1800c15b8  jnz     short loc_1800C15C4
0x1800c15ba  xor     ebx, ebx
0x1800c15bc  mov     [r8], ebx
0x1800c15bf  jmp     loc_1800C17B1
0x1800c15c4  mov     edx, [rsp+78h+arg_20]
0x1800c15cb  lea     rax, [rsp+78h+hKey]
0x1800c15d0  lea     r9, [rsp+78h+arg_10]
0x1800c15d8  mov     [rsp+78h+var_58], rax
0x1800c15dd  lea     r8, [rsp+78h+Src]
0x1800c15e2  call    DwGetEapInfo
0x1800c15e7  mov     ebx, eax
0x1800c15e9  test    eax, eax
0x1800c15eb  jnz     loc_1800C178E
0x1800c15f1  mov     edi, [rsp+78h+arg_10]
0x1800c15f8  test    edi, edi
0x1800c15fa  jz      loc_1800C178E
0x1800c1600  mov     rsi, [rsp+78h+Src]
0x1800c1605  cmp     edi, 4
0x1800c1608  jb      short loc_1800C161E
0x1800c160a  cmp     dword ptr [rsi], 31504145h
0x1800c1610  jz      short loc_1800C163C
0x1800c1612  cmp     dword ptr [rsi], 32504145h
0x1800c1618  jz      loc_1800C16B7
0x1800c161e  mov     rcx, [rsp+78h+hKey]; hKey
0x1800c1623  lea     rdx, aEapinfo; "EapInfo"
0x1800c162a  call    cs:__imp_RegDeleteValueW
0x1800c1630  mov     dword ptr [r14], 0
0x1800c1637  jmp     loc_1800C1793
0x1800c163c  xor     r15d, r15d
0x1800c163f  lea     r12, [rsi+rdi]
0x1800c1643  mov     rbp, rsi
0x1800c1646  mov     rcx, rsi
0x1800c1649  cmp     rcx, r12
0x1800c164c  jnb     short loc_1800C167D
0x1800c164e  mov     edx, [rcx+18h]
0x1800c1651  add     edx, 20h ; ' '
0x1800c1654  cmp     edx, 20h ; ' '
0x1800c1657  jb      short loc_1800C1673
0x1800c1659  lea     r8d, [rdx+7]
0x1800c165d  and     r8d, 0FFFFFFF8h
0x1800c1661  add     r8d, r15d
0x1800c1664  cmp     r8d, r15d
0x1800c1667  jb      short loc_1800C1673
0x1800c1669  mov     eax, edx
0x1800c166b  mov     r15d, r8d
0x1800c166e  add     rcx, rax
0x1800c1671  jmp     short loc_1800C1649
0x1800c1673  mov     ebx, 80070216h
0x1800c1678  jmp     loc_1800C1793
0x1800c167d  mov     edx, r15d; uBytes
0x1800c1680  mov     ecx, 40h ; '@'; uFlags
0x1800c1685  call    cs:__imp_LocalAlloc
0x1800c168b  mov     r13, rax
0x1800c168e  test    rax, rax
0x1800c1691  jnz     loc_1800C1725
0x1800c1697  call    cs:__imp_GetLastError
0x1800c169d  mov     ebx, eax
0x1800c169f  test    ebx, ebx
0x1800c16a1  jnz     loc_1800C1793
0x1800c16a7  mov     rbp, [rsp+78h+arg_8]
0x1800c16af  mov     r15, [rsp+78h+arg_18]
0x1800c16b7  xor     ecx, ecx
0x1800c16b9  mov     rdx, rsi
0x1800c16bc  test    edi, edi
0x1800c16be  jz      loc_1800C1630
0x1800c16c4  mov     r8d, [rsp+78h+arg_28]
0x1800c16cc  mov     rax, [r15]
0x1800c16cf  sub     rax, [rdx+8]
0x1800c16d3  jnz     short loc_1800C16DD
0x1800c16d5  mov     rax, [r15+8]
0x1800c16d9  sub     rax, [rdx+10h]
0x1800c16dd  test    rax, rax
0x1800c16e0  jnz     short loc_1800C16E8
0x1800c16e2  cmp     r8d, [rdx+4]
0x1800c16e6  jz      short loc_1800C16FC
0x1800c16e8  mov     eax, [rdx+18h]
0x1800c16eb  add     eax, 27h ; '''
0x1800c16ee  and     eax, 0FFFFFFF8h
0x1800c16f1  add     ecx, eax
0x1800c16f3  mov     edx, ecx
0x1800c16f5  add     rdx, rsi
0x1800c16f8  cmp     ecx, edi
0x1800c16fa  jb      short loc_1800C16CC
0x1800c16fc  cmp     ecx, edi
0x1800c16fe  jnb     loc_1800C1630
0x1800c1704  lea     rdi, [rdx+18h]
0x1800c1708  test    rbp, rbp
0x1800c170b  jz      short loc_1800C1782
0x1800c170d  mov     eax, [rdi]
0x1800c170f  cmp     [r14], eax
0x1800c1712  jb      short loc_1800C1782
0x1800c1714  mov     r8d, eax; Size
0x1800c1717  add     rdx, 1Ch; Src
0x1800c171b  mov     rcx, rbp; void *
0x1800c171e  call    memcpy_0
0x1800c1723  jmp     short loc_1800C1787
0x1800c1725  xor     ebx, ebx
0x1800c1727  mov     rdi, rbp
0x1800c172a  mov     rsi, r13
0x1800c172d  cmp     rbp, r12
0x1800c1730  jnb     short loc_1800C1765
0x1800c1732  mov     r8d, [rdi+18h]
0x1800c1736  mov     rdx, rdi; Src
0x1800c1739  add     r8, 20h ; ' '; Size
0x1800c173d  mov     rcx, rsi; void *
0x1800c1740  call    memcpy_0
0x1800c1745  mov     dword ptr [rsi], 32504145h
0x1800c174b  mov     edx, [rdi+18h]
0x1800c174e  add     rdi, 20h ; ' '
0x1800c1752  add     rdi, rdx
0x1800c1755  lea     rax, [rdx+27h]
0x1800c1759  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800c175d  add     rsi, rax
0x1800c1760  cmp     rdi, r12
0x1800c1763  jb      short loc_1800C1732
0x1800c1765  mov     rsi, r13
0x1800c1768  mov     edi, r15d
0x1800c176b  test    rbp, rbp
0x1800c176e  jz      loc_1800C169F
0x1800c1774  mov     rcx, rbp; hMem
0x1800c1777  call    cs:__imp_LocalFree
0x1800c177d  jmp     loc_1800C16A7
0x1800c1782  mov     ebx, 25Bh
0x1800c1787  mov     eax, [rdi]
0x1800c1789  mov     [r14], eax
0x1800c178c  jmp     short loc_1800C1793
0x1800c178e  mov     rsi, [rsp+78h+Src]
0x1800c1793  test    rsi, rsi
0x1800c1796  jz      short loc_1800C17A1
0x1800c1798  mov     rcx, rsi; hMem
0x1800c179b  call    cs:__imp_LocalFree
0x1800c17a1  mov     rcx, [rsp+78h+hKey]; hKey
0x1800c17a6  test    rcx, rcx
0x1800c17a9  jz      short loc_1800C17B1
0x1800c17ab  call    cs:__imp_RegCloseKey
0x1800c17b1  mov     eax, ebx
0x1800c17b3  mov     rbx, [rsp+78h+arg_0]
0x1800c17bb  add     rsp, 40h
0x1800c17bf  pop     r15
0x1800c17c1  pop     r14
0x1800c17c3  pop     r13
0x1800c17c5  pop     r12
0x1800c17c7  pop     rdi
0x1800c17c8  pop     rsi
0x1800c17c9  pop     rbp
0x1800c17ca  retn
```
