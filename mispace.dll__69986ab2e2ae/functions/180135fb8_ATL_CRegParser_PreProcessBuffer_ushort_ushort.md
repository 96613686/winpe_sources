# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180135fb8`
- end: `0x1801361f2`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `570`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18013640c`

## callees

- `0x180006350`
- `0x180133988`
- `0x180134440`
- `0x180135fb8`
- `0x180136ff8`
- `0x180137058`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801360e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801360e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180136039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013619f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180136039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013619f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180136051`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180136051`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013608f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180136140`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013616f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013608f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180136140`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18013616f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rax
  __int64 v19; // r8
  int v20; // ebx
  const WCHAR *i; // rax
  unsigned int v22; // ebx
  __int64 v23; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v25; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 v26[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  LODWORD(v23) = 0;
  if ( v7 < 100 )
    v7 = 1000;
  HIDWORD(v23) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_29:
    v22 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_30;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_26:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v23, v14, 1) )
      goto LABEL_33;
LABEL_27:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_29;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_26;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_32;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v22 = -2147467259;
    goto LABEL_30;
  }
  _o_wcsncpy_s(v26, 32, *(_QWORD *)this, (int)v17, v23);
  v18 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), v26);
  if ( !v18 )
  {
LABEL_32:
    v22 = -2147352567;
    goto LABEL_30;
  }
  v25 = 0;
  v19 = -1;
  do
    ++v19;
  while ( v18[v19] );
  v20 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v23, v18, v19);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
  if ( v20 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_27;
  }
LABEL_33:
  v22 = -2147024882;
LABEL_30:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x180135fb8  mov     [rsp-8+arg_8], rbx
0x180135fbd  mov     [rsp-8+arg_18], rsi
0x180135fc2  push    rbp
0x180135fc3  push    rdi
0x180135fc4  push    r12
0x180135fc6  push    r14
0x180135fc8  push    r15
0x180135fca  lea     rbp, [rsp-37h]
0x180135fcf  sub     rsp, 90h
0x180135fd6  mov     rax, cs:__security_cookie
0x180135fdd  xor     rax, rsp
0x180135fe0  mov     [rbp+57h+var_30], rax
0x180135fe4  xor     r15d, r15d
0x180135fe7  mov     r14, r8
0x180135fea  mov     rbx, rdx
0x180135fed  mov     rdi, rcx
0x180135ff0  test    rdx, rdx
0x180135ff3  jz      loc_1801361C4
0x180135ff9  test    r8, r8
0x180135ffc  jz      loc_1801361C4
0x180136002  mov     [r8], r15
0x180136005  or      rax, 0FFFFFFFFFFFFFFFFh
0x180136009  inc     rax
0x18013600c  cmp     [rdx+rax*2], r15w
0x180136011  jnz     short loc_180136009
0x180136013  add     eax, eax
0x180136015  mov     [rbp+57h+var_90], r15d
0x180136019  cmp     eax, 64h ; 'd'
0x18013601c  mov     ecx, 3E8h
0x180136021  cmovl   eax, ecx
0x180136024  mov     ecx, eax
0x180136026  mov     [rbp+57h+var_8C], eax
0x180136029  add     rcx, rcx
0x18013602c  mov     eax, 0FFFFFFFFh
0x180136031  cmp     rcx, rax
0x180136034  jbe     short loc_18013604F
0x180136036  mov     rcx, r15; pv
0x180136039  call    cs:__imp_CoTaskMemFree
0x180136040  nop     dword ptr [rax+rax+00h]
0x180136045  mov     eax, 8007000Eh
0x18013604a  jmp     loc_1801361C9
0x18013604f  mov     ecx, ecx; cb
0x180136051  call    cs:__imp_CoTaskMemAlloc
0x180136058  nop     dword ptr [rax+rax+00h]
0x18013605d  mov     [rbp+57h+pv], rax
0x180136061  mov     rcx, rax
0x180136064  test    rax, rax
0x180136067  jz      short loc_180136039
0x180136069  mov     [rax], r15w
0x18013606d  mov     [rdi], rbx
0x180136070  movzx   eax, word ptr [rbx]
0x180136073  test    ax, ax
0x180136076  jz      loc_180136191
0x18013607c  mov     r12d, 25h ; '%'
0x180136082  cmp     ax, r12w
0x180136086  jnz     loc_180136156
0x18013608c  mov     rcx, rbx; lpsz
0x18013608f  call    cs:__imp_CharNextW
0x180136096  nop     dword ptr [rax+rax+00h]
0x18013609b  mov     [rdi], rax
0x18013609e  cmp     [rax], r12w
0x1801360a2  jnz     short loc_1801360AC
0x1801360a4  mov     rdx, rax
0x1801360a7  jmp     loc_180136159
0x1801360ac  mov     edx, r12d; unsigned __int16
0x1801360af  mov     rcx, rax; lpsz
0x1801360b2  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1801360b7  mov     rsi, rax
0x1801360ba  test    rax, rax
0x1801360bd  jz      loc_1801361B6
0x1801360c3  mov     rcx, rax
0x1801360c6  sub     rcx, [rdi]
0x1801360c9  sar     rcx, 1
0x1801360cc  cmp     rcx, 1Fh
0x1801360d0  jg      loc_1801361AF
0x1801360d6  mov     r8, [rdi]
0x1801360d9  mov     edx, 20h ; ' '
0x1801360de  movsxd  r9, ecx
0x1801360e1  lea     rcx, [rbp+57h+var_70]
0x1801360e5  call    cs:__imp__o_wcsncpy_s
0x1801360ec  nop     dword ptr [rax+rax+00h]
0x1801360f1  mov     rcx, [rdi+8]; this
0x1801360f5  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x1801360f9  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x1801360fe  test    rax, rax
0x180136101  jz      loc_1801361B6
0x180136107  mov     [rbp+57h+var_80], r15
0x18013610b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18013610f  inc     r8; int
0x180136112  cmp     [rax+r8*2], r15w
0x180136117  jnz     short loc_18013610F
0x180136119  mov     rdx, rax; unsigned __int16 *
0x18013611c  lea     rcx, [rbp+57h+var_90]; this
0x180136120  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180136125  lea     rcx, [rbp+57h+var_80]
0x180136129  mov     ebx, eax
0x18013612b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180136130  test    ebx, ebx
0x180136132  jz      loc_1801361BD
0x180136138  mov     rax, [rdi]
0x18013613b  jmp     short loc_18013614F
0x18013613d  mov     rcx, rax; lpsz
0x180136140  call    cs:__imp_CharNextW
0x180136147  nop     dword ptr [rax+rax+00h]
0x18013614c  mov     [rdi], rax
0x18013614f  cmp     rax, rsi
0x180136152  jnz     short loc_18013613D
0x180136154  jmp     short loc_18013616C
0x180136156  mov     rdx, rbx; unsigned __int16 *
0x180136159  mov     r8d, 1; int
0x18013615f  lea     rcx, [rbp+57h+var_90]; this
0x180136163  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180136168  test    eax, eax
0x18013616a  jz      short loc_1801361BD
0x18013616c  mov     rcx, [rdi]; lpsz
0x18013616f  call    cs:__imp_CharNextW
0x180136176  nop     dword ptr [rax+rax+00h]
0x18013617b  mov     rbx, rax
0x18013617e  mov     [rdi], rax
0x180136181  movzx   eax, word ptr [rax]
0x180136184  test    ax, ax
0x180136187  jnz     loc_180136082
0x18013618d  mov     rcx, [rbp+57h+pv]
0x180136191  mov     ebx, r15d
0x180136194  mov     [rbp+57h+pv], r15
0x180136198  mov     [r14], rcx
0x18013619b  mov     rcx, [rbp+57h+pv]; pv
0x18013619f  call    cs:__imp_CoTaskMemFree
0x1801361a6  nop     dword ptr [rax+rax+00h]
0x1801361ab  mov     eax, ebx
0x1801361ad  jmp     short loc_1801361C9
0x1801361af  mov     ebx, 80004005h
0x1801361b4  jmp     short loc_18013619B
0x1801361b6  mov     ebx, 80020009h
0x1801361bb  jmp     short loc_18013619B
0x1801361bd  mov     ebx, 8007000Eh
0x1801361c2  jmp     short loc_18013619B
0x1801361c4  mov     eax, 80004003h
0x1801361c9  mov     rcx, [rbp+57h+var_30]
0x1801361cd  xor     rcx, rsp; StackCookie
0x1801361d0  call    __security_check_cookie
0x1801361d5  lea     r11, [rsp+0B0h+var_20]
0x1801361dd  mov     rbx, [r11+38h]
0x1801361e1  mov     rsi, [r11+48h]
0x1801361e5  mov     rsp, r11
0x1801361e8  pop     r15
0x1801361ea  pop     r14
0x1801361ec  pop     r12
0x1801361ee  pop     rdi
0x1801361ef  pop     rbp
0x1801361f0  retn
```
