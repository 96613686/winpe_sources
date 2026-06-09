# PlaliDeleteW(ushort const *,ushort const *)

- ea: `0x18012edd0`
- end: `0x18012f04a`
- name: `?PlaliDeleteW@@YAJPEBG0@Z`
- size: `634`
- prototype: `__int64 __fastcall(wchar_t *String2, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800aced0`
- `0x18012ec18`

## callees

- `0x18012e71c`
- `0x18012edd0`
- `0x18012f320`
- `0x180130e30`
- `0x18013161c`
- `0x18013167c`
- `0x1801317fc`
- `0x180132c88`
- `0x180132f38`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18012ef19`
- `msvcrt!_wcsicmp` at `0x18012ef57`
- `msvcrt!_wcsicmp` at `0x18012ef19`
- `msvcrt!_wcsicmp` at `0x18012ef57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012eefa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012eefa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ef6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012efc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f00e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ef6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012efc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f00e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012ee6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012ee6c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18012efce`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18012efce`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18012eed1`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18012eed1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012eea5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012eea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012ee96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012efdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012efef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012ee96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012efdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012efef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012efe9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012effd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012efe9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012effd`

## pseudocode

```c
__int64 __fastcall PlaliDeleteW(wchar_t *String2, unsigned __int16 *a2)
{
  DWORD v2; // r14d
  LSTATUS v6; // edi
  unsigned __int16 *v7; // r15
  DWORD v8; // r13d
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rbx
  const wchar_t *v11; // rcx
  const wchar_t *v12; // rcx
  HANDLE v13; // rax
  HANDLE v14; // rax
  HKEY hKey; // [rsp+60h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v17; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D0h] [rbp+50h] BYREF
  DWORD cSubKeys; // [rsp+D8h] [rbp+58h] BYREF

  v2 = 0;
  hKey = 0;
  if ( !String2 )
    return 3221228477LL;
  v6 = 0;
  if ( !(unsigned int)PlaliConnectToRegistry(a2, &hKey, 1, 1) )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v6 )
    {
      v7 = 0;
      v17 = 0;
      v18 = 0;
      phkResult = 0;
      v8 = 2 * cbMaxSubKeyLen + 2;
      ProcessHeap = GetProcessHeap();
      v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v8);
      if ( v10 )
      {
        while ( v2 < cSubKeys )
        {
          v6 = RegEnumKeyW(hKey, v2, v10, v8 >> 1);
          if ( !v6 )
          {
            v6 = RegOpenKeyExW(hKey, v10, 0, 0x2001Fu, &phkResult);
            if ( v6 )
              break;
            if ( !(unsigned int)PlaliIsStringEmpty(v10) )
            {
              if ( !_wcsicmp(v11, String2)
                || (PlaliReadRegistryStringValue(phkResult, L"Collection Name", 1u, &v17, &v18),
                    v7 = v17,
                    !(unsigned int)PlaliIsStringEmpty(v17))
                && !_wcsicmp(v12, String2) )
              {
                v18 = 0;
                v6 = PlaliReadRegistryDwordValue(phkResult, L"Current State", &v18);
                if ( !v6 )
                {
                  if ( v18 != 1 || (PlaliGetServiceState(a2, &v18), v18 == 1) )
                  {
                    RegCloseKey(phkResult);
                    v6 = RegDeleteKeyW(hKey, v10);
                  }
                  else
                  {
                    v6 = 1056;
                  }
                }
                break;
              }
              v6 = 2;
            }
            if ( phkResult )
              RegCloseKey(phkResult);
          }
          ++v2;
        }
        if ( v7 )
        {
          v13 = GetProcessHeap();
          HeapFree(v13, 0, v7);
        }
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v10);
      }
      else
      {
        v6 = 14;
      }
    }
    RegCloseKey(hKey);
    if ( !v6 )
    {
      PlaliSynchronize(a2);
      PlaliUpdateServiceMode(a2);
    }
  }
  return PlaliErrorToPdhStatus(v6);
}

```

## disassembly

