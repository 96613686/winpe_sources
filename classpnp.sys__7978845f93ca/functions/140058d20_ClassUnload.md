# ClassUnload

- ea: `0x140058d20`
- end: `0x140058e88`
- name: `ClassUnload`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140001008`
- `0x140026d30`
- `0x14003e430`
- `0x14003e470`
- `0x140058d20`
- `0x14005a734`
- `0x14005ad00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140058dd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058df9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058e1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058dd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058df9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058e1b`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140058d43`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140058d43`
- `ntoskrnl!IoUnregisterPriorityCallback` at `0x140058e5e`
- `ntoskrnl!IoUnregisterPriorityCallback` at `0x140058e5e`
- `ntoskrnl!EtwUnregister` at `0x140058e3f`
- `ntoskrnl!EtwUnregister` at `0x140058e3f`

## pseudocode

```c
int __fastcall ClassUnload(struct _DRIVER_OBJECT *a1)
{
  REGHANDLE *DriverObjectExtension; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  REGHANDLE *v5; // rbx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  REGHANDLE v9; // rcx
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-38h] BYREF

  DriverObjectExtension = (REGHANDLE *)IoGetDriverObjectExtension(a1, ClassInitialize);
  v5 = DriverObjectExtension;
  if ( (unsigned int)dword_14004D060 > 5 )
    LODWORD(DriverObjectExtension) = tlgWriteTransfer_EtwWriteTransfer(
                                       (unsigned int)dword_14004D060,
                                       (unsigned __int8 *)&byte_1400486C5,
                                       v3,
                                       v4,
                                       2u,
                                       &v11);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 18, v3, v5);
    }
    ((void (__fastcall *)(struct _DRIVER_OBJECT *))v5[49])(a1);
    v6 = (void *)v5[112];
    if ( v6 )
    {
      ExFreePoolWithTag(v6, 0);
      v5[112] = 0;
    }
    v7 = (void *)v5[111];
    if ( v7 )
    {
      ExFreePoolWithTag(v7, 0);
      v5[111] = 0;
    }
    v8 = (void *)v5[1];
    if ( v8 )
    {
      ExFreePoolWithTag(v8, 0);
      v5[1] = 0;
    }
    v9 = v5[54];
    *(_DWORD *)v5 = 0;
    if ( v9 )
    {
      EtwUnregister(v9);
      v5[54] = 0;
      WppCleanupKm();
    }
    IoUnregisterPriorityCallback(a1);
    LODWORD(DriverObjectExtension) = wil_UninitializeFeatureStaging();
  }
  return (int)DriverObjectExtension;
}

```

## disassembly

```asm
0x140058d20  mov     [rsp+arg_8], rbx
0x140058d25  push    rdi
0x140058d26  sub     rsp, 60h
0x140058d2a  mov     rax, cs:__security_cookie
0x140058d31  xor     rax, rsp
0x140058d34  mov     [rsp+68h+var_18], rax
0x140058d39  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x140058d40  mov     rdi, rcx
0x140058d43  call    cs:__imp_IoGetDriverObjectExtension
0x140058d4a  nop     dword ptr [rax+rax+00h]
0x140058d4f  mov     ecx, cs:dword_14004D060; int
0x140058d55  mov     rbx, rax
0x140058d58  cmp     ecx, 5
0x140058d5b  jbe     short loc_140058D7B
0x140058d5d  lea     rax, [rsp+68h+var_38]
0x140058d62  mov     [rsp+68h+var_40], rax; __int64
0x140058d67  lea     rdx, byte_1400486C5; int
0x140058d6e  mov     [rsp+68h+var_48], 2; ULONG
0x140058d76  call    _tlgWriteTransfer_EtwWriteTransfer
0x140058d7b  test    rbx, rbx
0x140058d7e  jz      loc_140058E6F
0x140058d84  mov     rcx, cs:WPP_GLOBAL_Control
0x140058d8b  lea     rax, WPP_GLOBAL_Control
0x140058d92  cmp     rcx, rax
0x140058d95  jz      short loc_140058DB7
0x140058d97  test    dword ptr [rcx+2Ch], 100h
0x140058d9e  jz      short loc_140058DB7
0x140058da0  cmp     byte ptr [rcx+29h], 4
0x140058da4  jb      short loc_140058DB7
0x140058da6  mov     rcx, [rcx+18h]
0x140058daa  mov     edx, 12h
0x140058daf  mov     r9, rbx
0x140058db2  call    WPP_SF_Z
0x140058db7  mov     rax, [rbx+188h]
0x140058dbe  mov     rcx, rdi
0x140058dc1  call    _guard_dispatch_icall
0x140058dc6  mov     rcx, [rbx+380h]; P
0x140058dcd  test    rcx, rcx
0x140058dd0  jz      short loc_140058DEB
0x140058dd2  xor     edx, edx; Tag
0x140058dd4  call    cs:__imp_ExFreePoolWithTag
0x140058ddb  nop     dword ptr [rax+rax+00h]
0x140058de0  mov     qword ptr [rbx+380h], 0
0x140058deb  mov     rcx, [rbx+378h]; P
0x140058df2  test    rcx, rcx
0x140058df5  jz      short loc_140058E10
0x140058df7  xor     edx, edx; Tag
0x140058df9  call    cs:__imp_ExFreePoolWithTag
0x140058e00  nop     dword ptr [rax+rax+00h]
0x140058e05  mov     qword ptr [rbx+378h], 0
0x140058e10  mov     rcx, [rbx+8]; P
0x140058e14  test    rcx, rcx
0x140058e17  jz      short loc_140058E2F
0x140058e19  xor     edx, edx; Tag
0x140058e1b  call    cs:__imp_ExFreePoolWithTag
0x140058e22  nop     dword ptr [rax+rax+00h]
0x140058e27  mov     qword ptr [rbx+8], 0
0x140058e2f  mov     rcx, [rbx+1B0h]; RegHandle
0x140058e36  xor     eax, eax
0x140058e38  mov     [rbx], eax
0x140058e3a  test    rcx, rcx
0x140058e3d  jz      short loc_140058E5B
0x140058e3f  call    cs:__imp_EtwUnregister
0x140058e46  nop     dword ptr [rax+rax+00h]
0x140058e4b  mov     qword ptr [rbx+1B0h], 0
0x140058e56  call    WppCleanupKm
0x140058e5b  mov     rcx, rdi
0x140058e5e  call    cs:__imp_IoUnregisterPriorityCallback
0x140058e65  nop     dword ptr [rax+rax+00h]
0x140058e6a  call    wil_UninitializeFeatureStaging
0x140058e6f  mov     rcx, [rsp+68h+var_18]
0x140058e74  xor     rcx, rsp; StackCookie
0x140058e77  call    __security_check_cookie
0x140058e7c  mov     rbx, [rsp+68h+arg_8]
0x140058e81  add     rsp, 60h
0x140058e85  pop     rdi
0x140058e86  retn
```
