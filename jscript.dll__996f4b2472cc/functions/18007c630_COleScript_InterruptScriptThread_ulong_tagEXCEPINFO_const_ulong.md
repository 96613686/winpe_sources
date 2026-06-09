# COleScript::InterruptScriptThread(ulong,tagEXCEPINFO const *,ulong)

- ea: `0x18007c630`
- end: `0x18007c6fd`
- name: `?InterruptScriptThread@COleScript@@UEAAJKPEBUtagEXCEPINFO@@K@Z`
- size: `205`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int, const struct tagEXCEPINFO *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001612c`
- `0x180016e68`
- `0x1800172e8`
- `0x180017330`
- `0x18007c630`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007c646`
- `KERNEL32!GetCurrentThreadId` at `0x18007c646`

## pseudocode

```c
__int64 __fastcall COleScript::InterruptScriptThread(
        COleScript *this,
        DWORD CurrentThreadId,
        const struct tagEXCEPINFO *a3)
{
  int v5; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax

  if ( CurrentThreadId == -1 )
  {
    CurrentThreadId = GetCurrentThreadId();
  }
  else if ( CurrentThreadId + 3 <= 1 )
  {
    CurrentThreadId = *((_DWORD *)this + 65);
  }
  v5 = *((_DWORD *)this + 65);
  if ( v5 == -1 )
    return 2147549183LL;
  if ( CurrentThreadId != v5 )
    return 2147942487LL;
  if ( !(unsigned int)COleScript::DisableInterrupts(this) )
    return 2147500037LL;
  if ( *((_DWORD *)this + 74) != 1 || *(_DWORD *)(*((_QWORD *)this + 84) + 1040LL) )
  {
    v7 = -2147024809;
  }
  else
  {
    v7 = 0;
    FreeExcepInfo((struct tagEXCEPINFO *)((char *)this + 608));
    if ( a3 )
      CopyException((struct tagEXCEPINFO *)((char *)this + 608), a3);
    v8 = *((_QWORD *)this + 84);
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 1040));
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 1044));
  }
  COleScript::EnableInterrupts(this);
  return v7;
}

```

## disassembly

```asm
0x18007c630  push    rbx
0x18007c632  push    rbp
0x18007c633  push    rsi
0x18007c634  push    rdi
0x18007c635  sub     rsp, 28h
0x18007c639  or      ebx, 0FFFFFFFFh
0x18007c63c  mov     rbp, r8
0x18007c63f  mov     rdi, rcx
0x18007c642  cmp     edx, ebx
0x18007c644  jnz     short loc_18007C656
0x18007c646  call    cs:__imp_GetCurrentThreadId
0x18007c64d  nop     dword ptr [rax+rax+00h]
0x18007c652  mov     edx, eax
0x18007c654  jmp     short loc_18007C664
0x18007c656  lea     eax, [rdx+3]
0x18007c659  cmp     eax, 1
0x18007c65c  ja      short loc_18007C664
0x18007c65e  mov     edx, [rcx+104h]
0x18007c664  mov     eax, [rdi+104h]
0x18007c66a  cmp     eax, ebx
0x18007c66c  jnz     short loc_18007C675
0x18007c66e  mov     eax, 8000FFFFh
0x18007c673  jmp     short loc_18007C6F3
0x18007c675  cmp     edx, eax
0x18007c677  jz      short loc_18007C680
0x18007c679  mov     eax, 80070057h
0x18007c67e  jmp     short loc_18007C6F3
0x18007c680  mov     rcx, rdi; this
0x18007c683  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18007c688  test    eax, eax
0x18007c68a  jnz     short loc_18007C693
0x18007c68c  mov     eax, 80004005h
0x18007c691  jmp     short loc_18007C6F3
0x18007c693  cmp     dword ptr [rdi+128h], 1
0x18007c69a  jnz     short loc_18007C6E4
0x18007c69c  mov     rax, [rdi+2A0h]
0x18007c6a3  cmp     dword ptr [rax+410h], 0
0x18007c6aa  jnz     short loc_18007C6E4
0x18007c6ac  lea     rsi, [rdi+260h]
0x18007c6b3  xor     ebx, ebx
0x18007c6b5  mov     rcx, rsi; struct tagEXCEPINFO *
0x18007c6b8  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x18007c6bd  test    rbp, rbp
0x18007c6c0  jz      short loc_18007C6CD
0x18007c6c2  mov     rdx, rbp; struct tagEXCEPINFO *
0x18007c6c5  mov     rcx, rsi; struct tagEXCEPINFO *
0x18007c6c8  call    ?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z; CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)
0x18007c6cd  mov     rax, [rdi+2A0h]
0x18007c6d4  lock inc dword ptr [rax+410h]
0x18007c6db  lock inc dword ptr [rax+414h]
0x18007c6e2  jmp     short loc_18007C6E9
0x18007c6e4  mov     ebx, 80070057h
0x18007c6e9  mov     rcx, rdi; this
0x18007c6ec  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x18007c6f1  mov     eax, ebx
0x18007c6f3  add     rsp, 28h
0x18007c6f7  pop     rdi
0x18007c6f8  pop     rsi
0x18007c6f9  pop     rbp
0x18007c6fa  pop     rbx
0x18007c6fb  retn
```
