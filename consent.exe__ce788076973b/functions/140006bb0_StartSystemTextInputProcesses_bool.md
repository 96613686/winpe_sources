# StartSystemTextInputProcesses(bool)

- ea: `0x140006bb0`
- end: `0x140006cfa`
- name: `?StartSystemTextInputProcesses@@YA_N_N@Z`
- size: `330`
- prototype: `bool __fastcall(const struct SystemEventInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001adb0`

## callees

- `0x140006bb0`
- `0x140007af4`
- `0x140007b80`
- `0x14001cd2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006c58`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006c58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006c66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006c66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006cba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006cd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006ce8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006cba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006cd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006ce8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140006be3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140006be3`

## pseudocode

```c
bool __fastcall StartSystemTextInputProcesses(const struct SystemEventInfo *a1)
{
  HANDLE v1; // rbx
  HANDLE SystemEvent; // rax
  bool result; // al
  UACIndicatorControlHost *v4; // rcx
  bool v5; // bl
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+20h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+10h] BYREF

  v1 = g_hSessionEventsNeedProcessing;
  if ( !g_hSessionEventsNeedProcessing )
  {
    SecurityDescriptor = 0;
    v1 = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"O:SYG:SYD:(A;;0x1F0003;;;SY)(A;;0x2;;;WD)",
           1u,
           &SecurityDescriptor,
           0) )
    {
      EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
      *(_QWORD *)&EventAttributes.nLength = 24;
      *(_QWORD *)&EventAttributes.bInheritHandle = 0;
      v1 = CreateEventW(&EventAttributes, 0, 0, L"Global\\{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-server");
      LocalFree(SecurityDescriptor);
    }
    g_hSessionEventsNeedProcessing = v1;
  }
  SystemEvent = g_hStartSystemTextInputProcesses;
  if ( !g_hStartSystemTextInputProcesses )
  {
    SystemEvent = CreateSystemEvent((const struct SystemEventInfo *)off_140020030);
    v1 = g_hSessionEventsNeedProcessing;
    g_hStartSystemTextInputProcesses = SystemEvent;
  }
  if ( !v1 )
    goto LABEL_8;
  if ( !SystemEvent )
  {
    CloseHandle(v1);
    SystemEvent = g_hStartSystemTextInputProcesses;
    g_hSessionEventsNeedProcessing = 0;
LABEL_8:
    if ( SystemEvent )
    {
      CloseHandle(SystemEvent);
      g_hStartSystemTextInputProcesses = 0;
    }
    if ( g_hStartSystemTabtip )
    {
      CloseHandle(g_hStartSystemTabtip);
      g_hStartSystemTabtip = 0;
    }
    return 0;
  }
  result = _SetSystemEvent(a1);
  v5 = result;
  if ( result )
  {
    UACIndicatorControlHost::Activate(v4);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140006bb0  mov     [rsp+arg_0], rbx
0x140006bb5  push    rdi
0x140006bb6  sub     rsp, 40h
0x140006bba  mov     rbx, cs:?g_hSessionEventsNeedProcessing@@3PEAXEA; void * g_hSessionEventsNeedProcessing
0x140006bc1  xor     edi, edi
0x140006bc3  test    rbx, rbx
0x140006bc6  jnz     short loc_140006BF4
0x140006bc8  mov     rcx, cs:off_140020028; StringSecurityDescriptor
0x140006bcf  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x140006bd4  xor     r9d, r9d; SecurityDescriptorSize
0x140006bd7  mov     [rsp+48h+SecurityDescriptor], rdi
0x140006bdc  mov     edx, 1; StringSDRevision
0x140006be1  mov     ebx, edi
0x140006be3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140006be9  test    eax, eax
0x140006beb  jnz     short loc_140006C2F
0x140006bed  mov     cs:?g_hSessionEventsNeedProcessing@@3PEAXEA, rbx; void * g_hSessionEventsNeedProcessing
0x140006bf4  mov     rax, cs:?g_hStartSystemTextInputProcesses@@3PEAXEA; void * g_hStartSystemTextInputProcesses
0x140006bfb  test    rax, rax
0x140006bfe  jz      short loc_140006C71
0x140006c00  test    rbx, rbx
0x140006c03  jnz     loc_140006C90
0x140006c09  test    rax, rax
0x140006c0c  jnz     loc_140006CD3
0x140006c12  mov     rcx, cs:?g_hStartSystemTabtip@@3PEAXEA; hObject
0x140006c19  test    rcx, rcx
0x140006c1c  jnz     loc_140006CE8
0x140006c22  xor     al, al
0x140006c24  mov     rbx, [rsp+48h+arg_0]
0x140006c29  add     rsp, 40h
0x140006c2d  pop     rdi
0x140006c2e  retn
0x140006c2f  mov     rax, [rsp+48h+SecurityDescriptor]
0x140006c34  lea     rcx, [rsp+48h+EventAttributes]; lpEventAttributes
0x140006c39  mov     r9, cs:lpName; lpName
0x140006c40  xor     r8d, r8d; bInitialState
0x140006c43  xor     edx, edx; bManualReset
0x140006c45  mov     [rsp+48h+EventAttributes.lpSecurityDescriptor], rax
0x140006c4a  mov     qword ptr [rsp+48h+EventAttributes.nLength], 18h
0x140006c53  mov     qword ptr [rsp+48h+EventAttributes.bInheritHandle], rdi
0x140006c58  call    cs:__imp_CreateEventW
0x140006c5e  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x140006c63  mov     rbx, rax
0x140006c66  call    cs:__imp_LocalFree
0x140006c6c  jmp     loc_140006BED
0x140006c71  lea     rcx, off_140020030; struct SystemEventInfo *
0x140006c78  call    ?CreateSystemEvent@@YAPEAXPEBUSystemEventInfo@@@Z; CreateSystemEvent(SystemEventInfo const *)
0x140006c7d  mov     rbx, cs:?g_hSessionEventsNeedProcessing@@3PEAXEA; void * g_hSessionEventsNeedProcessing
0x140006c84  mov     cs:?g_hStartSystemTextInputProcesses@@3PEAXEA, rax; void * g_hStartSystemTextInputProcesses
0x140006c8b  jmp     loc_140006C00
0x140006c90  test    rax, rax
0x140006c93  jz      short loc_140006CAE
0x140006c95  call    ?_SetSystemEvent@@YA_NPEBUSystemEventInfo@@@Z; _SetSystemEvent(SystemEventInfo const *)
0x140006c9a  movzx   ebx, al
0x140006c9d  test    al, al
0x140006c9f  jz      short loc_140006C24
0x140006ca1  call    ?Activate@UACIndicatorControlHost@@QEAAXXZ; UACIndicatorControlHost::Activate(void)
0x140006ca6  movzx   eax, bl
0x140006ca9  jmp     loc_140006C24
0x140006cae  test    rbx, rbx
0x140006cb1  jz      loc_140006C09
0x140006cb7  mov     rcx, rbx; hObject
0x140006cba  call    cs:__imp_CloseHandle
0x140006cc0  mov     rax, cs:?g_hStartSystemTextInputProcesses@@3PEAXEA; void * g_hStartSystemTextInputProcesses
0x140006cc7  mov     cs:?g_hSessionEventsNeedProcessing@@3PEAXEA, rdi; void * g_hSessionEventsNeedProcessing
0x140006cce  jmp     loc_140006C09
0x140006cd3  mov     rcx, rax; hObject
0x140006cd6  call    cs:__imp_CloseHandle
0x140006cdc  mov     cs:?g_hStartSystemTextInputProcesses@@3PEAXEA, rdi; void * g_hStartSystemTextInputProcesses
0x140006ce3  jmp     loc_140006C12
0x140006ce8  call    cs:__imp_CloseHandle
0x140006cee  mov     cs:?g_hStartSystemTabtip@@3PEAXEA, rdi; void * g_hStartSystemTabtip
0x140006cf5  jmp     loc_140006C22
```
