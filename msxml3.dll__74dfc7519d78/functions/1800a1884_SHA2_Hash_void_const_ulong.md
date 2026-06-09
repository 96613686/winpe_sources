# SHA2::Hash(void const *,ulong)

- ea: `0x1800a1884`
- end: `0x1800a19c5`
- name: `?Hash@SHA2@@QEBA?AUDigest@1@PEBXK@Z`
- size: `321`
- prototype: `struct SHA2::Digest __high(const void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a1c60`

## callees

- `0x18001ad40`
- `0x18001f080`
- `0x18004a8fc`
- `0x1800a1884`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800a193f`
- `bcrypt!BCryptCreateHash` at `0x1800a193f`
- `bcrypt!BCryptDestroyHash` at `0x1800a1998`
- `bcrypt!BCryptDestroyHash` at `0x180104134`
- `bcrypt!BCryptDestroyHash` at `0x1800a1998`
- `bcrypt!BCryptDestroyHash` at `0x180104134`
- `bcrypt!BCryptFinishHash` at `0x1800a1981`
- `bcrypt!BCryptFinishHash` at `0x1800a1981`
- `bcrypt!BCryptGetProperty` at `0x1800a18ed`
- `bcrypt!BCryptGetProperty` at `0x1800a18ed`
- `bcrypt!BCryptHashData` at `0x1800a1960`
- `bcrypt!BCryptHashData` at `0x1800a1960`

## pseudocode

```c
__int64 __fastcall SHA2::Hash(__int64 a1, __int64 a2, UCHAR *a3)
{
  NTSTATUS Property; // eax
  UCHAR *v6; // rbx
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-18h] BYREF
  UCHAR *pcbResult; // [rsp+60h] [rbp+8h] BYREF
  ULONG pbOutput; // [rsp+78h] [rbp+20h] BYREF

  HIDWORD(pcbResult) = HIDWORD(a1);
  phHash = 0;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  LODWORD(pcbResult) = 0;
  pbOutput = 0;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&pcbResult, 0);
  if ( Property < 0 )
    Exception::throwHR(Property);
  v6 = (UCHAR *)_MemAlloc(pbOutput, 4u);
  pcbResult = v6;
  v7 = BCryptCreateHash(hAlgorithm, &phHash, v6, pbOutput, 0, 0, 0);
  if ( v7 < 0 )
    Exception::throwHR(v7);
  v8 = BCryptHashData(phHash, a3, 0x18u, 0);
  if ( v8 < 0 )
    Exception::throwHR(v8);
  v9 = BCryptFinishHash(phHash, (PUCHAR)a2, 0x20u, 0);
  if ( v9 < 0 )
    Exception::throwHR(v9);
  v10 = BCryptDestroyHash(phHash);
  if ( v10 < 0 )
    Exception::throwHR(v10);
  MemFreeObject(v6);
  return a2;
}

