# COleScript::EnumStackFramesEx64(unsigned __int64,IEnumDebugStackFrames64 * *)

- ea: `0x180078880`
- end: `0x180078934`
- name: `?EnumStackFramesEx64@COleScript@@UEAAJ_KPEAPEAUIEnumDebugStackFrames64@@@Z`
- size: `180`
- prototype: `int(COleScript *__hidden this, unsigned __int64, struct IEnumDebugStackFrames64 **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003fac`
- `0x180054480`
- `0x1800576a0`
- `0x180078880`
- `0x18007cb60`
- `0x180080510`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800788c2`
- `KERNEL32!GetCurrentThreadId` at `0x1800788c2`

## pseudocode

```c
__int64 __fastcall COleScript::EnumStackFramesEx64(
        COleScript *this,
        unsigned __int64 a2,
        struct IEnumDebugStackFrames64 **a3)
{
  int v7; // ebx
  CEnumDebugStackFrames *v8; // rax
  CEnumDebugStackFrames *v9; // rax
  CEnumDebugStackFrames *v10; // rdi
  unsigned int Interface; // ebx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !(unsigned int)COleScript::FDebuggerEnabled((COleScript *)((char *)this - 48)) )
    return 2147549183LL;
  v7 = *((_DWORD *)this + 53);
  if ( GetCurrentThreadId() != v7 || !*((_QWORD *)this + 78) )
    return 2147500037LL;
  v8 = (CEnumDebugStackFrames *)operator new(0x30u);
  if ( !v8 )
    return 2147942414LL;
  v9 = CEnumDebugStackFrames::CEnumDebugStackFrames(v8, a2, *((struct CSession **)this + 78));
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  Interface = CEnumDebugStackFrames::QueryInterface(v9, &IID_IEnumDebugStackFrames64, (void **)a3);
  CEnumDebugStackFrames::Release(v10);
  return Interface;
}

```

## disassembly

```asm
0x180078880  push    rbx
0x180078882  push    rbp
0x180078883  push    rsi
0x180078884  push    rdi
0x180078885  sub     rsp, 28h
0x180078889  mov     rsi, r8
0x18007888c  mov     rbp, rdx
0x18007888f  mov     rdi, rcx
0x180078892  test    r8, r8
0x180078895  jnz     short loc_1800788A1
0x180078897  mov     eax, 80004003h
0x18007889c  jmp     loc_18007892B
0x1800788a1  add     rcx, 0FFFFFFFFFFFFFFD0h; this
0x1800788a5  mov     qword ptr [r8], 0
0x1800788ac  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x1800788b1  test    eax, eax
0x1800788b3  jnz     short loc_1800788BC
0x1800788b5  mov     eax, 8000FFFFh
0x1800788ba  jmp     short loc_18007892B
0x1800788bc  mov     ebx, [rdi+0D4h]
0x1800788c2  call    cs:__imp_GetCurrentThreadId
0x1800788c8  cmp     eax, ebx
0x1800788ca  jnz     short loc_180078926
0x1800788cc  cmp     qword ptr [rdi+270h], 0
0x1800788d4  jz      short loc_180078926
0x1800788d6  mov     ecx, 30h ; '0'; Size
0x1800788db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800788e0  test    rax, rax
0x1800788e3  jz      short loc_18007891F
0x1800788e5  mov     r8, [rdi+270h]; struct CSession *
0x1800788ec  mov     rdx, rbp; unsigned __int64
0x1800788ef  mov     rcx, rax; this
0x1800788f2  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x1800788f7  mov     rdi, rax
0x1800788fa  test    rax, rax
0x1800788fd  jz      short loc_18007891F
0x1800788ff  mov     r8, rsi; void **
0x180078902  lea     rdx, IID_IEnumDebugStackFrames64; struct _GUID *
0x180078909  mov     rcx, rax; this
0x18007890c  call    ?QueryInterface@CEnumDebugStackFrames@@UEAAJAEBU_GUID@@PEAPEAX@Z; CEnumDebugStackFrames::QueryInterface(_GUID const &,void * *)
0x180078911  mov     rcx, rdi; this
0x180078914  mov     ebx, eax
0x180078916  call    ?Release@CEnumDebugStackFrames@@UEAAKXZ; CEnumDebugStackFrames::Release(void)
0x18007891b  mov     eax, ebx
0x18007891d  jmp     short loc_18007892B
0x18007891f  mov     eax, 8007000Eh
0x180078924  jmp     short loc_18007892B
0x180078926  mov     eax, 80004005h
0x18007892b  add     rsp, 28h
0x18007892f  pop     rdi
0x180078930  pop     rsi
0x180078931  pop     rbp
0x180078932  pop     rbx
0x180078933  retn
```
