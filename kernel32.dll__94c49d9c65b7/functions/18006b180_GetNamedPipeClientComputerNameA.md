# GetNamedPipeClientComputerNameA

- ea: `0x18006b180`
- end: `0x18006b291`
- name: `GetNamedPipeClientComputerNameA`
- size: `273`
- prototype: `BOOL __stdcall(HANDLE Pipe, LPSTR ClientComputerName, ULONG ClientComputerNameLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f920`
- `0x18006b180`
- `0x18007a7d1`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x18006b284`
- `ntdll!RtlFreeAnsiString` at `0x18007b997`
- `ntdll!RtlFreeAnsiString` at `0x18006b284`
- `ntdll!RtlFreeAnsiString` at `0x18007b997`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18006b226`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18006b226`
- `ntdll!RtlSetLastWin32Error` at `0x18006b1c7`
- `ntdll!RtlSetLastWin32Error` at `0x18006b258`
- `ntdll!RtlSetLastWin32Error` at `0x18006b1c7`
- `ntdll!RtlSetLastWin32Error` at `0x18006b258`
- `ntdll!RtlInitUnicodeString` at `0x18006b213`
- `ntdll!RtlInitUnicodeString` at `0x18006b213`
- `api-ms-win-core-namedpipe-l1-1-0!GetNamedPipeClientComputerNameW` at `0x18006b1ff`
- `api-ms-win-core-namedpipe-l1-1-0!GetNamedPipeClientComputerNameW` at `0x18006b1ff`

## pseudocode

```c
BOOL __stdcall GetNamedPipeClientComputerNameA(HANDLE Pipe, LPSTR ClientComputerName, ULONG ClientComputerNameLength)
{
  BOOL v5; // ebx
  NTSTATUS v7; // eax
  struct _STRING AnsiString; // [rsp+20h] [rbp-248h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-238h] BYREF
  WCHAR ClientComputerNamea[264]; // [rsp+40h] [rbp-228h] BYREF

  AnsiString = 0;
  DestinationString = 0;
  v5 = 1;
  if ( !ClientComputerNameLength )
  {
    RtlSetLastWin32Error(0x7Au);
    return 0;
  }
  if ( !GetNamedPipeClientComputerNameW(Pipe, ClientComputerNamea, 0x208u) )
    return 0;
  RtlInitUnicodeString(&DestinationString, ClientComputerNamea);
  v7 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
  if ( v7 < 0 )
  {
    BaseSetLastNTError((unsigned int)v7);
    return 0;
  }
  if ( *AnsiString.Buffer )
  {
    if ( ClientComputerNameLength >= (unsigned int)AnsiString.Length + 1 )
    {
      ClientComputerName[AnsiString.Length] = 0;
      memcpy_0(ClientComputerName, AnsiString.Buffer, AnsiString.Length);
    }
    else
    {
      RtlSetLastWin32Error(0x7Au);
      v5 = 0;
    }
  }
  else
  {
    *ClientComputerName = 0;
  }
  RtlFreeAnsiString(&AnsiString);
  return v5;
}

