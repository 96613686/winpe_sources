# ACCreateDeviceObject(_DRIVER_OBJECT *,_UNICODE_STRING const *,_DEVICE_OBJECT * *)

- ea: `0x14000cef8`
- end: `0x14000d3d5`
- name: `?ACCreateDeviceObject@@YAJPEAU_DRIVER_OBJECT@@PEBU_UNICODE_STRING@@PEAPEAU_DEVICE_OBJECT@@@Z`
- size: `1245`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *, const struct _UNICODE_STRING *, struct _DEVICE_OBJECT **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140020b40`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x140001c04`
- `0x140001c34`
- `0x14000cb74`
- `0x14000ce0c`
- `0x14000cef8`
- `0x14000d42c`
- `0x14000d558`
- `0x14001b300`
- `0x140024bb0`
- `0x140024fc0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000cfd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d0f9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cfd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d0f9`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000d11a`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000d13b`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000d11a`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000d13b`
- `ntoskrnl!wcscpy_s` at `0x14000d033`
- `ntoskrnl!wcscpy_s` at `0x14000d033`
- `ntoskrnl!wcscat_s` at `0x14000cfb4`
- `ntoskrnl!wcscat_s` at `0x14000d04e`
- `ntoskrnl!wcscat_s` at `0x14000cfb4`
- `ntoskrnl!wcscat_s` at `0x14000d04e`
- `ntoskrnl!IoCreateDevice` at `0x14000d087`
- `ntoskrnl!IoCreateDevice` at `0x14000d087`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000d2f9`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000d2f9`
- `ntoskrnl!IoDeleteDevice` at `0x14000d3a3`
- `ntoskrnl!IoDeleteDevice` at `0x14000d3a3`

## pseudocode

