# IPsecSaContextCreate0

- ea: `0x18001af20`
- end: `0x18001b018`
- name: `IPsecSaContextCreate0`
- size: `248`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const IPSEC_TRAFFIC0 *outboundTraffic, UINT64 *inboundFilterId, UINT64 *id)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800034e0`
- `0x180004540`
- `0x180006e40`
- `0x180007e38`
- `0x18001346a`
- `0x18001af20`
- `0x18001b020`
- `0x180035300`
- `0x1800375d8`

## string_xrefs

- `0x18001af47`: `IPsecSaContextCreate0`
- `0x18001afec`: `IPsecSaContextCreate1`
- `0x18001afbc`: `FwppAllocAndDeepCopyToVerIndependent_IPSEC_TRAFFIC0`

## pseudocode

```c
DWORD __stdcall IPsecSaContextCreate0(
        HANDLE engineHandle,
        const IPSEC_TRAFFIC0 *outboundTraffic,
        UINT64 *inboundFilterId,
        UINT64 *id)
{
  __int64 v8; // r8
  const char *v9; // rdx
  __int64 v10; // rbx
  DWORD v11; // eax

  if ( !id )
  {
    v8 = 2150760476LL;
    v9 = "IPsecSaContextCreate0";
LABEL_10:
    v10 = WfpReportSysErrorAsWinError(engineHandle, v9, v8);
    goto LABEL_11;
  }
  if ( outboundTraffic )
  {
    v10 = WfpPoolAllocNonPaged(0x48u);
    if ( v10 || (memset_0(0, 0, 0x48u), (v10 = FwppDeepCopyToVerIndependent_IPSEC_TRAFFIC0(outboundTraffic, 0)) != 0) )
    {
      FwppDeepFree_FWPM_NET_EVENT_CAPABILITY_DROP0(0);
      WfpReportError(v10, "FwppAllocAndDeepCopyToVerIndependent_IPSEC_TRAFFIC0");
      goto LABEL_11;
    }
  }
  else
  {
    v10 = 0;
  }
  v11 = IPsecSaContextCreate1(engineHandle, 0, 0, inboundFilterId, id);
  if ( v11 )
  {
    v8 = v11;
    v9 = "IPsecSaContextCreate1";
    goto LABEL_10;
  }
LABEL_11:
  FwppDeepFree_FWPM_NET_EVENT_CAPABILITY_DROP0(0);
  return WfpErrorToFwpErr(v10);
}

```

## disassembly

```asm
0x18001af20  push    rbx
0x18001af22  push    rbp
0x18001af23  push    rsi
0x18001af24  push    r12
0x18001af26  push    r14
0x18001af28  push    r15
0x18001af2a  sub     rsp, 38h
0x18001af2e  xor     esi, esi
0x18001af30  mov     r14, r9
0x18001af33  mov     r15, r8
0x18001af36  mov     rbp, rdx
0x18001af39  mov     r12, rcx
0x18001af3c  test    r9, r9
0x18001af3f  jnz     short loc_18001AF53
0x18001af41  mov     r8d, 8032001Ch
0x18001af47  lea     rdx, aIpsecsacontext_31; "IPsecSaContextCreate0"
0x18001af4e  jmp     loc_18001AFF3
0x18001af53  mov     [rsp+68h+outboundTraffic], rsi
0x18001af5b  test    rbp, rbp
0x18001af5e  jz      short loc_18001AFCD
0x18001af60  lea     r8, [rsp+68h+outboundTraffic]
0x18001af68  mov     ecx, 48h ; 'H'; dwBytes
0x18001af6d  call    WfpPoolAllocNonPaged
0x18001af72  mov     rbx, rax
0x18001af75  test    rax, rax
0x18001af78  jnz     short loc_18001AFAF
0x18001af7a  mov     rcx, [rsp+68h+outboundTraffic]; void *
0x18001af82  lea     r8d, [rax+48h]; Size
0x18001af86  xor     edx, edx; Val
0x18001af88  call    memset_0
0x18001af8d  mov     rdx, [rsp+68h+outboundTraffic]
0x18001af95  mov     rcx, rbp
0x18001af98  call    FwppDeepCopyToVerIndependent_IPSEC_TRAFFIC0
0x18001af9d  mov     rbx, rax
0x18001afa0  test    rax, rax
0x18001afa3  jnz     short loc_18001AFAF
0x18001afa5  mov     rsi, [rsp+68h+outboundTraffic]
0x18001afad  jmp     short loc_18001AFCF
0x18001afaf  mov     rcx, [rsp+68h+outboundTraffic]
0x18001afb7  call    FwppDeepFree_FWPM_NET_EVENT_CAPABILITY_DROP0
0x18001afbc  lea     rdx, aFwppallocandde_72; "FwppAllocAndDeepCopyToVerIndependent_IP"...
0x18001afc3  mov     rcx, rbx
0x18001afc6  call    WfpReportError
0x18001afcb  jmp     short loc_18001AFFB
0x18001afcd  xor     ebx, ebx
0x18001afcf  mov     r9, r15; inboundFilterId
0x18001afd2  mov     [rsp+68h+id], r14; id
0x18001afd7  xor     r8d, r8d; virtualIfTunnelInfo
0x18001afda  mov     rdx, rsi; outboundTraffic
0x18001afdd  mov     rcx, r12; engineHandle
0x18001afe0  call    IPsecSaContextCreate1
0x18001afe5  test    eax, eax
0x18001afe7  jz      short loc_18001AFFB
0x18001afe9  mov     r8d, eax
0x18001afec  lea     rdx, aIpsecsacontext_24; "IPsecSaContextCreate1"
0x18001aff3  call    WfpReportSysErrorAsWinError
0x18001aff8  mov     rbx, rax
0x18001affb  mov     rcx, rsi
0x18001affe  call    FwppDeepFree_FWPM_NET_EVENT_CAPABILITY_DROP0
0x18001b003  mov     rcx, rbx
0x18001b006  add     rsp, 38h
0x18001b00a  pop     r15
0x18001b00c  pop     r14
0x18001b00e  pop     r12
0x18001b010  pop     rsi
0x18001b011  pop     rbp
0x18001b012  pop     rbx
0x18001b013  jmp     WfpErrorToFwpErr
```
