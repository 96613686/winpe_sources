# XMLHttp2::_GetResponseHeader(ushort const *,ushort * *)

- ea: `0x1800a32bc`
- end: `0x1800a3447`
- name: `?_GetResponseHeader@XMLHttp2@@AEAAJPEBGPEAPEAG@Z`
- size: `395`
- prototype: `__int64 __fastcall(XMLHttp2 *this, const wchar_t *pwszHeader, wchar_t **ppwszValue)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013a1b0`

## callees

- `0x1800a32bc`
- `0x1800bfc70`
- `0x180185008`
- `0x1801857b4`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a332e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a332e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a33cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a33cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a3398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a3398`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a3345`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a3345`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a33d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a33e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a33d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a33e0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a3388`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a3388`

## pseudocode

```c
__int64 __fastcall XMLHttp2::_GetResponseHeader(XMLHttp2 *this, const wchar_t *pwszHeader, wchar_t **ppwszValue)
{
  wchar_t *v4; // r14
  wchar_t *v5; // rdi
  int v8; // ebx
  unsigned int m_dwStaThreadId; // ebx
  wchar_t *v10; // rax
  UINT v11; // ebx
  wchar_t *v12; // rax
  wchar_t *bstrValue; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  bstrValue = 0;
  v5 = 0;
  if ( (xmmword_1801F6C20 & 2) != 0 )
    WPP_SF_qSq(0x401u, 0x9Bu, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, this, pwszHeader, ppwszValue);
  if ( !ppwszValue )
  {
    v8 = -2147467261;
    goto $CleanUp_146;
  }
  *ppwszValue = 0;
  if ( this->m_dwStaThreadId )
  {
    m_dwStaThreadId = this->m_dwStaThreadId;
    if ( m_dwStaThreadId != GetCurrentThreadId() )
    {
      v8 = -2147417842;
      goto $CleanUp_146;
    }
  }
  v10 = SysAllocString(pwszHeader);
  v4 = v10;
  if ( !v10 )
    goto LABEL_9;
  v8 = this->m_pXMLHttp->getResponseHeader(this->m_pXMLHttp, v10, &bstrValue);
  if ( v8 >= 0 )
  {
    if ( bstrValue && *bstrValue )
    {
      v11 = SysStringLen(bstrValue);
      v12 = (wchar_t *)CoTaskMemAlloc(2LL * v11 + 2);
      v5 = v12;
      if ( !v12 )
      {
LABEL_9:
        v8 = -2147024882;
        goto $CleanUp_146;
      }
      v8 = StringCchCopyW(v12, v11 + 1, bstrValue);
      if ( v8 >= 0 )
      {
        *ppwszValue = v5;
        v5 = 0;
      }
    }
    else
    {
      v8 = -2147024894;
    }
  }
$CleanUp_146:
  CoTaskMemFree(v5);
  SysFreeString(v4);
  SysFreeString(bstrValue);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v8 >> 31) + 4].rgbFlags[0] & 2) != 0 )
    WPP_SF_d((((unsigned __int16)(v8 >> 31) + 2) << 9) | 1, 0x9Cu, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a32bc  mov     rax, rsp
0x1800a32bf  mov     [rax+8], rbx
0x1800a32c3  mov     [rax+10h], rbp
0x1800a32c7  push    rsi
0x1800a32c8  push    rdi
0x1800a32c9  push    r12
0x1800a32cb  push    r14
0x1800a32cd  push    r15
0x1800a32cf  sub     rsp, 30h
0x1800a32d3  xor     r12d, r12d
0x1800a32d6  mov     rsi, ppwszValue
0x1800a32d9  mov     r14d, r12d
0x1800a32dc  mov     [rax+18h], r12
0x1800a32e0  mov     edi, r12d
0x1800a32e3  mov     r15, pwszHeader
0x1800a32e6  mov     rbp, this
0x1800a32e9  test    byte ptr cs:xmmword_1801F6C20, 2; __annotation("TMF:",
0x1800a32f0  jz      short loc_1800A3313
0x1800a32f2  mov     [rax-30h], ppwszValue
0x1800a32f6  mov     edx, 9Bh; id
0x1800a32fb  lea     ppwszValue, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1800a3302  mov     [rax-38h], r15
0x1800a3306  mov     ecx, 401h; LevelKeyword
0x1800a330b  mov     r9, rbp; _a1
0x1800a330e  call    WPP_SF_qSq
0x1800a3313  test    rsi, rsi
0x1800a3316  jnz     short loc_1800A3322
0x1800a3318  mov     ebx, 80004003h
0x1800a331d  jmp     $CleanUp_146
0x1800a3322  mov     [rsi], r12
0x1800a3325  cmp     [rbp+30h], r12d
0x1800a3329  jz      short loc_1800A3342
0x1800a332b  mov     ebx, [rbp+30h]
0x1800a332e  call    cs:__imp_GetCurrentThreadId
0x1800a3334  cmp     ebx, eax
0x1800a3336  jz      short loc_1800A3342
0x1800a3338  mov     ebx, 8001010Eh
0x1800a333d  jmp     $CleanUp_146
0x1800a3342  mov     this, r15; psz
0x1800a3345  call    cs:__imp_SysAllocString
0x1800a334b  mov     r14, rax
0x1800a334e  test    rax, rax
0x1800a3351  jnz     short loc_1800A335A
0x1800a3353  mov     ebx, 8007000Eh
0x1800a3358  jmp     short $CleanUp_146
0x1800a335a  mov     this, [rbp+28h]
0x1800a335e  lea     ppwszValue, [rsp+58h+bstrValue]
0x1800a3363  mov     pwszHeader, r14
0x1800a3366  mov     rax, [this]
0x1800a3369  mov     rax, [rax+48h]
0x1800a336d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3372  mov     ebx, eax
0x1800a3374  test    eax, eax
0x1800a3376  js      short $CleanUp_146
0x1800a3378  mov     this, [rsp+58h+bstrValue]; pbstr
0x1800a337d  test    this, this
0x1800a3380  jz      short loc_1800A33C4
0x1800a3382  cmp     [this], r12w
0x1800a3386  jz      short loc_1800A33C4
0x1800a3388  call    cs:__imp_SysStringLen
0x1800a338e  mov     ebx, eax
0x1800a3390  lea     this, ds:2[rbx*2]; cb
0x1800a3398  call    cs:__imp_CoTaskMemAlloc
0x1800a339e  mov     rdi, rax
0x1800a33a1  test    rax, rax
0x1800a33a4  jz      short loc_1800A3353
0x1800a33a6  mov     ppwszValue, [rsp+58h+bstrValue]; pszSrc
0x1800a33ab  lea     edx, [rbx+1]; cchDest
0x1800a33ae  mov     this, rax; pszDest
0x1800a33b1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a33b6  mov     ebx, eax
0x1800a33b8  test    eax, eax
0x1800a33ba  js      short $CleanUp_146
0x1800a33bc  mov     [rsi], rdi
0x1800a33bf  mov     rdi, r12
0x1800a33c2  jmp     short $CleanUp_146
0x1800a33c4  mov     ebx, 80070002h
0x1800a33c9  mov     this, rdi; pv
0x1800a33cc  call    cs:__imp_CoTaskMemFree
0x1800a33d2  mov     this, r14; bstrString
0x1800a33d5  call    cs:__imp_SysFreeString
0x1800a33db  mov     this, [rsp+58h+bstrValue]; bstrString
0x1800a33e0  call    cs:__imp_SysFreeString
0x1800a33e6  mov     r9d, ebx; __annotation("TMF:",
0x1800a33e9  sar     r9d, 1Fh
0x1800a33ed  lea     eax, ds:4[r9*2]
0x1800a33f5  movsxd  this, eax
0x1800a33f8  lea     rax, g_rgFastWppLevelEnabledFlags
0x1800a33ff  test    byte ptr [rax+this*8], 2
0x1800a3403  jz      short loc_1800A342E
0x1800a3405  add     r9w, 2
0x1800a340a  lea     ppwszValue, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1800a3411  movzx   ecx, r9w
0x1800a3415  mov     eax, 200h
0x1800a341a  imul    ecx, eax
0x1800a341d  mov     edx, 9Ch; id
0x1800a3422  mov     r9d, ebx; _a1
0x1800a3425  or      cx, 1; LevelKeyword
0x1800a3429  call    WPP_SF_d
0x1800a342e  mov     rbp, [rsp+58h+arg_8]
0x1800a3433  mov     eax, ebx
0x1800a3435  mov     rbx, [rsp+58h+arg_0]
0x1800a343a  add     rsp, 30h
0x1800a343e  pop     r15
0x1800a3440  pop     r14
0x1800a3442  pop     r12
0x1800a3444  pop     rdi
0x1800a3445  pop     rsi
0x1800a3446  retn
```
