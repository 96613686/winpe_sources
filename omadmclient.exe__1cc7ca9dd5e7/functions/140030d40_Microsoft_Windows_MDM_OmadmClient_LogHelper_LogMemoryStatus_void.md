# Microsoft::Windows::MDM::OmadmClient::LogHelper::LogMemoryStatus(void)

- ea: `0x140030d40`
- end: `0x140030e9f`
- name: `?LogMemoryStatus@LogHelper@OmadmClient@MDM@Windows@Microsoft@@UEAAXXZ`
- size: `351`
- prototype: `void __fastcall(Microsoft::Windows::MDM::OmadmClient::LogHelper *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003450`
- `0x14000d71c`
- `0x1400307fc`
- `0x140030d40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140030dad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140030dad`

## pseudocode

```c
void __fastcall Microsoft::Windows::MDM::OmadmClient::LogHelper::LogMemoryStatus(
        Microsoft::Windows::MDM::OmadmClient::LogHelper *this,
        __int64 a2,
        __int64 a3)
{
  DWORD CurrentProcessId; // eax
  int ProcessMemorySize; // eax
  __int64 v6; // r8
  int v7; // ebx
  __int64 *v8; // rdx
  unsigned __int64 v9; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int64 *v11; // [rsp+48h] [rbp-20h]
  __int64 v12; // [rsp+50h] [rbp-18h]

  if ( !*((_DWORD *)this + 2) )
    return;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(v9) = 7;
    v11 = &v9;
    v12 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      a3,
      2u,
      &v10);
  }
  CurrentProcessId = *((_DWORD *)this + 3);
  if ( !CurrentProcessId )
  {
    CurrentProcessId = GetCurrentProcessId();
    *((_DWORD *)this + 3) = CurrentProcessId;
  }
  v9 = 0;
  ProcessMemorySize = Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProcessMemorySize(this, CurrentProcessId, &v9);
  if ( ProcessMemorySize < 0 )
  {
LABEL_12:
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 2) == 0 )
      return;
    LODWORD(v9) = ProcessMemorySize;
    v8 = ErrorGettingHeapUsageEvent;
    goto LABEL_14;
  }
  v7 = v9;
  if ( v9 > 0xFFFFFFFF )
  {
    ProcessMemorySize = -2147024362;
    goto LABEL_12;
  }
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 0x10) != 0 )
  {
    v11 = &v9;
    v12 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RAM_FROM_SESSION_INIT_TO_COMPLETION_MARKER_START,
      v6,
      2u,
      &v10);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 0x10) != 0 )
    {
      LODWORD(v9) = v7;
      v8 = RAM_FROM_SESSION_INIT_TO_COMPLETION_MARKER_STOP;
LABEL_14:
      v12 = 4;
      v11 = &v9;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)v8,
        v6,
        2u,
        &v10);
    }
  }
}

```

## disassembly

```asm
0x140030d40  mov     r11, rsp
0x140030d43  push    rbx
0x140030d44  sub     rsp, 60h
0x140030d48  mov     rax, cs:__security_cookie
0x140030d4f  xor     rax, rsp
0x140030d52  mov     [rsp+68h+var_10], rax
0x140030d57  cmp     dword ptr [rcx+8], 0
0x140030d5b  mov     rbx, rcx
0x140030d5e  jz      loc_140030E8B
0x140030d64  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140030d6b  jz      short loc_140030DA6
0x140030d6d  lea     rax, [r11-38h]
0x140030d71  mov     dword ptr [rsp+68h+var_38], 7
0x140030d79  mov     [r11-20h], rax
0x140030d7d  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x140030d84  lea     rax, [r11-30h]
0x140030d88  mov     qword ptr [r11-18h], 4
0x140030d90  mov     r9d, 2
0x140030d96  mov     [r11-48h], rax
0x140030d9a  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140030da1  call    McGenEventWrite_EventWriteTransfer
0x140030da6  mov     eax, [rbx+0Ch]
0x140030da9  test    eax, eax
0x140030dab  jnz     short loc_140030DBC
0x140030dad  call    cs:__imp_GetCurrentProcessId
0x140030db4  nop     dword ptr [rax+rax+00h]
0x140030db9  mov     [rbx+0Ch], eax
0x140030dbc  lea     r8, [rsp+68h+var_38]; unsigned __int64 *
0x140030dc1  mov     [rsp+68h+var_38], 0
0x140030dca  mov     edx, eax; unsigned int
0x140030dcc  call    ?GetProcessMemorySize@LogHelper@OmadmClient@MDM@Windows@Microsoft@@IEAAJKPEA_K@Z; Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProcessMemorySize(ulong,unsigned __int64 *)
0x140030dd1  test    eax, eax
0x140030dd3  js      short loc_140030E48
0x140030dd5  mov     rbx, [rsp+68h+var_38]
0x140030dda  mov     eax, 0FFFFFFFFh
0x140030ddf  cmp     rbx, rax
0x140030de2  ja      short loc_140030E43
0x140030de4  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x140030dea  test    al, 10h
0x140030dec  jz      loc_140030E8B
0x140030df2  lea     rax, [rsp+68h+var_38]
0x140030df7  mov     dword ptr [rsp+68h+var_38], ebx
0x140030dfb  mov     [rsp+68h+var_20], rax
0x140030e00  lea     rdx, RAM_FROM_SESSION_INIT_TO_COMPLETION_MARKER_START
0x140030e07  lea     rax, [rsp+68h+var_30]
0x140030e0c  mov     [rsp+68h+var_18], 4
0x140030e15  mov     r9d, 2
0x140030e1b  mov     [rsp+68h+var_48], rax
0x140030e20  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140030e27  call    McGenEventWrite_EventWriteTransfer
0x140030e2c  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x140030e32  test    al, 10h
0x140030e34  jz      short loc_140030E8B
0x140030e36  mov     dword ptr [rsp+68h+var_38], ebx
0x140030e3a  lea     rdx, RAM_FROM_SESSION_INIT_TO_COMPLETION_MARKER_STOP
0x140030e41  jmp     short loc_140030E5C
0x140030e43  mov     eax, 80070216h
0x140030e48  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 2
0x140030e4f  jz      short loc_140030E8B
0x140030e51  mov     dword ptr [rsp+68h+var_38], eax
0x140030e55  lea     rdx, ErrorGettingHeapUsageEvent
0x140030e5c  lea     rax, [rsp+68h+var_38]
0x140030e61  mov     [rsp+68h+var_18], 4
0x140030e6a  mov     [rsp+68h+var_20], rax
0x140030e6f  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140030e76  lea     rax, [rsp+68h+var_30]
0x140030e7b  mov     r9d, 2
0x140030e81  mov     [rsp+68h+var_48], rax
0x140030e86  call    McGenEventWrite_EventWriteTransfer
0x140030e8b  mov     rcx, [rsp+68h+var_10]
0x140030e90  xor     rcx, rsp; StackCookie
0x140030e93  call    __security_check_cookie
0x140030e98  add     rsp, 60h
0x140030e9c  pop     rbx
0x140030e9d  retn
```
