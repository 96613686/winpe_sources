# HashCNG::Create(ILogContext const *,ushort const *,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14002b5d0`
- end: `0x14002b860`
- name: `?Create@HashCNG@@AEAAXPEBVILogContext@@PEBGAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV34@@Z`
- size: `656`
- prototype: `void __fastcall(BCRYPT_HASH_HANDLE *phHash, __int64, const WCHAR *, __int64, PUCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002b868`

## callees

- `0x14000e6a0`
- `0x1400140c4`
- `0x1400234dc`
- `0x14002b5d0`
- `0x14002c3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b76d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b7ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b7e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b80c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b76d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b7ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b7e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b80c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b835`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14002b630`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14002b630`
- `bcrypt!BCryptGetProperty` at `0x14002b669`
- `bcrypt!BCryptGetProperty` at `0x14002b6ab`
- `bcrypt!BCryptGetProperty` at `0x14002b669`
- `bcrypt!BCryptGetProperty` at `0x14002b6ab`
- `bcrypt!BCryptFinishHash` at `0x14002b732`
- `bcrypt!BCryptFinishHash` at `0x14002b732`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14002b747`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14002b747`
- `bcrypt!BCryptHashData` at `0x14002b716`
- `bcrypt!BCryptHashData` at `0x14002b716`
- `bcrypt!BCryptCreateHash` at `0x14002b6f8`
- `bcrypt!BCryptCreateHash` at `0x14002b6f8`

## pseudocode

```c
void __fastcall HashCNG::Create(BCRYPT_HASH_HANDLE *phHash, __int64 a2, const WCHAR *a3, __int64 a4, PUCHAR *a5)
{
  DWORD LastError; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-98h] BYREF
  UCHAR v14[4]; // [rsp+44h] [rbp-94h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-90h] BYREF
  ULONG pcbResult; // [rsp+50h] [rbp-88h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+58h] [rbp-80h] BYREF
  __int64 v18; // [rsp+68h] [rbp-70h]
  _BYTE pExceptionObject[16]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v20[16]; // [rsp+80h] [rbp-58h] BYREF
  _BYTE v21[16]; // [rsp+90h] [rbp-48h] BYREF
  _BYTE v22[16]; // [rsp+A0h] [rbp-38h] BYREF
  _BYTE v23[16]; // [rsp+B0h] [rbp-28h] BYREF
  _BYTE v24[16]; // [rsp+C0h] [rbp-18h] BYREF

  phAlgorithm = 0;
  *(_OWORD *)pbHashObject = 0;
  v18 = 0;
  *(_DWORD *)v14 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, a3, 0, 0) < 0 )
  {
    LastError = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, LastError);
    throw (Win32Exception *)pExceptionObject;
  }
  if ( BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0) < 0 )
  {
    v8 = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)v20, v8);
    throw (Win32Exception *)v20;
  }
  std::vector<unsigned char>::resize(pbHashObject, *(unsigned int *)pbOutput);
  if ( BCryptGetProperty(phAlgorithm, L"HashDigestLength", v14, 4u, &pcbResult, 0) < 0 )
  {
    v9 = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)v21, v9);
    throw (Win32Exception *)v21;
  }
  std::vector<unsigned char>::resize(a5, *(unsigned int *)v14);
  if ( BCryptCreateHash(phAlgorithm, phHash, pbHashObject[0], *(ULONG *)pbOutput, 0, 0, 0) < 0 )
  {
    v10 = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)v22, v10);
    throw (Win32Exception *)v22;
  }
  if ( BCryptHashData(*phHash, *(PUCHAR *)a4, *(_DWORD *)(a4 + 8) - *(_DWORD *)a4, 0) < 0 )
  {
    v11 = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)v23, v11);
    throw (Win32Exception *)v23;
  }
  if ( BCryptFinishHash(*phHash, *a5, *(ULONG *)v14, 0) < 0 )
  {
    v12 = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)v24, v12);
    throw (Win32Exception *)v24;
  }
  BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  std::vector<unsigned char>::~vector<unsigned char>((char **)pbHashObject);
}

```

