# IDriverPrioritiesRestore

- ea: `0x180001ad0`
- end: `0x180001c2b`
- name: `IDriverPrioritiesRestore`
- size: `347`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800012a0`
- `0x180002900`
- `0x180005990`
- `0x180005e70`
- `0x1800089c0`
- `0x18000da50`
- `0x1800119c0`

## callees

- `0x180001210`
- `0x180001ad0`
- `0x180001c40`
- `0x180001cd0`
- `0x180001dc0`
- `0x180002220`
- `0x180009270`
- `0x18000afdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001b6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001b6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001b7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001b7e`

## pseudocode

```c
__int64 __fastcall IDriverPrioritiesRestore(__int64 a1)
{
  unsigned int v2; // esi
  HKEY v3; // rbx
  unsigned int v4; // r14d
  unsigned int i; // ebp
  __int64 v7; // r15
  DWORD Type; // [rsp+30h] [rbp-208h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-200h] BYREF
  wchar_t pszDest[32]; // [rsp+40h] [rbp-1F8h] BYREF
  BYTE Data[352]; // [rsp+80h] [rbp-1B8h] BYREF

  v2 = 0;
  v3 = IRegOpenKeyAcm(L"Priority v4.00");
  v4 = 1;
  for ( i = 1; ; ++i )
  {
    StringCchPrintfW(pszDest, 0x20u, L"Priority%u", i);
    Type = -2;
    cbData[0] = 352;
    if ( RegQueryValueExW(v3, pszDest, 0, &Type, Data, cbData) || Type != 1 )
      break;
    v7 = 0;
    *(_QWORD *)cbData = 0;
    while ( !(unsigned int)IDriverGetNext(a1, cbData, v7, 0xC0000000) )
    {
      v7 = *(_QWORD *)cbData;
      if ( (unsigned int)IDriverPrioritiesIsMatch(*(_QWORD *)cbData, Data) )
      {
        if ( v4 != *(_DWORD *)(v7 + 16) )
          v2 = 1;
        if ( !(unsigned int)IDriverPriority(a1, v7, v4, (unsigned int)(*(_WORD *)Data != 49) + 1) )
        {
          ++v4;
          break;
        }
      }
    }
  }
  if ( v3 )
    RegCloseKey(v3);
  IDriverRefreshPriority(a1);
  return v2;
}

```

## disassembly

```asm
0x180001ad0  push    rbx
0x180001ad2  push    rbp
0x180001ad3  push    rsi
0x180001ad4  push    rdi
0x180001ad5  push    r12
0x180001ad7  push    r13
0x180001ad9  push    r14
0x180001adb  push    r15
0x180001add  sub     rsp, 1F8h
0x180001ae4  mov     rax, cs:__security_cookie
0x180001aeb  xor     rax, rsp
0x180001aee  mov     [rsp+238h+var_58], rax
0x180001af6  mov     rdi, rcx
0x180001af9  xor     esi, esi
0x180001afb  lea     rcx, gszSecPriority; "Priority v4.00"
0x180001b02  call    IRegOpenKeyAcm
0x180001b07  mov     r12d, 1
0x180001b0d  mov     rbx, rax
0x180001b10  mov     r14d, r12d
0x180001b13  mov     ebp, r12d
0x180001b16  mov     r13d, 31h ; '1'
0x180001b1c  mov     r9d, ebp
0x180001b1f  lea     r8, gszKeyPriority; "Priority%u"
0x180001b26  mov     edx, 20h ; ' '; cchDest
0x180001b2b  lea     rcx, [rsp+238h+pszDest]; pszDest
0x180001b30  call    StringCchPrintfW
0x180001b35  lea     rax, [rsp+238h+cbData]
0x180001b3a  mov     [rsp+238h+Type], 0FFFFFFFEh
0x180001b42  mov     [rsp+238h+lpcbData], rax; lpcbData
0x180001b47  lea     r9, [rsp+238h+Type]; lpType
0x180001b4c  lea     rax, [rsp+238h+Data]
0x180001b54  mov     [rsp+238h+cbData], 160h
0x180001b5c  xor     r8d, r8d; lpReserved
0x180001b5f  mov     [rsp+238h+lpData], rax; lpData
0x180001b64  lea     rdx, [rsp+238h+pszDest]; lpValueName
0x180001b69  mov     rcx, rbx; hKey
0x180001b6c  call    cs:__imp_RegQueryValueExW
0x180001b72  test    eax, eax
0x180001b74  jz      short loc_180001BB2
0x180001b76  test    rbx, rbx
0x180001b79  jz      short loc_180001B84
0x180001b7b  mov     rcx, rbx; hKey
0x180001b7e  call    cs:__imp_RegCloseKey
0x180001b84  mov     rcx, rdi
0x180001b87  call    IDriverRefreshPriority
0x180001b8c  mov     eax, esi
0x180001b8e  mov     rcx, [rsp+238h+var_58]
0x180001b96  xor     rcx, rsp; StackCookie
0x180001b99  call    __security_check_cookie
0x180001b9e  add     rsp, 1F8h
0x180001ba5  pop     r15
0x180001ba7  pop     r14
0x180001ba9  pop     r13
0x180001bab  pop     r12
0x180001bad  pop     rdi
0x180001bae  pop     rsi
0x180001baf  pop     rbp
0x180001bb0  pop     rbx
0x180001bb1  retn
0x180001bb2  cmp     [rsp+238h+Type], r12d
0x180001bb7  jnz     short loc_180001B76
0x180001bb9  xor     r15d, r15d
0x180001bbc  mov     qword ptr [rsp+238h+cbData], r15
0x180001bc1  mov     r9d, 0C0000000h
0x180001bc7  lea     rdx, [rsp+238h+cbData]
0x180001bcc  mov     r8, r15
0x180001bcf  mov     rcx, rdi
0x180001bd2  call    IDriverGetNext
0x180001bd7  test    eax, eax
0x180001bd9  jnz     short loc_180001C24
0x180001bdb  mov     r15, qword ptr [rsp+238h+cbData]
0x180001be0  lea     rdx, [rsp+238h+Data]
0x180001be8  mov     rcx, r15
0x180001beb  call    IDriverPrioritiesIsMatch
0x180001bf0  test    eax, eax
0x180001bf2  jz      short loc_180001BC1
0x180001bf4  xor     r9d, r9d
0x180001bf7  mov     r8d, r14d
0x180001bfa  cmp     r13w, word ptr [rsp+238h+Data]
0x180001c03  mov     rdx, r15
0x180001c06  mov     rcx, rdi
0x180001c09  setnz   r9b
0x180001c0d  inc     r9d
0x180001c10  cmp     r14d, [r15+10h]
0x180001c14  cmovnz  esi, r12d
0x180001c18  call    IDriverPriority
0x180001c1d  test    eax, eax
0x180001c1f  jnz     short loc_180001BC1
0x180001c21  inc     r14d
0x180001c24  inc     ebp
0x180001c26  jmp     loc_180001B1C
```
