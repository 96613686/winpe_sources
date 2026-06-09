# PpfState::PpfState(void)

- ea: `0x18000f300`
- end: `0x18000f3b8`
- name: `??0PpfState@@QEAA@XZ`
- size: `184`
- prototype: `PpfState *__fastcall(PpfState *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180013ef4`
- `0x1800141f4`
- `0x180015ff8`
- `0x180016498`

## callees

- `0x18000367c`
- `0x1800351d0`
- `0x180036f08`

## string_xrefs

- `0x18000f356`: `PpfScheduledTaskMain`
- `0x18000f348`: `PCR Prediction Framework Scheduled Task`

## pseudocode

```c
PpfState *__fastcall PpfState::PpfState(PpfState *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  PpfTransformStore::PpfTransformStore((PpfState *)((char *)this + 16));
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  v2 = operator new(0x30u);
  *v2 = v2;
  v2[1] = v2;
  *((_QWORD *)this + 15) = v2;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 18) = L"PCR Prediction Framework Scheduled Task";
  *((_QWORD *)this + 19) = L"PpfScheduledTaskMain";
  *((_DWORD *)this + 40) = 0;
  PpfEventLogProviderRegistration::PpfEventLogProviderRegistration((PpfState *)((char *)this + 164));
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  v3 = operator new(0x30u);
  *v3 = v3;
  v3[1] = v3;
  *((_QWORD *)this + 23) = v3;
  return this;
}

```

## disassembly

```asm
0x18000f300  mov     [rsp+arg_8], rbx
0x18000f305  mov     [rsp+arg_0], rcx
0x18000f30a  push    rsi
0x18000f30b  sub     rsp, 20h
0x18000f30f  mov     rbx, rcx
0x18000f312  xor     esi, esi
0x18000f314  mov     [rcx], rsi
0x18000f317  mov     [rcx+8], esi
0x18000f31a  add     rcx, 10h; this
0x18000f31e  call    ??0PpfTransformStore@@QEAA@XZ; PpfTransformStore::PpfTransformStore(void)
0x18000f323  nop
0x18000f324  mov     [rbx+78h], rsi
0x18000f328  mov     [rbx+80h], rsi
0x18000f32f  lea     ecx, [rsi+30h]; Size
0x18000f332  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f337  mov     [rax], rax
0x18000f33a  mov     [rax+8], rax
0x18000f33e  mov     [rbx+78h], rax
0x18000f342  mov     [rbx+88h], esi
0x18000f348  lea     rax, aPcrPredictionF; "PCR Prediction Framework Scheduled Task"
0x18000f34f  mov     [rbx+90h], rax
0x18000f356  lea     rax, aPpfscheduledta_0; "PpfScheduledTaskMain"
0x18000f35d  mov     [rbx+98h], rax
0x18000f364  mov     [rbx+0A0h], esi
0x18000f36a  lea     rcx, [rbx+0A4h]; this
0x18000f371  call    ??0PpfEventLogProviderRegistration@@QEAA@XZ; PpfEventLogProviderRegistration::PpfEventLogProviderRegistration(void)
0x18000f376  nop
0x18000f377  mov     [rbx+0A8h], rsi
0x18000f37e  mov     [rbx+0B0h], rsi
0x18000f385  mov     [rbx+0B8h], rsi
0x18000f38c  mov     [rbx+0C0h], rsi
0x18000f393  lea     ecx, [rsi+30h]; Size
0x18000f396  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f39b  mov     [rax], rax
0x18000f39e  mov     [rax+8], rax
0x18000f3a2  mov     [rbx+0B8h], rax
0x18000f3a9  mov     rax, rbx
0x18000f3ac  mov     rbx, [rsp+28h+arg_8]
0x18000f3b1  add     rsp, 20h
0x18000f3b5  pop     rsi
0x18000f3b6  retn
```
