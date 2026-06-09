# CMsftDiscMaster2::UnregisterDeviceInterfaceNotification(void)

- ea: `0x1800017cc`
- end: `0x1800017fe`
- name: `?UnregisterDeviceInterfaceNotification@CMsftDiscMaster2@@QEAAXXZ`
- size: `50`
- prototype: `void __fastcall(CMsftDiscMaster2 *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001194`
- `0x180001210`

## callees

- `0x1800017cc`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x1800017dc`
- `ntdll!RtlDllShutdownInProgress` at `0x1800017dc`
- `CFGMGR32!CM_Unregister_Notification` at `0x1800017ea`
- `CFGMGR32!CM_Unregister_Notification` at `0x1800017ea`

## pseudocode

```c
void __fastcall CMsftDiscMaster2::UnregisterDeviceInterfaceNotification(CMsftDiscMaster2 *this)
{
  if ( *((_QWORD *)this + 14) )
  {
    if ( !RtlDllShutdownInProgress() )
    {
      CM_Unregister_Notification(*((_QWORD *)this + 14));
      *((_QWORD *)this + 14) = 0;
    }
  }
}

```

## disassembly

```asm
0x1800017cc  push    rbx
0x1800017ce  sub     rsp, 20h
0x1800017d2  cmp     qword ptr [rcx+70h], 0
0x1800017d7  mov     rbx, rcx
0x1800017da  jz      short loc_1800017F8
0x1800017dc  call    cs:__imp_RtlDllShutdownInProgress
0x1800017e2  test    al, al
0x1800017e4  jnz     short loc_1800017F8
0x1800017e6  mov     rcx, [rbx+70h]
0x1800017ea  call    cs:__imp_CM_Unregister_Notification
0x1800017f0  mov     qword ptr [rbx+70h], 0
0x1800017f8  add     rsp, 20h
0x1800017fc  pop     rbx
0x1800017fd  retn
```
