# CXMLTag::CreateCustomPropertyNameFromTagName(CLMString const &,wchar_t * *)

- ea: `0x18000c5f0`
- end: `0x18000cb3a`
- name: `?CreateCustomPropertyNameFromTagName@CXMLTag@@AEAAXAEBVCLMString@@PEAPEA_W@Z`
- size: `1354`
- prototype: `void __fastcall(CXMLTag *__hidden this, const struct CLMString *, wchar_t **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bea0`

## callees

- `0x18000aab0`
- `0x18000c5f0`
- `0x180011108`
- `0x1800111bc`
- `0x180013500`
- `0x180013968`
- `0x180014130`
- `0x180014544`
- `0x18001457c`
- `0x180020834`
- `0x18002192c`
- `0x180023310`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c820`
- `api-ms-win-core-string-l1-1-0!GetStringTypeW` at `0x18000c694`
- `api-ms-win-core-string-l1-1-0!GetStringTypeW` at `0x18000c694`

## string_xrefs

- `0x18000c838`: `onecoreuap\base\appmodel\search\filters\html\nlhtml\xmltag.cxx`
- `0x18000cae4`: `onecoreuap\base\appmodel\search\filters\html\nlhtml\xmltag.cxx`
- `0x18000cb03`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
void __fastcall CXMLTag::CreateCustomPropertyNameFromTagName(CXMLTag *this, const struct CLMString *a2, wchar_t **a3)
{
  WORD *v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  WORD *v11; // r12
  const WCHAR *v12; // rdx
  int v13; // edi
  char *v14; // r15
  wchar_t *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  void **v18; // r10
  unsigned int v19; // r11d
  unsigned __int64 v20; // rcx
  __int64 v21; // rsi
  wchar_t v22; // r13
  signed int LastError; // eax
  _WORD *i; // r8
  __int16 v25; // ax
  WCHAR v26; // cx
  int v27; // edi
  int v28; // edi
  int v29; // edi
  int v30; // edi
  int v31; // edi
  CXMLTag *v32; // rcx
  CXMLTag *v33; // rcx
  CXMLTag *v34; // rcx
  unsigned __int8 v35; // al
  char v36; // r8
  __int16 v37; // r9
  unsigned int v38; // [rsp+20h] [rbp-10h]
  WORD CharType[2]; // [rsp+30h] [rbp+0h] BYREF
  int v40; // [rsp+34h] [rbp+4h]
  int v41; // [rsp+38h] [rbp+8h]
  int v42; // [rsp+3Ch] [rbp+Ch]
  int v43; // [rsp+40h] [rbp+10h]
  WORD *v44; // [rsp+48h] [rbp+18h]
  wchar_t **v45; // [rsp+50h] [rbp+20h]
  void **v46; // [rsp+60h] [rbp+30h] BYREF
  wchar_t *v47; // [rsp+68h] [rbp+38h]
  __int64 v48; // [rsp+70h] [rbp+40h]
  wchar_t v49[36]; // [rsp+78h] [rbp+48h] BYREF
  _QWORD v50[2]; // [rsp+C0h] [rbp+90h] BYREF
  int v51; // [rsp+D0h] [rbp+A0h]
  int v52; // [rsp+D4h] [rbp+A4h]
  wchar_t v53[36]; // [rsp+D8h] [rbp+A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+138h]

  v45 = a3;
  v5 = 0;
  v44 = 0;
  v6 = *((unsigned int *)a2 + 5);
  if ( (unsigned int)v6 > 0x40 )
  {
    v5 = (WORD *)operator new[](saturated_mul(v6, 2u));
    v44 = v5;
    v11 = v5;
  }
  else
  {
    v7 = 2 * v6 + 15;
    if ( v7 <= 2 * v6 )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
    v9 = alloca(v8);
    v10 = alloca(v8);
    v11 = CharType;
  }
  v12 = (const WCHAR *)*((_QWORD *)a2 + 1);
  if ( g_nOSWinNT == 2 )
  {
    if ( !GetStringTypeW(1u, v12, *((_DWORD *)a2 + 5), v11) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\xmltag.cxx",
        (const char *)(unsigned int)LastError,
        v38);
    }
  }
  else
  {
    for ( i = v11; ; ++i )
    {
      v26 = *v12;
      if ( !*v12 )
        break;
      if ( (unsigned __int16)(v26 - 48) <= 9u
        || (unsigned __int16)(v26 - 97) <= 5u
        || (unsigned __int16)(v26 - 65) <= 5u )
      {
        v25 = 128;
      }
      else
      {
        v25 = 0;
      }
      *i = v25;
      ++v12;
    }
  }
  v13 = 0;
  v14 = (char *)this + 1432;
  *((_DWORD *)v14 + 5) = 0;
  **((_WORD **)v14 + 1) = 0;
  v15 = v49;
  v47 = v49;
  v16 = 33;
  v48 = 33;
  v17 = 0;
  v49[0] = 0;
  v18 = &TLMString<32,32,256>::`vftable';
  v46 = &TLMString<32,32,256>::`vftable';
  v43 = 0;
  v42 = 0;
  v41 = 0;
  v40 = 0;
  v19 = 0;
  while ( 1 )
  {
    *(_DWORD *)CharType = v19;
    if ( v19 >= *((_DWORD *)a2 + 5) )
      break;
    v20 = (unsigned int)v17 + 2LL;
    if ( v20 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v20, v15, v16);
    v21 = v19;
    v22 = *(_WORD *)(*((_QWORD *)a2 + 1) + 2LL * v19);
    if ( (unsigned int)v20 > (unsigned int)v16 )
    {
      ((void (__fastcall *)(void ***, _QWORD))*v18)(&v46, (unsigned int)v20);
      LODWORD(v17) = HIDWORD(v48);
      v15 = v47;
      v19 = *(_DWORD *)CharType;
    }
    v15[(unsigned int)v17] = v22;
    ++HIDWORD(v48);
    v47[HIDWORD(v48)] = 0;
    if ( v13 )
    {
      v27 = v13 - 1;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( v29 )
          {
            v30 = v29 - 1;
            if ( v30 )
            {
              v31 = v30 - 1;
              if ( v31 )
              {
                if ( v31 != 1 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x3C2,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\xmltag.cxx",
                    (const char *)0x8000FFFFLL,
                    v38);
                if ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v21) == 95 )
                {
                  v13 = 0;
                  CXMLTag::ByteValueFromWChar((CXMLTag *)0x5F, v43);
                  CXMLTag::ByteValueFromWChar(v32, v42);
                  CXMLTag::ByteValueFromWChar(v33, v41);
                  v35 = CXMLTag::ByteValueFromWChar(v34, v40);
                  CLMString::operator+=(v14, (unsigned __int16)(v37 | (unsigned __int8)(v35 + v36)));
                  CLMString::Truncate((CLMString *)&v46, 0);
                  goto LABEL_20;
                }
              }
              else if ( SLOBYTE(v11[v21]) < 0 )
              {
                v40 = *(unsigned __int16 *)(*((_QWORD *)a2 + 1) + 2 * v21);
                v13 = 6;
                goto LABEL_21;
              }
            }
            else if ( SLOBYTE(v11[v21]) < 0 )
            {
              v41 = *(unsigned __int16 *)(*((_QWORD *)a2 + 1) + 2 * v21);
              v13 = 5;
              goto LABEL_21;
            }
          }
          else if ( SLOBYTE(v11[v21]) < 0 )
          {
            v42 = *(unsigned __int16 *)(*((_QWORD *)a2 + 1) + 2 * v21);
            v13 = 4;
            goto LABEL_21;
          }
        }
        else if ( SLOBYTE(v11[v21]) < 0 )
        {
          v43 = *(unsigned __int16 *)(*((_QWORD *)a2 + 1) + 2 * v21);
          v13 = 3;
          goto LABEL_21;
        }
      }
      else if ( ((*(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v21) - 88) & 0xFFDF) == 0 )
      {
        v13 = 2;
        goto LABEL_21;
      }
    }
    else if ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v21) == 95 )
    {
      v13 = 1;
      goto LABEL_21;
    }
    if ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v21) != 95 )
    {
      (*(void (__fastcall **)(char *, wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v14 + 32LL))(
        v14,
        v47,
        *((unsigned int *)v14 + 5),
        HIDWORD(v48));
      HIDWORD(v48) = 0;
      *v47 = 0;
      v13 = 0;
LABEL_20:
      v19 = *(_DWORD *)CharType;
      goto LABEL_21;
    }
    if ( (unsigned int)(HIDWORD(v48) - 1) > HIDWORD(v48) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x40C,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
        (const char *)0xCE,
        v38);
    (*(void (__fastcall **)(char *, wchar_t *, _QWORD))(*(_QWORD *)v14 + 32LL))(v14, v47, *((unsigned int *)v14 + 5));
    v50[1] = v53;
    v51 = 33;
    wcscpy(v53, L"_");
    v13 = 1;
    v52 = 1;
    v50[0] = &TLMString<32,32,256>::`vftable';
    ((void (__fastcall *)(void ***, wchar_t *, _QWORD, __int64))v46[4])(&v46, v53, 0, 0xFFFFFFFFLL);
    v50[0] = &TLMString<32,32,256>::`vftable';
    CLMString::DeleteBuf((CLMString *)v50, v53);
    v19 = *(_DWORD *)CharType;
LABEL_21:
    ++v19;
    v17 = HIDWORD(v48);
    v16 = (unsigned int)v48;
    v15 = v47;
    v18 = v46;
  }
  if ( v13 )
    (*(void (__fastcall **)(char *, wchar_t *, _QWORD, __int64))(*(_QWORD *)v14 + 32LL))(
      v14,
      v15,
      *((unsigned int *)v14 + 5),
      v17);
  *v45 = (wchar_t *)*((_QWORD *)v14 + 1);
  v46 = &TLMString<32,32,256>::`vftable';
  CLMString::DeleteBuf((CLMString *)&v46, v49);
  v46 = &CLMString::`vftable';
  if ( v5 )
    operator delete(v5);
}

```

