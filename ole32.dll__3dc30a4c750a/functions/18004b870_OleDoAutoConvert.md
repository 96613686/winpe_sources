# OleDoAutoConvert

- ea: `0x18004b870`
- end: `0x18004b9aa`
- name: `OleDoAutoConvert`
- size: `314`
- prototype: `HRESULT __stdcall(LPSTORAGE pStg, LPCLSID pClsidNew)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004b784`

## callees

- `0x18001a640`
- `0x18002cbb0`
- `0x18004b870`
- `0x180052390`
- `0x180084ba0`
- `0x1800860a0`
- `0x180098c00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b981`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b981`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18004b8b4`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18004b8b4`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18004b918`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18004b955`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18004b918`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18004b955`

## pseudocode

```c
HRESULT __stdcall OleDoAutoConvert(LPSTORAGE pStg, LPCLSID pClsidNew)
{
  OLECHAR *v3; // rsi
  HRESULT AutoConvertInternal; // ebx
  bool v6; // r8
  HRESULT UserType; // eax
  unsigned __int16 cfOld; // [rsp+20h] [rbp-30h] BYREF
  wchar_t *lpszOld; // [rsp+28h] [rbp-28h] BYREF
  wchar_t *lpszNew; // [rsp+30h] [rbp-20h] BYREF
  _GUID clsidOld; // [rsp+38h] [rbp-18h] BYREF

  cfOld = 0;
  v3 = 0;
  lpszOld = 0;
  lpszNew = 0;
  clsidOld = 0;
  AutoConvertInternal = ReadClassStg(pStg, &clsidOld);
  if ( AutoConvertInternal )
  {
    clsidOld = GUID_NULL;
$errRtn_66:
    *pClsidNew = clsidOld;
    goto $okRtn;
  }
  AutoConvertInternal = OleGetAutoConvertInternal(&clsidOld, pClsidNew, v6);
  if ( AutoConvertInternal )
    goto $errRtn_66;
  ReadFmtUserTypeStg(pStg, &cfOld, &lpszOld);
  UserType = OleRegGetUserType(pClsidNew, 1u, &lpszNew);
  v3 = lpszNew;
  if ( UserType )
    v3 = 0;
  AutoConvertInternal = WriteClassStg(pStg, pClsidNew);
  if ( AutoConvertInternal )
    goto $errRtn_66;
  AutoConvertInternal = WriteFmtUserTypeStg(pStg, cfOld, v3);
  if ( AutoConvertInternal || (AutoConvertInternal = SetBitOleStg(pStg, 0xFFFFFFFF, 4u)) != 0 )
  {
    WriteClassStg(pStg, &clsidOld);
    WriteFmtUserTypeStg(pStg, cfOld, lpszOld);
    goto $errRtn_66;
  }
$okRtn:
  CoTaskMemFree(lpszOld);
  CoTaskMemFree(v3);
  return AutoConvertInternal;
}

