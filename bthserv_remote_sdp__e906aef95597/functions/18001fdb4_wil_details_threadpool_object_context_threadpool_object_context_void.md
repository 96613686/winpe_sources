# wil::details::threadpool_object_context::~threadpool_object_context(void)

- ea: `0x18001fdb4`
- end: `0x18001fe38`
- name: `??1threadpool_object_context@details@wil@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(wil::details::threadpool_object_context *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fba0`
- `0x18001fe40`
- `0x180021454`

## callees

- `0x180009944`
- `0x18001fdb4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fdd1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fdd1`

## pseudocode

```c
void __fastcall wil::details::threadpool_object_context::~threadpool_object_context(
        wil::details::threadpool_object_context *this)
{
  __int64 v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  volatile signed __int32 *v5; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *(_QWORD *)this;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF) == 1 && !SetEvent(*(HANDLE *)(v2 + 16)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D3, v3, v4);
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v5 && _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
    if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  }
}

```

## disassembly

```asm
0x18001fdb4  push    rbx
0x18001fdb6  sub     rsp, 20h
0x18001fdba  mov     rbx, rcx
0x18001fdbd  or      eax, 0FFFFFFFFh
0x18001fdc0  mov     rcx, [rcx]
0x18001fdc3  lock xadd [rcx+8], eax
0x18001fdc8  cmp     eax, 1
0x18001fdcb  jnz     short loc_18001FDE1
0x18001fdcd  mov     rcx, [rcx+10h]; hEvent
0x18001fdd1  call    cs:__imp_SetEvent
0x18001fdd8  nop     dword ptr [rax+rax+00h]
0x18001fddd  test    eax, eax
0x18001fddf  jz      short loc_18001FE28
0x18001fde1  mov     rbx, [rbx+8]
0x18001fde5  test    rbx, rbx
0x18001fde8  jz      short loc_18001FE21
0x18001fdea  or      eax, 0FFFFFFFFh
0x18001fded  lock xadd [rbx+8], eax
0x18001fdf2  cmp     eax, 1
0x18001fdf5  jnz     short loc_18001FE21
0x18001fdf7  mov     rax, [rbx]
0x18001fdfa  mov     rcx, rbx
0x18001fdfd  mov     rax, [rax]
0x18001fe00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe05  or      eax, 0FFFFFFFFh
0x18001fe08  lock xadd [rbx+0Ch], eax
0x18001fe0d  cmp     eax, 1
0x18001fe10  jnz     short loc_18001FE21
0x18001fe12  mov     rax, [rbx]
0x18001fe15  mov     rcx, rbx
0x18001fe18  mov     rax, [rax+8]
0x18001fe1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe21  add     rsp, 20h
0x18001fe25  pop     rbx
0x18001fe26  retn
0x18001fe28  mov     rcx, [rsp+28h]; this
0x18001fe2d  mov     edx, 9D3h; void *
0x18001fe32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
