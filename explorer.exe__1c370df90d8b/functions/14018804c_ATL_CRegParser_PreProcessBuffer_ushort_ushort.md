# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x14018804c`
- end: `0x1401882b9`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1401892a0`

## callees

- `0x1401040e0`
- `0x1401328bc`
- `0x14014cc6c`
- `0x14015ca30`
- `0x14015cc5c`
- `0x14016edbc`
- `0x14018804c`
- `0x1401935fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14018818f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14018818f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401881f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401881f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401881a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401881a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401880f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140188283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401880f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140188283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401880dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401880dc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1401881c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1401881c8`
- `USER32!CharNextW` at `0x140188125`
- `USER32!CharNextW` at `0x140188234`
- `USER32!CharNextW` at `0x14018824a`
- `USER32!CharNextW` at `0x140188125`
- `USER32!CharNextW` at `0x140188234`
- `USER32!CharNextW` at `0x14018824a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  __int64 v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v25; // rcx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v27[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned int)(2 * v6);
  if ( (int)v7 < 100 )
    v7 = 1000;
  v27[0] = 0;
  v27[1] = v7;
  LODWORD(cb) = 0;
  if ( (int)ATL::AtlMultiply<unsigned long>(&cb, v7, 2) >= 0 )
  {
    v8 = CoTaskMemAlloc((unsigned int)cb);
    pv = v8;
    if ( v8 )
      *v8 = 0;
  }
  else
  {
    v8 = 0;
    pv = 0;
  }
  if ( !v8 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v11 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v11, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v10 = CharNextW(v4);
    *(_QWORD *)this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_18;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_39;
    v15 = ((__int64)v13 - *(_QWORD *)this) >> 1;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_41;
    }
    v16 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = *((_QWORD *)this + 1);
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 32));
    v19 = v17 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v19 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v19 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v21 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v19,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v21 = 0;
