# AccessRouterSubkey

- ea: `0x180017700`
- end: `0x1800178a3`
- name: `AccessRouterSubkey`
- size: `419`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180022324`
- `0x180022b50`
- `0x180022be8`
- `0x180023210`
- `0x1800236e0`
- `0x180023e40`
- `0x180025e20`
- `0x1800276c0`
- `0x180027da0`
- `0x180028100`

## callees

- `0x180016c40`
- `0x180017700`
- `0x180021d50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017874`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017874`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001779f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001779f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017882`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001786e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001786e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017809`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017830`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017809`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017830`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001785c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001785c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001776e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001777d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001776e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001777d`

## string_xrefs

- `0x180017774`: `System\CurrentControlSet\Services`
- `0x1800177c9`: `System\CurrentControlSet\Services`
- `0x180017767`: `RemoteAccess`
- `0x1800177bd`: `RemoteAccess`

## pseudocode

```c
__int64 __fastcall AccessRouterSubkey(HKEY hKey, LPCWSTR lpSubKey, int a3, HKEY *a4)
{
  __int64 result; // rax
  const wchar_t *v9; // r14
  const WCHAR *v10; // rcx
  int v11; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v13; // rsi
  unsigned int v14; // ebx
  LSTATUS v15; // eax
  HANDLE v16; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-48h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-40h] BYREF
  unsigned __int64 v19; // [rsp+60h] [rbp-38h]
  int v20; // [rsp+B8h] [rbp+20h] BYREF

  hKeya = 0;
  dwDisposition = 0;
  v20 = 0;
  if ( !a4 )
    return 87;
  *a4 = 0;
  result = IsNt40Machine(hKey, &v20);
  if ( !(_DWORD)result )
  {
    v9 = L"Router";
    v10 = L"Router";
    if ( !v20 )
      v10 = L"RemoteAccess";
    v11 = lstrlenW(v10);
    v19 = (unsigned int)(lstrlenW(L"System\\CurrentControlSet\\Services") + v11 + 2);
    ProcessHeap = GetProcessHeap();
    v13 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v19);
    if ( v13 )
    {
      if ( !v20 )
        v9 = L"RemoteAccess";
      StringCchPrintfW(v13, v19, L"%s\\%s", L"System\\CurrentControlSet\\Services", v9);
      hKeya = 0;
      v14 = RegOpenKeyExW(hKey, v13, 0, 0x2001Fu, &hKeya);
      if ( !v14 )
      {
        if ( a3 )
          v15 = RegCreateKeyExW(hKeya, lpSubKey, 0, 0, 0, 0x2001Fu, 0, a4, &dwDisposition);
        else
          v15 = RegOpenKeyExW(hKeya, lpSubKey, 0, 0x2001Fu, a4);
        v14 = v15;
      }
      if ( hKeya )
        RegCloseKey(hKeya);
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v13);
      return v14;
    }
    else
    {
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017700  mov     rax, rsp
0x180017703  mov     [rax+8], rbx
0x180017707  mov     [rax+10h], rbp
0x18001770b  push    rsi
0x18001770c  push    rdi
0x18001770d  push    r12
0x18001770f  push    r13
0x180017711  push    r14
0x180017713  sub     rsp, 70h
0x180017717  xor     ebx, ebx
0x180017719  mov     rdi, r9
0x18001771c  mov     [rax-40h], rbx
0x180017720  mov     r13d, r8d
0x180017723  mov     [rax-48h], ebx
0x180017726  mov     rbp, rdx
0x180017729  mov     [rax+20h], ebx
0x18001772c  mov     r12, rcx
0x18001772f  test    r9, r9
0x180017732  jnz     short loc_18001773C
0x180017734  lea     eax, [rbx+57h]
0x180017737  jmp     loc_18001788A
0x18001773c  lea     rdx, [rsp+98h+arg_18]
0x180017744  mov     [r9], rbx
0x180017747  call    IsNt40Machine
0x18001774c  test    eax, eax
0x18001774e  jnz     loc_18001788A
0x180017754  lea     r14, c_szRouter; "Router"
0x18001775b  mov     rcx, r14
0x18001775e  cmp     [rsp+98h+arg_18], ebx
0x180017765  jnz     short loc_18001776E
0x180017767  lea     rcx, c_szRemoteAccess; "RemoteAccess"
0x18001776e  call    cs:__imp_lstrlenW
0x180017774  lea     rcx, c_szSystemCCSServices; "System\\CurrentControlSet\\Services"
0x18001777b  mov     ebx, eax
0x18001777d  call    cs:__imp_lstrlenW
0x180017783  add     ebx, eax
0x180017785  lea     eax, [rbx+2]
0x180017788  mov     [rsp+98h+var_38], rax
0x18001778d  lea     rbx, [rax+rax]
0x180017791  call    cs:__imp_GetProcessHeap
0x180017797  mov     r8, rbx; dwBytes
0x18001779a  xor     edx, edx; dwFlags
0x18001779c  mov     rcx, rax; hHeap
0x18001779f  call    cs:__imp_HeapAlloc
0x1800177a5  mov     rsi, rax
0x1800177a8  test    rax, rax
0x1800177ab  jnz     short loc_1800177B5
0x1800177ad  lea     eax, [rsi+8]
0x1800177b0  jmp     loc_18001788A
0x1800177b5  cmp     [rsp+98h+arg_18], 0
0x1800177bd  lea     rax, c_szRemoteAccess; "RemoteAccess"
0x1800177c4  mov     rdx, [rsp+98h+var_38]; unsigned __int64
0x1800177c9  lea     r9, c_szSystemCCSServices; "System\\CurrentControlSet\\Services"
0x1800177d0  cmovz   r14, rax
0x1800177d4  lea     r8, aSS_0; "%s\\%s"
0x1800177db  mov     rcx, rsi; unsigned __int16 *
0x1800177de  mov     [rsp+98h+phkResult], r14
0x1800177e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800177e8  lea     rax, [rsp+98h+hKey]
0x1800177ed  xor     r14d, r14d
0x1800177f0  mov     r9d, 2001Fh; samDesired
0x1800177f6  mov     [rsp+98h+phkResult], rax; phkResult
0x1800177fb  xor     r8d, r8d; ulOptions
0x1800177fe  mov     [rsp+98h+hKey], r14
0x180017803  mov     rdx, rsi; lpSubKey
0x180017806  mov     rcx, r12; hKey
0x180017809  call    cs:__imp_RegOpenKeyExW
0x18001780f  mov     ebx, eax
0x180017811  test    eax, eax
0x180017813  jnz     short loc_180017864
0x180017815  mov     rcx, [rsp+98h+hKey]; hKey
0x18001781a  xor     r8d, r8d; Reserved
0x18001781d  mov     rdx, rbp; lpSubKey
0x180017820  test    r13d, r13d
0x180017823  jnz     short loc_180017838
0x180017825  mov     r9d, 2001Fh; samDesired
0x18001782b  mov     [rsp+98h+phkResult], rdi; phkResult
0x180017830  call    cs:__imp_RegOpenKeyExW
0x180017836  jmp     short loc_180017862
0x180017838  lea     rax, [rsp+98h+dwDisposition]
0x18001783d  xor     r9d, r9d; lpClass
0x180017840  mov     [rsp+98h+lpdwDisposition], rax; lpdwDisposition
0x180017845  mov     [rsp+98h+var_60], rdi; phkResult
0x18001784a  mov     [rsp+98h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001784f  mov     [rsp+98h+samDesired], 2001Fh; samDesired
0x180017857  mov     dword ptr [rsp+98h+phkResult], r14d; dwOptions
0x18001785c  call    cs:__imp_RegCreateKeyExW
0x180017862  mov     ebx, eax
0x180017864  mov     rcx, [rsp+98h+hKey]; hKey
0x180017869  test    rcx, rcx
0x18001786c  jz      short loc_180017874
0x18001786e  call    cs:__imp_RegCloseKey
0x180017874  call    cs:__imp_GetProcessHeap
0x18001787a  mov     r8, rsi; lpMem
0x18001787d  xor     edx, edx; dwFlags
0x18001787f  mov     rcx, rax; hHeap
0x180017882  call    cs:__imp_HeapFree
0x180017888  mov     eax, ebx
0x18001788a  lea     r11, [rsp+98h+var_28]
0x18001788f  mov     rbx, [r11+30h]
0x180017893  mov     rbp, [r11+38h]
0x180017897  mov     rsp, r11
0x18001789a  pop     r14
0x18001789c  pop     r13
0x18001789e  pop     r12
0x1800178a0  pop     rdi
0x1800178a1  pop     rsi
0x1800178a2  retn
```
