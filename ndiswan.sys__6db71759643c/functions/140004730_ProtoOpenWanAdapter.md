# ProtoOpenWanAdapter

- ea: `0x140004730`
- end: `0x1400048b8`
- name: `ProtoOpenWanAdapter`
- size: `392`
- prototype: `__int64 __fastcall(NDIS_HANDLE ProtocolBindingContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400040a0`

## callees

- `0x140004730`
- `0x14000a290`
- `0x14000cac8`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140004836`
- `ntoskrnl!KeClearEvent` at `0x140004836`
- `ntoskrnl!KeInitializeEvent` at `0x14000479f`
- `ntoskrnl!KeInitializeEvent` at `0x14000479f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004821`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004821`
- `NDIS!NdisOpenAdapterEx` at `0x1400047f8`
- `NDIS!NdisOpenAdapterEx` at `0x1400047f8`

## pseudocode

```c
__int64 __fastcall ProtoOpenWanAdapter(char *ProtocolBindingContext)
{
  unsigned int v2; // edi
  _NDIS_OPEN_PARAMETERS OpenParameters; // [rsp+30h] [rbp-40h] BYREF
  int v5; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v6; // [rsp+A8h] [rbp+38h] BYREF
  int v7; // [rsp+B0h] [rbp+40h] BYREF
  int v8; // [rsp+B4h] [rbp+44h]

  v6 = 0;
  v7 = 8;
  memset(&OpenParameters, 0, sizeof(OpenParameters));
  v8 = 12;
  v5 = -2130671474;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_S(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids,
      *((_QWORD *)ProtocolBindingContext + 9));
  }
  KeInitializeEvent((PRKEVENT)(ProtocolBindingContext + 136), NotificationEvent, 0);
  OpenParameters.Header = (NDIS_OBJECT_HEADER)3670407;
  OpenParameters.AdapterName = (PNDIS_STRING)(ProtocolBindingContext + 64);
  OpenParameters.MediumArraySize = 2;
  OpenParameters.MediumArray = (PNDIS_MEDIUM)&v7;
  OpenParameters.SelectedMediumIndex = &v6;
  OpenParameters.FrameTypeArray = (PNET_FRAME_TYPE)&v5;
  OpenParameters.FrameTypeArraySize = 2;
  v2 = NdisOpenAdapterEx(
         NdisProtocolHandle,
         ProtocolBindingContext,
         &OpenParameters,
         *((NDIS_HANDLE *)ProtocolBindingContext + 12),
         (PNDIS_HANDLE)ProtocolBindingContext + 7);
  if ( v2 == 259 )
  {
    KeWaitForSingleObject(ProtocolBindingContext + 136, Executive, 0, 1u, 0);
    v2 = *((_DWORD *)ProtocolBindingContext + 40);
    KeClearEvent((PRKEVENT)(ProtocolBindingContext + 136));
  }
  if ( !v2 )
    *((_DWORD *)ProtocolBindingContext + 30) = *(&v7 + v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  return v2;
}

```

## disassembly

