# RemoveProviderByName

- ea: `0x180035bc0`
- end: `0x180035d7d`
- name: `RemoveProviderByName`
- size: `445`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800328c0`
- `0x180035acc`

## callees

- `0x1800222f0`
- `0x1800327a8`
- `0x18003281c`
- `0x180033500`
- `0x18003396c`
- `0x180035538`
- `0x18003592c`
- `0x180035bc0`

## import_xrefs

- `WS2_32!WSCDeinstallProviderEx` at `0x180035c6f`
- `WS2_32!WSCDeinstallProviderEx` at `0x180035cf9`
- `WS2_32!WSCDeinstallProviderEx` at `0x180035c6f`
- `WS2_32!WSCDeinstallProviderEx` at `0x180035cf9`

## string_xrefs

- `0x180035be9`: `Attempting to remove provider`
- `0x180035c8a`: `Provider could not be found for deinstallation`
- `0x180035d14`: `Provider could not be found for deinstallation`
- `0x180035ca9`: `Failed to deinstall provider`
- `0x180035d54`: `Failed to recursively delete provider subtree`

## pseudocode

```c
__int64 __fastcall RemoveProviderByName(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v8; // ecx
  __int64 result; // rax
  const wchar_t *v10; // rdx
  unsigned int v11; // [rsp+30h] [rbp-30h] BYREF
  _DWORD v12[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h]
  __int128 v14; // [rsp+48h] [rbp-18h] BYREF

  v11 = 0;
  v14 = 0;
  LogMsgWithProvider(L"Attempting to remove provider", a2);
  if ( *(_DWORD *)a3 != 1297109836 )
  {
    *(_DWORD *)a3 = 1297109836;
    MwcGetProtoArray(0, a3 + 8, a3 + 16, a3 + 20, a4);
    if ( ((*(_DWORD *)(a4 + 4) - 2) & 0xFFFFFFFD) == 0 )
    {
      LOBYTE(v8) = 1;
      MwcGetProtoArray(v8, a3 + 24, a3 + 32, a3 + 36, a4);
    }
  }
  v11 = ReadProviderId(a1, a2, &v14);
  if ( v11 )
    goto LABEL_18;
  if ( (unsigned int)WSCDeinstallProviderEx(&v14, &v11, a4) == -1 )
  {
    result = v11;
    if ( v11 != 10014 )
      goto LABEL_8;
    LogError(10014, L"Provider could not be found for deinstallation");
    v11 = 0;
  }
  else if ( *(_DWORD *)(a3 + 20) )
  {
    MwcMarkRemovedProtocols(&v14, *(_QWORD *)(a3 + 8), *(unsigned int *)(a3 + 16));
  }
  if ( ((*(_DWORD *)(a4 + 4) - 2) & 0xFFFFFFFD) == 0 )
  {
    v12[0] = *(_DWORD *)a4;
    v13 = *(_QWORD *)(a4 + 8);
    v12[1] = 4;
    if ( (unsigned int)WSCDeinstallProviderEx(&v14, &v11, v12) != -1 )
    {
      if ( *(_DWORD *)(a3 + 36) )
        MwcMarkRemovedProtocols(&v14, *(_QWORD *)(a3 + 24), *(unsigned int *)(a3 + 32));
      goto LABEL_18;
    }
    result = v11;
    if ( v11 == 10014 )
    {
      LogError(10014, L"Provider could not be found for deinstallation");
      v11 = 0;
      goto LABEL_18;
    }
LABEL_8:
    if ( !(_DWORD)result )
      return result;
    v10 = L"Failed to deinstall provider";
    goto LABEL_20;
  }
LABEL_18:
  result = RecursivelyDeleteRegistryTree(a1, a2);
  v11 = result;
  if ( !(_DWORD)result )
    return result;
  v10 = L"Failed to recursively delete provider subtree";
LABEL_20:
  LogError((unsigned int)result, v10);
  return v11;
}

