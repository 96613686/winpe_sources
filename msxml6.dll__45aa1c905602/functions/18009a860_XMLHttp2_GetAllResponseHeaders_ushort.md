# XMLHttp2::_GetAllResponseHeaders(ushort * *)

- ea: `0x18009a860`
- end: `0x18009a9d8`
- name: `?_GetAllResponseHeaders@XMLHttp2@@AEAAJPEAPEAG@Z`
- size: `376`
- prototype: `HRESULT __fastcall(XMLHttp2 *this, wchar_t **ppwszHeaders)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009a7b0`

## callees

- `0x18009a860`
- `0x1800c12f4`
- `0x180189008`
- `0x180189d98`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009a8c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009a8c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a95d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a95d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009a91c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009a91c`
- `OLEAUT32!__imp_SysFreeString` at `0x18009a96e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009a96e`
- `OLEAUT32!__imp_SysStringLen` at `0x18009a906`
- `OLEAUT32!__imp_SysStringLen` at `0x18009a906`

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
  if ( (xmmword_1801FAD20 & 2) != 0 )
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
0x18009a860  mov     rax, rsp
0x18009a863  mov     [rax+8], rbx
0x18009a867  mov     [rax+18h], rbp
0x18009a86b  push    rsi
0x18009a86c  push    rdi
0x18009a86d  push    r14
0x18009a86f  sub     rsp, 30h
0x18009a873  xor     r14d, r14d
0x18009a876  mov     rsi, ppwszHeaders
0x18009a879  mov     edi, r14d
0x18009a87c  mov     [rax+10h], r14
0x18009a880  mov     rbp, this
0x18009a883  test    byte ptr cs:xmmword_1801FAD20, 2; __annotation("TMF:",
0x18009a88a  jz      short loc_18009A8A9
0x18009a88c  mov     edx, 97h; id
0x18009a891  mov     [rax-28h], rsi
0x18009a895  mov     ecx, 401h; LevelKeyword
0x18009a89a  lea     r8, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18009a8a1  mov     r9, rbp; _a1
0x18009a8a4  call    WPP_SF_qq
0x18009a8a9  test    rsi, rsi
0x18009a8ac  jnz     short loc_18009A8B8
0x18009a8ae  mov     ebx, 80004003h
0x18009a8b3  jmp     $CleanUp_122
0x18009a8b8  mov     [rsi], r14
0x18009a8bb  cmp     [rbp+30h], r14d
0x18009a8bf  jz      short loc_18009A8DB
0x18009a8c1  mov     ebx, [rbp+30h]
0x18009a8c4  call    cs:__imp_GetCurrentThreadId
0x18009a8cb  nop     dword ptr [rax+rax+00h]
0x18009a8d0  cmp     ebx, eax
0x18009a8d2  jz      short loc_18009A8DB
0x18009a8d4  mov     ebx, 8001010Eh
0x18009a8d9  jmp     short $CleanUp_122
0x18009a8db  mov     this, [rbp+28h]
0x18009a8df  lea     ppwszHeaders, [rsp+48h+bstrHeaders]
0x18009a8e4  mov     rax, [this]
0x18009a8e7  mov     rax, [rax+50h]
0x18009a8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a8f0  mov     ebx, eax
0x18009a8f2  test    eax, eax
0x18009a8f4  js      short $CleanUp_122
0x18009a8f6  mov     this, [rsp+48h+bstrHeaders]; pbstr
0x18009a8fb  test    this, this
0x18009a8fe  jz      short loc_18009A955
0x18009a900  cmp     [this], r14w
0x18009a904  jz      short loc_18009A955
0x18009a906  call    cs:__imp_SysStringLen
0x18009a90d  nop     dword ptr [rax+rax+00h]
0x18009a912  mov     ebx, eax
0x18009a914  lea     this, ds:2[rbx*2]; cb
0x18009a91c  call    cs:__imp_CoTaskMemAlloc
0x18009a923  nop     dword ptr [rax+rax+00h]
0x18009a928  mov     rdi, rax
0x18009a92b  test    rax, rax
0x18009a92e  jnz     short loc_18009A937
0x18009a930  mov     ebx, 8007000Eh
0x18009a935  jmp     short $CleanUp_122
0x18009a937  mov     r8, [rsp+48h+bstrHeaders]; pszSrc
0x18009a93c  lea     edx, [rbx+1]; cchDest
0x18009a93f  mov     this, rdi; pszDest
0x18009a942  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009a947  mov     ebx, eax
0x18009a949  test    eax, eax
0x18009a94b  js      short $CleanUp_122
0x18009a94d  mov     [rsi], rdi
0x18009a950  mov     rdi, r14
0x18009a953  jmp     short $CleanUp_122
0x18009a955  mov     ebx, 80070002h
0x18009a95a  mov     this, rdi; pv
0x18009a95d  call    cs:__imp_CoTaskMemFree
0x18009a964  nop     dword ptr [rax+rax+00h]
0x18009a969  mov     this, [rsp+48h+bstrHeaders]; bstrString
0x18009a96e  call    cs:__imp_SysFreeString
0x18009a975  nop     dword ptr [rax+rax+00h]
0x18009a97a  mov     r9d, ebx; __annotation("TMF:",
0x18009a97d  sar     r9d, 1Fh
0x18009a981  lea     eax, ds:4[r9*2]
0x18009a989  movsxd  this, eax
0x18009a98c  lea     rax, g_rgFastWppLevelEnabledFlags
0x18009a993  test    byte ptr [rax+this*8], 2
0x18009a997  jz      short loc_18009A9C2
0x18009a999  add     r9w, 2
0x18009a99e  lea     r8, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18009a9a5  movzx   ecx, r9w
0x18009a9a9  mov     eax, 200h
0x18009a9ae  imul    ecx, eax
0x18009a9b1  mov     edx, 98h; id
0x18009a9b6  mov     r9d, ebx; _a1
0x18009a9b9  or      cx, 1; LevelKeyword
0x18009a9bd  call    WPP_SF_d
0x18009a9c2  mov     rbp, [rsp+48h+arg_10]
0x18009a9c7  mov     eax, ebx
0x18009a9c9  mov     rbx, [rsp+48h+arg_0]
0x18009a9ce  add     rsp, 30h
0x18009a9d2  pop     r14
0x18009a9d4  pop     rdi
0x18009a9d5  pop     rsi
0x18009a9d6  retn
```
