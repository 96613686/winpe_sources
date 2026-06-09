# CHotPlug_CreateInstance

- ea: `0x1800026f0`
- end: `0x180002771`
- name: `CHotPlug_CreateInstance`
- size: `129`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001e88`
- `0x1800026f0`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CHotPlug_CreateInstance(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  unsigned int v6; // edi

  *a2 = 0;
  v4 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    v4[2] = 1;
    *(_QWORD *)v4 = &CHotPlug::`vftable';
    v6 = ((__int64 (__fastcall *)(_DWORD *, __int64, _QWORD *))CHotPlug::`vftable')(v4, a1, a2);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x1800026f0  mov     [rsp+arg_0], rbx
0x1800026f5  mov     [rsp+arg_8], rsi
0x1800026fa  push    rdi
0x1800026fb  sub     rsp, 20h
0x1800026ff  mov     rdi, rdx
0x180002702  mov     qword ptr [rdx], 0
0x180002709  mov     rsi, rcx
0x18000270c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002713  mov     ecx, 10h; unsigned __int64
0x180002718  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000271d  mov     rbx, rax
0x180002720  test    rax, rax
0x180002723  jz      short loc_18000275A
0x180002725  lea     rax, ??_7CHotPlug@@6B@; const CHotPlug::`vftable'
0x18000272c  mov     dword ptr [rbx+8], 1
0x180002733  mov     [rbx], rax
0x180002736  mov     r8, rdi
0x180002739  mov     rax, [rax]
0x18000273c  mov     rdx, rsi
0x18000273f  mov     rcx, rbx
0x180002742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002747  mov     rcx, [rbx]
0x18000274a  mov     edi, eax
0x18000274c  mov     rax, [rcx+10h]
0x180002750  mov     rcx, rbx
0x180002753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002758  jmp     short loc_18000275F
0x18000275a  mov     edi, 8007000Eh
0x18000275f  mov     rbx, [rsp+28h+arg_0]
0x180002764  mov     eax, edi
0x180002766  mov     rsi, [rsp+28h+arg_8]
0x18000276b  add     rsp, 20h
0x18000276f  pop     rdi
0x180002770  retn
```
