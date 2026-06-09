# IsClassInDeviceDenyList

- ea: `0x1800087c4`
- end: `0x180008924`
- name: `IsClassInDeviceDenyList`
- size: `352`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008d80`

## callees

- `0x180003b40`
- `0x180003cf8`
- `0x1800040d8`
- `0x18000859c`
- `0x1800087c4`
- `0x18000a16e`
- `0x18000a1a0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800088f7`
- `KERNEL32!HeapFree` at `0x1800088f7`

## string_xrefs

- `0x18000881a`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x18000886e`: `Software\Policies\Microsoft\Windows\DeviceInstall`

## pseudocode

```c
_BOOL8 __fastcall IsClassInDeviceDenyList(STRSAFE_LPCWSTR pszSrc, int *a2, __int64 a3)
{
  int PolicyListStrings; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  BOOL v8; // edi
  int PolicyValue; // eax
  int v10; // ecx
  STRSAFE_LPWSTR *v11; // r9
  size_t *pcchRemaining; // [rsp+20h] [rbp-88h]
  size_t v14; // [rsp+30h] [rbp-78h] BYREF
  wchar_t pszDest[40]; // [rsp+40h] [rbp-68h] BYREF

  v14 = 0;
  if ( `IsClassInDeviceDenyList'::`2'::PolicyListCheckInit && `IsClassInDeviceDenyList'::`2'::PolicyListNotFound
    || (PolicyListStrings = pSetupGetPolicyListStrings(
                              (__int64)pszSrc,
                              L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                              a3,
                              L"DenyDeviceClasses",
                              (wchar_t **)&v14),
        PolicyListStrings == 2) )
  {
    `IsClassInDeviceDenyList'::`2'::PolicyListCheckInit = 1;
    `IsClassInDeviceDenyList'::`2'::PolicyListNotFound = 1;
    v8 = 0;
  }
  else
  {
    v8 = 1;
    if ( !PolicyListStrings )
    {
      `IsClassInDeviceDenyList'::`2'::PolicyListCheckInit = 1;
      if ( a2 )
      {
        if ( `IsClassInDeviceDenyList'::`2'::PolicyRetroactiveInit )
        {
          v10 = `IsClassInDeviceDenyList'::`2'::PolicyRetroactiveResult;
        }
        else
        {
          PolicyValue = pSetupGetPolicyValue(
                          v6,
                          L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                          v7,
                          L"DenyDeviceClassesRetroactive",
                          0,
                          1u);
          `IsClassInDeviceDenyList'::`2'::PolicyRetroactiveInit = 1;
          v10 = PolicyValue == 1;
          `IsClassInDeviceDenyList'::`2'::PolicyRetroactiveResult = v10;
        }
        *a2 = v10;
      }
      memset_0(pszDest, 0, sizeof(pszDest));
      if ( StringCchCopyExW(pszDest, 0x27u, pszSrc, v11, pcchRemaining, 0x800u) >= 0 )
        v8 = IsAnyStringInList((LPCWCH)v14, pszDest, 0) != 0;
    }
  }
  if ( v14 )
    HeapFree(hHeap, 0, (LPVOID)v14);
  return v8;
}

