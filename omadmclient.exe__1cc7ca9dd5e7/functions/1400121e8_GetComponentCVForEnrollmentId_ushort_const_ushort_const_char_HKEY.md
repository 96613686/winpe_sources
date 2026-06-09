# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x1400121e8`
- end: `0x1400123aa`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `450`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400123b0`
- `0x140012b54`

## callees

- `0x140003450`
- `0x1400121e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001222f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001222f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012269`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012269`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001237c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001237c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400122e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012351`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400122e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012351`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400122f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012365`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400122f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012365`
- `DMCmnUtils!UnicodeToMB` at `0x1400122b6`
- `DMCmnUtils!UnicodeToMB` at `0x1400122b6`

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
0x1400121e8  mov     [rsp-8+arg_0], rbx
0x1400121ed  push    rbp
0x1400121ee  push    rsi
0x1400121ef  push    rdi
0x1400121f0  lea     rbp, [rsp-80h]
0x1400121f5  sub     rsp, 180h
0x1400121fc  mov     rax, cs:__security_cookie
0x140012203  xor     rax, rsp
0x140012206  mov     [rbp+90h+var_20], rax
0x14001220a  mov     rax, r9
0x14001220d  mov     rbx, r8
0x140012210  mov     [rsp+190h+hKey], 0
0x140012219  lea     rcx, [rsp+190h+hKey]
0x14001221e  mov     [rsp+190h+phkResult], rcx; phkResult
0x140012223  mov     r9d, 20019h; samDesired
0x140012229  xor     r8d, r8d; ulOptions
0x14001222c  mov     rcx, rax; hKey
0x14001222f  call    cs:__imp_RegOpenKeyExW
0x140012236  nop     dword ptr [rax+rax+00h]
0x14001223b  mov     [rsp+190h+cbData], 102h
0x140012243  lea     rax, [rsp+190h+cbData]
0x140012248  mov     [rsp+190h+lpcbData], rax; lpcbData
0x14001224d  lea     rax, [rsp+190h+Data]
0x140012252  mov     [rsp+190h+phkResult], rax; lpData
0x140012257  xor     r9d, r9d; lpType
0x14001225a  xor     r8d, r8d; lpReserved
0x14001225d  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x140012264  mov     rcx, [rsp+190h+hKey]; hKey
0x140012269  call    cs:__imp_RegQueryValueExW
0x140012270  nop     dword ptr [rax+rax+00h]
0x140012275  test    eax, eax
0x140012277  jnz     loc_140012372
0x14001227d  mov     [rsp+190h+lpMem], 0
0x140012286  mov     [rsp+190h+var_15C], eax
0x14001228a  lea     rax, [rsp+190h+lpMem]
0x14001228f  mov     [rsp+190h+var_148], rax
0x140012294  mov     [rsp+190h+var_140], 0
0x14001229d  mov     [rsp+190h+var_138], 1
0x1400122a2  lea     r9, [rsp+190h+var_15C]
0x1400122a7  lea     r8, [rsp+190h+var_140]
0x1400122ac  mov     edx, 0FDE9h
0x1400122b1  lea     rcx, [rsp+190h+Data]
0x1400122b6  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x1400122bd  nop     dword ptr [rax+rax+00h]
0x1400122c2  mov     esi, eax
0x1400122c4  cmp     [rsp+190h+var_138], 0
0x1400122c9  jz      short loc_140012300
0x1400122cb  mov     rdx, [rsp+190h+var_148]
0x1400122d0  mov     rdi, [rdx]
0x1400122d3  mov     rcx, [rsp+190h+var_140]
0x1400122d8  mov     [rdx], rcx
0x1400122db  test    rdi, rdi
0x1400122de  jz      short loc_140012300
0x1400122e0  call    cs:__imp_GetProcessHeap
0x1400122e7  nop     dword ptr [rax+rax+00h]
0x1400122ec  mov     rcx, rax; hHeap
0x1400122ef  mov     r8, rdi; lpMem
0x1400122f2  xor     edx, edx; dwFlags
0x1400122f4  call    cs:__imp_HeapFree
0x1400122fb  nop     dword ptr [rax+rax+00h]
0x140012300  mov     rdi, [rsp+190h+lpMem]
0x140012305  test    esi, esi
0x140012307  js      short loc_140012343
0x140012309  mov     eax, 7FFFFFFEh
0x14001230e  mov     rdx, rdi
0x140012311  mov     ecx, 81h
0x140012316  test    rax, rax
0x140012319  jz      short loc_140012335
0x14001231b  mov     r8b, [rdx]
0x14001231e  test    r8b, r8b
0x140012321  jz      short loc_140012335
0x140012323  inc     rdx
0x140012326  mov     [rbx], r8b
0x140012329  inc     rbx
0x14001232c  dec     rax
0x14001232f  sub     rcx, 1
0x140012333  jnz     short loc_140012316
0x140012335  lea     rax, [rbx-1]
0x140012339  test    rcx, rcx
0x14001233c  cmovnz  rax, rbx
0x140012340  mov     byte ptr [rax], 0
0x140012343  mov     [rsp+190h+lpMem], 0
0x14001234c  test    rdi, rdi
0x14001234f  jz      short loc_140012372
0x140012351  call    cs:__imp_GetProcessHeap
0x140012358  nop     dword ptr [rax+rax+00h]
0x14001235d  mov     rcx, rax; hHeap
0x140012360  mov     r8, rdi; lpMem
0x140012363  xor     edx, edx; dwFlags
0x140012365  call    cs:__imp_HeapFree
0x14001236c  nop     dword ptr [rax+rax+00h]
0x140012371  nop
0x140012372  mov     rcx, [rsp+190h+hKey]; hKey
0x140012377  test    rcx, rcx
0x14001237a  jz      short loc_140012388
0x14001237c  call    cs:__imp_RegCloseKey
0x140012383  nop     dword ptr [rax+rax+00h]
0x140012388  xor     eax, eax
0x14001238a  mov     rcx, [rbp+90h+var_20]
0x14001238e  xor     rcx, rsp; StackCookie
0x140012391  call    __security_check_cookie
0x140012396  mov     rbx, [rsp+190h+arg_0]
0x14001239e  add     rsp, 180h
0x1400123a5  pop     rdi
0x1400123a6  pop     rsi
0x1400123a7  pop     rbp
0x1400123a8  retn
```
