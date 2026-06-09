# PsmpReadRefillRates

- ea: `0x18001752c`
- end: `0x18001764a`
- name: `PsmpReadRefillRates`
- size: `286`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180020f3c`

## callees

- `0x18001752c`
- `0x180017650`
- `0x180019d64`
- `0x18001b7e0`
- `0x1800226ec`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800175be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800175be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800175e6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800175e6`

## pseudocode

```c
__int64 __fastcall PsmpReadRefillRates(int *a1)
{
  __int64 v2; // rbx
  __int64 i; // rdi
  __int64 result; // rax
  int v5; // edx
  int v6; // r8d
  wchar_t pszDest[264]; // [rsp+40h] [rbp-258h] BYREF

  v2 = 0;
  do
  {
    for ( i = 0; i != 3; ++i )
    {
      StringCchPrintfW(pszDest, 0x104u, L"%ws%wsRefillRate", PsmpTypeName[v2], PsmpStateName[i]);
      result = PsmpReadRegUlongWithPrefix(KeyHandle, PsmpQuotaName[*a1], pszDest);
      if ( (int)result >= 0 )
      {
        RtlAcquireSRWLockExclusive(&PsmpPolicyLock);
        *(_QWORD *)&a1[4 * v2 + 56 + 2 * (unsigned int)v2 + 2 * i] = 0;
        result = RtlReleaseSRWLockExclusive(&PsmpPolicyLock);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          result = WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, (unsigned int)pszDest, 0);
      }
    }
    v2 = (unsigned int)(v2 + 1);
  }
  while ( (unsigned int)v2 < 2 );
  return result;
}

```

## disassembly

```asm
0x18001752c  push    rbx
0x18001752e  push    rbp
0x18001752f  push    rsi
0x180017530  push    rdi
0x180017531  push    r14
0x180017533  push    r15
0x180017535  sub     rsp, 268h
0x18001753c  mov     rax, cs:__security_cookie
0x180017543  xor     rax, rsp
0x180017546  mov     [rsp+298h+var_48], rax
0x18001754e  mov     rbp, rcx
0x180017551  mov     [rsp+298h+var_268], 0
0x180017559  xor     ebx, ebx
0x18001755b  lea     r15, __ImageBase
0x180017562  mov     esi, ebx
0x180017564  xor     edi, edi
0x180017566  mov     rax, ds:rva PsmpStateName[r15+rdi*8]
0x18001756e  lea     r8, aWsWsrefillrate; "%ws%wsRefillRate"
0x180017575  mov     r9, ds:rva PsmpTypeName[r15+rbx*8]
0x18001757d  lea     rcx, [rsp+298h+pszDest]; pszDest
0x180017582  mov     edx, 104h; cchDest
0x180017587  mov     [rsp+298h+var_278], rax
0x18001758c  call    StringCchPrintfW
0x180017591  movsxd  rdx, dword ptr [rbp+0]
0x180017595  lea     r9, [rsp+298h+var_268]
0x18001759a  mov     rcx, cs:KeyHandle; KeyHandle
0x1800175a1  lea     r8, [rsp+298h+pszDest]; SourceString
0x1800175a6  mov     rdx, ds:rva PsmpQuotaName[r15+rdx*8]; pszSrc
0x1800175ae  call    PsmpReadRegUlongWithPrefix
0x1800175b3  test    eax, eax
0x1800175b5  js      short loc_180017612
0x1800175b7  lea     rcx, PsmpPolicyLock
0x1800175be  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800175c4  mov     edx, [rbp+4]
0x1800175c7  lea     rcx, [rdi+rbx*2]
0x1800175cb  mov     r14d, [rsp+298h+var_268]
0x1800175d0  add     rcx, rsi
0x1800175d3  imul    rdx, r14
0x1800175d7  mov     [rbp+rcx*8+0E0h], rdx
0x1800175df  lea     rcx, PsmpPolicyLock
0x1800175e6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800175ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175f3  test    byte ptr [rcx+1Ch], 1
0x1800175f7  jz      short loc_180017612
0x1800175f9  cmp     byte ptr [rcx+19h], 4
0x1800175fd  jb      short loc_180017612
0x1800175ff  mov     rcx, [rcx+10h]
0x180017603  lea     r9, [rsp+298h+pszDest]
0x180017608  mov     dword ptr [rsp+298h+var_278], r14d
0x18001760d  call    WPP_SF_SD
0x180017612  inc     rdi
0x180017615  cmp     rdi, 3
0x180017619  jnz     loc_180017566
0x18001761f  inc     ebx
0x180017621  cmp     ebx, 2
0x180017624  jb      loc_180017562
0x18001762a  mov     rcx, [rsp+298h+var_48]
0x180017632  xor     rcx, rsp; StackCookie
0x180017635  call    __security_check_cookie
0x18001763a  add     rsp, 268h
0x180017641  pop     r15
0x180017643  pop     r14
0x180017645  pop     rdi
0x180017646  pop     rsi
0x180017647  pop     rbp
0x180017648  pop     rbx
0x180017649  retn
```
