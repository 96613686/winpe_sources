# FeAcquireReadEngineLock

- ea: `0x18003c148`
- end: `0x18003c1cf`
- name: `FeAcquireReadEngineLock`
- size: `135`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18003c670`
- `0x18003d9a8`
- `0x18003da90`
- `0x180040e80`
- `0x1800419d8`
- `0x180041b3c`

## callees

- `0x180007e38`
- `0x180011500`
- `0x18003c148`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c1a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c1a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c161`

## string_xrefs

- `0x18003c1b1`: `FeAcquireReadEngineLock`
- `0x18003c186`: `FeAcquireWriteEngineLock`

## pseudocode

```c
__int64 __fastcall FeAcquireReadEngineLock(__int64 a1, int a2)
{
  __int64 v3; // rdi
  __int64 v4; // rcx

  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
  if ( a2 )
  {
    v4 = *((unsigned int *)gWfpGlobal + 28);
    if ( (_DWORD)v4 == 2 )
    {
      v3 = WfpReportSysErrorAsNtStatus(v4, "FeAcquireWriteEngineLock", 3221225473LL);
      if ( v3 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
        WfpReportError(v3, "FeAcquireReadEngineLock");
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18003c148  mov     [rsp+arg_0], rbx
0x18003c14d  push    rdi
0x18003c14e  sub     rsp, 20h
0x18003c152  mov     rcx, cs:gWfpGlobal
0x18003c159  mov     ebx, edx
0x18003c15b  add     rcx, 8; lpCriticalSection
0x18003c15f  xor     edi, edi
0x18003c161  call    cs:__imp_EnterCriticalSection
0x18003c168  nop     dword ptr [rax+rax+00h]
0x18003c16d  test    ebx, ebx
0x18003c16f  jz      short loc_18003C1C0
0x18003c171  mov     rax, cs:gWfpGlobal
0x18003c178  mov     ecx, [rax+70h]
0x18003c17b  cmp     ecx, 2
0x18003c17e  jnz     short loc_18003C1C0
0x18003c180  mov     r8d, 0C0000001h
0x18003c186  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x18003c18d  call    WfpReportSysErrorAsNtStatus
0x18003c192  mov     rdi, rax
0x18003c195  test    rax, rax
0x18003c198  jz      short loc_18003C1C0
0x18003c19a  mov     rcx, cs:gWfpGlobal
0x18003c1a1  add     rcx, 8; lpCriticalSection
0x18003c1a5  call    cs:__imp_LeaveCriticalSection
0x18003c1ac  nop     dword ptr [rax+rax+00h]
0x18003c1b1  lea     rdx, aFeacquirereade; "FeAcquireReadEngineLock"
0x18003c1b8  mov     rcx, rdi
0x18003c1bb  call    WfpReportError
0x18003c1c0  mov     rbx, [rsp+28h+arg_0]
0x18003c1c5  mov     rax, rdi
0x18003c1c8  add     rsp, 20h
0x18003c1cc  pop     rdi
0x18003c1cd  retn
```
