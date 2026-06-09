# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18001098c`
- end: `0x180010c67`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010f18`

## callees

- `0x18000e6cc`
- `0x18000f208`
- `0x18001098c`
- `0x1800127fc`
- `0x1800181e0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180010acf`
- `msvcrt!wcsncpy_s` at `0x180010acf`
- `KERNEL32!EnterCriticalSection` at `0x180010b05`
- `KERNEL32!EnterCriticalSection` at `0x180010b05`
- `KERNEL32!LeaveCriticalSection` at `0x180010b3b`
- `KERNEL32!LeaveCriticalSection` at `0x180010b3b`
- `KERNEL32!lstrcmpiW` at `0x180010b23`
- `KERNEL32!lstrcmpiW` at `0x180010b23`
- `USER32!CharNextW` at `0x180010a60`
- `USER32!CharNextW` at `0x180010a91`
- `USER32!CharNextW` at `0x180010b9c`
- `USER32!CharNextW` at `0x180010bc5`
- `USER32!CharNextW` at `0x180010a60`
- `USER32!CharNextW` at `0x180010a91`
- `USER32!CharNextW` at `0x180010b9c`
- `USER32!CharNextW` at `0x180010bc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010a16`

## pseudocode

```c
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
  errno_t v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  const WCHAR *i; // rax
  unsigned int v24; // ebx
  _DWORD v25[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h]
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
  if ( v7 < 100 )
    v7 = 1000;
  v25[0] = 0;
  v25[1] = v7;
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
    v24 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v15, 1) )
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
    v24 = -2147467259;
    goto LABEL_52;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *this, (int)v17);
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
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_34;
  }
  if ( v20 == -1 )
  {
LABEL_34:
    v21 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C);
      __debugbreak();
    }
    v21 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v21 )
  {
LABEL_54:
    v24 = -2147352567;
    goto LABEL_52;
  }
  v27 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v21, v22) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v24 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v24;
}

