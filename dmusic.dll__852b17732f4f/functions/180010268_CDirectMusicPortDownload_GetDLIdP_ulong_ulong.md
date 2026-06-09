# CDirectMusicPortDownload::GetDLIdP(ulong *,ulong)

- ea: `0x180010268`
- end: `0x1800102ac`
- name: `?GetDLIdP@CDirectMusicPortDownload@@SAXPEAKK@Z`
- size: `68`
- prototype: `void __fastcall(unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b730`
- `0x18000b918`
- `0x18000f030`
- `0x180010230`
- `0x180017cfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001027e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001027e`

## pseudocode

```c
void __fastcall CDirectMusicPortDownload::GetDLIdP(unsigned int *a1, int a2)
{
  unsigned int v4; // eax

  EnterCriticalSection(&CDirectMusicPortDownload::sDMDLCriticalSection);
  v4 = CDirectMusicPortDownload::sNextDLId;
  *a1 = CDirectMusicPortDownload::sNextDLId;
  CDirectMusicPortDownload::sNextDLId = a2 + v4;
  LeaveCriticalSection(&CDirectMusicPortDownload::sDMDLCriticalSection);
}

```

## disassembly

```asm
0x180010268  mov     [rsp+arg_0], rbx
0x18001026d  push    rdi
0x18001026e  sub     rsp, 20h
0x180010272  mov     rbx, rcx
0x180010275  mov     edi, edx
0x180010277  lea     rcx, ?sDMDLCriticalSection@CDirectMusicPortDownload@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001027e  call    cs:__imp_EnterCriticalSection
0x180010284  mov     eax, cs:?sNextDLId@CDirectMusicPortDownload@@2KA; ulong CDirectMusicPortDownload::sNextDLId
0x18001028a  lea     rcx, ?sDMDLCriticalSection@CDirectMusicPortDownload@@2U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CDirectMusicPortDownload::sDMDLCriticalSection
0x180010291  mov     [rbx], eax
0x180010293  add     eax, edi
0x180010295  mov     cs:?sNextDLId@CDirectMusicPortDownload@@2KA, eax; ulong CDirectMusicPortDownload::sNextDLId
0x18001029b  mov     rbx, [rsp+28h+arg_0]
0x1800102a0  add     rsp, 20h
0x1800102a4  pop     rdi
0x1800102a5  jmp     cs:__imp_LeaveCriticalSection
```
