# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180117604`
- end: `0x18011789a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `662`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801180dc`

## callees

- `0x180110ed0`
- `0x180112754`
- `0x180114608`
- `0x180114858`
- `0x1801171f4`
- `0x180117604`
- `0x18011972c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180117745`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180117745`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801177b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801177b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180117763`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180117763`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801176d5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180117802`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18011781e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801176d5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180117802`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18011781e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18011778a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18011778a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011769e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011769e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117686`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011785d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117686`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011785d`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, unsigned __int16 *a2, LPVOID *a3)
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
  __int64 v26; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h] BYREF
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
  LODWORD(v26) = 0;
  if ( v7 < 100 )
    v7 = 1000;
  HIDWORD(v26) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v9 = CoTaskMemAlloc((unsigned int)v8);
  pv = v9;
  if ( !v9 )
    goto LABEL_9;
  *v9 = 0;
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_16:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v12, 1) )
        goto LABEL_17;
      goto LABEL_34;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_16;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_37;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_39;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, v26);
    ATL::AtlCrtErrorCheck(v17);
    v18 = *((_QWORD *)this + 1);
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
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
          goto LABEL_27;
        }
        break;
      }
    }
    v22 = 0;
LABEL_27:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_37:
      v13 = -2147352567;
      goto LABEL_39;
    }
    v28 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v28);
    if ( !v24 )
    {
LABEL_17:
      v13 = -2147024882;
      goto LABEL_39;
    }
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_34:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  *a3 = pv;
  pv = 0;
