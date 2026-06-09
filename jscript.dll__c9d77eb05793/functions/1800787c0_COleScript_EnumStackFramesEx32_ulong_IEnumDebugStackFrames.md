# COleScript::EnumStackFramesEx32(ulong,IEnumDebugStackFrames * *)

- ea: `0x1800787c0`
- end: `0x18007886f`
- name: `?EnumStackFramesEx32@COleScript@@UEAAJKPEAPEAUIEnumDebugStackFrames@@@Z`
- size: `175`
- prototype: `int(COleScript *__hidden this, unsigned int, struct IEnumDebugStackFrames **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800787a0`

## callees

- `0x180003fac`
- `0x180054480`
- `0x1800576a0`
- `0x1800787c0`
- `0x18007cb60`
- `0x180080510`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800787fd`
- `KERNEL32!GetCurrentThreadId` at `0x1800787fd`

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
0x1800787c0  push    rbx
0x1800787c2  push    rbp
0x1800787c3  push    rsi
0x1800787c4  push    rdi
0x1800787c5  sub     rsp, 28h
0x1800787c9  mov     ebp, edx
0x1800787cb  mov     rsi, r8
0x1800787ce  mov     rdi, rcx
0x1800787d1  test    r8, r8
0x1800787d4  jnz     short loc_1800787E0
0x1800787d6  mov     eax, 80004003h
0x1800787db  jmp     loc_180078866
0x1800787e0  mov     qword ptr [r8], 0
0x1800787e7  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x1800787ec  test    eax, eax
0x1800787ee  jnz     short loc_1800787F7
0x1800787f0  mov     eax, 8000FFFFh
0x1800787f5  jmp     short loc_180078866
0x1800787f7  mov     ebx, [rdi+104h]
0x1800787fd  call    cs:__imp_GetCurrentThreadId
0x180078803  cmp     eax, ebx
0x180078805  jnz     short loc_180078861
0x180078807  cmp     qword ptr [rdi+2A0h], 0
0x18007880f  jz      short loc_180078861
0x180078811  mov     ecx, 30h ; '0'; Size
0x180078816  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007881b  test    rax, rax
0x18007881e  jz      short loc_18007885A
0x180078820  mov     r8, [rdi+2A0h]; struct CSession *
0x180078827  mov     rdx, rbp; unsigned __int64
0x18007882a  mov     rcx, rax; this
0x18007882d  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x180078832  mov     rdi, rax
0x180078835  test    rax, rax
0x180078838  jz      short loc_18007885A
0x18007883a  mov     r8, rsi; void **
0x18007883d  lea     rdx, IID_IEnumDebugStackFrames; struct _GUID *
0x180078844  mov     rcx, rax; this
0x180078847  call    ?QueryInterface@CEnumDebugStackFrames@@UEAAJAEBU_GUID@@PEAPEAX@Z; CEnumDebugStackFrames::QueryInterface(_GUID const &,void * *)
0x18007884c  mov     rcx, rdi; this
0x18007884f  mov     ebx, eax
0x180078851  call    ?Release@CEnumDebugStackFrames@@UEAAKXZ; CEnumDebugStackFrames::Release(void)
0x180078856  mov     eax, ebx
0x180078858  jmp     short loc_180078866
0x18007885a  mov     eax, 8007000Eh
0x18007885f  jmp     short loc_180078866
0x180078861  mov     eax, 80004005h
0x180078866  add     rsp, 28h
0x18007886a  pop     rdi
0x18007886b  pop     rsi
0x18007886c  pop     rbp
0x18007886d  pop     rbx
0x18007886e  retn
```
