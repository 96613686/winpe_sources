# PcpRegisterCallout

- ea: `0x14001ee0c`
- end: `0x14001f138`
- name: `PcpRegisterCallout`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d284`

## callees

- `0x14000eb54`
- `0x140013110`
- `0x140013600`
- `0x14001ee0c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001eea7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001eea7`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001f006`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001f104`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001f006`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001f104`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x14001efaa`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x14001f07f`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x14001efaa`
- `fwpkclnt!FwpiCalloutRegisterAndAddWithoutDevice0` at `0x14001f07f`
- `fwpkclnt!FwpmEngineOpen0` at `0x14001eee7`
- `fwpkclnt!FwpmEngineOpen0` at `0x14001eee7`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x14001f0d7`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x14001f0d7`
- `fwpkclnt!FwpmEngineClose0` at `0x14001f017`
- `fwpkclnt!FwpmEngineClose0` at `0x14001f017`

## pseudocode

```c
__int64 PcpRegisterCallout()
{
  unsigned int v0; // ebx
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  HANDLE engineHandle; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE engineHandle_8[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v9; // [rsp+50h] [rbp-B8h]
  __int128 v10; // [rsp+60h] [rbp-A8h]
  __int128 v11; // [rsp+70h] [rbp-98h] BYREF
  __int128 v12; // [rsp+80h] [rbp-88h]
  __int128 v13; // [rsp+90h] [rbp-78h]
  _OWORD v14[6]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v15[6]; // [rsp+108h] [rbp+0h] BYREF

  *(_OWORD *)engineHandle_8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  memset(v14, 0, 0x58u);
  memset(v15, 0, 0x58u);
  v0 = 0;
  engineHandle = 0;
  if ( PcgWfpEngineHandle )
    return 0;
  if ( KeWaitForSingleObject(&PcgWfpInitSemaphore, Executive, 0, 0, 0) )
    return 3221225473LL;
  if ( !PcgWfpEngineHandle )
  {
    v2 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_529dca1514e63b6a2d0440b789ffd930_Traceguids, v2);
      }
      v0 = -1073741823;
      goto LABEL_25;
    }
    *(_QWORD *)&v9 = 0;
    *((_QWORD *)&v9 + 1) = PcWfpCallout;
    *(_QWORD *)&v10 = PcWfpNotify;
    *((_QWORD *)&v10 + 1) = 0;
    *(_OWORD *)engineHandle_8 = PcgWfpCalloutGuid;
    memset(v14, 0, 0x58u);
    *(_QWORD *)&v14[1] = L"QoS";
    v14[4] = FWPM_LAYER_OUTBOUND_TRANSPORT_V4;
    v14[0] = PcgWfpCalloutGuid;
    v3 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, engineHandle_8, v14, 0, 0);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_529dca1514e63b6a2d0440b789ffd930_Traceguids, v3);
      }
LABEL_17:
      KeReleaseSemaphore(&PcgWfpInitSemaphore, 0, 1, 0);
      FwpmEngineClose0(engineHandle);
      return 3221225473LL;
    }
    *(_QWORD *)&v12 = 0;
    *((_QWORD *)&v12 + 1) = PcWfpCallout;
    *(_QWORD *)&v13 = PcWfpNotify;
    v11 = PcgWfpV6CalloutGuid;
    *((_QWORD *)&v13 + 1) = 0;
    memset(v15, 0, 0x58u);
    *(_QWORD *)&v15[1] = L"QoS";
    v15[4] = FWPM_LAYER_OUTBOUND_TRANSPORT_V6;
    v15[0] = PcgWfpV6CalloutGuid;
    v4 = FwpiCalloutRegisterAndAddWithoutDevice0(engineHandle, &v11, v15, 0, 0);
    v6 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_529dca1514e63b6a2d0440b789ffd930_Traceguids, v4);
      }
      FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &PcgWfpCalloutGuid, v5, v6);
      goto LABEL_17;
    }
    PcgWfpEngineHandle = engineHandle;
  }
LABEL_25:
  KeReleaseSemaphore(&PcgWfpInitSemaphore, 0, 1, 0);
  return v0;
}

```

