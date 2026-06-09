# CAboSink::SinkConfigurationChange(ulong,_MD_CHANGE_OBJECT_W *)

- ea: `0x180009770`
- end: `0x1800097de`
- name: `?SinkConfigurationChange@CAboSink@@UEAAJKPEAU_MD_CHANGE_OBJECT_W@@@Z`
- size: `110`
- prototype: `int(CAboSink *__hidden this, unsigned int, struct _MD_CHANGE_OBJECT_W *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003590`
- `0x180009770`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800097cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800097cb`
- `KERNEL32!EnterCriticalSection` at `0x180009789`
- `KERNEL32!EnterCriticalSection` at `0x180009789`

## pseudocode

```c
__int64 __fastcall CAboSink::SinkConfigurationChange(CAboSink *this, unsigned int a2, struct _MD_CHANGE_OBJECT_W *a3)
{
  int NewContext; // edi
  struct _LIST_ENTRY *i; // rbx

  NewContext = 0;
  EnterCriticalSection(&CADMCOMW::sm_csObjectListLock);
  for ( i = CADMCOMW::sm_ObjectList.Flink; i != &CADMCOMW::sm_ObjectList; i = i->Flink )
  {
    NewContext = CADMCOMW::CreateNewContext((CADMCOMW *)&i[-9], a2, a3, 1);
    if ( NewContext < 0 )
      break;
  }
  LeaveCriticalSection(&CADMCOMW::sm_csObjectListLock);
  return (unsigned int)NewContext;
}

```

## disassembly

```asm
0x180009770  push    rbx
0x180009772  push    rbp
0x180009773  push    rsi
0x180009774  push    rdi
0x180009775  push    r14
0x180009777  sub     rsp, 20h
0x18000977b  xor     edi, edi
0x18000977d  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009784  mov     rsi, r8
0x180009787  mov     ebp, edx
0x180009789  call    cs:__imp_EnterCriticalSection
0x18000978f  mov     rbx, qword ptr cs:?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x180009796  lea     r14, ?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x18000979d  jmp     short loc_1800097BF
0x18000979f  lea     rcx, [rbx-90h]; this
0x1800097a6  mov     r9d, 1; int
0x1800097ac  mov     r8, rsi; struct _MD_CHANGE_OBJECT_W *
0x1800097af  mov     edx, ebp; unsigned int
0x1800097b1  call    ?CreateNewContext@CADMCOMW@@AEAAJKPEAU_MD_CHANGE_OBJECT_W@@H@Z; CADMCOMW::CreateNewContext(ulong,_MD_CHANGE_OBJECT_W *,int)
0x1800097b6  mov     edi, eax
0x1800097b8  test    eax, eax
0x1800097ba  js      short loc_1800097C4
0x1800097bc  mov     rbx, [rbx]
0x1800097bf  cmp     rbx, r14
0x1800097c2  jnz     short loc_18000979F
0x1800097c4  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800097cb  call    cs:__imp_LeaveCriticalSection
0x1800097d1  mov     eax, edi
0x1800097d3  add     rsp, 20h
0x1800097d7  pop     r14
0x1800097d9  pop     rdi
0x1800097da  pop     rsi
0x1800097db  pop     rbp
0x1800097dc  pop     rbx
0x1800097dd  retn
```
