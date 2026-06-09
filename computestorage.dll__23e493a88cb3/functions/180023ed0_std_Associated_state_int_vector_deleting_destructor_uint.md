# std::_Associated_state<int>::`vector deleting destructor'(uint)

- ea: `0x180023ed0`
- end: `0x180023f3d`
- name: `??_E?$_Associated_state@H@std@@UEAAPEAXI@Z`
- size: `109`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002b74`
- `0x180023ed0`

## import_xrefs

- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x180023eff`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x180023eff`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023f0f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023f0f`

## pseudocode

```c
char *__fastcall std::_Associated_state<int>::`vector deleting destructor'(char *a1, char a2)
{
  bool v2; // zf

  v2 = a1[193] == 0;
  *(_QWORD *)a1 = &std::_Associated_state<int>::`vftable';
  if ( !v2 && !*((_DWORD *)a1 + 47) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(a1 + 32));
  __ExceptionPtrDestroy(a1 + 16);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180023ed0  mov     [rsp+arg_0], rbx
0x180023ed5  push    rdi
0x180023ed6  sub     rsp, 20h
0x180023eda  cmp     byte ptr [rcx+0C1h], 0
0x180023ee1  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x180023ee8  mov     [rcx], rax
0x180023eeb  mov     edi, edx
0x180023eed  mov     rbx, rcx
0x180023ef0  jz      short loc_180023F0B
0x180023ef2  cmp     dword ptr [rcx+0BCh], 0
0x180023ef9  jnz     short loc_180023F0B
0x180023efb  add     rcx, 20h ; ' '; _Mtx_t
0x180023eff  call    cs:__imp__Cnd_unregister_at_thread_exit
0x180023f06  nop     dword ptr [rax+rax+00h]
0x180023f0b  lea     rcx, [rbx+10h]
0x180023f0f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180023f16  nop     dword ptr [rax+rax+00h]
0x180023f1b  test    dil, 1
0x180023f1f  jz      short loc_180023F2E
0x180023f21  mov     edx, 0D0h; unsigned __int64
0x180023f26  mov     rcx, rbx; void *
0x180023f29  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023f2e  mov     rax, rbx
0x180023f31  mov     rbx, [rsp+28h+arg_0]
0x180023f36  add     rsp, 20h
0x180023f3a  pop     rdi
0x180023f3b  retn
```
