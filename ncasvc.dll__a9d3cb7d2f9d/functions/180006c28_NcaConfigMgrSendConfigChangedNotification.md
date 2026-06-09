# NcaConfigMgrSendConfigChangedNotification

- ea: `0x180006c28`
- end: `0x180006c56`
- name: `NcaConfigMgrSendConfigChangedNotification`
- size: `46`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005c20`
- `0x180006190`

## callees

- `0x180007238`

## pseudocode

```c
__int64 NcaConfigMgrSendConfigChangedNotification()
{
  _DWORD v1[2]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v2; // [rsp+28h] [rbp-10h]

  v2 = 0;
  v1[0] = 0;
  v1[1] = 1;
  return NcaApiSrvImplNotifySubscriptions((struct NCA_STATUS_EVENT_ *)v1, 0);
}

```

## disassembly

```asm
0x180006c28  mov     rax, rsp
0x180006c2b  sub     rsp, 38h
0x180006c2f  xor     edx, edx; struct NCA_DAP_USER_EVSNPSHT_ *
0x180006c31  mov     qword ptr [rax-10h], 0
0x180006c39  lea     rcx, [rax-18h]; struct NCA_STATUS_EVENT_ *
0x180006c3d  mov     dword ptr [rax-18h], 0
0x180006c44  mov     dword ptr [rax-14h], 1
0x180006c4b  call    ?NcaApiSrvImplNotifySubscriptions@@YAKPEAUNCA_STATUS_EVENT_@@PEAUNCA_DAP_USER_EVSNPSHT_@@@Z; NcaApiSrvImplNotifySubscriptions(NCA_STATUS_EVENT_ *,NCA_DAP_USER_EVSNPSHT_ *)
0x180006c50  add     rsp, 38h
0x180006c54  retn
```
