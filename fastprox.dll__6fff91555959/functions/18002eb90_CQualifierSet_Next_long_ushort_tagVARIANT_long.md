# CQualifierSet::Next(long,ushort * *,tagVARIANT *,long *)

- ea: `0x18002eb90`
- end: `0x18002ee28`
- name: `?Next@CQualifierSet@@UEAAJJPEAPEAGPEAUtagVARIANT@@PEAJ@Z`
- size: `664`
- prototype: `__int64 __usercall@<rax>(CQualifierSet *__hidden this@<rcx>, int@<edx>, unsigned __int16 **@<r8>, struct tagVARIANT *@<r9>, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180008f20`
- `0x18002eb90`
- `0x18002ee30`
- `0x180037120`
- `0x180050490`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002ec97`
- `wbemcomn!GetMemLogObject` at `0x18002ecf9`
- `wbemcomn!GetMemLogObject` at `0x18002ed5b`
- `wbemcomn!GetMemLogObject` at `0x18002edbd`
- `wbemcomn!GetMemLogObject` at `0x18002ec97`
- `wbemcomn!GetMemLogObject` at `0x18002ecf9`
- `wbemcomn!GetMemLogObject` at `0x18002ed5b`
- `wbemcomn!GetMemLogObject` at `0x18002edbd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002eca7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ed09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ed6b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002edc8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002eca7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ed09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ed6b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002edc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CQualifierSet::Next(
        CQualifierSet *this,
        int a2,
        unsigned __int16 **a3,
        struct tagVARIANT *a4,
        int *a5)
{
  __int64 v9; // rdi
  int *v10; // rsi
  int v11; // eax
  _QWORD *v12; // r15
  _DWORD *v13; // r14
  int v14; // ebx
  __int64 result; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  _QWORD v22[9]; // [rsp+30h] [rbp-48h] BYREF

  try
  {
    v9 = *((_QWORD *)this + 5);
    v22[0] = v9;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 280LL))(v9, 0);
    if ( a2 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
          2147749896LL);
      }
      CWbemObject::CLock::~CLock((CWbemObject::CLock *)v22);
      result = 2147749896LL;
    }
    else
    {
      v10 = (int *)((char *)this + 76);
      v11 = *((_DWORD *)this + 19);
      if ( v11 == -1 )
      {
        v17 = GetMemLogObject();
        CMemoryLog::Write(v17, -2147217379);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            128,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            2147749917LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)v22);
        result = 2147749917LL;
      }
      else if ( v11 == *((_DWORD *)this + 16) )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 288LL))(v9, 0);
        result = 262149;
      }
      else if ( (unsigned int)CQualifierSet::SelfRebase(this) )
      {
        v12 = (_QWORD *)((char *)this + 68);
        if ( a3 )
          *a3 = COleAuto::_SysAllocString(*(const unsigned __int16 **)(*v12 + 8LL * *v10));
        v13 = (_DWORD *)((char *)this + 76);
        v14 = (*(__int64 (__fastcall **)(CQualifierSet *, _QWORD, _QWORD, struct tagVARIANT *, int *))(*(_QWORD *)this + 24LL))(
                this,
                *(_QWORD *)(*v12 + 8LL * *v10),
                0,
                a4,
                a5);
        if ( v14 < 0 )
        {
          v19 = GetMemLogObject();
          CMemoryLog::Write(v19, v14);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              130,
              WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
              (unsigned int)v14);
          }
          CWbemObject::CLock::~CLock((CWbemObject::CLock *)v22);
          result = (unsigned int)v14;
        }
        else
        {
          ++*v13;
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 288LL))(v9, 0);
          result = 0;
        }
      }
      else
      {
        v18 = GetMemLogObject();
        CMemoryLog::Write(v18, -2147217359);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            129,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            2147749937LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)v22);
        result = 2147749937LL;
      }
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, -2147217407);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749889LL);
    }
    return 2147749889LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002eb90  push    rbx
