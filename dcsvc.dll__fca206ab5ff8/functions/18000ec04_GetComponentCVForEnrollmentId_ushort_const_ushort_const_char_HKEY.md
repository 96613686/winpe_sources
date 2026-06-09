# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x18000ec04`
- end: `0x18000ed95`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ed9c`

## callees

- `0x180001cf0`
- `0x18000ec04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ecea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ecea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ecf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ecf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ec7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ec7f`
- `DMCmnUtils!UnicodeToMB` at `0x18000ecc6`
- `DMCmnUtils!UnicodeToMB` at `0x18000ecc6`

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
0x18000ec04  mov     [rsp-8+arg_0], rbx
0x18000ec09  push    rbp
0x18000ec0a  push    rsi
0x18000ec0b  push    rdi
0x18000ec0c  lea     rbp, [rsp-80h]
0x18000ec11  sub     rsp, 180h
0x18000ec18  mov     rax, cs:__security_cookie
0x18000ec1f  xor     rax, rsp
0x18000ec22  mov     [rbp+90h+var_20], rax
0x18000ec26  mov     rax, r9
0x18000ec29  mov     rbx, r8
0x18000ec2c  mov     [rsp+190h+hKey], 0
0x18000ec35  lea     rcx, [rsp+190h+hKey]
0x18000ec3a  mov     [rsp+190h+phkResult], rcx; phkResult
0x18000ec3f  mov     r9d, 20019h; samDesired
0x18000ec45  xor     r8d, r8d; ulOptions
0x18000ec48  mov     rcx, rax; hKey
0x18000ec4b  call    cs:__imp_RegOpenKeyExW
0x18000ec51  mov     [rsp+190h+cbData], 102h
0x18000ec59  lea     rax, [rsp+190h+cbData]
0x18000ec5e  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18000ec63  lea     rax, [rsp+190h+Data]
0x18000ec68  mov     [rsp+190h+phkResult], rax; lpData
0x18000ec6d  xor     r9d, r9d; lpType
0x18000ec70  xor     r8d, r8d; lpReserved
0x18000ec73  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x18000ec7a  mov     rcx, [rsp+190h+hKey]; hKey
0x18000ec7f  call    cs:__imp_RegQueryValueExW
0x18000ec85  test    eax, eax
0x18000ec87  jnz     loc_18000ED64
0x18000ec8d  mov     [rsp+190h+lpMem], 0
0x18000ec96  mov     [rsp+190h+var_15C], eax
0x18000ec9a  lea     rax, [rsp+190h+lpMem]
0x18000ec9f  mov     [rsp+190h+var_148], rax
0x18000eca4  mov     [rsp+190h+var_140], 0
0x18000ecad  mov     [rsp+190h+var_138], 1
0x18000ecb2  lea     r9, [rsp+190h+var_15C]
0x18000ecb7  lea     r8, [rsp+190h+var_140]
0x18000ecbc  mov     edx, 0FDE9h
0x18000ecc1  lea     rcx, [rsp+190h+Data]
0x18000ecc6  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18000eccc  mov     esi, eax
0x18000ecce  cmp     [rsp+190h+var_138], 0
0x18000ecd3  jz      short loc_18000ECFE
0x18000ecd5  mov     rdx, [rsp+190h+var_148]
0x18000ecda  mov     rdi, [rdx]
0x18000ecdd  mov     rcx, [rsp+190h+var_140]
0x18000ece2  mov     [rdx], rcx
0x18000ece5  test    rdi, rdi
0x18000ece8  jz      short loc_18000ECFE
0x18000ecea  call    cs:__imp_GetProcessHeap
0x18000ecf0  mov     rcx, rax; hHeap
0x18000ecf3  mov     r8, rdi; lpMem
0x18000ecf6  xor     edx, edx; dwFlags
0x18000ecf8  call    cs:__imp_HeapFree
0x18000ecfe  mov     rdi, [rsp+190h+lpMem]
0x18000ed03  test    esi, esi
0x18000ed05  js      short loc_18000ED41
0x18000ed07  mov     eax, 7FFFFFFEh
0x18000ed0c  mov     rdx, rdi
0x18000ed0f  mov     ecx, 81h
0x18000ed14  test    rax, rax
0x18000ed17  jz      short loc_18000ED33
0x18000ed19  mov     r8b, [rdx]
0x18000ed1c  test    r8b, r8b
0x18000ed1f  jz      short loc_18000ED33
0x18000ed21  inc     rdx
0x18000ed24  mov     [rbx], r8b
0x18000ed27  inc     rbx
0x18000ed2a  dec     rax
0x18000ed2d  sub     rcx, 1
0x18000ed31  jnz     short loc_18000ED14
0x18000ed33  lea     rax, [rbx-1]
0x18000ed37  test    rcx, rcx
0x18000ed3a  cmovnz  rax, rbx
0x18000ed3e  mov     byte ptr [rax], 0
0x18000ed41  mov     [rsp+190h+lpMem], 0
0x18000ed4a  test    rdi, rdi
0x18000ed4d  jz      short loc_18000ED64
0x18000ed4f  call    cs:__imp_GetProcessHeap
0x18000ed55  mov     rcx, rax; hHeap
0x18000ed58  mov     r8, rdi; lpMem
0x18000ed5b  xor     edx, edx; dwFlags
0x18000ed5d  call    cs:__imp_HeapFree
0x18000ed63  nop
0x18000ed64  mov     rcx, [rsp+190h+hKey]; hKey
0x18000ed69  test    rcx, rcx
0x18000ed6c  jz      short loc_18000ED74
0x18000ed6e  call    cs:__imp_RegCloseKey
0x18000ed74  xor     eax, eax
0x18000ed76  mov     rcx, [rbp+90h+var_20]
0x18000ed7a  xor     rcx, rsp; StackCookie
0x18000ed7d  call    __security_check_cookie
0x18000ed82  mov     rbx, [rsp+190h+arg_0]
0x18000ed8a  add     rsp, 180h
0x18000ed91  pop     rdi
0x18000ed92  pop     rsi
0x18000ed93  pop     rbp
0x18000ed94  retn
```
