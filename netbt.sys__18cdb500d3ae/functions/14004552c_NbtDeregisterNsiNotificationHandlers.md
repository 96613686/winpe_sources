# NbtDeregisterNsiNotificationHandlers

- ea: `0x14004552c`
- end: `0x140045566`
- name: `NbtDeregisterNsiNotificationHandlers`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002cbc4`

## callees

- `0x14004552c`

## import_xrefs

- `NETIO!NsiDeregisterChangeNotification` at `0x140045549`
- `NETIO!NsiDeregisterChangeNotification` at `0x140045549`

## pseudocode

```c
__int64 NbtDeregisterNsiNotificationHandlers()
{
  __int64 result; // rax

  if ( qword_140038010 )
  {
    result = NsiDeregisterChangeNotification(off_140038000, (unsigned int)dword_140038008);
    qword_140038010 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14004552c  sub     rsp, 28h
0x140045530  mov     r8, cs:qword_140038010
0x140045537  test    r8, r8
0x14004553a  jz      short loc_140045560
0x14004553c  mov     edx, cs:dword_140038008
0x140045542  mov     rcx, cs:off_140038000
0x140045549  call    cs:__imp_NsiDeregisterChangeNotification
0x140045550  nop     dword ptr [rax+rax+00h]
0x140045555  mov     cs:qword_140038010, 0
0x140045560  add     rsp, 28h
0x140045564  retn
```
