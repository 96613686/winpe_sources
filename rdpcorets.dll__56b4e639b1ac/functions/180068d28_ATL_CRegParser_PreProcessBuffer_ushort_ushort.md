# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180068d28`
- end: `0x180068f81`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `601`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006954c`

## callees

- `0x180033da0`
- `0x180066e38`
- `0x180067990`
- `0x180067be4`
- `0x180068a3c`
- `0x180068d28`
- `0x18006a154`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180068e57`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180068e57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068eb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068eb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068e6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068e6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068daa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068f4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068daa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068f4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068dbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068dbc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180068ded`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180068efc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180068f12`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180068ded`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180068efc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180068f12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180068e90`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180068e90`

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
0x180068d28  mov     [rsp-8+arg_8], rbx
0x180068d2d  push    rbp
0x180068d2e  push    rsi
0x180068d2f  push    rdi
0x180068d30  push    r12
0x180068d32  push    r13
0x180068d34  push    r14
0x180068d36  push    r15
0x180068d38  lea     rbp, [rsp-27h]
0x180068d3d  sub     rsp, 90h
0x180068d44  mov     rax, cs:__security_cookie
0x180068d4b  xor     rax, rsp
0x180068d4e  mov     [rbp+57h+var_40], rax
0x180068d52  xor     r13d, r13d
0x180068d55  mov     r15, r8
0x180068d58  mov     rbx, rdx
0x180068d5b  mov     rdi, rcx
0x180068d5e  test    rdx, rdx
0x180068d61  jz      loc_180068F55
0x180068d67  test    r8, r8
0x180068d6a  jz      loc_180068F55
0x180068d70  mov     [r8], r13
0x180068d73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180068d77  inc     rax
0x180068d7a  cmp     [rdx+rax*2], r13w
0x180068d7f  jnz     short loc_180068D77
0x180068d81  add     eax, eax
0x180068d83  mov     [rbp+57h+var_A0], r13d
0x180068d87  cmp     eax, 64h ; 'd'
0x180068d8a  mov     ecx, 3E8h
0x180068d8f  cmovl   eax, ecx
0x180068d92  mov     ecx, eax
0x180068d94  mov     [rbp+57h+var_9C], eax
0x180068d97  add     rcx, rcx
0x180068d9a  mov     eax, 0FFFFFFFFh
0x180068d9f  cmp     rcx, rax
0x180068da2  jbe     short loc_180068DBA
0x180068da4  mov     rax, r13
0x180068da7  mov     rcx, rax; pv
0x180068daa  call    cs:__imp_CoTaskMemFree
0x180068db0  mov     eax, 8007000Eh
0x180068db5  jmp     loc_180068F5A
0x180068dba  mov     ecx, ecx; cb
0x180068dbc  call    cs:__imp_CoTaskMemAlloc
0x180068dc2  mov     [rbp+57h+pv], rax
0x180068dc6  test    rax, rax
0x180068dc9  jz      short loc_180068DA7
0x180068dcb  mov     [rax], r13w
0x180068dcf  mov     esi, 25h ; '%'
0x180068dd4  mov     [rdi], rbx
0x180068dd7  cmp     [rbx], r13w
0x180068ddb  jz      loc_180068F39
0x180068de1  cmp     [rbx], si
0x180068de4  jnz     loc_180068F23
0x180068dea  mov     rcx, rbx; lpsz
0x180068ded  call    cs:__imp_CharNextW
0x180068df3  mov     [rdi], rax
0x180068df6  cmp     [rax], si
0x180068df9  jnz     short loc_180068E1F
0x180068dfb  mov     rdx, rax; unsigned __int16 *
0x180068dfe  mov     r8d, 1; int
0x180068e04  lea     rcx, [rbp+57h+var_A0]; this
0x180068e08  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180068e0d  test    eax, eax
0x180068e0f  jnz     loc_180068F0F
0x180068e15  mov     ebx, 8007000Eh
0x180068e1a  jmp     loc_180068F47
0x180068e1f  mov     edx, esi; unsigned __int16
0x180068e21  mov     rcx, rax; lpsz
0x180068e24  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180068e29  mov     rsi, rax
0x180068e2c  test    rax, rax
0x180068e2f  jz      loc_180068F32
0x180068e35  mov     rcx, rax
0x180068e38  sub     rcx, [rdi]
0x180068e3b  sar     rcx, 1
0x180068e3e  cmp     rcx, 1Fh
0x180068e42  jg      loc_180068F2B
0x180068e48  mov     r8, [rdi]
0x180068e4b  mov     edx, 20h ; ' '
0x180068e50  movsxd  r9, ecx
0x180068e53  lea     rcx, [rbp+57h+String2]
0x180068e57  call    cs:__imp__o_wcsncpy_s
0x180068e5d  mov     ecx, eax; int
0x180068e5f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180068e64  mov     rbx, [rdi+8]
0x180068e68  lea     r12, [rbx+20h]
0x180068e6c  mov     rcx, r12; lpCriticalSection
0x180068e6f  call    cs:__imp_EnterCriticalSection
0x180068e75  lea     r14, [rbx+8]
0x180068e79  mov     ebx, r13d
0x180068e7c  cmp     ebx, [r14+10h]
0x180068e80  jge     short loc_180068EB2
0x180068e82  mov     rcx, [r14]
0x180068e85  lea     rdx, [rbp+57h+String2]; lpString2
0x180068e89  movsxd  rax, ebx
0x180068e8c  mov     rcx, [rcx+rax*8]; lpString1
0x180068e90  call    cs:__imp_lstrcmpiW
0x180068e96  test    eax, eax
0x180068e98  jz      short loc_180068E9E
0x180068e9a  inc     ebx
0x180068e9c  jmp     short loc_180068E7C
0x180068e9e  cmp     ebx, 0FFFFFFFFh
0x180068ea1  jz      short loc_180068EB2
0x180068ea3  mov     edx, ebx
0x180068ea5  mov     rcx, r14
0x180068ea8  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180068ead  mov     rbx, [rax]
0x180068eb0  jmp     short loc_180068EB5
0x180068eb2  mov     rbx, r13
0x180068eb5  mov     rcx, r12; lpCriticalSection
0x180068eb8  call    cs:__imp_LeaveCriticalSection
0x180068ebe  test    rbx, rbx
0x180068ec1  jz      short loc_180068F32
0x180068ec3  mov     [rbp+57h+var_90], r13
0x180068ec7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180068ecb  inc     r8; int
0x180068ece  cmp     [rbx+r8*2], r13w
0x180068ed3  jnz     short loc_180068ECB
0x180068ed5  mov     rdx, rbx; unsigned __int16 *
0x180068ed8  lea     rcx, [rbp+57h+var_A0]; this
0x180068edc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180068ee1  lea     rcx, [rbp+57h+var_90]
0x180068ee5  mov     ebx, eax
0x180068ee7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180068eec  test    ebx, ebx
0x180068eee  jz      loc_180068E15
0x180068ef4  mov     rax, [rdi]
0x180068ef7  jmp     short loc_180068F05
0x180068ef9  mov     rcx, rax; lpsz
0x180068efc  call    cs:__imp_CharNextW
0x180068f02  mov     [rdi], rax
0x180068f05  cmp     rax, rsi
0x180068f08  jnz     short loc_180068EF9
0x180068f0a  mov     esi, 25h ; '%'
0x180068f0f  mov     rcx, [rdi]; lpsz
0x180068f12  call    cs:__imp_CharNextW
0x180068f18  mov     rbx, rax
0x180068f1b  mov     [rdi], rax
0x180068f1e  jmp     loc_180068DD7
0x180068f23  mov     rdx, rbx
0x180068f26  jmp     loc_180068DFE
0x180068f2b  mov     ebx, 80004005h
0x180068f30  jmp     short loc_180068F47
0x180068f32  mov     ebx, 80020009h
0x180068f37  jmp     short loc_180068F47
0x180068f39  mov     rcx, [rbp+57h+pv]
0x180068f3d  mov     ebx, r13d
0x180068f40  mov     [r15], rcx
0x180068f43  mov     [rbp+57h+pv], r13
0x180068f47  mov     rcx, [rbp+57h+pv]; pv
0x180068f4b  call    cs:__imp_CoTaskMemFree
0x180068f51  mov     eax, ebx
0x180068f53  jmp     short loc_180068F5A
0x180068f55  mov     eax, 80004003h
0x180068f5a  mov     rcx, [rbp+57h+var_40]
0x180068f5e  xor     rcx, rsp; StackCookie
0x180068f61  call    __security_check_cookie
0x180068f66  mov     rbx, [rsp+0C0h+arg_8]
0x180068f6e  add     rsp, 90h
0x180068f75  pop     r15
0x180068f77  pop     r14
0x180068f79  pop     r13
0x180068f7b  pop     r12
0x180068f7d  pop     rdi
0x180068f7e  pop     rsi
0x180068f7f  pop     rbp
0x180068f80  retn
```