```

## disassembly

```asm
0x18001098c  mov     [rsp-8+arg_8], rbx
0x180010991  push    rbp
0x180010992  push    rsi
0x180010993  push    rdi
0x180010994  push    r12
0x180010996  push    r13
0x180010998  push    r14
0x18001099a  push    r15
0x18001099c  lea     rbp, [rsp-27h]
0x1800109a1  sub     rsp, 90h
0x1800109a8  mov     rax, cs:__security_cookie
0x1800109af  xor     rax, rsp
0x1800109b2  mov     [rbp+57h+var_40], rax
0x1800109b6  mov     r12, r8
0x1800109b9  mov     rbx, rdx
0x1800109bc  mov     r14, rcx
0x1800109bf  xor     r13d, r13d
0x1800109c2  test    rdx, rdx
0x1800109c5  jz      loc_180010C0F
0x1800109cb  test    r8, r8
0x1800109ce  jz      loc_180010C0F
0x1800109d4  mov     [r8], r13
0x1800109d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800109db  inc     rax
0x1800109de  cmp     [rdx+rax*2], r13w
0x1800109e3  jnz     short loc_1800109DB
0x1800109e5  add     eax, eax
0x1800109e7  mov     ecx, 3E8h
0x1800109ec  cmp     eax, 64h ; 'd'
0x1800109ef  cmovl   eax, ecx
0x1800109f2  mov     [rbp+57h+var_A0], r13d
0x1800109f6  mov     [rbp+57h+var_9C], eax
0x1800109f9  mov     ecx, eax
0x1800109fb  add     rcx, rcx
0x1800109fe  mov     eax, 0FFFFFFFFh
0x180010a03  cmp     rcx, rax
0x180010a06  jbe     short loc_180010A14
0x180010a08  mov     rax, r13
0x180010a0b  mov     rdx, r13
0x180010a0e  mov     [rbp+57h+pv], rdx
0x180010a12  jmp     short loc_180010A2C
0x180010a14  mov     ecx, ecx; cb
0x180010a16  call    cs:__imp_CoTaskMemAlloc
0x180010a1c  mov     rdx, rax
0x180010a1f  mov     [rbp+57h+pv], rax
0x180010a23  test    rax, rax
0x180010a26  jz      short loc_180010A2C
0x180010a28  mov     [rax], r13w
0x180010a2c  test    rax, rax
0x180010a2f  jnz     short loc_180010A44
0x180010a31  mov     rcx, rax; pv
0x180010a34  call    cs:__imp_CoTaskMemFree
0x180010a3a  mov     eax, 8007000Eh
0x180010a3f  jmp     loc_180010C14
0x180010a44  mov     [r14], rbx
0x180010a47  movzx   eax, word ptr [rbx]
0x180010a4a  test    ax, ax
0x180010a4d  jz      loc_180010BE1
0x180010a53  cmp     ax, 25h ; '%'
0x180010a57  jnz     loc_180010BAC
0x180010a5d  mov     rcx, rbx; lpsz
0x180010a60  call    cs:__imp_CharNextW
0x180010a66  mov     [r14], rax
0x180010a69  movzx   ecx, word ptr [rax]
0x180010a6c  cmp     cx, 25h ; '%'
0x180010a70  jnz     short loc_180010A7A
0x180010a72  mov     rdx, rax
0x180010a75  jmp     loc_180010BAF
0x180010a7a  test    rax, rax
0x180010a7d  jz      loc_180010C01
0x180010a83  mov     rdi, r13
0x180010a86  jmp     short loc_180010A9A
0x180010a88  cmp     cx, 25h ; '%'
0x180010a8c  jz      short loc_180010AA1
0x180010a8e  mov     rcx, rax; lpsz
0x180010a91  call    cs:__imp_CharNextW
0x180010a97  movzx   ecx, word ptr [rax]
0x180010a9a  test    cx, cx
0x180010a9d  jnz     short loc_180010A88
0x180010a9f  jmp     short loc_180010AA4
0x180010aa1  mov     rdi, rax
0x180010aa4  test    rdi, rdi
0x180010aa7  jz      loc_180010C01
0x180010aad  mov     rax, rdi
0x180010ab0  sub     rax, [r14]
0x180010ab3  sar     rax, 1
0x180010ab6  cmp     rax, 1Fh
0x180010aba  jg      loc_180010BFA
0x180010ac0  movsxd  r9, eax; MaxCount
0x180010ac3  mov     r8, [r14]; Source
0x180010ac6  mov     edx, 20h ; ' '; SizeInWords
0x180010acb  lea     rcx, [rbp+57h+Destination]; Destination
0x180010acf  call    cs:__imp_wcsncpy_s
0x180010ad5  test    eax, eax
0x180010ad7  jz      short loc_180010AFD
0x180010ad9  cmp     eax, 0Ch
0x180010adc  jz      loc_180010C5C
0x180010ae2  cmp     eax, 16h
0x180010ae5  jz      loc_180010C51
0x180010aeb  cmp     eax, 22h ; '"'
0x180010aee  jz      loc_180010C51
0x180010af4  cmp     eax, 50h ; 'P'
0x180010af7  jnz     loc_180010C46
0x180010afd  mov     rsi, [r14+8]
0x180010b01  lea     rcx, [rsi+20h]; lpCriticalSection
0x180010b05  call    cs:__imp_EnterCriticalSection
0x180010b0b  mov     ebx, r13d
0x180010b0e  cmp     [rsi+18h], r13d
0x180010b12  jle     short loc_180010B34
0x180010b14  movsxd  rax, ebx
0x180010b17  mov     rcx, [rsi+8]
0x180010b1b  lea     rdx, [rbp+57h+Destination]; lpString2
0x180010b1f  mov     rcx, [rcx+rax*8]; lpString1
0x180010b23  call    cs:__imp_lstrcmpiW
0x180010b29  test    eax, eax
0x180010b2b  jz      short loc_180010B76
0x180010b2d  inc     ebx
0x180010b2f  cmp     ebx, [rsi+18h]
0x180010b32  jl      short loc_180010B14
0x180010b34  mov     rbx, r13
0x180010b37  lea     rcx, [rsi+20h]; lpCriticalSection
0x180010b3b  call    cs:__imp_LeaveCriticalSection
0x180010b41  test    rbx, rbx
0x180010b44  jz      loc_180010C01
0x180010b4a  mov     [rbp+57h+var_90], r13
0x180010b4e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010b52  inc     r8; int
0x180010b55  cmp     [rbx+r8*2], r13w
0x180010b5a  jnz     short loc_180010B52
0x180010b5c  mov     rdx, rbx; unsigned __int16 *
0x180010b5f  lea     rcx, [rbp+57h+var_A0]; this
0x180010b63  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180010b68  nop
0x180010b69  test    eax, eax
0x180010b6b  jz      loc_180010C08
0x180010b71  mov     rax, [r14]
0x180010b74  jmp     short loc_180010BA5
0x180010b76  cmp     ebx, 0FFFFFFFFh
0x180010b79  jz      short loc_180010B34
0x180010b7b  test    ebx, ebx
0x180010b7d  js      loc_180010C3B
0x180010b83  cmp     ebx, [rsi+18h]
0x180010b86  jge     loc_180010C3B
0x180010b8c  movsxd  rcx, ebx
0x180010b8f  mov     rax, [rsi+10h]
0x180010b93  mov     rbx, [rax+rcx*8]
0x180010b97  jmp     short loc_180010B37
0x180010b99  mov     rcx, rax; lpsz
0x180010b9c  call    cs:__imp_CharNextW
0x180010ba2  mov     [r14], rax
0x180010ba5  cmp     rax, rdi
0x180010ba8  jnz     short loc_180010B99
0x180010baa  jmp     short loc_180010BC2
0x180010bac  mov     rdx, rbx; unsigned __int16 *
0x180010baf  mov     r8d, 1; int
0x180010bb5  lea     rcx, [rbp+57h+var_A0]; this
0x180010bb9  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180010bbe  test    eax, eax
0x180010bc0  jz      short loc_180010C08
0x180010bc2  mov     rcx, [r14]; lpsz
0x180010bc5  call    cs:__imp_CharNextW
0x180010bcb  mov     rbx, rax
0x180010bce  mov     [r14], rax
0x180010bd1  movzx   eax, word ptr [rax]
0x180010bd4  test    ax, ax
0x180010bd7  jnz     loc_180010A53
0x180010bdd  mov     rdx, [rbp+57h+pv]
0x180010be1  mov     ebx, r13d
0x180010be4  mov     [rbp+57h+pv], r13
0x180010be8  mov     [r12], rdx
0x180010bec  mov     rcx, [rbp+57h+pv]; pv
0x180010bf0  call    cs:__imp_CoTaskMemFree
0x180010bf6  mov     eax, ebx
0x180010bf8  jmp     short loc_180010C14
0x180010bfa  mov     ebx, 80004005h
0x180010bff  jmp     short loc_180010BEC
0x180010c01  mov     ebx, 80020009h
0x180010c06  jmp     short loc_180010BEC
0x180010c08  mov     ebx, 8007000Eh
0x180010c0d  jmp     short loc_180010BEC
0x180010c0f  mov     eax, 80004003h
0x180010c14  mov     rcx, [rbp+57h+var_40]
0x180010c18  xor     rcx, rsp; StackCookie
0x180010c1b  call    __security_check_cookie
0x180010c20  mov     rbx, [rsp+0C0h+arg_8]
0x180010c28  add     rsp, 90h
0x180010c2f  pop     r15
0x180010c31  pop     r14
0x180010c33  pop     r13
0x180010c35  pop     r12
0x180010c37  pop     rdi
0x180010c38  pop     rsi
0x180010c39  pop     rbp
0x180010c3a  retn
0x180010c3b  mov     ecx, 0C000008Ch; unsigned int
0x180010c40  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180010c45  int     3; Trap to Debugger
0x180010c46  mov     ecx, 80004005h; int
0x180010c4b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010c51  mov     ecx, 80070057h; int
0x180010c56  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010c5c  mov     ecx, 8007000Eh; int
0x180010c61  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
