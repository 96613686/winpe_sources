# DisableWriteCache

- ea: `0x14000e2a0`
- end: `0x14000e305`
- name: `DisableWriteCache`
- size: `101`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14000e2a0`
- `0x14000f804`
- `0x140012ca0`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14000e2ed`
- `ntoskrnl!IoFreeWorkItem` at `0x14000e2ed`

## pseudocode

```c
void __fastcall DisableWriteCache(PDEVICE_OBJECT DeviceObject, struct _IO_WORKITEM *Context)
{
  PVOID DeviceExtension; // rbx
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]

  DeviceExtension = DeviceObject->DeviceExtension;
  v4 = 0;
  v5 = 0;
  if ( (int)DiskGetCacheInformation((__int64)DeviceExtension, (__int64)&v4) >= 0 && BYTE2(v4) == 1 )
  {
    BYTE2(v4) = 0;
    DiskSetCacheInformation((__int64)DeviceExtension, &v4);
  }
  IoFreeWorkItem(Context);
}

```

## disassembly

```asm
0x14000e2a0  mov     [rsp+arg_0], rbx
0x14000e2a5  push    rdi
0x14000e2a6  sub     rsp, 40h
0x14000e2aa  mov     rbx, [rcx+40h]
0x14000e2ae  mov     rdi, rdx
0x14000e2b1  xorps   xmm0, xmm0
0x14000e2b4  lea     rdx, [rsp+48h+var_28]
0x14000e2b9  xor     eax, eax
0x14000e2bb  mov     rcx, rbx
0x14000e2be  movups  [rsp+48h+var_28], xmm0
0x14000e2c3  mov     [rsp+48h+var_18], rax
0x14000e2c8  call    DiskGetCacheInformation
0x14000e2cd  test    eax, eax
0x14000e2cf  js      short loc_14000E2EA
0x14000e2d1  cmp     byte ptr [rsp+48h+var_28+2], 1
0x14000e2d6  jnz     short loc_14000E2EA
0x14000e2d8  lea     rdx, [rsp+48h+var_28]
0x14000e2dd  mov     byte ptr [rsp+48h+var_28+2], 0
0x14000e2e2  mov     rcx, rbx
0x14000e2e5  call    DiskSetCacheInformation
0x14000e2ea  mov     rcx, rdi; IoWorkItem
0x14000e2ed  call    cs:__imp_IoFreeWorkItem
0x14000e2f4  nop     dword ptr [rax+rax+00h]
0x14000e2f9  mov     rbx, [rsp+48h+arg_0]
0x14000e2fe  add     rsp, 40h
0x14000e302  pop     rdi
0x14000e303  retn
```
