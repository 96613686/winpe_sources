# StopMailslotMiniRdrInFSP

- ea: `0x14008425c`
- end: `0x14008430c`
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
- `0x14008425c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400842d5`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400842d5`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x1400842f9`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x1400842f9`
- `rdbss!RxCreateRxContext` at `0x140084285`
- `rdbss!RxCreateRxContext` at `0x140084285`
- `rdbss!RxStopMinirdr` at `0x1400842ea`
- `rdbss!RxStopMinirdr` at `0x1400842ea`

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
0x14008425c  push    rbx
0x14008425e  sub     rsp, 20h
0x140084262  test    dword ptr [rcx+78h], 202h
0x140084269  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFF0BDC0h
0x140084272  jnz     short loc_140084276
0x140084274  int     2Ch; Windows NT - assertion failure
0x140084276  mov     rdx, cs:MRxMailslotDeviceObject; RxDeviceObject
0x14008427d  mov     r8d, 202h; InitialContextFlags
0x140084283  xor     ecx, ecx; Irp
0x140084285  call    cs:__imp_RxCreateRxContext
0x14008428c  nop     dword ptr [rax+rax+00h]
0x140084291  mov     rbx, rax
0x140084294  test    rax, rax
0x140084297  jnz     short loc_1400842E3
0x140084299  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400842a0  lea     rax, WPP_GLOBAL_Control
0x1400842a7  cmp     rcx, rax
0x1400842aa  jz      short loc_1400842CC
0x1400842ac  mov     eax, [rcx+2Ch]
0x1400842af  test    al, 1
0x1400842b1  jz      short loc_1400842CC
0x1400842b3  cmp     byte ptr [rcx+29h], 1
0x1400842b7  jb      short loc_1400842CC
0x1400842b9  mov     rcx, [rcx+18h]
0x1400842bd  lea     edx, [rbx+15h]
0x1400842c0  lea     r8, WPP_5920f11caaa43625fe05f06d3a909c93_Traceguids
0x1400842c7  call    WPP_SF_
0x1400842cc  lea     r8, [rsp+28h+Interval]; Interval
0x1400842d1  xor     edx, edx; Alertable
0x1400842d3  xor     ecx, ecx; WaitMode
0x1400842d5  call    cs:__imp_KeDelayExecutionThread
0x1400842dc  nop     dword ptr [rax+rax+00h]
0x1400842e1  jmp     short loc_140084276
0x1400842e3  lea     rdx, [rax+23h]; PostToFsp
0x1400842e7  mov     rcx, rbx; RxContext
0x1400842ea  call    cs:__imp_RxStopMinirdr
0x1400842f1  nop     dword ptr [rax+rax+00h]
0x1400842f6  mov     rcx, rbx; RxContext
0x1400842f9  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140084300  nop     dword ptr [rax+rax+00h]
0x140084305  add     rsp, 20h
0x140084309  pop     rbx
0x14008430a  retn
```
