# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x14000da8c`
- end: `0x14000dc46`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, const unsigned __int16 *, char *, HKEY)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000dc4c`
- `0x14000e3e4`

## callees

- `0x14000da8c`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000db83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000dbf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000db83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000dbf4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000db97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000dc08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000db97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000dc08`
- `DMCmnUtils!UnicodeToMB` at `0x14000db59`
- `DMCmnUtils!UnicodeToMB` at `0x14000db59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000db0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000db0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000dad6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000dad6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000dc1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000dc1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetComponentCVForEnrollmentId(LPCWSTR lpValueName, const unsigned __int16 *a2, char *a3, HKEY a4)
{
  int v6; // esi
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  void *v9; // rbx
  __int64 v10; // rax
  char *v11; // rdx
  __int64 v12; // rcx
  char v13; // r8
  char *v14; // rax
  HANDLE v15; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID *p_lpMem; // [rsp+48h] [rbp-B8h]
  char *v22; // [rsp+50h] [rbp-B0h] BYREF
  char v23; // [rsp+58h] [rbp-A8h]
  unsigned __int16 Data[136]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  RegOpenKeyExW(a4, a2, 0, 0x20019u, &hKey);
  cbData = 258;
  if ( !RegQueryValueExW(hKey, lpValueName, 0, 0, (LPBYTE)Data, &cbData) )
  {
    lpMem = 0;
    v18 = 0;
    p_lpMem = &lpMem;
    v22 = 0;
    v23 = 1;
    v6 = UnicodeToMB(Data, 0xFDE9u, &v22, &v18);
    if ( v23 )
    {
      v7 = *p_lpMem;
      *p_lpMem = v22;
      if ( v7 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v7);
      }
    }
    v9 = lpMem;
    if ( v6 >= 0 )
    {
      v10 = 2147483646;
      v11 = (char *)lpMem;
      v12 = 129;
      do
      {
        if ( !v10 )
          break;
        v13 = *v11;
        if ( !*v11 )
          break;
        ++v11;
        *a3++ = v13;
        --v10;
        --v12;
      }
      while ( v12 );
      v14 = a3 - 1;
      if ( v12 )
        v14 = a3;
      *v14 = 0;
    }
    lpMem = 0;
    if ( v9 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v9);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x14000da8c  push    rbp
0x14000da8e  push    rbx
0x14000da8f  push    rsi
0x14000da90  push    rdi
0x14000da91  lea     rbp, [rsp-88h]
0x14000da99  sub     rsp, 188h
0x14000daa0  mov     rax, cs:__security_cookie
0x14000daa7  xor     rax, rsp
0x14000daaa  mov     [rbp+0A0h+var_30], rax
0x14000daae  mov     rax, r9
0x14000dab1  mov     rdi, r8
0x14000dab4  mov     rbx, rcx
0x14000dab7  mov     [rsp+1A0h+hKey], 0
0x14000dac0  lea     rcx, [rsp+1A0h+hKey]
0x14000dac5  mov     [rsp+1A0h+phkResult], rcx; phkResult
0x14000daca  mov     r9d, 20019h; samDesired
0x14000dad0  xor     r8d, r8d; ulOptions
0x14000dad3  mov     rcx, rax; hKey
0x14000dad6  call    cs:__imp_RegOpenKeyExW
0x14000dadd  nop     dword ptr [rax+rax+00h]
0x14000dae2  mov     [rsp+1A0h+cbData], 102h
0x14000daea  lea     rax, [rsp+1A0h+cbData]
0x14000daef  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x14000daf4  lea     rax, [rsp+1A0h+Data]
0x14000daf9  mov     [rsp+1A0h+phkResult], rax; lpData
0x14000dafe  xor     r9d, r9d; lpType
0x14000db01  xor     r8d, r8d; lpReserved
0x14000db04  mov     rdx, rbx; lpValueName
0x14000db07  mov     rcx, [rsp+1A0h+hKey]; hKey
0x14000db0c  call    cs:__imp_RegQueryValueExW
0x14000db13  nop     dword ptr [rax+rax+00h]
0x14000db18  test    eax, eax
0x14000db1a  jnz     loc_14000DC15
0x14000db20  mov     [rsp+1A0h+lpMem], 0
0x14000db29  mov     [rsp+1A0h+var_16C], eax
0x14000db2d  lea     rax, [rsp+1A0h+lpMem]
0x14000db32  mov     [rsp+1A0h+var_158], rax
0x14000db37  mov     [rsp+1A0h+var_150], 0
0x14000db40  mov     [rsp+1A0h+var_148], 1
0x14000db45  lea     r9, [rsp+1A0h+var_16C]
0x14000db4a  lea     r8, [rsp+1A0h+var_150]
0x14000db4f  mov     edx, 0FDE9h
0x14000db54  lea     rcx, [rsp+1A0h+Data]
0x14000db59  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x14000db60  nop     dword ptr [rax+rax+00h]
0x14000db65  mov     esi, eax
0x14000db67  cmp     [rsp+1A0h+var_148], 0
0x14000db6c  jz      short loc_14000DBA3
0x14000db6e  mov     rdx, [rsp+1A0h+var_158]
0x14000db73  mov     rbx, [rdx]
0x14000db76  mov     rcx, [rsp+1A0h+var_150]
0x14000db7b  mov     [rdx], rcx
0x14000db7e  test    rbx, rbx
0x14000db81  jz      short loc_14000DBA3
0x14000db83  call    cs:__imp_GetProcessHeap
0x14000db8a  nop     dword ptr [rax+rax+00h]
0x14000db8f  mov     rcx, rax; hHeap
0x14000db92  mov     r8, rbx; lpMem
0x14000db95  xor     edx, edx; dwFlags
0x14000db97  call    cs:__imp_HeapFree
0x14000db9e  nop     dword ptr [rax+rax+00h]
0x14000dba3  mov     rbx, [rsp+1A0h+lpMem]
0x14000dba8  test    esi, esi
0x14000dbaa  js      short loc_14000DBE6
0x14000dbac  mov     eax, 7FFFFFFEh
0x14000dbb1  mov     rdx, rbx
0x14000dbb4  mov     ecx, 81h
0x14000dbb9  test    rax, rax
0x14000dbbc  jz      short loc_14000DBD8
0x14000dbbe  mov     r8b, [rdx]
0x14000dbc1  test    r8b, r8b
0x14000dbc4  jz      short loc_14000DBD8
0x14000dbc6  inc     rdx
0x14000dbc9  mov     [rdi], r8b
0x14000dbcc  inc     rdi
0x14000dbcf  dec     rax
0x14000dbd2  sub     rcx, 1
0x14000dbd6  jnz     short loc_14000DBB9
0x14000dbd8  lea     rax, [rdi-1]
0x14000dbdc  test    rcx, rcx
0x14000dbdf  cmovnz  rax, rdi
0x14000dbe3  mov     byte ptr [rax], 0
0x14000dbe6  mov     [rsp+1A0h+lpMem], 0
0x14000dbef  test    rbx, rbx
0x14000dbf2  jz      short loc_14000DC15
0x14000dbf4  call    cs:__imp_GetProcessHeap
0x14000dbfb  nop     dword ptr [rax+rax+00h]
0x14000dc00  mov     rcx, rax; hHeap
0x14000dc03  mov     r8, rbx; lpMem
0x14000dc06  xor     edx, edx; dwFlags
0x14000dc08  call    cs:__imp_HeapFree
0x14000dc0f  nop     dword ptr [rax+rax+00h]
0x14000dc14  nop
0x14000dc15  mov     rcx, [rsp+1A0h+hKey]; hKey
0x14000dc1a  test    rcx, rcx
0x14000dc1d  jz      short loc_14000DC2B
0x14000dc1f  call    cs:__imp_RegCloseKey
0x14000dc26  nop     dword ptr [rax+rax+00h]
0x14000dc2b  xor     eax, eax
0x14000dc2d  mov     rcx, [rbp+0A0h+var_30]
0x14000dc31  xor     rcx, rsp; StackCookie
0x14000dc34  call    __security_check_cookie
0x14000dc39  add     rsp, 188h
0x14000dc40  pop     rdi
0x14000dc41  pop     rsi
0x14000dc42  pop     rbx
0x14000dc43  pop     rbp
0x14000dc44  retn
```
