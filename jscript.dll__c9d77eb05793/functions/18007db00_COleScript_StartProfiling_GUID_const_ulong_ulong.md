# COleScript::StartProfiling(_GUID const &,ulong,ulong)

- ea: `0x18007db00`
- end: `0x18007db61`
- name: `?StartProfiling@COleScript@@UEAAJAEBU_GUID@@KK@Z`
- size: `97`
- prototype: `int(COleScript *__hidden this, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800616f8`
- `0x18007db00`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007db27`
- `KERNEL32!GetCurrentThreadId` at `0x18007db27`

## pseudocode

```c
__int64 __fastcall COleScript::StartProfiling(COleScript *this, const struct _GUID *a2, char a3, unsigned int a4)
{
  int v8; // ebx

  if ( *((_QWORD *)this + 80) && (v8 = *((_DWORD *)this + 57), GetCurrentThreadId() == v8) )
    return EEToProfInterfaceImpl::CreateAndInitializeProfiler(
             (LPVOID *)(*((_QWORD *)this + 80) + 8LL),
             *(struct COleScript **)(*((_QWORD *)this + 80) + 40LL),
             a2,
             a3,
             a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18007db00  push    rbx
0x18007db02  push    rbp
0x18007db03  push    rsi
0x18007db04  push    rdi
0x18007db05  push    r14
0x18007db07  sub     rsp, 30h
0x18007db0b  cmp     qword ptr [rcx+280h], 0
0x18007db13  mov     esi, r9d
0x18007db16  mov     ebp, r8d
0x18007db19  mov     r14, rdx
0x18007db1c  mov     rdi, rcx
0x18007db1f  jz      short loc_18007DB51
0x18007db21  mov     ebx, [rcx+0E4h]
0x18007db27  call    cs:__imp_GetCurrentThreadId
0x18007db2d  cmp     eax, ebx
0x18007db2f  jnz     short loc_18007DB51
0x18007db31  mov     rdx, [rdi+280h]
0x18007db38  mov     r9d, ebp; unsigned int
0x18007db3b  mov     r8, r14; struct _GUID *
0x18007db3e  mov     [rsp+58h+var_38], esi; unsigned int
0x18007db42  lea     rcx, [rdx+8]; ppv
0x18007db46  mov     rdx, [rdx+28h]; struct COleScript *
0x18007db4a  call    ?CreateAndInitializeProfiler@EEToProfInterfaceImpl@@QEAAJPEAVCOleScript@@AEBU_GUID@@KK@Z; EEToProfInterfaceImpl::CreateAndInitializeProfiler(COleScript *,_GUID const &,ulong,ulong)
0x18007db4f  jmp     short loc_18007DB56
0x18007db51  mov     eax, 80004005h
0x18007db56  add     rsp, 30h
0x18007db5a  pop     r14
0x18007db5c  pop     rdi
0x18007db5d  pop     rsi
0x18007db5e  pop     rbp
0x18007db5f  pop     rbx
0x18007db60  retn
```
