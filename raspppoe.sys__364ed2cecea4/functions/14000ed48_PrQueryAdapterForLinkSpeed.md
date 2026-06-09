# PrQueryAdapterForLinkSpeed

- ea: `0x14000ed48`
- end: `0x14000ee5a`
- name: `PrQueryAdapterForLinkSpeed`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004100`

## callees

- `0x14000110c`
- `0x140004bb0`
- `0x140007040`
- `0x14000ed48`

## import_xrefs

- `NDIS!NdisResetEvent` at `0x14000ee08`
- `NDIS!NdisResetEvent` at `0x14000ee08`
- `NDIS!NdisWaitEvent` at `0x14000edf9`
- `NDIS!NdisWaitEvent` at `0x14000edf9`
- `NDIS!NdisOidRequest` at `0x14000edcc`
- `NDIS!NdisOidRequest` at `0x14000edcc`

## pseudocode

```c
bool __fastcall PrQueryAdapterForLinkSpeed(__int64 a1)
{
  struct _NDIS_OID_REQUEST *v2; // rbx
  NDIS_STATUS v3; // eax

  v2 = (struct _NDIS_OID_REQUEST *)(a1 + 56);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  memset(v2, 0, sizeof(struct _NDIS_OID_REQUEST));
  v2->Header = (NDIS_OBJECT_HEADER)15466902;
  v2->DATA.QUERY_INFORMATION.InformationBuffer = (PVOID)(a1 + 328);
  v2->DATA.QUERY_INFORMATION.Oid = 65799;
  v2->DATA.QUERY_INFORMATION.InformationBufferLength = 4;
  v3 = NdisOidRequest(*(NDIS_HANDLE *)(a1 + 344), v2);
  if ( v3 != 259 )
    PrRequestComplete(a1, (__int64)v2, v3);
  NdisWaitEvent((PNDIS_EVENT)(a1 + 296), 0);
  NdisResetEvent((PNDIS_EVENT)(a1 + 296));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  return *(_DWORD *)(a1 + 48) == 0;
}

```

## disassembly

```asm
0x14000ed48  mov     [rsp+arg_0], rbx
0x14000ed4d  mov     [rsp+arg_8], rsi
0x14000ed52  push    rdi
0x14000ed53  sub     rsp, 20h
0x14000ed57  mov     rdi, rcx
0x14000ed5a  lea     rbx, [rcx+38h]
0x14000ed5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed65  lea     rsi, WPP_GLOBAL_Control
0x14000ed6c  cmp     rcx, rsi
0x14000ed6f  jz      short loc_14000ED93
0x14000ed71  mov     eax, [rcx+2Ch]
0x14000ed74  test    al, 4
0x14000ed76  jz      short loc_14000ED93
0x14000ed78  cmp     byte ptr [rcx+29h], 3
0x14000ed7c  jb      short loc_14000ED93
0x14000ed7e  mov     rcx, [rcx+18h]
0x14000ed82  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000ed89  mov     edx, 2Ch ; ','
0x14000ed8e  call    WPP_SF_
0x14000ed93  xor     edx, edx; Val
0x14000ed95  mov     r8d, 0F0h; Size
0x14000ed9b  mov     rcx, rbx; void *
0x14000ed9e  call    memset
0x14000eda3  lea     rax, [rdi+148h]
0x14000edaa  mov     dword ptr [rbx], 0EC0196h
0x14000edb0  mov     [rbx+28h], rax
0x14000edb4  mov     rdx, rbx; OidRequest
0x14000edb7  mov     dword ptr [rbx+20h], 10107h
0x14000edbe  mov     dword ptr [rbx+30h], 4
0x14000edc5  mov     rcx, [rdi+158h]; NdisBindingHandle
0x14000edcc  call    cs:__imp_NdisOidRequest
0x14000edd3  nop     dword ptr [rax+rax+00h]
0x14000edd8  cmp     eax, 103h
0x14000eddd  jz      short loc_14000EDED
0x14000eddf  mov     r8d, eax
0x14000ede2  mov     rdx, rbx
0x14000ede5  mov     rcx, rdi
0x14000ede8  call    PrRequestComplete
0x14000eded  lea     rbx, [rdi+128h]
0x14000edf4  xor     edx, edx; MsToWait
0x14000edf6  mov     rcx, rbx; Event
0x14000edf9  call    cs:__imp_NdisWaitEvent
0x14000ee00  nop     dword ptr [rax+rax+00h]
0x14000ee05  mov     rcx, rbx; Event
0x14000ee08  call    cs:__imp_NdisResetEvent
0x14000ee0f  nop     dword ptr [rax+rax+00h]
0x14000ee14  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee1b  cmp     rcx, rsi
0x14000ee1e  jz      short loc_14000EE42
0x14000ee20  mov     eax, [rcx+2Ch]
0x14000ee23  test    al, 4
0x14000ee25  jz      short loc_14000EE42
0x14000ee27  cmp     byte ptr [rcx+29h], 3
0x14000ee2b  jb      short loc_14000EE42
0x14000ee2d  mov     rcx, [rcx+18h]
0x14000ee31  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000ee38  mov     edx, 2Dh ; '-'
0x14000ee3d  call    WPP_SF_
0x14000ee42  cmp     dword ptr [rdi+30h], 0
0x14000ee46  mov     rbx, [rsp+28h+arg_0]
0x14000ee4b  mov     rsi, [rsp+28h+arg_8]
0x14000ee50  setz    al
0x14000ee53  add     rsp, 20h
0x14000ee57  pop     rdi
0x14000ee58  retn
```
