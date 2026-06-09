# I_CryptGetCNGAlgorithmProvider

- ea: `0x18002a8bc`
- end: `0x18002aa41`
- name: `I_CryptGetCNGAlgorithmProvider`
- size: `389`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002b7b0`
- `0x18002bc30`
- `0x180089450`
- `0x1800ad1f8`
- `0x1800b1b68`
- `0x1800e2634`
- `0x1801012c8`
- `0x18010a04c`
- `0x18010a2b8`
- `0x18010ff64`

## callees

- `0x18002a8bc`
- `0x18002aa48`
- `0x18002bbd4`
- `0x180081758`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a996`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a9d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a996`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a9d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a942`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a9f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a942`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a9f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a8fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a927`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a973`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a8fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a927`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a973`

## pseudocode

```c
__int64 __fastcall I_CryptGetCNGAlgorithmProvider(unsigned int a1, const WCHAR *a2, unsigned int a3)
{
  __int64 v3; // r14
  void *CNGAlgorithmProviderContext; // rdi
  __int64 i; // rbx
  __int64 v9; // rax

  v3 = a1;
  if ( CompareStringW(0x409u, 1u, a2, -1, L"ECDSA", -1) == 2 || CompareStringW(0x409u, 1u, a2, -1, L"ECDH", -1) == 2 )
    return CreateCNGAlgorithmProviderContext((unsigned int)v3, a2, a3);
  CNGAlgorithmProviderContext = 0;
  _mm_lfence();
  EnterCriticalSection(&stru_18015CDD8);
  for ( i = qword_18015CE00[v3];
        i && (CompareStringW(0x409u, 1u, a2, -1, *(PCNZWCH *)(i + 16), -1) != 2 || a3 != *(_DWORD *)(i + 24));
        i = *(_QWORD *)i )
  {
    ;
  }
  if ( !i )
  {
    LeaveCriticalSection(&stru_18015CDD8);
    CNGAlgorithmProviderContext = (void *)CreateCNGAlgorithmProviderContext((unsigned int)v3, a2, a3);
    if ( !CNGAlgorithmProviderContext )
      goto LABEL_9;
    EnterCriticalSection(&stru_18015CDD8);
    i = FindCNGAlgorithmProviderContext((unsigned int)v3, a2, a3);
    if ( !i )
    {
      i = (__int64)CNGAlgorithmProviderContext;
      v9 = qword_18015CE00[v3];
      CNGAlgorithmProviderContext = 0;
      qword_18015CE00[v3] = i;
      *(_QWORD *)i = v9;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)(i + 8));
  LeaveCriticalSection(&stru_18015CDD8);
LABEL_9:
  if ( CNGAlgorithmProviderContext )
    I_CryptReleaseCNGAlgorithmProvider(CNGAlgorithmProviderContext);
  return i;
}

