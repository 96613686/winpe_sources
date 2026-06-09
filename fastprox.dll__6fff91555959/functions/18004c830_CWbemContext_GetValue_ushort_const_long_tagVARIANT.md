# CWbemContext::GetValue(ushort const *,long,tagVARIANT *)

- ea: `0x18004c830`
- end: `0x18004cad6`
- name: `?GetValue@CWbemContext@@UEAAJPEBGJPEAUtagVARIANT@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(CWbemContext *__hidden this, const unsigned __int16 *, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x18004c830`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18004c9be`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18004ca03`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18004c9be`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18004ca03`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18004c89a`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18004c946`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18004c89a`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18004c946`
- `wbemcomn!GetMemLogObject` at `0x18004ca19`
- `wbemcomn!GetMemLogObject` at `0x18004ca73`
- `wbemcomn!GetMemLogObject` at `0x18004ca19`
- `wbemcomn!GetMemLogObject` at `0x18004ca73`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004c889`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004c889`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004c8fe`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004c982`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004ca66`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004cac6`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004c8fe`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004c982`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004ca66`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004cac6`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18004c85e`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18004c85e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ca24`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ca81`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ca24`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ca81`
- `OLEAUT32!__imp_VariantInit` at `0x18004c93a`
- `OLEAUT32!__imp_VariantInit` at `0x18004c93a`
- `OLEAUT32!__imp_VariantCopy` at `0x18004c954`
- `OLEAUT32!__imp_VariantCopy` at `0x18004c954`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemContext::GetValue(
        CWbemContext *this,
        const unsigned __int16 *a2,
        int a3,
        struct tagVARIANT *a4)
{
  int v8; // r14d
  CFlexArray *v9; // r15
  WCHAR *v10; // rsi
  const unsigned __int16 *i; // rdi
  WCHAR v12; // bx
  WCHAR v13; // cx
  char *v15; // rax
  HRESULT v16; // ebx
  int v17; // eax
  int v18; // eax
  CMemoryLog *v19; // rax
  CMemoryLog *MemLogObject; // rax
  _BYTE v21[8]; // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  WCHAR SrcStr; // [rsp+90h] [rbp+40h] BYREF
  WCHAR DestStr; // [rsp+A0h] [rbp+50h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v21, (struct _RTL_CRITICAL_SECTION *)((char *)this + 168));
  if ( a3 || !a2 || !a4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, 2147749896LL);
    }
    CInCritSec::~CInCritSec((CInCritSec *)v21);
    return 2147749896LL;
  }
  v8 = 0;
  v9 = (CWbemContext *)((char *)this + 40);
LABEL_5:
  if ( v8 >= CFlexArray::Size(v9) )
  {
LABEL_18:
    CInCritSec::~CInCritSec((CInCritSec *)v21);
    return 2147749890LL;
  }
  v10 = *(WCHAR **)CFlexArray::GetAt(v9, v8);
  for ( i = a2; ; ++i )
  {
    v12 = *i;
    if ( !*i )
      break;
    if ( v12 > 0x7Fu )
    {
      SrcStr = *i;
      DestStr = 0;
      v17 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1);
      v12 = DestStr;
      if ( !v17 )
        v12 = SrcStr;
    }
    else if ( (unsigned __int16)(v12 - 65) <= 0x19u )
    {
      v12 += 32;
    }
LABEL_11:
    v13 = *v10;
    if ( *v10 > 0x7Fu )
    {
      SrcStr = *v10;
      DestStr = 0;
      v18 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1);
      v13 = DestStr;
      if ( !v18 )
        v13 = SrcStr;
    }
    else if ( (unsigned __int16)(v13 - 65) <= 0x19u )
    {
      v13 += 32;
    }
    if ( v12 != v13 )
    {
      ++v8;
      goto LABEL_5;
    }
    ++v10;
  }
  if ( *v10 )
    goto LABEL_11;
  if ( v8 == -1 )
    goto LABEL_18;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v15 = (char *)CFlexArray::GetAt(v9, v8);
  v16 = VariantCopy(&pvarg, (const VARIANTARG *)(v15 + 16));
  if ( v16 < 0 )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, v16);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        (unsigned int)v16);
    }
    CInCritSec::~CInCritSec((CInCritSec *)v21);
    return (unsigned int)v16;
  }
  else
  {
    *a4 = pvarg;
    pvarg.vt = 0;
    CInCritSec::~CInCritSec((CInCritSec *)v21);
    return 0;
  }
}

```

