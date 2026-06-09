# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000d0cc`
- end: `0x18000d325`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `601`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d45c`

## callees

- `0x18000bc94`
- `0x18000c5b0`
- `0x18000c78c`
- `0x18000cdec`
- `0x18000d0cc`
- `0x18000de8c`
- `0x180018a80`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000d1fb`
- `msvcrt!wcsncpy_s` at `0x18000d1fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d25c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d25c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d213`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d14e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d14e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d160`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d160`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d191`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d2a0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d2b6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d191`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d2a0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d2b6`
- `KERNEL32!lstrcmpiW` at `0x18000d234`
- `KERNEL32!lstrcmpiW` at `0x18000d234`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, LPVOID *a3)
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
  _DWORD v26[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h] BYREF
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
  v26[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
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
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_16:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v12, 1) )
        goto LABEL_17;
      goto LABEL_34;
    }
    v11 = CharNextW(v4);
    *this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_16;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_37;
    v16 = v14 - *this;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_39;
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
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v28);
    if ( !v24 )
    {
LABEL_17:
      v13 = -2147024882;
      goto LABEL_39;
    }
    for ( j = *this; j != v15; *this = j )
      j = CharNextW(j);
LABEL_34:
    v4 = CharNextW(*this);
    *this = v4;
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
0x18000d0cc  mov     [rsp-8+arg_8], rbx
0x18000d0d1  push    rbp
0x18000d0d2  push    rsi
0x18000d0d3  push    rdi
0x18000d0d4  push    r12
0x18000d0d6  push    r13
0x18000d0d8  push    r14
0x18000d0da  push    r15
0x18000d0dc  lea     rbp, [rsp-27h]
0x18000d0e1  sub     rsp, 90h
0x18000d0e8  mov     rax, cs:__security_cookie
0x18000d0ef  xor     rax, rsp
0x18000d0f2  mov     [rbp+57h+var_40], rax
0x18000d0f6  xor     r13d, r13d
0x18000d0f9  mov     r15, r8
0x18000d0fc  mov     rbx, rdx
0x18000d0ff  mov     rdi, rcx
0x18000d102  test    rdx, rdx
0x18000d105  jz      loc_18000D2F9
0x18000d10b  test    r8, r8
0x18000d10e  jz      loc_18000D2F9
0x18000d114  mov     [r8], r13
0x18000d117  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d11b  inc     rax
0x18000d11e  cmp     [rdx+rax*2], r13w
0x18000d123  jnz     short loc_18000D11B
0x18000d125  add     eax, eax
0x18000d127  mov     [rbp+57h+var_A0], r13d
0x18000d12b  cmp     eax, 64h ; 'd'
0x18000d12e  mov     ecx, 3E8h
0x18000d133  cmovl   eax, ecx
0x18000d136  mov     ecx, eax
0x18000d138  mov     [rbp+57h+var_9C], eax
0x18000d13b  add     rcx, rcx
0x18000d13e  mov     eax, 0FFFFFFFFh
0x18000d143  cmp     rcx, rax
0x18000d146  jbe     short loc_18000D15E
0x18000d148  mov     rax, r13
0x18000d14b  mov     rcx, rax; pv
0x18000d14e  call    cs:__imp_CoTaskMemFree
0x18000d154  mov     eax, 8007000Eh
0x18000d159  jmp     loc_18000D2FE
0x18000d15e  mov     ecx, ecx; cb
0x18000d160  call    cs:__imp_CoTaskMemAlloc
0x18000d166  mov     [rbp+57h+pv], rax
0x18000d16a  test    rax, rax
0x18000d16d  jz      short loc_18000D14B
0x18000d16f  mov     [rax], r13w
0x18000d173  mov     esi, 25h ; '%'
0x18000d178  mov     [rdi], rbx
0x18000d17b  cmp     [rbx], r13w
0x18000d17f  jz      loc_18000D2DD
0x18000d185  cmp     [rbx], si
0x18000d188  jnz     loc_18000D2C7
0x18000d18e  mov     rcx, rbx; lpsz
0x18000d191  call    cs:__imp_CharNextW
0x18000d197  mov     [rdi], rax
0x18000d19a  cmp     [rax], si
0x18000d19d  jnz     short loc_18000D1C3
0x18000d19f  mov     rdx, rax; unsigned __int16 *
0x18000d1a2  mov     r8d, 1; int
0x18000d1a8  lea     rcx, [rbp+57h+var_A0]; this
0x18000d1ac  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000d1b1  test    eax, eax
0x18000d1b3  jnz     loc_18000D2B3
0x18000d1b9  mov     ebx, 8007000Eh
0x18000d1be  jmp     loc_18000D2EB
0x18000d1c3  mov     edx, esi; unsigned __int16
0x18000d1c5  mov     rcx, rax; lpsz
0x18000d1c8  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000d1cd  mov     rsi, rax
0x18000d1d0  test    rax, rax
0x18000d1d3  jz      loc_18000D2D6
0x18000d1d9  mov     rcx, rax
0x18000d1dc  sub     rcx, [rdi]
0x18000d1df  sar     rcx, 1
0x18000d1e2  cmp     rcx, 1Fh
0x18000d1e6  jg      loc_18000D2CF
0x18000d1ec  mov     r8, [rdi]; Source
0x18000d1ef  mov     edx, 20h ; ' '; SizeInWords
0x18000d1f4  movsxd  r9, ecx; MaxCount
0x18000d1f7  lea     rcx, [rbp+57h+Destination]; Destination
0x18000d1fb  call    cs:__imp_wcsncpy_s
0x18000d201  mov     ecx, eax; int
0x18000d203  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000d208  mov     rbx, [rdi+8]
0x18000d20c  lea     r12, [rbx+20h]
0x18000d210  mov     rcx, r12; lpCriticalSection
0x18000d213  call    cs:__imp_EnterCriticalSection
0x18000d219  lea     r14, [rbx+8]
0x18000d21d  mov     ebx, r13d
0x18000d220  cmp     ebx, [r14+10h]
0x18000d224  jge     short loc_18000D256
0x18000d226  mov     rcx, [r14]
0x18000d229  lea     rdx, [rbp+57h+Destination]; lpString2
0x18000d22d  movsxd  rax, ebx
0x18000d230  mov     rcx, [rcx+rax*8]; lpString1
0x18000d234  call    cs:__imp_lstrcmpiW
0x18000d23a  test    eax, eax
0x18000d23c  jz      short loc_18000D242
0x18000d23e  inc     ebx
0x18000d240  jmp     short loc_18000D220
0x18000d242  cmp     ebx, 0FFFFFFFFh
0x18000d245  jz      short loc_18000D256
0x18000d247  mov     edx, ebx
0x18000d249  mov     rcx, r14
0x18000d24c  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000d251  mov     rbx, [rax]
0x18000d254  jmp     short loc_18000D259
0x18000d256  mov     rbx, r13
0x18000d259  mov     rcx, r12; lpCriticalSection
0x18000d25c  call    cs:__imp_LeaveCriticalSection
0x18000d262  test    rbx, rbx
0x18000d265  jz      short loc_18000D2D6
0x18000d267  mov     [rbp+57h+var_90], r13
0x18000d26b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d26f  inc     r8; int
0x18000d272  cmp     [rbx+r8*2], r13w
0x18000d277  jnz     short loc_18000D26F
0x18000d279  mov     rdx, rbx; unsigned __int16 *
0x18000d27c  lea     rcx, [rbp+57h+var_A0]; this
0x18000d280  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000d285  lea     rcx, [rbp+57h+var_90]
0x18000d289  mov     ebx, eax
0x18000d28b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000d290  test    ebx, ebx
0x18000d292  jz      loc_18000D1B9
0x18000d298  mov     rax, [rdi]
0x18000d29b  jmp     short loc_18000D2A9
0x18000d29d  mov     rcx, rax; lpsz
0x18000d2a0  call    cs:__imp_CharNextW
0x18000d2a6  mov     [rdi], rax
0x18000d2a9  cmp     rax, rsi
0x18000d2ac  jnz     short loc_18000D29D
0x18000d2ae  mov     esi, 25h ; '%'
0x18000d2b3  mov     rcx, [rdi]; lpsz
0x18000d2b6  call    cs:__imp_CharNextW
0x18000d2bc  mov     rbx, rax
0x18000d2bf  mov     [rdi], rax
0x18000d2c2  jmp     loc_18000D17B
0x18000d2c7  mov     rdx, rbx
0x18000d2ca  jmp     loc_18000D1A2
0x18000d2cf  mov     ebx, 80004005h
0x18000d2d4  jmp     short loc_18000D2EB
0x18000d2d6  mov     ebx, 80020009h
0x18000d2db  jmp     short loc_18000D2EB
0x18000d2dd  mov     rcx, [rbp+57h+pv]
0x18000d2e1  mov     ebx, r13d
0x18000d2e4  mov     [r15], rcx
0x18000d2e7  mov     [rbp+57h+pv], r13
0x18000d2eb  mov     rcx, [rbp+57h+pv]; pv
0x18000d2ef  call    cs:__imp_CoTaskMemFree
0x18000d2f5  mov     eax, ebx
0x18000d2f7  jmp     short loc_18000D2FE
0x18000d2f9  mov     eax, 80004003h
0x18000d2fe  mov     rcx, [rbp+57h+var_40]
0x18000d302  xor     rcx, rsp; StackCookie
0x18000d305  call    __security_check_cookie
0x18000d30a  mov     rbx, [rsp+0C0h+arg_8]
0x18000d312  add     rsp, 90h
0x18000d319  pop     r15
0x18000d31b  pop     r14
0x18000d31d  pop     r13
0x18000d31f  pop     r12
0x18000d321  pop     rdi
0x18000d322  pop     rsi
0x18000d323  pop     rbp
0x18000d324  retn
```