LABEL_29:
    LeaveCriticalSection(v18);
    if ( !v21 )
    {
LABEL_39:
      v12 = -2147352567;
      goto LABEL_41;
    }
    cb = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v23 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v21, v22);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
    if ( !v23 )
    {
LABEL_19:
      v12 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v14; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v12 = 0;
  v25 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v25;
LABEL_41:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x14018804c  mov     [rsp-8+arg_8], rbx
0x140188051  push    rbp
0x140188052  push    rsi
0x140188053  push    rdi
0x140188054  push    r12
0x140188056  push    r13
0x140188058  push    r14
0x14018805a  push    r15
0x14018805c  lea     rbp, [rsp-27h]
0x140188061  sub     rsp, 90h
0x140188068  mov     rax, cs:__security_cookie
0x14018806f  xor     rax, rsp
0x140188072  mov     [rbp+57h+var_40], rax
0x140188076  mov     r15, r8
0x140188079  mov     rbx, rdx
0x14018807c  mov     rdi, rcx
0x14018807f  xor     r13d, r13d
0x140188082  test    rdx, rdx
0x140188085  jz      loc_14018828D
0x14018808b  test    r8, r8
0x14018808e  jz      loc_14018828D
0x140188094  mov     [r8], r13
0x140188097  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14018809b  inc     rdx
0x14018809e  cmp     [rbx+rdx*2], r13w
0x1401880a3  jnz     short loc_14018809B
0x1401880a5  add     edx, edx
0x1401880a7  mov     eax, 3E8h
0x1401880ac  cmp     edx, 64h ; 'd'
0x1401880af  cmovl   edx, eax
0x1401880b2  mov     [rbp+57h+var_98], r13d
0x1401880b6  mov     [rbp+57h+var_94], edx
0x1401880b9  mov     dword ptr [rbp+57h+cb], r13d
0x1401880bd  mov     r8d, 2
0x1401880c3  lea     rcx, [rbp+57h+cb]
0x1401880c7  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x1401880cc  test    eax, eax
0x1401880ce  jns     short loc_1401880D9
0x1401880d0  mov     rax, r13
0x1401880d3  mov     [rbp+57h+pv], r13
0x1401880d7  jmp     short loc_1401880EF
0x1401880d9  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x1401880dc  call    cs:__imp_CoTaskMemAlloc
0x1401880e2  mov     [rbp+57h+pv], rax
0x1401880e6  test    rax, rax
0x1401880e9  jz      short loc_1401880EF
0x1401880eb  mov     [rax], r13w
0x1401880ef  test    rax, rax
0x1401880f2  jnz     short loc_140188107
0x1401880f4  mov     rcx, rax; pv
0x1401880f7  call    cs:__imp_CoTaskMemFree
0x1401880fd  mov     eax, 8007000Eh
0x140188102  jmp     loc_140188292
0x140188107  mov     [rdi], rbx
0x14018810a  mov     esi, 25h ; '%'
0x14018810f  cmp     [rbx], r13w
0x140188113  jz      loc_140188271
0x140188119  cmp     [rbx], si
0x14018811c  jnz     loc_14018825B
0x140188122  mov     rcx, rbx; lpsz
0x140188125  call    cs:__imp_CharNextW
0x14018812b  mov     [rdi], rax
0x14018812e  cmp     [rax], si
0x140188131  jnz     short loc_140188157
0x140188133  mov     rdx, rax; unsigned __int16 *
0x140188136  mov     r8d, 1; int
0x14018813c  lea     rcx, [rbp+57h+var_98]; this
0x140188140  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140188145  test    eax, eax
0x140188147  jnz     loc_140188247
0x14018814d  mov     ebx, 8007000Eh
0x140188152  jmp     loc_14018827F
0x140188157  mov     edx, esi; unsigned __int16
0x140188159  mov     rcx, rax; lpsz
0x14018815c  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x140188161  mov     rsi, rax
0x140188164  test    rax, rax
0x140188167  jz      loc_14018826A
0x14018816d  mov     rcx, rax
0x140188170  sub     rcx, [rdi]
0x140188173  sar     rcx, 1
0x140188176  cmp     rcx, 1Fh
0x14018817a  jg      loc_140188263
0x140188180  movsxd  r9, ecx
0x140188183  mov     r8, [rdi]
0x140188186  mov     edx, 20h ; ' '
0x14018818b  lea     rcx, [rbp+57h+String2]
0x14018818f  call    cs:__imp__o_wcsncpy_s
0x140188195  mov     ecx, eax; int
0x140188197  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14018819c  mov     rbx, [rdi+8]
0x1401881a0  lea     r12, [rbx+20h]
0x1401881a4  mov     rcx, r12; lpCriticalSection
0x1401881a7  call    cs:__imp_EnterCriticalSection
0x1401881ad  lea     r14, [rbx+8]
0x1401881b1  mov     ebx, r13d
0x1401881b4  cmp     ebx, [r14+10h]
0x1401881b8  jge     short loc_1401881EA
0x1401881ba  movsxd  rax, ebx
0x1401881bd  mov     rcx, [r14]
0x1401881c0  lea     rdx, [rbp+57h+String2]; lpString2
0x1401881c4  mov     rcx, [rcx+rax*8]; lpString1
0x1401881c8  call    cs:__imp_lstrcmpiW
0x1401881ce  test    eax, eax
0x1401881d0  jz      short loc_1401881D6
0x1401881d2  inc     ebx
0x1401881d4  jmp     short loc_1401881B4
0x1401881d6  cmp     ebx, 0FFFFFFFFh
0x1401881d9  jz      short loc_1401881EA
0x1401881db  mov     edx, ebx
0x1401881dd  mov     rcx, r14
0x1401881e0  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1401881e5  mov     rbx, [rax]
0x1401881e8  jmp     short loc_1401881ED
0x1401881ea  mov     rbx, r13
0x1401881ed  mov     rcx, r12; lpCriticalSection
0x1401881f0  call    cs:__imp_LeaveCriticalSection
0x1401881f6  test    rbx, rbx
0x1401881f9  jz      short loc_14018826A
0x1401881fb  mov     [rbp+57h+cb], r13
0x1401881ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x140188203  inc     r8; int
0x140188206  cmp     [rbx+r8*2], r13w
0x14018820b  jnz     short loc_140188203
0x14018820d  mov     rdx, rbx; unsigned __int16 *
0x140188210  lea     rcx, [rbp+57h+var_98]; this
0x140188214  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140188219  mov     ebx, eax
0x14018821b  lea     rcx, [rbp+57h+cb]
0x14018821f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140188224  test    ebx, ebx
0x140188226  jz      loc_14018814D
0x14018822c  mov     rax, [rdi]
0x14018822f  jmp     short loc_14018823D
0x140188231  mov     rcx, rax; lpsz
0x140188234  call    cs:__imp_CharNextW
0x14018823a  mov     [rdi], rax
0x14018823d  cmp     rax, rsi
0x140188240  jnz     short loc_140188231
0x140188242  mov     esi, 25h ; '%'
0x140188247  mov     rcx, [rdi]; lpsz
0x14018824a  call    cs:__imp_CharNextW
0x140188250  mov     rbx, rax
0x140188253  mov     [rdi], rax
0x140188256  jmp     loc_14018810F
0x14018825b  mov     rdx, rbx
0x14018825e  jmp     loc_140188136
0x140188263  mov     ebx, 80004005h
0x140188268  jmp     short loc_14018827F
0x14018826a  mov     ebx, 80020009h
0x14018826f  jmp     short loc_14018827F
0x140188271  mov     ebx, r13d
0x140188274  mov     rcx, [rbp+57h+pv]
0x140188278  mov     [rbp+57h+pv], r13
0x14018827c  mov     [r15], rcx
0x14018827f  mov     rcx, [rbp+57h+pv]; pv
0x140188283  call    cs:__imp_CoTaskMemFree
0x140188289  mov     eax, ebx
0x14018828b  jmp     short loc_140188292
0x14018828d  mov     eax, 80004003h
0x140188292  mov     rcx, [rbp+57h+var_40]
0x140188296  xor     rcx, rsp; StackCookie
0x140188299  call    __security_check_cookie
0x14018829e  mov     rbx, [rsp+0C0h+arg_8]
0x1401882a6  add     rsp, 90h
0x1401882ad  pop     r15
0x1401882af  pop     r14
0x1401882b1  pop     r13
0x1401882b3  pop     r12
0x1401882b5  pop     rdi
0x1401882b6  pop     rsi
0x1401882b7  pop     rbp
0x1401882b8  retn
```
