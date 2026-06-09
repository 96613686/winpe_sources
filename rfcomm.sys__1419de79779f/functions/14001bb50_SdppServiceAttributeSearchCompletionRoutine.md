# SdppServiceAttributeSearchCompletionRoutine

- ea: `0x14001bb50`
- end: `0x14001bcd3`
- name: `SdppServiceAttributeSearchCompletionRoutine`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14001ade8`
- `0x14001bb50`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001bc81`
- `ntoskrnl!IoFreeIrp` at `0x14001bc81`
- `ntoskrnl!ExFreePool` at `0x14001bc90`
- `ntoskrnl!ExFreePool` at `0x14001bc90`

## pseudocode

```c
__int64 __fastcall SdppServiceAttributeSearchCompletionRoutine(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 Status; // r9
  unsigned int v6; // eax
  __int64 v7; // r8
  int v8; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      59,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  if ( a2 )
  {
    if ( a2->IoStatus.Status >= 0 )
    {
      v6 = *(_DWORD *)(a3 + 72);
      if ( v6 )
      {
        v7 = *(unsigned int *)(a3 + 76);
        if ( v6 <= (unsigned int)v7 )
          (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(a3 + 56))(*(_QWORD *)(a3 + 64), a3 + 80, v7, 0);
        else
          SdpServiceAttributeSearchInternal(
            *(PDEVICE_OBJECT *)a3,
            a3 + 36,
            *(_WORD *)(a3 + 52),
            *(_WORD *)(a3 + 54),
            *(_QWORD *)(a3 + 56),
            *(_QWORD *)(a3 + 64),
            v6);
        goto LABEL_16;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          61,
          (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
      Status = 3221226021LL;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          60,
          (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
          a2->IoStatus.Status);
      Status = (unsigned int)a2->IoStatus.Status;
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(a3 + 56))(*(_QWORD *)(a3 + 64), 0, 0, Status);
LABEL_16:
    IoFreeIrp(a2);
  }
  ExFreePool((PVOID)a3);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      3,
      62,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001bb50  push    rbx
0x14001bb52  push    rbp
0x14001bb53  push    rsi
0x14001bb54  push    rdi
0x14001bb55  sub     rsp, 58h
0x14001bb59  mov     rbx, r8
0x14001bb5c  mov     rdi, rdx
0x14001bb5f  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001bb66  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001bb6d  lea     rbp, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001bb74  jz      short loc_14001BB95
0x14001bb76  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb7d  mov     r9d, 3Bh ; ';'
0x14001bb83  mov     [rsp+78h+var_58], rbp
0x14001bb88  mov     rcx, [rcx+40h]
0x14001bb8c  lea     r8d, [r9-38h]
0x14001bb90  call    WPP_RECORDER_SF_
0x14001bb95  test    rdi, rdi
0x14001bb98  jz      loc_14001BC8D
0x14001bb9e  mov     eax, [rdi+30h]
0x14001bba1  test    eax, eax
0x14001bba3  jns     short loc_14001BBE7
0x14001bba5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001bbac  jz      short loc_14001BBD1
0x14001bbae  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bbb5  mov     r9d, 3Ch ; '<'
0x14001bbbb  mov     dword ptr [rsp+78h+var_50], eax
0x14001bbbf  mov     [rsp+78h+var_58], rbp
0x14001bbc4  mov     rcx, [rcx+40h]
0x14001bbc8  lea     r8d, [r9-3Bh]
0x14001bbcc  call    WPP_RECORDER_SF_d
0x14001bbd1  mov     r9d, [rdi+30h]
0x14001bbd5  mov     rax, [rbx+38h]
0x14001bbd9  xor     r8d, r8d
0x14001bbdc  mov     rcx, [rbx+40h]
0x14001bbe0  xor     edx, edx
0x14001bbe2  jmp     loc_14001BC79
0x14001bbe7  mov     eax, [rbx+48h]
0x14001bbea  test    eax, eax
0x14001bbec  jnz     short loc_14001BC1C
0x14001bbee  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001bbf5  jz      short loc_14001BC14
0x14001bbf7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bbfe  lea     r9d, [rax+3Dh]
0x14001bc02  lea     r8d, [rax+1]
0x14001bc06  mov     [rsp+78h+var_58], rbp
0x14001bc0b  mov     rcx, [rcx+40h]
0x14001bc0f  call    WPP_RECORDER_SF_
0x14001bc14  mov     r9d, 0C0000225h
0x14001bc1a  jmp     short loc_14001BBD5
0x14001bc1c  mov     r8d, [rbx+4Ch]
0x14001bc20  mov     r10, [rbx+40h]
0x14001bc24  mov     r11, [rbx+38h]
0x14001bc28  cmp     eax, r8d
0x14001bc2b  jbe     short loc_14001BC6C
0x14001bc2d  mov     r9d, [rbx+20h]
0x14001bc31  lea     rcx, [rbx+24h]
0x14001bc35  mov     r8, [rbx+18h]
0x14001bc39  mov     rdx, [rbx+8]
0x14001bc3d  mov     [rsp+78h+var_30], eax; int
0x14001bc41  movzx   eax, word ptr [rbx+36h]
0x14001bc45  mov     [rsp+78h+var_38], r10; __int64
0x14001bc4a  mov     [rsp+78h+var_40], r11; __int64
0x14001bc4f  mov     [rsp+78h+var_48], ax; __int16
0x14001bc54  movzx   eax, word ptr [rbx+34h]
0x14001bc58  mov     [rsp+78h+var_50], ax; __int16
0x14001bc5d  mov     [rsp+78h+var_58], rcx; __int64
0x14001bc62  mov     rcx, [rbx]; DeviceObject
0x14001bc65  call    SdpServiceAttributeSearchInternal
0x14001bc6a  jmp     short loc_14001BC7E
0x14001bc6c  lea     rdx, [rbx+50h]
0x14001bc70  xor     r9d, r9d
0x14001bc73  mov     rcx, r10
0x14001bc76  mov     rax, r11
0x14001bc79  call    _guard_dispatch_icall
0x14001bc7e  mov     rcx, rdi; Irp
0x14001bc81  call    cs:__imp_IoFreeIrp
0x14001bc88  nop     dword ptr [rax+rax+00h]
0x14001bc8d  mov     rcx, rbx; P
0x14001bc90  call    cs:__imp_ExFreePool
0x14001bc97  nop     dword ptr [rax+rax+00h]
0x14001bc9c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001bca3  jz      short loc_14001BCC4
0x14001bca5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bcac  mov     r9d, 3Eh ; '>'
0x14001bcb2  mov     [rsp+78h+var_58], rbp
0x14001bcb7  mov     rcx, [rcx+40h]
0x14001bcbb  lea     r8d, [r9-3Bh]
0x14001bcbf  call    WPP_RECORDER_SF_
0x14001bcc4  mov     eax, 0C0000016h
0x14001bcc9  add     rsp, 58h
0x14001bccd  pop     rdi
0x14001bcce  pop     rsi
0x14001bccf  pop     rbp
0x14001bcd0  pop     rbx
0x14001bcd1  retn
```
