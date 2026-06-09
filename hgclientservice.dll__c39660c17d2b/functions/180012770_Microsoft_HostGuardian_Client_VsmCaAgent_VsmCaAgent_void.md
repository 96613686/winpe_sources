# Microsoft::HostGuardian::Client::VsmCaAgent::~VsmCaAgent(void)

- ea: `0x180012770`
- end: `0x1800127dd`
- name: `??1VsmCaAgent@Client@HostGuardian@Microsoft@@AEAA@XZ`
- size: `109`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::VsmCaAgent *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016a20`

## callees

- `0x180001770`
- `0x1800077a0`
- `0x180012770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800127c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800127c4`

## string_xrefs

- `0x180012799`: `CAAgent destroyed.`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::~VsmCaAgent(
        Microsoft::HostGuardian::Client::VsmCaAgent *this,
        __int64 a2,
        __int64 a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF

  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v4[3] = 38;
    v4[2] = L"CAAgent destroyed.";
    McGenEventWrite_EventWriteTransfer(this, ServiceDebugInformational, a3, 2, v4);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
}

```

## disassembly

```asm
0x180012770  mov     r11, rsp
0x180012773  push    rbx
0x180012774  sub     rsp, 60h
0x180012778  mov     rax, cs:__security_cookie
0x18001277f  xor     rax, rsp
0x180012782  mov     [rsp+68h+var_18], rax
0x180012787  mov     r9d, 2
0x18001278d  mov     rbx, rcx
0x180012790  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, r9b
0x180012797  jz      short loc_1800127C0
0x180012799  lea     rax, aCaagentDestroy; "CAAgent destroyed."
0x1800127a0  mov     qword ptr [r11-20h], 26h ; '&'
0x1800127a8  mov     [r11-28h], rax
0x1800127ac  lea     rdx, ServiceDebugInformational
0x1800127b3  lea     rax, [r11-38h]
0x1800127b7  mov     [r11-48h], rax
0x1800127bb  call    McGenEventWrite_EventWriteTransfer
0x1800127c0  lea     rcx, [rbx+38h]; lpCriticalSection
0x1800127c4  call    cs:__imp_DeleteCriticalSection
0x1800127ca  mov     rcx, [rsp+68h+var_18]
0x1800127cf  xor     rcx, rsp; StackCookie
0x1800127d2  call    __security_check_cookie
0x1800127d7  add     rsp, 60h
0x1800127db  pop     rbx
0x1800127dc  retn
```
