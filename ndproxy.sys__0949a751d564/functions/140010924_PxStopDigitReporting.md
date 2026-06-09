# PxStopDigitReporting

- ea: `0x140010924`
- end: `0x140010a0b`
- name: `PxStopDigitReporting`
- size: `231`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140010a14`
- `0x140014310`
- `0x140015290`

## callees

- `0x140007fc0`
- `0x1400084c0`
- `0x140010924`

## import_xrefs

- `NDIS!NdisInitializeEvent` at `0x140010976`
- `NDIS!NdisInitializeEvent` at `0x140010976`
- `NDIS!NdisCoOidRequest` at `0x1400109c5`
- `NDIS!NdisCoOidRequest` at `0x1400109c5`
- `NDIS!NdisWaitEvent` at `0x1400109de`
- `NDIS!NdisWaitEvent` at `0x1400109de`

## pseudocode

```c
NDIS_STATUS __fastcall PxStopDigitReporting(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  void *v4; // r8
  NDIS_STATUS result; // eax
  int v6; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE OidRequest[280]; // [rsp+40h] [rbp-C0h] BYREF

  v6 = 0;
  memset(OidRequest, 0, sizeof(OidRequest));
  *(_DWORD *)OidRequest = 15729046;
  *(_QWORD *)&OidRequest[8] = 0;
  NdisInitializeEvent((PNDIS_EVENT)&OidRequest[248]);
  v2 = a1[7];
  v3 = a1[11];
  v4 = (void *)a1[5];
  *(_QWORD *)&OidRequest[40] = &v6;
  *(_DWORD *)&OidRequest[4] = 1;
  *(_DWORD *)&OidRequest[32] = -33550327;
  *(_DWORD *)&OidRequest[48] = 4;
  result = NdisCoOidRequest(*(NDIS_HANDLE *)(v3 + 32), *(NDIS_HANDLE *)(v2 + 24), v4, 0, (PNDIS_OID_REQUEST)OidRequest);
  if ( result == 259 )
  {
    NdisWaitEvent((PNDIS_EVENT)&OidRequest[248], 0);
    return *(_DWORD *)&OidRequest[272];
  }
  return result;
}

```

## disassembly

```asm
0x140010924  mov     [rsp-8+arg_8], rbx
0x140010929  push    rbp
0x14001092a  lea     rbp, [rsp-70h]
0x14001092f  sub     rsp, 170h
0x140010936  mov     rax, cs:__security_cookie
0x14001093d  xor     rax, rsp
0x140010940  mov     [rbp+70h+var_10], rax
0x140010944  mov     rbx, rcx
0x140010947  mov     [rsp+170h+var_140], 0
0x14001094f  lea     rcx, [rsp+170h+var_130]; void *
0x140010954  xor     edx, edx; Val
0x140010956  mov     r8d, 118h; Size
0x14001095c  call    memset
0x140010961  lea     rcx, [rbp+70h+Event]; Event
0x140010965  mov     dword ptr [rsp+170h+var_130.Header.Type], 0F00196h
0x14001096d  mov     qword ptr [rsp+170h+var_130.PortNumber], 0
0x140010976  call    cs:__imp_NdisInitializeEvent
0x14001097d  nop     dword ptr [rax+rax+00h]
0x140010982  mov     rdx, [rbx+38h]
0x140010986  lea     rax, [rsp+170h+var_140]
0x14001098b  mov     rcx, [rbx+58h]
0x14001098f  xor     r9d, r9d; NdisPartyHandle
0x140010992  mov     r8, [rbx+28h]; NdisVcHandle
0x140010996  mov     qword ptr [rsp+170h+var_130.DATA+8], rax
0x14001099b  lea     rax, [rsp+170h+var_130]
0x1400109a0  mov     [rsp+170h+var_130.RequestType], 1
0x1400109a8  mov     dword ptr [rsp+170h+var_130.DATA], 0FE001009h
0x1400109b0  mov     dword ptr [rsp+170h+var_130.DATA+10h], 4
0x1400109b8  mov     rdx, [rdx+18h]; NdisAfHandle
0x1400109bc  mov     rcx, [rcx+20h]; NdisBindingHandle
0x1400109c0  mov     [rsp+170h+OidRequest], rax; OidRequest
0x1400109c5  call    cs:__imp_NdisCoOidRequest
0x1400109cc  nop     dword ptr [rax+rax+00h]
0x1400109d1  cmp     eax, 103h
0x1400109d6  jnz     short loc_1400109ED
0x1400109d8  xor     edx, edx; MsToWait
0x1400109da  lea     rcx, [rbp+70h+Event]; Event
0x1400109de  call    cs:__imp_NdisWaitEvent
0x1400109e5  nop     dword ptr [rax+rax+00h]
0x1400109ea  mov     eax, [rbp+70h+var_20]
0x1400109ed  mov     rcx, [rbp+70h+var_10]
0x1400109f1  xor     rcx, rsp; StackCookie
0x1400109f4  call    __security_check_cookie
0x1400109f9  mov     rbx, [rsp+170h+arg_8]
0x140010a01  add     rsp, 170h
0x140010a08  pop     rbp
0x140010a09  retn
```
