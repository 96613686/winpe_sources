# DhcpV6SetBindingInfo

- ea: `0x180075ee4`
- end: `0x18007616d`
- name: `DhcpV6SetBindingInfo`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180044e10`

## callees

- `0x180003228`
- `0x18001d4ec`
- `0x180075ee4`
- `0x180077724`
- `0x18008f5b4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800760f8`
- `ADVAPI32!RegCloseKey` at `0x180076115`
- `ADVAPI32!RegCloseKey` at `0x1800760f8`
- `ADVAPI32!RegCloseKey` at `0x180076115`
- `ADVAPI32!RegSetValueExW` at `0x1800760e5`
- `ADVAPI32!RegSetValueExW` at `0x1800760e5`
- `ADVAPI32!RegDeleteValueW` at `0x1800760a0`
- `ADVAPI32!RegDeleteValueW` at `0x1800760a0`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180075f53`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180075fb9`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180075f53`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180075fb9`
- `KERNEL32!HeapAlloc` at `0x180075f1f`
- `KERNEL32!HeapAlloc` at `0x180075f8c`
- `KERNEL32!HeapAlloc` at `0x180075f1f`
- `KERNEL32!HeapAlloc` at `0x180075f8c`
- `KERNEL32!HeapFree` at `0x180075f72`
- `KERNEL32!HeapFree` at `0x180076072`
- `KERNEL32!HeapFree` at `0x180076140`
- `KERNEL32!HeapFree` at `0x180075f72`
- `KERNEL32!HeapFree` at `0x180076072`
- `KERNEL32!HeapFree` at `0x180076140`

## pseudocode

```c
__int64 __fastcall DhcpV6SetBindingInfo(__int64 a1)
{
  IP_ADAPTER_ADDRESSES_LH *v2; // rsi
  ULONG AdaptersAddresses; // ebx
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  unsigned int v7; // ebp
  __int64 v8; // rcx
  unsigned __int64 v9; // r15
  void *v10; // rbx
  int v11; // edi
  ULONG SizePointer; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-28h] BYREF

  hKey = 0;
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
    if ( (*(_BYTE *)(v9 + v8) & 1) != 0 )
      goto LABEL_24;
    v10 = (void *)DhcpOemToUnicode(*(PCSZ *)(v9 + v8 + 56));
    v11 = DhcpOpenInterfaceByNameV6(v10, &hKey);
    HeapFree(gDhcpHeap, 0, v10);
    if ( v11 )
      break;
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
0x180075ee4  mov     rax, rsp
0x180075ee7  mov     [rax+10h], rbx
0x180075eeb  mov     [rax+18h], rbp
0x180075eef  mov     [rax+20h], rsi
0x180075ef3  push    rdi
0x180075ef4  push    r14
0x180075ef6  push    r15
0x180075ef8  sub     rsp, 50h
0x180075efc  mov     r14, rcx
0x180075eff  mov     qword ptr [rax-30h], 0
0x180075f07  mov     rcx, cs:gDhcpHeap; hHeap
0x180075f0e  mov     r8d, 3A98h; dwBytes
0x180075f14  mov     edi, 8
0x180075f19  mov     [rax-38h], r8d
0x180075f1d  mov     edx, edi; dwFlags
0x180075f1f  call    cs:__imp_HeapAlloc
0x180075f26  nop     dword ptr [rax+rax+00h]
0x180075f2b  mov     rsi, rax
0x180075f2e  test    rax, rax
0x180075f31  jz      loc_180076150
0x180075f37  lea     rax, [rsp+68h+var_38]
0x180075f3c  mov     r9, rsi; AdapterAddresses
0x180075f3f  lea     ebp, [rdi-2]
0x180075f42  mov     [rsp+68h+SizePointer], rax; SizePointer
0x180075f47  lea     r15d, [rdi+0Fh]
0x180075f4b  mov     edx, ebp; Flags
0x180075f4d  mov     ecx, r15d; Family
0x180075f50  xor     r8d, r8d; Reserved
0x180075f53  call    cs:__imp_GetAdaptersAddresses
0x180075f5a  nop     dword ptr [rax+rax+00h]
0x180075f5f  mov     ebx, eax
0x180075f61  cmp     eax, 6Fh ; 'o'
0x180075f64  jnz     short loc_180075FC7
0x180075f66  mov     rcx, cs:gDhcpHeap; hHeap
0x180075f6d  mov     r8, rsi; lpMem
0x180075f70  xor     edx, edx; dwFlags
0x180075f72  call    cs:__imp_HeapFree
0x180075f79  nop     dword ptr [rax+rax+00h]
0x180075f7e  mov     r8d, [rsp+68h+var_38]; dwBytes
0x180075f83  mov     edx, edi; dwFlags
0x180075f85  mov     rcx, cs:gDhcpHeap; hHeap
0x180075f8c  call    cs:__imp_HeapAlloc
0x180075f93  nop     dword ptr [rax+rax+00h]
0x180075f98  mov     rsi, rax
0x180075f9b  test    rax, rax
0x180075f9e  jz      loc_180076150
0x180075fa4  lea     rax, [rsp+68h+var_38]
0x180075fa9  mov     r9, rsi; AdapterAddresses
0x180075fac  xor     r8d, r8d; Reserved
0x180075faf  mov     [rsp+68h+SizePointer], rax; SizePointer
0x180075fb4  mov     edx, ebp; Flags
0x180075fb6  mov     ecx, r15d; Family
0x180075fb9  call    cs:__imp_GetAdaptersAddresses
0x180075fc0  nop     dword ptr [rax+rax+00h]
0x180075fc5  mov     ebx, eax
0x180075fc7  test    ebx, ebx
0x180075fc9  jz      short loc_180076003
0x180075fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180075fd2  lea     rax, WPP_GLOBAL_Control
0x180075fd9  cmp     rcx, rax
0x180075fdc  jz      short loc_180075FF9
0x180075fde  test    byte ptr [rcx+1Ch], 10h
0x180075fe2  jz      short loc_180075FF9
0x180075fe4  mov     rcx, [rcx+10h]
0x180075fe8  lea     r8, WPP_f298aecaa2ea3c2eae42f14ee92a4112_Traceguids
0x180075fef  mov     edx, 20h ; ' '
0x180075ff4  call    WPP_SF_
0x180075ff9  mov     ebx, 65Bh
0x180075ffe  jmp     loc_180076134
0x180076003  xor     eax, eax
0x180076005  cmp     [r14], eax
0x180076008  jbe     loc_180076126
0x18007600e  mov     rdx, [r14+8]
0x180076012  mov     ecx, eax
0x180076014  shl     rcx, 6
0x180076018  test    byte ptr [rcx+rdx], 1
0x18007601c  jz      short loc_180076029
0x18007601e  cmp     dword ptr [rcx+rdx+4], 0
0x180076023  jz      loc_1800760BA
0x180076029  inc     eax
0x18007602b  cmp     eax, [r14]
0x18007602e  jb      short loc_180076012
0x180076030  xor     ebp, ebp
0x180076032  mov     rcx, [r14+8]
0x180076036  mov     r15d, ebp
0x180076039  shl     r15, 6
0x18007603d  test    byte ptr [r15+rcx], 1
0x180076042  jnz     loc_180076108
0x180076048  mov     rcx, [r15+rcx+38h]; SourceString
0x18007604d  xor     edx, edx
0x18007604f  call    DhcpOemToUnicode
0x180076054  lea     rdx, [rsp+68h+hKey]
0x180076059  mov     rcx, rax
0x18007605c  mov     rbx, rax
0x18007605f  call    DhcpOpenInterfaceByNameV6
0x180076064  mov     rcx, cs:gDhcpHeap; hHeap
0x18007606b  mov     r8, rbx; lpMem
0x18007606e  xor     edx, edx; dwFlags
0x180076070  mov     edi, eax
0x180076072  call    cs:__imp_HeapFree
0x180076079  nop     dword ptr [rax+rax+00h]
0x18007607e  mov     rcx, [rsp+68h+hKey]; hKey
0x180076083  test    edi, edi
0x180076085  jnz     loc_180076115
0x18007608b  mov     rax, [r14+8]
0x18007608f  mov     edx, [r15+rax+4]
0x180076094  cmp     edx, 1
0x180076097  jnz     short loc_1800760C1
0x180076099  lea     rdx, aBindtodhcpserv; "BindToDHCPServer"
0x1800760a0  call    cs:__imp_RegDeleteValueW
0x1800760a7  nop     dword ptr [rax+rax+00h]
0x1800760ac  mov     ebx, eax
0x1800760ae  add     eax, 0FFFFFFFEh
0x1800760b1  cmp     eax, 1
0x1800760b4  ja      short loc_1800760F3
0x1800760b6  xor     ebx, ebx
0x1800760b8  jmp     short loc_1800760F3
0x1800760ba  mov     ebx, 4E53h
0x1800760bf  jmp     short loc_180076134
0x1800760c1  mov     edi, 4
0x1800760c6  mov     dword ptr [rsp+68h+Data], edx
0x1800760ca  lea     rax, [rsp+68h+Data]
0x1800760cf  mov     [rsp+68h+cbData], edi; cbData
0x1800760d3  mov     r9d, edi; dwType
0x1800760d6  mov     [rsp+68h+SizePointer], rax; lpData
0x1800760db  xor     r8d, r8d; Reserved
0x1800760de  lea     rdx, aBindtodhcpserv; "BindToDHCPServer"
0x1800760e5  call    cs:__imp_RegSetValueExW
0x1800760ec  nop     dword ptr [rax+rax+00h]
0x1800760f1  mov     ebx, eax
0x1800760f3  mov     rcx, [rsp+68h+hKey]; hKey
0x1800760f8  call    cs:__imp_RegCloseKey
0x1800760ff  nop     dword ptr [rax+rax+00h]
0x180076104  test    ebx, ebx
0x180076106  jnz     short loc_180076126
0x180076108  inc     ebp
0x18007610a  cmp     ebp, [r14]
0x18007610d  jb      loc_180076032
0x180076113  jmp     short loc_180076126
0x180076115  call    cs:__imp_RegCloseKey
0x18007611c  nop     dword ptr [rax+rax+00h]
0x180076121  mov     ebx, 4E52h
0x180076126  lea     rdx, DhcpV6RefreshBinding
0x18007612d  xor     ecx, ecx
0x18007612f  call    DhcpV6WalkthroughEndpoints
0x180076134  mov     rcx, cs:gDhcpHeap; hHeap
0x18007613b  mov     r8, rsi; lpMem
0x18007613e  xor     edx, edx; dwFlags
0x180076140  call    cs:__imp_HeapFree
0x180076147  nop     dword ptr [rax+rax+00h]
0x18007614c  mov     eax, ebx
0x18007614e  jmp     short loc_180076152
0x180076150  mov     eax, edi
0x180076152  lea     r11, [rsp+68h+var_18]
0x180076157  mov     rbx, [r11+28h]
0x18007615b  mov     rbp, [r11+30h]
0x18007615f  mov     rsi, [r11+38h]
0x180076163  mov     rsp, r11
0x180076166  pop     r15
0x180076168  pop     r14
0x18007616a  pop     rdi
0x18007616b  retn
```
