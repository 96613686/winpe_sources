# KerbGetDnsHostName(_UNICODE_STRING *)

- ea: `0x1800780b4`
- end: `0x1800781df`
- name: `?KerbGetDnsHostName@@YAJPEAU_UNICODE_STRING@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180078664`

## callees

- `0x18000b300`
- `0x180070680`
- `0x1800780b4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007810d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007814d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007810d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007814d`
- `ntdll!RtlInitUnicodeString` at `0x1800780fa`
- `ntdll!RtlInitUnicodeString` at `0x180078161`
- `ntdll!RtlInitUnicodeString` at `0x1800780fa`
- `ntdll!RtlInitUnicodeString` at `0x180078161`
- `ntdll!RtlDowncaseUnicodeString` at `0x18007819b`
- `ntdll!RtlDowncaseUnicodeString` at `0x18007819b`

## pseudocode

```c
__int64 __fastcall KerbGetDnsHostName(struct _UNICODE_STRING *a1)
{
  NTSTATUS v2; // ebx
  __int64 v3; // rcx
  WCHAR *v4; // rdx
  unsigned __int64 v5; // rdx
  DWORD nSize; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  nSize = 256;
  DestinationString = 0;
  v2 = 0;
  RtlInitUnicodeString(a1, 0);
  if ( GetComputerNameExW(ComputerNameDnsHostname, Buffer, &nSize) )
  {
    v3 = nSize;
    if ( nSize <= 0x100 )
    {
      v4 = &Buffer[nSize + 1];
      nSize = 256 - nSize;
      Buffer[v3] = 46;
      if ( GetComputerNameExW(ComputerNameDnsDomain, v4, &nSize) )
      {
        RtlInitUnicodeString(&DestinationString, Buffer);
        v5 = (unsigned __int64)DestinationString.Length >> 1;
        if ( DestinationString.Buffer[v5 - 1] == 46 )
        {
          DestinationString.Buffer[v5 - 1] = 0;
          DestinationString.Length -= 2;
        }
        v2 = RtlDowncaseUnicodeString(&DestinationString, &DestinationString, 0);
        if ( v2 >= 0 )
          return (unsigned int)KerbDuplicateStringEx(a1, &DestinationString);
      }
    }
    else
    {
      return (unsigned int)-1073741595;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800780b4  mov     [rsp-8+arg_8], rbx
0x1800780b9  mov     [rsp-8+arg_10], rsi
0x1800780be  push    rbp
0x1800780bf  push    rdi
0x1800780c0  push    r14
0x1800780c2  lea     rbp, [rsp-160h]
0x1800780ca  sub     rsp, 260h
0x1800780d1  mov     rax, cs:__security_cookie
0x1800780d8  xor     rax, rsp
0x1800780db  mov     [rbp+170h+var_20], rax
0x1800780e2  xorps   xmm0, xmm0
0x1800780e5  mov     edi, 100h
0x1800780ea  xor     edx, edx; SourceString
0x1800780ec  mov     [rsp+270h+nSize], edi
0x1800780f0  movups  xmmword ptr [rsp+270h+DestinationString.Length], xmm0
0x1800780f5  mov     rsi, rcx
0x1800780f8  xor     ebx, ebx
0x1800780fa  call    cs:__imp_RtlInitUnicodeString
0x180078100  lea     r8, [rsp+270h+nSize]; nSize
0x180078105  lea     rdx, [rsp+270h+Buffer]; lpBuffer
0x18007810a  lea     ecx, [rbx+1]; NameType
0x18007810d  call    cs:__imp_GetComputerNameExW
0x180078113  test    eax, eax
0x180078115  jz      loc_1800781B6
0x18007811b  mov     ecx, [rsp+270h+nSize]
0x18007811f  cmp     ecx, edi
0x180078121  jbe     short loc_18007812D
0x180078123  mov     ebx, 0C00000E5h
0x180078128  jmp     loc_1800781B6
0x18007812d  sub     edi, ecx
0x18007812f  lea     rdx, [rsp+rcx*2+270h+var_22E]; lpBuffer
0x180078134  mov     r14d, 2Eh ; '.'
0x18007813a  mov     [rsp+270h+nSize], edi
0x18007813e  mov     [rsp+rcx*2+270h+Buffer], r14w
0x180078144  lea     r8, [rsp+270h+nSize]; nSize
0x180078149  lea     ecx, [r14-2Ch]; NameType
0x18007814d  call    cs:__imp_GetComputerNameExW
0x180078153  test    eax, eax
0x180078155  jz      short loc_1800781B6
0x180078157  lea     rdx, [rsp+270h+Buffer]; SourceString
0x18007815c  lea     rcx, [rsp+270h+DestinationString]; DestinationString
0x180078161  call    cs:__imp_RtlInitUnicodeString
0x180078167  movzx   edx, [rsp+270h+DestinationString.Length]
0x18007816c  mov     r8, [rsp+270h+DestinationString.Buffer]
0x180078171  shr     rdx, 1
0x180078174  cmp     [r8+rdx*2-2], r14w
0x18007817a  jnz     short loc_18007818E
0x18007817c  xor     eax, eax
0x18007817e  mov     [r8+rdx*2-2], ax
0x180078184  mov     eax, 0FFFEh
0x180078189  add     [rsp+270h+DestinationString.Length], ax
0x18007818e  xor     r8d, r8d; AllocateDestinationString
0x180078191  lea     rdx, [rsp+270h+DestinationString]; UniSource
0x180078196  lea     rcx, [rsp+270h+DestinationString]; UniDest
0x18007819b  call    cs:__imp_RtlDowncaseUnicodeString
0x1800781a1  mov     ebx, eax
0x1800781a3  test    eax, eax
0x1800781a5  js      short loc_1800781B6
0x1800781a7  lea     rdx, [rsp+270h+DestinationString]; struct _UNICODE_STRING *
0x1800781ac  mov     rcx, rsi; struct _UNICODE_STRING *
0x1800781af  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800781b4  mov     ebx, eax
0x1800781b6  mov     eax, ebx
0x1800781b8  mov     rcx, [rbp+170h+var_20]
0x1800781bf  xor     rcx, rsp; StackCookie
0x1800781c2  call    __security_check_cookie
0x1800781c7  lea     r11, [rsp+270h+var_10]
0x1800781cf  mov     rbx, [r11+28h]
0x1800781d3  mov     rsi, [r11+30h]
0x1800781d7  mov     rsp, r11
0x1800781da  pop     r14
0x1800781dc  pop     rdi
0x1800781dd  pop     rbp
0x1800781de  retn
```
