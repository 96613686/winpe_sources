# RTSecurityContextBase::HandleInternalCert(int)

- ea: `0x180016f30`
- end: `0x180016f96`
- name: `?HandleInternalCert@RTSecurityContextBase@@IEAAJH@Z`
- size: `102`
- prototype: `__int64 __fastcall(RTSecurityContextBase *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017460`
- `0x1800174e0`

## callees

- `0x18001275c`
- `0x180013c74`
- `0x180016f30`
- `0x180016f9c`

## pseudocode

```c
__int64 __fastcall RTSecurityContextBase::HandleInternalCert(RTSecurityContextBase *this, int a2)
{
  int v4; // ebx

  v4 = RTSecurityContextBase::HandleInternalCertImpl(this, a2);
  if ( v4 == -1072824273 )
  {
    if ( (unsigned int)RTFirstTimeRegisterInternalCert(a2) != 1074659338 )
    {
LABEL_5:
      LogMsgHR(v4, (wchar_t *)L"rt/rtsecctx", 0x14u);
      return (unsigned int)v4;
    }
    v4 = RTSecurityContextBase::HandleInternalCertImpl(this, a2);
  }
  if ( v4 < 0 )
    goto LABEL_5;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016f30  mov     [rsp+arg_0], rbx
0x180016f35  mov     [rsp+arg_8], rsi
0x180016f3a  push    rdi
0x180016f3b  sub     rsp, 20h
0x180016f3f  mov     edi, edx
0x180016f41  mov     rsi, rcx
0x180016f44  call    ?HandleInternalCertImpl@RTSecurityContextBase@@AEAAJH@Z; RTSecurityContextBase::HandleInternalCertImpl(int)
0x180016f49  mov     ebx, eax
0x180016f4b  cmp     eax, 0C00E002Fh
0x180016f50  jnz     short loc_180016F6C
0x180016f52  mov     ecx, edi
0x180016f54  call    RTFirstTimeRegisterInternalCert
0x180016f59  cmp     eax, 400E000Ah
0x180016f5e  jnz     short loc_180016F70
0x180016f60  mov     edx, edi; int
0x180016f62  mov     rcx, rsi; this
0x180016f65  call    ?HandleInternalCertImpl@RTSecurityContextBase@@AEAAJH@Z; RTSecurityContextBase::HandleInternalCertImpl(int)
0x180016f6a  mov     ebx, eax
0x180016f6c  test    ebx, ebx
0x180016f6e  jns     short loc_180016F84
0x180016f70  mov     r8d, 14h; unsigned __int16
0x180016f76  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016f7d  mov     ecx, ebx; int
0x180016f7f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180016f84  mov     rsi, [rsp+28h+arg_8]
0x180016f89  mov     eax, ebx
0x180016f8b  mov     rbx, [rsp+28h+arg_0]
0x180016f90  add     rsp, 20h
0x180016f94  pop     rdi
0x180016f95  retn
```
