# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180004694`
- end: `0x1800049b2`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `798`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004b4c`

## callees

- `0x180003730`
- `0x18000418c`
- `0x180004694`
- `0x180005ca0`
- `0x18000df10`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800047ef`
- `msvcrt!wcsncpy_s` at `0x1800047ef`
- `KERNEL32!lstrcmpiW` at `0x18000484f`
- `KERNEL32!lstrcmpiW` at `0x18000484f`
- `KERNEL32!LeaveCriticalSection` at `0x18000486d`
- `KERNEL32!LeaveCriticalSection` at `0x18000486d`
- `KERNEL32!EnterCriticalSection` at `0x18000482b`
- `KERNEL32!EnterCriticalSection` at `0x18000482b`
- `USER32!CharNextW` at `0x180004774`
- `USER32!CharNextW` at `0x1800047ab`
- `USER32!CharNextW` at `0x1800048d4`
- `USER32!CharNextW` at `0x180004903`
- `USER32!CharNextW` at `0x180004774`
- `USER32!CharNextW` at `0x1800047ab`
- `USER32!CharNextW` at `0x1800048d4`
- `USER32!CharNextW` at `0x180004903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000471e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000471e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004742`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004934`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004742`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004934`

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
0x180004694  mov     [rsp-8+arg_8], rbx
0x180004699  push    rbp
0x18000469a  push    rsi
0x18000469b  push    rdi
0x18000469c  push    r12
0x18000469e  push    r13
0x1800046a0  push    r14
0x1800046a2  push    r15
0x1800046a4  lea     rbp, [rsp-27h]
0x1800046a9  sub     rsp, 90h
0x1800046b0  mov     rax, cs:__security_cookie
0x1800046b7  xor     rax, rsp
0x1800046ba  mov     [rbp+57h+var_40], rax
0x1800046be  mov     r12, r8
0x1800046c1  mov     rbx, rdx
0x1800046c4  mov     r14, rcx
0x1800046c7  xor     r13d, r13d
0x1800046ca  test    rdx, rdx
0x1800046cd  jz      loc_180004959
0x1800046d3  test    r8, r8
0x1800046d6  jz      loc_180004959
0x1800046dc  mov     [r8], r13
0x1800046df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800046e3  inc     rax
0x1800046e6  cmp     [rdx+rax*2], r13w
0x1800046eb  jnz     short loc_1800046E3
0x1800046ed  add     eax, eax
0x1800046ef  mov     ecx, 3E8h
0x1800046f4  cmp     eax, 64h ; 'd'
0x1800046f7  cmovl   eax, ecx
0x1800046fa  mov     [rbp+57h+var_A0], r13d
0x1800046fe  mov     [rbp+57h+var_9C], eax
0x180004701  mov     ecx, eax
0x180004703  add     rcx, rcx
0x180004706  mov     eax, 0FFFFFFFFh
0x18000470b  cmp     rcx, rax
0x18000470e  jbe     short loc_18000471C
0x180004710  mov     rax, r13
0x180004713  mov     rdx, r13
0x180004716  mov     [rbp+57h+pv], rdx
0x18000471a  jmp     short loc_18000473A
0x18000471c  mov     ecx, ecx; cb
0x18000471e  call    cs:__imp_CoTaskMemAlloc
0x180004725  nop     dword ptr [rax+rax+00h]
0x18000472a  mov     rdx, rax
0x18000472d  mov     [rbp+57h+pv], rax
0x180004731  test    rax, rax
0x180004734  jz      short loc_18000473A
0x180004736  mov     [rax], r13w
0x18000473a  test    rax, rax
0x18000473d  jnz     short loc_180004758
0x18000473f  mov     rcx, rax; pv
0x180004742  call    cs:__imp_CoTaskMemFree
0x180004749  nop     dword ptr [rax+rax+00h]
0x18000474e  mov     eax, 8007000Eh
0x180004753  jmp     loc_18000495E
0x180004758  mov     [r14], rbx
0x18000475b  movzx   eax, word ptr [rbx]
0x18000475e  test    ax, ax
0x180004761  jz      loc_180004925
0x180004767  cmp     ax, 25h ; '%'
0x18000476b  jnz     loc_1800048EA
0x180004771  mov     rcx, rbx; lpsz
0x180004774  call    cs:__imp_CharNextW
0x18000477b  nop     dword ptr [rax+rax+00h]
0x180004780  mov     [r14], rax
0x180004783  movzx   ecx, word ptr [rax]
0x180004786  cmp     cx, 25h ; '%'
0x18000478a  jnz     short loc_180004794
0x18000478c  mov     rdx, rax
0x18000478f  jmp     loc_1800048ED
0x180004794  test    rax, rax
0x180004797  jz      loc_18000494B
0x18000479d  mov     rdi, r13
0x1800047a0  jmp     short loc_1800047BA
0x1800047a2  cmp     cx, 25h ; '%'
0x1800047a6  jz      short loc_1800047C1
0x1800047a8  mov     rcx, rax; lpsz
0x1800047ab  call    cs:__imp_CharNextW
0x1800047b2  nop     dword ptr [rax+rax+00h]
0x1800047b7  movzx   ecx, word ptr [rax]
0x1800047ba  test    cx, cx
0x1800047bd  jnz     short loc_1800047A2
0x1800047bf  jmp     short loc_1800047C4
0x1800047c1  mov     rdi, rax
0x1800047c4  test    rdi, rdi
0x1800047c7  jz      loc_18000494B
0x1800047cd  mov     rax, rdi
0x1800047d0  sub     rax, [r14]
0x1800047d3  sar     rax, 1
0x1800047d6  cmp     rax, 1Fh
0x1800047da  jg      loc_180004944
0x1800047e0  movsxd  r9, eax; MaxCount
0x1800047e3  mov     r8, [r14]; Source
0x1800047e6  mov     edx, 20h ; ' '; SizeInWords
0x1800047eb  lea     rcx, [rbp+57h+Destination]; Destination
0x1800047ef  call    cs:__imp_wcsncpy_s
0x1800047f6  nop     dword ptr [rax+rax+00h]
0x1800047fb  test    eax, eax
0x1800047fd  jz      short loc_180004823
0x1800047ff  cmp     eax, 0Ch
0x180004802  jz      loc_1800049A7
0x180004808  cmp     eax, 16h
0x18000480b  jz      loc_18000499C
0x180004811  cmp     eax, 22h ; '"'
0x180004814  jz      loc_18000499C
0x18000481a  cmp     eax, 50h ; 'P'
0x18000481d  jnz     loc_180004991
0x180004823  mov     rsi, [r14+8]
0x180004827  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000482b  call    cs:__imp_EnterCriticalSection
0x180004832  nop     dword ptr [rax+rax+00h]
0x180004837  mov     ebx, r13d
0x18000483a  cmp     [rsi+18h], r13d
0x18000483e  jle     short loc_180004866
0x180004840  movsxd  rax, ebx
0x180004843  mov     rcx, [rsi+8]
0x180004847  lea     rdx, [rbp+57h+Destination]; lpString2
0x18000484b  mov     rcx, [rcx+rax*8]; lpString1
0x18000484f  call    cs:__imp_lstrcmpiW
0x180004856  nop     dword ptr [rax+rax+00h]
0x18000485b  test    eax, eax
0x18000485d  jz      short loc_1800048AE
0x18000485f  inc     ebx
0x180004861  cmp     ebx, [rsi+18h]
0x180004864  jl      short loc_180004840
0x180004866  mov     rbx, r13
0x180004869  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000486d  call    cs:__imp_LeaveCriticalSection
0x180004874  nop     dword ptr [rax+rax+00h]
0x180004879  test    rbx, rbx
0x18000487c  jz      loc_18000494B
0x180004882  mov     [rbp+57h+var_90], r13
0x180004886  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000488a  inc     r8; int
0x18000488d  cmp     [rbx+r8*2], r13w
0x180004892  jnz     short loc_18000488A
0x180004894  mov     rdx, rbx; unsigned __int16 *
0x180004897  lea     rcx, [rbp+57h+var_A0]; this
0x18000489b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800048a0  nop
0x1800048a1  test    eax, eax
0x1800048a3  jz      loc_180004952
0x1800048a9  mov     rax, [r14]
0x1800048ac  jmp     short loc_1800048E3
0x1800048ae  cmp     ebx, 0FFFFFFFFh
0x1800048b1  jz      short loc_180004866
0x1800048b3  test    ebx, ebx
0x1800048b5  js      loc_180004986
0x1800048bb  cmp     ebx, [rsi+18h]
0x1800048be  jge     loc_180004986
0x1800048c4  movsxd  rcx, ebx
0x1800048c7  mov     rax, [rsi+10h]
0x1800048cb  mov     rbx, [rax+rcx*8]
0x1800048cf  jmp     short loc_180004869
0x1800048d1  mov     rcx, rax; lpsz
0x1800048d4  call    cs:__imp_CharNextW
0x1800048db  nop     dword ptr [rax+rax+00h]
0x1800048e0  mov     [r14], rax
0x1800048e3  cmp     rax, rdi
0x1800048e6  jnz     short loc_1800048D1
0x1800048e8  jmp     short loc_180004900
0x1800048ea  mov     rdx, rbx; unsigned __int16 *
0x1800048ed  mov     r8d, 1; int
0x1800048f3  lea     rcx, [rbp+57h+var_A0]; this
0x1800048f7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800048fc  test    eax, eax
0x1800048fe  jz      short loc_180004952
0x180004900  mov     rcx, [r14]; lpsz
0x180004903  call    cs:__imp_CharNextW
0x18000490a  nop     dword ptr [rax+rax+00h]
0x18000490f  mov     rbx, rax
0x180004912  mov     [r14], rax
0x180004915  movzx   eax, word ptr [rax]
0x180004918  test    ax, ax
0x18000491b  jnz     loc_180004767
0x180004921  mov     rdx, [rbp+57h+pv]
0x180004925  mov     ebx, r13d
0x180004928  mov     [rbp+57h+pv], r13
0x18000492c  mov     [r12], rdx
0x180004930  mov     rcx, [rbp+57h+pv]; pv
0x180004934  call    cs:__imp_CoTaskMemFree
0x18000493b  nop     dword ptr [rax+rax+00h]
0x180004940  mov     eax, ebx
0x180004942  jmp     short loc_18000495E
0x180004944  mov     ebx, 80004005h
0x180004949  jmp     short loc_180004930
0x18000494b  mov     ebx, 80020009h
0x180004950  jmp     short loc_180004930
0x180004952  mov     ebx, 8007000Eh
0x180004957  jmp     short loc_180004930
0x180004959  mov     eax, 80004003h
0x18000495e  mov     rcx, [rbp+57h+var_40]
0x180004962  xor     rcx, rsp; StackCookie
0x180004965  call    __security_check_cookie
0x18000496a  mov     rbx, [rsp+0C0h+arg_8]
0x180004972  add     rsp, 90h
0x180004979  pop     r15
0x18000497b  pop     r14
0x18000497d  pop     r13
0x18000497f  pop     r12
0x180004981  pop     rdi
0x180004982  pop     rsi
0x180004983  pop     rbp
0x180004984  retn
0x180004986  mov     ecx, 0C000008Ch; unsigned int
0x18000498b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180004990  int     3; Trap to Debugger
0x180004991  mov     ecx, 80004005h; int
0x180004996  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000499c  mov     ecx, 80070057h; int
0x1800049a1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800049a7  mov     ecx, 8007000Eh; int
0x1800049ac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
