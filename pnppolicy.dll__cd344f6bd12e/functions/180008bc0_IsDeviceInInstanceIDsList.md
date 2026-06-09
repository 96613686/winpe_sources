# IsDeviceInInstanceIDsList

- ea: `0x180008bc0`
- end: `0x180008d78`
- name: `IsDeviceInInstanceIDsList`
- size: `440`
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
- `0x180008bc0`
- `0x18000a16e`
- `0x18000a1a0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008d4d`
- `KERNEL32!HeapFree` at `0x180008d4d`

## string_xrefs

- `0x180008c1d`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x180008c71`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x180008cc1`: `Software\Policies\Microsoft\Windows\DeviceInstall`

## pseudocode

```c
__int64 __fastcall IsDeviceInInstanceIDsList(STRSAFE_LPCWSTR pszSrc, int a2, int *a3)
{
  unsigned int v3; // edi
  int v5; // ebx
  int PolicyListStrings; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  int PolicyValue; // eax
  int v11; // ecx
  int v12; // eax
  STRSAFE_LPWSTR *v13; // r9
  size_t *pcchRemaining; // [rsp+20h] [rbp-1E8h]
  size_t v16[2]; // [rsp+30h] [rbp-1D8h] BYREF
  wchar_t pszDest[208]; // [rsp+40h] [rbp-1C8h] BYREF

  v3 = 0;
  v16[0] = 0;
  v5 = a2;
  if ( a2 )
  {
    if ( dword_1800117BC && dword_1800117B8
      || (PolicyListStrings = pSetupGetPolicyListStrings(
                                (__int64)pszSrc,
                                L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                                (__int64)a3,
                                L"DenyInstanceIDs",
                                (wchar_t **)v16),
          PolicyListStrings == 2) )
    {
      dword_1800117BC = 1;
      dword_1800117B8 = 1;
      goto LABEL_21;
    }
    if ( PolicyListStrings )
      goto LABEL_20;
    v5 = 1;
    dword_1800117BC = 1;
    if ( a3 )
    {
      if ( dword_1800117AC )
      {
        v11 = dword_1800117A8;
      }
      else
      {
        PolicyValue = pSetupGetPolicyValue(
                        v8,
                        L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                        v9,
                        L"DenyInstanceIDsRetroactive",
                        0,
                        1u);
        dword_1800117AC = 1;
        v11 = PolicyValue == 1;
        dword_1800117A8 = v11;
      }
      *a3 = v11;
    }
  }
  else
  {
    if ( dword_1800117B4 && dword_1800117B0
      || (v12 = pSetupGetPolicyListStrings(
                  (__int64)pszSrc,
                  L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                  (__int64)a3,
                  L"AllowInstanceIDs",
                  (wchar_t **)v16),
          v12 == 2) )
    {
      dword_1800117B4 = 1;
      dword_1800117B0 = 1;
      goto LABEL_21;
    }
    if ( v12 )
      goto LABEL_20;
    v5 = 1;
    dword_1800117B4 = 1;
  }
  memset_0(pszDest, 0, 0x192u);
  if ( StringCchCopyExW(pszDest, 0xC8u, pszSrc, v13, pcchRemaining, 0x800u) >= 0
    && (unsigned int)IsAnyStringInList((LPCWCH)v16[0], pszDest, 0) )
  {
LABEL_20:
    v3 = v5;
  }
LABEL_21:
  if ( v16[0] )
    HeapFree(hHeap, 0, (LPVOID)v16[0]);
  return v3;
}

```

## disassembly

