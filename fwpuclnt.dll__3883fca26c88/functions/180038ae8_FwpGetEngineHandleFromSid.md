# FwpGetEngineHandleFromSid

- ea: `0x180038ae8`
- end: `0x180038c32`
- name: `FwpGetEngineHandleFromSid`
- size: `330`
- prototype: `__int64 __fastcall(PSID Sid2, HANDLE *engineHandle)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180038a44`
- `0x180038dd8`

## callees

- `0x1800034e0`
- `0x180003704`
- `0x180007380`
- `0x180007e38`
- `0x180012bd0`
- `0x18001346a`
- `0x180038ae8`
- `0x18003966c`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180038b48`
- `ntdll!RtlEqualSid` at `0x180038b48`

## string_xrefs

- `0x180038ba6`: `FwpmEngineOpen0`
- `0x180038b76`: `Name Resolution Cache Session`
- `0x180038be3`: `FwpGetEngineHandleFromSid`
- `0x180038bf7`: `FwpGetEngineHandleFromSid`

## pseudocode

```c
__int64 __fastcall FwpGetEngineHandleFromSid(PSID Sid2, HANDLE *engineHandle, int a3)
{
  __int64 v6; // rcx
  __int64 *v7; // rbx
  __int64 *v8; // rsi
  __int64 inserted; // rbx
  DWORD v10; // eax
  __int64 v11; // r8
  const char *v12; // rdx
  HANDLE v14[2]; // [rsp+30h] [rbp-88h] BYREF
  FWPM_SESSION0 session; // [rsp+40h] [rbp-78h] BYREF

  memset_0(&session, 0, sizeof(session));
  v7 = (__int64 *)qword_18007C420;
  while ( v7 != &qword_18007C420 )
  {
    v8 = v7;
    v7 = (__int64 *)*v7;
    if ( RtlEqualSid((PSID)v8[3], Sid2) )
    {
      inserted = 0;
      *engineHandle = (HANDLE)v8[2];
      return inserted;
    }
  }
  if ( !a3 )
  {
    v11 = 1168;
    v12 = "FwpGetEngineHandleFromSid";
LABEL_11:
    inserted = WfpReportSysErrorAsWinError(v6, v12, v11);
    if ( inserted )
      goto LABEL_12;
    return inserted;
  }
  session.flags = 268435457;
  session.txnWaitTimeoutInMSec = 10000;
  session.displayData.name = L"Name Resolution Cache Session";
  v10 = FwpmEngineOpen0(0, 0xAu, 0, &session, engineHandle);
  if ( v10 )
  {
    v11 = v10;
    v12 = "FwpmEngineOpen0";
    goto LABEL_11;
  }
  inserted = FwppInsertNameCacheEntry(*engineHandle, Sid2);
  if ( inserted )
  {
    v14[0] = *engineHandle;
    FwppSessionDestroy(v14);
    *engineHandle = 0;
LABEL_12:
    WfpReportError(inserted, "FwpGetEngineHandleFromSid");
  }
  return inserted;
}

```

## disassembly

```asm
0x180038ae8  mov     [rsp+arg_10], rbx
0x180038aed  mov     [rsp+arg_18], rbp
0x180038af2  push    rsi
0x180038af3  push    rdi
0x180038af4  push    r14
0x180038af6  sub     rsp, 0A0h
0x180038afd  mov     rax, cs:__security_cookie
0x180038b04  xor     rax, rsp
0x180038b07  mov     [rsp+0B8h+var_28], rax
0x180038b0f  mov     rdi, rdx
0x180038b12  mov     r14d, r8d
0x180038b15  xor     edx, edx; Val
0x180038b17  mov     rbp, rcx
0x180038b1a  lea     rcx, [rsp+0B8h+session]; void *
0x180038b1f  lea     r8d, [rdx+48h]; Size
0x180038b23  call    memset_0
0x180038b28  mov     rbx, cs:qword_18007C420
0x180038b2f  lea     rax, qword_18007C420
0x180038b36  cmp     rbx, rax
0x180038b39  jz      short loc_180038B66
0x180038b3b  mov     rsi, rbx
0x180038b3e  mov     rdx, rbp; Sid2
0x180038b41  mov     rbx, [rbx]
0x180038b44  mov     rcx, [rsi+18h]; Sid1
0x180038b48  call    cs:__imp_RtlEqualSid
0x180038b4f  nop     dword ptr [rax+rax+00h]
0x180038b54  test    al, al
0x180038b56  jz      short loc_180038B2F
0x180038b58  mov     rax, [rsi+10h]
0x180038b5c  xor     ebx, ebx
0x180038b5e  mov     [rdi], rax
0x180038b61  jmp     loc_180038C06
0x180038b66  test    r14d, r14d
0x180038b69  jz      short loc_180038BDD
0x180038b6b  xor     r8d, r8d; authIdentity
0x180038b6e  mov     [rsp+0B8h+session.flags], 10000001h
0x180038b76  lea     rax, aNameResolution; "Name Resolution Cache Session"
0x180038b7d  mov     [rsp+0B8h+session.txnWaitTimeoutInMSec], 2710h
0x180038b85  lea     r9, [rsp+0B8h+session]; session
0x180038b8a  mov     [rsp+0B8h+session.displayData.name], rax
0x180038b8f  xor     ecx, ecx; serverName
0x180038b91  mov     [rsp+0B8h+engineHandle], rdi; engineHandle
0x180038b96  lea     edx, [r8+0Ah]; authnService
0x180038b9a  call    FwpmEngineOpen0
0x180038b9f  test    eax, eax
0x180038ba1  jz      short loc_180038BAF
0x180038ba3  mov     r8d, eax
0x180038ba6  lea     rdx, aFwpmengineopen_0; "FwpmEngineOpen0"
0x180038bad  jmp     short loc_180038BEA
0x180038baf  mov     rcx, [rdi]
0x180038bb2  mov     rdx, rbp
0x180038bb5  call    FwppInsertNameCacheEntry
0x180038bba  mov     rbx, rax
0x180038bbd  test    rax, rax
0x180038bc0  jz      short loc_180038C06
0x180038bc2  mov     rax, [rdi]
0x180038bc5  lea     rcx, [rsp+0B8h+var_88]
0x180038bca  mov     [rsp+0B8h+var_88], rax
0x180038bcf  call    FwppSessionDestroy
0x180038bd4  mov     qword ptr [rdi], 0
0x180038bdb  jmp     short loc_180038BF7
0x180038bdd  mov     r8d, 490h
0x180038be3  lea     rdx, aFwpgetengineha_0; "FwpGetEngineHandleFromSid"
0x180038bea  call    WfpReportSysErrorAsWinError
0x180038bef  mov     rbx, rax
0x180038bf2  test    rax, rax
0x180038bf5  jz      short loc_180038C06
0x180038bf7  lea     rdx, aFwpgetengineha_0; "FwpGetEngineHandleFromSid"
0x180038bfe  mov     rcx, rbx
0x180038c01  call    WfpReportError
0x180038c06  mov     rax, rbx
0x180038c09  mov     rcx, [rsp+0B8h+var_28]
0x180038c11  xor     rcx, rsp; StackCookie
0x180038c14  call    __security_check_cookie
0x180038c19  lea     r11, [rsp+0B8h+var_18]
0x180038c21  mov     rbx, [r11+30h]
0x180038c25  mov     rbp, [r11+38h]
0x180038c29  mov     rsp, r11
0x180038c2c  pop     r14
0x180038c2e  pop     rdi
0x180038c2f  pop     rsi
0x180038c30  retn
```
