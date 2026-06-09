# CleanupDriverEntry

- ea: `0x14002cbc4`
- end: `0x14002cd9a`
- name: `CleanupDriverEntry`
- size: `470`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140044a00`
- `0x140053828`

## callees

- `0x14001a2b8`
- `0x140027df4`
- `0x14002bfc0`
- `0x14002cbc4`
- `0x140044468`
- `0x140044864`
- `0x14004488c`
- `0x140044bc4`
- `0x140044c80`
- `0x14004552c`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14002cc74`
- `ntoskrnl!IoFreeIrp` at `0x14002cc74`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002cd11`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002cd11`
- `ntoskrnl!IoFreeMdl` at `0x14002cca4`
- `ntoskrnl!IoFreeMdl` at `0x14002cca4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cc5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cc95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ccf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cc5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cc95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ccf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd74`

## pseudocode

```c
__int64 __fastcall CleanupDriverEntry(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  PMDL v7; // rbx
  PVOID v8; // rcx
  __int64 v9; // rax
  __int64 result; // rax

  v1 = a1 - 1;
  if ( v1 )
  {
    v2 = v1 - 1;
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( v4 )
        {
          v5 = v4 - 1;
          if ( v5 )
          {
            v6 = v5 - 1;
            if ( v6 )
            {
              if ( v6 != 1 )
                goto LABEL_34;
              NbtDeregisterNsiNotificationHandlers();
              NbtSetNsi9FTriageBlock(0);
            }
            if ( pWinsDeviceContext )
            {
              NbtDestroyDevice(pWinsDeviceContext, 0);
              pWinsDeviceContext = 0;
            }
            NbtAcdUnbind();
          }
          if ( pNbtSmbDevice )
          {
            NbtDestroyDevice(pNbtSmbDevice, 0);
            pNbtSmbDevice = 0;
          }
          if ( Dpc )
            ExFreePoolWithTag(Dpc, 0);
          if ( Irp )
            IoFreeIrp(Irp);
        }
        while ( 1 )
        {
          v7 = Mdl;
          if ( !Mdl )
            break;
          Mdl = Mdl->Next;
          ExFreePoolWithTag((char *)v7->StartVa + v7->ByteOffset, 0);
          IoFreeMdl(v7);
        }
      }
      DestroyTimerQ();
      while ( 1 )
      {
        v8 = qword_140039470;
        if ( qword_140039470 == &qword_140039470 )
          break;
        if ( *((PVOID **)qword_140039470 + 1) != &qword_140039470
          || (v9 = *(_QWORD *)qword_140039470, *(PVOID *)(*(_QWORD *)qword_140039470 + 8LL) != qword_140039470) )
        {
          __fastfail(3u);
        }
        qword_140039470 = *(PVOID *)qword_140039470;
        *(_QWORD *)(v9 + 8) = &qword_140039470;
        ExFreePoolWithTag(v8, 0);
      }
      DestroyHashTables();
      ExDeleteResourceLite(&Resource);
    }
    if ( Src )
      ExFreePoolWithTag(Src, 0);
    if ( Str2 )
      ExFreePoolWithTag(Str2, 0);
    if ( qword_1400394E0 )
      ExFreePoolWithTag(qword_1400394E0, 0);
  }
  ExFreePoolWithTag(stru_1400394D0.Buffer, 0);
LABEL_34:
  wil_UninitializeFeatureStaging();
  result = Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline();
  if ( (_DWORD)result )
    return TraceLoggingUnregister_EtwUnregister();
  return result;
}

```

## disassembly

