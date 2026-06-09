# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000ca4c`
- end: `0x18000ccb0`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dddc`

## callees

- `0x180004078`
- `0x180006d38`
- `0x180006f14`
- `0x18000c30c`
- `0x18000ca4c`
- `0x18000f11c`
- `0x18002f3b0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000cb86`
- `msvcrt!wcsncpy_s` at `0x18000cb86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cb9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cb9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cbe7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cbe7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cb1c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cc2b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cc41`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cb1c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cc2b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cc41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cbbf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cbbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cad3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cad3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000caee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000caee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  errno_t v17; // eax
  const wchar_t *v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  const wchar_t *v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  _DWORD v27[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  _QWORD *v29; // [rsp+30h] [rbp-39h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

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
  v27[0] = 0;
  v27[1] = v7;
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
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = v14 - *this;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = wcsncpy_s(Destination, 0x20u, *this, (int)v16);
    ATL::AtlCrtErrorCheck(v17);
    v18 = this[1];
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
    v20 = v18 + 4;
    for ( i = 0; (signed int)i < *((_DWORD *)v20 + 4); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), Destination) )
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
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *this; j != v15; *this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*this);
    *this = v4;
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
0x18000ca4c  mov     [rsp-8+arg_8], rbx
0x18000ca51  push    rbp
0x18000ca52  push    rsi
0x18000ca53  push    rdi
0x18000ca54  push    r12
0x18000ca56  push    r13
0x18000ca58  push    r14
0x18000ca5a  push    r15
0x18000ca5c  lea     rbp, [rsp-27h]
0x18000ca61  sub     rsp, 90h
0x18000ca68  mov     rax, cs:__security_cookie
0x18000ca6f  xor     rax, rsp
0x18000ca72  mov     [rbp+57h+var_40], rax
0x18000ca76  mov     r15, r8
0x18000ca79  mov     rbx, rdx
0x18000ca7c  mov     rdi, rcx
0x18000ca7f  xor     r13d, r13d
0x18000ca82  test    rdx, rdx
0x18000ca85  jz      loc_18000CC84
0x18000ca8b  test    r8, r8
0x18000ca8e  jz      loc_18000CC84
0x18000ca94  mov     [r8], r13
0x18000ca97  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ca9b  inc     rax
0x18000ca9e  cmp     [rdx+rax*2], r13w
0x18000caa3  jnz     short loc_18000CA9B
0x18000caa5  add     eax, eax
0x18000caa7  mov     ecx, 3E8h
0x18000caac  cmp     eax, 64h ; 'd'
0x18000caaf  cmovl   eax, ecx
0x18000cab2  mov     [rbp+57h+var_A0], r13d
0x18000cab6  mov     [rbp+57h+var_9C], eax
0x18000cab9  mov     ecx, eax
0x18000cabb  add     rcx, rcx
0x18000cabe  mov     eax, 0FFFFFFFFh
0x18000cac3  cmp     rcx, rax
0x18000cac6  jbe     short loc_18000CAD1
0x18000cac8  mov     rax, r13
0x18000cacb  mov     [rbp+57h+pv], r13
0x18000cacf  jmp     short loc_18000CAE6
0x18000cad1  mov     ecx, ecx; cb
0x18000cad3  call    cs:__imp_CoTaskMemAlloc
0x18000cad9  mov     [rbp+57h+pv], rax
0x18000cadd  test    rax, rax
0x18000cae0  jz      short loc_18000CAE6
0x18000cae2  mov     [rax], r13w
0x18000cae6  test    rax, rax
0x18000cae9  jnz     short loc_18000CAFE
0x18000caeb  mov     rcx, rax; pv
0x18000caee  call    cs:__imp_CoTaskMemFree
0x18000caf4  mov     eax, 8007000Eh
0x18000caf9  jmp     loc_18000CC89
0x18000cafe  mov     [rdi], rbx
0x18000cb01  mov     esi, 25h ; '%'
0x18000cb06  cmp     [rbx], r13w
0x18000cb0a  jz      loc_18000CC68
0x18000cb10  cmp     [rbx], si
0x18000cb13  jnz     loc_18000CC52
0x18000cb19  mov     rcx, rbx; lpsz
0x18000cb1c  call    cs:__imp_CharNextW
0x18000cb22  mov     [rdi], rax
0x18000cb25  cmp     [rax], si
0x18000cb28  jnz     short loc_18000CB4E
0x18000cb2a  mov     rdx, rax; unsigned __int16 *
0x18000cb2d  mov     r8d, 1; int
0x18000cb33  lea     rcx, [rbp+57h+var_A0]; this
0x18000cb37  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000cb3c  test    eax, eax
0x18000cb3e  jnz     loc_18000CC3E
0x18000cb44  mov     ebx, 8007000Eh
0x18000cb49  jmp     loc_18000CC76
0x18000cb4e  mov     edx, esi; unsigned __int16
0x18000cb50  mov     rcx, rax; lpsz
0x18000cb53  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000cb58  mov     rsi, rax
0x18000cb5b  test    rax, rax
0x18000cb5e  jz      loc_18000CC61
0x18000cb64  mov     rcx, rax
0x18000cb67  sub     rcx, [rdi]
0x18000cb6a  sar     rcx, 1
0x18000cb6d  cmp     rcx, 1Fh
0x18000cb71  jg      loc_18000CC5A
0x18000cb77  movsxd  r9, ecx; MaxCount
0x18000cb7a  mov     r8, [rdi]; Source
0x18000cb7d  mov     edx, 20h ; ' '; SizeInWords
0x18000cb82  lea     rcx, [rbp+57h+Destination]; Destination
0x18000cb86  call    cs:__imp_wcsncpy_s
0x18000cb8c  mov     ecx, eax; int
0x18000cb8e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000cb93  mov     rbx, [rdi+8]
0x18000cb97  lea     r12, [rbx+20h]
0x18000cb9b  mov     rcx, r12; lpCriticalSection
0x18000cb9e  call    cs:__imp_EnterCriticalSection
0x18000cba4  lea     r14, [rbx+8]
0x18000cba8  mov     ebx, r13d
0x18000cbab  cmp     ebx, [r14+10h]
0x18000cbaf  jge     short loc_18000CBE1
0x18000cbb1  movsxd  rax, ebx
0x18000cbb4  mov     rcx, [r14]
0x18000cbb7  lea     rdx, [rbp+57h+Destination]; lpString2
0x18000cbbb  mov     rcx, [rcx+rax*8]; lpString1
0x18000cbbf  call    cs:__imp_lstrcmpiW
0x18000cbc5  test    eax, eax
0x18000cbc7  jz      short loc_18000CBCD
0x18000cbc9  inc     ebx
0x18000cbcb  jmp     short loc_18000CBAB
0x18000cbcd  cmp     ebx, 0FFFFFFFFh
0x18000cbd0  jz      short loc_18000CBE1
0x18000cbd2  mov     edx, ebx
0x18000cbd4  mov     rcx, r14
0x18000cbd7  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000cbdc  mov     rbx, [rax]
0x18000cbdf  jmp     short loc_18000CBE4
0x18000cbe1  mov     rbx, r13
0x18000cbe4  mov     rcx, r12; lpCriticalSection
0x18000cbe7  call    cs:__imp_LeaveCriticalSection
0x18000cbed  test    rbx, rbx
0x18000cbf0  jz      short loc_18000CC61
0x18000cbf2  mov     [rbp+57h+var_90], r13
0x18000cbf6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000cbfa  inc     r8; int
0x18000cbfd  cmp     [rbx+r8*2], r13w
0x18000cc02  jnz     short loc_18000CBFA
0x18000cc04  mov     rdx, rbx; unsigned __int16 *
0x18000cc07  lea     rcx, [rbp+57h+var_A0]; this
0x18000cc0b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000cc10  mov     ebx, eax
0x18000cc12  lea     rcx, [rbp+57h+var_90]
0x18000cc16  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000cc1b  test    ebx, ebx
0x18000cc1d  jz      loc_18000CB44
0x18000cc23  mov     rax, [rdi]
0x18000cc26  jmp     short loc_18000CC34
0x18000cc28  mov     rcx, rax; lpsz
0x18000cc2b  call    cs:__imp_CharNextW
0x18000cc31  mov     [rdi], rax
0x18000cc34  cmp     rax, rsi
0x18000cc37  jnz     short loc_18000CC28
0x18000cc39  mov     esi, 25h ; '%'
0x18000cc3e  mov     rcx, [rdi]; lpsz
0x18000cc41  call    cs:__imp_CharNextW
0x18000cc47  mov     rbx, rax
0x18000cc4a  mov     [rdi], rax
0x18000cc4d  jmp     loc_18000CB06
0x18000cc52  mov     rdx, rbx
0x18000cc55  jmp     loc_18000CB2D
0x18000cc5a  mov     ebx, 80004005h
0x18000cc5f  jmp     short loc_18000CC76
0x18000cc61  mov     ebx, 80020009h
0x18000cc66  jmp     short loc_18000CC76
0x18000cc68  mov     ebx, r13d
0x18000cc6b  mov     rcx, [rbp+57h+pv]
0x18000cc6f  mov     [rbp+57h+pv], r13
0x18000cc73  mov     [r15], rcx
0x18000cc76  mov     rcx, [rbp+57h+pv]; pv
0x18000cc7a  call    cs:__imp_CoTaskMemFree
0x18000cc80  mov     eax, ebx
0x18000cc82  jmp     short loc_18000CC89
0x18000cc84  mov     eax, 80004003h
0x18000cc89  mov     rcx, [rbp+57h+var_40]
0x18000cc8d  xor     rcx, rsp; StackCookie
0x18000cc90  call    __security_check_cookie
0x18000cc95  mov     rbx, [rsp+0C0h+arg_8]
0x18000cc9d  add     rsp, 90h
0x18000cca4  pop     r15
0x18000cca6  pop     r14
0x18000cca8  pop     r13
0x18000ccaa  pop     r12
0x18000ccac  pop     rdi
0x18000ccad  pop     rsi
0x18000ccae  pop     rbp
0x18000ccaf  retn
```
