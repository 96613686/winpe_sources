# NetpLogonCreateRandomMailslot

- ea: `0x180083ca4`
- end: `0x180083e37`
- name: `NetpLogonCreateRandomMailslot`
- size: `403`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009fb0`

## callees

- `0x18000e270`
- `0x180044584`
- `0x180083b08`
- `0x180083ba8`
- `0x180083ca4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083dda`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateMailslotA` at `0x180083dcb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateMailslotA` at `0x180083dcb`
- `CRYPTSP!CryptGenRandom` at `0x180083d65`
- `CRYPTSP!CryptGenRandom` at `0x180083d65`
- `CRYPTSP!CryptAcquireContextW` at `0x180083d0b`
- `CRYPTSP!CryptAcquireContextW` at `0x180083d0b`
- `CRYPTSP!CryptReleaseContext` at `0x180083e09`
- `CRYPTSP!CryptReleaseContext` at `0x180083e09`

## pseudocode

```c
__int64 __fastcall NetpLogonCreateRandomMailslot(__int64 a1, __int64 a2, _QWORD *a3)
{
  HCRYPTPROV v3; // rbp
  DWORD LastError; // ebx
  HANDLE MailslotA; // rdi
  unsigned int i; // esi
  unsigned __int64 v9; // rdx
  BYTE pbBuffer[8]; // [rsp+30h] [rbp-68h] BYREF
  HCRYPTPROV hProv; // [rsp+38h] [rbp-60h] BYREF
  CHAR Name[32]; // [rsp+40h] [rbp-58h] BYREF

  v3 = NlGlobalCryptProvider;
  *(_BYTE *)a2 = 0;
  *(_DWORD *)pbBuffer = 0;
  hProv = 0;
  *a3 = 0;
  if ( !v3 )
  {
    if ( !CryptAcquireContextW(&hProv, 0, 0, 1u, 0xF0000000) )
    {
LABEL_3:
      LastError = GetLastError();
      goto LABEL_19;
    }
    v3 = hProv;
  }
  if ( (int)RtlStringCchCopyA((char *)a2, 0x1Cu, "\\MAILSLOT\\NET\\GETDCXXXXXXXX") >= 0 )
  {
    MailslotA = 0;
    LastError = 0;
    for ( i = 0; i < 3; ++i )
    {
      if ( !CryptGenRandom(v3, 4u, pbBuffer) )
        goto LABEL_3;
      if ( (int)RtlStringCchPrintfA((char *)(a2 + 19), 9u, "%08X", *(_DWORD *)pbBuffer) < 0
        || (int)RtlStringCchCopyA(Name, 0x20u, "\\\\.") < 0
        || (int)RtlStringCchCatA(Name, v9, (const char *)a2) < 0 )
      {
        goto LABEL_6;
      }
      MailslotA = CreateMailslotA(Name, 0x298u, 0x1388u, 0);
      if ( MailslotA != (HANDLE)-1LL )
      {
        LastError = 0;
        goto LABEL_18;
      }
      LastError = GetLastError();
      if ( LastError != 183 )
        goto LABEL_19;
    }
    if ( i == 3 )
      goto LABEL_6;
LABEL_18:
    *a3 = MailslotA;
  }
  else
  {
LABEL_6:
    LastError = 2140;
  }
LABEL_19:
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  return LastError;
}

```

## disassembly

