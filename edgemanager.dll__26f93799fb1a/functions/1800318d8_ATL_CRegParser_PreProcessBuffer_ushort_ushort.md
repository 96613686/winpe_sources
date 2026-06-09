# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800318d8`
- end: `0x180031b45`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031ecc`

## callees

- `0x18002b530`
- `0x18002d340`
- `0x18002e130`
- `0x18002f378`
- `0x18002f5e0`
- `0x1800313a4`
- `0x1800318d8`
- `0x18003316c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180031a1b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180031a1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031a7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031a7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031a33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031a33`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800319b1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180031ac0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180031ad6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800319b1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180031ac0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180031ad6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180031a54`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180031a54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031b0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031b0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031968`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031968`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
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
  int v16; // eax
  __int64 v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  __int64 v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v25; // rcx
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
    for ( j = *(const WCHAR **)this; j != v14; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
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
0x1800318d8  mov     [rsp-8+arg_8], rbx
0x1800318dd  push    rbp
0x1800318de  push    rsi
0x1800318df  push    rdi
0x1800318e0  push    r12
0x1800318e2  push    r13
0x1800318e4  push    r14
0x1800318e6  push    r15
0x1800318e8  lea     rbp, [rsp-27h]
0x1800318ed  sub     rsp, 90h
0x1800318f4  mov     rax, cs:__security_cookie
0x1800318fb  xor     rax, rsp
0x1800318fe  mov     [rbp+57h+var_40], rax
0x180031902  mov     r15, r8
0x180031905  mov     rbx, rdx
0x180031908  mov     rdi, rcx
0x18003190b  xor     r13d, r13d
0x18003190e  test    rdx, rdx
0x180031911  jz      loc_180031B19
0x180031917  test    r8, r8
0x18003191a  jz      loc_180031B19
0x180031920  mov     [r8], r13
0x180031923  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180031927  inc     rdx
0x18003192a  cmp     [rbx+rdx*2], r13w
0x18003192f  jnz     short loc_180031927
0x180031931  add     edx, edx
0x180031933  mov     eax, 3E8h
0x180031938  cmp     edx, 64h ; 'd'
0x18003193b  cmovl   edx, eax
0x18003193e  mov     [rbp+57h+var_98], r13d
0x180031942  mov     [rbp+57h+var_94], edx
0x180031945  mov     dword ptr [rbp+57h+cb], r13d
0x180031949  mov     r8d, 2
0x18003194f  lea     rcx, [rbp+57h+cb]
0x180031953  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180031958  test    eax, eax
0x18003195a  jns     short loc_180031965
0x18003195c  mov     rax, r13
0x18003195f  mov     [rbp+57h+pv], r13
0x180031963  jmp     short loc_18003197B
0x180031965  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180031968  call    cs:__imp_CoTaskMemAlloc
0x18003196e  mov     [rbp+57h+pv], rax
0x180031972  test    rax, rax
0x180031975  jz      short loc_18003197B
0x180031977  mov     [rax], r13w
0x18003197b  test    rax, rax
0x18003197e  jnz     short loc_180031993
0x180031980  mov     rcx, rax; pv
0x180031983  call    cs:__imp_CoTaskMemFree
0x180031989  mov     eax, 8007000Eh
0x18003198e  jmp     loc_180031B1E
0x180031993  mov     [rdi], rbx
0x180031996  mov     esi, 25h ; '%'
0x18003199b  cmp     [rbx], r13w
0x18003199f  jz      loc_180031AFD
0x1800319a5  cmp     [rbx], si
0x1800319a8  jnz     loc_180031AE7
0x1800319ae  mov     rcx, rbx; lpsz
0x1800319b1  call    cs:__imp_CharNextW
0x1800319b7  mov     [rdi], rax
0x1800319ba  cmp     [rax], si
0x1800319bd  jnz     short loc_1800319E3
0x1800319bf  mov     rdx, rax; unsigned __int16 *
0x1800319c2  mov     r8d, 1; int
0x1800319c8  lea     rcx, [rbp+57h+var_98]; this
0x1800319cc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800319d1  test    eax, eax
0x1800319d3  jnz     loc_180031AD3
0x1800319d9  mov     ebx, 8007000Eh
0x1800319de  jmp     loc_180031B0B
0x1800319e3  mov     edx, esi; unsigned __int16
0x1800319e5  mov     rcx, rax; lpsz
0x1800319e8  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800319ed  mov     rsi, rax
0x1800319f0  test    rax, rax
0x1800319f3  jz      loc_180031AF6
0x1800319f9  mov     rcx, rax
0x1800319fc  sub     rcx, [rdi]
0x1800319ff  sar     rcx, 1
0x180031a02  cmp     rcx, 1Fh
0x180031a06  jg      loc_180031AEF
0x180031a0c  movsxd  r9, ecx
0x180031a0f  mov     r8, [rdi]
0x180031a12  mov     edx, 20h ; ' '
0x180031a17  lea     rcx, [rbp+57h+String2]
0x180031a1b  call    cs:__imp__o_wcsncpy_s
0x180031a21  mov     ecx, eax; int
0x180031a23  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180031a28  mov     rbx, [rdi+8]
0x180031a2c  lea     r12, [rbx+20h]
0x180031a30  mov     rcx, r12; lpCriticalSection
0x180031a33  call    cs:__imp_EnterCriticalSection
0x180031a39  lea     r14, [rbx+8]
0x180031a3d  mov     ebx, r13d
0x180031a40  cmp     ebx, [r14+10h]
0x180031a44  jge     short loc_180031A76
0x180031a46  movsxd  rax, ebx
0x180031a49  mov     rcx, [r14]
0x180031a4c  lea     rdx, [rbp+57h+String2]; lpString2
0x180031a50  mov     rcx, [rcx+rax*8]; lpString1
0x180031a54  call    cs:__imp_lstrcmpiW
0x180031a5a  test    eax, eax
0x180031a5c  jz      short loc_180031A62
0x180031a5e  inc     ebx
0x180031a60  jmp     short loc_180031A40
0x180031a62  cmp     ebx, 0FFFFFFFFh
0x180031a65  jz      short loc_180031A76
0x180031a67  mov     edx, ebx
0x180031a69  mov     rcx, r14
0x180031a6c  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180031a71  mov     rbx, [rax]
0x180031a74  jmp     short loc_180031A79
0x180031a76  mov     rbx, r13
0x180031a79  mov     rcx, r12; lpCriticalSection
0x180031a7c  call    cs:__imp_LeaveCriticalSection
0x180031a82  test    rbx, rbx
0x180031a85  jz      short loc_180031AF6
0x180031a87  mov     [rbp+57h+cb], r13
0x180031a8b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031a8f  inc     r8; int
0x180031a92  cmp     [rbx+r8*2], r13w
0x180031a97  jnz     short loc_180031A8F
0x180031a99  mov     rdx, rbx; unsigned __int16 *
0x180031a9c  lea     rcx, [rbp+57h+var_98]; this
0x180031aa0  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180031aa5  mov     ebx, eax
0x180031aa7  lea     rcx, [rbp+57h+cb]
0x180031aab  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180031ab0  test    ebx, ebx
0x180031ab2  jz      loc_1800319D9
0x180031ab8  mov     rax, [rdi]
0x180031abb  jmp     short loc_180031AC9
0x180031abd  mov     rcx, rax; lpsz
0x180031ac0  call    cs:__imp_CharNextW
0x180031ac6  mov     [rdi], rax
0x180031ac9  cmp     rax, rsi
0x180031acc  jnz     short loc_180031ABD
0x180031ace  mov     esi, 25h ; '%'
0x180031ad3  mov     rcx, [rdi]; lpsz
0x180031ad6  call    cs:__imp_CharNextW
0x180031adc  mov     rbx, rax
0x180031adf  mov     [rdi], rax
0x180031ae2  jmp     loc_18003199B
0x180031ae7  mov     rdx, rbx
0x180031aea  jmp     loc_1800319C2
0x180031aef  mov     ebx, 80004005h
0x180031af4  jmp     short loc_180031B0B
0x180031af6  mov     ebx, 80020009h
0x180031afb  jmp     short loc_180031B0B
0x180031afd  mov     ebx, r13d
0x180031b00  mov     rcx, [rbp+57h+pv]
0x180031b04  mov     [rbp+57h+pv], r13
0x180031b08  mov     [r15], rcx
0x180031b0b  mov     rcx, [rbp+57h+pv]; pv
0x180031b0f  call    cs:__imp_CoTaskMemFree
0x180031b15  mov     eax, ebx
0x180031b17  jmp     short loc_180031B1E
0x180031b19  mov     eax, 80004003h
0x180031b1e  mov     rcx, [rbp+57h+var_40]
0x180031b22  xor     rcx, rsp; StackCookie
0x180031b25  call    __security_check_cookie
0x180031b2a  mov     rbx, [rsp+0C0h+arg_8]
0x180031b32  add     rsp, 90h
0x180031b39  pop     r15
0x180031b3b  pop     r14
0x180031b3d  pop     r13
0x180031b3f  pop     r12
0x180031b41  pop     rdi
0x180031b42  pop     rsi
0x180031b43  pop     rbp
0x180031b44  retn
```
