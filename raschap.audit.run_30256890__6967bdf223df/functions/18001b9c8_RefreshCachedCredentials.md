# RefreshCachedCredentials

- ea: `0x18001b9c8`
- end: `0x18001bc73`
- name: `RefreshCachedCredentials`
- size: `683`
- prototype: `__int64 __fastcall(PCSZ SourceString, PCSZ, PCSZ)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b9b4`

## callees

- `0x180002ec8`
- `0x180006a20`
- `0x180013b20`
- `0x180014610`
- `0x18001b9c8`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x18001ba76`
- `ntdll!RtlInitAnsiString` at `0x18001badd`
- `ntdll!RtlInitAnsiString` at `0x18001bb41`
- `ntdll!RtlInitAnsiString` at `0x18001ba76`
- `ntdll!RtlInitAnsiString` at `0x18001badd`
- `ntdll!RtlInitAnsiString` at `0x18001bb41`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001baa5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001bb0f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001bb73`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001baa5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001bb0f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001bb73`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18001bbd0`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18001bbd0`
- `SspiCli!LsaFreeReturnBuffer` at `0x18001bc4a`
- `SspiCli!LsaFreeReturnBuffer` at `0x18001bc4a`

## pseudocode

```c
__int64 __fastcall RefreshCachedCredentials(PCSZ SourceString, PCSZ a2, PCSZ a3)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // edi
  int ProtocolStatus; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ReturnBufferLength; // [rsp+44h] [rbp-BCh] BYREF
  PVOID Buffer; // [rsp+48h] [rbp-B8h] BYREF
  struct _STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _STRING SourceStringa; // [rsp+60h] [rbp-A0h] BYREF
  struct _STRING v17; // [rsp+70h] [rbp-90h] BYREF
  _DWORD ProtocolSubmitBuffer[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v19; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v20; // [rsp+98h] [rbp-68h] BYREF
  int v21; // [rsp+A8h] [rbp-58h]
  __int64 v22; // [rsp+B0h] [rbp-50h]
  struct _UNICODE_STRING v23; // [rsp+B8h] [rbp-48h] BYREF
  char v24; // [rsp+C8h] [rbp-38h]
  char v25; // [rsp+D0h] [rbp-30h] BYREF
  char v26; // [rsp+2D2h] [rbp+1D2h] BYREF
  char v27; // [rsp+2F2h] [rbp+1F2h] BYREF

  ProtocolSubmitBuffer[1] = 0;
  memset_0(ProtocolSubmitBuffer, 0, 0x474u);
  Buffer = 0;
  v6 = 0;
  ReturnBufferLength = 32;
  ProtocolStatus = 0;
  DestinationString = 0;
  SourceStringa = 0;
  v17 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4e6115e193eb3138f1c42874084446a3_Traceguids);
  ProtocolSubmitBuffer[0] = 6;
  RtlInitAnsiString(&DestinationString, SourceString);
  v20.Length = 0;
  v20.MaximumLength = 2 * (DestinationString.Length + 1);
  v20.Buffer = (PWSTR)&v25;
  if ( RtlAnsiStringToUnicodeString(&v20, &DestinationString, 0) >= 0 )
  {
    RtlInitAnsiString(&SourceStringa, a2);
    v19.Length = 0;
    v19.MaximumLength = 2 * (SourceStringa.Length + 1);
    v19.Buffer = (PWSTR)&v26;
    if ( RtlAnsiStringToUnicodeString(&v19, &SourceStringa, 0) < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v6;
      v8 = 18;
      goto LABEL_6;
    }
    v21 = 0;
    v22 = 0;
    RtlInitAnsiString(&v17, a3);
    v23.Length = 0;
    v23.MaximumLength = 2 * (v17.Length + 1);
    v23.Buffer = (PWSTR)&v27;
    if ( RtlAnsiStringToUnicodeString(&v23, &v17, 0) < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v6;
      v8 = 19;
      goto LABEL_6;
    }
    v24 = 1;
    v9 = LsaCallAuthenticationPackage(
           g_hLsa,
           AuthenticationPackage,
           ProtocolSubmitBuffer,
           0x478u,
           &Buffer,
           &ReturnBufferLength,
           &ProtocolStatus);
    v6 = ProtocolStatus;
    v10 = v9;
    if ( v9 || ProtocolStatus )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_4e6115e193eb3138f1c42874084446a3_Traceguids,
          v9,
          ProtocolStatus);
        v6 = ProtocolStatus;
      }
      if ( v10 )
        v6 = v10;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4e6115e193eb3138f1c42874084446a3_Traceguids);
      v6 = 0;
    }
    memset_0(v23.Buffer, 0, v23.MaximumLength);
    if ( Buffer )
      LsaFreeReturnBuffer(Buffer);
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v8 = 17;
LABEL_6:
      WPP_SF_(v7[2], v8, WPP_4e6115e193eb3138f1c42874084446a3_Traceguids);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18001b9c8  push    rbp
