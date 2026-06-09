# ScopedWatchdogTimer::WaitCallback(void *,uchar)

- ea: `0x180007090`
- end: `0x1800070cd`
- name: `?WaitCallback@ScopedWatchdogTimer@@SAXPEAXE@Z`
- size: `61`
- prototype: `void __fastcall(void (**)(void), char)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007090`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800070b9`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800070b9`

## string_xrefs

- `0x18000709c`: `ScopedWatchdogTimer - operation in thread 0x%08x timed out`

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
0x180007090  test    dl, dl
0x180007092  jz      short locret_1800070CC
0x180007094  push    rbx
0x180007095  sub     rsp, 30h
0x180007099  mov     eax, [rcx+8]
0x18000709c  lea     r9, aScopedwatchdog_0; "ScopedWatchdogTimer - operation in thre"...
0x1800070a3  mov     rbx, rcx
0x1800070a6  mov     [rsp+38h+var_18], eax
0x1800070aa  xor     ecx, ecx
0x1800070ac  lea     rdx, aScopedwatchdog_1; "ScopedWatchdogTimer::WaitCallback"
0x1800070b3  mov     r8d, 16h
0x1800070b9  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800070bf  mov     rax, [rbx]
0x1800070c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070c7  add     rsp, 30h
0x1800070cb  pop     rbx
0x1800070cc  retn
```
