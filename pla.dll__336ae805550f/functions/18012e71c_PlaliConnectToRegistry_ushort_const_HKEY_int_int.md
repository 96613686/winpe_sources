# PlaliConnectToRegistry(ushort const *,HKEY__ * &,int,int)

- ea: `0x18012e71c`
- end: `0x18012e7e1`
- name: `?PlaliConnectToRegistry@@YAJPEBGAEAPEAUHKEY__@@HH@Z`
- size: `197`
- prototype: `__int64 __fastcall(LPCWSTR lpMachineName, HKEY *, int, int)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18012dc60`
- `0x18012e4e0`
- `0x18012ec18`
- `0x18012edd0`
- `0x18012f050`
- `0x18012f3c8`
- `0x18012f4b0`

## callees

- `0x180039e30`
- `0x18012e71c`
- `0x18012ea3c`
- `0x18012f320`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e7a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e7a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e7ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e7ca`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18012e763`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18012e763`

## string_xrefs

- `0x18012e793`: `System\CurrentControlSet\Services\SysmonLog`
- `0x18012e780`: `System\CurrentControlSet\Services\SysmonLog\Log Queries`

## pseudocode

```c
__int64 __fastcall PlaliConnectToRegistry(wchar_t *lpMachineName, HKEY *a2, int a3, int a4)
{
  LSTATUS Query; // ebx
  const WCHAR *v9; // rdx
  REGSAM v10; // r9d
  int v12; // [rsp+30h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-30h] BYREF

  v12 = 1;
  phkResult = HKEY_LOCAL_MACHINE;
  PlaiIsLocalServer(lpMachineName, &v12);
  if ( !v12 )
  {
    Query = RegConnectRegistryW(lpMachineName, HKEY_LOCAL_MACHINE, &phkResult);
    if ( Query )
      goto LABEL_10;
  }
  if ( a3 )
  {
    v9 = L"System\\CurrentControlSet\\Services\\SysmonLog\\Log Queries";
    if ( a4 )
    {
      v10 = 131103;
      goto LABEL_8;
    }
  }
  else
  {
    v9 = L"System\\CurrentControlSet\\Services\\SysmonLog";
  }
  v10 = 131097;
LABEL_8:
  Query = RegOpenKeyExW(phkResult, v9, 0, v10, a2);
  if ( Query )
    Query = PlaliCreateQuery(phkResult, a2);
LABEL_10:
  if ( phkResult && phkResult != HKEY_LOCAL_MACHINE )
    RegCloseKey(phkResult);
  return PlaliErrorToPdhStatus(Query);
}

```

## disassembly

```asm
0x18012e71c  push    rbx
0x18012e71e  push    rbp
0x18012e71f  push    rsi
0x18012e720  push    rdi
0x18012e721  push    r14
0x18012e723  sub     rsp, 40h
0x18012e727  mov     rdi, rdx
0x18012e72a  mov     [rsp+68h+var_38], 1
0x18012e732  mov     r14, 0FFFFFFFF80000002h
0x18012e739  lea     rdx, [rsp+68h+var_38]; int *
0x18012e73e  mov     [rsp+68h+phkResult], r14
0x18012e743  mov     esi, r9d
0x18012e746  mov     ebp, r8d
0x18012e749  mov     rbx, rcx
0x18012e74c  call    ?PlaiIsLocalServer@@YAJPEBGPEAH@Z; PlaiIsLocalServer(ushort const *,int *)
0x18012e751  cmp     [rsp+68h+var_38], 0
0x18012e756  jnz     short loc_18012E76F
0x18012e758  lea     r8, [rsp+68h+phkResult]; phkResult
0x18012e75d  mov     rdx, r14; hKey
0x18012e760  mov     rcx, rbx; lpMachineName
0x18012e763  call    cs:__imp_RegConnectRegistryW
0x18012e769  mov     ebx, eax
0x18012e76b  test    eax, eax
0x18012e76d  jnz     short loc_18012E7BB
0x18012e76f  mov     rcx, [rsp+68h+phkResult]; hKey
0x18012e774  xor     r8d, r8d; ulOptions
0x18012e777  mov     [rsp+68h+var_48], rdi; phkResult
0x18012e77c  test    ebp, ebp
0x18012e77e  jz      short loc_18012E793
0x18012e780  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sy"...
0x18012e787  test    esi, esi
0x18012e789  jz      short loc_18012E79A
0x18012e78b  mov     r9d, 2001Fh
0x18012e791  jmp     short loc_18012E7A0
0x18012e793  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sy"...
0x18012e79a  mov     r9d, 20019h; samDesired
0x18012e7a0  call    cs:__imp_RegOpenKeyExW
0x18012e7a6  mov     ebx, eax
0x18012e7a8  test    eax, eax
0x18012e7aa  jz      short loc_18012E7BB
0x18012e7ac  mov     rcx, [rsp+68h+phkResult]; HKEY
0x18012e7b1  mov     rdx, rdi; HKEY *
0x18012e7b4  call    ?PlaliCreateQuery@@YAKPEAUHKEY__@@AEAPEAU1@@Z; PlaliCreateQuery(HKEY__ *,HKEY__ * &)
0x18012e7b9  mov     ebx, eax
0x18012e7bb  mov     rcx, [rsp+68h+phkResult]; hKey
0x18012e7c0  test    rcx, rcx
0x18012e7c3  jz      short loc_18012E7D0
0x18012e7c5  cmp     rcx, r14
0x18012e7c8  jz      short loc_18012E7D0
0x18012e7ca  call    cs:__imp_RegCloseKey
0x18012e7d0  mov     ecx, ebx; unsigned int
0x18012e7d2  add     rsp, 40h
0x18012e7d6  pop     r14
0x18012e7d8  pop     rdi
0x18012e7d9  pop     rsi
0x18012e7da  pop     rbp
0x18012e7db  pop     rbx
0x18012e7dc  jmp     ?PlaliErrorToPdhStatus@@YAJK@Z; PlaliErrorToPdhStatus(ulong)
```
