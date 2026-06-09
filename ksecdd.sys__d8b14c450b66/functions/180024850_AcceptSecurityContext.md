# AcceptSecurityContext

- ea: `0x180024850`
- end: `0x1800248b0`
- name: `AcceptSecurityContext`
- size: `96`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, PSecBufferDesc pInput, unsigned int fContextReq, unsigned int TargetDataRep, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800248c0`

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
0x180024850  mov     r11, rsp
0x180024853  sub     rsp, 68h
0x180024857  mov     rax, [rsp+68h+ptsExpiry]
0x18002485f  mov     [r11-18h], rax
0x180024863  mov     rax, [rsp+68h+pfContextAttr]
0x18002486b  mov     [r11-20h], rax
0x18002486f  mov     rax, [rsp+68h+pOutput]
0x180024877  mov     [r11-28h], rax
0x18002487b  mov     rax, [rsp+68h+phNewContext]
0x180024883  mov     [r11-30h], rax
0x180024887  mov     eax, [rsp+68h+TargetDataRep]
0x18002488e  mov     [rsp+68h+var_38], eax
0x180024892  mov     [r11-40h], r9d
0x180024896  xor     r9d, r9d
0x180024899  mov     [r11-48h], r8
0x18002489d  mov     r8, rdx
0x1800248a0  mov     rdx, rcx
0x1800248a3  xor     ecx, ecx
0x1800248a5  call    KsecProcessSecurityContext
0x1800248aa  add     rsp, 68h
0x1800248ae  retn
```