## disassembly

```asm
0x18000c5f0  push    rbp
0x18000c5f2  push    rsi
0x18000c5f3  push    rdi
0x18000c5f4  push    r12
0x18000c5f6  push    r13
0x18000c5f8  push    r14
0x18000c5fa  push    r15
0x18000c5fc  sub     rsp, 130h
0x18000c603  lea     rbp, [rsp+30h]
0x18000c608  mov     [rbp+130h+arg_18], rbx
0x18000c60f  mov     rax, cs:__security_cookie
0x18000c616  xor     rax, rbp
0x18000c619  mov     [rbp+130h+var_40], rax
0x18000c620  mov     [rbp+130h+var_110], r8
0x18000c624  mov     r14, rdx
0x18000c627  mov     r15, rcx
0x18000c62a  xor     r13d, r13d
0x18000c62d  mov     ebx, r13d
0x18000c630  mov     [rbp+130h+var_118], rbx
0x18000c634  mov     edx, [rdx+14h]
0x18000c637  lea     edi, [r13+2]
0x18000c63b  cmp     edx, 40h ; '@'
0x18000c63e  ja      loc_18000C84A
0x18000c644  lea     rax, [rdx+rdx]
0x18000c648  lea     rcx, [rax+0Fh]
0x18000c64c  cmp     rcx, rax
0x18000c64f  ja      short loc_18000C65B
0x18000c651  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000c65b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c65f  mov     rax, rcx
0x18000c662  call    _alloca_probe
0x18000c667  sub     rsp, rcx
0x18000c66a  lea     r12, [rsp+160h+CharType]
0x18000c66f  mov     r10d, 5
0x18000c675  lea     r9d, [r10+7Bh]
0x18000c679  mov     rdx, [r14+8]; lpSrcStr
0x18000c67d  cmp     cs:?g_nOSWinNT@@3HA, edi; int g_nOSWinNT
0x18000c683  jnz     loc_18000C927
0x18000c689  mov     r9, r12; lpCharType
0x18000c68c  mov     r8d, [r14+14h]; cchSrc
0x18000c690  lea     ecx, [r10-4]; dwInfoType
0x18000c694  call    cs:__imp_GetStringTypeW
0x18000c69a  test    eax, eax
0x18000c69c  jz      loc_18000C820
0x18000c6a2  mov     edi, r13d
0x18000c6a5  add     r15, 598h
0x18000c6ac  mov     [r15+14h], r13d
0x18000c6b0  mov     rcx, [r15+8]
0x18000c6b4  mov     [rcx], r13w
0x18000c6b8  lea     rdx, [rbp+130h+var_E8]
0x18000c6bc  mov     [rbp+130h+var_F8], rdx
0x18000c6c0  mov     r8d, 21h ; '!'
0x18000c6c6  mov     [rbp+130h+var_F0], r8
0x18000c6ca  mov     r9d, r13d
0x18000c6cd  mov     [rbp+130h+var_E8], r13w
0x18000c6d2  lea     rsi, ??_7?$TLMString@$0CA@$0CA@$0BAA@@@6B@; const TLMString<32,32,256>::`vftable'
0x18000c6d9  mov     r10, rsi
0x18000c6dc  mov     [rbp+130h+var_100], rsi
0x18000c6e0  mov     [rbp+130h+var_120], r13d
0x18000c6e4  mov     [rbp+130h+var_124], r13d
0x18000c6e8  mov     [rbp+130h+var_128], r13d
0x18000c6ec  mov     [rbp+130h+var_12C], r13d
0x18000c6f0  mov     r11d, r13d
0x18000c6f3  mov     dword ptr [rbp+130h+CharType], r11d
0x18000c6f7  cmp     r11d, [r14+14h]
0x18000c6fb  jb      short loc_18000C75E
0x18000c6fd  test    edi, edi
0x18000c6ff  jnz     loc_18000CB15
0x18000c705  mov     rax, [r15+8]
0x18000c709  mov     rcx, [rbp+130h+var_110]
0x18000c70d  mov     [rcx], rax
0x18000c710  mov     [rbp+130h+var_100], rsi
0x18000c714  lea     rdx, [rbp+130h+var_E8]; wchar_t *
0x18000c718  lea     rcx, [rbp+130h+var_100]; this
0x18000c71c  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x18000c721  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18000c728  mov     [rbp+130h+var_100], rax
0x18000c72c  test    rbx, rbx
0x18000c72f  jnz     loc_18000CB2D
0x18000c735  mov     rcx, [rbp+130h+var_40]
0x18000c73c  xor     rcx, rbp; StackCookie
0x18000c73f  call    __security_check_cookie
0x18000c744  mov     rbx, [rbp+130h+arg_18]
0x18000c74b  lea     rsp, [rbp+100h]
0x18000c752  pop     r15
0x18000c754  pop     r14
0x18000c756  pop     r13
0x18000c758  pop     r12
0x18000c75a  pop     rdi
0x18000c75b  pop     rsi
0x18000c75c  pop     rbp
0x18000c75d  retn
0x18000c75e  mov     ecx, r9d
0x18000c761  add     rcx, 2
0x18000c765  mov     eax, 0FFFFFFFFh
0x18000c76a  cmp     rcx, rax
0x18000c76d  ja      loc_18000C81A
0x18000c773  mov     esi, r11d
0x18000c776  mov     rax, [r14+8]
0x18000c77a  movzx   r13d, word ptr [rax+rsi*2]
0x18000c77f  cmp     ecx, r8d
0x18000c782  ja      loc_18000C969
0x18000c788  mov     eax, r9d
0x18000c78b  mov     [rdx+rax*2], r13w
0x18000c790  mov     eax, dword ptr [rbp+130h+var_F0+4]
0x18000c793  inc     eax
0x18000c795  mov     dword ptr [rbp+130h+var_F0+4], eax
0x18000c798  mov     edx, eax
0x18000c79a  xor     r13d, r13d
0x18000c79d  mov     rax, [rbp+130h+var_F8]
0x18000c7a1  mov     [rax+rdx*2], r13w
0x18000c7a6  test    edi, edi
0x18000c7a8  jnz     loc_18000C988
0x18000c7ae  mov     rax, [r14+8]
0x18000c7b2  lea     ecx, [rdi+5Fh]
0x18000c7b5  cmp     [rax+rsi*2], cx
0x18000c7b9  jz      loc_18000CAC3
0x18000c7bf  mov     rax, [r14+8]
0x18000c7c3  cmp     [rax+rsi*2], cx
0x18000c7c7  jz      loc_18000C872
0x18000c7cd  mov     rax, [r15]
0x18000c7d0  mov     r9d, dword ptr [rbp+130h+var_F0+4]
0x18000c7d4  mov     r8d, [r15+14h]
0x18000c7d8  mov     rdx, [rbp+130h+var_F8]
0x18000c7dc  mov     rcx, r15
0x18000c7df  mov     rax, [rax+20h]
0x18000c7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7e8  mov     dword ptr [rbp+130h+var_F0+4], r13d
0x18000c7ec  mov     rax, [rbp+130h+var_F8]
0x18000c7f0  mov     [rax], r13w
0x18000c7f4  mov     edi, r13d
0x18000c7f7  mov     r11d, dword ptr [rbp+130h+CharType]
0x18000c7fb  lea     rsi, ??_7?$TLMString@$0CA@$0CA@$0BAA@@@6B@; const TLMString<32,32,256>::`vftable'
0x18000c802  inc     r11d
0x18000c805  mov     r9d, dword ptr [rbp+130h+var_F0+4]
0x18000c809  mov     r8d, dword ptr [rbp+130h+var_F0]
0x18000c80d  mov     rdx, [rbp+130h+var_F8]
0x18000c811  mov     r10, [rbp+130h+var_100]
0x18000c815  jmp     loc_18000C6F3
0x18000c81a  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18000c820  call    cs:__imp_GetLastError
0x18000c826  test    eax, eax
0x18000c828  jg      loc_18000C91A
0x18000c82e  mov     rcx, [rbp+138h]; this
0x18000c835  mov     r9d, eax; char *
0x18000c838  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000c83f  mov     edx, 35Ah; void *
0x18000c844  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c84a  mov     rax, rdi
0x18000c84d  mul     rdx
0x18000c850  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c857  cmovb   rax, rcx
0x18000c85b  mov     rcx, rax; unsigned __int64
0x18000c85e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c863  mov     rbx, rax
0x18000c866  mov     [rbp+130h+var_118], rax
0x18000c86a  mov     r12, rax
0x18000c86d  jmp     loc_18000C66F
0x18000c872  mov     eax, dword ptr [rbp+130h+var_F0+4]
0x18000c875  lea     r9d, [rax-1]
0x18000c879  cmp     r9d, eax
0x18000c87c  ja      loc_18000CAF6
0x18000c882  mov     rax, [r15]
0x18000c885  mov     r8d, [r15+14h]
0x18000c889  mov     rdx, [rbp+130h+var_F8]
0x18000c88d  mov     rcx, r15
0x18000c890  mov     rax, [rax+20h]
0x18000c894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c899  lea     rax, [rbp+130h+var_88]
0x18000c8a0  mov     [rbp+130h+var_98], rax
0x18000c8a7  mov     [rbp+130h+var_90], 21h ; '!'
0x18000c8b1  mov     dword ptr [rbp+130h+var_88], 5Fh ; '_'
0x18000c8bb  mov     edi, 1
0x18000c8c0  mov     [rbp+130h+var_8C], edi
0x18000c8c6  lea     rsi, ??_7?$TLMString@$0CA@$0CA@$0BAA@@@6B@; const TLMString<32,32,256>::`vftable'
0x18000c8cd  mov     [rbp+130h+var_A0], rsi
0x18000c8d4  mov     rax, [rbp+130h+var_100]
0x18000c8d8  mov     r9d, 0FFFFFFFFh
0x18000c8de  xor     r8d, r8d
0x18000c8e1  lea     rdx, [rbp+130h+var_88]
0x18000c8e8  lea     rcx, [rbp+130h+var_100]
0x18000c8ec  mov     rax, [rax+20h]
0x18000c8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8f5  nop
0x18000c8f6  mov     [rbp+130h+var_A0], rsi
0x18000c8fd  lea     rdx, [rbp+130h+var_88]; wchar_t *
0x18000c904  lea     rcx, [rbp+130h+var_A0]; this
0x18000c90b  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x18000c910  nop
0x18000c911  mov     r11d, dword ptr [rbp+130h+CharType]
0x18000c915  jmp     loc_18000C802
0x18000c91a  movzx   eax, ax
0x18000c91d  or      eax, 80070000h
0x18000c922  jmp     loc_18000C82E
0x18000c927  mov     r8, r12
0x18000c92a  jmp     short loc_18000C95B
0x18000c92c  lea     eax, [rcx-30h]
0x18000c92f  cmp     ax, 9
0x18000c933  jbe     short loc_18000C94D
0x18000c935  lea     eax, [rcx-61h]
0x18000c938  cmp     ax, r10w
0x18000c93c  jbe     short loc_18000C94D
0x18000c93e  sub     cx, 41h ; 'A'
0x18000c942  cmp     cx, r10w
0x18000c946  jbe     short loc_18000C94D
0x18000c948  mov     eax, r13d
0x18000c94b  jmp     short loc_18000C951
0x18000c94d  movzx   eax, r9w
0x18000c951  mov     [r8], ax
0x18000c955  add     rdx, rdi
0x18000c958  add     r8, rdi
0x18000c95b  movzx   ecx, word ptr [rdx]
0x18000c95e  cmp     r13w, cx
0x18000c962  jnz     short loc_18000C92C
0x18000c964  jmp     loc_18000C6A2
0x18000c969  mov     edx, ecx
0x18000c96b  lea     rcx, [rbp+130h+var_100]
0x18000c96f  mov     rax, [r10]
0x18000c972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c977  mov     r9d, dword ptr [rbp+130h+var_F0+4]
0x18000c97b  mov     rdx, [rbp+130h+var_F8]
0x18000c97f  mov     r11d, dword ptr [rbp+130h+CharType]
0x18000c983  jmp     loc_18000C788
0x18000c988  sub     edi, 1
0x18000c98b  jz      loc_18000CAA3
0x18000c991  sub     edi, 1
0x18000c994  jz      loc_18000CA87
0x18000c99a  sub     edi, 1
0x18000c99d  jz      loc_18000CA6B
0x18000c9a3  sub     edi, 1
0x18000c9a6  jz      loc_18000CA4F
0x18000c9ac  sub     edi, 1
0x18000c9af  jz      short loc_18000CA2F
0x18000c9b1  cmp     edi, 1
0x18000c9b4  jnz     loc_18000CAD7
0x18000c9ba  mov     rax, [r14+8]
0x18000c9be  lea     ecx, [rdi+5Eh]; this
0x18000c9c1  cmp     [rax+rsi*2], cx
0x18000c9c5  jnz     loc_18000C7BF
0x18000c9cb  mov     edi, r13d
0x18000c9ce  movzx   edx, word ptr [rbp+130h+var_120]; wchar_t
0x18000c9d2  call    ?ByteValueFromWChar@CXMLTag@@AEAAE_W@Z; CXMLTag::ByteValueFromWChar(wchar_t)
0x18000c9d7  mov     r8b, al
0x18000c9da  shl     r8b, 4
0x18000c9de  movzx   edx, word ptr [rbp+130h+var_124]; wchar_t
0x18000c9e2  call    ?ByteValueFromWChar@CXMLTag@@AEAAE_W@Z; CXMLTag::ByteValueFromWChar(wchar_t)
0x18000c9e7  add     r8b, al
0x18000c9ea  movzx   r9d, r8b
0x18000c9ee  shl     r9w, 8
0x18000c9f3  movzx   edx, word ptr [rbp+130h+var_128]; wchar_t
0x18000c9f7  call    ?ByteValueFromWChar@CXMLTag@@AEAAE_W@Z; CXMLTag::ByteValueFromWChar(wchar_t)
0x18000c9fc  mov     r8b, al
0x18000c9ff  shl     r8b, 4
0x18000ca03  movzx   edx, word ptr [rbp+130h+var_12C]; wchar_t
0x18000ca07  call    ?ByteValueFromWChar@CXMLTag@@AEAAE_W@Z; CXMLTag::ByteValueFromWChar(wchar_t)
0x18000ca0c  add     r8b, al
0x18000ca0f  movzx   edx, r8b
0x18000ca13  or      dx, r9w
0x18000ca17  mov     rcx, r15
0x18000ca1a  call    ??YCLMString@@QEAAX_W@Z; CLMString::operator+=(wchar_t)
0x18000ca1f  xor     edx, edx; unsigned int
0x18000ca21  lea     rcx, [rbp+130h+var_100]; this
0x18000ca25  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x18000ca2a  jmp     loc_18000C7F7
0x18000ca2f  test    byte ptr [r12+rsi*2], 80h
0x18000ca34  jz      loc_18000CACD
0x18000ca3a  mov     rax, [r14+8]
0x18000ca3e  movzx   eax, word ptr [rax+rsi*2]
0x18000ca42  mov     [rbp+130h+var_12C], eax
0x18000ca45  mov     edi, 6
0x18000ca4a  jmp     loc_18000C7FB
0x18000ca4f  test    byte ptr [r12+rsi*2], 80h
0x18000ca54  jz      short loc_18000CACD
0x18000ca56  mov     rax, [r14+8]
0x18000ca5a  movzx   eax, word ptr [rax+rsi*2]
0x18000ca5e  mov     [rbp+130h+var_128], eax
0x18000ca61  mov     edi, 5
0x18000ca66  jmp     loc_18000C7FB
0x18000ca6b  test    byte ptr [r12+rsi*2], 80h
0x18000ca70  jz      short loc_18000CACD
0x18000ca72  mov     rax, [r14+8]
0x18000ca76  movzx   eax, word ptr [rax+rsi*2]
0x18000ca7a  mov     [rbp+130h+var_124], eax
0x18000ca7d  mov     edi, 4
0x18000ca82  jmp     loc_18000C7FB
0x18000ca87  test    byte ptr [r12+rsi*2], 80h
0x18000ca8c  jz      short loc_18000CACD
0x18000ca8e  mov     rax, [r14+8]
0x18000ca92  movzx   eax, word ptr [rax+rsi*2]
0x18000ca96  mov     [rbp+130h+var_120], eax
0x18000ca99  mov     edi, 3
0x18000ca9e  jmp     loc_18000C7FB
0x18000caa3  mov     rax, [r14+8]
0x18000caa7  movzx   ecx, word ptr [rax+rsi*2]
0x18000caab  sub     cx, 58h ; 'X'
0x18000caaf  mov     eax, 0FFDFh
0x18000cab4  test    ax, cx
0x18000cab7  jnz     short loc_18000CACD
0x18000cab9  mov     edi, 2
0x18000cabe  jmp     loc_18000C7FB
  ... truncated ...
```
