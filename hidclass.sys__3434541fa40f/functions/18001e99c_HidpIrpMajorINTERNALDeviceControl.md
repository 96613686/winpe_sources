# HidpIrpMajorINTERNALDeviceControl

- ea: `0x18001e99c`
- end: `0x18001eb20`
- name: `HidpIrpMajorINTERNALDeviceControl`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004c00`

## callees

- `0x18000c2c0`
- `0x18001952c`
- `0x18001e99c`
- `0x18001ed14`
- `0x18001f788`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18001eb08`
- `ntoskrnl!IofCompleteRequest` at `0x18001eb08`

## pseudocode

```c
__int64 __fastcall HidpIrpMajorINTERNALDeviceControl(__int64 a1, IRP *a2, __int64 a3, __int64 a4)
{
  unsigned int LowPart; // ebp
  __int64 FdoExtension; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // esi
  const char *v12; // r8
  __int64 v13; // r9
  int v14; // eax
  char v16; // [rsp+50h] [rbp-48h]

  LowPart = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  FdoExtension = GetFdoExtension(a1, a2, a1, a4);
  v9 = FdoExtension;
  if ( !*(_BYTE *)(v10 + 24) )
  {
    v11 = -1073741585;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      LOBYTE(v7) = 0;
    }
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqLd(WPP_GLOBAL_Control->AttachedDevice, v7, v8, *(_QWORD *)(FdoExtension + 672));
    }
    v12 = "Ioctl sent to FDO";
    goto LABEL_19;
  }
  *(_QWORD *)(v7 + 56) = 0;
  if ( !*(_DWORD *)(FdoExtension + 1720) )
  {
    v11 = -1073741667;
    v12 = "Device not started";
LABEL_19:
    TraceLoggingIrpInternalIoctlFailed(v9, LowPart, v12);
    goto LABEL_20;
  }
  v11 = *(_DWORD *)(v7 + 48);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
    || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
  {
    LOBYTE(v7) = 0;
  }
  if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = *(_QWORD *)(v8 + 96);
    v16 = *(_QWORD *)(v8 + 80);
    v14 = *(_DWORD *)(v8 + 40);
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qdqLd(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      v8,
      *(_QWORD *)(v9 + 672),
      3,
      4,
      62,
      (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
      *(_QWORD *)(v13 + 32),
      v14,
      v16,
      LowPart,
      v11);
  }
LABEL_20:
  a2->IoStatus.Status = v11;
  IofCompleteRequest(a2, 0);
  return v11;
}

```

## disassembly

