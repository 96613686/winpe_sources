# CRefThread::Release(void)

- ea: `0x180009fb0`
- end: `0x18000a024`
- name: `?Release@CRefThread@@UEAAKXZ`
- size: `116`
- prototype: `unsigned int __fastcall(CRefThread *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180009fb0`
- `0x18001272e`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009ffa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009ffa`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x18000a00c`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x18000a00c`

## pseudocode

```c
__int64 __fastcall CRefThread::Release(CRefThread *this)
{
  DWORD v1; // edi
  void *v2; // rsi
  unsigned __int32 v3; // ebx

  v1 = *((_DWORD *)this + 4);
  v2 = (void *)*((_QWORD *)this + 3);
  v3 = _InterlockedDecrement(*((volatile signed __int32 **)this + 1));
  if ( !v3 )
    (*(void (__fastcall **)(CRefThread *, __int64))(*(_QWORD *)this + 32LL))(this, 1);
  if ( v1 != GetCurrentThreadId_0() )
  {
    if ( v2 )
      SetEvent(v2);
    else
      PostThreadMessageW(v1, 0, 0, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x180009fb0  mov     [rsp+arg_0], rbx
0x180009fb5  mov     [rsp+arg_8], rsi
0x180009fba  push    rdi
0x180009fbb  sub     rsp, 20h
0x180009fbf  mov     edi, [rcx+10h]
0x180009fc2  mov     ebx, 0FFFFFFFFh
0x180009fc7  mov     rsi, [rcx+18h]
0x180009fcb  mov     rax, [rcx+8]
0x180009fcf  lock xadd [rax], ebx
0x180009fd3  sub     ebx, 1
0x180009fd6  jnz     short loc_180009FE9
0x180009fd8  mov     rax, [rcx]
0x180009fdb  mov     edx, 1
0x180009fe0  mov     rax, [rax+20h]
0x180009fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe9  call    GetCurrentThreadId_0
0x180009fee  cmp     edi, eax
0x180009ff0  jz      short loc_18000A012
0x180009ff2  test    rsi, rsi
0x180009ff5  jz      short loc_18000A002
0x180009ff7  mov     rcx, rsi; hEvent
0x180009ffa  call    cs:__imp_SetEvent
0x18000a000  jmp     short loc_18000A012
0x18000a002  xor     r9d, r9d; lParam
0x18000a005  xor     r8d, r8d; wParam
0x18000a008  xor     edx, edx; Msg
0x18000a00a  mov     ecx, edi; idThread
0x18000a00c  call    cs:__imp_PostThreadMessageW
0x18000a012  mov     rsi, [rsp+28h+arg_8]
0x18000a017  mov     eax, ebx
0x18000a019  mov     rbx, [rsp+28h+arg_0]
0x18000a01e  add     rsp, 20h
0x18000a022  pop     rdi
0x18000a023  retn
```
