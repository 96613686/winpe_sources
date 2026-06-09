# CWbemClass::Clone(IWbemClassObject * *)

- ea: `0x1800201b0`
- end: `0x180020436`
- name: `?Clone@CWbemClass@@UEAAJPEAPEAUIWbemClassObject@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(CWbemClass *__hidden this, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001f640`
- `0x1800201b0`
- `0x180020440`
- `0x180037120`
- `0x180050490`
- `0x18006fa66`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800202dd`
- `wbemcomn!GetMemLogObject` at `0x18002034e`
- `wbemcomn!GetMemLogObject` at `0x1800203b1`
- `wbemcomn!GetMemLogObject` at `0x1800202dd`
- `wbemcomn!GetMemLogObject` at `0x18002034e`
- `wbemcomn!GetMemLogObject` at `0x1800203b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800202ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002035c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800203bf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800202ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002035c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800203bf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800201f7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800201f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemClass::Clone(CWbemClass *this, struct IWbemClassObject **a2)
{
  CWbemClass *v4; // rax
  CWbemClass *v5; // rsi
  void *v6; // rax
  void *v7; // r14
  unsigned int v8; // ebx
  __int64 result; // rax
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v13; // rax
  CWbemClass *v14; // [rsp+50h] [rbp+18h] BYREF
  CWbemClass *v15; // [rsp+58h] [rbp+20h]

  try
  {
    v14 = this;
    (*(void (__fastcall **)(CWbemClass *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
    if ( a2 )
    {
      CClassAndMethods::Compact((CWbemClass *)((char *)this + 504));
      v4 = (CWbemClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
      v15 = v4;
      if ( v4 )
        v5 = CWbemClass::CWbemClass(v4);
      else
        v5 = 0;
      if ( v5 )
      {
        v15 = v5;
        v6 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 8LL))(
                       *((_QWORD *)this + 15),
                       *((unsigned int *)this + 38));
        v7 = v6;
        if ( v6 )
        {
          memcpy_0(v6, *((const void **)this + 9), *((unsigned int *)this + 38));
          (*(void (__fastcall **)(CWbemClass *, void *, _QWORD))(*(_QWORD *)v5 + 1152LL))(
            v5,
            v7,
            *((unsigned int *)this + 38));
          (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v5 + 1128LL))(v5);
          v8 = (**(__int64 (__fastcall ***)(CWbemClass *, GUID *, struct IWbemClassObject **))v5)(
                 v5,
                 &IID_IWbemClassObject,
                 a2);
          (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v5 + 16LL))(v5);
          v15 = 0;
          (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
          result = v8;
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
              121,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749894LL);
          }
          (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v5 + 16LL))(v5);
          v15 = 0;
          CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v14);
          result = 2147749894LL;
        }
      }
      else
      {
        v11 = GetMemLogObject();
        CMemoryLog::Write(v11, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            120,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            2147749894LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v14);
        result = 2147749894LL;
      }
    }
    else
    {
      v10 = GetMemLogObject();
      CMemoryLog::Write(v10, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          119,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          2147749896LL);
      }
      (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      result = 2147749896LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v14 = this;
}