```asm
0x18012edd0  mov     [rsp-38h+arg_8], rbx
0x18012edd5  push    rbp
0x18012edd6  push    rsi
0x18012edd7  push    rdi
0x18012edd8  push    r12
0x18012edda  push    r13
0x18012eddc  push    r14
0x18012edde  push    r15
0x18012ede0  mov     rbp, rsp
0x18012ede3  sub     rsp, 80h
0x18012edea  xor     r14d, r14d
0x18012eded  mov     rsi, rdx
0x18012edf0  mov     [rbp+hKey], r14
0x18012edf4  mov     r12, rcx
0x18012edf7  test    rcx, rcx
0x18012edfa  jnz     short loc_18012EE06
0x18012edfc  mov     eax, 0C0000BBDh
0x18012ee01  jmp     loc_18012F02F
0x18012ee06  mov     eax, 1
0x18012ee0b  lea     rdx, [rbp+hKey]; HKEY *
0x18012ee0f  mov     r9d, eax; int
0x18012ee12  mov     r8d, eax; int
0x18012ee15  mov     rcx, rsi; lpMachineName
0x18012ee18  mov     edi, r14d
0x18012ee1b  call    ?PlaliConnectToRegistry@@YAJPEBGAEAPEAUHKEY__@@HH@Z; PlaliConnectToRegistry(ushort const *,HKEY__ * &,int,int)
0x18012ee20  test    eax, eax
0x18012ee22  jnz     loc_18012F028
0x18012ee28  mov     rcx, [rbp+hKey]; hKey
0x18012ee2c  lea     rax, [rbp+cbMaxSubKeyLen]
0x18012ee30  mov     [rsp+80h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18012ee35  xor     r9d, r9d; lpReserved
0x18012ee38  mov     [rsp+80h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18012ee3d  xor     r8d, r8d; lpcchClass
0x18012ee40  mov     [rsp+80h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18012ee45  xor     edx, edx; lpClass
0x18012ee47  mov     [rsp+80h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18012ee4c  mov     [rsp+80h+lpcValues], r14; lpcValues
0x18012ee51  mov     [rsp+80h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18012ee56  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18012ee5b  lea     rax, [rbp+cSubKeys]
0x18012ee5f  mov     [rsp+80h+lpcSubKeys], rax; lpcSubKeys
0x18012ee64  mov     [rbp+cSubKeys], r14d
0x18012ee68  mov     [rbp+cbMaxSubKeyLen], r14d
0x18012ee6c  call    cs:__imp_RegQueryInfoKeyW
0x18012ee72  mov     edi, eax
0x18012ee74  test    eax, eax
0x18012ee76  jnz     loc_18012F00A
0x18012ee7c  mov     ecx, [rbp+cbMaxSubKeyLen]
0x18012ee7f  mov     r15, r14
0x18012ee82  mov     [rbp+var_10], r14
0x18012ee86  mov     [rbp+arg_0], r14d
0x18012ee8a  mov     [rbp+phkResult], r14
0x18012ee8e  lea     r13d, ds:2[rcx*2]
0x18012ee96  call    cs:__imp_GetProcessHeap
0x18012ee9c  mov     r8d, r13d; dwBytes
0x18012ee9f  lea     edx, [rdi+8]; dwFlags
0x18012eea2  mov     rcx, rax; hHeap
0x18012eea5  call    cs:__imp_HeapAlloc
0x18012eeab  mov     rbx, rax
0x18012eeae  test    rax, rax
0x18012eeb1  jz      loc_18012F005
0x18012eeb7  cmp     r14d, [rbp+cSubKeys]
0x18012eebb  jnb     loc_18012EFD6
0x18012eec1  mov     rcx, [rbp+hKey]; hKey
0x18012eec5  mov     r9d, r13d
0x18012eec8  shr     r9d, 1; cchName
0x18012eecb  mov     r8, rbx; lpName
0x18012eece  mov     edx, r14d; dwIndex
0x18012eed1  call    cs:__imp_RegEnumKeyW
0x18012eed7  mov     edi, eax
0x18012eed9  test    eax, eax
0x18012eedb  jnz     loc_18012EF75
0x18012eee1  mov     rcx, [rbp+hKey]; hKey
0x18012eee5  lea     rax, [rbp+phkResult]
0x18012eee9  mov     r9d, 2001Fh; samDesired
0x18012eeef  mov     [rsp+80h+lpcSubKeys], rax; phkResult
0x18012eef4  xor     r8d, r8d; ulOptions
0x18012eef7  mov     rdx, rbx; lpSubKey
0x18012eefa  call    cs:__imp_RegOpenKeyExW
0x18012ef00  mov     edi, eax
0x18012ef02  test    eax, eax
0x18012ef04  jnz     loc_18012EFD6
0x18012ef0a  mov     rcx, rbx; unsigned __int16 *
0x18012ef0d  call    ?PlaliIsStringEmpty@@YAHPEBG@Z; PlaliIsStringEmpty(ushort const *)
0x18012ef12  test    eax, eax
0x18012ef14  jnz     short loc_18012EF66
0x18012ef16  mov     rdx, r12; String2
0x18012ef19  call    cs:__imp__wcsicmp
0x18012ef1f  test    eax, eax
0x18012ef21  jz      short loc_18012EF7D
0x18012ef23  mov     rcx, [rbp+phkResult]; hKey
0x18012ef27  lea     rax, [rbp+arg_0]
0x18012ef2b  lea     r9, [rbp+var_10]; unsigned __int16 **
0x18012ef2f  mov     [rsp+80h+lpcSubKeys], rax; unsigned int *
0x18012ef34  lea     r8d, [rdi+1]; unsigned int
0x18012ef38  lea     rdx, aCollectionName; "Collection Name"
0x18012ef3f  call    ?PlaliReadRegistryStringValue@@YAJPEAUHKEY__@@PEBGKPEAPEAGPEAK@Z; PlaliReadRegistryStringValue(HKEY__ *,ushort const *,ulong,ushort * *,ulong *)
0x18012ef44  mov     r15, [rbp+var_10]
0x18012ef48  mov     rcx, r15; unsigned __int16 *
0x18012ef4b  call    ?PlaliIsStringEmpty@@YAHPEBG@Z; PlaliIsStringEmpty(ushort const *)
0x18012ef50  test    eax, eax
0x18012ef52  jnz     short loc_18012EF61
0x18012ef54  mov     rdx, r12; String2
0x18012ef57  call    cs:__imp__wcsicmp
0x18012ef5d  test    eax, eax
0x18012ef5f  jz      short loc_18012EF7D
0x18012ef61  mov     edi, 2
0x18012ef66  mov     rcx, [rbp+phkResult]; hKey
0x18012ef6a  test    rcx, rcx
0x18012ef6d  jz      short loc_18012EF75
0x18012ef6f  call    cs:__imp_RegCloseKey
0x18012ef75  inc     r14d
0x18012ef78  jmp     loc_18012EEB7
0x18012ef7d  mov     rcx, [rbp+phkResult]; hKey
0x18012ef81  lea     r8, [rbp+arg_0]; unsigned int *
0x18012ef85  xor     r14d, r14d
0x18012ef88  lea     rdx, aCurrentState; "Current State"
0x18012ef8f  mov     [rbp+arg_0], r14d
0x18012ef93  call    ?PlaliReadRegistryDwordValue@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaliReadRegistryDwordValue(HKEY__ *,ushort const *,ulong *)
0x18012ef98  mov     edi, eax
0x18012ef9a  test    eax, eax
0x18012ef9c  jnz     short loc_18012EFD6
0x18012ef9e  cmp     [rbp+arg_0], 1
0x18012efa2  jnz     short loc_18012EFBD
0x18012efa4  lea     rdx, [rbp+arg_0]; unsigned int *
0x18012efa8  mov     rcx, rsi; unsigned __int16 *
0x18012efab  call    ?PlaliGetServiceState@@YAKPEBGPEAK@Z; PlaliGetServiceState(ushort const *,ulong *)
0x18012efb0  cmp     [rbp+arg_0], 1
0x18012efb4  jz      short loc_18012EFBD
0x18012efb6  mov     edi, 420h
0x18012efbb  jmp     short loc_18012EFD6
0x18012efbd  mov     rcx, [rbp+phkResult]; hKey
0x18012efc1  call    cs:__imp_RegCloseKey
0x18012efc7  mov     rcx, [rbp+hKey]; hKey
0x18012efcb  mov     rdx, rbx; lpSubKey
0x18012efce  call    cs:__imp_RegDeleteKeyW
0x18012efd4  mov     edi, eax
0x18012efd6  test    r15, r15
0x18012efd9  jz      short loc_18012EFEF
0x18012efdb  call    cs:__imp_GetProcessHeap
0x18012efe1  mov     r8, r15; lpMem
0x18012efe4  xor     edx, edx; dwFlags
0x18012efe6  mov     rcx, rax; hHeap
0x18012efe9  call    cs:__imp_HeapFree
0x18012efef  call    cs:__imp_GetProcessHeap
0x18012eff5  mov     r8, rbx; lpMem
0x18012eff8  xor     edx, edx; dwFlags
0x18012effa  mov     rcx, rax; hHeap
0x18012effd  call    cs:__imp_HeapFree
0x18012f003  jmp     short loc_18012F00A
0x18012f005  mov     edi, 0Eh
0x18012f00a  mov     rcx, [rbp+hKey]; hKey
0x18012f00e  call    cs:__imp_RegCloseKey
0x18012f014  test    edi, edi
0x18012f016  jnz     short loc_18012F028
0x18012f018  mov     rcx, rsi; unsigned __int16 *
0x18012f01b  call    ?PlaliSynchronize@@YAJPEBG@Z; PlaliSynchronize(ushort const *)
0x18012f020  mov     rcx, rsi; unsigned __int16 *
0x18012f023  call    ?PlaliUpdateServiceMode@@YAKPEBG@Z; PlaliUpdateServiceMode(ushort const *)
0x18012f028  mov     ecx, edi; unsigned int
0x18012f02a  call    ?PlaliErrorToPdhStatus@@YAJK@Z; PlaliErrorToPdhStatus(ulong)
0x18012f02f  mov     rbx, [rsp+80h+arg_8]
0x18012f037  add     rsp, 80h
0x18012f03e  pop     r15
0x18012f040  pop     r14
0x18012f042  pop     r13
0x18012f044  pop     r12
0x18012f046  pop     rdi
0x18012f047  pop     rsi
0x18012f048  pop     rbp
0x18012f049  retn
```
