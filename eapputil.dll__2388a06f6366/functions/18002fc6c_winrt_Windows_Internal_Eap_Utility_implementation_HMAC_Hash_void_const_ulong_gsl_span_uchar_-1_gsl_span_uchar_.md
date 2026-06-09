# winrt::Windows::Internal::Eap::Utility::implementation::HMAC_Hash(void * const,ulong,gsl::span<uchar,-1>,gsl::span<uchar,-1>,gsl::span<uchar,-1>)

- ea: `0x18002fc6c`
- end: `0x18002fdb7`
- name: `?HMAC_Hash@implementation@Utility@Eap@Internal@Windows@winrt@@YAXQEAXKV?$span@E$0?0@gsl@@11@Z`
- size: `331`
- prototype: `void __fastcall(BCRYPT_ALG_HANDLE hAlgorithm, ULONG cbHashObject, __int64, __int64, _QWORD *phHash)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180030020`

## callees

- `0x1800101c4`
- `0x18001767c`
- `0x180025cd0`
- `0x18002fc6c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18002fcdc`
- `bcrypt!BCryptCreateHash` at `0x18002fcdc`
- `bcrypt!BCryptHashData` at `0x18002fd09`
- `bcrypt!BCryptHashData` at `0x18002fd09`
- `bcrypt!BCryptFinishHash` at `0x18002fd31`
- `bcrypt!BCryptFinishHash` at `0x18002fd31`
- `bcrypt!BCryptDestroyHash` at `0x18002fd50`
- `bcrypt!BCryptDestroyHash` at `0x18002fd50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::HMAC_Hash(
        BCRYPT_ALG_HANDLE hAlgorithm,
        ULONG cbHashObject,
        __int64 a3,
        __int64 a4,
        _QWORD *phHash)
{
  _QWORD *v9; // r14
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int pbSecret; // [rsp+20h] [rbp-78h]
  PUCHAR pbHashObject[3]; // [rsp+40h] [rbp-58h] BYREF
  char *v15[8]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v9 = phHash;
  std::vector<unsigned char>::vector<unsigned char>(v15, *phHash);
  std::vector<unsigned char>::vector<unsigned char>(pbHashObject, cbHashObject);
  phHash = 0;
  v10 = BCryptCreateHash(
          hAlgorithm,
          (BCRYPT_HASH_HANDLE *)&phHash,
          pbHashObject[0],
          cbHashObject,
          *(PUCHAR *)(a3 + 8),
          *(_DWORD *)a3,
          0)
      | 0x10000000;
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v10,
      pbSecret);
  v11 = BCryptHashData(phHash, *(PUCHAR *)(a4 + 8), *(_DWORD *)a4, 0) | 0x10000000;
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v11,
      pbSecret);
  v12 = BCryptFinishHash(phHash, (PUCHAR)v9[1], *(_DWORD *)v9, 0) | 0x10000000;
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v12,
      pbSecret);
  if ( phHash )
    BCryptDestroyHash(phHash);
  std::vector<unsigned char>::~vector<unsigned char>((char **)pbHashObject);
  std::vector<unsigned char>::~vector<unsigned char>(v15);
}

```

## disassembly

```asm
0x18002fc6c  push    rbx
0x18002fc6e  push    rsi
0x18002fc6f  push    rdi
0x18002fc70  push    r14
0x18002fc72  push    r15
0x18002fc74  sub     rsp, 70h
0x18002fc78  mov     r15, r9
0x18002fc7b  mov     rbx, r8
0x18002fc7e  mov     edi, edx
0x18002fc80  mov     rsi, rcx
0x18002fc83  mov     r14, [rsp+98h+phHash]
0x18002fc8b  mov     rdx, [r14]
0x18002fc8e  lea     rcx, [rsp+98h+var_40]
0x18002fc93  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18002fc98  nop
0x18002fc99  mov     edx, edi
0x18002fc9b  lea     rcx, [rsp+98h+pbHashObject]
0x18002fca0  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18002fca5  nop
0x18002fca6  mov     [rsp+98h+phHash], 0
0x18002fcb2  mov     [rsp+98h+dwFlags], 0; dwFlags
0x18002fcba  mov     eax, [rbx]
0x18002fcbc  mov     [rsp+98h+cbSecret], eax; cbSecret
0x18002fcc0  mov     rax, [rbx+8]
0x18002fcc4  mov     [rsp+98h+pbSecret], rax; int
0x18002fcc9  mov     r9d, edi; cbHashObject
0x18002fccc  mov     r8, [rsp+98h+pbHashObject]; pbHashObject
0x18002fcd1  lea     rdx, [rsp+98h+phHash]; phHash
0x18002fcd9  mov     rcx, rsi; hAlgorithm
0x18002fcdc  call    cs:__imp_BCryptCreateHash
0x18002fce2  mov     ebx, 10000000h
0x18002fce7  or      eax, ebx
0x18002fce9  mov     rcx, [rsp+98h]; this
0x18002fcf1  jl      loc_18002FD8D
0x18002fcf7  xor     r9d, r9d; dwFlags
0x18002fcfa  mov     r8d, [r15]; cbInput
0x18002fcfd  mov     rdx, [r15+8]; pbInput
0x18002fd01  mov     rcx, [rsp+98h+phHash]; hHash
0x18002fd09  call    cs:__imp_BCryptHashData
0x18002fd0f  or      eax, ebx
0x18002fd11  mov     rcx, [rsp+98h]; this
0x18002fd19  jl      loc_18002FDA2
0x18002fd1f  xor     r9d, r9d; dwFlags
0x18002fd22  mov     r8d, [r14]; cbOutput
0x18002fd25  mov     rdx, [r14+8]; pbOutput
0x18002fd29  mov     rcx, [rsp+98h+phHash]; hHash
0x18002fd31  call    cs:__imp_BCryptFinishHash
0x18002fd37  or      eax, ebx
0x18002fd39  mov     rcx, [rsp+98h]; this
0x18002fd41  jl      short loc_18002FD78
0x18002fd43  mov     rcx, [rsp+98h+phHash]; hHash
0x18002fd4b  test    rcx, rcx
0x18002fd4e  jz      short loc_18002FD57
0x18002fd50  call    cs:__imp_BCryptDestroyHash
0x18002fd56  nop
0x18002fd57  lea     rcx, [rsp+98h+pbHashObject]
0x18002fd5c  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002fd61  nop
0x18002fd62  lea     rcx, [rsp+98h+var_40]
0x18002fd67  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002fd6c  add     rsp, 70h
0x18002fd70  pop     r15
0x18002fd72  pop     r14
0x18002fd74  pop     rdi
0x18002fd75  pop     rsi
0x18002fd76  pop     rbx
0x18002fd77  retn
0x18002fd78  mov     r9d, eax; char *
0x18002fd7b  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002fd82  mov     edx, 1Ch; void *
0x18002fd87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fd8d  mov     r9d, eax; char *
0x18002fd90  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002fd97  mov     edx, 19h; void *
0x18002fd9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fda2  mov     r9d, eax; char *
0x18002fda5  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002fdac  mov     edx, 1Ah; void *
0x18002fdb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
