# CWbemContext::SetValue(ushort const *,long,tagVARIANT *)

- ea: `0x180037840`
- end: `0x180037bdd`
- name: `?SetValue@CWbemContext@@UEAAJPEBGJPEAUtagVARIANT@@@Z`
- size: `925`
- prototype: `__int64 __fastcall(CWbemContext *this, const unsigned __int16 *, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x180037840`
- `0x180037be4`
- `0x1800388c0`
- `0x180038ad4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180037b13`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180037b67`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180037b13`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180037b67`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800378c0`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18003793d`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800378c0`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18003793d`
- `wbemcomn!GetMemLogObject` at `0x1800379fb`
- `wbemcomn!GetMemLogObject` at `0x180037a5f`
- `wbemcomn!GetMemLogObject` at `0x180037b91`
- `wbemcomn!GetMemLogObject` at `0x1800379fb`
- `wbemcomn!GetMemLogObject` at `0x180037a5f`
- `wbemcomn!GetMemLogObject` at `0x180037b91`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800378ad`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800379e5`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800378ad`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800379e5`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x1800379d8`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x1800379d8`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180037967`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180037a52`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180037a8b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180037967`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180037a52`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180037a8b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003786f`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003786f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037a09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037a6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037b9f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037a09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037a6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037b9f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003799d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003799d`
- `OLEAUT32!__imp_VariantCopy` at `0x18003794d`
- `OLEAUT32!__imp_VariantCopy` at `0x18003794d`

## pseudocode

```c
__int64 __fastcall CWbemContext::SetValue(
        CWbemContext *this,
        const unsigned __int16 *a2,
        int a3,
        struct tagVARIANT *a4)
{
  int v8; // esi
  CFlexArray *v9; // r15
  __int16 *v10; // r12
  const unsigned __int16 *v11; // rax
  unsigned __int16 v12; // di
  __int16 v13; // cx
  char *v14; // rax
  char *v15; // rbx
  HRESULT v16; // eax
  struct IErrorInfo *v17; // rdx
  CWbemContext::CContextObj *v19; // rax
  CWbemContext::CContextObj *v20; // rdi
  unsigned int v21; // edx
  CMemoryLog *v22; // rax
  unsigned int v23; // ebx
  CMemoryLog *v24; // rax
  CWbemRefreshingSvc *v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  CMemoryLog *MemLogObject; // rax
  int v30; // ebx
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  int v33; // ebx
  CMemoryLog *v34; // rax
  __int64 v35; // [rsp+0h] [rbp-88h] BYREF
  _BYTE v36[8]; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v37; // [rsp+38h] [rbp-50h]
  CWbemContext::CContextObj *v38; // [rsp+40h] [rbp-48h]
  _com_error *v39; // [rsp+48h] [rbp-40h] BYREF
  _com_error *v40; // [rsp+50h] [rbp-38h] BYREF
  CWbemContext::CContextObj *SrcStr; // [rsp+90h] [rbp+8h] BYREF
  unsigned int DestStr; // [rsp+A0h] [rbp+18h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v36, (struct _RTL_CRITICAL_SECTION *)((char *)this + 168));
  if ( a3 || !a2 || !a4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v26 = 72;
    goto LABEL_45;
  }
  if ( a4->vt != 36 )
  {
    v8 = 0;
    v9 = (CWbemContext *)((char *)this + 40);
    while ( v8 < CFlexArray::Size(v9) )
    {
      v10 = *(__int16 **)CFlexArray::GetAt(v9, v8);
      v11 = a2;
      while ( 1 )
      {
        v37 = v11;
        v12 = *v11;
        if ( *v11 )
        {
          if ( v12 > 0x7Fu )
          {
            LOWORD(SrcStr) = *v11;
            LOWORD(DestStr) = 0;
            v27 = LCMapStringW(0x7Fu, 0x100u, (LPCWSTR)&SrcStr, 1, (LPWSTR)&DestStr, 1);
            v12 = DestStr;
            if ( !v27 )
              v12 = (unsigned __int16)SrcStr;
          }
          else if ( (unsigned __int16)(v12 - 65) <= 0x19u )
          {
            v12 += 32;
          }
        }
        else if ( !*v10 )
        {
          if ( v8 == -1 )
            goto LABEL_25;
          v14 = (char *)CFlexArray::GetAt(v9, v8);
          v15 = v14;
          if ( __eh34_try(-1, 2) )
          {
            __eh34_scope_strut(2);
            v16 = VariantCopy((VARIANTARG *)(v14 + 16), a4);
            if ( v16 < 0 )
              _com_raise_error(v16, v17);
          }
          if ( __eh34_catch(2) )
          {
            if ( __eh34_catch_type(2, &_com_error `RTTI Type Descriptor', &v39) )
            {
              v30 = *((_DWORD *)v39 + 2);
              DestStr = v30;
              if ( v30 < 0 )
              {
                v31 = GetMemLogObject();
                CMemoryLog::Write(v31, v30);
              }
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  77,
                  WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
                  (unsigned int)v30);
              }
              v23 = DestStr;
              __eh34_try_continuation(2, &_com_error `RTTI Type Descriptor', &loc_180037AD6);
              goto LABEL_38;
            }
          }
          *((_DWORD *)v15 + 2) = 0;
          goto LABEL_23;
        }
        v13 = *v10;
        if ( (unsigned __int16)*v10 > 0x7Fu )
        {
          LOWORD(SrcStr) = *v10;
          LOWORD(DestStr) = 0;
          v28 = LCMapStringW(0x7Fu, 0x100u, (LPCWSTR)&SrcStr, 1, (LPWSTR)&DestStr, 1);
          v13 = DestStr;
          if ( !v28 )
            v13 = (__int16)SrcStr;
        }
        else if ( (unsigned __int16)(v13 - 65) <= 0x19u )
        {
          v13 += 32;
        }
        if ( v12 != v13 )
          break;
        v11 = v37 + 1;
        ++v10;
      }
      ++v8;
    }
LABEL_25:
    v38 = 0;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v19 = (CWbemContext::CContextObj *)CWin32DefaultArena::WbemMemAlloc(0x28u);
      SrcStr = v19;
      if ( v19 )
        v20 = (CWbemContext::CContextObj *)((_QWORD (__stdcall *)(CWbemContext::CContextObj *, const unsigned __int16 *, int, struct tagVARIANT *))CWbemContext::CContextObj::CContextObj)(
                                             v19,
                                             a2,
                                             0,
                                             a4);
      else
        v20 = 0;
      v38 = v20;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
      {
        if ( v38 )
          ((void (__fastcall *)(CWbemContext::CContextObj *, unsigned int))CWbemContext::CContextObj::`scalar deleting destructor')(
            v38,
            (unsigned int)&v35);
        v32 = GetMemLogObject();
        CMemoryLog::Write(v32, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            74,
            WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
            2147749894LL);
        }
        v23 = -2147217402;
        __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_180037B87);
LABEL_38:
        CInCritSec::~CInCritSec((CInCritSec *)v36);
        return v23;
      }
      if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v40) )
      {
        v33 = *((_DWORD *)v40 + 2);
        DestStr = v33;
        if ( v33 < 0 )
        {
          v34 = GetMemLogObject();
          CMemoryLog::Write(v34, v33);
        }
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            75,
            WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
            (unsigned int)v33);
        }
        v23 = DestStr;
        __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_180037AD6);
        goto LABEL_38;
      }
    }
    if ( v20 )
    {
      if ( !CFlexArray::Add(v9, v20) && CFlexArray::Size(v9) )
      {
LABEL_23:
        CInCritSec::~CInCritSec((CInCritSec *)v36);
        return 0;
      }
      ((void (__fastcall *)(CWbemContext::CContextObj *, unsigned int))CWbemContext::CContextObj::`scalar deleting destructor')(
        v20,
        v21);
    }
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, 2147749894LL);
    }
    v23 = -2147217402;
    goto LABEL_38;
  }
  v24 = GetMemLogObject();
  CMemoryLog::Write(v24, -2147217400);
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = 73;
LABEL_45:
    WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, 2147749896LL);
  }
