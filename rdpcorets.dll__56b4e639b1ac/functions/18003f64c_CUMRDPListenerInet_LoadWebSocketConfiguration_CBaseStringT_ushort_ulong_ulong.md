# CUMRDPListenerInet::LoadWebSocketConfiguration(CBaseStringT<ushort> &,ulong &,ulong &)

- ea: `0x18003f64c`
- end: `0x18003f856`
- name: `?LoadWebSocketConfiguration@CUMRDPListenerInet@@AEAAXAEAV?$CBaseStringT@G@@AEAK1@Z`
- size: `522`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040610`
- `0x1800422e0`

## callees

- `0x180009088`
- `0x180033da0`
- `0x18003b564`
- `0x18003eec4`
- `0x18003f64c`
- `0x180041f74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f715`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f785`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f7e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f820`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f715`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f785`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f7e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f820`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f835`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f835`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f6d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f6d3`

## string_xrefs

- `0x18003f6e6`: `WebSocketUri`
- `0x18003f769`: `WebSocketUri`
- `0x18003f7ff`: `WebSocketSecurityMonitorTimeout`

## pseudocode

```c
int __fastcall CUMRDPListenerInet::LoadWebSocketConfiguration(__int64 a1, __int64 a2, _DWORD *a3, _DWORD *a4)
{
  int result; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  int IsError; // eax
  void *v11; // r9
  unsigned int v12; // r10d
  void *pvData; // rcx
  unsigned int v14; // r10d
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  result = StringCchPrintfW(
             SubKey,
             0x104u,
             L"%s\\%s",
             L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
             a1 + 128);
  if ( result < 0 )
    return result;
  hkey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hkey);
  if ( result )
    return result;
  pcbData = 0;
  if ( !RegGetValueW(hkey, 0, L"WebSocketUri", 2u, 0, 0, &pcbData) )
  {
    IsError = CBaseStringT<unsigned short>::IsError(a2, v8, v9, *(_QWORD *)(a2 + 24));
    pvData = 0;
    if ( !IsError )
      pvData = v11;
    v14 = v12 >> 1;
    if ( !v14 )
      goto LABEL_9;
    if ( (int)CBaseStringT<unsigned short>::EnsureSpace(a2, v14) >= 0 )
    {
      pvData = *(void **)(a2 + 24);
LABEL_9:
      if ( pvData )
      {
        if ( RegGetValueW(hkey, 0, L"WebSocketUri", 2u, 0, pvData, &pcbData) )
        {
          *(_DWORD *)(a2 + 16) = 0;
          *(_DWORD *)(a2 + 8) = 0;
        }
        else
        {
          CBaseStringT<unsigned short>::SetLength(a2, pcbData >> 1);
        }
      }
    }
  }
  pcbData = 4;
  if ( RegGetValueW(hkey, 0, L"WebSocketAcceptCount", 0x10u, 0, a3, &pcbData) )
    *a3 = 1;
  pcbData = 4;
  if ( RegGetValueW(hkey, 0, L"WebSocketSecurityMonitorTimeout", 0x10u, 0, a4, &pcbData) )
    *a4 = 10;
  return RegCloseKey(hkey);
}

