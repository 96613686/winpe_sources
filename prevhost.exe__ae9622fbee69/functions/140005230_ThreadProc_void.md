# ThreadProc(void *)

- ea: `0x140005230`
- end: `0x140005292`
- name: `?ThreadProc@@YAKPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140004588`
- `0x140005230`
- `0x140006010`

## pseudocode

```c
__int64 __fastcall ThreadProc(LPVOID lpThreadParameter)
{
  struct IPreviewHandler *v2; // rdi

  if ( *((int *)lpThreadParameter + 15) >= 0 )
  {
    v2 = (struct IPreviewHandler *)*((_QWORD *)lpThreadParameter + 8);
    if ( v2 )
    {
      ((void (__fastcall *)(_QWORD))v2->lpVtbl->AddRef)(*((_QWORD *)lpThreadParameter + 8));
      MessageLoop(v2, *((void **)lpThreadParameter + 6));
      ((void (__fastcall *)(struct IPreviewHandler *))v2->lpVtbl->Release)(v2);
    }
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpThreadParameter + 16LL))(lpThreadParameter);
  return 0;
}

```

## disassembly

```asm
0x140005230  mov     [rsp+arg_0], rbx
0x140005235  push    rdi
0x140005236  sub     rsp, 20h
0x14000523a  cmp     dword ptr [rcx+3Ch], 0
0x14000523e  mov     rbx, rcx
0x140005241  jl      short loc_140005276
0x140005243  mov     rdi, [rcx+40h]
0x140005247  test    rdi, rdi
0x14000524a  jz      short loc_140005276
0x14000524c  mov     rax, [rdi]
0x14000524f  mov     rcx, rdi
0x140005252  mov     rax, [rax+8]
0x140005256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000525b  mov     rdx, [rbx+30h]; void *
0x14000525f  mov     rcx, rdi; struct IPreviewHandler *
0x140005262  call    ?MessageLoop@@YAXPEAUIPreviewHandler@@PEAX@Z; MessageLoop(IPreviewHandler *,void *)
0x140005267  mov     rax, [rdi]
0x14000526a  mov     rcx, rdi
0x14000526d  mov     rax, [rax+10h]
0x140005271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005276  mov     rax, [rbx]
0x140005279  mov     rcx, rbx
0x14000527c  mov     rax, [rax+10h]
0x140005280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005285  mov     rbx, [rsp+28h+arg_0]
0x14000528a  xor     eax, eax
0x14000528c  add     rsp, 20h
0x140005290  pop     rdi
0x140005291  retn
```