```asm
0x180083ca4  mov     r11, rsp
0x180083ca7  mov     [r11+8], rbx
0x180083cab  mov     [r11+20h], rbp
0x180083caf  push    rsi
0x180083cb0  push    rdi
0x180083cb1  push    r12
0x180083cb3  push    r14
0x180083cb5  push    r15
0x180083cb7  sub     rsp, 70h
0x180083cbb  mov     rax, cs:__security_cookie
0x180083cc2  xor     rax, rsp
0x180083cc5  mov     [rsp+98h+var_38], rax
0x180083cca  mov     rbp, cs:?NlGlobalCryptProvider@@3_KA; unsigned __int64 NlGlobalCryptProvider
0x180083cd1  mov     r15, r8
0x180083cd4  mov     byte ptr [rdx], 0
0x180083cd7  mov     r14, rdx
0x180083cda  mov     dword ptr [rsp+98h+pbBuffer], 0
0x180083ce2  mov     qword ptr [r11-60h], 0
0x180083cea  mov     qword ptr [r8], 0
0x180083cf1  test    rbp, rbp
0x180083cf4  jnz     short loc_180083D27
0x180083cf6  lea     r9d, [rbp+1]; dwProvType
0x180083cfa  mov     [rsp+98h+dwFlags], 0F0000000h; dwFlags
0x180083d02  xor     r8d, r8d; szProvider
0x180083d05  lea     rcx, [r11-60h]; phProv
0x180083d09  xor     edx, edx; szContainer
0x180083d0b  call    cs:__imp_CryptAcquireContextW
0x180083d11  test    eax, eax
0x180083d13  jnz     short loc_180083D22
0x180083d15  call    cs:__imp_GetLastError
0x180083d1b  mov     ebx, eax
0x180083d1d  jmp     loc_180083DFD
0x180083d22  mov     rbp, [rsp+98h+hProv]
0x180083d27  lea     r8, aMailslotNetGet; "\\MAILSLOT\\NET\\GETDCXXXXXXXX"
0x180083d2e  mov     edx, 1Ch; unsigned __int64
0x180083d33  mov     rcx, r14; char *
0x180083d36  call    ?RtlStringCchCopyA@@YAJPEAD_KPEBD@Z; RtlStringCchCopyA(char *,unsigned __int64,char const *)
0x180083d3b  test    eax, eax
0x180083d3d  jns     short loc_180083D49
0x180083d3f  mov     ebx, 85Ch
0x180083d44  jmp     loc_180083DFD
0x180083d49  xor     edi, edi
0x180083d4b  xor     ebx, ebx
0x180083d4d  xor     esi, esi
0x180083d4f  cmp     esi, 3
0x180083d52  jnb     loc_180083DF4
0x180083d58  lea     r8, [rsp+98h+pbBuffer]; pbBuffer
0x180083d5d  mov     edx, 4; dwLen
0x180083d62  mov     rcx, rbp; hProv
0x180083d65  call    cs:__imp_CryptGenRandom
0x180083d6b  test    eax, eax
0x180083d6d  jz      short loc_180083D15
0x180083d6f  mov     r9d, dword ptr [rsp+98h+pbBuffer]
0x180083d74  lea     r8, a08x_0; "%08X"
0x180083d7b  mov     edx, 9; unsigned __int64
0x180083d80  lea     rcx, [r14+13h]; char *
0x180083d84  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180083d89  test    eax, eax
0x180083d8b  js      short loc_180083D3F
0x180083d8d  lea     r8, asc_1800E1FC4; "\\\\."
0x180083d94  mov     edx, 20h ; ' '; unsigned __int64
0x180083d99  lea     rcx, [rsp+98h+Name]; char *
0x180083d9e  call    ?RtlStringCchCopyA@@YAJPEAD_KPEBD@Z; RtlStringCchCopyA(char *,unsigned __int64,char const *)
0x180083da3  test    eax, eax
0x180083da5  js      short loc_180083D3F
0x180083da7  mov     r8, r14; char *
0x180083daa  lea     rcx, [rsp+98h+Name]; char *
0x180083daf  call    ?RtlStringCchCatA@@YAJPEAD_KPEBD@Z; RtlStringCchCatA(char *,unsigned __int64,char const *)
0x180083db4  test    eax, eax
0x180083db6  js      short loc_180083D3F
0x180083db8  xor     r9d, r9d; lpSecurityAttributes
0x180083dbb  lea     rcx, [rsp+98h+Name]; lpName
0x180083dc0  mov     edx, 298h; nMaxMessageSize
0x180083dc5  mov     r8d, 1388h; lReadTimeout
0x180083dcb  call    cs:__imp_CreateMailslotA
0x180083dd1  mov     rdi, rax
0x180083dd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180083dd8  jnz     short loc_180083DF0
0x180083dda  call    cs:__imp_GetLastError
0x180083de0  mov     ebx, eax
0x180083de2  cmp     eax, 0B7h
0x180083de7  jnz     short loc_180083DFD
0x180083de9  inc     esi
0x180083deb  jmp     loc_180083D4F
0x180083df0  xor     ebx, ebx
0x180083df2  jmp     short loc_180083DFA
0x180083df4  jz      loc_180083D3F
0x180083dfa  mov     [r15], rdi
0x180083dfd  mov     rcx, [rsp+98h+hProv]; hProv
0x180083e02  test    rcx, rcx
0x180083e05  jz      short loc_180083E0F
0x180083e07  xor     edx, edx; dwFlags
0x180083e09  call    cs:__imp_CryptReleaseContext
0x180083e0f  mov     eax, ebx
0x180083e11  mov     rcx, [rsp+98h+var_38]
0x180083e16  xor     rcx, rsp; StackCookie
0x180083e19  call    __security_check_cookie
0x180083e1e  lea     r11, [rsp+98h+var_28]
0x180083e23  mov     rbx, [r11+30h]
0x180083e27  mov     rbp, [r11+48h]
0x180083e2b  mov     rsp, r11
0x180083e2e  pop     r15
0x180083e30  pop     r14
0x180083e32  pop     r12
0x180083e34  pop     rdi
0x180083e35  pop     rsi
0x180083e36  retn
```
