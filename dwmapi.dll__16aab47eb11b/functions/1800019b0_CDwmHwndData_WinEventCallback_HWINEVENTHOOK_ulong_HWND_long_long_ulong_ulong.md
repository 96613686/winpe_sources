# CDwmHwndData::WinEventCallback(HWINEVENTHOOK__ *,ulong,HWND__ *,long,long,ulong,ulong)

- ea: `0x1800019b0`
- end: `0x1800019fe`
- name: `?WinEventCallback@CDwmHwndData@@CAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z`
- size: `78`
- prototype: `void __stdcall(HWINEVENTHOOK hWinEventHook, DWORD event, HWND hwnd, LONG idObject, LONG idChild, DWORD idEventThread, DWORD dwmsEventTime)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001008`
- `0x1800019b0`
- `0x180002e90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800019ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800019ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800019d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800019d2`

## pseudocode

```c
void __fastcall CDwmHwndData::WinEventCallback(HWINEVENTHOOK hWinEventHook, DWORD event, HWND hwnd, LONG idObject)
{
  if ( event == 32769 && !idObject )
  {
    EnterCriticalSection(&CDwmHwndData::s_cs);
    if ( CDwmHwndData::FindElement(hwnd) )
      CDwmHwndData::RemoveElement((__int64)hwnd);
    LeaveCriticalSection(&CDwmHwndData::s_cs);
  }
}

```

## disassembly

```asm
0x1800019b0  cmp     edx, 8001h
0x1800019b6  jnz     short locret_1800019CA
0x1800019b8  push    rbx
0x1800019b9  sub     rsp, 20h
0x1800019bd  mov     rbx, r8
0x1800019c0  test    r9d, r9d
0x1800019c3  jz      short loc_1800019CB
0x1800019c5  add     rsp, 20h
0x1800019c9  pop     rbx
0x1800019ca  retn
0x1800019cb  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x1800019d2  call    cs:__imp_EnterCriticalSection
0x1800019d8  mov     rcx, rbx; HWND
0x1800019db  call    ?FindElement@CDwmHwndData@@SAPEAV1@PEAUHWND__@@@Z; CDwmHwndData::FindElement(HWND__ *)
0x1800019e0  test    rax, rax
0x1800019e3  jnz     short loc_1800019F4
0x1800019e5  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x1800019ec  call    cs:__imp_LeaveCriticalSection
0x1800019f2  jmp     short loc_1800019C5
0x1800019f4  mov     rcx, rbx; HWND
0x1800019f7  call    ?RemoveElement@CDwmHwndData@@CA_NPEAUHWND__@@@Z; CDwmHwndData::RemoveElement(HWND__ *)
0x1800019fc  jmp     short loc_1800019E5
```
