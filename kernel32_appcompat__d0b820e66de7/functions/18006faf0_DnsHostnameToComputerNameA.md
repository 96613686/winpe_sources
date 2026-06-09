# DnsHostnameToComputerNameA

- ea: `0x18006faf0`
- end: `0x18006fbf2`
- name: `DnsHostnameToComputerNameA`
- size: `258`
- prototype: `BOOL __stdcall(LPCSTR Hostname, LPSTR ComputerName, LPDWORD nSize)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ccf0`
- `0x18006faf0`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x18006fb91`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18006fb91`
- `ntdll!RtlFreeUnicodeString` at `0x18006fbad`
- `ntdll!RtlFreeUnicodeString` at `0x18006fbad`
- `ntdll!RtlDnsHostNameToComputerName` at `0x18006fb63`
- `ntdll!RtlDnsHostNameToComputerName` at `0x18006fb63`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18006fb2f`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18006fb2f`

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
0x18006faf0  mov     [rsp-18h+arg_18], rbx
0x18006faf5  push    rbp
0x18006faf6  push    rsi
0x18006faf7  push    rdi
0x18006faf8  mov     rbp, rsp
0x18006fafb  sub     rsp, 80h
0x18006fb02  mov     rax, cs:__security_cookie
0x18006fb09  xor     rax, rsp
0x18006fb0c  mov     [rbp+var_10], rax
0x18006fb10  xorps   xmm0, xmm0
0x18006fb13  mov     rsi, rdx
0x18006fb16  mov     rdx, rcx; Source
0x18006fb19  xorps   xmm1, xmm1
0x18006fb1c  lea     rcx, [rbp+Destination]; Destination
0x18006fb20  mov     rdi, r8
0x18006fb23  movups  xmmword ptr [rbp+ComputerName.Length], xmm0
0x18006fb27  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x18006fb2b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006fb2f  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18006fb36  nop     dword ptr [rax+rax+00h]
0x18006fb3b  test    al, al
0x18006fb3d  jz      loc_18006FBC4
0x18006fb43  xor     eax, eax
0x18006fb45  mov     dword ptr [rbp+ComputerName.Length], 200000h
0x18006fb4c  mov     [rbp+var_30], ax
0x18006fb50  lea     rdx, [rbp+Destination]; DnsHostName
0x18006fb54  lea     rax, [rbp+var_30]
0x18006fb58  xor     r8d, r8d; AllocateComputerNameString
0x18006fb5b  lea     rcx, [rbp+ComputerName]; ComputerName
0x18006fb5f  mov     [rbp+ComputerName.Buffer], rax
0x18006fb63  call    cs:__imp_RtlDnsHostNameToComputerName
0x18006fb6a  nop     dword ptr [rax+rax+00h]
0x18006fb6f  mov     ebx, eax
0x18006fb71  test    eax, eax
0x18006fb73  js      short loc_18006FBA9
0x18006fb75  xor     eax, eax
0x18006fb77  mov     [rbp+DestinationString.Buffer], rsi
0x18006fb7b  mov     [rbp+DestinationString.Length], ax
0x18006fb7f  lea     rdx, [rbp+ComputerName]; SourceString
0x18006fb83  movzx   eax, word ptr [rdi]
0x18006fb86  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006fb8a  xor     r8d, r8d; AllocateDestinationString
0x18006fb8d  mov     [rbp+DestinationString.MaximumLength], ax
0x18006fb91  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18006fb98  nop     dword ptr [rax+rax+00h]
0x18006fb9d  mov     ebx, eax
0x18006fb9f  test    eax, eax
0x18006fba1  js      short loc_18006FBA9
0x18006fba3  movzx   eax, [rbp+DestinationString.Length]
0x18006fba7  mov     [rdi], eax
0x18006fba9  lea     rcx, [rbp+Destination]; UnicodeString
0x18006fbad  call    cs:__imp_RtlFreeUnicodeString
0x18006fbb4  nop     dword ptr [rax+rax+00h]
0x18006fbb9  test    ebx, ebx
0x18006fbbb  js      short loc_18006FBC9
0x18006fbbd  mov     eax, 1
0x18006fbc2  jmp     short loc_18006FBD2
0x18006fbc4  mov     ebx, 0C0000017h
0x18006fbc9  mov     ecx, ebx
0x18006fbcb  call    BaseSetLastNTError
0x18006fbd0  xor     eax, eax
0x18006fbd2  mov     rcx, [rbp+var_10]
0x18006fbd6  xor     rcx, rsp; StackCookie
0x18006fbd9  call    __security_check_cookie
0x18006fbde  mov     rbx, [rsp+80h+arg_18]
0x18006fbe6  add     rsp, 80h
0x18006fbed  pop     rdi
0x18006fbee  pop     rsi
0x18006fbef  pop     rbp
0x18006fbf0  retn
```
