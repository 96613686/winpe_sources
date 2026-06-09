# CWbemInstance::SpawnInstance(long,IWbemClassObject * *)

- ea: `0x18006ae30`
- end: `0x18006b0a4`
- name: `?SpawnInstance@CWbemInstance@@UEAAJJPEAPEAUIWbemClassObject@@@Z`
- size: `628`
- prototype: `__int64 __fastcall(CWbemInstance *__hidden this, int, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180010150`
- `0x180013e80`
- `0x18001e970`
- `0x180037120`
- `0x180050490`
- `0x18006ae30`
- `0x180091972`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18006ae6d`
- `wbemcomn!GetMemLogObject` at `0x18006aed7`
- `wbemcomn!GetMemLogObject` at `0x18006b025`
- `wbemcomn!GetMemLogObject` at `0x18006ae6d`
- `wbemcomn!GetMemLogObject` at `0x18006aed7`
- `wbemcomn!GetMemLogObject` at `0x18006b025`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006ae7d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006aee7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006b030`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006ae7d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006aee7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006b030`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18006af89`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18006af89`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemInstance::SpawnInstance(CWbemInstance *this, int a2, struct IWbemClassObject **a3)
{
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  CMemoryLog *v8; // rax
  unsigned int v9; // eax
  size_t v10; // r12
  int inited; // ebx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // r15
  CWbemInstance *v14; // rax
  CWbemInstance *v15; // rdi
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  CWbemInstance *v18; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    v18 = this;
    (*(void (__fastcall **)(CWbemInstance *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
    if ( a2 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749896LL);
      }
LABEL_7:
      CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v18);
      return 2147749896LL;
    }
    if ( !a3 )
    {
      v8 = GetMemLogObject();
      CMemoryLog::Write(v8, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749896LL);
      }
      goto LABEL_7;
    }
    v9 = CWbemInstance::EstimateInstanceSpace((CWbemInstance *)((char *)this + 400), 0);
    v10 = (int)v9;
    inited = -2147217402;
    v12 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 8LL))(
                               *((_QWORD *)this + 15),
                               v9);
    v13 = v12;
    if ( !v12 )
      goto LABEL_24;
    memset_0(v12, 0, v10);
    v14 = (CWbemInstance *)CWin32DefaultArena::WbemMemAlloc(0x2A0u);
    v15 = v14 ? CWbemInstance::CWbemInstance(v14) : 0LL;
    if ( v15 )
    {
      inited = CWbemInstance::InitEmptyInstance(v15, (CWbemInstance *)((char *)this + 400), v13, v10, 0);
      if ( inited < 0 )
      {
        (*(void (__fastcall **)(CWbemInstance *, __int64))(*(_QWORD *)v15 + 848LL))(v15, 1);
      }
      else
      {
        *((_DWORD *)v15 + 10) = 0;
        inited = (**(__int64 (__fastcall ***)(CWbemInstance *, GUID *, struct IWbemClassObject **))v15)(
                   v15,
                   &IID_IWbemClassObject,
                   a3);
      }
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, unsigned __int8 *))(**((_QWORD **)this + 15) + 24LL))(*((_QWORD *)this + 15), v13);
    }
    if ( inited < 0 )
    {
LABEL_24:
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, inited);
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        (unsigned int)inited);
    }
    (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
    result = (unsigned int)inited;
  }
  catch ( CX_MemoryException )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v18 = this;
}

```

## disassembly

