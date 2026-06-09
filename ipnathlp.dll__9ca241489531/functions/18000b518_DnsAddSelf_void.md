# DnsAddSelf(void)

- ea: `0x18000b518`
- end: `0x18000b8f1`
- name: `?DnsAddSelf@@YAXXZ`
- size: `985`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180009b74`

## callees

- `0x180007fb4`
- `0x18000a6fc`
- `0x18000b518`
- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x1800128e0`
- `0x180032db8`
- `0x180037cf4`
- `0x18003f5a0`
- `0x18004e0c0`
- `0x18004ed64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b650`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b758`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b650`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b758`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b661`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b661`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b766`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b766`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b626`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b626`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b726`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b778`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b726`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7df`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b806`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b806`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b731`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b731`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000b591`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000b591`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b856`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b856`

## pseudocode

```c
void DnsAddSelf(void)
{
  unsigned int PrivateInterfaceAddress; // ebx
  PVOID *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rdx
  unsigned __int64 v4; // rdi
  SIZE_T v5; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi
  unsigned __int16 *v9; // r8
  WCHAR *v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rax
  bool v14; // zf
  unsigned __int16 *v15; // rcx
  unsigned __int64 v16; // rdx
  __int64 v17; // r8
  HANDLE v18; // rax
  __int64 v19; // rdx
  DWORD LastError; // eax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v23[4]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[512]; // [rsp+60h] [rbp-A0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
  nSize = 512;
  *(_QWORD *)v23 = 0;
  SystemTimeAsFileTime = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, &nSize) )
  {
    *(_QWORD *)v23 = 0;
    LastError = GetLastError();
    FormatMessageW(0x1300u, 0, LastError, 0x400u, v23, 0, 0);
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids,
        *(_QWORD *)v23);
      v1 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !*(_QWORD *)v23 )
    {
LABEL_7:
      if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x10) != 0 && *((_BYTE *)v1 + 25) >= 6u )
      {
        v19 = 63;
        goto LABEL_50;
      }
      return;
    }
    LocalFree(*(HLOCAL *)v23);
LABEL_6:
    v1 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  if ( AcquireComponentReference(&DhcpComponentReference)
    && (PrivateInterfaceAddress = DhcpGetPrivateInterfaceAddress(),
        ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DhcpComponentReference),
        PrivateInterfaceAddress)
    || (PrivateInterfaceAddress = DnsGetPrivateInterfaceAddress()) != 0 )
  {
    g_PrivateIPAddr = PrivateInterfaceAddress;
  }
  else
  {
    PrivateInterfaceAddress = g_PrivateIPAddr;
    if ( !g_PrivateIPAddr )
      goto LABEL_6;
  }
  if ( !DnsICSDomainSuffix )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_7;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
    goto LABEL_6;
  }
  EnterCriticalSection(&DnsGlobalInfoLock);
  v2 = -1;
  do
    ++v2;
  while ( DnsICSDomainSuffix[v2] );
  v3 = nSize + 2 + (unsigned int)v2;
  v4 = (unsigned int)v3;
  v5 = 2 * v3;
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v5);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, v5);
    if ( v4 )
    {
      if ( v4 > 0x7FFFFFFF )
      {
        *v8 = 0;
      }
      else
      {
        v9 = v8;
        v10 = Buffer;
        v11 = 2147483646;
        v12 = (unsigned int)v4;
        v13 = v8;
        do
        {
          if ( !v11 )
            break;
          if ( !*v10 )
            break;
          *v13++ = *v10++;
          --v11;
          --v12;
        }
        while ( v12 );
        v14 = v12 == 0;
        v15 = v13 - 1;
        v16 = v4;
        if ( !v14 )
          v15 = v13;
        *v15 = 0;
        do
        {
          if ( !*v9 )
            break;
          ++v9;
          --v16;
        }
        while ( v16 );
        if ( v16 )
        {
          v17 = (v4 - v16) & -(__int64)(v16 != 0);
          StringCopyWorkerW(&v8[v17], v4 - v17, (size_t *)v17, L".", (size_t)lpBuffer);
        }
      }
    }
    StringCchCatW(v8, v4, DnsICSDomainSuffix);
    LeaveCriticalSection(&DnsGlobalInfoLock);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(_QWORD *)&SystemTimeAsFileTime += 1576800000000000LL;
    DnsAddAddressForName(v8, PrivateInterfaceAddress, SystemTimeAsFileTime);
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v8);
    goto LABEL_6;
  }
  LeaveCriticalSection(&DnsGlobalInfoLock);
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = 61;
LABEL_50:
    WPP_SF_(v1[2], v19, &WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids);
  }
}

