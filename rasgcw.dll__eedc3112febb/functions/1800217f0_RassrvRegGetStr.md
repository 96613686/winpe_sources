# RassrvRegGetStr

- ea: `0x1800217f0`
- end: `0x1800218d6`
- name: `RassrvRegGetStr`
- size: `230`
- prototype: `__int64 __usercall@<rax>(size_t *pcchRemaining@<rcx>, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800286e8`
- `0x180028afc`

## callees

- `0x1800217f0`
- `0x180021c04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800218be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800218be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002183a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002183a`
- `rtutils!TracePrintfExA` at `0x1800218ab`
- `rtutils!TracePrintfExA` at `0x1800218ab`
- `KERNEL32!RegQueryValueExW` at `0x180021867`
- `KERNEL32!RegQueryValueExW` at `0x180021867`

## string_xrefs

- `0x1800218a1`: `RassrvRegGetStr: StringCchCopyExW failed. hr = 0x%x`

## pseudocode

```c
__int64 __fastcall RassrvRegGetStr(
        BYTE *pcchRemaining,
        __int64 a2,
        const wchar_t *a3,
        const WCHAR *a4,
        LPCWSTR lpValueName)
{
  unsigned int v7; // ebx
  STRSAFE_LPWSTR *v8; // r9
  HRESULT v9; // eax
  unsigned __int16 v10; // di
  size_t *lpData; // [rsp+20h] [rbp-28h]
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF

  Type = 1;
  cbData = 257;
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a4, 0, 0x20019u, &hKey);
  if ( !v7 )
  {
    v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, pcchRemaining, &cbData);
    if ( v7 )
    {
      v7 = 0;
      v9 = StringCchCopyExW((STRSAFE_LPWSTR)pcchRemaining, 0x101u, a3, v8, lpData, 0x900u);
      v10 = v9;
      if ( v9 < 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "RassrvRegGetStr: StringCchCopyExW failed. hr = 0x%x", v9);
        v7 = v10;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x1800217f0  mov     rax, rsp
0x1800217f3  mov     [rax+8], rbx
0x1800217f7  mov     [rax+18h], rsi
0x1800217fb  mov     [rax+10h], edx
0x1800217fe  push    rdi
0x1800217ff  sub     rsp, 40h
0x180021803  mov     rdi, rcx
0x180021806  mov     dword ptr [rax-18h], 1
0x18002180d  lea     rcx, [rax-10h]
0x180021811  mov     dword ptr [rax+10h], 101h
0x180021818  mov     [rax-28h], rcx
0x18002181c  mov     rdx, r9; lpSubKey
0x18002181f  mov     rsi, r8
0x180021822  mov     qword ptr [rax-10h], 0
0x18002182a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021831  mov     r9d, 20019h; samDesired
0x180021837  xor     r8d, r8d; ulOptions
0x18002183a  call    cs:__imp_RegOpenKeyExW
0x180021840  mov     ebx, eax
0x180021842  test    eax, eax
0x180021844  jnz     short loc_1800218B4
0x180021846  mov     rdx, [rsp+48h+lpValueName]; lpValueName
0x18002184b  lea     rax, [rsp+48h+cbData]
0x180021850  mov     rcx, [rsp+48h+hKey]; hKey
0x180021855  lea     r9, [rsp+48h+Type]; lpType
0x18002185a  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002185f  xor     r8d, r8d; lpReserved
0x180021862  mov     [rsp+48h+lpData], rdi; pcchRemaining
0x180021867  call    cs:__imp_RegQueryValueExW
0x18002186d  mov     ebx, eax
0x18002186f  test    eax, eax
0x180021871  jz      short loc_1800218B4
0x180021873  mov     r8, rsi; pszSrc
0x180021876  mov     dword ptr [rsp+48h+lpcbData], 900h; dwFlags
0x18002187e  mov     edx, 101h; cchDest
0x180021883  mov     rcx, rdi; pszDest
0x180021886  xor     ebx, ebx
0x180021888  call    StringCchCopyExW
0x18002188d  mov     edi, eax
0x18002188f  test    eax, eax
0x180021891  jns     short loc_1800218B4
0x180021893  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180021899  cmp     ecx, 0FFFFFFFFh
0x18002189c  jz      short loc_1800218B1
0x18002189e  mov     r9d, eax
0x1800218a1  lea     r8, aRassrvreggetst; "RassrvRegGetStr: StringCchCopyExW faile"...
0x1800218a8  lea     edx, [rbx+0Ch]; dwFlags
0x1800218ab  call    cs:__imp_TracePrintfExA
0x1800218b1  movzx   ebx, di
0x1800218b4  mov     rcx, [rsp+48h+hKey]; hKey
0x1800218b9  test    rcx, rcx
0x1800218bc  jz      short loc_1800218C4
0x1800218be  call    cs:__imp_RegCloseKey
0x1800218c4  mov     rsi, [rsp+48h+arg_10]
0x1800218c9  mov     eax, ebx
0x1800218cb  mov     rbx, [rsp+48h+arg_0]
0x1800218d0  add     rsp, 40h
0x1800218d4  pop     rdi
0x1800218d5  retn
```