```c
__int64 __fastcall ACCreateDeviceObject(
        struct _DRIVER_OBJECT *a1,
        const struct _UNICODE_STRING *a2,
        struct _DEVICE_OBJECT **a3)
{
  struct _DRIVER_OBJECT *v3; // r15
  const wchar_t *Buffer; // r14
  CDeviceExt *v6; // rdi
  __int64 v7; // rsi
  __int16 v8; // bx
  WCHAR *v9; // rax
  NTSTATUS v10; // ebx
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // rsi
  const struct _UNICODE_STRING *v15; // rcx
  const struct _UNICODE_STRING *v16; // rcx
  PIO_WORKITEM WorkItem; // rax
  PIO_WORKITEM v18; // rax
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  PDEVICE_OBJECT *v21; // rdx
  PDEVICE_OBJECT *v22; // rax
  PDEVICE_OBJECT *v23; // rdx
  __int64 v24; // rcx
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Dst[304]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = g_pDriver;
  wcscpy(Dst, L"\\Device\\");
  DestinationString = 0;
  memset(&Dst[9], 0, 0x246u);
  Buffer = g_RegistryPath.Buffer;
  v6 = 0;
  v7 = g_RegistryPath.Length >> 1;
  DeviceObject = 0;
  v8 = g_RegistryPath.Length >> 1;
  v9 = &g_RegistryPath.Buffer[v7 - 1];
  if ( (_WORD)v7 )
  {
    do
    {
      if ( *v9 == 92 )
        break;
      Buffer = v9--;
      --v8;
    }
    while ( v8 );
  }
  if ( wcscat_s(Dst, 0x12Cu, Buffer) )
  {
    v10 = -1073741811;
    goto LABEL_47;
  }
  RtlInitUnicodeString(&DestinationString, Dst);
  v11 = (unsigned __int16)(v7 - v8 + 12) + 1LL;
  v12 = 2 * v11;
  if ( !is_mul_ok(v11, 2u) )
    v12 = -1;
  v13 = (wchar_t *)operator new(v12, 0x100u, 0x4341514Du, LowPoolPriority);
  v14 = v13;
  if ( v13 )
  {
    if ( wcscpy_s(v13, v11, L"\\DosDevices\\") )
      __int2c();
    if ( wcscat_s(v14, v11, Buffer) )
      __int2c();
    v10 = IoCreateDevice(v3, 0x458u, &DestinationString, 0x1965u, 0, 0, &DeviceObject);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->Queue.ListEntry.Blink,
          10,
          &WPP_69fd9661c77c30c062a3dbba9d316503_Traceguids,
          (unsigned int)v10);
      }
      operator delete(v14);
      goto LABEL_47;
    }
    v6 = CDeviceExt::CDeviceExt((CDeviceExt *)DeviceObject->DeviceExtension, DeviceObject);
    RtlInitUnicodeString((PUNICODE_STRING)((char *)v6 + 1096), v14);
    GetCheckForQMOverrideMode(v15, v6);
    GetCheckForClearDriverPacket(v16, v6);
    WorkItem = IoAllocateWorkItem(DeviceObject);
    *((_QWORD *)v6 + 50) = WorkItem;
    if ( !WorkItem )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
      {
        goto LABEL_46;
      }
      v20 = 11;
      goto LABEL_45;
    }
    v18 = IoAllocateWorkItem(DeviceObject);
    *((_QWORD *)v6 + 56) = v18;
    if ( !v18 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
      {
        goto LABEL_46;
      }
      v20 = 12;
      goto LABEL_45;
    }
    if ( !CTimer::SetCallback(
            (CDeviceExt *)((char *)v6 + 160),
            *((struct _DEVICE_OBJECT **)v6 + 9),
            (void (*)(struct _DEVICE_OBJECT *, void *))CQMInterface::TimerCallback,
            (char *)v6 + 72) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
      {
        goto LABEL_46;
      }
      v20 = 13;
      goto LABEL_45;
    }
    v21 = (PDEVICE_OBJECT *)operator new(0x58u, 0x100u, 0x4341514Du, LowPoolPriority);
    if ( v21 )
    {
      *v21 = DeviceObject;
      v21[2] = (PDEVICE_OBJECT)HandleMultipleInstances;
      v21[1] = 0;
      v21[3] = (PDEVICE_OBJECT)TimeCompare;
      v21[4] = (PDEVICE_OBJECT)DeleteSchedList;
      *((_DWORD *)v21 + 10) = 1;
      v21[6] = (PDEVICE_OBJECT)&ACPacketTimeout;
      v21[7] = (PDEVICE_OBJECT)((char *)v6 + 536);
      v21[9] = (PDEVICE_OBJECT)((char *)v6 + 480);
      *((_DWORD *)v21 + 20) = 0;
      v21[8] = 0;
    }
    else
    {
      v21 = 0;
    }
    *((_QWORD *)v6 + 44) = v21;
    v22 = (PDEVICE_OBJECT *)operator new(0x58u, 0x100u, 0x4341514Du, LowPoolPriority);
    v23 = v22;
    if ( v22 )
    {
      *v22 = DeviceObject;
      v22[1] = 0;
      v22[3] = (PDEVICE_OBJECT)TimeCompare;
      v22[4] = (PDEVICE_OBJECT)DeleteSchedList;
      v22[2] = (PDEVICE_OBJECT)HandleMultipleInstances;
      *((_DWORD *)v22 + 10) = 1;
      v22[6] = (PDEVICE_OBJECT)ACReceiveTimeout;
      v22[7] = (PDEVICE_OBJECT)((char *)v6 + 752);
      v22[9] = (PDEVICE_OBJECT)((char *)v6 + 696);
      *((_DWORD *)v22 + 20) = 0;
      v22[8] = 0;
    }
    else
    {
      v23 = 0;
    }
    v24 = *((_QWORD *)v6 + 44);
    *((_QWORD *)v6 + 45) = v23;
    if ( v24
      && v23
      && CTimer::SetCallback(
           *(CTimer **)(v24 + 56),
           *(struct _DEVICE_OBJECT **)v24,
           (void (*)(struct _DEVICE_OBJECT *, void *))CScheduler::TimerCallback,
           (void *)v24)
      && CTimer::SetCallback(
           *(CTimer **)(*((_QWORD *)v6 + 45) + 56LL),
           **((struct _DEVICE_OBJECT ***)v6 + 45),
           (void (*)(struct _DEVICE_OBJECT *, void *))CScheduler::TimerCallback,
           *((void **)v6 + 45)) )
    {
      v10 = IoCreateSymbolicLink((PUNICODE_STRING)((char *)v6 + 1096), &DestinationString);
      if ( v10 >= 0 )
      {
        *a3 = DeviceObject;
        return (unsigned int)v10;
      }
      goto LABEL_46;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      v20 = 14;
LABEL_45:
      WPP_SF_(v19->Queue.ListEntry.Blink, v20, &WPP_69fd9661c77c30c062a3dbba9d316503_Traceguids);
    }
  }
LABEL_46:
  v10 = -1073741670;
LABEL_47:
  if ( DeviceObject )
  {
    CDeviceExt::~CDeviceExt(v6);
    IoDeleteDevice(DeviceObject);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000cef8  push    rbp
0x14000cefa  push    rbx
0x14000cefb  push    rsi
0x14000cefc  push    rdi
0x14000cefd  push    r12
0x14000ceff  push    r13
0x14000cf01  push    r14
0x14000cf03  push    r15
0x14000cf05  lea     rbp, [rsp-1D8h]
0x14000cf0d  sub     rsp, 2D8h
0x14000cf14  mov     rax, cs:__security_cookie
0x14000cf1b  xor     rax, rsp
0x14000cf1e  mov     [rbp+210h+var_50], rax
0x14000cf25  movups  xmm1, xmmword ptr cs:aDevice; "\\Device\\"
0x14000cf2c  movzx   eax, word ptr cs:aDevice+10h; ""
0x14000cf33  lea     rcx, [rsp+310h+var_29E]; void *
0x14000cf38  mov     r15, cs:?g_pDriver@@3PEAU_DRIVER_OBJECT@@EA; _DRIVER_OBJECT * g_pDriver
0x14000cf3f  mov     r12, r8
0x14000cf42  xorps   xmm0, xmm0
0x14000cf45  movaps  xmmword ptr [rsp+310h+Dst], xmm1
0x14000cf4a  xor     edx, edx; Val
0x14000cf4c  mov     [rsp+310h+var_2A0], ax
0x14000cf51  mov     r8d, 246h; Size
0x14000cf57  movups  xmmword ptr [rsp+310h+DestinationString.Length], xmm0
0x14000cf5c  call    memset
0x14000cf61  movzx   eax, cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING g_RegistryPath ...
0x14000cf68  xor     r13d, r13d
0x14000cf6b  mov     r14, cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Buffer; _UNICODE_STRING g_RegistryPath ...
0x14000cf72  mov     edi, r13d
0x14000cf75  shr     ax, 1
0x14000cf78  movzx   esi, ax
0x14000cf7b  mov     [rsp+310h+var_2D0], r13
0x14000cf80  movzx   ebx, si
0x14000cf83  lea     rax, [r14-2]
0x14000cf87  lea     rax, [rax+rsi*2]
0x14000cf8b  test    si, si
0x14000cf8e  jz      short loc_14000CFA7
0x14000cf90  cmp     word ptr [rax], 5Ch ; '\'
0x14000cf94  jz      short loc_14000CFA7
0x14000cf96  mov     r14, rax
0x14000cf99  mov     ecx, 0FFFFh
0x14000cf9e  sub     rax, 2
0x14000cfa2  add     bx, cx
0x14000cfa5  jnz     short loc_14000CF90
0x14000cfa7  mov     r8, r14; Src
0x14000cfaa  lea     rcx, [rsp+310h+Dst]; Dst
0x14000cfaf  mov     edx, 12Ch; SizeInWords
0x14000cfb4  call    cs:__imp_wcscat_s
0x14000cfbb  nop     dword ptr [rax+rax+00h]
0x14000cfc0  test    eax, eax
0x14000cfc2  jz      short loc_14000CFCE
0x14000cfc4  mov     ebx, 0C000000Dh
0x14000cfc9  jmp     loc_14000D38F
0x14000cfce  lea     rdx, [rsp+310h+Dst]; SourceString
0x14000cfd3  lea     rcx, [rsp+310h+DestinationString]; DestinationString
0x14000cfd8  call    cs:__imp_RtlInitUnicodeString
0x14000cfdf  nop     dword ptr [rax+rax+00h]
0x14000cfe4  sub     si, bx
0x14000cfe7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000cfee  add     si, 0Ch
0x14000cff2  mov     eax, 2
0x14000cff7  movzx   ebx, si
0x14000cffa  mov     r8d, 4341514Dh; unsigned int
0x14000d000  inc     rbx
0x14000d003  mul     rbx
0x14000d006  mov     edx, 100h; unsigned __int64
0x14000d00b  cmovb   rax, rcx
0x14000d00f  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000d012  mov     rcx, rax; unsigned __int64
0x14000d015  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000d01a  mov     rsi, rax
0x14000d01d  test    rax, rax
0x14000d020  jz      loc_14000D38A
0x14000d026  lea     r8, aDosdevices; "\\DosDevices\\"
0x14000d02d  mov     rdx, rbx; SizeInWords
0x14000d030  mov     rcx, rax; Dst
0x14000d033  call    cs:__imp_wcscpy_s
0x14000d03a  nop     dword ptr [rax+rax+00h]
0x14000d03f  test    eax, eax
0x14000d041  jz      short loc_14000D045
0x14000d043  int     2Ch; Windows NT - assertion failure
0x14000d045  mov     r8, r14; Src
0x14000d048  mov     rdx, rbx; SizeInWords
0x14000d04b  mov     rcx, rsi; Dst
0x14000d04e  call    cs:__imp_wcscat_s
0x14000d055  nop     dword ptr [rax+rax+00h]
0x14000d05a  test    eax, eax
0x14000d05c  jz      short loc_14000D060
0x14000d05e  int     2Ch; Windows NT - assertion failure
0x14000d060  lea     rax, [rsp+310h+var_2D0]
0x14000d065  mov     r9d, 1965h; DeviceType
0x14000d06b  mov     [rsp+310h+DeviceObject], rax; DeviceObject
0x14000d070  lea     r8, [rsp+310h+DestinationString]; DeviceName
0x14000d075  mov     [rsp+310h+Exclusive], r13b; Exclusive
0x14000d07a  mov     edx, 458h; DeviceExtensionSize
0x14000d07f  mov     rcx, r15; DriverObject
0x14000d082  mov     [rsp+310h+DeviceCharacteristics], r13d; DeviceCharacteristics
0x14000d087  call    cs:__imp_IoCreateDevice
0x14000d08e  nop     dword ptr [rax+rax+00h]
0x14000d093  mov     ebx, eax
0x14000d095  test    eax, eax
0x14000d097  jns     short loc_14000D0D8
0x14000d099  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0a0  lea     rax, WPP_GLOBAL_Control
0x14000d0a7  cmp     rcx, rax
0x14000d0aa  jz      short loc_14000D0CB
0x14000d0ac  mov     eax, [rcx+6Ch]
0x14000d0af  test    al, 1
0x14000d0b1  jz      short loc_14000D0CB
0x14000d0b3  mov     rcx, [rcx+58h]
0x14000d0b7  lea     r8, WPP_69fd9661c77c30c062a3dbba9d316503_Traceguids
0x14000d0be  mov     edx, 0Ah
0x14000d0c3  mov     r9d, ebx
0x14000d0c6  call    WPP_SF_d
0x14000d0cb  mov     rcx, rsi; void *
0x14000d0ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000d0d3  jmp     loc_14000D38F
0x14000d0d8  mov     rcx, [rsp+310h+var_2D0]
0x14000d0dd  mov     rdx, rcx; struct _DEVICE_OBJECT *
0x14000d0e0  mov     rcx, [rcx+40h]; this
0x14000d0e4  call    ??0CDeviceExt@@QEAA@PEAU_DEVICE_OBJECT@@@Z; CDeviceExt::CDeviceExt(_DEVICE_OBJECT *)
0x14000d0e9  mov     rdx, rsi; SourceString
0x14000d0ec  mov     rdi, rax
0x14000d0ef  lea     rbx, [rax+448h]
0x14000d0f6  mov     rcx, rbx; DestinationString
0x14000d0f9  call    cs:__imp_RtlInitUnicodeString
0x14000d100  nop     dword ptr [rax+rax+00h]
0x14000d105  mov     rdx, rdi; struct CDeviceExt *
0x14000d108  call    ?GetCheckForQMOverrideMode@@YAXPEBU_UNICODE_STRING@@PEAUCDeviceExt@@@Z; GetCheckForQMOverrideMode(_UNICODE_STRING const *,CDeviceExt *)
0x14000d10d  mov     rdx, rdi; struct CDeviceExt *
0x14000d110  call    ?GetCheckForClearDriverPacket@@YAXPEBU_UNICODE_STRING@@PEAUCDeviceExt@@@Z; GetCheckForClearDriverPacket(_UNICODE_STRING const *,CDeviceExt *)
0x14000d115  mov     rcx, [rsp+310h+var_2D0]; DeviceObject
0x14000d11a  call    cs:__imp_IoAllocateWorkItem
0x14000d121  nop     dword ptr [rax+rax+00h]
0x14000d126  mov     [rdi+190h], rax
0x14000d12d  test    rax, rax
0x14000d130  jz      loc_14000D35B
0x14000d136  mov     rcx, [rsp+310h+var_2D0]; DeviceObject
0x14000d13b  call    cs:__imp_IoAllocateWorkItem
0x14000d142  nop     dword ptr [rax+rax+00h]
0x14000d147  mov     [rdi+1C0h], rax
0x14000d14e  test    rax, rax
0x14000d151  jz      loc_14000D33A
0x14000d157  mov     rdx, [rdi+48h]; struct _DEVICE_OBJECT *
0x14000d15b  lea     rcx, [rdi+0A0h]; this
0x14000d162  lea     r9, [rdi+48h]; void *
0x14000d166  lea     r8, ?TimerCallback@CQMInterface@@CAXPEAU_DEVICE_OBJECT@@PEAX@Z; void (*)(struct _DEVICE_OBJECT *, void *)
0x14000d16d  call    ?SetCallback@CTimer@@QEAA_NPEAU_DEVICE_OBJECT@@P6AX0PEAX@Z1@Z; CTimer::SetCallback(_DEVICE_OBJECT *,void (*)(_DEVICE_OBJECT *,void *),void *)
0x14000d172  test    al, al
0x14000d174  jnz     short loc_14000D1A2
0x14000d176  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d17d  lea     rax, WPP_GLOBAL_Control
0x14000d184  cmp     rcx, rax
0x14000d187  jz      loc_14000D38A
0x14000d18d  mov     eax, [rcx+6Ch]
0x14000d190  test    al, 1
0x14000d192  jz      loc_14000D38A
0x14000d198  mov     edx, 0Dh
0x14000d19d  jmp     loc_14000D37A
0x14000d1a2  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000d1a5  mov     edx, 100h; unsigned __int64
0x14000d1aa  mov     r8d, 4341514Dh; unsigned int
0x14000d1b0  lea     esi, [r9+58h]
0x14000d1b4  mov     ecx, esi; unsigned __int64
0x14000d1b6  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000d1bb  mov     rdx, rax
0x14000d1be  lea     r14, ?TimeCompare@@YAHPEAX0@Z; TimeCompare(void *,void *)
0x14000d1c5  lea     r15, ?DeleteSchedList@@YAXPEAX@Z; DeleteSchedList(void *)
0x14000d1cc  lea     rax, ?HandleMultipleInstances@@YAHPEAX0H@Z; HandleMultipleInstances(void *,void *,int)
0x14000d1d3  test    rdx, rdx
0x14000d1d6  jz      short loc_14000D222
0x14000d1d8  mov     rcx, [rsp+310h+var_2D0]
0x14000d1dd  mov     [rdx], rcx
0x14000d1e0  mov     [rdx+10h], rax
0x14000d1e4  lea     rax, ACPacketTimeout
0x14000d1eb  mov     [rdx+8], r13
0x14000d1ef  mov     [rdx+18h], r14
0x14000d1f3  mov     [rdx+20h], r15
0x14000d1f7  mov     dword ptr [rdx+28h], 1
0x14000d1fe  mov     [rdx+30h], rax
0x14000d202  lea     rax, [rdi+218h]
0x14000d209  mov     [rdx+38h], rax
0x14000d20d  lea     rax, [rdi+1E0h]
0x14000d214  mov     [rdx+48h], rax
0x14000d218  mov     [rdx+50h], r13d
0x14000d21c  mov     [rdx+40h], r13
0x14000d220  jmp     short loc_14000D225
0x14000d222  mov     rdx, r13
0x14000d225  mov     [rdi+160h], rdx
0x14000d22c  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000d22f  mov     edx, 100h; unsigned __int64
0x14000d234  mov     r8d, 4341514Dh; unsigned int
0x14000d23a  mov     rcx, rsi; unsigned __int64
0x14000d23d  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000d242  mov     rdx, rax
0x14000d245  test    rax, rax
0x14000d248  jz      short loc_14000D29B
0x14000d24a  mov     rcx, [rsp+310h+var_2D0]
0x14000d24f  mov     [rax], rcx
0x14000d252  mov     [rax+8], r13
0x14000d256  mov     [rax+18h], r14
0x14000d25a  mov     [rax+20h], r15
0x14000d25e  lea     rax, ?HandleMultipleInstances@@YAHPEAX0H@Z; HandleMultipleInstances(void *,void *,int)
0x14000d265  mov     [rdx+10h], rax
0x14000d269  lea     rax, ACReceiveTimeout
0x14000d270  mov     dword ptr [rdx+28h], 1
0x14000d277  mov     [rdx+30h], rax
0x14000d27b  lea     rax, [rdi+2F0h]
0x14000d282  mov     [rdx+38h], rax
0x14000d286  lea     rax, [rdi+2B8h]
0x14000d28d  mov     [rdx+48h], rax
0x14000d291  mov     [rdx+50h], r13d
0x14000d295  mov     [rdx+40h], r13
0x14000d299  jmp     short loc_14000D29E
0x14000d29b  mov     rdx, r13
0x14000d29e  mov     rcx, [rdi+160h]
0x14000d2a5  mov     [rdi+168h], rdx
0x14000d2ac  test    rcx, rcx
0x14000d2af  jz      short loc_14000D319
0x14000d2b1  test    rdx, rdx
0x14000d2b4  jz      short loc_14000D319
0x14000d2b6  mov     rdx, [rcx]; struct _DEVICE_OBJECT *
0x14000d2b9  lea     r8, ?TimerCallback@CScheduler@@CAXPEAU_DEVICE_OBJECT@@PEAX@Z; void (*)(struct _DEVICE_OBJECT *, void *)
0x14000d2c0  mov     r9, rcx; void *
0x14000d2c3  mov     rcx, [rcx+38h]; this
0x14000d2c7  call    ?SetCallback@CTimer@@QEAA_NPEAU_DEVICE_OBJECT@@P6AX0PEAX@Z1@Z; CTimer::SetCallback(_DEVICE_OBJECT *,void (*)(_DEVICE_OBJECT *,void *),void *)
0x14000d2cc  test    al, al
0x14000d2ce  jz      short loc_14000D319
0x14000d2d0  mov     rcx, [rdi+168h]
0x14000d2d7  lea     r8, ?TimerCallback@CScheduler@@CAXPEAU_DEVICE_OBJECT@@PEAX@Z; void (*)(struct _DEVICE_OBJECT *, void *)
0x14000d2de  mov     r9, rcx; void *
0x14000d2e1  mov     rdx, [rcx]; struct _DEVICE_OBJECT *
0x14000d2e4  mov     rcx, [rcx+38h]; this
0x14000d2e8  call    ?SetCallback@CTimer@@QEAA_NPEAU_DEVICE_OBJECT@@P6AX0PEAX@Z1@Z; CTimer::SetCallback(_DEVICE_OBJECT *,void (*)(_DEVICE_OBJECT *,void *),void *)
0x14000d2ed  test    al, al
0x14000d2ef  jz      short loc_14000D319
0x14000d2f1  lea     rdx, [rsp+310h+DestinationString]; DeviceName
0x14000d2f6  mov     rcx, rbx; SymbolicLinkName
0x14000d2f9  call    cs:__imp_IoCreateSymbolicLink
0x14000d300  nop     dword ptr [rax+rax+00h]
0x14000d305  mov     ebx, eax
0x14000d307  test    eax, eax
0x14000d309  js      short loc_14000D38A
0x14000d30b  mov     rax, [rsp+310h+var_2D0]
0x14000d310  mov     [r12], rax
0x14000d314  jmp     loc_14000D3AF
0x14000d319  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d320  lea     rax, WPP_GLOBAL_Control
0x14000d327  cmp     rcx, rax
0x14000d32a  jz      short loc_14000D38A
0x14000d32c  mov     eax, [rcx+6Ch]
0x14000d32f  test    al, 1
0x14000d331  jz      short loc_14000D38A
0x14000d333  mov     edx, 0Eh
0x14000d338  jmp     short loc_14000D37A
0x14000d33a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d341  lea     rax, WPP_GLOBAL_Control
0x14000d348  cmp     rcx, rax
0x14000d34b  jz      short loc_14000D38A
0x14000d34d  mov     eax, [rcx+6Ch]
0x14000d350  test    al, 1
0x14000d352  jz      short loc_14000D38A
0x14000d354  mov     edx, 0Ch
0x14000d359  jmp     short loc_14000D37A
0x14000d35b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d362  lea     rax, WPP_GLOBAL_Control
0x14000d369  cmp     rcx, rax
0x14000d36c  jz      short loc_14000D38A
0x14000d36e  mov     eax, [rcx+6Ch]
0x14000d371  test    al, 1
0x14000d373  jz      short loc_14000D38A
0x14000d375  mov     edx, 0Bh
0x14000d37a  mov     rcx, [rcx+58h]
0x14000d37e  lea     r8, WPP_69fd9661c77c30c062a3dbba9d316503_Traceguids
0x14000d385  call    WPP_SF_
0x14000d38a  mov     ebx, 0C000009Ah
0x14000d38f  cmp     [rsp+310h+var_2D0], r13
0x14000d394  jz      short loc_14000D3AF
0x14000d396  mov     rcx, rdi; this
0x14000d399  call    ??1CDeviceExt@@QEAA@XZ; CDeviceExt::~CDeviceExt(void)
0x14000d39e  mov     rcx, [rsp+310h+var_2D0]; DeviceObject
0x14000d3a3  call    cs:__imp_IoDeleteDevice
0x14000d3aa  nop     dword ptr [rax+rax+00h]
0x14000d3af  mov     eax, ebx
0x14000d3b1  mov     rcx, [rbp+210h+var_50]
0x14000d3b8  xor     rcx, rsp; StackCookie
0x14000d3bb  call    __security_check_cookie
0x14000d3c0  add     rsp, 2D8h
0x14000d3c7  pop     r15
0x14000d3c9  pop     r14
0x14000d3cb  pop     r13
0x14000d3cd  pop     r12
0x14000d3cf  pop     rdi
0x14000d3d0  pop     rsi
0x14000d3d1  pop     rbx
0x14000d3d2  pop     rbp
0x14000d3d3  retn
```
