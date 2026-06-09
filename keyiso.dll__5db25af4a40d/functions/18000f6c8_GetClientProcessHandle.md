# _GetClientProcessHandle

- ea: `0x18000f6c8`
- end: `0x18000f786`
- name: `_GetClientProcessHandle`
- size: `190`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f88c`

## callees

- `0x180003cf0`
- `0x18000f6c8`

## import_xrefs

- `ntdll!NtClose` at `0x18000f76c`
- `ntdll!NtClose` at `0x18000f76c`
- `ntdll!NtOpenProcess` at `0x18000f72b`
- `ntdll!NtOpenProcess` at `0x18000f72b`

## string_xrefs

- `0x18000f73d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall GetClientProcessHandle(__int64 a1, void **a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  void *v5; // rcx
  _CLIENT_ID ClientId; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *ProcessHandle; // [rsp+70h] [rbp+10h] BYREF

  ProcessHandle = 0;
  ClientId.UniqueProcess = (HANDLE)*(unsigned int *)(a1 + 16);
  ClientId.UniqueThread = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v3 = NtOpenProcess(&ProcessHandle, 0x440u, &ObjectAttributes, &ClientId);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = 0;
    *a2 = ProcessHandle;
    v4 = 0;
    ProcessHandle = 0;
  }
  else
  {
    DebugTraceError((unsigned int)v3, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 226);
    v5 = ProcessHandle;
  }
  if ( v5 )
    NtClose(v5);
  return v4;
}

```

## disassembly

```asm
0x18000f6c8  mov     [rsp-8+arg_8], rbx
0x18000f6cd  mov     [rsp-8+arg_10], rdi
0x18000f6d2  push    rbp
0x18000f6d3  mov     rbp, rsp
0x18000f6d6  sub     rsp, 60h
0x18000f6da  xor     eax, eax
0x18000f6dc  mov     [rbp+ProcessHandle], 0
0x18000f6e4  mov     qword ptr [rbp+ObjectAttributes.Attributes], rax
0x18000f6e8  lea     r9, [rbp+ClientId]; ClientId
0x18000f6ec  mov     eax, [rcx+10h]
0x18000f6ef  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000f6f3  mov     rdi, rdx
0x18000f6f6  mov     [rbp+ClientId.UniqueProcess], rax
0x18000f6fa  xorps   xmm0, xmm0
0x18000f6fd  mov     [rbp+ClientId.UniqueThread], 0
0x18000f705  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18000f709  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000f711  mov     edx, 440h; DesiredAccess
0x18000f716  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000f71e  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18000f726  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f72b  call    cs:__imp_NtOpenProcess
0x18000f731  mov     ebx, eax
0x18000f733  test    eax, eax
0x18000f735  jns     short loc_18000F758
0x18000f737  mov     r9d, 0E2h
0x18000f73d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f744  lea     rdx, aStatus; "Status"
0x18000f74b  mov     ecx, eax
0x18000f74d  call    DebugTraceError
0x18000f752  mov     rcx, [rbp+ProcessHandle]
0x18000f756  jmp     short loc_18000F767
0x18000f758  mov     rax, [rbp+ProcessHandle]
0x18000f75c  xor     ecx, ecx; Handle
0x18000f75e  mov     [rdi], rax
0x18000f761  xor     ebx, ebx
0x18000f763  mov     [rbp+ProcessHandle], rcx
0x18000f767  test    rcx, rcx
0x18000f76a  jz      short loc_18000F772
0x18000f76c  call    cs:__imp_NtClose
0x18000f772  lea     r11, [rsp+60h+var_s0]
0x18000f777  mov     eax, ebx
0x18000f779  mov     rbx, [r11+18h]
0x18000f77d  mov     rdi, [r11+20h]
0x18000f781  mov     rsp, r11
0x18000f784  pop     rbp
0x18000f785  retn
```
