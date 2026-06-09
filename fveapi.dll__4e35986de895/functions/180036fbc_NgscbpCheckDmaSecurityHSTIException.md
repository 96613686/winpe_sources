# NgscbpCheckDmaSecurityHSTIException

- ea: `0x180036fbc`
- end: `0x1800373e8`
- name: `NgscbpCheckDmaSecurityHSTIException`
- size: `1068`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008320`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x1800369f0`
- `0x180036fbc`
- `0x1800373f0`
- `0x180037794`
- `0x180037db0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800371a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800371d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800371a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800371d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037195`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800371be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037195`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800371be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037180`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800373d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037180`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800373d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037086`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800370c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800370fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037086`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800370c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800370fe`

## string_xrefs

- `0x180037058`: `SYSTEM\CurrentControlSet\Control\DmaSecurity\VerifiedBuses\HSTI`
- `0x18003705f`: `SYSTEM\CurrentControlSet\Control\DmaSecurity\Default\VerifiedBuses\HSTI`

## pseudocode

```c
__int64 __fastcall NgscbpCheckDmaSecurityHSTIException(char a1, const WCHAR *a2, __int64 a3, _BYTE *a4)
{
  WCHAR *v6; // r14
  unsigned int CpuVendorW; // eax
  int v8; // ebx
  unsigned int CpuVendorHash; // eax
  const WCHAR *v10; // rdx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  HANDLE ProcessHeap; // rax
  void *v15; // rdi
  HANDLE v16; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  HKEY v20; // rcx
  unsigned int v21; // eax
  PVOID *v22; // rcx
  int v23; // edx
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-20h] BYREF
  HKEY hkey; // [rsp+38h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp+58h] BYREF

  hKey = 0;
  phkResult = 0;
  hkey = 0;
  v6 = 0;
  lpMem = 0;
  lpSubKey = 0;
  if ( !a4 )
  {
    v8 = -2147467261;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return (unsigned int)v8;
    v19 = 225;
    goto LABEL_39;
  }
  *a4 = 0;
  if ( !a2 || !*a2 || !a3 )
  {
    v8 = -2147024809;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return (unsigned int)v8;
    v19 = 226;
LABEL_39:
    WPP_SF_d(v18[2], v19, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, (unsigned int)v8);
    goto LABEL_22;
  }
  CpuVendorW = NgscbGetCpuVendorW((unsigned __int16 **)&lpMem);
  v8 = CpuVendorW;
  if ( CpuVendorW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, CpuVendorW);
    if ( v8 < 0 )
      goto LABEL_22;
  }
  CpuVendorHash = NgscbGetCpuVendorHash((unsigned __int16 **)&lpSubKey);
  v8 = CpuVendorHash;
  if ( CpuVendorHash )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        228,
        &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
        CpuVendorHash);
    if ( v8 < 0 )
      goto LABEL_57;
  }
  v10 = L"SYSTEM\\CurrentControlSet\\Control\\DmaSecurity\\Default\\VerifiedBuses\\HSTI";
  if ( !a1 )
    v10 = L"SYSTEM\\CurrentControlSet\\Control\\DmaSecurity\\VerifiedBuses\\HSTI";
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0x20019u, &hKey);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  if ( v11 == -2147024894 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
    v8 = 0;
LABEL_57:
    v6 = (WCHAR *)lpSubKey;
    goto LABEL_22;
  }
  v6 = (WCHAR *)lpSubKey;
  v12 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  if ( v12 == -2147024894 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, lpMem);
    goto LABEL_21;
  }
  v13 = RegOpenKeyExW(phkResult, a2, 0, 0x20019u, &hkey);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  if ( v13 == -2147024894 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        231,
        (unsigned int)&WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
        (_DWORD)a2,
        (__int64)lpMem);
LABEL_21:
    v8 = 0;
    goto LABEL_22;
  }
  v20 = hkey;
  *a4 = 1;
  v21 = NgscbpCheckHSTIPrerequisitesProfile(v20);
  v8 = v21;
  if ( v21 )
  {
    v22 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v21);
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 < 0 )
      goto LABEL_22;
  }
  else
  {
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *a4 )
  {
    if ( v22 == &WPP_GLOBAL_Control || (*((_BYTE *)v22 + 28) & 8) == 0 )
      goto LABEL_22;
    v23 = 234;
  }
  else
  {
    if ( v22 == &WPP_GLOBAL_Control || (*((_BYTE *)v22 + 28) & 4) == 0 )
      goto LABEL_22;
    v23 = 233;
  }
  WPP_SF_SS(
    (unsigned int)v22[2],
    v23,
    (unsigned int)&WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
    (_DWORD)a2,
    (__int64)lpMem);
LABEL_22:
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v15 = lpMem;
  if ( lpMem )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180036fbc  mov     [rsp-38h+arg_8], rbx
0x180036fc1  mov     [rsp-38h+arg_0], cl
0x180036fc5  push    rbp
0x180036fc6  push    rsi
0x180036fc7  push    rdi
0x180036fc8  push    r12
0x180036fca  push    r13
0x180036fcc  push    r14
0x180036fce  push    r15
0x180036fd0  mov     rbp, rsp
0x180036fd3  sub     rsp, 50h
0x180036fd7  xor     edi, edi
0x180036fd9  mov     r12, r9
0x180036fdc  mov     [rbp+hKey], rdi
0x180036fe0  mov     r13, r8
0x180036fe3  mov     [rbp+var_10], rdi
0x180036fe7  mov     r15, rdx
0x180036fea  mov     [rbp+hkey], rdi
0x180036fee  mov     r14d, edi
0x180036ff1  mov     [rbp+lpMem], rdi
0x180036ff5  mov     [rbp+lpSubKey], rdi
0x180036ff9  test    r9, r9
0x180036ffc  jz      loc_180037268
0x180037002  mov     [r9], dil
0x180037005  test    rdx, rdx
0x180037008  jz      loc_18003722D
0x18003700e  cmp     [rdx], di
0x180037011  jz      loc_18003722D
0x180037017  test    r8, r8
0x18003701a  jz      loc_18003722D
0x180037020  lea     rcx, [rbp+lpMem]; unsigned __int16 **
0x180037024  call    ?NgscbGetCpuVendorW@@YAJPEAPEAG@Z; NgscbGetCpuVendorW(ushort * *)
0x180037029  lea     rdi, WPP_GLOBAL_Control
0x180037030  mov     ebx, eax
0x180037032  lea     rsi, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180037039  test    eax, eax
0x18003703b  jnz     loc_180037295
0x180037041  lea     rcx, [rbp+lpSubKey]; unsigned __int16 **
0x180037045  call    ?NgscbGetCpuVendorHash@@YAJPEAPEAG@Z; NgscbGetCpuVendorHash(ushort * *)
0x18003704a  mov     ebx, eax
0x18003704c  test    eax, eax
0x18003704e  jnz     loc_1800372C8
0x180037054  cmp     [rbp+arg_0], r14b
0x180037058  lea     rax, ?NGSCB_DMA_OEM_HSTI_SECURITY@@3QBGB; "SYSTEM\\CurrentControlSet\\Control\\Dma"...
0x18003705f  lea     rdx, ?NGSCB_DMA_DEFAULT_HSTI_SECURITY@@3QBGB; "SYSTEM\\CurrentControlSet\\Control\\Dma"...
0x180037066  mov     r14d, 20019h
0x18003706c  cmovz   rdx, rax; lpSubKey
0x180037070  mov     r9d, r14d; samDesired
0x180037073  lea     rax, [rbp+hKey]
0x180037077  xor     r8d, r8d; ulOptions
0x18003707a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037081  mov     [rsp+50h+phkResult], rax; phkResult
0x180037086  call    cs:__imp_RegOpenKeyExW
0x18003708d  nop     dword ptr [rax+rax+00h]
0x180037092  test    eax, eax
0x180037094  jle     short loc_18003709E
0x180037096  movzx   eax, ax
0x180037099  or      eax, 80070000h
0x18003709e  mov     ebx, 80070002h
0x1800370a3  cmp     eax, ebx
0x1800370a5  jz      loc_1800372F7
0x1800370ab  mov     rcx, [rbp+hKey]; hKey
0x1800370af  lea     rax, [rbp+var_10]
0x1800370b3  mov     r9d, r14d; samDesired
0x1800370b6  mov     [rsp+50h+phkResult], rax; phkResult
0x1800370bb  mov     r14, [rbp+lpSubKey]
0x1800370bf  xor     r8d, r8d; ulOptions
0x1800370c2  mov     rdx, r14; lpSubKey
0x1800370c5  call    cs:__imp_RegOpenKeyExW
0x1800370cc  nop     dword ptr [rax+rax+00h]
0x1800370d1  test    eax, eax
0x1800370d3  jle     short loc_1800370DD
0x1800370d5  movzx   eax, ax
0x1800370d8  or      eax, 80070000h
0x1800370dd  cmp     eax, ebx
0x1800370df  jz      loc_1800371F9
0x1800370e5  mov     rcx, [rbp+var_10]; hKey
0x1800370e9  lea     rax, [rbp+hkey]
0x1800370ed  mov     r9d, 20019h; samDesired
0x1800370f3  mov     [rsp+50h+phkResult], rax; phkResult
0x1800370f8  xor     r8d, r8d; ulOptions
0x1800370fb  mov     rdx, r15; lpSubKey
0x1800370fe  call    cs:__imp_RegOpenKeyExW
0x180037105  nop     dword ptr [rax+rax+00h]
0x18003710a  test    eax, eax
0x18003710c  jle     short loc_180037116
0x18003710e  movzx   eax, ax
0x180037111  or      eax, 80070000h
0x180037116  cmp     eax, ebx
0x180037118  jnz     loc_180037325
0x18003711e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037125  cmp     rcx, rdi
0x180037128  jz      short loc_18003714D
0x18003712a  test    byte ptr [rcx+1Ch], 4
0x18003712e  jz      short loc_18003714D
0x180037130  mov     rax, [rbp+lpMem]
0x180037134  mov     edx, 0E7h
0x180037139  mov     rcx, [rcx+10h]
0x18003713d  mov     r9, r15
0x180037140  mov     r8, rsi
0x180037143  mov     [rsp+50h+phkResult], rax
0x180037148  call    WPP_SF_SS
0x18003714d  xor     ebx, ebx
0x18003714f  mov     rcx, [rbp+hkey]; hKey
0x180037153  xor     esi, esi
0x180037155  test    rcx, rcx
0x180037158  jnz     loc_1800373D3
0x18003715e  mov     rcx, [rbp+var_10]; hKey
0x180037162  test    rcx, rcx
0x180037165  jz      short loc_180037177
0x180037167  call    cs:__imp_RegCloseKey
0x18003716e  nop     dword ptr [rax+rax+00h]
0x180037173  mov     [rbp+var_10], rsi
0x180037177  mov     rcx, [rbp+hKey]; hKey
0x18003717b  test    rcx, rcx
0x18003717e  jz      short loc_180037190
0x180037180  call    cs:__imp_RegCloseKey
0x180037187  nop     dword ptr [rax+rax+00h]
0x18003718c  mov     [rbp+hKey], rsi
0x180037190  test    r14, r14
0x180037193  jz      short loc_1800371B5
0x180037195  call    cs:__imp_GetProcessHeap
0x18003719c  nop     dword ptr [rax+rax+00h]
0x1800371a1  mov     r8, r14; lpMem
0x1800371a4  xor     edx, edx; dwFlags
0x1800371a6  mov     rcx, rax; hHeap
0x1800371a9  call    cs:__imp_HeapFree
0x1800371b0  nop     dword ptr [rax+rax+00h]
0x1800371b5  mov     rdi, [rbp+lpMem]
0x1800371b9  test    rdi, rdi
0x1800371bc  jz      short loc_1800371DE
0x1800371be  call    cs:__imp_GetProcessHeap
0x1800371c5  nop     dword ptr [rax+rax+00h]
0x1800371ca  mov     r8, rdi; lpMem
0x1800371cd  xor     edx, edx; dwFlags
0x1800371cf  mov     rcx, rax; hHeap
0x1800371d2  call    cs:__imp_HeapFree
0x1800371d9  nop     dword ptr [rax+rax+00h]
0x1800371de  mov     eax, ebx
0x1800371e0  mov     rbx, [rsp+50h+arg_8]
0x1800371e8  add     rsp, 50h
0x1800371ec  pop     r15
0x1800371ee  pop     r14
0x1800371f0  pop     r13
0x1800371f2  pop     r12
0x1800371f4  pop     rdi
0x1800371f5  pop     rsi
0x1800371f6  pop     rbp
0x1800371f7  retn
0x1800371f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180037200  cmp     rcx, rdi
0x180037203  jz      loc_18003714D
0x180037209  test    byte ptr [rcx+1Ch], 4
0x18003720d  jz      loc_18003714D
0x180037213  mov     r9, [rbp+lpMem]
0x180037217  mov     edx, 0E6h
0x18003721c  mov     rcx, [rcx+10h]
0x180037220  mov     r8, rsi
0x180037223  call    WPP_SF_S
0x180037228  jmp     loc_18003714D
0x18003722d  mov     ebx, 80070057h
0x180037232  mov     rcx, cs:WPP_GLOBAL_Control
0x180037239  lea     rdi, WPP_GLOBAL_Control
0x180037240  cmp     rcx, rdi
0x180037243  jz      short loc_1800371DE
0x180037245  test    byte ptr [rcx+1Ch], 40h
0x180037249  jz      short loc_1800371DE
0x18003724b  mov     edx, 0E2h
0x180037250  mov     rcx, [rcx+10h]
0x180037254  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18003725b  mov     r9d, ebx
0x18003725e  call    WPP_SF_d
0x180037263  jmp     loc_18003714F
0x180037268  mov     ebx, 80004003h
0x18003726d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037274  lea     rdi, WPP_GLOBAL_Control
0x18003727b  cmp     rcx, rdi
0x18003727e  jz      loc_1800371DE
0x180037284  test    byte ptr [rcx+1Ch], 40h
0x180037288  jz      loc_1800371DE
0x18003728e  mov     edx, 0E1h
0x180037293  jmp     short loc_180037250
0x180037295  mov     rcx, cs:WPP_GLOBAL_Control
0x18003729c  cmp     rcx, rdi
0x18003729f  jz      short loc_1800372BB
0x1800372a1  test    byte ptr [rcx+1Ch], 40h
0x1800372a5  jz      short loc_1800372BB
0x1800372a7  mov     rcx, [rcx+10h]
0x1800372ab  mov     edx, 0E3h
0x1800372b0  mov     r9d, ebx
0x1800372b3  mov     r8, rsi
0x1800372b6  call    WPP_SF_d
0x1800372bb  test    ebx, ebx
0x1800372bd  js      loc_18003714F
0x1800372c3  jmp     loc_180037041
0x1800372c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372cf  cmp     rcx, rdi
0x1800372d2  jz      short loc_1800372EE
0x1800372d4  test    byte ptr [rcx+1Ch], 40h
0x1800372d8  jz      short loc_1800372EE
0x1800372da  mov     rcx, [rcx+10h]
0x1800372de  mov     edx, 0E4h
0x1800372e3  mov     r9d, ebx
0x1800372e6  mov     r8, rsi
0x1800372e9  call    WPP_SF_d
0x1800372ee  test    ebx, ebx
0x1800372f0  js      short loc_18003731C
0x1800372f2  jmp     loc_180037054
0x1800372f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372fe  cmp     rcx, rdi
0x180037301  jz      short loc_18003731A
0x180037303  test    byte ptr [rcx+1Ch], 4
0x180037307  jz      short loc_18003731A
0x180037309  mov     rcx, [rcx+10h]
0x18003730d  mov     edx, 0E5h
0x180037312  mov     r8, rsi
0x180037315  call    WPP_SF_
0x18003731a  xor     ebx, ebx
0x18003731c  mov     r14, [rbp+lpSubKey]
0x180037320  jmp     loc_18003714F
0x180037325  mov     rcx, [rbp+hkey]; hkey
0x180037329  mov     r8, r13
0x18003732c  mov     rdx, r12
0x18003732f  mov     byte ptr [r12], 1
0x180037334  call    NgscbpCheckHSTIPrerequisitesProfile
0x180037339  mov     ebx, eax
0x18003733b  test    eax, eax
0x18003733d  jz      short loc_180037376
0x18003733f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037346  cmp     rcx, rdi
0x180037349  jz      short loc_18003736C
0x18003734b  test    byte ptr [rcx+1Ch], 40h
0x18003734f  jz      short loc_18003736C
0x180037351  mov     rcx, [rcx+10h]
0x180037355  mov     edx, 0E8h
0x18003735a  mov     r9d, eax
0x18003735d  mov     r8, rsi
0x180037360  call    WPP_SF_d
0x180037365  mov     rcx, cs:WPP_GLOBAL_Control
0x18003736c  test    ebx, ebx
0x18003736e  js      loc_18003714F
0x180037374  jmp     short loc_18003737D
0x180037376  mov     rcx, cs:WPP_GLOBAL_Control
0x18003737d  cmp     byte ptr [r12], 0
0x180037382  jnz     short loc_18003739E
0x180037384  cmp     rcx, rdi
0x180037387  jz      loc_18003714F
0x18003738d  test    byte ptr [rcx+1Ch], 4
0x180037391  jz      loc_18003714F
0x180037397  mov     edx, 0E9h
0x18003739c  jmp     short loc_1800373B6
0x18003739e  cmp     rcx, rdi
0x1800373a1  jz      loc_18003714F
0x1800373a7  test    byte ptr [rcx+1Ch], 8
0x1800373ab  jz      loc_18003714F
0x1800373b1  mov     edx, 0EAh
0x1800373b6  mov     rax, [rbp+lpMem]
0x1800373ba  mov     r9, r15
0x1800373bd  mov     rcx, [rcx+10h]
0x1800373c1  mov     r8, rsi
0x1800373c4  mov     [rsp+50h+phkResult], rax
0x1800373c9  call    WPP_SF_SS
0x1800373ce  jmp     loc_18003714F
0x1800373d3  call    cs:__imp_RegCloseKey
0x1800373da  nop     dword ptr [rax+rax+00h]
0x1800373df  mov     [rbp+hkey], rsi
0x1800373e3  jmp     loc_18003715E
```
