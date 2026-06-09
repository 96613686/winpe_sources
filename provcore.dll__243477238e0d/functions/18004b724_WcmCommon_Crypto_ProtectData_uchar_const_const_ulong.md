# WcmCommon::Crypto::ProtectData(uchar const * const,ulong)

- ea: `0x18004b724`
- end: `0x18004b828`
- name: `?ProtectData@Crypto@WcmCommon@@YA?AV?$vector@EV?$allocator@E@std@@@std@@QEBEK@Z`
- size: `260`
- prototype: `std::vector<unsigned char> *__fastcall(std::vector<unsigned char> *result, const unsigned __int8 *const Buffer, unsigned int Length)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b830`

## callees

- `0x180002790`
- `0x18000b178`
- `0x180024c48`
- `0x18004acb0`
- `0x18004b654`
- `0x18004b724`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b802`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b802`
- `CRYPT32!CryptProtectData` at `0x18004b7b5`
- `CRYPT32!CryptProtectData` at `0x18004b7b5`

## string_xrefs

- `0x18004b767`: `onecoreuap\net\wcm\common\lib\wcm_crypto.cpp`
- `0x18004b7cc`: `onecoreuap\net\wcm\common\lib\wcm_crypto.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::vector<unsigned char> *__fastcall WcmCommon::Crypto::ProtectData(
        std::vector<unsigned char> *result,
        unsigned __int8 *Buffer,
        unsigned int Length)
{
  const std::allocator<unsigned char> *v4; // r9
  DWORD LastError; // eax
  _CRYPTOAPI_BLOB dataOut; // [rsp+58h] [rbp-28h] BYREF
  _CRYPTOAPI_BLOB dataIn; // [rsp+68h] [rbp-18h] BYREF
  void *retaddr; // [rsp+88h] [rbp+8h]

  *(_QWORD *)&dataOut.cbData = result;
  if ( Length )
  {
    if ( !Buffer )
      wil::details::in1diag3::Throw_Hr(retaddr, 0x22u, "onecoreuap\\net\\wcm\\common\\lib\\wcm_crypto.cpp", -2147024809);
    *(&dataIn.cbData + 1) = 0;
    dataIn.cbData = Length;
    dataIn.pbData = Buffer;
    dataOut = 0;
    if ( !CryptProtectData(&dataIn, 0, 0, 0, 0, 1u, &dataOut) )
    {
      LastError = GetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        0x2Eu,
        "onecoreuap\\net\\wcm\\common\\lib\\wcm_crypto.cpp",
        LastError);
    }
    std::vector<unsigned char>::vector<unsigned char>(result, dataOut.pbData, &dataOut.pbData[dataOut.cbData], v4);
    LocalFree(dataOut.pbData);
  }
  else
  {
    std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)result);
  }
  return result;
}

```

## disassembly

```asm
0x18004b724  mov     [rsp-8+arg_18], rbx
0x18004b729  push    rbp
0x18004b72a  mov     rbp, rsp
0x18004b72d  sub     rsp, 80h
0x18004b734  mov     rax, cs:__security_cookie
0x18004b73b  xor     rax, rsp
0x18004b73e  mov     [rbp+var_8], rax
0x18004b742  mov     rbx, rcx
0x18004b745  mov     qword ptr [rbp+dataOut.cbData], rcx
0x18004b749  test    Length, Length
0x18004b74c  jnz     short loc_18004B758
0x18004b74e  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18004b753  jmp     loc_18004B808
0x18004b758  test    Buffer, Buffer
0x18004b75b  jnz     short loc_18004B779
0x18004b75d  mov     rcx, [rbp+8]; callerReturnAddress
0x18004b761  mov     r9d, 80070057h; hr
0x18004b767  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004b76e  mov     edx, 22h ; '"'; lineNumber
0x18004b773  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b779  mov     dword ptr [rbp+dataIn+4], 0
0x18004b780  mov     [rbp+dataIn.cbData], Length
0x18004b784  mov     [rbp+dataIn.pbData], Buffer
0x18004b788  xorps   xmm0, xmm0
0x18004b78b  movups  xmmword ptr [rbp+dataOut.cbData], xmm0
0x18004b78f  lea     rax, [rbp+dataOut]
0x18004b793  mov     [rsp+80h+pDataOut], rax; pDataOut
0x18004b798  mov     [rsp+80h+dwFlags], 1; dwFlags
0x18004b7a0  mov     [rsp+80h+pPromptStruct], 0; pPromptStruct
0x18004b7a9  xor     r9d, r9d; pvReserved
0x18004b7ac  xor     Length, Length; pOptionalEntropy
0x18004b7af  xor     edx, edx; szDataDescr
0x18004b7b1  lea     rcx, [rbp+dataIn]; pDataIn
0x18004b7b5  call    cs:__imp_CryptProtectData
0x18004b7bb  test    eax, eax
0x18004b7bd  jnz     short loc_18004B7DE
0x18004b7bf  call    cs:__imp_GetLastError
0x18004b7c5  mov     rcx, [rbp+8]; callerReturnAddress
0x18004b7c9  mov     r9d, eax; err
0x18004b7cc  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004b7d3  mov     edx, 2Eh ; '.'; lineNumber
0x18004b7d8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004b7de  lea     rax, [rbp+dataOut]
0x18004b7e2  mov     [rbp+freeData.m_lambda.dataOut], rax
0x18004b7e6  mov     [rbp+freeData.m_call], 1
0x18004b7ea  mov     Length, [rbp+dataOut.cbData]
0x18004b7ee  mov     Buffer, [rbp+dataOut.pbData]; _First
0x18004b7f2  add     r8, Buffer; _Last
0x18004b7f5  mov     rcx, rbx; this
0x18004b7f8  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18004b7fd  nop
0x18004b7fe  mov     rcx, [rbp+dataOut.pbData]; hMem
0x18004b802  call    cs:__imp_LocalFree
0x18004b808  mov     rax, rbx
0x18004b80b  mov     rcx, [rbp+var_8]
0x18004b80f  xor     rcx, rsp; StackCookie
0x18004b812  call    __security_check_cookie
0x18004b817  mov     rbx, [rsp+80h+arg_18]
0x18004b81f  add     rsp, 80h
0x18004b826  pop     rbp
0x18004b827  retn
```
