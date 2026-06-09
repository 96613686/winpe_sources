# CCustomEtwTracerV2::CtrlCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *)

- ea: `0x1800021c0`
- end: `0x180002230`
- name: `?CtrlCallback@CCustomEtwTracerV2@@UEAAKPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@@Z`
- size: `112`
- prototype: `unsigned int __fastcall(CCustomEtwTracerV2 *__hidden this, const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800021c0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CCustomEtwTracerV2::CtrlCallback(
        CCustomEtwTracerV2 *this,
        const struct _GUID *a2,
        int a3,
        unsigned __int8 a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        struct _EVENT_FILTER_DESCRIPTOR *a7)
{
  int v8; // eax

  if ( a3 == 1 )
  {
    v8 = 5;
    *((_DWORD *)this + 2) = 1;
    if ( a4 <= 5u )
      v8 = a4;
    *((_DWORD *)this + 6) = v8;
    *((_QWORD *)this + 8) = a6;
    *((_QWORD *)this + 7) = a5;
    *((_QWORD *)this + 9) = a7;
    (**(void (__fastcall ***)(CCustomEtwTracerV2 *, const struct _GUID *))this)(this, a2);
  }
  else
  {
    (*(void (__fastcall **)(CCustomEtwTracerV2 *, const struct _GUID *))(*(_QWORD *)this + 8LL))(this, a2);
    *((_DWORD *)this + 2) = 0;
    *(_QWORD *)((char *)this + 20) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 7) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800021c0  push    rbx
0x1800021c2  sub     rsp, 20h
0x1800021c6  mov     rbx, rcx
0x1800021c9  cmp     r8d, 1
0x1800021cd  jnz     short loc_18000220B
0x1800021cf  lea     eax, [r8+4]
0x1800021d3  mov     [rcx+8], r8d
0x1800021d7  cmp     r9b, al
0x1800021da  ja      short loc_1800021E0
0x1800021dc  movzx   eax, r9b
0x1800021e0  mov     [rcx+18h], eax
0x1800021e3  mov     rax, [rsp+28h+arg_28]
0x1800021e8  mov     [rcx+40h], rax
0x1800021ec  mov     rax, [rsp+28h+arg_20]
0x1800021f1  mov     [rcx+38h], rax
0x1800021f5  mov     rax, [rsp+28h+arg_30]
0x1800021fa  mov     [rcx+48h], rax
0x1800021fe  mov     rax, [rcx]
0x180002201  mov     rax, [rax]
0x180002204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002209  jmp     short loc_180002228
0x18000220b  mov     rax, [rcx]
0x18000220e  mov     rax, [rax+8]
0x180002212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002217  xor     eax, eax
0x180002219  mov     [rbx+8], eax
0x18000221c  mov     [rbx+14h], rax
0x180002220  mov     [rbx+40h], rax
0x180002224  mov     [rbx+38h], rax
0x180002228  xor     eax, eax
0x18000222a  add     rsp, 20h
0x18000222e  pop     rbx
0x18000222f  retn
```
