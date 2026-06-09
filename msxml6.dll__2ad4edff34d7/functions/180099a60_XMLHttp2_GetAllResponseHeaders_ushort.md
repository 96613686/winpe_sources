# XMLHttp2::_GetAllResponseHeaders(ushort * *)

- ea: `0x180099a60`
- end: `0x180099bb9`
- name: `?_GetAllResponseHeaders@XMLHttp2@@AEAAJPEAPEAG@Z`
- size: `345`
- prototype: `__int64 __fastcall(XMLHttp2 *this, wchar_t **ppwszHeaders)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800999b0`

## callees

- `0x180099a60`
- `0x1800bfc70`
- `0x180185008`
- `0x180185d8c`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099ac4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099ac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099b4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099b4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099b10`
- `OLEAUT32!__imp_SysFreeString` at `0x180099b56`
- `OLEAUT32!__imp_SysFreeString` at `0x180099b56`
- `OLEAUT32!__imp_SysStringLen` at `0x180099b00`
- `OLEAUT32!__imp_SysStringLen` at `0x180099b00`

## pseudocode

```c
__int64 __fastcall XMLHttp2::_GetAllResponseHeaders(XMLHttp2 *this, wchar_t **ppwszHeaders)
{
  wchar_t *v3; // rdi
  int v5; // ebx
  unsigned int m_dwStaThreadId; // ebx
  UINT v7; // ebx
  wchar_t *v8; // rax
  wchar_t *bstrHeaders; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  bstrHeaders = 0;
  if ( (xmmword_1801F6C20 & 2) != 0 )
    WPP_SF_qq(0x401u, 0x97u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, this, ppwszHeaders);
  if ( ppwszHeaders )
  {
    *ppwszHeaders = 0;
    if ( !this->m_dwStaThreadId || (m_dwStaThreadId = this->m_dwStaThreadId, m_dwStaThreadId == GetCurrentThreadId()) )
    {
      v5 = this->m_pXMLHttp->getAllResponseHeaders(this->m_pXMLHttp, &bstrHeaders);
      if ( v5 >= 0 )
      {
        if ( bstrHeaders && *bstrHeaders )
        {
          v7 = SysStringLen(bstrHeaders);
          v8 = (wchar_t *)CoTaskMemAlloc(2LL * v7 + 2);
          v3 = v8;
          if ( v8 )
          {
            v5 = StringCchCopyW(v8, v7 + 1, bstrHeaders);
            if ( v5 >= 0 )
            {
              *ppwszHeaders = v3;
              v3 = 0;
            }
          }
          else
          {
            v5 = -2147024882;
          }
        }
        else
        {
          v5 = -2147024894;
        }
      }
    }
    else
    {
      v5 = -2147417842;
    }
  }
  else
  {
    v5 = -2147467261;
  }
  CoTaskMemFree(v3);
  SysFreeString(bstrHeaders);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v5 >> 31) + 4].rgbFlags[0] & 2) != 0 )
    WPP_SF_d((((unsigned __int16)(v5 >> 31) + 2) << 9) | 1, 0x98u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180099a60  mov     rax, rsp
0x180099a63  mov     [rax+8], rbx
0x180099a67  mov     [rax+18h], rbp
0x180099a6b  push    rsi
0x180099a6c  push    rdi
0x180099a6d  push    r14
0x180099a6f  sub     rsp, 30h
0x180099a73  xor     r14d, r14d
0x180099a76  mov     rsi, ppwszHeaders
0x180099a79  mov     edi, r14d
0x180099a7c  mov     [rax+10h], r14
0x180099a80  mov     rbp, this
0x180099a83  test    byte ptr cs:xmmword_1801F6C20, 2; __annotation("TMF:",
0x180099a8a  jz      short loc_180099AA9
0x180099a8c  mov     edx, 97h; id
0x180099a91  mov     [rax-28h], rsi
0x180099a95  mov     ecx, 401h; LevelKeyword
0x180099a9a  lea     r8, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x180099aa1  mov     r9, rbp; _a1
0x180099aa4  call    WPP_SF_qq
0x180099aa9  test    rsi, rsi
0x180099aac  jnz     short loc_180099AB8
0x180099aae  mov     ebx, 80004003h
0x180099ab3  jmp     $CleanUp_124
0x180099ab8  mov     [rsi], r14
0x180099abb  cmp     [rbp+30h], r14d
0x180099abf  jz      short loc_180099AD5
0x180099ac1  mov     ebx, [rbp+30h]
0x180099ac4  call    cs:__imp_GetCurrentThreadId
0x180099aca  cmp     ebx, eax
0x180099acc  jz      short loc_180099AD5
0x180099ace  mov     ebx, 8001010Eh
0x180099ad3  jmp     short $CleanUp_124
0x180099ad5  mov     this, [rbp+28h]
0x180099ad9  lea     ppwszHeaders, [rsp+48h+bstrHeaders]
0x180099ade  mov     rax, [this]
0x180099ae1  mov     rax, [rax+50h]
0x180099ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099aea  mov     ebx, eax
0x180099aec  test    eax, eax
0x180099aee  js      short $CleanUp_124
0x180099af0  mov     this, [rsp+48h+bstrHeaders]; pbstr
0x180099af5  test    this, this
0x180099af8  jz      short loc_180099B43
0x180099afa  cmp     [this], r14w
0x180099afe  jz      short loc_180099B43
0x180099b00  call    cs:__imp_SysStringLen
0x180099b06  mov     ebx, eax
0x180099b08  lea     this, ds:2[rbx*2]; cb
0x180099b10  call    cs:__imp_CoTaskMemAlloc
0x180099b16  mov     rdi, rax
0x180099b19  test    rax, rax
0x180099b1c  jnz     short loc_180099B25
0x180099b1e  mov     ebx, 8007000Eh
0x180099b23  jmp     short $CleanUp_124
0x180099b25  mov     r8, [rsp+48h+bstrHeaders]; pszSrc
0x180099b2a  lea     edx, [rbx+1]; cchDest
0x180099b2d  mov     this, rdi; pszDest
0x180099b30  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099b35  mov     ebx, eax
0x180099b37  test    eax, eax
0x180099b39  js      short $CleanUp_124
0x180099b3b  mov     [rsi], rdi
0x180099b3e  mov     rdi, r14
0x180099b41  jmp     short $CleanUp_124
0x180099b43  mov     ebx, 80070002h
0x180099b48  mov     this, rdi; pv
0x180099b4b  call    cs:__imp_CoTaskMemFree
0x180099b51  mov     this, [rsp+48h+bstrHeaders]; bstrString
0x180099b56  call    cs:__imp_SysFreeString
0x180099b5c  mov     r9d, ebx; __annotation("TMF:",
0x180099b5f  sar     r9d, 1Fh
0x180099b63  lea     eax, ds:4[r9*2]
0x180099b6b  movsxd  this, eax
0x180099b6e  lea     rax, g_rgFastWppLevelEnabledFlags
0x180099b75  test    byte ptr [rax+this*8], 2
0x180099b79  jz      short loc_180099BA4
0x180099b7b  add     r9w, 2
0x180099b80  lea     r8, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x180099b87  movzx   ecx, r9w
0x180099b8b  mov     eax, 200h
0x180099b90  imul    ecx, eax
0x180099b93  mov     edx, 98h; id
0x180099b98  mov     r9d, ebx; _a1
0x180099b9b  or      cx, 1; LevelKeyword
0x180099b9f  call    WPP_SF_d
0x180099ba4  mov     rbp, [rsp+48h+arg_10]
0x180099ba9  mov     eax, ebx
0x180099bab  mov     rbx, [rsp+48h+arg_0]
0x180099bb0  add     rsp, 30h
0x180099bb4  pop     r14
0x180099bb6  pop     rdi
0x180099bb7  pop     rsi
0x180099bb8  retn
```
