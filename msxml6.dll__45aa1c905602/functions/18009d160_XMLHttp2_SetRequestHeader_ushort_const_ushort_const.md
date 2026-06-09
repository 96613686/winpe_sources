# XMLHttp2::_SetRequestHeader(ushort const *,ushort const *)

- ea: `0x18009d160`
- end: `0x18009d29c`
- name: `?_SetRequestHeader@XMLHttp2@@AEAAJPEBG0@Z`
- size: `316`
- prototype: `HRESULT __fastcall(XMLHttp2 *this, const wchar_t *pwszHeader, const wchar_t *pwszValue)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18013e2b0`

## callees

- `0x18009d160`
- `0x180189008`
- `0x18018924c`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d1bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d1bd`
- `OLEAUT32!__imp_SysAllocString` at `0x18009d1d7`
- `OLEAUT32!__imp_SysAllocString` at `0x18009d1fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18009d1d7`
- `OLEAUT32!__imp_SysAllocString` at `0x18009d1fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d229`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d238`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d229`
- `OLEAUT32!__imp_SysFreeString` at `0x18009d238`

## pseudocode

```c
__int64 __fastcall XMLHttp2::_SetRequestHeader(XMLHttp2 *this, const wchar_t *pwszHeader, const wchar_t *pwszValue)
{
  wchar_t *v3; // r15
  wchar_t *v5; // r14
  int v8; // ebx
  unsigned int m_dwStaThreadId; // ebx

  v3 = 0;
  v5 = 0;
  if ( (xmmword_1801FAD20 & 2) != 0 )
    WPP_SF_qSS(0x401u, 0x95u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, this, pwszHeader, pwszValue);
  if ( pwszHeader )
  {
    if ( !this->m_dwStaThreadId || (m_dwStaThreadId = this->m_dwStaThreadId, m_dwStaThreadId == GetCurrentThreadId()) )
    {
      v3 = SysAllocString(pwszHeader);
      if ( v3 && (!pwszValue || (v5 = SysAllocString(pwszValue)) != 0) )
        v8 = this->m_pXMLHttp->setRequestHeader(this->m_pXMLHttp, v3, v5);
      else
        v8 = -2147024882;
    }
    else
    {
      v8 = -2147417842;
    }
  }
  else
  {
    v8 = -2147024809;
  }
  SysFreeString(v3);
  SysFreeString(v5);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v8 >> 31) + 4].rgbFlags[0] & 2) != 0 )
    WPP_SF_d((((unsigned __int16)(v8 >> 31) + 2) << 9) | 1, 0x96u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18009d160  push    rbx
0x18009d162  push    rbp
0x18009d163  push    rsi
0x18009d164  push    rdi
0x18009d165  push    r14
0x18009d167  push    r15
0x18009d169  sub     rsp, 38h
0x18009d16d  xor     r15d, r15d
0x18009d170  mov     rsi, pwszValue
0x18009d173  xor     r14d, r14d
0x18009d176  mov     rdi, pwszHeader
0x18009d179  mov     rbp, this
0x18009d17c  test    byte ptr cs:xmmword_1801FAD20, 2; __annotation("TMF:",
0x18009d183  jz      short loc_18009D1A8
0x18009d185  mov     [rsp+68h+_a3], pwszValue; _a3
0x18009d18a  mov     edx, 95h; id
0x18009d18f  lea     pwszValue, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18009d196  mov     [rsp+68h+_a2], rdi; _a2
0x18009d19b  mov     ecx, 401h; LevelKeyword
0x18009d1a0  mov     r9, rbp; _a1
0x18009d1a3  call    WPP_SF_qSS
0x18009d1a8  test    rdi, rdi
0x18009d1ab  jnz     short loc_18009D1B4
0x18009d1ad  mov     ebx, 80070057h
0x18009d1b2  jmp     short $CleanUp_130
0x18009d1b4  cmp     [rbp+30h], r14d
0x18009d1b8  jz      short loc_18009D1D4
0x18009d1ba  mov     ebx, [rbp+30h]
0x18009d1bd  call    cs:__imp_GetCurrentThreadId
0x18009d1c4  nop     dword ptr [rax+rax+00h]
0x18009d1c9  cmp     ebx, eax
0x18009d1cb  jz      short loc_18009D1D4
0x18009d1cd  mov     ebx, 8001010Eh
0x18009d1d2  jmp     short $CleanUp_130
0x18009d1d4  mov     this, rdi; psz
0x18009d1d7  call    cs:__imp_SysAllocString
0x18009d1de  nop     dword ptr [rax+rax+00h]
0x18009d1e3  mov     r15, rax
0x18009d1e6  test    rax, rax
0x18009d1e9  jnz     short loc_18009D1F2
0x18009d1eb  mov     ebx, 8007000Eh
0x18009d1f0  jmp     short $CleanUp_130
0x18009d1f2  test    rsi, rsi
0x18009d1f5  jz      short loc_18009D20E
0x18009d1f7  mov     this, rsi; psz
0x18009d1fa  call    cs:__imp_SysAllocString
0x18009d201  nop     dword ptr [rax+rax+00h]
0x18009d206  mov     r14, rax
0x18009d209  test    rax, rax
0x18009d20c  jz      short loc_18009D1EB
0x18009d20e  mov     this, [rbp+28h]
0x18009d212  mov     pwszValue, r14
0x18009d215  mov     pwszHeader, r15
0x18009d218  mov     rax, [this]
0x18009d21b  mov     rax, [rax+40h]
0x18009d21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d224  mov     ebx, eax
0x18009d226  mov     this, r15; bstrString
0x18009d229  call    cs:__imp_SysFreeString
0x18009d230  nop     dword ptr [rax+rax+00h]
0x18009d235  mov     this, r14; bstrString
0x18009d238  call    cs:__imp_SysFreeString
0x18009d23f  nop     dword ptr [rax+rax+00h]
0x18009d244  mov     r9d, ebx; __annotation("TMF:",
0x18009d247  lea     rax, g_rgFastWppLevelEnabledFlags
0x18009d24e  sar     r9d, 1Fh
0x18009d252  lea     ecx, ds:4[r9*2]
0x18009d25a  movsxd  pwszHeader, ecx
0x18009d25d  test    byte ptr [rax+pwszHeader*8], 2
0x18009d261  jz      short loc_18009D28C
0x18009d263  add     r9w, 2
0x18009d268  lea     pwszValue, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18009d26f  movzx   ecx, r9w
0x18009d273  mov     eax, 200h
0x18009d278  imul    ecx, eax
0x18009d27b  mov     edx, 96h; id
0x18009d280  mov     r9d, ebx; _a1
0x18009d283  or      cx, 1; LevelKeyword
0x18009d287  call    WPP_SF_d
0x18009d28c  mov     eax, ebx
0x18009d28e  add     rsp, 38h
0x18009d292  pop     r15
0x18009d294  pop     r14
0x18009d296  pop     rdi
0x18009d297  pop     rsi
0x18009d298  pop     rbp
0x18009d299  pop     rbx
0x18009d29a  retn
```
