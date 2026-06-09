# SHA2::Hash(void const *,ulong)

- ea: `0x180108a10`
- end: `0x180108b51`
- name: `?Hash@SHA2@@QEBA?AUDigest@1@PEBXK@Z`
- size: `321`
- prototype: `SHA2::Digest *__fastcall(SHA2 *this, SHA2::Digest *result, const void *input, unsigned int input)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1801090e8`

## callees

- `0x18000ae54`
- `0x18003617c`
- `0x1800bc3b0`
- `0x180108a10`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180108b24`
- `bcrypt!BCryptDestroyHash` at `0x18017f402`
- `bcrypt!BCryptDestroyHash` at `0x180108b24`
- `bcrypt!BCryptDestroyHash` at `0x18017f402`
- `bcrypt!BCryptGetProperty` at `0x180108a79`
- `bcrypt!BCryptGetProperty` at `0x180108a79`
- `bcrypt!BCryptHashData` at `0x180108aec`
- `bcrypt!BCryptHashData` at `0x180108aec`
- `bcrypt!BCryptFinishHash` at `0x180108b0d`
- `bcrypt!BCryptFinishHash` at `0x180108b0d`
- `bcrypt!BCryptCreateHash` at `0x180108acb`
- `bcrypt!BCryptCreateHash` at `0x180108acb`

## pseudocode

```c
SHA2::Digest *__fastcall SHA2::Hash(SHA2 *this, SHA2::Digest *result, unsigned __int8 *input, unsigned int a4)
{
  NTSTATUS Property; // eax
  unsigned __int8 *v7; // rbx
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  void *cryptHash; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int8 *pcbResult; // [rsp+60h] [rbp+8h] BYREF
  ULONG pbOutput; // [rsp+78h] [rbp+20h] BYREF

  HIDWORD(pcbResult) = HIDWORD(this);
  cryptHash = 0;
  *(_OWORD *)result->q = 0;
  *(_OWORD *)&result->q[2] = 0;
  LODWORD(pcbResult) = 0;
  pbOutput = 0;
  Property = BCryptGetProperty(sha2.m_bcrypt.m_handle, L"ObjectLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&pcbResult, 0);
  if ( Property < 0 )
    Exception::throwHR(Property);
  v7 = (unsigned __int8 *)_MemAlloc(pbOutput, 4);
  pcbResult = v7;
  v8 = BCryptCreateHash(sha2.m_bcrypt.m_handle, &cryptHash, v7, pbOutput, 0, 0, 0);
  if ( v8 < 0 )
    Exception::throwHR(v8);
  v9 = BCryptHashData(cryptHash, input, 0x18u, 0);
  if ( v9 < 0 )
    Exception::throwHR(v9);
  v10 = BCryptFinishHash(cryptHash, (PUCHAR)result, 0x20u, 0);
  if ( v10 < 0 )
    Exception::throwHR(v10);
  v11 = BCryptDestroyHash(cryptHash);
  if ( v11 < 0 )
    Exception::throwHR(v11);
  MemFree(v7);
  return result;
}

```

## disassembly

```asm
0x180108a10  mov     rax, rsp
0x180108a13  mov     [rax+10h], rbx
0x180108a17  mov     [rax+18h], rsi
0x180108a1b  mov     [rax+20h], r9d
0x180108a1f  mov     [rax+8], rcx
0x180108a23  push    rdi
0x180108a24  sub     rsp, 50h
0x180108a28  mov     rsi, input
0x180108a2b  mov     rdi, rdx
0x180108a2e  mov     qword ptr [rax-18h], 0
0x180108a36  xorps   xmm0, xmm0
0x180108a39  movups  xmmword ptr [rdx], xmm0
0x180108a3c  movups  xmmword ptr [rdx+10h], xmm0
0x180108a40  mov     dword ptr [rax+8], 0
0x180108a47  mov     dword ptr [rax+20h], 0
0x180108a4e  mov     dword ptr [rax-30h], 0
0x180108a55  lea     rax, [rax+8]
0x180108a59  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180108a5e  mov     ebx, 4
0x180108a63  mov     r9d, ebx; cbOutput
0x180108a66  lea     input, [rsp+58h+pbOutput]; pbOutput
0x180108a6b  lea     rdx, aObjectlength; "ObjectLength"
0x180108a72  mov     rcx, cs:sha2.m_bcrypt.m_handle; hObject
0x180108a79  call    cs:__imp_BCryptGetProperty
0x180108a7f  test    eax, eax
0x180108a81  jns     short loc_180108A8B
0x180108a83  mov     ecx, eax; hr
0x180108a85  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180108a8b  mov     ecx, [rsp+58h+pbOutput]; cb
0x180108a8f  mov     edx, ebx; dwFlags
0x180108a91  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180108a96  mov     rbx, rax
0x180108a99  mov     [rsp+58h+arg_0], rax
0x180108a9e  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180108aa6  mov     [rsp+58h+cbSecret], 0; cbSecret
0x180108aae  mov     [rsp+58h+pcbResult], 0; pbSecret
0x180108ab7  mov     r9d, [rsp+58h+pbOutput]; cbHashObject
0x180108abc  mov     input, rax; pbHashObject
0x180108abf  lea     rdx, [rsp+58h+cryptHash]; phHash
0x180108ac4  mov     rcx, cs:sha2.m_bcrypt.m_handle; hAlgorithm
0x180108acb  call    cs:__imp_BCryptCreateHash
0x180108ad1  test    eax, eax
0x180108ad3  jns     short loc_180108ADD
0x180108ad5  mov     ecx, eax; hr
0x180108ad7  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180108add  xor     r9d, r9d; dwFlags
0x180108ae0  lea     r8d, [r9+18h]; cbInput
0x180108ae4  mov     rdx, rsi; pbInput
0x180108ae7  mov     rcx, [rsp+58h+cryptHash]; hHash
0x180108aec  call    cs:__imp_BCryptHashData
0x180108af2  test    eax, eax
0x180108af4  jns     short loc_180108AFE
0x180108af6  mov     ecx, eax; hr
0x180108af8  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180108afe  xor     r9d, r9d; dwFlags
0x180108b01  lea     r8d, [r9+20h]; cbOutput
0x180108b05  mov     rdx, rdi; pbOutput
0x180108b08  mov     rcx, [rsp+58h+cryptHash]; hHash
0x180108b0d  call    cs:__imp_BCryptFinishHash
0x180108b13  test    eax, eax
0x180108b15  jns     short $LN8_36
0x180108b17  mov     ecx, eax; hr
0x180108b19  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180108b1f  mov     rcx, [rsp+58h+cryptHash]; hHash
0x180108b24  call    cs:__imp_BCryptDestroyHash
0x180108b2a  test    eax, eax
0x180108b2c  jns     short loc_180108B36
0x180108b2e  mov     ecx, eax; hr
0x180108b30  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180108b36  mov     rcx, rbx; pv
0x180108b39  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180108b3e  mov     rax, rdi
0x180108b41  mov     rbx, [rsp+58h+digest]
0x180108b46  mov     rsi, [rsp+58h+arg_10]
0x180108b4b  add     rsp, 50h
0x180108b4f  pop     rdi
0x180108b50  retn
0x18017f3f5  push    rbp
0x18017f3f7  sub     rsp, 40h
0x18017f3fb  mov     rbp, rdx
0x18017f3fe  mov     rcx, [rbp+40h]; hHash
0x18017f402  call    cs:__imp_BCryptDestroyHash
0x18017f408  test    eax, eax
0x18017f40a  jns     short loc_18017F414
0x18017f40c  mov     ecx, eax; hr
0x18017f40e  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18017f414  mov     rcx, [rbp+60h]; pv
0x18017f418  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18017f41d  nop
0x18017f41e  add     rsp, 40h
0x18017f422  pop     rbp
0x18017f423  retn
```
