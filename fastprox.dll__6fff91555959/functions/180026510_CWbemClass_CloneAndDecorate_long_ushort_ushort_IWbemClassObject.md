# CWbemClass::CloneAndDecorate(long,ushort *,ushort *,IWbemClassObject * *)

- ea: `0x180026510`
- end: `0x180026872`
- name: `?CloneAndDecorate@CWbemClass@@UEAAJJPEAG0PEAPEAUIWbemClassObject@@@Z`
- size: `866`
- prototype: `int(CWbemClass *__hidden this, int, unsigned __int16 *, unsigned __int16 *, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18001e0e0`
- `0x18001f640`
- `0x180020000`
- `0x180020440`
- `0x180026510`
- `0x1800276c0`
- `0x180037120`
- `0x180050490`
- `0x18006fa66`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002670a`
- `wbemcomn!GetMemLogObject` at `0x180026756`
- `wbemcomn!GetMemLogObject` at `0x1800267b9`
- `wbemcomn!GetMemLogObject` at `0x18002670a`
- `wbemcomn!GetMemLogObject` at `0x180026756`
- `wbemcomn!GetMemLogObject` at `0x1800267b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002671a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180026764`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800267c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002671a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180026764`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800267c7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180026577`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180026577`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemClass::CloneAndDecorate(
        CWbemClass *this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IWbemClassObject **a5)
{
  CWbemClass *v8; // rax
  CWbemClass *v9; // rsi
  char *v10; // r13
  char *v11; // rax
  char v12; // cl
  unsigned int v13; // ebx
  unsigned int Length; // eax
  unsigned int v15; // ebx
  __int64 result; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v20; // rax
  int v21; // [rsp+20h] [rbp-68h] BYREF
  int v22; // [rsp+24h] [rbp-64h] BYREF
  int v23; // [rsp+28h] [rbp-60h]
  int v24; // [rsp+2Ch] [rbp-5Ch]
  unsigned int v25; // [rsp+30h] [rbp-58h]
  CWbemClass *v26; // [rsp+38h] [rbp-50h] BYREF
  CWbemClass *v27; // [rsp+40h] [rbp-48h]

  try
  {
    v26 = this;
    (*(void (__fastcall **)(CWbemClass *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
    if ( a5 && a3 && a4 )
    {
      CClassAndMethods::Compact((CWbemClass *)((char *)this + 504));
      v8 = (CWbemClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
      v27 = v8;
      if ( v8 )
        v9 = CWbemClass::CWbemClass(v8);
      else
        v9 = 0;
      if ( v9 )
      {
        v27 = v9;
        v21 = 0;
        v23 = CCompressedString::ComputeNecessarySpace(a3, &v21);
        v22 = 0;
        v24 = v23 + CCompressedString::ComputeNecessarySpace(a4, &v22);
        v25 = v24 + *((_DWORD *)this + 38) - CDecorationPart::GetLength((CWbemClass *)((char *)this + 72)) + 1;
        v10 = (char *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 8LL))(*((_QWORD *)this + 15));
        if ( v10 )
        {
          v11 = (char *)*((_QWORD *)this + 9);
          v12 = *v11;
          *v10 = *v11;
          v12 |= 4u;
          *v10 = v12;
          *v10 = v12 & 0xDF;
          CCompressedString::SetFromUnicode((CCompressedString *)(v10 + 1), v21, a3);
          CCompressedString::SetFromUnicode((CCompressedString *)&v10[v23 + 1], v22, a4);
          v13 = *((_DWORD *)this + 38) - CDecorationPart::GetLength((CWbemClass *)((char *)this + 72));
          Length = CDecorationPart::GetLength((CWbemClass *)((char *)this + 72));
          memcpy_0(&v10[v24 + 1], (const void *)(*((_QWORD *)this + 9) + Length), v13);
          (*(void (__fastcall **)(CWbemClass *, char *, _QWORD))(*(_QWORD *)v9 + 1152LL))(v9, v10, v25);
          (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v9 + 1128LL))(v9);
          v15 = (**(__int64 (__fastcall ***)(CWbemClass *, GUID *, struct IWbemClassObject **))v9)(
                  v9,
                  &IID_IWbemClassObject,
                  a5);
          (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v9 + 16LL))(v9);
          v27 = 0;
          (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
          result = v15;
        }
        else
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              125,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749894LL);
          }
          (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v9 + 16LL))(v9);
          v27 = 0;
          CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v26);
          result = 2147749894LL;
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
            124,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            2147749894LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v26);
        result = 2147749894LL;
      }
    }
    else
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          123,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          2147749896LL);
      }
      (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      result = 2147749896LL;
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x180026510  push    rbx
0x180026512  push    rsi
0x180026513  push    rdi
0x180026514  push    r12
0x180026516  push    r13
0x180026518  push    r14
0x18002651a  push    r15
0x18002651c  sub     rsp, 50h
0x180026520  mov     r14, r9
0x180026523  mov     r15, r8
0x180026526  mov     rdi, rcx
0x180026529  mov     [rsp+88h+var_50], rcx
0x18002652e  mov     rax, [rcx]
0x180026531  mov     edx, 1
0x180026536  mov     rax, [rax+118h]
0x18002653d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026542  nop
0x180026543  mov     r12, [rsp+88h+arg_20]
0x18002654b  test    r12, r12
0x18002654e  jz      loc_18002670A
0x180026554  test    r15, r15
0x180026557  jz      loc_18002670A
0x18002655d  test    r14, r14
0x180026560  jz      loc_18002670A
0x180026566  lea     rcx, [rdi+1F8h]; this
0x18002656d  call    ?Compact@CClassAndMethods@@QEAAXXZ; CClassAndMethods::Compact(void)
0x180026572  mov     ecx, 360h
0x180026577  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002657d  mov     [rsp+88h+var_48], rax
0x180026582  test    rax, rax
0x180026585  jz      loc_18002674F
0x18002658b  mov     rcx, rax; this
0x18002658e  call    ??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x180026593  mov     rsi, rax
0x180026596  test    rsi, rsi
0x180026599  jz      loc_180026756
0x18002659f  mov     [rsp+88h+var_48], rsi
0x1800265a4  mov     [rsp+88h+var_68], 0
0x1800265ac  lea     rdx, [rsp+88h+var_68]; int *
0x1800265b1  mov     rcx, r15; unsigned __int16 *
0x1800265b4  call    ?ComputeNecessarySpace@CCompressedString@@SAHPEBGAEAH@Z; CCompressedString::ComputeNecessarySpace(ushort const *,int &)
0x1800265b9  mov     ebx, eax
0x1800265bb  mov     [rsp+88h+var_60], eax
0x1800265bf  mov     [rsp+88h+var_64], 0
0x1800265c7  lea     rdx, [rsp+88h+var_64]; int *
0x1800265cc  mov     rcx, r14; unsigned __int16 *
0x1800265cf  call    ?ComputeNecessarySpace@CCompressedString@@SAHPEBGAEAH@Z; CCompressedString::ComputeNecessarySpace(ushort const *,int &)
0x1800265d4  lea     r13d, [rbx+rax]
0x1800265d8  mov     [rsp+88h+var_5C], r13d
0x1800265dd  lea     rcx, [rdi+48h]; this
0x1800265e1  call    ?GetLength@CDecorationPart@@QEAAKXZ; CDecorationPart::GetLength(void)
0x1800265e6  mov     edx, [rdi+98h]
0x1800265ec  add     edx, r13d
0x1800265ef  sub     edx, eax
0x1800265f1  inc     edx
0x1800265f3  mov     [rsp+88h+var_58], edx
0x1800265f7  mov     rcx, [rdi+78h]
0x1800265fb  mov     rax, [rcx]
0x1800265fe  mov     rax, [rax+8]
0x180026602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026607  mov     r13, rax
0x18002660a  test    rax, rax
0x18002660d  jz      loc_1800267B9
0x180026613  mov     rax, [rdi+48h]
0x180026617  mov     cl, [rax]
0x180026619  mov     [r13+0], cl
0x18002661d  or      cl, 4
0x180026620  mov     [r13+0], cl
0x180026624  and     cl, 0DFh
0x180026627  mov     [r13+0], cl
0x18002662b  lea     rbx, [r13+1]
0x18002662f  mov     r8, r15; unsigned __int16 *
0x180026632  mov     edx, [rsp+88h+var_68]; int
0x180026636  mov     rcx, rbx; this
0x180026639  call    ?SetFromUnicode@CCompressedString@@QEAAXHPEBG@Z; CCompressedString::SetFromUnicode(int,ushort const *)
0x18002663e  movsxd  rcx, [rsp+88h+var_60]
0x180026643  add     rcx, rbx; this
0x180026646  mov     r8, r14; unsigned __int16 *
0x180026649  mov     edx, [rsp+88h+var_64]; int
0x18002664d  call    ?SetFromUnicode@CCompressedString@@QEAAXHPEBG@Z; CCompressedString::SetFromUnicode(int,ushort const *)
0x180026652  lea     r14, [rdi+48h]
0x180026656  mov     rcx, r14; this
0x180026659  call    ?GetLength@CDecorationPart@@QEAAKXZ; CDecorationPart::GetLength(void)
0x18002665e  mov     ebx, [rdi+98h]
0x180026664  sub     ebx, eax
0x180026666  mov     rcx, r14; this
0x180026669  call    ?GetLength@CDecorationPart@@QEAAKXZ; CDecorationPart::GetLength(void)
0x18002666e  mov     edx, eax
0x180026670  add     rdx, [r14]; Src
0x180026673  movsxd  rcx, [rsp+88h+var_5C]
0x180026678  inc     rcx
0x18002667b  add     rcx, r13; void *
0x18002667e  mov     r8d, ebx; Size
0x180026681  call    memcpy_0
0x180026686  mov     rax, [rsi]
0x180026689  mov     r8d, [rsp+88h+var_58]
0x18002668e  mov     rdx, r13
0x180026691  mov     rcx, rsi
0x180026694  mov     rax, [rax+480h]
0x18002669b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266a0  mov     rax, [rsi]
0x1800266a3  mov     rcx, rsi
0x1800266a6  mov     rax, [rax+468h]
0x1800266ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266b2  mov     rax, [rsi]
0x1800266b5  mov     r8, r12
0x1800266b8  lea     rdx, IID_IWbemClassObject
0x1800266bf  mov     rcx, rsi
0x1800266c2  mov     rax, [rax]
0x1800266c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266ca  mov     ebx, eax
0x1800266cc  mov     rcx, [rsi]
0x1800266cf  mov     rax, [rcx+10h]
0x1800266d3  mov     rcx, rsi
0x1800266d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266db  mov     [rsp+88h+var_48], 0
0x1800266e4  mov     rcx, [rdi]
0x1800266e7  mov     rax, [rcx+120h]
0x1800266ee  xor     edx, edx
0x1800266f0  mov     rcx, rdi
0x1800266f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266f8  mov     eax, ebx
0x1800266fa  add     rsp, 50h
0x1800266fe  pop     r15
0x180026700  pop     r14
0x180026702  pop     r13
0x180026704  pop     r12
0x180026706  pop     rdi
0x180026707  pop     rsi
0x180026708  pop     rbx
0x180026709  retn
0x18002670a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180026710  mov     ebx, 80041008h
0x180026715  mov     edx, ebx
0x180026717  mov     rcx, rax
0x18002671a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180026720  lea     rax, WPP_GLOBAL_Control
0x180026727  mov     rcx, cs:WPP_GLOBAL_Control
0x18002672e  cmp     rcx, rax
0x180026731  jnz     loc_180026834
0x180026737  mov     rcx, [rdi]
0x18002673a  mov     rax, [rcx+120h]
0x180026741  xor     edx, edx
0x180026743  mov     rcx, rdi
0x180026746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002674b  mov     eax, ebx
0x18002674d  jmp     short loc_1800266FA
0x18002674f  xor     esi, esi
0x180026751  jmp     loc_180026596
0x180026756  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002675c  mov     edx, 80041006h
0x180026761  mov     rcx, rax
0x180026764  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002676a  lea     rax, WPP_GLOBAL_Control
0x180026771  mov     rcx, cs:WPP_GLOBAL_Control
0x180026778  cmp     rcx, rax
0x18002677b  jz      short loc_1800267A5
0x18002677d  test    byte ptr [rcx+1Ch], 1
0x180026781  jz      short loc_1800267A5
0x180026783  cmp     byte ptr [rcx+19h], 2
0x180026787  jb      short loc_1800267A5
0x180026789  mov     edx, 7Ch ; '|'
0x18002678e  mov     r9d, 80041006h
0x180026794  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18002679b  mov     rcx, [rcx+10h]
0x18002679f  call    WPP_SF_d
0x1800267a4  nop
0x1800267a5  lea     rcx, [rsp+88h+var_50]; this
0x1800267aa  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x1800267af  mov     eax, 80041006h
0x1800267b4  jmp     loc_1800266FA
0x1800267b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800267bf  mov     edx, 80041006h
0x1800267c4  mov     rcx, rax
0x1800267c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800267cd  lea     rax, WPP_GLOBAL_Control
0x1800267d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267db  cmp     rcx, rax
0x1800267de  jz      short loc_180026808
0x1800267e0  test    byte ptr [rcx+1Ch], 1
0x1800267e4  jz      short loc_180026808
0x1800267e6  cmp     byte ptr [rcx+19h], 2
0x1800267ea  jb      short loc_180026808
0x1800267ec  mov     edx, 7Dh ; '}'
0x1800267f1  mov     r9d, 80041006h
0x1800267f7  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800267fe  mov     rcx, [rcx+10h]
0x180026802  call    WPP_SF_d
0x180026807  nop
0x180026808  mov     rax, [rsi]
0x18002680b  mov     rcx, rsi
0x18002680e  mov     rax, [rax+10h]
0x180026812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026817  mov     [rsp+88h+var_48], 0
0x180026820  lea     rcx, [rsp+88h+var_50]; this
0x180026825  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18002682a  mov     eax, 80041006h
0x18002682f  jmp     loc_1800266FA
0x180026834  test    byte ptr [rcx+1Ch], 1
0x180026838  jz      loc_180026737
0x18002683e  cmp     byte ptr [rcx+19h], 2
0x180026842  jb      loc_180026737
0x180026848  mov     edx, 7Bh ; '{'
0x18002684d  mov     r9d, 80041008h
0x180026853  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18002685a  mov     rcx, [rcx+10h]
0x18002685e  call    WPP_SF_d
0x180026863  jmp     loc_180026737
0x180026868  mov     eax, 80041006h
0x18002686d  jmp     loc_1800266FA
```
