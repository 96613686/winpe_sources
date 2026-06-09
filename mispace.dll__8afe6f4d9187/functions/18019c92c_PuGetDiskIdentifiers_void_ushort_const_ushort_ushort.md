# PuGetDiskIdentifiers(void *,ushort const *,ushort * *,ushort *)

- ea: `0x18019c92c`
- end: `0x18019cc7e`
- name: `?PuGetDiskIdentifiers@@YAJPEAXPEBGPEAPEAGPEAG@Z`
- size: `850`
- prototype: `__int64 __fastcall(HANDLE hDevice, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18019d09c`

## callees

- `0x180006290`
- `0x180006cf4`
- `0x18000ce3c`
- `0x1800c5770`
- `0x18019c92c`
- `0x1801a0cbc`
- `0x1801a49e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18019cb26`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18019cb74`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18019cb26`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18019cb74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019cafa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019cafa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019c9a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019cbf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019cc13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019cc31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019cc4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019c9a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019cbf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019cc13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019cc31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019cc4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c995`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c9ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ca8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cb2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cb82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cbe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cc00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cc1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cc3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c995`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c9ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ca8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cb2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cb82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cbe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cc00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cc1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019cc3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019c9cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019caa4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019cb4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019cba5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019c9cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019caa4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019cb4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019cba5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18019cac8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18019cac8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019ca1b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019ca1b`

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
  HANDLE v11; // rax
  void *v12; // rax
  unsigned __int64 v13; // rdx
  const char *v14; // rax
  unsigned __int64 v16; // rbx
  HANDLE v17; // rax
  WCHAR *v18; // rax
  unsigned __int16 *v19; // r15
  unsigned int v20; // ebx
  unsigned __int16 *v21; // rcx
  __int64 v22; // rsi
  HANDLE v23; // rax
  WCHAR *v24; // rax
  __int64 v25; // r15
  HANDLE v26; // rax
  unsigned __int64 v27; // r12
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // r15
  unsigned __int16 *v30; // rcx
  HANDLE v31; // rax
  HANDLE v32; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  unsigned __int16 v35[2]; // [rsp+40h] [rbp-39h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-35h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 v38; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int64 v39; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int16 **v40; // [rsp+60h] [rbp-19h]
  unsigned __int16 *v41; // [rsp+68h] [rbp-11h]
  __int64 InBuffer; // [rsp+78h] [rbp-1h] BYREF
  int v43; // [rsp+80h] [rbp+7h]

  v41 = a4;
  lpOutBuffer = 0;
  v40 = a3;
  v5 = 0;
  BytesReturned = 0;
  v6 = 0;
  InBuffer = 0;
  v43 = 0;
  LODWORD(v38) = 0;
  v35[0] = 0;
  nOutBufferSize = 8;
  nSize = 0;
  v39 = 0;
  while ( 1 )
  {
    if ( lpOutBuffer )
    {
      ProcessHeap = GetProcessHeap();
      if ( ProcessHeap )
        HeapFree(ProcessHeap, 0, lpOutBuffer);
    }
    v11 = GetProcessHeap();
    if ( !v11 )
      return (unsigned int)-2147024882;
    v12 = HeapAlloc(v11, 8u, nOutBufferSize);
    lpOutBuffer = v12;
    if ( !v12 )
      return (unsigned int)-2147024882;
    memset_0(v12, 0, nOutBufferSize);
    InBuffer = 2;
    if ( !DeviceIoControl(hDevice, 0x2D1400u, &InBuffer, 0xCu, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
    {
      GetLastError();
      goto LABEL_21;
    }
    if ( nOutBufferSize >= *((_DWORD *)lpOutBuffer + 1) )
      break;
    nOutBufferSize = *((_DWORD *)lpOutBuffer + 1);
  }
  if ( BytesReturned >= 0x10 && BytesReturned == *((_DWORD *)lpOutBuffer + 1) )
  {
    v14 = (const char *)PuParseDeviceID((unsigned __int8 *)lpOutBuffer + 12, v13, *((_DWORD *)lpOutBuffer + 2), v35);
    v5 = (CHAR *)v14;
    if ( v14 )
    {
      v38 = 0;
      if ( (int)StringCchLengthA(v14, v13, &v38) < 0 )
        return 2147942487LL;
      v16 = v38 + 1;
      v17 = GetProcessHeap();
      if ( !v17 )
        return 2147942414LL;
      v18 = (WCHAR *)HeapAlloc(v17, 8u, 2 * v16);
      v19 = v18;
      if ( !v18 )
        return 2147942414LL;
      MultiByteToWideChar(0, 1u, v5, v16, v18, v16);
      v20 = 0;
      v21 = v41;
      *v40 = v19;
      *v21 = v35[0];
      goto LABEL_35;
    }
    LODWORD(v38) = v35[0];
  }
LABEL_21:
  v20 = 0;
  if ( !a2 )
  {
    v20 = -2147220965;
    goto LABEL_35;
  }
  StringCchLengthW(a2, v13, &v39);
  GetComputerNameExW(ComputerNameDnsHostname, 0, &nSize);
  v22 = nSize;
  v23 = GetProcessHeap();
  if ( !v23 )
  {
    v6 = 0;
LABEL_26:
    v20 = -2147024882;
    goto LABEL_35;
  }
  v24 = (WCHAR *)HeapAlloc(v23, 8u, 2 * v22);
  v6 = v24;
  if ( !v24 )
    goto LABEL_26;
  if ( nSize && GetComputerNameExW(ComputerNameDnsHostname, v24, &nSize) )
  {
    v25 = nSize;
    v26 = GetProcessHeap();
    if ( !v26 )
      goto LABEL_26;
    v27 = v39;
    v28 = (unsigned __int16 *)HeapAlloc(v26, 8u, 2 * (v39 + v25) + 6);
    v29 = v28;
    if ( !v28 )
      goto LABEL_26;
    StringCchPrintfW(v28, v27 + nSize + 3LL, L"%s:%s", a2, v6);
    v30 = v41;
    *v40 = v29;
    *v30 = v38;
  }
  v31 = GetProcessHeap();
  if ( v31 )
    HeapFree(v31, 0, v6);
  v6 = 0;
LABEL_35:
  v32 = GetProcessHeap();
  if ( v32 )
    HeapFree(v32, 0, lpOutBuffer);
  if ( v5 )
  {
    v33 = GetProcessHeap();
    if ( v33 )
      HeapFree(v33, 0, v5);
  }
  if ( v6 )
  {
    v34 = GetProcessHeap();
    if ( v34 )
      HeapFree(v34, 0, v6);
  }
  return v20;
}

```

