# DnsHostnameToComputerNameA

- ea: `0x1800689f0`
- end: `0x180068ad5`
- name: `DnsHostnameToComputerNameA`
- size: `229`
- prototype: `BOOL __stdcall(LPCSTR Hostname, LPSTR ComputerName, LPDWORD nSize)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f920`
- `0x1800689f0`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x180068a81`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180068a81`
- `ntdll!RtlFreeUnicodeString` at `0x180068a97`
- `ntdll!RtlFreeUnicodeString` at `0x180068a97`
- `ntdll!RtlDnsHostNameToComputerName` at `0x180068a59`
- `ntdll!RtlDnsHostNameToComputerName` at `0x180068a59`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180068a2f`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180068a2f`

## pseudocode

```c
BOOL __stdcall DnsHostnameToComputerNameA(LPCSTR Hostname, LPSTR ComputerName, LPDWORD nSize)
{
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING ComputerNamea; // [rsp+20h] [rbp-60h] BYREF
  struct _STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-40h] BYREF
  __int16 v10; // [rsp+50h] [rbp-30h] BYREF

  ComputerNamea = 0;
  Destination = 0;
  DestinationString = 0;
  if ( RtlCreateUnicodeStringFromAsciiz(&Destination, Hostname) )
  {
    *(_DWORD *)&ComputerNamea.Length = 0x200000;
    v10 = 0;
    ComputerNamea.Buffer = (PWSTR)&v10;
    v5 = RtlDnsHostNameToComputerName(&ComputerNamea, &Destination, 0);
    if ( v5 >= 0 )
    {
      DestinationString.Buffer = ComputerName;
      DestinationString.Length = 0;
      DestinationString.MaximumLength = *(_WORD *)nSize;
      v5 = RtlUnicodeStringToAnsiString(&DestinationString, &ComputerNamea, 0);
      if ( v5 >= 0 )
        *nSize = DestinationString.Length;
    }
    RtlFreeUnicodeString(&Destination);
    if ( v5 >= 0 )
      return 1;
  }
  else
  {
    v5 = -1073741801;
  }
  BaseSetLastNTError((unsigned int)v5);
  return 0;
}

```

## disassembly

```asm
0x1800689f0  mov     [rsp-18h+arg_18], rbx
0x1800689f5  push    rbp
0x1800689f6  push    rsi
0x1800689f7  push    rdi
0x1800689f8  mov     rbp, rsp
0x1800689fb  sub     rsp, 80h
0x180068a02  mov     rax, cs:__security_cookie
0x180068a09  xor     rax, rsp
0x180068a0c  mov     [rbp+var_10], rax
0x180068a10  xorps   xmm0, xmm0
0x180068a13  mov     rsi, rdx
0x180068a16  mov     rdx, rcx; Source
0x180068a19  xorps   xmm1, xmm1
0x180068a1c  lea     rcx, [rbp+Destination]; Destination
0x180068a20  mov     rdi, r8
0x180068a23  movups  xmmword ptr [rbp+ComputerName.Length], xmm0
0x180068a27  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x180068a2b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180068a2f  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180068a35  test    al, al
0x180068a37  jz      short loc_180068AA8
0x180068a39  xor     eax, eax
0x180068a3b  mov     dword ptr [rbp+ComputerName.Length], 200000h
0x180068a42  mov     [rbp+var_30], ax
0x180068a46  lea     rdx, [rbp+Destination]; DnsHostName
0x180068a4a  lea     rax, [rbp+var_30]
0x180068a4e  xor     r8d, r8d; AllocateComputerNameString
0x180068a51  lea     rcx, [rbp+ComputerName]; ComputerName
0x180068a55  mov     [rbp+ComputerName.Buffer], rax
0x180068a59  call    cs:__imp_RtlDnsHostNameToComputerName
0x180068a5f  mov     ebx, eax
0x180068a61  test    eax, eax
0x180068a63  js      short loc_180068A93
0x180068a65  xor     eax, eax
0x180068a67  mov     [rbp+DestinationString.Buffer], rsi
0x180068a6b  mov     [rbp+DestinationString.Length], ax
0x180068a6f  lea     rdx, [rbp+ComputerName]; SourceString
0x180068a73  movzx   eax, word ptr [rdi]
0x180068a76  lea     rcx, [rbp+DestinationString]; DestinationString
0x180068a7a  xor     r8d, r8d; AllocateDestinationString
0x180068a7d  mov     [rbp+DestinationString.MaximumLength], ax
0x180068a81  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180068a87  mov     ebx, eax
0x180068a89  test    eax, eax
0x180068a8b  js      short loc_180068A93
0x180068a8d  movzx   eax, [rbp+DestinationString.Length]
0x180068a91  mov     [rdi], eax
0x180068a93  lea     rcx, [rbp+Destination]; UnicodeString
0x180068a97  call    cs:__imp_RtlFreeUnicodeString
0x180068a9d  test    ebx, ebx
0x180068a9f  js      short loc_180068AAD
0x180068aa1  mov     eax, 1
0x180068aa6  jmp     short loc_180068AB6
0x180068aa8  mov     ebx, 0C0000017h
0x180068aad  mov     ecx, ebx
0x180068aaf  call    BaseSetLastNTError
0x180068ab4  xor     eax, eax
0x180068ab6  mov     rcx, [rbp+var_10]
0x180068aba  xor     rcx, rsp; StackCookie
0x180068abd  call    __security_check_cookie
0x180068ac2  mov     rbx, [rsp+80h+arg_18]
0x180068aca  add     rsp, 80h
0x180068ad1  pop     rdi
0x180068ad2  pop     rsi
0x180068ad3  pop     rbp
0x180068ad4  retn
```
