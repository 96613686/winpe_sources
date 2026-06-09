# PmGetFirmwareInfo(_DEVICE_EXTENSION *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)

- ea: `0x14002392c`
- end: `0x140023a9a`
- name: `?PmGetFirmwareInfo@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, enum _STORAGE_BUS_TYPE, PVOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400261fc`

## callees

- `0x140010f20`
- `0x14002392c`
- `0x140023cb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140023a4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023a68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023a4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023a68`
- `ntoskrnl!ExAllocatePool2` at `0x1400239f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400239f4`

## pseudocode

```c
__int64 __fastcall PmGetFirmwareInfo(struct _DEVICE_EXTENSION *a1, enum _STORAGE_BUS_TYPE a2, PVOID *a3)
{
  struct _DEVICE_OBJECT *v5; // rcx
  unsigned int v6; // ebx
  ULONG v7; // esi
  struct _STORAGE_HW_FIRMWARE_INFO *Pool2; // rax
  struct _STORAGE_HW_FIRMWARE_INFO *v9; // rdi
  int InputBuffer; // [rsp+40h] [rbp-19h] BYREF
  ULONG InputBufferLength; // [rsp+44h] [rbp-15h]
  _BOOL8 v13; // [rsp+48h] [rbp-11h]
  ULONG v14[4]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v15; // [rsp+60h] [rbp+7h]
  __int128 v16; // [rsp+70h] [rbp+17h]
  __int64 v17; // [rsp+80h] [rbp+27h]

  v13 = 0;
  v17 = 0;
  InputBuffer = 16;
  InputBufferLength = 16;
  v5 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 2);
  v13 = a2 == BusTypeNvme;
  *(_OWORD *)v14 = 0;
  v15 = 0;
  v16 = 0;
  v6 = PmSendDeviceControl(v5, 0x2D1C00u, &InputBuffer, 0x10u, v14, 0x38u, 0);
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147483643 )
    return v6;
  if ( v14[0] != 56 )
    return (unsigned int)-1073741820;
  v7 = 56;
  if ( v14[1] > 0x38 )
    v7 = v14[1];
  Pool2 = (struct _STORAGE_HW_FIRMWARE_INFO *)ExAllocatePool2(64, v7, 1112108368);
  v9 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v6 = PmSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 2), 0x2D1C00u, &InputBuffer, InputBufferLength, Pool2, v7, 0);
  if ( (v6 & 0x80000000) != 0 )
  {
LABEL_16:
    ExFreePoolWithTag(v9, 0);
    return v6;
  }
  if ( v9->Version != 56 || v9->Size != v7 )
  {
    v6 = -1073741820;
    goto LABEL_16;
  }
  if ( *a3 )
    ExFreePoolWithTag(*a3, 0);
  *a3 = v9;
  return v6;
}

```

## disassembly

