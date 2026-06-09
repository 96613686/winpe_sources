# CUniversalRefresher::XConfigure::Remove(long,long)

- ea: `0x180047870`
- end: `0x1800479f7`
- name: `?Remove@XConfigure@CUniversalRefresher@@UEAAJJJ@Z`
- size: `391`
- prototype: `int(CUniversalRefresher::XConfigure *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180037120`
- `0x180047654`
- `0x180047870`
- `0x180048df0`
- `0x180048f08`
- `0x180048f30`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180047906`
- `wbemcomn!GetMemLogObject` at `0x180047958`
- `wbemcomn!GetMemLogObject` at `0x1800479b9`
- `wbemcomn!GetMemLogObject` at `0x180047906`
- `wbemcomn!GetMemLogObject` at `0x180047958`
- `wbemcomn!GetMemLogObject` at `0x1800479b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047916`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047969`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800479c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047916`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047969`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800479c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUniversalRefresher::XConfigure::Remove(CUniversalRefresher::XConfigure *this, int a2, int a3)
{
  int v6; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v9; // rax
  CMemoryLog *v10; // rax
  __int64 v11; // [rsp+20h] [rbp-38h] BYREF

  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    MemLogObject = GetMemLogObject();
    v6 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749896LL);
    }
  }
  else
  {
    v11 = *((_QWORD *)this + 1) + 448LL;
    if ( (unsigned int)CSharedLock::Lock((CSharedLock *)(v11 + 16), 0x2710u) )
    {
      v6 = CUniversalRefresher::Remove(*((CUniversalRefresher **)this + 1), a2, a3);
      if ( v6 < 0 )
      {
        v10 = GetMemLogObject();
        CMemoryLog::Write(v10, v6);
      }
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
          (unsigned int)v6);
      }
      CSharedLock::Unlock((CSharedLock *)(v11 + 16));
    }
    else
    {
      v9 = GetMemLogObject();
      v6 = -2147217321;
      CMemoryLog::Write(v9, -2147217321);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749975LL);
      }
      CHiPerfLockAccess::~CHiPerfLockAccess((CHiPerfLockAccess *)&v11);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180047870  push    rbx
0x180047872  push    rbp
0x180047873  push    rsi
0x180047874  push    rdi
0x180047875  sub     rsp, 38h
0x180047879  mov     ebx, r8d
0x18004787c  mov     ebp, edx
0x18004787e  mov     rdi, rcx
0x180047881  test    r8d, 0FFFFFFFEh
0x180047888  jnz     short loc_180047906
0x18004788a  mov     rax, [rcx+8]
0x18004788e  add     rax, 1C0h
0x180047894  mov     [rsp+58h+var_38], rax
0x180047899  mov     [rsp+58h+var_30], 0
0x1800478a1  lea     rsi, [rax+10h]
0x1800478a5  mov     edx, 2710h; unsigned int
0x1800478aa  mov     rcx, rsi; this
0x1800478ad  call    ?Lock@CSharedLock@@QEAAHK@Z; CSharedLock::Lock(ulong)
0x1800478b2  mov     [rsp+58h+var_30], eax
0x1800478b6  test    eax, eax
0x1800478b8  jz      loc_180047958
0x1800478be  mov     r8d, ebx; int
0x1800478c1  mov     edx, ebp; int
0x1800478c3  mov     rcx, [rdi+8]; this
0x1800478c7  call    ?Remove@CUniversalRefresher@@IEAAJJJ@Z; CUniversalRefresher::Remove(long,long)
0x1800478cc  mov     ebx, eax
0x1800478ce  test    eax, eax
0x1800478d0  js      loc_1800479B9
0x1800478d6  lea     rax, WPP_GLOBAL_Control
0x1800478dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800478e4  cmp     rcx, rax
0x1800478e7  jz      short loc_1800478F3
0x1800478e9  test    byte ptr [rcx+1Ch], 1
0x1800478ed  jnz     loc_1800479CF
0x1800478f3  mov     rcx, rsi; this
0x1800478f6  call    ?Unlock@CSharedLock@@QEAAHXZ; CSharedLock::Unlock(void)
0x1800478fb  mov     eax, ebx
0x1800478fd  add     rsp, 38h
0x180047901  pop     rdi
0x180047902  pop     rsi
0x180047903  pop     rbp
0x180047904  pop     rbx
0x180047905  retn
0x180047906  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004790c  mov     ebx, 80041008h
0x180047911  mov     edx, ebx
0x180047913  mov     rcx, rax
0x180047916  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004791c  lea     rax, WPP_GLOBAL_Control
0x180047923  mov     rcx, cs:WPP_GLOBAL_Control
0x18004792a  cmp     rcx, rax
0x18004792d  jz      short loc_1800478FB
0x18004792f  test    byte ptr [rcx+1Ch], 1
0x180047933  jz      short loc_1800478FB
0x180047935  cmp     byte ptr [rcx+19h], 2
0x180047939  jb      short loc_1800478FB
0x18004793b  mov     edx, 17h
0x180047940  mov     r9d, 80041008h
0x180047946  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004794d  mov     rcx, [rcx+10h]
0x180047951  call    WPP_SF_d
0x180047956  jmp     short loc_1800478FB
0x180047958  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004795e  nop
0x18004795f  mov     ebx, 80041057h
0x180047964  mov     edx, ebx
0x180047966  mov     rcx, rax
0x180047969  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004796f  lea     rax, WPP_GLOBAL_Control
0x180047976  mov     rcx, cs:WPP_GLOBAL_Control
0x18004797d  cmp     rcx, rax
0x180047980  jz      short loc_1800479AA
0x180047982  test    byte ptr [rcx+1Ch], 1
0x180047986  jz      short loc_1800479AA
0x180047988  cmp     byte ptr [rcx+19h], 2
0x18004798c  jb      short loc_1800479AA
0x18004798e  mov     edx, 18h
0x180047993  mov     r9d, 80041057h
0x180047999  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800479a0  mov     rcx, [rcx+10h]
0x1800479a4  call    WPP_SF_d
0x1800479a9  nop
0x1800479aa  lea     rcx, [rsp+58h+var_38]; this
0x1800479af  call    ??1CHiPerfLockAccess@@QEAA@XZ; CHiPerfLockAccess::~CHiPerfLockAccess(void)
0x1800479b4  jmp     loc_1800478FB
0x1800479b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800479bf  mov     edx, ebx
0x1800479c1  mov     rcx, rax
0x1800479c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800479ca  jmp     loc_1800478D6
0x1800479cf  cmp     byte ptr [rcx+19h], 2
0x1800479d3  jb      loc_1800478F3
0x1800479d9  mov     edx, 19h
0x1800479de  mov     r9d, ebx
0x1800479e1  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800479e8  mov     rcx, [rcx+10h]
0x1800479ec  call    WPP_SF_d
0x1800479f1  jmp     loc_1800478F3
```