LABEL_39:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x180117604  mov     [rsp-8+arg_8], rbx
0x180117609  push    rbp
0x18011760a  push    rsi
0x18011760b  push    rdi
0x18011760c  push    r12
0x18011760e  push    r13
0x180117610  push    r14
0x180117612  push    r15
0x180117614  lea     rbp, [rsp-27h]
0x180117619  sub     rsp, 90h
0x180117620  mov     rax, cs:__security_cookie
0x180117627  xor     rax, rsp
0x18011762a  mov     [rbp+57h+var_40], rax
0x18011762e  xor     r13d, r13d
0x180117631  mov     r15, r8
0x180117634  mov     rbx, rdx
0x180117637  mov     rdi, rcx
0x18011763a  test    rdx, rdx
0x18011763d  jz      loc_18011786D
0x180117643  test    r8, r8
0x180117646  jz      loc_18011786D
0x18011764c  mov     [r8], r13
0x18011764f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180117653  inc     rax
0x180117656  cmp     [rdx+rax*2], r13w
0x18011765b  jnz     short loc_180117653
0x18011765d  add     eax, eax
0x18011765f  mov     [rbp+57h+var_A0], r13d
0x180117663  cmp     eax, 64h ; 'd'
0x180117666  mov     ecx, 3E8h
0x18011766b  cmovl   eax, ecx
0x18011766e  mov     ecx, eax
0x180117670  mov     [rbp+57h+var_9C], eax
0x180117673  add     rcx, rcx
0x180117676  mov     eax, 0FFFFFFFFh
0x18011767b  cmp     rcx, rax
0x18011767e  jbe     short loc_18011769C
0x180117680  mov     rax, r13
0x180117683  mov     rcx, rax; pv
0x180117686  call    cs:__imp_CoTaskMemFree
0x18011768d  nop     dword ptr [rax+rax+00h]
0x180117692  mov     eax, 8007000Eh
0x180117697  jmp     loc_180117872
0x18011769c  mov     ecx, ecx; cb
0x18011769e  call    cs:__imp_CoTaskMemAlloc
0x1801176a5  nop     dword ptr [rax+rax+00h]
0x1801176aa  mov     [rbp+57h+pv], rax
0x1801176ae  test    rax, rax
0x1801176b1  jz      short loc_180117683
0x1801176b3  mov     [rax], r13w
0x1801176b7  mov     esi, 25h ; '%'
0x1801176bc  mov     [rdi], rbx
0x1801176bf  cmp     [rbx], r13w
0x1801176c3  jz      loc_18011784B
0x1801176c9  cmp     [rbx], si
0x1801176cc  jnz     loc_180117835
0x1801176d2  mov     rcx, rbx; lpsz
0x1801176d5  call    cs:__imp_CharNextW
0x1801176dc  nop     dword ptr [rax+rax+00h]
0x1801176e1  mov     [rdi], rax
0x1801176e4  cmp     [rax], si
0x1801176e7  jnz     short loc_18011770D
0x1801176e9  mov     rdx, rax; unsigned __int16 *
0x1801176ec  mov     r8d, 1; int
0x1801176f2  lea     rcx, [rbp+57h+var_A0]; this
0x1801176f6  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1801176fb  test    eax, eax
0x1801176fd  jnz     loc_18011781B
0x180117703  mov     ebx, 8007000Eh
0x180117708  jmp     loc_180117859
0x18011770d  mov     edx, esi; unsigned __int16
0x18011770f  mov     rcx, rax; lpsz
0x180117712  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180117717  mov     rsi, rax
0x18011771a  test    rax, rax
0x18011771d  jz      loc_180117844
0x180117723  mov     rcx, rax
0x180117726  sub     rcx, [rdi]
0x180117729  sar     rcx, 1
0x18011772c  cmp     rcx, 1Fh
0x180117730  jg      loc_18011783D
0x180117736  mov     r8, [rdi]
0x180117739  mov     edx, 20h ; ' '
0x18011773e  movsxd  r9, ecx
0x180117741  lea     rcx, [rbp+57h+String2]
0x180117745  call    cs:__imp__o_wcsncpy_s
0x18011774c  nop     dword ptr [rax+rax+00h]
0x180117751  mov     ecx, eax; int
0x180117753  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180117758  mov     rbx, [rdi+8]
0x18011775c  lea     r12, [rbx+20h]
0x180117760  mov     rcx, r12; lpCriticalSection
0x180117763  call    cs:__imp_EnterCriticalSection
0x18011776a  nop     dword ptr [rax+rax+00h]
0x18011776f  lea     r14, [rbx+8]
0x180117773  mov     ebx, r13d
0x180117776  cmp     ebx, [r14+10h]
0x18011777a  jge     short loc_1801177B2
0x18011777c  mov     rcx, [r14]
0x18011777f  lea     rdx, [rbp+57h+String2]; lpString2
0x180117783  movsxd  rax, ebx
0x180117786  mov     rcx, [rcx+rax*8]; lpString1
0x18011778a  call    cs:__imp_lstrcmpiW
0x180117791  nop     dword ptr [rax+rax+00h]
0x180117796  test    eax, eax
0x180117798  jz      short loc_18011779E
0x18011779a  inc     ebx
0x18011779c  jmp     short loc_180117776
0x18011779e  cmp     ebx, 0FFFFFFFFh
0x1801177a1  jz      short loc_1801177B2
0x1801177a3  mov     edx, ebx
0x1801177a5  mov     rcx, r14
0x1801177a8  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1801177ad  mov     rbx, [rax]
0x1801177b0  jmp     short loc_1801177B5
0x1801177b2  mov     rbx, r13
0x1801177b5  mov     rcx, r12; lpCriticalSection
0x1801177b8  call    cs:__imp_LeaveCriticalSection
0x1801177bf  nop     dword ptr [rax+rax+00h]
0x1801177c4  test    rbx, rbx
0x1801177c7  jz      short loc_180117844
0x1801177c9  mov     [rbp+57h+var_90], r13
0x1801177cd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801177d1  inc     r8; int
0x1801177d4  cmp     [rbx+r8*2], r13w
0x1801177d9  jnz     short loc_1801177D1
0x1801177db  mov     rdx, rbx; unsigned __int16 *
0x1801177de  lea     rcx, [rbp+57h+var_A0]; this
0x1801177e2  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1801177e7  lea     rcx, [rbp+57h+var_90]
0x1801177eb  mov     ebx, eax
0x1801177ed  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1801177f2  test    ebx, ebx
0x1801177f4  jz      loc_180117703
0x1801177fa  mov     rax, [rdi]
0x1801177fd  jmp     short loc_180117811
0x1801177ff  mov     rcx, rax; lpsz
0x180117802  call    cs:__imp_CharNextW
0x180117809  nop     dword ptr [rax+rax+00h]
0x18011780e  mov     [rdi], rax
0x180117811  cmp     rax, rsi
0x180117814  jnz     short loc_1801177FF
0x180117816  mov     esi, 25h ; '%'
0x18011781b  mov     rcx, [rdi]; lpsz
0x18011781e  call    cs:__imp_CharNextW
0x180117825  nop     dword ptr [rax+rax+00h]
0x18011782a  mov     rbx, rax
0x18011782d  mov     [rdi], rax
0x180117830  jmp     loc_1801176BF
0x180117835  mov     rdx, rbx
0x180117838  jmp     loc_1801176EC
0x18011783d  mov     ebx, 80004005h
0x180117842  jmp     short loc_180117859
0x180117844  mov     ebx, 80020009h
0x180117849  jmp     short loc_180117859
0x18011784b  mov     rcx, [rbp+57h+pv]
0x18011784f  mov     ebx, r13d
0x180117852  mov     [r15], rcx
0x180117855  mov     [rbp+57h+pv], r13
0x180117859  mov     rcx, [rbp+57h+pv]; pv
0x18011785d  call    cs:__imp_CoTaskMemFree
0x180117864  nop     dword ptr [rax+rax+00h]
0x180117869  mov     eax, ebx
0x18011786b  jmp     short loc_180117872
0x18011786d  mov     eax, 80004003h
0x180117872  mov     rcx, [rbp+57h+var_40]
0x180117876  xor     rcx, rsp; StackCookie
0x180117879  call    __security_check_cookie
0x18011787e  mov     rbx, [rsp+0C0h+arg_8]
0x180117886  add     rsp, 90h
0x18011788d  pop     r15
0x18011788f  pop     r14
0x180117891  pop     r13
0x180117893  pop     r12
0x180117895  pop     rdi
0x180117896  pop     rsi
0x180117897  pop     rbp
0x180117898  retn
```
