# CWbemClass::SpawnDerivedClass(long,IWbemClassObject * *)

- ea: `0x180028e50`
- end: `0x180029095`
- name: `?SpawnDerivedClass@CWbemClass@@UEAAJJPEAPEAUIWbemClassObject@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(CWbemClass *__hidden this, int, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180028e50`
- `0x1800290a0`
- `0x180037120`
- `0x180050490`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180028f34`
- `wbemcomn!GetMemLogObject` at `0x180028f7a`
- `wbemcomn!GetMemLogObject` at `0x180028f97`
- `wbemcomn!GetMemLogObject` at `0x18002900d`
- `wbemcomn!GetMemLogObject` at `0x180028f34`
- `wbemcomn!GetMemLogObject` at `0x180028f7a`
- `wbemcomn!GetMemLogObject` at `0x180028f97`
- `wbemcomn!GetMemLogObject` at `0x18002900d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028f45`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028f85`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028fa7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002901d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028f45`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028f85`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028fa7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002901d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemClass::SpawnDerivedClass(CWbemClass *this, int a2, struct IWbemClassObject **a3)
{
  int v6; // esi
  struct CWbemClass *v7; // rbx
  CMemoryLog *MemLogObject; // rax
  unsigned int v10; // ebx
  CWbemRefreshingSvc *v11; // rcx
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r9
  CMemoryLog *v16; // rax
  struct CWbemClass *v17; // [rsp+40h] [rbp+8h] BYREF
  CWbemClass *v18; // [rsp+50h] [rbp+18h] BYREF

  v18 = this;
  (*(void (__fastcall **)(CWbemClass *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
  if ( !a3 )
  {
    MemLogObject = GetMemLogObject();
    v10 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_10;
    }
    v14 = 133;
    v15 = 2147749896LL;
    goto LABEL_17;
  }
  if ( a2 )
  {
    v16 = GetMemLogObject();
    v10 = -2147217400;
    CMemoryLog::Write(v16, -2147217400);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749896LL);
    }
    CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v18);
    return v10;
  }
  if ( (**((_BYTE **)this + 9) & 4) == 0 )
  {
    *a3 = 0;
    v13 = GetMemLogObject();
    v10 = -2147217376;
    CMemoryLog::Write(v13, -2147217376);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_10;
    }
    v14 = 135;
    v15 = 2147749920LL;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v11 + 2), v14, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, v15);
