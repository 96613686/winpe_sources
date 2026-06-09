# SdppServiceSearchCompletionRoutine

- ea: `0x14001bce0`
- end: `0x14001bde0`
- name: `SdppServiceSearchCompletionRoutine`
- size: `256`
- prototype: `__int64 __fastcall(__int64, IRP *, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14001bce0`
- `0x14001fc70`
- `0x140020380`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001bd8e`
- `ntoskrnl!IoFreeIrp` at `0x14001bd8e`
- `ntoskrnl!ExFreePool` at `0x14001bd9d`
- `ntoskrnl!ExFreePool` at `0x14001bd9d`

## pseudocode

```c
__int64 __fastcall SdppServiceSearchCompletionRoutine(__int64 a1, IRP *a2, _QWORD *a3)
{
  __int64 v5; // rdx
  int v6; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      63,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  if ( a2 )
  {
    if ( a2->IoStatus.Status >= 0 )
    {
      memmove((void *)*a3, a3 + 4, a2->IoStatus.Information);
      v5 = LODWORD(a2->IoStatus.Information) >> 2;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          64,
          (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
          a2->IoStatus.Status);
      v5 = 0;
    }
    ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))a3[3])(a3[2], v5, *a3, (unsigned int)a2->IoStatus.Status);
    IoFreeIrp(a2);
  }
  ExFreePool(a3);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      3,
      65,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001bce0  push    rbx
0x14001bce2  push    rbp
0x14001bce3  push    rsi
0x14001bce4  push    rdi
0x14001bce5  sub     rsp, 38h
0x14001bce9  mov     rdi, r8
0x14001bcec  mov     rbx, rdx
0x14001bcef  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001bcf6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001bcfd  lea     rbp, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001bd04  jz      short loc_14001BD25
0x14001bd06  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd0d  mov     r9d, 3Fh ; '?'
0x14001bd13  mov     [rsp+58h+var_38], rbp
0x14001bd18  mov     rcx, [rcx+40h]
0x14001bd1c  lea     r8d, [r9-3Ch]
0x14001bd20  call    WPP_RECORDER_SF_
0x14001bd25  test    rbx, rbx
0x14001bd28  jz      short loc_14001BD9A
0x14001bd2a  mov     eax, [rbx+30h]
0x14001bd2d  test    eax, eax
0x14001bd2f  jns     short loc_14001BD61
0x14001bd31  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001bd38  jz      short loc_14001BD5D
0x14001bd3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd41  mov     r9d, 40h ; '@'
0x14001bd47  mov     [rsp+58h+var_30], eax
0x14001bd4b  mov     [rsp+58h+var_38], rbp
0x14001bd50  mov     rcx, [rcx+40h]
0x14001bd54  lea     r8d, [r9-3Fh]
0x14001bd58  call    WPP_RECORDER_SF_d
0x14001bd5d  xor     edx, edx
0x14001bd5f  jmp     short loc_14001BD77
0x14001bd61  mov     r8, [rbx+38h]; Size
0x14001bd65  lea     rdx, [rdi+20h]; Src
0x14001bd69  mov     rcx, [rdi]; void *
0x14001bd6c  call    memmove
0x14001bd71  mov     edx, [rbx+38h]
0x14001bd74  shr     edx, 2
0x14001bd77  mov     r9d, [rbx+30h]
0x14001bd7b  mov     r8, [rdi]
0x14001bd7e  mov     rcx, [rdi+10h]
0x14001bd82  mov     rax, [rdi+18h]
0x14001bd86  call    _guard_dispatch_icall
0x14001bd8b  mov     rcx, rbx; Irp
0x14001bd8e  call    cs:__imp_IoFreeIrp
0x14001bd95  nop     dword ptr [rax+rax+00h]
0x14001bd9a  mov     rcx, rdi; P
0x14001bd9d  call    cs:__imp_ExFreePool
0x14001bda4  nop     dword ptr [rax+rax+00h]
0x14001bda9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001bdb0  jz      short loc_14001BDD1
0x14001bdb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bdb9  mov     r9d, 41h ; 'A'
0x14001bdbf  mov     [rsp+58h+var_38], rbp
0x14001bdc4  mov     rcx, [rcx+40h]
0x14001bdc8  lea     r8d, [r9-3Eh]
0x14001bdcc  call    WPP_RECORDER_SF_
0x14001bdd1  mov     eax, 0C0000016h
0x14001bdd6  add     rsp, 38h
0x14001bdda  pop     rdi
0x14001bddb  pop     rsi
0x14001bddc  pop     rbp
0x14001bddd  pop     rbx
0x14001bdde  retn
```
