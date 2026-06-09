# DnsAddSelf(void)

- ea: `0x18000bdb4`
- end: `0x18000c1d6`
- name: `?DnsAddSelf@@YAXXZ`
- size: `1058`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000a20c`

## callees

- `0x18000843c`
- `0x18000ae7c`
- `0x18000bdb4`
- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x180013804`
- `0x180035620`
- `0x18003a66c`
- `0x180042b8c`
- `0x180051f30`
- `0x180052bf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c019`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bf10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bf10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c02d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c02d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bec9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bec9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bfdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c045`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bfdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0b2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c0df`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c0df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bfec`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bfec`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000be2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000be2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c135`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c135`

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
0x18000bdb4  push    rbp
0x18000bdb6  push    rbx
0x18000bdb7  push    rsi
0x18000bdb8  push    rdi
0x18000bdb9  push    r13
0x18000bdbb  push    r14
0x18000bdbd  push    r15
0x18000bdbf  lea     rbp, [rsp-370h]
0x18000bdc7  sub     rsp, 470h
0x18000bdce  mov     rax, cs:__security_cookie
0x18000bdd5  xor     rax, rsp
0x18000bdd8  mov     [rbp+3A0h+var_40], rax
0x18000bddf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bde6  lea     r13, WPP_GLOBAL_Control
0x18000bded  cmp     rcx, r13
0x18000bdf0  jnz     loc_18000C07F
0x18000bdf6  xor     r15d, r15d
0x18000bdf9  mov     [rsp+4A0h+nSize], 200h
0x18000be01  mov     ebx, 400h
0x18000be06  mov     qword ptr [rsp+4A0h+var_458], r15
0x18000be0b  mov     r8d, ebx; Size
0x18000be0e  mov     qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18000be13  xor     edx, edx; Val
0x18000be15  lea     rcx, [rsp+4A0h+Buffer]; void *
0x18000be1a  call    memset_0
0x18000be1f  lea     r8, [rsp+4A0h+nSize]; nSize
0x18000be24  lea     rdx, [rsp+4A0h+Buffer]; lpBuffer
0x18000be29  lea     ecx, [r15+1]; NameType
0x18000be2d  call    cs:__imp_GetComputerNameExW
0x18000be34  nop     dword ptr [rax+rax+00h]
0x18000be39  test    eax, eax
0x18000be3b  jz      loc_18000C0AD
0x18000be41  lea     rcx, ?DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x18000be48  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18000be4d  test    al, al
0x18000be4f  jnz     short loc_18000BE98
0x18000be51  call    ?DnsGetPrivateInterfaceAddress@@YAKXZ; DnsGetPrivateInterfaceAddress(void)
0x18000be56  mov     ebx, eax
0x18000be58  test    eax, eax
0x18000be5a  jnz     short loc_18000BEAF
0x18000be5c  mov     ebx, cs:?g_PrivateIPAddr@@3KA; ulong g_PrivateIPAddr
0x18000be62  test    ebx, ebx
0x18000be64  jnz     short loc_18000BEB5
0x18000be66  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be6d  cmp     rcx, r13
0x18000be70  jnz     loc_18000C1A8
0x18000be76  mov     rcx, [rbp+3A0h+var_40]
0x18000be7d  xor     rcx, rsp; StackCookie
0x18000be80  call    __security_check_cookie
0x18000be85  add     rsp, 470h
0x18000be8c  pop     r15
0x18000be8e  pop     r14
0x18000be90  pop     r13
0x18000be92  pop     rdi
0x18000be93  pop     rsi
0x18000be94  pop     rbx
0x18000be95  pop     rbp
0x18000be96  retn
0x18000be98  call    ?DhcpGetPrivateInterfaceAddress@@YAKXZ; DhcpGetPrivateInterfaceAddress(void)
0x18000be9d  lea     rcx, ?DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18000bea4  mov     ebx, eax
0x18000bea6  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000beab  test    ebx, ebx
0x18000bead  jz      short loc_18000BE51
0x18000beaf  mov     cs:?g_PrivateIPAddr@@3KA, ebx; ulong g_PrivateIPAddr
0x18000beb5  cmp     cs:?DnsICSDomainSuffix@@3PEAGEA, r15; ushort * DnsICSDomainSuffix
0x18000bebc  jz      loc_18000C16A
0x18000bec2  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000bec9  call    cs:__imp_EnterCriticalSection
0x18000bed0  nop     dword ptr [rax+rax+00h]
0x18000bed5  mov     rax, cs:?DnsICSDomainSuffix@@3PEAGEA; ushort * DnsICSDomainSuffix
0x18000bedc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000bee0  inc     rdx
0x18000bee3  cmp     [rax+rdx*2], r15w
0x18000bee8  jnz     short loc_18000BEE0
0x18000beea  mov     eax, [rsp+4A0h+nSize]
0x18000beee  add     eax, 2
0x18000bef1  add     edx, eax
0x18000bef3  mov     edi, edx
0x18000bef5  lea     r14, [rdx+rdx]
0x18000bef9  call    cs:__imp_GetProcessHeap
0x18000bf00  nop     dword ptr [rax+rax+00h]
0x18000bf05  mov     r8, r14; dwBytes
0x18000bf08  mov     edx, 8; dwFlags
0x18000bf0d  mov     rcx, rax; hHeap
0x18000bf10  call    cs:__imp_HeapAlloc
0x18000bf17  nop     dword ptr [rax+rax+00h]
0x18000bf1c  mov     rsi, rax
0x18000bf1f  test    rax, rax
0x18000bf22  jz      loc_18000C03E
0x18000bf28  mov     r8, r14; Size
0x18000bf2b  xor     edx, edx; Val
0x18000bf2d  mov     rcx, rax; void *
0x18000bf30  call    memset_0
0x18000bf35  test    rdi, rdi
0x18000bf38  jz      loc_18000BFC2
0x18000bf3e  mov     ecx, 7FFFFFFFh
0x18000bf43  cmp     rdi, rcx
0x18000bf46  ja      loc_18000C146
0x18000bf4c  mov     r8, rsi
0x18000bf4f  lea     r9, [rsp+4A0h+Buffer]
0x18000bf54  mov     ecx, 7FFFFFFEh
0x18000bf59  mov     edx, edi
0x18000bf5b  mov     rax, rsi
0x18000bf5e  test    rcx, rcx
0x18000bf61  jz      short loc_18000BF82
0x18000bf63  movzx   r10d, word ptr [r9]
0x18000bf67  test    r10w, r10w
0x18000bf6b  jz      short loc_18000BF82
0x18000bf6d  mov     [rax], r10w
0x18000bf71  add     r9, 2
0x18000bf75  add     rax, 2
0x18000bf79  dec     rcx
0x18000bf7c  sub     rdx, 1
0x18000bf80  jnz     short loc_18000BF5E
0x18000bf82  test    rdx, rdx
0x18000bf85  lea     rcx, [rax-2]
0x18000bf89  mov     r10, rdi
0x18000bf8c  mov     rdx, rdi
0x18000bf8f  cmovnz  rcx, rax
0x18000bf93  mov     [rcx], r15w
0x18000bf97  cmp     [r8], r15w
0x18000bf9b  jz      short loc_18000BFA7
0x18000bf9d  add     r8, 2
0x18000bfa1  sub     rdx, 1
0x18000bfa5  jnz     short loc_18000BF97
0x18000bfa7  mov     rcx, r10
0x18000bfaa  mov     rax, rdx
0x18000bfad  sub     rcx, rdx
0x18000bfb0  neg     rax
0x18000bfb3  sbb     r8, r8
0x18000bfb6  and     r8, rcx; pcchNewDestLength
0x18000bfb9  test    rdx, rdx
0x18000bfbc  jnz     loc_18000C14F
0x18000bfc2  mov     r8, cs:?DnsICSDomainSuffix@@3PEAGEA; unsigned __int16 *
0x18000bfc9  mov     rdx, rdi; unsigned __int64
0x18000bfcc  mov     rcx, rsi; unsigned __int16 *
0x18000bfcf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bfd4  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000bfdb  call    cs:__imp_LeaveCriticalSection
0x18000bfe2  nop     dword ptr [rax+rax+00h]
0x18000bfe7  lea     rcx, [rsp+4A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000bfec  call    cs:__imp_GetSystemTimeAsFileTime
0x18000bff3  nop     dword ptr [rax+rax+00h]
0x18000bff8  mov     r8, qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime]
0x18000bffd  mov     rax, 59A175BE1C000h
0x18000c007  add     r8, rax; struct _FILETIME
0x18000c00a  mov     edx, ebx; unsigned int
0x18000c00c  mov     rcx, rsi; unsigned __int16 *
0x18000c00f  mov     qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime], r8
0x18000c014  call    ?DnsAddAddressForName@@YAXPEAGKU_FILETIME@@@Z; DnsAddAddressForName(ushort *,ulong,_FILETIME)
0x18000c019  call    cs:__imp_GetProcessHeap
0x18000c020  nop     dword ptr [rax+rax+00h]
0x18000c025  mov     r8, rsi; lpMem
0x18000c028  xor     edx, edx; dwFlags
0x18000c02a  mov     rcx, rax; hHeap
0x18000c02d  call    cs:__imp_HeapFree
0x18000c034  nop     dword ptr [rax+rax+00h]
0x18000c039  jmp     loc_18000BE66
0x18000c03e  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c045  call    cs:__imp_LeaveCriticalSection
0x18000c04c  nop     dword ptr [rax+rax+00h]
0x18000c051  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c058  cmp     rcx, r13
0x18000c05b  jz      loc_18000BE76
0x18000c061  test    byte ptr [rcx+1Ch], 10h
0x18000c065  jz      loc_18000BE76
0x18000c06b  cmp     byte ptr [rcx+19h], 2
0x18000c06f  jb      loc_18000BE76
0x18000c075  mov     edx, 3Dh ; '='
0x18000c07a  jmp     loc_18000C1C1
0x18000c07f  test    byte ptr [rcx+1Ch], 10h
0x18000c083  jz      loc_18000BDF6
0x18000c089  cmp     byte ptr [rcx+19h], 6
0x18000c08d  jb      loc_18000BDF6
0x18000c093  mov     rcx, [rcx+10h]
0x18000c097  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18000c09e  mov     edx, 3Bh ; ';'
0x18000c0a3  call    WPP_SF_
0x18000c0a8  jmp     loc_18000BDF6
0x18000c0ad  mov     qword ptr [rsp+4A0h+var_458], r15
0x18000c0b2  call    cs:__imp_GetLastError
0x18000c0b9  nop     dword ptr [rax+rax+00h]
0x18000c0be  mov     [rsp+4A0h+Arguments], r15; Arguments
0x18000c0c3  mov     r9d, ebx; dwLanguageId
0x18000c0c6  mov     r8d, eax; dwMessageId
0x18000c0c9  mov     [rsp+4A0h+var_478], r15d; nSize
0x18000c0ce  lea     rax, [rsp+4A0h+var_458]
0x18000c0d3  xor     edx, edx; lpSource
0x18000c0d5  mov     ecx, 1300h; dwFlags
0x18000c0da  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x18000c0df  call    cs:__imp_FormatMessageW
0x18000c0e6  nop     dword ptr [rax+rax+00h]
0x18000c0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0f2  cmp     rcx, r13
0x18000c0f5  jz      short loc_18000C124
0x18000c0f7  test    byte ptr [rcx+1Ch], 10h
0x18000c0fb  jz      short loc_18000C124
0x18000c0fd  cmp     byte ptr [rcx+19h], 2
0x18000c101  jb      short loc_18000C124
0x18000c103  mov     r9, qword ptr [rsp+4A0h+var_458]
0x18000c108  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18000c10f  mov     rcx, [rcx+10h]
0x18000c113  mov     edx, 3Ch ; '<'
0x18000c118  call    WPP_SF_S
0x18000c11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c124  mov     rax, qword ptr [rsp+4A0h+var_458]
0x18000c129  test    rax, rax
0x18000c12c  jz      loc_18000BE6D
0x18000c132  mov     rcx, rax; hMem
0x18000c135  call    cs:__imp_LocalFree
0x18000c13c  nop     dword ptr [rax+rax+00h]
0x18000c141  jmp     loc_18000BE66
0x18000c146  mov     [rsi], r15w
0x18000c14a  jmp     loc_18000BFC2
0x18000c14f  sub     r10, r8
0x18000c152  lea     rcx, [rsi+r8*2]; pszDest
0x18000c156  mov     rdx, r10; cchDest
0x18000c159  lea     r9, asc_18009D884; "."
0x18000c160  call    StringCopyWorkerW
0x18000c165  jmp     loc_18000BFC2
0x18000c16a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c171  cmp     rcx, r13
0x18000c174  jz      loc_18000BE76
0x18000c17a  test    byte ptr [rcx+1Ch], 10h
0x18000c17e  jz      loc_18000BE6D
0x18000c184  cmp     byte ptr [rcx+19h], 2
0x18000c188  jb      loc_18000BE6D
0x18000c18e  mov     rcx, [rcx+10h]
0x18000c192  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18000c199  mov     edx, 3Eh ; '>'
0x18000c19e  call    WPP_SF_
0x18000c1a3  jmp     loc_18000BE66
0x18000c1a8  test    byte ptr [rcx+1Ch], 10h
0x18000c1ac  jz      loc_18000BE76
0x18000c1b2  cmp     byte ptr [rcx+19h], 6
0x18000c1b6  jb      loc_18000BE76
0x18000c1bc  mov     edx, 3Fh ; '?'
0x18000c1c1  mov     rcx, [rcx+10h]
0x18000c1c5  lea     r8, WPP_55848c2aecbd3eaa7f2e1736bce6fd1b_Traceguids
0x18000c1cc  call    WPP_SF_
0x18000c1d1  jmp     loc_18000BE76
```
