# CEventLog::CopyRecord(ulong)

- ea: `0x1800153ec`
- end: `0x180015447`
- name: `?CopyRecord@CEventLog@@QEAAPEAU_EVENTLOGRECORD@@K@Z`
- size: `91`
- prototype: `struct _EVENTLOGRECORD *__fastcall(CEventLog *this, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180017ab8`

## callees

- `0x1800153ec`
- `0x18001556c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180015433`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015433`

## pseudocode

```c
struct _EVENTLOGRECORD *__fastcall CEventLog::CopyRecord(CEventLog *this, __int64 a2)
{
  void *v3; // [rsp+30h] [rbp-18h] BYREF
  int v4; // [rsp+60h] [rbp+18h] BYREF
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v5 = 0;
  v4 = 0;
  if ( (int)CEventLog::SeekRead(this, a2, 4, &v3, &v5, &v4) >= 0 )
    return (struct _EVENTLOGRECORD *)v3;
  operator delete[](v3);
  return 0;
}

```

## disassembly

```asm
0x1800153ec  mov     r11, rsp
0x1800153ef  sub     rsp, 48h
0x1800153f3  lea     rax, [r11+18h]
0x1800153f7  mov     qword ptr [r11-18h], 0
0x1800153ff  mov     [r11-20h], rax
0x180015403  lea     r9, [r11-18h]
0x180015407  lea     rax, [r11+20h]
0x18001540b  mov     [rsp+48h+arg_18], 0
0x180015413  mov     r8d, 4
0x180015419  mov     [r11-28h], rax
0x18001541d  mov     [rsp+48h+arg_10], 0
0x180015425  call    ?SeekRead@CEventLog@@QEAAJKW4DIRECTION@@PEAPEAEPEAK2@Z; CEventLog::SeekRead(ulong,DIRECTION,uchar * *,ulong *,ulong *)
0x18001542a  test    eax, eax
0x18001542c  jns     short loc_18001543D
0x18001542e  mov     rcx, [rsp+48h+var_18]
0x180015433  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015439  xor     eax, eax
0x18001543b  jmp     short loc_180015442
0x18001543d  mov     rax, [rsp+48h+var_18]
0x180015442  add     rsp, 48h
0x180015446  retn
```
