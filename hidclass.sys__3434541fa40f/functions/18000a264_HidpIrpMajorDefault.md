# HidpIrpMajorDefault

- ea: `0x18000a264`
- end: `0x18000a42a`
- name: `HidpIrpMajorDefault`
- size: `454`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004c00`
- `0x18003fb20`

## callees

- `0x180006940`
- `0x18000a020`
- `0x18000a264`
- `0x18000c2c0`
- `0x18001f890`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18000a33f`
- `ntoskrnl!IofCompleteRequest` at `0x18000a33f`

## pseudocode

```c
__int64 __fastcall HidpIrpMajorDefault(__int64 a1, IRP *a2, __int64 a3)
{
  int v4; // edx
  _QWORD *FdoExtension; // rdi
  __int64 v6; // r9
  __int64 v7; // rcx
  char v8; // cl
  __int64 v9; // r8
  unsigned int Status; // edi
  PDEVICE_OBJECT *v11; // r8
  char v12; // r10
  _IO_STACK_LOCATION *CurrentStackLocation; // rax

  FdoExtension = (_QWORD *)GetFdoExtension(a1, a2, a3, a1);
  if ( *(_BYTE *)(v7 + 24) )
  {
    LOBYTE(v4) = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (v8 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      v8 = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      LOBYTE(v4) = 0;
    if ( v8 || (_BYTE)v4 )
    {
      v9 = *(_QWORD *)(v6 + 96);
      LOBYTE(v9) = v4;
      LOBYTE(v4) = v8;
      WPP_RECORDER_AND_TRACE_SF_qdqqc(WPP_GLOBAL_Control->AttachedDevice, v4, v9, FdoExtension[84], 5);
    }
    Status = a2->IoStatus.Status;
    IofCompleteRequest(a2, 0);
  }
  else
  {
    v11 = &WPP_GLOBAL_Control;
    LOBYTE(v4) = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (v12 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      v12 = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      LOBYTE(v4) = 0;
    if ( v12 || (_BYTE)v4 )
    {
      LOBYTE(v11) = v4;
      LOBYTE(v4) = v12;
      WPP_RECORDER_AND_TRACE_SF_qqc(WPP_GLOBAL_Control->AttachedDevice, v4, (_DWORD)v11, FdoExtension[84], 5);
    }
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    return (unsigned int)HidpCallDriver(*FdoExtension, a2);
  }
  return Status;
}

```

## disassembly

