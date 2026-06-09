# WcmCommon::Crypto::UnprotectString(uchar const * const,ulong)

- ea: `0x18004b8fc`
- end: `0x18004ba25`
- name: `?UnprotectString@Crypto@WcmCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBEK@Z`
- size: `297`
- prototype: `std::wstring *__fastcall(std::wstring *result, const unsigned __int8 *const Buffer, unsigned int Length)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004b898`

## callees

- `0x180002790`
- `0x1800081b8`
- `0x18000b0a0`
- `0x180024c48`
- `0x18004acb0`
- `0x18004b8fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b997`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9ff`
- `CRYPT32!CryptUnprotectData` at `0x18004b98d`
- `CRYPT32!CryptUnprotectData` at `0x18004b98d`

## string_xrefs

- `0x18004b93f`: `onecoreuap\net\wcm\common\lib\wcm_crypto.cpp`
- `0x18004b9a4`: `onecoreuap\net\wcm\common\lib\wcm_crypto.cpp`
- `0x18004b9d2`: `onecoreuap\net\wcm\common\lib\wcm_crypto.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::wstring *__fastcall WcmCommon::Crypto::UnprotectString(
        std::wstring *result,
        unsigned __int8 *Buffer,
        unsigned int Length)
{
  const std::allocator<unsigned short> *v4; // r9
  DWORD LastError; // eax
  _CRYPTOAPI_BLOB dataOut; // [rsp+58h] [rbp-28h] BYREF
  _CRYPTOAPI_BLOB dataIn; // [rsp+68h] [rbp-18h] BYREF
  void *retaddr; // [rsp+88h] [rbp+8h]

  *(_QWORD *)&dataOut.cbData = result;
  if ( Length )
  {
    if ( !Buffer )
      wil::details::in1diag3::Throw_Hr(retaddr, 0x8Eu, "onecoreuap\\net\\wcm\\common\\lib\\wcm_crypto.cpp", -2147024809);
    *(&dataIn.cbData + 1) = 0;
    dataIn.cbData = Length;
    dataIn.pbData = Buffer;
    dataOut = 0;
    if ( !CryptUnprotectData(&dataIn, 0, 0, 0, 0, 1u, &dataOut) )
    {
      LastError = GetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        0x9Au,
        "onecoreuap\\net\\wcm\\common\\lib\\wcm_crypto.cpp",
        LastError);
    }
    if ( (dataOut.cbData & 1) != 0 )
      wil::details::in1diag3::Throw_Win32(retaddr, 0xA2u, "onecoreuap\\net\\wcm\\common\\lib\\wcm_crypto.cpp", 0x18u);
    std::wstring::wstring(
      result,
      (std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short> > >)dataOut.pbData,
      (std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short> > >)&dataOut.pbData[2 * ((unsigned __int64)dataOut.cbData >> 1)],
      v4);
    LocalFree(dataOut.pbData);
  }
  else
  {
    std::wstring::wstring(result);
  }
  return result;
}

```

## disassembly

```asm
0x18004b8fc  mov     [rsp-8+arg_18], rbx
0x18004b901  push    rbp
0x18004b902  mov     rbp, rsp
0x18004b905  sub     rsp, 80h
0x18004b90c  mov     rax, cs:__security_cookie
0x18004b913  xor     rax, rsp
0x18004b916  mov     [rbp+var_8], rax
0x18004b91a  mov     rbx, rcx
0x18004b91d  mov     qword ptr [rbp+dataOut.cbData], rcx
0x18004b921  test    Length, Length
0x18004b924  jnz     short loc_18004B930
0x18004b926  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004b92b  jmp     loc_18004BA05
0x18004b930  test    Buffer, Buffer
0x18004b933  jnz     short loc_18004B951
0x18004b935  mov     rcx, [rbp+8]; callerReturnAddress
0x18004b939  mov     r9d, 80070057h; hr
0x18004b93f  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004b946  mov     edx, 8Eh; lineNumber
0x18004b94b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b951  mov     dword ptr [rbp+dataIn+4], 0
0x18004b958  mov     [rbp+dataIn.cbData], Length
0x18004b95c  mov     [rbp+dataIn.pbData], Buffer
0x18004b960  xorps   xmm0, xmm0
0x18004b963  movups  xmmword ptr [rbp+dataOut.cbData], xmm0
0x18004b967  lea     rax, [rbp+dataOut]
0x18004b96b  mov     [rsp+80h+pDataOut], rax; pDataOut
0x18004b970  mov     [rsp+80h+dwFlags], 1; dwFlags
0x18004b978  mov     [rsp+80h+pPromptStruct], 0; pPromptStruct
0x18004b981  xor     r9d, r9d; pvReserved
0x18004b984  xor     Length, Length; pOptionalEntropy
0x18004b987  xor     edx, edx; ppszDataDescr
0x18004b989  lea     rcx, [rbp+dataIn]; pDataIn
0x18004b98d  call    cs:__imp_CryptUnprotectData
0x18004b993  test    eax, eax
0x18004b995  jnz     short loc_18004B9B6
0x18004b997  call    cs:__imp_GetLastError
0x18004b99d  mov     rcx, [rbp+8]; callerReturnAddress
0x18004b9a1  mov     r9d, eax; err
0x18004b9a4  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004b9ab  mov     edx, 9Ah; lineNumber
0x18004b9b0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004b9b6  lea     rax, [rbp+dataOut]
0x18004b9ba  mov     [rbp+freeData.m_lambda.dataOut], rax
0x18004b9be  mov     [rbp+freeData.m_call], 1
0x18004b9c2  test    byte ptr [rbp+dataOut.cbData], 1
0x18004b9c6  jz      short loc_18004B9E4
0x18004b9c8  mov     rcx, [rbp+8]; callerReturnAddress
0x18004b9cc  mov     r9d, 18h; err
0x18004b9d2  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004b9d9  mov     edx, 0A2h; lineNumber
0x18004b9de  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004b9e4  mov     Buffer, [rbp+dataOut.pbData]; _First
0x18004b9e8  mov     eax, [rbp+dataOut.cbData]
0x18004b9eb  shr     rax, 1
0x18004b9ee  lea     r8, [Buffer+rax*2]; _Last
0x18004b9f2  mov     rcx, rbx; this
0x18004b9f5  call    ??$?0V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@1@0AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,std::allocator<ushort> const &)
0x18004b9fa  nop
0x18004b9fb  mov     rcx, [rbp+dataOut.pbData]; hMem
0x18004b9ff  call    cs:__imp_LocalFree
0x18004ba05  mov     rax, rbx
0x18004ba08  mov     rcx, [rbp+var_8]
0x18004ba0c  xor     rcx, rsp; StackCookie
0x18004ba0f  call    __security_check_cookie
0x18004ba14  mov     rbx, [rsp+80h+arg_18]
0x18004ba1c  add     rsp, 80h
0x18004ba23  pop     rbp
0x18004ba24  retn
```