0x18002eb92  push    rsi
0x18002eb93  push    rdi
0x18002eb94  push    r12
0x18002eb96  push    r14
0x18002eb98  push    r15
0x18002eb9a  sub     rsp, 48h
0x18002eb9e  mov     r12, r9
0x18002eba1  mov     r14, r8
0x18002eba4  mov     esi, edx
0x18002eba6  mov     rbx, rcx
0x18002eba9  mov     rdi, [rcx+28h]
0x18002ebad  mov     [rsp+78h+var_48], rdi
0x18002ebb2  mov     rax, [rdi]
0x18002ebb5  xor     edx, edx
0x18002ebb7  mov     rcx, rdi
0x18002ebba  mov     rax, [rax+118h]
0x18002ebc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebc6  nop
0x18002ebc7  test    esi, esi
0x18002ebc9  jnz     loc_18002EC97
0x18002ebcf  lea     rsi, [rbx+4Ch]
0x18002ebd3  mov     eax, [rsi]
0x18002ebd5  cmp     eax, 0FFFFFFFFh
0x18002ebd8  jz      loc_18002ECF9
0x18002ebde  cmp     eax, [rbx+40h]
0x18002ebe1  jz      loc_18002EC77
0x18002ebe7  mov     rcx, rbx; this
0x18002ebea  call    ?SelfRebase@CQualifierSet@@QEAAHXZ; CQualifierSet::SelfRebase(void)
0x18002ebef  test    eax, eax
0x18002ebf1  jz      loc_18002ED5B
0x18002ebf7  lea     r15, [rbx+44h]
0x18002ebfb  test    r14, r14
0x18002ebfe  jz      loc_18002EC92
0x18002ec04  movsxd  rax, dword ptr [rsi]
0x18002ec07  mov     rcx, [r15]
0x18002ec0a  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x18002ec0e  call    ?_SysAllocString@COleAuto@@SAPEAGPEBG@Z; COleAuto::_SysAllocString(ushort const *)
0x18002ec13  mov     [r14], rax
0x18002ec16  lea     r14, [rbx+4Ch]
0x18002ec1a  mov     rax, [rbx]
0x18002ec1d  movsxd  r10, dword ptr [rsi]
0x18002ec20  mov     rdx, [r15]
0x18002ec23  mov     rcx, [rsp+78h+arg_20]
0x18002ec2b  mov     [rsp+78h+var_58], rcx
0x18002ec30  mov     r9, r12
0x18002ec33  xor     r8d, r8d
0x18002ec36  mov     rdx, [rdx+r10*8]
0x18002ec3a  mov     rcx, rbx
0x18002ec3d  mov     rax, [rax+18h]
0x18002ec41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec46  mov     ebx, eax
0x18002ec48  test    eax, eax
0x18002ec4a  js      loc_18002EDBD
0x18002ec50  inc     dword ptr [r14]
0x18002ec53  mov     rax, [rdi]
0x18002ec56  xor     edx, edx
0x18002ec58  mov     rcx, rdi
0x18002ec5b  mov     rax, [rax+120h]
0x18002ec62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec67  xor     eax, eax
0x18002ec69  add     rsp, 48h
0x18002ec6d  pop     r15
0x18002ec6f  pop     r14
0x18002ec71  pop     r12
0x18002ec73  pop     rdi
0x18002ec74  pop     rsi
0x18002ec75  pop     rbx
0x18002ec76  retn
0x18002ec77  mov     rax, [rdi]
0x18002ec7a  xor     edx, edx
0x18002ec7c  mov     rcx, rdi
0x18002ec7f  mov     rax, [rax+120h]
0x18002ec86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec8b  mov     eax, 40005h
0x18002ec90  jmp     short loc_18002EC69
0x18002ec92  mov     r14, rsi
0x18002ec95  jmp     short loc_18002EC1A
0x18002ec97  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ec9d  mov     ebx, 80041008h
0x18002eca2  mov     edx, ebx
0x18002eca4  mov     rcx, rax
0x18002eca7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ecad  lea     rax, WPP_GLOBAL_Control
0x18002ecb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecbb  cmp     rcx, rax
0x18002ecbe  jz      short loc_18002ECE8
0x18002ecc0  test    byte ptr [rcx+1Ch], 1
0x18002ecc4  jz      short loc_18002ECE8
0x18002ecc6  cmp     byte ptr [rcx+19h], 2
0x18002ecca  jb      short loc_18002ECE8
0x18002eccc  mov     edx, 7Fh
0x18002ecd1  mov     r9d, 80041008h
0x18002ecd7  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18002ecde  mov     rcx, [rcx+10h]
0x18002ece2  call    WPP_SF_d
0x18002ece7  nop
0x18002ece8  lea     rcx, [rsp+78h+var_48]; this
0x18002eced  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18002ecf2  mov     eax, ebx
0x18002ecf4  jmp     loc_18002EC69
0x18002ecf9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ecff  mov     ebx, 8004101Dh
0x18002ed04  mov     edx, ebx
0x18002ed06  mov     rcx, rax
0x18002ed09  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ed0f  lea     rax, WPP_GLOBAL_Control
0x18002ed16  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed1d  cmp     rcx, rax
0x18002ed20  jz      short loc_18002ED4A
0x18002ed22  test    byte ptr [rcx+1Ch], 1
0x18002ed26  jz      short loc_18002ED4A
0x18002ed28  cmp     byte ptr [rcx+19h], 2
0x18002ed2c  jb      short loc_18002ED4A
0x18002ed2e  mov     edx, 80h
0x18002ed33  mov     r9d, 8004101Dh
0x18002ed39  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18002ed40  mov     rcx, [rcx+10h]
0x18002ed44  call    WPP_SF_d
0x18002ed49  nop
0x18002ed4a  lea     rcx, [rsp+78h+var_48]; this
0x18002ed4f  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18002ed54  mov     eax, ebx
0x18002ed56  jmp     loc_18002EC69
0x18002ed5b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ed61  mov     ebx, 80041031h
0x18002ed66  mov     edx, ebx
0x18002ed68  mov     rcx, rax
0x18002ed6b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ed71  lea     rax, WPP_GLOBAL_Control
0x18002ed78  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed7f  cmp     rcx, rax
0x18002ed82  jz      short loc_18002EDAC
0x18002ed84  test    byte ptr [rcx+1Ch], 1
0x18002ed88  jz      short loc_18002EDAC
0x18002ed8a  cmp     byte ptr [rcx+19h], 2
0x18002ed8e  jb      short loc_18002EDAC
0x18002ed90  mov     edx, 81h
0x18002ed95  mov     r9d, 80041031h
0x18002ed9b  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18002eda2  mov     rcx, [rcx+10h]
0x18002eda6  call    WPP_SF_d
0x18002edab  nop
0x18002edac  lea     rcx, [rsp+78h+var_48]; this
0x18002edb1  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18002edb6  mov     eax, ebx
0x18002edb8  jmp     loc_18002EC69
0x18002edbd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002edc3  mov     edx, ebx
0x18002edc5  mov     rcx, rax
0x18002edc8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002edce  lea     rax, WPP_GLOBAL_Control
0x18002edd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eddc  cmp     rcx, rax
0x18002eddf  jz      short loc_18002EE06
0x18002ede1  test    byte ptr [rcx+1Ch], 1
0x18002ede5  jz      short loc_18002EE06
0x18002ede7  cmp     byte ptr [rcx+19h], 2
0x18002edeb  jb      short loc_18002EE06
0x18002eded  mov     edx, 82h
0x18002edf2  mov     r9d, ebx
0x18002edf5  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18002edfc  mov     rcx, [rcx+10h]
0x18002ee00  call    WPP_SF_d
0x18002ee05  nop
0x18002ee06  lea     rcx, [rsp+78h+var_48]; this
0x18002ee0b  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18002ee10  mov     eax, ebx
0x18002ee12  jmp     loc_18002EC69
0x18002ee17  mov     eax, 80041006h
0x18002ee1c  jmp     short loc_18002EE23
0x18002ee1e  mov     eax, 80041001h
0x18002ee23  jmp     loc_18002EC69
```
