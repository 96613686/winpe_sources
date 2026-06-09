# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x18001c96c`
- end: `0x18001cafd`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cb04`

## callees

- `0x1800039f0`
- `0x18001c96c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ca60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cac5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ca60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cac5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ca52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cab7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ca52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cab7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cad6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cad6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c9e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c9e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c9b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c9b3`
- `DMCmnUtils!UnicodeToMB` at `0x18001ca2e`
- `DMCmnUtils!UnicodeToMB` at `0x18001ca2e`

## pseudocode

```c
__int64 __fastcall GetComponentCVForEnrollmentId(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char *a3,
        HKEY a4)
{
  int v5; // esi
  void *v6; // rdi
  HANDLE ProcessHeap; // rax
  void *v8; // rdi
  __int64 v9; // rax
  char *v10; // rdx
  __int64 v11; // rcx
  char v12; // r8
  char *v13; // rax
  HANDLE v14; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID *p_lpMem; // [rsp+48h] [rbp-B8h]
  char *v21; // [rsp+50h] [rbp-B0h] BYREF
  char v22; // [rsp+58h] [rbp-A8h]
  unsigned __int16 Data[136]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  RegOpenKeyExW(a4, a2, 0, 0x20019u, &hKey);
  cbData = 258;
  if ( !RegQueryValueExW(hKey, L"OmaDmSession", 0, 0, (LPBYTE)Data, &cbData) )
  {
    lpMem = 0;
    v17 = 0;
    p_lpMem = &lpMem;
    v21 = 0;
    v22 = 1;
    v5 = UnicodeToMB(Data, 0xFDE9u, &v21, &v17);
    if ( v22 )
    {
      v6 = *p_lpMem;
      *p_lpMem = v21;
      if ( v6 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6);
      }
    }
    v8 = lpMem;
    if ( v5 >= 0 )
    {
      v9 = 2147483646;
      v10 = (char *)lpMem;
      v11 = 129;
      do
      {
        if ( !v9 )
          break;
        v12 = *v10;
        if ( !*v10 )
          break;
        ++v10;
        *a3++ = v12;
        --v9;
        --v11;
      }
      while ( v11 );
      v13 = a3 - 1;
      if ( v11 )
        v13 = a3;
      *v13 = 0;
    }
    lpMem = 0;
    if ( v8 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v8);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001c96c  mov     [rsp-8+arg_0], rbx
0x18001c971  push    rbp
0x18001c972  push    rsi
0x18001c973  push    rdi
0x18001c974  lea     rbp, [rsp-80h]
0x18001c979  sub     rsp, 180h
0x18001c980  mov     rax, cs:__security_cookie
0x18001c987  xor     rax, rsp
0x18001c98a  mov     [rbp+90h+var_20], rax
0x18001c98e  mov     rax, r9
0x18001c991  mov     rbx, r8
0x18001c994  mov     [rsp+190h+hKey], 0
0x18001c99d  lea     rcx, [rsp+190h+hKey]
0x18001c9a2  mov     [rsp+190h+phkResult], rcx; phkResult
0x18001c9a7  mov     r9d, 20019h; samDesired
0x18001c9ad  xor     r8d, r8d; ulOptions
0x18001c9b0  mov     rcx, rax; hKey
0x18001c9b3  call    cs:__imp_RegOpenKeyExW
0x18001c9b9  mov     [rsp+190h+cbData], 102h
0x18001c9c1  lea     rax, [rsp+190h+cbData]
0x18001c9c6  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18001c9cb  lea     rax, [rsp+190h+Data]
0x18001c9d0  mov     [rsp+190h+phkResult], rax; lpData
0x18001c9d5  xor     r9d, r9d; lpType
0x18001c9d8  xor     r8d, r8d; lpReserved
0x18001c9db  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x18001c9e2  mov     rcx, [rsp+190h+hKey]; hKey
0x18001c9e7  call    cs:__imp_RegQueryValueExW
0x18001c9ed  test    eax, eax
0x18001c9ef  jnz     loc_18001CACC
0x18001c9f5  mov     [rsp+190h+lpMem], 0
0x18001c9fe  mov     [rsp+190h+var_15C], eax
0x18001ca02  lea     rax, [rsp+190h+lpMem]
0x18001ca07  mov     [rsp+190h+var_148], rax
0x18001ca0c  mov     [rsp+190h+var_140], 0
0x18001ca15  mov     [rsp+190h+var_138], 1
0x18001ca1a  lea     r9, [rsp+190h+var_15C]
0x18001ca1f  lea     r8, [rsp+190h+var_140]
0x18001ca24  mov     edx, 0FDE9h
0x18001ca29  lea     rcx, [rsp+190h+Data]
0x18001ca2e  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18001ca34  mov     esi, eax
0x18001ca36  cmp     [rsp+190h+var_138], 0
0x18001ca3b  jz      short loc_18001CA66
0x18001ca3d  mov     rdx, [rsp+190h+var_148]
0x18001ca42  mov     rdi, [rdx]
0x18001ca45  mov     rcx, [rsp+190h+var_140]
0x18001ca4a  mov     [rdx], rcx
0x18001ca4d  test    rdi, rdi
0x18001ca50  jz      short loc_18001CA66
0x18001ca52  call    cs:__imp_GetProcessHeap
0x18001ca58  mov     rcx, rax; hHeap
0x18001ca5b  mov     r8, rdi; lpMem
0x18001ca5e  xor     edx, edx; dwFlags
0x18001ca60  call    cs:__imp_HeapFree
0x18001ca66  mov     rdi, [rsp+190h+lpMem]
0x18001ca6b  test    esi, esi
0x18001ca6d  js      short loc_18001CAA9
0x18001ca6f  mov     eax, 7FFFFFFEh
0x18001ca74  mov     rdx, rdi
0x18001ca77  mov     ecx, 81h
0x18001ca7c  test    rax, rax
0x18001ca7f  jz      short loc_18001CA9B
0x18001ca81  mov     r8b, [rdx]
0x18001ca84  test    r8b, r8b
0x18001ca87  jz      short loc_18001CA9B
0x18001ca89  inc     rdx
0x18001ca8c  mov     [rbx], r8b
0x18001ca8f  inc     rbx
0x18001ca92  dec     rax
0x18001ca95  sub     rcx, 1
0x18001ca99  jnz     short loc_18001CA7C
0x18001ca9b  lea     rax, [rbx-1]
0x18001ca9f  test    rcx, rcx
0x18001caa2  cmovnz  rax, rbx
0x18001caa6  mov     byte ptr [rax], 0
0x18001caa9  mov     [rsp+190h+lpMem], 0
0x18001cab2  test    rdi, rdi
0x18001cab5  jz      short loc_18001CACC
0x18001cab7  call    cs:__imp_GetProcessHeap
0x18001cabd  mov     rcx, rax; hHeap
0x18001cac0  mov     r8, rdi; lpMem
0x18001cac3  xor     edx, edx; dwFlags
0x18001cac5  call    cs:__imp_HeapFree
0x18001cacb  nop
0x18001cacc  mov     rcx, [rsp+190h+hKey]; hKey
0x18001cad1  test    rcx, rcx
0x18001cad4  jz      short loc_18001CADC
0x18001cad6  call    cs:__imp_RegCloseKey
0x18001cadc  xor     eax, eax
0x18001cade  mov     rcx, [rbp+90h+var_20]
0x18001cae2  xor     rcx, rsp; StackCookie
0x18001cae5  call    __security_check_cookie
0x18001caea  mov     rbx, [rsp+190h+arg_0]
0x18001caf2  add     rsp, 180h
0x18001caf9  pop     rdi
0x18001cafa  pop     rsi
0x18001cafb  pop     rbp
0x18001cafc  retn
```
