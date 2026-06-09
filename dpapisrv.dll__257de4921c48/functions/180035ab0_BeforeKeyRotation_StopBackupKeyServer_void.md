# BeforeKeyRotation::StopBackupKeyServer(void)

- ea: `0x180035ab0`
- end: `0x180035b61`
- name: `?StopBackupKeyServer@BeforeKeyRotation@@YAKXZ`
- size: `177`
- prototype: `unsigned int __fastcall(BeforeKeyRotation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800283c4`

## callees

- `0x180008300`
- `0x18001d810`
- `0x1800318e0`
- `0x180031940`
- `0x180035ab0`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIf` at `0x180035b04`
- `RPCRT4!RpcServerUnregisterIf` at `0x180035b04`
- `ntdll!RtlDeleteCriticalSection` at `0x180035ad5`
- `ntdll!RtlDeleteCriticalSection` at `0x180035ad5`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::StopBackupKeyServer(BeforeKeyRotation *this)
{
  unsigned int v2; // ebx
  BeforeKeyRotation *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // r8
  _BYTE v6[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( BeforeKeyRotation::g_fcsInitializationSetup )
  {
    RtlDeleteCriticalSection(&BeforeKeyRotation::g_csInitialization);
    BeforeKeyRotation::g_fcsInitializationSetup = 0;
  }
  if ( !g_fBackupKeyServerStarted )
    return 0;
  v2 = RpcServerUnregisterIf(qword_18003FD60, 0, 0);
  BeforeKeyRotation::FreePreferredBackupKey(v3);
  FreeSystemCredentials();
  g_fBackupKeyServerStarted = 0;
  if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v4, (__int64)ETW_LOG_BACKUPKEYSVC_STOPPED, v5, 1, (__int64)v6);
  return v2;
}

```

## disassembly

```asm
0x180035ab0  push    rbx
0x180035ab2  sub     rsp, 50h
0x180035ab6  mov     rax, cs:__security_cookie
0x180035abd  xor     rax, rsp
0x180035ac0  mov     [rsp+58h+var_18], rax
0x180035ac5  cmp     cs:?g_fcsInitializationSetup@BeforeKeyRotation@@3HA, 0; int BeforeKeyRotation::g_fcsInitializationSetup
0x180035acc  jz      short loc_180035AEB
0x180035ace  lea     rcx, ?g_csInitialization@BeforeKeyRotation@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180035ad5  call    cs:__imp_RtlDeleteCriticalSection
0x180035adc  nop     dword ptr [rax+rax+00h]
0x180035ae1  mov     cs:?g_fcsInitializationSetup@BeforeKeyRotation@@3HA, 0; int BeforeKeyRotation::g_fcsInitializationSetup
0x180035aeb  cmp     cs:?g_fBackupKeyServerStarted@@3HA, 0; int g_fBackupKeyServerStarted
0x180035af2  jnz     short loc_180035AF8
0x180035af4  xor     eax, eax
0x180035af6  jmp     short loc_180035B4D
0x180035af8  xor     r8d, r8d; WaitForCallsToComplete
0x180035afb  lea     rcx, qword_18003FD60; IfSpec
0x180035b02  xor     edx, edx; MgrTypeUuid
0x180035b04  call    cs:__imp_RpcServerUnregisterIf
0x180035b0b  nop     dword ptr [rax+rax+00h]
0x180035b10  mov     ebx, eax
0x180035b12  call    ?FreePreferredBackupKey@BeforeKeyRotation@@YAHXZ; BeforeKeyRotation::FreePreferredBackupKey(void)
0x180035b17  call    ?FreeSystemCredentials@@YAHXZ; FreeSystemCredentials(void)
0x180035b1c  mov     r9d, 1
0x180035b22  mov     cs:?g_fBackupKeyServerStarted@@3HA, 0; int g_fBackupKeyServerStarted
0x180035b2c  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, r9b
0x180035b33  jz      short loc_180035B4B
0x180035b35  lea     rax, [rsp+58h+var_28]
0x180035b3a  lea     rdx, ETW_LOG_BACKUPKEYSVC_STOPPED
0x180035b41  mov     [rsp+58h+var_38], rax
0x180035b46  call    McGenEventWrite_EtwEventWriteTransfer
0x180035b4b  mov     eax, ebx
0x180035b4d  mov     rcx, [rsp+58h+var_18]
0x180035b52  xor     rcx, rsp; StackCookie
0x180035b55  call    __security_check_cookie
0x180035b5a  add     rsp, 50h
0x180035b5e  pop     rbx
0x180035b5f  retn
```
