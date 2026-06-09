# GetNamedPipeClientComputerNameA

- ea: `0x1800724f0`
- end: `0x180072626`
- name: `GetNamedPipeClientComputerNameA`
- size: `310`
- prototype: `BOOL __stdcall(HANDLE Pipe, LPSTR ClientComputerName, ULONG ClientComputerNameLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ccf0`
- `0x1800724f0`
- `0x180082751`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x180072613`
- `ntdll!RtlFreeAnsiString` at `0x180083afc`
- `ntdll!RtlFreeAnsiString` at `0x180072613`
- `ntdll!RtlFreeAnsiString` at `0x180083afc`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800725a9`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800725a9`
- `ntdll!RtlSetLastWin32Error` at `0x180072537`
- `ntdll!RtlSetLastWin32Error` at `0x1800725e1`
- `ntdll!RtlSetLastWin32Error` at `0x180072537`
- `ntdll!RtlSetLastWin32Error` at `0x1800725e1`
- `ntdll!RtlInitUnicodeString` at `0x180072590`
- `ntdll!RtlInitUnicodeString` at `0x180072590`
- `api-ms-win-core-namedpipe-l1-1-0!GetNamedPipeClientComputerNameW` at `0x180072576`
- `api-ms-win-core-namedpipe-l1-1-0!GetNamedPipeClientComputerNameW` at `0x180072576`

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
0x1800724f0  mov     [rsp+arg_10], rbx
0x1800724f5  mov     [rsp+arg_18], rsi
0x1800724fa  push    rdi
0x1800724fb  sub     rsp, 260h
0x180072502  mov     rax, cs:__security_cookie
0x180072509  xor     rax, rsp
0x18007250c  mov     [rsp+268h+var_18], rax
0x180072514  mov     esi, r8d
0x180072517  mov     rdi, rdx
0x18007251a  xorps   xmm0, xmm0
0x18007251d  movups  xmmword ptr [rsp+268h+AnsiString.Length], xmm0
0x180072522  xorps   xmm1, xmm1
0x180072525  movups  xmmword ptr [rsp+268h+DestinationString.Length], xmm1
0x18007252a  mov     ebx, 1
0x18007252f  cmp     r8d, ebx
0x180072532  jnb     short loc_18007256B
0x180072534  lea     ecx, [rbx+79h]; LastError
0x180072537  call    cs:__imp_RtlSetLastWin32Error
0x18007253e  nop     dword ptr [rax+rax+00h]
0x180072543  xor     eax, eax
0x180072545  mov     rcx, [rsp+268h+var_18]
0x18007254d  xor     rcx, rsp; StackCookie
0x180072550  call    __security_check_cookie
0x180072555  lea     r11, [rsp+268h+var_8]
0x18007255d  mov     rbx, [r11+20h]
0x180072561  mov     rsi, [r11+28h]
0x180072565  mov     rsp, r11
0x180072568  pop     rdi
0x180072569  retn
0x18007256b  mov     r8d, 208h; ClientComputerNameLength
0x180072571  lea     rdx, [rsp+268h+ClientComputerName]; ClientComputerName
0x180072576  call    cs:__imp_GetNamedPipeClientComputerNameW
0x18007257d  nop     dword ptr [rax+rax+00h]
0x180072582  test    eax, eax
0x180072584  jz      short loc_180072543
0x180072586  lea     rdx, [rsp+268h+ClientComputerName]; SourceString
0x18007258b  lea     rcx, [rsp+268h+DestinationString]; DestinationString
0x180072590  call    cs:__imp_RtlInitUnicodeString
0x180072597  nop     dword ptr [rax+rax+00h]
0x18007259c  mov     r8b, bl; AllocateDestinationString
0x18007259f  lea     rdx, [rsp+268h+DestinationString]; SourceString
0x1800725a4  lea     rcx, [rsp+268h+AnsiString]; DestinationString
0x1800725a9  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1800725b0  nop     dword ptr [rax+rax+00h]
0x1800725b5  test    eax, eax
0x1800725b7  jns     short loc_1800725C2
0x1800725b9  mov     ecx, eax
0x1800725bb  call    BaseSetLastNTError
0x1800725c0  jmp     short loc_180072543
0x1800725c2  mov     rax, [rsp+268h+AnsiString.Buffer]
0x1800725c7  cmp     byte ptr [rax], 0
0x1800725ca  jnz     short loc_1800725D1
0x1800725cc  mov     byte ptr [rdi], 0
0x1800725cf  jmp     short loc_18007260E
0x1800725d1  movzx   eax, [rsp+268h+AnsiString.Length]
0x1800725d6  add     eax, ebx
0x1800725d8  cmp     esi, eax
0x1800725da  jnb     short loc_1800725F1
0x1800725dc  mov     ecx, 7Ah ; 'z'; LastError
0x1800725e1  call    cs:__imp_RtlSetLastWin32Error
0x1800725e8  nop     dword ptr [rax+rax+00h]
0x1800725ed  xor     ebx, ebx
0x1800725ef  jmp     short loc_18007260E
0x1800725f1  movzx   eax, [rsp+268h+AnsiString.Length]
0x1800725f6  mov     byte ptr [rax+rdi], 0
0x1800725fa  movzx   r8d, [rsp+268h+AnsiString.Length]; Size
0x180072600  mov     rdx, [rsp+268h+AnsiString.Buffer]; Src
0x180072605  mov     rcx, rdi; void *
0x180072608  call    memcpy_0
0x18007260d  nop
0x18007260e  lea     rcx, [rsp+268h+AnsiString]; AnsiString
0x180072613  call    cs:__imp_RtlFreeAnsiString
0x18007261a  nop     dword ptr [rax+rax+00h]
0x18007261f  mov     eax, ebx
0x180072621  jmp     loc_180072545
0x180083aef  push    rbp
0x180083af1  sub     rsp, 20h
0x180083af5  mov     rbp, rdx
0x180083af8  lea     rcx, [rbp+20h]; AnsiString
0x180083afc  call    cs:__imp_RtlFreeAnsiString
0x180083b03  nop     dword ptr [rax+rax+00h]
0x180083b08  nop
0x180083b09  add     rsp, 20h
0x180083b0d  pop     rbp
0x180083b0e  retn
```
