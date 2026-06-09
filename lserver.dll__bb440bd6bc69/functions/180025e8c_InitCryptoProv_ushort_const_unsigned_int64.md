# InitCryptoProv(ushort const *,unsigned __int64 *)

- ea: `0x180025e8c`
- end: `0x180025f96`
- name: `?InitCryptoProv@@YAKPEBGPEA_K@Z`
- size: `266`
- prototype: `unsigned int(const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002689c`

## callees

- `0x180025e8c`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180025ee5`
- `msvcrt!_snwprintf_s` at `0x180025ee5`
- `ADVAPI32!CryptAcquireContextW` at `0x180025f0c`
- `ADVAPI32!CryptAcquireContextW` at `0x180025f2f`
- `ADVAPI32!CryptAcquireContextW` at `0x180025f5a`
- `ADVAPI32!CryptAcquireContextW` at `0x180025f0c`
- `ADVAPI32!CryptAcquireContextW` at `0x180025f2f`
- `ADVAPI32!CryptAcquireContextW` at `0x180025f5a`
- `KERNEL32!GetCurrentThreadId` at `0x180025ec2`
- `KERNEL32!GetCurrentThreadId` at `0x180025ec2`
- `KERNEL32!GetLastError` at `0x180025f6a`
- `KERNEL32!GetLastError` at `0x180025f6a`

## pseudocode

```c
__int64 __fastcall InitCryptoProv(const unsigned __int16 *a1, unsigned __int64 *a2)
{
  unsigned int v3; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-58h]
  wchar_t Buffer[8]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v7; // [rsp+40h] [rbp-38h]
  __int128 v8; // [rsp+50h] [rbp-28h]
  int v9; // [rsp+60h] [rbp-18h]

  *(_OWORD *)Buffer = 0;
  v9 = 0;
  v7 = 0;
  v3 = 0;
  v8 = 0;
  dwFlags = GetCurrentThreadId();
  _snwprintf_s(Buffer, 0x1Au, 0x19u, L"TlsContainer%d", dwFlags);
  CryptAcquireContextW(a2, Buffer, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0x30u);
  if ( !CryptAcquireContextW(a2, Buffer, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0)
    && !CryptAcquireContextW(a2, Buffer, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0x28u) )
  {
    return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x180025e8c  mov     [rsp+arg_0], rbx
0x180025e91  push    rdi
0x180025e92  sub     rsp, 70h
0x180025e96  mov     rax, cs:__security_cookie
0x180025e9d  xor     rax, rsp
0x180025ea0  mov     [rsp+78h+var_10], rax
0x180025ea5  xorps   xmm0, xmm0
0x180025ea8  xor     eax, eax
0x180025eaa  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x180025eaf  mov     [rsp+78h+var_18], eax
0x180025eb3  mov     rdi, rdx
0x180025eb6  movups  [rsp+78h+var_38], xmm0
0x180025ebb  xor     ebx, ebx
0x180025ebd  movups  [rsp+78h+var_28], xmm0
0x180025ec2  call    cs:__imp_GetCurrentThreadId
0x180025ec9  nop     dword ptr [rax+rax+00h]
0x180025ece  lea     r9, aTlscontainerD; "TlsContainer%d"
0x180025ed5  mov     [rsp+78h+dwFlags], eax
0x180025ed9  lea     edx, [rbx+1Ah]; BufferCount
0x180025edc  lea     r8d, [rbx+19h]; MaxCount
0x180025ee0  lea     rcx, [rsp+78h+Buffer]; Buffer
0x180025ee5  call    cs:__imp__snwprintf_s
0x180025eec  nop     dword ptr [rax+rax+00h]
0x180025ef1  lea     r9d, [rbx+18h]; dwProvType
0x180025ef5  mov     [rsp+78h+dwFlags], 30h ; '0'; dwFlags
0x180025efd  lea     r8, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180025f04  mov     rcx, rdi; phProv
0x180025f07  lea     rdx, [rsp+78h+Buffer]; szContainer
0x180025f0c  call    cs:__imp_CryptAcquireContextW
0x180025f13  nop     dword ptr [rax+rax+00h]
0x180025f18  lea     r9d, [rbx+18h]; dwProvType
0x180025f1c  mov     [rsp+78h+dwFlags], ebx; dwFlags
0x180025f20  lea     r8, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180025f27  mov     rcx, rdi; phProv
0x180025f2a  lea     rdx, [rsp+78h+Buffer]; szContainer
0x180025f2f  call    cs:__imp_CryptAcquireContextW
0x180025f36  nop     dword ptr [rax+rax+00h]
0x180025f3b  test    eax, eax
0x180025f3d  jnz     short loc_180025F78
0x180025f3f  lea     r9d, [rbx+18h]; dwProvType
0x180025f43  mov     [rsp+78h+dwFlags], 28h ; '('; dwFlags
0x180025f4b  lea     r8, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180025f52  mov     rcx, rdi; phProv
0x180025f55  lea     rdx, [rsp+78h+Buffer]; szContainer
0x180025f5a  call    cs:__imp_CryptAcquireContextW
0x180025f61  nop     dword ptr [rax+rax+00h]
0x180025f66  test    eax, eax
0x180025f68  jnz     short loc_180025F78
0x180025f6a  call    cs:__imp_GetLastError
0x180025f71  nop     dword ptr [rax+rax+00h]
0x180025f76  mov     ebx, eax
0x180025f78  mov     eax, ebx
0x180025f7a  mov     rcx, [rsp+78h+var_10]
0x180025f7f  xor     rcx, rsp; StackCookie
0x180025f82  call    __security_check_cookie
0x180025f87  mov     rbx, [rsp+78h+arg_0]
0x180025f8f  add     rsp, 70h
0x180025f93  pop     rdi
0x180025f94  retn
```
