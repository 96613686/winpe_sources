# CWbemInstance::GetLimitedVersion(CLimitationMapping *,CWbemInstance * *)

- ea: `0x1800184a0`
- end: `0x18001883c`
- name: `?GetLimitedVersion@CWbemInstance@@QEAAJPEAVCLimitationMapping@@PEAPEAV1@@Z`
- size: `924`
- prototype: `int(CWbemInstance *__hidden this, struct CLimitationMapping *, struct CWbemInstance **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180067120`

## callees

- `0x180013e80`
- `0x1800183f0`
- `0x1800184a0`
- `0x180018ab0`
- `0x180020be0`
- `0x180022000`
- `0x180037120`
- `0x18006d1d4`
- `0x180091972`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001869e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001869e`
- `wbemcomn!GetMemLogObject` at `0x180018638`
- `wbemcomn!GetMemLogObject` at `0x180018665`
- `wbemcomn!GetMemLogObject` at `0x1800186d8`
- `wbemcomn!GetMemLogObject` at `0x18001876e`
- `wbemcomn!GetMemLogObject` at `0x1800187d0`
- `wbemcomn!GetMemLogObject` at `0x180018638`
- `wbemcomn!GetMemLogObject` at `0x180018665`
- `wbemcomn!GetMemLogObject` at `0x1800186d8`
- `wbemcomn!GetMemLogObject` at `0x18001876e`
- `wbemcomn!GetMemLogObject` at `0x1800187d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018648`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018675`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800186e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001877e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800187e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018648`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018675`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800186e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001877e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800187e0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800185aa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800185aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemInstance::GetLimitedVersion(
        CWbemInstance *this,
        struct CLimitationMapping *a2,
        struct CWbemInstance **a3)
{
  unsigned int v6; // esi
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdi
  unsigned int v9; // ebx
  unsigned __int8 *LimitedRepresentation; // rax
  unsigned __int8 *v11; // r9
  CWbemInstance *v12; // rax
  struct CWbemInstance *v13; // rbx
  __int64 result; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v20; // rax
  unsigned __int8 *v21; // [rsp+48h] [rbp-50h] BYREF
  char v22; // [rsp+50h] [rbp-48h]
  CWbemInstance *v23; // [rsp+B8h] [rbp+20h] BYREF

  try
  {
    v6 = *((_DWORD *)this + 42);
    if ( (*((_BYTE *)this + 60) & 0xC) != 0xC )
      v6 += **((_DWORD **)this + 56);
    v7 = CBasicBlobControl::sAllocate(v6);
    v8 = v7;
    if ( v7 )
    {
      v21 = v7;
      v22 = 0;
      memset_0(v7, 0, v6);
      v9 = (_DWORD)v8 + v6;
      LimitedRepresentation = CDecorationPart::CreateLimitedRepresentation((CWbemInstance *)((char *)this + 72), a2, v8);
      if ( LimitedRepresentation )
      {
        LODWORD(v23) = 0;
        v11 = CClassPart::CreateLimitedRepresentation(
                (CWbemInstance *)((char *)this + 400),
                a2,
                v9 - (unsigned int)LimitedRepresentation,
                LimitedRepresentation,
                (int *)&v23);
        if ( v11 )
        {
          if ( (_DWORD)v23 )
          {
            *v8 &= ~0x40u;
            *v8 |= 0x40u;
          }
          if ( CInstancePart::CreateLimitedRepresentation(
                 (CWbemInstance *)((char *)this + 176),
                 a2,
                 v9 - (unsigned int)v11,
                 v11) )
          {
            v12 = (CWbemInstance *)CWin32DefaultArena::WbemMemAlloc(0x2A0u);
            v23 = v12;
            if ( v12 )
              v13 = CWbemInstance::CWbemInstance(v12);
            else
              v13 = 0;
            if ( v13 )
            {
              v23 = v13;
              v22 = 1;
              (*(void (__fastcall **)(struct CWbemInstance *, unsigned __int8 *, _QWORD))(*(_QWORD *)v13 + 1152LL))(
                v13,
                v8,
                v6);
              (*(void (__fastcall **)(struct CWbemInstance *))(*(_QWORD *)v13 + 8LL))(v13);
              *a3 = v13;
              (*(void (__fastcall **)(struct CWbemInstance *))(*(_QWORD *)v13 + 16LL))(v13);
              v23 = 0;
              return 0;
            }
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, -2147217402);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
                2147749894LL);
            }
          }
          else
          {
            v18 = GetMemLogObject();
            CMemoryLog::Write(v18, -2147217402);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                66,
                WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
                2147749894LL);
            }
          }
          OnDeleteIf<unsigned char *,void (*)(unsigned char *),&public: static void CBasicBlobControl::sDelete(unsigned char *)>::~OnDeleteIf<unsigned char *,void (*)(unsigned char *),&public: static void CBasicBlobControl::sDelete(unsigned char *)>((__int64)&v21);
          result = 2147749894LL;
        }
        else
        {
          v16 = GetMemLogObject();
          CMemoryLog::Write(v16, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              65,
              WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
              2147749894LL);
          }
          HeapFree(CBasicBlobControl::m_Heap, 0, v8);
          result = 2147749894LL;
        }
      }
      else
      {
        v17 = GetMemLogObject();
        CMemoryLog::Write(v17, -2147217407);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
            2147749889LL);
        }
        OnDeleteIf<unsigned char *,void (*)(unsigned char *),&public: static void CBasicBlobControl::sDelete(unsigned char *)>::~OnDeleteIf<unsigned char *,void (*)(unsigned char *),&public: static void CBasicBlobControl::sDelete(unsigned char *)>((__int64)&v21);
        result = 2147749889LL;
      }
    }
    else
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749894LL);
      }
      result = 2147749894LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800184a0  push    rbx
