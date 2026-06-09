# CSchedulePage::CSchedulePage(ITask *,ushort *,int,int)

- ea: `0x180012c38`
- end: `0x180012d26`
- name: `??0CSchedulePage@@QEAA@PEAUITask@@PEAGHH@Z`
- size: `238`
- prototype: `CSchedulePage *__fastcall(CSchedulePage *__hidden this, struct ITask *, unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180012fe8`

## callees

- `0x180017f60`
- `0x18001b010`

## pseudocode

```c
CSchedulePage *__fastcall CSchedulePage::CSchedulePage(
        CSchedulePage *this,
        struct ITask *a2,
        unsigned __int16 *a3,
        int a4,
        int a5)
{
  CPropPage::CPropPage(this, (const unsigned __int16 *)0x192, a3);
  *((_QWORD *)this + 83) = a2;
  *((_QWORD *)this + 84) = 0;
  *(_QWORD *)this = &CSchedulePage::`vftable';
  *((_QWORD *)this + 85) = &CJobTriggerList::`vftable';
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = &CJobTriggerList::`vftable';
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_DWORD *)this + 191) = a5;
  *((_QWORD *)this + 91) = 0;
  *((_DWORD *)this + 184) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_DWORD *)this + 188) = 0;
  *((_DWORD *)this + 192) = 0;
  *((_DWORD *)this + 185) = -1;
  *((_DWORD *)this + 190) = a4;
  *((_QWORD *)this + 104) = &CSelectMonth::`vftable';
  *((_WORD *)this + 424) = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 83) + 8LL))(*((_QWORD *)this + 83));
  *((_DWORD *)this + 189) = *((_DWORD *)this + 190);
  return this;
}

```

## disassembly

```asm
0x180012c38  mov     [rsp+arg_0], rbx
0x180012c3d  mov     [rsp+arg_8], rsi
0x180012c42  push    rdi
0x180012c43  sub     rsp, 20h
0x180012c47  mov     rbx, rdx
0x180012c4a  mov     edi, r9d
0x180012c4d  mov     edx, 192h; unsigned __int16 *
0x180012c52  mov     rsi, rcx
0x180012c55  call    ??0CPropPage@@QEAA@PEBGPEAG@Z; CPropPage::CPropPage(ushort const *,ushort *)
0x180012c5a  xor     ecx, ecx
0x180012c5c  mov     [rsi+298h], rbx
0x180012c63  mov     [rsi+2A0h], rcx
0x180012c6a  lea     rax, ??_7CSchedulePage@@6B@; const CSchedulePage::`vftable'
0x180012c71  mov     [rsi], rax
0x180012c74  lea     rax, ??_7CJobTriggerList@@6B@; const CJobTriggerList::`vftable'
0x180012c7b  mov     [rsi+2A8h], rax
0x180012c82  mov     [rsi+2B0h], rcx
0x180012c89  mov     [rsi+2B8h], rcx
0x180012c90  mov     [rsi+2C0h], rax
0x180012c97  mov     eax, [rsp+28h+arg_20]
0x180012c9b  mov     [rsi+2C8h], rcx
0x180012ca2  mov     [rsi+2D0h], rcx
0x180012ca9  mov     [rsi+2FCh], eax
0x180012caf  lea     rax, ??_7CSelectMonth@@6B@; const CSelectMonth::`vftable'
0x180012cb6  mov     [rsi+2D8h], rcx
0x180012cbd  mov     [rsi+2E0h], ecx
0x180012cc3  mov     [rsi+2E8h], rcx
0x180012cca  mov     [rsi+2F0h], ecx
0x180012cd0  mov     [rsi+300h], ecx
0x180012cd6  mov     dword ptr [rsi+2E4h], 0FFFFFFFFh
0x180012ce0  mov     [rsi+2F8h], edi
0x180012ce6  mov     [rsi+340h], rax
0x180012ced  mov     [rsi+350h], cx
0x180012cf4  mov     rcx, [rsi+298h]
0x180012cfb  mov     rax, [rcx]
0x180012cfe  mov     rax, [rax+8]
0x180012d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d07  mov     eax, [rsi+2F8h]
0x180012d0d  mov     rbx, [rsp+28h+arg_0]
0x180012d12  mov     [rsi+2F4h], eax
0x180012d18  mov     rax, rsi
0x180012d1b  mov     rsi, [rsp+28h+arg_8]
0x180012d20  add     rsp, 20h
0x180012d24  pop     rdi
0x180012d25  retn
```
