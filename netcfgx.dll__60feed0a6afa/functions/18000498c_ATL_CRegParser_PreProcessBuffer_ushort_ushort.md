# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000498c`
- end: `0x180004c67`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004ea8`

## callees

- `0x180001f90`
- `0x180003cac`
- `0x180003eb0`
- `0x18000498c`
- `0x1800063bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180004acf`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180004acf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bf0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004a60`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004a91`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004b9c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bc5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004a60`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004a91`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004b9c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004bc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b05`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b23`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b23`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h]
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
  if ( v7 < 100 )
    v7 = 1000;
  v26[0] = 0;
  v26[1] = v7;
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
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_51:
    v25 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
      goto LABEL_55;
LABEL_49:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_51;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_48;
  }
  if ( !v13 )
    goto LABEL_54;
  v16 = 0;
  while ( v14 )
  {
    if ( v14 == 37 )
    {
      v16 = v13;
      break;
    }
    v13 = CharNextW(v13);
    v14 = *v13;
  }
  if ( !v16 )
    goto LABEL_54;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v25 = -2147467259;
    goto LABEL_52;
  }
  v18 = _o_wcsncpy_s(String2, 32, *this, (int)v17);
  if ( v18 )
  {
    if ( v18 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v18 == 22 || v18 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v18 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v19 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  v20 = 0;
  if ( *((int *)v19 + 6) <= 0 )
    goto LABEL_34;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), String2) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_34;
  }
  if ( v20 == -1 )
  {
LABEL_34:
    v22 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v22 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v22 )
  {
LABEL_54:
    v25 = -2147352567;
    goto LABEL_52;
  }
  v28 = 0;
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v25 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x18000498c  mov     [rsp-8+arg_8], rbx
0x180004991  push    rbp
0x180004992  push    rsi
0x180004993  push    rdi
0x180004994  push    r12
0x180004996  push    r13
0x180004998  push    r14
0x18000499a  push    r15
0x18000499c  lea     rbp, [rsp-27h]
0x1800049a1  sub     rsp, 90h
0x1800049a8  mov     rax, cs:__security_cookie
0x1800049af  xor     rax, rsp
0x1800049b2  mov     [rbp+57h+var_40], rax
0x1800049b6  mov     r12, r8
0x1800049b9  mov     rbx, rdx
0x1800049bc  mov     r14, rcx
0x1800049bf  xor     r13d, r13d
0x1800049c2  test    rdx, rdx
0x1800049c5  jz      loc_180004C0F
0x1800049cb  test    r8, r8
0x1800049ce  jz      loc_180004C0F
0x1800049d4  mov     [r8], r13
0x1800049d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800049db  inc     rax
0x1800049de  cmp     [rdx+rax*2], r13w
0x1800049e3  jnz     short loc_1800049DB
0x1800049e5  add     eax, eax
0x1800049e7  mov     ecx, 3E8h
0x1800049ec  cmp     eax, 64h ; 'd'
0x1800049ef  cmovl   eax, ecx
0x1800049f2  mov     [rbp+57h+var_A0], r13d
0x1800049f6  mov     [rbp+57h+var_9C], eax
0x1800049f9  mov     ecx, eax
0x1800049fb  add     rcx, rcx
0x1800049fe  mov     eax, 0FFFFFFFFh
0x180004a03  cmp     rcx, rax
0x180004a06  jbe     short loc_180004A14
0x180004a08  mov     rax, r13
0x180004a0b  mov     rdx, r13
0x180004a0e  mov     [rbp+57h+pv], rdx
0x180004a12  jmp     short loc_180004A2C
0x180004a14  mov     ecx, ecx; cb
0x180004a16  call    cs:__imp_CoTaskMemAlloc
0x180004a1c  mov     rdx, rax
0x180004a1f  mov     [rbp+57h+pv], rax
0x180004a23  test    rax, rax
0x180004a26  jz      short loc_180004A2C
0x180004a28  mov     [rax], r13w
0x180004a2c  test    rax, rax
0x180004a2f  jnz     short loc_180004A44
0x180004a31  mov     rcx, rax; pv
0x180004a34  call    cs:__imp_CoTaskMemFree
0x180004a3a  mov     eax, 8007000Eh
0x180004a3f  jmp     loc_180004C14
0x180004a44  mov     [r14], rbx
0x180004a47  movzx   eax, word ptr [rbx]
0x180004a4a  test    ax, ax
0x180004a4d  jz      loc_180004BE1
0x180004a53  cmp     ax, 25h ; '%'
0x180004a57  jnz     loc_180004BAC
0x180004a5d  mov     rcx, rbx; lpsz
0x180004a60  call    cs:__imp_CharNextW
0x180004a66  mov     [r14], rax
0x180004a69  movzx   ecx, word ptr [rax]
0x180004a6c  cmp     cx, 25h ; '%'
0x180004a70  jnz     short loc_180004A7A
0x180004a72  mov     rdx, rax
0x180004a75  jmp     loc_180004BAF
0x180004a7a  test    rax, rax
0x180004a7d  jz      loc_180004C01
0x180004a83  mov     rdi, r13
0x180004a86  jmp     short loc_180004A9A
0x180004a88  cmp     cx, 25h ; '%'
0x180004a8c  jz      short loc_180004AA1
0x180004a8e  mov     rcx, rax; lpsz
0x180004a91  call    cs:__imp_CharNextW
0x180004a97  movzx   ecx, word ptr [rax]
0x180004a9a  test    cx, cx
0x180004a9d  jnz     short loc_180004A88
0x180004a9f  jmp     short loc_180004AA4
0x180004aa1  mov     rdi, rax
0x180004aa4  test    rdi, rdi
0x180004aa7  jz      loc_180004C01
0x180004aad  mov     rax, rdi
0x180004ab0  sub     rax, [r14]
0x180004ab3  sar     rax, 1
0x180004ab6  cmp     rax, 1Fh
0x180004aba  jg      loc_180004BFA
0x180004ac0  movsxd  r9, eax
0x180004ac3  mov     r8, [r14]
0x180004ac6  mov     edx, 20h ; ' '
0x180004acb  lea     rcx, [rbp+57h+String2]
0x180004acf  call    cs:__imp__o_wcsncpy_s
0x180004ad5  test    eax, eax
0x180004ad7  jz      short loc_180004AFD
0x180004ad9  cmp     eax, 0Ch
0x180004adc  jz      loc_180004C5C
0x180004ae2  cmp     eax, 16h
0x180004ae5  jz      loc_180004C51
0x180004aeb  cmp     eax, 22h ; '"'
0x180004aee  jz      loc_180004C51
0x180004af4  cmp     eax, 50h ; 'P'
0x180004af7  jnz     loc_180004C46
0x180004afd  mov     rsi, [r14+8]
0x180004b01  lea     rcx, [rsi+20h]; lpCriticalSection
0x180004b05  call    cs:__imp_EnterCriticalSection
0x180004b0b  mov     ebx, r13d
0x180004b0e  cmp     [rsi+18h], r13d
0x180004b12  jle     short loc_180004B34
0x180004b14  movsxd  rax, ebx
0x180004b17  mov     rcx, [rsi+8]
0x180004b1b  lea     rdx, [rbp+57h+String2]; lpString2
0x180004b1f  mov     rcx, [rcx+rax*8]; lpString1
0x180004b23  call    cs:__imp_lstrcmpiW
0x180004b29  test    eax, eax
0x180004b2b  jz      short loc_180004B76
0x180004b2d  inc     ebx
0x180004b2f  cmp     ebx, [rsi+18h]
0x180004b32  jl      short loc_180004B14
0x180004b34  mov     rbx, r13
0x180004b37  lea     rcx, [rsi+20h]; lpCriticalSection
0x180004b3b  call    cs:__imp_LeaveCriticalSection
0x180004b41  test    rbx, rbx
0x180004b44  jz      loc_180004C01
0x180004b4a  mov     [rbp+57h+var_90], r13
0x180004b4e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004b52  inc     r8; int
0x180004b55  cmp     [rbx+r8*2], r13w
0x180004b5a  jnz     short loc_180004B52
0x180004b5c  mov     rdx, rbx; unsigned __int16 *
0x180004b5f  lea     rcx, [rbp+57h+var_A0]; this
0x180004b63  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004b68  nop
0x180004b69  test    eax, eax
0x180004b6b  jz      loc_180004C08
0x180004b71  mov     rax, [r14]
0x180004b74  jmp     short loc_180004BA5
0x180004b76  cmp     ebx, 0FFFFFFFFh
0x180004b79  jz      short loc_180004B34
0x180004b7b  test    ebx, ebx
0x180004b7d  js      loc_180004C3B
0x180004b83  cmp     ebx, [rsi+18h]
0x180004b86  jge     loc_180004C3B
0x180004b8c  movsxd  rcx, ebx
0x180004b8f  mov     rax, [rsi+10h]
0x180004b93  mov     rbx, [rax+rcx*8]
0x180004b97  jmp     short loc_180004B37
0x180004b99  mov     rcx, rax; lpsz
0x180004b9c  call    cs:__imp_CharNextW
0x180004ba2  mov     [r14], rax
0x180004ba5  cmp     rax, rdi
0x180004ba8  jnz     short loc_180004B99
0x180004baa  jmp     short loc_180004BC2
0x180004bac  mov     rdx, rbx; unsigned __int16 *
0x180004baf  mov     r8d, 1; int
0x180004bb5  lea     rcx, [rbp+57h+var_A0]; this
0x180004bb9  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004bbe  test    eax, eax
0x180004bc0  jz      short loc_180004C08
0x180004bc2  mov     rcx, [r14]; lpsz
0x180004bc5  call    cs:__imp_CharNextW
0x180004bcb  mov     rbx, rax
0x180004bce  mov     [r14], rax
0x180004bd1  movzx   eax, word ptr [rax]
0x180004bd4  test    ax, ax
0x180004bd7  jnz     loc_180004A53
0x180004bdd  mov     rdx, [rbp+57h+pv]
0x180004be1  mov     ebx, r13d
0x180004be4  mov     [rbp+57h+pv], r13
0x180004be8  mov     [r12], rdx
0x180004bec  mov     rcx, [rbp+57h+pv]; pv
0x180004bf0  call    cs:__imp_CoTaskMemFree
0x180004bf6  mov     eax, ebx
0x180004bf8  jmp     short loc_180004C14
0x180004bfa  mov     ebx, 80004005h
0x180004bff  jmp     short loc_180004BEC
0x180004c01  mov     ebx, 80020009h
0x180004c06  jmp     short loc_180004BEC
0x180004c08  mov     ebx, 8007000Eh
0x180004c0d  jmp     short loc_180004BEC
0x180004c0f  mov     eax, 80004003h
0x180004c14  mov     rcx, [rbp+57h+var_40]
0x180004c18  xor     rcx, rsp; StackCookie
0x180004c1b  call    __security_check_cookie
0x180004c20  mov     rbx, [rsp+0C0h+arg_8]
0x180004c28  add     rsp, 90h
0x180004c2f  pop     r15
0x180004c31  pop     r14
0x180004c33  pop     r13
0x180004c35  pop     r12
0x180004c37  pop     rdi
0x180004c38  pop     rsi
0x180004c39  pop     rbp
0x180004c3a  retn
0x180004c3b  mov     ecx, 0C000008Ch; unsigned int
0x180004c40  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180004c45  int     3; Trap to Debugger
0x180004c46  mov     ecx, 80004005h; int
0x180004c4b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004c51  mov     ecx, 80070057h; int
0x180004c56  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004c5c  mov     ecx, 8007000Eh; int
0x180004c61  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
