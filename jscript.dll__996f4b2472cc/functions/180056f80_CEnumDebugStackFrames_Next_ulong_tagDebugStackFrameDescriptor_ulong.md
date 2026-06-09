# CEnumDebugStackFrames::Next(ulong,tagDebugStackFrameDescriptor *,ulong *)

- ea: `0x180056f80`
- end: `0x1800570f0`
- name: `?Next@CEnumDebugStackFrames@@UEAAJKPEAUtagDebugStackFrameDescriptor@@PEAK@Z`
- size: `368`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int, struct tagDebugStackFrameDescriptor *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180056e4c`
- `0x180056f80`
- `0x180057100`
- `0x180057140`
- `0x180082ba8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180056fd5`
- `KERNEL32!GetCurrentThreadId` at `0x180056fd5`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Next(
        CEnumDebugStackFrames *this,
        int a2,
        struct tagDebugStackFrameDescriptor *a3,
        unsigned int *a4)
{
  int v6; // r14d
  int v8; // ebx
  __int64 result; // rax
  struct tagDebugStackFrameDescriptor *v10; // rbx
  int NextFrame; // r12d
  struct CDebugStackFrame *v12; // rax
  unsigned __int64 v13; // [rsp+20h] [rbp-10h] BYREF
  struct CDebugStackFrame *v14; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int64 v15; // [rsp+78h] [rbp+48h] BYREF

  v14 = 0;
  v15 = 0;
  v13 = 0;
  v6 = a2;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    return 0;
  v8 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v8 )
    return 2147549183LL;
  if ( !a3 || v6 != 1 && !a4 )
    return 2147500035LL;
  result = CEnumDebugStackFrames::NextCommon(this);
  if ( !(_DWORD)result )
  {
    a3->pdsf = (IDebugStackFrame *)*((_QWORD *)this + 4);
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 40LL));
    CDebugStackFrame::GetPhysicalStackRange(*((CDebugStackFrame **)this + 4), &v15, &v13);
    v10 = a3 + 1;
    a3->dwMin = v15;
    a3->dwLim = v13;
    a3->punkFinal = 0;
    while ( --v6 )
    {
      NextFrame = CDebugStackFrame::GetNextFrame(*((CDebugStackFrame **)this + 4), &v14);
      CDebugStackFrame::Release(*((CDebugStackFrame **)this + 4));
      v12 = v14;
      *((_QWORD *)this + 4) = v14;
      if ( NextFrame < 0 )
      {
        *((_DWORD *)this + 7) |= 2u;
        break;
      }
      if ( NextFrame )
      {
        *((_DWORD *)this + 7) |= 1u;
        break;
      }
      v10->pdsf = (IDebugStackFrame *)v12;
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 40LL));
      CDebugStackFrame::GetPhysicalStackRange(*((CDebugStackFrame **)this + 4), &v15, &v13);
      v10->dwMin = v15;
      v10->dwLim = v13;
      v10->punkFinal = 0;
      ++v10;
    }
    if ( a4 )
      *a4 = v10 - a3;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180056f80  mov     [rsp-28h+arg_0], rbx
0x180056f85  mov     [rsp-28h+arg_8], rsi
0x180056f8a  push    rbp
0x180056f8b  push    rdi
0x180056f8c  push    r12
0x180056f8e  push    r14
0x180056f90  push    r15
0x180056f92  mov     rbp, rsp
0x180056f95  sub     rsp, 30h
0x180056f99  mov     [rbp+var_8], 0
0x180056fa1  mov     rsi, r9
0x180056fa4  mov     [rbp+arg_18], 0
0x180056fac  mov     r15, r8
0x180056faf  mov     [rbp+var_10], 0
0x180056fb7  mov     r14d, edx
0x180056fba  mov     rdi, rcx
0x180056fbd  test    r9, r9
0x180056fc0  jz      short loc_180056FC9
0x180056fc2  mov     dword ptr [r9], 0
0x180056fc9  test    r14d, r14d
0x180056fcc  jz      loc_1800570CF
0x180056fd2  mov     ebx, [rcx+0Ch]
0x180056fd5  call    cs:__imp_GetCurrentThreadId
0x180056fdc  nop     dword ptr [rax+rax+00h]
0x180056fe1  cmp     eax, ebx
0x180056fe3  jz      short loc_180056FEF
0x180056fe5  mov     eax, 8000FFFFh
0x180056fea  jmp     loc_1800570D1
0x180056fef  test    r15, r15
0x180056ff2  jz      loc_1800570E9
0x180056ff8  cmp     r14d, 1
0x180056ffc  jz      short loc_180057007
0x180056ffe  test    rsi, rsi
0x180057001  jz      loc_1800570E9
0x180057007  mov     rcx, rdi; this
0x18005700a  call    ?NextCommon@CEnumDebugStackFrames@@AEAAJXZ; CEnumDebugStackFrames::NextCommon(void)
0x18005700f  test    eax, eax
0x180057011  jnz     loc_1800570D1
0x180057017  mov     rax, [rdi+20h]
0x18005701b  mov     [r15], rax
0x18005701e  mov     rax, [rdi+20h]
0x180057022  lock inc dword ptr [rax+28h]
0x180057026  mov     rcx, [rdi+20h]; this
0x18005702a  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18005702e  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180057032  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180057037  mov     eax, dword ptr [rbp+arg_18]
0x18005703a  lea     rbx, [r15+20h]
0x18005703e  mov     [r15+8], eax
0x180057042  mov     eax, dword ptr [rbp+var_10]
0x180057045  mov     [r15+0Ch], eax
0x180057049  mov     qword ptr [r15+18h], 0
0x180057051  dec     r14d
0x180057054  test    r14d, r14d
0x180057057  jz      short loc_1800570C1
0x180057059  mov     rcx, [rdi+20h]; this
0x18005705d  lea     rdx, [rbp+var_8]; struct CDebugStackFrame **
0x180057061  call    ?GetNextFrame@CDebugStackFrame@@QEAAJPEAPEAV1@@Z; CDebugStackFrame::GetNextFrame(CDebugStackFrame * *)
0x180057066  mov     rcx, [rdi+20h]; this
0x18005706a  mov     r12d, eax
0x18005706d  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x180057072  mov     rax, [rbp+var_8]
0x180057076  mov     [rdi+20h], rax
0x18005707a  test    r12d, r12d
0x18005707d  js      short loc_1800570BD
0x18005707f  jnz     short loc_1800570B7
0x180057081  mov     [rbx], rax
0x180057084  mov     rax, [rdi+20h]
0x180057088  lock inc dword ptr [rax+28h]
0x18005708c  mov     rcx, [rdi+20h]; this
0x180057090  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180057094  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180057098  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x18005709d  mov     eax, dword ptr [rbp+arg_18]
0x1800570a0  mov     [rbx+8], eax
0x1800570a3  mov     eax, dword ptr [rbp+var_10]
0x1800570a6  mov     [rbx+0Ch], eax
0x1800570a9  mov     qword ptr [rbx+18h], 0
0x1800570b1  add     rbx, 20h ; ' '
0x1800570b5  jmp     short loc_180057051
0x1800570b7  or      dword ptr [rdi+1Ch], 1
0x1800570bb  jmp     short loc_1800570C1
0x1800570bd  or      dword ptr [rdi+1Ch], 2
0x1800570c1  test    rsi, rsi
0x1800570c4  jz      short loc_1800570CF
0x1800570c6  sub     rbx, r15
0x1800570c9  sar     rbx, 5
0x1800570cd  mov     [rsi], ebx
0x1800570cf  xor     eax, eax
0x1800570d1  mov     rbx, [rsp+30h+arg_0]
0x1800570d6  mov     rsi, [rsp+30h+arg_8]
0x1800570db  add     rsp, 30h
0x1800570df  pop     r15
0x1800570e1  pop     r14
0x1800570e3  pop     r12
0x1800570e5  pop     rdi
0x1800570e6  pop     rbp
0x1800570e7  retn
0x1800570e9  mov     eax, 80004003h
0x1800570ee  jmp     short loc_1800570D1
```
