# COleScript::EnumStackFramesEx64(unsigned __int64,IEnumDebugStackFrames64 * *)

- ea: `0x180079ea0`
- end: `0x180079f5b`
- name: `?EnumStackFramesEx64@COleScript@@UEAAJ_KPEAPEAUIEnumDebugStackFrames64@@@Z`
- size: `187`
- prototype: `int(COleScript *__hidden this, unsigned __int64, struct IEnumDebugStackFrames64 **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800323cc`
- `0x1800552c0`
- `0x1800585d0`
- `0x180079ea0`
- `0x18007e3e0`
- `0x1800820b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180079ee2`
- `KERNEL32!GetCurrentThreadId` at `0x180079ee2`

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
0x180079ea0  push    rbx
0x180079ea2  push    rbp
0x180079ea3  push    rsi
0x180079ea4  push    rdi
0x180079ea5  sub     rsp, 28h
0x180079ea9  mov     rsi, r8
0x180079eac  mov     rbp, rdx
0x180079eaf  mov     rdi, rcx
0x180079eb2  test    r8, r8
0x180079eb5  jnz     short loc_180079EC1
0x180079eb7  mov     eax, 80004003h
0x180079ebc  jmp     loc_180079F51
0x180079ec1  add     rcx, 0FFFFFFFFFFFFFFD0h; this
0x180079ec5  mov     qword ptr [r8], 0
0x180079ecc  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x180079ed1  test    eax, eax
0x180079ed3  jnz     short loc_180079EDC
0x180079ed5  mov     eax, 8000FFFFh
0x180079eda  jmp     short loc_180079F51
0x180079edc  mov     ebx, [rdi+0D4h]
0x180079ee2  call    cs:__imp_GetCurrentThreadId
0x180079ee9  nop     dword ptr [rax+rax+00h]
0x180079eee  cmp     eax, ebx
0x180079ef0  jnz     short loc_180079F4C
0x180079ef2  cmp     qword ptr [rdi+270h], 0
0x180079efa  jz      short loc_180079F4C
0x180079efc  mov     ecx, 30h ; '0'; Size
0x180079f01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079f06  test    rax, rax
0x180079f09  jz      short loc_180079F45
0x180079f0b  mov     r8, [rdi+270h]; struct CSession *
0x180079f12  mov     rdx, rbp; unsigned __int64
0x180079f15  mov     rcx, rax; this
0x180079f18  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x180079f1d  mov     rdi, rax
0x180079f20  test    rax, rax
0x180079f23  jz      short loc_180079F45
0x180079f25  mov     r8, rsi; void **
0x180079f28  lea     rdx, IID_IEnumDebugStackFrames64; struct _GUID *
0x180079f2f  mov     rcx, rax; this
0x180079f32  call    ?QueryInterface@CEnumDebugStackFrames@@UEAAJAEBU_GUID@@PEAPEAX@Z; CEnumDebugStackFrames::QueryInterface(_GUID const &,void * *)
0x180079f37  mov     rcx, rdi; this
0x180079f3a  mov     ebx, eax
0x180079f3c  call    ?Release@CEnumDebugStackFrames@@UEAAKXZ; CEnumDebugStackFrames::Release(void)
0x180079f41  mov     eax, ebx
0x180079f43  jmp     short loc_180079F51
0x180079f45  mov     eax, 8007000Eh
0x180079f4a  jmp     short loc_180079F51
0x180079f4c  mov     eax, 80004005h
0x180079f51  add     rsp, 28h
0x180079f55  pop     rdi
0x180079f56  pop     rsi
0x180079f57  pop     rbp
0x180079f58  pop     rbx
0x180079f59  retn
```
