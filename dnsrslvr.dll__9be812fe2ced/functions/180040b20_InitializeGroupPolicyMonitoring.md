# InitializeGroupPolicyMonitoring

- ea: `0x180040b20`
- end: `0x180040bd7`
- name: `InitializeGroupPolicyMonitoring`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002c980`

## callees

- `0x180040b20`
- `0x180048708`
- `0x18004ccd8`
- `0x180086700`
- `0x180086e44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b87`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040b4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040b4f`
- `ext-ms-win-gpapi-grouppolicy-l1-1-0!RegisterGPNotificationInternalWorker` at `0x180040b7d`
- `ext-ms-win-gpapi-grouppolicy-l1-1-0!RegisterGPNotificationInternalWorker` at `0x180040b7d`

## pseudocode

```c
__int64 InitializeGroupPolicyMonitoring()
{
  DWORD LastError; // ebx
  int v1; // ecx

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 30, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
  g_hGroupPolicyChange = CreateEventW(0, 0, 0, 0);
  if ( !g_hGroupPolicyChange )
    goto LABEL_7;
  if ( !(unsigned __int8)IsRegisterGPNotificationInternalWorkerPresent() )
  {
    LastError = 127;
LABEL_8:
    CleanupGroupPolicyMonitoring();
    goto LABEL_10;
  }
  if ( !(unsigned int)RegisterGPNotificationInternalWorker(g_hGroupPolicyChange, 1) )
  {
LABEL_7:
    LastError = GetLastError();
    if ( !LastError )
      goto LABEL_10;
    goto LABEL_8;
  }
  LastError = 0;
  g_isRegisteredWithGroupPolicy = 1;
LABEL_10:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_Dq(
      v1,
      31,
      (unsigned int)WPP_f740467901d037f9bb0724a7406bee3b_Traceguids,
      LastError,
      (__int64)g_hGroupPolicyChange);
  return LastError;
}

```

## disassembly

```asm
0x180040b20  push    rbx
0x180040b22  sub     rsp, 30h
0x180040b26  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180040b2d  jz      short loc_180040B45
0x180040b2f  mov     edx, 1Eh
0x180040b34  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x180040b3b  mov     ecx, 40Bh
0x180040b40  call    WPP_SF_
0x180040b45  xor     r9d, r9d; lpName
0x180040b48  xor     r8d, r8d; bInitialState
0x180040b4b  xor     edx, edx; bManualReset
0x180040b4d  xor     ecx, ecx; lpEventAttributes
0x180040b4f  call    cs:__imp_CreateEventW
0x180040b55  mov     cs:g_hGroupPolicyChange, rax
0x180040b5c  test    rax, rax
0x180040b5f  jz      short loc_180040B87
0x180040b61  call    IsRegisterGPNotificationInternalWorkerPresent
0x180040b66  test    al, al
0x180040b68  jnz     short loc_180040B71
0x180040b6a  mov     ebx, 7Fh
0x180040b6f  jmp     short loc_180040B93
0x180040b71  mov     rcx, cs:g_hGroupPolicyChange
0x180040b78  mov     edx, 1
0x180040b7d  call    cs:__imp_RegisterGPNotificationInternalWorker
0x180040b83  test    eax, eax
0x180040b85  jnz     short loc_180040B9A
0x180040b87  call    cs:__imp_GetLastError
0x180040b8d  mov     ebx, eax
0x180040b8f  test    eax, eax
0x180040b91  jz      short loc_180040BA6
0x180040b93  call    CleanupGroupPolicyMonitoring
0x180040b98  jmp     short loc_180040BA6
0x180040b9a  xor     ebx, ebx
0x180040b9c  mov     cs:g_isRegisteredWithGroupPolicy, 1
0x180040ba6  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180040bad  jz      short loc_180040BCF
0x180040baf  mov     rax, cs:g_hGroupPolicyChange
0x180040bb6  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x180040bbd  mov     edx, 1Fh
0x180040bc2  mov     [rsp+38h+var_18], rax
0x180040bc7  mov     r9d, ebx
0x180040bca  call    WPP_SF_Dq
0x180040bcf  mov     eax, ebx
0x180040bd1  add     rsp, 30h
0x180040bd5  pop     rbx
0x180040bd6  retn
```
