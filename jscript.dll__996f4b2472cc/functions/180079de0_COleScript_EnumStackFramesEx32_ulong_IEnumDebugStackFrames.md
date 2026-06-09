# COleScript::EnumStackFramesEx32(ulong,IEnumDebugStackFrames * *)

- ea: `0x180079de0`
- end: `0x180079e96`
- name: `?EnumStackFramesEx32@COleScript@@UEAAJKPEAPEAUIEnumDebugStackFrames@@@Z`
- size: `182`
- prototype: `int(COleScript *__hidden this, unsigned int, struct IEnumDebugStackFrames **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180079dc0`

## callees

- `0x1800323cc`
- `0x1800552c0`
- `0x1800585d0`
- `0x180079de0`
- `0x18007e3e0`
- `0x1800820b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180079e1d`
- `KERNEL32!GetCurrentThreadId` at `0x180079e1d`

## pseudocode

```c
__int64 __fastcall COleScript::EnumStackFramesEx32(
        struct CSession **this,
        unsigned int a2,
        struct IEnumDebugStackFrames **a3)
{
  unsigned __int64 v3; // rbp
  int v7; // ebx
  CEnumDebugStackFrames *v8; // rax
  CEnumDebugStackFrames *v9; // rax
  CEnumDebugStackFrames *v10; // rdi
  unsigned int Interface; // ebx

  v3 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !(unsigned int)COleScript::FDebuggerEnabled((COleScript *)this) )
    return 2147549183LL;
  v7 = *((_DWORD *)this + 65);
  if ( GetCurrentThreadId() != v7 || !this[84] )
    return 2147500037LL;
  v8 = (CEnumDebugStackFrames *)operator new(0x30u);
  if ( !v8 )
    return 2147942414LL;
  v9 = CEnumDebugStackFrames::CEnumDebugStackFrames(v8, v3, this[84]);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  Interface = CEnumDebugStackFrames::QueryInterface(v9, &IID_IEnumDebugStackFrames, (void **)a3);
  CEnumDebugStackFrames::Release(v10);
  return Interface;
}

```

## disassembly

```asm
0x180079de0  push    rbx
0x180079de2  push    rbp
0x180079de3  push    rsi
0x180079de4  push    rdi
0x180079de5  sub     rsp, 28h
0x180079de9  mov     ebp, edx
0x180079deb  mov     rsi, r8
0x180079dee  mov     rdi, rcx
0x180079df1  test    r8, r8
0x180079df4  jnz     short loc_180079E00
0x180079df6  mov     eax, 80004003h
0x180079dfb  jmp     loc_180079E8C
0x180079e00  mov     qword ptr [r8], 0
0x180079e07  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x180079e0c  test    eax, eax
0x180079e0e  jnz     short loc_180079E17
0x180079e10  mov     eax, 8000FFFFh
0x180079e15  jmp     short loc_180079E8C
0x180079e17  mov     ebx, [rdi+104h]
0x180079e1d  call    cs:__imp_GetCurrentThreadId
0x180079e24  nop     dword ptr [rax+rax+00h]
0x180079e29  cmp     eax, ebx
0x180079e2b  jnz     short loc_180079E87
0x180079e2d  cmp     qword ptr [rdi+2A0h], 0
0x180079e35  jz      short loc_180079E87
0x180079e37  mov     ecx, 30h ; '0'; Size
0x180079e3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079e41  test    rax, rax
0x180079e44  jz      short loc_180079E80
0x180079e46  mov     r8, [rdi+2A0h]; struct CSession *
0x180079e4d  mov     rdx, rbp; unsigned __int64
0x180079e50  mov     rcx, rax; this
0x180079e53  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x180079e58  mov     rdi, rax
0x180079e5b  test    rax, rax
0x180079e5e  jz      short loc_180079E80
0x180079e60  mov     r8, rsi; void **
0x180079e63  lea     rdx, IID_IEnumDebugStackFrames; struct _GUID *
0x180079e6a  mov     rcx, rax; this
0x180079e6d  call    ?QueryInterface@CEnumDebugStackFrames@@UEAAJAEBU_GUID@@PEAPEAX@Z; CEnumDebugStackFrames::QueryInterface(_GUID const &,void * *)
0x180079e72  mov     rcx, rdi; this
0x180079e75  mov     ebx, eax
0x180079e77  call    ?Release@CEnumDebugStackFrames@@UEAAKXZ; CEnumDebugStackFrames::Release(void)
0x180079e7c  mov     eax, ebx
0x180079e7e  jmp     short loc_180079E8C
0x180079e80  mov     eax, 8007000Eh
0x180079e85  jmp     short loc_180079E8C
0x180079e87  mov     eax, 80004005h
0x180079e8c  add     rsp, 28h
0x180079e90  pop     rdi
0x180079e91  pop     rsi
0x180079e92  pop     rbp
0x180079e93  pop     rbx
0x180079e94  retn
```
