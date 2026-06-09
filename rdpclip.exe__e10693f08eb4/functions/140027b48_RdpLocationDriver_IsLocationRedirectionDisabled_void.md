# RdpLocationDriver::IsLocationRedirectionDisabled(void)

- ea: `0x140027b48`
- end: `0x140027c86`
- name: `?IsLocationRedirectionDisabled@RdpLocationDriver@@AEAAHXZ`
- size: `318`
- prototype: `__int64 __fastcall(RdpLocationDriver *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140027f18`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140027b48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140027c75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140027c75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140027b81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140027b81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140027bc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140027bc0`

## string_xrefs

- `0x140027b71`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
_BOOL8 __fastcall RdpLocationDriver::IsLocationRedirectionDisabled(RdpLocationDriver *this)
{
  bool v1; // bl
  int v2; // edi
  unsigned int v3; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  RdpLocationDriver *Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Type = this;
  hKey = 0;
  v1 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0,
         0x20019u,
         &hKey) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_984f9dcecce8362309603129c531ec25_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
  else
  {
    Data = 0;
    LODWORD(Type) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"fDisableLocationRedir", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData)
      && (_DWORD)Type == 4 )
    {
      v2 = Data;
      v1 = Data != 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v3 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_984f9dcecce8362309603129c531ec25_Traceguids, v3, v2);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x140027b48  mov     [rsp-18h+Type], rcx
0x140027b4d  push    rbp
0x140027b4e  push    rbx
0x140027b4f  push    rdi
0x140027b50  mov     rbp, rsp
0x140027b53  sub     rsp, 30h
0x140027b57  lea     rax, [rbp+hKey]
0x140027b5b  mov     [rbp+hKey], 0
0x140027b63  mov     r9d, 20019h; samDesired
0x140027b69  mov     [rsp+30h+phkResult], rax; phkResult
0x140027b6e  xor     r8d, r8d; ulOptions
0x140027b71  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x140027b78  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140027b7f  xor     bl, bl
0x140027b81  call    cs:__imp_RegOpenKeyExW
0x140027b87  test    eax, eax
0x140027b89  jnz     loc_140027C29
0x140027b8f  mov     rcx, [rbp+hKey]; hKey
0x140027b93  lea     r9, [rbp+Type]; lpType
0x140027b97  mov     [rbp+Data], eax
0x140027b9a  lea     rdx, aFdisablelocati; "fDisableLocationRedir"
0x140027ba1  mov     dword ptr [rbp+Type], eax
0x140027ba4  xor     r8d, r8d; lpReserved
0x140027ba7  lea     rax, [rbp+cbData]
0x140027bab  mov     [rbp+cbData], 4
0x140027bb2  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140027bb7  lea     rax, [rbp+Data]
0x140027bbb  mov     [rsp+30h+phkResult], rax; lpData
0x140027bc0  call    cs:__imp_RegQueryValueExW
0x140027bc6  test    eax, eax
0x140027bc8  jnz     loc_140027C6C
0x140027bce  cmp     dword ptr [rbp+Type], 4
0x140027bd2  jnz     loc_140027C6C
0x140027bd8  mov     edi, [rbp+Data]
0x140027bdb  test    edi, edi
0x140027bdd  setnz   bl
0x140027be0  mov     rax, cs:WPP_GLOBAL_Control
0x140027be7  lea     rcx, WPP_GLOBAL_Control
0x140027bee  cmp     rax, rcx
0x140027bf1  jz      short loc_140027C6C
0x140027bf3  test    byte ptr [rax+1Ch], 1
0x140027bf7  jz      short loc_140027C6C
0x140027bf9  cmp     byte ptr [rax+19h], 4
0x140027bfd  jb      short loc_140027C6C
0x140027bff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140027c04  mov     rcx, cs:WPP_GLOBAL_Control
0x140027c0b  lea     r8, WPP_984f9dcecce8362309603129c531ec25_Traceguids
0x140027c12  mov     edx, 1Eh
0x140027c17  mov     dword ptr [rsp+30h+phkResult], edi
0x140027c1b  mov     r9d, eax
0x140027c1e  mov     rcx, [rcx+10h]
0x140027c22  call    WPP_SF_Dd
0x140027c27  jmp     short loc_140027C6C
0x140027c29  mov     rax, cs:WPP_GLOBAL_Control
0x140027c30  lea     rcx, WPP_GLOBAL_Control
0x140027c37  cmp     rax, rcx
0x140027c3a  jz      short loc_140027C6C
0x140027c3c  test    byte ptr [rax+1Ch], 1
0x140027c40  jz      short loc_140027C6C
0x140027c42  cmp     byte ptr [rax+19h], 4
0x140027c46  jb      short loc_140027C6C
0x140027c48  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140027c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140027c54  lea     r8, WPP_984f9dcecce8362309603129c531ec25_Traceguids
0x140027c5b  mov     edx, 1Fh
0x140027c60  mov     r9d, eax
0x140027c63  mov     rcx, [rcx+10h]
0x140027c67  call    WPP_SF_d
0x140027c6c  mov     rcx, [rbp+hKey]; hKey
0x140027c70  test    rcx, rcx
0x140027c73  jz      short loc_140027C7B
0x140027c75  call    cs:__imp_RegCloseKey
0x140027c7b  movzx   eax, bl
0x140027c7e  add     rsp, 30h
0x140027c82  pop     rdi
0x140027c83  pop     rbx
0x140027c84  pop     rbp
0x140027c85  retn
```
