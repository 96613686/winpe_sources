# CLoadDui::~CLoadDui(void)

- ea: `0x180003788`
- end: `0x1800037bd`
- name: `??1CLoadDui@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CLoadDui *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800025cc`

## callees

- `0x180003788`

## import_xrefs

- `DUI70!UnInitThread` at `0x1800037b1`
- `DUI70!UnInitThread` at `0x1800037b1`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000379a`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000379a`

## pseudocode

```c
void __fastcall CLoadDui::~CLoadDui(CLoadDui *this)
{
  DirectUI::DUIXmlParser *v2; // rcx

  v2 = (DirectUI::DUIXmlParser *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    DirectUI::DUIXmlParser::Destroy(v2);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *((_DWORD *)this + 45) )
    UnInitThread();
}

```

## disassembly

```asm
0x180003788  push    rbx
0x18000378a  sub     rsp, 20h
0x18000378e  mov     rbx, rcx
0x180003791  mov     rcx, [rcx+8]
0x180003795  test    rcx, rcx
0x180003798  jz      short loc_1800037A8
0x18000379a  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800037a0  mov     qword ptr [rbx+8], 0
0x1800037a8  cmp     dword ptr [rbx+0B4h], 0
0x1800037af  jz      short loc_1800037B7
0x1800037b1  call    cs:__imp_UnInitThread
0x1800037b7  add     rsp, 20h
0x1800037bb  pop     rbx
0x1800037bc  retn
```
