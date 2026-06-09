# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800051d4`
- end: `0x180005441`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `__int64 __fastcall(const wchar_t **this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000576c`

## callees

- `0x180002b4c`
- `0x180002f64`
- `0x1800040a8`
- `0x180004184`
- `0x180004e4c`
- `0x1800051d4`
- `0x1800065c0`
- `0x180031680`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180005317`
- `msvcrt!wcsncpy_s` at `0x180005317`
- `KERNEL32!EnterCriticalSection` at `0x18000532f`
- `KERNEL32!EnterCriticalSection` at `0x18000532f`
- `KERNEL32!LeaveCriticalSection` at `0x180005378`
- `KERNEL32!LeaveCriticalSection` at `0x180005378`
- `KERNEL32!lstrcmpiW` at `0x180005350`
- `KERNEL32!lstrcmpiW` at `0x180005350`
- `USER32!CharNextW` at `0x1800052ad`
- `USER32!CharNextW` at `0x1800053bc`
- `USER32!CharNextW` at `0x1800053d2`
- `USER32!CharNextW` at `0x1800052ad`
- `USER32!CharNextW` at `0x1800053bc`
- `USER32!CharNextW` at `0x1800053d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000527f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000540b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000527f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000540b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005264`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005264`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  unsigned __int16 *v25; // rcx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v27[2]; // [rsp+28h] [rbp-41h] BYREF
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
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v11 = v4;
LABEL_18:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v11, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v10 = CharNextW(v4);
    *this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_18;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_39;
    v15 = v13 - *this;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_41;
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
    for ( j = *this; j != v14; *this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v12 = 0;
  v25 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v25;
LABEL_41:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x1800051d4  mov     [rsp-8+arg_8], rbx
0x1800051d9  push    rbp
0x1800051da  push    rsi
0x1800051db  push    rdi
0x1800051dc  push    r12
0x1800051de  push    r13
0x1800051e0  push    r14
0x1800051e2  push    r15
0x1800051e4  lea     rbp, [rsp-27h]
0x1800051e9  sub     rsp, 90h
0x1800051f0  mov     rax, cs:__security_cookie
0x1800051f7  xor     rax, rsp
0x1800051fa  mov     [rbp+57h+var_40], rax
0x1800051fe  mov     r15, r8
0x180005201  mov     rbx, rdx
0x180005204  mov     rdi, rcx
0x180005207  xor     r13d, r13d
0x18000520a  test    rdx, rdx
0x18000520d  jz      loc_180005415
0x180005213  test    r8, r8
0x180005216  jz      loc_180005415
0x18000521c  mov     [r8], r13
0x18000521f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005223  inc     rdx
0x180005226  cmp     [rbx+rdx*2], r13w
0x18000522b  jnz     short loc_180005223
0x18000522d  add     edx, edx
0x18000522f  mov     eax, 3E8h
0x180005234  cmp     edx, 64h ; 'd'
0x180005237  cmovl   edx, eax
0x18000523a  mov     [rbp+57h+var_98], r13d
0x18000523e  mov     [rbp+57h+var_94], edx
0x180005241  mov     dword ptr [rbp+57h+cb], r13d
0x180005245  mov     r8d, 2
0x18000524b  lea     rcx, [rbp+57h+cb]
0x18000524f  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180005254  test    eax, eax
0x180005256  jns     short loc_180005261
0x180005258  mov     rax, r13
0x18000525b  mov     [rbp+57h+pv], r13
0x18000525f  jmp     short loc_180005277
0x180005261  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180005264  call    cs:__imp_CoTaskMemAlloc
0x18000526a  mov     [rbp+57h+pv], rax
0x18000526e  test    rax, rax
0x180005271  jz      short loc_180005277
0x180005273  mov     [rax], r13w
0x180005277  test    rax, rax
0x18000527a  jnz     short loc_18000528F
0x18000527c  mov     rcx, rax; pv
0x18000527f  call    cs:__imp_CoTaskMemFree
0x180005285  mov     eax, 8007000Eh
0x18000528a  jmp     loc_18000541A
0x18000528f  mov     [rdi], rbx
0x180005292  mov     esi, 25h ; '%'
0x180005297  cmp     [rbx], r13w
0x18000529b  jz      loc_1800053F9
0x1800052a1  cmp     [rbx], si
0x1800052a4  jnz     loc_1800053E3
0x1800052aa  mov     rcx, rbx; lpsz
0x1800052ad  call    cs:__imp_CharNextW
0x1800052b3  mov     [rdi], rax
0x1800052b6  cmp     [rax], si
0x1800052b9  jnz     short loc_1800052DF
0x1800052bb  mov     rdx, rax; unsigned __int16 *
0x1800052be  mov     r8d, 1; int
0x1800052c4  lea     rcx, [rbp+57h+var_98]; this
0x1800052c8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800052cd  test    eax, eax
0x1800052cf  jnz     loc_1800053CF
0x1800052d5  mov     ebx, 8007000Eh
0x1800052da  jmp     loc_180005407
0x1800052df  mov     edx, esi; unsigned __int16
0x1800052e1  mov     rcx, rax; lpsz
0x1800052e4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800052e9  mov     rsi, rax
0x1800052ec  test    rax, rax
0x1800052ef  jz      loc_1800053F2
0x1800052f5  mov     rcx, rax
0x1800052f8  sub     rcx, [rdi]
0x1800052fb  sar     rcx, 1
0x1800052fe  cmp     rcx, 1Fh
0x180005302  jg      loc_1800053EB
0x180005308  movsxd  r9, ecx; MaxCount
0x18000530b  mov     r8, [rdi]; Source
0x18000530e  mov     edx, 20h ; ' '; SizeInWords
0x180005313  lea     rcx, [rbp+57h+Destination]; Destination
0x180005317  call    cs:__imp_wcsncpy_s
0x18000531d  mov     ecx, eax; int
0x18000531f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005324  mov     rbx, [rdi+8]
0x180005328  lea     r12, [rbx+20h]
0x18000532c  mov     rcx, r12; lpCriticalSection
0x18000532f  call    cs:__imp_EnterCriticalSection
0x180005335  lea     r14, [rbx+8]
0x180005339  mov     ebx, r13d
0x18000533c  cmp     ebx, [r14+10h]
0x180005340  jge     short loc_180005372
0x180005342  movsxd  rax, ebx
0x180005345  mov     rcx, [r14]
0x180005348  lea     rdx, [rbp+57h+Destination]; lpString2
0x18000534c  mov     rcx, [rcx+rax*8]; lpString1
0x180005350  call    cs:__imp_lstrcmpiW
0x180005356  test    eax, eax
0x180005358  jz      short loc_18000535E
0x18000535a  inc     ebx
0x18000535c  jmp     short loc_18000533C
0x18000535e  cmp     ebx, 0FFFFFFFFh
0x180005361  jz      short loc_180005372
0x180005363  mov     edx, ebx
0x180005365  mov     rcx, r14
0x180005368  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000536d  mov     rbx, [rax]
0x180005370  jmp     short loc_180005375
0x180005372  mov     rbx, r13
0x180005375  mov     rcx, r12; lpCriticalSection
0x180005378  call    cs:__imp_LeaveCriticalSection
0x18000537e  test    rbx, rbx
0x180005381  jz      short loc_1800053F2
0x180005383  mov     [rbp+57h+cb], r13
0x180005387  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000538b  inc     r8; int
0x18000538e  cmp     [rbx+r8*2], r13w
0x180005393  jnz     short loc_18000538B
0x180005395  mov     rdx, rbx; unsigned __int16 *
0x180005398  lea     rcx, [rbp+57h+var_98]; this
0x18000539c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800053a1  mov     ebx, eax
0x1800053a3  lea     rcx, [rbp+57h+cb]
0x1800053a7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800053ac  test    ebx, ebx
0x1800053ae  jz      loc_1800052D5
0x1800053b4  mov     rax, [rdi]
0x1800053b7  jmp     short loc_1800053C5
0x1800053b9  mov     rcx, rax; lpsz
0x1800053bc  call    cs:__imp_CharNextW
0x1800053c2  mov     [rdi], rax
0x1800053c5  cmp     rax, rsi
0x1800053c8  jnz     short loc_1800053B9
0x1800053ca  mov     esi, 25h ; '%'
0x1800053cf  mov     rcx, [rdi]; lpsz
0x1800053d2  call    cs:__imp_CharNextW
0x1800053d8  mov     rbx, rax
0x1800053db  mov     [rdi], rax
0x1800053de  jmp     loc_180005297
0x1800053e3  mov     rdx, rbx
0x1800053e6  jmp     loc_1800052BE
0x1800053eb  mov     ebx, 80004005h
0x1800053f0  jmp     short loc_180005407
0x1800053f2  mov     ebx, 80020009h
0x1800053f7  jmp     short loc_180005407
0x1800053f9  mov     ebx, r13d
0x1800053fc  mov     rcx, [rbp+57h+pv]
0x180005400  mov     [rbp+57h+pv], r13
0x180005404  mov     [r15], rcx
0x180005407  mov     rcx, [rbp+57h+pv]; pv
0x18000540b  call    cs:__imp_CoTaskMemFree
0x180005411  mov     eax, ebx
0x180005413  jmp     short loc_18000541A
0x180005415  mov     eax, 80004003h
0x18000541a  mov     rcx, [rbp+57h+var_40]
0x18000541e  xor     rcx, rsp; StackCookie
0x180005421  call    __security_check_cookie
0x180005426  mov     rbx, [rsp+0C0h+arg_8]
0x18000542e  add     rsp, 90h
0x180005435  pop     r15
0x180005437  pop     r14
0x180005439  pop     r13
0x18000543b  pop     r12
0x18000543d  pop     rdi
0x18000543e  pop     rsi
0x18000543f  pop     rbp
0x180005440  retn
```
