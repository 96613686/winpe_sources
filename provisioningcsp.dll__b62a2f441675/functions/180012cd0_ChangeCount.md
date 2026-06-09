# ChangeCount

- ea: `0x180012cd0`
- end: `0x180012eb2`
- name: `ChangeCount`
- size: `482`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e6e0`
- `0x180012ec0`

## callees

- `0x180006974`
- `0x180009eb0`
- `0x180012cd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012d2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012d2f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012e28`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012e28`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012dbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012dbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e8b`

## pseudocode

```c
__int64 __fastcall ChangeCount(int a1, unsigned int *a2)
{
  unsigned int v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // ecx
  HKEY v11; // rcx
  unsigned int dwOptions; // [rsp+20h] [rbp-40h]
  int dwOptionsa; // [rsp+20h] [rbp-40h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned int Data; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  hKey = 0;
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 1u, 0x2001Fu, 0, &hKey, 0);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x12,
           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\rebootrequest.cpp",
           (const char *)v4,
           dwOptions);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\rebootrequest.cpp",
        (const char *)(unsigned int)v5,
        dwOptionsa);
LABEL_4:
      if ( hKey )
        RegCloseKey(hKey);
      return v6;
    }
  }
  Data = 0;
  cbData = 4;
  v8 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)&Data, &cbData);
  if ( v8 == 2 )
  {
    if ( a1 == 1 )
    {
      Data = 1;
      goto LABEL_17;
    }
LABEL_11:
    v9 = 36;
LABEL_12:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v9,
           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\rebootrequest.cpp",
           (const char *)v8,
           dwOptionsb);
    goto LABEL_4;
  }
  if ( v8 )
    goto LABEL_11;
  if ( Data > 0x7FFFFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\rebootrequest.cpp",
      (const char *)0x80070216LL,
      dwOptionsb);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942934LL;
  }
  v10 = 0;
  if ( (int)(a1 + Data) >= 0 )
    v10 = a1 + Data;
  Data = v10;
LABEL_17:
  v8 = RegSetValueExW(hKey, 0, 0, 4u, (const BYTE *)&Data, cbData);
  if ( v8 )
  {
    v9 = 50;
    goto LABEL_12;
  }
  v11 = hKey;
  *a2 = Data;
  if ( v11 )
    RegCloseKey(v11);
  return 0;
}

