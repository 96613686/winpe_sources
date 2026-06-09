# CHiPerfEnum::GetObjects(long,ulong,IWbemObjectAccess * *,ulong *)

- ea: `0x1800488c0`
- end: `0x180048a6e`
- name: `?GetObjects@CHiPerfEnum@@UEAAJJKPEAPEAUIWbemObjectAccess@@PEAK@Z`
- size: `430`
- prototype: `__int64 __fastcall(CHiPerfEnum *__hidden this, int, unsigned int, struct IWbemObjectAccess **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x1800488c0`
- `0x180048df0`
- `0x180048f08`
- `0x180048f30`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180048937`
- `wbemcomn!GetMemLogObject` at `0x1800489d1`
- `wbemcomn!GetMemLogObject` at `0x180048937`
- `wbemcomn!GetMemLogObject` at `0x1800489d1`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180048914`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180048927`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180048985`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800489c2`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180048914`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180048927`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180048985`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800489c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048942`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800489e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048942`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800489e1`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180048999`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180048999`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHiPerfEnum::GetObjects(
        CHiPerfEnum *this,
        int a2,
        unsigned int a3,
        struct IWbemObjectAccess **a4,
        unsigned int *a5)
{
  CSharedLock *v8; // rbp
  CFlexArray *v9; // rsi
  unsigned int v10; // ebx
  CMemoryLog *v11; // rax
  __int64 i; // rdi
  struct IWbemObjectAccess ***v14; // rax
  struct IWbemObjectAccess **v15; // r15
  struct IWbemObjectAccess *v16; // rcx
  CMemoryLog *MemLogObject; // rax
  char *v18; // [rsp+20h] [rbp-48h] BYREF

  if ( a2 )
  {
    MemLogObject = GetMemLogObject();
    v10 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c8bd429c931931aae9fbbec477661e47_Traceguids, 2147749896LL);
    }
    return v10;
  }
  v18 = (char *)this + 248;
  v8 = (CHiPerfEnum *)((char *)this + 264);
  if ( (unsigned int)CSharedLock::Lock((CHiPerfEnum *)((char *)this + 264), 0x2710u) )
  {
    v9 = (CHiPerfEnum *)((char *)this + 24);
    *a5 = CFlexArray::Size(v9);
    if ( a3 >= CFlexArray::Size(v9) )
    {
      v10 = 0;
      for ( i = 0; (unsigned int)i < CFlexArray::Size(v9); i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= a3 )
          break;
        v14 = (struct IWbemObjectAccess ***)CFlexArray::operator[](v9, (unsigned int)i);
        v15 = *v14;
        v16 = **v14;
        if ( v16 )
          ((void (__fastcall *)(struct IWbemObjectAccess *))v16->lpVtbl->AddRef)(v16);
        a4[i] = *v15;
      }
    }
    else
    {
      v10 = -2147217348;
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, -2147217348);
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_c8bd429c931931aae9fbbec477661e47_Traceguids, v10);
    }
    CSharedLock::Unlock(v8);
    return v10;
  }
  CHiPerfLockAccess::~CHiPerfLockAccess((CHiPerfLockAccess *)&v18);
  return 262148;
}

```

## disassembly