```

## disassembly

```asm
0x1800201b0  mov     [rsp+arg_0], rbx
0x1800201b5  push    rsi
0x1800201b6  push    rdi
0x1800201b7  push    r14
0x1800201b9  sub     rsp, 20h
0x1800201bd  mov     rbx, rdx
0x1800201c0  mov     rdi, rcx
0x1800201c3  mov     [rsp+38h+arg_10], rcx
0x1800201c8  mov     rax, [rcx]
0x1800201cb  mov     edx, 1
0x1800201d0  mov     rax, [rax+118h]
0x1800201d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201dc  nop
0x1800201dd  test    rbx, rbx
0x1800201e0  jz      loc_1800202DD
0x1800201e6  lea     rcx, [rdi+1F8h]; this
0x1800201ed  call    ?Compact@CClassAndMethods@@QEAAXXZ; CClassAndMethods::Compact(void)
0x1800201f2  mov     ecx, 360h
0x1800201f7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800201fd  mov     [rsp+38h+arg_18], rax
0x180020202  test    rax, rax
0x180020205  jz      loc_180020347
0x18002020b  mov     rcx, rax; this
0x18002020e  call    ??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x180020213  mov     rsi, rax
0x180020216  test    rsi, rsi
0x180020219  jz      loc_18002034E
0x18002021f  mov     [rsp+38h+arg_18], rsi
0x180020224  mov     rcx, [rdi+78h]
0x180020228  mov     rax, [rcx]
0x18002022b  mov     edx, [rdi+98h]
0x180020231  mov     rax, [rax+8]
0x180020235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002023a  mov     r14, rax
0x18002023d  test    rax, rax
0x180020240  jz      loc_1800203B1
0x180020246  mov     r8d, [rdi+98h]; Size
0x18002024d  mov     rdx, [rdi+48h]; Src
0x180020251  mov     rcx, rax; void *
0x180020254  call    memcpy_0
0x180020259  mov     rax, [rsi]
0x18002025c  mov     r8d, [rdi+98h]
0x180020263  mov     rdx, r14
0x180020266  mov     rcx, rsi
0x180020269  mov     rax, [rax+480h]
0x180020270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020275  mov     rax, [rsi]
0x180020278  mov     rcx, rsi
0x18002027b  mov     rax, [rax+468h]
0x180020282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020287  mov     rax, [rsi]
0x18002028a  mov     r8, rbx
0x18002028d  lea     rdx, IID_IWbemClassObject
0x180020294  mov     rcx, rsi
0x180020297  mov     rax, [rax]
0x18002029a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002029f  mov     ebx, eax
0x1800202a1  mov     rcx, [rsi]
0x1800202a4  mov     rax, [rcx+10h]
0x1800202a8  mov     rcx, rsi
0x1800202ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202b0  mov     [rsp+38h+arg_18], 0
0x1800202b9  mov     rcx, [rdi]
0x1800202bc  mov     rax, [rcx+120h]
0x1800202c3  xor     edx, edx
0x1800202c5  mov     rcx, rdi
0x1800202c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202cd  mov     eax, ebx
0x1800202cf  mov     rbx, [rsp+38h+arg_0]
0x1800202d4  add     rsp, 20h
0x1800202d8  pop     r14
0x1800202da  pop     rdi
0x1800202db  pop     rsi
0x1800202dc  retn
0x1800202dd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800202e3  mov     ebx, 80041008h
0x1800202e8  mov     edx, ebx
0x1800202ea  mov     rcx, rax
0x1800202ed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800202f3  lea     rax, WPP_GLOBAL_Control
0x1800202fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180020301  cmp     rcx, rax
0x180020304  jnz     short loc_18002031E
0x180020306  mov     rcx, [rdi]
0x180020309  mov     rax, [rcx+120h]
0x180020310  xor     edx, edx
0x180020312  mov     rcx, rdi
0x180020315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002031a  mov     eax, ebx
0x18002031c  jmp     short loc_1800202CF
0x18002031e  test    byte ptr [rcx+1Ch], 1
0x180020322  jz      short loc_180020306
0x180020324  cmp     byte ptr [rcx+19h], 2
0x180020328  jb      short loc_180020306
0x18002032a  mov     edx, 77h ; 'w'
0x18002032f  mov     r9d, 80041008h
0x180020335  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18002033c  mov     rcx, [rcx+10h]
0x180020340  call    WPP_SF_d
0x180020345  jmp     short loc_180020306
0x180020347  xor     esi, esi
0x180020349  jmp     loc_180020216
0x18002034e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180020354  mov     edx, 80041006h
0x180020359  mov     rcx, rax
0x18002035c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180020362  lea     rax, WPP_GLOBAL_Control
0x180020369  mov     rcx, cs:WPP_GLOBAL_Control
0x180020370  cmp     rcx, rax
0x180020373  jz      short loc_18002039D
0x180020375  test    byte ptr [rcx+1Ch], 1
0x180020379  jz      short loc_18002039D
0x18002037b  cmp     byte ptr [rcx+19h], 2
0x18002037f  jb      short loc_18002039D
0x180020381  mov     edx, 78h ; 'x'
0x180020386  mov     r9d, 80041006h
0x18002038c  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180020393  mov     rcx, [rcx+10h]
0x180020397  call    WPP_SF_d
0x18002039c  nop
0x18002039d  lea     rcx, [rsp+38h+arg_10]; this
0x1800203a2  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x1800203a7  mov     eax, 80041006h
0x1800203ac  jmp     loc_1800202CF
0x1800203b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800203b7  mov     edx, 80041006h
0x1800203bc  mov     rcx, rax
0x1800203bf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800203c5  lea     rax, WPP_GLOBAL_Control
0x1800203cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203d3  cmp     rcx, rax
0x1800203d6  jz      short loc_180020400
0x1800203d8  test    byte ptr [rcx+1Ch], 1
0x1800203dc  jz      short loc_180020400
0x1800203de  cmp     byte ptr [rcx+19h], 2
0x1800203e2  jb      short loc_180020400
0x1800203e4  mov     edx, 79h ; 'y'
0x1800203e9  mov     r9d, 80041006h
0x1800203ef  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800203f6  mov     rcx, [rcx+10h]
0x1800203fa  call    WPP_SF_d
0x1800203ff  nop
0x180020400  mov     rax, [rsi]
0x180020403  mov     rcx, rsi
0x180020406  mov     rax, [rax+10h]
0x18002040a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002040f  mov     [rsp+38h+arg_18], 0
0x180020418  lea     rcx, [rsp+38h+arg_10]; this
0x18002041d  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180020422  mov     eax, 80041006h
0x180020427  jmp     loc_1800202CF
0x18002042c  mov     eax, 80041006h
0x180020431  jmp     loc_1800202CF
```