```

## disassembly

```asm
0x1800a1884  mov     rax, rsp
0x1800a1887  mov     [rax+10h], rbx
0x1800a188b  mov     [rax+18h], rsi
0x1800a188f  mov     [rax+20h], r9d
0x1800a1893  mov     [rax+8], rcx
0x1800a1897  push    rdi
0x1800a1898  sub     rsp, 50h
0x1800a189c  mov     rsi, r8
0x1800a189f  mov     rdi, rdx
0x1800a18a2  mov     qword ptr [rax-18h], 0
0x1800a18aa  xorps   xmm0, xmm0
0x1800a18ad  movups  xmmword ptr [rdx], xmm0
0x1800a18b0  movups  xmmword ptr [rdx+10h], xmm0
0x1800a18b4  mov     dword ptr [rax+8], 0
0x1800a18bb  mov     dword ptr [rax+20h], 0
0x1800a18c2  mov     dword ptr [rax-30h], 0
0x1800a18c9  lea     rax, [rax+8]
0x1800a18cd  mov     [rsp+58h+pcbResult], rax; pcbResult
0x1800a18d2  mov     ebx, 4
0x1800a18d7  mov     r9d, ebx; cbOutput
0x1800a18da  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x1800a18df  lea     rdx, pszProperty; "ObjectLength"
0x1800a18e6  mov     rcx, cs:hAlgorithm; hObject
0x1800a18ed  call    cs:__imp_BCryptGetProperty
0x1800a18f3  test    eax, eax
0x1800a18f5  jns     short loc_1800A18FF
0x1800a18f7  mov     ecx, eax; int
0x1800a18f9  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800a18ff  mov     ecx, [rsp+58h+pbOutput]; unsigned __int64
0x1800a1903  mov     edx, ebx; unsigned int
0x1800a1905  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1800a190a  mov     rbx, rax
0x1800a190d  mov     [rsp+58h+arg_0], rax
0x1800a1912  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800a191a  mov     [rsp+58h+cbSecret], 0; cbSecret
0x1800a1922  mov     [rsp+58h+pcbResult], 0; pbSecret
0x1800a192b  mov     r9d, [rsp+58h+pbOutput]; cbHashObject
0x1800a1930  mov     r8, rax; pbHashObject
0x1800a1933  lea     rdx, [rsp+58h+phHash]; phHash
0x1800a1938  mov     rcx, cs:hAlgorithm; hAlgorithm
0x1800a193f  call    cs:__imp_BCryptCreateHash
0x1800a1945  test    eax, eax
0x1800a1947  jns     short loc_1800A1951
0x1800a1949  mov     ecx, eax; int
0x1800a194b  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800a1951  xor     r9d, r9d; dwFlags
0x1800a1954  lea     r8d, [r9+18h]; cbInput
0x1800a1958  mov     rdx, rsi; pbInput
0x1800a195b  mov     rcx, [rsp+58h+phHash]; hHash
0x1800a1960  call    cs:__imp_BCryptHashData
0x1800a1966  test    eax, eax
0x1800a1968  jns     short loc_1800A1972
0x1800a196a  mov     ecx, eax; int
0x1800a196c  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800a1972  xor     r9d, r9d; dwFlags
0x1800a1975  lea     r8d, [r9+20h]; cbOutput
0x1800a1979  mov     rdx, rdi; pbOutput
0x1800a197c  mov     rcx, [rsp+58h+phHash]; hHash
0x1800a1981  call    cs:__imp_BCryptFinishHash
0x1800a1987  test    eax, eax
0x1800a1989  jns     short loc_1800A1993
0x1800a198b  mov     ecx, eax; int
0x1800a198d  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800a1993  mov     rcx, [rsp+58h+phHash]; hHash
0x1800a1998  call    cs:__imp_BCryptDestroyHash
0x1800a199e  test    eax, eax
0x1800a19a0  jns     short loc_1800A19AA
0x1800a19a2  mov     ecx, eax; int
0x1800a19a4  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800a19aa  mov     rcx, rbx; void *
0x1800a19ad  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x1800a19b2  mov     rax, rdi
0x1800a19b5  mov     rbx, [rsp+58h+arg_8]
0x1800a19ba  mov     rsi, [rsp+58h+arg_10]
0x1800a19bf  add     rsp, 50h
0x1800a19c3  pop     rdi
0x1800a19c4  retn
0x180104127  push    rbp
0x180104129  sub     rsp, 40h
0x18010412d  mov     rbp, rdx
0x180104130  mov     rcx, [rbp+40h]; hHash
0x180104134  call    cs:__imp_BCryptDestroyHash
0x18010413a  test    eax, eax
0x18010413c  jns     short loc_180104146
0x18010413e  mov     ecx, eax; int
0x180104140  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180104146  mov     rcx, [rbp+60h]; void *
0x18010414a  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x18010414f  nop
0x180104150  add     rsp, 40h
0x180104154  pop     rbp
0x180104155  retn
```
