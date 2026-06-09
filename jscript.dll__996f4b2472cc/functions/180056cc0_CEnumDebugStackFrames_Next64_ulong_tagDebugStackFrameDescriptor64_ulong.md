# CEnumDebugStackFrames::Next64(ulong,tagDebugStackFrameDescriptor64 *,ulong *)

- ea: `0x180056cc0`
- end: `0x180056e44`
- name: `?Next64@CEnumDebugStackFrames@@UEAAJKPEAUtagDebugStackFrameDescriptor64@@PEAK@Z`
- size: `388`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int, struct tagDebugStackFrameDescriptor64 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180056cc0`
- `0x180056e4c`
- `0x180057100`
- `0x180057140`
- `0x180082ba8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180056d15`
- `KERNEL32!GetCurrentThreadId` at `0x180056d15`

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
0x180056cc0  mov     [rsp-28h+arg_0], rbx
0x180056cc5  mov     [rsp-28h+arg_8], rsi
0x180056cca  push    rbp
0x180056ccb  push    rdi
0x180056ccc  push    r12
0x180056cce  push    r14
0x180056cd0  push    r15
0x180056cd2  mov     rbp, rsp
0x180056cd5  sub     rsp, 30h
0x180056cd9  mov     [rbp+var_8], 0
0x180056ce1  mov     rsi, r9
0x180056ce4  mov     [rbp+arg_18], 0
0x180056cec  mov     r15, r8
0x180056cef  mov     [rbp+var_10], 0
0x180056cf7  mov     r14d, edx
0x180056cfa  mov     rdi, rcx
0x180056cfd  test    r9, r9
0x180056d00  jz      short loc_180056D09
0x180056d02  mov     dword ptr [r9], 0
0x180056d09  test    r14d, r14d
0x180056d0c  jz      loc_180056E23
0x180056d12  mov     ebx, [rcx+0Ch]
0x180056d15  call    cs:__imp_GetCurrentThreadId
0x180056d1c  nop     dword ptr [rax+rax+00h]
0x180056d21  cmp     eax, ebx
0x180056d23  jz      short loc_180056D2F
0x180056d25  mov     eax, 8000FFFFh
0x180056d2a  jmp     loc_180056E25
0x180056d2f  test    r15, r15
0x180056d32  jz      loc_180056E3D
0x180056d38  cmp     r14d, 1
0x180056d3c  jz      short loc_180056D47
0x180056d3e  test    rsi, rsi
0x180056d41  jz      loc_180056E3D
0x180056d47  mov     rcx, rdi; this
0x180056d4a  call    ?NextCommon@CEnumDebugStackFrames@@AEAAJXZ; CEnumDebugStackFrames::NextCommon(void)
0x180056d4f  test    eax, eax
0x180056d51  jnz     loc_180056E25
0x180056d57  mov     rax, [rdi+20h]
0x180056d5b  mov     [r15], rax
0x180056d5e  mov     rax, [rdi+20h]
0x180056d62  lock inc dword ptr [rax+28h]
0x180056d66  mov     rcx, [rdi+20h]; this
0x180056d6a  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180056d6e  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180056d72  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180056d77  mov     rax, [rbp+arg_18]
0x180056d7b  lea     rbx, [r15+28h]
0x180056d7f  mov     [r15+8], rax
0x180056d83  mov     rax, [rbp+var_10]
0x180056d87  mov     [r15+10h], rax
0x180056d8b  mov     qword ptr [r15+20h], 0
0x180056d93  dec     r14d
0x180056d96  test    r14d, r14d
0x180056d99  jz      short loc_180056E07
0x180056d9b  mov     rcx, [rdi+20h]; this
0x180056d9f  lea     rdx, [rbp+var_8]; struct CDebugStackFrame **
0x180056da3  call    ?GetNextFrame@CDebugStackFrame@@QEAAJPEAPEAV1@@Z; CDebugStackFrame::GetNextFrame(CDebugStackFrame * *)
0x180056da8  mov     rcx, [rdi+20h]; this
0x180056dac  mov     r12d, eax
0x180056daf  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x180056db4  mov     rax, [rbp+var_8]
0x180056db8  mov     [rdi+20h], rax
0x180056dbc  test    r12d, r12d
0x180056dbf  js      short loc_180056E03
0x180056dc1  jnz     short loc_180056DFD
0x180056dc3  mov     [rbx], rax
0x180056dc6  mov     rax, [rdi+20h]
0x180056dca  lock inc dword ptr [rax+28h]
0x180056dce  mov     rcx, [rdi+20h]; this
0x180056dd2  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180056dd6  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180056dda  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180056ddf  mov     rax, [rbp+arg_18]
0x180056de3  mov     [rbx+8], rax
0x180056de7  mov     rax, [rbp+var_10]
0x180056deb  mov     [rbx+10h], rax
0x180056def  mov     qword ptr [rbx+20h], 0
0x180056df7  add     rbx, 28h ; '('
0x180056dfb  jmp     short loc_180056D93
0x180056dfd  or      dword ptr [rdi+1Ch], 1
0x180056e01  jmp     short loc_180056E07
0x180056e03  or      dword ptr [rdi+1Ch], 2
0x180056e07  test    rsi, rsi
0x180056e0a  jz      short loc_180056E23
0x180056e0c  sub     rbx, r15
0x180056e0f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180056e19  sar     rbx, 3
0x180056e1d  imul    rbx, rax
0x180056e21  mov     [rsi], ebx
0x180056e23  xor     eax, eax
0x180056e25  mov     rbx, [rsp+30h+arg_0]
0x180056e2a  mov     rsi, [rsp+30h+arg_8]
0x180056e2f  add     rsp, 30h
0x180056e33  pop     r15
0x180056e35  pop     r14
0x180056e37  pop     r12
0x180056e39  pop     rdi
0x180056e3a  pop     rbp
0x180056e3b  retn
0x180056e3d  mov     eax, 80004003h
0x180056e42  jmp     short loc_180056E25
```