```asm
0x14002cbc4  push    rbx
0x14002cbc6  sub     rsp, 20h
0x14002cbca  sub     ecx, 1
0x14002cbcd  jz      loc_14002CD6B
0x14002cbd3  sub     ecx, 1
0x14002cbd6  jz      loc_14002CD1D
0x14002cbdc  sub     ecx, 1
0x14002cbdf  jz      loc_14002CCBC
0x14002cbe5  sub     ecx, 1
0x14002cbe8  jz      loc_14002CCB0
0x14002cbee  sub     ecx, 1
0x14002cbf1  jz      short loc_14002CC30
0x14002cbf3  sub     ecx, 1
0x14002cbf6  jz      short loc_14002CC0D
0x14002cbf8  cmp     ecx, 1
0x14002cbfb  jnz     loc_14002CD80
0x14002cc01  call    NbtDeregisterNsiNotificationHandlers
0x14002cc06  xor     ecx, ecx
0x14002cc08  call    NbtSetNsi9FTriageBlock
0x14002cc0d  mov     rcx, cs:pWinsDeviceContext; DeviceObject
0x14002cc14  test    rcx, rcx
0x14002cc17  jz      short loc_14002CC2B
0x14002cc19  xor     edx, edx
0x14002cc1b  call    NbtDestroyDevice
0x14002cc20  mov     cs:pWinsDeviceContext, 0
0x14002cc2b  call    NbtAcdUnbind
0x14002cc30  mov     rcx, cs:pNbtSmbDevice; DeviceObject
0x14002cc37  test    rcx, rcx
0x14002cc3a  jz      short loc_14002CC4E
0x14002cc3c  xor     edx, edx
0x14002cc3e  call    NbtDestroyDevice
0x14002cc43  mov     cs:pNbtSmbDevice, 0
0x14002cc4e  mov     rcx, cs:Dpc; P
0x14002cc55  test    rcx, rcx
0x14002cc58  jz      short loc_14002CC68
0x14002cc5a  xor     edx, edx; Tag
0x14002cc5c  call    cs:__imp_ExFreePoolWithTag
0x14002cc63  nop     dword ptr [rax+rax+00h]
0x14002cc68  mov     rcx, cs:Irp; Irp
0x14002cc6f  test    rcx, rcx
0x14002cc72  jz      short loc_14002CCB0
0x14002cc74  call    cs:__imp_IoFreeIrp
0x14002cc7b  nop     dword ptr [rax+rax+00h]
0x14002cc80  jmp     short loc_14002CCB0
0x14002cc82  mov     rax, [rbx]
0x14002cc85  xor     edx, edx; Tag
0x14002cc87  mov     cs:Mdl.Next, rax
0x14002cc8e  mov     ecx, [rbx+2Ch]
0x14002cc91  add     rcx, [rbx+20h]; P
0x14002cc95  call    cs:__imp_ExFreePoolWithTag
0x14002cc9c  nop     dword ptr [rax+rax+00h]
0x14002cca1  mov     rcx, rbx; Mdl
0x14002cca4  call    cs:__imp_IoFreeMdl
0x14002ccab  nop     dword ptr [rax+rax+00h]
0x14002ccb0  mov     rbx, cs:Mdl.Next
0x14002ccb7  test    rbx, rbx
0x14002ccba  jnz     short loc_14002CC82
0x14002ccbc  call    DestroyTimerQ
0x14002ccc1  lea     rbx, qword_140039470
0x14002ccc8  mov     rcx, cs:qword_140039470; P
0x14002cccf  cmp     rcx, rbx
0x14002ccd2  jz      short loc_14002CD05
0x14002ccd4  cmp     [rcx+8], rbx
0x14002ccd8  jnz     short loc_14002CCFE
0x14002ccda  mov     rax, [rcx]
0x14002ccdd  cmp     [rax+8], rcx
0x14002cce1  jnz     short loc_14002CCFE
0x14002cce3  mov     cs:qword_140039470, rax
0x14002ccea  xor     edx, edx; Tag
0x14002ccec  mov     [rax+8], rbx
0x14002ccf0  call    cs:__imp_ExFreePoolWithTag
0x14002ccf7  nop     dword ptr [rax+rax+00h]
0x14002ccfc  jmp     short loc_14002CCC8
0x14002ccfe  mov     ecx, 3
0x14002cd03  int     29h; Win8: RtlFailFast(ecx)
0x14002cd05  call    DestroyHashTables
0x14002cd0a  lea     rcx, Resource; Resource
0x14002cd11  call    cs:__imp_ExDeleteResourceLite
0x14002cd18  nop     dword ptr [rax+rax+00h]
0x14002cd1d  mov     rcx, cs:Src; P
0x14002cd24  test    rcx, rcx
0x14002cd27  jz      short loc_14002CD37
0x14002cd29  xor     edx, edx; Tag
0x14002cd2b  call    cs:__imp_ExFreePoolWithTag
0x14002cd32  nop     dword ptr [rax+rax+00h]
0x14002cd37  mov     rcx, cs:Str2; P
0x14002cd3e  test    rcx, rcx
0x14002cd41  jz      short loc_14002CD51
0x14002cd43  xor     edx, edx; Tag
0x14002cd45  call    cs:__imp_ExFreePoolWithTag
0x14002cd4c  nop     dword ptr [rax+rax+00h]
0x14002cd51  mov     rcx, cs:qword_1400394E0; P
0x14002cd58  test    rcx, rcx
0x14002cd5b  jz      short loc_14002CD6B
0x14002cd5d  xor     edx, edx; Tag
0x14002cd5f  call    cs:__imp_ExFreePoolWithTag
0x14002cd66  nop     dword ptr [rax+rax+00h]
0x14002cd6b  mov     rcx, cs:stru_1400394D0.Buffer; P
0x14002cd72  xor     edx, edx; Tag
0x14002cd74  call    cs:__imp_ExFreePoolWithTag
0x14002cd7b  nop     dword ptr [rax+rax+00h]
0x14002cd80  call    wil_UninitializeFeatureStaging
0x14002cd85  call    Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline
0x14002cd8a  test    eax, eax
0x14002cd8c  jz      short loc_14002CD93
0x14002cd8e  call    TraceLoggingUnregister_EtwUnregister
0x14002cd93  add     rsp, 20h
0x14002cd97  pop     rbx
0x14002cd98  retn
```
