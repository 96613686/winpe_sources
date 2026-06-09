# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x14000b56c`
- end: `0x14000b7ac`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `576`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x14000b980`

## callees

- `0x1400093c4`
- `0x1400095c0`
- `0x140009e98`
- `0x140009f74`
- `0x14000ac5c`
- `0x14000b56c`
- `0x14000c8f8`
- `0x140113390`

## import_xrefs

- `USER32!CharNextW` at `0x14000b63c`
- `USER32!CharNextW` at `0x14000b715`
- `USER32!CharNextW` at `0x14000b73e`
- `USER32!CharNextW` at `0x14000b63c`
- `USER32!CharNextW` at `0x14000b715`
- `USER32!CharNextW` at `0x14000b73e`
- `msvcrt!wcsncpy_s` at `0x14000b68c`
- `msvcrt!wcsncpy_s` at `0x14000b68c`
- `KERNEL32!lstrcmpiW` at `0x14000b6b9`
- `KERNEL32!lstrcmpiW` at `0x14000b6b9`
- `ole32!CoTaskMemAlloc` at `0x14000b609`
- `ole32!CoTaskMemAlloc` at `0x14000b609`
- `ole32!CoTaskMemFree` at `0x14000b5f6`
- `ole32!CoTaskMemFree` at `0x14000b776`
- `ole32!CoTaskMemFree` at `0x14000b5f6`
- `ole32!CoTaskMemFree` at `0x14000b776`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, LPVOID *a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rsi
  __int64 v14; // rcx
  errno_t v15; // eax
  LPCWSTR v16; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  int v20; // ebx
  const WCHAR *j; // rax
  unsigned int v22; // ebx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v24[2]; // [rsp+28h] [rbp-41h] BYREF
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
  v24[0] = 0;
  LODWORD(cb) = 0;
  if ( (int)v7 < 100 )
    v7 = 1000;
  v24[1] = v7;
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
  for ( *this = v4; ; *this = v4 )
  {
    if ( !*v4 )
    {
      v22 = 0;
      *a3 = pv;
      pv = 0;
      goto LABEL_38;
    }
    if ( *v4 == 37 )
      break;
    v11 = v4;
LABEL_32:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v11, 1) )
    {
LABEL_36:
      v22 = -2147024882;
      goto LABEL_38;
    }
LABEL_33:
    v4 = CharNextW(*this);
  }
  v10 = CharNextW(v4);
  *this = v10;
  if ( *v10 == 37 )
  {
    v11 = v10;
    goto LABEL_32;
  }
  v12 = ATL::CRegParser::StrChrW(v10, 0x25u);
  v13 = v12;
  if ( v12 )
  {
    v14 = v12 - *this;
    if ( v14 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_38;
    }
    v15 = wcsncpy_s(Destination, 0x20u, *this, (int)v14);
    ATL::AtlCrtErrorCheck(v15);
    v16 = this[1];
    for ( i = 0; (signed int)i < *((_DWORD *)v16 + 6); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v16 + 1) + 8LL * (int)i), Destination) )
      {
        if ( i == -1 )
          break;
        v18 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                            v16 + 4,
                                            i);
        if ( !v18 )
          break;
        cb = 0;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v20 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v18, v19);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
        if ( v20 )
        {
          for ( j = *this; j != v13; *this = j )
            j = CharNextW(j);
          goto LABEL_33;
        }
        goto LABEL_36;
      }
    }
  }
  v22 = -2147352567;
LABEL_38:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x14000b56c  mov     [rsp-8+arg_8], rbx
0x14000b571  push    rbp
0x14000b572  push    rsi
0x14000b573  push    rdi
0x14000b574  push    r12
0x14000b576  push    r13
0x14000b578  push    r14
0x14000b57a  push    r15
0x14000b57c  lea     rbp, [rsp-27h]
0x14000b581  sub     rsp, 90h
0x14000b588  mov     rax, cs:__security_cookie
0x14000b58f  xor     rax, rsp
0x14000b592  mov     [rbp+57h+var_40], rax
0x14000b596  xor     r12d, r12d
0x14000b599  mov     r15, r8
0x14000b59c  mov     rbx, rdx
0x14000b59f  mov     rdi, rcx
0x14000b5a2  test    rdx, rdx
0x14000b5a5  jz      loc_14000B780
0x14000b5ab  test    r8, r8
0x14000b5ae  jz      loc_14000B780
0x14000b5b4  mov     [r8], r12
0x14000b5b7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000b5bb  inc     rdx
0x14000b5be  cmp     [rbx+rdx*2], r12w
0x14000b5c3  jnz     short loc_14000B5BB
0x14000b5c5  add     edx, edx
0x14000b5c7  mov     [rbp+57h+var_98], r12d
0x14000b5cb  mov     eax, 3E8h
0x14000b5d0  mov     dword ptr [rbp+57h+cb], r12d
0x14000b5d4  cmp     edx, 64h ; 'd'
0x14000b5d7  lea     rcx, [rbp+57h+cb]
0x14000b5db  mov     r8d, 2
0x14000b5e1  cmovl   edx, eax
0x14000b5e4  mov     [rbp+57h+var_94], edx
0x14000b5e7  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x14000b5ec  test    eax, eax
0x14000b5ee  jns     short loc_14000B606
0x14000b5f0  mov     rax, r12
0x14000b5f3  mov     rcx, rax; pv
0x14000b5f6  call    cs:__imp_CoTaskMemFree
0x14000b5fc  mov     eax, 8007000Eh
0x14000b601  jmp     loc_14000B785
0x14000b606  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x14000b609  call    cs:__imp_CoTaskMemAlloc
0x14000b60f  mov     [rbp+57h+pv], rax
0x14000b613  test    rax, rax
0x14000b616  jz      short loc_14000B5F3
0x14000b618  mov     [rax], r12w
0x14000b61c  mov     r13d, 25h ; '%'
0x14000b622  mov     [rdi], rbx
0x14000b625  cmp     [rbx], r12w
0x14000b629  jz      loc_14000B764
0x14000b62f  cmp     [rbx], r13w
0x14000b633  jnz     loc_14000B725
0x14000b639  mov     rcx, rbx; lpsz
0x14000b63c  call    cs:__imp_CharNextW
0x14000b642  mov     [rdi], rax
0x14000b645  cmp     [rax], r13w
0x14000b649  jnz     short loc_14000B653
0x14000b64b  mov     rdx, rax
0x14000b64e  jmp     loc_14000B728
0x14000b653  mov     edx, r13d; unsigned __int16
0x14000b656  mov     rcx, rax; lpsz
0x14000b659  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x14000b65e  mov     rsi, rax
0x14000b661  test    rax, rax
0x14000b664  jz      loc_14000B756
0x14000b66a  mov     rcx, rax
0x14000b66d  sub     rcx, [rdi]
0x14000b670  sar     rcx, 1
0x14000b673  cmp     rcx, 1Fh
0x14000b677  jg      loc_14000B74F
0x14000b67d  mov     r8, [rdi]; Source
0x14000b680  mov     edx, 20h ; ' '; SizeInWords
0x14000b685  movsxd  r9, ecx; MaxCount
0x14000b688  lea     rcx, [rbp+57h+Destination]; Destination
0x14000b68c  call    cs:__imp_wcsncpy_s
0x14000b692  mov     ecx, eax; int
0x14000b694  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000b699  mov     r14, [rdi+8]
0x14000b69d  mov     ebx, r12d
0x14000b6a0  cmp     ebx, [r14+18h]
0x14000b6a4  jge     loc_14000B756
0x14000b6aa  mov     rcx, [r14+8]
0x14000b6ae  lea     rdx, [rbp+57h+Destination]; lpString2
0x14000b6b2  movsxd  rax, ebx
0x14000b6b5  mov     rcx, [rcx+rax*8]; lpString1
0x14000b6b9  call    cs:__imp_lstrcmpiW
0x14000b6bf  test    eax, eax
0x14000b6c1  jz      short loc_14000B6C7
0x14000b6c3  inc     ebx
0x14000b6c5  jmp     short loc_14000B6A0
0x14000b6c7  cmp     ebx, 0FFFFFFFFh
0x14000b6ca  jz      loc_14000B756
0x14000b6d0  mov     edx, ebx
0x14000b6d2  lea     rcx, [r14+8]
0x14000b6d6  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x14000b6db  mov     rdx, [rax]; unsigned __int16 *
0x14000b6de  test    rdx, rdx
0x14000b6e1  jz      short loc_14000B756
0x14000b6e3  mov     [rbp+57h+cb], r12
0x14000b6e7  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000b6eb  inc     r8; int
0x14000b6ee  cmp     [rdx+r8*2], r12w
0x14000b6f3  jnz     short loc_14000B6EB
0x14000b6f5  lea     rcx, [rbp+57h+var_98]; this
0x14000b6f9  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14000b6fe  lea     rcx, [rbp+57h+cb]
0x14000b702  mov     ebx, eax
0x14000b704  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14000b709  test    ebx, ebx
0x14000b70b  jz      short loc_14000B75D
0x14000b70d  mov     rax, [rdi]
0x14000b710  jmp     short loc_14000B71E
0x14000b712  mov     rcx, rax; lpsz
0x14000b715  call    cs:__imp_CharNextW
0x14000b71b  mov     [rdi], rax
0x14000b71e  cmp     rax, rsi
0x14000b721  jnz     short loc_14000B712
0x14000b723  jmp     short loc_14000B73B
0x14000b725  mov     rdx, rbx; unsigned __int16 *
0x14000b728  mov     r8d, 1; int
0x14000b72e  lea     rcx, [rbp+57h+var_98]; this
0x14000b732  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14000b737  test    eax, eax
0x14000b739  jz      short loc_14000B75D
0x14000b73b  mov     rcx, [rdi]; lpsz
0x14000b73e  call    cs:__imp_CharNextW
0x14000b744  mov     rbx, rax
0x14000b747  mov     [rdi], rax
0x14000b74a  jmp     loc_14000B625
0x14000b74f  mov     ebx, 80004005h
0x14000b754  jmp     short loc_14000B772
0x14000b756  mov     ebx, 80020009h
0x14000b75b  jmp     short loc_14000B772
0x14000b75d  mov     ebx, 8007000Eh
0x14000b762  jmp     short loc_14000B772
0x14000b764  mov     rcx, [rbp+57h+pv]
0x14000b768  mov     ebx, r12d
0x14000b76b  mov     [r15], rcx
0x14000b76e  mov     [rbp+57h+pv], r12
0x14000b772  mov     rcx, [rbp+57h+pv]; pv
0x14000b776  call    cs:__imp_CoTaskMemFree
0x14000b77c  mov     eax, ebx
0x14000b77e  jmp     short loc_14000B785
0x14000b780  mov     eax, 80004003h
0x14000b785  mov     rcx, [rbp+57h+var_40]
0x14000b789  xor     rcx, rsp; StackCookie
0x14000b78c  call    __security_check_cookie
0x14000b791  mov     rbx, [rsp+0C0h+arg_8]
0x14000b799  add     rsp, 90h
0x14000b7a0  pop     r15
0x14000b7a2  pop     r14
0x14000b7a4  pop     r13
0x14000b7a6  pop     r12
0x14000b7a8  pop     rdi
0x14000b7a9  pop     rsi
0x14000b7aa  pop     rbp
0x14000b7ab  retn
```
