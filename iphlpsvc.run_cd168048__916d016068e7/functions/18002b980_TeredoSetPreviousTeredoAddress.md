# TeredoSetPreviousTeredoAddress

- ea: `0x18002b980`
- end: `0x18002bb4c`
- name: `TeredoSetPreviousTeredoAddress`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a990`

## callees

- `0x18002b6dc`
- `0x18002b980`
- `0x18002bb54`
- `0x18002bc18`
- `0x180043140`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb1c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ba6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ba6c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ba3c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ba3c`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002b9f6`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002b9f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002baab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002baab`
- `WS2_32!__imp_ntohs` at `0x18002ba7f`
- `WS2_32!__imp_ntohs` at `0x18002ba7f`

## pseudocode

```c
LSTATUS __fastcall TeredoSetPreviousTeredoAddress(__int64 a1, HKEY a2, char a3)
{
  int v6; // edi
  LSTATUS result; // eax
  int v8; // r14d
  HKEY v9; // rbx
  HKEY hKey; // [rsp+30h] [rbp-79h] BYREF
  size_t pcchLength; // [rsp+38h] [rbp-71h] BYREF
  WCHAR S[72]; // [rsp+40h] [rbp-69h] BYREF

  hKey = a2;
  memset_0(S, 0, 0x82u);
  v6 = 0;
  pcchLength = 0;
  if ( a2 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    result = TeredoCreateGatewayKey(&hKey, 1);
    if ( result )
      return result;
    v6 = 1;
  }
  RtlIpv6AddressToStringW((const struct in6_addr *)(a1 + 13688), S);
  result = StringLengthWorkerW(S, 0x41u, &pcchLength);
  if ( result >= 0 )
  {
    v8 = pcchLength;
    result = -1;
    if ( pcchLength <= 0xFFFFFFFF )
    {
      v9 = hKey;
      RegDeleteValueW(hKey, L"TeredoAddress");
      RegSetValueExW(v9, L"TeredoAddress", 0, 1u, (const BYTE *)S, 2 * v8);
      ntohs(*(_WORD *)(a1 + 12766));
      SetInteger(hKey, L"ClientLocalPort");
      pcchLength = 0;
      GetSystemTimeAsFileTime((LPFILETIME)&pcchLength);
      result = SetUlongLong(hKey, L"AddressCreationTimestamp");
      if ( a3 )
      {
        if ( *(int *)(a1 + 13548) < 7 )
        {
          SetInteger(hKey, L"NatType");
          result = SetUlongLong(hKey, L"NatDetectionTimestamp");
        }
      }
    }
  }
  if ( v6 )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18002b980  mov     [rsp-8+arg_10], rbx
0x18002b985  push    rbp
0x18002b986  push    rsi
0x18002b987  push    rdi
0x18002b988  push    r14
0x18002b98a  push    r15
0x18002b98c  lea     rbp, [rsp-37h]
0x18002b991  sub     rsp, 0E0h
0x18002b998  mov     rax, cs:__security_cookie
0x18002b99f  xor     rax, rsp
0x18002b9a2  mov     [rbp+57h+var_30], rax
0x18002b9a6  mov     r15b, r8b
0x18002b9a9  mov     [rbp+57h+hKey], rdx
0x18002b9ad  mov     rbx, rdx
0x18002b9b0  mov     rsi, rcx
0x18002b9b3  xor     edx, edx; Val
0x18002b9b5  lea     rcx, [rbp+57h+S]; void *
0x18002b9b9  mov     r8d, 82h; Size
0x18002b9bf  call    memset_0
0x18002b9c4  xor     edi, edi
0x18002b9c6  mov     [rbp+57h+pcchLength], 0
0x18002b9ce  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002b9d2  jnz     short loc_18002B9EB
0x18002b9d4  lea     edx, [rbx+2]
0x18002b9d7  lea     rcx, [rbp+57h+hKey]; phkResult
0x18002b9db  call    TeredoCreateGatewayKey
0x18002b9e0  test    eax, eax
0x18002b9e2  jnz     loc_18002BB28
0x18002b9e8  lea     edi, [rbx+2]
0x18002b9eb  lea     rcx, [rsi+3578h]; Addr
0x18002b9f2  lea     rdx, [rbp+57h+S]; S
0x18002b9f6  call    cs:__imp_RtlIpv6AddressToStringW
0x18002b9fd  nop     dword ptr [rax+rax+00h]
0x18002ba02  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x18002ba06  mov     edx, 41h ; 'A'; cchMax
0x18002ba0b  lea     rcx, [rbp+57h+S]; psz
0x18002ba0f  call    StringLengthWorkerW
0x18002ba14  test    eax, eax
0x18002ba16  js      loc_18002BB14
0x18002ba1c  mov     r14, [rbp+57h+pcchLength]
0x18002ba20  mov     eax, 0FFFFFFFFh
0x18002ba25  cmp     r14, rax
0x18002ba28  ja      loc_18002BB14
0x18002ba2e  mov     rbx, [rbp+57h+hKey]
0x18002ba32  lea     rdx, aTeredoaddress; "TeredoAddress"
0x18002ba39  mov     rcx, rbx; hKey
0x18002ba3c  call    cs:__imp_RegDeleteValueW
0x18002ba43  nop     dword ptr [rax+rax+00h]
0x18002ba48  lea     eax, [r14+r14]
0x18002ba4c  mov     r9d, 1; dwType
0x18002ba52  mov     [rsp+100h+cbData], eax; cbData
0x18002ba56  lea     rdx, aTeredoaddress; "TeredoAddress"
0x18002ba5d  lea     rax, [rbp+57h+S]
0x18002ba61  xor     r8d, r8d; Reserved
0x18002ba64  mov     rcx, rbx; hKey
0x18002ba67  mov     [rsp+100h+lpData], rax; lpData
0x18002ba6c  call    cs:__imp_RegSetValueExW
0x18002ba73  nop     dword ptr [rax+rax+00h]
0x18002ba78  movzx   ecx, word ptr [rsi+31DEh]; netshort
0x18002ba7f  call    cs:__imp_ntohs
0x18002ba86  nop     dword ptr [rax+rax+00h]
0x18002ba8b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ba8f  lea     rdx, aClientlocalpor; "ClientLocalPort"
0x18002ba96  movzx   r8d, ax
0x18002ba9a  call    SetInteger
0x18002ba9f  lea     rcx, [rbp+57h+pcchLength]; lpSystemTimeAsFileTime
0x18002baa3  mov     [rbp+57h+pcchLength], 0
0x18002baab  call    cs:__imp_GetSystemTimeAsFileTime
0x18002bab2  nop     dword ptr [rax+rax+00h]
0x18002bab7  mov     rcx, [rbp+57h+hKey]; hKey
0x18002babb  mov     rax, 0D6BF94D5E57A42BDh
0x18002bac5  mul     [rbp+57h+pcchLength]
0x18002bac9  mov     rbx, rdx
0x18002bacc  lea     rdx, aAddresscreatio; "AddressCreationTimestamp"
0x18002bad3  shr     rbx, 17h
0x18002bad7  mov     r8, rbx
0x18002bada  call    SetUlongLong
0x18002badf  test    r15b, r15b
0x18002bae2  jz      short loc_18002BB14
0x18002bae4  mov     r8d, [rsi+34ECh]
0x18002baeb  cmp     r8d, 7
0x18002baef  jge     short loc_18002BB14
0x18002baf1  mov     rcx, [rbp+57h+hKey]; hKey
0x18002baf5  lea     rdx, aNattype; "NatType"
0x18002bafc  call    SetInteger
0x18002bb01  mov     rcx, [rbp+57h+hKey]; hKey
0x18002bb05  lea     rdx, aNatdetectionti; "NatDetectionTimestamp"
0x18002bb0c  mov     r8, rbx
0x18002bb0f  call    SetUlongLong
0x18002bb14  test    edi, edi
0x18002bb16  jz      short loc_18002BB28
0x18002bb18  mov     rcx, [rbp+57h+hKey]; hKey
0x18002bb1c  call    cs:__imp_RegCloseKey
0x18002bb23  nop     dword ptr [rax+rax+00h]
0x18002bb28  mov     rcx, [rbp+57h+var_30]
0x18002bb2c  xor     rcx, rsp; StackCookie
0x18002bb2f  call    __security_check_cookie
0x18002bb34  mov     rbx, [rsp+100h+arg_10]
0x18002bb3c  add     rsp, 0E0h
0x18002bb43  pop     r15
0x18002bb45  pop     r14
0x18002bb47  pop     rdi
0x18002bb48  pop     rsi
0x18002bb49  pop     rbp
0x18002bb4a  retn
```
