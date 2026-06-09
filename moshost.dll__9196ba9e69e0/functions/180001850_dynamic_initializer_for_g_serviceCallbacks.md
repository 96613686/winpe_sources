# _dynamic_initializer_for__g_serviceCallbacks__

- ea: `0x180001850`
- end: `0x1800018af`
- name: `_dynamic_initializer_for__g_serviceCallbacks__`
- size: `95`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800020bc`
- `0x18000210c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001860`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001860`

## pseudocode

```c
int dynamic_initializer_for__g_serviceCallbacks__()
{
  _QWORD *v0; // rax

  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  qword_1800180D8 = 0;
  qword_1800180E0 = 0;
  v0 = operator new(0x28u);
  *v0 = v0;
  v0[1] = v0;
  v0[2] = v0;
  *((_WORD *)v0 + 12) = 257;
  qword_1800180D8 = (__int64)v0;
  return atexit(dynamic_atexit_destructor_for__g_serviceCallbacks__);
}

```

## disassembly

```asm
0x180001850  sub     rsp, 28h
0x180001854  xor     r8d, r8d; Flags
0x180001857  xor     edx, edx; dwSpinCount
0x180001859  lea     rcx, CriticalSection; lpCriticalSection
0x180001860  call    cs:__imp_InitializeCriticalSectionEx
0x180001866  nop
0x180001867  mov     cs:qword_1800180D8, 0
0x180001872  mov     cs:qword_1800180E0, 0
0x18000187d  mov     ecx, 28h ; '('; Size
0x180001882  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001887  mov     [rax], rax
0x18000188a  mov     [rax+8], rax
0x18000188e  mov     [rax+10h], rax
0x180001892  mov     word ptr [rax+18h], 101h
0x180001898  mov     cs:qword_1800180D8, rax
0x18000189f  lea     rcx, _dynamic_atexit_destructor_for__g_serviceCallbacks__
0x1800018a6  add     rsp, 28h
0x1800018aa  jmp     atexit
```
