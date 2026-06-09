# CreateShellSessionSubKey(ushort const *,ulong,bool *,HKEY__ * *)

- ea: `0x18009cc34`
- end: `0x18009cd24`
- name: `?CreateShellSessionSubKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, bool *, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18009fdd0`

## callees

- `0x18006ed20`
- `0x18009cb60`
- `0x18009cc34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ccf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009cd01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ccf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009cd01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009ccc9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009ccc9`

## pseudocode

```c
__int64 __fastcall CreateShellSessionSubKey(const unsigned __int16 *a1, __int64 a2, bool *a3, HKEY *a4)
{
  signed int v5; // ebx
  LSTATUS v6; // eax
  HKEY phkResult; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-18h] BYREF

  if ( a4 )
    *a4 = 0;
  hKey = 0;
  v5 = CreateShellSessionKey((unsigned int)a1, &hKey);
  if ( v5 >= 0 )
  {
    phkResult = 0;
    dwDisposition = 0;
    v6 = RegCreateKeyExW(hKey, L"DirectLaunchHandlers", 0, 0, 1u, 0x20019u, 0, &phkResult, &dwDisposition);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
      if ( a4 )
        *a4 = phkResult;
      else
        RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18009cc34  mov     [rsp+arg_0], rbx
0x18009cc39  push    rdi
0x18009cc3a  sub     rsp, 70h
0x18009cc3e  mov     rax, cs:__security_cookie
0x18009cc45  xor     rax, rsp
0x18009cc48  mov     [rsp+78h+var_10], rax
0x18009cc4d  mov     rdi, r9
0x18009cc50  test    r9, r9
0x18009cc53  jz      short loc_18009CC5C
0x18009cc55  mov     qword ptr [r9], 0
0x18009cc5c  lea     rdx, [rsp+78h+hKey]; HKEY *
0x18009cc61  mov     [rsp+78h+hKey], 0
0x18009cc6a  call    ?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z; CreateShellSessionKey(ulong,HKEY__ * *)
0x18009cc6f  mov     ebx, eax
0x18009cc71  test    eax, eax
0x18009cc73  js      loc_18009CD07
0x18009cc79  mov     rcx, [rsp+78h+hKey]; hKey
0x18009cc7e  lea     rax, [rsp+78h+dwDisposition]
0x18009cc83  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18009cc88  lea     rdx, aDirectlaunchha_0; "DirectLaunchHandlers"
0x18009cc8f  lea     rax, [rsp+78h+var_28]
0x18009cc94  mov     [rsp+78h+var_28], 0
0x18009cc9d  mov     [rsp+78h+phkResult], rax; phkResult
0x18009cca2  xor     r9d, r9d; lpClass
0x18009cca5  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009ccae  xor     r8d, r8d; Reserved
0x18009ccb1  mov     [rsp+78h+samDesired], 20019h; samDesired
0x18009ccb9  mov     [rsp+78h+dwOptions], 1; dwOptions
0x18009ccc1  mov     [rsp+78h+dwDisposition], 0
0x18009ccc9  call    cs:__imp_RegCreateKeyExW
0x18009cccf  mov     ebx, eax
0x18009ccd1  test    eax, eax
0x18009ccd3  jle     short loc_18009CCDE
0x18009ccd5  movzx   ebx, ax
0x18009ccd8  or      ebx, 80070000h
0x18009ccde  test    ebx, ebx
0x18009cce0  js      short loc_18009CCFC
0x18009cce2  test    rdi, rdi
0x18009cce5  jz      short loc_18009CCF1
0x18009cce7  mov     rax, [rsp+78h+var_28]
0x18009ccec  mov     [rdi], rax
0x18009ccef  jmp     short loc_18009CCFC
0x18009ccf1  mov     rcx, [rsp+78h+var_28]; hKey
0x18009ccf6  call    cs:__imp_RegCloseKey
0x18009ccfc  mov     rcx, [rsp+78h+hKey]; hKey
0x18009cd01  call    cs:__imp_RegCloseKey
0x18009cd07  mov     eax, ebx
0x18009cd09  mov     rcx, [rsp+78h+var_10]
0x18009cd0e  xor     rcx, rsp; StackCookie
0x18009cd11  call    __security_check_cookie
0x18009cd16  mov     rbx, [rsp+78h+arg_0]
0x18009cd1e  add     rsp, 70h
0x18009cd22  pop     rdi
0x18009cd23  retn
```
