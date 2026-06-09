# DhcpAppendHostNameOption

- ea: `0x18002f3f8`
- end: `0x18002f526`
- name: `DhcpAppendHostNameOption`
- size: `302`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180034bcc`

## callees

- `0x180006484`
- `0x180019620`
- `0x18001cef0`
- `0x18001d826`
- `0x18002f3f8`
- `0x180047b0c`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4a6`
- `DNSAPI!DnsQueryConfigDword` at `0x18002f43e`
- `DNSAPI!DnsQueryConfigDword` at `0x18002f43e`

## pseudocode

```c
__int64 __fastcall DhcpAppendHostNameOption(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  DWORD LastError; // eax
  char *v11; // r8
  unsigned int v13; // [rsp+30h] [rbp-3C8h] BYREF
  char *v14; // [rsp+38h] [rbp-3C0h] BYREF
  _BYTE v15[912]; // [rsp+40h] [rbp-3B8h] BYREF

  v13 = 0;
  if ( DhcpGlobalUseMHAsyncDns )
    v6 = *(_QWORD *)(a1 + 56);
  else
    v6 = 0;
  if ( (unsigned int)DnsQueryConfigDword(65552, v6) && *(_DWORD *)(a1 + 152) )
  {
    memset_0(v15, 0, 0x384u);
    v13 = 900;
    v14 = v15;
    v8 = -1;
    do
      ++v8;
    while ( *(&DhcpGlobalHostNameW + v8) );
    if ( (unsigned int)ConvertUnicodeToPunycode(&DhcpGlobalHostNameW, v8, &v14, &v13) )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(1025, 266, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, LastError);
      }
      return a2;
    }
    v11 = v14;
  }
  else
  {
    if ( (unsigned int)WxStringCchLengthDWordA(&DhcpGlobalHostName, v7, &v13) )
      return a2;
    v11 = &DhcpGlobalHostName;
  }
  LOBYTE(v9) = 12;
  return DhcpAppendOption(a2, v9, v11, v13, a3);
}

```

## disassembly

```asm
0x18002f3f8  mov     [rsp+arg_18], rbx
0x18002f3fd  push    rbp
0x18002f3fe  push    rsi
0x18002f3ff  push    rdi
0x18002f400  sub     rsp, 3E0h
0x18002f407  mov     rax, cs:__security_cookie
0x18002f40e  xor     rax, rsp
0x18002f411  mov     [rsp+3F8h+var_28], rax
0x18002f419  xor     ebp, ebp
0x18002f41b  mov     rsi, r8
0x18002f41e  cmp     cs:DhcpGlobalUseMHAsyncDns, ebp
0x18002f424  mov     rdi, rdx
0x18002f427  mov     rbx, rcx
0x18002f42a  mov     [rsp+3F8h+var_3C8], ebp
0x18002f42e  jz      short loc_18002F436
0x18002f430  mov     rdx, [rcx+38h]
0x18002f434  jmp     short loc_18002F439
0x18002f436  mov     rdx, rbp
0x18002f439  mov     ecx, 10010h
0x18002f43e  call    cs:__imp_DnsQueryConfigDword
0x18002f444  test    eax, eax
0x18002f446  jz      loc_18002F4CE
0x18002f44c  cmp     [rbx+98h], ebp
0x18002f452  jz      short loc_18002F4CE
0x18002f454  mov     ebx, 384h
0x18002f459  lea     rcx, [rsp+3F8h+var_3B8]; void *
0x18002f45e  mov     r8d, ebx; Size
0x18002f461  xor     edx, edx; Val
0x18002f463  call    memset_0
0x18002f468  lea     rax, [rsp+3F8h+var_3B8]
0x18002f46d  mov     [rsp+3F8h+var_3C8], ebx
0x18002f471  mov     [rsp+3F8h+var_3C0], rax
0x18002f476  lea     rcx, DhcpGlobalHostNameW
0x18002f47d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002f481  inc     rdx
0x18002f484  cmp     [rcx+rdx*2], bp
0x18002f488  jnz     short loc_18002F481
0x18002f48a  lea     r9, [rsp+3F8h+var_3C8]
0x18002f48f  lea     r8, [rsp+3F8h+var_3C0]
0x18002f494  call    ConvertUnicodeToPunycode
0x18002f499  test    eax, eax
0x18002f49b  jz      short loc_18002F4C7
0x18002f49d  test    byte ptr cs:xmmword_1800616A0, 2
0x18002f4a4  jz      short loc_18002F4E3
0x18002f4a6  call    cs:__imp_GetLastError
0x18002f4ac  mov     edx, 10Ah
0x18002f4b1  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18002f4b8  mov     r9d, eax
0x18002f4bb  mov     ecx, 401h
0x18002f4c0  call    WPP_SF_d
0x18002f4c5  jmp     short loc_18002F4E3
0x18002f4c7  mov     r8, [rsp+3F8h+var_3C0]
0x18002f4cc  jmp     short loc_18002F4EF
0x18002f4ce  lea     r8, [rsp+3F8h+var_3C8]
0x18002f4d3  lea     rcx, DhcpGlobalHostName
0x18002f4da  call    WxStringCchLengthDWordA
0x18002f4df  test    eax, eax
0x18002f4e1  jz      short loc_18002F4E8
0x18002f4e3  mov     rax, rdi
0x18002f4e6  jmp     short loc_18002F503
0x18002f4e8  lea     r8, DhcpGlobalHostName
0x18002f4ef  mov     r9d, [rsp+3F8h+var_3C8]
0x18002f4f4  mov     dl, 0Ch
0x18002f4f6  mov     rcx, rdi
0x18002f4f9  mov     [rsp+3F8h+var_3D8], rsi
0x18002f4fe  call    DhcpAppendOption
0x18002f503  mov     rcx, [rsp+3F8h+var_28]
0x18002f50b  xor     rcx, rsp; StackCookie
0x18002f50e  call    __security_check_cookie
0x18002f513  mov     rbx, [rsp+3F8h+arg_18]
0x18002f51b  add     rsp, 3E0h
0x18002f522  pop     rdi
0x18002f523  pop     rsi
0x18002f524  pop     rbp
0x18002f525  retn
```
