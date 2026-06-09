# Microsoft::Windows::Performance::CryptographicHasher::CryptographicHasher(ushort const *)

- ea: `0x1800221fc`
- end: `0x180022360`
- name: `??0CryptographicHasher@Performance@Windows@Microsoft@@QEAA@PEBG@Z`
- size: `356`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CryptographicHasher *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022c80`

## callees

- `0x1800221fc`
- `0x18002266c`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180022243`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180022243`
- `bcrypt!BCryptGetProperty` at `0x18002228e`
- `bcrypt!BCryptGetProperty` at `0x1800222e7`
- `bcrypt!BCryptGetProperty` at `0x18002228e`
- `bcrypt!BCryptGetProperty` at `0x1800222e7`
- `bcrypt!BCryptCreateHash` at `0x180022336`
- `bcrypt!BCryptCreateHash` at `0x180022336`

## pseudocode

```c
Microsoft::Windows::Performance::CryptographicHasher *__fastcall Microsoft::Windows::Performance::CryptographicHasher::CryptographicHasher(
        Microsoft::Windows::Performance::CryptographicHasher *this,
        const unsigned __int16 *a2)
{
  PUCHAR *v2; // rsi
  BCRYPT_HANDLE *v3; // rdi
  BCRYPT_HANDLE v5; // rcx
  ULONG pbOutput; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *pcbResult; // [rsp+68h] [rbp+10h] BYREF

  pcbResult = a2;
  *(_BYTE *)this = 0;
  v2 = (PUCHAR *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  v3 = (BCRYPT_HANDLE *)((char *)this + 8);
  *((_QWORD *)this + 4) = 0;
  if ( BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 1, L"SHA256", 0, 0x20u) >= 0 )
  {
    v5 = *v3;
    pbOutput = 0;
    LODWORD(pcbResult) = 0;
    if ( BCryptGetProperty(v5, L"ObjectLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&pcbResult, 0) >= 0
      && (_DWORD)pcbResult == 4
      && (unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(v2, pbOutput)
      && BCryptGetProperty(*v3, L"HashDigestLength", (PUCHAR)this + 40, 4u, (ULONG *)&pcbResult, 0) >= 0
      && (_DWORD)pcbResult == 4
      && (unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(
                            (char *)this + 32,
                            *((unsigned int *)this + 10))
      && BCryptCreateHash(*v3, (BCRYPT_HASH_HANDLE *)this + 2, *v2, pbOutput, 0, 0, 0x20u) >= 0 )
    {
      *(_BYTE *)this = 1;
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800221fc  mov     [rsp+arg_10], rbx
0x180022201  mov     [rsp+arg_18], rbp
0x180022206  mov     [rsp+arg_8], rdx
0x18002220b  push    rsi
0x18002220c  push    rdi
0x18002220d  push    r14
0x18002220f  sub     rsp, 40h
0x180022213  mov     byte ptr [rcx], 0
0x180022216  lea     rsi, [rcx+18h]
0x18002221a  mov     qword ptr [rsi], 0
0x180022221  lea     rdi, [rcx+8]
0x180022225  mov     qword ptr [rcx+20h], 0
0x18002222d  lea     rdx, pszAlgId; "SHA256"
0x180022234  mov     rbx, rcx
0x180022237  mov     r9d, 20h ; ' '; dwFlags
0x18002223d  mov     rcx, rdi; phAlgorithm
0x180022240  xor     r8d, r8d; pszImplementation
0x180022243  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002224a  nop     dword ptr [rax+rax+00h]
0x18002224f  test    eax, eax
0x180022251  js      loc_180022349
0x180022257  mov     rcx, [rdi]; hObject
0x18002225a  lea     rax, [rsp+58h+arg_8]
0x18002225f  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180022267  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x18002226c  mov     r9d, 4; cbOutput
0x180022272  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180022277  lea     rdx, pszProperty; "ObjectLength"
0x18002227e  mov     [rsp+58h+pbOutput], 0
0x180022286  mov     dword ptr [rsp+58h+arg_8], 0
0x18002228e  call    cs:__imp_BCryptGetProperty
0x180022295  nop     dword ptr [rax+rax+00h]
0x18002229a  test    eax, eax
0x18002229c  js      loc_180022349
0x1800222a2  cmp     dword ptr [rsp+58h+arg_8], 4
0x1800222a7  jnz     loc_180022349
0x1800222ad  mov     edx, [rsp+58h+pbOutput]
0x1800222b1  mov     rcx, rsi
0x1800222b4  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1800222b9  test    al, al
0x1800222bb  jz      loc_180022349
0x1800222c1  mov     rcx, [rdi]; hObject
0x1800222c4  lea     rax, [rsp+58h+arg_8]
0x1800222c9  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800222d1  lea     r8, [rbx+28h]; pbOutput
0x1800222d5  mov     r9d, 4; cbOutput
0x1800222db  mov     [rsp+58h+pcbResult], rax; pcbResult
0x1800222e0  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800222e7  call    cs:__imp_BCryptGetProperty
0x1800222ee  nop     dword ptr [rax+rax+00h]
0x1800222f3  test    eax, eax
0x1800222f5  js      short loc_180022349
0x1800222f7  cmp     dword ptr [rsp+58h+arg_8], 4
0x1800222fc  jnz     short loc_180022349
0x1800222fe  mov     edx, [rbx+28h]
0x180022301  lea     rcx, [rbx+20h]
0x180022305  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18002230a  test    al, al
0x18002230c  jz      short loc_180022349
0x18002230e  mov     r9d, [rsp+58h+pbOutput]; cbHashObject
0x180022313  lea     rdx, [rbx+10h]; phHash
0x180022317  mov     r8, [rsi]; pbHashObject
0x18002231a  mov     rcx, [rdi]; hAlgorithm
0x18002231d  mov     [rsp+58h+var_28], 20h ; ' '; dwFlags
0x180022325  mov     [rsp+58h+dwFlags], 0; cbSecret
0x18002232d  mov     [rsp+58h+pcbResult], 0; pbSecret
0x180022336  call    cs:__imp_BCryptCreateHash
0x18002233d  nop     dword ptr [rax+rax+00h]
0x180022342  test    eax, eax
0x180022344  js      short loc_180022349
0x180022346  mov     byte ptr [rbx], 1
0x180022349  mov     rbp, [rsp+58h+arg_18]
0x18002234e  mov     rax, rbx
0x180022351  mov     rbx, [rsp+58h+arg_10]
0x180022356  add     rsp, 40h
0x18002235a  pop     r14
0x18002235c  pop     rdi
0x18002235d  pop     rsi
0x18002235e  retn
```
