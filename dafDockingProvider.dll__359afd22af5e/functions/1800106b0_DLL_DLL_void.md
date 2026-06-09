# DLL::~DLL(void)

- ea: `0x1800106b0`
- end: `0x1800106f7`
- name: `??1DLL@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013d88`

## callees

- `0x1800106b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800106d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800106d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800106f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800106b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800106b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800106e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800106e2`

## pseudocode

```c
void __fastcall DLL::~DLL(LPCRITICAL_SECTION lpCriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  EnterCriticalSection(lpCriticalSection);
  DebugInfo = lpCriticalSection[1].DebugInfo;
  --lpCriticalSection[1].LockCount;
  if ( DebugInfo && !lpCriticalSection[1].LockCount )
  {
    FreeLibrary((HMODULE)DebugInfo);
    lpCriticalSection[1].DebugInfo = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800106b0  push    rbx
0x1800106b2  sub     rsp, 20h
0x1800106b6  mov     rbx, rcx
0x1800106b9  call    cs:__imp_EnterCriticalSection
0x1800106bf  mov     rcx, [rbx+28h]; hLibModule
0x1800106c3  dec     dword ptr [rbx+30h]
0x1800106c6  test    rcx, rcx
0x1800106c9  jz      short loc_1800106DF
0x1800106cb  cmp     dword ptr [rbx+30h], 0
0x1800106cf  jnz     short loc_1800106DF
0x1800106d1  call    cs:__imp_FreeLibrary
0x1800106d7  mov     qword ptr [rbx+28h], 0
0x1800106df  mov     rcx, rbx; lpCriticalSection
0x1800106e2  call    cs:__imp_LeaveCriticalSection
0x1800106e8  mov     rcx, rbx
0x1800106eb  add     rsp, 20h
0x1800106ef  pop     rbx
0x1800106f0  jmp     cs:__imp_DeleteCriticalSection
```
