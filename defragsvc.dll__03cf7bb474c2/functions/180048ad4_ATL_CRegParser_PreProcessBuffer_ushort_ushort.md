# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180048ad4`
- end: `0x180048d26`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `594`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048e9c`

## callees

- `0x180047080`
- `0x180047ad8`
- `0x1800486ec`
- `0x180048ad4`
- `0x180049c44`
- `0x180067b30`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180048c03`
- `msvcrt!wcsncpy_s` at `0x180048c03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c14`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180048b99`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180048ca1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180048cb7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180048b99`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180048ca1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180048cb7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180048c35`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180048c35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048b68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048b68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048b56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048b56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048cf0`

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
  const wchar_t *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  const wchar_t *v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  _DWORD v25[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
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
  v25[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v25[1] = v7;
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
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v12, 1) )
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
    wcsncpy_s(Destination, 0x20u, *this, (int)v16);
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
      v13 = -2147352567;
      goto LABEL_39;
    }
    v27 = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v23 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v21, v22);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v27);
    if ( !v23 )
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
0x180048ad4  mov     [rsp-8+arg_8], rbx
0x180048ad9  push    rbp
0x180048ada  push    rsi
0x180048adb  push    rdi
0x180048adc  push    r12
0x180048ade  push    r13
0x180048ae0  push    r14
0x180048ae2  push    r15
0x180048ae4  lea     rbp, [rsp-27h]
0x180048ae9  sub     rsp, 90h
0x180048af0  mov     rax, cs:__security_cookie
0x180048af7  xor     rax, rsp
0x180048afa  mov     [rbp+57h+var_40], rax
0x180048afe  xor     r13d, r13d
0x180048b01  mov     r15, r8
0x180048b04  mov     rbx, rdx
0x180048b07  mov     rdi, rcx
0x180048b0a  test    rdx, rdx
0x180048b0d  jz      loc_180048CFA
0x180048b13  test    r8, r8
0x180048b16  jz      loc_180048CFA
0x180048b1c  mov     [r8], r13
0x180048b1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048b23  inc     rax
0x180048b26  cmp     [rdx+rax*2], r13w
0x180048b2b  jnz     short loc_180048B23
0x180048b2d  add     eax, eax
0x180048b2f  mov     [rbp+57h+var_A0], r13d
0x180048b33  cmp     eax, 64h ; 'd'
0x180048b36  mov     ecx, 3E8h
0x180048b3b  cmovl   eax, ecx
0x180048b3e  mov     ecx, eax
0x180048b40  mov     [rbp+57h+var_9C], eax
0x180048b43  add     rcx, rcx
0x180048b46  mov     eax, 0FFFFFFFFh
0x180048b4b  cmp     rcx, rax
0x180048b4e  jbe     short loc_180048B66
0x180048b50  mov     rax, r13
0x180048b53  mov     rcx, rax; pv
0x180048b56  call    cs:__imp_CoTaskMemFree
0x180048b5c  mov     eax, 8007000Eh
0x180048b61  jmp     loc_180048CFF
0x180048b66  mov     ecx, ecx; cb
0x180048b68  call    cs:__imp_CoTaskMemAlloc
0x180048b6e  mov     [rbp+57h+pv], rax
0x180048b72  test    rax, rax
0x180048b75  jz      short loc_180048B53
0x180048b77  mov     [rax], r13w
0x180048b7b  mov     esi, 25h ; '%'
0x180048b80  mov     [rdi], rbx
0x180048b83  cmp     [rbx], r13w
0x180048b87  jz      loc_180048CDE
0x180048b8d  cmp     [rbx], si
0x180048b90  jnz     loc_180048CC8
0x180048b96  mov     rcx, rbx; lpsz
0x180048b99  call    cs:__imp_CharNextW
0x180048b9f  mov     [rdi], rax
0x180048ba2  cmp     [rax], si
0x180048ba5  jnz     short loc_180048BCB
0x180048ba7  mov     rdx, rax; unsigned __int16 *
0x180048baa  mov     r8d, 1; int
0x180048bb0  lea     rcx, [rbp+57h+var_A0]; this
0x180048bb4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180048bb9  test    eax, eax
0x180048bbb  jnz     loc_180048CB4
0x180048bc1  mov     ebx, 8007000Eh
0x180048bc6  jmp     loc_180048CEC
0x180048bcb  mov     edx, esi; unsigned __int16
0x180048bcd  mov     rcx, rax; lpsz
0x180048bd0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180048bd5  mov     rsi, rax
0x180048bd8  test    rax, rax
0x180048bdb  jz      loc_180048CD7
0x180048be1  mov     rcx, rax
0x180048be4  sub     rcx, [rdi]
0x180048be7  sar     rcx, 1
0x180048bea  cmp     rcx, 1Fh
0x180048bee  jg      loc_180048CD0
0x180048bf4  mov     r8, [rdi]; Source
0x180048bf7  mov     edx, 20h ; ' '; SizeInWords
0x180048bfc  movsxd  r9, ecx; MaxCount
0x180048bff  lea     rcx, [rbp+57h+Destination]; Destination
0x180048c03  call    cs:__imp_wcsncpy_s
0x180048c09  mov     rbx, [rdi+8]
0x180048c0d  lea     r12, [rbx+20h]
0x180048c11  mov     rcx, r12; lpCriticalSection
0x180048c14  call    cs:__imp_EnterCriticalSection
0x180048c1a  lea     r14, [rbx+8]
0x180048c1e  mov     ebx, r13d
0x180048c21  cmp     ebx, [r14+10h]
0x180048c25  jge     short loc_180048C57
0x180048c27  mov     rcx, [r14]
0x180048c2a  lea     rdx, [rbp+57h+Destination]; lpString2
0x180048c2e  movsxd  rax, ebx
0x180048c31  mov     rcx, [rcx+rax*8]; lpString1
0x180048c35  call    cs:__imp_lstrcmpiW
0x180048c3b  test    eax, eax
0x180048c3d  jz      short loc_180048C43
0x180048c3f  inc     ebx
0x180048c41  jmp     short loc_180048C21
0x180048c43  cmp     ebx, 0FFFFFFFFh
0x180048c46  jz      short loc_180048C57
0x180048c48  mov     edx, ebx
0x180048c4a  mov     rcx, r14
0x180048c4d  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180048c52  mov     rbx, [rax]
0x180048c55  jmp     short loc_180048C5A
0x180048c57  mov     rbx, r13
0x180048c5a  mov     rcx, r12; lpCriticalSection
0x180048c5d  call    cs:__imp_LeaveCriticalSection
0x180048c63  test    rbx, rbx
0x180048c66  jz      short loc_180048CD7
0x180048c68  mov     [rbp+57h+var_90], r13
0x180048c6c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180048c70  inc     r8; int
0x180048c73  cmp     [rbx+r8*2], r13w
0x180048c78  jnz     short loc_180048C70
0x180048c7a  mov     rdx, rbx; unsigned __int16 *
0x180048c7d  lea     rcx, [rbp+57h+var_A0]; this
0x180048c81  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180048c86  lea     rcx, [rbp+57h+var_90]
0x180048c8a  mov     ebx, eax
0x180048c8c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180048c91  test    ebx, ebx
0x180048c93  jz      loc_180048BC1
0x180048c99  mov     rax, [rdi]
0x180048c9c  jmp     short loc_180048CAA
0x180048c9e  mov     rcx, rax; lpsz
0x180048ca1  call    cs:__imp_CharNextW
0x180048ca7  mov     [rdi], rax
0x180048caa  cmp     rax, rsi
0x180048cad  jnz     short loc_180048C9E
0x180048caf  mov     esi, 25h ; '%'
0x180048cb4  mov     rcx, [rdi]; lpsz
0x180048cb7  call    cs:__imp_CharNextW
0x180048cbd  mov     rbx, rax
0x180048cc0  mov     [rdi], rax
0x180048cc3  jmp     loc_180048B83
0x180048cc8  mov     rdx, rbx
0x180048ccb  jmp     loc_180048BAA
0x180048cd0  mov     ebx, 80004005h
0x180048cd5  jmp     short loc_180048CEC
0x180048cd7  mov     ebx, 80020009h
0x180048cdc  jmp     short loc_180048CEC
0x180048cde  mov     rcx, [rbp+57h+pv]
0x180048ce2  mov     ebx, r13d
0x180048ce5  mov     [r15], rcx
0x180048ce8  mov     [rbp+57h+pv], r13
0x180048cec  mov     rcx, [rbp+57h+pv]; pv
0x180048cf0  call    cs:__imp_CoTaskMemFree
0x180048cf6  mov     eax, ebx
0x180048cf8  jmp     short loc_180048CFF
0x180048cfa  mov     eax, 80004003h
0x180048cff  mov     rcx, [rbp+57h+var_40]
0x180048d03  xor     rcx, rsp; StackCookie
0x180048d06  call    __security_check_cookie
0x180048d0b  mov     rbx, [rsp+0C0h+arg_8]
0x180048d13  add     rsp, 90h
0x180048d1a  pop     r15
0x180048d1c  pop     r14
0x180048d1e  pop     r13
0x180048d20  pop     r12
0x180048d22  pop     rdi
0x180048d23  pop     rsi
0x180048d24  pop     rbp
0x180048d25  retn
```