```

## disassembly

```asm
0x180012cd0  mov     r11, rsp
0x180012cd3  mov     [r11+8], rbx
0x180012cd7  mov     [r11+10h], rsi
0x180012cdb  push    rbp
0x180012cdc  push    rdi
0x180012cdd  push    r15
0x180012cdf  mov     rbp, rsp
0x180012ce2  sub     rsp, 60h
0x180012ce6  mov     qword ptr [r11-38h], 0
0x180012cee  lea     rax, [rbp+hKey]
0x180012cf2  mov     [r11-40h], rax
0x180012cf6  mov     rsi, rdx
0x180012cf9  mov     rdx, cs:lpSubKey; lpSubKey
0x180012d00  mov     edi, ecx
0x180012d02  mov     qword ptr [r11-48h], 0
0x180012d0a  xor     r9d, r9d; lpClass
0x180012d0d  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x180012d15  xor     r8d, r8d; Reserved
0x180012d18  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012d1f  mov     [rsp+60h+dwOptions], 1; int
0x180012d27  mov     [rbp+hKey], 0
0x180012d2f  call    cs:__imp_RegCreateKeyExW
0x180012d36  nop     dword ptr [rax+rax+00h]
0x180012d3b  lea     r15, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\provcsp\\reboo"...
0x180012d42  test    eax, eax
0x180012d44  jz      short loc_180012D90
0x180012d46  mov     rcx, [rbp+18h]; this
0x180012d4a  mov     r9d, eax; char *
0x180012d4d  mov     r8, r15; unsigned int
0x180012d50  mov     edx, 12h; void *
0x180012d55  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012d5a  mov     ebx, eax
0x180012d5c  test    eax, eax
0x180012d5e  jns     short loc_180012D90
0x180012d60  mov     rcx, [rbp+18h]; this
0x180012d64  mov     r9d, eax; char *
0x180012d67  mov     r8, r15; unsigned int
0x180012d6a  mov     edx, 19h; void *
0x180012d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d74  mov     rcx, [rbp+hKey]; hKey
0x180012d78  test    rcx, rcx
0x180012d7b  jz      short loc_180012D89
0x180012d7d  call    cs:__imp_RegCloseKey
0x180012d84  nop     dword ptr [rax+rax+00h]
0x180012d89  mov     eax, ebx
0x180012d8b  jmp     loc_180012E9C
0x180012d90  mov     rcx, [rbp+hKey]; hKey
0x180012d94  lea     rax, [rbp+cbData]
0x180012d98  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180012d9d  mov     ebx, 4
0x180012da2  lea     rax, [rbp+Data]
0x180012da6  mov     [rbp+Data], 0
0x180012dad  xor     r9d, r9d; lpType
0x180012db0  mov     qword ptr [rsp+60h+dwOptions], rax; int
0x180012db5  xor     r8d, r8d; lpReserved
0x180012db8  mov     [rbp+cbData], ebx
0x180012dbb  xor     edx, edx; lpValueName
0x180012dbd  call    cs:__imp_RegQueryValueExW
0x180012dc4  nop     dword ptr [rax+rax+00h]
0x180012dc9  cmp     eax, 2
0x180012dcc  jnz     short loc_180012DD8
0x180012dce  cmp     edi, 1
0x180012dd1  jnz     short loc_180012DDC
0x180012dd3  mov     [rbp+Data], edi
0x180012dd6  jmp     short loc_180012E0C
0x180012dd8  test    eax, eax
0x180012dda  jz      short loc_180012DF4
0x180012ddc  mov     edx, 24h ; '$'; void *
0x180012de1  mov     rcx, [rbp+18h]; this
0x180012de5  mov     r8, r15; unsigned int
0x180012de8  mov     r9d, eax; char *
0x180012deb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012df0  mov     ebx, eax
0x180012df2  jmp     short loc_180012D74
0x180012df4  mov     eax, [rbp+Data]
0x180012df7  cmp     eax, 7FFFFFFFh
0x180012dfc  ja      short loc_180012E6B
0x180012dfe  xor     ecx, ecx
0x180012e00  add     eax, edi
0x180012e02  cmovns  ecx, eax
0x180012e05  test    ecx, ecx
0x180012e07  js      short loc_180012E5D
0x180012e09  mov     [rbp+Data], ecx
0x180012e0c  mov     eax, [rbp+cbData]
0x180012e0f  mov     r9d, ebx; dwType
0x180012e12  mov     rcx, [rbp+hKey]; hKey
0x180012e16  xor     r8d, r8d; Reserved
0x180012e19  mov     [rsp+60h+samDesired], eax; cbData
0x180012e1d  xor     edx, edx; lpValueName
0x180012e1f  lea     rax, [rbp+Data]
0x180012e23  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180012e28  call    cs:__imp_RegSetValueExW
0x180012e2f  nop     dword ptr [rax+rax+00h]
0x180012e34  test    eax, eax
0x180012e36  jz      short loc_180012E3F
0x180012e38  mov     edx, 32h ; '2'
0x180012e3d  jmp     short loc_180012DE1
0x180012e3f  mov     rcx, [rbp+hKey]; hKey
0x180012e43  mov     eax, [rbp+Data]
0x180012e46  mov     [rsi], eax
0x180012e48  test    rcx, rcx
0x180012e4b  jz      short loc_180012E59
0x180012e4d  call    cs:__imp_RegCloseKey
0x180012e54  nop     dword ptr [rax+rax+00h]
0x180012e59  xor     eax, eax
0x180012e5b  jmp     short loc_180012E9C
0x180012e5d  mov     [rbp+Data], 0FFFFFFFFh
0x180012e64  mov     edx, 2Fh ; '/'
0x180012e69  jmp     short loc_180012E70
0x180012e6b  mov     edx, 27h ; '''; void *
0x180012e70  mov     rcx, [rbp+18h]; this
0x180012e74  mov     r9d, 80070216h; char *
0x180012e7a  mov     r8, r15; unsigned int
0x180012e7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e82  mov     rcx, [rbp+hKey]; hKey
0x180012e86  test    rcx, rcx
0x180012e89  jz      short loc_180012E97
0x180012e8b  call    cs:__imp_RegCloseKey
0x180012e92  nop     dword ptr [rax+rax+00h]
0x180012e97  mov     eax, 80070216h
0x180012e9c  lea     r11, [rsp+60h+var_s0]
0x180012ea1  mov     rbx, [r11+20h]
0x180012ea5  mov     rsi, [r11+28h]
0x180012ea9  mov     rsp, r11
0x180012eac  pop     r15
0x180012eae  pop     rdi
0x180012eaf  pop     rbp
0x180012eb0  retn
```
