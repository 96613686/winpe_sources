# StopMailslotMiniRdrInFSP

- ea: `0x1400842ac`
- end: `0x14008435c`
- name: `StopMailslotMiniRdrInFSP`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001f0e0`

## callees

- `0x140039fa8`
- `0x1400842ac`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140084325`
- `ntoskrnl!KeDelayExecutionThread` at `0x140084325`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140084349`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140084349`
- `rdbss!RxCreateRxContext` at `0x1400842d5`
- `rdbss!RxCreateRxContext` at `0x1400842d5`
- `rdbss!RxStopMinirdr` at `0x14008433a`
- `rdbss!RxStopMinirdr` at `0x14008433a`

## pseudocode

```c
void __fastcall StopMailslotMiniRdrInFSP(__int64 a1)
{
  bool v1; // zf
  PRX_CONTEXT RxContext; // rax
  struct _RX_CONTEXT *v3; // rbx
  LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  v1 = (*(_DWORD *)(a1 + 120) & 0x202) == 0;
  Interval.QuadPart = -1000000;
  if ( v1 )
    __int2c();
  while ( 1 )
  {
    RxContext = RxCreateRxContext(0, MRxMailslotDeviceObject, 0x202u);
    v3 = RxContext;
    if ( RxContext )
      break;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_5920f11caaa43625fe05f06d3a909c93_Traceguids);
    }
    KeDelayExecutionThread(0, 0, &Interval);
  }
  RxStopMinirdr(RxContext, (PBOOLEAN)&RxContext->RealDevice + 3);
  RxDereferenceAndDeleteRxContext_Real(v3);
}

```

## disassembly

```asm
0x1400842ac  push    rbx
0x1400842ae  sub     rsp, 20h
0x1400842b2  test    dword ptr [rcx+78h], 202h
0x1400842b9  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFF0BDC0h
0x1400842c2  jnz     short loc_1400842C6
0x1400842c4  int     2Ch; Windows NT - assertion failure
0x1400842c6  mov     rdx, cs:MRxMailslotDeviceObject; RxDeviceObject
0x1400842cd  mov     r8d, 202h; InitialContextFlags
0x1400842d3  xor     ecx, ecx; Irp
0x1400842d5  call    cs:__imp_RxCreateRxContext
0x1400842dc  nop     dword ptr [rax+rax+00h]
0x1400842e1  mov     rbx, rax
0x1400842e4  test    rax, rax
0x1400842e7  jnz     short loc_140084333
0x1400842e9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400842f0  lea     rax, WPP_GLOBAL_Control
0x1400842f7  cmp     rcx, rax
0x1400842fa  jz      short loc_14008431C
0x1400842fc  mov     eax, [rcx+2Ch]
0x1400842ff  test    al, 1
0x140084301  jz      short loc_14008431C
0x140084303  cmp     byte ptr [rcx+29h], 1
0x140084307  jb      short loc_14008431C
0x140084309  mov     rcx, [rcx+18h]
0x14008430d  lea     edx, [rbx+15h]
0x140084310  lea     r8, WPP_5920f11caaa43625fe05f06d3a909c93_Traceguids
0x140084317  call    WPP_SF_
0x14008431c  lea     r8, [rsp+28h+Interval]; Interval
0x140084321  xor     edx, edx; Alertable
0x140084323  xor     ecx, ecx; WaitMode
0x140084325  call    cs:__imp_KeDelayExecutionThread
0x14008432c  nop     dword ptr [rax+rax+00h]
0x140084331  jmp     short loc_1400842C6
0x140084333  lea     rdx, [rax+23h]; PostToFsp
0x140084337  mov     rcx, rbx; RxContext
0x14008433a  call    cs:__imp_RxStopMinirdr
0x140084341  nop     dword ptr [rax+rax+00h]
0x140084346  mov     rcx, rbx; RxContext
0x140084349  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140084350  nop     dword ptr [rax+rax+00h]
0x140084355  add     rsp, 20h
0x140084359  pop     rbx
0x14008435a  retn
```
