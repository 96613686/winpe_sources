# PerfDiagDm::DuiHelper::GetDuiContent(int)

- ea: `0x1800bdb2c`
- end: `0x1800bdb88`
- name: `?GetDuiContent@DuiHelper@PerfDiagDm@@QEAAPEAUIUnknown@@H@Z`
- size: `92`
- prototype: `struct IUnknown *__fastcall(PerfDiagDm::DuiHelper *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800bdb90`
- `0x1800bdf10`

## callees

- `0x1800bdb2c`
- `0x1800be794`

## import_xrefs

- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1800bdb61`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1800bdb61`
- `DUI70!CreateDUIWrapper` at `0x1800bdb6f`
- `DUI70!CreateDUIWrapper` at `0x1800bdb6f`

## pseudocode

```c
struct IUnknown *__fastcall PerfDiagDm::DuiHelper::GetDuiContent(
        PerfDiagDm::DuiHelper *this,
        __int64 a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  v6 = 0;
  if ( (int)PerfDiagDm::DuiHelper::LoadResource(this, a2, a3, &v6, (struct DirectUI::Element **)this) < 0 )
    return 0;
  DirectUI::Element::EndDefer(*(DirectUI::Element **)this, v6);
  if ( (int)CreateDUIWrapper(*(_QWORD *)this, &v5) < 0 )
    return 0;
  else
    return (struct IUnknown *)v5;
}

```

## disassembly

```asm
0x1800bdb2c  mov     rax, rsp
0x1800bdb2f  mov     [rax+10h], edx
0x1800bdb32  push    rbx
0x1800bdb33  sub     rsp, 30h
0x1800bdb37  lea     r9, [rax+10h]; unsigned int *
0x1800bdb3b  mov     qword ptr [rax+8], 0
0x1800bdb43  mov     rbx, rcx
0x1800bdb46  mov     dword ptr [rax+10h], 0
0x1800bdb4d  mov     [rax-18h], rcx
0x1800bdb51  call    ?LoadResource@DuiHelper@PerfDiagDm@@AEAAJHPEBGPEAKPEAPEAVElement@DirectUI@@@Z; PerfDiagDm::DuiHelper::LoadResource(int,ushort const *,ulong *,DirectUI::Element * *)
0x1800bdb56  test    eax, eax
0x1800bdb58  js      short loc_1800BDB80
0x1800bdb5a  mov     edx, [rsp+38h+arg_8]
0x1800bdb5e  mov     rcx, [rbx]
0x1800bdb61  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x1800bdb67  mov     rcx, [rbx]
0x1800bdb6a  lea     rdx, [rsp+38h+arg_0]
0x1800bdb6f  call    cs:__imp_CreateDUIWrapper
0x1800bdb75  test    eax, eax
0x1800bdb77  js      short loc_1800BDB80
0x1800bdb79  mov     rax, [rsp+38h+arg_0]
0x1800bdb7e  jmp     short loc_1800BDB82
0x1800bdb80  xor     eax, eax
0x1800bdb82  add     rsp, 30h
0x1800bdb86  pop     rbx
0x1800bdb87  retn
```
