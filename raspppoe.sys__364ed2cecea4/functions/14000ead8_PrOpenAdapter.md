# PrOpenAdapter

- ea: `0x14000ead8`
- end: `0x14000ec27`
- name: `PrOpenAdapter`
- size: `335`
- prototype: `__int64 __fastcall(NDIS_HANDLE ProtocolBindingContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004100`

## callees

- `0x14000110c`
- `0x140004540`
- `0x14000ead8`

## import_xrefs

- `NDIS!NdisResetEvent` at `0x14000ebd4`
- `NDIS!NdisResetEvent` at `0x14000ebd4`
- `NDIS!NdisWaitEvent` at `0x14000ebc5`
- `NDIS!NdisWaitEvent` at `0x14000ebc5`
- `NDIS!NdisOpenAdapterEx` at `0x14000eb9c`
- `NDIS!NdisOpenAdapterEx` at `0x14000eb9c`

## pseudocode

```c
bool __fastcall PrOpenAdapter(char *ProtocolBindingContext, UNICODE_STRING *a2)
{
  unsigned int v4; // eax
  _NDIS_OPEN_PARAMETERS OpenParameters; // [rsp+30h] [rbp-40h] BYREF
  int v7; // [rsp+90h] [rbp+20h] BYREF
  int v8; // [rsp+98h] [rbp+28h] BYREF
  int v9; // [rsp+A0h] [rbp+30h] BYREF

  v9 = 0;
  v8 = 0;
  memset(&OpenParameters, 0, sizeof(OpenParameters));
  v7 = -2006677405;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  OpenParameters.Header = (NDIS_OBJECT_HEADER)3670407;
  OpenParameters.MediumArray = (PNDIS_MEDIUM)&v8;
  OpenParameters.SelectedMediumIndex = (PUINT)&v9;
  OpenParameters.FrameTypeArray = (PNET_FRAME_TYPE)&v7;
  OpenParameters.AdapterName = a2;
  OpenParameters.MediumArraySize = 1;
  OpenParameters.FrameTypeArraySize = 2;
  v4 = NdisOpenAdapterEx(
         gl_NdisProtocolDriverHandle,
         ProtocolBindingContext,
         &OpenParameters,
         *((NDIS_HANDLE *)ProtocolBindingContext + 5),
         (PNDIS_HANDLE)ProtocolBindingContext + 43);
  if ( v4 != 259 )
    PrOpenAdapterComplete(ProtocolBindingContext, v4);
  NdisWaitEvent((PNDIS_EVENT)(ProtocolBindingContext + 296), 0);
  NdisResetEvent((PNDIS_EVENT)(ProtocolBindingContext + 296));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  return *((_DWORD *)ProtocolBindingContext + 8) == 0;
}

```

## disassembly

```asm
0x14000ead8  mov     [rsp-18h+arg_18], rbx
0x14000eadd  push    rbp
0x14000eade  push    rdi
0x14000eadf  push    r14
0x14000eae1  mov     rbp, rsp
0x14000eae4  sub     rsp, 70h
0x14000eae8  xorps   xmm0, xmm0
0x14000eaeb  mov     [rbp+arg_10], 0
0x14000eaf2  xor     eax, eax
0x14000eaf4  mov     [rbp+arg_8], 0
0x14000eafb  movups  xmmword ptr [rbp+OpenParameters.Header.Type], xmm0
0x14000eaff  mov     qword ptr [rbp+OpenParameters.FrameTypeArraySize], rax
0x14000eb03  mov     rbx, rdx
0x14000eb06  movups  xmmword ptr [rbp+OpenParameters.MediumArray], xmm0
0x14000eb0a  mov     rdi, rcx
0x14000eb0d  mov     [rbp+arg_0], 88648863h
0x14000eb14  movups  xmmword ptr [rbp+OpenParameters.SelectedMediumIndex], xmm0
0x14000eb18  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb1f  lea     r14, WPP_GLOBAL_Control
0x14000eb26  cmp     rcx, r14
0x14000eb29  jz      short loc_14000EB4D
0x14000eb2b  mov     eax, [rcx+2Ch]
0x14000eb2e  test    al, 4
0x14000eb30  jz      short loc_14000EB4D
0x14000eb32  cmp     byte ptr [rcx+29h], 3
0x14000eb36  jb      short loc_14000EB4D
0x14000eb38  mov     rcx, [rcx+18h]
0x14000eb3c  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000eb43  mov     edx, 25h ; '%'
0x14000eb48  call    WPP_SF_
0x14000eb4d  lea     rax, [rbp+arg_8]
0x14000eb51  mov     dword ptr [rbp+OpenParameters.Header.Type], 380187h
0x14000eb58  mov     [rbp+OpenParameters.MediumArray], rax
0x14000eb5c  lea     rax, [rbp+arg_10]
0x14000eb60  mov     [rbp+OpenParameters.SelectedMediumIndex], rax
0x14000eb64  lea     rax, [rbp+arg_0]
0x14000eb68  mov     [rbp+OpenParameters.FrameTypeArray], rax
0x14000eb6c  mov     [rbp+OpenParameters.AdapterName], rbx
0x14000eb70  mov     [rbp+OpenParameters.MediumArraySize], 1
0x14000eb77  mov     [rbp+OpenParameters.FrameTypeArraySize], 2
0x14000eb7e  mov     r9, [rdi+28h]; BindContext
0x14000eb82  lea     rax, [rdi+158h]
0x14000eb89  mov     rcx, cs:gl_NdisProtocolDriverHandle; NdisProtocolHandle
0x14000eb90  lea     r8, [rbp+OpenParameters]; OpenParameters
0x14000eb94  mov     rdx, rdi; ProtocolBindingContext
0x14000eb97  mov     [rsp+70h+NdisBindingHandle], rax; NdisBindingHandle
0x14000eb9c  call    cs:__imp_NdisOpenAdapterEx
0x14000eba3  nop     dword ptr [rax+rax+00h]
0x14000eba8  cmp     eax, 103h
0x14000ebad  jz      short loc_14000EBB9
0x14000ebaf  mov     edx, eax
0x14000ebb1  mov     rcx, rdi
0x14000ebb4  call    PrOpenAdapterComplete
0x14000ebb9  lea     rbx, [rdi+128h]
0x14000ebc0  xor     edx, edx; MsToWait
0x14000ebc2  mov     rcx, rbx; Event
0x14000ebc5  call    cs:__imp_NdisWaitEvent
0x14000ebcc  nop     dword ptr [rax+rax+00h]
0x14000ebd1  mov     rcx, rbx; Event
0x14000ebd4  call    cs:__imp_NdisResetEvent
0x14000ebdb  nop     dword ptr [rax+rax+00h]
0x14000ebe0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ebe7  cmp     rcx, r14
0x14000ebea  jz      short loc_14000EC0E
0x14000ebec  mov     eax, [rcx+2Ch]
0x14000ebef  test    al, 4
0x14000ebf1  jz      short loc_14000EC0E
0x14000ebf3  cmp     byte ptr [rcx+29h], 3
0x14000ebf7  jb      short loc_14000EC0E
0x14000ebf9  mov     rcx, [rcx+18h]
0x14000ebfd  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000ec04  mov     edx, 26h ; '&'
0x14000ec09  call    WPP_SF_
0x14000ec0e  cmp     dword ptr [rdi+20h], 0
0x14000ec12  mov     rbx, [rsp+70h+arg_18]
0x14000ec1a  setz    al
0x14000ec1d  add     rsp, 70h
0x14000ec21  pop     r14
0x14000ec23  pop     rdi
0x14000ec24  pop     rbp
0x14000ec25  retn
```
