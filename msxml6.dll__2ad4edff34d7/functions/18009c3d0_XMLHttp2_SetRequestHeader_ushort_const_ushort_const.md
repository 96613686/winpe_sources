# XMLHttp2::_SetRequestHeader(ushort const *,ushort const *)

- ea: `0x18009c3d0`
- end: `0x18009c4ed`
- name: `?_SetRequestHeader@XMLHttp2@@AEAAJPEBG0@Z`
- size: `285`
- prototype: `__int64 __fastcall(XMLHttp2 *this, const wchar_t *pwszHeader, const wchar_t *pwszValue)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18013b1a0`

## callees

- `0x18009c3d0`
- `0x180185008`
- `0x180185244`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c42d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c42d`
- `OLEAUT32!__imp_SysAllocString` at `0x18009c441`
- `OLEAUT32!__imp_SysAllocString` at `0x18009c45e`
- `OLEAUT32!__imp_SysAllocString` at `0x18009c441`
- `OLEAUT32!__imp_SysAllocString` at `0x18009c45e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009c487`
- `OLEAUT32!__imp_SysFreeString` at `0x18009c490`
- `OLEAUT32!__imp_SysFreeString` at `0x18009c487`
- `OLEAUT32!__imp_SysFreeString` at `0x18009c490`

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
  if ( (xmmword_1801F6C20 & 2) != 0 )
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
0x18009c3d0  push    rbx
0x18009c3d2  push    rbp
0x18009c3d3  push    rsi
0x18009c3d4  push    rdi
0x18009c3d5  push    r14
0x18009c3d7  push    r15
0x18009c3d9  sub     rsp, 38h
0x18009c3dd  xor     r15d, r15d
0x18009c3e0  mov     rsi, pwszValue
0x18009c3e3  xor     r14d, r14d
0x18009c3e6  mov     rdi, pwszHeader
0x18009c3e9  mov     rbp, this
0x18009c3ec  test    byte ptr cs:xmmword_1801F6C20, 2; __annotation("TMF:",
0x18009c3f3  jz      short loc_18009C418
0x18009c3f5  mov     [rsp+68h+_a3], pwszValue; _a3
0x18009c3fa  mov     edx, 95h; id
0x18009c3ff  lea     pwszValue, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18009c406  mov     [rsp+68h+_a2], rdi; _a2
0x18009c40b  mov     ecx, 401h; LevelKeyword
0x18009c410  mov     r9, rbp; _a1
0x18009c413  call    WPP_SF_qSS
0x18009c418  test    rdi, rdi
0x18009c41b  jnz     short loc_18009C424
0x18009c41d  mov     ebx, 80070057h
0x18009c422  jmp     short $CleanUp_132
0x18009c424  cmp     [rbp+30h], r14d
0x18009c428  jz      short loc_18009C43E
0x18009c42a  mov     ebx, [rbp+30h]
0x18009c42d  call    cs:__imp_GetCurrentThreadId
0x18009c433  cmp     ebx, eax
0x18009c435  jz      short loc_18009C43E
0x18009c437  mov     ebx, 8001010Eh
0x18009c43c  jmp     short $CleanUp_132
0x18009c43e  mov     this, rdi; psz
0x18009c441  call    cs:__imp_SysAllocString
0x18009c447  mov     r15, rax
0x18009c44a  test    rax, rax
0x18009c44d  jnz     short loc_18009C456
0x18009c44f  mov     ebx, 8007000Eh
0x18009c454  jmp     short $CleanUp_132
0x18009c456  test    rsi, rsi
0x18009c459  jz      short loc_18009C46C
0x18009c45b  mov     this, rsi; psz
0x18009c45e  call    cs:__imp_SysAllocString
0x18009c464  mov     r14, rax
0x18009c467  test    rax, rax
0x18009c46a  jz      short loc_18009C44F
0x18009c46c  mov     this, [rbp+28h]
0x18009c470  mov     pwszValue, r14
0x18009c473  mov     pwszHeader, r15
0x18009c476  mov     rax, [this]
0x18009c479  mov     rax, [rax+40h]
0x18009c47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c482  mov     ebx, eax
0x18009c484  mov     this, r15; bstrString
0x18009c487  call    cs:__imp_SysFreeString
0x18009c48d  mov     this, r14; bstrString
0x18009c490  call    cs:__imp_SysFreeString
0x18009c496  mov     r9d, ebx; __annotation("TMF:",
0x18009c499  lea     rax, g_rgFastWppLevelEnabledFlags
0x18009c4a0  sar     r9d, 1Fh
0x18009c4a4  lea     ecx, ds:4[r9*2]
0x18009c4ac  movsxd  pwszHeader, ecx
0x18009c4af  test    byte ptr [rax+pwszHeader*8], 2
0x18009c4b3  jz      short loc_18009C4DE
0x18009c4b5  add     r9w, 2
0x18009c4ba  lea     pwszValue, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18009c4c1  movzx   ecx, r9w
0x18009c4c5  mov     eax, 200h
0x18009c4ca  imul    ecx, eax
0x18009c4cd  mov     edx, 96h; id
0x18009c4d2  mov     r9d, ebx; _a1
0x18009c4d5  or      cx, 1; LevelKeyword
0x18009c4d9  call    WPP_SF_d
0x18009c4de  mov     eax, ebx
0x18009c4e0  add     rsp, 38h
0x18009c4e4  pop     r15
0x18009c4e6  pop     r14
0x18009c4e8  pop     rdi
0x18009c4e9  pop     rsi
0x18009c4ea  pop     rbp
0x18009c4eb  pop     rbx
0x18009c4ec  retn
```
