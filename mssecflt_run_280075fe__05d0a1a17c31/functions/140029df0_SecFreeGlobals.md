# SecFreeGlobals

- ea: `0x140029df0`
- end: `0x140029fc6`
- name: `SecFreeGlobals`
- size: `470`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x140029d80`
- `0x140045000`

## callees

- `0x140009b80`
- `0x140010593`
- `0x140029df0`
- `0x14003a790`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140029f38`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140029f38`
- `ntoskrnl!IoDeleteDevice` at `0x140029f16`
- `ntoskrnl!IoDeleteDevice` at `0x140029f16`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140029e86`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140029ea0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140029eba`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140029ed4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140029e86`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140029ea0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140029eba`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140029ed4`
- `ntoskrnl!ZwClose` at `0x140029f86`
- `ntoskrnl!ZwClose` at `0x140029f86`

## pseudocode

```c
void SecFreeGlobals()
{
  void *v0; // rcx
  struct _DEVICE_OBJECT *v1; // rcx
  void *v2; // rcx
  void *v3; // rcx

  if ( SecData )
  {
    v0 = (void *)*((_QWORD *)SecData + 40);
    if ( v0 )
    {
      SecFreePool(v0, 0x74736353u);
      *((_QWORD *)SecData + 40) = 0;
    }
    SecRemoveSessionFiltersUnsafe((char *)SecData + 1248);
    FltDeletePushLock_0((PULONG_PTR)SecData + 155);
    FltDeletePushLock_0((PULONG_PTR)SecData + 151);
    FltDeletePushLock_0((PULONG_PTR)SecData + 163);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)SecData + 4);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)SecData + 3);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)SecData + 7);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)SecData + 8);
    FltDeletePushLock_0((PULONG_PTR)SecData + 41);
    FltDeletePushLock_0((PULONG_PTR)SecData + 146);
    v1 = (struct _DEVICE_OBJECT *)*((_QWORD *)SecData + 2);
    if ( v1 )
    {
      IoDeleteDevice(v1);
      *((_QWORD *)SecData + 2) = 0;
      IoDeleteSymbolicLink((PUNICODE_STRING)&SymbolicLinkName);
    }
    v2 = (void *)*((_QWORD *)SecData + 165);
    if ( v2 )
    {
      SecFreePool(v2, 0x64736353u);
      *((_QWORD *)SecData + 165) = 0;
    }
    v3 = (void *)*((_QWORD *)SecData + 166);
    if ( v3 )
    {
      ZwClose(v3);
      *((_QWORD *)SecData + 166) = 0;
    }
    SecFreePool(SecData, 0x64676353u);
    SecData = 0;
  }
}

```

## disassembly

```asm
0x140029df0  sub     rsp, 28h
0x140029df4  mov     rax, cs:SecData
0x140029dfb  test    rax, rax
0x140029dfe  jz      loc_140029FC0
0x140029e04  mov     rcx, [rax+140h]; P
0x140029e0b  test    rcx, rcx
0x140029e0e  jz      short loc_140029E2C
0x140029e10  mov     edx, 74736353h; Tag
0x140029e15  call    SecFreePool
0x140029e1a  mov     rax, cs:SecData
0x140029e21  mov     qword ptr [rax+140h], 0
0x140029e2c  mov     rcx, cs:SecData
0x140029e33  add     rcx, 4E0h
0x140029e3a  call    SecRemoveSessionFiltersUnsafe
0x140029e3f  mov     rcx, cs:SecData
0x140029e46  add     rcx, 4D8h; PushLock
0x140029e4d  call    FltDeletePushLock_0
0x140029e52  mov     rcx, cs:SecData
0x140029e59  add     rcx, 4B8h; PushLock
0x140029e60  call    FltDeletePushLock_0
0x140029e65  mov     rcx, cs:SecData
0x140029e6c  add     rcx, 518h; PushLock
0x140029e73  call    FltDeletePushLock_0
0x140029e78  mov     rcx, cs:SecData
0x140029e7f  add     rcx, 200h; Lookaside
0x140029e86  call    cs:__imp_ExDeletePagedLookasideList
0x140029e8d  nop     dword ptr [rax+rax+00h]
0x140029e92  mov     rcx, cs:SecData
0x140029e99  add     rcx, 180h; Lookaside
0x140029ea0  call    cs:__imp_ExDeletePagedLookasideList
0x140029ea7  nop     dword ptr [rax+rax+00h]
0x140029eac  mov     rcx, cs:SecData
0x140029eb3  add     rcx, 380h; Lookaside
0x140029eba  call    cs:__imp_ExDeletePagedLookasideList
0x140029ec1  nop     dword ptr [rax+rax+00h]
0x140029ec6  mov     rcx, cs:SecData
0x140029ecd  add     rcx, 400h; Lookaside
0x140029ed4  call    cs:__imp_ExDeletePagedLookasideList
0x140029edb  nop     dword ptr [rax+rax+00h]
0x140029ee0  mov     rcx, cs:SecData
0x140029ee7  add     rcx, 148h; PushLock
0x140029eee  call    FltDeletePushLock_0
0x140029ef3  mov     rcx, cs:SecData
0x140029efa  add     rcx, 490h; PushLock
0x140029f01  call    FltDeletePushLock_0
0x140029f06  mov     rax, cs:SecData
0x140029f0d  mov     rcx, [rax+10h]; DeviceObject
0x140029f11  test    rcx, rcx
0x140029f14  jz      short loc_140029F44
0x140029f16  call    cs:__imp_IoDeleteDevice
0x140029f1d  nop     dword ptr [rax+rax+00h]
0x140029f22  mov     rax, cs:SecData
0x140029f29  lea     rcx, SymbolicLinkName; SymbolicLinkName
0x140029f30  mov     qword ptr [rax+10h], 0
0x140029f38  call    cs:__imp_IoDeleteSymbolicLink
0x140029f3f  nop     dword ptr [rax+rax+00h]
0x140029f44  mov     rax, cs:SecData
0x140029f4b  mov     rcx, [rax+528h]; P
0x140029f52  test    rcx, rcx
0x140029f55  jz      short loc_140029F73
0x140029f57  mov     edx, 64736353h; Tag
0x140029f5c  call    SecFreePool
0x140029f61  mov     rax, cs:SecData
0x140029f68  mov     qword ptr [rax+528h], 0
0x140029f73  mov     rax, cs:SecData
0x140029f7a  mov     rcx, [rax+530h]; Handle
0x140029f81  test    rcx, rcx
0x140029f84  jz      short loc_140029FA4
0x140029f86  call    cs:__imp_ZwClose
0x140029f8d  nop     dword ptr [rax+rax+00h]
0x140029f92  mov     rax, cs:SecData
0x140029f99  mov     qword ptr [rax+530h], 0
0x140029fa4  mov     rcx, cs:SecData; P
0x140029fab  mov     edx, 64676353h; Tag
0x140029fb0  call    SecFreePool
0x140029fb5  mov     cs:SecData, 0
0x140029fc0  add     rsp, 28h
0x140029fc4  retn
```
