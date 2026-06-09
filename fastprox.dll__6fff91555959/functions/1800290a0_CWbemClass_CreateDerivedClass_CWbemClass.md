# CWbemClass::CreateDerivedClass(CWbemClass * *)

- ea: `0x1800290a0`
- end: `0x18002938a`
- name: `?CreateDerivedClass@CWbemClass@@QEAAJPEAPEAV1@@Z`
- size: `746`
- prototype: `__int64 __fastcall(CWbemClass *__hidden this, struct CWbemClass **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180028e50`
- `0x180075950`

## callees

- `0x18001f640`
- `0x180020440`
- `0x1800290a0`
- `0x1800293e0`
- `0x180029460`
- `0x180037120`
- `0x180072920`
- `0x180091972`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180029207`
- `wbemcomn!GetMemLogObject` at `0x18002925a`
- `wbemcomn!GetMemLogObject` at `0x1800292b4`
- `wbemcomn!GetMemLogObject` at `0x180029207`
- `wbemcomn!GetMemLogObject` at `0x18002925a`
- `wbemcomn!GetMemLogObject` at `0x1800292b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029212`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029268`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800292c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029212`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029268`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800292c2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800290d1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800290d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemClass::CreateDerivedClass(CWbemClass *this, struct CWbemClass **a2)
{
  CClassAndMethods *v4; // r12
  CWbemClass *v5; // rax
  struct CWbemClass *v6; // r14
  int *v7; // rsi
  int v8; // edi
  __int64 v9; // rbx
  unsigned int v10; // esi
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // rdi
  __int64 v13; // r12
  unsigned int v14; // ebx
  __int64 result; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax

  try
  {
    v4 = (CWbemClass *)((char *)this + 504);
    CClassAndMethods::Compact((CWbemClass *)((char *)this + 504));
    v5 = (CWbemClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
    if ( v5 )
      v6 = CWbemClass::CWbemClass(v5);
    else
      v6 = 0;
    if ( v6 )
    {
      v7 = (int *)*((_QWORD *)this + 96);
      v8 = *v7;
      v9 = *((_QWORD *)this + 71);
      v10 = v8 + CClassAndMethods::EstimateDerivedPartSpace(v4) + (_DWORD)v7 - v9 + 1;
      v11 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 8LL))(
                                 *((_QWORD *)this + 15),
                                 v10);
      v12 = v11;
      if ( v11 )
      {
        v13 = *((_QWORD *)this + 15);
        memset_0(v11, 0, (int)v10);
        v14 = CWbemClass::WriteDerivedClass(this, v12, v10, 0);
        if ( (v14 & 0x80000000) != 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v14);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, v14);
          }
           CBlobControl::`vcall'{24,{flat}}(v13, v12);
          (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v6 + 16LL))(v6);
          result = v14;
        }
        else
        {
          (*(void (__fastcall **)(struct CWbemClass *, unsigned __int8 *, _QWORD))(*(_QWORD *)v6 + 1152LL))(
            v6,
            v12,
            v10);
          (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v6 + 8LL))(v6);
          *a2 = v6;
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, v14);
          }
          (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v6 + 16LL))(v6);
          result = v14;
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
            138,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            2147749894LL);
        }
        (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v6 + 16LL))(v6);
        result = 2147749894LL;
      }
    }
    else
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          137,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          2147749894LL);
      }
      result = 2147749894LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800290a0  mov     [rsp+arg_0], rbx
0x1800290a5  mov     [rsp+arg_8], rsi
0x1800290aa  push    rdi
0x1800290ab  push    r12
0x1800290ad  push    r13
0x1800290af  push    r14
0x1800290b1  push    r15
0x1800290b3  sub     rsp, 40h
0x1800290b7  mov     r13, rdx
0x1800290ba  mov     r15, rcx
0x1800290bd  lea     r12, [rcx+1F8h]
0x1800290c4  mov     rcx, r12; this
0x1800290c7  call    ?Compact@CClassAndMethods@@QEAAXXZ; CClassAndMethods::Compact(void)
0x1800290cc  mov     ecx, 360h
0x1800290d1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800290d7  mov     [rsp+68h+arg_10], rax
0x1800290df  test    rax, rax
0x1800290e2  jz      loc_1800291FF
0x1800290e8  mov     rcx, rax; this
0x1800290eb  call    ??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x1800290f0  mov     r14, rax
0x1800290f3  test    r14, r14
0x1800290f6  jz      loc_18002925A
0x1800290fc  mov     [rsp+68h+arg_10], r14
0x180029104  mov     rsi, [r15+300h]
0x18002910b  mov     edi, [rsi]
0x18002910d  mov     rbx, [r15+238h]
0x180029114  mov     rcx, r12; this
0x180029117  call    ?EstimateDerivedPartSpace@CClassAndMethods@@QEAAKXZ; CClassAndMethods::EstimateDerivedPartSpace(void)
0x18002911c  sub     esi, ebx
0x18002911e  add     eax, edi
0x180029120  inc     esi
0x180029122  add     esi, eax
0x180029124  mov     rcx, [r15+78h]
0x180029128  mov     rax, [rcx]
0x18002912b  mov     edx, esi
0x18002912d  mov     rax, [rax+8]
0x180029131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029136  mov     rdi, rax
0x180029139  test    rax, rax
0x18002913c  jz      loc_1800292B4
0x180029142  mov     r12, [r15+78h]
0x180029146  mov     [rsp+68h+var_48], r12
0x18002914b  mov     [rsp+68h+var_40], rax
0x180029150  mov     [rsp+68h+var_38], 0
0x180029155  movsxd  r8, esi; Size
0x180029158  xor     edx, edx; Val
0x18002915a  mov     rcx, rax; void *
0x18002915d  call    memset_0
0x180029162  xor     r9d, r9d; struct CDecorationPart *
0x180029165  mov     r8d, esi; int
0x180029168  mov     rdx, rdi; unsigned __int8 *
0x18002916b  mov     rcx, r15; this
0x18002916e  call    ?WriteDerivedClass@CWbemClass@@QEAAJPEAEHPEAVCDecorationPart@@@Z; CWbemClass::WriteDerivedClass(uchar *,int,CDecorationPart *)
0x180029173  mov     ebx, eax
0x180029175  test    eax, eax
0x180029177  js      loc_180029207
0x18002917d  mov     [rsp+68h+var_38], 1
0x180029182  mov     rax, [r14]
0x180029185  mov     r8d, esi
0x180029188  mov     rdx, rdi
0x18002918b  mov     rcx, r14
0x18002918e  mov     rax, [rax+480h]
0x180029195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002919a  mov     rax, [r14]
0x18002919d  mov     rcx, r14
0x1800291a0  mov     rax, [rax+8]
0x1800291a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291a9  mov     [r13+0], r14
0x1800291ad  lea     rax, WPP_GLOBAL_Control
0x1800291b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291bb  cmp     rcx, rax
0x1800291be  jz      short loc_1800291CA
0x1800291c0  test    byte ptr [rcx+1Ch], 1
0x1800291c4  jnz     loc_180029359
0x1800291ca  mov     rax, [r14]
0x1800291cd  mov     rcx, r14
0x1800291d0  mov     rax, [rax+10h]
0x1800291d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291d9  mov     [rsp+68h+arg_10], 0
0x1800291e5  mov     eax, ebx
0x1800291e7  mov     rbx, [rsp+68h+arg_0]
0x1800291ec  mov     rsi, [rsp+68h+arg_8]
0x1800291f1  add     rsp, 40h
0x1800291f5  pop     r15
0x1800291f7  pop     r14
0x1800291f9  pop     r13
0x1800291fb  pop     r12
0x1800291fd  pop     rdi
0x1800291fe  retn
0x1800291ff  xor     r14d, r14d
0x180029202  jmp     loc_1800290F3
0x180029207  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002920d  mov     edx, ebx
0x18002920f  mov     rcx, rax
0x180029212  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180029218  lea     rax, WPP_GLOBAL_Control
0x18002921f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029226  cmp     rcx, rax
0x180029229  jnz     loc_180029328
0x18002922f  mov     rdx, rdi
0x180029232  mov     rcx, r12
0x180029235  call    ??_9CBlobControl@@$BBI@AA; [thunk]: CBlobControl::`vcall'{24,{flat}}
0x18002923a  nop
0x18002923b  mov     rax, [r14]
0x18002923e  mov     rcx, r14
0x180029241  mov     rax, [rax+10h]
0x180029245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002924a  mov     [rsp+68h+arg_10], 0
0x180029256  mov     eax, ebx
0x180029258  jmp     short loc_1800291E7
0x18002925a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180029260  mov     edx, 80041006h
0x180029265  mov     rcx, rax
0x180029268  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002926e  lea     rax, WPP_GLOBAL_Control
0x180029275  mov     rcx, cs:WPP_GLOBAL_Control
0x18002927c  cmp     rcx, rax
0x18002927f  jnz     short loc_18002928B
0x180029281  mov     eax, 80041006h
0x180029286  jmp     loc_1800291E7
0x18002928b  test    byte ptr [rcx+1Ch], 1
0x18002928f  jz      short loc_180029281
0x180029291  cmp     byte ptr [rcx+19h], 2
0x180029295  jb      short loc_180029281
0x180029297  mov     edx, 89h
0x18002929c  mov     r9d, 80041006h
0x1800292a2  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800292a9  mov     rcx, [rcx+10h]
0x1800292ad  call    WPP_SF_d
0x1800292b2  jmp     short loc_180029281
0x1800292b4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800292ba  mov     edx, 80041006h
0x1800292bf  mov     rcx, rax
0x1800292c2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800292c8  lea     rax, WPP_GLOBAL_Control
0x1800292cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292d6  cmp     rcx, rax
0x1800292d9  jz      short loc_180029303
0x1800292db  test    byte ptr [rcx+1Ch], 1
0x1800292df  jz      short loc_180029303
0x1800292e1  cmp     byte ptr [rcx+19h], 2
0x1800292e5  jb      short loc_180029303
0x1800292e7  mov     edx, 8Ah
0x1800292ec  mov     r9d, 80041006h
0x1800292f2  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800292f9  mov     rcx, [rcx+10h]
0x1800292fd  call    WPP_SF_d
0x180029302  nop
0x180029303  mov     rax, [r14]
0x180029306  mov     rcx, r14
0x180029309  mov     rax, [rax+10h]
0x18002930d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029312  mov     [rsp+68h+arg_10], 0
0x18002931e  mov     eax, 80041006h
0x180029323  jmp     loc_1800291E7
0x180029328  test    byte ptr [rcx+1Ch], 1
0x18002932c  jz      loc_18002922F
0x180029332  cmp     byte ptr [rcx+19h], 2
0x180029336  jb      loc_18002922F
0x18002933c  mov     edx, 8Bh
0x180029341  mov     r9d, ebx
0x180029344  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18002934b  mov     rcx, [rcx+10h]
0x18002934f  call    WPP_SF_d
0x180029354  jmp     loc_18002922F
0x180029359  cmp     byte ptr [rcx+19h], 2
0x18002935d  jb      loc_1800291CA
0x180029363  mov     edx, 8Ch
0x180029368  mov     r9d, ebx
0x18002936b  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180029372  mov     rcx, [rcx+10h]
0x180029376  call    WPP_SF_d
0x18002937b  jmp     loc_1800291CA
0x180029380  mov     eax, 80041006h
0x180029385  jmp     loc_1800291E7
```
