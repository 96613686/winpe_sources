# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x180020aac`
- end: `0x180020c6e`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `450`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020c74`
- `0x180020df4`

## callees

- `0x1800031b0`
- `0x180020aac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020bb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020c29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020bb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020c29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ba4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020c15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020ba4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020c15`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020b2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020b2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020c40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020c40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020af3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020af3`
- `DMCmnUtils!UnicodeToMB` at `0x180020b7a`
- `DMCmnUtils!UnicodeToMB` at `0x180020b7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180020aac  mov     [rsp-8+arg_0], rbx
0x180020ab1  push    rbp
0x180020ab2  push    rsi
0x180020ab3  push    rdi
0x180020ab4  lea     rbp, [rsp-80h]
0x180020ab9  sub     rsp, 180h
0x180020ac0  mov     rax, cs:__security_cookie
0x180020ac7  xor     rax, rsp
0x180020aca  mov     [rbp+90h+var_20], rax
0x180020ace  mov     rax, r9
0x180020ad1  mov     rbx, r8
0x180020ad4  mov     [rsp+190h+hKey], 0
0x180020add  lea     rcx, [rsp+190h+hKey]
0x180020ae2  mov     [rsp+190h+phkResult], rcx; phkResult
0x180020ae7  mov     r9d, 20019h; samDesired
0x180020aed  xor     r8d, r8d; ulOptions
0x180020af0  mov     rcx, rax; hKey
0x180020af3  call    cs:__imp_RegOpenKeyExW
0x180020afa  nop     dword ptr [rax+rax+00h]
0x180020aff  mov     [rsp+190h+cbData], 102h
0x180020b07  lea     rax, [rsp+190h+cbData]
0x180020b0c  mov     [rsp+190h+lpcbData], rax; lpcbData
0x180020b11  lea     rax, [rsp+190h+Data]
0x180020b16  mov     [rsp+190h+phkResult], rax; lpData
0x180020b1b  xor     r9d, r9d; lpType
0x180020b1e  xor     r8d, r8d; lpReserved
0x180020b21  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x180020b28  mov     rcx, [rsp+190h+hKey]; hKey
0x180020b2d  call    cs:__imp_RegQueryValueExW
0x180020b34  nop     dword ptr [rax+rax+00h]
0x180020b39  test    eax, eax
0x180020b3b  jnz     loc_180020C36
0x180020b41  mov     [rsp+190h+lpMem], 0
0x180020b4a  mov     [rsp+190h+var_15C], eax
0x180020b4e  lea     rax, [rsp+190h+lpMem]
0x180020b53  mov     [rsp+190h+var_148], rax
0x180020b58  mov     [rsp+190h+var_140], 0
0x180020b61  mov     [rsp+190h+var_138], 1
0x180020b66  lea     r9, [rsp+190h+var_15C]
0x180020b6b  lea     r8, [rsp+190h+var_140]
0x180020b70  mov     edx, 0FDE9h
0x180020b75  lea     rcx, [rsp+190h+Data]
0x180020b7a  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x180020b81  nop     dword ptr [rax+rax+00h]
0x180020b86  mov     esi, eax
0x180020b88  cmp     [rsp+190h+var_138], 0
0x180020b8d  jz      short loc_180020BC4
0x180020b8f  mov     rdx, [rsp+190h+var_148]
0x180020b94  mov     rdi, [rdx]
0x180020b97  mov     rcx, [rsp+190h+var_140]
0x180020b9c  mov     [rdx], rcx
0x180020b9f  test    rdi, rdi
0x180020ba2  jz      short loc_180020BC4
0x180020ba4  call    cs:__imp_GetProcessHeap
0x180020bab  nop     dword ptr [rax+rax+00h]
0x180020bb0  mov     rcx, rax; hHeap
0x180020bb3  mov     r8, rdi; lpMem
0x180020bb6  xor     edx, edx; dwFlags
0x180020bb8  call    cs:__imp_HeapFree
0x180020bbf  nop     dword ptr [rax+rax+00h]
0x180020bc4  mov     rdi, [rsp+190h+lpMem]
0x180020bc9  test    esi, esi
0x180020bcb  js      short loc_180020C07
0x180020bcd  mov     eax, 7FFFFFFEh
0x180020bd2  mov     rdx, rdi
0x180020bd5  mov     ecx, 81h
0x180020bda  test    rax, rax
0x180020bdd  jz      short loc_180020BF9
0x180020bdf  mov     r8b, [rdx]
0x180020be2  test    r8b, r8b
0x180020be5  jz      short loc_180020BF9
0x180020be7  inc     rdx
0x180020bea  mov     [rbx], r8b
0x180020bed  inc     rbx
0x180020bf0  dec     rax
0x180020bf3  sub     rcx, 1
0x180020bf7  jnz     short loc_180020BDA
0x180020bf9  lea     rax, [rbx-1]
0x180020bfd  test    rcx, rcx
0x180020c00  cmovnz  rax, rbx
0x180020c04  mov     byte ptr [rax], 0
0x180020c07  mov     [rsp+190h+lpMem], 0
0x180020c10  test    rdi, rdi
0x180020c13  jz      short loc_180020C36
0x180020c15  call    cs:__imp_GetProcessHeap
0x180020c1c  nop     dword ptr [rax+rax+00h]
0x180020c21  mov     rcx, rax; hHeap
0x180020c24  mov     r8, rdi; lpMem
0x180020c27  xor     edx, edx; dwFlags
0x180020c29  call    cs:__imp_HeapFree
0x180020c30  nop     dword ptr [rax+rax+00h]
0x180020c35  nop
0x180020c36  mov     rcx, [rsp+190h+hKey]; hKey
0x180020c3b  test    rcx, rcx
0x180020c3e  jz      short loc_180020C4C
0x180020c40  call    cs:__imp_RegCloseKey
0x180020c47  nop     dword ptr [rax+rax+00h]
0x180020c4c  xor     eax, eax
0x180020c4e  mov     rcx, [rbp+90h+var_20]
0x180020c52  xor     rcx, rsp; StackCookie
0x180020c55  call    __security_check_cookie
0x180020c5a  mov     rbx, [rsp+190h+arg_0]
0x180020c62  add     rsp, 180h
0x180020c69  pop     rdi
0x180020c6a  pop     rsi
0x180020c6b  pop     rbp
0x180020c6c  retn
```
