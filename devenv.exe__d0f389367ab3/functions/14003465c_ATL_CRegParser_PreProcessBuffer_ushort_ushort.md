# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x14003465c`
- end: `0x140034a6b`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `1039`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x14003601c`

## callees

- `0x140001020`
- `0x140033ab0`
- `0x140034528`
- `0x14003465c`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x14003493d`
- `KERNEL32!lstrcmpiW` at `0x14003493d`
- `KERNEL32!EnterCriticalSection` at `0x140034920`
- `KERNEL32!EnterCriticalSection` at `0x140034920`
- `KERNEL32!LeaveCriticalSection` at `0x14003495a`
- `KERNEL32!LeaveCriticalSection` at `0x14003495a`
- `VCRUNTIME140!wcsstr` at `0x140034740`
- `VCRUNTIME140!wcsstr` at `0x140034740`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1400348ea`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1400348ea`
- `USER32!CharNextW` at `0x140034753`
- `USER32!CharNextW` at `0x14003475f`
- `USER32!CharNextW` at `0x14003476b`
- `USER32!CharNextW` at `0x140034777`
- `USER32!CharNextW` at `0x1400347c5`
- `USER32!CharNextW` at `0x1400347db`
- `USER32!CharNextW` at `0x140034857`
- `USER32!CharNextW` at `0x1400348a3`
- `USER32!CharNextW` at `0x1400349bd`
- `USER32!CharNextW` at `0x1400349d6`
- `USER32!CharNextW` at `0x140034753`
- `USER32!CharNextW` at `0x14003475f`
- `USER32!CharNextW` at `0x14003476b`
- `USER32!CharNextW` at `0x140034777`
- `USER32!CharNextW` at `0x1400347c5`
- `USER32!CharNextW` at `0x1400347db`
- `USER32!CharNextW` at `0x140034857`
- `USER32!CharNextW` at `0x1400348a3`
- `USER32!CharNextW` at `0x1400349bd`
- `USER32!CharNextW` at `0x1400349d6`
- `ole32!CoTaskMemFree` at `0x140034a09`
- `ole32!CoTaskMemFree` at `0x140034a09`
- `ole32!CoTaskMemAlloc` at `0x1400346e4`
- `ole32!CoTaskMemAlloc` at `0x1400346e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  const wchar_t *v3; // rsi
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  bool v10; // al
  int v11; // r13d
  char v12; // r12
  char v13; // r15
  wchar_t *v14; // rax
  const WCHAR *v15; // rax
  const WCHAR *v16; // rax
  const WCHAR *v17; // rax
  const unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rdx
  LPWSTR v20; // rax
  WCHAR v21; // cx
  const WCHAR *v22; // r14
  errno_t v23; // eax
  LPCWSTR v24; // rsi
  int v25; // r12d
  __int64 v26; // r15
  const unsigned __int16 *v27; // r15
  __int64 v28; // r8
  const WCHAR *i; // rax
  unsigned __int16 *v30; // rcx
  char v32; // [rsp+20h] [rbp-59h]
  char v33; // [rsp+21h] [rbp-58h]
  bool v34; // [rsp+22h] [rbp-57h]
  _DWORD v35[2]; // [rsp+28h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-49h]
  __int64 v37; // [rsp+38h] [rbp-41h]
  unsigned __int16 **v38; // [rsp+40h] [rbp-39h]
  wchar_t Destination[32]; // [rsp+50h] [rbp-29h] BYREF

  v38 = a3;
  v3 = a2;
  v5 = 0;
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
  v35[0] = 0;
  v35[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
LABEL_12:
    v5 = -2147024882;
    goto LABEL_74;
  }
  *this = v3;
  v10 = ATL::_AtlRegisterPerUser;
  v34 = ATL::_AtlRegisterPerUser;
  v11 = 0;
  v12 = 0;
  v33 = 0;
  v13 = 0;
  v32 = 0;
  if ( *v3 )
  {
    while ( 1 )
    {
      if ( !v10 )
        goto LABEL_35;
      if ( !v11 )
      {
        v14 = wcsstr(v3, L"HKCR");
        if ( v14 )
        {
          if ( v14 == *this )
          {
            v15 = CharNextW(*this);
            *this = v15;
            v16 = CharNextW(v15);
            *this = v16;
            v17 = CharNextW(v16);
            *this = v17;
            *this = CharNextW(v17);
            v37 = 0;
            if ( !ATL::CRegParser::CParseBuffer::Append(
                    (ATL::CRegParser::CParseBuffer *)v35,
                    L"HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClasses",
                    31) )
              goto LABEL_12;
            v12 = 1;
            v33 = 1;
          }
        }
      }
      if ( **this == 39 )
      {
        if ( !v13 )
        {
          v13 = 1;
          v32 = 1;
          goto LABEL_35;
        }
        if ( *CharNextW(*this) == 39 )
        {
          v18 = CharNextW(*this);
          *this = v18;
          if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v35, v18, 1) )
            goto LABEL_12;
          goto LABEL_35;
        }
        v13 = 0;
        v32 = 0;
      }
      else if ( v13 )
      {
        goto LABEL_35;
      }
      if ( **this == 123 )
      {
        ++v11;
      }
      else if ( **this == 125 && !--v11 && v12 == 1 )
      {
        v37 = 0;
        if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v35, L"\r\n\t}\r\n}\r\n", 9) )
          goto LABEL_12;
        v12 = 0;
        v33 = 0;
      }
LABEL_35:
      v19 = *this;
      if ( **this != 37 )
        goto LABEL_38;
      v20 = CharNextW(*this);
      *this = v20;
      v21 = *v20;
      if ( *v20 == 37 )
      {
        v19 = v20;
LABEL_38:
        if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v35, v19, 1) )
          goto LABEL_12;
        goto LABEL_70;
      }
      v22 = 0;
      if ( !v20 )
        goto LABEL_41;
      while ( v21 )
      {
        if ( v21 == 37 )
        {
          v22 = v20;
          break;
        }
        v20 = CharNextW(v20);
        v21 = *v20;
      }
      if ( !v22 )
      {
LABEL_41:
        v5 = -2147352567;
        goto LABEL_74;
      }
      if ( (__int64)(((char *)v22 - (char *)*this) & 0xFFFFFFFFFFFFFFFEuLL) > 62 )
      {
        v5 = -2147467259;
        goto LABEL_74;
      }
      _mm_lfence();
      v23 = wcsncpy_s(Destination, 0x20u, *this, (int)(v22 - *this));
      if ( v23 )
      {
        if ( v23 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v23 == 22 || v23 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v23 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      v24 = this[1];
      EnterCriticalSection((LPCRITICAL_SECTION)(v24 + 16));
      v25 = 0;
      v26 = 0;
      if ( *((int *)v24 + 6) <= 0 )
        goto LABEL_57;
      while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v24 + 1) + 8 * v26), Destination) )
      {
        ++v25;
        ++v26;
        if ( v25 >= *((_DWORD *)v24 + 6) )
          goto LABEL_57;
      }
      if ( v26 == -1 )
      {
LABEL_57:
        v27 = 0;
      }
      else
      {
        if ( v26 < 0 || v25 >= *((_DWORD *)v24 + 6) )
          ATL::AtlThrowImpl(-2147483637);
        _mm_lfence();
        v27 = *(const unsigned __int16 **)(*((_QWORD *)v24 + 2) + 8 * v26);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 16));
      if ( !v27 )
        goto LABEL_41;
      v37 = 0;
      v28 = -1;
      do
        ++v28;
      while ( v27[v28] );
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v35, v27, v28) )
        goto LABEL_12;
      for ( i = *this; i != v22; *this = i )
        i = CharNextW(i);
      v12 = v33;
      v13 = v32;
LABEL_70:
      v3 = CharNextW(*this);
      *this = v3;
      if ( !*v3 )
        break;
      v10 = v34;
    }
  }
  v30 = (unsigned __int16 *)pv;
  pv = 0;
  *v38 = v30;
LABEL_74:
  CoTaskMemFree(pv);
  return v5;
}

```

