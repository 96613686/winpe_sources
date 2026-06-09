# AcceptSecurityContext

- ea: `0x1800248a0`
- end: `0x180024900`
- name: `AcceptSecurityContext`
- size: `96`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, PSecBufferDesc pInput, unsigned int fContextReq, unsigned int TargetDataRep, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180024910`

## pseudocode

```c
SECURITY_STATUS __stdcall AcceptSecurityContext(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        PSecBufferDesc pInput,
        unsigned int fContextReq,
        unsigned int TargetDataRep,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  return KsecProcessSecurityContext(
           0,
           (__int128 *)phCredential,
           (__int64 *)phContext,
           0,
           pInput,
           fContextReq,
           TargetDataRep,
           (__int128 *)phNewContext,
           (__int64)pOutput,
           pfContextAttr,
           (__int64)ptsExpiry);
}

```

## disassembly

```asm
0x1800248a0  mov     r11, rsp
0x1800248a3  sub     rsp, 68h
0x1800248a7  mov     rax, [rsp+68h+ptsExpiry]
0x1800248af  mov     [r11-18h], rax
0x1800248b3  mov     rax, [rsp+68h+pfContextAttr]
0x1800248bb  mov     [r11-20h], rax
0x1800248bf  mov     rax, [rsp+68h+pOutput]
0x1800248c7  mov     [r11-28h], rax
0x1800248cb  mov     rax, [rsp+68h+phNewContext]
0x1800248d3  mov     [r11-30h], rax
0x1800248d7  mov     eax, [rsp+68h+TargetDataRep]
0x1800248de  mov     [rsp+68h+var_38], eax
0x1800248e2  mov     [r11-40h], r9d
0x1800248e6  xor     r9d, r9d
0x1800248e9  mov     [r11-48h], r8
0x1800248ed  mov     r8, rdx
0x1800248f0  mov     rdx, rcx
0x1800248f3  xor     ecx, ecx
0x1800248f5  call    KsecProcessSecurityContext
0x1800248fa  add     rsp, 68h
0x1800248fe  retn
```
