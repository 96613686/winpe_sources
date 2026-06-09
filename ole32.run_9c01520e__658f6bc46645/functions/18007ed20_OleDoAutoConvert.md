# OleDoAutoConvert

- ea: `0x18007ed20`
- end: `0x18007ee77`
- name: `OleDoAutoConvert`
- size: `343`
- prototype: `HRESULT __stdcall(LPSTORAGE pStg, LPCLSID pClsidNew)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007b7c0`

## callees

- `0x18000ea30`
- `0x1800304d0`
- `0x180046460`
- `0x18007ed20`
- `0x18007f2a4`
- `0x1800807a0`
- `0x18009a3a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ee39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ee48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ee39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ee48`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18007ed65`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18007ed65`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18007edcd`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18007ee10`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18007edcd`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18007ee10`

## pseudocode

```c
HRESULT __stdcall OleDoAutoConvert(LPSTORAGE pStg, LPCLSID pClsidNew)
{
  wchar_t *v3; // rsi
  HRESULT AutoConvertInternal; // ebx
  bool v6; // r8
  HRESULT UserType; // eax
  unsigned __int16 cfOld; // [rsp+20h] [rbp-30h] BYREF
  wchar_t *lpszOld; // [rsp+28h] [rbp-28h] BYREF
  wchar_t *lpszNew; // [rsp+30h] [rbp-20h] BYREF
  _GUID clsidOld; // [rsp+38h] [rbp-18h] BYREF

  cfOld = 0;
  lpszOld = 0;
  clsidOld = 0;
  v3 = 0;
  lpszNew = 0;
  AutoConvertInternal = ReadClassStg(pStg, &clsidOld);
  if ( AutoConvertInternal )
  {
    clsidOld = GUID_NULL;
$errRtn_87:
    *pClsidNew = clsidOld;
    goto $okRtn;
  }
  AutoConvertInternal = OleGetAutoConvertInternal(&clsidOld, pClsidNew, v6);
  if ( AutoConvertInternal )
    goto $errRtn_87;
  ReadFmtUserTypeStg(pStg, &cfOld, &lpszOld);
  UserType = OleRegGetUserType(pClsidNew, 1u, &lpszNew);
  v3 = lpszNew;
  if ( UserType )
    v3 = 0;
  AutoConvertInternal = WriteClassStg(pStg, pClsidNew);
  if ( AutoConvertInternal )
    goto $errRtn_87;
  AutoConvertInternal = WriteFmtUserTypeStg(pStg, cfOld, v3);
  if ( AutoConvertInternal || (AutoConvertInternal = SetBitOleStg(pStg, 0xFFFFFFFF, 4u)) != 0 )
  {
    WriteClassStg(pStg, &clsidOld);
    WriteFmtUserTypeStg(pStg, cfOld, lpszOld);
    goto $errRtn_87;
  }
$okRtn:
  CoTaskMemFree(lpszOld);
  CoTaskMemFree(v3);
  return AutoConvertInternal;
}

```

## disassembly