```

## disassembly

```asm
0x1800087c4  mov     [rsp+arg_10], rbx
0x1800087c9  mov     [rsp+arg_18], rsi
0x1800087ce  push    rdi
0x1800087cf  sub     rsp, 0A0h
0x1800087d6  mov     rax, cs:__security_cookie
0x1800087dd  xor     rax, rsp
0x1800087e0  mov     [rsp+0A8h+var_18], rax
0x1800087e8  cmp     cs:?PolicyListCheckInit@?1??IsClassInDeviceDenyList@@9@9, 0; `IsClassInDeviceDenyList'::`2'::PolicyListCheckInit
0x1800087ef  mov     rbx, rdx
0x1800087f2  mov     rsi, rcx
0x1800087f5  mov     [rsp+0A8h+var_78], 0
0x1800087fe  jz      short loc_180008809
0x180008800  cmp     cs:?PolicyListNotFound@?1??IsClassInDeviceDenyList@@9@9, 0; `IsClassInDeviceDenyList'::`2'::PolicyListNotFound
0x180008807  jnz     short loc_18000882B
0x180008809  lea     rax, [rsp+0A8h+var_78]
0x18000880e  lea     r9, aDenydeviceclas_0; "DenyDeviceClasses"
0x180008815  mov     [rsp+0A8h+pcchRemaining], rax; pcchRemaining
0x18000881a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008821  call    pSetupGetPolicyListStrings
0x180008826  cmp     eax, 2
0x180008829  jnz     short loc_180008843
0x18000882b  mov     edi, 1
0x180008830  mov     cs:?PolicyListCheckInit@?1??IsClassInDeviceDenyList@@9@9, edi; `IsClassInDeviceDenyList'::`2'::PolicyListCheckInit
0x180008836  mov     cs:?PolicyListNotFound@?1??IsClassInDeviceDenyList@@9@9, edi; `IsClassInDeviceDenyList'::`2'::PolicyListNotFound
0x18000883c  xor     edi, edi
0x18000883e  jmp     loc_1800088E4
0x180008843  mov     edi, 1
0x180008848  test    eax, eax
0x18000884a  jnz     loc_1800088E4
0x180008850  mov     cs:?PolicyListCheckInit@?1??IsClassInDeviceDenyList@@9@9, edi; `IsClassInDeviceDenyList'::`2'::PolicyListCheckInit
0x180008856  test    rbx, rbx
0x180008859  jz      short loc_18000889B
0x18000885b  cmp     cs:?PolicyRetroactiveInit@?1??IsClassInDeviceDenyList@@9@9, eax; `IsClassInDeviceDenyList'::`2'::PolicyRetroactiveInit
0x180008861  jnz     short loc_180008893
0x180008863  mov     [rsp+0A8h+dwFlags], edi
0x180008867  lea     r9, aDenydeviceclas; "DenyDeviceClassesRetroactive"
0x18000886e  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008875  mov     dword ptr [rsp+0A8h+pcchRemaining], eax
0x180008879  call    pSetupGetPolicyValue
0x18000887e  xor     ecx, ecx
0x180008880  mov     cs:?PolicyRetroactiveInit@?1??IsClassInDeviceDenyList@@9@9, edi; `IsClassInDeviceDenyList'::`2'::PolicyRetroactiveInit
0x180008886  cmp     eax, edi
0x180008888  setz    cl
0x18000888b  mov     cs:?PolicyRetroactiveResult@?1??IsClassInDeviceDenyList@@9@9, ecx; `IsClassInDeviceDenyList'::`2'::PolicyRetroactiveResult
0x180008891  jmp     short loc_180008899
0x180008893  mov     ecx, cs:?PolicyRetroactiveResult@?1??IsClassInDeviceDenyList@@9@9; `IsClassInDeviceDenyList'::`2'::PolicyRetroactiveResult
0x180008899  mov     [rbx], ecx
0x18000889b  xor     edx, edx; Val
0x18000889d  lea     rcx, [rsp+0A8h+pszDest]; void *
0x1800088a2  lea     r8d, [rdx+50h]; Size
0x1800088a6  call    memset_0
0x1800088ab  mov     r8, rsi; pszSrc
0x1800088ae  mov     [rsp+0A8h+dwFlags], 800h; dwFlags
0x1800088b6  mov     edx, 27h ; '''; cchDest
0x1800088bb  lea     rcx, [rsp+0A8h+pszDest]; pszDest
0x1800088c0  call    StringCchCopyExW
0x1800088c5  test    eax, eax
0x1800088c7  js      short loc_1800088E4
0x1800088c9  mov     rcx, [rsp+0A8h+var_78]; lpString1
0x1800088ce  lea     rdx, [rsp+0A8h+pszDest]; lpString2
0x1800088d3  xor     r8d, r8d
0x1800088d6  xor     ebx, ebx
0x1800088d8  call    IsAnyStringInList
0x1800088dd  test    eax, eax
0x1800088df  cmovnz  ebx, edi
0x1800088e2  mov     edi, ebx
0x1800088e4  mov     r8, [rsp+0A8h+var_78]; lpMem
0x1800088e9  test    r8, r8
0x1800088ec  jz      short loc_1800088FD
0x1800088ee  mov     rcx, cs:hHeap; hHeap
0x1800088f5  xor     edx, edx; dwFlags
0x1800088f7  call    cs:__imp_HeapFree
0x1800088fd  mov     eax, edi
0x1800088ff  mov     rcx, [rsp+0A8h+var_18]
0x180008907  xor     rcx, rsp; StackCookie
0x18000890a  call    __security_check_cookie
0x18000890f  lea     r11, [rsp+0A8h+var_8]
0x180008917  mov     rbx, [r11+20h]
0x18000891b  mov     rsi, [r11+28h]
0x18000891f  mov     rsp, r11
0x180008922  pop     rdi
0x180008923  retn
```