```asm
0x140004730  push    rbp
0x140004732  push    rbx
0x140004733  push    rsi
0x140004734  push    rdi
0x140004735  push    r14
0x140004737  mov     rbp, rsp
0x14000473a  sub     rsp, 70h
0x14000473e  xorps   xmm0, xmm0
0x140004741  mov     [rbp+arg_8], 0
0x140004748  xor     eax, eax
0x14000474a  mov     [rbp+arg_10], 8
0x140004751  movups  xmmword ptr [rbp+OpenParameters.Header.Type], xmm0
0x140004755  mov     qword ptr [rbp+OpenParameters.FrameTypeArraySize], rax
0x140004759  mov     rbx, rcx
0x14000475c  movups  xmmword ptr [rbp+OpenParameters.MediumArray], xmm0
0x140004760  mov     [rbp+arg_14], 0Ch
0x140004767  movups  xmmword ptr [rbp+OpenParameters.SelectedMediumIndex], xmm0
0x14000476b  mov     [rbp+arg_0], 8100888Eh
0x140004772  mov     rcx, cs:WPP_GLOBAL_Control
0x140004779  lea     r14, WPP_GLOBAL_Control
0x140004780  cmp     rcx, r14
0x140004783  jz      short loc_140004790
0x140004785  mov     eax, [rcx+2Ch]
0x140004788  test    al, 4
0x14000478a  jnz     loc_140004860
0x140004790  lea     rsi, [rbx+88h]
0x140004797  xor     r8d, r8d; State
0x14000479a  mov     rcx, rsi; Event
0x14000479d  xor     edx, edx; Type
0x14000479f  call    cs:__imp_KeInitializeEvent
0x1400047a6  nop     dword ptr [rax+rax+00h]
0x1400047ab  lea     rax, [rbx+40h]
0x1400047af  mov     dword ptr [rbp+OpenParameters.Header.Type], 380187h
0x1400047b6  mov     [rbp+OpenParameters.AdapterName], rax
0x1400047ba  mov     ecx, 2
0x1400047bf  lea     rax, [rbp+arg_10]
0x1400047c3  mov     [rbp+OpenParameters.MediumArraySize], ecx
0x1400047c6  mov     [rbp+OpenParameters.MediumArray], rax
0x1400047ca  lea     rax, [rbp+arg_8]
0x1400047ce  mov     [rbp+OpenParameters.SelectedMediumIndex], rax
0x1400047d2  lea     rax, [rbp+arg_0]
0x1400047d6  mov     [rbp+OpenParameters.FrameTypeArray], rax
0x1400047da  mov     [rbp+OpenParameters.FrameTypeArraySize], ecx
0x1400047dd  mov     r9, [rbx+60h]; BindContext
0x1400047e1  lea     rax, [rbx+38h]
0x1400047e5  mov     rcx, cs:NdisProtocolHandle; NdisProtocolHandle
0x1400047ec  lea     r8, [rbp+OpenParameters]; OpenParameters
0x1400047f0  mov     rdx, rbx; ProtocolBindingContext
0x1400047f3  mov     [rsp+70h+NdisBindingHandle], rax; NdisBindingHandle
0x1400047f8  call    cs:__imp_NdisOpenAdapterEx
0x1400047ff  nop     dword ptr [rax+rax+00h]
0x140004804  mov     edi, eax
0x140004806  cmp     eax, 103h
0x14000480b  jnz     short loc_140004842
0x14000480d  mov     r9b, 1; Alertable
0x140004810  mov     [rsp+70h+NdisBindingHandle], 0; Timeout
0x140004819  xor     r8d, r8d; WaitMode
0x14000481c  xor     edx, edx; WaitReason
0x14000481e  mov     rcx, rsi; Object
0x140004821  call    cs:__imp_KeWaitForSingleObject
0x140004828  nop     dword ptr [rax+rax+00h]
0x14000482d  mov     edi, [rbx+0A0h]
0x140004833  mov     rcx, rsi; Event
0x140004836  call    cs:__imp_KeClearEvent
0x14000483d  nop     dword ptr [rax+rax+00h]
0x140004842  test    edi, edi
0x140004844  jz      short loc_140004888
0x140004846  mov     rcx, cs:WPP_GLOBAL_Control
0x14000484d  cmp     rcx, r14
0x140004850  jnz     short loc_140004894
0x140004852  mov     eax, edi
0x140004854  add     rsp, 70h
0x140004858  pop     r14
0x14000485a  pop     rdi
0x14000485b  pop     rsi
0x14000485c  pop     rbx
0x14000485d  pop     rbp
0x14000485e  retn
0x140004860  cmp     byte ptr [rcx+29h], 5
0x140004864  jb      loc_140004790
0x14000486a  mov     r9, [rbx+48h]
0x14000486e  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140004875  mov     rcx, [rcx+18h]
0x140004879  mov     edx, 0Ah
0x14000487e  call    WPP_SF_S
0x140004883  jmp     loc_140004790
0x140004888  mov     eax, [rbp+arg_8]
0x14000488b  mov     ecx, [rbp+rax*4+arg_10]
0x14000488f  mov     [rbx+78h], ecx
0x140004892  jmp     short loc_140004846
0x140004894  mov     eax, [rcx+2Ch]
0x140004897  test    al, 4
0x140004899  jz      short loc_140004852
0x14000489b  cmp     byte ptr [rcx+29h], 5
0x14000489f  jb      short loc_140004852
0x1400048a1  mov     rcx, [rcx+18h]
0x1400048a5  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x1400048ac  mov     edx, 0Bh
0x1400048b1  call    WPP_SF_
0x1400048b6  jmp     short loc_140004852
```
