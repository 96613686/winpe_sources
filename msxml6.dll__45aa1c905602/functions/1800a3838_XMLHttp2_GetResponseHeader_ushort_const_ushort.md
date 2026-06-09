# XMLHttp2::_GetResponseHeader(ushort const *,ushort * *)

- ea: `0x1800a3838`
- end: `0x1800a39ee`
- name: `?_GetResponseHeader@XMLHttp2@@AEAAJPEBGPEAPEAG@Z`
- size: `438`
- prototype: `HRESULT __fastcall(XMLHttp2 *this, const wchar_t *pwszHeader, wchar_t **ppwszValue)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013d290`

## callees

- `0x1800a3838`
- `0x1800c12f4`
- `0x180189008`
- `0x1801897c0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a38aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a38aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a3926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a3926`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a38c7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a38c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a396f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a3980`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a396f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a3980`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a3910`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a3910`

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
  if ( (xmmword_1801FAD20 & 2) != 0 )
    WPP_SF_qSq(0x401u, 0x9Bu, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, this, pwszHeader, ppwszValue);
  if ( !ppwszValue )
  {
    v8 = -2147467261;
    goto $CleanUp_144;
  }
  *ppwszValue = 0;
  if ( this->m_dwStaThreadId )
  {
    m_dwStaThreadId = this->m_dwStaThreadId;
    if ( m_dwStaThreadId != GetCurrentThreadId() )
    {
      v8 = -2147417842;
      goto $CleanUp_144;
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
        goto $CleanUp_144;
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
$CleanUp_144:
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
0x1800a3838  mov     rax, rsp
0x1800a383b  mov     [rax+8], rbx
0x1800a383f  mov     [rax+10h], rbp
0x1800a3843  push    rsi
0x1800a3844  push    rdi
0x1800a3845  push    r12
0x1800a3847  push    r14
0x1800a3849  push    r15
0x1800a384b  sub     rsp, 30h
0x1800a384f  xor     r12d, r12d
0x1800a3852  mov     rsi, ppwszValue
0x1800a3855  mov     r14d, r12d
0x1800a3858  mov     [rax+18h], r12
0x1800a385c  mov     edi, r12d
0x1800a385f  mov     r15, pwszHeader
0x1800a3862  mov     rbp, this
0x1800a3865  test    byte ptr cs:xmmword_1801FAD20, 2; __annotation("TMF:",
0x1800a386c  jz      short loc_1800A388F
0x1800a386e  mov     [rax-30h], ppwszValue
0x1800a3872  mov     edx, 9Bh; id
0x1800a3877  lea     ppwszValue, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1800a387e  mov     [rax-38h], r15
0x1800a3882  mov     ecx, 401h; LevelKeyword
0x1800a3887  mov     r9, rbp; _a1
0x1800a388a  call    WPP_SF_qSq
0x1800a388f  test    rsi, rsi
0x1800a3892  jnz     short loc_1800A389E
0x1800a3894  mov     ebx, 80004003h
0x1800a3899  jmp     $CleanUp_144
0x1800a389e  mov     [rsi], r12
0x1800a38a1  cmp     [rbp+30h], r12d
0x1800a38a5  jz      short loc_1800A38C4
0x1800a38a7  mov     ebx, [rbp+30h]
0x1800a38aa  call    cs:__imp_GetCurrentThreadId
0x1800a38b1  nop     dword ptr [rax+rax+00h]
0x1800a38b6  cmp     ebx, eax
0x1800a38b8  jz      short loc_1800A38C4
0x1800a38ba  mov     ebx, 8001010Eh
0x1800a38bf  jmp     $CleanUp_144
0x1800a38c4  mov     this, r15; psz
0x1800a38c7  call    cs:__imp_SysAllocString
0x1800a38ce  nop     dword ptr [rax+rax+00h]
0x1800a38d3  mov     r14, rax
0x1800a38d6  test    rax, rax
0x1800a38d9  jnz     short loc_1800A38E2
0x1800a38db  mov     ebx, 8007000Eh
0x1800a38e0  jmp     short $CleanUp_144
0x1800a38e2  mov     this, [rbp+28h]
0x1800a38e6  lea     ppwszValue, [rsp+58h+bstrValue]
0x1800a38eb  mov     pwszHeader, r14
0x1800a38ee  mov     rax, [this]
0x1800a38f1  mov     rax, [rax+48h]
0x1800a38f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a38fa  mov     ebx, eax
0x1800a38fc  test    eax, eax
0x1800a38fe  js      short $CleanUp_144
0x1800a3900  mov     this, [rsp+58h+bstrValue]; pbstr
0x1800a3905  test    this, this
0x1800a3908  jz      short loc_1800A3958
0x1800a390a  cmp     [this], r12w
0x1800a390e  jz      short loc_1800A3958
0x1800a3910  call    cs:__imp_SysStringLen
0x1800a3917  nop     dword ptr [rax+rax+00h]
0x1800a391c  mov     ebx, eax
0x1800a391e  lea     this, ds:2[rbx*2]; cb
0x1800a3926  call    cs:__imp_CoTaskMemAlloc
0x1800a392d  nop     dword ptr [rax+rax+00h]
0x1800a3932  mov     rdi, rax
0x1800a3935  test    rax, rax
0x1800a3938  jz      short loc_1800A38DB
0x1800a393a  mov     ppwszValue, [rsp+58h+bstrValue]; pszSrc
0x1800a393f  lea     edx, [rbx+1]; cchDest
0x1800a3942  mov     this, rax; pszDest
0x1800a3945  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a394a  mov     ebx, eax
0x1800a394c  test    eax, eax
0x1800a394e  js      short $CleanUp_144
0x1800a3950  mov     [rsi], rdi
0x1800a3953  mov     rdi, r12
0x1800a3956  jmp     short $CleanUp_144
0x1800a3958  mov     ebx, 80070002h
0x1800a395d  mov     this, rdi; pv
0x1800a3960  call    cs:__imp_CoTaskMemFree
0x1800a3967  nop     dword ptr [rax+rax+00h]
0x1800a396c  mov     this, r14; bstrString
0x1800a396f  call    cs:__imp_SysFreeString
0x1800a3976  nop     dword ptr [rax+rax+00h]
0x1800a397b  mov     this, [rsp+58h+bstrValue]; bstrString
0x1800a3980  call    cs:__imp_SysFreeString
0x1800a3987  nop     dword ptr [rax+rax+00h]
0x1800a398c  mov     r9d, ebx; __annotation("TMF:",
0x1800a398f  sar     r9d, 1Fh
0x1800a3993  lea     eax, ds:4[r9*2]
0x1800a399b  movsxd  this, eax
0x1800a399e  lea     rax, g_rgFastWppLevelEnabledFlags
0x1800a39a5  test    byte ptr [rax+this*8], 2
0x1800a39a9  jz      short loc_1800A39D4
0x1800a39ab  add     r9w, 2
0x1800a39b0  lea     ppwszValue, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1800a39b7  movzx   ecx, r9w
0x1800a39bb  mov     eax, 200h
0x1800a39c0  imul    ecx, eax
0x1800a39c3  mov     edx, 9Ch; id
0x1800a39c8  mov     r9d, ebx; _a1
0x1800a39cb  or      cx, 1; LevelKeyword
0x1800a39cf  call    WPP_SF_d
0x1800a39d4  mov     rbp, [rsp+58h+arg_8]
0x1800a39d9  mov     eax, ebx
0x1800a39db  mov     rbx, [rsp+58h+arg_0]
0x1800a39e0  add     rsp, 30h
0x1800a39e4  pop     r15
0x1800a39e6  pop     r14
0x1800a39e8  pop     r12
0x1800a39ea  pop     rdi
0x1800a39eb  pop     rsi
0x1800a39ec  retn
```
