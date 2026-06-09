# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18001472c`
- end: `0x180014985`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `601`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800152f0`

## callees

- `0x18000f970`
- `0x180010f88`
- `0x180011eb0`
- `0x180011f78`
- `0x1800136b4`
- `0x18001472c`
- `0x180016550`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001485b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001485b`
- `KERNEL32!EnterCriticalSection` at `0x180014873`
- `KERNEL32!EnterCriticalSection` at `0x180014873`
- `KERNEL32!LeaveCriticalSection` at `0x1800148bc`
- `KERNEL32!LeaveCriticalSection` at `0x1800148bc`
- `KERNEL32!lstrcmpiW` at `0x180014894`
- `KERNEL32!lstrcmpiW` at `0x180014894`
- `USER32!CharNextW` at `0x1800147f1`
- `USER32!CharNextW` at `0x180014900`
- `USER32!CharNextW` at `0x180014916`
- `USER32!CharNextW` at `0x1800147f1`
- `USER32!CharNextW` at `0x180014900`
- `USER32!CharNextW` at `0x180014916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800147ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001494f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800147ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001494f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800147c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800147c0`

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
0x18001472c  mov     [rsp-8+arg_8], rbx
0x180014731  push    rbp
0x180014732  push    rsi
0x180014733  push    rdi
0x180014734  push    r12
0x180014736  push    r13
0x180014738  push    r14
0x18001473a  push    r15
0x18001473c  lea     rbp, [rsp-27h]
0x180014741  sub     rsp, 90h
0x180014748  mov     rax, cs:__security_cookie
0x18001474f  xor     rax, rsp
0x180014752  mov     [rbp+57h+var_40], rax
0x180014756  xor     r13d, r13d
0x180014759  mov     r15, r8
0x18001475c  mov     rbx, rdx
0x18001475f  mov     rdi, rcx
0x180014762  test    rdx, rdx
0x180014765  jz      loc_180014959
0x18001476b  test    r8, r8
0x18001476e  jz      loc_180014959
0x180014774  mov     [r8], r13
0x180014777  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001477b  inc     rax
0x18001477e  cmp     [rdx+rax*2], r13w
0x180014783  jnz     short loc_18001477B
0x180014785  add     eax, eax
0x180014787  mov     [rbp+57h+var_A0], r13d
0x18001478b  cmp     eax, 64h ; 'd'
0x18001478e  mov     ecx, 3E8h
0x180014793  cmovl   eax, ecx
0x180014796  mov     ecx, eax
0x180014798  mov     [rbp+57h+var_9C], eax
0x18001479b  add     rcx, rcx
0x18001479e  mov     eax, 0FFFFFFFFh
0x1800147a3  cmp     rcx, rax
0x1800147a6  jbe     short loc_1800147BE
0x1800147a8  mov     rax, r13
0x1800147ab  mov     rcx, rax; pv
0x1800147ae  call    cs:__imp_CoTaskMemFree
0x1800147b4  mov     eax, 8007000Eh
0x1800147b9  jmp     loc_18001495E
0x1800147be  mov     ecx, ecx; cb
0x1800147c0  call    cs:__imp_CoTaskMemAlloc
0x1800147c6  mov     [rbp+57h+pv], rax
0x1800147ca  test    rax, rax
0x1800147cd  jz      short loc_1800147AB
0x1800147cf  mov     [rax], r13w
0x1800147d3  mov     esi, 25h ; '%'
0x1800147d8  mov     [rdi], rbx
0x1800147db  cmp     [rbx], r13w
0x1800147df  jz      loc_18001493D
0x1800147e5  cmp     [rbx], si
0x1800147e8  jnz     loc_180014927
0x1800147ee  mov     rcx, rbx; lpsz
0x1800147f1  call    cs:__imp_CharNextW
0x1800147f7  mov     [rdi], rax
0x1800147fa  cmp     [rax], si
0x1800147fd  jnz     short loc_180014823
0x1800147ff  mov     rdx, rax; unsigned __int16 *
0x180014802  mov     r8d, 1; int
0x180014808  lea     rcx, [rbp+57h+var_A0]; this
0x18001480c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180014811  test    eax, eax
0x180014813  jnz     loc_180014913
0x180014819  mov     ebx, 8007000Eh
0x18001481e  jmp     loc_18001494B
0x180014823  mov     edx, esi; unsigned __int16
0x180014825  mov     rcx, rax; lpsz
0x180014828  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001482d  mov     rsi, rax
0x180014830  test    rax, rax
0x180014833  jz      loc_180014936
0x180014839  mov     rcx, rax
0x18001483c  sub     rcx, [rdi]
0x18001483f  sar     rcx, 1
0x180014842  cmp     rcx, 1Fh
0x180014846  jg      loc_18001492F
0x18001484c  mov     r8, [rdi]
0x18001484f  mov     edx, 20h ; ' '
0x180014854  movsxd  r9, ecx
0x180014857  lea     rcx, [rbp+57h+String2]
0x18001485b  call    cs:__imp__o_wcsncpy_s
0x180014861  mov     ecx, eax; int
0x180014863  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180014868  mov     rbx, [rdi+8]
0x18001486c  lea     r12, [rbx+20h]
0x180014870  mov     rcx, r12; lpCriticalSection
0x180014873  call    cs:__imp_EnterCriticalSection
0x180014879  lea     r14, [rbx+8]
0x18001487d  mov     ebx, r13d
0x180014880  cmp     ebx, [r14+10h]
0x180014884  jge     short loc_1800148B6
0x180014886  mov     rcx, [r14]
0x180014889  lea     rdx, [rbp+57h+String2]; lpString2
0x18001488d  movsxd  rax, ebx
0x180014890  mov     rcx, [rcx+rax*8]; lpString1
0x180014894  call    cs:__imp_lstrcmpiW
0x18001489a  test    eax, eax
0x18001489c  jz      short loc_1800148A2
0x18001489e  inc     ebx
0x1800148a0  jmp     short loc_180014880
0x1800148a2  cmp     ebx, 0FFFFFFFFh
0x1800148a5  jz      short loc_1800148B6
0x1800148a7  mov     edx, ebx
0x1800148a9  mov     rcx, r14
0x1800148ac  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1800148b1  mov     rbx, [rax]
0x1800148b4  jmp     short loc_1800148B9
0x1800148b6  mov     rbx, r13
0x1800148b9  mov     rcx, r12; lpCriticalSection
0x1800148bc  call    cs:__imp_LeaveCriticalSection
0x1800148c2  test    rbx, rbx
0x1800148c5  jz      short loc_180014936
0x1800148c7  mov     [rbp+57h+var_90], r13
0x1800148cb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800148cf  inc     r8; int
0x1800148d2  cmp     [rbx+r8*2], r13w
0x1800148d7  jnz     short loc_1800148CF
0x1800148d9  mov     rdx, rbx; unsigned __int16 *
0x1800148dc  lea     rcx, [rbp+57h+var_A0]; this
0x1800148e0  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800148e5  lea     rcx, [rbp+57h+var_90]
0x1800148e9  mov     ebx, eax
0x1800148eb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800148f0  test    ebx, ebx
0x1800148f2  jz      loc_180014819
0x1800148f8  mov     rax, [rdi]
0x1800148fb  jmp     short loc_180014909
0x1800148fd  mov     rcx, rax; lpsz
0x180014900  call    cs:__imp_CharNextW
0x180014906  mov     [rdi], rax
0x180014909  cmp     rax, rsi
0x18001490c  jnz     short loc_1800148FD
0x18001490e  mov     esi, 25h ; '%'
0x180014913  mov     rcx, [rdi]; lpsz
0x180014916  call    cs:__imp_CharNextW
0x18001491c  mov     rbx, rax
0x18001491f  mov     [rdi], rax
0x180014922  jmp     loc_1800147DB
0x180014927  mov     rdx, rbx
0x18001492a  jmp     loc_180014802
0x18001492f  mov     ebx, 80004005h
0x180014934  jmp     short loc_18001494B
0x180014936  mov     ebx, 80020009h
0x18001493b  jmp     short loc_18001494B
0x18001493d  mov     rcx, [rbp+57h+pv]
0x180014941  mov     ebx, r13d
0x180014944  mov     [r15], rcx
0x180014947  mov     [rbp+57h+pv], r13
0x18001494b  mov     rcx, [rbp+57h+pv]; pv
0x18001494f  call    cs:__imp_CoTaskMemFree
0x180014955  mov     eax, ebx
0x180014957  jmp     short loc_18001495E
0x180014959  mov     eax, 80004003h
0x18001495e  mov     rcx, [rbp+57h+var_40]
0x180014962  xor     rcx, rsp; StackCookie
0x180014965  call    __security_check_cookie
0x18001496a  mov     rbx, [rsp+0C0h+arg_8]
0x180014972  add     rsp, 90h
0x180014979  pop     r15
0x18001497b  pop     r14
0x18001497d  pop     r13
0x18001497f  pop     r12
0x180014981  pop     rdi
0x180014982  pop     rsi
0x180014983  pop     rbp
0x180014984  retn
```
