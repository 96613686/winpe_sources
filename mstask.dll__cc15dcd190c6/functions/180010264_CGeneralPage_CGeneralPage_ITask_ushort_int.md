# CGeneralPage::CGeneralPage(ITask *,ushort *,int)

- ea: `0x180010264`
- end: `0x18001030f`
- name: `??0CGeneralPage@@QEAA@PEAUITask@@PEAGH@Z`
- size: `171`
- prototype: `CGeneralPage *__fastcall(CGeneralPage *__hidden this, struct ITask *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800105a8`

## callees

- `0x180017f60`
- `0x18001b010`

## pseudocode

```c
CGeneralPage *__fastcall CGeneralPage::CGeneralPage(CGeneralPage *this, struct ITask *a2, unsigned __int16 *a3, int a4)
{
  CPropPage::CPropPage(this, (const unsigned __int16 *)0x191, a3);
  *((_DWORD *)this + 174) &= ~0x20u;
  *(_QWORD *)this = &CGeneralPage::`vftable';
  *((_QWORD *)this + 86) = a2;
  *((_QWORD *)this + 88) = 0;
  *((_DWORD *)this + 178) = a4;
  *((_DWORD *)this + 180) = 0;
  *(_QWORD *)((char *)this + 772) = 1;
  *(_QWORD *)((char *)this + 780) = 0;
  ((void (__fastcall *)(struct ITask *))a2->lpVtbl->AddRef)(a2);
  *((_WORD *)this + 366) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = &String;
  return this;
}

```

## disassembly

```asm
0x180010264  mov     [rsp+arg_0], rbx
0x180010269  mov     [rsp+arg_8], rsi
0x18001026e  push    rdi
0x18001026f  sub     rsp, 20h
0x180010273  mov     rdi, rdx
0x180010276  mov     ebx, r9d
0x180010279  mov     edx, 191h; unsigned __int16 *
0x18001027e  mov     rsi, rcx
0x180010281  call    ??0CPropPage@@QEAA@PEBGPEAG@Z; CPropPage::CPropPage(ushort const *,ushort *)
0x180010286  and     dword ptr [rsi+2B8h], 0FFFFFFDFh
0x18001028d  lea     rax, ??_7CGeneralPage@@6B@; const CGeneralPage::`vftable'
0x180010294  mov     [rsi], rax
0x180010297  mov     rcx, rdi
0x18001029a  mov     [rsi+2B0h], rdi
0x1800102a1  mov     qword ptr [rsi+2C0h], 0
0x1800102ac  mov     [rsi+2C8h], ebx
0x1800102b2  mov     dword ptr [rsi+2D0h], 0
0x1800102bc  mov     qword ptr [rsi+304h], 1
0x1800102c7  mov     qword ptr [rsi+30Ch], 0
0x1800102d2  mov     rax, [rdi]
0x1800102d5  mov     rax, [rax+8]
0x1800102d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102de  mov     rbx, [rsp+28h+arg_0]
0x1800102e3  xor     eax, eax
0x1800102e5  mov     [rsi+2DCh], ax
0x1800102ec  mov     [rsi+298h], rax
0x1800102f3  lea     rax, String
0x1800102fa  mov     [rsi+2A0h], rax
0x180010301  mov     rax, rsi
0x180010304  mov     rsi, [rsp+28h+arg_8]
0x180010309  add     rsp, 20h
0x18001030d  pop     rdi
0x18001030e  retn
```