```asm
0x18006ae30  mov     rax, rsp
0x18006ae33  mov     [rax+8], rbx
0x18006ae37  mov     [rax+10h], rsi
0x18006ae3b  push    rdi
0x18006ae3c  push    r12
0x18006ae3e  push    r13
0x18006ae40  push    r14
0x18006ae42  push    r15
0x18006ae44  sub     rsp, 40h
0x18006ae48  mov     r14, r8
0x18006ae4b  mov     ebx, edx
0x18006ae4d  mov     rsi, rcx
0x18006ae50  mov     [rax+20h], rcx
0x18006ae54  mov     rax, [rcx]
0x18006ae57  mov     edx, 1
0x18006ae5c  mov     rax, [rax+118h]
0x18006ae63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae68  nop
0x18006ae69  test    ebx, ebx
0x18006ae6b  jz      short loc_18006AED2
0x18006ae6d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006ae73  mov     ebx, 80041008h
0x18006ae78  mov     edx, ebx
0x18006ae7a  mov     rcx, rax
0x18006ae7d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006ae83  lea     rax, WPP_GLOBAL_Control
0x18006ae8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ae91  cmp     rcx, rax
0x18006ae94  jz      short loc_18006AEBE
0x18006ae96  test    byte ptr [rcx+1Ch], 1
0x18006ae9a  jz      short loc_18006AEBE
0x18006ae9c  cmp     byte ptr [rcx+19h], 2
0x18006aea0  jb      short loc_18006AEBE
0x18006aea2  mov     edx, 38h ; '8'
0x18006aea7  mov     r9d, 80041008h
0x18006aead  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18006aeb4  mov     rcx, [rcx+10h]
0x18006aeb8  call    WPP_SF_d
0x18006aebd  nop
0x18006aebe  lea     rcx, [rsp+68h+arg_18]; this
0x18006aec6  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18006aecb  mov     eax, ebx
0x18006aecd  jmp     loc_18006B08B
0x18006aed2  test    r14, r14
0x18006aed5  jnz     short loc_18006AF3B
0x18006aed7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006aedd  mov     ebx, 80041008h
0x18006aee2  mov     edx, ebx
0x18006aee4  mov     rcx, rax
0x18006aee7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006aeed  lea     rax, WPP_GLOBAL_Control
0x18006aef4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aefb  cmp     rcx, rax
0x18006aefe  jz      short loc_18006AF27
0x18006af00  test    byte ptr [rcx+1Ch], 1
0x18006af04  jz      short loc_18006AF27
0x18006af06  cmp     byte ptr [rcx+19h], 2
0x18006af0a  jb      short loc_18006AF27
0x18006af0c  lea     edx, [r14+39h]
0x18006af10  mov     r9d, 80041008h
0x18006af16  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18006af1d  mov     rcx, [rcx+10h]
0x18006af21  call    WPP_SF_d
0x18006af26  nop
0x18006af27  lea     rcx, [rsp+68h+arg_18]; this
0x18006af2f  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18006af34  mov     eax, ebx
0x18006af36  jmp     loc_18006B08B
0x18006af3b  lea     r13, [rsi+190h]
0x18006af42  xor     edx, edx; struct CDecorationPart *
0x18006af44  mov     rcx, r13; struct CClassPart *
0x18006af47  call    ?EstimateInstanceSpace@CWbemInstance@@SAKAEAVCClassPart@@PEAVCDecorationPart@@@Z; CWbemInstance::EstimateInstanceSpace(CClassPart &,CDecorationPart *)
0x18006af4c  movsxd  r12, eax
0x18006af4f  mov     ebx, 80041006h
0x18006af54  mov     [rsp+68h+var_38], ebx
0x18006af58  mov     rcx, [rsi+78h]
0x18006af5c  mov     rdx, [rcx]
0x18006af5f  mov     rax, [rdx+8]
0x18006af63  mov     edx, r12d
0x18006af66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af6b  mov     r15, rax
0x18006af6e  test    rax, rax
0x18006af71  jz      loc_18006B025
0x18006af77  mov     r8, r12; Size
0x18006af7a  xor     edx, edx; Val
0x18006af7c  mov     rcx, rax; void *
0x18006af7f  call    memset_0
0x18006af84  mov     ecx, 2A0h
0x18006af89  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18006af8f  mov     [rsp+68h+var_30], rax
0x18006af94  test    rax, rax
0x18006af97  jz      short loc_18006AFA6
0x18006af99  mov     rcx, rax; this
0x18006af9c  call    ??0CWbemInstance@@QEAA@XZ; CWbemInstance::CWbemInstance(void)
0x18006afa1  mov     rdi, rax
0x18006afa4  jmp     short loc_18006AFA8
0x18006afa6  xor     edi, edi
0x18006afa8  test    rdi, rdi
0x18006afab  jz      short loc_18006B00E
0x18006afad  mov     [rsp+68h+var_48], 0; struct CDecorationPart *
0x18006afb6  mov     r9d, r12d; int
0x18006afb9  mov     r8, r15; unsigned __int8 *
0x18006afbc  mov     rdx, r13; struct CClassPart *
0x18006afbf  mov     rcx, rdi; this
0x18006afc2  call    ?InitEmptyInstance@CWbemInstance@@QEAAJAEAVCClassPart@@PEAEHPEAVCDecorationPart@@@Z; CWbemInstance::InitEmptyInstance(CClassPart &,uchar *,int,CDecorationPart *)
0x18006afc7  mov     ebx, eax
0x18006afc9  mov     [rsp+68h+var_38], eax
0x18006afcd  mov     rcx, rdi
0x18006afd0  test    eax, eax
0x18006afd2  js      short loc_18006AFF8
0x18006afd4  mov     dword ptr [rdi+28h], 0
0x18006afdb  mov     rax, [rdi]
0x18006afde  mov     r8, r14
0x18006afe1  lea     rdx, IID_IWbemClassObject
0x18006afe8  mov     rax, [rax]
0x18006afeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aff0  mov     ebx, eax
0x18006aff2  mov     [rsp+68h+var_38], eax
0x18006aff6  jmp     short loc_18006B021
0x18006aff8  mov     rax, [rdi]
0x18006affb  mov     edx, 1
0x18006b000  mov     rax, [rax+350h]
0x18006b007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b00c  jmp     short loc_18006B021
0x18006b00e  mov     rcx, [rsi+78h]
0x18006b012  mov     rax, [rcx]
0x18006b015  mov     rdx, r15
0x18006b018  mov     rax, [rax+18h]
0x18006b01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b021  test    ebx, ebx
0x18006b023  jns     short loc_18006B036
0x18006b025  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006b02b  mov     edx, ebx
0x18006b02d  mov     rcx, rax
0x18006b030  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006b036  lea     rax, WPP_GLOBAL_Control
0x18006b03d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b044  cmp     rcx, rax
0x18006b047  jz      short loc_18006B06E
0x18006b049  test    byte ptr [rcx+1Ch], 1
0x18006b04d  jz      short loc_18006B06E
0x18006b04f  cmp     byte ptr [rcx+19h], 2
0x18006b053  jb      short loc_18006B06E
0x18006b055  mov     edx, 3Ah ; ':'
0x18006b05a  mov     r9d, ebx
0x18006b05d  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18006b064  mov     rcx, [rcx+10h]
0x18006b068  call    WPP_SF_d
0x18006b06d  nop
0x18006b06e  mov     rax, [rsi]
0x18006b071  xor     edx, edx
0x18006b073  mov     rcx, rsi
0x18006b076  mov     rax, [rax+120h]
0x18006b07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b082  mov     eax, ebx
0x18006b084  jmp     short loc_18006B08B
0x18006b086  mov     eax, 80041006h
0x18006b08b  mov     rbx, [rsp+68h+arg_0]
0x18006b090  mov     rsi, [rsp+68h+arg_8]
0x18006b095  add     rsp, 40h
0x18006b099  pop     r15
0x18006b09b  pop     r14
0x18006b09d  pop     r13
0x18006b09f  pop     r12
0x18006b0a1  pop     rdi
0x18006b0a2  retn
```