```

## disassembly

```asm
0x18004b870  mov     [rsp-18h+arg_10], rbx
0x18004b875  mov     [rsp-18h+arg_18], rsi
0x18004b87a  push    rbp
0x18004b87b  push    rdi
0x18004b87c  push    r14
0x18004b87e  mov     rbp, rsp
0x18004b881  sub     rsp, 50h
0x18004b885  mov     rax, cs:__security_cookie
0x18004b88c  xor     rax, rsp
0x18004b88f  mov     [rbp+var_8], rax
0x18004b893  xor     eax, eax
0x18004b895  mov     r14, pClsidNew
0x18004b898  xorps   xmm0, xmm0
0x18004b89b  mov     [rbp+cfOld], ax
0x18004b89f  xor     esi, esi
0x18004b8a1  mov     [rbp+lpszOld], rax
0x18004b8a5  lea     pClsidNew, [rbp+clsidOld]; pclsid
0x18004b8a9  mov     [rbp+lpszNew], rsi
0x18004b8ad  movups  xmmword ptr [rbp+clsidOld.Data1], xmm0
0x18004b8b1  mov     rdi, pStg
0x18004b8b4  call    cs:__imp_ReadClassStg
0x18004b8ba  mov     ebx, eax
0x18004b8bc  test    eax, eax
0x18004b8be  jz      short loc_18004B8D1
0x18004b8c0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004b8c7  movdqu  xmmword ptr [rbp+clsidOld.Data1], xmm0
0x18004b8cc  jmp     $errRtn_66
0x18004b8d1  mov     pClsidNew, r14; pClsidNew
0x18004b8d4  lea     pStg, [rbp+clsidOld]; clsidOld
0x18004b8d8  call    ?OleGetAutoConvertInternal@@YAJAEBU_GUID@@PEAU1@_N@Z; OleGetAutoConvertInternal(_GUID const &,_GUID *,bool)
0x18004b8dd  mov     ebx, eax
0x18004b8df  test    eax, eax
0x18004b8e1  jnz     $errRtn_66
0x18004b8e7  lea     r8, [rbp+lpszOld]; lplpszUserType
0x18004b8eb  mov     pStg, rdi; pstg
0x18004b8ee  lea     pClsidNew, [rbp+cfOld]; pcf
0x18004b8f2  call    ReadFmtUserTypeStg
0x18004b8f7  lea     r8, [rbp+lpszNew]; pszUserType
0x18004b8fb  mov     pStg, r14; clsid
0x18004b8fe  lea     edx, [rbx+1]; dwFormOfType
0x18004b901  call    OleRegGetUserType
0x18004b906  mov     rsi, [rbp+lpszNew]
0x18004b90a  xor     ecx, ecx
0x18004b90c  test    eax, eax
0x18004b90e  mov     pClsidNew, r14; rclsid
0x18004b911  cmovnz  rsi, pStg
0x18004b915  mov     pStg, rdi; pStg
0x18004b918  call    cs:__imp_WriteClassStg
0x18004b91e  mov     ebx, eax
0x18004b920  test    eax, eax
0x18004b922  jnz     short $errRtn_66
0x18004b924  movzx   edx, [rbp+cfOld]; cf
0x18004b928  mov     r8, rsi; lpszUserType
0x18004b92b  mov     pStg, rdi; pstg
0x18004b92e  call    WriteFmtUserTypeStg
0x18004b933  mov     ebx, eax
0x18004b935  test    eax, eax
0x18004b937  jnz     short $errRewriteInfo
0x18004b939  lea     r8d, [rax+4]; value
0x18004b93d  or      edx, 0FFFFFFFFh; mask
0x18004b940  mov     pStg, rdi; pstg
0x18004b943  call    SetBitOleStg
0x18004b948  mov     ebx, eax
0x18004b94a  test    eax, eax
0x18004b94c  jz      short $okRtn
0x18004b94e  lea     pClsidNew, [rbp+clsidOld]; rclsid
0x18004b952  mov     pStg, rdi; pStg
0x18004b955  call    cs:__imp_WriteClassStg
0x18004b95b  mov     r8, [rbp+lpszOld]; lpszUserType
0x18004b95f  mov     pStg, rdi; pstg
0x18004b962  movzx   edx, [rbp+cfOld]; cf
0x18004b966  call    WriteFmtUserTypeStg
0x18004b96b  movups  xmm0, xmmword ptr [rbp+clsidOld.Data1]
0x18004b96f  movdqu  xmmword ptr [r14], xmm0
0x18004b974  mov     pStg, [rbp+lpszOld]; pv
0x18004b978  call    cs:__imp_CoTaskMemFree
0x18004b97e  mov     pStg, rsi; pv
0x18004b981  call    cs:__imp_CoTaskMemFree
0x18004b987  mov     eax, ebx
0x18004b989  mov     pStg, [rbp+var_8]
0x18004b98d  xor     pStg, rsp; StackCookie
0x18004b990  call    __security_check_cookie
0x18004b995  lea     r11, [rsp+50h+var_s0]
0x18004b99a  mov     rbx, [r11+30h]
0x18004b99e  mov     rsi, [r11+38h]
0x18004b9a2  mov     rsp, r11
0x18004b9a5  pop     r14
0x18004b9a7  pop     rdi
0x18004b9a8  pop     rbp
0x18004b9a9  retn
```