LABEL_10:
    (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
    return v10;
  }
  v17 = 0;
  v6 = CWbemClass::CreateDerivedClass(this, &v17);
  if ( v6 < 0
    || (v7 = v17,
        v6 = (**(__int64 (__fastcall ***)(struct CWbemClass *, GUID *, struct IWbemClassObject **))v17)(
               v17,
               &IID_IWbemClassObject,
               a3),
        (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v7 + 16LL))(v7),
        v6 < 0) )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, v6);
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      136,
      WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
      (unsigned int)v6);
  }
  (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180028e50  mov     [rsp+arg_8], rbx
0x180028e55  push    rsi
0x180028e56  push    rdi
0x180028e57  push    r14
0x180028e59  sub     rsp, 20h
0x180028e5d  mov     r14, r8
0x180028e60  mov     ebx, edx
0x180028e62  mov     rdi, rcx
0x180028e65  mov     [rsp+38h+arg_10], rcx
0x180028e6a  mov     rax, [rcx]
0x180028e6d  mov     edx, 1
0x180028e72  mov     rax, [rax+118h]
0x180028e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e7e  nop
0x180028e7f  test    r14, r14
0x180028e82  jz      loc_180028F34
0x180028e88  test    ebx, ebx
0x180028e8a  jnz     loc_18002900D
0x180028e90  mov     rax, [rdi+48h]
0x180028e94  test    byte ptr [rax], 4
0x180028e97  jz      loc_180028F90
0x180028e9d  mov     [rsp+38h+arg_0], 0
0x180028ea6  lea     rdx, [rsp+38h+arg_0]; struct CWbemClass **
0x180028eab  mov     rcx, rdi; this
0x180028eae  call    ?CreateDerivedClass@CWbemClass@@QEAAJPEAPEAV1@@Z; CWbemClass::CreateDerivedClass(CWbemClass * *)
0x180028eb3  mov     esi, eax
0x180028eb5  test    eax, eax
0x180028eb7  js      loc_180028F7A
0x180028ebd  mov     rbx, [rsp+38h+arg_0]
0x180028ec2  mov     rax, [rbx]
0x180028ec5  mov     r8, r14
0x180028ec8  lea     rdx, IID_IWbemClassObject
0x180028ecf  mov     rcx, rbx
0x180028ed2  mov     rax, [rax]
0x180028ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eda  mov     esi, eax
0x180028edc  mov     rax, [rbx]
0x180028edf  mov     rcx, rbx
0x180028ee2  mov     rax, [rax+10h]
0x180028ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eeb  test    esi, esi
0x180028eed  js      loc_180028F7A
0x180028ef3  lea     rax, WPP_GLOBAL_Control
0x180028efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f01  cmp     rcx, rax
0x180028f04  jz      short loc_180028F10
0x180028f06  test    byte ptr [rcx+1Ch], 1
0x180028f0a  jnz     loc_18002906D
0x180028f10  mov     rax, [rdi]
0x180028f13  xor     edx, edx
0x180028f15  mov     rcx, rdi
0x180028f18  mov     rax, [rax+120h]
0x180028f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f24  mov     eax, esi
0x180028f26  mov     rbx, [rsp+38h+arg_8]
0x180028f2b  add     rsp, 20h
0x180028f2f  pop     r14
0x180028f31  pop     rdi
0x180028f32  pop     rsi
0x180028f33  retn
0x180028f34  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028f3a  nop
0x180028f3b  mov     ebx, 80041008h
0x180028f40  mov     edx, ebx
0x180028f42  mov     rcx, rax
0x180028f45  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180028f4b  lea     rax, WPP_GLOBAL_Control
0x180028f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f59  cmp     rcx, rax
0x180028f5c  jnz     loc_180028FEC
0x180028f62  mov     rcx, [rdi]
0x180028f65  mov     rax, [rcx+120h]
0x180028f6c  xor     edx, edx
0x180028f6e  mov     rcx, rdi
0x180028f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f76  mov     eax, ebx
0x180028f78  jmp     short loc_180028F26
0x180028f7a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028f80  mov     edx, esi
0x180028f82  mov     rcx, rax
0x180028f85  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180028f8b  jmp     loc_180028EF3
0x180028f90  mov     qword ptr [r14], 0
0x180028f97  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028f9d  mov     ebx, 80041020h
0x180028fa2  mov     edx, ebx
0x180028fa4  mov     rcx, rax
0x180028fa7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180028fad  lea     rax, WPP_GLOBAL_Control
0x180028fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fbb  cmp     rcx, rax
0x180028fbe  jz      short loc_180028F62
0x180028fc0  test    byte ptr [rcx+1Ch], 1
0x180028fc4  jz      short loc_180028F62
0x180028fc6  cmp     byte ptr [rcx+19h], 2
0x180028fca  jb      short loc_180028F62
0x180028fcc  mov     edx, 87h
0x180028fd1  mov     r9d, 80041020h
0x180028fd7  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180028fde  mov     rcx, [rcx+10h]
0x180028fe2  call    WPP_SF_d
0x180028fe7  jmp     loc_180028F62
0x180028fec  test    byte ptr [rcx+1Ch], 1
0x180028ff0  jz      loc_180028F62
0x180028ff6  cmp     byte ptr [rcx+19h], 2
0x180028ffa  jb      loc_180028F62
0x180029000  mov     edx, 85h
0x180029005  mov     r9d, 80041008h
0x18002900b  jmp     short loc_180028FD7
0x18002900d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180029013  mov     ebx, 80041008h
0x180029018  mov     edx, ebx
0x18002901a  mov     rcx, rax
0x18002901d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180029023  lea     rax, WPP_GLOBAL_Control
0x18002902a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029031  cmp     rcx, rax
0x180029034  jz      short loc_18002905E
0x180029036  test    byte ptr [rcx+1Ch], 1
0x18002903a  jz      short loc_18002905E
0x18002903c  cmp     byte ptr [rcx+19h], 2
0x180029040  jb      short loc_18002905E
0x180029042  mov     edx, 86h
0x180029047  mov     r9d, 80041008h
0x18002904d  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180029054  mov     rcx, [rcx+10h]
0x180029058  call    WPP_SF_d
0x18002905d  nop
0x18002905e  lea     rcx, [rsp+38h+arg_10]; this
0x180029063  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180029068  jmp     loc_180028F76
0x18002906d  cmp     byte ptr [rcx+19h], 2
0x180029071  jb      loc_180028F10
0x180029077  mov     edx, 88h
0x18002907c  mov     r9d, esi
0x18002907f  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180029086  mov     rcx, [rcx+10h]
0x18002908a  call    WPP_SF_d
0x18002908f  jmp     loc_180028F10
```
