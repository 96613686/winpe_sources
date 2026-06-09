# CUMRDPListenerInet::GetAdapterIndexFromId(ulong,ulong *)

- ea: `0x18003c5a4`
- end: `0x18003c798`
- name: `?GetAdapterIndexFromId@CUMRDPListenerInet@@AEAAHKPEAK@Z`
- size: `500`
- prototype: `__int64 __fastcall(CUMRDPListenerInet *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003ef10`

## callees

- `0x180009088`
- `0x180033da0`
- `0x18003c5a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c6d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c6d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c6fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c70b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c6fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c70b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003c65a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003c65a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c602`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c68e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c602`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c68e`
- `IPHLPAPI!GetAdapterIndex` at `0x18003c75b`
- `IPHLPAPI!GetAdapterIndex` at `0x18003c75b`

## pseudocode

```c
_BOOL8 __fastcall CUMRDPListenerInet::GetAdapterIndexFromId(CUMRDPListenerInet *this, int a2, unsigned int *a3)
{
  BOOL v4; // ebx
  DWORD i; // edi
  unsigned int *v6; // rsi
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v14; // [rsp+68h] [rbp-98h]
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR AdapterName[264]; // [rsp+280h] [rbp+180h] BYREF

  v14 = a3;
  v4 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Terminal Server\\lanatable",
          0,
          0x20019u,
          &hKey) )
  {
    for ( i = 0; !v4; ++i )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
        break;
      phkResult = 0;
      if ( RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
        break;
      *(_DWORD *)Data = 0;
      cbData = 4;
      Type = 4;
      if ( !RegQueryValueExW(phkResult, L"LanaId", 0, &Type, Data, &cbData) && cbData == 4 && Type == 4 )
        v4 = *(_DWORD *)Data == a2;
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
    v6 = v14;
    if ( v4 )
    {
      *(_DWORD *)Data = 0;
      if ( (int)StringCchPrintfW(AdapterName, 0x104u, L"%s%s", L"\\Device\\TCPIP_", Name) < 0
        || GetAdapterIndex(AdapterName, (PULONG)Data) )
      {
        return 0;
      }
      else
      {
        *v6 = *(_DWORD *)Data;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003c5a4  mov     [rsp-8+arg_0], rbx
0x18003c5a9  mov     [rsp-8+arg_8], rsi
0x18003c5ae  push    rbp
0x18003c5af  push    rdi
0x18003c5b0  push    r14
0x18003c5b2  lea     rbp, [rsp-3A0h]
0x18003c5ba  sub     rsp, 4A0h
0x18003c5c1  mov     rax, cs:__security_cookie
0x18003c5c8  xor     rax, rsp
0x18003c5cb  mov     [rbp+3B0h+var_20], rax
0x18003c5d2  mov     [rsp+4B0h+var_448], r8
0x18003c5d7  lea     rax, [rsp+4B0h+hKey]
0x18003c5dc  mov     r14d, edx
0x18003c5df  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18003c5e4  xor     ebx, ebx
0x18003c5e6  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x18003c5ed  xor     r8d, r8d; ulOptions
0x18003c5f0  mov     [rsp+4B0h+hKey], rbx
0x18003c5f5  mov     r9d, 20019h; samDesired
0x18003c5fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c602  call    cs:__imp_RegOpenKeyExW
0x18003c608  test    eax, eax
0x18003c60a  jnz     loc_18003C76F
0x18003c610  xor     edi, edi
0x18003c612  lea     esi, [rbx+1]
0x18003c615  test    ebx, ebx
0x18003c617  jnz     loc_18003C706
0x18003c61d  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18003c622  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x18003c627  mov     [rsp+4B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18003c630  lea     r8, [rsp+4B0h+Name]; lpName
0x18003c635  mov     [rsp+4B0h+lpcchClass], 0; lpcchClass
0x18003c63e  mov     edx, edi; dwIndex
0x18003c640  mov     [rsp+4B0h+lpClass], 0; lpClass
0x18003c649  mov     [rsp+4B0h+phkResult], 0; lpReserved
0x18003c652  mov     [rsp+4B0h+cchName], 104h
0x18003c65a  call    cs:__imp_RegEnumKeyExW
0x18003c660  test    eax, eax
0x18003c662  jnz     loc_18003C706
0x18003c668  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18003c66d  lea     rax, [rsp+4B0h+var_450]
0x18003c672  mov     r9d, 20019h; samDesired
0x18003c678  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18003c67d  xor     r8d, r8d; ulOptions
0x18003c680  mov     [rsp+4B0h+var_450], 0
0x18003c689  lea     rdx, [rsp+4B0h+Name]; lpSubKey
0x18003c68e  call    cs:__imp_RegOpenKeyExW
0x18003c694  test    eax, eax
0x18003c696  jnz     short loc_18003C706
0x18003c698  mov     rcx, [rsp+4B0h+var_450]; hKey
0x18003c69d  lea     r9, [rsp+4B0h+Type]; lpType
0x18003c6a2  mov     dword ptr [rsp+4B0h+Data], eax
0x18003c6a6  lea     rdx, aLanaid; "LanaId"
0x18003c6ad  lea     rax, [rsp+4B0h+cbData]
0x18003c6b2  mov     [rsp+4B0h+cbData], 4
0x18003c6ba  mov     [rsp+4B0h+lpClass], rax; lpcbData
0x18003c6bf  xor     r8d, r8d; lpReserved
0x18003c6c2  lea     rax, [rsp+4B0h+Data]
0x18003c6c7  mov     [rsp+4B0h+Type], 4
0x18003c6cf  mov     [rsp+4B0h+phkResult], rax; lpData
0x18003c6d4  add     edi, esi
0x18003c6d6  call    cs:__imp_RegQueryValueExW
0x18003c6dc  test    eax, eax
0x18003c6de  jnz     short loc_18003C6F6
0x18003c6e0  cmp     [rsp+4B0h+cbData], 4
0x18003c6e5  jnz     short loc_18003C6F6
0x18003c6e7  cmp     [rsp+4B0h+Type], 4
0x18003c6ec  jnz     short loc_18003C6F6
0x18003c6ee  cmp     dword ptr [rsp+4B0h+Data], r14d
0x18003c6f3  cmovz   ebx, esi
0x18003c6f6  mov     rcx, [rsp+4B0h+var_450]; hKey
0x18003c6fb  call    cs:__imp_RegCloseKey
0x18003c701  jmp     loc_18003C615
0x18003c706  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18003c70b  call    cs:__imp_RegCloseKey
0x18003c711  mov     rsi, [rsp+4B0h+var_448]
0x18003c716  test    ebx, ebx
0x18003c718  jz      short loc_18003C76F
0x18003c71a  lea     rax, [rsp+4B0h+Name]
0x18003c71f  mov     dword ptr [rsp+4B0h+Data], 0
0x18003c727  lea     r9, aDeviceTcpip; "\\Device\\TCPIP_"
0x18003c72e  mov     [rsp+4B0h+phkResult], rax
0x18003c733  lea     r8, aSS_0; "%s%s"
0x18003c73a  mov     edx, 104h; unsigned __int64
0x18003c73f  lea     rcx, [rbp+3B0h+AdapterName]; unsigned __int16 *
0x18003c746  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c74b  test    eax, eax
0x18003c74d  js      short loc_18003C76D
0x18003c74f  lea     rdx, [rsp+4B0h+Data]; IfIndex
0x18003c754  lea     rcx, [rbp+3B0h+AdapterName]; AdapterName
0x18003c75b  call    cs:__imp_GetAdapterIndex
0x18003c761  test    eax, eax
0x18003c763  jnz     short loc_18003C76D
0x18003c765  mov     eax, dword ptr [rsp+4B0h+Data]
0x18003c769  mov     [rsi], eax
0x18003c76b  jmp     short loc_18003C76F
0x18003c76d  xor     ebx, ebx
0x18003c76f  mov     eax, ebx
0x18003c771  mov     rcx, [rbp+3B0h+var_20]
0x18003c778  xor     rcx, rsp; StackCookie
0x18003c77b  call    __security_check_cookie
0x18003c780  lea     r11, [rsp+4B0h+var_10]
0x18003c788  mov     rbx, [r11+20h]
0x18003c78c  mov     rsi, [r11+28h]
0x18003c790  mov     rsp, r11
0x18003c793  pop     r14
0x18003c795  pop     rdi
0x18003c796  pop     rbp
0x18003c797  retn
```