```asm
0x180008bc0  mov     [rsp+arg_8], rbx
0x180008bc5  push    rbp
0x180008bc6  push    rsi
0x180008bc7  push    rdi
0x180008bc8  sub     rsp, 1F0h
0x180008bcf  mov     rax, cs:__security_cookie
0x180008bd6  xor     rax, rsp
0x180008bd9  mov     [rsp+208h+var_28], rax
0x180008be1  xor     edi, edi
0x180008be3  mov     [rsp+208h+var_1D8], 0
0x180008bec  mov     rsi, r8
0x180008bef  mov     ebx, edx
0x180008bf1  mov     rbp, rcx
0x180008bf4  test    edx, edx
0x180008bf6  jz      loc_180008CA0
0x180008bfc  cmp     cs:dword_1800117BC, edi
0x180008c02  jz      short loc_180008C0C
0x180008c04  cmp     cs:dword_1800117B8, edi
0x180008c0a  jnz     short loc_180008C2E
0x180008c0c  lea     rax, [rsp+208h+var_1D8]
0x180008c11  lea     r9, aDenyinstanceid; "DenyInstanceIDs"
0x180008c18  mov     [rsp+208h+pcchRemaining], rax
0x180008c1d  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008c24  call    pSetupGetPolicyListStrings
0x180008c29  cmp     eax, 2
0x180008c2c  jnz     short loc_180008C44
0x180008c2e  mov     ebx, 1
0x180008c33  mov     cs:dword_1800117BC, ebx
0x180008c39  mov     cs:dword_1800117B8, ebx
0x180008c3f  jmp     loc_180008D3A
0x180008c44  test    eax, eax
0x180008c46  jnz     loc_180008D38
0x180008c4c  lea     ebx, [rax+1]
0x180008c4f  mov     cs:dword_1800117BC, ebx
0x180008c55  test    rsi, rsi
0x180008c58  jz      loc_180008CF2
0x180008c5e  cmp     cs:dword_1800117AC, edi
0x180008c64  jnz     short loc_180008C96
0x180008c66  mov     [rsp+208h+dwFlags], ebx
0x180008c6a  lea     r9, aDenyinstanceid_0; "DenyInstanceIDsRetroactive"
0x180008c71  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008c78  mov     dword ptr [rsp+208h+pcchRemaining], edi
0x180008c7c  call    pSetupGetPolicyValue
0x180008c81  xor     ecx, ecx
0x180008c83  mov     cs:dword_1800117AC, ebx
0x180008c89  cmp     eax, ebx
0x180008c8b  setz    cl
0x180008c8e  mov     cs:dword_1800117A8, ecx
0x180008c94  jmp     short loc_180008C9C
0x180008c96  mov     ecx, cs:dword_1800117A8
0x180008c9c  mov     [rsi], ecx
0x180008c9e  jmp     short loc_180008CF2
0x180008ca0  cmp     cs:dword_1800117B4, edi
0x180008ca6  jz      short loc_180008CB0
0x180008ca8  cmp     cs:dword_1800117B0, edi
0x180008cae  jnz     short loc_180008CD2
0x180008cb0  lea     rax, [rsp+208h+var_1D8]
0x180008cb5  lea     r9, aAllowinstancei; "AllowInstanceIDs"
0x180008cbc  mov     [rsp+208h+pcchRemaining], rax; pcchRemaining
0x180008cc1  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008cc8  call    pSetupGetPolicyListStrings
0x180008ccd  cmp     eax, 2
0x180008cd0  jnz     short loc_180008CE5
0x180008cd2  mov     ebx, 1
0x180008cd7  mov     cs:dword_1800117B4, ebx
0x180008cdd  mov     cs:dword_1800117B0, ebx
0x180008ce3  jmp     short loc_180008D3A
0x180008ce5  test    eax, eax
0x180008ce7  jnz     short loc_180008D38
0x180008ce9  lea     ebx, [rax+1]
0x180008cec  mov     cs:dword_1800117B4, ebx
0x180008cf2  xor     edx, edx; Val
0x180008cf4  lea     rcx, [rsp+208h+pszDest]; void *
0x180008cf9  mov     r8d, 192h; Size
0x180008cff  call    memset_0
0x180008d04  mov     r8, rbp; pszSrc
0x180008d07  mov     [rsp+208h+dwFlags], 800h; dwFlags
0x180008d0f  mov     edx, 0C8h; cchDest
0x180008d14  lea     rcx, [rsp+208h+pszDest]; pszDest
0x180008d19  call    StringCchCopyExW
0x180008d1e  test    eax, eax
0x180008d20  js      short loc_180008D3A
0x180008d22  mov     rcx, [rsp+208h+var_1D8]; lpString1
0x180008d27  lea     rdx, [rsp+208h+pszDest]; lpString2
0x180008d2c  xor     r8d, r8d
0x180008d2f  call    IsAnyStringInList
0x180008d34  test    eax, eax
0x180008d36  jz      short loc_180008D3A
0x180008d38  mov     edi, ebx
0x180008d3a  mov     r8, [rsp+208h+var_1D8]; lpMem
0x180008d3f  test    r8, r8
0x180008d42  jz      short loc_180008D53
0x180008d44  mov     rcx, cs:hHeap; hHeap
0x180008d4b  xor     edx, edx; dwFlags
0x180008d4d  call    cs:__imp_HeapFree
0x180008d53  mov     eax, edi
0x180008d55  mov     rcx, [rsp+208h+var_28]
0x180008d5d  xor     rcx, rsp; StackCookie
0x180008d60  call    __security_check_cookie
0x180008d65  mov     rbx, [rsp+208h+arg_8]
0x180008d6d  add     rsp, 1F0h
0x180008d74  pop     rdi
0x180008d75  pop     rsi
0x180008d76  pop     rbp
0x180008d77  retn
```
