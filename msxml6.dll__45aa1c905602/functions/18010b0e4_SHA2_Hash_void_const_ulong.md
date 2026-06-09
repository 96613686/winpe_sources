# SHA2::Hash(void const *,ulong)

- ea: `0x18010b0e4`
- end: `0x18010b244`
- name: `?Hash@SHA2@@QEBA?AUDigest@1@PEBXK@Z`
- size: `352`
- prototype: `SHA2::Digest *__fastcall(SHA2 *this, SHA2::Digest *result, const void *input, unsigned int input)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18010b7f0`

## callees

- `0x1800101e4`
- `0x180017480`
- `0x1800bda08`
- `0x18010b0e4`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18010b210`
- `bcrypt!BCryptDestroyHash` at `0x1801830c0`
- `bcrypt!BCryptDestroyHash` at `0x18010b210`
- `bcrypt!BCryptDestroyHash` at `0x1801830c0`
- `bcrypt!BCryptGetProperty` at `0x18010b14d`
- `bcrypt!BCryptGetProperty` at `0x18010b14d`
- `bcrypt!BCryptHashData` at `0x18010b1cc`
- `bcrypt!BCryptHashData` at `0x18010b1cc`
- `bcrypt!BCryptFinishHash` at `0x18010b1f3`
- `bcrypt!BCryptFinishHash` at `0x18010b1f3`
- `bcrypt!BCryptCreateHash` at `0x18010b1a5`
- `bcrypt!BCryptCreateHash` at `0x18010b1a5`

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
  v7 = (unsigned __int8 *)_MemAlloc(pbOutput, 4u);
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
0x18010b0e4  mov     rax, rsp
0x18010b0e7  mov     [rax+10h], rbx
0x18010b0eb  mov     [rax+18h], rsi
0x18010b0ef  mov     [rax+20h], r9d
0x18010b0f3  mov     [rax+8], rcx
0x18010b0f7  push    rdi
0x18010b0f8  sub     rsp, 50h
0x18010b0fc  mov     rsi, input
0x18010b0ff  mov     rdi, rdx
0x18010b102  mov     qword ptr [rax-18h], 0
0x18010b10a  xorps   xmm0, xmm0
0x18010b10d  movups  xmmword ptr [rdx], xmm0
0x18010b110  movups  xmmword ptr [rdx+10h], xmm0
0x18010b114  mov     dword ptr [rax+8], 0
0x18010b11b  mov     dword ptr [rax+20h], 0
0x18010b122  mov     dword ptr [rax-30h], 0
0x18010b129  lea     rax, [rax+8]
0x18010b12d  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18010b132  mov     ebx, 4
0x18010b137  mov     r9d, ebx; cbOutput
0x18010b13a  lea     input, [rsp+58h+pbOutput]; pbOutput
0x18010b13f  lea     rdx, aObjectlength; "ObjectLength"
0x18010b146  mov     rcx, cs:sha2.m_bcrypt.m_handle; hObject
0x18010b14d  call    cs:__imp_BCryptGetProperty
0x18010b154  nop     dword ptr [rax+rax+00h]
0x18010b159  test    eax, eax
0x18010b15b  jns     short loc_18010B165
0x18010b15d  mov     ecx, eax; hr
0x18010b15f  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18010b165  mov     ecx, [rsp+58h+pbOutput]; cb
0x18010b169  mov     edx, ebx; dwFlags
0x18010b16b  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18010b170  mov     rbx, rax
0x18010b173  mov     [rsp+58h+arg_0], rax
0x18010b178  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18010b180  mov     [rsp+58h+cbSecret], 0; cbSecret
0x18010b188  mov     [rsp+58h+pcbResult], 0; pbSecret
0x18010b191  mov     r9d, [rsp+58h+pbOutput]; cbHashObject
0x18010b196  mov     input, rax; pbHashObject
0x18010b199  lea     rdx, [rsp+58h+cryptHash]; phHash
0x18010b19e  mov     rcx, cs:sha2.m_bcrypt.m_handle; hAlgorithm
0x18010b1a5  call    cs:__imp_BCryptCreateHash
0x18010b1ac  nop     dword ptr [rax+rax+00h]
0x18010b1b1  test    eax, eax
0x18010b1b3  jns     short loc_18010B1BD
0x18010b1b5  mov     ecx, eax; hr
0x18010b1b7  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18010b1bd  xor     r9d, r9d; dwFlags
0x18010b1c0  lea     r8d, [r9+18h]; cbInput
0x18010b1c4  mov     rdx, rsi; pbInput
0x18010b1c7  mov     rcx, [rsp+58h+cryptHash]; hHash
0x18010b1cc  call    cs:__imp_BCryptHashData
0x18010b1d3  nop     dword ptr [rax+rax+00h]
0x18010b1d8  test    eax, eax
0x18010b1da  jns     short loc_18010B1E4
0x18010b1dc  mov     ecx, eax; hr
0x18010b1de  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18010b1e4  xor     r9d, r9d; dwFlags
0x18010b1e7  lea     r8d, [r9+20h]; cbOutput
0x18010b1eb  mov     rdx, rdi; pbOutput
0x18010b1ee  mov     rcx, [rsp+58h+cryptHash]; hHash
0x18010b1f3  call    cs:__imp_BCryptFinishHash
0x18010b1fa  nop     dword ptr [rax+rax+00h]
0x18010b1ff  test    eax, eax
0x18010b201  jns     short $LN8_36
0x18010b203  mov     ecx, eax; hr
0x18010b205  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18010b20b  mov     rcx, [rsp+58h+cryptHash]; hHash
0x18010b210  call    cs:__imp_BCryptDestroyHash
0x18010b217  nop     dword ptr [rax+rax+00h]
0x18010b21c  test    eax, eax
0x18010b21e  jns     short loc_18010B228
0x18010b220  mov     ecx, eax; hr
0x18010b222  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18010b228  mov     rcx, rbx; pv
0x18010b22b  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18010b230  mov     rax, rdi
0x18010b233  mov     rbx, [rsp+58h+digest]
0x18010b238  mov     rsi, [rsp+58h+arg_10]
0x18010b23d  add     rsp, 50h
0x18010b241  pop     rdi
0x18010b242  retn
0x1801830b3  push    rbp
0x1801830b5  sub     rsp, 40h
0x1801830b9  mov     rbp, rdx
0x1801830bc  mov     rcx, [rbp+40h]; hHash
0x1801830c0  call    cs:__imp_BCryptDestroyHash
0x1801830c7  nop     dword ptr [rax+rax+00h]
0x1801830cc  test    eax, eax
0x1801830ce  jns     short loc_1801830D8
0x1801830d0  mov     ecx, eax; hr
0x1801830d2  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1801830d8  mov     rcx, [rbp+60h]; pv
0x1801830dc  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1801830e1  nop
0x1801830e2  add     rsp, 40h
0x1801830e6  pop     rbp
0x1801830e7  retn
```
