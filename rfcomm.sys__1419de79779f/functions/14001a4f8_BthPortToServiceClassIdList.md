# BthPortToServiceClassIdList

- ea: `0x14001a4f8`
- end: `0x14001a64b`
- name: `BthPortToServiceClassIdList`
- size: `339`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x140006f68`
- `0x1400079c0`
- `0x14000a380`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14001a4f8`
- `0x14001ab9c`
- `0x14001ba60`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001a557`
- `ntoskrnl!ExAllocatePool2` at `0x14001a557`
- `ntoskrnl!ExFreePool` at `0x14001a5f2`
- `ntoskrnl!ExFreePool` at `0x14001a601`
- `ntoskrnl!ExFreePool` at `0x14001a5f2`
- `ntoskrnl!ExFreePool` at `0x14001a601`

## pseudocode

```c
__int64 __fastcall BthPortToServiceClassIdList(
        PDEVICE_OBJECT DeviceObject,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5)
{
  __int64 Pool2; // rax
  int v10; // edx
  _QWORD *v11; // rbx
  int v12; // edi
  bool v13; // zf
  __int128 v14; // xmm1
  void *v15; // rcx
  __int64 v17; // [rsp+28h] [rbp-40h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      49,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  Pool2 = ExAllocatePool2(64, 96, 1146311746);
  v11 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    v13 = *(_QWORD *)a3 == 0;
    v14 = *(_OWORD *)(a3 + 12);
    *(_QWORD *)(Pool2 + 16) = DeviceObject;
    *(_OWORD *)(Pool2 + 32) = *(_OWORD *)a3;
    *(_QWORD *)(Pool2 + 24) = a2;
    *(_OWORD *)(Pool2 + 44) = v14;
    *(_QWORD *)(Pool2 + 72) = a5;
    *(_QWORD *)(Pool2 + 64) = TdiPortToServiceClassIdCallback;
    if ( v13 )
    {
      v12 = 0;
      SdppPortToIdSearch((PVOID)Pool2);
    }
    else
    {
      v12 = SdpConnectEx(DeviceObject, Pool2, a4 != 0 ? 5 : 0);
      if ( v12 < 0 )
      {
        v15 = (void *)v11[11];
        if ( v15 )
          ExFreePool(v15);
        ExFreePool(v11);
      }
    }
  }
  else
  {
    v12 = -1073741670;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v17) = v12;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      3,
      50,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
      v17);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14001a4f8  push    rbx
0x14001a4fa  push    rbp
0x14001a4fb  push    rsi
0x14001a4fc  push    rdi
0x14001a4fd  push    r13
0x14001a4ff  push    r14
0x14001a501  push    r15
0x14001a503  sub     rsp, 30h
0x14001a507  mov     r14b, r9b
0x14001a50a  mov     rdi, r8
0x14001a50d  mov     rsi, rdx
0x14001a510  mov     rbp, rcx
0x14001a513  lea     r15, WPP_RECORDER_INITIALIZED
0x14001a51a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001a521  lea     r13, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001a528  jz      short loc_14001A549
0x14001a52a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a531  mov     r9d, 31h ; '1'
0x14001a537  mov     [rsp+68h+var_48], r13
0x14001a53c  mov     rcx, [rcx+40h]
0x14001a540  lea     r8d, [r9-2Eh]
0x14001a544  call    WPP_RECORDER_SF_
0x14001a549  mov     edx, 60h ; '`'
0x14001a54e  mov     r8d, 44535442h
0x14001a554  lea     ecx, [rdx-20h]
0x14001a557  call    cs:__imp_ExAllocatePool2
0x14001a55e  nop     dword ptr [rax+rax+00h]
0x14001a563  mov     rbx, rax
0x14001a566  test    rax, rax
0x14001a569  jnz     short loc_14001A575
0x14001a56b  mov     edi, 0C000009Ah
0x14001a570  jmp     loc_14001A60D
0x14001a575  cmp     qword ptr [rdi], 0
0x14001a579  movups  xmm1, xmmword ptr [rdi+0Ch]
0x14001a57d  mov     [rax+10h], rbp
0x14001a581  movaps  xmm0, xmmword ptr [rdi]
0x14001a584  movups  xmmword ptr [rax+20h], xmm0
0x14001a588  mov     [rax+18h], rsi
0x14001a58c  movups  xmmword ptr [rax+2Ch], xmm1
0x14001a590  mov     rax, [rsp+68h+arg_20]
0x14001a598  mov     [rbx+48h], rax
0x14001a59c  lea     rax, TdiPortToServiceClassIdCallback
0x14001a5a3  mov     [rbx+40h], rax
0x14001a5a7  jnz     short loc_14001A5BC
0x14001a5a9  xor     edi, edi
0x14001a5ab  xor     r8d, r8d
0x14001a5ae  mov     rcx, rbx; P
0x14001a5b1  lea     rdx, [rdi-2]
0x14001a5b5  call    SdppPortToIdSearch
0x14001a5ba  jmp     short loc_14001A60D
0x14001a5bc  mov     r8, [rbx+20h]
0x14001a5c0  lea     r9, SdppPortToIdSearch
0x14001a5c7  neg     r14b
0x14001a5ca  mov     rdx, rsi
0x14001a5cd  mov     rcx, rbp; DeviceObject
0x14001a5d0  sbb     eax, eax
0x14001a5d2  and     eax, 5
0x14001a5d5  mov     dword ptr [rsp+68h+var_40], eax; int
0x14001a5d9  mov     [rsp+68h+var_48], rbx; __int64
0x14001a5de  call    SdpConnectEx
0x14001a5e3  mov     edi, eax
0x14001a5e5  test    eax, eax
0x14001a5e7  jns     short loc_14001A60D
0x14001a5e9  mov     rcx, [rbx+58h]; P
0x14001a5ed  test    rcx, rcx
0x14001a5f0  jz      short loc_14001A5FE
0x14001a5f2  call    cs:__imp_ExFreePool
0x14001a5f9  nop     dword ptr [rax+rax+00h]
0x14001a5fe  mov     rcx, rbx; P
0x14001a601  call    cs:__imp_ExFreePool
0x14001a608  nop     dword ptr [rax+rax+00h]
0x14001a60d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001a614  jz      short loc_14001A639
0x14001a616  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a61d  mov     r9d, 32h ; '2'
0x14001a623  mov     dword ptr [rsp+68h+var_40], edi
0x14001a627  mov     [rsp+68h+var_48], r13
0x14001a62c  mov     rcx, [rcx+40h]
0x14001a630  lea     r8d, [r9-2Fh]
0x14001a634  call    WPP_RECORDER_SF_d
0x14001a639  mov     eax, edi
0x14001a63b  add     rsp, 30h
0x14001a63f  pop     r15
0x14001a641  pop     r14
0x14001a643  pop     r13
0x14001a645  pop     rdi
0x14001a646  pop     rsi
0x14001a647  pop     rbp
0x14001a648  pop     rbx
0x14001a649  retn
```
