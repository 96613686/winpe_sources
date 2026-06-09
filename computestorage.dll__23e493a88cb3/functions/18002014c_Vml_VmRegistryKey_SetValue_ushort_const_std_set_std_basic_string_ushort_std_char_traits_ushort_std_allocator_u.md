# Vml::VmRegistryKey::SetValue(ushort const *,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18002014c`
- end: `0x180020346`
- name: `?SetValue@VmRegistryKey@Vml@@QEAAXPEBGAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ffa0`

## callees

- `0x180002690`
- `0x180008fac`
- `0x180012818`
- `0x180013cb4`
- `0x18002014c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180020236`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180020236`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800202ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800202ef`

## string_xrefs

- `0x180020334`: `onecore\vm\common\vml\VmRegistry.h`

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
  return std::wstring::~wstring((char **)Src);
}

```

## disassembly

```asm
0x18002014c  mov     [rsp-38h+arg_10], rbx
0x180020151  push    rbp
0x180020152  push    rsi
0x180020153  push    rdi
0x180020154  push    r12
0x180020156  push    r13
0x180020158  push    r14
0x18002015a  push    r15
0x18002015c  mov     rbp, rsp
0x18002015f  sub     rsp, 60h
0x180020163  mov     rax, cs:__security_cookie
0x18002016a  xor     rax, rsp
0x18002016d  mov     [rbp+var_10], rax
0x180020171  mov     rbx, r8
0x180020174  mov     r13, rdx
0x180020177  mov     r12, rcx
0x18002017a  xor     r14d, r14d
0x18002017d  mov     esi, r14d
0x180020180  mov     rdi, [r8]
0x180020183  mov     rax, [rdi]
0x180020186  inc     esi
0x180020188  cmp     rax, rdi
0x18002018b  jz      short loc_1800201D5
0x18002018d  add     esi, [rax+30h]
0x180020190  mov     rdx, [rax+10h]
0x180020194  cmp     [rdx+19h], r14b
0x180020198  jz      short loc_1800201B8
0x18002019a  mov     rcx, [rax+8]
0x18002019e  jmp     short loc_1800201AD
0x1800201a0  cmp     rax, [rcx+10h]
0x1800201a4  jnz     short loc_1800201B3
0x1800201a6  mov     rax, rcx
0x1800201a9  mov     rcx, [rcx+8]
0x1800201ad  cmp     [rcx+19h], r14b
0x1800201b1  jz      short loc_1800201A0
0x1800201b3  mov     rax, rcx
0x1800201b6  jmp     short loc_180020186
0x1800201b8  mov     rax, rdx
0x1800201bb  mov     rdx, [rdx]
0x1800201be  cmp     [rdx+19h], r14b
0x1800201c2  jnz     short loc_180020186
0x1800201c4  mov     rax, rdx
0x1800201c7  mov     rcx, [rdx]
0x1800201ca  mov     rdx, rcx
0x1800201cd  cmp     [rcx+19h], r14b
0x1800201d1  jz      short loc_1800201C4
0x1800201d3  jmp     short loc_180020186
0x1800201d5  mov     edx, esi
0x1800201d7  xorps   xmm0, xmm0
0x1800201da  movups  xmmword ptr [rbp+Src], xmm0
0x1800201de  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800201e6  movdqu  [rbp+var_20], xmm1
0x1800201eb  mov     word ptr [rbp+Src], r14w
0x1800201f0  lea     rcx, [rbp+Src]; Src
0x1800201f4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800201f9  mov     rbx, [rbx]
0x1800201fc  mov     rbx, [rbx]
0x1800201ff  mov     r15d, r14d
0x180020202  cmp     rbx, rdi
0x180020205  jz      loc_1800202AF
0x18002020b  mov     r14d, [rbx+30h]
0x18002020f  lea     r8, [rbx+20h]
0x180020213  cmp     qword ptr [rbx+38h], 7
0x180020218  jbe     short loc_18002021D
0x18002021a  mov     r8, [r8]
0x18002021d  lea     rcx, [rbp+Src]
0x180020221  cmp     qword ptr [rbp+var_20+8], 7
0x180020226  cmova   rcx, [rbp+Src]
0x18002022b  lea     edx, [r14+1]
0x18002022f  mov     eax, r15d
0x180020232  lea     rcx, [rcx+rax*2]
0x180020236  call    cs:__imp__o_wcscpy_s
0x18002023d  nop     dword ptr [rax+rax+00h]
0x180020242  lea     r8, [rbp+Src]
0x180020246  cmp     qword ptr [rbp+var_20+8], 7
0x18002024b  cmova   r8, [rbp+Src]
0x180020250  lea     edx, [r14+r15]
0x180020254  xor     r14d, r14d
0x180020257  mov     [r8+rdx*2], r14w
0x18002025c  lea     r15d, [rdx+1]
0x180020260  mov     rcx, [rbx+10h]
0x180020264  cmp     [rcx+19h], r14b
0x180020268  jz      short loc_18002028B
0x18002026a  mov     rax, [rbx+8]
0x18002026e  jmp     short loc_18002027D
0x180020270  cmp     rbx, [rax+10h]
0x180020274  jnz     short loc_180020283
0x180020276  mov     rbx, rax
0x180020279  mov     rax, [rax+8]
0x18002027d  cmp     [rax+19h], r14b
0x180020281  jz      short loc_180020270
0x180020283  mov     rbx, rax
0x180020286  jmp     loc_180020202
0x18002028b  mov     rbx, rcx
0x18002028e  mov     rcx, [rcx]
0x180020291  cmp     [rcx+19h], r14b
0x180020295  jnz     loc_180020202
0x18002029b  mov     rbx, rcx
0x18002029e  mov     rax, [rcx]
0x1800202a1  mov     rcx, rax
0x1800202a4  cmp     [rax+19h], r14b
0x1800202a8  jz      short loc_18002029B
0x1800202aa  jmp     loc_180020202
0x1800202af  lea     r8, [rbp+Src]
0x1800202b3  cmp     qword ptr [rbp+var_20+8], 7
0x1800202b8  cmova   r8, [rbp+Src]
0x1800202bd  mov     ecx, r15d
0x1800202c0  mov     [r8+rcx*2], r14w
0x1800202c5  lea     rcx, [rbp+Src]
0x1800202c9  cmp     qword ptr [rbp+var_20+8], 7
0x1800202ce  cmova   rcx, [rbp+Src]
0x1800202d3  lea     eax, [rsi+rsi]
0x1800202d6  mov     [rsp+60h+cbData], eax; cbData
0x1800202da  mov     [rsp+60h+lpData], rcx; unsigned int
0x1800202df  mov     r9d, 7; dwType
0x1800202e5  xor     r8d, r8d; Reserved
0x1800202e8  mov     rdx, r13; lpValueName
0x1800202eb  mov     rcx, [r12]; hKey
0x1800202ef  call    cs:__imp_RegSetValueExW
0x1800202f6  nop     dword ptr [rax+rax+00h]
0x1800202fb  mov     rcx, [rbp+38h]; this
0x1800202ff  test    eax, eax
0x180020301  jnz     short loc_180020331
0x180020303  lea     rcx, [rbp+Src]
0x180020307  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002030c  mov     rcx, [rbp+var_10]
0x180020310  xor     rcx, rsp; StackCookie
0x180020313  call    __security_check_cookie
0x180020318  mov     rbx, [rsp+60h+arg_10]
0x180020320  add     rsp, 60h
0x180020324  pop     r15
0x180020326  pop     r14
0x180020328  pop     r13
0x18002032a  pop     r12
0x18002032c  pop     rdi
0x18002032d  pop     rsi
0x18002032e  pop     rbp
0x18002032f  retn
0x180020331  mov     r9d, eax; char *
0x180020334  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18002033b  mov     edx, 353h; void *
0x180020340  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
