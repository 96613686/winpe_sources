# MibStatisticsWorker(SnmpVarBind *,uint,_MIB_ENTRY *,_MIB_ENTRIES *,void *)

- ea: `0x180001cd0`
- end: `0x180001d09`
- name: `?MibStatisticsWorker@@YAIPEAUSnmpVarBind@@IPEAU_MIB_ENTRY@@PEAU_MIB_ENTRIES@@PEAX@Z`
- size: `57`
- prototype: `__int64 __fastcall(struct SnmpVarBind *, int, struct _MIB_ENTRY *, struct _MIB_ENTRIES *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001c00`
- `0x180001cd0`

## pseudocode

```c
__int64 __fastcall MibStatisticsWorker(
        struct SnmpVarBind *a1,
        int a2,
        struct _MIB_ENTRY *a3,
        struct _MIB_ENTRIES *a4,
        void *a5)
{
  switch ( a2 )
  {
    case 160:
      goto LABEL_6;
    case 161:
    case 163:
      return MibLeafFunction(&a1->name, a2, (unsigned __int64)a3, (__int64)a4, (__int64)a5);
    case 224:
LABEL_6:
      if ( a5 && *((_DWORD *)a3 + 3) != -1 )
        return MibLeafFunction(&a1->name, a2, (unsigned __int64)a3, (__int64)a4, (__int64)a5);
      break;
  }
  return 5;
}

```

## disassembly

```asm
0x180001cd0  mov     r10, [rsp+arg_20]
0x180001cd5  mov     eax, edx
0x180001cd7  sub     eax, 0A0h
0x180001cdc  jz      short loc_180001CED
0x180001cde  sub     eax, 1
0x180001ce1  jz      short loc_180001CF9
0x180001ce3  sub     eax, 2
0x180001ce6  jz      short loc_180001CF9
0x180001ce8  cmp     eax, 3Dh ; '='
0x180001ceb  jnz     short loc_180001D03
0x180001ced  test    r10, r10
0x180001cf0  jz      short loc_180001D03
0x180001cf2  cmp     dword ptr [r8+0Ch], 0FFFFFFFFh
0x180001cf7  jz      short loc_180001D03
0x180001cf9  mov     [rsp+arg_20], r10; __int64
0x180001cfe  jmp     MibLeafFunction
0x180001d03  mov     eax, 5
0x180001d08  retn
```