```asm
0x18001e99c  push    rbx
0x18001e99e  push    rbp
0x18001e99f  push    rsi
0x18001e9a0  push    rdi
0x18001e9a1  sub     rsp, 78h
0x18001e9a5  mov     rax, [rdx+0B8h]
0x18001e9ac  mov     rbx, rdx
0x18001e9af  mov     r8, rcx
0x18001e9b2  mov     ebp, [rax+18h]
0x18001e9b5  call    GetFdoExtension
0x18001e9ba  xor     r9d, r9d
0x18001e9bd  mov     rdi, rax
0x18001e9c0  cmp     [rcx+18h], r9b
0x18001e9c4  jnz     short loc_18001EA3B
0x18001e9c6  mov     esi, 0C00000EFh
0x18001e9cb  mov     r10, cs:WPP_GLOBAL_Control
0x18001e9d2  lea     rax, WPP_GLOBAL_Control
0x18001e9d9  cmp     r10, rax
0x18001e9dc  jz      short loc_18001E9F0
0x18001e9de  mov     ecx, [r10+2Ch]
0x18001e9e2  test    cl, 8
0x18001e9e5  jz      short loc_18001E9F0
0x18001e9e7  cmp     byte ptr [r10+29h], 4
0x18001e9ec  mov     dl, 1
0x18001e9ee  jnb     short loc_18001E9F3
0x18001e9f0  mov     dl, r9b
0x18001e9f3  lea     rax, WPP_RECORDER_INITIALIZED
0x18001e9fa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001ea01  setnz   r8b
0x18001ea05  test    dl, dl
0x18001ea07  jnz     short loc_18001EA0E
0x18001ea09  test    r8b, r8b
0x18001ea0c  jz      short loc_18001EA2F
0x18001ea0e  mov     rax, [rdi]
0x18001ea11  mov     r9, [rdi+2A0h]
0x18001ea18  mov     rcx, [r10+18h]
0x18001ea1c  mov     dword ptr [rsp+98h+var_48], ebp
0x18001ea20  mov     [rsp+98h+var_50], rbx
0x18001ea25  mov     [rsp+98h+var_58], rax
0x18001ea2a  call    WPP_RECORDER_AND_TRACE_SF_qqLd
0x18001ea2f  lea     r8, aIoctlSentToFdo; "Ioctl sent to FDO"
0x18001ea36  jmp     loc_18001EAF6
0x18001ea3b  mov     [rdx+38h], r9
0x18001ea3f  cmp     [rax+6B8h], r9d
0x18001ea46  jz      loc_18001EAEA
0x18001ea4c  mov     esi, [rdx+30h]
0x18001ea4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea56  lea     rax, WPP_GLOBAL_Control
0x18001ea5d  cmp     rcx, rax
0x18001ea60  jz      short loc_18001EA71
0x18001ea62  mov     eax, [rcx+2Ch]
0x18001ea65  test    al, 8
0x18001ea67  jz      short loc_18001EA71
0x18001ea69  cmp     byte ptr [rcx+29h], 3
0x18001ea6d  mov     dl, 1
0x18001ea6f  jnb     short loc_18001EA74
0x18001ea71  mov     dl, r9b
0x18001ea74  lea     rax, WPP_RECORDER_INITIALIZED
0x18001ea7b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001ea82  setnz   r10b
0x18001ea86  test    dl, dl
0x18001ea88  jnz     short loc_18001EA8F
0x18001ea8a  test    r10b, r10b
0x18001ea8d  jz      short loc_18001EB00
0x18001ea8f  mov     rax, [r8+50h]
0x18001ea93  mov     r9, [r8+60h]
0x18001ea97  mov     rcx, [rcx+18h]
0x18001ea9b  mov     [rsp+98h+var_38], esi
0x18001ea9f  mov     [rsp+98h+var_40], ebp
0x18001eaa3  mov     [rsp+98h+var_48], rax
0x18001eaa8  mov     eax, [r8+28h]
0x18001eaac  mov     r8b, r10b
0x18001eaaf  mov     dword ptr [rsp+98h+var_50], eax
0x18001eab3  mov     rax, [r9+20h]
0x18001eab7  mov     r9, [rdi+2A0h]
0x18001eabe  mov     [rsp+98h+var_58], rax
0x18001eac3  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18001eaca  mov     [rsp+98h+var_60], rax
0x18001eacf  mov     [rsp+98h+var_68], 3Eh ; '>'
0x18001ead6  mov     [rsp+98h+var_70], 4
0x18001eade  mov     [rsp+98h+var_78], 3
0x18001eae3  call    WPP_RECORDER_AND_TRACE_SF_qdqLd
0x18001eae8  jmp     short loc_18001EB00
0x18001eaea  mov     esi, 0C000009Dh
0x18001eaef  lea     r8, aDeviceNotStart; "Device not started"
0x18001eaf6  mov     edx, ebp
0x18001eaf8  mov     rcx, rdi
0x18001eafb  call    TraceLoggingIrpInternalIoctlFailed
0x18001eb00  xor     edx, edx; PriorityBoost
0x18001eb02  mov     [rbx+30h], esi
0x18001eb05  mov     rcx, rbx; Irp
0x18001eb08  call    cs:__imp_IofCompleteRequest
0x18001eb0f  nop     dword ptr [rax+rax+00h]
0x18001eb14  mov     eax, esi
0x18001eb16  add     rsp, 78h
0x18001eb1a  pop     rdi
0x18001eb1b  pop     rsi
0x18001eb1c  pop     rbp
0x18001eb1d  pop     rbx
0x18001eb1e  retn
```
