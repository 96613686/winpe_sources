# CEnumDebugStackFrames::Next(ulong,tagDebugStackFrameDescriptor *,ulong *)

- ea: `0x1800560a0`
- end: `0x180056209`
- name: `?Next@CEnumDebugStackFrames@@UEAAJKPEAUtagDebugStackFrameDescriptor@@PEAK@Z`
- size: `361`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int, struct tagDebugStackFrameDescriptor *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180055f64`
- `0x1800560a0`
- `0x180056210`
- `0x180056250`
- `0x180080fd4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800560f5`
- `KERNEL32!GetCurrentThreadId` at `0x1800560f5`

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
0x1800560a0  mov     [rsp-28h+arg_0], rbx
0x1800560a5  mov     [rsp-28h+arg_8], rsi
0x1800560aa  push    rbp
0x1800560ab  push    rdi
0x1800560ac  push    r12
0x1800560ae  push    r14
0x1800560b0  push    r15
0x1800560b2  mov     rbp, rsp
0x1800560b5  sub     rsp, 30h
0x1800560b9  mov     [rbp+var_8], 0
0x1800560c1  mov     rsi, r9
0x1800560c4  mov     [rbp+arg_18], 0
0x1800560cc  mov     r15, r8
0x1800560cf  mov     [rbp+var_10], 0
0x1800560d7  mov     r14d, edx
0x1800560da  mov     rdi, rcx
0x1800560dd  test    r9, r9
0x1800560e0  jz      short loc_1800560E9
0x1800560e2  mov     dword ptr [r9], 0
0x1800560e9  test    r14d, r14d
0x1800560ec  jz      loc_1800561E9
0x1800560f2  mov     ebx, [rcx+0Ch]
0x1800560f5  call    cs:__imp_GetCurrentThreadId
0x1800560fb  cmp     eax, ebx
0x1800560fd  jz      short loc_180056109
0x1800560ff  mov     eax, 8000FFFFh
0x180056104  jmp     loc_1800561EB
0x180056109  test    r15, r15
0x18005610c  jz      loc_180056202
0x180056112  cmp     r14d, 1
0x180056116  jz      short loc_180056121
0x180056118  test    rsi, rsi
0x18005611b  jz      loc_180056202
0x180056121  mov     rcx, rdi; this
0x180056124  call    ?NextCommon@CEnumDebugStackFrames@@AEAAJXZ; CEnumDebugStackFrames::NextCommon(void)
0x180056129  test    eax, eax
0x18005612b  jnz     loc_1800561EB
0x180056131  mov     rax, [rdi+20h]
0x180056135  mov     [r15], rax
0x180056138  mov     rax, [rdi+20h]
0x18005613c  lock inc dword ptr [rax+28h]
0x180056140  mov     rcx, [rdi+20h]; this
0x180056144  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180056148  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x18005614c  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180056151  mov     eax, dword ptr [rbp+arg_18]
0x180056154  lea     rbx, [r15+20h]
0x180056158  mov     [r15+8], eax
0x18005615c  mov     eax, dword ptr [rbp+var_10]
0x18005615f  mov     [r15+0Ch], eax
0x180056163  mov     qword ptr [r15+18h], 0
0x18005616b  dec     r14d
0x18005616e  test    r14d, r14d
0x180056171  jz      short loc_1800561DB
0x180056173  mov     rcx, [rdi+20h]; this
0x180056177  lea     rdx, [rbp+var_8]; struct CDebugStackFrame **
0x18005617b  call    ?GetNextFrame@CDebugStackFrame@@QEAAJPEAPEAV1@@Z; CDebugStackFrame::GetNextFrame(CDebugStackFrame * *)
0x180056180  mov     rcx, [rdi+20h]; this
0x180056184  mov     r12d, eax
0x180056187  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x18005618c  mov     rax, [rbp+var_8]
0x180056190  mov     [rdi+20h], rax
0x180056194  test    r12d, r12d
0x180056197  js      short loc_1800561D7
0x180056199  jnz     short loc_1800561D1
0x18005619b  mov     [rbx], rax
0x18005619e  mov     rax, [rdi+20h]
0x1800561a2  lock inc dword ptr [rax+28h]
0x1800561a6  mov     rcx, [rdi+20h]; this
0x1800561aa  lea     r8, [rbp+var_10]; unsigned __int64 *
0x1800561ae  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x1800561b2  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x1800561b7  mov     eax, dword ptr [rbp+arg_18]
0x1800561ba  mov     [rbx+8], eax
0x1800561bd  mov     eax, dword ptr [rbp+var_10]
0x1800561c0  mov     [rbx+0Ch], eax
0x1800561c3  mov     qword ptr [rbx+18h], 0
0x1800561cb  add     rbx, 20h ; ' '
0x1800561cf  jmp     short loc_18005616B
0x1800561d1  or      dword ptr [rdi+1Ch], 1
0x1800561d5  jmp     short loc_1800561DB
0x1800561d7  or      dword ptr [rdi+1Ch], 2
0x1800561db  test    rsi, rsi
0x1800561de  jz      short loc_1800561E9
0x1800561e0  sub     rbx, r15
0x1800561e3  sar     rbx, 5
0x1800561e7  mov     [rsi], ebx
0x1800561e9  xor     eax, eax
0x1800561eb  mov     rbx, [rsp+30h+arg_0]
0x1800561f0  mov     rsi, [rsp+30h+arg_8]
0x1800561f5  add     rsp, 30h
0x1800561f9  pop     r15
0x1800561fb  pop     r14
0x1800561fd  pop     r12
0x1800561ff  pop     rdi
0x180056200  pop     rbp
0x180056201  retn
0x180056202  mov     eax, 80004003h
0x180056207  jmp     short loc_1800561EB
```