## disassembly

```asm
0x14002b5d0  mov     r11, rsp
0x14002b5d3  mov     [r11+8], rbx
0x14002b5d7  mov     [r11+18h], rsi
0x14002b5db  mov     [r11+10h], rdx
0x14002b5df  push    rdi
0x14002b5e0  sub     rsp, 0D0h
0x14002b5e7  mov     rsi, r9
0x14002b5ea  mov     rax, r8
0x14002b5ed  mov     rdi, rcx
0x14002b5f0  mov     [rsp+0D8h+phAlgorithm], 0
0x14002b5f9  xorps   xmm0, xmm0
0x14002b5fc  movdqu  xmmword ptr [rsp+0D8h+pbHashObject], xmm0
0x14002b602  mov     qword ptr [r11-70h], 0
0x14002b60a  mov     dword ptr [rsp+0D8h+var_94], 0
0x14002b612  mov     dword ptr [rsp+0D8h+pbOutput], 0
0x14002b61a  mov     [rsp+0D8h+var_88], 0
0x14002b622  xor     r9d, r9d; dwFlags
0x14002b625  xor     r8d, r8d; pszImplementation
0x14002b628  mov     rdx, rax; pszAlgId
0x14002b62b  lea     rcx, [rsp+0D8h+phAlgorithm]; phAlgorithm
0x14002b630  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002b636  test    eax, eax
0x14002b638  js      loc_14002B76D
0x14002b63e  mov     [rsp+0D8h+dwFlags], 0; dwFlags
0x14002b646  lea     rax, [rsp+0D8h+var_88]
0x14002b64b  mov     [rsp+0D8h+pcbResult], rax; pcbResult
0x14002b650  mov     ebx, 4
0x14002b655  mov     r9d, ebx; cbOutput
0x14002b658  lea     r8, [rsp+0D8h+pbOutput]; pbOutput
0x14002b65d  lea     rdx, pszProperty; "ObjectLength"
0x14002b664  mov     rcx, [rsp+0D8h+phAlgorithm]; hObject
0x14002b669  call    cs:__imp_BCryptGetProperty
0x14002b66f  test    eax, eax
0x14002b671  js      loc_14002B791
0x14002b677  mov     edx, dword ptr [rsp+0D8h+pbOutput]
0x14002b67b  lea     rcx, [rsp+0D8h+pbHashObject]
0x14002b680  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x14002b685  mov     [rsp+0D8h+dwFlags], 0; dwFlags
0x14002b68d  lea     rax, [rsp+0D8h+var_88]
0x14002b692  mov     [rsp+0D8h+pcbResult], rax; pcbResult
0x14002b697  mov     r9d, ebx; cbOutput
0x14002b69a  lea     r8, [rsp+0D8h+var_94]; pbOutput
0x14002b69f  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14002b6a6  mov     rcx, [rsp+0D8h+phAlgorithm]; hObject
0x14002b6ab  call    cs:__imp_BCryptGetProperty
0x14002b6b1  test    eax, eax
0x14002b6b3  js      loc_14002B7BA
0x14002b6b9  mov     edx, dword ptr [rsp+0D8h+var_94]
0x14002b6bd  mov     rbx, [rsp+0D8h+arg_20]
0x14002b6c5  mov     rcx, rbx
0x14002b6c8  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x14002b6cd  mov     [rsp+0D8h+var_A8], 0; dwFlags
0x14002b6d5  mov     [rsp+0D8h+dwFlags], 0; cbSecret
0x14002b6dd  mov     [rsp+0D8h+pcbResult], 0; pbSecret
0x14002b6e6  mov     r9d, dword ptr [rsp+0D8h+pbOutput]; cbHashObject
0x14002b6eb  mov     r8, [rsp+0D8h+pbHashObject]; pbHashObject
0x14002b6f0  mov     rdx, rdi; phHash
0x14002b6f3  mov     rcx, [rsp+0D8h+phAlgorithm]; hAlgorithm
0x14002b6f8  call    cs:__imp_BCryptCreateHash
0x14002b6fe  test    eax, eax
0x14002b700  js      loc_14002B7E3
0x14002b706  mov     r8d, [rsi+8]
0x14002b70a  sub     r8d, [rsi]; cbInput
0x14002b70d  xor     r9d, r9d; dwFlags
0x14002b710  mov     rdx, [rsi]; pbInput
0x14002b713  mov     rcx, [rdi]; hHash
0x14002b716  call    cs:__imp_BCryptHashData
0x14002b71c  test    eax, eax
0x14002b71e  js      loc_14002B80C
0x14002b724  xor     r9d, r9d; dwFlags
0x14002b727  mov     r8d, dword ptr [rsp+0D8h+var_94]; cbOutput
0x14002b72c  mov     rdx, [rbx]; pbOutput
0x14002b72f  mov     rcx, [rdi]; hHash
0x14002b732  call    cs:__imp_BCryptFinishHash
0x14002b738  test    eax, eax
0x14002b73a  js      loc_14002B835
0x14002b740  xor     edx, edx; dwFlags
0x14002b742  mov     rcx, [rsp+0D8h+phAlgorithm]; hAlgorithm
0x14002b747  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14002b74d  nop
0x14002b74e  lea     rcx, [rsp+0D8h+pbHashObject]
0x14002b753  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14002b758  lea     r11, [rsp+0D8h+var_8]
0x14002b760  mov     rbx, [r11+10h]
0x14002b764  mov     rsi, [r11+20h]
0x14002b768  mov     rsp, r11
0x14002b76b  pop     rdi
0x14002b76c  retn
0x14002b76d  call    cs:__imp_GetLastError
0x14002b773  nop
0x14002b774  mov     edx, eax; unsigned int
0x14002b776  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x14002b77b  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002b780  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002b787  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x14002b78c  call    _CxxThrowException_0
0x14002b791  call    cs:__imp_GetLastError
0x14002b797  mov     edx, eax; unsigned int
0x14002b799  lea     rcx, [rsp+0D8h+var_58]; this
0x14002b7a1  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002b7a6  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002b7ad  lea     rcx, [rsp+0D8h+var_58]; pExceptionObject
0x14002b7b5  call    _CxxThrowException_0
0x14002b7ba  call    cs:__imp_GetLastError
0x14002b7c0  mov     edx, eax; unsigned int
0x14002b7c2  lea     rcx, [rsp+0D8h+var_48]; this
0x14002b7ca  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002b7cf  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002b7d6  lea     rcx, [rsp+0D8h+var_48]; pExceptionObject
0x14002b7de  call    _CxxThrowException_0
0x14002b7e3  call    cs:__imp_GetLastError
0x14002b7e9  mov     edx, eax; unsigned int
0x14002b7eb  lea     rcx, [rsp+0D8h+var_38]; this
0x14002b7f3  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002b7f8  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002b7ff  lea     rcx, [rsp+0D8h+var_38]; pExceptionObject
0x14002b807  call    _CxxThrowException_0
0x14002b80c  call    cs:__imp_GetLastError
0x14002b812  mov     edx, eax; unsigned int
0x14002b814  lea     rcx, [rsp+0D8h+var_28]; this
0x14002b81c  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002b821  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002b828  lea     rcx, [rsp+0D8h+var_28]; pExceptionObject
0x14002b830  call    _CxxThrowException_0
0x14002b835  call    cs:__imp_GetLastError
0x14002b83b  mov     edx, eax; unsigned int
0x14002b83d  lea     rcx, [rsp+0D8h+var_18]; this
0x14002b845  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002b84a  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002b851  lea     rcx, [rsp+0D8h+var_18]; pExceptionObject
0x14002b859  call    _CxxThrowException_0
```
