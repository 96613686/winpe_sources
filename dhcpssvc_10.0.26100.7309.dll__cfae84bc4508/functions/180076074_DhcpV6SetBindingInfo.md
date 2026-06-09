# DhcpV6SetBindingInfo

- ea: `0x180076074`
- end: `0x180076361`
- name: `DhcpV6SetBindingInfo`
- size: `749`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180045320`

## callees

- `0x18000323c`
- `0x18001df3c`
- `0x180075e24`
- `0x180076074`
- `0x180077874`
- `0x18008f418`
- `0x18008f788`
- `0x1800cc9e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800762d9`
- `ADVAPI32!RegCloseKey` at `0x1800762fb`
- `ADVAPI32!RegCloseKey` at `0x1800762d9`
- `ADVAPI32!RegCloseKey` at `0x1800762fb`
- `ADVAPI32!RegSetValueExW` at `0x1800762c7`
- `ADVAPI32!RegSetValueExW` at `0x1800762c7`
- `ADVAPI32!RegDeleteValueW` at `0x180076287`
- `ADVAPI32!RegDeleteValueW` at `0x180076287`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800760f7`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18007615c`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800760f7`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18007615c`
- `KERNEL32!HeapAlloc` at `0x1800760c2`
- `KERNEL32!HeapAlloc` at `0x18007612f`
- `KERNEL32!HeapAlloc` at `0x1800760c2`
- `KERNEL32!HeapAlloc` at `0x18007612f`
- `KERNEL32!HeapFree` at `0x180076116`
- `KERNEL32!HeapFree` at `0x18007621c`
- `KERNEL32!HeapFree` at `0x180076326`
- `KERNEL32!HeapFree` at `0x180076116`
- `KERNEL32!HeapFree` at `0x18007621c`
- `KERNEL32!HeapFree` at `0x180076326`

## pseudocode

```c
__int64 __fastcall DhcpV6SetBindingInfo(__int64 a1)
{
  IP_ADAPTER_ADDRESSES_LH *v2; // rsi
  ULONG AdaptersAddresses; // ebx
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  unsigned int v7; // r15d
  __int64 v8; // rcx
  unsigned __int64 v9; // r12
  void *v10; // rbx
  int v11; // edi
  __int64 v12; // rbx
  ULONG SizePointer; // [rsp+30h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  int v16; // [rsp+40h] [rbp-40h] BYREF
  BYTE Data[12]; // [rsp+44h] [rbp-3Ch] BYREF
  __int128 v18; // [rsp+50h] [rbp-30h] BYREF
  __int128 v19; // [rsp+60h] [rbp-20h] BYREF

  hKey = 0;
  v16 = 0;
  SizePointer = 15000;
  v2 = (IP_ADAPTER_ADDRESSES_LH *)HeapAlloc(gDhcpHeap, 8u, 0x3A98u);
  if ( !v2 )
    return 8;
  AdaptersAddresses = GetAdaptersAddresses(0x17u, 6u, 0, v2, &SizePointer);
  if ( AdaptersAddresses == 111 )
  {
    HeapFree(gDhcpHeap, 0, v2);
    v2 = (IP_ADAPTER_ADDRESSES_LH *)HeapAlloc(gDhcpHeap, 8u, SizePointer);
    if ( v2 )
    {
      AdaptersAddresses = GetAdaptersAddresses(0x17u, 6u, 0, v2, &SizePointer);
      goto LABEL_5;
    }
    return 8;
  }
LABEL_5:
  if ( AdaptersAddresses )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_f298aecaa2ea3c2eae42f14ee92a4112_Traceguids);
    AdaptersAddresses = 1627;
    goto LABEL_28;
  }
  v4 = 0;
  if ( !*(_DWORD *)a1 )
    goto LABEL_27;
  v5 = *(_QWORD *)(a1 + 8);
  do
  {
    v6 = (unsigned __int64)v4 << 6;
    if ( (*(_BYTE *)(v6 + v5) & 1) != 0 && !*(_DWORD *)(v6 + v5 + 4) )
    {
      AdaptersAddresses = 20051;
      goto LABEL_28;
    }
    ++v4;
  }
  while ( v4 < *(_DWORD *)a1 );
  v7 = 0;
  while ( 1 )
  {
    v8 = *(_QWORD *)(a1 + 8);
    v9 = (unsigned __int64)v7 << 6;
    v19 = 0;
    if ( (*(_BYTE *)(v9 + v8) & 1) != 0 )
      goto LABEL_24;
    v10 = (void *)DhcpOemToUnicode(*(PCSZ *)(v9 + v8 + 56));
    v11 = DhcpOpenInterfaceByNameV6(v10, &hKey);
    HeapFree(gDhcpHeap, 0, v10);
    if ( v11 )
      break;
    v12 = *(_QWORD *)(a1 + 8);
    MemAddr6ConvertIpv6AddrToByte(v9 + v12 + 8, &v19);
    v18 = *(_OWORD *)*(_QWORD *)(v9 + v12 + 56);
    DhcpV6IsAddressStatic(v2, &v18, &v19, &v16);
    if ( *(_DWORD *)(v9 + *(_QWORD *)(a1 + 8) + 4) == 1 )
    {
      AdaptersAddresses = RegDeleteValueW(hKey, L"BindToDHCPServer");
      if ( AdaptersAddresses - 2 <= 1 )
        AdaptersAddresses = 0;
    }
    else
    {
      *(_DWORD *)Data = *(_DWORD *)(v9 + *(_QWORD *)(a1 + 8) + 4);
      AdaptersAddresses = RegSetValueExW(hKey, L"BindToDHCPServer", 0, 4u, Data, 4u);
    }
    RegCloseKey(hKey);
    if ( AdaptersAddresses )
      goto LABEL_27;
LABEL_24:
    if ( ++v7 >= *(_DWORD *)a1 )
      goto LABEL_27;
  }
  RegCloseKey(hKey);
  AdaptersAddresses = 20050;