## disassembly

```asm
0x14003465c  mov     [rsp-8+arg_8], rbx
0x140034661  push    rbp
0x140034662  push    rsi
0x140034663  push    rdi
0x140034664  push    r12
0x140034666  push    r13
0x140034668  push    r14
0x14003466a  push    r15
0x14003466c  lea     rbp, [rsp-27h]
0x140034671  sub     rsp, 0A0h
0x140034678  mov     rax, cs:__security_cookie
0x14003467f  xor     rax, rsp
0x140034682  mov     [rbp+57h+var_40], rax
0x140034686  mov     rax, r8
0x140034689  mov     [rbp+57h+var_90], rax
0x14003468d  mov     rsi, rdx
0x140034690  mov     rdi, rcx
0x140034693  xor     ebx, ebx
0x140034695  test    rdx, rdx
0x140034698  jz      loc_140034A13
0x14003469e  test    rax, rax
0x1400346a1  jz      loc_140034A13
0x1400346a7  mov     [r8], rbx
0x1400346aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400346ae  inc     rax
0x1400346b1  cmp     [rdx+rax*2], bx
0x1400346b5  jnz     short loc_1400346AE
0x1400346b7  add     eax, eax
0x1400346b9  mov     ecx, 3E8h
0x1400346be  cmp     eax, 64h ; 'd'
0x1400346c1  cmovl   eax, ecx
0x1400346c4  mov     [rbp+57h+var_A8], ebx
0x1400346c7  mov     [rbp+57h+var_A4], eax
0x1400346ca  mov     ecx, eax
0x1400346cc  add     rcx, rcx
0x1400346cf  mov     eax, 0FFFFFFFFh
0x1400346d4  cmp     rcx, rax
0x1400346d7  jbe     short loc_1400346E2
0x1400346d9  mov     rax, rbx
0x1400346dc  mov     [rbp+57h+pv], rbx
0x1400346e0  jmp     short loc_1400346F6
0x1400346e2  mov     ecx, ecx; cb
0x1400346e4  call    cs:__imp_CoTaskMemAlloc
0x1400346ea  mov     [rbp+57h+pv], rax
0x1400346ee  test    rax, rax
0x1400346f1  jz      short loc_1400346F6
0x1400346f3  mov     [rax], bx
0x1400346f6  test    rax, rax
0x1400346f9  jnz     short loc_140034705
0x1400346fb  mov     ebx, 8007000Eh
0x140034700  jmp     loc_140034A05
0x140034705  mov     [rdi], rsi
0x140034708  mov     al, cs:?_AtlRegisterPerUser@ATL@@3_NA; bool ATL::_AtlRegisterPerUser
0x14003470e  mov     [rbp+57h+var_AE], al
0x140034711  mov     r13d, ebx
0x140034714  mov     r12b, bl
0x140034717  mov     [rbp+57h+var_AF], bl
0x14003471a  mov     r15b, bl
0x14003471d  mov     [rbp+57h+var_B0], bl
0x140034720  cmp     [rsi], bx
0x140034723  jz      loc_1400349F6
0x140034729  cmp     al, 1
0x14003472b  jnz     loc_14003484B
0x140034731  test    r13d, r13d
0x140034734  jnz     short loc_1400347A7
0x140034736  lea     rdx, aHkcr; "HKCR"
0x14003473d  mov     rcx, rsi; Str
0x140034740  call    cs:__imp_wcsstr
0x140034746  test    rax, rax
0x140034749  jz      short loc_1400347A7
0x14003474b  cmp     rax, [rdi]
0x14003474e  jnz     short loc_1400347A7
0x140034750  mov     rcx, [rdi]; lpsz
0x140034753  call    cs:__imp_CharNextW
0x140034759  mov     [rdi], rax
0x14003475c  mov     rcx, rax; lpsz
0x14003475f  call    cs:__imp_CharNextW
0x140034765  mov     [rdi], rax
0x140034768  mov     rcx, rax; lpsz
0x14003476b  call    cs:__imp_CharNextW
0x140034771  mov     [rdi], rax
0x140034774  mov     rcx, rax; lpsz
0x140034777  call    cs:__imp_CharNextW
0x14003477d  mov     [rdi], rax
0x140034780  mov     [rbp+57h+var_98], rbx
0x140034784  lea     r8d, [r13+1Fh]; int
0x140034788  lea     rdx, aHkcuSoftwareCl; "HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClass"...
0x14003478f  lea     rcx, [rbp+57h+var_A8]; this
0x140034793  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140034798  test    eax, eax
0x14003479a  jz      loc_1400346FB
0x1400347a0  mov     r12b, 1
0x1400347a3  mov     [rbp+57h+var_AF], r12b
0x1400347a7  mov     rcx, [rdi]; lpsz
0x1400347aa  mov     esi, 27h ; '''
0x1400347af  cmp     si, [rcx]
0x1400347b2  jnz     short loc_140034800
0x1400347b4  test    r15b, r15b
0x1400347b7  jnz     short loc_1400347C5
0x1400347b9  mov     r15b, 1
0x1400347bc  mov     [rbp+57h+var_B0], r15b
0x1400347c0  jmp     loc_14003484B
0x1400347c5  call    cs:__imp_CharNextW
0x1400347cb  cmp     si, [rax]
0x1400347ce  jz      short loc_1400347D8
0x1400347d0  mov     r15b, bl
0x1400347d3  mov     [rbp+57h+var_B0], bl
0x1400347d6  jmp     short loc_140034805
0x1400347d8  mov     rcx, [rdi]; lpsz
0x1400347db  call    cs:__imp_CharNextW
0x1400347e1  mov     [rdi], rax
0x1400347e4  mov     r8d, 1; int
0x1400347ea  mov     rdx, rax; unsigned __int16 *
0x1400347ed  lea     rcx, [rbp+57h+var_A8]; this
0x1400347f1  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1400347f6  test    eax, eax
0x1400347f8  jz      loc_1400346FB
0x1400347fe  jmp     short loc_14003484B
0x140034800  test    r15b, r15b
0x140034803  jnz     short loc_14003484B
0x140034805  mov     rax, [rdi]
0x140034808  cmp     word ptr [rax], 7Bh ; '{'
0x14003480c  jnz     short loc_140034813
0x14003480e  inc     r13d
0x140034811  jmp     short loc_14003484B
0x140034813  cmp     word ptr [rax], 7Dh ; '}'
0x140034817  jnz     short loc_14003484B
0x140034819  sub     r13d, 1
0x14003481d  jnz     short loc_14003484B
0x14003481f  cmp     r12b, 1
0x140034823  jnz     short loc_14003484B
0x140034825  mov     [rbp+57h+var_98], rbx
0x140034829  lea     r8d, [r13+9]; int
0x14003482d  lea     rdx, asc_14007F6D0; "\r\n\t}\r\n}\r\n"
0x140034834  lea     rcx, [rbp+57h+var_A8]; this
0x140034838  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14003483d  test    eax, eax
0x14003483f  jz      loc_1400346FB
0x140034845  mov     r12b, bl
0x140034848  mov     [rbp+57h+var_AF], bl
0x14003484b  mov     rdx, [rdi]
0x14003484e  cmp     word ptr [rdx], 25h ; '%'
0x140034852  jnz     short loc_14003486C
0x140034854  mov     rcx, rdx; lpsz
0x140034857  call    cs:__imp_CharNextW
0x14003485d  mov     [rdi], rax
0x140034860  movzx   ecx, word ptr [rax]
0x140034863  cmp     cx, 25h ; '%'
0x140034867  jnz     short loc_140034888
0x140034869  mov     rdx, rax; unsigned __int16 *
0x14003486c  mov     r8d, 1; int
0x140034872  lea     rcx, [rbp+57h+var_A8]; this
0x140034876  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14003487b  test    eax, eax
0x14003487d  jz      loc_1400346FB
0x140034883  jmp     loc_1400349D3
0x140034888  mov     r14, rbx
0x14003488b  test    rax, rax
0x14003488e  jnz     short loc_1400348AC
0x140034890  mov     ebx, 80020009h
0x140034895  jmp     loc_140034A05
0x14003489a  cmp     cx, 25h ; '%'
0x14003489e  jz      short loc_1400348B3
0x1400348a0  mov     rcx, rax; lpsz
0x1400348a3  call    cs:__imp_CharNextW
0x1400348a9  movzx   ecx, word ptr [rax]
0x1400348ac  test    cx, cx
0x1400348af  jnz     short loc_14003489A
0x1400348b1  jmp     short loc_1400348B6
0x1400348b3  mov     r14, rax
0x1400348b6  test    r14, r14
0x1400348b9  jz      short loc_140034890
0x1400348bb  mov     rax, r14
0x1400348be  sub     rax, [rdi]
0x1400348c1  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400348c5  cmp     rax, 3Eh ; '>'
0x1400348c9  jg      loc_1400349EF
0x1400348cf  lfence
0x1400348d2  mov     rax, r14
0x1400348d5  sub     rax, [rdi]
0x1400348d8  sar     rax, 1
0x1400348db  movsxd  r9, eax; MaxCount
0x1400348de  mov     r8, [rdi]; Source
0x1400348e1  mov     edx, 20h ; ' '; SizeInWords
0x1400348e6  lea     rcx, [rbp+57h+Destination]; Destination
0x1400348ea  call    cs:__imp_wcsncpy_s
0x1400348f0  test    eax, eax
0x1400348f2  jz      short loc_140034918
0x1400348f4  cmp     eax, 0Ch
0x1400348f7  jz      loc_140034A60
0x1400348fd  cmp     eax, 16h
0x140034900  jz      loc_140034A55
0x140034906  cmp     eax, 22h ; '"'
0x140034909  jz      loc_140034A55
0x14003490f  cmp     eax, 50h ; 'P'
0x140034912  jnz     loc_140034A4A
0x140034918  mov     rsi, [rdi+8]
0x14003491c  lea     rcx, [rsi+20h]; lpCriticalSection
0x140034920  call    cs:__imp_EnterCriticalSection
0x140034926  mov     r12d, ebx
0x140034929  mov     r15, rbx
0x14003492c  cmp     [rsi+18h], ebx
0x14003492f  jle     short loc_140034953
0x140034931  mov     rax, [rsi+8]
0x140034935  lea     rdx, [rbp+57h+Destination]; lpString2
0x140034939  mov     rcx, [rax+r15*8]; lpString1
0x14003493d  call    cs:__imp_lstrcmpiW
0x140034943  test    eax, eax
0x140034945  jz      short loc_140034994
0x140034947  inc     r12d
0x14003494a  inc     r15
0x14003494d  cmp     r12d, [rsi+18h]
0x140034951  jl      short loc_140034931
0x140034953  mov     r15, rbx
0x140034956  lea     rcx, [rsi+20h]; lpCriticalSection
0x14003495a  call    cs:__imp_LeaveCriticalSection
0x140034960  test    r15, r15
0x140034963  jz      loc_140034890
0x140034969  mov     [rbp+57h+var_98], rbx
0x14003496d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140034971  inc     r8; int
0x140034974  cmp     [r15+r8*2], bx
0x140034979  jnz     short loc_140034971
0x14003497b  mov     rdx, r15; unsigned __int16 *
0x14003497e  lea     rcx, [rbp+57h+var_A8]; this
0x140034982  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140034987  test    eax, eax
0x140034989  jz      loc_1400346FB
0x14003498f  mov     rax, [rdi]
0x140034992  jmp     short loc_1400349C6
0x140034994  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140034998  jz      short loc_140034953
0x14003499a  test    r15, r15
0x14003499d  js      loc_140034A3F
0x1400349a3  cmp     r12d, [rsi+18h]
0x1400349a7  jge     loc_140034A3F
0x1400349ad  lfence
0x1400349b0  mov     rax, [rsi+10h]
0x1400349b4  mov     r15, [rax+r15*8]
0x1400349b8  jmp     short loc_140034956
0x1400349ba  mov     rcx, rax; lpsz
0x1400349bd  call    cs:__imp_CharNextW
0x1400349c3  mov     [rdi], rax
0x1400349c6  cmp     rax, r14
0x1400349c9  jnz     short loc_1400349BA
0x1400349cb  mov     r12b, [rbp+57h+var_AF]
0x1400349cf  mov     r15b, [rbp+57h+var_B0]
0x1400349d3  mov     rcx, [rdi]; lpsz
0x1400349d6  call    cs:__imp_CharNextW
0x1400349dc  mov     rsi, rax
0x1400349df  mov     [rdi], rax
0x1400349e2  cmp     [rax], bx
0x1400349e5  jz      short loc_1400349F6
0x1400349e7  mov     al, [rbp+57h+var_AE]
0x1400349ea  jmp     loc_140034729
0x1400349ef  mov     ebx, 80004005h
0x1400349f4  jmp     short loc_140034A05
0x1400349f6  mov     rcx, [rbp+57h+pv]
0x1400349fa  mov     [rbp+57h+pv], rbx
0x1400349fe  mov     rax, [rbp+57h+var_90]
0x140034a02  mov     [rax], rcx
0x140034a05  mov     rcx, [rbp+57h+pv]; pv
0x140034a09  call    cs:__imp_CoTaskMemFree
0x140034a0f  mov     eax, ebx
0x140034a11  jmp     short loc_140034A18
0x140034a13  mov     eax, 80004003h
0x140034a18  mov     rcx, [rbp+57h+var_40]
0x140034a1c  xor     rcx, rsp; StackCookie
0x140034a1f  call    __security_check_cookie
0x140034a24  mov     rbx, [rsp+0D0h+arg_8]
0x140034a2c  add     rsp, 0A0h
0x140034a33  pop     r15
0x140034a35  pop     r14
0x140034a37  pop     r13
0x140034a39  pop     r12
0x140034a3b  pop     rdi
0x140034a3c  pop     rsi
0x140034a3d  pop     rbp
0x140034a3e  retn
0x140034a3f  mov     ecx, 8000000Bh; int
0x140034a44  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140034a4a  mov     ecx, 80004005h; int
0x140034a4f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140034a55  mov     ecx, 80070057h; int
0x140034a5a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140034a60  mov     ecx, 8007000Eh; int
0x140034a65  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