```

## disassembly

```asm
0x18006b180  mov     [rsp+arg_10], rbx
0x18006b185  mov     [rsp+arg_18], rsi
0x18006b18a  push    rdi
0x18006b18b  sub     rsp, 260h
0x18006b192  mov     rax, cs:__security_cookie
0x18006b199  xor     rax, rsp
0x18006b19c  mov     [rsp+268h+var_18], rax
0x18006b1a4  mov     esi, r8d
0x18006b1a7  mov     rdi, rdx
0x18006b1aa  xorps   xmm0, xmm0
0x18006b1ad  movups  xmmword ptr [rsp+268h+AnsiString.Length], xmm0
0x18006b1b2  xorps   xmm1, xmm1
0x18006b1b5  movups  xmmword ptr [rsp+268h+DestinationString.Length], xmm1
0x18006b1ba  mov     ebx, 1
0x18006b1bf  cmp     r8d, ebx
0x18006b1c2  jnb     short loc_18006B1F4
0x18006b1c4  lea     ecx, [rbx+79h]; LastError
0x18006b1c7  call    cs:__imp_RtlSetLastWin32Error
0x18006b1cd  xor     eax, eax
0x18006b1cf  mov     rcx, [rsp+268h+var_18]
0x18006b1d7  xor     rcx, rsp; StackCookie
0x18006b1da  call    __security_check_cookie
0x18006b1df  lea     r11, [rsp+268h+var_8]
0x18006b1e7  mov     rbx, [r11+20h]
0x18006b1eb  mov     rsi, [r11+28h]
0x18006b1ef  mov     rsp, r11
0x18006b1f2  pop     rdi
0x18006b1f3  retn
0x18006b1f4  mov     r8d, 208h; ClientComputerNameLength
0x18006b1fa  lea     rdx, [rsp+268h+ClientComputerName]; ClientComputerName
0x18006b1ff  call    cs:__imp_GetNamedPipeClientComputerNameW
0x18006b205  test    eax, eax
0x18006b207  jz      short loc_18006B1CD
0x18006b209  lea     rdx, [rsp+268h+ClientComputerName]; SourceString
0x18006b20e  lea     rcx, [rsp+268h+DestinationString]; DestinationString
0x18006b213  call    cs:__imp_RtlInitUnicodeString
0x18006b219  mov     r8b, bl; AllocateDestinationString
0x18006b21c  lea     rdx, [rsp+268h+DestinationString]; SourceString
0x18006b221  lea     rcx, [rsp+268h+AnsiString]; DestinationString
0x18006b226  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18006b22c  test    eax, eax
0x18006b22e  jns     short loc_18006B239
0x18006b230  mov     ecx, eax
0x18006b232  call    BaseSetLastNTError
0x18006b237  jmp     short loc_18006B1CD
0x18006b239  mov     rax, [rsp+268h+AnsiString.Buffer]
0x18006b23e  cmp     byte ptr [rax], 0
0x18006b241  jnz     short loc_18006B248
0x18006b243  mov     byte ptr [rdi], 0
0x18006b246  jmp     short loc_18006B27F
0x18006b248  movzx   eax, [rsp+268h+AnsiString.Length]
0x18006b24d  add     eax, ebx
0x18006b24f  cmp     esi, eax
0x18006b251  jnb     short loc_18006B262
0x18006b253  mov     ecx, 7Ah ; 'z'; LastError
0x18006b258  call    cs:__imp_RtlSetLastWin32Error
0x18006b25e  xor     ebx, ebx
0x18006b260  jmp     short loc_18006B27F
0x18006b262  movzx   eax, [rsp+268h+AnsiString.Length]
0x18006b267  mov     byte ptr [rax+rdi], 0
0x18006b26b  movzx   r8d, [rsp+268h+AnsiString.Length]; Size
0x18006b271  mov     rdx, [rsp+268h+AnsiString.Buffer]; Src
0x18006b276  mov     rcx, rdi; void *
0x18006b279  call    memcpy_0
0x18006b27e  nop
0x18006b27f  lea     rcx, [rsp+268h+AnsiString]; AnsiString
0x18006b284  call    cs:__imp_RtlFreeAnsiString
0x18006b28a  mov     eax, ebx
0x18006b28c  jmp     loc_18006B1CF
0x18007b98a  push    rbp
0x18007b98c  sub     rsp, 20h
0x18007b990  mov     rbp, rdx
0x18007b993  lea     rcx, [rbp+20h]; AnsiString
0x18007b997  call    cs:__imp_RtlFreeAnsiString
0x18007b99d  nop
0x18007b99e  add     rsp, 20h
0x18007b9a2  pop     rbp
0x18007b9a3  retn
```
