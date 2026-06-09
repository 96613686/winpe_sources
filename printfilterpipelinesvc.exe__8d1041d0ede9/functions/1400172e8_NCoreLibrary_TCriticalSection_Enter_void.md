# NCoreLibrary::TCriticalSection::Enter(void)

- ea: `0x1400172e8`
- end: `0x140017309`
- name: `?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ`
- size: `33`
- prototype: `void __fastcall(NCoreLibrary::TCriticalSection *__hidden this)`
- caller_count: `55`
- callee_count: `0`
- tags: ``

## callers

- `0x140016f70`
- `0x140017200`
- `0x140017340`
- `0x140017570`
- `0x140017b80`
- `0x140017c94`
- `0x140017f24`
- `0x1400182a0`
- `0x140018660`
- `0x140018754`
- `0x140018894`
- `0x1400189b0`
- `0x1400192d8`
- `0x1400194a0`
- `0x140019b1c`
- `0x140019ef0`
- `0x14001a3d0`
- `0x14001a620`
- `0x14001cce4`
- `0x14001cd70`
- `0x14001d970`
- `0x14001f220`
- `0x14001f534`
- `0x14001f6e0`
- `0x1400201a0`
- `0x140021bf0`
- `0x140021e4c`
- `0x140022110`
- `0x1400223e0`
- `0x140022514`
- `0x140022dd0`
- `0x140023880`
- `0x14002bf6c`
- `0x14002c3e0`
- `0x14002dd30`
- `0x14002ede8`
- `0x14002f4b0`
- `0x1400307e4`
- `0x140035d68`
- `0x140038508`
- `0x1400388a0`
- `0x14003a34c`
- `0x14003b19c`
- `0x14003b2c8`
- `0x14003f740`
- `0x140040a40`
- `0x1400430a8`
- `0x1400431dc`
- `0x1400459a4`
- `0x14005c600`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400172fa`
- `KERNEL32!GetCurrentThreadId` at `0x1400172fa`
- `KERNEL32!EnterCriticalSection` at `0x1400172f1`
- `KERNEL32!EnterCriticalSection` at `0x1400172f1`

## pseudocode

```c
void __fastcall NCoreLibrary::TCriticalSection::Enter(struct _RTL_CRITICAL_SECTION *this)
{
  EnterCriticalSection(this);
  ++HIDWORD(this[1].DebugInfo);
  LODWORD(this[1].DebugInfo) = GetCurrentThreadId();
}

```

## disassembly

```asm
0x1400172e8  push    rbx
0x1400172ea  sub     rsp, 20h
0x1400172ee  mov     rbx, rcx
0x1400172f1  call    cs:__imp_EnterCriticalSection
0x1400172f7  inc     dword ptr [rbx+2Ch]
0x1400172fa  call    cs:__imp_GetCurrentThreadId
0x140017300  mov     [rbx+28h], eax
0x140017303  add     rsp, 20h
0x140017307  pop     rbx
0x140017308  retn
```
