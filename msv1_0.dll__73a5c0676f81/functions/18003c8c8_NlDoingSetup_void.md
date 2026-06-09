# NlDoingSetup(void)

- ea: `0x18003c8c8`
- end: `0x18003ca86`
- name: `?NlDoingSetup@@YAEXZ`
- size: `446`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18003ef28`

## callees

- `0x18002ee7c`
- `0x18002f014`
- `0x18003c8c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003c972`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003c972`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c97e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c97e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003c90f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003c90f`

## pseudocode

```c
unsigned __int8 NlDoingSetup(void)
{
  unsigned int v0; // eax
  __int64 v1; // r9
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // edi
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  v0 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\Setup", 0, 1u, &hKey);
  v1 = v0;
  if ( v0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v3 = 14;
LABEL_17:
    WPP_SF_d(v2[2], v3, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids, v1);
    return 0;
  }
  cbData = 4;
  v4 = RegQueryValueExA(hKey, "SystemSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  if ( v4 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v3 = 15;
    v1 = v4;
    goto LABEL_17;
  }
  v1 = Type;
  if ( Type != 4 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v3 = 16;
    goto LABEL_17;
  }
  v1 = cbData;
  if ( cbData != 4 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v3 = 17;
    goto LABEL_17;
  }
  if ( Data != 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x18003c8c8  push    rbp
0x18003c8ca  push    rdi
0x18003c8cb  mov     rbp, rsp
0x18003c8ce  sub     rsp, 38h
0x18003c8d2  lea     rax, [rbp+hKey]
0x18003c8d6  mov     [rbp+hKey], 0
0x18003c8de  mov     r9d, 1; samDesired
0x18003c8e4  mov     [rsp+38h+phkResult], rax; phkResult
0x18003c8e9  xor     r8d, r8d; ulOptions
0x18003c8ec  mov     [rbp+Type], 0
0x18003c8f3  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18003c8fa  mov     [rbp+Data], 0
0x18003c901  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c908  mov     [rbp+cbData], 0
0x18003c90f  call    cs:__imp_RegOpenKeyExA
0x18003c915  mov     r9d, eax
0x18003c918  test    eax, eax
0x18003c91a  jz      short loc_18003C947
0x18003c91c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c923  lea     rax, WPP_GLOBAL_Control
0x18003c92a  cmp     rcx, rax
0x18003c92d  jz      loc_18003CA4B
0x18003c933  test    byte ptr [rcx+1Ch], 4
0x18003c937  jz      loc_18003CA4B
0x18003c93d  mov     edx, 0Eh
0x18003c942  jmp     loc_18003CA05
0x18003c947  mov     rcx, [rbp+hKey]; hKey
0x18003c94b  lea     rax, [rbp+cbData]
0x18003c94f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003c954  lea     r9, [rbp+Type]; lpType
0x18003c958  lea     rax, [rbp+Data]
0x18003c95c  mov     [rbp+cbData], 4
0x18003c963  xor     r8d, r8d; lpReserved
0x18003c966  mov     [rsp+38h+phkResult], rax; lpData
0x18003c96b  lea     rdx, ValueName; "SystemSetupInProgress"
0x18003c972  call    cs:__imp_RegQueryValueExA
0x18003c978  mov     rcx, [rbp+hKey]; hKey
0x18003c97c  mov     edi, eax
0x18003c97e  call    cs:__imp_RegCloseKey
0x18003c984  test    edi, edi
0x18003c986  jz      short loc_18003C9B3
0x18003c988  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c98f  lea     rax, WPP_GLOBAL_Control
0x18003c996  cmp     rcx, rax
0x18003c999  jz      loc_18003CA4B
0x18003c99f  test    byte ptr [rcx+1Ch], 4
0x18003c9a3  jz      loc_18003CA4B
0x18003c9a9  mov     edx, 0Fh
0x18003c9ae  mov     r9d, edi
0x18003c9b1  jmp     short loc_18003CA05
0x18003c9b3  mov     r9d, [rbp+Type]
0x18003c9b7  cmp     r9d, 4
0x18003c9bb  jz      short loc_18003C9DD
0x18003c9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9c4  lea     rax, WPP_GLOBAL_Control
0x18003c9cb  cmp     rcx, rax
0x18003c9ce  jz      short loc_18003CA4B
0x18003c9d0  test    byte ptr [rcx+1Ch], 4
0x18003c9d4  jz      short loc_18003CA4B
0x18003c9d6  mov     edx, 10h
0x18003c9db  jmp     short loc_18003CA05
0x18003c9dd  mov     r9d, [rbp+cbData]
0x18003c9e1  cmp     r9d, 4
0x18003c9e5  jz      short loc_18003CA17
0x18003c9e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9ee  lea     rax, WPP_GLOBAL_Control
0x18003c9f5  cmp     rcx, rax
0x18003c9f8  jz      short loc_18003CA4B
0x18003c9fa  test    byte ptr [rcx+1Ch], 4
0x18003c9fe  jz      short loc_18003CA4B
0x18003ca00  mov     edx, 11h
0x18003ca05  mov     rcx, [rcx+10h]
0x18003ca09  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003ca10  call    WPP_SF_d
0x18003ca15  jmp     short loc_18003CA4B
0x18003ca17  cmp     [rbp+Data], 1
0x18003ca1b  jz      short loc_18003CA4F
0x18003ca1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca24  lea     rax, WPP_GLOBAL_Control
0x18003ca2b  cmp     rcx, rax
0x18003ca2e  jz      short loc_18003CA4B
0x18003ca30  test    byte ptr [rcx+1Ch], 4
0x18003ca34  jz      short loc_18003CA4B
0x18003ca36  mov     rcx, [rcx+10h]
0x18003ca3a  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003ca41  mov     edx, 12h
0x18003ca46  call    WPP_SF_
0x18003ca4b  xor     al, al
0x18003ca4d  jmp     short loc_18003CA7F
0x18003ca4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca56  lea     rax, WPP_GLOBAL_Control
0x18003ca5d  cmp     rcx, rax
0x18003ca60  jz      short loc_18003CA7D
0x18003ca62  test    byte ptr [rcx+1Ch], 4
0x18003ca66  jz      short loc_18003CA7D
0x18003ca68  mov     rcx, [rcx+10h]
0x18003ca6c  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003ca73  mov     edx, 13h
0x18003ca78  call    WPP_SF_
0x18003ca7d  mov     al, 1
0x18003ca7f  add     rsp, 38h
0x18003ca83  pop     rdi
0x18003ca84  pop     rbp
0x18003ca85  retn
```
