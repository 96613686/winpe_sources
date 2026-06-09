# CProfileTask::_Initialize(void)

- ea: `0x180015abc`
- end: `0x180015af2`
- name: `?_Initialize@CProfileTask@@IEAAJXZ`
- size: `54`
- prototype: `__int64 __fastcall(CProfileTask *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180014fd8`
- `0x1800153c0`

## callees

- `0x180009864`
- `0x180015abc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015ad1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015ad1`

## pseudocode

```c
__int64 __fastcall CProfileTask::_Initialize(CProfileTask *this)
{
  HANDLE EventW; // rax
  UstVarLib *v3; // rcx

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 11) = EventW;
  if ( EventW )
    return 0;
  else
    return UstVarLib::ResultFromLastError(v3);
}

```

## disassembly

```asm
0x180015abc  push    rbx
0x180015abe  sub     rsp, 20h
0x180015ac2  xor     r9d, r9d; lpName
0x180015ac5  mov     rbx, rcx
0x180015ac8  xor     r8d, r8d; bInitialState
0x180015acb  xor     ecx, ecx; lpEventAttributes
0x180015acd  lea     edx, [r9+1]; bManualReset
0x180015ad1  call    cs:__imp_CreateEventW
0x180015ad7  mov     [rbx+58h], rax
0x180015adb  test    rax, rax
0x180015ade  jnz     short loc_180015AEA
0x180015ae0  add     rsp, 20h
0x180015ae4  pop     rbx
0x180015ae5  jmp     ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x180015aea  xor     eax, eax
0x180015aec  add     rsp, 20h
0x180015af0  pop     rbx
0x180015af1  retn
```
