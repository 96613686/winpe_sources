# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x18000eccc`
- end: `0x18000ef39`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010268`

## callees

- `0x180006270`
- `0x18000913c`
- `0x180009eb8`
- `0x18000bbc4`
- `0x18000be84`
- `0x18000de00`
- `0x18000eccc`
- `0x1800118f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ee0f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ee0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ed5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ed5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ed77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ed77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef03`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000eda5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000eeb4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000eeca`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000eda5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000eeb4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000eeca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ee48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ee48`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, wchar_t *a2, wchar_t **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const wchar_t *v11; // rdx
  unsigned int v12; // ebx
  wchar_t *v13; // rax
  wchar_t *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  __int64 v19; // r14
  unsigned int i; // ebx
  const wchar_t *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  wchar_t *v25; // rcx
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
          v21 = *(const wchar_t **)ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
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
  v25 = (wchar_t *)pv;
  pv = 0;
  *a3 = v25;
LABEL_41:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x18000eccc  mov     [rsp-8+arg_8], rbx
0x18000ecd1  push    rbp
0x18000ecd2  push    rsi
0x18000ecd3  push    rdi
0x18000ecd4  push    r12
0x18000ecd6  push    r13
0x18000ecd8  push    r14
0x18000ecda  push    r15
0x18000ecdc  lea     rbp, [rsp-27h]
0x18000ece1  sub     rsp, 90h
0x18000ece8  mov     rax, cs:__security_cookie
0x18000ecef  xor     rax, rsp
0x18000ecf2  mov     [rbp+57h+var_40], rax
0x18000ecf6  mov     r15, r8
0x18000ecf9  mov     rbx, rdx
0x18000ecfc  mov     rdi, rcx
0x18000ecff  xor     r13d, r13d
0x18000ed02  test    rdx, rdx
0x18000ed05  jz      loc_18000EF0D
0x18000ed0b  test    r8, r8
0x18000ed0e  jz      loc_18000EF0D
0x18000ed14  mov     [r8], r13
0x18000ed17  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ed1b  inc     rdx
0x18000ed1e  cmp     [rbx+rdx*2], r13w
0x18000ed23  jnz     short loc_18000ED1B
0x18000ed25  add     edx, edx
0x18000ed27  mov     eax, 3E8h
0x18000ed2c  cmp     edx, 64h ; 'd'
0x18000ed2f  cmovl   edx, eax
0x18000ed32  mov     [rbp+57h+var_98], r13d
0x18000ed36  mov     [rbp+57h+var_94], edx
0x18000ed39  mov     dword ptr [rbp+57h+cb], r13d
0x18000ed3d  mov     r8d, 2
0x18000ed43  lea     rcx, [rbp+57h+cb]
0x18000ed47  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18000ed4c  test    eax, eax
0x18000ed4e  jns     short loc_18000ED59
0x18000ed50  mov     rax, r13
0x18000ed53  mov     [rbp+57h+pv], r13
0x18000ed57  jmp     short loc_18000ED6F
0x18000ed59  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18000ed5c  call    cs:__imp_CoTaskMemAlloc
0x18000ed62  mov     [rbp+57h+pv], rax
0x18000ed66  test    rax, rax
0x18000ed69  jz      short loc_18000ED6F
0x18000ed6b  mov     [rax], r13w
0x18000ed6f  test    rax, rax
0x18000ed72  jnz     short loc_18000ED87
0x18000ed74  mov     rcx, rax; pv
0x18000ed77  call    cs:__imp_CoTaskMemFree
0x18000ed7d  mov     eax, 8007000Eh
0x18000ed82  jmp     loc_18000EF12
0x18000ed87  mov     [rdi], rbx
0x18000ed8a  mov     esi, 25h ; '%'
0x18000ed8f  cmp     [rbx], r13w
0x18000ed93  jz      loc_18000EEF1
0x18000ed99  cmp     [rbx], si
0x18000ed9c  jnz     loc_18000EEDB
0x18000eda2  mov     rcx, rbx; lpsz
0x18000eda5  call    cs:__imp_CharNextW
0x18000edab  mov     [rdi], rax
0x18000edae  cmp     [rax], si
0x18000edb1  jnz     short loc_18000EDD7
0x18000edb3  mov     rdx, rax; wchar_t *
0x18000edb6  mov     r8d, 1; int
0x18000edbc  lea     rcx, [rbp+57h+var_98]; this
0x18000edc0  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18000edc5  test    eax, eax
0x18000edc7  jnz     loc_18000EEC7
0x18000edcd  mov     ebx, 8007000Eh
0x18000edd2  jmp     loc_18000EEFF
0x18000edd7  mov     edx, esi; wchar_t
0x18000edd9  mov     rcx, rax; lpsz
0x18000eddc  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18000ede1  mov     rsi, rax
0x18000ede4  test    rax, rax
0x18000ede7  jz      loc_18000EEEA
0x18000eded  mov     rcx, rax
0x18000edf0  sub     rcx, [rdi]
0x18000edf3  sar     rcx, 1
0x18000edf6  cmp     rcx, 1Fh
0x18000edfa  jg      loc_18000EEE3
0x18000ee00  movsxd  r9, ecx
0x18000ee03  mov     r8, [rdi]
0x18000ee06  mov     edx, 20h ; ' '
0x18000ee0b  lea     rcx, [rbp+57h+String2]
0x18000ee0f  call    cs:__imp__o_wcsncpy_s
0x18000ee15  mov     ecx, eax; int
0x18000ee17  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000ee1c  mov     rbx, [rdi+8]
0x18000ee20  lea     r12, [rbx+20h]
0x18000ee24  mov     rcx, r12; lpCriticalSection
0x18000ee27  call    cs:__imp_EnterCriticalSection
0x18000ee2d  lea     r14, [rbx+8]
0x18000ee31  mov     ebx, r13d
0x18000ee34  cmp     ebx, [r14+10h]
0x18000ee38  jge     short loc_18000EE6A
0x18000ee3a  movsxd  rax, ebx
0x18000ee3d  mov     rcx, [r14]
0x18000ee40  lea     rdx, [rbp+57h+String2]; lpString2
0x18000ee44  mov     rcx, [rcx+rax*8]; lpString1
0x18000ee48  call    cs:__imp_lstrcmpiW
0x18000ee4e  test    eax, eax
0x18000ee50  jz      short loc_18000EE56
0x18000ee52  inc     ebx
0x18000ee54  jmp     short loc_18000EE34
0x18000ee56  cmp     ebx, 0FFFFFFFFh
0x18000ee59  jz      short loc_18000EE6A
0x18000ee5b  mov     edx, ebx
0x18000ee5d  mov     rcx, r14
0x18000ee60  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000ee65  mov     rbx, [rax]
0x18000ee68  jmp     short loc_18000EE6D
0x18000ee6a  mov     rbx, r13
0x18000ee6d  mov     rcx, r12; lpCriticalSection
0x18000ee70  call    cs:__imp_LeaveCriticalSection
0x18000ee76  test    rbx, rbx
0x18000ee79  jz      short loc_18000EEEA
0x18000ee7b  mov     [rbp+57h+cb], r13
0x18000ee7f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ee83  inc     r8; int
0x18000ee86  cmp     [rbx+r8*2], r13w
0x18000ee8b  jnz     short loc_18000EE83
0x18000ee8d  mov     rdx, rbx; wchar_t *
0x18000ee90  lea     rcx, [rbp+57h+var_98]; this
0x18000ee94  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18000ee99  mov     ebx, eax
0x18000ee9b  lea     rcx, [rbp+57h+cb]
0x18000ee9f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000eea4  test    ebx, ebx
0x18000eea6  jz      loc_18000EDCD
0x18000eeac  mov     rax, [rdi]
0x18000eeaf  jmp     short loc_18000EEBD
0x18000eeb1  mov     rcx, rax; lpsz
0x18000eeb4  call    cs:__imp_CharNextW
0x18000eeba  mov     [rdi], rax
0x18000eebd  cmp     rax, rsi
0x18000eec0  jnz     short loc_18000EEB1
0x18000eec2  mov     esi, 25h ; '%'
0x18000eec7  mov     rcx, [rdi]; lpsz
0x18000eeca  call    cs:__imp_CharNextW
0x18000eed0  mov     rbx, rax
0x18000eed3  mov     [rdi], rax
0x18000eed6  jmp     loc_18000ED8F
0x18000eedb  mov     rdx, rbx
0x18000eede  jmp     loc_18000EDB6
0x18000eee3  mov     ebx, 80004005h
0x18000eee8  jmp     short loc_18000EEFF
0x18000eeea  mov     ebx, 80020009h
0x18000eeef  jmp     short loc_18000EEFF
0x18000eef1  mov     ebx, r13d
0x18000eef4  mov     rcx, [rbp+57h+pv]
0x18000eef8  mov     [rbp+57h+pv], r13
0x18000eefc  mov     [r15], rcx
0x18000eeff  mov     rcx, [rbp+57h+pv]; pv
0x18000ef03  call    cs:__imp_CoTaskMemFree
0x18000ef09  mov     eax, ebx
0x18000ef0b  jmp     short loc_18000EF12
0x18000ef0d  mov     eax, 80004003h
0x18000ef12  mov     rcx, [rbp+57h+var_40]
0x18000ef16  xor     rcx, rsp; StackCookie
0x18000ef19  call    __security_check_cookie
0x18000ef1e  mov     rbx, [rsp+0C0h+arg_8]
0x18000ef26  add     rsp, 90h
0x18000ef2d  pop     r15
0x18000ef2f  pop     r14
0x18000ef31  pop     r13
0x18000ef33  pop     r12
0x18000ef35  pop     rdi
0x18000ef36  pop     rsi
0x18000ef37  pop     rbp
0x18000ef38  retn
```
