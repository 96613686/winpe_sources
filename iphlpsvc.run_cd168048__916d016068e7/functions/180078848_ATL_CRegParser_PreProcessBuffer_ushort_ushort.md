# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180078848`
- end: `0x180078ae5`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `669`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180078c3c`

## callees

- `0x18004b630`
- `0x180077534`
- `0x180077fd8`
- `0x180078114`
- `0x18007857c`
- `0x180078638`
- `0x180078848`
- `0x1800797f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180078995`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180078995`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078a01`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078925`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078a4c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078a68`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078925`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078a4c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078a68`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800789d3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800789d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800788f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078aa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800788f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078aa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800788cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800788cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v27) = 0;
  HIDWORD(v27) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, v27);
    ATL::AtlCrtErrorCheck(v17);
    v18 = *((_QWORD *)this + 1);
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 32);
    ATL::CComSafeDeleteCriticalSection::Lock((ATL::CComSafeDeleteCriticalSection *)(v18 + 32));
    v20 = v18 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v20 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v22 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v20,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v22 = 0;
LABEL_29:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_39:
      v13 = -2147352567;
      goto LABEL_41;
    }
    v29 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x180078848  mov     [rsp-8+arg_8], rbx
0x18007884d  push    rbp
0x18007884e  push    rsi
0x18007884f  push    rdi
0x180078850  push    r12
0x180078852  push    r13
0x180078854  push    r14
0x180078856  push    r15
0x180078858  lea     rbp, [rsp-27h]
0x18007885d  sub     rsp, 90h
0x180078864  mov     rax, cs:__security_cookie
0x18007886b  xor     rax, rsp
0x18007886e  mov     [rbp+57h+var_40], rax
0x180078872  mov     r15, r8
0x180078875  mov     rbx, rdx
0x180078878  mov     rdi, rcx
0x18007887b  xor     r13d, r13d
0x18007887e  test    rdx, rdx
0x180078881  jz      loc_180078AB8
0x180078887  test    r8, r8
0x18007888a  jz      loc_180078AB8
0x180078890  mov     [r8], r13
0x180078893  or      rax, 0FFFFFFFFFFFFFFFFh
0x180078897  inc     rax
0x18007889a  cmp     [rdx+rax*2], r13w
0x18007889f  jnz     short loc_180078897
0x1800788a1  add     eax, eax
0x1800788a3  mov     ecx, 3E8h
0x1800788a8  cmp     eax, 64h ; 'd'
0x1800788ab  cmovl   eax, ecx
0x1800788ae  mov     [rbp+57h+var_A0], r13d
0x1800788b2  mov     [rbp+57h+var_9C], eax
0x1800788b5  mov     ecx, eax
0x1800788b7  add     rcx, rcx
0x1800788ba  mov     eax, 0FFFFFFFFh
0x1800788bf  cmp     rcx, rax
0x1800788c2  jbe     short loc_1800788CD
0x1800788c4  mov     rax, r13
0x1800788c7  mov     [rbp+57h+pv], r13
0x1800788cb  jmp     short loc_1800788E8
0x1800788cd  mov     ecx, ecx; cb
0x1800788cf  call    cs:__imp_CoTaskMemAlloc
0x1800788d6  nop     dword ptr [rax+rax+00h]
0x1800788db  mov     [rbp+57h+pv], rax
0x1800788df  test    rax, rax
0x1800788e2  jz      short loc_1800788E8
0x1800788e4  mov     [rax], r13w
0x1800788e8  test    rax, rax
0x1800788eb  jnz     short loc_180078907
0x1800788ed  mov     rcx, rax; pv
0x1800788f0  call    cs:__imp_CoTaskMemFree
0x1800788f7  nop     dword ptr [rax+rax+00h]
0x1800788fc  nop
0x1800788fd  mov     eax, 8007000Eh
0x180078902  jmp     loc_180078ABD
0x180078907  mov     [rdi], rbx
0x18007890a  mov     esi, 25h ; '%'
0x18007890f  cmp     [rbx], r13w
0x180078913  jz      loc_180078A95
0x180078919  cmp     [rbx], si
0x18007891c  jnz     loc_180078A7F
0x180078922  mov     rcx, rbx; lpsz
0x180078925  call    cs:__imp_CharNextW
0x18007892c  nop     dword ptr [rax+rax+00h]
0x180078931  mov     [rdi], rax
0x180078934  cmp     [rax], si
0x180078937  jnz     short loc_18007895D
0x180078939  mov     rdx, rax; unsigned __int16 *
0x18007893c  mov     r8d, 1; int
0x180078942  lea     rcx, [rbp+57h+var_A0]; this
0x180078946  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18007894b  test    eax, eax
0x18007894d  jnz     loc_180078A65
0x180078953  mov     ebx, 8007000Eh
0x180078958  jmp     loc_180078AA3
0x18007895d  mov     edx, esi; unsigned __int16
0x18007895f  mov     rcx, rax; lpsz
0x180078962  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180078967  mov     rsi, rax
0x18007896a  test    rax, rax
0x18007896d  jz      loc_180078A8E
0x180078973  mov     rcx, rax
0x180078976  sub     rcx, [rdi]
0x180078979  sar     rcx, 1
0x18007897c  cmp     rcx, 1Fh
0x180078980  jg      loc_180078A87
0x180078986  movsxd  r9, ecx
0x180078989  mov     r8, [rdi]
0x18007898c  mov     edx, 20h ; ' '
0x180078991  lea     rcx, [rbp+57h+String2]
0x180078995  call    cs:__imp__o_wcsncpy_s
0x18007899c  nop     dword ptr [rax+rax+00h]
0x1800789a1  mov     ecx, eax; int
0x1800789a3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800789a8  mov     rbx, [rdi+8]
0x1800789ac  lea     r12, [rbx+20h]
0x1800789b0  mov     rcx, r12; this
0x1800789b3  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x1800789b8  lea     r14, [rbx+8]
0x1800789bc  mov     ebx, r13d
0x1800789bf  cmp     ebx, [r14+10h]
0x1800789c3  jge     short loc_1800789FB
0x1800789c5  movsxd  rax, ebx
0x1800789c8  mov     rcx, [r14]
0x1800789cb  lea     rdx, [rbp+57h+String2]; lpString2
0x1800789cf  mov     rcx, [rcx+rax*8]; lpString1
0x1800789d3  call    cs:__imp_lstrcmpiW
0x1800789da  nop     dword ptr [rax+rax+00h]
0x1800789df  test    eax, eax
0x1800789e1  jz      short loc_1800789E7
0x1800789e3  inc     ebx
0x1800789e5  jmp     short loc_1800789BF
0x1800789e7  cmp     ebx, 0FFFFFFFFh
0x1800789ea  jz      short loc_1800789FB
0x1800789ec  mov     edx, ebx
0x1800789ee  mov     rcx, r14
0x1800789f1  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1800789f6  mov     rbx, [rax]
0x1800789f9  jmp     short loc_1800789FE
0x1800789fb  mov     rbx, r13
0x1800789fe  mov     rcx, r12; lpCriticalSection
0x180078a01  call    cs:__imp_LeaveCriticalSection
0x180078a08  nop     dword ptr [rax+rax+00h]
0x180078a0d  nop
0x180078a0e  test    rbx, rbx
0x180078a11  jz      short loc_180078A8E
0x180078a13  mov     [rbp+57h+var_90], r13
0x180078a17  or      r8, 0FFFFFFFFFFFFFFFFh
0x180078a1b  inc     r8; int
0x180078a1e  cmp     [rbx+r8*2], r13w
0x180078a23  jnz     short loc_180078A1B
0x180078a25  mov     rdx, rbx; unsigned __int16 *
0x180078a28  lea     rcx, [rbp+57h+var_A0]; this
0x180078a2c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180078a31  mov     ebx, eax
0x180078a33  lea     rcx, [rbp+57h+var_90]
0x180078a37  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180078a3c  test    ebx, ebx
0x180078a3e  jz      loc_180078953
0x180078a44  mov     rax, [rdi]
0x180078a47  jmp     short loc_180078A5B
0x180078a49  mov     rcx, rax; lpsz
0x180078a4c  call    cs:__imp_CharNextW
0x180078a53  nop     dword ptr [rax+rax+00h]
0x180078a58  mov     [rdi], rax
0x180078a5b  cmp     rax, rsi
0x180078a5e  jnz     short loc_180078A49
0x180078a60  mov     esi, 25h ; '%'
0x180078a65  mov     rcx, [rdi]; lpsz
0x180078a68  call    cs:__imp_CharNextW
0x180078a6f  nop     dword ptr [rax+rax+00h]
0x180078a74  mov     rbx, rax
0x180078a77  mov     [rdi], rax
0x180078a7a  jmp     loc_18007890F
0x180078a7f  mov     rdx, rbx
0x180078a82  jmp     loc_18007893C
0x180078a87  mov     ebx, 80004005h
0x180078a8c  jmp     short loc_180078AA3
0x180078a8e  mov     ebx, 80020009h
0x180078a93  jmp     short loc_180078AA3
0x180078a95  mov     ebx, r13d
0x180078a98  mov     rcx, [rbp+57h+pv]
0x180078a9c  mov     [rbp+57h+pv], r13
0x180078aa0  mov     [r15], rcx
0x180078aa3  mov     rcx, [rbp+57h+pv]; pv
0x180078aa7  call    cs:__imp_CoTaskMemFree
0x180078aae  nop     dword ptr [rax+rax+00h]
0x180078ab3  nop
0x180078ab4  mov     eax, ebx
0x180078ab6  jmp     short loc_180078ABD
0x180078ab8  mov     eax, 80004003h
0x180078abd  mov     rcx, [rbp+57h+var_40]
0x180078ac1  xor     rcx, rsp; StackCookie
0x180078ac4  call    __security_check_cookie
0x180078ac9  mov     rbx, [rsp+0C0h+arg_8]
0x180078ad1  add     rsp, 90h
0x180078ad8  pop     r15
0x180078ada  pop     r14
0x180078adc  pop     r13
0x180078ade  pop     r12
0x180078ae0  pop     rdi
0x180078ae1  pop     rsi
0x180078ae2  pop     rbp
0x180078ae3  retn
```
