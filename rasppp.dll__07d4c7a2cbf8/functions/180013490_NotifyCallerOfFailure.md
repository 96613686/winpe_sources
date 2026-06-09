# NotifyCallerOfFailure

- ea: `0x180013490`
- end: `0x1800134bc`
- name: `NotifyCallerOfFailure`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000419c`
- `0x180004388`
- `0x18000aed4`
- `0x18000b310`
- `0x18000c4ac`
- `0x18000e364`
- `0x18000e86c`
- `0x180015320`
- `0x180015ae0`
- `0x180016d40`
- `0x180017990`

## callees

- `0x180012dcc`

## pseudocode

```c
ULONG __fastcall NotifyCallerOfFailure(__int64 a1, unsigned int a2)
{
  int v2; // eax
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = a2;
  v2 = *(_DWORD *)(a1 + 56);
  *(_DWORD *)(a1 + 48) = 0;
  return NotifyCaller(a1, (v2 & 4) != 0 ? 20 : 1, &v4);
}

```

## disassembly

```asm
0x180013490  mov     [rsp+arg_8], edx
0x180013494  sub     rsp, 28h
0x180013498  mov     eax, [rcx+38h]
0x18001349b  lea     r8, [rsp+28h+arg_8]
0x1800134a0  and     al, 4
0x1800134a2  mov     dword ptr [rcx+30h], 0
0x1800134a9  neg     al
0x1800134ab  sbb     edx, edx
0x1800134ad  and     edx, 13h
0x1800134b0  inc     edx
0x1800134b2  call    NotifyCaller
0x1800134b7  add     rsp, 28h
0x1800134bb  retn
```
