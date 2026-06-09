# RasPppoeCleanup

- ea: `0x140001020`
- end: `0x140001106`
- name: `RasPppoeCleanup`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d010`
- `0x140019078`

## callees

- `0x140001020`
- `0x14000110c`
- `0x14000f350`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140001062`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140001062`
- `NDIS!NdisDeregisterProtocolDriver` at `0x14000107a`
- `NDIS!NdisDeregisterProtocolDriver` at `0x14000107a`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x1400010ba`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x1400010ba`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400010a2`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400010a2`

## pseudocode

```c
void RasPppoeCleanup()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_8b64b0573a0f33142dd353fcc66fbdac_Traceguids);
  }
  ExDeleteNPagedLookasideList(&gl_llistWorkItems);
  if ( gl_NdisProtocolDriverHandle )
  {
    NdisDeregisterProtocolDriver(gl_NdisProtocolDriverHandle);
    gl_NdisProtocolDriverHandle = 0;
  }
  PrUnload();
  if ( gl_NblPoolHandle )
    NdisFreeNetBufferListPool(gl_NblPoolHandle);
  if ( gl_NdisMiniportDriverHandle )
  {
    NdisMDeregisterMiniportDriver(gl_NdisMiniportDriverHandle);
    gl_NdisMiniportDriverHandle = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_8b64b0573a0f33142dd353fcc66fbdac_Traceguids);
  }
}

```

## disassembly

```asm
0x140001020  push    rbx
0x140001022  sub     rsp, 20h
0x140001026  mov     rcx, cs:WPP_GLOBAL_Control
0x14000102d  lea     rbx, WPP_GLOBAL_Control
0x140001034  cmp     rcx, rbx
0x140001037  jz      short loc_14000105B
0x140001039  mov     eax, [rcx+2Ch]
0x14000103c  test    al, 10h
0x14000103e  jz      short loc_14000105B
0x140001040  cmp     byte ptr [rcx+29h], 3
0x140001044  jb      short loc_14000105B
0x140001046  mov     rcx, [rcx+18h]
0x14000104a  lea     r8, WPP_8b64b0573a0f33142dd353fcc66fbdac_Traceguids
0x140001051  mov     edx, 0Fh
0x140001056  call    WPP_SF_
0x14000105b  lea     rcx, gl_llistWorkItems; Lookaside
0x140001062  call    cs:__imp_ExDeleteNPagedLookasideList
0x140001069  nop     dword ptr [rax+rax+00h]
0x14000106e  mov     rcx, cs:gl_NdisProtocolDriverHandle; NdisProtocolHandle
0x140001075  test    rcx, rcx
0x140001078  jz      short loc_140001091
0x14000107a  call    cs:__imp_NdisDeregisterProtocolDriver
0x140001081  nop     dword ptr [rax+rax+00h]
0x140001086  mov     cs:gl_NdisProtocolDriverHandle, 0
0x140001091  call    PrUnload
0x140001096  mov     rcx, cs:gl_NblPoolHandle; PoolHandle
0x14000109d  test    rcx, rcx
0x1400010a0  jz      short loc_1400010AE
0x1400010a2  call    cs:__imp_NdisFreeNetBufferListPool
0x1400010a9  nop     dword ptr [rax+rax+00h]
0x1400010ae  mov     rcx, cs:gl_NdisMiniportDriverHandle; NdisMiniportDriverHandle
0x1400010b5  test    rcx, rcx
0x1400010b8  jz      short loc_1400010D1
0x1400010ba  call    cs:__imp_NdisMDeregisterMiniportDriver
0x1400010c1  nop     dword ptr [rax+rax+00h]
0x1400010c6  mov     cs:gl_NdisMiniportDriverHandle, 0
0x1400010d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400010d8  cmp     rcx, rbx
0x1400010db  jz      short loc_1400010FF
0x1400010dd  mov     eax, [rcx+2Ch]
0x1400010e0  test    al, 10h
0x1400010e2  jz      short loc_1400010FF
0x1400010e4  cmp     byte ptr [rcx+29h], 3
0x1400010e8  jb      short loc_1400010FF
0x1400010ea  mov     rcx, [rcx+18h]
0x1400010ee  lea     r8, WPP_8b64b0573a0f33142dd353fcc66fbdac_Traceguids
0x1400010f5  mov     edx, 10h
0x1400010fa  call    WPP_SF_
0x1400010ff  add     rsp, 20h
0x140001103  pop     rbx
0x140001104  retn
```
