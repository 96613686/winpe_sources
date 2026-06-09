# CEnumDebugStackFrames::Next64(ulong,tagDebugStackFrameDescriptor64 *,ulong *)

- ea: `0x180055de0`
- end: `0x180055f5d`
- name: `?Next64@CEnumDebugStackFrames@@UEAAJKPEAUtagDebugStackFrameDescriptor64@@PEAK@Z`
- size: `381`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int, struct tagDebugStackFrameDescriptor64 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180055de0`
- `0x180055f64`
- `0x180056210`
- `0x180056250`
- `0x180080fd4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180055e35`
- `KERNEL32!GetCurrentThreadId` at `0x180055e35`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Next64(
        CEnumDebugStackFrames *this,
        int a2,
        struct tagDebugStackFrameDescriptor64 *a3,
        unsigned int *a4)
{
  int v6; // r14d
  int v8; // ebx
  __int64 result; // rax
  struct tagDebugStackFrameDescriptor64 *v10; // rbx
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
      *a4 = -858993459 * (((char *)v10 - (char *)a3) >> 3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180055de0  mov     [rsp-28h+arg_0], rbx
0x180055de5  mov     [rsp-28h+arg_8], rsi
0x180055dea  push    rbp
0x180055deb  push    rdi
0x180055dec  push    r12
0x180055dee  push    r14
0x180055df0  push    r15
0x180055df2  mov     rbp, rsp
0x180055df5  sub     rsp, 30h
0x180055df9  mov     [rbp+var_8], 0
0x180055e01  mov     rsi, r9
0x180055e04  mov     [rbp+arg_18], 0
0x180055e0c  mov     r15, r8
0x180055e0f  mov     [rbp+var_10], 0
0x180055e17  mov     r14d, edx
0x180055e1a  mov     rdi, rcx
0x180055e1d  test    r9, r9
0x180055e20  jz      short loc_180055E29
0x180055e22  mov     dword ptr [r9], 0
0x180055e29  test    r14d, r14d
0x180055e2c  jz      loc_180055F3D
0x180055e32  mov     ebx, [rcx+0Ch]
0x180055e35  call    cs:__imp_GetCurrentThreadId
0x180055e3b  cmp     eax, ebx
0x180055e3d  jz      short loc_180055E49
0x180055e3f  mov     eax, 8000FFFFh
0x180055e44  jmp     loc_180055F3F
0x180055e49  test    r15, r15
0x180055e4c  jz      loc_180055F56
0x180055e52  cmp     r14d, 1
0x180055e56  jz      short loc_180055E61
0x180055e58  test    rsi, rsi
0x180055e5b  jz      loc_180055F56
0x180055e61  mov     rcx, rdi; this
0x180055e64  call    ?NextCommon@CEnumDebugStackFrames@@AEAAJXZ; CEnumDebugStackFrames::NextCommon(void)
0x180055e69  test    eax, eax
0x180055e6b  jnz     loc_180055F3F
0x180055e71  mov     rax, [rdi+20h]
0x180055e75  mov     [r15], rax
0x180055e78  mov     rax, [rdi+20h]
0x180055e7c  lock inc dword ptr [rax+28h]
0x180055e80  mov     rcx, [rdi+20h]; this
0x180055e84  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180055e88  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180055e8c  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180055e91  mov     rax, [rbp+arg_18]
0x180055e95  lea     rbx, [r15+28h]
0x180055e99  mov     [r15+8], rax
0x180055e9d  mov     rax, [rbp+var_10]
0x180055ea1  mov     [r15+10h], rax
0x180055ea5  mov     qword ptr [r15+20h], 0
0x180055ead  dec     r14d
0x180055eb0  test    r14d, r14d
0x180055eb3  jz      short loc_180055F21
0x180055eb5  mov     rcx, [rdi+20h]; this
0x180055eb9  lea     rdx, [rbp+var_8]; struct CDebugStackFrame **
0x180055ebd  call    ?GetNextFrame@CDebugStackFrame@@QEAAJPEAPEAV1@@Z; CDebugStackFrame::GetNextFrame(CDebugStackFrame * *)
0x180055ec2  mov     rcx, [rdi+20h]; this
0x180055ec6  mov     r12d, eax
0x180055ec9  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x180055ece  mov     rax, [rbp+var_8]
0x180055ed2  mov     [rdi+20h], rax
0x180055ed6  test    r12d, r12d
0x180055ed9  js      short loc_180055F1D
0x180055edb  jnz     short loc_180055F17
0x180055edd  mov     [rbx], rax
0x180055ee0  mov     rax, [rdi+20h]
0x180055ee4  lock inc dword ptr [rax+28h]
0x180055ee8  mov     rcx, [rdi+20h]; this
0x180055eec  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180055ef0  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180055ef4  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180055ef9  mov     rax, [rbp+arg_18]
0x180055efd  mov     [rbx+8], rax
0x180055f01  mov     rax, [rbp+var_10]
0x180055f05  mov     [rbx+10h], rax
0x180055f09  mov     qword ptr [rbx+20h], 0
0x180055f11  add     rbx, 28h ; '('
0x180055f15  jmp     short loc_180055EAD
0x180055f17  or      dword ptr [rdi+1Ch], 1
0x180055f1b  jmp     short loc_180055F21
0x180055f1d  or      dword ptr [rdi+1Ch], 2
0x180055f21  test    rsi, rsi
0x180055f24  jz      short loc_180055F3D
0x180055f26  sub     rbx, r15
0x180055f29  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180055f33  sar     rbx, 3
0x180055f37  imul    rbx, rax
0x180055f3b  mov     [rsi], ebx
0x180055f3d  xor     eax, eax
0x180055f3f  mov     rbx, [rsp+30h+arg_0]
0x180055f44  mov     rsi, [rsp+30h+arg_8]
0x180055f49  add     rsp, 30h
0x180055f4d  pop     r15
0x180055f4f  pop     r14
0x180055f51  pop     r12
0x180055f53  pop     rdi
0x180055f54  pop     rbp
0x180055f55  retn
0x180055f56  mov     eax, 80004003h
0x180055f5b  jmp     short loc_180055F3F
```