```asm
0x18000a264  mov     [rsp+arg_0], rbx
0x18000a269  mov     [rsp+arg_8], rsi
0x18000a26e  push    rdi
0x18000a26f  sub     rsp, 70h
0x18000a273  mov     r11, [rdx+0B8h]
0x18000a27a  mov     rbx, rdx
0x18000a27d  mov     r9, rcx
0x18000a280  call    GetFdoExtension
0x18000a285  xor     esi, esi
0x18000a287  mov     rdi, rax
0x18000a28a  cmp     [rcx+18h], sil
0x18000a28e  jz      loc_18000A350
0x18000a294  mov     r10, cs:WPP_GLOBAL_Control
0x18000a29b  lea     r8, WPP_GLOBAL_Control
0x18000a2a2  mov     dl, 1
0x18000a2a4  cmp     r10, r8
0x18000a2a7  jz      short loc_18000A2BB
0x18000a2a9  mov     ecx, [r10+2Ch]
0x18000a2ad  test    cl, 8
0x18000a2b0  jz      short loc_18000A2BB
0x18000a2b2  cmp     byte ptr [r10+29h], 5
0x18000a2b7  mov     cl, dl
0x18000a2b9  jnb     short loc_18000A2BE
0x18000a2bb  mov     cl, sil
0x18000a2be  lea     rax, WPP_RECORDER_INITIALIZED
0x18000a2c5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000a2cc  jz      short loc_18000A2D5
0x18000a2ce  cmp     [r10+48h], si
0x18000a2d3  jnz     short loc_18000A2D8
0x18000a2d5  mov     dl, sil
0x18000a2d8  test    cl, cl
0x18000a2da  jnz     short loc_18000A2E0
0x18000a2dc  test    dl, dl
0x18000a2de  jz      short loc_18000A337
0x18000a2e0  mov     r8, [r9+60h]
0x18000a2e4  mov     al, [r11]
0x18000a2e7  mov     [rsp+78h+var_18], al
0x18000a2eb  mov     rax, [r9+50h]
0x18000a2ef  mov     [rsp+78h+var_20], rbx
0x18000a2f4  mov     [rsp+78h+var_28], rax
0x18000a2f9  mov     eax, [r9+28h]
0x18000a2fd  mov     r9, [rdi+2A0h]
0x18000a304  mov     dword ptr [rsp+78h+var_30], eax
0x18000a308  mov     rax, [r8+20h]
0x18000a30c  mov     r8b, dl
0x18000a30f  mov     [rsp+78h+var_38], rax
0x18000a314  mov     dl, cl
0x18000a316  mov     rcx, [r10+18h]
0x18000a31a  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18000a321  mov     [rsp+78h+var_40], rax
0x18000a326  mov     [rsp+78h+var_48], 12h
0x18000a32d  mov     [rsp+78h+var_58], 5
0x18000a332  call    WPP_RECORDER_AND_TRACE_SF_qdqqc
0x18000a337  mov     edi, [rbx+30h]
0x18000a33a  xor     edx, edx; PriorityBoost
0x18000a33c  mov     rcx, rbx; Irp
0x18000a33f  call    cs:__imp_IofCompleteRequest
0x18000a346  nop     dword ptr [rax+rax+00h]
0x18000a34b  jmp     loc_18000A415
0x18000a350  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a357  lea     r8, WPP_GLOBAL_Control
0x18000a35e  mov     dl, 1
0x18000a360  cmp     rcx, r8
0x18000a363  jz      short loc_18000A375
0x18000a365  mov     eax, [rcx+2Ch]
0x18000a368  test    al, 8
0x18000a36a  jz      short loc_18000A375
0x18000a36c  cmp     byte ptr [rcx+29h], 5
0x18000a370  mov     r10b, dl
0x18000a373  jnb     short loc_18000A378
0x18000a375  mov     r10b, sil
0x18000a378  lea     rax, WPP_RECORDER_INITIALIZED
0x18000a37f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000a386  jz      short loc_18000A38E
0x18000a388  cmp     [rcx+48h], si
0x18000a38c  jnz     short loc_18000A391
0x18000a38e  mov     dl, sil
0x18000a391  test    r10b, r10b
0x18000a394  jnz     short loc_18000A39A
0x18000a396  test    dl, dl
0x18000a398  jz      short loc_18000A3DC
0x18000a39a  mov     al, [r11]
0x18000a39d  mov     r8b, dl
0x18000a3a0  mov     r9, [rdi+2A0h]
0x18000a3a7  mov     dl, r10b
0x18000a3aa  mov     rcx, [rcx+18h]
0x18000a3ae  mov     byte ptr [rsp+78h+var_28], al
0x18000a3b2  mov     rax, [rdi]
0x18000a3b5  mov     [rsp+78h+var_30], rbx
0x18000a3ba  mov     [rsp+78h+var_38], rax
0x18000a3bf  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18000a3c6  mov     [rsp+78h+var_40], rax
0x18000a3cb  mov     [rsp+78h+var_48], 13h
0x18000a3d2  mov     [rsp+78h+var_58], 5
0x18000a3d7  call    WPP_RECORDER_AND_TRACE_SF_qqc
0x18000a3dc  mov     rax, [rbx+0B8h]
0x18000a3e3  mov     rdx, rbx
0x18000a3e6  movups  xmm0, xmmword ptr [rax]
0x18000a3e9  movups  xmmword ptr [rax-48h], xmm0
0x18000a3ed  movups  xmm1, xmmword ptr [rax+10h]
0x18000a3f1  movups  xmmword ptr [rax-38h], xmm1
0x18000a3f5  movups  xmm0, xmmword ptr [rax+20h]
0x18000a3f9  movups  xmmword ptr [rax-28h], xmm0
0x18000a3fd  movsd   xmm1, qword ptr [rax+30h]
0x18000a402  movsd   qword ptr [rax-18h], xmm1
0x18000a407  mov     [rax-45h], sil
0x18000a40b  mov     rcx, [rdi]
0x18000a40e  call    HidpCallDriver
0x18000a413  mov     edi, eax
0x18000a415  lea     r11, [rsp+78h+var_8]
0x18000a41a  mov     eax, edi
0x18000a41c  mov     rbx, [r11+10h]
0x18000a420  mov     rsi, [r11+18h]
0x18000a424  mov     rsp, r11
0x18000a427  pop     rdi
0x18000a428  retn
```
