# SmbCryptoInitializeCipher

- ea: `0x14004d160`
- end: `0x14004d285`
- name: `SmbCryptoInitializeCipher`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140086444`

## callees

- `0x14004d160`
- `0x140059dc0`

## import_xrefs

- `ksecdd!BCryptSetProperty` at `0x14004d1cf`
- `ksecdd!BCryptSetProperty` at `0x14004d1cf`
- `ksecdd!BCryptGetProperty` at `0x14004d20a`
- `ksecdd!BCryptGetProperty` at `0x14004d20a`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14004d1a0`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14004d1a0`

## pseudocode

```c
NTSTATUS __fastcall SmbCryptoInitializeCipher(__int64 a1, __int64 a2, UCHAR *a3, __int64 a4, int a5, int a6)
{
  NTSTATUS result; // eax
  ULONG pcbResult; // [rsp+30h] [rbp-28h] BYREF
  UCHAR pbOutput[8]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v11; // [rsp+40h] [rbp-18h]

  pcbResult = 0;
  *(_QWORD *)pbOutput = 0;
  v11 = 0;
  result = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)a1, L"AES", 0, 1u);
  if ( result >= 0 )
  {
    result = BCryptSetProperty(*(BCRYPT_HANDLE *)a1, L"ChainingMode", a3, 0x20u, 0);
    if ( result >= 0 )
    {
      result = BCryptGetProperty(*(BCRYPT_HANDLE *)a1, L"AuthTagLength", pbOutput, 0xCu, &pcbResult, 0);
      if ( result >= 0 )
      {
        if ( *(_DWORD *)pbOutput <= 0x10u )
        {
          if ( *(_DWORD *)&pbOutput[4] > 0x10u )
            *(_DWORD *)(a1 + 12) = 16 - (16 - (unsigned __int64)*(unsigned int *)pbOutput) % v11;
          else
            *(_DWORD *)(a1 + 12) = *(_DWORD *)&pbOutput[4];
          *(_DWORD *)(a1 + 8) = a5;
          *(_DWORD *)(a1 + 16) = a6;
          return 0;
        }
        else
        {
          return -1073741637;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14004d160  mov     [rsp+arg_8], rbx
0x14004d165  push    rdi
0x14004d166  sub     rsp, 50h
0x14004d16a  mov     rax, cs:__security_cookie
0x14004d171  xor     rax, rsp
0x14004d174  mov     [rsp+58h+var_10], rax
0x14004d179  xor     eax, eax
0x14004d17b  mov     [rsp+58h+pcbResult], 0
0x14004d183  mov     rdi, r8
0x14004d186  mov     qword ptr [rsp+58h+pbOutput], rax
0x14004d18b  xor     r8d, r8d; pszImplementation
0x14004d18e  mov     [rsp+58h+var_18], eax
0x14004d192  lea     rdx, pszAlgId; "AES"
0x14004d199  mov     rbx, rcx
0x14004d19c  lea     r9d, [rax+1]; dwFlags
0x14004d1a0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14004d1a7  nop     dword ptr [rax+rax+00h]
0x14004d1ac  test    eax, eax
0x14004d1ae  js      loc_14004D26C
0x14004d1b4  mov     rcx, [rbx]; hObject
0x14004d1b7  lea     rdx, aChainingmode; "ChainingMode"
0x14004d1be  mov     r9d, 20h ; ' '; cbInput
0x14004d1c4  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14004d1cc  mov     r8, rdi; pbInput
0x14004d1cf  call    cs:__imp_BCryptSetProperty
0x14004d1d6  nop     dword ptr [rax+rax+00h]
0x14004d1db  test    eax, eax
0x14004d1dd  js      loc_14004D26C
0x14004d1e3  mov     rcx, [rbx]; hObject
0x14004d1e6  lea     rax, [rsp+58h+pcbResult]
0x14004d1eb  mov     [rsp+58h+var_30], 0; dwFlags
0x14004d1f3  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x14004d1f8  mov     r9d, 0Ch; cbOutput
0x14004d1fe  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x14004d203  lea     rdx, aAuthtaglength; "AuthTagLength"
0x14004d20a  call    cs:__imp_BCryptGetProperty
0x14004d211  nop     dword ptr [rax+rax+00h]
0x14004d216  test    eax, eax
0x14004d218  js      short loc_14004D26C
0x14004d21a  mov     r8d, 10h
0x14004d220  cmp     dword ptr [rsp+58h+pbOutput], r8d
0x14004d225  jbe     short loc_14004D22E
0x14004d227  mov     eax, 0C00000BBh
0x14004d22c  jmp     short loc_14004D26C
0x14004d22e  mov     eax, dword ptr [rsp+58h+pbOutput+4]
0x14004d232  cmp     eax, r8d
0x14004d235  ja      short loc_14004D23C
0x14004d237  mov     [rbx+0Ch], eax
0x14004d23a  jmp     short loc_14004D256
0x14004d23c  mov     ecx, dword ptr [rsp+58h+pbOutput]
0x14004d240  mov     rax, r8
0x14004d243  sub     rax, rcx
0x14004d246  xor     edx, edx
0x14004d248  mov     ecx, [rsp+58h+var_18]
0x14004d24c  div     rcx
0x14004d24f  sub     r8d, edx
0x14004d252  mov     [rbx+0Ch], r8d
0x14004d256  mov     eax, [rsp+58h+arg_20]
0x14004d25d  mov     [rbx+8], eax
0x14004d260  mov     eax, [rsp+58h+arg_28]
0x14004d267  mov     [rbx+10h], eax
0x14004d26a  xor     eax, eax
0x14004d26c  mov     rcx, [rsp+58h+var_10]
0x14004d271  xor     rcx, rsp; StackCookie
0x14004d274  call    __security_check_cookie
0x14004d279  mov     rbx, [rsp+58h+arg_8]
0x14004d27e  add     rsp, 50h
0x14004d282  pop     rdi
0x14004d283  retn
```
