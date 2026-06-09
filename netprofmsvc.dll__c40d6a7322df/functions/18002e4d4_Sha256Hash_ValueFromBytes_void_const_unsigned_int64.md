# Sha256Hash::ValueFromBytes(void const *,unsigned __int64)

- ea: `0x18002e4d4`
- end: `0x18002e681`
- name: `?ValueFromBytes@Sha256Hash@@CA?AV?$array@E$0CA@@std@@PEBX_K@Z`
- size: `429`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002e46c`
- `0x180067a4c`
- `0x180116330`
- `0x1801167c4`
- `0x1801176a8`
- `0x180117f84`
- `0x180118acc`

## callees

- `0x18002e4d4`
- `0x18002e688`
- `0x1800a88a0`
- `0x1800a8d70`
- `0x1800a959c`
- `0x1800a9738`
- `0x1800baf04`
- `0x1800f2a40`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002e515`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002e515`
- `bcrypt!BCryptDestroyHash` at `0x18002e5fb`
- `bcrypt!BCryptDestroyHash` at `0x18002e5fb`
- `bcrypt!BCryptFinishHash` at `0x18002e5d1`
- `bcrypt!BCryptFinishHash` at `0x18002e5d1`
- `bcrypt!BCryptHashData` at `0x18002e5a5`
- `bcrypt!BCryptHashData` at `0x18002e5a5`
- `bcrypt!BCryptCreateHash` at `0x18002e57e`
- `bcrypt!BCryptCreateHash` at `0x18002e57e`

## string_xrefs

- `0x18002e630`: `onecore\net\netprofiles\service\src\common\sha256hash.cpp`
- `0x18002e645`: `onecore\net\netprofiles\service\src\common\sha256hash.cpp`
- `0x18002e65a`: `onecore\net\netprofiles\service\src\common\sha256hash.cpp`
- `0x18002e66f`: `onecore\net\netprofiles\service\src\common\sha256hash.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_OWORD *__fastcall Sha256Hash::ValueFromBytes(_OWORD *a1, UCHAR *a2, __int64 a3)
{
  const char *v6; // r9
  unsigned int v7; // ebx
  void *v8; // rsi
  NTSTATUS v9; // eax
  ULONG v10; // eax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  int pbSecret; // [rsp+20h] [rbp-60h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-38h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v17; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( !InitOnceExecuteOnce(&InitOnce, Sha256HashInitOnce, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\sha256hash.cpp",
      v6);
  v7 = Size;
  v8 = operator new[]((unsigned int)Size);
  memset_0(v8, 0, v7);
  phHash = 0;
  v9 = BCryptCreateHash(hObject, &phHash, (PUCHAR)v8, Size, 0, 0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\sha256hash.cpp",
      (const char *)(unsigned int)v9,
      pbSecret);
  v10 = wil::safe_cast<unsigned long,unsigned __int64,0>(a3);
  v11 = BCryptHashData(phHash, a2, v10, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\sha256hash.cpp",
      (const char *)(unsigned int)v11,
      pbSecret);
  *(_OWORD *)pbOutput = 0;
  v17 = 0;
  v12 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\sha256hash.cpp",
      (const char *)(unsigned int)v12,
      pbSecret);
  *a1 = *(_OWORD *)pbOutput;
  a1[1] = v17;
  if ( phHash )
    BCryptDestroyHash(phHash);
  operator delete(v8);
  return a1;
}

