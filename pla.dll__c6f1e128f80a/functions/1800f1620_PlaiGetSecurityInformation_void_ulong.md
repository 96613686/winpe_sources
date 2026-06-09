# PlaiGetSecurityInformation(void *,ulong *)

- ea: `0x1800f1620`
- end: `0x1800f19cb`
- name: `?PlaiGetSecurityInformation@@YAJPEAXPEAK@Z`
- size: `939`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180085210`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800f1620`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f167f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f179a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f167f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f179a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1950`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800f1671`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800f1671`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800f1866`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800f1866`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800f178c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800f178c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800f190b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800f190b`

## string_xrefs

- `0x1800f1714`: `PlaiGetSecurityInformation`
- `0x1800f182f`: `PlaiGetSecurityInformation`

## pseudocode

```c
__int64 __fastcall PlaiGetSecurityInformation(PSECURITY_DESCRIPTOR pSecurityDescriptor, unsigned int *a2)
{
  DWORD LastError; // eax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // edi
  DWORD v9; // eax
  int v10; // eax
  __int64 v11; // rax
  DWORD v12; // eax
  int v13; // eax
  __int64 v14; // rax
  DWORD v16; // eax
  int v17; // eax
  __int64 v18; // rax
  int v19; // [rsp+70h] [rbp-90h] BYREF
  int v20; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL bDaclPresent; // [rsp+84h] [rbp-7Ch] BYREF
  PSID pOwner; // [rsp+88h] [rbp-78h] BYREF
  PACL pDacl[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v25[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v26[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v27[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v28[64]; // [rsp+220h] [rbp+120h] BYREF

  pOwner = 0;
  pDacl[0] = 0;
  bDaclPresent = 0;
  bOwnerDefaulted = 0;
  if ( !GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
  {
    LastError = GetLastError();
    v5 = PlaiHResultFromWin32(LastError);
    v6 = v5;
    if ( v5 < 0 )
    {
      v19 = 0;
      v20 = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v25, 0x4000000000000800uLL);
        v7 = -1;
        do
          ++v7;
        while ( v25[v7] );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v20,
          4,
          qword_180147320,
          1,
          &v19,
          4,
          "PlaiGetSecurityInformation",
          27);
      }
      return v6;
    }
  }
  v8 = pOwner != 0;
  if ( !GetSecurityDescriptorGroup(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
  {
    v9 = GetLastError();
    v10 = PlaiHResultFromWin32(v9);
    v6 = v10;
    if ( v10 < 0 )
    {
      v20 = 0;
      v19 = v10;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        return v6;
      }
      PlaiWhoAmI(v26, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v26[v11] );
      goto LABEL_16;
    }
  }
  if ( pOwner )
    v8 |= 2u;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, pDacl, &bOwnerDefaulted) )
  {
    v12 = GetLastError();
    v13 = PlaiHResultFromWin32(v12);
    v6 = v13;
    if ( v13 < 0 )
    {
      v20 = 0;
      v19 = v13;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        return v6;
      }
      PlaiWhoAmI(v27, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v27[v14] );
      goto LABEL_16;
    }
  }
  if ( bDaclPresent )
    v8 |= 4u;
  if ( GetSecurityDescriptorSacl(pSecurityDescriptor, &bDaclPresent, pDacl, &bOwnerDefaulted) )
  {
    v6 = 0;
  }
  else
  {
    v16 = GetLastError();
    v17 = PlaiHResultFromWin32(v16);
    v6 = v17;
    if ( v17 < 0 )
    {
      v20 = 0;
      v19 = v17;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        return v6;
      }
      PlaiWhoAmI(v28, 0x4000000000000800uLL);
      v18 = -1;
      do
        ++v18;
      while ( v28[v18] );
LABEL_16:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v19,
        4,
        qword_180147320,
        1,
        &v20,
        4,
        "PlaiGetSecurityInformation",
        27);
      return v6;
    }
  }
  if ( bDaclPresent )
    v8 |= 8u;
  *a2 = v8;
  return v6;
}

```