0x18001b9ca  push    rbx
0x18001b9cb  push    rsi
0x18001b9cc  push    rdi
0x18001b9cd  push    r12
0x18001b9cf  push    r13
0x18001b9d1  push    r14
0x18001b9d3  lea     rbp, [rsp-410h]
0x18001b9db  sub     rsp, 510h
0x18001b9e2  mov     rax, cs:__security_cookie
0x18001b9e9  xor     rax, rsp
0x18001b9ec  mov     [rbp+440h+var_40], rax
0x18001b9f3  mov     r14, r8
0x18001b9f6  mov     rsi, rdx
0x18001b9f9  mov     rdi, rcx
0x18001b9fc  xor     eax, eax
0x18001b9fe  xor     edx, edx; Val
0x18001ba00  mov     [rbp+440h+var_4BC], eax
0x18001ba03  mov     r8d, 474h; Size
0x18001ba09  lea     rcx, [rbp+440h+ProtocolSubmitBuffer]; void *
0x18001ba0d  call    memset_0
0x18001ba12  xorps   xmm0, xmm0
0x18001ba15  mov     [rsp+540h+Buffer], 0
0x18001ba1e  xor     ebx, ebx
0x18001ba20  mov     [rsp+540h+var_4FC], 20h ; ' '
0x18001ba28  xorps   xmm1, xmm1
0x18001ba2b  mov     [rsp+540h+var_500], ebx
0x18001ba2f  movups  xmmword ptr [rsp+540h+DestinationString.Length], xmm0
0x18001ba34  movups  xmmword ptr [rsp+540h+SourceString.Length], xmm1
0x18001ba39  movups  xmmword ptr [rsp+540h+var_4D0.Length], xmm0
0x18001ba3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba45  lea     r13, WPP_GLOBAL_Control
0x18001ba4c  lea     r12, WPP_4e6115e193eb3138f1c42874084446a3_Traceguids
0x18001ba53  cmp     rcx, r13
0x18001ba56  jz      short loc_18001BA67
0x18001ba58  mov     rcx, [rcx+10h]
0x18001ba5c  lea     edx, [rbx+10h]
0x18001ba5f  mov     r8, r12
0x18001ba62  call    WPP_SF_
0x18001ba67  mov     rdx, rdi; SourceString
0x18001ba6a  mov     [rbp+440h+ProtocolSubmitBuffer], 6
0x18001ba71  lea     rcx, [rsp+540h+DestinationString]; DestinationString
0x18001ba76  call    cs:__imp_RtlInitAnsiString
0x18001ba7c  xor     eax, eax
0x18001ba7e  lea     rdx, [rsp+540h+DestinationString]; SourceString
0x18001ba83  mov     [rbp+440h+var_4A8.Length], ax
0x18001ba87  lea     rcx, [rbp+440h+var_4A8]; DestinationString
0x18001ba8b  movzx   eax, [rsp+540h+DestinationString.Length]
0x18001ba90  xor     r8d, r8d; AllocateDestinationString
0x18001ba93  inc     ax
0x18001ba96  add     ax, ax
0x18001ba99  mov     [rbp+440h+var_4A8.MaximumLength], ax
0x18001ba9d  lea     rax, [rbp+440h+var_470]
0x18001baa1  mov     [rbp+440h+var_4A8.Buffer], rax
0x18001baa5  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18001baab  test    eax, eax
0x18001baad  jns     short loc_18001BAD5
0x18001baaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bab6  cmp     rcx, r13
0x18001bab9  jz      loc_18001BC50
0x18001babf  mov     edx, 11h
0x18001bac4  mov     rcx, [rcx+10h]
0x18001bac8  mov     r8, r12
0x18001bacb  call    WPP_SF_
0x18001bad0  jmp     loc_18001BC50
0x18001bad5  mov     rdx, rsi; SourceString
0x18001bad8  lea     rcx, [rsp+540h+SourceString]; DestinationString
0x18001badd  call    cs:__imp_RtlInitAnsiString
0x18001bae3  xor     eax, eax
0x18001bae5  lea     rdx, [rsp+540h+SourceString]; SourceString
0x18001baea  mov     [rbp+440h+var_4B8.Length], ax
0x18001baee  lea     rcx, [rbp+440h+var_4B8]; DestinationString
0x18001baf2  movzx   eax, [rsp+540h+SourceString.Length]
0x18001baf7  xor     r8d, r8d; AllocateDestinationString
0x18001bafa  inc     ax
0x18001bafd  add     ax, ax
0x18001bb00  mov     [rbp+440h+var_4B8.MaximumLength], ax
0x18001bb04  lea     rax, [rbp+440h+var_26E]
0x18001bb0b  mov     [rbp+440h+var_4B8.Buffer], rax
0x18001bb0f  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18001bb15  test    eax, eax
0x18001bb17  jns     short loc_18001BB30
0x18001bb19  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb20  cmp     rcx, r13
0x18001bb23  jz      loc_18001BC50
0x18001bb29  mov     edx, 12h
0x18001bb2e  jmp     short loc_18001BAC4
0x18001bb30  xor     eax, eax
0x18001bb32  lea     rcx, [rsp+540h+var_4D0]; DestinationString
0x18001bb37  mov     rdx, r14; SourceString
0x18001bb3a  mov     [rbp+440h+var_498], eax
0x18001bb3d  mov     [rbp+440h+var_490], rax
0x18001bb41  call    cs:__imp_RtlInitAnsiString
0x18001bb47  xor     eax, eax
0x18001bb49  lea     rdx, [rsp+540h+var_4D0]; SourceString
0x18001bb4e  mov     [rbp+440h+var_488.Length], ax
0x18001bb52  lea     rcx, [rbp+440h+var_488]; DestinationString
0x18001bb56  movzx   eax, [rsp+540h+var_4D0.Length]
0x18001bb5b  xor     r8d, r8d; AllocateDestinationString
0x18001bb5e  inc     ax
0x18001bb61  add     ax, ax
0x18001bb64  mov     [rbp+440h+var_488.MaximumLength], ax
0x18001bb68  lea     rax, [rbp+440h+var_24E]
0x18001bb6f  mov     [rbp+440h+var_488.Buffer], rax
0x18001bb73  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18001bb79  test    eax, eax
0x18001bb7b  jns     short loc_18001BB97
0x18001bb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb84  cmp     rcx, r13
0x18001bb87  jz      loc_18001BC50
0x18001bb8d  mov     edx, 13h
0x18001bb92  jmp     loc_18001BAC4
0x18001bb97  mov     edx, cs:AuthenticationPackage; AuthenticationPackage
0x18001bb9d  lea     rax, [rsp+540h+var_500]
0x18001bba2  mov     rcx, cs:g_hLsa; LsaHandle
0x18001bba9  lea     r8, [rbp+440h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x18001bbad  mov     [rsp+540h+ProtocolStatus], rax; ProtocolStatus
0x18001bbb2  mov     r9d, 478h; SubmitBufferLength
0x18001bbb8  lea     rax, [rsp+540h+var_4FC]
0x18001bbbd  mov     [rbp+440h+var_478], 1
0x18001bbc1  mov     [rsp+540h+ReturnBufferLength], rax; ReturnBufferLength
0x18001bbc6  lea     rax, [rsp+540h+Buffer]
0x18001bbcb  mov     [rsp+540h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x18001bbd0  call    cs:__imp_LsaCallAuthenticationPackage
0x18001bbd6  mov     ebx, [rsp+540h+var_500]
0x18001bbda  mov     edi, eax
0x18001bbdc  test    eax, eax
0x18001bbde  jnz     short loc_18001BC03
0x18001bbe0  test    ebx, ebx
0x18001bbe2  jnz     short loc_18001BC03
0x18001bbe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbeb  cmp     rcx, r13
0x18001bbee  jz      short loc_18001BBFF
0x18001bbf0  mov     rcx, [rcx+10h]
0x18001bbf4  lea     edx, [rax+14h]
0x18001bbf7  mov     r8, r12
0x18001bbfa  call    WPP_SF_
0x18001bbff  xor     ebx, ebx
0x18001bc01  jmp     short loc_18001BC30
0x18001bc03  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc0a  cmp     rcx, r13
0x18001bc0d  jz      short loc_18001BC2B
0x18001bc0f  mov     rcx, [rcx+10h]
0x18001bc13  mov     edx, 15h
0x18001bc18  mov     r9d, edi
0x18001bc1b  mov     dword ptr [rsp+540h+ProtocolReturnBuffer], ebx
0x18001bc1f  mov     r8, r12
0x18001bc22  call    WPP_SF_dd
0x18001bc27  mov     ebx, [rsp+540h+var_500]
0x18001bc2b  test    edi, edi
0x18001bc2d  cmovnz  ebx, edi
0x18001bc30  movzx   r8d, [rbp+440h+var_488.MaximumLength]; Size
0x18001bc35  xor     edx, edx; Val
0x18001bc37  mov     rcx, [rbp+440h+var_488.Buffer]; void *
0x18001bc3b  call    memset_0
0x18001bc40  mov     rcx, [rsp+540h+Buffer]; Buffer
0x18001bc45  test    rcx, rcx
0x18001bc48  jz      short loc_18001BC50
0x18001bc4a  call    cs:__imp_LsaFreeReturnBuffer
0x18001bc50  mov     eax, ebx
0x18001bc52  mov     rcx, [rbp+440h+var_40]
0x18001bc59  xor     rcx, rsp; StackCookie
0x18001bc5c  call    __security_check_cookie
0x18001bc61  add     rsp, 510h
0x18001bc68  pop     r14
0x18001bc6a  pop     r13
0x18001bc6c  pop     r12
0x18001bc6e  pop     rdi
0x18001bc6f  pop     rsi
0x18001bc70  pop     rbx
0x18001bc71  pop     rbp
0x18001bc72  retn
```
