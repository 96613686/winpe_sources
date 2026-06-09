# Vml::VmRegistryKey::SetValue(ushort const *,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x180025a44`
- end: `0x180025c2e`
- name: `?SetValue@VmRegistryKey@Vml@@QEAAXPEBGAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800258b0`

## callees

- `0x1800067c0`
- `0x180009e8c`
- `0x180011a4c`
- `0x180025a44`
- `0x180027380`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180025b2e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180025b2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025bde`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025bde`

## string_xrefs

- `0x180025c1c`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Vml::VmRegistryKey::SetValue(HKEY *a1, const WCHAR *a2, __int64 ***a3)
{
  int v6; // esi
  __int64 **v7; // rdi
  __int64 *v8; // rax
  int v9; // esi
  __int64 **v10; // rdx
  __int64 *i; // rcx
  __int64 *j; // rdx
  __int64 *v13; // rbx
  unsigned int v14; // r15d
  int v15; // r14d
  _QWORD *v16; // r8
  BYTE **v17; // rcx
  BYTE **v18; // r8
  __int64 v19; // rdx
  __int64 **v20; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  BYTE **v23; // r8
  const BYTE *v24; // rcx
  unsigned int v25; // eax
  unsigned int lpData; // [rsp+20h] [rbp-40h]
  BYTE *Src[2]; // [rsp+30h] [rbp-30h] BYREF
  __m128i si128; // [rsp+40h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v6 = 0;
  v7 = *a3;
  v8 = **a3;
  while ( 1 )
  {
    v9 = v6 + 1;
    if ( v8 == (__int64 *)v7 )
      break;
    v6 = *((_DWORD *)v8 + 12) + v9;
    v10 = (__int64 **)v8[2];
    if ( *((_BYTE *)v10 + 25) )
    {
      for ( i = (__int64 *)v8[1]; !*((_BYTE *)i + 25) && v8 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v8 = i;
      v8 = i;
    }
    else
    {
      v8 = (__int64 *)v8[2];
      for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v8 = j;
    }
  }
  *(_OWORD *)Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  std::wstring::resize(Src);
  v13 = **a3;
  v14 = 0;
  while ( v13 != (__int64 *)v7 )
  {
    v15 = *((_DWORD *)v13 + 12);
    v16 = v13 + 4;
    if ( (unsigned __int64)v13[7] > 7 )
      v16 = (_QWORD *)*v16;
    v17 = Src;
    if ( si128.m128i_i64[1] > 7uLL )
      v17 = (BYTE **)Src[0];
    _o_wcscpy_s((char *)v17 + 2 * v14, (unsigned int)(v15 + 1), v16);
    v18 = Src;
    if ( si128.m128i_i64[1] > 7uLL )
      v18 = (BYTE **)Src[0];
    v19 = v15 + v14;
    *((_WORD *)v18 + v19) = 0;
    v14 = v19 + 1;
    v20 = (__int64 **)v13[2];
    if ( *((_BYTE *)v20 + 25) )
    {
      for ( k = (__int64 *)v13[1]; !*((_BYTE *)k + 25) && v13 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v13 = k;
      v13 = k;
    }
    else
    {
      v13 = (__int64 *)v13[2];
      for ( m = *v20; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v13 = m;
    }
  }
  v23 = Src;
  if ( si128.m128i_i64[1] > 7uLL )
    v23 = (BYTE **)Src[0];
  *((_WORD *)v23 + v14) = 0;
  v24 = (const BYTE *)Src;
  if ( si128.m128i_i64[1] > 7uLL )
    v24 = Src[0];
  v25 = RegSetValueExW(*a1, a2, 0, 7u, v24, 2 * v9);
  if ( v25 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x353,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v25,
      lpData);
  return std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x180025a44  mov     [rsp-38h+arg_10], rbx
0x180025a49  push    rbp
0x180025a4a  push    rsi
0x180025a4b  push    rdi
0x180025a4c  push    r12
0x180025a4e  push    r13
0x180025a50  push    r14
0x180025a52  push    r15
0x180025a54  mov     rbp, rsp
0x180025a57  sub     rsp, 60h
0x180025a5b  mov     rax, cs:__security_cookie
0x180025a62  xor     rax, rsp
0x180025a65  mov     [rbp+var_10], rax
0x180025a69  mov     rbx, r8
0x180025a6c  mov     r13, rdx
0x180025a6f  mov     r12, rcx
0x180025a72  xor     r14d, r14d
0x180025a75  mov     esi, r14d
0x180025a78  mov     rdi, [r8]
0x180025a7b  mov     rax, [rdi]
0x180025a7e  inc     esi
0x180025a80  cmp     rax, rdi
0x180025a83  jz      short loc_180025ACD
0x180025a85  add     esi, [rax+30h]
0x180025a88  mov     rdx, [rax+10h]
0x180025a8c  cmp     [rdx+19h], r14b
0x180025a90  jz      short loc_180025AB0
0x180025a92  mov     rcx, [rax+8]
0x180025a96  jmp     short loc_180025AA5
0x180025a98  cmp     rax, [rcx+10h]
0x180025a9c  jnz     short loc_180025AAB
0x180025a9e  mov     rax, rcx
0x180025aa1  mov     rcx, [rcx+8]
0x180025aa5  cmp     [rcx+19h], r14b
0x180025aa9  jz      short loc_180025A98
0x180025aab  mov     rax, rcx
0x180025aae  jmp     short loc_180025A7E
0x180025ab0  mov     rax, rdx
0x180025ab3  mov     rdx, [rdx]
0x180025ab6  cmp     [rdx+19h], r14b
0x180025aba  jnz     short loc_180025A7E
0x180025abc  mov     rax, rdx
0x180025abf  mov     rcx, [rdx]
0x180025ac2  mov     rdx, rcx
0x180025ac5  cmp     [rcx+19h], r14b
0x180025ac9  jz      short loc_180025ABC
0x180025acb  jmp     short loc_180025A7E
0x180025acd  mov     edx, esi
0x180025acf  xorps   xmm0, xmm0
0x180025ad2  movups  xmmword ptr [rbp+Src], xmm0
0x180025ad6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180025ade  movdqu  [rbp+var_20], xmm1
0x180025ae3  mov     word ptr [rbp+Src], r14w
0x180025ae8  lea     rcx, [rbp+Src]; Src
0x180025aec  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180025af1  mov     rbx, [rbx]
0x180025af4  mov     rbx, [rbx]
0x180025af7  mov     r15d, r14d
0x180025afa  cmp     rbx, rdi
0x180025afd  jz      loc_180025B9E
0x180025b03  mov     r14d, [rbx+30h]
0x180025b07  lea     r8, [rbx+20h]
0x180025b0b  cmp     qword ptr [rbx+38h], 7
0x180025b10  jbe     short loc_180025B15
0x180025b12  mov     r8, [r8]
0x180025b15  lea     rcx, [rbp+Src]
0x180025b19  cmp     qword ptr [rbp+var_20+8], 7
0x180025b1e  cmova   rcx, [rbp+Src]
0x180025b23  lea     edx, [r14+1]
0x180025b27  mov     eax, r15d
0x180025b2a  lea     rcx, [rcx+rax*2]
0x180025b2e  call    cs:__imp__o_wcscpy_s
0x180025b34  lea     r8, [rbp+Src]
0x180025b38  cmp     qword ptr [rbp+var_20+8], 7
0x180025b3d  cmova   r8, [rbp+Src]
0x180025b42  lea     edx, [r14+r15]
0x180025b46  xor     r14d, r14d
0x180025b49  mov     [r8+rdx*2], r14w
0x180025b4e  lea     r15d, [rdx+1]
0x180025b52  mov     rcx, [rbx+10h]
0x180025b56  cmp     [rcx+19h], r14b
0x180025b5a  jz      short loc_180025B7A
0x180025b5c  mov     rax, [rbx+8]
0x180025b60  jmp     short loc_180025B6F
0x180025b62  cmp     rbx, [rax+10h]
0x180025b66  jnz     short loc_180025B75
0x180025b68  mov     rbx, rax
0x180025b6b  mov     rax, [rax+8]
0x180025b6f  cmp     [rax+19h], r14b
0x180025b73  jz      short loc_180025B62
0x180025b75  mov     rbx, rax
0x180025b78  jmp     short loc_180025AFA
0x180025b7a  mov     rbx, rcx
0x180025b7d  mov     rcx, [rcx]
0x180025b80  cmp     [rcx+19h], r14b
0x180025b84  jnz     loc_180025AFA
0x180025b8a  mov     rbx, rcx
0x180025b8d  mov     rax, [rcx]
0x180025b90  mov     rcx, rax
0x180025b93  cmp     [rax+19h], r14b
0x180025b97  jz      short loc_180025B8A
0x180025b99  jmp     loc_180025AFA
0x180025b9e  lea     r8, [rbp+Src]
0x180025ba2  cmp     qword ptr [rbp+var_20+8], 7
0x180025ba7  cmova   r8, [rbp+Src]
0x180025bac  mov     ecx, r15d
0x180025baf  mov     [r8+rcx*2], r14w
0x180025bb4  lea     rcx, [rbp+Src]
0x180025bb8  cmp     qword ptr [rbp+var_20+8], 7
0x180025bbd  cmova   rcx, [rbp+Src]
0x180025bc2  lea     eax, [rsi+rsi]
0x180025bc5  mov     [rsp+60h+cbData], eax; cbData
0x180025bc9  mov     [rsp+60h+lpData], rcx; unsigned int
0x180025bce  mov     r9d, 7; dwType
0x180025bd4  xor     r8d, r8d; Reserved
0x180025bd7  mov     rdx, r13; lpValueName
0x180025bda  mov     rcx, [r12]; hKey
0x180025bde  call    cs:__imp_RegSetValueExW
0x180025be4  mov     rcx, [rbp+38h]; this
0x180025be8  test    eax, eax
0x180025bea  jnz     short loc_180025C19
0x180025bec  lea     rcx, [rbp+Src]
0x180025bf0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025bf5  mov     rcx, [rbp+var_10]
0x180025bf9  xor     rcx, rsp; StackCookie
0x180025bfc  call    __security_check_cookie
0x180025c01  mov     rbx, [rsp+60h+arg_10]
0x180025c09  add     rsp, 60h
0x180025c0d  pop     r15
0x180025c0f  pop     r14
0x180025c11  pop     r13
0x180025c13  pop     r12
0x180025c15  pop     rdi
0x180025c16  pop     rsi
0x180025c17  pop     rbp
0x180025c18  retn
0x180025c19  mov     r9d, eax; char *
0x180025c1c  lea     r8, aOnecoreVmCommo_35; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x180025c23  mov     edx, 353h; void *
0x180025c28  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
