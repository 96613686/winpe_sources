# InitializeSecurityContextW

- ea: `0x180024820`
- end: `0x180024896`
- name: `InitializeSecurityContextW`
- size: `118`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, PSECURITY_STRING pTargetName, unsigned int fContextReq, unsigned int Reserved1, unsigned int TargetDataRep, PSecBufferDesc pInput, unsigned int Reserved2, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180024910`

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
0x180024820  mov     r11, rsp
0x180024823  sub     rsp, 68h
0x180024827  mov     rax, [rsp+68h+ptsExpiry]
0x18002482f  mov     r10d, r9d
0x180024832  mov     [r11-18h], rax
0x180024836  lea     r9, xmmword_1800196F0
0x18002483d  mov     rax, [rsp+68h+pfContextAttr]
0x180024845  test    r8, r8
0x180024848  mov     [r11-20h], rax
0x18002484c  mov     rax, [rsp+68h+pOutput]
0x180024854  cmovnz  r9, r8
0x180024858  mov     [r11-28h], rax
0x18002485c  mov     r8, rdx
0x18002485f  mov     rax, [rsp+68h+phNewContext]
0x180024867  mov     rdx, rcx
0x18002486a  mov     [r11-30h], rax
0x18002486e  xor     ecx, ecx
0x180024870  mov     eax, [rsp+68h+TargetDataRep]
0x180024877  mov     [rsp+68h+var_38], eax
0x18002487b  mov     rax, [rsp+68h+pInput]
0x180024883  mov     [r11-40h], r10d
0x180024887  mov     [r11-48h], rax
0x18002488b  call    KsecProcessSecurityContext
0x180024890  add     rsp, 68h
0x180024894  retn
```
