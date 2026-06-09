# Event::Event(bool,bool)

- ea: `0x18000d4e8`
- end: `0x18000d52e`
- name: `??0Event@@QEAA@_N0@Z`
- size: `70`
- prototype: `Event *__fastcall(Event *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dfb0`
- `0x18000ec30`
- `0x18001064c`

## callees

- `0x18000d338`
- `0x18000d4e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d4ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d4ff`

## string_xrefs

- `0x18000d521`: `CreateEventW`

## pseudocode

```c
Event *__fastcall Event::Event(Event *this)
{
  HANDLE EventW; // rax

  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 1) = EventW;
  *(_QWORD *)this = &Event::`vftable';
  if ( !EventW )
    SystemError::Throw(L"CreateEventW");
  return this;
}

```

## disassembly

```asm
0x18000d4e8  mov     [rsp+arg_0], rcx
0x18000d4ed  push    rbx
0x18000d4ee  sub     rsp, 20h
0x18000d4f2  mov     rbx, rcx
0x18000d4f5  xor     r9d, r9d; lpName
0x18000d4f8  xor     r8d, r8d; bInitialState
0x18000d4fb  xor     edx, edx; bManualReset
0x18000d4fd  xor     ecx, ecx; lpEventAttributes
0x18000d4ff  call    cs:__imp_CreateEventW
0x18000d505  mov     [rbx+8], rax
0x18000d509  lea     rcx, ??_7Event@@6B@; const Event::`vftable'
0x18000d510  mov     [rbx], rcx
0x18000d513  test    rax, rax
0x18000d516  jz      short loc_18000D521
0x18000d518  mov     rax, rbx
0x18000d51b  add     rsp, 20h
0x18000d51f  pop     rbx
0x18000d520  retn
0x18000d521  lea     rcx, aCreateeventw; "CreateEventW"
0x18000d528  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
```
