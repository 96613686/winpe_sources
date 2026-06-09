# IsClassInDeviceAllowList

- ea: `0x1800086bc`
- end: `0x1800087be`
- name: `IsClassInDeviceAllowList`
- size: `258`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008d80`

## callees

- `0x180003b40`
- `0x180003cf8`
- `0x18000859c`
- `0x1800086bc`
- `0x18000a16e`
- `0x18000a1a0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008795`
- `KERNEL32!HeapFree` at `0x180008795`

## string_xrefs

- `0x18000870a`: `Software\Policies\Microsoft\Windows\DeviceInstall`

## pseudocode

```c
_BOOL8 __fastcall IsClassInDeviceAllowList(STRSAFE_LPCWSTR pszSrc, __int64 a2, __int64 a3)
{
  int PolicyListStrings; // eax
  BOOL v5; // ebx
  STRSAFE_LPWSTR *v6; // r9
  HRESULT v7; // eax
  size_t *pcchRemaining; // [rsp+20h] [rbp-88h]
  size_t v10; // [rsp+30h] [rbp-78h] BYREF
  wchar_t pszDest[40]; // [rsp+40h] [rbp-68h] BYREF

  v10 = 0;
  if ( `IsClassInDeviceAllowList'::`2'::PolicyListCheckInit && `IsClassInDeviceAllowList'::`2'::PolicyListNotFound
    || (PolicyListStrings = pSetupGetPolicyListStrings(
                              (__int64)pszSrc,
                              L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                              a3,
                              L"AllowDeviceClasses",
                              (wchar_t **)&v10),
        PolicyListStrings == 2) )
  {
    `IsClassInDeviceAllowList'::`2'::PolicyListCheckInit = 1;
    `IsClassInDeviceAllowList'::`2'::PolicyListNotFound = 1;
LABEL_5:
    v5 = 0;
    goto LABEL_9;
  }
  if ( PolicyListStrings )
    goto LABEL_5;
  `IsClassInDeviceAllowList'::`2'::PolicyListCheckInit = 1;
  memset_0(pszDest, 0, sizeof(pszDest));
  v7 = StringCchCopyExW(pszDest, 0x27u, pszSrc, v6, pcchRemaining, 0x800u);
  v5 = 0;
  if ( v7 >= 0 )
    v5 = IsAnyStringInList((LPCWCH)v10, pszDest, 0) != 0;
LABEL_9:
  if ( v10 )
    HeapFree(hHeap, 0, (LPVOID)v10);
  return v5;
}

```

## disassembly

```asm
0x1800086bc  mov     [rsp+arg_8], rbx
0x1800086c1  push    rdi
0x1800086c2  sub     rsp, 0A0h
0x1800086c9  mov     rax, cs:__security_cookie
0x1800086d0  xor     rax, rsp
0x1800086d3  mov     [rsp+0A8h+var_18], rax
0x1800086db  cmp     cs:?PolicyListCheckInit@?1??IsClassInDeviceAllowList@@9@9, 0; `IsClassInDeviceAllowList'::`2'::PolicyListCheckInit
0x1800086e2  mov     rbx, rcx
0x1800086e5  mov     [rsp+0A8h+var_78], 0
0x1800086ee  jz      short loc_1800086F9
0x1800086f0  cmp     cs:?PolicyListNotFound@?1??IsClassInDeviceAllowList@@9@9, 0; `IsClassInDeviceAllowList'::`2'::PolicyListNotFound
0x1800086f7  jnz     short loc_18000871B
0x1800086f9  lea     rax, [rsp+0A8h+var_78]
0x1800086fe  lea     r9, aAllowdevicecla; "AllowDeviceClasses"
0x180008705  mov     [rsp+0A8h+pcchRemaining], rax; pcchRemaining
0x18000870a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008711  call    pSetupGetPolicyListStrings
0x180008716  cmp     eax, 2
0x180008719  jnz     short loc_180008730
0x18000871b  mov     edi, 1
0x180008720  mov     cs:?PolicyListCheckInit@?1??IsClassInDeviceAllowList@@9@9, edi; `IsClassInDeviceAllowList'::`2'::PolicyListCheckInit
0x180008726  mov     cs:?PolicyListNotFound@?1??IsClassInDeviceAllowList@@9@9, edi; `IsClassInDeviceAllowList'::`2'::PolicyListNotFound
0x18000872c  xor     ebx, ebx
0x18000872e  jmp     short loc_180008782
0x180008730  test    eax, eax
0x180008732  jnz     short loc_18000872C
0x180008734  lea     edi, [rax+1]
0x180008737  xor     edx, edx; Val
0x180008739  lea     r8d, [rax+50h]; Size
0x18000873d  mov     cs:?PolicyListCheckInit@?1??IsClassInDeviceAllowList@@9@9, edi; `IsClassInDeviceAllowList'::`2'::PolicyListCheckInit
0x180008743  lea     rcx, [rsp+0A8h+pszDest]; void *
0x180008748  call    memset_0
0x18000874d  mov     r8, rbx; pszSrc
0x180008750  mov     [rsp+0A8h+dwFlags], 800h; dwFlags
0x180008758  lea     edx, [rdi+26h]; cchDest
0x18000875b  lea     rcx, [rsp+0A8h+pszDest]; pszDest
0x180008760  call    StringCchCopyExW
0x180008765  xor     ebx, ebx
0x180008767  test    eax, eax
0x180008769  js      short loc_180008782
0x18000876b  mov     rcx, [rsp+0A8h+var_78]; lpString1
0x180008770  lea     rdx, [rsp+0A8h+pszDest]; lpString2
0x180008775  xor     r8d, r8d
0x180008778  call    IsAnyStringInList
0x18000877d  test    eax, eax
0x18000877f  cmovnz  ebx, edi
0x180008782  mov     r8, [rsp+0A8h+var_78]; lpMem
0x180008787  test    r8, r8
0x18000878a  jz      short loc_18000879B
0x18000878c  mov     rcx, cs:hHeap; hHeap
0x180008793  xor     edx, edx; dwFlags
0x180008795  call    cs:__imp_HeapFree
0x18000879b  mov     eax, ebx
0x18000879d  mov     rcx, [rsp+0A8h+var_18]
0x1800087a5  xor     rcx, rsp; StackCookie
0x1800087a8  call    __security_check_cookie
0x1800087ad  mov     rbx, [rsp+0A8h+arg_8]
0x1800087b5  add     rsp, 0A0h
0x1800087bc  pop     rdi
0x1800087bd  retn
```
