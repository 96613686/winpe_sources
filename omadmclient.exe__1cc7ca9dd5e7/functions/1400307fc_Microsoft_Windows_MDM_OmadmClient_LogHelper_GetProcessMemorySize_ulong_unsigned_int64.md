# Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProcessMemorySize(ulong,unsigned __int64 *)

- ea: `0x1400307fc`
- end: `0x140030992`
- name: `?GetProcessMemorySize@LogHelper@OmadmClient@MDM@Windows@Microsoft@@IEAAJKPEA_K@Z`
- size: `406`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::LogHelper *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140030d40`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000d71c`
- `0x14000d778`
- `0x1400307fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030909`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030946`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003087f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003087f`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1400308f9`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1400308f9`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProcessMemorySize(
        Microsoft::Windows::MDM::OmadmClient::LogHelper *this,
        DWORD a2,
        unsigned __int64 *a3)
{
  HANDLE v5; // rdi
  signed int LastError; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  signed int v10; // eax
  int v11; // [rsp+30h] [rbp-98h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v13; // [rsp+88h] [rbp-40h]
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+90h] [rbp-38h] BYREF
  int *v15; // [rsp+A0h] [rbp-28h]
  __int64 v16; // [rsp+A8h] [rbp-20h]

  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v11 = 84;
    v15 = &v11;
    v16 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      (__int64)a3,
      2u,
      &v14);
  }
  *a3 = 0;
  if ( a2 )
  {
    v5 = OpenProcess(0x400u, 0, a2);
    if ( !v5 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_7:
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v7, OmaDmClientFunctionReturnValueEvent, 84, v8);
      return v8;
    }
    memset_0(&ppsmemCounters, 0, 0x50u);
    ppsmemCounters.cb = 80;
    if ( !K32GetProcessMemoryInfo(v5, &ppsmemCounters, 0x50u) )
    {
      v10 = GetLastError();
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      CloseHandle(v5);
      goto LABEL_7;
    }
    *a3 = v13;
    CloseHandle(v5);
  }
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    McTemplateU0qq_EventWriteTransfer(this, OmaDmClientFunctionReturnValueEvent, 84, 0);
  return 0;
}

```

## disassembly

```asm
0x1400307fc  mov     r11, rsp
0x1400307ff  mov     [r11+8], rbx
0x140030803  push    rdi
0x140030804  sub     rsp, 0C0h
0x14003080b  mov     rax, cs:__security_cookie
0x140030812  xor     rax, rsp
0x140030815  mov     [rsp+0C8h+var_18], rax
0x14003081d  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140030824  mov     rbx, r8
0x140030827  mov     edi, edx
0x140030829  jz      short loc_140030866
0x14003082b  lea     rax, [rsp+0C8h+var_98]
0x140030830  mov     [rsp+0C8h+var_98], 54h ; 'T'
0x140030838  mov     [r11-28h], rax
0x14003083c  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x140030843  lea     rax, [r11-38h]
0x140030847  mov     qword ptr [r11-20h], 4
0x14003084f  mov     r9d, 2
0x140030855  mov     [rsp+0C8h+var_A8], rax
0x14003085a  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140030861  call    McGenEventWrite_EventWriteTransfer
0x140030866  mov     qword ptr [rbx], 0
0x14003086d  test    edi, edi
0x14003086f  jz      loc_140030952
0x140030875  mov     r8d, edi; dwProcessId
0x140030878  xor     edx, edx; bInheritHandle
0x14003087a  mov     ecx, 400h; dwDesiredAccess
0x14003087f  call    cs:__imp_OpenProcess
0x140030886  nop     dword ptr [rax+rax+00h]
0x14003088b  mov     rdi, rax
0x14003088e  test    rax, rax
0x140030891  jnz     short loc_1400308D3
0x140030893  call    cs:__imp_GetLastError
0x14003089a  nop     dword ptr [rax+rax+00h]
0x14003089f  mov     ebx, eax
0x1400308a1  test    eax, eax
0x1400308a3  jle     short loc_1400308AE
0x1400308a5  movzx   ebx, ax
0x1400308a8  or      ebx, 80070000h
0x1400308ae  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x1400308b5  jz      short loc_1400308CC
0x1400308b7  mov     r9d, ebx
0x1400308ba  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x1400308c1  mov     r8d, 54h ; 'T'
0x1400308c7  call    McTemplateU0qq_EventWriteTransfer
0x1400308cc  mov     eax, ebx
0x1400308ce  jmp     loc_140030970
0x1400308d3  xor     edx, edx; Val
0x1400308d5  lea     rcx, [rsp+0C8h+ppsmemCounters]; void *
0x1400308da  lea     r8d, [rdx+50h]; Size
0x1400308de  call    memset_0
0x1400308e3  mov     r8d, 50h ; 'P'; cb
0x1400308e9  mov     [rsp+0C8h+ppsmemCounters.cb], 50h ; 'P'
0x1400308f1  lea     rdx, [rsp+0C8h+ppsmemCounters]; ppsmemCounters
0x1400308f6  mov     rcx, rdi; Process
0x1400308f9  call    cs:__imp_K32GetProcessMemoryInfo
0x140030900  nop     dword ptr [rax+rax+00h]
0x140030905  test    eax, eax
0x140030907  jnz     short loc_140030938
0x140030909  call    cs:__imp_GetLastError
0x140030910  nop     dword ptr [rax+rax+00h]
0x140030915  mov     ebx, eax
0x140030917  test    eax, eax
0x140030919  jle     short loc_140030924
0x14003091b  movzx   ebx, ax
0x14003091e  or      ebx, 80070000h
0x140030924  mov     rcx, rdi; hObject
0x140030927  call    cs:__imp_CloseHandle
0x14003092e  nop     dword ptr [rax+rax+00h]
0x140030933  jmp     loc_1400308AE
0x140030938  mov     rax, [rsp+0C8h+var_40]
0x140030940  mov     rcx, rdi; hObject
0x140030943  mov     [rbx], rax
0x140030946  call    cs:__imp_CloseHandle
0x14003094d  nop     dword ptr [rax+rax+00h]
0x140030952  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140030959  jz      short loc_14003096E
0x14003095b  xor     r9d, r9d
0x14003095e  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140030965  lea     r8d, [r9+54h]
0x140030969  call    McTemplateU0qq_EventWriteTransfer
0x14003096e  xor     eax, eax
0x140030970  mov     rcx, [rsp+0C8h+var_18]
0x140030978  xor     rcx, rsp; StackCookie
0x14003097b  call    __security_check_cookie
0x140030980  mov     rbx, [rsp+0C8h+arg_0]
0x140030988  add     rsp, 0C0h
0x14003098f  pop     rdi
0x140030990  retn
```
