# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x18000e624`
- end: `0x18000e8ff`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `731`
- prototype: `__int64 __fastcall(LPCWSTR *this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ec38`

## callees

- `0x1800024a0`
- `0x18000c33c`
- `0x18000c434`
- `0x18000e624`
- `0x1800107a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000e767`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000e767`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e79d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e79d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e7d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e7d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e6ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e6ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e888`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e6f8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e729`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e834`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e85d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e6f8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e729`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e834`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e85d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e7bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e7bb`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, wchar_t *a2, wchar_t **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  wchar_t *v9; // rax
  wchar_t *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const wchar_t *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const wchar_t *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  __int64 v26; // [rsp+20h] [rbp-49h] BYREF
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
  LODWORD(v26) = 0;
  HIDWORD(v26) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (wchar_t *)CoTaskMemAlloc((unsigned int)v8);
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
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v15, 1) )
      goto LABEL_55;
LABEL_49:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (wchar_t *)pv;
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
  v18 = _o_wcsncpy_s(String2, 32, *this, (int)v17, v26);
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
    v22 = *(const wchar_t **)(*((_QWORD *)v19 + 2) + 8LL * v20);
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
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v22, v23) )
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
0x18000e624  mov     [rsp-8+arg_8], rbx
0x18000e629  push    rbp
0x18000e62a  push    rsi
0x18000e62b  push    rdi
0x18000e62c  push    r12
0x18000e62e  push    r13
0x18000e630  push    r14
0x18000e632  push    r15
0x18000e634  lea     rbp, [rsp-27h]
0x18000e639  sub     rsp, 90h
0x18000e640  mov     rax, cs:__security_cookie
0x18000e647  xor     rax, rsp
0x18000e64a  mov     [rbp+57h+var_40], rax
0x18000e64e  mov     r12, r8
0x18000e651  mov     rbx, rdx
0x18000e654  mov     r14, rcx
0x18000e657  xor     r13d, r13d
0x18000e65a  test    rdx, rdx
0x18000e65d  jz      loc_18000E8A7
0x18000e663  test    r8, r8
0x18000e666  jz      loc_18000E8A7
0x18000e66c  mov     [r8], r13
0x18000e66f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e673  inc     rax
0x18000e676  cmp     [rdx+rax*2], r13w
0x18000e67b  jnz     short loc_18000E673
0x18000e67d  add     eax, eax
0x18000e67f  mov     ecx, 3E8h
0x18000e684  cmp     eax, 64h ; 'd'
0x18000e687  cmovl   eax, ecx
0x18000e68a  mov     [rbp+57h+var_A0], r13d
0x18000e68e  mov     [rbp+57h+var_9C], eax
0x18000e691  mov     ecx, eax
0x18000e693  add     rcx, rcx
0x18000e696  mov     eax, 0FFFFFFFFh
0x18000e69b  cmp     rcx, rax
0x18000e69e  jbe     short loc_18000E6AC
0x18000e6a0  mov     rax, r13
0x18000e6a3  mov     rdx, r13
0x18000e6a6  mov     [rbp+57h+pv], rdx
0x18000e6aa  jmp     short loc_18000E6C4
0x18000e6ac  mov     ecx, ecx; cb
0x18000e6ae  call    cs:__imp_CoTaskMemAlloc
0x18000e6b4  mov     rdx, rax
0x18000e6b7  mov     [rbp+57h+pv], rax
0x18000e6bb  test    rax, rax
0x18000e6be  jz      short loc_18000E6C4
0x18000e6c0  mov     [rax], r13w
0x18000e6c4  test    rax, rax
0x18000e6c7  jnz     short loc_18000E6DC
0x18000e6c9  mov     rcx, rax; pv
0x18000e6cc  call    cs:__imp_CoTaskMemFree
0x18000e6d2  mov     eax, 8007000Eh
0x18000e6d7  jmp     loc_18000E8AC
0x18000e6dc  mov     [r14], rbx
0x18000e6df  movzx   eax, word ptr [rbx]
0x18000e6e2  test    ax, ax
0x18000e6e5  jz      loc_18000E879
0x18000e6eb  cmp     ax, 25h ; '%'
0x18000e6ef  jnz     loc_18000E844
0x18000e6f5  mov     rcx, rbx; lpsz
0x18000e6f8  call    cs:__imp_CharNextW
0x18000e6fe  mov     [r14], rax
0x18000e701  movzx   ecx, word ptr [rax]
0x18000e704  cmp     cx, 25h ; '%'
0x18000e708  jnz     short loc_18000E712
0x18000e70a  mov     rdx, rax
0x18000e70d  jmp     loc_18000E847
0x18000e712  test    rax, rax
0x18000e715  jz      loc_18000E899
0x18000e71b  mov     rdi, r13
0x18000e71e  jmp     short loc_18000E732
0x18000e720  cmp     cx, 25h ; '%'
0x18000e724  jz      short loc_18000E739
0x18000e726  mov     rcx, rax; lpsz
0x18000e729  call    cs:__imp_CharNextW
0x18000e72f  movzx   ecx, word ptr [rax]
0x18000e732  test    cx, cx
0x18000e735  jnz     short loc_18000E720
0x18000e737  jmp     short loc_18000E73C
0x18000e739  mov     rdi, rax
0x18000e73c  test    rdi, rdi
0x18000e73f  jz      loc_18000E899
0x18000e745  mov     rax, rdi
0x18000e748  sub     rax, [r14]
0x18000e74b  sar     rax, 1
0x18000e74e  cmp     rax, 1Fh
0x18000e752  jg      loc_18000E892
0x18000e758  movsxd  r9, eax
0x18000e75b  mov     r8, [r14]
0x18000e75e  mov     edx, 20h ; ' '
0x18000e763  lea     rcx, [rbp+57h+String2]
0x18000e767  call    cs:__imp__o_wcsncpy_s
0x18000e76d  test    eax, eax
0x18000e76f  jz      short loc_18000E795
0x18000e771  cmp     eax, 0Ch
0x18000e774  jz      loc_18000E8F4
0x18000e77a  cmp     eax, 16h
0x18000e77d  jz      loc_18000E8E9
0x18000e783  cmp     eax, 22h ; '"'
0x18000e786  jz      loc_18000E8E9
0x18000e78c  cmp     eax, 50h ; 'P'
0x18000e78f  jnz     loc_18000E8DE
0x18000e795  mov     rsi, [r14+8]
0x18000e799  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000e79d  call    cs:__imp_EnterCriticalSection
0x18000e7a3  mov     ebx, r13d
0x18000e7a6  cmp     [rsi+18h], r13d
0x18000e7aa  jle     short loc_18000E7CC
0x18000e7ac  movsxd  rax, ebx
0x18000e7af  mov     rcx, [rsi+8]
0x18000e7b3  lea     rdx, [rbp+57h+String2]; lpString2
0x18000e7b7  mov     rcx, [rcx+rax*8]; lpString1
0x18000e7bb  call    cs:__imp_lstrcmpiW
0x18000e7c1  test    eax, eax
0x18000e7c3  jz      short loc_18000E80E
0x18000e7c5  inc     ebx
0x18000e7c7  cmp     ebx, [rsi+18h]
0x18000e7ca  jl      short loc_18000E7AC
0x18000e7cc  mov     rbx, r13
0x18000e7cf  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000e7d3  call    cs:__imp_LeaveCriticalSection
0x18000e7d9  test    rbx, rbx
0x18000e7dc  jz      loc_18000E899
0x18000e7e2  mov     [rbp+57h+var_90], r13
0x18000e7e6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e7ea  inc     r8; int
0x18000e7ed  cmp     [rbx+r8*2], r13w
0x18000e7f2  jnz     short loc_18000E7EA
0x18000e7f4  mov     rdx, rbx; wchar_t *
0x18000e7f7  lea     rcx, [rbp+57h+var_A0]; this
0x18000e7fb  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18000e800  nop
0x18000e801  test    eax, eax
0x18000e803  jz      loc_18000E8A0
0x18000e809  mov     rax, [r14]
0x18000e80c  jmp     short loc_18000E83D
0x18000e80e  cmp     ebx, 0FFFFFFFFh
0x18000e811  jz      short loc_18000E7CC
0x18000e813  test    ebx, ebx
0x18000e815  js      loc_18000E8D3
0x18000e81b  cmp     ebx, [rsi+18h]
0x18000e81e  jge     loc_18000E8D3
0x18000e824  movsxd  rcx, ebx
0x18000e827  mov     rax, [rsi+10h]
0x18000e82b  mov     rbx, [rax+rcx*8]
0x18000e82f  jmp     short loc_18000E7CF
0x18000e831  mov     rcx, rax; lpsz
0x18000e834  call    cs:__imp_CharNextW
0x18000e83a  mov     [r14], rax
0x18000e83d  cmp     rax, rdi
0x18000e840  jnz     short loc_18000E831
0x18000e842  jmp     short loc_18000E85A
0x18000e844  mov     rdx, rbx; wchar_t *
0x18000e847  mov     r8d, 1; int
0x18000e84d  lea     rcx, [rbp+57h+var_A0]; this
0x18000e851  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18000e856  test    eax, eax
0x18000e858  jz      short loc_18000E8A0
0x18000e85a  mov     rcx, [r14]; lpsz
0x18000e85d  call    cs:__imp_CharNextW
0x18000e863  mov     rbx, rax
0x18000e866  mov     [r14], rax
0x18000e869  movzx   eax, word ptr [rax]
0x18000e86c  test    ax, ax
0x18000e86f  jnz     loc_18000E6EB
0x18000e875  mov     rdx, [rbp+57h+pv]
0x18000e879  mov     ebx, r13d
0x18000e87c  mov     [rbp+57h+pv], r13
0x18000e880  mov     [r12], rdx
0x18000e884  mov     rcx, [rbp+57h+pv]; pv
0x18000e888  call    cs:__imp_CoTaskMemFree
0x18000e88e  mov     eax, ebx
0x18000e890  jmp     short loc_18000E8AC
0x18000e892  mov     ebx, 80004005h
0x18000e897  jmp     short loc_18000E884
0x18000e899  mov     ebx, 80020009h
0x18000e89e  jmp     short loc_18000E884
0x18000e8a0  mov     ebx, 8007000Eh
0x18000e8a5  jmp     short loc_18000E884
0x18000e8a7  mov     eax, 80004003h
0x18000e8ac  mov     rcx, [rbp+57h+var_40]
0x18000e8b0  xor     rcx, rsp; StackCookie
0x18000e8b3  call    __security_check_cookie
0x18000e8b8  mov     rbx, [rsp+0C0h+arg_8]
0x18000e8c0  add     rsp, 90h
0x18000e8c7  pop     r15
0x18000e8c9  pop     r14
0x18000e8cb  pop     r13
0x18000e8cd  pop     r12
0x18000e8cf  pop     rdi
0x18000e8d0  pop     rsi
0x18000e8d1  pop     rbp
0x18000e8d2  retn
0x18000e8d3  mov     ecx, 0C000008Ch; unsigned int
0x18000e8d8  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000e8dd  int     3; Trap to Debugger
0x18000e8de  mov     ecx, 80004005h; int
0x18000e8e3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e8e9  mov     ecx, 80070057h; int
0x18000e8ee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e8f4  mov     ecx, 8007000Eh; int
0x18000e8f9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
