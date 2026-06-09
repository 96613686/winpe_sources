# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1803b8cb4`
- end: `0x1803b8f16`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `610`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1803ba024`

## callees

- `0x18032c914`
- `0x1803b0350`
- `0x1803b0e98`
- `0x1803b2dd0`
- `0x1803b6eb4`
- `0x1803b8cb4`
- `0x1803bbd10`
- `0x180688fc0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1803b8dec`
- `msvcrt!wcsncpy_s` at `0x1803b8dec`
- `KERNEL32!LeaveCriticalSection` at `0x1803b8e4d`
- `KERNEL32!LeaveCriticalSection` at `0x1803b8e4d`
- `KERNEL32!EnterCriticalSection` at `0x1803b8e04`
- `KERNEL32!EnterCriticalSection` at `0x1803b8e04`
- `KERNEL32!lstrcmpiW` at `0x1803b8e25`
- `KERNEL32!lstrcmpiW` at `0x1803b8e25`
- `USER32!CharNextW` at `0x1803b8d82`
- `USER32!CharNextW` at `0x1803b8e91`
- `USER32!CharNextW` at `0x1803b8ea7`
- `USER32!CharNextW` at `0x1803b8d82`
- `USER32!CharNextW` at `0x1803b8e91`
- `USER32!CharNextW` at `0x1803b8ea7`
- `OLE32!CoTaskMemFree` at `0x1803b8d3e`
- `OLE32!CoTaskMemFree` at `0x1803b8ee0`
- `OLE32!CoTaskMemFree` at `0x1803b8d3e`
- `OLE32!CoTaskMemFree` at `0x1803b8ee0`
- `OLE32!CoTaskMemAlloc` at `0x1803b8d51`
- `OLE32!CoTaskMemAlloc` at `0x1803b8d51`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, LPVOID *a3)
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
  errno_t v16; // eax
  const wchar_t *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  const wchar_t *v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v26[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned int)(2 * v6);
  v26[0] = 0;
  LODWORD(cb) = 0;
  if ( (int)v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
  if ( (int)ATL::AtlMultiply<unsigned long>(&cb, v7, 2) < 0 )
  {
    v8 = 0;
LABEL_9:
    CoTaskMemFree(v8);
    return 2147942414LL;
  }
  v8 = CoTaskMemAlloc((unsigned int)cb);
  pv = v8;
  if ( !v8 )
    goto LABEL_9;
  *v8 = 0;
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v11 = v4;
LABEL_16:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v11, 1) )
        goto LABEL_17;
      goto LABEL_34;
    }
    v10 = CharNextW(v4);
    *this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_16;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_37;
    v15 = v13 - *this;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_39;
    }
    v16 = wcsncpy_s(Destination, 0x20u, *this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = this[1];
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
    v19 = v17 + 4;
    for ( i = 0; (signed int)i < *((_DWORD *)v19 + 4); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v19 + 8LL * (int)i), Destination) )
      {
        if ( i != -1 )
        {
          v21 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v19,
                                              i);
          goto LABEL_27;
        }
        break;
      }
    }
    v21 = 0;
LABEL_27:
    LeaveCriticalSection(v18);
    if ( !v21 )
    {
LABEL_37:
      v12 = -2147352567;
      goto LABEL_39;
    }
    cb = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v23 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v21, v22);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
    if ( !v23 )
    {
LABEL_17:
      v12 = -2147024882;
      goto LABEL_39;
    }
    for ( j = *this; j != v14; *this = j )
      j = CharNextW(j);
LABEL_34:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v12 = 0;
  *a3 = pv;
  pv = 0;
LABEL_39:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x1803b8cb4  mov     [rsp-8+arg_8], rbx
0x1803b8cb9  push    rbp
0x1803b8cba  push    rsi
0x1803b8cbb  push    rdi
0x1803b8cbc  push    r12
0x1803b8cbe  push    r13
0x1803b8cc0  push    r14
0x1803b8cc2  push    r15
0x1803b8cc4  lea     rbp, [rsp-27h]
0x1803b8cc9  sub     rsp, 90h
0x1803b8cd0  mov     rax, cs:__security_cookie
0x1803b8cd7  xor     rax, rsp
0x1803b8cda  mov     [rbp+57h+var_40], rax
0x1803b8cde  xor     r13d, r13d
0x1803b8ce1  mov     r15, r8
0x1803b8ce4  mov     rbx, rdx
0x1803b8ce7  mov     rdi, rcx
0x1803b8cea  test    rdx, rdx
0x1803b8ced  jz      loc_1803B8EEA
0x1803b8cf3  test    r8, r8
0x1803b8cf6  jz      loc_1803B8EEA
0x1803b8cfc  mov     [r8], r13
0x1803b8cff  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1803b8d03  inc     rdx
0x1803b8d06  cmp     [rbx+rdx*2], r13w
0x1803b8d0b  jnz     short loc_1803B8D03
0x1803b8d0d  add     edx, edx
0x1803b8d0f  mov     [rbp+57h+var_98], r13d
0x1803b8d13  mov     eax, 3E8h
0x1803b8d18  mov     dword ptr [rbp+57h+cb], r13d
0x1803b8d1c  cmp     edx, 64h ; 'd'
0x1803b8d1f  lea     rcx, [rbp+57h+cb]
0x1803b8d23  mov     r8d, 2
0x1803b8d29  cmovl   edx, eax
0x1803b8d2c  mov     [rbp+57h+var_94], edx
0x1803b8d2f  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x1803b8d34  test    eax, eax
0x1803b8d36  jns     short loc_1803B8D4E
0x1803b8d38  mov     rax, r13
0x1803b8d3b  mov     rcx, rax; pv
0x1803b8d3e  call    cs:__imp_CoTaskMemFree
0x1803b8d44  mov     eax, 8007000Eh
0x1803b8d49  jmp     loc_1803B8EEF
0x1803b8d4e  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x1803b8d51  call    cs:__imp_CoTaskMemAlloc
0x1803b8d57  mov     [rbp+57h+pv], rax
0x1803b8d5b  test    rax, rax
0x1803b8d5e  jz      short loc_1803B8D3B
0x1803b8d60  mov     [rax], r13w
0x1803b8d64  mov     esi, 25h ; '%'
0x1803b8d69  mov     [rdi], rbx
0x1803b8d6c  cmp     [rbx], r13w
0x1803b8d70  jz      loc_1803B8ECE
0x1803b8d76  cmp     [rbx], si
0x1803b8d79  jnz     loc_1803B8EB8
0x1803b8d7f  mov     rcx, rbx; lpsz
0x1803b8d82  call    cs:__imp_CharNextW
0x1803b8d88  mov     [rdi], rax
0x1803b8d8b  cmp     [rax], si
0x1803b8d8e  jnz     short loc_1803B8DB4
0x1803b8d90  mov     rdx, rax; unsigned __int16 *
0x1803b8d93  mov     r8d, 1; int
0x1803b8d99  lea     rcx, [rbp+57h+var_98]; this
0x1803b8d9d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1803b8da2  test    eax, eax
0x1803b8da4  jnz     loc_1803B8EA4
0x1803b8daa  mov     ebx, 8007000Eh
0x1803b8daf  jmp     loc_1803B8EDC
0x1803b8db4  mov     edx, esi; unsigned __int16
0x1803b8db6  mov     rcx, rax; lpsz
0x1803b8db9  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1803b8dbe  mov     rsi, rax
0x1803b8dc1  test    rax, rax
0x1803b8dc4  jz      loc_1803B8EC7
0x1803b8dca  mov     rcx, rax
0x1803b8dcd  sub     rcx, [rdi]
0x1803b8dd0  sar     rcx, 1
0x1803b8dd3  cmp     rcx, 1Fh
0x1803b8dd7  jg      loc_1803B8EC0
0x1803b8ddd  mov     r8, [rdi]; Source
0x1803b8de0  mov     edx, 20h ; ' '; SizeInWords
0x1803b8de5  movsxd  r9, ecx; MaxCount
0x1803b8de8  lea     rcx, [rbp+57h+Destination]; Destination
0x1803b8dec  call    cs:__imp_wcsncpy_s
0x1803b8df2  mov     ecx, eax; int
0x1803b8df4  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1803b8df9  mov     rbx, [rdi+8]
0x1803b8dfd  lea     r12, [rbx+20h]
0x1803b8e01  mov     rcx, r12; lpCriticalSection
0x1803b8e04  call    cs:__imp_EnterCriticalSection
0x1803b8e0a  lea     r14, [rbx+8]
0x1803b8e0e  mov     ebx, r13d
0x1803b8e11  cmp     ebx, [r14+10h]
0x1803b8e15  jge     short loc_1803B8E47
0x1803b8e17  mov     rcx, [r14]
0x1803b8e1a  lea     rdx, [rbp+57h+Destination]; lpString2
0x1803b8e1e  movsxd  rax, ebx
0x1803b8e21  mov     rcx, [rcx+rax*8]; lpString1
0x1803b8e25  call    cs:__imp_lstrcmpiW
0x1803b8e2b  test    eax, eax
0x1803b8e2d  jz      short loc_1803B8E33
0x1803b8e2f  inc     ebx
0x1803b8e31  jmp     short loc_1803B8E11
0x1803b8e33  cmp     ebx, 0FFFFFFFFh
0x1803b8e36  jz      short loc_1803B8E47
0x1803b8e38  mov     edx, ebx
0x1803b8e3a  mov     rcx, r14
0x1803b8e3d  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1803b8e42  mov     rbx, [rax]
0x1803b8e45  jmp     short loc_1803B8E4A
0x1803b8e47  mov     rbx, r13
0x1803b8e4a  mov     rcx, r12; lpCriticalSection
0x1803b8e4d  call    cs:__imp_LeaveCriticalSection
0x1803b8e53  test    rbx, rbx
0x1803b8e56  jz      short loc_1803B8EC7
0x1803b8e58  mov     [rbp+57h+cb], r13
0x1803b8e5c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1803b8e60  inc     r8; int
0x1803b8e63  cmp     [rbx+r8*2], r13w
0x1803b8e68  jnz     short loc_1803B8E60
0x1803b8e6a  mov     rdx, rbx; unsigned __int16 *
0x1803b8e6d  lea     rcx, [rbp+57h+var_98]; this
0x1803b8e71  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1803b8e76  lea     rcx, [rbp+57h+cb]
0x1803b8e7a  mov     ebx, eax
0x1803b8e7c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1803b8e81  test    ebx, ebx
0x1803b8e83  jz      loc_1803B8DAA
0x1803b8e89  mov     rax, [rdi]
0x1803b8e8c  jmp     short loc_1803B8E9A
0x1803b8e8e  mov     rcx, rax; lpsz
0x1803b8e91  call    cs:__imp_CharNextW
0x1803b8e97  mov     [rdi], rax
0x1803b8e9a  cmp     rax, rsi
0x1803b8e9d  jnz     short loc_1803B8E8E
0x1803b8e9f  mov     esi, 25h ; '%'
0x1803b8ea4  mov     rcx, [rdi]; lpsz
0x1803b8ea7  call    cs:__imp_CharNextW
0x1803b8ead  mov     rbx, rax
0x1803b8eb0  mov     [rdi], rax
0x1803b8eb3  jmp     loc_1803B8D6C
0x1803b8eb8  mov     rdx, rbx
0x1803b8ebb  jmp     loc_1803B8D93
0x1803b8ec0  mov     ebx, 80004005h
0x1803b8ec5  jmp     short loc_1803B8EDC
0x1803b8ec7  mov     ebx, 80020009h
0x1803b8ecc  jmp     short loc_1803B8EDC
0x1803b8ece  mov     rcx, [rbp+57h+pv]
0x1803b8ed2  mov     ebx, r13d
0x1803b8ed5  mov     [r15], rcx
0x1803b8ed8  mov     [rbp+57h+pv], r13
0x1803b8edc  mov     rcx, [rbp+57h+pv]; pv
0x1803b8ee0  call    cs:__imp_CoTaskMemFree
0x1803b8ee6  mov     eax, ebx
0x1803b8ee8  jmp     short loc_1803B8EEF
0x1803b8eea  mov     eax, 80004003h
0x1803b8eef  mov     rcx, [rbp+57h+var_40]
0x1803b8ef3  xor     rcx, rsp; StackCookie
0x1803b8ef6  call    __security_check_cookie
0x1803b8efb  mov     rbx, [rsp+0C0h+arg_8]
0x1803b8f03  add     rsp, 90h
0x1803b8f0a  pop     r15
0x1803b8f0c  pop     r14
0x1803b8f0e  pop     r13
0x1803b8f10  pop     r12
0x1803b8f12  pop     rdi
0x1803b8f13  pop     rsi
0x1803b8f14  pop     rbp
0x1803b8f15  retn
```
