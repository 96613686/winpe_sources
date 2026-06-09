# InitializeSecurityContextW

- ea: `0x1800247d0`
- end: `0x180024846`
- name: `InitializeSecurityContextW`
- size: `118`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, PSECURITY_STRING pTargetName, unsigned int fContextReq, unsigned int Reserved1, unsigned int TargetDataRep, PSecBufferDesc pInput, unsigned int Reserved2, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800248c0`

## pseudocode

```c
SECURITY_STATUS __stdcall InitializeSecurityContextW(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        PSECURITY_STRING pTargetName,
        unsigned int fContextReq,
        unsigned int Reserved1,
        unsigned int TargetDataRep,
        PSecBufferDesc pInput,
        unsigned int Reserved2,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  PSECURITY_STRING v13; // r9

  v13 = (PSECURITY_STRING)&xmmword_1800196F0;
  if ( pTargetName )
    v13 = pTargetName;
  return KsecProcessSecurityContext(
           0,
           (__int128 *)phCredential,
           (__int64 *)phContext,
           (__int64)v13,
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
0x1800247d0  mov     r11, rsp
0x1800247d3  sub     rsp, 68h
0x1800247d7  mov     rax, [rsp+68h+ptsExpiry]
0x1800247df  mov     r10d, r9d
0x1800247e2  mov     [r11-18h], rax
0x1800247e6  lea     r9, xmmword_1800196F0
0x1800247ed  mov     rax, [rsp+68h+pfContextAttr]
0x1800247f5  test    r8, r8
0x1800247f8  mov     [r11-20h], rax
0x1800247fc  mov     rax, [rsp+68h+pOutput]
0x180024804  cmovnz  r9, r8
0x180024808  mov     [r11-28h], rax
0x18002480c  mov     r8, rdx
0x18002480f  mov     rax, [rsp+68h+phNewContext]
0x180024817  mov     rdx, rcx
0x18002481a  mov     [r11-30h], rax
0x18002481e  xor     ecx, ecx
0x180024820  mov     eax, [rsp+68h+TargetDataRep]
0x180024827  mov     [rsp+68h+var_38], eax
0x18002482b  mov     rax, [rsp+68h+pInput]
0x180024833  mov     [r11-40h], r10d
0x180024837  mov     [r11-48h], rax
0x18002483b  call    KsecProcessSecurityContext
0x180024840  add     rsp, 68h
0x180024844  retn
```
