# CThreadData::GetOle32Procs(void)

- ea: `0x1800427ac`
- end: `0x1800427f1`
- name: `?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ`
- size: `69`
- prototype: `struct COLE32_PROC *(void)`
- caller_count: `32`
- callee_count: `2`
- tags: ``

## callers

- `0x18004b3ac`
- `0x18004c338`
- `0x180054750`
- `0x180054a88`
- `0x1800551d0`
- `0x180057498`
- `0x18005c608`
- `0x18005d8d0`
- `0x1800717bc`
- `0x180076438`
- `0x18007e71c`
- `0x18007ef54`
- `0x18007fbac`
- `0x18007fe50`
- `0x18008e9e0`
- `0x18008fd88`
- `0x18008fe00`
- `0x18009253c`
- `0x1800925d4`
- `0x180092670`
- `0x18009270c`
- `0x180092768`
- `0x1800927b8`
- `0x180092814`
- `0x180092870`
- `0x1800928dc`
- `0x180092940`
- `0x180092e64`
- `0x180092ed0`
- `0x180092f2c`
- `0x1800939d0`
- `0x180093a3c`

## callees

- `0x1800427ac`
- `0x1800929e0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800427b7`
- `KERNEL32!EnterCriticalSection` at `0x1800427b7`
- `KERNEL32!LeaveCriticalSection` at `0x1800427d8`
- `KERNEL32!LeaveCriticalSection` at `0x1800427d8`

## pseudocode

```c
struct COLE32_PROC *CThreadData::GetOle32Procs(void)
{
  EnterCriticalSection(&g_CriticalSection);
  if ( !CW32System::_fOleinitCheckDisabled )
    CThreadData::OnOleCall();
  LeaveCriticalSection(&g_CriticalSection);
  return (struct COLE32_PROC *)qword_1800A7080;
}

```

## disassembly

```asm
0x1800427ac  sub     rsp, 28h
0x1800427b0  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800427b7  call    cs:__imp_EnterCriticalSection
0x1800427be  nop     dword ptr [rax+rax+00h]
0x1800427c3  cmp     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, 0; bool CW32System::_fOleinitCheckDisabled
0x1800427ca  jnz     short loc_1800427D1
0x1800427cc  call    ?OnOleCall@CThreadData@@SAXXZ; CThreadData::OnOleCall(void)
0x1800427d1  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800427d8  call    cs:__imp_LeaveCriticalSection
0x1800427df  nop     dword ptr [rax+rax+00h]
0x1800427e4  lea     rax, qword_1800A7080
0x1800427eb  add     rsp, 28h
0x1800427ef  retn
```