```

## disassembly

```asm
0x18002a8bc  push    rbx
0x18002a8be  push    rbp
0x18002a8bf  push    rsi
0x18002a8c0  push    rdi
0x18002a8c1  push    r12
0x18002a8c3  push    r14
0x18002a8c5  push    r15
0x18002a8c7  sub     rsp, 30h
0x18002a8cb  or      r12d, 0FFFFFFFFh
0x18002a8cf  mov     r14d, ecx
0x18002a8d2  mov     ebp, r8d
0x18002a8d5  mov     [rsp+68h+cchCount2], r12d; cchCount2
0x18002a8da  mov     rsi, rdx
0x18002a8dd  lea     rax, aEcdsa; "ECDSA"
0x18002a8e4  mov     r8, rdx; lpString1
0x18002a8e7  mov     [rsp+68h+lpString2], rax; lpString2
0x18002a8ec  lea     ebx, [r12+2]
0x18002a8f1  mov     edi, 409h
0x18002a8f6  mov     edx, ebx; dwCmpFlags
0x18002a8f8  mov     r9d, r12d; cchCount1
0x18002a8fb  mov     ecx, edi; Locale
0x18002a8fd  call    cs:__imp_CompareStringW
0x18002a903  cmp     eax, 2
0x18002a906  jz      loc_18002A9BE
0x18002a90c  lea     rax, aEcdh; "ECDH"
0x18002a913  mov     [rsp+68h+cchCount2], r12d; cchCount2
0x18002a918  mov     r9d, r12d; cchCount1
0x18002a91b  mov     [rsp+68h+lpString2], rax; lpString2
0x18002a920  mov     r8, rsi; lpString1
0x18002a923  mov     edx, ebx; dwCmpFlags
0x18002a925  mov     ecx, edi; Locale
0x18002a927  call    cs:__imp_CompareStringW
0x18002a92d  cmp     eax, 2
0x18002a930  jz      loc_18002A9BE
0x18002a936  xor     edi, edi
0x18002a938  lfence
0x18002a93b  lea     rcx, stru_18015CDD8; lpCriticalSection
0x18002a942  call    cs:__imp_EnterCriticalSection
0x18002a948  lea     rax, qword_18015CE00
0x18002a94f  mov     rbx, [rax+r14*8]
0x18002a953  jmp     short loc_18002A981
0x18002a955  mov     rax, [rbx+10h]
0x18002a959  mov     r9d, r12d; cchCount1
0x18002a95c  mov     [rsp+68h+cchCount2], r12d; cchCount2
0x18002a961  mov     r8, rsi; lpString1
0x18002a964  mov     edx, 1; dwCmpFlags
0x18002a969  mov     [rsp+68h+lpString2], rax; lpString2
0x18002a96e  mov     ecx, 409h; Locale
0x18002a973  call    cs:__imp_CompareStringW
0x18002a979  cmp     eax, 2
0x18002a97c  jz      short loc_18002A9B7
0x18002a97e  mov     rbx, [rbx]
0x18002a981  test    rbx, rbx
0x18002a984  jnz     short loc_18002A955
0x18002a986  test    rbx, rbx
0x18002a989  jz      short loc_18002A9CE
0x18002a98b  lock inc dword ptr [rbx+8]
0x18002a98f  lea     rcx, stru_18015CDD8; lpCriticalSection
0x18002a996  call    cs:__imp_LeaveCriticalSection
0x18002a99c  test    rdi, rdi
0x18002a99f  jnz     loc_18002AA34
0x18002a9a5  mov     rax, rbx
0x18002a9a8  add     rsp, 30h
0x18002a9ac  pop     r15
0x18002a9ae  pop     r14
0x18002a9b0  pop     r12
0x18002a9b2  pop     rdi
0x18002a9b3  pop     rsi
0x18002a9b4  pop     rbp
0x18002a9b5  pop     rbx
0x18002a9b6  retn
0x18002a9b7  cmp     ebp, [rbx+18h]
0x18002a9ba  jnz     short loc_18002A97E
0x18002a9bc  jmp     short loc_18002A986
0x18002a9be  mov     r8d, ebp
0x18002a9c1  mov     rdx, rsi
0x18002a9c4  mov     ecx, r14d
0x18002a9c7  call    CreateCNGAlgorithmProviderContext
0x18002a9cc  jmp     short loc_18002A9A8
0x18002a9ce  lea     rcx, stru_18015CDD8; lpCriticalSection
0x18002a9d5  call    cs:__imp_LeaveCriticalSection
0x18002a9db  mov     r8d, ebp
0x18002a9de  mov     rdx, rsi
0x18002a9e1  mov     ecx, r14d
0x18002a9e4  call    CreateCNGAlgorithmProviderContext
0x18002a9e9  mov     rdi, rax
0x18002a9ec  test    rax, rax
0x18002a9ef  jz      short loc_18002A99C
0x18002a9f1  lea     rcx, stru_18015CDD8; lpCriticalSection
0x18002a9f8  call    cs:__imp_EnterCriticalSection
0x18002a9fe  mov     r8d, ebp
0x18002aa01  mov     rdx, rsi
0x18002aa04  mov     ecx, r14d
0x18002aa07  call    FindCNGAlgorithmProviderContext
0x18002aa0c  mov     rbx, rax
0x18002aa0f  test    rax, rax
0x18002aa12  jnz     loc_18002A98B
0x18002aa18  mov     rbx, rdi
0x18002aa1b  lea     rcx, qword_18015CE00
0x18002aa22  mov     rax, [rcx+r14*8]
0x18002aa26  xor     edi, edi
0x18002aa28  mov     [rcx+r14*8], rbx
0x18002aa2c  mov     [rbx], rax
0x18002aa2f  jmp     loc_18002A98B
0x18002aa34  mov     rcx, rdi; hMem
0x18002aa37  call    I_CryptReleaseCNGAlgorithmProvider
0x18002aa3c  jmp     loc_18002A9A5
```