```asm
0x18007ed20  mov     [rsp-28h+arg_10], rbx
0x18007ed25  push    rbp
0x18007ed26  push    rsi
0x18007ed27  push    rdi
0x18007ed28  push    r14
0x18007ed2a  push    r15
0x18007ed2c  mov     rbp, rsp
0x18007ed2f  sub     rsp, 50h
0x18007ed33  mov     rax, cs:__security_cookie
0x18007ed3a  xor     rax, rsp
0x18007ed3d  mov     [rbp+var_8], rax
0x18007ed41  xor     r15d, r15d
0x18007ed44  mov     r14, pClsidNew
0x18007ed47  xorps   xmm0, xmm0
0x18007ed4a  mov     [rbp+cfOld], r15w
0x18007ed4f  lea     pClsidNew, [rbp+clsidOld]; pclsid
0x18007ed53  mov     [rbp+lpszOld], r15
0x18007ed57  movups  xmmword ptr [rbp+clsidOld.Data1], xmm0
0x18007ed5b  mov     esi, r15d
0x18007ed5e  mov     [rbp+lpszNew], r15
0x18007ed62  mov     rdi, pStg
0x18007ed65  call    cs:__imp_ReadClassStg
0x18007ed6c  nop     dword ptr [rax+rax+00h]
0x18007ed71  mov     ebx, eax
0x18007ed73  test    eax, eax
0x18007ed75  jz      short loc_18007ED88
0x18007ed77  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007ed7e  movdqu  xmmword ptr [rbp+clsidOld.Data1], xmm0
0x18007ed83  jmp     $errRtn_87
0x18007ed88  mov     pClsidNew, r14; pClsidNew
0x18007ed8b  lea     pStg, [rbp+clsidOld]; clsidOld
0x18007ed8f  call    ?OleGetAutoConvertInternal@@YAJAEBU_GUID@@PEAU1@_N@Z; OleGetAutoConvertInternal(_GUID const &,_GUID *,bool)
0x18007ed94  mov     ebx, eax
0x18007ed96  test    eax, eax
0x18007ed98  jnz     $errRtn_87
0x18007ed9e  lea     r8, [rbp+lpszOld]; lplpszUserType
0x18007eda2  mov     pStg, rdi; pstg
0x18007eda5  lea     pClsidNew, [rbp+cfOld]; pcf
0x18007eda9  call    ReadFmtUserTypeStg
0x18007edae  lea     r8, [rbp+lpszNew]; pszUserType
0x18007edb2  mov     pStg, r14; clsid
0x18007edb5  lea     edx, [rbx+1]; dwFormOfType
0x18007edb8  call    OleRegGetUserType
0x18007edbd  mov     rsi, [rbp+lpszNew]
0x18007edc1  test    eax, eax
0x18007edc3  mov     pClsidNew, r14; rclsid
0x18007edc6  mov     pStg, rdi; pStg
0x18007edc9  cmovnz  rsi, r15
0x18007edcd  call    cs:__imp_WriteClassStg
0x18007edd4  nop     dword ptr [rax+rax+00h]
0x18007edd9  mov     ebx, eax
0x18007eddb  test    eax, eax
0x18007eddd  jnz     short $errRtn_87
0x18007eddf  movzx   edx, [rbp+cfOld]; cf
0x18007ede3  mov     r8, rsi; lpszUserType
0x18007ede6  mov     pStg, rdi; pstg
0x18007ede9  call    WriteFmtUserTypeStg
0x18007edee  mov     ebx, eax
0x18007edf0  test    eax, eax
0x18007edf2  jnz     short $errRewriteInfo
0x18007edf4  lea     r8d, [rax+4]; value
0x18007edf8  or      edx, 0FFFFFFFFh; mask
0x18007edfb  mov     pStg, rdi; pstg
0x18007edfe  call    SetBitOleStg
0x18007ee03  mov     ebx, eax
0x18007ee05  test    eax, eax
0x18007ee07  jz      short $okRtn
0x18007ee09  lea     pClsidNew, [rbp+clsidOld]; rclsid
0x18007ee0d  mov     pStg, rdi; pStg
0x18007ee10  call    cs:__imp_WriteClassStg
0x18007ee17  nop     dword ptr [rax+rax+00h]
0x18007ee1c  mov     r8, [rbp+lpszOld]; lpszUserType
0x18007ee20  mov     pStg, rdi; pstg
0x18007ee23  movzx   edx, [rbp+cfOld]; cf
0x18007ee27  call    WriteFmtUserTypeStg
0x18007ee2c  movups  xmm0, xmmword ptr [rbp+clsidOld.Data1]
0x18007ee30  movdqu  xmmword ptr [r14], xmm0
0x18007ee35  mov     pStg, [rbp+lpszOld]; pv
0x18007ee39  call    cs:__imp_CoTaskMemFree
0x18007ee40  nop     dword ptr [rax+rax+00h]
0x18007ee45  mov     pStg, rsi; pv
0x18007ee48  call    cs:__imp_CoTaskMemFree
0x18007ee4f  nop     dword ptr [rax+rax+00h]
0x18007ee54  mov     eax, ebx
0x18007ee56  mov     pStg, [rbp+var_8]
0x18007ee5a  xor     pStg, rsp; StackCookie
0x18007ee5d  call    __security_check_cookie
0x18007ee62  mov     rbx, [rsp+50h+arg_10]
0x18007ee6a  add     rsp, 50h
0x18007ee6e  pop     r15
0x18007ee70  pop     r14
0x18007ee72  pop     rdi
0x18007ee73  pop     rsi
0x18007ee74  pop     rbp
0x18007ee75  retn
```
