# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000ac58`
- end: `0x18000aec5`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `__int64 __fastcall(const wchar_t **this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b05c`

## callees

- `0x1800086e0`
- `0x18000882c`
- `0x1800094b8`
- `0x1800096a8`
- `0x18000a850`
- `0x18000ac58`
- `0x18000bc8c`
- `0x18001a5e0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000ad9b`
- `msvcrt!wcsncpy_s` at `0x18000ad9b`
- `USER32!CharNextW` at `0x18000ad31`
- `USER32!CharNextW` at `0x18000ae40`
- `USER32!CharNextW` at `0x18000ae56`
- `USER32!CharNextW` at `0x18000ad31`
- `USER32!CharNextW` at `0x18000ae40`
- `USER32!CharNextW` at `0x18000ae56`
- `KERNEL32!lstrcmpiW` at `0x18000add4`
- `KERNEL32!lstrcmpiW` at `0x18000add4`
- `KERNEL32!EnterCriticalSection` at `0x18000adb3`
- `KERNEL32!EnterCriticalSection` at `0x18000adb3`
- `KERNEL32!LeaveCriticalSection` at `0x18000adfc`
- `KERNEL32!LeaveCriticalSection` at `0x18000adfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ace8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ace8`

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
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&cb);
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
0x18000ac58  mov     [rsp-8+arg_8], rbx
0x18000ac5d  push    rbp
0x18000ac5e  push    rsi
0x18000ac5f  push    rdi
0x18000ac60  push    r12
0x18000ac62  push    r13
0x18000ac64  push    r14
0x18000ac66  push    r15
0x18000ac68  lea     rbp, [rsp-27h]
0x18000ac6d  sub     rsp, 90h
0x18000ac74  mov     rax, cs:__security_cookie
0x18000ac7b  xor     rax, rsp
0x18000ac7e  mov     [rbp+57h+var_40], rax
0x18000ac82  mov     r15, r8
0x18000ac85  mov     rbx, rdx
0x18000ac88  mov     rdi, rcx
0x18000ac8b  xor     r13d, r13d
0x18000ac8e  test    rdx, rdx
0x18000ac91  jz      loc_18000AE99
0x18000ac97  test    r8, r8
0x18000ac9a  jz      loc_18000AE99
0x18000aca0  mov     [r8], r13
0x18000aca3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000aca7  inc     rdx
0x18000acaa  cmp     [rbx+rdx*2], r13w
0x18000acaf  jnz     short loc_18000ACA7
0x18000acb1  add     edx, edx
0x18000acb3  mov     eax, 3E8h
0x18000acb8  cmp     edx, 64h ; 'd'
0x18000acbb  cmovl   edx, eax
0x18000acbe  mov     [rbp+57h+var_98], r13d
0x18000acc2  mov     [rbp+57h+var_94], edx
0x18000acc5  mov     dword ptr [rbp+57h+cb], r13d
0x18000acc9  mov     r8d, 2
0x18000accf  lea     rcx, [rbp+57h+cb]
0x18000acd3  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18000acd8  test    eax, eax
0x18000acda  jns     short loc_18000ACE5
0x18000acdc  mov     rax, r13
0x18000acdf  mov     [rbp+57h+pv], r13
0x18000ace3  jmp     short loc_18000ACFB
0x18000ace5  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18000ace8  call    cs:__imp_CoTaskMemAlloc
0x18000acee  mov     [rbp+57h+pv], rax
0x18000acf2  test    rax, rax
0x18000acf5  jz      short loc_18000ACFB
0x18000acf7  mov     [rax], r13w
0x18000acfb  test    rax, rax
0x18000acfe  jnz     short loc_18000AD13
0x18000ad00  mov     rcx, rax; pv
0x18000ad03  call    cs:__imp_CoTaskMemFree
0x18000ad09  mov     eax, 8007000Eh
0x18000ad0e  jmp     loc_18000AE9E
0x18000ad13  mov     [rdi], rbx
0x18000ad16  mov     esi, 25h ; '%'
0x18000ad1b  cmp     [rbx], r13w
0x18000ad1f  jz      loc_18000AE7D
0x18000ad25  cmp     [rbx], si
0x18000ad28  jnz     loc_18000AE67
0x18000ad2e  mov     rcx, rbx; lpsz
0x18000ad31  call    cs:__imp_CharNextW
0x18000ad37  mov     [rdi], rax
0x18000ad3a  cmp     [rax], si
0x18000ad3d  jnz     short loc_18000AD63
0x18000ad3f  mov     rdx, rax; unsigned __int16 *
0x18000ad42  mov     r8d, 1; int
0x18000ad48  lea     rcx, [rbp+57h+var_98]; this
0x18000ad4c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000ad51  test    eax, eax
0x18000ad53  jnz     loc_18000AE53
0x18000ad59  mov     ebx, 8007000Eh
0x18000ad5e  jmp     loc_18000AE8B
0x18000ad63  mov     edx, esi; unsigned __int16
0x18000ad65  mov     rcx, rax; lpsz
0x18000ad68  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000ad6d  mov     rsi, rax
0x18000ad70  test    rax, rax
0x18000ad73  jz      loc_18000AE76
0x18000ad79  mov     rcx, rax
0x18000ad7c  sub     rcx, [rdi]
0x18000ad7f  sar     rcx, 1
0x18000ad82  cmp     rcx, 1Fh
0x18000ad86  jg      loc_18000AE6F
0x18000ad8c  movsxd  r9, ecx; MaxCount
0x18000ad8f  mov     r8, [rdi]; Source
0x18000ad92  mov     edx, 20h ; ' '; SizeInWords
0x18000ad97  lea     rcx, [rbp+57h+Destination]; Destination
0x18000ad9b  call    cs:__imp_wcsncpy_s
0x18000ada1  mov     ecx, eax; int
0x18000ada3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000ada8  mov     rbx, [rdi+8]
0x18000adac  lea     r12, [rbx+20h]
0x18000adb0  mov     rcx, r12; lpCriticalSection
0x18000adb3  call    cs:__imp_EnterCriticalSection
0x18000adb9  lea     r14, [rbx+8]
0x18000adbd  mov     ebx, r13d
0x18000adc0  cmp     ebx, [r14+10h]
0x18000adc4  jge     short loc_18000ADF6
0x18000adc6  movsxd  rax, ebx
0x18000adc9  mov     rcx, [r14]
0x18000adcc  lea     rdx, [rbp+57h+Destination]; lpString2
0x18000add0  mov     rcx, [rcx+rax*8]; lpString1
0x18000add4  call    cs:__imp_lstrcmpiW
0x18000adda  test    eax, eax
0x18000addc  jz      short loc_18000ADE2
0x18000adde  inc     ebx
0x18000ade0  jmp     short loc_18000ADC0
0x18000ade2  cmp     ebx, 0FFFFFFFFh
0x18000ade5  jz      short loc_18000ADF6
0x18000ade7  mov     edx, ebx
0x18000ade9  mov     rcx, r14
0x18000adec  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000adf1  mov     rbx, [rax]
0x18000adf4  jmp     short loc_18000ADF9
0x18000adf6  mov     rbx, r13
0x18000adf9  mov     rcx, r12; lpCriticalSection
0x18000adfc  call    cs:__imp_LeaveCriticalSection
0x18000ae02  test    rbx, rbx
0x18000ae05  jz      short loc_18000AE76
0x18000ae07  mov     [rbp+57h+cb], r13
0x18000ae0b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ae0f  inc     r8; int
0x18000ae12  cmp     [rbx+r8*2], r13w
0x18000ae17  jnz     short loc_18000AE0F
0x18000ae19  mov     rdx, rbx; unsigned __int16 *
0x18000ae1c  lea     rcx, [rbp+57h+var_98]; this
0x18000ae20  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000ae25  mov     ebx, eax
0x18000ae27  lea     rcx, [rbp+57h+cb]
0x18000ae2b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000ae30  test    ebx, ebx
0x18000ae32  jz      loc_18000AD59
0x18000ae38  mov     rax, [rdi]
0x18000ae3b  jmp     short loc_18000AE49
0x18000ae3d  mov     rcx, rax; lpsz
0x18000ae40  call    cs:__imp_CharNextW
0x18000ae46  mov     [rdi], rax
0x18000ae49  cmp     rax, rsi
0x18000ae4c  jnz     short loc_18000AE3D
0x18000ae4e  mov     esi, 25h ; '%'
0x18000ae53  mov     rcx, [rdi]; lpsz
0x18000ae56  call    cs:__imp_CharNextW
0x18000ae5c  mov     rbx, rax
0x18000ae5f  mov     [rdi], rax
0x18000ae62  jmp     loc_18000AD1B
0x18000ae67  mov     rdx, rbx
0x18000ae6a  jmp     loc_18000AD42
0x18000ae6f  mov     ebx, 80004005h
0x18000ae74  jmp     short loc_18000AE8B
0x18000ae76  mov     ebx, 80020009h
0x18000ae7b  jmp     short loc_18000AE8B
0x18000ae7d  mov     ebx, r13d
0x18000ae80  mov     rcx, [rbp+57h+pv]
0x18000ae84  mov     [rbp+57h+pv], r13
0x18000ae88  mov     [r15], rcx
0x18000ae8b  mov     rcx, [rbp+57h+pv]; pv
0x18000ae8f  call    cs:__imp_CoTaskMemFree
0x18000ae95  mov     eax, ebx
0x18000ae97  jmp     short loc_18000AE9E
0x18000ae99  mov     eax, 80004003h
0x18000ae9e  mov     rcx, [rbp+57h+var_40]
0x18000aea2  xor     rcx, rsp; StackCookie
0x18000aea5  call    __security_check_cookie
0x18000aeaa  mov     rbx, [rsp+0C0h+arg_8]
0x18000aeb2  add     rsp, 90h
0x18000aeb9  pop     r15
0x18000aebb  pop     r14
0x18000aebd  pop     r13
0x18000aebf  pop     r12
0x18000aec1  pop     rdi
0x18000aec2  pop     rsi
0x18000aec3  pop     rbp
0x18000aec4  retn
```
