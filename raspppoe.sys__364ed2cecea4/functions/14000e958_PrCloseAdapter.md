# PrCloseAdapter

- ea: `0x14000e958`
- end: `0x14000ea1e`
- name: `PrCloseAdapter`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004100`
- `0x140004e10`

## callees

- `0x14000110c`
- `0x1400043c0`
- `0x14000e958`

## import_xrefs

- `NDIS!NdisCloseAdapterEx` at `0x14000e9a1`
- `NDIS!NdisCloseAdapterEx` at `0x14000e9a1`
- `NDIS!NdisResetEvent` at `0x14000e9d8`
- `NDIS!NdisResetEvent` at `0x14000e9d8`
- `NDIS!NdisWaitEvent` at `0x14000e9c5`
- `NDIS!NdisWaitEvent` at `0x14000e9c5`

## pseudocode

```c
void __fastcall PrCloseAdapter(__int64 a1)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x41u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  if ( NdisCloseAdapterEx(*(NDIS_HANDLE *)(a1 + 344)) != 259 )
    PrCloseAdapterComplete(a1);
  NdisWaitEvent((PNDIS_EVENT)(a1 + 296), 0);
  NdisResetEvent((PNDIS_EVENT)(a1 + 296));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x42u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
}

```

## disassembly

```asm
0x14000e958  mov     [rsp+arg_0], rbx
0x14000e95d  push    rdi
0x14000e95e  sub     rsp, 20h
0x14000e962  mov     rbx, rcx
0x14000e965  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e96c  lea     rdi, WPP_GLOBAL_Control
0x14000e973  cmp     rcx, rdi
0x14000e976  jz      short loc_14000E99A
0x14000e978  mov     eax, [rcx+2Ch]
0x14000e97b  test    al, 4
0x14000e97d  jz      short loc_14000E99A
0x14000e97f  cmp     byte ptr [rcx+29h], 3
0x14000e983  jb      short loc_14000E99A
0x14000e985  mov     rcx, [rcx+18h]
0x14000e989  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000e990  mov     edx, 41h ; 'A'
0x14000e995  call    WPP_SF_
0x14000e99a  mov     rcx, [rbx+158h]; NdisBindingHandle
0x14000e9a1  call    cs:__imp_NdisCloseAdapterEx
0x14000e9a8  nop     dword ptr [rax+rax+00h]
0x14000e9ad  cmp     eax, 103h
0x14000e9b2  jz      short loc_14000E9BC
0x14000e9b4  mov     rcx, rbx
0x14000e9b7  call    PrCloseAdapterComplete
0x14000e9bc  xor     edx, edx; MsToWait
0x14000e9be  lea     rcx, [rbx+128h]; Event
0x14000e9c5  call    cs:__imp_NdisWaitEvent
0x14000e9cc  nop     dword ptr [rax+rax+00h]
0x14000e9d1  lea     rcx, [rbx+128h]; Event
0x14000e9d8  call    cs:__imp_NdisResetEvent
0x14000e9df  nop     dword ptr [rax+rax+00h]
0x14000e9e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9eb  cmp     rcx, rdi
0x14000e9ee  jz      short loc_14000EA12
0x14000e9f0  mov     eax, [rcx+2Ch]
0x14000e9f3  test    al, 4
0x14000e9f5  jz      short loc_14000EA12
0x14000e9f7  cmp     byte ptr [rcx+29h], 3
0x14000e9fb  jb      short loc_14000EA12
0x14000e9fd  mov     rcx, [rcx+18h]
0x14000ea01  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000ea08  mov     edx, 42h ; 'B'
0x14000ea0d  call    WPP_SF_
0x14000ea12  mov     rbx, [rsp+28h+arg_0]
0x14000ea17  add     rsp, 20h
0x14000ea1b  pop     rdi
0x14000ea1c  retn
```
