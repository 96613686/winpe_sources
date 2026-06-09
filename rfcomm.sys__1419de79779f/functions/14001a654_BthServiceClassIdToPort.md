# BthServiceClassIdToPort

- ea: `0x14001a654`
- end: `0x14001a765`
- name: `BthServiceClassIdToPort`
- size: `273`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x140007b60`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14001a654`
- `0x14001ab9c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001a6ae`
- `ntoskrnl!ExAllocatePool2` at `0x14001a6ae`
- `ntoskrnl!ExFreePool` at `0x14001a71d`
- `ntoskrnl!ExFreePool` at `0x14001a71d`

## pseudocode

```c
__int64 __fastcall BthServiceClassIdToPort(PDEVICE_OBJECT DeviceObject, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 Pool2; // rax
  int v9; // edx
  void *v10; // rbx
  int v11; // edi
  __int64 v13; // [rsp+28h] [rbp-40h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      41,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  Pool2 = ExAllocatePool2(64, 180, 1146311746);
  v10 = (void *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 40) = a5;
    *(_QWORD *)(Pool2 + 24) = DeviceObject;
    *(_QWORD *)(Pool2 + 32) = a2;
    *(_DWORD *)(Pool2 + 48) = 30;
    *(_QWORD *)(Pool2 + 8) = a3;
    *(_QWORD *)Pool2 = TdiServiceClassIdCallback;
    v11 = SdpConnectEx(DeviceObject, Pool2, 0);
    if ( v11 < 0 )
      ExFreePool(v10);
  }
  else
  {
    v11 = -1073741670;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v13) = v11;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      3,
      42,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
      v13);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14001a654  push    rbx
0x14001a656  push    rbp
0x14001a657  push    rsi
0x14001a658  push    rdi
0x14001a659  push    r12
0x14001a65b  push    r14
0x14001a65d  sub     rsp, 38h
0x14001a661  mov     rbp, r8
0x14001a664  mov     rdi, rdx
0x14001a667  mov     rsi, rcx
0x14001a66a  lea     r14, WPP_RECORDER_INITIALIZED
0x14001a671  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001a678  lea     r12, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001a67f  jz      short loc_14001A6A0
0x14001a681  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a688  mov     r9d, 29h ; ')'
0x14001a68e  mov     [rsp+68h+var_48], r12
0x14001a693  mov     rcx, [rcx+40h]
0x14001a697  lea     r8d, [r9-26h]
0x14001a69b  call    WPP_RECORDER_SF_
0x14001a6a0  mov     edx, 0B4h
0x14001a6a5  mov     r8d, 44535442h
0x14001a6ab  lea     ecx, [rdx-74h]
0x14001a6ae  call    cs:__imp_ExAllocatePool2
0x14001a6b5  nop     dword ptr [rax+rax+00h]
0x14001a6ba  mov     rbx, rax
0x14001a6bd  test    rax, rax
0x14001a6c0  jnz     short loc_14001A6C9
0x14001a6c2  mov     edi, 0C000009Ah
0x14001a6c7  jmp     short loc_14001A729
0x14001a6c9  mov     r8, [rsp+68h+arg_20]
0x14001a6d1  lea     r9, SdppIdToPortSearch
0x14001a6d8  mov     [rax+28h], r8
0x14001a6dc  mov     rdx, rdi
0x14001a6df  mov     [rax+18h], rsi
0x14001a6e3  mov     rcx, rsi; DeviceObject
0x14001a6e6  mov     [rax+20h], rdi
0x14001a6ea  mov     dword ptr [rax+30h], 1Eh
0x14001a6f1  mov     [rax+8], rbp
0x14001a6f5  lea     rax, TdiServiceClassIdCallback
0x14001a6fc  mov     [rbx], rax
0x14001a6ff  mov     r8, [r8]
0x14001a702  mov     dword ptr [rsp+68h+var_40], 0; int
0x14001a70a  mov     [rsp+68h+var_48], rbx; __int64
0x14001a70f  call    SdpConnectEx
0x14001a714  mov     edi, eax
0x14001a716  test    eax, eax
0x14001a718  jns     short loc_14001A729
0x14001a71a  mov     rcx, rbx; P
0x14001a71d  call    cs:__imp_ExFreePool
0x14001a724  nop     dword ptr [rax+rax+00h]
0x14001a729  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001a730  jz      short loc_14001A755
0x14001a732  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a739  mov     r9d, 2Ah ; '*'
0x14001a73f  mov     dword ptr [rsp+68h+var_40], edi
0x14001a743  mov     [rsp+68h+var_48], r12
0x14001a748  mov     rcx, [rcx+40h]
0x14001a74c  lea     r8d, [r9-27h]
0x14001a750  call    WPP_RECORDER_SF_d
0x14001a755  mov     eax, edi
0x14001a757  add     rsp, 38h
0x14001a75b  pop     r14
0x14001a75d  pop     r12
0x14001a75f  pop     rdi
0x14001a760  pop     rsi
0x14001a761  pop     rbp
0x14001a762  pop     rbx
0x14001a763  retn
```