LABEL_27:
  DhcpV6WalkthroughEndpoints(0, DhcpV6RefreshBinding);
LABEL_28:
  HeapFree(gDhcpHeap, 0, v2);
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x180076074  mov     [rsp-28h+arg_8], rbx
0x180076079  mov     [rsp-28h+arg_10], rsi
0x18007607e  push    rbp
0x18007607f  push    rdi
0x180076080  push    r12
0x180076082  push    r14
0x180076084  push    r15
0x180076086  mov     rbp, rsp
0x180076089  sub     rsp, 80h
0x180076090  mov     rax, cs:__security_cookie
0x180076097  xor     rax, rsp
0x18007609a  mov     [rbp+var_10], rax
0x18007609e  and     [rbp+hKey], 0
0x1800760a3  mov     r14, rcx
0x1800760a6  mov     rcx, cs:gDhcpHeap; hHeap
0x1800760ad  mov     r8d, 3A98h; dwBytes
0x1800760b3  and     [rbp+var_40], 0
0x1800760b7  mov     edi, 8
0x1800760bc  mov     edx, edi; dwFlags
0x1800760be  mov     [rbp+var_50], r8d
0x1800760c2  call    cs:__imp_HeapAlloc
0x1800760c9  nop     dword ptr [rax+rax+00h]
0x1800760ce  mov     rsi, rax
0x1800760d1  test    rax, rax
0x1800760d4  jz      loc_180076336
0x1800760da  lea     rax, [rbp+var_50]
0x1800760de  mov     r9, rsi; AdapterAddresses
0x1800760e1  lea     r15d, [rdi-2]
0x1800760e5  mov     [rsp+80h+SizePointer], rax; SizePointer
0x1800760ea  lea     r12d, [rdi+0Fh]
0x1800760ee  mov     edx, r15d; Flags
0x1800760f1  mov     ecx, r12d; Family
0x1800760f4  xor     r8d, r8d; Reserved
0x1800760f7  call    cs:__imp_GetAdaptersAddresses
0x1800760fe  nop     dword ptr [rax+rax+00h]
0x180076103  mov     ebx, eax
0x180076105  cmp     eax, 6Fh ; 'o'
0x180076108  jnz     short loc_18007616A
0x18007610a  mov     rcx, cs:gDhcpHeap; hHeap
0x180076111  mov     r8, rsi; lpMem
0x180076114  xor     edx, edx; dwFlags
0x180076116  call    cs:__imp_HeapFree
0x18007611d  nop     dword ptr [rax+rax+00h]
0x180076122  mov     r8d, [rbp+var_50]; dwBytes
0x180076126  mov     edx, edi; dwFlags
0x180076128  mov     rcx, cs:gDhcpHeap; hHeap
0x18007612f  call    cs:__imp_HeapAlloc
0x180076136  nop     dword ptr [rax+rax+00h]
0x18007613b  mov     rsi, rax
0x18007613e  test    rax, rax
0x180076141  jz      loc_180076336
0x180076147  lea     rax, [rbp+var_50]
0x18007614b  mov     r9, rsi; AdapterAddresses
0x18007614e  xor     r8d, r8d; Reserved
0x180076151  mov     [rsp+80h+SizePointer], rax; SizePointer
0x180076156  mov     edx, r15d; Flags
0x180076159  mov     ecx, r12d; Family
0x18007615c  call    cs:__imp_GetAdaptersAddresses
0x180076163  nop     dword ptr [rax+rax+00h]
0x180076168  mov     ebx, eax
0x18007616a  test    ebx, ebx
0x18007616c  jz      short loc_1800761A6
0x18007616e  mov     rcx, cs:WPP_GLOBAL_Control
0x180076175  lea     rax, WPP_GLOBAL_Control
0x18007617c  cmp     rcx, rax
0x18007617f  jz      short loc_18007619C
0x180076181  test    byte ptr [rcx+1Ch], 10h
0x180076185  jz      short loc_18007619C
0x180076187  mov     rcx, [rcx+10h]
0x18007618b  lea     r8, WPP_f298aecaa2ea3c2eae42f14ee92a4112_Traceguids
0x180076192  mov     edx, 20h ; ' '
0x180076197  call    WPP_SF_
0x18007619c  mov     ebx, 65Bh
0x1800761a1  jmp     loc_18007631A
0x1800761a6  xor     eax, eax
0x1800761a8  cmp     [r14], eax
0x1800761ab  jbe     loc_18007630C
0x1800761b1  mov     rdx, [r14+8]
0x1800761b5  mov     ecx, eax
0x1800761b7  shl     rcx, 6
0x1800761bb  test    byte ptr [rcx+rdx], 1
0x1800761bf  jz      short loc_1800761CC
0x1800761c1  cmp     dword ptr [rcx+rdx+4], 0
0x1800761c6  jz      loc_1800762A1
0x1800761cc  inc     eax
0x1800761ce  cmp     eax, [r14]
0x1800761d1  jb      short loc_1800761B5
0x1800761d3  xor     r15d, r15d
0x1800761d6  mov     rcx, [r14+8]
0x1800761da  xorps   xmm0, xmm0
0x1800761dd  mov     r12d, r15d
0x1800761e0  shl     r12, 6
0x1800761e4  movups  [rbp+var_20], xmm0
0x1800761e8  test    byte ptr [r12+rcx], 1
0x1800761ed  jnz     loc_1800762E9
0x1800761f3  mov     rcx, [r12+rcx+38h]; SourceString
0x1800761f8  xor     edx, edx
0x1800761fa  call    DhcpOemToUnicode
0x1800761ff  lea     rdx, [rbp+hKey]
0x180076203  mov     rcx, rax
0x180076206  mov     rbx, rax
0x180076209  call    DhcpOpenInterfaceByNameV6
0x18007620e  mov     rcx, cs:gDhcpHeap; hHeap
0x180076215  mov     r8, rbx; lpMem
0x180076218  xor     edx, edx; dwFlags
0x18007621a  mov     edi, eax
0x18007621c  call    cs:__imp_HeapFree
0x180076223  nop     dword ptr [rax+rax+00h]
0x180076228  test    edi, edi
0x18007622a  jnz     loc_1800762F7
0x180076230  mov     rbx, [r14+8]
0x180076234  lea     rdx, [rbp+var_20]
0x180076238  lea     rcx, [rbx+8]
0x18007623c  add     rcx, r12
0x18007623f  call    MemAddr6ConvertIpv6AddrToByte
0x180076244  mov     rax, [r12+rbx+38h]
0x180076249  lea     r9, [rbp+var_40]
0x18007624d  movaps  xmm0, [rbp+var_20]
0x180076251  lea     r8, [rbp+var_20]
0x180076255  lea     rdx, [rbp+var_30]
0x180076259  movdqa  [rbp+var_20], xmm0
0x18007625e  mov     rcx, rsi
0x180076261  movups  xmm1, xmmword ptr [rax]
0x180076264  movdqu  [rbp+var_30], xmm1
0x180076269  call    DhcpV6IsAddressStatic
0x18007626e  mov     rax, [r14+8]
0x180076272  lea     rdx, aBindtodhcpserv; "BindToDHCPServer"
0x180076279  mov     ecx, [r12+rax+4]
0x18007627e  cmp     ecx, 1
0x180076281  jnz     short loc_1800762A8
0x180076283  mov     rcx, [rbp+hKey]; hKey
0x180076287  call    cs:__imp_RegDeleteValueW
0x18007628e  nop     dword ptr [rax+rax+00h]
0x180076293  mov     ebx, eax
0x180076295  add     eax, 0FFFFFFFEh
0x180076298  cmp     eax, 1
0x18007629b  ja      short loc_1800762D5
0x18007629d  xor     ebx, ebx
0x18007629f  jmp     short loc_1800762D5
0x1800762a1  mov     ebx, 4E53h
0x1800762a6  jmp     short loc_18007631A
0x1800762a8  mov     edi, 4
0x1800762ad  mov     dword ptr [rbp+Data], ecx
0x1800762b0  mov     rcx, [rbp+hKey]; hKey
0x1800762b4  lea     rax, [rbp+Data]
0x1800762b8  mov     [rsp+80h+cbData], edi; cbData
0x1800762bc  mov     r9d, edi; dwType
0x1800762bf  xor     r8d, r8d; Reserved
0x1800762c2  mov     [rsp+80h+SizePointer], rax; lpData
0x1800762c7  call    cs:__imp_RegSetValueExW
0x1800762ce  nop     dword ptr [rax+rax+00h]
0x1800762d3  mov     ebx, eax
0x1800762d5  mov     rcx, [rbp+hKey]; hKey
0x1800762d9  call    cs:__imp_RegCloseKey
0x1800762e0  nop     dword ptr [rax+rax+00h]
0x1800762e5  test    ebx, ebx
0x1800762e7  jnz     short loc_18007630C
0x1800762e9  inc     r15d
0x1800762ec  cmp     r15d, [r14]
0x1800762ef  jb      loc_1800761D6
0x1800762f5  jmp     short loc_18007630C
0x1800762f7  mov     rcx, [rbp+hKey]; hKey
0x1800762fb  call    cs:__imp_RegCloseKey
0x180076302  nop     dword ptr [rax+rax+00h]
0x180076307  mov     ebx, 4E52h
0x18007630c  lea     rdx, DhcpV6RefreshBinding
0x180076313  xor     ecx, ecx
0x180076315  call    DhcpV6WalkthroughEndpoints
0x18007631a  mov     rcx, cs:gDhcpHeap; hHeap
0x180076321  mov     r8, rsi; lpMem
0x180076324  xor     edx, edx; dwFlags
0x180076326  call    cs:__imp_HeapFree
0x18007632d  nop     dword ptr [rax+rax+00h]
0x180076332  mov     eax, ebx
0x180076334  jmp     short loc_180076338
0x180076336  mov     eax, edi
0x180076338  mov     rcx, [rbp+var_10]
0x18007633c  xor     rcx, rsp; StackCookie
0x18007633f  call    __security_check_cookie
0x180076344  lea     r11, [rsp+80h+var_s0]
0x18007634c  mov     rbx, [r11+38h]
0x180076350  mov     rsi, [r11+40h]
0x180076354  mov     rsp, r11
0x180076357  pop     r15
0x180076359  pop     r14
0x18007635b  pop     r12
0x18007635d  pop     rdi
0x18007635e  pop     rbp
0x18007635f  retn
```
