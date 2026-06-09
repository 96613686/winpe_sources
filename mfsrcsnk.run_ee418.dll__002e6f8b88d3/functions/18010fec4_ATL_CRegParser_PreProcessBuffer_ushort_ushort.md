# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18010fec4`
- end: `0x18011011d`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `601`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801108ec`

## callees

- `0x1801099f0`
- `0x18010b218`
- `0x18010d120`
- `0x18010d374`
- `0x18010fb08`
- `0x18010fec4`
- `0x180111e44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18010fff3`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18010fff3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180110054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180110054`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011000b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011000b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18010ff89`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180110098`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801100ae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18010ff89`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180110098`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801100ae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18011002c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18011002c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010ff58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010ff58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010ff46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801100e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010ff46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801100e7`

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
0x18010fec4  mov     [rsp-8+arg_8], rbx
0x18010fec9  push    rbp
0x18010feca  push    rsi
0x18010fecb  push    rdi
0x18010fecc  push    r12
0x18010fece  push    r13
0x18010fed0  push    r14
0x18010fed2  push    r15
0x18010fed4  lea     rbp, [rsp-27h]
0x18010fed9  sub     rsp, 90h
0x18010fee0  mov     rax, cs:__security_cookie
0x18010fee7  xor     rax, rsp
0x18010feea  mov     [rbp+57h+var_40], rax
0x18010feee  xor     r13d, r13d
0x18010fef1  mov     r15, r8
0x18010fef4  mov     rbx, rdx
0x18010fef7  mov     rdi, rcx
0x18010fefa  test    rdx, rdx
0x18010fefd  jz      loc_1801100F1
0x18010ff03  test    r8, r8
0x18010ff06  jz      loc_1801100F1
0x18010ff0c  mov     [r8], r13
0x18010ff0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010ff13  inc     rax
0x18010ff16  cmp     [rdx+rax*2], r13w
0x18010ff1b  jnz     short loc_18010FF13
0x18010ff1d  add     eax, eax
0x18010ff1f  mov     [rbp+57h+var_A0], r13d
0x18010ff23  cmp     eax, 64h ; 'd'
0x18010ff26  mov     ecx, 3E8h
0x18010ff2b  cmovl   eax, ecx
0x18010ff2e  mov     ecx, eax
0x18010ff30  mov     [rbp+57h+var_9C], eax
0x18010ff33  add     rcx, rcx
0x18010ff36  mov     eax, 0FFFFFFFFh
0x18010ff3b  cmp     rcx, rax
0x18010ff3e  jbe     short loc_18010FF56
0x18010ff40  mov     rax, r13
0x18010ff43  mov     rcx, rax; pv
0x18010ff46  call    cs:__imp_CoTaskMemFree
0x18010ff4c  mov     eax, 8007000Eh
0x18010ff51  jmp     loc_1801100F6
0x18010ff56  mov     ecx, ecx; cb
0x18010ff58  call    cs:__imp_CoTaskMemAlloc
0x18010ff5e  mov     [rbp+57h+pv], rax
0x18010ff62  test    rax, rax
0x18010ff65  jz      short loc_18010FF43
0x18010ff67  mov     [rax], r13w
0x18010ff6b  mov     esi, 25h ; '%'
0x18010ff70  mov     [rdi], rbx
0x18010ff73  cmp     [rbx], r13w
0x18010ff77  jz      loc_1801100D5
0x18010ff7d  cmp     [rbx], si
0x18010ff80  jnz     loc_1801100BF
0x18010ff86  mov     rcx, rbx; lpsz
0x18010ff89  call    cs:__imp_CharNextW
0x18010ff8f  mov     [rdi], rax
0x18010ff92  cmp     [rax], si
0x18010ff95  jnz     short loc_18010FFBB
0x18010ff97  mov     rdx, rax; unsigned __int16 *
0x18010ff9a  mov     r8d, 1; int
0x18010ffa0  lea     rcx, [rbp+57h+var_A0]; this
0x18010ffa4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18010ffa9  test    eax, eax
0x18010ffab  jnz     loc_1801100AB
0x18010ffb1  mov     ebx, 8007000Eh
0x18010ffb6  jmp     loc_1801100E3
0x18010ffbb  mov     edx, esi; unsigned __int16
0x18010ffbd  mov     rcx, rax; lpsz
0x18010ffc0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18010ffc5  mov     rsi, rax
0x18010ffc8  test    rax, rax
0x18010ffcb  jz      loc_1801100CE
0x18010ffd1  mov     rcx, rax
0x18010ffd4  sub     rcx, [rdi]
0x18010ffd7  sar     rcx, 1
0x18010ffda  cmp     rcx, 1Fh
0x18010ffde  jg      loc_1801100C7
0x18010ffe4  mov     r8, [rdi]
0x18010ffe7  mov     edx, 20h ; ' '
0x18010ffec  movsxd  r9, ecx
0x18010ffef  lea     rcx, [rbp+57h+String2]
0x18010fff3  call    cs:__imp__o_wcsncpy_s
0x18010fff9  mov     ecx, eax; int
0x18010fffb  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180110000  mov     rbx, [rdi+8]
0x180110004  lea     r12, [rbx+20h]
0x180110008  mov     rcx, r12; lpCriticalSection
0x18011000b  call    cs:__imp_EnterCriticalSection
0x180110011  lea     r14, [rbx+8]
0x180110015  mov     ebx, r13d
0x180110018  cmp     ebx, [r14+10h]
0x18011001c  jge     short loc_18011004E
0x18011001e  mov     rcx, [r14]
0x180110021  lea     rdx, [rbp+57h+String2]; lpString2
0x180110025  movsxd  rax, ebx
0x180110028  mov     rcx, [rcx+rax*8]; lpString1
0x18011002c  call    cs:__imp_lstrcmpiW
0x180110032  test    eax, eax
0x180110034  jz      short loc_18011003A
0x180110036  inc     ebx
0x180110038  jmp     short loc_180110018
0x18011003a  cmp     ebx, 0FFFFFFFFh
0x18011003d  jz      short loc_18011004E
0x18011003f  mov     edx, ebx
0x180110041  mov     rcx, r14
0x180110044  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180110049  mov     rbx, [rax]
0x18011004c  jmp     short loc_180110051
0x18011004e  mov     rbx, r13
0x180110051  mov     rcx, r12; lpCriticalSection
0x180110054  call    cs:__imp_LeaveCriticalSection
0x18011005a  test    rbx, rbx
0x18011005d  jz      short loc_1801100CE
0x18011005f  mov     [rbp+57h+var_90], r13
0x180110063  or      r8, 0FFFFFFFFFFFFFFFFh
0x180110067  inc     r8; int
0x18011006a  cmp     [rbx+r8*2], r13w
0x18011006f  jnz     short loc_180110067
0x180110071  mov     rdx, rbx; unsigned __int16 *
0x180110074  lea     rcx, [rbp+57h+var_A0]; this
0x180110078  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18011007d  lea     rcx, [rbp+57h+var_90]
0x180110081  mov     ebx, eax
0x180110083  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180110088  test    ebx, ebx
0x18011008a  jz      loc_18010FFB1
0x180110090  mov     rax, [rdi]
0x180110093  jmp     short loc_1801100A1
0x180110095  mov     rcx, rax; lpsz
0x180110098  call    cs:__imp_CharNextW
0x18011009e  mov     [rdi], rax
0x1801100a1  cmp     rax, rsi
0x1801100a4  jnz     short loc_180110095
0x1801100a6  mov     esi, 25h ; '%'
0x1801100ab  mov     rcx, [rdi]; lpsz
0x1801100ae  call    cs:__imp_CharNextW
0x1801100b4  mov     rbx, rax
0x1801100b7  mov     [rdi], rax
0x1801100ba  jmp     loc_18010FF73
0x1801100bf  mov     rdx, rbx
0x1801100c2  jmp     loc_18010FF9A
0x1801100c7  mov     ebx, 80004005h
0x1801100cc  jmp     short loc_1801100E3
0x1801100ce  mov     ebx, 80020009h
0x1801100d3  jmp     short loc_1801100E3
0x1801100d5  mov     rcx, [rbp+57h+pv]
0x1801100d9  mov     ebx, r13d
0x1801100dc  mov     [r15], rcx
0x1801100df  mov     [rbp+57h+pv], r13
0x1801100e3  mov     rcx, [rbp+57h+pv]; pv
0x1801100e7  call    cs:__imp_CoTaskMemFree
0x1801100ed  mov     eax, ebx
0x1801100ef  jmp     short loc_1801100F6
0x1801100f1  mov     eax, 80004003h
0x1801100f6  mov     rcx, [rbp+57h+var_40]
0x1801100fa  xor     rcx, rsp; StackCookie
0x1801100fd  call    __security_check_cookie
0x180110102  mov     rbx, [rsp+0C0h+arg_8]
0x18011010a  add     rsp, 90h
0x180110111  pop     r15
0x180110113  pop     r14
0x180110115  pop     r13
0x180110117  pop     r12
0x180110119  pop     rdi
0x18011011a  pop     rsi
0x18011011b  pop     rbp
0x18011011c  retn
```
