# PuGetDiskIdentifiers(void *,ushort const *,ushort * *,ushort *)

- ea: `0x1801a17c0`
- end: `0x1801a1b5b`
- name: `?PuGetDiskIdentifiers@@YAJPEAXPEBGPEAPEAGPEAG@Z`
- size: `923`
- prototype: `__int64 __fastcall(HANDLE hDevice, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1801a1fac`

## callees

- `0x180006350`
- `0x180006dd4`
- `0x18000cdb0`
- `0x1800298d0`
- `0x1800c87b4`
- `0x1801a17c0`
- `0x1801a5e74`
- `0x1801a9f34`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801a19e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801a1a46`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801a19e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801a1a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a19b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a19b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1840`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1931`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a19f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1a5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1ac9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1ae2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1afe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1b1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1840`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1931`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a19f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1a5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1ac9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1ae2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1afe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1b1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a1863`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a194e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a1a12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a1a83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a1863`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a194e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a1a12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a1a83`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801a1978`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801a1978`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a18b9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a18b9`

## pseudocode

```c
__int64 __fastcall PuGetDiskIdentifiers(
        HANDLE hDevice,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 *a4)
{
  void *lpOutBuffer; // rdi
  CHAR *v5; // r14
  WCHAR *v6; // rsi
  DWORD nOutBufferSize; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int v11; // edx
  HANDLE v12; // rax
  void *v13; // rax
  unsigned __int64 v14; // rdx
  const char *v15; // rax
  unsigned __int64 v17; // rbx
  HANDLE v18; // rax
  WCHAR *v19; // rax
  unsigned __int16 *v20; // r15
  unsigned int v21; // ebx
  unsigned __int16 *v22; // rcx
  __int64 v23; // rsi
  HANDLE v24; // rax
  WCHAR *v25; // rax
  __int64 v26; // r15
  HANDLE v27; // rax
  unsigned __int64 v28; // r12
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // r15
  unsigned __int16 *v31; // rcx
  HANDLE v32; // rax
  unsigned int v33; // edx
  HANDLE v34; // rax
  unsigned int v35; // edx
  HANDLE v36; // rax
  unsigned int v37; // edx
  HANDLE v38; // rax
  unsigned int v39; // edx
  unsigned __int16 v40[2]; // [rsp+40h] [rbp-39h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-35h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 v43; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int64 v44; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int16 **v45; // [rsp+60h] [rbp-19h]
  unsigned __int16 *v46; // [rsp+68h] [rbp-11h]
  __int64 InBuffer; // [rsp+78h] [rbp-1h] BYREF
  int v48; // [rsp+80h] [rbp+7h]

  v46 = a4;
  lpOutBuffer = 0;
  v45 = a3;
  v5 = 0;
  BytesReturned = 0;
  v6 = 0;
  InBuffer = 0;
  v48 = 0;
  LODWORD(v43) = 0;
  v40[0] = 0;
  nOutBufferSize = 8;
  nSize = 0;
  v44 = 0;
  while ( 1 )
  {
    if ( lpOutBuffer )
    {
      ProcessHeap = GetProcessHeap();
      PmHeapFree(ProcessHeap, v11, lpOutBuffer);
    }
    v12 = GetProcessHeap();
    if ( !v12 )
      return (unsigned int)-2147024882;
    v13 = HeapAlloc(v12, 8u, nOutBufferSize);
    lpOutBuffer = v13;
    if ( !v13 )
      return (unsigned int)-2147024882;
    memset_0(v13, 0, nOutBufferSize);
    InBuffer = 2;
    if ( !DeviceIoControl(hDevice, 0x2D1400u, &InBuffer, 0xCu, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
    {
      GetLastError();
      goto LABEL_20;
    }
    if ( nOutBufferSize >= *((_DWORD *)lpOutBuffer + 1) )
      break;
    nOutBufferSize = *((_DWORD *)lpOutBuffer + 1);
  }
  if ( BytesReturned >= 0x10 && BytesReturned == *((_DWORD *)lpOutBuffer + 1) )
  {
    v15 = (const char *)PuParseDeviceID((unsigned __int8 *)lpOutBuffer + 12, v14, *((_DWORD *)lpOutBuffer + 2), v40);
    v5 = (CHAR *)v15;
    if ( v15 )
    {
      v43 = 0;
      if ( (int)StringCchLengthA(v15, v14, &v43) < 0 )
        return 2147942487LL;
      v17 = v43 + 1;
      v18 = GetProcessHeap();
      if ( !v18 )
        return 2147942414LL;
      v19 = (WCHAR *)HeapAlloc(v18, 8u, 2 * v17);
      v20 = v19;
      if ( !v19 )
        return 2147942414LL;
      MultiByteToWideChar(0, 1u, v5, v17, v19, v17);
      v21 = 0;
      v22 = v46;
      *v45 = v20;
      *v22 = v40[0];
      goto LABEL_32;
    }
    LODWORD(v43) = v40[0];
  }
LABEL_20:
  v21 = 0;
  if ( !a2 )
  {
    v21 = -2147220965;
    goto LABEL_32;
  }
  StringCchLengthW(a2, v14, &v44);
  GetComputerNameExW(ComputerNameDnsHostname, 0, &nSize);
  v23 = nSize;
  v24 = GetProcessHeap();
  if ( !v24 )
  {
    v6 = 0;
LABEL_25:
    v21 = -2147024882;
    goto LABEL_32;
  }
  v25 = (WCHAR *)HeapAlloc(v24, 8u, 2 * v23);
  v6 = v25;
  if ( !v25 )
    goto LABEL_25;
  if ( nSize && GetComputerNameExW(ComputerNameDnsHostname, v25, &nSize) )
  {
    v26 = nSize;
    v27 = GetProcessHeap();
    if ( !v27 )
      goto LABEL_25;
    v28 = v44;
    v29 = (unsigned __int16 *)HeapAlloc(v27, 8u, 2 * (v44 + v26) + 6);
    v30 = v29;
    if ( !v29 )
      goto LABEL_25;
    StringCchPrintfW(v29, v28 + nSize + 3LL, L"%s:%s", a2, v6);
    v31 = v46;
    *v45 = v30;
    *v31 = v43;
  }
  v32 = GetProcessHeap();
  PmHeapFree(v32, v33, v6);
  v6 = 0;
LABEL_32:
  v34 = GetProcessHeap();
  PmHeapFree(v34, v35, lpOutBuffer);
  if ( v5 )
  {
    v36 = GetProcessHeap();
    PmHeapFree(v36, v37, v5);
  }
  if ( v6 )
  {
    v38 = GetProcessHeap();
    PmHeapFree(v38, v39, v6);
  }
  return v21;
}

```

## disassembly

```asm
0x1801a17c0  push    rbp
0x1801a17c2  push    rbx
0x1801a17c3  push    rsi
0x1801a17c4  push    rdi
0x1801a17c5  push    r12
0x1801a17c7  push    r13
0x1801a17c9  push    r14
0x1801a17cb  push    r15
0x1801a17cd  lea     rbp, [rsp-1Fh]
0x1801a17d2  sub     rsp, 98h
0x1801a17d9  mov     rax, cs:__security_cookie
0x1801a17e0  xor     rax, rsp
0x1801a17e3  mov     [rbp+57h+var_48], rax
0x1801a17e7  xor     eax, eax
0x1801a17e9  mov     [rbp+57h+var_68], r9
0x1801a17ed  xor     edi, edi
0x1801a17ef  mov     [rbp+57h+var_70], r8
0x1801a17f3  xor     r14d, r14d
0x1801a17f6  mov     [rbp+57h+BytesReturned], 0
0x1801a17fd  xor     esi, esi
0x1801a17ff  mov     [rbp+57h+InBuffer], rax
0x1801a1803  xor     r12d, r12d
0x1801a1806  mov     [rbp+57h+var_50], eax
0x1801a1809  mov     dword ptr [rbp+57h+var_80], r12d
0x1801a180d  mov     r13, rdx
0x1801a1810  mov     [rbp+57h+var_90], r12w
0x1801a1815  mov     ebx, 8
0x1801a181a  mov     r12, rcx
0x1801a181d  mov     [rbp+57h+nSize], eax
0x1801a1820  mov     [rbp+57h+var_78], rax
0x1801a1824  test    rdi, rdi
0x1801a1827  jz      short loc_1801A1840
0x1801a1829  call    cs:__imp_GetProcessHeap
0x1801a1830  nop     dword ptr [rax+rax+00h]
0x1801a1835  mov     rcx, rax; void *
0x1801a1838  mov     r8, rdi; void *
0x1801a183b  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a1840  call    cs:__imp_GetProcessHeap
0x1801a1847  nop     dword ptr [rax+rax+00h]
0x1801a184c  test    rax, rax
0x1801a184f  jz      loc_1801A1B33
0x1801a1855  mov     r8d, ebx; dwBytes
0x1801a1858  mov     edx, 8; dwFlags
0x1801a185d  mov     rcx, rax; hHeap
0x1801a1860  mov     r15d, ebx
0x1801a1863  call    cs:__imp_HeapAlloc
0x1801a186a  nop     dword ptr [rax+rax+00h]
0x1801a186f  mov     rdi, rax
0x1801a1872  test    rax, rax
0x1801a1875  jz      loc_1801A1B33
0x1801a187b  mov     r8d, r15d; Size
0x1801a187e  xor     edx, edx; Val
0x1801a1880  mov     rcx, rax; void *
0x1801a1883  call    memset_0
0x1801a1888  mov     [rsp+0D0h+lpOverlapped], rsi; lpOverlapped
0x1801a188d  lea     rax, [rbp+57h+BytesReturned]
0x1801a1891  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x1801a1896  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1801a189a  mov     [rsp+0D0h+nOutBufferSize], ebx; nOutBufferSize
0x1801a189e  mov     r9d, 0Ch; nInBufferSize
0x1801a18a4  mov     edx, 2D1400h; dwIoControlCode
0x1801a18a9  mov     [rsp+0D0h+lpOutBuffer], rdi; lpOutBuffer
0x1801a18ae  mov     rcx, r12; hDevice
0x1801a18b1  mov     [rbp+57h+InBuffer], 2
0x1801a18b9  call    cs:__imp_DeviceIoControl
0x1801a18c0  nop     dword ptr [rax+rax+00h]
0x1801a18c5  test    eax, eax
0x1801a18c7  jz      loc_1801A19B0
0x1801a18cd  cmp     ebx, [rdi+4]
0x1801a18d0  jnb     short loc_1801A18DA
0x1801a18d2  mov     ebx, [rdi+4]
0x1801a18d5  jmp     loc_1801A1824
0x1801a18da  mov     eax, [rbp+57h+BytesReturned]
0x1801a18dd  cmp     eax, 10h
0x1801a18e0  jb      loc_1801A19BC
0x1801a18e6  cmp     eax, [rdi+4]
0x1801a18e9  jnz     loc_1801A19BC
0x1801a18ef  mov     r8d, [rdi+8]; unsigned int
0x1801a18f3  lea     rcx, [rdi+0Ch]; unsigned __int8 *
0x1801a18f7  lea     r9, [rbp+57h+var_90]; unsigned __int16 *
0x1801a18fb  call    ?PuParseDeviceID@@YAPEAEPEAEKKPEAG@Z; PuParseDeviceID(uchar *,ulong,ulong,ushort *)
0x1801a1900  mov     r14, rax
0x1801a1903  test    rax, rax
0x1801a1906  jz      loc_1801A19A7
0x1801a190c  lea     r8, [rbp+57h+var_80]; unsigned __int64 *
0x1801a1910  mov     [rbp+57h+var_80], rsi
0x1801a1914  mov     rcx, rax; char *
0x1801a1917  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801a191c  test    eax, eax
0x1801a191e  jns     short loc_1801A192A
0x1801a1920  mov     eax, 80070057h
0x1801a1925  jmp     loc_1801A1B3A
0x1801a192a  mov     rbx, [rbp+57h+var_80]
0x1801a192e  inc     rbx
0x1801a1931  call    cs:__imp_GetProcessHeap
0x1801a1938  nop     dword ptr [rax+rax+00h]
0x1801a193d  test    rax, rax
0x1801a1940  jz      short loc_1801A199D
0x1801a1942  lea     r8, [rbx+rbx]; dwBytes
0x1801a1946  mov     edx, 8; dwFlags
0x1801a194b  mov     rcx, rax; hHeap
0x1801a194e  call    cs:__imp_HeapAlloc
0x1801a1955  nop     dword ptr [rax+rax+00h]
0x1801a195a  mov     r15, rax
0x1801a195d  test    rax, rax
0x1801a1960  jz      short loc_1801A199D
0x1801a1962  mov     [rsp+0D0h+nOutBufferSize], ebx; cchWideChar
0x1801a1966  mov     r9d, ebx; cbMultiByte
0x1801a1969  mov     r8, r14; lpMultiByteStr
0x1801a196c  mov     [rsp+0D0h+lpOutBuffer], rax; lpWideCharStr
0x1801a1971  mov     edx, 1; dwFlags
0x1801a1976  xor     ecx, ecx; CodePage
0x1801a1978  call    cs:__imp_MultiByteToWideChar
0x1801a197f  nop     dword ptr [rax+rax+00h]
0x1801a1984  mov     rax, [rbp+57h+var_70]
0x1801a1988  xor     ebx, ebx
0x1801a198a  mov     rcx, [rbp+57h+var_68]
0x1801a198e  mov     [rax], r15
0x1801a1991  movzx   eax, [rbp+57h+var_90]
0x1801a1995  mov     [rcx], ax
0x1801a1998  jmp     loc_1801A1AE2
0x1801a199d  mov     eax, 8007000Eh
0x1801a19a2  jmp     loc_1801A1B3A
0x1801a19a7  movzx   eax, [rbp+57h+var_90]
0x1801a19ab  mov     dword ptr [rbp+57h+var_80], eax
0x1801a19ae  jmp     short loc_1801A19BC
0x1801a19b0  call    cs:__imp_GetLastError
0x1801a19b7  nop     dword ptr [rax+rax+00h]
0x1801a19bc  xor     ebx, ebx
0x1801a19be  test    r13, r13
0x1801a19c1  jnz     short loc_1801A19CD
0x1801a19c3  mov     ebx, 8004021Bh
0x1801a19c8  jmp     loc_1801A1AE2
0x1801a19cd  lea     r8, [rbp+57h+var_78]; unsigned __int64 *
0x1801a19d1  mov     rcx, r13; unsigned __int16 *
0x1801a19d4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801a19d9  xor     edx, edx; lpBuffer
0x1801a19db  lea     r8, [rbp+57h+nSize]; nSize
0x1801a19df  lea     ecx, [rdx+1]; NameType
0x1801a19e2  call    cs:__imp_GetComputerNameExW
0x1801a19e9  nop     dword ptr [rax+rax+00h]
0x1801a19ee  mov     esi, [rbp+57h+nSize]
0x1801a19f1  call    cs:__imp_GetProcessHeap
0x1801a19f8  nop     dword ptr [rax+rax+00h]
0x1801a19fd  test    rax, rax
0x1801a1a00  jnz     short loc_1801A1A06
0x1801a1a02  xor     esi, esi
0x1801a1a04  jmp     short loc_1801A1A26
0x1801a1a06  lea     r8, [rsi+rsi]; dwBytes
0x1801a1a0a  mov     edx, 8; dwFlags
0x1801a1a0f  mov     rcx, rax; hHeap
0x1801a1a12  call    cs:__imp_HeapAlloc
0x1801a1a19  nop     dword ptr [rax+rax+00h]
0x1801a1a1e  mov     rsi, rax
0x1801a1a21  test    rax, rax
0x1801a1a24  jnz     short loc_1801A1A30
0x1801a1a26  mov     ebx, 8007000Eh
0x1801a1a2b  jmp     loc_1801A1AE2
0x1801a1a30  cmp     [rbp+57h+nSize], 0
0x1801a1a34  jz      loc_1801A1AC9
0x1801a1a3a  lea     r8, [rbp+57h+nSize]; nSize
0x1801a1a3e  mov     rdx, rsi; lpBuffer
0x1801a1a41  mov     ecx, 1; NameType
0x1801a1a46  call    cs:__imp_GetComputerNameExW
0x1801a1a4d  nop     dword ptr [rax+rax+00h]
0x1801a1a52  test    eax, eax
0x1801a1a54  jz      short loc_1801A1AC9
0x1801a1a56  mov     r15d, [rbp+57h+nSize]
0x1801a1a5a  call    cs:__imp_GetProcessHeap
0x1801a1a61  nop     dword ptr [rax+rax+00h]
0x1801a1a66  test    rax, rax
0x1801a1a69  jz      short loc_1801A1A26
0x1801a1a6b  mov     r12, [rbp+57h+var_78]
0x1801a1a6f  mov     edx, 8; dwFlags
0x1801a1a74  mov     rcx, rax; hHeap
0x1801a1a77  lea     r8, [r12+r15]
0x1801a1a7b  lea     r8, ds:6[r8*2]; dwBytes
0x1801a1a83  call    cs:__imp_HeapAlloc
0x1801a1a8a  nop     dword ptr [rax+rax+00h]
0x1801a1a8f  mov     r15, rax
0x1801a1a92  test    rax, rax
0x1801a1a95  jz      short loc_1801A1A26
0x1801a1a97  mov     edx, [rbp+57h+nSize]
0x1801a1a9a  lea     r8, aSS_3; "%s:%s"
0x1801a1aa1  add     rdx, 3
0x1801a1aa5  mov     [rsp+0D0h+lpOutBuffer], rsi
0x1801a1aaa  add     rdx, r12; unsigned __int64
0x1801a1aad  mov     r9, r13
0x1801a1ab0  mov     rcx, rax; unsigned __int16 *
0x1801a1ab3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a1ab8  mov     rax, [rbp+57h+var_70]
0x1801a1abc  mov     rcx, [rbp+57h+var_68]
0x1801a1ac0  mov     [rax], r15
0x1801a1ac3  mov     eax, dword ptr [rbp+57h+var_80]
0x1801a1ac6  mov     [rcx], ax
0x1801a1ac9  call    cs:__imp_GetProcessHeap
0x1801a1ad0  nop     dword ptr [rax+rax+00h]
0x1801a1ad5  mov     rcx, rax; void *
0x1801a1ad8  mov     r8, rsi; void *
0x1801a1adb  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a1ae0  xor     esi, esi
0x1801a1ae2  call    cs:__imp_GetProcessHeap
0x1801a1ae9  nop     dword ptr [rax+rax+00h]
0x1801a1aee  mov     rcx, rax; void *
0x1801a1af1  mov     r8, rdi; void *
0x1801a1af4  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a1af9  test    r14, r14
0x1801a1afc  jz      short loc_1801A1B15
0x1801a1afe  call    cs:__imp_GetProcessHeap
0x1801a1b05  nop     dword ptr [rax+rax+00h]
0x1801a1b0a  mov     rcx, rax; void *
0x1801a1b0d  mov     r8, r14; void *
0x1801a1b10  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a1b15  test    rsi, rsi
0x1801a1b18  jz      short loc_1801A1B38
0x1801a1b1a  call    cs:__imp_GetProcessHeap
0x1801a1b21  nop     dword ptr [rax+rax+00h]
0x1801a1b26  mov     rcx, rax; void *
0x1801a1b29  mov     r8, rsi; void *
0x1801a1b2c  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a1b31  jmp     short loc_1801A1B38
0x1801a1b33  mov     ebx, 8007000Eh
0x1801a1b38  mov     eax, ebx
0x1801a1b3a  mov     rcx, [rbp+57h+var_48]
0x1801a1b3e  xor     rcx, rsp; StackCookie
0x1801a1b41  call    __security_check_cookie
0x1801a1b46  add     rsp, 98h
0x1801a1b4d  pop     r15
0x1801a1b4f  pop     r14
0x1801a1b51  pop     r13
0x1801a1b53  pop     r12
0x1801a1b55  pop     rdi
0x1801a1b56  pop     rsi
0x1801a1b57  pop     rbx
0x1801a1b58  pop     rbp
0x1801a1b59  retn
```
