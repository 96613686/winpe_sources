# COleScript::InterruptScriptThread(ulong,tagEXCEPINFO const *,ulong)

- ea: `0x18007ae50`
- end: `0x18007af16`
- name: `?InterruptScriptThread@COleScript@@UEAAJKPEBUtagEXCEPINFO@@K@Z`
- size: `198`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int, const struct tagEXCEPINFO *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001913c`
- `0x180019e28`
- `0x18001a29c`
- `0x18001a2dc`
- `0x18007ae50`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007ae66`
- `KERNEL32!GetCurrentThreadId` at `0x18007ae66`

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
0x18007ae50  push    rbx
0x18007ae52  push    rbp
0x18007ae53  push    rsi
0x18007ae54  push    rdi
0x18007ae55  sub     rsp, 28h
0x18007ae59  or      ebx, 0FFFFFFFFh
0x18007ae5c  mov     rbp, r8
0x18007ae5f  mov     rdi, rcx
0x18007ae62  cmp     edx, ebx
0x18007ae64  jnz     short loc_18007AE70
0x18007ae66  call    cs:__imp_GetCurrentThreadId
0x18007ae6c  mov     edx, eax
0x18007ae6e  jmp     short loc_18007AE7E
0x18007ae70  lea     eax, [rdx+3]
0x18007ae73  cmp     eax, 1
0x18007ae76  ja      short loc_18007AE7E
0x18007ae78  mov     edx, [rcx+104h]
0x18007ae7e  mov     eax, [rdi+104h]
0x18007ae84  cmp     eax, ebx
0x18007ae86  jnz     short loc_18007AE8F
0x18007ae88  mov     eax, 8000FFFFh
0x18007ae8d  jmp     short loc_18007AF0D
0x18007ae8f  cmp     edx, eax
0x18007ae91  jz      short loc_18007AE9A
0x18007ae93  mov     eax, 80070057h
0x18007ae98  jmp     short loc_18007AF0D
0x18007ae9a  mov     rcx, rdi; this
0x18007ae9d  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18007aea2  test    eax, eax
0x18007aea4  jnz     short loc_18007AEAD
0x18007aea6  mov     eax, 80004005h
0x18007aeab  jmp     short loc_18007AF0D
0x18007aead  cmp     dword ptr [rdi+128h], 1
0x18007aeb4  jnz     short loc_18007AEFE
0x18007aeb6  mov     rax, [rdi+2A0h]
0x18007aebd  cmp     dword ptr [rax+410h], 0
0x18007aec4  jnz     short loc_18007AEFE
0x18007aec6  lea     rsi, [rdi+260h]
0x18007aecd  xor     ebx, ebx
0x18007aecf  mov     rcx, rsi; struct tagEXCEPINFO *
0x18007aed2  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x18007aed7  test    rbp, rbp
0x18007aeda  jz      short loc_18007AEE7
0x18007aedc  mov     rdx, rbp; struct tagEXCEPINFO *
0x18007aedf  mov     rcx, rsi; struct tagEXCEPINFO *
0x18007aee2  call    ?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z; CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)
0x18007aee7  mov     rax, [rdi+2A0h]
0x18007aeee  lock inc dword ptr [rax+410h]
0x18007aef5  lock inc dword ptr [rax+414h]
0x18007aefc  jmp     short loc_18007AF03
0x18007aefe  mov     ebx, 80070057h
0x18007af03  mov     rcx, rdi; this
0x18007af06  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x18007af0b  mov     eax, ebx
0x18007af0d  add     rsp, 28h
0x18007af11  pop     rdi
0x18007af12  pop     rsi
0x18007af13  pop     rbp
0x18007af14  pop     rbx
0x18007af15  retn
```