```

## disassembly

```asm
0x180035bc0  push    rbp
0x180035bc2  push    rbx
0x180035bc3  push    rsi
0x180035bc4  push    rdi
0x180035bc5  push    r14
0x180035bc7  mov     rbp, rsp
0x180035bca  sub     rsp, 60h
0x180035bce  mov     rax, cs:__security_cookie
0x180035bd5  xor     rax, rsp
0x180035bd8  mov     [rbp+var_8], rax
0x180035bdc  mov     r14, rcx
0x180035bdf  mov     [rbp+var_30], 0
0x180035be6  xorps   xmm0, xmm0
0x180035be9  lea     rcx, aAttemptingToRe; "Attempting to remove provider"
0x180035bf0  movups  [rbp+var_18], xmm0
0x180035bf4  mov     rdi, r9
0x180035bf7  mov     rbx, r8
0x180035bfa  mov     rsi, rdx
0x180035bfd  call    LogMsgWithProvider
0x180035c02  mov     eax, 4D50534Ch
0x180035c07  cmp     [rbx], eax
0x180035c09  jz      short loc_180035C4A
0x180035c0b  lea     r9, [rbx+14h]
0x180035c0f  mov     [rbx], eax
0x180035c11  lea     r8, [rbx+10h]
0x180035c15  mov     [rsp+60h+var_40], rdi
0x180035c1a  lea     rdx, [rbx+8]
0x180035c1e  xor     ecx, ecx
0x180035c20  call    MwcGetProtoArray
0x180035c25  mov     eax, [rdi+4]
0x180035c28  sub     eax, 2
0x180035c2b  test    eax, 0FFFFFFFDh
0x180035c30  jnz     short loc_180035C4A
0x180035c32  lea     r9, [rbx+24h]
0x180035c36  mov     [rsp+60h+var_40], rdi
0x180035c3b  lea     r8, [rbx+20h]
0x180035c3f  mov     cl, 1
0x180035c41  lea     rdx, [rbx+18h]
0x180035c45  call    MwcGetProtoArray
0x180035c4a  lea     r8, [rbp+var_18]
0x180035c4e  mov     rdx, rsi
0x180035c51  mov     rcx, r14
0x180035c54  call    ReadProviderId
0x180035c59  mov     [rbp+var_30], eax
0x180035c5c  test    eax, eax
0x180035c5e  jnz     loc_180035D42
0x180035c64  mov     r8, rdi
0x180035c67  lea     rdx, [rbp+var_30]
0x180035c6b  lea     rcx, [rbp+var_18]
0x180035c6f  call    cs:__imp_WSCDeinstallProviderEx
0x180035c76  nop     dword ptr [rax+rax+00h]
0x180035c7b  cmp     eax, 0FFFFFFFFh
0x180035c7e  jnz     short loc_180035CB5
0x180035c80  mov     eax, [rbp+var_30]
0x180035c83  cmp     eax, 271Eh
0x180035c88  jnz     short loc_180035CA1
0x180035c8a  lea     rdx, aProviderCouldN; "Provider could not be found for deinsta"...
0x180035c91  mov     ecx, eax
0x180035c93  call    LogError
0x180035c98  mov     [rbp+var_30], 0
0x180035c9f  jmp     short loc_180035CCC
0x180035ca1  test    eax, eax
0x180035ca3  jz      loc_180035D65
0x180035ca9  lea     rdx, aFailedToDeinst; "Failed to deinstall provider"
0x180035cb0  jmp     loc_180035D5B
0x180035cb5  cmp     dword ptr [rbx+14h], 0
0x180035cb9  jbe     short loc_180035CCC
0x180035cbb  mov     r8d, [rbx+10h]
0x180035cbf  lea     rcx, [rbp+var_18]
0x180035cc3  mov     rdx, [rbx+8]
0x180035cc7  call    MwcMarkRemovedProtocols
0x180035ccc  mov     eax, [rdi+4]
0x180035ccf  sub     eax, 2
0x180035cd2  test    eax, 0FFFFFFFDh
0x180035cd7  jnz     short loc_180035D42
0x180035cd9  mov     eax, [rdi]
0x180035cdb  lea     r8, [rbp+var_28]
0x180035cdf  mov     [rbp+var_28], eax
0x180035ce2  lea     rdx, [rbp+var_30]
0x180035ce6  mov     rax, [rdi+8]
0x180035cea  lea     rcx, [rbp+var_18]
0x180035cee  mov     [rbp+var_20], rax
0x180035cf2  mov     [rbp+var_24], 4
0x180035cf9  call    cs:__imp_WSCDeinstallProviderEx
0x180035d00  nop     dword ptr [rax+rax+00h]
0x180035d05  cmp     eax, 0FFFFFFFFh
0x180035d08  jnz     short loc_180035D2B
0x180035d0a  mov     eax, [rbp+var_30]
0x180035d0d  cmp     eax, 271Eh
0x180035d12  jnz     short loc_180035CA1
0x180035d14  lea     rdx, aProviderCouldN; "Provider could not be found for deinsta"...
0x180035d1b  mov     ecx, eax
0x180035d1d  call    LogError
0x180035d22  mov     [rbp+var_30], 0
0x180035d29  jmp     short loc_180035D42
0x180035d2b  cmp     dword ptr [rbx+24h], 0
0x180035d2f  jbe     short loc_180035D42
0x180035d31  mov     r8d, [rbx+20h]
0x180035d35  lea     rcx, [rbp+var_18]
0x180035d39  mov     rdx, [rbx+18h]
0x180035d3d  call    MwcMarkRemovedProtocols
0x180035d42  mov     rdx, rsi
0x180035d45  mov     rcx, r14
0x180035d48  call    RecursivelyDeleteRegistryTree
0x180035d4d  mov     [rbp+var_30], eax
0x180035d50  test    eax, eax
0x180035d52  jz      short loc_180035D65
0x180035d54  lea     rdx, aFailedToRecurs_1; "Failed to recursively delete provider s"...
0x180035d5b  mov     ecx, eax
0x180035d5d  call    LogError
0x180035d62  mov     eax, [rbp+var_30]
0x180035d65  mov     rcx, [rbp+var_8]
0x180035d69  xor     rcx, rsp; StackCookie
0x180035d6c  call    __security_check_cookie
0x180035d71  add     rsp, 60h
0x180035d75  pop     r14
0x180035d77  pop     rdi
0x180035d78  pop     rsi
0x180035d79  pop     rbx
0x180035d7a  pop     rbp
0x180035d7b  retn
```