```

## disassembly

```asm
0x18002e4d4  mov     [rsp-28h+arg_0], rbx
0x18002e4d9  push    rbp
0x18002e4da  push    rsi
0x18002e4db  push    rdi
0x18002e4dc  push    r14
0x18002e4de  push    r15
0x18002e4e0  mov     rbp, rsp
0x18002e4e3  sub     rsp, 80h
0x18002e4ea  mov     rax, cs:__security_cookie
0x18002e4f1  xor     rax, rsp
0x18002e4f4  mov     [rbp+var_10], rax
0x18002e4f8  mov     r15, r8
0x18002e4fb  mov     r14, rdx
0x18002e4fe  mov     rdi, rcx
0x18002e501  xor     r9d, r9d; Context
0x18002e504  xor     r8d, r8d; Parameter
0x18002e507  lea     rdx, Sha256HashInitOnce; InitFn
0x18002e50e  lea     rcx, InitOnce; InitOnce
0x18002e515  call    cs:__imp_InitOnceExecuteOnce
0x18002e51b  mov     rcx, [rbp+28h]; this
0x18002e51f  test    eax, eax
0x18002e521  jz      loc_18002E630
0x18002e527  mov     ebx, cs:Size
0x18002e52d  mov     ecx, ebx; unsigned __int64
0x18002e52f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002e534  mov     rsi, rax
0x18002e537  mov     r8d, ebx; Size
0x18002e53a  xor     edx, edx; Val
0x18002e53c  mov     rcx, rax; void *
0x18002e53f  call    memset_0
0x18002e544  mov     [rbp+var_40], rsi
0x18002e548  mov     [rbp+phHash], 0
0x18002e550  mov     [rsp+80h+dwFlags], 0; dwFlags
0x18002e558  mov     [rsp+80h+cbSecret], 0; cbSecret
0x18002e560  mov     [rsp+80h+pbSecret], 0; int
0x18002e569  mov     r9d, cs:Size; cbHashObject
0x18002e570  mov     r8, rsi; pbHashObject
0x18002e573  lea     rdx, [rbp+phHash]; phHash
0x18002e577  mov     rcx, cs:hObject; hAlgorithm
0x18002e57e  call    cs:__imp_BCryptCreateHash
0x18002e584  mov     rcx, [rbp+28h]; this
0x18002e588  test    eax, eax
0x18002e58a  js      loc_18002E642
0x18002e590  mov     rcx, r15
0x18002e593  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x18002e598  xor     r9d, r9d; dwFlags
0x18002e59b  mov     r8d, eax; cbInput
0x18002e59e  mov     rdx, r14; pbInput
0x18002e5a1  mov     rcx, [rbp+phHash]; hHash
0x18002e5a5  call    cs:__imp_BCryptHashData
0x18002e5ab  mov     rcx, [rbp+28h]; this
0x18002e5af  test    eax, eax
0x18002e5b1  js      loc_18002E657
0x18002e5b7  xorps   xmm0, xmm0
0x18002e5ba  movups  xmmword ptr [rbp+pbOutput], xmm0
0x18002e5be  movups  [rbp+var_20], xmm0
0x18002e5c2  xor     r9d, r9d; dwFlags
0x18002e5c5  lea     r8d, [r9+20h]; cbOutput
0x18002e5c9  lea     rdx, [rbp+pbOutput]; pbOutput
0x18002e5cd  mov     rcx, [rbp+phHash]; hHash
0x18002e5d1  call    cs:__imp_BCryptFinishHash
0x18002e5d7  mov     rcx, [rbp+28h]; this
0x18002e5db  test    eax, eax
0x18002e5dd  js      loc_18002E66C
0x18002e5e3  movups  xmm0, xmmword ptr [rbp+pbOutput]
0x18002e5e7  movups  xmmword ptr [rdi], xmm0
0x18002e5ea  movups  xmm1, [rbp+var_20]
0x18002e5ee  movups  xmmword ptr [rdi+10h], xmm1
0x18002e5f2  mov     rcx, [rbp+phHash]; hHash
0x18002e5f6  test    rcx, rcx
0x18002e5f9  jz      short loc_18002E602
0x18002e5fb  call    cs:__imp_BCryptDestroyHash
0x18002e601  nop
0x18002e602  mov     rcx, rsi; Block
0x18002e605  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e60a  mov     rax, rdi
0x18002e60d  mov     rcx, [rbp+var_10]
0x18002e611  xor     rcx, rsp; StackCookie
0x18002e614  call    __security_check_cookie
0x18002e619  mov     rbx, [rsp+80h+arg_0]
0x18002e621  add     rsp, 80h
0x18002e628  pop     r15
0x18002e62a  pop     r14
0x18002e62c  pop     rdi
0x18002e62d  pop     rsi
0x18002e62e  pop     rbp
0x18002e62f  retn
0x18002e630  lea     r8, aOnecoreNetNetp_37; "onecore\\net\\netprofiles\\service\\src"...
0x18002e637  mov     edx, 3Eh ; '>'; void *
0x18002e63c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002e642  mov     r9d, eax; char *
0x18002e645  lea     r8, aOnecoreNetNetp_37; "onecore\\net\\netprofiles\\service\\src"...
0x18002e64c  mov     edx, 45h ; 'E'; void *
0x18002e651  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002e657  mov     r9d, eax; char *
0x18002e65a  lea     r8, aOnecoreNetNetp_37; "onecore\\net\\netprofiles\\service\\src"...
0x18002e661  mov     edx, 47h ; 'G'; void *
0x18002e666  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002e66c  mov     r9d, eax; char *
0x18002e66f  lea     r8, aOnecoreNetNetp_37; "onecore\\net\\netprofiles\\service\\src"...
0x18002e676  mov     edx, 4Ah ; 'J'; void *
0x18002e67b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