## disassembly

```asm
0x18004c830  mov     [rsp-38h+arg_8], rbx
0x18004c835  push    rbp
0x18004c836  push    rsi
0x18004c837  push    rdi
0x18004c838  push    r12
0x18004c83a  push    r13
0x18004c83c  push    r14
0x18004c83e  push    r15
0x18004c840  mov     rbp, rsp
0x18004c843  sub     rsp, 50h
0x18004c847  mov     r13, r9
0x18004c84a  mov     ebx, r8d
0x18004c84d  mov     r12, rdx
0x18004c850  mov     rdi, rcx
0x18004c853  lea     rdx, [rcx+0A8h]
0x18004c85a  lea     rcx, [rbp+var_20]
0x18004c85e  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18004c864  nop
0x18004c865  test    ebx, ebx
0x18004c867  jnz     loc_18004CA73
0x18004c86d  test    r12, r12
0x18004c870  jz      loc_18004CA73
0x18004c876  test    r13, r13
0x18004c879  jz      loc_18004CA73
0x18004c87f  xor     r14d, r14d
0x18004c882  lea     r15, [rdi+28h]
0x18004c886  mov     rcx, r15
0x18004c889  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18004c88f  cmp     r14d, eax
0x18004c892  jge     short loc_18004C8FA
0x18004c894  mov     edx, r14d
0x18004c897  mov     rcx, r15
0x18004c89a  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18004c8a0  mov     rsi, [rax]
0x18004c8a3  mov     rdi, r12
0x18004c8a6  movzx   ebx, word ptr [rdi]
0x18004c8a9  test    bx, bx
0x18004c8ac  jz      short loc_18004C8EE
0x18004c8ae  cmp     bx, 7Fh
0x18004c8b2  ja      loc_18004C98F
0x18004c8b8  lea     eax, [rbx-41h]
0x18004c8bb  cmp     ax, 19h
0x18004c8bf  ja      short loc_18004C8C5
0x18004c8c1  add     bx, 20h ; ' '
0x18004c8c5  movzx   ecx, word ptr [rsi]
0x18004c8c8  cmp     cx, 7Fh
0x18004c8cc  ja      loc_18004C9D4
0x18004c8d2  lea     eax, [rcx-41h]
0x18004c8d5  cmp     ax, 19h
0x18004c8d9  ja      short loc_18004C8DF
0x18004c8db  add     cx, 20h ; ' '
0x18004c8df  cmp     bx, cx
0x18004c8e2  jnz     short loc_18004C921
0x18004c8e4  add     rdi, 2
0x18004c8e8  add     rsi, 2
0x18004c8ec  jmp     short loc_18004C8A6
0x18004c8ee  cmp     word ptr [rsi], 0
0x18004c8f2  jnz     short loc_18004C8C5
0x18004c8f4  cmp     r14d, 0FFFFFFFFh
0x18004c8f8  jnz     short loc_18004C929
0x18004c8fa  lea     rcx, [rbp+var_20]
0x18004c8fe  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18004c904  mov     eax, 80041002h
0x18004c909  mov     rbx, [rsp+50h+arg_8]
0x18004c911  add     rsp, 50h
0x18004c915  pop     r15
0x18004c917  pop     r14
0x18004c919  pop     r13
0x18004c91b  pop     r12
0x18004c91d  pop     rdi
0x18004c91e  pop     rsi
0x18004c91f  pop     rbp
0x18004c920  retn
0x18004c921  inc     r14d
0x18004c924  jmp     loc_18004C886
0x18004c929  xorps   xmm0, xmm0
0x18004c92c  xor     eax, eax
0x18004c92e  movups  xmmword ptr [rbp+pvarg], xmm0
0x18004c932  mov     qword ptr [rbp+pvarg+10h], rax
0x18004c936  lea     rcx, [rbp+pvarg]; pvarg
0x18004c93a  call    cs:__imp_VariantInit
0x18004c940  mov     edx, r14d
0x18004c943  mov     rcx, r15
0x18004c946  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18004c94c  lea     rdx, [rax+10h]; pvargSrc
0x18004c950  lea     rcx, [rbp+pvarg]; pvargDest
0x18004c954  call    cs:__imp_VariantCopy
0x18004c95a  mov     ebx, eax
0x18004c95c  test    eax, eax
0x18004c95e  js      loc_18004CA19
0x18004c964  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18004c968  movups  xmmword ptr [r13+0], xmm0
0x18004c96d  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18004c972  movsd   qword ptr [r13+10h], xmm1
0x18004c978  xor     eax, eax
0x18004c97a  mov     word ptr [rbp+pvarg], ax
0x18004c97e  lea     rcx, [rbp+var_20]
0x18004c982  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18004c988  xor     eax, eax
0x18004c98a  jmp     loc_18004C909
0x18004c98f  mov     [rbp+SrcStr], bx
0x18004c993  xor     eax, eax
0x18004c995  mov     [rbp+DestStr], ax
0x18004c999  mov     [rsp+50h+cchDest], 1; cchDest
0x18004c9a1  lea     rax, [rbp+DestStr]
0x18004c9a5  mov     [rsp+50h+lpDestStr], rax; lpDestStr
0x18004c9aa  mov     r9d, 1; cchSrc
0x18004c9b0  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18004c9b4  mov     edx, 100h; dwMapFlags
0x18004c9b9  mov     ecx, 7Fh; Locale
0x18004c9be  call    cs:__imp_LCMapStringW
0x18004c9c4  movzx   ebx, [rbp+DestStr]
0x18004c9c8  test    eax, eax
0x18004c9ca  cmovz   bx, [rbp+SrcStr]
0x18004c9cf  jmp     loc_18004C8C5
0x18004c9d4  mov     [rbp+SrcStr], cx
0x18004c9d8  xor     eax, eax
0x18004c9da  mov     [rbp+DestStr], ax
0x18004c9de  mov     [rsp+50h+cchDest], 1; cchDest
0x18004c9e6  lea     rax, [rbp+DestStr]
0x18004c9ea  mov     [rsp+50h+lpDestStr], rax; lpDestStr
0x18004c9ef  mov     r9d, 1; cchSrc
0x18004c9f5  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18004c9f9  mov     edx, 100h; dwMapFlags
0x18004c9fe  mov     ecx, 7Fh; Locale
0x18004ca03  call    cs:__imp_LCMapStringW
0x18004ca09  movzx   ecx, [rbp+DestStr]
0x18004ca0d  test    eax, eax
0x18004ca0f  cmovz   cx, [rbp+SrcStr]
0x18004ca14  jmp     loc_18004C8DF
0x18004ca19  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004ca1f  mov     edx, ebx
0x18004ca21  mov     rcx, rax
0x18004ca24  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004ca2a  lea     rax, WPP_GLOBAL_Control
0x18004ca31  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca38  cmp     rcx, rax
0x18004ca3b  jz      short loc_18004CA62
0x18004ca3d  test    byte ptr [rcx+1Ch], 1
0x18004ca41  jz      short loc_18004CA62
0x18004ca43  cmp     byte ptr [rcx+19h], 2
0x18004ca47  jb      short loc_18004CA62
0x18004ca49  mov     edx, 4Fh ; 'O'
0x18004ca4e  mov     r9d, ebx
0x18004ca51  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x18004ca58  mov     rcx, [rcx+10h]
0x18004ca5c  call    WPP_SF_d
0x18004ca61  nop
0x18004ca62  lea     rcx, [rbp+var_20]
0x18004ca66  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18004ca6c  mov     eax, ebx
0x18004ca6e  jmp     loc_18004C909
0x18004ca73  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004ca79  mov     edx, 80041008h
0x18004ca7e  mov     rcx, rax
0x18004ca81  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004ca87  lea     rax, WPP_GLOBAL_Control
0x18004ca8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca95  cmp     rcx, rax
0x18004ca98  jz      short loc_18004CAC2
0x18004ca9a  test    byte ptr [rcx+1Ch], 1
0x18004ca9e  jz      short loc_18004CAC2
0x18004caa0  cmp     byte ptr [rcx+19h], 2
0x18004caa4  jb      short loc_18004CAC2
0x18004caa6  mov     edx, 4Eh ; 'N'
0x18004caab  mov     r9d, 80041008h
0x18004cab1  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x18004cab8  mov     rcx, [rcx+10h]
0x18004cabc  call    WPP_SF_d
0x18004cac1  nop
0x18004cac2  lea     rcx, [rbp+var_20]
0x18004cac6  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18004cacc  mov     eax, 80041008h
0x18004cad1  jmp     loc_18004C909
```
