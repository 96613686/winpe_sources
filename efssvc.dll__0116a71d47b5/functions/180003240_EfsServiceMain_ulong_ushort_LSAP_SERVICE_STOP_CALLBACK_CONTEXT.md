# EfsServiceMain(ulong,ushort * *,_LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)

- ea: `0x180003240`
- end: `0x180003259`
- name: `?EfsServiceMain@@YAJKPEAPEAGPEAU_LSAP_SERVICE_STOP_CALLBACK_CONTEXT@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **, struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002ee0`

## pseudocode

```c
__int64 __fastcall EfsServiceMain(__int64 a1, unsigned __int16 **a2, struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *a3)
{
  return ((int)CEfsService::StartServiceW(a3) >> 31) & 0xC00000E5;
}

```

## disassembly

```asm
0x180003240  sub     rsp, 28h
0x180003244  mov     rcx, r8; struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *
0x180003247  call    ?StartServiceW@CEfsService@@SAJPEAU_LSAP_SERVICE_STOP_CALLBACK_CONTEXT@@@Z; CEfsService::StartServiceW(_LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)
0x18000324c  sar     eax, 1Fh
0x18000324f  and     eax, 0C00000E5h
0x180003254  add     rsp, 28h
0x180003258  retn
```