```asm
0x1800488c0  push    rbx
0x1800488c2  push    rbp
0x1800488c3  push    rsi
0x1800488c4  push    rdi
0x1800488c5  push    r12
0x1800488c7  push    r14
0x1800488c9  push    r15
0x1800488cb  sub     rsp, 30h
0x1800488cf  mov     r12, r9
0x1800488d2  mov     r14d, r8d
0x1800488d5  mov     rsi, rcx
0x1800488d8  test    edx, edx
0x1800488da  jnz     loc_1800489D1
0x1800488e0  lea     rax, [rcx+0F8h]
0x1800488e7  mov     [rsp+68h+var_48], rax
0x1800488ec  mov     [rsp+68h+var_40], edx
0x1800488f0  lea     rbp, [rax+10h]
0x1800488f4  mov     edx, 2710h; unsigned int
0x1800488f9  mov     rcx, rbp; this
0x1800488fc  call    ?Lock@CSharedLock@@QEAAHK@Z; CSharedLock::Lock(ulong)
0x180048901  mov     [rsp+68h+var_40], eax
0x180048905  test    eax, eax
0x180048907  jz      loc_180048A32
0x18004890d  add     rsi, 18h
0x180048911  mov     rcx, rsi
0x180048914  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18004891a  mov     rcx, [rsp+68h+arg_20]
0x180048922  mov     [rcx], eax
0x180048924  mov     rcx, rsi
0x180048927  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18004892d  cmp     r14d, eax
0x180048930  jnb     short loc_18004897E
0x180048932  mov     ebx, 8004103Ch
0x180048937  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004893d  mov     edx, ebx
0x18004893f  mov     rcx, rax
0x180048942  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048948  lea     rax, WPP_GLOBAL_Control
0x18004894f  mov     rcx, cs:WPP_GLOBAL_Control
0x180048956  cmp     rcx, rax
0x180048959  jz      short loc_180048965
0x18004895b  test    byte ptr [rcx+1Ch], 1
0x18004895f  jnz     loc_180048A46
0x180048965  mov     rcx, rbp; this
0x180048968  call    ?Unlock@CSharedLock@@QEAAHXZ; CSharedLock::Unlock(void)
0x18004896d  mov     eax, ebx
0x18004896f  add     rsp, 30h
0x180048973  pop     r15
0x180048975  pop     r14
0x180048977  pop     r12
0x180048979  pop     rdi
0x18004897a  pop     rsi
0x18004897b  pop     rbp
0x18004897c  pop     rbx
0x18004897d  retn
0x18004897e  xor     ebx, ebx
0x180048980  xor     edi, edi
0x180048982  mov     rcx, rsi
0x180048985  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18004898b  test    eax, eax
0x18004898d  jz      short loc_180048948
0x18004898f  cmp     edi, r14d
0x180048992  jnb     short loc_180048948
0x180048994  mov     edx, edi
0x180048996  mov     rcx, rsi
0x180048999  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x18004899f  mov     r15, [rax]
0x1800489a2  mov     rcx, [r15]
0x1800489a5  test    rcx, rcx
0x1800489a8  jz      short loc_1800489B6
0x1800489aa  mov     rax, [rcx]
0x1800489ad  mov     rax, [rax+8]
0x1800489b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489b6  mov     rax, [r15]
0x1800489b9  mov     [r12+rdi*8], rax
0x1800489bd  inc     edi
0x1800489bf  mov     rcx, rsi
0x1800489c2  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800489c8  cmp     edi, eax
0x1800489ca  jb      short loc_18004898F
0x1800489cc  jmp     loc_180048948
0x1800489d1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800489d7  mov     ebx, 80041008h
0x1800489dc  mov     edx, ebx
0x1800489de  mov     rcx, rax
0x1800489e1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800489e7  lea     rax, WPP_GLOBAL_Control
0x1800489ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800489f5  cmp     rcx, rax
0x1800489f8  jz      loc_18004896D
0x1800489fe  test    byte ptr [rcx+1Ch], 1
0x180048a02  jz      loc_18004896D
0x180048a08  cmp     byte ptr [rcx+19h], 2
0x180048a0c  jb      loc_18004896D
0x180048a12  mov     edx, 0Eh
0x180048a17  mov     r9d, 80041008h
0x180048a1d  lea     r8, WPP_c8bd429c931931aae9fbbec477661e47_Traceguids
0x180048a24  mov     rcx, [rcx+10h]
0x180048a28  call    WPP_SF_d
0x180048a2d  jmp     loc_18004896D
0x180048a32  lea     rcx, [rsp+68h+var_48]; this
0x180048a37  call    ??1CHiPerfLockAccess@@QEAA@XZ; CHiPerfLockAccess::~CHiPerfLockAccess(void)
0x180048a3c  mov     eax, 40004h
0x180048a41  jmp     loc_18004896F
0x180048a46  cmp     byte ptr [rcx+19h], 2
0x180048a4a  jb      loc_180048965
0x180048a50  mov     edx, 0Fh
0x180048a55  mov     r9d, ebx
0x180048a58  lea     r8, WPP_c8bd429c931931aae9fbbec477661e47_Traceguids
0x180048a5f  mov     rcx, [rcx+10h]
0x180048a63  call    WPP_SF_d
0x180048a68  jmp     loc_180048965
```