## disassembly

```asm
0x14001ee0c  mov     rax, rsp
0x14001ee0f  push    rbp
0x14001ee10  push    rbx
0x14001ee11  push    rsi
0x14001ee12  push    r12
0x14001ee14  push    r14
0x14001ee16  push    r15
0x14001ee18  lea     rbp, [rax-0B8h]
0x14001ee1f  sub     rsp, 188h
0x14001ee26  movaps  xmmword ptr [rax-48h], xmm6
0x14001ee2a  mov     rax, cs:__security_cookie
0x14001ee31  xor     rax, rsp
0x14001ee34  mov     [rbp+0B0h+var_50], rax
0x14001ee38  xorps   xmm0, xmm0
0x14001ee3b  lea     rcx, [rbp+0B0h+var_110]; void *
0x14001ee3f  xorps   xmm1, xmm1
0x14001ee42  mov     esi, 58h ; 'X'
0x14001ee47  mov     r8d, esi; Size
0x14001ee4a  xor     edx, edx; Val
0x14001ee4c  movups  xmmword ptr [rsp+1B0h+engineHandle+8], xmm0
0x14001ee51  movups  [rsp+1B0h+var_170+8], xmm0
0x14001ee56  movups  [rsp+1B0h+var_160+8], xmm0
0x14001ee5b  movups  [rsp+1B0h+var_150+8], xmm1
0x14001ee60  movups  [rsp+1B0h+var_140+8], xmm1
0x14001ee65  movups  [rbp+0B0h+var_128], xmm1
0x14001ee69  call    memset
0x14001ee6e  mov     r8d, esi; Size
0x14001ee71  lea     rcx, [rbp+0B0h+var_B0]; void *
0x14001ee75  xor     edx, edx; Val
0x14001ee77  call    memset
0x14001ee7c  xor     ebx, ebx
0x14001ee7e  cmp     cs:PcgWfpEngineHandle, rbx
0x14001ee85  mov     [rsp+1B0h+engineHandle], rbx
0x14001ee8a  jz      short loc_14001EE93
0x14001ee8c  xor     eax, eax
0x14001ee8e  jmp     loc_14001F112
0x14001ee93  xor     r9d, r9d; Alertable
0x14001ee96  mov     [rsp+20h], rbx; Timeout
0x14001ee9b  xor     r8d, r8d; WaitMode
0x14001ee9e  lea     rcx, PcgWfpInitSemaphore; Object
0x14001eea5  xor     edx, edx; WaitReason
0x14001eea7  call    cs:__imp_KeWaitForSingleObject
0x14001eeae  nop     dword ptr [rax+rax+00h]
0x14001eeb3  test    eax, eax
0x14001eeb5  jz      short loc_14001EEC1
0x14001eeb7  mov     eax, 0C0000001h
0x14001eebc  jmp     loc_14001F112
0x14001eec1  cmp     cs:PcgWfpEngineHandle, rbx
0x14001eec8  jnz     loc_14001F0F4
0x14001eece  xor     r9d, r9d; session
0x14001eed1  lea     rax, [rsp+1B0h+engineHandle]
0x14001eed6  xor     r8d, r8d; authIdentity
0x14001eed9  mov     [rsp+20h], rax; engineHandle
0x14001eede  xor     ecx, ecx; serverName
0x14001eee0  lea     r14d, [r9+0Ah]
0x14001eee4  mov     edx, r14d; authnService
0x14001eee7  call    cs:__imp_FwpmEngineOpen0
0x14001eeee  nop     dword ptr [rax+rax+00h]
0x14001eef3  mov     r9d, eax
0x14001eef6  test    eax, eax
0x14001eef8  jz      short loc_14001EF3B
0x14001eefa  mov     r10, cs:WPP_GLOBAL_Control
0x14001ef01  lea     rcx, WPP_GLOBAL_Control
0x14001ef08  cmp     r10, rcx
0x14001ef0b  jz      short loc_14001EF31
0x14001ef0d  cmp     byte ptr [r10+29h], 2
0x14001ef12  jb      short loc_14001EF31
0x14001ef14  test    dword ptr [r10+2Ch], 800h
0x14001ef1c  jz      short loc_14001EF31
0x14001ef1e  mov     rcx, [r10+18h]
0x14001ef22  lea     r8, WPP_529dca1514e63b6a2d0440b789ffd930_Traceguids
0x14001ef29  mov     edx, r14d
0x14001ef2c  call    WPP_SF_D
0x14001ef31  mov     ebx, 0C0000001h
0x14001ef36  jmp     loc_14001F0F4
0x14001ef3b  movups  xmm6, cs:PcgWfpCalloutGuid
0x14001ef42  lea     r14, PcWfpCallout
0x14001ef49  mov     qword ptr [rsp+1B0h+var_170+8], rbx
0x14001ef4e  lea     r15, PcWfpNotify
0x14001ef55  mov     qword ptr [rsp+1B0h+var_160], r14
0x14001ef5a  mov     r8, rsi; Size
0x14001ef5d  mov     qword ptr [rsp+1B0h+var_160+8], r15
0x14001ef62  xor     edx, edx; Val
0x14001ef64  mov     qword ptr [rsp+1B0h+var_150], rbx
0x14001ef69  lea     rcx, [rbp+0B0h+var_110]; void *
0x14001ef6d  movdqu  xmmword ptr [rsp+1B0h+engineHandle+8], xmm6
0x14001ef73  call    memset
0x14001ef78  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_TRANSPORT_V4.Data1
0x14001ef7f  mov     rcx, [rsp+1B0h+engineHandle]
0x14001ef84  lea     r12, aQos; "QoS"
0x14001ef8b  xor     r9d, r9d
0x14001ef8e  mov     [rbp+0B0h+var_100], r12
0x14001ef92  lea     r8, [rbp+0B0h+var_110]
0x14001ef96  mov     [rsp+20h], rbx
0x14001ef9b  lea     rdx, [rsp+1B0h+engineHandle+8]
0x14001efa0  movdqu  [rbp+0B0h+var_D0], xmm0
0x14001efa5  movdqu  [rbp+0B0h+var_110], xmm6
0x14001efaa  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x14001efb1  nop     dword ptr [rax+rax+00h]
0x14001efb6  mov     r9d, eax
0x14001efb9  test    eax, eax
0x14001efbb  jz      short loc_14001F028
0x14001efbd  mov     r10, cs:WPP_GLOBAL_Control
0x14001efc4  lea     rcx, WPP_GLOBAL_Control
0x14001efcb  cmp     r10, rcx
0x14001efce  jz      short loc_14001EFF6
0x14001efd0  cmp     byte ptr [r10+29h], 2
0x14001efd5  jb      short loc_14001EFF6
0x14001efd7  test    dword ptr [r10+2Ch], 800h
0x14001efdf  jz      short loc_14001EFF6
0x14001efe1  mov     rcx, [r10+18h]
0x14001efe5  lea     r8, WPP_529dca1514e63b6a2d0440b789ffd930_Traceguids
0x14001efec  mov     edx, 0Bh
0x14001eff1  call    WPP_SF_D
0x14001eff6  xor     r9d, r9d; Wait
0x14001eff9  lea     rcx, PcgWfpInitSemaphore; Semaphore
0x14001f000  xor     edx, edx; Increment
0x14001f002  lea     r8d, [r9+1]; Adjustment
0x14001f006  call    cs:__imp_KeReleaseSemaphore
0x14001f00d  nop     dword ptr [rax+rax+00h]
0x14001f012  mov     rcx, [rsp+1B0h+engineHandle]; engineHandle
0x14001f017  call    cs:__imp_FwpmEngineClose0
0x14001f01e  nop     dword ptr [rax+rax+00h]
0x14001f023  jmp     loc_14001EEB7
0x14001f028  movups  xmm6, cs:PcgWfpV6CalloutGuid
0x14001f02f  mov     r8, rsi; Size
0x14001f032  mov     qword ptr [rsp+1B0h+var_140+8], rbx
0x14001f037  xor     edx, edx; Val
0x14001f039  mov     [rbp+0B0h+var_130], r14
0x14001f03d  lea     rcx, [rbp+0B0h+var_B0]; void *
0x14001f041  mov     qword ptr [rbp+0B0h+var_128], r15
0x14001f045  movdqu  [rsp+1B0h+var_150+8], xmm6
0x14001f04b  mov     qword ptr [rbp+0B0h+var_128+8], rbx
0x14001f04f  call    memset
0x14001f054  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_TRANSPORT_V6.Data1
0x14001f05b  mov     rcx, [rsp+1B0h+engineHandle]
0x14001f060  lea     r8, [rbp+0B0h+var_B0]
0x14001f064  xor     r9d, r9d
0x14001f067  mov     [rbp+0B0h+var_A0], r12
0x14001f06b  lea     rdx, [rsp+1B0h+var_150+8]
0x14001f070  mov     [rsp+20h], rbx
0x14001f075  movdqu  [rbp+0B0h+var_70], xmm0
0x14001f07a  movdqu  [rbp+0B0h+var_B0], xmm6
0x14001f07f  call    cs:__imp_FwpiCalloutRegisterAndAddWithoutDevice0
0x14001f086  nop     dword ptr [rax+rax+00h]
0x14001f08b  mov     r9d, eax
0x14001f08e  test    eax, eax
0x14001f090  jz      short loc_14001F0E8
0x14001f092  mov     r10, cs:WPP_GLOBAL_Control
0x14001f099  lea     rcx, WPP_GLOBAL_Control
0x14001f0a0  cmp     r10, rcx
0x14001f0a3  jz      short loc_14001F0CB
0x14001f0a5  cmp     byte ptr [r10+29h], 2
0x14001f0aa  jb      short loc_14001F0CB
0x14001f0ac  test    dword ptr [r10+2Ch], 800h
0x14001f0b4  jz      short loc_14001F0CB
0x14001f0b6  mov     rcx, [r10+18h]
0x14001f0ba  lea     r8, WPP_529dca1514e63b6a2d0440b789ffd930_Traceguids
0x14001f0c1  mov     edx, 0Ch
0x14001f0c6  call    WPP_SF_D
0x14001f0cb  mov     rcx, [rsp+1B0h+engineHandle]
0x14001f0d0  lea     rdx, PcgWfpCalloutGuid
0x14001f0d7  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x14001f0de  nop     dword ptr [rax+rax+00h]
0x14001f0e3  jmp     loc_14001EFF6
0x14001f0e8  mov     rax, [rsp+1B0h+engineHandle]
0x14001f0ed  mov     cs:PcgWfpEngineHandle, rax
0x14001f0f4  xor     r9d, r9d; Wait
0x14001f0f7  lea     rcx, PcgWfpInitSemaphore; Semaphore
0x14001f0fe  xor     edx, edx; Increment
0x14001f100  lea     r8d, [r9+1]; Adjustment
0x14001f104  call    cs:__imp_KeReleaseSemaphore
0x14001f10b  nop     dword ptr [rax+rax+00h]
0x14001f110  mov     eax, ebx
0x14001f112  mov     rcx, [rbp+0B0h+var_50]
0x14001f116  xor     rcx, rsp; StackCookie
0x14001f119  call    __security_check_cookie
0x14001f11e  movaps  xmm6, [rsp+1B0h+var_48+8]
0x14001f126  add     rsp, 188h
0x14001f12d  pop     r15
0x14001f12f  pop     r14
0x14001f131  pop     r12
0x14001f133  pop     rsi
0x14001f134  pop     rbx
0x14001f135  pop     rbp
0x14001f136  retn
```