## disassembly

```asm
0x18019c92c  push    rbp
0x18019c92e  push    rbx
0x18019c92f  push    rsi
0x18019c930  push    rdi
0x18019c931  push    r12
0x18019c933  push    r13
0x18019c935  push    r14
0x18019c937  push    r15
0x18019c939  lea     rbp, [rsp-1Fh]
0x18019c93e  sub     rsp, 98h
0x18019c945  mov     rax, cs:__security_cookie
0x18019c94c  xor     rax, rsp
0x18019c94f  mov     [rbp+57h+var_48], rax
0x18019c953  xor     eax, eax
0x18019c955  mov     [rbp+57h+var_68], r9
0x18019c959  xor     edi, edi
0x18019c95b  mov     [rbp+57h+var_70], r8
0x18019c95f  xor     r14d, r14d
0x18019c962  mov     [rbp+57h+BytesReturned], 0
0x18019c969  xor     esi, esi
0x18019c96b  mov     [rbp+57h+InBuffer], rax
0x18019c96f  xor     r12d, r12d
0x18019c972  mov     [rbp+57h+var_50], eax
0x18019c975  mov     dword ptr [rbp+57h+var_80], r12d
0x18019c979  mov     r13, rdx
0x18019c97c  mov     [rbp+57h+var_90], r12w
0x18019c981  mov     ebx, 8
0x18019c986  mov     r12, rcx
0x18019c989  mov     [rbp+57h+nSize], eax
0x18019c98c  mov     [rbp+57h+var_78], rax
0x18019c990  test    rdi, rdi
0x18019c993  jz      short loc_18019C9AE
0x18019c995  call    cs:__imp_GetProcessHeap
0x18019c99b  test    rax, rax
0x18019c99e  jz      short loc_18019C9AE
0x18019c9a0  mov     r8, rdi; lpMem
0x18019c9a3  xor     edx, edx; dwFlags
0x18019c9a5  mov     rcx, rax; hHeap
0x18019c9a8  call    cs:__imp_HeapFree
0x18019c9ae  call    cs:__imp_GetProcessHeap
0x18019c9b4  test    rax, rax
0x18019c9b7  jz      loc_18019CC57
0x18019c9bd  mov     r8d, ebx; dwBytes
0x18019c9c0  mov     edx, 8; dwFlags
0x18019c9c5  mov     rcx, rax; hHeap
0x18019c9c8  mov     r15d, ebx
0x18019c9cb  call    cs:__imp_HeapAlloc
0x18019c9d1  mov     rdi, rax
0x18019c9d4  test    rax, rax
0x18019c9d7  jz      loc_18019CC57
0x18019c9dd  mov     r8d, r15d; Size
0x18019c9e0  xor     edx, edx; Val
0x18019c9e2  mov     rcx, rax; void *
0x18019c9e5  call    memset_0
0x18019c9ea  mov     [rsp+0D0h+lpOverlapped], rsi; lpOverlapped
0x18019c9ef  lea     rax, [rbp+57h+BytesReturned]
0x18019c9f3  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x18019c9f8  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18019c9fc  mov     [rsp+0D0h+nOutBufferSize], ebx; nOutBufferSize
0x18019ca00  mov     r9d, 0Ch; nInBufferSize
0x18019ca06  mov     edx, 2D1400h; dwIoControlCode
0x18019ca0b  mov     [rsp+0D0h+lpOutBuffer], rdi; lpOutBuffer
0x18019ca10  mov     rcx, r12; hDevice
0x18019ca13  mov     [rbp+57h+InBuffer], 2
0x18019ca1b  call    cs:__imp_DeviceIoControl
0x18019ca21  test    eax, eax
0x18019ca23  jz      loc_18019CAFA
0x18019ca29  cmp     ebx, [rdi+4]
0x18019ca2c  jnb     short loc_18019CA36
0x18019ca2e  mov     ebx, [rdi+4]
0x18019ca31  jmp     loc_18019C990
0x18019ca36  mov     eax, [rbp+57h+BytesReturned]
0x18019ca39  cmp     eax, 10h
0x18019ca3c  jb      loc_18019CB00
0x18019ca42  cmp     eax, [rdi+4]
0x18019ca45  jnz     loc_18019CB00
0x18019ca4b  mov     r8d, [rdi+8]; unsigned int
0x18019ca4f  lea     rcx, [rdi+0Ch]; unsigned __int8 *
0x18019ca53  lea     r9, [rbp+57h+var_90]; unsigned __int16 *
0x18019ca57  call    ?PuParseDeviceID@@YAPEAEPEAEKKPEAG@Z; PuParseDeviceID(uchar *,ulong,ulong,ushort *)
0x18019ca5c  mov     r14, rax
0x18019ca5f  test    rax, rax
0x18019ca62  jz      loc_18019CAF1
0x18019ca68  lea     r8, [rbp+57h+var_80]; unsigned __int64 *
0x18019ca6c  mov     [rbp+57h+var_80], rsi
0x18019ca70  mov     rcx, rax; char *
0x18019ca73  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18019ca78  test    eax, eax
0x18019ca7a  jns     short loc_18019CA86
0x18019ca7c  mov     eax, 80070057h
0x18019ca81  jmp     loc_18019CC5E
0x18019ca86  mov     rbx, [rbp+57h+var_80]
0x18019ca8a  inc     rbx
0x18019ca8d  call    cs:__imp_GetProcessHeap
0x18019ca93  test    rax, rax
0x18019ca96  jz      short loc_18019CAE7
0x18019ca98  lea     r8, [rbx+rbx]; dwBytes
0x18019ca9c  mov     edx, 8; dwFlags
0x18019caa1  mov     rcx, rax; hHeap
0x18019caa4  call    cs:__imp_HeapAlloc
0x18019caaa  mov     r15, rax
0x18019caad  test    rax, rax
0x18019cab0  jz      short loc_18019CAE7
0x18019cab2  mov     [rsp+0D0h+nOutBufferSize], ebx; cchWideChar
0x18019cab6  mov     r9d, ebx; cbMultiByte
0x18019cab9  mov     r8, r14; lpMultiByteStr
0x18019cabc  mov     [rsp+0D0h+lpOutBuffer], rax; lpWideCharStr
0x18019cac1  mov     edx, 1; dwFlags
0x18019cac6  xor     ecx, ecx; CodePage
0x18019cac8  call    cs:__imp_MultiByteToWideChar
0x18019cace  mov     rax, [rbp+57h+var_70]
0x18019cad2  xor     ebx, ebx
0x18019cad4  mov     rcx, [rbp+57h+var_68]
0x18019cad8  mov     [rax], r15
0x18019cadb  movzx   eax, [rbp+57h+var_90]
0x18019cadf  mov     [rcx], ax
0x18019cae2  jmp     loc_18019CC00
0x18019cae7  mov     eax, 8007000Eh
0x18019caec  jmp     loc_18019CC5E
0x18019caf1  movzx   eax, [rbp+57h+var_90]
0x18019caf5  mov     dword ptr [rbp+57h+var_80], eax
0x18019caf8  jmp     short loc_18019CB00
0x18019cafa  call    cs:__imp_GetLastError
0x18019cb00  xor     ebx, ebx
0x18019cb02  test    r13, r13
0x18019cb05  jnz     short loc_18019CB11
0x18019cb07  mov     ebx, 8004021Bh
0x18019cb0c  jmp     loc_18019CC00
0x18019cb11  lea     r8, [rbp+57h+var_78]; unsigned __int64 *
0x18019cb15  mov     rcx, r13; unsigned __int16 *
0x18019cb18  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18019cb1d  xor     edx, edx; lpBuffer
0x18019cb1f  lea     r8, [rbp+57h+nSize]; nSize
0x18019cb23  lea     ecx, [rdx+1]; NameType
0x18019cb26  call    cs:__imp_GetComputerNameExW
0x18019cb2c  mov     esi, [rbp+57h+nSize]
0x18019cb2f  call    cs:__imp_GetProcessHeap
0x18019cb35  test    rax, rax
0x18019cb38  jnz     short loc_18019CB3E
0x18019cb3a  xor     esi, esi
0x18019cb3c  jmp     short loc_18019CB58
0x18019cb3e  lea     r8, [rsi+rsi]; dwBytes
0x18019cb42  mov     edx, 8; dwFlags
0x18019cb47  mov     rcx, rax; hHeap
0x18019cb4a  call    cs:__imp_HeapAlloc
0x18019cb50  mov     rsi, rax
0x18019cb53  test    rax, rax
0x18019cb56  jnz     short loc_18019CB62
0x18019cb58  mov     ebx, 8007000Eh
0x18019cb5d  jmp     loc_18019CC00
0x18019cb62  cmp     [rbp+57h+nSize], 0
0x18019cb66  jz      short loc_18019CBE5
0x18019cb68  lea     r8, [rbp+57h+nSize]; nSize
0x18019cb6c  mov     rdx, rsi; lpBuffer
0x18019cb6f  mov     ecx, 1; NameType
0x18019cb74  call    cs:__imp_GetComputerNameExW
0x18019cb7a  test    eax, eax
0x18019cb7c  jz      short loc_18019CBE5
0x18019cb7e  mov     r15d, [rbp+57h+nSize]
0x18019cb82  call    cs:__imp_GetProcessHeap
0x18019cb88  test    rax, rax
0x18019cb8b  jz      short loc_18019CB58
0x18019cb8d  mov     r12, [rbp+57h+var_78]
0x18019cb91  mov     edx, 8; dwFlags
0x18019cb96  mov     rcx, rax; hHeap
0x18019cb99  lea     r8, [r12+r15]
0x18019cb9d  lea     r8, ds:6[r8*2]; dwBytes
0x18019cba5  call    cs:__imp_HeapAlloc
0x18019cbab  mov     r15, rax
0x18019cbae  test    rax, rax
0x18019cbb1  jz      short loc_18019CB58
0x18019cbb3  mov     edx, [rbp+57h+nSize]
0x18019cbb6  lea     r8, aSS_3; "%s:%s"
0x18019cbbd  add     rdx, 3
0x18019cbc1  mov     [rsp+0D0h+lpOutBuffer], rsi
0x18019cbc6  add     rdx, r12; unsigned __int64
0x18019cbc9  mov     r9, r13
0x18019cbcc  mov     rcx, rax; unsigned __int16 *
0x18019cbcf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019cbd4  mov     rax, [rbp+57h+var_70]
0x18019cbd8  mov     rcx, [rbp+57h+var_68]
0x18019cbdc  mov     [rax], r15
0x18019cbdf  mov     eax, dword ptr [rbp+57h+var_80]
0x18019cbe2  mov     [rcx], ax
0x18019cbe5  call    cs:__imp_GetProcessHeap
0x18019cbeb  test    rax, rax
0x18019cbee  jz      short loc_18019CBFE
0x18019cbf0  mov     r8, rsi; lpMem
0x18019cbf3  xor     edx, edx; dwFlags
0x18019cbf5  mov     rcx, rax; hHeap
0x18019cbf8  call    cs:__imp_HeapFree
0x18019cbfe  xor     esi, esi
0x18019cc00  call    cs:__imp_GetProcessHeap
0x18019cc06  test    rax, rax
0x18019cc09  jz      short loc_18019CC19
0x18019cc0b  mov     r8, rdi; lpMem
0x18019cc0e  xor     edx, edx; dwFlags
0x18019cc10  mov     rcx, rax; hHeap
0x18019cc13  call    cs:__imp_HeapFree
0x18019cc19  test    r14, r14
0x18019cc1c  jz      short loc_18019CC37
0x18019cc1e  call    cs:__imp_GetProcessHeap
0x18019cc24  test    rax, rax
0x18019cc27  jz      short loc_18019CC37
0x18019cc29  mov     r8, r14; lpMem
0x18019cc2c  xor     edx, edx; dwFlags
0x18019cc2e  mov     rcx, rax; hHeap
0x18019cc31  call    cs:__imp_HeapFree
0x18019cc37  test    rsi, rsi
0x18019cc3a  jz      short loc_18019CC5C
0x18019cc3c  call    cs:__imp_GetProcessHeap
0x18019cc42  test    rax, rax
0x18019cc45  jz      short loc_18019CC5C
0x18019cc47  mov     r8, rsi; lpMem
0x18019cc4a  xor     edx, edx; dwFlags
0x18019cc4c  mov     rcx, rax; hHeap
0x18019cc4f  call    cs:__imp_HeapFree
0x18019cc55  jmp     short loc_18019CC5C
0x18019cc57  mov     ebx, 8007000Eh
0x18019cc5c  mov     eax, ebx
0x18019cc5e  mov     rcx, [rbp+57h+var_48]
0x18019cc62  xor     rcx, rsp; StackCookie
0x18019cc65  call    __security_check_cookie
0x18019cc6a  add     rsp, 98h
0x18019cc71  pop     r15
0x18019cc73  pop     r14
0x18019cc75  pop     r13
0x18019cc77  pop     r12
0x18019cc79  pop     rdi
0x18019cc7a  pop     rsi
0x18019cc7b  pop     rbx
0x18019cc7c  pop     rbp
0x18019cc7d  retn
```