## disassembly

```asm
0x1800f1620  mov     [rsp-8+arg_10], rbx
0x1800f1625  push    rbp
0x1800f1626  push    rsi
0x1800f1627  push    rdi
0x1800f1628  push    r12
0x1800f162a  push    r13
0x1800f162c  push    r14
0x1800f162e  push    r15
0x1800f1630  lea     rbp, [rsp-1B0h]
0x1800f1638  sub     rsp, 2B0h
0x1800f163f  mov     rax, cs:__security_cookie
0x1800f1646  xor     rax, rsp
0x1800f1649  mov     [rbp+1E0h+var_40], rax
0x1800f1650  xor     r13d, r13d
0x1800f1653  lea     r8, [rbp+1E0h+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800f1657  mov     r15, rdx
0x1800f165a  mov     [rbp+1E0h+pOwner], r13
0x1800f165e  lea     rdx, [rbp+1E0h+pOwner]; pOwner
0x1800f1662  mov     [rbp+1E0h+pDacl], r13
0x1800f1666  mov     [rbp+1E0h+bDaclPresent], r13d
0x1800f166a  mov     r14, rcx
0x1800f166d  mov     [rbp+1E0h+bOwnerDefaulted], r13d
0x1800f1671  call    cs:__imp_GetSecurityDescriptorOwner
0x1800f1677  test    eax, eax
0x1800f1679  jnz     loc_1800F1770
0x1800f167f  call    cs:__imp_GetLastError
0x1800f1685  mov     ecx, eax; unsigned int
0x1800f1687  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f168c  mov     ebx, eax
0x1800f168e  test    eax, eax
0x1800f1690  jns     loc_1800F1770
0x1800f1696  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800f169d  mov     [rsp+2E0h+var_270], r13d
0x1800f16a2  mov     [rsp+2E0h+var_268], eax
0x1800f16a6  jz      loc_1800F1924
0x1800f16ac  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f16b6  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f16bd  jz      loc_1800F1924
0x1800f16c3  mov     rax, cs:qword_180169748
0x1800f16ca  and     rax, rdx
0x1800f16cd  cmp     cs:qword_180169748, rax
0x1800f16d4  jnz     loc_1800F1924
0x1800f16da  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x1800f16de  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f16e3  lea     rcx, [rbp+1E0h+var_240]
0x1800f16e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f16eb  inc     rax
0x1800f16ee  cmp     [rcx+rax*2], r13w
0x1800f16f3  jnz     short loc_1800F16EB
0x1800f16f5  lea     ecx, [rax+rax]
0x1800f16f8  mov     esi, 4
0x1800f16fd  lea     rax, [rbp+1E0h+var_240]
0x1800f1701  add     rcx, 2
0x1800f1705  mov     [rsp+2E0h+var_280], rcx
0x1800f170a  lea     r9, [rsp+2E0h+var_268]
0x1800f170f  mov     [rsp+2E0h+var_288], rax
0x1800f1714  lea     rax, aPlaigetsecurit; "PlaiGetSecurityInformation"
0x1800f171b  mov     [rsp+2E0h+var_290], 1Bh
0x1800f1724  lea     r12d, [rsi-3]
0x1800f1728  mov     [rsp+2E0h+var_298], rax
0x1800f172d  lea     rax, [rsp+2E0h+var_270]
0x1800f1732  mov     [rsp+2E0h+var_2A0], rsi
0x1800f1737  lea     rdx, PLA_EVENT_ERROR
0x1800f173e  mov     [rsp+2E0h+var_2A8], rax
0x1800f1743  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f174a  lea     rax, qword_180147320
0x1800f1751  mov     [rsp+2E0h+var_2B0], r12
0x1800f1756  mov     [rsp+2E0h+var_2B8], rax
0x1800f175b  mov     r8d, 5
0x1800f1761  mov     [rsp+2E0h+var_2C0], rsi
0x1800f1766  call    EventingWriteEvent
0x1800f176b  jmp     loc_1800F1924
0x1800f1770  cmp     [rbp+1E0h+pOwner], r13
0x1800f1774  lea     r8, [rbp+1E0h+bOwnerDefaulted]; lpbGroupDefaulted
0x1800f1778  mov     edi, r13d
0x1800f177b  lea     rdx, [rbp+1E0h+pOwner]; pGroup
0x1800f177f  mov     r12d, 1
0x1800f1785  mov     rcx, r14; pSecurityDescriptor
0x1800f1788  cmovnz  edi, r12d
0x1800f178c  call    cs:__imp_GetSecurityDescriptorGroup
0x1800f1792  test    eax, eax
0x1800f1794  jnz     loc_1800F184E
0x1800f179a  call    cs:__imp_GetLastError
0x1800f17a0  mov     ecx, eax; unsigned int
0x1800f17a2  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f17a7  mov     ebx, eax
0x1800f17a9  test    eax, eax
0x1800f17ab  jns     loc_1800F184E
0x1800f17b1  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800f17b8  mov     [rsp+2E0h+var_268], r13d
0x1800f17bd  mov     [rsp+2E0h+var_270], eax
0x1800f17c1  jz      loc_1800F1924
0x1800f17c7  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f17d1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f17d8  jz      loc_1800F1924
0x1800f17de  mov     rax, cs:qword_180169748
0x1800f17e5  and     rax, rdx
0x1800f17e8  cmp     cs:qword_180169748, rax
0x1800f17ef  jnz     loc_1800F1924
0x1800f17f5  lea     rcx, [rbp+1E0h+var_1C0]; unsigned __int16 *
0x1800f17f9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f17fe  lea     rcx, [rbp+1E0h+var_1C0]
0x1800f1802  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f1806  inc     rax
0x1800f1809  cmp     [rcx+rax*2], r13w
0x1800f180e  jnz     short loc_1800F1806
0x1800f1810  lea     ecx, [rax+rax]
0x1800f1813  lea     rax, [rbp+1E0h+var_1C0]
0x1800f1817  mov     esi, 4
0x1800f181c  add     rcx, 2
0x1800f1820  lea     r9, [rsp+2E0h+var_270]
0x1800f1825  mov     [rsp+2E0h+var_280], rcx
0x1800f182a  mov     [rsp+2E0h+var_288], rax
0x1800f182f  lea     rax, aPlaigetsecurit; "PlaiGetSecurityInformation"
0x1800f1836  mov     [rsp+2E0h+var_290], 1Bh
0x1800f183f  mov     [rsp+2E0h+var_298], rax
0x1800f1844  lea     rax, [rsp+2E0h+var_268]
0x1800f1849  jmp     loc_1800F1732
0x1800f184e  cmp     [rbp+1E0h+pOwner], r13
0x1800f1852  jz      short loc_1800F1857
0x1800f1854  or      edi, 2
0x1800f1857  lea     r9, [rbp+1E0h+bOwnerDefaulted]; lpbDaclDefaulted
0x1800f185b  mov     rcx, r14; pSecurityDescriptor
0x1800f185e  lea     r8, [rbp+1E0h+pDacl]; pDacl
0x1800f1862  lea     rdx, [rbp+1E0h+bDaclPresent]; lpbDaclPresent
0x1800f1866  call    cs:__imp_GetSecurityDescriptorDacl
0x1800f186c  test    eax, eax
0x1800f186e  jnz     short loc_1800F18EF
0x1800f1870  call    cs:__imp_GetLastError
0x1800f1876  mov     ecx, eax; unsigned int
0x1800f1878  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f187d  mov     ebx, eax
0x1800f187f  test    eax, eax
0x1800f1881  jns     short loc_1800F18EF
0x1800f1883  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800f188a  mov     [rsp+2E0h+var_268], r13d
0x1800f188f  mov     [rsp+2E0h+var_270], eax
0x1800f1893  jz      loc_1800F1924
0x1800f1899  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f18a3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f18aa  jz      short loc_1800F1924
0x1800f18ac  mov     rax, cs:qword_180169748
0x1800f18b3  and     rax, rdx
0x1800f18b6  cmp     cs:qword_180169748, rax
0x1800f18bd  jnz     short loc_1800F1924
0x1800f18bf  lea     rcx, [rbp+1E0h+var_140]; unsigned __int16 *
0x1800f18c6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f18cb  lea     rcx, [rbp+1E0h+var_140]
0x1800f18d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f18d6  inc     rax
0x1800f18d9  cmp     [rcx+rax*2], r13w
0x1800f18de  jnz     short loc_1800F18D6
0x1800f18e0  lea     ecx, [rax+rax]
0x1800f18e3  lea     rax, [rbp+1E0h+var_140]
0x1800f18ea  jmp     loc_1800F1817
0x1800f18ef  mov     esi, 4
0x1800f18f4  cmp     [rbp+1E0h+bDaclPresent], r13d
0x1800f18f8  jz      short loc_1800F18FC
0x1800f18fa  or      edi, esi
0x1800f18fc  lea     r9, [rbp+1E0h+bOwnerDefaulted]; lpbSaclDefaulted
0x1800f1900  mov     rcx, r14; pSecurityDescriptor
0x1800f1903  lea     r8, [rbp+1E0h+pDacl]; pSacl
0x1800f1907  lea     rdx, [rbp+1E0h+bDaclPresent]; lpbSaclPresent
0x1800f190b  call    cs:__imp_GetSecurityDescriptorSacl
0x1800f1911  test    eax, eax
0x1800f1913  jz      short loc_1800F1950
0x1800f1915  mov     ebx, r13d
0x1800f1918  cmp     [rbp+1E0h+bDaclPresent], r13d
0x1800f191c  jz      short loc_1800F1921
0x1800f191e  or      edi, 8
0x1800f1921  mov     [r15], edi
0x1800f1924  mov     eax, ebx
0x1800f1926  mov     rcx, [rbp+1E0h+var_40]
0x1800f192d  xor     rcx, rsp; StackCookie
0x1800f1930  call    __security_check_cookie
0x1800f1935  mov     rbx, [rsp+2E0h+arg_10]
0x1800f193d  add     rsp, 2B0h
0x1800f1944  pop     r15
0x1800f1946  pop     r14
0x1800f1948  pop     r13
0x1800f194a  pop     r12
0x1800f194c  pop     rdi
0x1800f194d  pop     rsi
0x1800f194e  pop     rbp
0x1800f194f  retn
0x1800f1950  call    cs:__imp_GetLastError
0x1800f1956  mov     ecx, eax; unsigned int
0x1800f1958  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f195d  mov     ebx, eax
0x1800f195f  test    eax, eax
0x1800f1961  jns     short loc_1800F1918
0x1800f1963  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800f196a  mov     [rsp+2E0h+var_268], r13d
0x1800f196f  mov     [rsp+2E0h+var_270], eax
0x1800f1973  jz      short loc_1800F1924
0x1800f1975  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f197f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f1986  jz      short loc_1800F1924
0x1800f1988  mov     rax, cs:qword_180169748
0x1800f198f  and     rax, rdx
0x1800f1992  cmp     cs:qword_180169748, rax
0x1800f1999  jnz     short loc_1800F1924
0x1800f199b  lea     rcx, [rbp+1E0h+var_C0]; unsigned __int16 *
0x1800f19a2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f19a7  lea     rcx, [rbp+1E0h+var_C0]
0x1800f19ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f19b2  inc     rax
0x1800f19b5  cmp     [rcx+rax*2], r13w
0x1800f19ba  jnz     short loc_1800F19B2
0x1800f19bc  lea     ecx, [rax+rax]
0x1800f19bf  lea     rax, [rbp+1E0h+var_C0]
0x1800f19c6  jmp     loc_1800F181C
```