0x1800184a2  push    rsi
0x1800184a3  push    rdi
0x1800184a4  push    r12
0x1800184a6  push    r14
0x1800184a8  push    r15
0x1800184aa  sub     rsp, 68h
0x1800184ae  mov     r12, r8
0x1800184b1  mov     r15, rdx
0x1800184b4  mov     r14, rcx
0x1800184b7  mov     esi, [rcx+0A8h]
0x1800184bd  mov     [rsp+98h+var_68], esi
0x1800184c1  mov     eax, [rcx+3Ch]
0x1800184c4  and     eax, 0Ch
0x1800184c7  cmp     al, 0Ch
0x1800184c9  jz      short loc_1800184D8
0x1800184cb  mov     rax, [rcx+1C0h]
0x1800184d2  add     esi, [rax]
0x1800184d4  mov     [rsp+98h+var_68], esi
0x1800184d8  mov     ecx, esi; int
0x1800184da  call    ?sAllocate@CBasicBlobControl@@SAPEAEH@Z; CBasicBlobControl::sAllocate(int)
0x1800184df  mov     rdi, rax
0x1800184e2  test    rax, rax
0x1800184e5  jz      loc_180018638
0x1800184eb  mov     [rsp+98h+var_50], rax
0x1800184f0  mov     [rsp+98h+var_48], 0
0x1800184f5  mov     ebx, esi
0x1800184f7  mov     r8d, esi; Size
0x1800184fa  xor     edx, edx; Val
0x1800184fc  mov     rcx, rax; void *
0x1800184ff  call    memset_0
0x180018504  mov     [rsp+98h+var_60], rdi
0x180018509  add     rbx, rdi
0x18001850c  mov     [rsp+98h+var_58], rbx
0x180018511  lea     rcx, [r14+48h]; this
0x180018515  mov     r8, rdi; unsigned __int8 *
0x180018518  mov     rdx, r15; struct CLimitationMapping *
0x18001851b  call    ?CreateLimitedRepresentation@CDecorationPart@@QEAAPEAEPEAVCLimitationMapping@@PEAE@Z; CDecorationPart::CreateLimitedRepresentation(CLimitationMapping *,uchar *)
0x180018520  mov     [rsp+98h+var_60], rax
0x180018525  test    rax, rax
0x180018528  jz      loc_1800186D8
0x18001852e  lea     rcx, [r14+190h]; this
0x180018535  mov     dword ptr [rsp+98h+arg_18], 0
0x180018540  mov     r8d, ebx
0x180018543  sub     r8d, eax; int
0x180018546  lea     rdx, [rsp+98h+arg_18]
0x18001854e  mov     [rsp+98h+var_78], rdx; int *
0x180018553  mov     r9, rax; unsigned __int8 *
0x180018556  mov     rdx, r15; struct CLimitationMapping *
0x180018559  call    ?CreateLimitedRepresentation@CClassPart@@QEAAPEAEPEAVCLimitationMapping@@HPEAEAEAH@Z; CClassPart::CreateLimitedRepresentation(CLimitationMapping *,int,uchar *,int &)
0x18001855e  mov     r9, rax; unsigned __int8 *
0x180018561  mov     [rsp+98h+var_60], rax
0x180018566  test    rax, rax
0x180018569  jz      loc_180018665
0x18001856f  cmp     dword ptr [rsp+98h+arg_18], 0
0x180018577  jz      short loc_180018582
0x180018579  and     byte ptr [rdi], 0BFh
0x18001857c  mov     al, [rdi]
0x18001857e  or      al, 40h
0x180018580  mov     [rdi], al
0x180018582  sub     ebx, r9d
0x180018585  lea     rcx, [r14+0B0h]; this
0x18001858c  mov     r8d, ebx; int
0x18001858f  mov     rdx, r15; struct CLimitationMapping *
0x180018592  call    ?CreateLimitedRepresentation@CInstancePart@@QEAAPEAEPEAVCLimitationMapping@@HPEAE@Z; CInstancePart::CreateLimitedRepresentation(CLimitationMapping *,int,uchar *)
0x180018597  mov     [rsp+98h+var_60], rax
0x18001859c  test    rax, rax
0x18001859f  jz      loc_18001876E
0x1800185a5  mov     ecx, 2A0h
0x1800185aa  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800185b0  mov     [rsp+98h+arg_18], rax
0x1800185b8  test    rax, rax
0x1800185bb  jz      loc_1800186A8
0x1800185c1  mov     rcx, rax; this
0x1800185c4  call    ??0CWbemInstance@@QEAA@XZ; CWbemInstance::CWbemInstance(void)
0x1800185c9  mov     rbx, rax
0x1800185cc  test    rbx, rbx
0x1800185cf  jz      loc_1800187D0
0x1800185d5  mov     [rsp+98h+arg_18], rbx
0x1800185dd  mov     [rsp+98h+var_48], 1
0x1800185e2  mov     rax, [rbx]
0x1800185e5  mov     r8d, esi
0x1800185e8  mov     rdx, rdi
0x1800185eb  mov     rcx, rbx
0x1800185ee  mov     rax, [rax+480h]
0x1800185f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185fa  mov     rax, [rbx]
0x1800185fd  mov     rcx, rbx
0x180018600  mov     rax, [rax+8]
0x180018604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018609  mov     [r12], rbx
0x18001860d  mov     rax, [rbx]
0x180018610  mov     rcx, rbx
0x180018613  mov     rax, [rax+10h]
0x180018617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001861c  mov     [rsp+98h+arg_18], 0
0x180018628  xor     eax, eax
0x18001862a  add     rsp, 68h
0x18001862e  pop     r15
0x180018630  pop     r14
0x180018632  pop     r12
0x180018634  pop     rdi
0x180018635  pop     rsi
0x180018636  pop     rbx
0x180018637  retn
0x180018638  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001863e  mov     ebx, 80041006h
0x180018643  mov     edx, ebx
0x180018645  mov     rcx, rax
0x180018648  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001864e  lea     rax, WPP_GLOBAL_Control
0x180018655  mov     rcx, cs:WPP_GLOBAL_Control
0x18001865c  cmp     rcx, rax
0x18001865f  jnz     short loc_1800186AF
0x180018661  mov     eax, ebx
0x180018663  jmp     short loc_18001862A
0x180018665  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001866b  mov     ebx, 80041006h
0x180018670  mov     edx, ebx
0x180018672  mov     rcx, rax
0x180018675  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001867b  lea     rax, WPP_GLOBAL_Control
0x180018682  mov     rcx, cs:WPP_GLOBAL_Control
0x180018689  cmp     rcx, rax
0x18001868c  jnz     loc_18001873A
0x180018692  mov     r8, rdi; lpMem
0x180018695  xor     edx, edx; dwFlags
0x180018697  mov     rcx, cs:?m_Heap@CBasicBlobControl@@2VCGetHeap@@A; hHeap
0x18001869e  call    cs:__imp_HeapFree
0x1800186a4  mov     eax, ebx
0x1800186a6  jmp     short loc_18001862A
0x1800186a8  xor     ebx, ebx
0x1800186aa  jmp     loc_1800185CC
0x1800186af  test    byte ptr [rcx+1Ch], 1
0x1800186b3  jz      short loc_180018661
0x1800186b5  cmp     byte ptr [rcx+19h], 2
0x1800186b9  jb      short loc_180018661
0x1800186bb  mov     edx, 3Fh ; '?'
0x1800186c0  mov     r9d, 80041006h
0x1800186c6  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x1800186cd  mov     rcx, [rcx+10h]
0x1800186d1  call    WPP_SF_d
0x1800186d6  jmp     short loc_180018661
0x1800186d8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800186de  mov     ebx, 80041001h
0x1800186e3  mov     edx, ebx
0x1800186e5  mov     rcx, rax
0x1800186e8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800186ee  lea     rax, WPP_GLOBAL_Control
0x1800186f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186fc  cmp     rcx, rax
0x1800186ff  jz      short loc_180018729
0x180018701  test    byte ptr [rcx+1Ch], 1
0x180018705  jz      short loc_180018729
0x180018707  cmp     byte ptr [rcx+19h], 2
0x18001870b  jb      short loc_180018729
0x18001870d  mov     edx, 40h ; '@'
0x180018712  mov     r9d, 80041001h
0x180018718  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18001871f  mov     rcx, [rcx+10h]
0x180018723  call    WPP_SF_d
0x180018728  nop
0x180018729  lea     rcx, [rsp+98h+var_50]
0x18001872e  call    ??1?$OnDeleteIf@PEAEP6AXPEAE@Z$1?sDelete@CBasicBlobControl@@SAX0@Z@@QEAA@XZ; OnDeleteIf<uchar *,void (*)(uchar *),&CBasicBlobControl::sDelete(uchar *)>::~OnDeleteIf<uchar *,void (*)(uchar *),&CBasicBlobControl::sDelete(uchar *)>(void)
0x180018733  mov     eax, ebx
0x180018735  jmp     loc_18001862A
0x18001873a  test    byte ptr [rcx+1Ch], 1
0x18001873e  jz      loc_180018692
0x180018744  cmp     byte ptr [rcx+19h], 2
0x180018748  jb      loc_180018692
0x18001874e  mov     edx, 41h ; 'A'
0x180018753  mov     r9d, 80041006h
0x180018759  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x180018760  mov     rcx, [rcx+10h]
0x180018764  call    WPP_SF_d
0x180018769  jmp     loc_180018692
0x18001876e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180018774  mov     ebx, 80041006h
0x180018779  mov     edx, ebx
0x18001877b  mov     rcx, rax
0x18001877e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180018784  lea     rax, WPP_GLOBAL_Control
0x18001878b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018792  cmp     rcx, rax
0x180018795  jz      short loc_1800187BF
0x180018797  test    byte ptr [rcx+1Ch], 1
0x18001879b  jz      short loc_1800187BF
0x18001879d  cmp     byte ptr [rcx+19h], 2
0x1800187a1  jb      short loc_1800187BF
0x1800187a3  mov     edx, 42h ; 'B'
0x1800187a8  mov     r9d, 80041006h
0x1800187ae  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x1800187b5  mov     rcx, [rcx+10h]
0x1800187b9  call    WPP_SF_d
0x1800187be  nop
0x1800187bf  lea     rcx, [rsp+98h+var_50]
0x1800187c4  call    ??1?$OnDeleteIf@PEAEP6AXPEAE@Z$1?sDelete@CBasicBlobControl@@SAX0@Z@@QEAA@XZ; OnDeleteIf<uchar *,void (*)(uchar *),&CBasicBlobControl::sDelete(uchar *)>::~OnDeleteIf<uchar *,void (*)(uchar *),&CBasicBlobControl::sDelete(uchar *)>(void)
0x1800187c9  mov     eax, ebx
0x1800187cb  jmp     loc_18001862A
0x1800187d0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800187d6  mov     ebx, 80041006h
0x1800187db  mov     edx, ebx
0x1800187dd  mov     rcx, rax
0x1800187e0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800187e6  lea     rax, WPP_GLOBAL_Control
0x1800187ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187f4  cmp     rcx, rax
0x1800187f7  jz      short loc_180018821
0x1800187f9  test    byte ptr [rcx+1Ch], 1
0x1800187fd  jz      short loc_180018821
0x1800187ff  cmp     byte ptr [rcx+19h], 2
0x180018803  jb      short loc_180018821
0x180018805  mov     edx, 43h ; 'C'
0x18001880a  mov     r9d, 80041006h
0x180018810  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x180018817  mov     rcx, [rcx+10h]
0x18001881b  call    WPP_SF_d
0x180018820  nop
0x180018821  lea     rcx, [rsp+98h+var_50]
0x180018826  call    ??1?$OnDeleteIf@PEAEP6AXPEAE@Z$1?sDelete@CBasicBlobControl@@SAX0@Z@@QEAA@XZ; OnDeleteIf<uchar *,void (*)(uchar *),&CBasicBlobControl::sDelete(uchar *)>::~OnDeleteIf<uchar *,void (*)(uchar *),&CBasicBlobControl::sDelete(uchar *)>(void)
0x18001882b  mov     eax, ebx
0x18001882d  jmp     loc_18001862A
0x180018832  mov     eax, 80041006h
0x180018837  jmp     loc_18001862A
```
