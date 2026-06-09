# GetPredefinedSids

- ea: `0x1800599a8`
- end: `0x180059b71`
- name: `GetPredefinedSids`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180059698`
- `0x1800b2730`
- `0x1800dfe68`
- `0x1800e066c`
- `0x1800e0870`

## callees

- `0x1800599a8`
- `0x18005a230`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059b64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059b64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059a20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059a20`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180059a63`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180059aa5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180059ae3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180059b20`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180059a63`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180059aa5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180059ae3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180059b20`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180059b38`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180059b38`

## pseudocode

```c
__int64 GetPredefinedSids()
{
  unsigned int v1; // ebx
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v3; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v4; // [rsp+70h] [rbp-10h] BYREF

  if ( dword_18015D640 )
    return 1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v1 = 1;
  *(_DWORD *)v3.Value = 0;
  *(_WORD *)&v3.Value[4] = 256;
  *(_DWORD *)v4.Value = 0;
  *(_WORD *)&v4.Value[4] = 4096;
  EnterCriticalSection(&stru_18015CD60);
  if ( !dword_18015D640 )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1)
      && AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pOwner)
      && AllocateAndInitializeSid(&v3, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &qword_18015D628)
      && AllocateAndInitializeSid(&v4, 1u, 0x3000u, 0, 0, 0, 0, 0, 0, 0, &qword_18015D618)
      && ConvertStringSidToSidW(L"S-1-5-80-242729624-280608522-2219052887-3187409060-2225943459", &Sid)
      && (pSid = I_CryptCreateAppContainerUserCertCapabilitySid()) != 0 )
    {
      dword_18015D640 = 1;
    }
    else
    {
      v1 = 0;
    }
  }
  LeaveCriticalSection(&stru_18015CD60);
  return v1;
}

```

## disassembly

```asm
0x1800599a8  mov     [rsp-8+arg_0], rbx
0x1800599ad  mov     [rsp-8+arg_8], rdi
0x1800599b2  push    rbp
0x1800599b3  mov     rbp, rsp
0x1800599b6  sub     rsp, 80h
0x1800599bd  mov     rax, cs:__security_cookie
0x1800599c4  xor     rax, rsp
0x1800599c7  mov     [rbp+var_8], rax
0x1800599cb  xor     edi, edi
0x1800599cd  cmp     cs:dword_18015D640, edi
0x1800599d3  jz      short loc_1800599F9
0x1800599d5  lea     eax, [rdi+1]
0x1800599d8  mov     rcx, [rbp+var_8]
0x1800599dc  xor     rcx, rsp; StackCookie
0x1800599df  call    __security_check_cookie
0x1800599e4  lea     r11, [rsp+80h+var_s0]
0x1800599ec  mov     rbx, [r11+10h]
0x1800599f0  mov     rdi, [r11+18h]
0x1800599f4  mov     rsp, r11
0x1800599f7  pop     rbp
0x1800599f8  retn
0x1800599f9  lea     rcx, stru_18015CD60; lpCriticalSection
0x180059a00  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x180059a03  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180059a09  mov     ebx, 1
0x180059a0e  mov     dword ptr [rbp+var_18.Value], edi
0x180059a11  mov     word ptr [rbp+var_18.Value+4], 100h
0x180059a17  mov     dword ptr [rbp+var_10.Value], edi
0x180059a1a  mov     word ptr [rbp+var_10.Value+4], 1000h
0x180059a20  call    cs:__imp_EnterCriticalSection
0x180059a26  cmp     cs:dword_18015D640, edi
0x180059a2c  jnz     loc_180059B5D
0x180059a32  lea     rax, pSid1
0x180059a39  xor     r9d, r9d; nSubAuthority1
0x180059a3c  mov     [rsp+80h+pSid], rax; pSid
0x180059a41  lea     r8d, [rbx+11h]; nSubAuthority0
0x180059a45  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180059a49  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180059a4d  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180059a51  mov     dl, bl; nSubAuthorityCount
0x180059a53  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180059a57  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180059a5b  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180059a5f  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180059a63  call    cs:__imp_AllocateAndInitializeSid
0x180059a69  test    eax, eax
0x180059a6b  jz      loc_180059B5B
0x180059a71  lea     rax, pOwner
0x180059a78  mov     r9d, 220h; nSubAuthority1
0x180059a7e  mov     [rsp+80h+pSid], rax; pSid
0x180059a83  lea     r8d, [rbx+1Fh]; nSubAuthority0
0x180059a87  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180059a8b  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180059a8f  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180059a93  mov     dl, 2; nSubAuthorityCount
0x180059a95  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180059a99  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180059a9d  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180059aa1  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180059aa5  call    cs:__imp_AllocateAndInitializeSid
0x180059aab  test    eax, eax
0x180059aad  jz      loc_180059B5B
0x180059ab3  lea     rax, qword_18015D628
0x180059aba  xor     r9d, r9d; nSubAuthority1
0x180059abd  mov     [rsp+80h+pSid], rax; pSid
0x180059ac2  lea     rcx, [rbp+var_18]; pIdentifierAuthority
0x180059ac6  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180059aca  xor     r8d, r8d; nSubAuthority0
0x180059acd  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180059ad1  mov     dl, bl; nSubAuthorityCount
0x180059ad3  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180059ad7  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180059adb  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180059adf  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180059ae3  call    cs:__imp_AllocateAndInitializeSid
0x180059ae9  test    eax, eax
0x180059aeb  jz      short loc_180059B5B
0x180059aed  lea     rax, qword_18015D618
0x180059af4  xor     r9d, r9d; nSubAuthority1
0x180059af7  mov     [rsp+80h+pSid], rax; pSid
0x180059afc  lea     rcx, [rbp+var_10]; pIdentifierAuthority
0x180059b00  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180059b04  mov     r8d, 3000h; nSubAuthority0
0x180059b0a  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180059b0e  mov     dl, bl; nSubAuthorityCount
0x180059b10  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180059b14  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180059b18  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180059b1c  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180059b20  call    cs:__imp_AllocateAndInitializeSid
0x180059b26  test    eax, eax
0x180059b28  jz      short loc_180059B5B
0x180059b2a  lea     rdx, Sid; Sid
0x180059b31  lea     rcx, StringSid; "S-1-5-80-242729624-280608522-2219052887"...
0x180059b38  call    cs:__imp_ConvertStringSidToSidW
0x180059b3e  test    eax, eax
0x180059b40  jz      short loc_180059B5B
0x180059b42  call    I_CryptCreateAppContainerUserCertCapabilitySid
0x180059b47  mov     cs:pSid, rax
0x180059b4e  test    rax, rax
0x180059b51  jz      short loc_180059B5B
0x180059b53  mov     cs:dword_18015D640, ebx
0x180059b59  jmp     short loc_180059B5D
0x180059b5b  mov     ebx, edi
0x180059b5d  lea     rcx, stru_18015CD60; lpCriticalSection
0x180059b64  call    cs:__imp_LeaveCriticalSection
0x180059b6a  mov     eax, ebx
0x180059b6c  jmp     loc_1800599D8
```
