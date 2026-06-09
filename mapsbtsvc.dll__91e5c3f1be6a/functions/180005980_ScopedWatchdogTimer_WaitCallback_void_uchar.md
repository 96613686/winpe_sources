# ScopedWatchdogTimer::WaitCallback(void *,uchar)

- ea: `0x180005980`
- end: `0x1800059bd`
- name: `?WaitCallback@ScopedWatchdogTimer@@SAXPEAXE@Z`
- size: `61`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005980`
- `0x180015010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800059a9`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800059a9`

## string_xrefs

- `0x18000598c`: `ScopedWatchdogTimer - operation in thread 0x%08x timed out`

## pseudocode

```c
void __fastcall ScopedWatchdogTimer::WaitCallback(void (**a1)(void), char a2)
{
  if ( a2 )
  {
    ZTraceHelperNoThis(
      0,
      "ScopedWatchdogTimer::WaitCallback",
      22,
      "ScopedWatchdogTimer - operation in thread 0x%08x timed out",
      *((_DWORD *)a1 + 2));
    (*a1)();
  }
}

```

## disassembly

```asm
0x180005980  test    dl, dl
0x180005982  jz      short locret_1800059BC
0x180005984  push    rbx
0x180005985  sub     rsp, 30h
0x180005989  mov     eax, [rcx+8]
0x18000598c  lea     r9, aScopedwatchdog_0; "ScopedWatchdogTimer - operation in thre"...
0x180005993  mov     rbx, rcx
0x180005996  mov     [rsp+38h+var_18], eax
0x18000599a  xor     ecx, ecx
0x18000599c  lea     rdx, aScopedwatchdog_1; "ScopedWatchdogTimer::WaitCallback"
0x1800059a3  mov     r8d, 16h
0x1800059a9  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800059af  mov     rax, [rbx]
0x1800059b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b7  add     rsp, 30h
0x1800059bb  pop     rbx
0x1800059bc  retn
```
