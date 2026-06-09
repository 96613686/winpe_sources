# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180010870`
- end: `0x180010a93`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010ccc`

## callees

- `0x18000adb0`
- `0x18000ee7c`
- `0x18000f0c0`
- `0x180010870`
- `0x180011a60`
- `0x180011ab8`
- `0x18002e230`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18001099c`
- `msvcrt!wcsncpy_s` at `0x18001099c`
- `USER32!CharNextW` at `0x18001094c`
- `USER32!CharNextW` at `0x1800109f4`
- `USER32!CharNextW` at `0x180010a1d`
- `USER32!CharNextW` at `0x18001094c`
- `USER32!CharNextW` at `0x1800109f4`
- `USER32!CharNextW` at `0x180010a1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001091a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001091a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800108fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800108fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  errno_t v18; // eax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  _DWORD v24[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-19h] BYREF

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
  v24[0] = 0;
  v24[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_31:
    v23 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_32;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_28:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v14, 1) )
      goto LABEL_35;
LABEL_29:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_31;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_28;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_34;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_32;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *(const wchar_t **)this, (int)v17);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), Destination);
  if ( !v19 )
  {
LABEL_34:
    v23 = -2147352567;
    goto LABEL_32;
  }
  v26 = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v19, v20);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v26);
  if ( v21 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_29;
  }
LABEL_35:
  v23 = -2147024882;
LABEL_32:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x180010870  mov     [rsp-8+arg_8], rbx
0x180010875  mov     [rsp-8+arg_18], rsi
0x18001087a  push    rbp
0x18001087b  push    rdi
0x18001087c  push    r12
0x18001087e  push    r14
0x180010880  push    r15
0x180010882  lea     rbp, [rsp-37h]
0x180010887  sub     rsp, 90h
0x18001088e  mov     rax, cs:__security_cookie
0x180010895  xor     rax, rsp
0x180010898  mov     [rbp+57h+var_30], rax
0x18001089c  mov     r14, r8
0x18001089f  mov     rbx, rdx
0x1800108a2  mov     rdi, rcx
0x1800108a5  xor     r15d, r15d
0x1800108a8  test    rdx, rdx
0x1800108ab  jz      loc_180010A66
0x1800108b1  test    r8, r8
0x1800108b4  jz      loc_180010A66
0x1800108ba  mov     [r8], r15
0x1800108bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800108c1  inc     rax
0x1800108c4  cmp     [rdx+rax*2], r15w
0x1800108c9  jnz     short loc_1800108C1
0x1800108cb  add     eax, eax
0x1800108cd  mov     ecx, 3E8h
0x1800108d2  cmp     eax, 64h ; 'd'
0x1800108d5  cmovl   eax, ecx
0x1800108d8  mov     [rbp+57h+var_90], r15d
0x1800108dc  mov     [rbp+57h+var_8C], eax
0x1800108df  mov     ecx, eax
0x1800108e1  add     rcx, rcx
0x1800108e4  mov     eax, 0FFFFFFFFh
0x1800108e9  cmp     rcx, rax
0x1800108ec  jbe     short loc_1800108FA
0x1800108ee  mov     rax, r15
0x1800108f1  mov     rdx, r15
0x1800108f4  mov     [rbp+57h+pv], rdx
0x1800108f8  jmp     short loc_180010912
0x1800108fa  mov     ecx, ecx; cb
0x1800108fc  call    cs:__imp_CoTaskMemAlloc
0x180010902  mov     rdx, rax
0x180010905  mov     [rbp+57h+pv], rax
0x180010909  test    rax, rax
0x18001090c  jz      short loc_180010912
0x18001090e  mov     [rax], r15w
0x180010912  test    rax, rax
0x180010915  jnz     short loc_18001092A
0x180010917  mov     rcx, rax; pv
0x18001091a  call    cs:__imp_CoTaskMemFree
0x180010920  mov     eax, 8007000Eh
0x180010925  jmp     loc_180010A6B
0x18001092a  mov     [rdi], rbx
0x18001092d  movzx   eax, word ptr [rbx]
0x180010930  test    ax, ax
0x180010933  jz      loc_180010A39
0x180010939  mov     r12d, 25h ; '%'
0x18001093f  cmp     ax, r12w
0x180010943  jnz     loc_180010A04
0x180010949  mov     rcx, rbx; lpsz
0x18001094c  call    cs:__imp_CharNextW
0x180010952  mov     [rdi], rax
0x180010955  cmp     [rax], r12w
0x180010959  jnz     short loc_180010963
0x18001095b  mov     rdx, rax
0x18001095e  jmp     loc_180010A07
0x180010963  mov     edx, r12d; unsigned __int16
0x180010966  mov     rcx, rax; lpsz
0x180010969  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001096e  mov     rsi, rax
0x180010971  test    rax, rax
0x180010974  jz      loc_180010A58
0x18001097a  mov     rcx, rax
0x18001097d  sub     rcx, [rdi]
0x180010980  sar     rcx, 1
0x180010983  cmp     rcx, 1Fh
0x180010987  jg      loc_180010A51
0x18001098d  movsxd  r9, ecx; MaxCount
0x180010990  mov     r8, [rdi]; Source
0x180010993  mov     edx, 20h ; ' '; SizeInWords
0x180010998  lea     rcx, [rbp+57h+Destination]; Destination
0x18001099c  call    cs:__imp_wcsncpy_s
0x1800109a2  mov     ecx, eax; int
0x1800109a4  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800109a9  lea     rdx, [rbp+57h+Destination]; unsigned __int16 *
0x1800109ad  mov     rcx, [rdi+8]; this
0x1800109b1  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x1800109b6  test    rax, rax
0x1800109b9  jz      loc_180010A58
0x1800109bf  mov     [rbp+57h+var_80], r15
0x1800109c3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800109c7  inc     r8; int
0x1800109ca  cmp     [rax+r8*2], r15w
0x1800109cf  jnz     short loc_1800109C7
0x1800109d1  mov     rdx, rax; unsigned __int16 *
0x1800109d4  lea     rcx, [rbp+57h+var_90]; this
0x1800109d8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800109dd  mov     ebx, eax
0x1800109df  lea     rcx, [rbp+57h+var_80]
0x1800109e3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800109e8  test    ebx, ebx
0x1800109ea  jz      short loc_180010A5F
0x1800109ec  mov     rax, [rdi]
0x1800109ef  jmp     short loc_1800109FD
0x1800109f1  mov     rcx, rax; lpsz
0x1800109f4  call    cs:__imp_CharNextW
0x1800109fa  mov     [rdi], rax
0x1800109fd  cmp     rax, rsi
0x180010a00  jnz     short loc_1800109F1
0x180010a02  jmp     short loc_180010A1A
0x180010a04  mov     rdx, rbx; unsigned __int16 *
0x180010a07  mov     r8d, 1; int
0x180010a0d  lea     rcx, [rbp+57h+var_90]; this
0x180010a11  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180010a16  test    eax, eax
0x180010a18  jz      short loc_180010A5F
0x180010a1a  mov     rcx, [rdi]; lpsz
0x180010a1d  call    cs:__imp_CharNextW
0x180010a23  mov     rbx, rax
0x180010a26  mov     [rdi], rax
0x180010a29  movzx   eax, word ptr [rax]
0x180010a2c  test    ax, ax
0x180010a2f  jnz     loc_18001093F
0x180010a35  mov     rdx, [rbp+57h+pv]
0x180010a39  mov     ebx, r15d
0x180010a3c  mov     [rbp+57h+pv], r15
0x180010a40  mov     [r14], rdx
0x180010a43  mov     rcx, [rbp+57h+pv]; pv
0x180010a47  call    cs:__imp_CoTaskMemFree
0x180010a4d  mov     eax, ebx
0x180010a4f  jmp     short loc_180010A6B
0x180010a51  mov     ebx, 80004005h
0x180010a56  jmp     short loc_180010A43
0x180010a58  mov     ebx, 80020009h
0x180010a5d  jmp     short loc_180010A43
0x180010a5f  mov     ebx, 8007000Eh
0x180010a64  jmp     short loc_180010A43
0x180010a66  mov     eax, 80004003h
0x180010a6b  mov     rcx, [rbp+57h+var_30]
0x180010a6f  xor     rcx, rsp; StackCookie
0x180010a72  call    __security_check_cookie
0x180010a77  lea     r11, [rsp+0B0h+var_20]
0x180010a7f  mov     rbx, [r11+38h]
0x180010a83  mov     rsi, [r11+48h]
0x180010a87  mov     rsp, r11
0x180010a8a  pop     r15
0x180010a8c  pop     r14
0x180010a8e  pop     r12
0x180010a90  pop     rdi
0x180010a91  pop     rbp
0x180010a92  retn
```
