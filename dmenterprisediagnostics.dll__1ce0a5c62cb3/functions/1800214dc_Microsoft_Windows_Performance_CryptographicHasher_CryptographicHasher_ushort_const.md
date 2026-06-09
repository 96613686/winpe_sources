# Microsoft::Windows::Performance::CryptographicHasher::CryptographicHasher(ushort const *)

- ea: `0x1800214dc`
- end: `0x180021623`
- name: `??0CryptographicHasher@Performance@Windows@Microsoft@@QEAA@PEBG@Z`
- size: `327`
- prototype: `Microsoft::Windows::Performance::CryptographicHasher *__fastcall(Microsoft::Windows::Performance::CryptographicHasher *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021ee0`

## callees

- `0x1800214dc`
- `0x18002191c`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180021523`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180021523`
- `bcrypt!BCryptGetProperty` at `0x180021568`
- `bcrypt!BCryptGetProperty` at `0x1800215b7`
- `bcrypt!BCryptGetProperty` at `0x180021568`
- `bcrypt!BCryptGetProperty` at `0x1800215b7`
- `bcrypt!BCryptCreateHash` at `0x180021600`
- `bcrypt!BCryptCreateHash` at `0x180021600`

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
0x1800214dc  mov     [rsp+arg_10], rbx
0x1800214e1  mov     [rsp+arg_18], rbp
0x1800214e6  mov     [rsp+arg_8], rdx
0x1800214eb  push    rsi
0x1800214ec  push    rdi
0x1800214ed  push    r14
0x1800214ef  sub     rsp, 40h
0x1800214f3  mov     byte ptr [rcx], 0
0x1800214f6  lea     rsi, [rcx+18h]
0x1800214fa  mov     qword ptr [rsi], 0
0x180021501  lea     rdi, [rcx+8]
0x180021505  mov     qword ptr [rcx+20h], 0
0x18002150d  lea     rdx, pszAlgId; "SHA256"
0x180021514  mov     rbx, rcx
0x180021517  mov     r9d, 20h ; ' '; dwFlags
0x18002151d  mov     rcx, rdi; phAlgorithm
0x180021520  xor     r8d, r8d; pszImplementation
0x180021523  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180021529  test    eax, eax
0x18002152b  js      loc_18002160D
0x180021531  mov     rcx, [rdi]; hObject
0x180021534  lea     rax, [rsp+58h+arg_8]
0x180021539  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180021541  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x180021546  mov     r9d, 4; cbOutput
0x18002154c  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180021551  lea     rdx, pszProperty; "ObjectLength"
0x180021558  mov     [rsp+58h+pbOutput], 0
0x180021560  mov     dword ptr [rsp+58h+arg_8], 0
0x180021568  call    cs:__imp_BCryptGetProperty
0x18002156e  test    eax, eax
0x180021570  js      loc_18002160D
0x180021576  cmp     dword ptr [rsp+58h+arg_8], 4
0x18002157b  jnz     loc_18002160D
0x180021581  mov     edx, [rsp+58h+pbOutput]
0x180021585  mov     rcx, rsi
0x180021588  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18002158d  test    al, al
0x18002158f  jz      short loc_18002160D
0x180021591  mov     rcx, [rdi]; hObject
0x180021594  lea     rax, [rsp+58h+arg_8]
0x180021599  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800215a1  lea     r8, [rbx+28h]; pbOutput
0x1800215a5  mov     r9d, 4; cbOutput
0x1800215ab  mov     [rsp+58h+pcbResult], rax; pcbResult
0x1800215b0  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800215b7  call    cs:__imp_BCryptGetProperty
0x1800215bd  test    eax, eax
0x1800215bf  js      short loc_18002160D
0x1800215c1  cmp     dword ptr [rsp+58h+arg_8], 4
0x1800215c6  jnz     short loc_18002160D
0x1800215c8  mov     edx, [rbx+28h]
0x1800215cb  lea     rcx, [rbx+20h]
0x1800215cf  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1800215d4  test    al, al
0x1800215d6  jz      short loc_18002160D
0x1800215d8  mov     r9d, [rsp+58h+pbOutput]; cbHashObject
0x1800215dd  lea     rdx, [rbx+10h]; phHash
0x1800215e1  mov     r8, [rsi]; pbHashObject
0x1800215e4  mov     rcx, [rdi]; hAlgorithm
0x1800215e7  mov     [rsp+58h+var_28], 20h ; ' '; dwFlags
0x1800215ef  mov     [rsp+58h+dwFlags], 0; cbSecret
0x1800215f7  mov     [rsp+58h+pcbResult], 0; pbSecret
0x180021600  call    cs:__imp_BCryptCreateHash
0x180021606  test    eax, eax
0x180021608  js      short loc_18002160D
0x18002160a  mov     byte ptr [rbx], 1
0x18002160d  mov     rbp, [rsp+58h+arg_18]
0x180021612  mov     rax, rbx
0x180021615  mov     rbx, [rsp+58h+arg_10]
0x18002161a  add     rsp, 40h
0x18002161e  pop     r14
0x180021620  pop     rdi
0x180021621  pop     rsi
0x180021622  retn
```
