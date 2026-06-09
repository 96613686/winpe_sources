# EfsServiceMain(ulong,ushort * *,_LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)

- ea: `0x180003370`
- end: `0x18000338a`
- name: `?EfsServiceMain@@YAJKPEAPEAGPEAU_LSAP_SERVICE_STOP_CALLBACK_CONTEXT@@@Z`
- size: `26`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **, struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002fb0`

## pseudocode

```c
__int64 __fastcall EfsServiceMain(__int64 a1, unsigned __int16 **a2, struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *a3)
{
  return ((int)CEfsService::StartServiceW(a3) >> 31) & 0xC00000E5;
}

```

## disassembly

```asm
0x180003370  sub     rsp, 28h
0x180003374  mov     rcx, r8; struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *
0x180003377  call    ?StartServiceW@CEfsService@@SAJPEAU_LSAP_SERVICE_STOP_CALLBACK_CONTEXT@@@Z; CEfsService::StartServiceW(_LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)
0x18000337c  sar     eax, 1Fh
0x18000337f  and     eax, 0C00000E5h
0x180003384  add     rsp, 28h
0x180003388  retn
```
