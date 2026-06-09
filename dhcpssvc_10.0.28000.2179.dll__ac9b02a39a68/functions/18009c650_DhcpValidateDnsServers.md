# DhcpValidateDnsServers

- ea: `0x18009c650`
- end: `0x18009c73f`
- name: `DhcpValidateDnsServers`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025144`

## callees

- `0x18009b2ac`
- `0x18009c5c4`
- `0x18009c650`
- `0x1800cdac0`

## import_xrefs

- `DNSAPI!DnsFree` at `0x18009c701`
- `DNSAPI!DnsFree` at `0x18009c701`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x18009c67c`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x18009c67c`
- `DNSAPI!DnsFreeConfigStructure` at `0x18009c70f`
- `DNSAPI!DnsFreeConfigStructure` at `0x18009c70f`
- `KERNEL32!MultiByteToWideChar` at `0x18009c6b9`
- `KERNEL32!MultiByteToWideChar` at `0x18009c6b9`

## pseudocode

```c
__int64 __fastcall DhcpValidateDnsServers(__int64 a1)
{
  __int64 ConfigAlloc; // rax
  void *v3; // rbx
  unsigned int v4; // edi
  WCHAR WideCharStr[256]; // [rsp+40h] [rbp-218h] BYREF

  ConfigAlloc = DnsQueryConfigAllocEx(65539, 0, 0);
  v3 = (void *)ConfigAlloc;
  if ( ConfigAlloc
    && *(_DWORD *)(ConfigAlloc + 8)
    && MultiByteToWideChar(0xFDE9u, 8u, *(LPCCH *)(ConfigAlloc + 16), -1, WideCharStr, 255) )
  {
    v4 = DhcpDnsValidateServerArray_W(a1, WideCharStr);
  }
  else
  {
    v4 = DhcpDnsValidateServerArray_W(a1, L".");
    if ( !v3 )
      return v4;
  }
  if ( (unsigned int)Feature_5977_1413__private_IsEnabledDeviceUsageNoInline() )
    DnsFree(v3, DnsFreeParsedMessageFields|DnsFreeRecordList|0x10000);
  else
    DnsFreeConfigStructure(v3, 65539);
  return v4;
}

```

## disassembly

```asm
0x18009c650  mov     [rsp+arg_8], rbx
0x18009c655  push    rdi
0x18009c656  sub     rsp, 250h
0x18009c65d  mov     rax, cs:__security_cookie
0x18009c664  xor     rax, rsp
0x18009c667  mov     [rsp+258h+var_18], rax
0x18009c66f  mov     rdi, rcx
0x18009c672  xor     r8d, r8d
0x18009c675  mov     ecx, 10003h
0x18009c67a  xor     edx, edx
0x18009c67c  call    cs:__imp_DnsQueryConfigAllocEx
0x18009c683  nop     dword ptr [rax+rax+00h]
0x18009c688  mov     rbx, rax
0x18009c68b  test    rax, rax
0x18009c68e  jz      short loc_18009C6DA
0x18009c690  cmp     dword ptr [rax+8], 0
0x18009c694  jz      short loc_18009C6DA
0x18009c696  mov     r8, [rbx+10h]; lpMultiByteStr
0x18009c69a  lea     rax, [rsp+258h+WideCharStr]
0x18009c69f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18009c6a3  mov     [rsp+258h+cchWideChar], 0FFh; cchWideChar
0x18009c6ab  mov     ecx, 0FDE9h; CodePage
0x18009c6b0  mov     [rsp+258h+lpWideCharStr], rax; lpWideCharStr
0x18009c6b5  lea     edx, [r9+9]; dwFlags
0x18009c6b9  call    cs:__imp_MultiByteToWideChar
0x18009c6c0  nop     dword ptr [rax+rax+00h]
0x18009c6c5  test    eax, eax
0x18009c6c7  jz      short loc_18009C6DA
0x18009c6c9  lea     rdx, [rsp+258h+WideCharStr]
0x18009c6ce  mov     rcx, rdi
0x18009c6d1  call    DhcpDnsValidateServerArray_W
0x18009c6d6  mov     edi, eax
0x18009c6d8  jmp     short loc_18009C6F0
0x18009c6da  lea     rdx, asc_1800E64A8; "."
0x18009c6e1  mov     rcx, rdi
0x18009c6e4  call    DhcpDnsValidateServerArray_W
0x18009c6e9  mov     edi, eax
0x18009c6eb  test    rbx, rbx
0x18009c6ee  jz      short loc_18009C71B
0x18009c6f0  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x18009c6f5  mov     edx, 10003h; FreeType
0x18009c6fa  mov     rcx, rbx; pData
0x18009c6fd  test    eax, eax
0x18009c6ff  jz      short loc_18009C70F
0x18009c701  call    cs:__imp_DnsFree
0x18009c708  nop     dword ptr [rax+rax+00h]
0x18009c70d  jmp     short loc_18009C71B
0x18009c70f  call    cs:__imp_DnsFreeConfigStructure
0x18009c716  nop     dword ptr [rax+rax+00h]
0x18009c71b  mov     eax, edi
0x18009c71d  mov     rcx, [rsp+258h+var_18]
0x18009c725  xor     rcx, rsp; StackCookie
0x18009c728  call    __security_check_cookie
0x18009c72d  mov     rbx, [rsp+258h+arg_8]
0x18009c735  add     rsp, 250h
0x18009c73c  pop     rdi
0x18009c73d  retn
```
