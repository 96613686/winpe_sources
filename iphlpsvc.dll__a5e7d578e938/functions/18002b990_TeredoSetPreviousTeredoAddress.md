# TeredoSetPreviousTeredoAddress

- ea: `0x18002b990`
- end: `0x18002bb5c`
- name: `TeredoSetPreviousTeredoAddress`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a9a0`

## callees

- `0x18002b6ec`
- `0x18002b990`
- `0x18002bb64`
- `0x18002bc28`
- `0x180043100`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ba7c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ba7c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ba4c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ba4c`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002ba06`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002ba06`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002babb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002babb`
- `WS2_32!__imp_ntohs` at `0x18002ba8f`
- `WS2_32!__imp_ntohs` at `0x18002ba8f`

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
0x18002b990  mov     [rsp-8+arg_10], rbx
0x18002b995  push    rbp
0x18002b996  push    rsi
0x18002b997  push    rdi
0x18002b998  push    r14
0x18002b99a  push    r15
0x18002b99c  lea     rbp, [rsp-37h]
0x18002b9a1  sub     rsp, 0E0h
0x18002b9a8  mov     rax, cs:__security_cookie
0x18002b9af  xor     rax, rsp
0x18002b9b2  mov     [rbp+57h+var_30], rax
0x18002b9b6  mov     r15b, r8b
0x18002b9b9  mov     [rbp+57h+hKey], rdx
0x18002b9bd  mov     rbx, rdx
0x18002b9c0  mov     rsi, rcx
0x18002b9c3  xor     edx, edx; Val
0x18002b9c5  lea     rcx, [rbp+57h+S]; void *
0x18002b9c9  mov     r8d, 82h; Size
0x18002b9cf  call    memset_0
0x18002b9d4  xor     edi, edi
0x18002b9d6  mov     [rbp+57h+pcchLength], 0
0x18002b9de  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002b9e2  jnz     short loc_18002B9FB
0x18002b9e4  lea     edx, [rbx+2]
0x18002b9e7  lea     rcx, [rbp+57h+hKey]; phkResult
0x18002b9eb  call    TeredoCreateGatewayKey
0x18002b9f0  test    eax, eax
0x18002b9f2  jnz     loc_18002BB38
0x18002b9f8  lea     edi, [rbx+2]
0x18002b9fb  lea     rcx, [rsi+3578h]; Addr
0x18002ba02  lea     rdx, [rbp+57h+S]; S
0x18002ba06  call    cs:__imp_RtlIpv6AddressToStringW
0x18002ba0d  nop     dword ptr [rax+rax+00h]
0x18002ba12  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x18002ba16  mov     edx, 41h ; 'A'; cchMax
0x18002ba1b  lea     rcx, [rbp+57h+S]; psz
0x18002ba1f  call    StringLengthWorkerW
0x18002ba24  test    eax, eax
0x18002ba26  js      loc_18002BB24
0x18002ba2c  mov     r14, [rbp+57h+pcchLength]
0x18002ba30  mov     eax, 0FFFFFFFFh
0x18002ba35  cmp     r14, rax
0x18002ba38  ja      loc_18002BB24
0x18002ba3e  mov     rbx, [rbp+57h+hKey]
0x18002ba42  lea     rdx, aTeredoaddress; "TeredoAddress"
0x18002ba49  mov     rcx, rbx; hKey
0x18002ba4c  call    cs:__imp_RegDeleteValueW
0x18002ba53  nop     dword ptr [rax+rax+00h]
0x18002ba58  lea     eax, [r14+r14]
0x18002ba5c  mov     r9d, 1; dwType
0x18002ba62  mov     [rsp+100h+cbData], eax; cbData
0x18002ba66  lea     rdx, aTeredoaddress; "TeredoAddress"
0x18002ba6d  lea     rax, [rbp+57h+S]
0x18002ba71  xor     r8d, r8d; Reserved
0x18002ba74  mov     rcx, rbx; hKey
0x18002ba77  mov     [rsp+100h+lpData], rax; lpData
0x18002ba7c  call    cs:__imp_RegSetValueExW
0x18002ba83  nop     dword ptr [rax+rax+00h]
0x18002ba88  movzx   ecx, word ptr [rsi+31DEh]; netshort
0x18002ba8f  call    cs:__imp_ntohs
0x18002ba96  nop     dword ptr [rax+rax+00h]
0x18002ba9b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ba9f  lea     rdx, aClientlocalpor; "ClientLocalPort"
0x18002baa6  movzx   r8d, ax
0x18002baaa  call    SetInteger
0x18002baaf  lea     rcx, [rbp+57h+pcchLength]; lpSystemTimeAsFileTime
0x18002bab3  mov     [rbp+57h+pcchLength], 0
0x18002babb  call    cs:__imp_GetSystemTimeAsFileTime
0x18002bac2  nop     dword ptr [rax+rax+00h]
0x18002bac7  mov     rcx, [rbp+57h+hKey]; hKey
0x18002bacb  mov     rax, 0D6BF94D5E57A42BDh
0x18002bad5  mul     [rbp+57h+pcchLength]
0x18002bad9  mov     rbx, rdx
0x18002badc  lea     rdx, aAddresscreatio; "AddressCreationTimestamp"
0x18002bae3  shr     rbx, 17h
0x18002bae7  mov     r8, rbx
0x18002baea  call    SetUlongLong
0x18002baef  test    r15b, r15b
0x18002baf2  jz      short loc_18002BB24
0x18002baf4  mov     r8d, [rsi+34ECh]
0x18002bafb  cmp     r8d, 7
0x18002baff  jge     short loc_18002BB24
0x18002bb01  mov     rcx, [rbp+57h+hKey]; hKey
0x18002bb05  lea     rdx, aNattype; "NatType"
0x18002bb0c  call    SetInteger
0x18002bb11  mov     rcx, [rbp+57h+hKey]; hKey
0x18002bb15  lea     rdx, aNatdetectionti; "NatDetectionTimestamp"
0x18002bb1c  mov     r8, rbx
0x18002bb1f  call    SetUlongLong
0x18002bb24  test    edi, edi
0x18002bb26  jz      short loc_18002BB38
0x18002bb28  mov     rcx, [rbp+57h+hKey]; hKey
0x18002bb2c  call    cs:__imp_RegCloseKey
0x18002bb33  nop     dword ptr [rax+rax+00h]
0x18002bb38  mov     rcx, [rbp+57h+var_30]
0x18002bb3c  xor     rcx, rsp; StackCookie
0x18002bb3f  call    __security_check_cookie
0x18002bb44  mov     rbx, [rsp+100h+arg_10]
0x18002bb4c  add     rsp, 0E0h
0x18002bb53  pop     r15
0x18002bb55  pop     r14
0x18002bb57  pop     rdi
0x18002bb58  pop     rsi
0x18002bb59  pop     rbp
0x18002bb5a  retn
```
