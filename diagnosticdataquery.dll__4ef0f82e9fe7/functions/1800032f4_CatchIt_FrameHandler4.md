# CatchIt___FrameHandler4_

- ea: `0x1800032f4`
- end: `0x1800033d2`
- name: `CatchIt___FrameHandler4_`
- size: `222`
- prototype: `void __fastcall(struct EHExceptionRecord *, unsigned __int64 *, struct _CONTEXT *, struct _xDISPATCHER_CONTEXT *, struct FH4::FuncInfo4 *, struct FH4::HandlerType4 *, __int64, int *, int, int, int, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800033d8`
- `0x1800038f4`

## callees

- `0x18000217c`
- `0x180002308`
- `0x1800026b0`
- `0x180003234`
- `0x1800032f4`

## pseudocode

```c
void __fastcall CatchIt___FrameHandler4_(
        struct EHExceptionRecord *a1,
        unsigned __int64 *a2,
        struct _CONTEXT *a3,
        struct _xDISPATCHER_CONTEXT *a4,
        struct FH4::FuncInfo4 *a5,
        struct FH4::HandlerType4 *a6,
        __int64 a7,
        int *a8,
        int a9,
        int a10,
        int a11,
        char a12)
{
  unsigned __int64 *EstablisherFrame; // rax
  unsigned __int64 *v16; // r15
  struct FH4::HandlerType4 *v17; // rbp
  __int64 v18; // rbx
  int v19; // edi
  int v20; // esi
  __int64 ImageBase; // rax
  unsigned __int64 v22; // [rsp+A8h] [rbp+10h] BYREF
  struct _CONTEXT *v23; // [rsp+B0h] [rbp+18h]

  v23 = a3;
  v22 = 0;
  EstablisherFrame = __FrameHandler4::GetEstablisherFrame(a2, a4, a5, &v22);
  v16 = EstablisherFrame;
  v17 = a6;
  if ( a7 )
    BuildCatchObjectInternal___FrameHandler4_(a1, EstablisherFrame, a6);
  v18 = *((int *)v17 + 4);
  v19 = a8[2];
  v20 = *a8;
  ImageBase = GetImageBase();
  __FrameHandler4::UnwindNestedFrames(a2, a1, v23, v16, (void *)(v18 + ImageBase), a5, v20, v19, v17, a4, a12);
}

```

## disassembly

```asm
0x1800032f4  mov     rax, rsp
0x1800032f7  mov     [rax+8], rbx
0x1800032fb  mov     [rax+18h], r8
0x1800032ff  push    rbp
0x180003300  push    rsi
0x180003301  push    rdi
0x180003302  push    r12
0x180003304  push    r13
0x180003306  push    r14
0x180003308  push    r15
0x18000330a  sub     rsp, 60h
0x18000330e  mov     r8, [rsp+98h+arg_20]; struct FH4::FuncInfo4 *
0x180003316  mov     r12, r9
0x180003319  mov     r13, rdx
0x18000331c  mov     qword ptr [rax+10h], 0
0x180003324  mov     r14, rcx
0x180003327  lea     r9, [rax+10h]; unsigned __int64 *
0x18000332b  mov     rdx, r12; struct _xDISPATCHER_CONTEXT *
0x18000332e  mov     rcx, r13; unsigned __int64 *
0x180003331  call    ?GetEstablisherFrame@__FrameHandler4@@SAPEA_KPEA_KPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@0@Z; __FrameHandler4::GetEstablisherFrame(unsigned __int64 *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,unsigned __int64 *)
0x180003336  mov     r9, [rsp+98h+arg_30]
0x18000333e  mov     r15, rax
0x180003341  mov     rbp, [rsp+98h+arg_28]
0x180003349  test    r9, r9
0x18000334c  jz      short loc_18000335C
0x18000334e  mov     r8, rbp
0x180003351  mov     rdx, rax
0x180003354  mov     rcx, r14
0x180003357  call    BuildCatchObjectInternal___FrameHandler4_
0x18000335c  mov     rcx, [rsp+98h+arg_38]
0x180003364  movsxd  rbx, dword ptr [rbp+10h]
0x180003368  mov     edi, [rcx+8]
0x18000336b  mov     esi, [rcx]
0x18000336d  call    _GetImageBase
0x180003372  mov     cl, [rsp+98h+arg_58]
0x180003379  add     rax, rbx
0x18000337c  mov     r8, [rsp+98h+arg_10]; struct _CONTEXT *
0x180003384  mov     r9, r15; unsigned __int64 *
0x180003387  mov     [rsp+98h+var_48], cl; char
0x18000338b  mov     rdx, r14; struct EHExceptionRecord *
0x18000338e  mov     rcx, [rsp+98h+arg_20]
0x180003396  mov     [rsp+98h+var_50], r12; struct _xDISPATCHER_CONTEXT *
0x18000339b  mov     [rsp+98h+var_58], rbp; struct FH4::HandlerType4 *
0x1800033a0  mov     [rsp+98h+var_60], edi; int
0x1800033a4  mov     [rsp+98h+var_68], esi; int
0x1800033a8  mov     [rsp+98h+var_70], rcx; struct FH4::FuncInfo4 *
0x1800033ad  mov     rcx, r13; unsigned __int64 *
0x1800033b0  mov     [rsp+98h+var_78], rax; void *
0x1800033b5  call    ?UnwindNestedFrames@__FrameHandler4@@SAXPEA_KPEAUEHExceptionRecord@@PEAU_CONTEXT@@0PEAXPEAUFuncInfo4@FH4@@HHPEAUHandlerType4@5@PEAU_xDISPATCHER_CONTEXT@@E@Z; __FrameHandler4::UnwindNestedFrames(unsigned __int64 *,EHExceptionRecord *,_CONTEXT *,unsigned __int64 *,void *,FH4::FuncInfo4 *,int,int,FH4::HandlerType4 *,_xDISPATCHER_CONTEXT *,uchar)
0x1800033ba  mov     rbx, [rsp+98h+arg_0]
0x1800033c2  add     rsp, 60h
0x1800033c6  pop     r15
0x1800033c8  pop     r14
0x1800033ca  pop     r13
0x1800033cc  pop     r12
0x1800033ce  pop     rdi
0x1800033cf  pop     rsi
0x1800033d0  pop     rbp
0x1800033d1  retn
```
