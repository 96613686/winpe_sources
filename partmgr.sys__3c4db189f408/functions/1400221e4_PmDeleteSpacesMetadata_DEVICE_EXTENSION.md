# PmDeleteSpacesMetadata(_DEVICE_EXTENSION *)

- ea: `0x1400221e4`
- end: `0x1400222b4`
- name: `?PmDeleteSpacesMetadata@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x14001d830`

## callees

- `0x14000df60`
- `0x14000f0f8`
- `0x14000f2a8`
- `0x14000f394`
- `0x14000f5ac`
- `0x140010f20`
- `0x140020240`
- `0x1400221e4`

## pseudocode

```c
__int64 __fastcall PmDeleteSpacesMetadata(struct _DEVICE_EXTENSION *a1)
{
  int updated; // ebx
  _QWORD v4[74]; // [rsp+30h] [rbp-278h] BYREF
  __int64 v5; // [rsp+280h] [rbp-28h]

  SC_DRIVE::SC_DRIVE((SC_DRIVE *)v4);
  v5 = 0;
  v4[0] = &PM_DRIVE::`vftable';
  updated = PM_DRIVE::Initialize((PM_DRIVE *)v4, a1);
  if ( updated >= 0 )
  {
    updated = SC_DRIVE::DeleteMetadata((SC_DRIVE *)v4);
    if ( updated >= 0 )
    {
      updated = SC_DISK::UpdateControl((SC_DISK *)v4);
      if ( updated >= 0 )
        updated = PmSendIO(*(PDEVICE_OBJECT *)(v5 + 8), 9u, 0, 0, 0);
    }
  }
  v4[0] = &PM_DRIVE::`vftable';
  SC_DRIVE::~SC_DRIVE((SC_DRIVE *)v4);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400221e4  mov     [rsp+arg_0], rbx
0x1400221e9  push    rdi
0x1400221ea  sub     rsp, 2A0h
0x1400221f1  mov     rax, cs:__security_cookie
0x1400221f8  xor     rax, rsp
0x1400221fb  mov     [rsp+2A8h+var_18], rax
0x140022203  mov     rbx, rcx
0x140022206  lea     rcx, [rsp+2A8h+var_278]; this
0x14002220b  call    ??0SC_DRIVE@@QEAA@XZ; SC_DRIVE::SC_DRIVE(void)
0x140022210  lea     rdi, ??_7PM_DRIVE@@6B@; const PM_DRIVE::`vftable'
0x140022217  mov     [rsp+2A8h+var_28], 0
0x140022223  mov     rdx, rbx; struct _DEVICE_EXTENSION *
0x140022226  mov     [rsp+2A8h+var_278], rdi
0x14002222b  lea     rcx, [rsp+2A8h+var_278]; this
0x140022230  call    ?Initialize@PM_DRIVE@@QEAAJPEAU_DEVICE_EXTENSION@@@Z; PM_DRIVE::Initialize(_DEVICE_EXTENSION *)
0x140022235  mov     ebx, eax
0x140022237  test    eax, eax
0x140022239  js      short loc_140022281
0x14002223b  lea     rcx, [rsp+2A8h+var_278]; this
0x140022240  call    ?DeleteMetadata@SC_DRIVE@@QEAAJXZ; SC_DRIVE::DeleteMetadata(void)
0x140022245  mov     ebx, eax
0x140022247  test    eax, eax
0x140022249  js      short loc_140022281
0x14002224b  lea     rcx, [rsp+2A8h+var_278]; this
0x140022250  call    ?UpdateControl@SC_DISK@@QEAAJXZ; SC_DISK::UpdateControl(void)
0x140022255  mov     ebx, eax
0x140022257  test    eax, eax
0x140022259  js      short loc_140022281
0x14002225b  mov     rcx, [rsp+2A8h+var_28]
0x140022263  xor     r9d, r9d; Length
0x140022266  xor     r8d, r8d; Buffer
0x140022269  mov     [rsp+2A8h+var_288], 0; PLARGE_INTEGER
0x140022272  mov     rcx, [rcx+8]; DeviceObject
0x140022276  lea     edx, [r9+9]; MajorFunction
0x14002227a  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x14002227f  mov     ebx, eax
0x140022281  lea     rcx, [rsp+2A8h+var_278]; this
0x140022286  mov     [rsp+2A8h+var_278], rdi
0x14002228b  call    ??1SC_DRIVE@@UEAA@XZ; SC_DRIVE::~SC_DRIVE(void)
0x140022290  mov     eax, ebx
0x140022292  mov     rcx, [rsp+2A8h+var_18]
0x14002229a  xor     rcx, rsp; StackCookie
0x14002229d  call    __security_check_cookie
0x1400222a2  mov     rbx, [rsp+2A8h+arg_0]
0x1400222aa  add     rsp, 2A0h
0x1400222b1  pop     rdi
0x1400222b2  retn
```