```

## disassembly

```asm
0x18000b518  push    rbp
0x18000b51a  push    rbx
0x18000b51b  push    rsi
0x18000b51c  push    rdi
0x18000b51d  push    r13
0x18000b51f  push    r14
0x18000b521  push    r15
0x18000b523  lea     rbp, [rsp-370h]
0x18000b52b  sub     rsp, 470h
0x18000b532  mov     rax, cs:__security_cookie
0x18000b539  xor     rax, rsp
0x18000b53c  mov     [rbp+3A0h+var_40], rax
0x18000b543  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b54a  lea     r13, WPP_GLOBAL_Control
0x18000b551  cmp     rcx, r13
0x18000b554  jnz     loc_18000B7AC
0x18000b55a  xor     r15d, r15d
0x18000b55d  mov     [rsp+4A0h+nSize], 200h
0x18000b565  mov     ebx, 400h
0x18000b56a  mov     qword ptr [rsp+4A0h+var_458], r15
0x18000b56f  mov     r8d, ebx; Size
0x18000b572  mov     qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18000b577  xor     edx, edx; Val
0x18000b579  lea     rcx, [rsp+4A0h+Buffer]; void *
0x18000b57e  call    memset_0
0x18000b583  lea     r8, [rsp+4A0h+nSize]; nSize
0x18000b588  lea     rdx, [rsp+4A0h+Buffer]; lpBuffer
0x18000b58d  lea     ecx, [r15+1]; NameType
0x18000b591  call    cs:__imp_GetComputerNameExW
0x18000b597  test    eax, eax
0x18000b599  jz      loc_18000B7DA
0x18000b59f  lea     rcx, ?DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x18000b5a6  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18000b5ab  test    al, al
0x18000b5ad  jnz     short loc_18000B5F5
0x18000b5af  call    ?DnsGetPrivateInterfaceAddress@@YAKXZ; DnsGetPrivateInterfaceAddress(void)
0x18000b5b4  mov     ebx, eax
0x18000b5b6  test    eax, eax
0x18000b5b8  jnz     short loc_18000B60C
0x18000b5ba  mov     ebx, cs:?g_PrivateIPAddr@@3KA; ulong g_PrivateIPAddr
0x18000b5c0  test    ebx, ebx
0x18000b5c2  jnz     short loc_18000B612
0x18000b5c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5cb  cmp     rcx, r13
0x18000b5ce  jnz     loc_18000B8C3
0x18000b5d4  mov     rcx, [rbp+3A0h+var_40]
0x18000b5db  xor     rcx, rsp; StackCookie
0x18000b5de  call    __security_check_cookie
0x18000b5e3  add     rsp, 470h
0x18000b5ea  pop     r15
0x18000b5ec  pop     r14
0x18000b5ee  pop     r13
0x18000b5f0  pop     rdi
0x18000b5f1  pop     rsi
0x18000b5f2  pop     rbx
0x18000b5f3  pop     rbp
0x18000b5f4  retn
0x18000b5f5  call    ?DhcpGetPrivateInterfaceAddress@@YAKXZ; DhcpGetPrivateInterfaceAddress(void)
0x18000b5fa  lea     rcx, ?DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18000b601  mov     ebx, eax
0x18000b603  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000b608  test    ebx, ebx
0x18000b60a  jz      short loc_18000B5AF
0x18000b60c  mov     cs:?g_PrivateIPAddr@@3KA, ebx; ulong g_PrivateIPAddr
0x18000b612  cmp     cs:?DnsICSDomainSuffix@@3PEAGEA, r15; ushort * DnsICSDomainSuffix
0x18000b619  jz      loc_18000B885
0x18000b61f  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b626  call    cs:__imp_EnterCriticalSection
0x18000b62c  mov     rax, cs:?DnsICSDomainSuffix@@3PEAGEA; ushort * DnsICSDomainSuffix
0x18000b633  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b637  inc     rdx
0x18000b63a  cmp     [rax+rdx*2], r15w
0x18000b63f  jnz     short loc_18000B637
0x18000b641  mov     eax, [rsp+4A0h+nSize]
0x18000b645  add     eax, 2
0x18000b648  add     edx, eax
0x18000b64a  mov     edi, edx
0x18000b64c  lea     r14, [rdx+rdx]
0x18000b650  call    cs:__imp_GetProcessHeap
0x18000b656  mov     r8, r14; dwBytes
0x18000b659  mov     edx, 8; dwFlags
0x18000b65e  mov     rcx, rax; hHeap
0x18000b661  call    cs:__imp_HeapAlloc
0x18000b667  mov     rsi, rax
0x18000b66a  test    rax, rax
0x18000b66d  jz      loc_18000B771
0x18000b673  mov     r8, r14; Size
0x18000b676  xor     edx, edx; Val
0x18000b678  mov     rcx, rax; void *
0x18000b67b  call    memset_0
0x18000b680  test    rdi, rdi
0x18000b683  jz      loc_18000B70D
0x18000b689  mov     ecx, 7FFFFFFFh
0x18000b68e  cmp     rdi, rcx
0x18000b691  ja      loc_18000B861
0x18000b697  mov     r8, rsi
0x18000b69a  lea     r9, [rsp+4A0h+Buffer]
0x18000b69f  mov     ecx, 7FFFFFFEh
0x18000b6a4  mov     edx, edi
0x18000b6a6  mov     rax, rsi
0x18000b6a9  test    rcx, rcx
0x18000b6ac  jz      short loc_18000B6CD
0x18000b6ae  movzx   r10d, word ptr [r9]
0x18000b6b2  test    r10w, r10w
0x18000b6b6  jz      short loc_18000B6CD
0x18000b6b8  mov     [rax], r10w
0x18000b6bc  add     r9, 2
0x18000b6c0  add     rax, 2
0x18000b6c4  dec     rcx
0x18000b6c7  sub     rdx, 1
0x18000b6cb  jnz     short loc_18000B6A9
0x18000b6cd  test    rdx, rdx
0x18000b6d0  lea     rcx, [rax-2]
0x18000b6d4  mov     r10, rdi
0x18000b6d7  mov     rdx, rdi
0x18000b6da  cmovnz  rcx, rax
0x18000b6de  mov     [rcx], r15w
0x18000b6e2  cmp     [r8], r15w
0x18000b6e6  jz      short loc_18000B6F2
0x18000b6e8  add     r8, 2
0x18000b6ec  sub     rdx, 1
0x18000b6f0  jnz     short loc_18000B6E2
0x18000b6f2  mov     rcx, r10
0x18000b6f5  mov     rax, rdx
0x18000b6f8  sub     rcx, rdx
0x18000b6fb  neg     rax
0x18000b6fe  sbb     r8, r8
0x18000b701  and     r8, rcx; pcchNewDestLength
0x18000b704  test    rdx, rdx
0x18000b707  jnz     loc_18000B86A
0x18000b70d  mov     r8, cs:?DnsICSDomainSuffix@@3PEAGEA; unsigned __int16 *
0x18000b714  mov     rdx, rdi; unsigned __int64
0x18000b717  mov     rcx, rsi; unsigned __int16 *
0x18000b71a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b71f  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b726  call    cs:__imp_LeaveCriticalSection
0x18000b72c  lea     rcx, [rsp+4A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000b731  call    cs:__imp_GetSystemTimeAsFileTime
0x18000b737  mov     r8, qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime]
0x18000b73c  mov     rax, 59A175BE1C000h
0x18000b746  add     r8, rax; struct _FILETIME
0x18000b749  mov     edx, ebx; unsigned int
0x18000b74b  mov     rcx, rsi; unsigned __int16 *
0x18000b74e  mov     qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime], r8
0x18000b753  call    ?DnsAddAddressForName@@YAXPEAGKU_FILETIME@@@Z; DnsAddAddressForName(ushort *,ulong,_FILETIME)
0x18000b758  call    cs:__imp_GetProcessHeap
0x18000b75e  mov     r8, rsi; lpMem
0x18000b761  xor     edx, edx; dwFlags
0x18000b763  mov     rcx, rax; hHeap
0x18000b766  call    cs:__imp_HeapFree
0x18000b76c  jmp     loc_18000B5C4
0x18000b771  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b778  call    cs:__imp_LeaveCriticalSection
0x18000b77e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b785  cmp     rcx, r13
0x18000b788  jz      loc_18000B5D4
0x18000b78e  test    byte ptr [rcx+1Ch], 10h
0x18000b792  jz      loc_18000B5D4
0x18000b798  cmp     byte ptr [rcx+19h], 2
0x18000b79c  jb      loc_18000B5D4
0x18000b7a2  mov     edx, 3Dh ; '='
0x18000b7a7  jmp     loc_18000B8DC
0x18000b7ac  test    byte ptr [rcx+1Ch], 10h
0x18000b7b0  jz      loc_18000B55A
0x18000b7b6  cmp     byte ptr [rcx+19h], 6
0x18000b7ba  jb      loc_18000B55A
0x18000b7c0  mov     rcx, [rcx+10h]
0x18000b7c4  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18000b7cb  mov     edx, 3Bh ; ';'
0x18000b7d0  call    WPP_SF_
0x18000b7d5  jmp     loc_18000B55A
0x18000b7da  mov     qword ptr [rsp+4A0h+var_458], r15
0x18000b7df  call    cs:__imp_GetLastError
0x18000b7e5  mov     [rsp+4A0h+Arguments], r15; Arguments
0x18000b7ea  mov     r9d, ebx; dwLanguageId
0x18000b7ed  mov     r8d, eax; dwMessageId
0x18000b7f0  mov     [rsp+4A0h+var_478], r15d; nSize
0x18000b7f5  lea     rax, [rsp+4A0h+var_458]
0x18000b7fa  xor     edx, edx; lpSource
0x18000b7fc  mov     ecx, 1300h; dwFlags
0x18000b801  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x18000b806  call    cs:__imp_FormatMessageW
0x18000b80c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b813  cmp     rcx, r13
0x18000b816  jz      short loc_18000B845
0x18000b818  test    byte ptr [rcx+1Ch], 10h
0x18000b81c  jz      short loc_18000B845
0x18000b81e  cmp     byte ptr [rcx+19h], 2
0x18000b822  jb      short loc_18000B845
0x18000b824  mov     r9, qword ptr [rsp+4A0h+var_458]
0x18000b829  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18000b830  mov     rcx, [rcx+10h]
0x18000b834  mov     edx, 3Ch ; '<'
0x18000b839  call    WPP_SF_S
0x18000b83e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b845  mov     rax, qword ptr [rsp+4A0h+var_458]
0x18000b84a  test    rax, rax
0x18000b84d  jz      loc_18000B5CB
0x18000b853  mov     rcx, rax; hMem
0x18000b856  call    cs:__imp_LocalFree
0x18000b85c  jmp     loc_18000B5C4
0x18000b861  mov     [rsi], r15w
0x18000b865  jmp     loc_18000B70D
0x18000b86a  sub     r10, r8
0x18000b86d  lea     rcx, [rsi+r8*2]; pszDest
0x18000b871  mov     rdx, r10; cchDest
0x18000b874  lea     r9, asc_180096884; "."
0x18000b87b  call    StringCopyWorkerW
0x18000b880  jmp     loc_18000B70D
0x18000b885  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b88c  cmp     rcx, r13
0x18000b88f  jz      loc_18000B5D4
0x18000b895  test    byte ptr [rcx+1Ch], 10h
0x18000b899  jz      loc_18000B5CB
0x18000b89f  cmp     byte ptr [rcx+19h], 2
0x18000b8a3  jb      loc_18000B5CB
0x18000b8a9  mov     rcx, [rcx+10h]
0x18000b8ad  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18000b8b4  mov     edx, 3Eh ; '>'
0x18000b8b9  call    WPP_SF_
0x18000b8be  jmp     loc_18000B5C4
0x18000b8c3  test    byte ptr [rcx+1Ch], 10h
0x18000b8c7  jz      loc_18000B5D4
0x18000b8cd  cmp     byte ptr [rcx+19h], 6
0x18000b8d1  jb      loc_18000B5D4
0x18000b8d7  mov     edx, 3Fh ; '?'
0x18000b8dc  mov     rcx, [rcx+10h]
0x18000b8e0  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18000b8e7  call    WPP_SF_
0x18000b8ec  jmp     loc_18000B5D4
```