```asm
0x14002392c  mov     [rsp-8+arg_8], rbx
0x140023931  push    rbp
0x140023932  push    rsi
0x140023933  push    rdi
0x140023934  push    r14
0x140023936  push    r15
0x140023938  lea     rbp, [rsp-37h]
0x14002393d  sub     rsp, 90h
0x140023944  mov     rax, cs:__security_cookie
0x14002394b  xor     rax, rsp
0x14002394e  mov     [rbp+57h+var_28], rax
0x140023952  xor     eax, eax
0x140023954  mov     [rsp+0B0h+var_80], 0; BOOLEAN
0x140023959  mov     [rbp+57h+var_68], rax
0x14002395d  xorps   xmm0, xmm0
0x140023960  mov     r15, rcx
0x140023963  mov     [rbp+57h+var_30], rax
0x140023967  cmp     edx, 11h
0x14002396a  mov     [rsp+0B0h+var_88], 38h ; '8'; ULONG
0x140023972  lea     r9d, [rax+10h]; InputBufferLength
0x140023976  mov     r14, r8
0x140023979  lea     ecx, [rax+1]
0x14002397c  mov     [rbp+57h+InputBuffer], r9d
0x140023980  cmovz   eax, ecx
0x140023983  mov     [rbp+57h+InputBufferLength], r9d
0x140023987  mov     rcx, [r15+10h]; DeviceObject
0x14002398b  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x14002398f  mov     dword ptr [rbp+57h+var_68], eax
0x140023992  mov     edx, 2D1C00h; IoControlCode
0x140023997  lea     rax, [rbp+57h+var_60]
0x14002399b  mov     [rsp+0B0h+var_90], rax; PVOID
0x1400239a0  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1400239a4  movups  [rbp+57h+var_50], xmm0
0x1400239a8  movups  [rbp+57h+var_40], xmm0
0x1400239ac  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x1400239b1  mov     ebx, eax
0x1400239b3  mov     eax, 80000000h
0x1400239b8  lea     ecx, [rbx+rax]
0x1400239bb  test    eax, ecx
0x1400239bd  jnz     short loc_1400239CB
0x1400239bf  cmp     ebx, 80000005h
0x1400239c5  jnz     loc_140023A74
0x1400239cb  cmp     [rbp+57h+var_60], 38h ; '8'
0x1400239cf  jz      short loc_1400239DB
0x1400239d1  mov     ebx, 0C0000004h
0x1400239d6  jmp     loc_140023A74
0x1400239db  mov     esi, 38h ; '8'
0x1400239e0  mov     ecx, 40h ; '@'
0x1400239e5  cmp     [rbp+57h+var_60+4], esi
0x1400239e8  mov     r8d, 42496D50h
0x1400239ee  cmova   esi, [rbp+57h+var_60+4]
0x1400239f2  mov     edx, esi
0x1400239f4  call    cs:__imp_ExAllocatePool2
0x1400239fb  nop     dword ptr [rax+rax+00h]
0x140023a00  mov     rdi, rax
0x140023a03  test    rax, rax
0x140023a06  jnz     short loc_140023A0F
0x140023a08  mov     ebx, 0C000009Ah
0x140023a0d  jmp     short loc_140023A74
0x140023a0f  mov     r9d, [rbp+57h+InputBufferLength]; InputBufferLength
0x140023a13  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x140023a17  mov     rcx, [r15+10h]; DeviceObject
0x140023a1b  mov     edx, 2D1C00h; IoControlCode
0x140023a20  mov     [rsp+0B0h+var_80], 0; BOOLEAN
0x140023a25  mov     [rsp+0B0h+var_88], esi; ULONG
0x140023a29  mov     [rsp+0B0h+var_90], rdi; PVOID
0x140023a2e  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140023a33  mov     ebx, eax
0x140023a35  test    eax, eax
0x140023a37  js      short loc_140023A63
0x140023a39  cmp     dword ptr [rdi], 38h ; '8'
0x140023a3c  jnz     short loc_140023A5E
0x140023a3e  cmp     [rdi+4], esi
0x140023a41  jnz     short loc_140023A5E
0x140023a43  mov     rcx, [r14]; P
0x140023a46  test    rcx, rcx
0x140023a49  jz      short loc_140023A59
0x140023a4b  xor     edx, edx; Tag
0x140023a4d  call    cs:__imp_ExFreePoolWithTag
0x140023a54  nop     dword ptr [rax+rax+00h]
0x140023a59  mov     [r14], rdi
0x140023a5c  jmp     short loc_140023A74
0x140023a5e  mov     ebx, 0C0000004h
0x140023a63  xor     edx, edx; Tag
0x140023a65  mov     rcx, rdi; P
0x140023a68  call    cs:__imp_ExFreePoolWithTag
0x140023a6f  nop     dword ptr [rax+rax+00h]
0x140023a74  mov     eax, ebx
0x140023a76  mov     rcx, [rbp+57h+var_28]
0x140023a7a  xor     rcx, rsp; StackCookie
0x140023a7d  call    __security_check_cookie
0x140023a82  mov     rbx, [rsp+0B0h+arg_8]
0x140023a8a  add     rsp, 90h
0x140023a91  pop     r15
0x140023a93  pop     r14
0x140023a95  pop     rdi
0x140023a96  pop     rsi
0x140023a97  pop     rbp
0x140023a98  retn
```
