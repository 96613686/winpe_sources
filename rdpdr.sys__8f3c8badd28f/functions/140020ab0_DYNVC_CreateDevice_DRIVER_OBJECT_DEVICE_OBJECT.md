# DYNVC_CreateDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT * *)

- ea: `0x140020ab0`
- end: `0x140020c30`
- name: `?DYNVC_CreateDevice@@YAJPEAU_DRIVER_OBJECT@@PEAPEAU_DEVICE_OBJECT@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, struct _DEVICE_OBJECT **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002e078`

## callees

- `0x140001660`
- `0x140001890`
- `0x14000327c`
- `0x140006480`
- `0x140020ab0`
- `0x140020e7c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140020b32`
- `ntoskrnl!ExAllocatePool2` at `0x140020b32`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020af3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020b0b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020af3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020b0b`

## pseudocode

```c
__int64 __fastcall DYNVC_CreateDevice(PDRIVER_OBJECT DriverObject, struct _DEVICE_OBJECT **a2)
{
  __int64 Pool2; // rax
  RefCount *v4; // rbx
  NTSTATUS v5; // edi
  ULONG v7; // [rsp+20h] [rbp-78h]
  BOOLEAN v8; // [rsp+28h] [rbp-70h]
  UNICODE_STRING DefaultSDDLString; // [rsp+50h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-38h] BYREF
  GUID DeviceClassGuid; // [rsp+70h] [rbp-28h] BYREF

  DestinationString = 0;
  DefaultSDDLString = 0;
  DeviceClassGuid = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\DrDynVc");
  RtlInitUnicodeString(&DefaultSDDLString, L"D:P(A;;GA;;;NS)");
  DeviceClassGuid = (GUID)DYNVC_DEVICE_GUID;
  Pool2 = ExAllocatePool2(64, 24, 1850565462);
  v4 = (RefCount *)Pool2;
  if ( Pool2 )
  {
    *(_BYTE *)(Pool2 + 8) = 1;
    *(_QWORD *)(Pool2 + 12) = 0;
    *(_QWORD *)Pool2 = &CDynVC::`vftable';
    RefCount::AddRef((RefCount *)Pool2);
    v5 = WdmlibIoCreateDeviceSecure(
           DriverObject,
           8u,
           &DestinationString,
           0x10u,
           v7,
           v8,
           &DefaultSDDLString,
           &DeviceClassGuid,
           (PDEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
    if ( v5 >= 0 )
    {
      **((_QWORD **)WPP_MAIN_CB.Queue.Wcb.DeviceObject + 8) = v4;
      *((_DWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceObject + 12) &= ~0x80u;
      *((_DWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceObject + 12) |= 0x10u;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids,
          (unsigned int)v5);
      RefCount::Release(v4);
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140020ab0  mov     [rsp+arg_8], rbx
0x140020ab5  push    rdi
0x140020ab6  sub     rsp, 90h
0x140020abd  mov     rax, cs:__security_cookie
0x140020ac4  xor     rax, rsp
0x140020ac7  mov     [rsp+98h+var_18], rax
0x140020acf  xorps   xmm0, xmm0
0x140020ad2  lea     rdx, aDeviceDrdynvc; "\\Device\\DrDynVc"
0x140020ad9  mov     rdi, rcx
0x140020adc  xorps   xmm1, xmm1
0x140020adf  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140020ae4  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x140020ae9  movups  xmmword ptr [rsp+98h+var_48.Length], xmm1
0x140020aee  movups  xmmword ptr [rsp+98h+var_28.Data1], xmm0
0x140020af3  call    cs:__imp_RtlInitUnicodeString
0x140020afa  nop     dword ptr [rax+rax+00h]
0x140020aff  lea     rdx, aDPAGaNs; "D:P(A;;GA;;;NS)"
0x140020b06  lea     rcx, [rsp+98h+var_48]; DestinationString
0x140020b0b  call    cs:__imp_RtlInitUnicodeString
0x140020b12  nop     dword ptr [rax+rax+00h]
0x140020b17  movups  xmm0, cs:DYNVC_DEVICE_GUID
0x140020b1e  mov     edx, 18h
0x140020b23  mov     r8d, 6E4D6356h
0x140020b29  movdqu  xmmword ptr [rsp+98h+var_28.Data1], xmm0
0x140020b2f  lea     ecx, [rdx+28h]
0x140020b32  call    cs:__imp_ExAllocatePool2
0x140020b39  nop     dword ptr [rax+rax+00h]
0x140020b3e  mov     rbx, rax
0x140020b41  test    rax, rax
0x140020b44  jz      loc_140020C07
0x140020b4a  mov     byte ptr [rax+8], 1
0x140020b4e  mov     rcx, rbx; this
0x140020b51  mov     qword ptr [rax+0Ch], 0
0x140020b59  lea     rax, ??_7CDynVC@@6B@; const CDynVC::`vftable'
0x140020b60  mov     [rbx], rax
0x140020b63  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140020b68  lea     rax, WPP_MAIN_CB.Queue+30h
0x140020b6f  mov     r9d, 10h; DeviceType
0x140020b75  mov     [rsp+98h+DeviceObject], rax; DeviceObject
0x140020b7a  lea     r8, [rsp+98h+DestinationString]; DeviceName
0x140020b7f  lea     rax, [rsp+98h+var_28]
0x140020b84  mov     rcx, rdi; DriverObject
0x140020b87  mov     [rsp+98h+DeviceClassGuid], rax; DeviceClassGuid
0x140020b8c  lea     rax, [rsp+98h+var_48]
0x140020b91  lea     edx, [r9-8]; DeviceExtensionSize
0x140020b95  mov     [rsp+98h+DefaultSDDLString], rax; DefaultSDDLString
0x140020b9a  call    WdmlibIoCreateDeviceSecure
0x140020b9f  mov     edi, eax
0x140020ba1  test    eax, eax
0x140020ba3  jns     short loc_140020BE0
0x140020ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x140020bac  lea     rax, WPP_GLOBAL_Control
0x140020bb3  cmp     rcx, rax
0x140020bb6  jz      short loc_140020BD6
0x140020bb8  cmp     byte ptr [rcx+29h], 2
0x140020bbc  jb      short loc_140020BD6
0x140020bbe  mov     rcx, [rcx+18h]
0x140020bc2  lea     r8, WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids
0x140020bc9  mov     edx, 0Bh
0x140020bce  mov     r9d, edi
0x140020bd1  call    WPP_SF_d
0x140020bd6  mov     rcx, rbx; this
0x140020bd9  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140020bde  jmp     short loc_140020C0C
0x140020be0  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140020be7  mov     rcx, [rax+40h]
0x140020beb  mov     [rcx], rbx
0x140020bee  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140020bf5  btr     dword ptr [rax+30h], 7
0x140020bfa  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140020c01  or      dword ptr [rax+30h], 10h
0x140020c05  jmp     short loc_140020C0C
0x140020c07  mov     edi, 0C0000017h
0x140020c0c  mov     eax, edi
0x140020c0e  mov     rcx, [rsp+98h+var_18]
0x140020c16  xor     rcx, rsp; StackCookie
0x140020c19  call    __security_check_cookie
0x140020c1e  mov     rbx, [rsp+98h+arg_8]
0x140020c26  add     rsp, 90h
0x140020c2d  pop     rdi
0x140020c2e  retn
```