LABEL_40:
  CInCritSec::~CInCritSec((CInCritSec *)v36);
  return 2147749896LL;
}

```

## disassembly

```asm
0x180037840  mov     [rsp+arg_8], rbx
0x180037845  mov     [rsp+arg_18], rsi
0x18003784a  push    rdi
0x18003784b  push    r12
0x18003784d  push    r13
0x18003784f  push    r14
0x180037851  push    r15
0x180037853  sub     rsp, 60h
0x180037857  mov     r14, r9
0x18003785a  mov     ebx, r8d
0x18003785d  mov     r13, rdx
0x180037860  mov     r15, rcx
0x180037863  lea     rdx, [rcx+0A8h]
0x18003786a  lea     rcx, [rsp+88h+var_58]
0x18003786f  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180037875  nop
0x180037876  xor     r12d, r12d
0x180037879  test    ebx, ebx
0x18003787b  jnz     loc_180037B91
0x180037881  test    r13, r13
0x180037884  jz      loc_180037B91
0x18003788a  test    r14, r14
0x18003788d  jz      loc_180037B91
0x180037893  cmp     word ptr [r14], 24h ; '$'
0x180037898  jz      loc_180037A5F
0x18003789e  mov     esi, r12d
0x1800378a1  add     r15, 28h ; '('
0x1800378a5  lea     ebx, [r12+1]
0x1800378aa  mov     rcx, r15
0x1800378ad  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800378b3  cmp     esi, eax
0x1800378b5  jge     loc_180037990
0x1800378bb  mov     edx, esi
0x1800378bd  mov     rcx, r15
0x1800378c0  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800378c6  mov     r12, [rax]
0x1800378c9  mov     rax, r13
0x1800378cc  xor     edx, edx
0x1800378ce  mov     [rsp+88h+var_50], rax
0x1800378d3  movzx   edi, word ptr [rax]
0x1800378d6  test    di, di
0x1800378d9  jz      short loc_18003792C
0x1800378db  mov     ecx, 7Fh; Locale
0x1800378e0  cmp     di, cx
0x1800378e3  ja      loc_180037AE2
0x1800378e9  lea     eax, [rdi-41h]
0x1800378ec  cmp     ax, 19h
0x1800378f0  ja      short loc_1800378F6
0x1800378f2  add     di, 20h ; ' '
0x1800378f6  movzx   ecx, word ptr [r12]
0x1800378fb  mov     r10d, 7Fh
0x180037901  cmp     cx, r10w
0x180037905  ja      loc_180037B33
0x18003790b  lea     eax, [rcx-41h]
0x18003790e  cmp     ax, 19h
0x180037912  ja      short loc_180037918
0x180037914  add     cx, 20h ; ' '
0x180037918  cmp     di, cx
0x18003791b  jnz     short loc_180037989
0x18003791d  mov     rax, [rsp+88h+var_50]
0x180037922  add     rax, 2
0x180037926  add     r12, 2
0x18003792a  jmp     short loc_1800378CE
0x18003792c  cmp     [r12], dx
0x180037931  jnz     short loc_1800378F6
0x180037933  cmp     esi, 0FFFFFFFFh
0x180037936  jz      short loc_180037990
0x180037938  mov     edx, esi
0x18003793a  mov     rcx, r15
0x18003793d  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180037943  mov     rbx, rax
0x180037946  lea     rcx, [rax+10h]; pvargDest
0x18003794a  mov     rdx, r14; pvargSrc
0x18003794d  call    cs:__imp_VariantCopy
0x180037953  test    eax, eax
0x180037955  js      loc_180037A9B
0x18003795b  mov     dword ptr [rbx+8], 0
0x180037962  lea     rcx, [rsp+88h+var_58]
0x180037967  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003796d  xor     eax, eax
0x18003796f  lea     r11, [rsp+88h+var_28]
0x180037974  mov     rbx, [r11+38h]
0x180037978  mov     rsi, [r11+48h]
0x18003797c  mov     rsp, r11
0x18003797f  pop     r15
0x180037981  pop     r14
0x180037983  pop     r13
0x180037985  pop     r12
0x180037987  pop     rdi
0x180037988  retn
0x180037989  add     esi, ebx
0x18003798b  jmp     loc_1800378AA
0x180037990  xor     r12d, r12d
0x180037993  mov     [rsp+88h+var_48], r12
0x180037998  lea     ecx, [r12+28h]
0x18003799d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800379a3  mov     [rsp+88h+SrcStr], rax
0x1800379ab  test    rax, rax
0x1800379ae  jz      loc_180037ACE
0x1800379b4  mov     r9, r14; struct tagVARIANT *
0x1800379b7  xor     r8d, r8d; int
0x1800379ba  mov     rdx, r13; unsigned __int16 *
0x1800379bd  mov     rcx, rax; this
0x1800379c0  call    ??0CContextObj@CWbemContext@@QEAA@PEBGJPEAUtagVARIANT@@@Z; CWbemContext::CContextObj::CContextObj(ushort const *,long,tagVARIANT *)
0x1800379c5  mov     rdi, rax
0x1800379c8  mov     [rsp+88h+var_48], rdi
0x1800379cd  test    rdi, rdi
0x1800379d0  jz      short loc_1800379FB
0x1800379d2  mov     rdx, rdi
0x1800379d5  mov     rcx, r15
0x1800379d8  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x1800379de  test    eax, eax
0x1800379e0  jnz     short loc_1800379F3
0x1800379e2  mov     rcx, r15
0x1800379e5  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800379eb  test    eax, eax
0x1800379ed  jnz     loc_180037962
0x1800379f3  mov     rcx, rdi; this
0x1800379f6  call    ??_GCContextObj@CWbemContext@@QEAAPEAXI@Z; CWbemContext::CContextObj::`scalar deleting destructor'(uint)
0x1800379fb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037a01  mov     edx, 80041006h
0x180037a06  mov     rcx, rax
0x180037a09  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037a0f  lea     rax, WPP_GLOBAL_Control
0x180037a16  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a1d  cmp     rcx, rax
0x180037a20  jz      short loc_180037A48
0x180037a22  test    [rcx+1Ch], bl
0x180037a25  jz      short loc_180037A48
0x180037a27  cmp     byte ptr [rcx+19h], 2
0x180037a2b  jb      short loc_180037A48
0x180037a2d  mov     edx, 4Ch ; 'L'
0x180037a32  mov     r9d, 80041006h
0x180037a38  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180037a3f  mov     rcx, [rcx+10h]
0x180037a43  call    WPP_SF_d
0x180037a48  mov     ebx, 80041006h
0x180037a4d  lea     rcx, [rsp+88h+var_58]
0x180037a52  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180037a58  mov     eax, ebx
0x180037a5a  jmp     loc_18003796F
0x180037a5f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037a65  mov     edx, 80041008h
0x180037a6a  mov     rcx, rax
0x180037a6d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037a73  lea     rax, WPP_GLOBAL_Control
0x180037a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a81  cmp     rcx, rax
0x180037a84  jnz     short loc_180037AA3
0x180037a86  lea     rcx, [rsp+88h+var_58]
0x180037a8b  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180037a91  mov     eax, 80041008h
0x180037a96  jmp     loc_18003796F
0x180037a9b  mov     ecx, eax; int
0x180037a9d  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180037aa3  mov     ebx, 1
0x180037aa8  test    [rcx+1Ch], bl
0x180037aab  jz      short loc_180037A86
0x180037aad  cmp     byte ptr [rcx+19h], 2
0x180037ab1  jb      short loc_180037A86
0x180037ab3  lea     edx, [rbx+48h]
0x180037ab6  mov     r9d, 80041008h
0x180037abc  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180037ac3  mov     rcx, [rcx+10h]
0x180037ac7  call    WPP_SF_d
0x180037acc  jmp     short loc_180037A86
0x180037ace  mov     rdi, r12
0x180037ad1  jmp     loc_1800379C8
0x180037ad6  mov     ebx, [rsp+88h+DestStr]
0x180037add  jmp     loc_180037B8C
0x180037ae2  mov     word ptr [rsp+88h+SrcStr], di
0x180037aea  mov     word ptr [rsp+88h+DestStr], dx
0x180037af2  mov     [rsp+88h+cchDest], ebx; cchDest
0x180037af6  lea     rax, [rsp+88h+DestStr]
0x180037afe  mov     [rsp+88h+lpDestStr], rax; lpDestStr
0x180037b03  mov     r9d, ebx; cchSrc
0x180037b06  lea     r8, [rsp+88h+SrcStr]; lpSrcStr
0x180037b0e  mov     edx, 100h; dwMapFlags
0x180037b13  call    cs:__imp_LCMapStringW
0x180037b19  movzx   edi, word ptr [rsp+88h+DestStr]
0x180037b21  xor     edx, edx
0x180037b23  test    eax, eax
0x180037b25  cmovz   di, word ptr [rsp+88h+SrcStr]
0x180037b2e  jmp     loc_1800378F6
0x180037b33  mov     word ptr [rsp+88h+SrcStr], cx
0x180037b3b  mov     word ptr [rsp+88h+DestStr], dx
0x180037b43  mov     [rsp+88h+cchDest], ebx; cchDest
0x180037b47  lea     rax, [rsp+88h+DestStr]
0x180037b4f  mov     [rsp+88h+lpDestStr], rax; lpDestStr
0x180037b54  mov     r9d, ebx; cchSrc
0x180037b57  lea     r8, [rsp+88h+SrcStr]; lpSrcStr
0x180037b5f  mov     edx, 100h; dwMapFlags
0x180037b64  mov     ecx, r10d; Locale
0x180037b67  call    cs:__imp_LCMapStringW
0x180037b6d  movzx   ecx, word ptr [rsp+88h+DestStr]
0x180037b75  xor     edx, edx
0x180037b77  test    eax, eax
0x180037b79  cmovz   cx, word ptr [rsp+88h+SrcStr]
0x180037b82  jmp     loc_180037918
0x180037b87  mov     ebx, 80041006h
0x180037b8c  jmp     loc_180037A4D
0x180037b91  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037b97  mov     edx, 80041008h
0x180037b9c  mov     rcx, rax
0x180037b9f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037ba5  lea     rax, WPP_GLOBAL_Control
0x180037bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bb3  cmp     rcx, rax
0x180037bb6  jz      loc_180037A86
0x180037bbc  mov     ebx, 1
0x180037bc1  test    [rcx+1Ch], bl
0x180037bc4  jz      loc_180037A86
0x180037bca  cmp     byte ptr [rcx+19h], 2
0x180037bce  jb      loc_180037A86
0x180037bd4  lea     edx, [rbx+47h]
0x180037bd7  jmp     loc_180037AB6
```
