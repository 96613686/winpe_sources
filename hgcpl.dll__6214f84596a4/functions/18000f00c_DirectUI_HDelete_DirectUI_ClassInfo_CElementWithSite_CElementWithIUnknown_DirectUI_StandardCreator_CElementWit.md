# DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)

- ea: `0x18000f00c`
- end: `0x18000f033`
- name: `??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z`
- size: `39`
- prototype: `__int64 __fastcall(DirectUI *this)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f210`
- `0x18000f3a0`
- `0x180017220`
- `0x1800172c0`
- `0x180017360`
- `0x180017410`
- `0x180017430`
- `0x180017450`
- `0x180017a78`
- `0x180017b18`
- `0x180017c90`
- `0x180017cb0`

## callees

- `0x180004d4c`
- `0x18001a010`

## pseudocode

```c
void __fastcall DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(
        DirectUI *this)
{
  void *v2; // rdx

  (*(void (__fastcall **)(DirectUI *, _QWORD))(*(_QWORD *)this + 144LL))(this, 0);
  DirectUI::HFree(this, v2);
}

```

## disassembly

```asm
0x18000f00c  push    rbx
0x18000f00e  sub     rsp, 20h
0x18000f012  mov     rax, [rcx]
0x18000f015  xor     edx, edx
0x18000f017  mov     rbx, rcx
0x18000f01a  mov     rax, [rax+90h]
0x18000f021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f026  mov     rcx, rbx; this
0x18000f029  add     rsp, 20h
0x18000f02d  pop     rbx
0x18000f02e  jmp     ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
```
