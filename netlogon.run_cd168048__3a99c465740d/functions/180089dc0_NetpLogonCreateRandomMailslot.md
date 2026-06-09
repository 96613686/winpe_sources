# NetpLogonCreateRandomMailslot

- ea: `0x180089dc0`
- end: `0x180089f78`
- name: `NetpLogonCreateRandomMailslot`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a564`

## callees

- `0x18000e910`
- `0x180047470`
- `0x180089ca0`
- `0x180089d40`
- `0x180089dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089f0e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateMailslotA` at `0x180089ef9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateMailslotA` at `0x180089ef9`
- `CRYPTSP!CryptGenRandom` at `0x180089e8d`
- `CRYPTSP!CryptGenRandom` at `0x180089e8d`
- `CRYPTSP!CryptAcquireContextW` at `0x180089e27`
- `CRYPTSP!CryptAcquireContextW` at `0x180089e27`
- `CRYPTSP!CryptReleaseContext` at `0x180089f43`
- `CRYPTSP!CryptReleaseContext` at `0x180089f43`

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
0x180089dc0  mov     r11, rsp
0x180089dc3  mov     [r11+8], rbx
0x180089dc7  mov     [r11+20h], rbp
0x180089dcb  push    rsi
0x180089dcc  push    rdi
0x180089dcd  push    r12
0x180089dcf  push    r14
0x180089dd1  push    r15
0x180089dd3  sub     rsp, 70h
0x180089dd7  mov     rax, cs:__security_cookie
0x180089dde  xor     rax, rsp
0x180089de1  mov     [rsp+98h+var_38], rax
0x180089de6  mov     rbp, cs:?NlGlobalCryptProvider@@3_KA; unsigned __int64 NlGlobalCryptProvider
0x180089ded  mov     r15, r8
0x180089df0  mov     byte ptr [rdx], 0
0x180089df3  mov     r14, rdx
0x180089df6  mov     dword ptr [rsp+98h+pbBuffer], 0
0x180089dfe  mov     qword ptr [r11-60h], 0
0x180089e06  mov     qword ptr [r8], 0
0x180089e0d  test    rbp, rbp
0x180089e10  jnz     short loc_180089E4F
0x180089e12  lea     r9d, [rbp+1]; dwProvType
0x180089e16  mov     [rsp+98h+dwFlags], 0F0000000h; dwFlags
0x180089e1e  xor     r8d, r8d; szProvider
0x180089e21  lea     rcx, [r11-60h]; phProv
0x180089e25  xor     edx, edx; szContainer
0x180089e27  call    cs:__imp_CryptAcquireContextW
0x180089e2e  nop     dword ptr [rax+rax+00h]
0x180089e33  test    eax, eax
0x180089e35  jnz     short loc_180089E4A
0x180089e37  call    cs:__imp_GetLastError
0x180089e3e  nop     dword ptr [rax+rax+00h]
0x180089e43  mov     ebx, eax
0x180089e45  jmp     loc_180089F37
0x180089e4a  mov     rbp, [rsp+98h+hProv]
0x180089e4f  lea     r8, aMailslotNetGet; "\\MAILSLOT\\NET\\GETDCXXXXXXXX"
0x180089e56  mov     edx, 1Ch; unsigned __int64
0x180089e5b  mov     rcx, r14; char *
0x180089e5e  call    ?RtlStringCchCopyA@@YAJPEAD_KPEBD@Z; RtlStringCchCopyA(char *,unsigned __int64,char const *)
0x180089e63  test    eax, eax
0x180089e65  jns     short loc_180089E71
0x180089e67  mov     ebx, 85Ch
0x180089e6c  jmp     loc_180089F37
0x180089e71  xor     edi, edi
0x180089e73  xor     ebx, ebx
0x180089e75  xor     esi, esi
0x180089e77  cmp     esi, 3
0x180089e7a  jnb     loc_180089F2E
0x180089e80  lea     r8, [rsp+98h+pbBuffer]; pbBuffer
0x180089e85  mov     edx, 4; dwLen
0x180089e8a  mov     rcx, rbp; hProv
0x180089e8d  call    cs:__imp_CryptGenRandom
0x180089e94  nop     dword ptr [rax+rax+00h]
0x180089e99  test    eax, eax
0x180089e9b  jz      short loc_180089E37
0x180089e9d  mov     r9d, dword ptr [rsp+98h+pbBuffer]
0x180089ea2  lea     r8, a08x_0; "%08X"
0x180089ea9  mov     edx, 9; unsigned __int64
0x180089eae  lea     rcx, [r14+13h]; char *
0x180089eb2  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180089eb7  test    eax, eax
0x180089eb9  js      short loc_180089E67
0x180089ebb  lea     r8, asc_1800E8FC4; "\\\\."
0x180089ec2  mov     edx, 20h ; ' '; unsigned __int64
0x180089ec7  lea     rcx, [rsp+98h+Name]; char *
0x180089ecc  call    ?RtlStringCchCopyA@@YAJPEAD_KPEBD@Z; RtlStringCchCopyA(char *,unsigned __int64,char const *)
0x180089ed1  test    eax, eax
0x180089ed3  js      short loc_180089E67
0x180089ed5  mov     r8, r14; char *
0x180089ed8  lea     rcx, [rsp+98h+Name]; char *
0x180089edd  call    ?RtlStringCchCatA@@YAJPEAD_KPEBD@Z; RtlStringCchCatA(char *,unsigned __int64,char const *)
0x180089ee2  test    eax, eax
0x180089ee4  js      short loc_180089E67
0x180089ee6  xor     r9d, r9d; lpSecurityAttributes
0x180089ee9  lea     rcx, [rsp+98h+Name]; lpName
0x180089eee  mov     edx, 298h; nMaxMessageSize
0x180089ef3  mov     r8d, 1388h; lReadTimeout
0x180089ef9  call    cs:__imp_CreateMailslotA
0x180089f00  nop     dword ptr [rax+rax+00h]
0x180089f05  mov     rdi, rax
0x180089f08  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180089f0c  jnz     short loc_180089F2A
0x180089f0e  call    cs:__imp_GetLastError
0x180089f15  nop     dword ptr [rax+rax+00h]
0x180089f1a  mov     ebx, eax
0x180089f1c  cmp     eax, 0B7h
0x180089f21  jnz     short loc_180089F37
0x180089f23  inc     esi
0x180089f25  jmp     loc_180089E77
0x180089f2a  xor     ebx, ebx
0x180089f2c  jmp     short loc_180089F34
0x180089f2e  jz      loc_180089E67
0x180089f34  mov     [r15], rdi
0x180089f37  mov     rcx, [rsp+98h+hProv]; hProv
0x180089f3c  test    rcx, rcx
0x180089f3f  jz      short loc_180089F4F
0x180089f41  xor     edx, edx; dwFlags
0x180089f43  call    cs:__imp_CryptReleaseContext
0x180089f4a  nop     dword ptr [rax+rax+00h]
0x180089f4f  mov     eax, ebx
0x180089f51  mov     rcx, [rsp+98h+var_38]
0x180089f56  xor     rcx, rsp; StackCookie
0x180089f59  call    __security_check_cookie
0x180089f5e  lea     r11, [rsp+98h+var_28]
0x180089f63  mov     rbx, [r11+30h]
0x180089f67  mov     rbp, [r11+48h]
0x180089f6b  mov     rsp, r11
0x180089f6e  pop     r15
0x180089f70  pop     r14
0x180089f72  pop     r12
0x180089f74  pop     rdi
0x180089f75  pop     rsi
0x180089f76  retn
```