```

## disassembly

```asm
0x18003f64c  push    rbp
0x18003f64e  push    rbx
0x18003f64f  push    rsi
0x18003f650  push    rdi
0x18003f651  lea     rbp, [rsp-178h]
0x18003f659  sub     rsp, 278h
0x18003f660  mov     rax, cs:__security_cookie
0x18003f667  xor     rax, rsp
0x18003f66a  mov     [rbp+190h+var_30], rax
0x18003f671  lea     rax, [rcx+80h]
0x18003f678  mov     rdi, r9
0x18003f67b  mov     rsi, r8
0x18003f67e  mov     [rsp+290h+phkResult], rax
0x18003f683  mov     rbx, rdx
0x18003f686  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Ter"...
0x18003f68d  lea     r8, aSS; "%s\\%s"
0x18003f694  mov     edx, 104h; unsigned __int64
0x18003f699  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x18003f69e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003f6a3  test    eax, eax
0x18003f6a5  js      loc_18003F83B
0x18003f6ab  lea     rax, [rsp+290h+hkey]
0x18003f6b0  mov     [rsp+290h+hkey], 0
0x18003f6b9  mov     r9d, 20019h; samDesired
0x18003f6bf  mov     [rsp+290h+phkResult], rax; phkResult
0x18003f6c4  xor     r8d, r8d; ulOptions
0x18003f6c7  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18003f6cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f6d3  call    cs:__imp_RegOpenKeyExW
0x18003f6d9  test    eax, eax
0x18003f6db  jnz     loc_18003F83B
0x18003f6e1  mov     rcx, [rsp+290h+hkey]; hkey
0x18003f6e6  lea     r8, Value; "WebSocketUri"
0x18003f6ed  mov     [rsp+290h+var_250], eax
0x18003f6f1  mov     r9d, 2; dwFlags
0x18003f6f7  lea     rax, [rsp+290h+var_250]
0x18003f6fc  xor     edx, edx; lpSubKey
0x18003f6fe  mov     [rsp+290h+pcbData], rax; pcbData
0x18003f703  mov     [rsp+290h+pvData], 0; pvData
0x18003f70c  mov     [rsp+290h+phkResult], 0; pdwType
0x18003f715  call    cs:__imp_RegGetValueW
0x18003f71b  test    eax, eax
0x18003f71d  jnz     loc_18003F7AD
0x18003f723  mov     r10d, [rsp+290h+var_250]
0x18003f728  mov     rcx, rbx
0x18003f72b  mov     r9, [rbx+18h]
0x18003f72f  call    ?IsError@?$CBaseStringT@G@@QEBAHXZ; CBaseStringT<ushort>::IsError(void)
0x18003f734  xor     ecx, ecx
0x18003f736  test    eax, eax
0x18003f738  cmovz   rcx, r9
0x18003f73c  shr     r10d, 1
0x18003f73f  jz      short loc_18003F754
0x18003f741  mov     edx, r10d
0x18003f744  mov     rcx, rbx
0x18003f747  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x18003f74c  test    eax, eax
0x18003f74e  js      short loc_18003F7AD
0x18003f750  mov     rcx, [rbx+18h]
0x18003f754  test    rcx, rcx
0x18003f757  jz      short loc_18003F7AD
0x18003f759  lea     rax, [rsp+290h+var_250]
0x18003f75e  mov     r9d, 2; dwFlags
0x18003f764  mov     [rsp+290h+pcbData], rax; pcbData
0x18003f769  lea     r8, Value; "WebSocketUri"
0x18003f770  mov     [rsp+290h+pvData], rcx; pvData
0x18003f775  xor     edx, edx; lpSubKey
0x18003f777  mov     rcx, [rsp+290h+hkey]; hkey
0x18003f77c  mov     [rsp+290h+phkResult], 0; pdwType
0x18003f785  call    cs:__imp_RegGetValueW
0x18003f78b  test    eax, eax
0x18003f78d  jz      short loc_18003F79F
0x18003f78f  mov     dword ptr [rbx+10h], 0
0x18003f796  mov     dword ptr [rbx+8], 0
0x18003f79d  jmp     short loc_18003F7AD
0x18003f79f  mov     edx, [rsp+290h+var_250]
0x18003f7a3  mov     rcx, rbx
0x18003f7a6  shr     edx, 1
0x18003f7a8  call    ?SetLength@?$CBaseStringT@G@@QEAAJK@Z; CBaseStringT<ushort>::SetLength(ulong)
0x18003f7ad  mov     rcx, [rsp+290h+hkey]; hkey
0x18003f7b2  lea     rax, [rsp+290h+var_250]
0x18003f7b7  mov     [rsp+290h+pcbData], rax; pcbData
0x18003f7bc  lea     r8, aWebsocketaccep; "WebSocketAcceptCount"
0x18003f7c3  mov     ebx, 4
0x18003f7c8  mov     [rsp+290h+pvData], rsi; pvData
0x18003f7cd  xor     edx, edx; lpSubKey
0x18003f7cf  mov     [rsp+290h+var_250], ebx
0x18003f7d3  mov     [rsp+290h+phkResult], 0; pdwType
0x18003f7dc  lea     r9d, [rbx+0Ch]; dwFlags
0x18003f7e0  call    cs:__imp_RegGetValueW
0x18003f7e6  test    eax, eax
0x18003f7e8  jz      short loc_18003F7F0
0x18003f7ea  mov     dword ptr [rsi], 1
0x18003f7f0  mov     rcx, [rsp+290h+hkey]; hkey
0x18003f7f5  lea     rax, [rsp+290h+var_250]
0x18003f7fa  mov     [rsp+290h+pcbData], rax; pcbData
0x18003f7ff  lea     r8, aWebsocketsecur; "WebSocketSecurityMonitorTimeout"
0x18003f806  mov     [rsp+290h+pvData], rdi; pvData
0x18003f80b  mov     r9d, 10h; dwFlags
0x18003f811  xor     edx, edx; lpSubKey
0x18003f813  mov     [rsp+290h+phkResult], 0; pdwType
0x18003f81c  mov     [rsp+290h+var_250], ebx
0x18003f820  call    cs:__imp_RegGetValueW
0x18003f826  test    eax, eax
0x18003f828  jz      short loc_18003F830
0x18003f82a  mov     dword ptr [rdi], 0Ah
0x18003f830  mov     rcx, [rsp+290h+hkey]; hKey
0x18003f835  call    cs:__imp_RegCloseKey
0x18003f83b  mov     rcx, [rbp+190h+var_30]
0x18003f842  xor     rcx, rsp; StackCookie
0x18003f845  call    __security_check_cookie
0x18003f84a  add     rsp, 278h
0x18003f851  pop     rdi
0x18003f852  pop     rsi
0x18003f853  pop     rbx
0x18003f854  pop     rbp
0x18003f855  retn
```
