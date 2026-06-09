# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18002eadc`
- end: `0x18002ed84`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `680`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ef0c`

## callees

- `0x1800294b0`
- `0x18002be80`
- `0x18002cb34`
- `0x18002ce30`
- `0x18002e27c`
- `0x18002eadc`
- `0x18002fb6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002ec2f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002ec2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eca2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eca2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ebbf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ecec`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ed08`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ebbf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ecec`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ed08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002ec74`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002ec74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eb8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ed47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eb8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ed47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eb6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eb6a`

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
  unsigned __int16 *v26; // rcx
  LPVOID pv[2]; // [rsp+20h] [rbp-49h] BYREF
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
  *(_OWORD *)pv = 0;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(pv[0]) = 0;
  HIDWORD(pv[0]) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv[1] = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv[1] = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, pv[0]);
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
          goto LABEL_29;
        }
        break;
      }
    }
    v22 = 0;
LABEL_29:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_39:
      v13 = -2147352567;
      goto LABEL_41;
    }
    v28 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v28);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv[1];
  pv[1] = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv[1]);
  return v13;
}

```

## disassembly

```asm
0x18002eadc  mov     [rsp-8+arg_8], rbx
0x18002eae1  push    rbp
0x18002eae2  push    rsi
0x18002eae3  push    rdi
0x18002eae4  push    r12
0x18002eae6  push    r13
0x18002eae8  push    r14
0x18002eaea  push    r15
0x18002eaec  lea     rbp, [rsp-27h]
0x18002eaf1  sub     rsp, 90h
0x18002eaf8  mov     rax, cs:__security_cookie
0x18002eaff  xor     rax, rsp
0x18002eb02  mov     [rbp+57h+var_40], rax
0x18002eb06  mov     r15, r8
0x18002eb09  mov     rbx, rdx
0x18002eb0c  mov     rdi, rcx
0x18002eb0f  xor     r13d, r13d
0x18002eb12  test    rdx, rdx
0x18002eb15  jz      loc_18002ED57
0x18002eb1b  test    r8, r8
0x18002eb1e  jz      loc_18002ED57
0x18002eb24  mov     [r8], r13
0x18002eb27  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002eb2b  inc     rax
0x18002eb2e  cmp     [rdx+rax*2], r13w
0x18002eb33  jnz     short loc_18002EB2B
0x18002eb35  add     eax, eax
0x18002eb37  xorps   xmm0, xmm0
0x18002eb3a  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18002eb3e  mov     ecx, 3E8h
0x18002eb43  cmp     eax, 64h ; 'd'
0x18002eb46  cmovl   eax, ecx
0x18002eb49  mov     dword ptr [rbp+57h+pv], r13d
0x18002eb4d  mov     dword ptr [rbp+57h+pv+4], eax
0x18002eb50  mov     ecx, eax
0x18002eb52  add     rcx, rcx
0x18002eb55  mov     eax, 0FFFFFFFFh
0x18002eb5a  cmp     rcx, rax
0x18002eb5d  jbe     short loc_18002EB68
0x18002eb5f  mov     rax, r13
0x18002eb62  mov     [rbp+57h+pv+8], r13
0x18002eb66  jmp     short loc_18002EB83
0x18002eb68  mov     ecx, ecx; cb
0x18002eb6a  call    cs:__imp_CoTaskMemAlloc
0x18002eb71  nop     dword ptr [rax+rax+00h]
0x18002eb76  mov     [rbp+57h+pv+8], rax
0x18002eb7a  test    rax, rax
0x18002eb7d  jz      short loc_18002EB83
0x18002eb7f  mov     [rax], r13w
0x18002eb83  test    rax, rax
0x18002eb86  jnz     short loc_18002EBA1
0x18002eb88  mov     rcx, rax; pv
0x18002eb8b  call    cs:__imp_CoTaskMemFree
0x18002eb92  nop     dword ptr [rax+rax+00h]
0x18002eb97  mov     eax, 8007000Eh
0x18002eb9c  jmp     loc_18002ED5C
0x18002eba1  mov     [rdi], rbx
0x18002eba4  mov     esi, 25h ; '%'
0x18002eba9  cmp     [rbx], r13w
0x18002ebad  jz      loc_18002ED35
0x18002ebb3  cmp     [rbx], si
0x18002ebb6  jnz     loc_18002ED1F
0x18002ebbc  mov     rcx, rbx; lpsz
0x18002ebbf  call    cs:__imp_CharNextW
0x18002ebc6  nop     dword ptr [rax+rax+00h]
0x18002ebcb  mov     [rdi], rax
0x18002ebce  cmp     [rax], si
0x18002ebd1  jnz     short loc_18002EBF7
0x18002ebd3  mov     rdx, rax; unsigned __int16 *
0x18002ebd6  mov     r8d, 1; int
0x18002ebdc  lea     rcx, [rbp+57h+pv]; this
0x18002ebe0  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002ebe5  test    eax, eax
0x18002ebe7  jnz     loc_18002ED05
0x18002ebed  mov     ebx, 8007000Eh
0x18002ebf2  jmp     loc_18002ED43
0x18002ebf7  mov     edx, esi; unsigned __int16
0x18002ebf9  mov     rcx, rax; lpsz
0x18002ebfc  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002ec01  mov     rsi, rax
0x18002ec04  test    rax, rax
0x18002ec07  jz      loc_18002ED2E
0x18002ec0d  mov     rcx, rax
0x18002ec10  sub     rcx, [rdi]
0x18002ec13  sar     rcx, 1
0x18002ec16  cmp     rcx, 1Fh
0x18002ec1a  jg      loc_18002ED27
0x18002ec20  movsxd  r9, ecx
0x18002ec23  mov     r8, [rdi]
0x18002ec26  mov     edx, 20h ; ' '
0x18002ec2b  lea     rcx, [rbp+57h+String2]
0x18002ec2f  call    cs:__imp__o_wcsncpy_s
0x18002ec36  nop     dword ptr [rax+rax+00h]
0x18002ec3b  mov     ecx, eax; int
0x18002ec3d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002ec42  mov     rbx, [rdi+8]
0x18002ec46  lea     r12, [rbx+20h]
0x18002ec4a  mov     rcx, r12; lpCriticalSection
0x18002ec4d  call    cs:__imp_EnterCriticalSection
0x18002ec54  nop     dword ptr [rax+rax+00h]
0x18002ec59  lea     r14, [rbx+8]
0x18002ec5d  mov     ebx, r13d
0x18002ec60  cmp     ebx, [r14+10h]
0x18002ec64  jge     short loc_18002EC9C
0x18002ec66  movsxd  rax, ebx
0x18002ec69  mov     rcx, [r14]
0x18002ec6c  lea     rdx, [rbp+57h+String2]; lpString2
0x18002ec70  mov     rcx, [rcx+rax*8]; lpString1
0x18002ec74  call    cs:__imp_lstrcmpiW
0x18002ec7b  nop     dword ptr [rax+rax+00h]
0x18002ec80  test    eax, eax
0x18002ec82  jz      short loc_18002EC88
0x18002ec84  inc     ebx
0x18002ec86  jmp     short loc_18002EC60
0x18002ec88  cmp     ebx, 0FFFFFFFFh
0x18002ec8b  jz      short loc_18002EC9C
0x18002ec8d  mov     edx, ebx
0x18002ec8f  mov     rcx, r14
0x18002ec92  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18002ec97  mov     rbx, [rax]
0x18002ec9a  jmp     short loc_18002EC9F
0x18002ec9c  mov     rbx, r13
0x18002ec9f  mov     rcx, r12; lpCriticalSection
0x18002eca2  call    cs:__imp_LeaveCriticalSection
0x18002eca9  nop     dword ptr [rax+rax+00h]
0x18002ecae  test    rbx, rbx
0x18002ecb1  jz      short loc_18002ED2E
0x18002ecb3  mov     [rbp+57h+var_90], r13
0x18002ecb7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002ecbb  inc     r8; int
0x18002ecbe  cmp     [rbx+r8*2], r13w
0x18002ecc3  jnz     short loc_18002ECBB
0x18002ecc5  mov     rdx, rbx; unsigned __int16 *
0x18002ecc8  lea     rcx, [rbp+57h+pv]; this
0x18002eccc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002ecd1  mov     ebx, eax
0x18002ecd3  lea     rcx, [rbp+57h+var_90]
0x18002ecd7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002ecdc  test    ebx, ebx
0x18002ecde  jz      loc_18002EBED
0x18002ece4  mov     rax, [rdi]
0x18002ece7  jmp     short loc_18002ECFB
0x18002ece9  mov     rcx, rax; lpsz
0x18002ecec  call    cs:__imp_CharNextW
0x18002ecf3  nop     dword ptr [rax+rax+00h]
0x18002ecf8  mov     [rdi], rax
0x18002ecfb  cmp     rax, rsi
0x18002ecfe  jnz     short loc_18002ECE9
0x18002ed00  mov     esi, 25h ; '%'
0x18002ed05  mov     rcx, [rdi]; lpsz
0x18002ed08  call    cs:__imp_CharNextW
0x18002ed0f  nop     dword ptr [rax+rax+00h]
0x18002ed14  mov     rbx, rax
0x18002ed17  mov     [rdi], rax
0x18002ed1a  jmp     loc_18002EBA9
0x18002ed1f  mov     rdx, rbx
0x18002ed22  jmp     loc_18002EBD6
0x18002ed27  mov     ebx, 80004005h
0x18002ed2c  jmp     short loc_18002ED43
0x18002ed2e  mov     ebx, 80020009h
0x18002ed33  jmp     short loc_18002ED43
0x18002ed35  mov     ebx, r13d
0x18002ed38  mov     rcx, [rbp+57h+pv+8]
0x18002ed3c  mov     [rbp+57h+pv+8], r13
0x18002ed40  mov     [r15], rcx
0x18002ed43  mov     rcx, [rbp+57h+pv+8]; pv
0x18002ed47  call    cs:__imp_CoTaskMemFree
0x18002ed4e  nop     dword ptr [rax+rax+00h]
0x18002ed53  mov     eax, ebx
0x18002ed55  jmp     short loc_18002ED5C
0x18002ed57  mov     eax, 80004003h
0x18002ed5c  mov     rcx, [rbp+57h+var_40]
0x18002ed60  xor     rcx, rsp; StackCookie
0x18002ed63  call    __security_check_cookie
0x18002ed68  mov     rbx, [rsp+0C0h+arg_8]
0x18002ed70  add     rsp, 90h
0x18002ed77  pop     r15
0x18002ed79  pop     r14
0x18002ed7b  pop     r13
0x18002ed7d  pop     r12
0x18002ed7f  pop     rdi
0x18002ed80  pop     rsi
0x18002ed81  pop     rbp
0x18002ed82  retn
```
